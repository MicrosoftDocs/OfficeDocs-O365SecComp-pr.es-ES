---
title: Office 365 BitLocker para cifrado
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: 'Resumen: información sobre BitLocker para el cifrado en la nube.'
ms.openlocfilehash: bbe32f642f214d27c7f9f82c39b11237556d51bf
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600950"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker y Administrador de claves distribuidas (DKM) para el cifrado

Los servidores de Office 365 usan BitLocker para cifrar las unidades de disco que contienen datos de clientes en reposo en el nivel de volumen. El cifrado de BitLocker es una característica de protección de datos que se integra en Windows. BitLocker es una de las tecnologías que se usan para protegerse frente a amenazas en caso de que haya fallos en otros procesos o controles (por ejemplo, el control de acceso o el reciclaje de hardware) que puedan dar lugar a que alguien obtenga acceso físico a los discos que contienen datos de clientes. En este caso, BitLocker elimina el potencial de robo de datos o de exposición debido a la pérdida, robo o desactivación de discos y equipos de forma inadecuada.

BitLocker se implementa con el cifrado estándar de cifrado avanzado (AES) 256 de bits en discos que contienen datos de cliente en Exchange Online, SharePoint Online y Skype empresarial. Los sectores de disco se cifran con una clave de cifrado de volumen completo (FVEK), que se cifra con la clave maestra de volumen (VMK), que a su vez se enlaza al módulo de plataforma de confianza (TPM) en el servidor. El VMK protege la FVEK de forma directa y, por lo tanto, la protección de la VMK se convierte en crítica. En la siguiente figura se muestra un ejemplo de la cadena de protección de claves de BitLocker para un servidor determinado (en este caso, mediante un servidor de Exchange Online).

En la siguiente tabla se describe la cadena de protección de claves de BitLocker para un servidor determinado (en este caso, un servidor de Exchange Online).

| PROTECTOR DE CLAVE | GRANULARIDAD | ¿CÓMO SE GENERA? | ¿DÓNDE SE ALMACENA? | PROTEGE |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| Clave externa de AES 256 bits | Por servidor | API de BitLocker | TPM o secreto seguro | Liquidación/control de acceso |
|  |  |  | Registro del servidor de buzones | TPM cifrado |
| Contraseña numérica de 48 dígitos | Por disco | API de BitLocker | Active Directory | Liquidación/control de acceso |
| El certificado X. 509 como agente de recuperación de datos (DRA) también denominado protector de clave pública | Entorno (por ejemplo, multiempresa de Exchange Online) | CA de Microsoft | Sistema de compilación | Ningún usuario tiene la contraseña completa a la clave privada. La contraseña está en protección física. |


La administración de claves de BitLocker implica la administración de las claves de recuperación que se usan para desbloquear o recuperar discos cifrados en un centro de recursos de Office 365. Office 365 almacena las claves maestras en un recurso compartido seguro, solo accesible para las personas que se han protegido y se han aprobado. Las credenciales de las claves se almacenan en un repositorio protegido para los datos de control de acceso (lo que se denomina un "almacén secreto"), que requiere un alto nivel de aprobaciones de elevación y administración para obtener acceso mediante una herramienta de elevación de acceso a tiempo.

BitLocker admite claves que se dividen en dos categorías de administración:

- Claves administradas por BitLocker, que suelen ser de corta duración y están vinculadas a la duración de una instancia de sistema operativo instalada en un servidor o a un disco determinado. Estas claves se eliminan y restablecen durante la reinstalación del servidor o el formato de disco.

- Claves de recuperación de BitLocker, que se administran fuera de BitLocker pero se usan para el descifrado de disco. BitLocker usa claves de recuperación para el escenario en el que se reinstala un sistema operativo y los discos de datos cifrados ya existen. Las claves de recuperación también las usan los sondeos de supervisión de disponibilidad administrada en Exchange online donde un respondedor puede necesitar desbloquear un disco.

Los volúmenes protegidos por BitLocker están cifrados con una clave de cifrado de volumen completo que, a su vez, se cifra con una clave maestra de volumen. BitLocker usa algoritmos compatibles con FIPS para garantizar que las claves de cifrado nunca se almacenan ni se envían a través de la red sin cifrar. La implementación de Office 365 de la protección de datos en reposo de los clientes no se desvía de la implementación de BitLocker predeterminada.