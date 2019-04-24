---
title: Controles de personal de Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 'Resumen: información general sobre los procedimientos de filtrado de personal de Microsoft para Office 365.'
ms.openlocfilehash: b69c219ef6b405734035d74ce10195ea8cddf401
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262422"
---
# <a name="office-365-personnel-controls"></a>Controles de personal de Office 365 

El examen de personal, que es el proceso de revisión y validación del estado y el comportamiento anteriores de un usuario, es un control de mitigación importante para evitar el compromiso del servicio de Office 365. Aunque el comportamiento pasado no es un predictor perfecto del comportamiento futuro de una persona, le ayuda a identificar posibles actores incorrectos. El estándar de examen de personal de Microsoft se aplica a todos los empleados, los empleados y el personal de la nube de Microsoft que participan en el desarrollo, la operación o la entrega de servicios en línea a los clientes de la nube gubernamental o comercial. El personal del asociado de negocios de cada entorno específico define los estándares de filtrado de los entornos de nube nacionales que no operan con Microsoft.

## <a name="microsofts-personnel-screening-standard"></a>Estándar de examen de personal de Microsoft

Los procedimientos de filtrado de personal de Microsoft para Office 365 están alineados con los estándares corporativos de Microsoft y los controles del Instituto Nacional de estándares y tecnología (NIST) para la detección de personas. El personal de Microsoft que requieran acceso a lo siguiente están sujetos al estándar de examen de personal de Microsoft:
- Acceso físico a centros de usuarios, colocaciones, salas protegidas, jaulas, racks de servidores o sitios perimetrales que proporcionan la infraestructura que admite los servicios en línea para los clientes de la nube pública o comercial.
- Acceso lógico a los datos de clientes de la nube pública o de la nube proporcionada a través de entornos administrados específicos.
    - Acceso a la administración de red a dispositivos y servicios que transporten o almacenan datos de clientes de la nube comercial o del gobierno.

Los eventos específicos relacionados con el personal que desencadenan los requisitos de filtrado son:
- El nuevo personal de Microsoft se coloca en funciones en las que el filtrado es un requisito definido.
- Personal interno de Microsoft transferencia o traslado a un rol existente que actualmente incluye la detección como un requisito definido.
- Funciones existentes que cambian el ámbito para incluir el filtrado como un requisito definido.

## <a name="screening-enforcement-criteria"></a>Criterios de aplicación de filtrado

Para asegurarse de que solo el personal aprobado tiene acceso a los datos de los clientes o entornos que necesitan un filtrado, se aplican los siguientes criterios de aplicación:

**Solo entornos de nube de Estados Unidos**:
- El acceso a los datos de clientes o entornos que requieran filtrado solo debe permitirse después de que se complete la contratación y se superen los requisitos de filtrado.
- El personal de Microsoft que ya no requiera el acceso a los datos de los clientes o a los entornos relacionados debe tener acceso eliminado cuando abandone Microsoft o se mueva a un nuevo rol.
- El personal de Microsoft debe dejar las tarjetas inteligentes de entorno de pantalla con administración antes de salir de los Estados Unidos.

**Entornos de nube nacionales**:
- El operador de terceros o el personal de confianza de datos es responsable de administrar y aplicar el acceso a los entornos de nube nacionales.

Dentro de los entornos de servicios en la nube de Microsoft, el acceso está restringido en función de la función de la persona y el tipo de datos implicados, tal como se describe en la tabla siguiente. El personal cualificado o no cualificado ubicado físicamente fuera de los Estados Unidos no puede tener acceso a los datos del cliente dentro de una nube de Estados Unidos. El acceso a los entornos de la nube nacional está restringido para que el personal de Microsoft no tenga acceso técnico a los datos de los clientes o sistemas que contienen datos de clientes, sin la aprobación del operador de terceros o del administrador de confianza de datos.

| Role | Acceso a los datos de clientes | Acceso a los datos del sistema |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------|---------------------------------|
| Personal cualificado físicamente en los Estados Unidos | Permitido | Permitido |
| Personal cualificado físicamente fuera de los Estados Unidos | No se permite | Permitido |
| Acceso a excepciones internacionales para el personal de Microsoft: permite el acceso lógico para el personal de Microsoft que no reside en el país donde están en reposo los datos de clientes comerciales o de la administración pública. | No se permite | Permitido |
| Personal no cualificado (personal sin pantalla que requiere un Escort por personal cualificado) | Permitido con autorización | Se permite con supervisión Escort |


## <a name="microsoft-pre-employment-screening"></a>Filtrado previo al empleo de Microsoft

Cuando la legislación local lo permite, el Departamento de seguridad global de Microsoft realiza un filtrado previo al empleo. Se trata de una investigación formal en segundo plano que incluye los siguientes criterios:
- Un cheque (por ejemplo, para integridad y exactitud) del currículum del candidato
- Confirmación de calificaciones académicas y profesionales
- Investigación de cualquier pérdida de credenciales profesionales
- Verificación de las tres empresas más antiguas
- Una comprobación de los expedientes de policía para la condena Felony
- Confirmación de identidad de una identificación emitida por el gobierno
- Comprobación de crédito cuando sea necesario

Es posible que sea necesario realizar revisiones periódicas o comprobaciones de antecedentes adicionales para determinadas funciones de administración, seguridad u otros roles, incluidos pero no limitados a los empleados de Estados Unidos en las funciones que requieran acceso a los datos de los clientes.
Para el personal contingente, el contrato con el tercero especifica los requisitos de filtrado de Microsoft que debe llevar a cabo un tercero. Para las comprobaciones de antecedentes, la compañía de terceros es responsable de suministrar a Microsoft la comprobación de que se ha realizado una comprobación de fondo. Los resultados de la comprobación de fondo se suelen recibir por correo electrónico del Departamento de recursos humanos de un tercero. Los empleados internacionales del personal de contratos pueden estar exentos del proceso de detección en segundo plano debido a las leyes en países que prohíben comprobaciones de antecedentes.

