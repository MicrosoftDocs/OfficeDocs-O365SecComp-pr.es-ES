---
title: Controles de personal de Office 365
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
description: 'Resumen: Información general del personal de Microsoft de filtrado recomendados para Office 365.'
ms.openlocfilehash: 282a361dadba344ace557fe2056908aaea9fdfaa
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22535947"
---
# <a name="office-365-personnel-controls"></a>Controles de personal de Office 365 

Personal de filtrado, que es el proceso de revisión y validación de comportamiento pasado y el estado de una persona, es un control de mitigación importante para evitar que el compromiso de servicio de Office 365. Mientras comportamiento pasado no es un perfecto predicción del comportamiento futuras de una persona, ayuda a identificar posibles actores bad. Personal de filtrado estándar de Microsoft se aplica a todos los empleados de Microsoft, jornada y personal contingente implicado en el desarrollo, la operación o la entrega de servicios en línea a gubernamentales o los clientes comerciales en la nube. Estándares de filtrado para la nube nacional entornos que no son operados por Microsoft están definidos por el personal de socio operativo para cada entorno específico.

## <a name="microsofts-personnel-screening-standard"></a>Personal de Microsoft estándar de filtrado

Personal de Microsoft de filtrado recomendados para Office 365 se alinea con los estándares corporativos y los controles de National Institute of Standards and Technology (NIST) de Microsoft para el personal de filtrado. Personal de Microsoft que requieren acceso a la siguiente está sujetos a personal de filtrado estándar del Microsoft:
- Acceso físico a centros de datos, CO-ubicaciones, salones protegidos, jaulas, los armarios de servidores o sitios perimetral que proporcionan la infraestructura que soporta servicios en línea para el gobierno o los clientes comerciales en la nube.
- Acceso lógico a gubernamentales o comercial en la nube proporciona a través de entornos administrados específicos de datos de cliente.
    - Administración de acceso a dispositivos y servicios de transporte o almacenan gubernamentales o comercial en la nube los datos de cliente de red.

Eventos específicos relacionados con el personal que desencadenan los requisitos de filtrado se incluyen:
- Nuevo personal de Microsoft se coloca en funciones donde filtrado es un requisito definido.
- Personal interno de Microsoft transferir o mover a un rol existente que actualmente incluye filtrado como un requisito definido.
- Roles existentes que cambiar ámbito para incluir filtrado como un requisito definido.

## <a name="screening-enforcement-criteria"></a>Aplicación criterios de filtrado

Para asegurarse de que sólo el personal de aprobado tiene acceso a los datos de cliente o en entornos que requieren la comprobación de seguridad, se aplica los siguientes criterios de aplicación:

**Solo en entornos de nube de Estados Unidos**:
- Acceso a datos de los clientes o entornos que requieren filtrado sólo debe permitirse después de finalizada la adjudicación y se pasan los requisitos de filtrado.
- Personal de Microsoft que ya no necesita tener acceso a los datos de cliente o entornos relacionados debe tener acceso quitado al salir de Microsoft o mover a un nuevo rol.
- Personal de Microsoft debe dejar las tarjetas inteligentes entorno protegida con administración antes de salir de los Estados Unidos.

**Entornos nacionales en la nube**:
- Personal de confianza de operador o datos de terceros es responsable de administrar y exigir un acceso para entornos nacionales en la nube.

Dentro de entornos de servicios de nube de Microsoft, el acceso está restringido según el rol de la persona y el tipo de datos implicados, como se detalla en la tabla siguiente. Personal cualificado o no que se encuentra físicamente fuera de Estados Unidos no tiene permiso para tener acceso a datos de clientes dentro de una nube de Estados Unidos. Acceso a entornos de nube nacional está restringido para que el personal de Microsoft no tienen técnicas de acceso a datos de los clientes o sistemas que contienen los datos de cliente, sin la aprobación por el Administrador de confianza de operador o datos de terceros.

| Rol | Acceso a datos de clientes | Acceso a datos del sistema |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------|---------------------------------|
| Personal cualificado ubicado físicamente en los Estados Unidos | Puede contener | Puede contener |
| Personal cualificado físicamente que se encuentra fuera de Estados Unidos | No permitido | Puede contener |
| Acceso de excepción internacional para Microsoft Staff: permite el acceso lógico para el personal de Microsoft que no se encuentran en el país donde es el gobierno o comercial de atención al cliente de datos en reposo | No permitido | Puede contener |
| No completos de personal (personal sin trama que requieren un escolta por personal cualificado) | Puede contener con autorización | Puede contener con supervisión escolta |


## <a name="microsoft-pre-employment-screening"></a>Filtrado de Microsoft antes de la contratación

Donde la legislación local permite para él, departamento de seguridad Global de Microsoft lleva a cabo antes de la contratación filtrado. Se trata de una investigación de fondo formal que incluye los siguientes criterios:
- Una comprobación (por ejemplo, para la integridad y precisión) de reanudación del candidato
- Confirmación de cualificaciones académicos y profesionales
- Investigación de cualquier pérdida de credenciales profesionales
- Comprobación de empresas de tres últimos
- Una comprobación de los registros de policía de condena delito
- Confirmación de identidad de una identificación gubernamental
- Verificación de crédito cuando resulte apropiado

Rescreening periódica o fondo adicional es posible que las comprobaciones de necesarios para ciertas administración, seguridad u otras funciones, incluidos, pero sin limitarse a los empleados en función de los Estados Unidos en roles que requieren acceso a los datos de cliente. Para el personal contingente, el contrato con el tercero especifica los requisitos de Microsoft para el filtrado que debe llevar a cabo el tercero. Para las comprobaciones de fondo, la empresa de otro fabricante es responsable de proporcionar a la verificación de Microsoft que se ha realizado una comprobación de segundo plano. Los resultados de la comprobación de fondo se reciben normalmente a través de correo electrónico del departamento de recursos humanos de terceros. Los empleados internacionales de personal con contrato pueden ser exentos del proceso debido a las leyes en países que prohíben fondo comprobaciones de filtrado de fondo.

