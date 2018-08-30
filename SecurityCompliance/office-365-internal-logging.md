---
title: Registro interno de Office 365 para ingeniería de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/18/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Obtener una explicación de cómo interno registro para Office 365 ingeniería de equipos de works.
ms.openlocfilehash: 1a613584b6b815524435acb20db7a8022d95e3bc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535904"
---
# <a name="internal-logging-for-office-365-engineering"></a>Registro interno para el equipo de ingeniería de Office 365
Además de los eventos y los datos de registro disponibles para los clientes, también es un sistema de colección de datos de registro interno que está disponible para los ingenieros de Office 365. Hay muchos tipos diferentes de datos de registro se cargan desde los servidores de Office 365 a un datos internos, big informática servicio denominado Cosmos. Cada equipo de servicio carga los registros de auditoría de sus respectivos servidores en la base de datos Cosmos agregación y análisis. Esta transferencia de datos se produce a través de una conexión TLS 140-2-validan FIPS en específicamente aprobados puertos y protocolos mediante una herramienta de automatización de la propiedad denominada el cargador de datos de Office (ODL).

Los equipos de servicio use Cosmos como un repositorio centralizado para llevar a cabo un análisis de uso de la aplicación, para medir el rendimiento del sistema y operativa y para buscar anomalías y patrones que puedan indicar problemas o problemas de seguridad. Cada equipo de servicio carga una línea base de los registros en Cosmos, dependiendo de lo desea buscar para analizar, que a menudo incluyen:
- Registros de eventos
- Registros de AppLocker
- Datos de rendimiento
- Datos de System Center
- Registros de detalles de llamadas
- Calidad de la experiencia de datos
- Registros del servidor Web de IIS
- Registros de SQL Server
- Datos de registro del sistema
- Registros de auditoría de seguridad

Antes de cargar datos en Cosmos, la aplicación de ODL usa un servicio de depuración para ocultar los campos que contienen datos de los clientes, como información de inquilinos y la información de identificación para el usuario final y reemplace esos campos con un valor hash. Los registros de anonymized y hash se volver a escribir y, a continuación, se cargan en Cosmos. Los equipos de servicio ejecutan consultas con ámbito en sus datos en Cosmos para la correlación, alertas y los informes. El período de retención de datos de registro de auditoría en Cosmos está determinado por los equipos de servicio; mayoría de los datos de registro de auditoría se conserva durante 90 días o más para admitir las investigaciones de incidentes de seguridad y para cumplir los requisitos de retención de las normativas.

Acceso a datos de Office 365 almacenados en Cosmos está restringido a personal no autorizado. Microsoft restringe la administración de la funcionalidad de auditoría para el subconjunto limitado de los miembros del equipo de servicio que son responsables de la funcionalidad de auditoría. Estos miembros del equipo no tienen la capacidad de modificar o eliminar datos de Cosmos y todos los cambios a los mecanismos de registro para Cosmos se registren y que se auditan.

Cada equipo de servicio tiene acceso a sus datos de registro para el análisis mediante la autorización de determinadas aplicaciones para llevar a cabo análisis específico. Por ejemplo, el equipo de seguridad de Office 365 usa datos desde Cosmos a través de un analizador de registro de eventos de propietario para correlacionar, alerta y generar informes útiles en posibles actividades sospechosas en el entorno de producción de Office 365. Los informes de estos datos se usan para corregir las vulnerabilidades y para mejorar el rendimiento general del servicio. Si un informe o alerta específica aún más requiere investigación, puede solicitar personal de servicio que se puede importar datos en el servicio Office 365. Desde el registro específico que se está importando desde Cosmos está en cifrado y personal de servicio no tienen acceso a las claves de descifrado, el registro de destino se pasa mediante programación a través de un servicio de descifrado que devuelve los resultados de ámbito para el personal de servicio autorizado. Las vulnerabilidades localizadas de este ejercicio se notifican y cambie el uso de canales de administración de incidentes de seguridad estándar de Microsoft.