## <a name="microsoft-employment-screening"></a>Filtrado de empleo de Microsoft
A partir de 2004, Microsoft ha requerido que los usuarios pasen una pantalla de registro penal de siete años para felonies y misdemeanors, y para comprobar su historial educativo y de empleo, como parte de la detección previa al empleo en Estados Unidos para empleados y en prácticas.

En Estados Unidos, antes de asignar un empleado de Microsoft o un subcontratista asignado por Microsoft para proporcionar servicios relacionados con Office 365, Microsoft llevará a cabo y hará que su subcontratista realice una comprobación de fondo que consista en una seguridad social. seguimiento de número y comprobación de los registros delictivos. Los datos de esta comprobación de segundo plano se usan como un factor de la decisión de contratación. La comprobación de registros criminales incluye una comprobación de los registros de los delincuentes Felony y delitos de siete años de registros federales, estatales y de condado (según corresponda).

Como condición de empleo, en el momento de la contratación, todos los empleados de Microsoft deben firmar los acuerdos de confidencialidad y no divulgación, y comprobar que han revisado la guía del empleado de Microsoft.

## <a name="microsoft-cloud-background-check"></a>Comprobación de fondo de nube de Microsoft
Es necesario realizar una comprobación de fondo de nube de Microsoft para que los candidatos se contrataran como empleados que ofrecen servicios relacionados con Office 365 en Estados Unidos. Los empleados de Microsoft de Estados Unidos con acceso a los datos de los clientes deben seguir el proceso de comprobación de fondo de nube de Microsoft, que es necesario para todos los servicios de Office 365. Fuera de los Estados Unidos, el proceso varía. Por ejemplo, la nube de Microsoft para Alemania usa un modelo de aprobación de confianza de datos, que está diseñado para garantizar que el administrador de datos (una compañía alemana), y no Microsoft, esté controlando el acceso a los datos de los clientes. La nube de Microsoft en Alemania se entrega desde los centros de datos de Alemania y los centros de operaciones (OC) que contengan el personal técnico del administrador de datos también se encuentran en Alemania. El administrador de datos opera, mantiene y controla el centro de datos y las instalaciones de OC.

En la siguiente tabla se enumeran las comprobaciones realizadas como parte de la comprobación de fondo de nube de Microsoft.

| Comprobación | Descripción |
|--------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| Búsqueda de números de seguridad social | Comprueba que el número de la seguridad social que se ha proporcionado es válido. |
| Comprobación de los antecedentes penales | Los registros criminales de siete años comprueban los inconvenientes de Felony y delitos en el estado, el condado y los niveles locales, y según corresponda a nivel federal. |
| Oficina de la lista de control de activos extranjeros | Departamento de tesorería: lista de individuos y organizaciones con quienes los ciudadanos de Estados Unidos y los residentes permanentes no están autorizados a hacer negocios. |
| Oficina de la industria y lista de seguridad | Lista de personas y entidades de Departamento de comercio que no se han comprometido en actividades de exportación. |
| Lista de personas desTitulares de controles comerciales de Office of Defense (*agregado el 1 de julio de 2010*) | Lista del Departamento de estado de individuos y entidades que no se han comprometido en actividades de exportación relacionadas con la industria de la defensa. |


Los resultados de la comprobación de fondo de nube de Microsoft se almacenan en nuestra base de datos de empleados, que está conectada a nuestros sistemas de control de acceso al centro de datos. Si la comprobación de fondo de nube de Microsoft expira y el empleado no la renueva, el acceso a los servicios de Office 365 se revocará y dejará de estar disponible hasta que la comprobación de fondo de nube de Microsoft vuelva a completarse. Cuando la relación de empleo con Microsoft finaliza, cualquier acceso a Datacenter existente se revoca inmediatamente.

La ciudadanía estadounidense se comprueba para todos los empleados con acceso físico o lógico a los servicios gubernamentales de Estados Unidos de Office 365. Para comprobar la nacionalidad, los empleados o los candidatos nuevos para el contrato se reúnen con un delegado de la ciudadanía estadounidense que está entrenado para revisar la documentación para comprobar la nacionalidad de Estados Unidos. Los empleados o los candidatos de nueva contratación deben poner la documentación necesaria y firmar un formulario de atestación en una reunión con el delegado de ciudadanía para su región. La reunión debe realizarse en persona. Una vez que la persona ha cumplido con el delegado de la ciudadanía y ha proporcionado la documentación y las firmas necesarias, el delegado de la ciudadanía reenvía una copia de los documentos a las operaciones de personal de Microsoft que envían la copia a la retención de registros.

El personal con acceso lógico a la nube de Office 365 U.S. Government Community, o el acceso lógico o físico a las ofertas del gobierno de Estados Unidos de Azure, debe cumplir con los requisitos del gobierno federal de la [información de justicia criminal del FBI Services](https://www.fbi.gov/services/cjis) (CJIS), incluida la detección de personal. El examen CJIS en apoyo del servicio de administración pública de Office 365 incluye una comprobación de fondo penal basada en huellas digitales, que es contratada por el contratante designado de la agencia del sistema de CJIS en [los Estados que se han inscrito](https://blogs.office.com/2013/10/23/california-and-microsoft-sign-cjis-security-policy-agreement/) en Microsoft online Programa de soporte CJIS de servicios.