## <a name="microsoft-employment-screening"></a>Filtrado de empleo de Microsoft
Desde 2004, Microsoft dispone de las personas necesarias para pasar de una pantalla de siete años penales registro para felonies y misdemeanors y para comprobar su educación y el historial de empleo, como parte de filtrado en los Estados Unidos para empleados de jornada y antes de la contratación.

En los Estados Unidos, antes de asignar cualquier empleado de Microsoft o cualquier subcontratista asignado por Microsoft para proporcionar servicios relacionados con Office 365, Microsoft va a llevar a cabo y hacer que su subcontratista llevar a cabo una comprobación de segundo plano que consta de una seguridad Social número de seguimiento y comprobación de grabación penal. Los datos de esta comprobación de fondo se utilizan como un factor en la decisión de contratación. La comprobación de registro penales incluye una comprobación de registros criminales siete años delito y misdemeanor de registros federales, Estados y provincia (según corresponda).

Como una condición de empleo, en el momento de contratación, todos los empleados de Microsoft son necesarios para iniciar sesión confidencialidad y acuerdos de confidencialidad y para comprobar que ha revisado el manual del empleado de Microsoft.

## <a name="microsoft-cloud-background-check"></a>Verificación de fondo de la nube de Microsoft
Una comprobación de fondo de la nube de Microsoft es necesaria para candidatos ser contratado como los empleados que proporciona servicios relacionados con Office 365 en los Estados Unidos. Los empleados de Microsoft en los Estados Unidos con acceso a los datos de cliente deben seguir el proceso de comprobación de fondo de la nube de Microsoft, que es necesaria para todos los servicios de Office 365. Fuera de los Estados Unidos, el proceso varía. Por ejemplo, la Cloud Microsoft para Alemania usa un modelo de aprobación de administrador de datos de confianza, que está diseñado para asegurarse de que el Administrador de datos de confianza (una empresa alemán) y no con Microsoft, está en un control de acceso a datos de clientes. El Microsoft Cloud en Alemania se entrega de centros de datos en Alemania y los centros de operaciones (OC) que contiene el personal técnico del Administrador de datos de confianza también están en Alemania. El centro de datos y las instalaciones OC se operado, mantener y controladas por el Administrador de datos de confianza.

En la siguiente tabla se enumera las comprobaciones que se llevan a cabo como parte de la comprobación de fondo de la nube de Microsoft.

| Filtrado | Descripción |
|--------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| Búsqueda de número de la seguridad social | Comprueba que el número de seguridad Social proporcionado es válido. |
| Comprobación de los antecedentes penales | Compruebe si hay registros criminales siete años delitos delito y misdemeanor en los niveles de estado, provincia y locales y, según corresponda, en el nivel de federal. |
| Office de la lista de Control de los activos externa | Lista de departamento del Tesoro de individuos y organizaciones con quienes los ciudadanos de Estados Unidos y residentes permanentes no se permiten hacer negocios. |
| Oficina de industria y seguridad lista | Lista de departamento de comercio de personas y entidades no permitirá participar en las actividades de exportación. |
| Office de defensa comercial precisar que las personas lista de controles (*agregado en el 1 de julio de 2010*) | Lista de departamento del estado de las personas y entidades no permitirá participar en las actividades relacionadas con el sector de la defensa de exportación. |


Los resultados de la comprobación de fondo de la nube de Microsoft se almacenan en la base de datos de empleado, que está conectado a nuestros sistemas de control de acceso de centro de datos. Si caduca la comprobación de fondo de la nube de Microsoft y el empleado no renovar, a continuación, acceso a servicios de Office 365 es revocado y ya no están disponibles hasta que la comprobación de fondo de la nube de Microsoft se complete de nuevo. Cuando finaliza la relación laboral con Microsoft, es revocado inmediatamente cualquier acceso de centro de datos existente.

Estados Unidos posea comprobada para todos los empleados con físico o lógico de acceso a los servicios de gobierno de Estados Unidos de Office 365. Para comprobar posea, los empleados o candidatos de contratación nueva cumplen con un delegado de posea de Estados Unidos que es capacitados para revisar la documentación de comprobar posea de Estados Unidos. Los empleados o candidatos de contratación nuevo deben incorporar la documentación necesaria y firmar un formulario de certificación en una reunión con el delegado posea para su región. La reunión debe realizarse en persona. Una vez que la persona tiene cumplen con el delegado posea y proporcionan la documentación necesaria y firmas, el delegado posea reenvía una copia de los documentos a Microsoft personal de las operaciones que enviar la copia de mantenimiento de registros.

Personal con acceso lógico a la nube de la Comunidad de Office 365 US gubernamentales o físico o lógico de acceso a las ofertas de gobierno de Estados Unidos de Azure, es necesarios para cumplir con los requerimientos del gobierno federal del FBI [información de Justicia penal Servicios de](https://www.fbi.gov/services/cjis) (CJIS), incluido el personal de filtrado. Filtrado de CJIS para apoyar el servicio de gobierno de Estados Unidos de Office 365 incluye una comprobación de fondo penales basadas en huellas digitales que se resolverá por la Agencia de sistema CJIS designada adjudicator en [los Estados que se inscriben](https://blogs.office.com/2013/10/23/california-and-microsoft-sign-cjis-security-policy-agreement/) en el Microsoft Online Programa de soporte de servicios CJIS.
