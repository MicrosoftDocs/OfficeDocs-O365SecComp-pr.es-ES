---
title: BitLocker de Office 365 para el cifrado
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: Información acerca de BitLocker para el cifrado en la nube.'
ms.openlocfilehash: 86c6bc9282d7c2b0a7d4e08d4636c8f9c2fa5db8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536212"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker y Administrador de claves distribuidas (DKM) para el cifrado
Los servidores de Office 365 usar BitLocker para cifrar las unidades de disco que contiene los datos de cliente en reposo en el nivel de volumen. El cifrado de BitLocker es una característica de protección de datos que está integrada en Windows. BitLocker es una de las tecnologías usadas para protegerse frente a las amenazas en caso de que hay transcurre de otros procesos o controles (por ejemplo, control de acceso o reciclado de hardware) que podrían conducir a una persona acceso físico a los discos que contiene los datos de cliente. En este caso, BitLocker elimina la posibilidad de robo de datos o exposición debido a los discos y equipos perdidos, robados o inapropiados.

BitLocker se implementa con el cifrado de 256 bits estándar de cifrado avanzado (AES) en los discos que contienen los datos de cliente en Exchange Online, SharePoint Online y Skype para la empresa. Sectores de disco se cifran con un completo volumen cifrado de clave (FVEK), que se cifran con el volumen clave maestra (VMK), que a su vez está enlazado para el módulo de plataforma segura (TPM) en el servidor. La VMK directamente protege la FVEK y por lo tanto, proteger la VMK se convierte en crítico. La siguiente ilustración muestra un ejemplo de la cadena de protección de clave de BitLocker para un servidor determinado (en este caso, con un servidor de Exchange Online).

En la siguiente tabla describe la cadena de protección de clave de BitLocker para un servidor determinado (en este caso, un servidor de Exchange Online).

| PROTECTOR DE CLAVE | GRANULARIDAD | ¿CÓMO GENERADO? | ¿DÓNDE SE ALMACENA? | PROTECCIÓN |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| Clave externa AES de 256 bits | Por servidor | API de BitLocker | TPM o secreto seguro | Caja de seguridad y Control de acceso |
|  |  |  | Registro del servidor de buzón de correo | Cifrado de TPM |
| Contraseña numérica de 48 dígitos | Por disco | API de BitLocker | Active Directory | Caja de seguridad y Control de acceso |
| Certificado X.509 como agente de recuperación de datos (DRA) también se denomina Protector de clave pública | Entorno (por ejemplo, Exchange Online multitenant) | Entidad de certificación de Microsoft | Sistema de compilación | No hay un usuario tiene la contraseña completa a la clave privada. La contraseña está bajo protección física. |


Administración de claves de BitLocker implica la administración de claves de recuperación que se usan para desbloquear o recuperar los discos cifrados en un centro de datos de Office 365. Office 365 almacena las claves maestras en un compartido de archivos protegido, sólo se puede tener acceso por personas que han sido filtran y aprobado. Las credenciales para las claves se almacenan en un repositorio seguro para los datos de control de acceso (lo que llamamos "almacenamiento secreto"), lo que requiere un alto grado de elevación y administración de aprobaciones tener acceso mediante una herramienta de elevación de acceso just-in-time.

BitLocker es compatible con las claves que se dividen en dos categorías de administración:
- Claves administradas de BitLocker, que generalmente son de corta duración y vinculado a la duración de una instancia de sistema operativo instalada en un servidor o en un disco determinado. Estas claves se eliminan o restablecerse durante la reinstalación del servidor o el formato de disco.
- Claves de recuperación de BitLocker, que se administran fuera de BitLocker pero se usa para el descifrado de disco. BitLocker usa claves de recuperación para el escenario en el que se vuelve a instalar un sistema operativo y los discos de datos cifrados ya existen. Las claves de recuperación también se usan por disponibilidad administrada supervisión sondeos en Exchange Online donde es posible que necesite un Respondedor para desbloquear un disco.

Volúmenes protegidos por BitLocker se cifran con una clave de cifrado de volumen completo, que a su vez se cifra con una clave maestra de volumen. BitLocker usa algoritmos compatibles con FIPS para garantizar que las claves de cifrado nunca se almacenan o enviadas a través de la conexión en texto sin cifrar. La implementación de Office 365 de atención al cliente-en-rest-protección de datos no se desvían de la implementación de BitLocker predeterminada.