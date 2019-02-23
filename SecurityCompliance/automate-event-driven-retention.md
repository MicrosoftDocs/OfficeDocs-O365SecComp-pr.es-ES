---
title: Retención automática controlada por eventos
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
description: En este tema se explica cómo configurar los flujos de procesos empresariales para automatizar la retención mediante eventos con la API de REST de Microsoft 365.
ms.openlocfilehash: a43fb7dd2c87879ec5c89c48e830c8c205eeedec
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220520"
---
# <a name="automate-event-based-retention"></a>Retención automática basada en eventos

La explosión de contenido en las organizaciones y la forma en la que se convierte en ROT (redundante obsoleto, trivial) constituye un asunto importante. Para seguir satisfaciendo los desafíos de cumplimiento legal, normativo y empresarial, las empresas deben conservar y proteger la información importante y encontrar rápidamente lo que es relevante. Conservar solo información importante y relevante es clave para el éxito del negocio.

Por lo tanto, las organizaciones pueden beneficiarse de las soluciones de retención del Centro de seguridad y cumplimiento de Office 365. La retención puede activarse con [etiquetas de retención](labels.md). Una etiqueta de retención tiene la opción de [basar el período de retención en un evento específico](event-driven-retention.md). Normalmente, el período de retención se basa en una fecha conocida, como la fecha de creación o fecha de última modificación del contenido. Sin embargo, las organizaciones también tienen requisitos para eliminar el contenido en función de la ocurrencia de un evento, como 7 años después de que un empleado deje la organización.

Para garantizar que las normas eliminación de contenido cumplen con las normas, es imprescindible conocer cuándo sucede un evento. Con un volumen de contenido en rápido aumento, se torna cada vez más difícil retener y eliminar contenido de manera oportuna y que cumpla con las normas.

La retención basada en eventos soluciona este problema. En este tema se explica cómo configurar los flujos de procesos empresariales para automatizar la retención mediante eventos con la API de REST de Microsoft 365.

## <a name="about-event-based-retention"></a>Acerca de la retención basada en eventos

Una organización puede ser pequeña, mediana o grande. La cantidad de documentos empresariales, documentos legales, archivos de empleados, contratos y documentos de productos que se crean y administran a diario aumenta enormemente.

Por ejemplo, cada día, decenas y cientos de empleados se unen a organizaciones y las dejan. El departamento de RR. HH. sigue creando, actualizando o eliminando documentos relacionados con los empleados según los requisitos empresariales. Este proceso está sujeto a las distintas directivas de retención indicadas para la empresa:

- **El período de retención de contenido puede ser una fecha conocida**, como la fecha en la que se creó, modificó por última vez o etiquetó el contenido. Por ejemplo, puedes retener documentos durante siete años después de su creación y luego eliminarlos.

- **El período de retención de contenido también puede ser una fecha desconocida**. Por ejemplo, con las etiquetas de retención, también puedes basar un período de retención en el momento en el que se produce un tipo de evento específico, como cuando un empleado deja la organización.

El evento desencadena el inicio del período de retención y a todo el contenido con una etiqueta aplicada para ese tipo de evento se le aplican las acciones de retención de la etiqueta. Esto se denomina retención basada en eventos: para obtener más información, consulta [Introducción a la retención basada en eventos](event-driven-retention.md).

## <a name="set-up-event-based-retention"></a>Configuración de la retención basada en eventos

Esta sección describe lo que es necesario realizar antes de retener contenido.

### <a name="identify-roles"></a>Identificación de funciones

Identifica las diferentes funciones en una organización que realizan tareas de administración de registros que serían responsables de una retención eficaz y eficiente de los documentos empresariales.

  | **Rol**| **Función**|
  | - | - |
  | Administración del Centro de seguridad y cumplimiento | Crea tipos de eventos de retención, etiquetas de retención y repositorios de registros en SharePoint |
  | Administrador de registros                                  | Proporciona detalles de cumplimiento y guías de políticas de retención y programaciones de retención   |
  | Administrador del sistema (empresa)                          | Configura y administra sistemas externos para que funcionen con Microsoft 365                       |
  | Trabajador de información                               | Administra el ciclo de vida de los procesos de su empresa (Recursos Humanos, Finanzas, TI, etc.)                 |

### <a name="set-up-the-security--compliance-center"></a>Configuración del Centro de seguridad y cumplimiento
  
1. La administración del cumplimiento crea un tipo de evento, como el final de una relación laboral, la finalización del contrato o el final de fabricación del producto (consulta el proceso paso a paso en el artículo [Retención de eventos](https://docs.microsoft.com/es-ES/office365/securitycompliance/event-driven-retention)
    
1. La administración de cumplimiento crea una etiqueta de retención basada en un evento y asocia la etiqueta con un tipo de evento
    
1. Hay 4 tipos de desencadenadores para las etiquetas de retención:
            
    1. Fecha de creación
                
    1. Última modificación
                
    1. Fecha de la etiqueta (cuando se etiquetó el contenido)
                
    1. Basado en eventos
    
1. La administración del cumplimiento publica la etiqueta

### <a name="set-up-sharepoint"></a>Configurar SharePoint
   
Para crear un repositorio de registros, la administración del cumplimiento:

1. Crea un sitio de SharePoint.

1. Realiza una de las siguientes acciones:
        
    - Crea una biblioteca de SharePoint: establece una etiqueta basada en eventos en el nivel de la biblioteca. Para obtener más información, consulta [Aplicar una etiqueta de retención predeterminada a todo el contenido de una biblioteca, carpeta o conjunto de documentos de SharePoint](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).
          
    - Establece conjunto de documentos en SharePoint. Para obtener más información, consulta [Introducción a los conjuntos de documentos](https://support.office.com/es-ES/article/Introduction-to-Document-Sets-3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).
      
1. Asigna el Id. de activo (el id. de activo es un nombre o código de producto que usa la organización, por ejemplo, el número de empleado pueden ser un id. de activo) para cada conjunto de documentos del empleado (al asignar el id. de activo a la carpeta, todos los elementos de esa carpeta heredan automáticamente el mismo id de activo. Esto significa que el mismo evento puede desencadenar el período de retención de todos los elementos.

## <a name="ways-to-trigger-event-based-retention"></a>Formas de desencadenar la retención basada en eventos

Existen dos formas de desencadenar la retención basada en eventos:

- **Con la interfaz de usuario del Centro de cumplimiento y seguridad** Este es un proceso que puede usarse para conservar menos contenido por vez o cuando la frecuencia que activa la retención es ocasional (mensual o anual). Para obtener más información sobre este método, consulta [Introducción a la retención basada en eventos](event-driven-retention.md). Sin embargo, esta forma de activar la retención puede requerir demasiado tiempo y ser propensa a errores, por lo que se reduce la escalabilidad. Por lo tanto, una solución perfecta y automatizada para activar la retención puede mejorar la seguridad y el cumplimiento de datos.

- **Con una API de REST de M365** Este proceso puede usarse cuando se deben retener grandes cantidades de contenido a la vez o cuando la frecuencia para activar la retención es asidua (diaria o semanal). El flujo detecta cuando un evento se ejecuta en el sistema de línea de negocio y crea automáticamente un evento relacionado en el Centro de seguridad y cumplimiento. No es necesario crear manualmente un evento en la interfaz de usuario cada vez que se produce un evento.

Hay dos opciones para usar la API de REST:

- **Microsoft Flow o una aplicación similar** pueden usarse para activar la ocurrencia de un evento de forma automática. Microsoft Flow es un orquestador para conectarse a otros sistemas. Para usar Microsoft Flow no es necesaria una solución personalizada.

- **PowerShell o un cliente de HTTP para llamar a la API de REST** Usar PowerShell (versión 6 o posterior) para pedirle a la API de REST de Microsoft 365 que cree eventos. 

Una API de Rest es un punto de conexión de servicio compatible con conjuntos de operaciones de HTTP (métodos), que aportan acceso para crear, recuperar, actualizar o eliminar a los recursos del servicio: para obtener más información, consulta [Componentes de una solicitud o respuesta de API de REST](https://docs.microsoft.com/es-ES/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse). En este caso, con la API de REST de Microsoft 365, los eventos se pueden crear y recuperar con las operaciones (métodos) POST y GET.

## <a name="example-scenarios"></a>Escenarios de ejemplo

Consideremos los siguientes escenarios.

### <a name="scenario-1-employees-leaving-the-organization"></a>Escenario 1: Empleados que dejan la organización 

Una organización crea y almacena numerosos documentos relacionados con los empleados para cada empleado. Estos documentos se administran y conservan mientras dura el vínculo laboral con cada empleado. Sin embargo, cuando el empleado se va de la organización o cuando lo echan, es una obligación legal y un requisito de la empresa conservar los documentos del empleado durante un período establecido.

Ahora si varios empleados dejan la organización todos los días, la organización debe activar el reloj de retención de cientos o miles de documentos cada día.

Además, se debe calcular el período de retención de cada uno de estos empleados con el siguiente formato: fecha de despido del empleado + número de días, meses o años en función del tipo de registro del empleado. Por ejemplo, es posible que la compensación y la tramitación de beneficios del mismo empleado necesiten retenciones diferentes.

El siguiente diagrama muestra cómo puede haber varias etiquetas asociadas a un solo evento. Aquí todos los archivos debajo de la etiqueta de compensación del trabajador y todos los archivos debajo de la etiqueta de beneficios del empleado están asociados con un evento único que es la desvinculación del empleado de la organización. Cada uno de estos archivos tiene un reloj de retención diferente. Por lo tanto, cuando un empleado abandona la organización, los archivos dentro de cada etiqueta tiene un período de retención diferente. Activar todos estos relojes de retención diferentes para cada tipo de archivo o etiqueta de cada empleado es una tarea muy difícil. Imagina realizar esta acción para varios empleados.

![Diagrama de tipo de evento, evento y etiquetas](media/automate-event-driven-retention-event-diagram-employee-leaving.png)

Por lo tanto, un proceso automatizado para activar estos relojes de retención diferentes para varios empleados permitirá ahorrar tiempo, evitar errores y lograr una alta eficiencia.

**Configuración de retención automatizada basada en eventos para este escenario:**

![Diagrama de funciones y acciones para el escenario del empleado que deja la organización](media/automate-event-driven-retention-employee-termination-diagram.png)

  - La administración crea carpetas del empleado en un conjunto de documentos denominado Naiara Padilla, David Pulido.

  - La administración agrega archivos del empleado, como los de beneficios, nómina o compensación del trabajador a cada carpeta de empleado.

  - La administración asigna el id. de activo a la carpeta de cada empleado. 

  - Administración de SCC inicia

  - sesión en el Centro de seguridad y cumplimiento.

  - La administración de SCC crea tipos de eventos relacionados con el empleado como “Desvinculación del empleado”, “Contratación del empleados” en el Centro de seguridad y cumplimiento.

  - La administración de SCC crea la etiqueta de "Retención de empleados" en el Centro de seguridad y cumplimiento.

  - Esta etiqueta de "Retención de empleados" se publica y se aplican manual o automáticamente a los archivos de empleado en SharePoint.

  - Un sistema de administración de Recursos Humanos como Workday puede trabajar con Microsoft Flow para ejecutarse periódicamente para administrar archivos del empleado.

  - Cuando un empleado deja la organización, Flow activa la API de REST de retención basada en eventos de M365 que inicia el reloj de retención de archivos específicos del empleado.

#### <a name="using-microsoft-flow"></a>Usar Microsoft Flow

Paso 1: crear un flujo para crear un evento mediante la API de REST de Microsoft 365

![Usar Flow para crear un evento](media/automate-event-driven-retention-flow-1.png)

![Usar Flow para llamar a la API de REST](media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a>Crear un evento

Código de ejemplo para llamar a la API de REST

<table>
<thead>
<tr class="header">
<th>Método</th>
<th>POST</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>URL</td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent)</td>
<td></td>
</tr>
<tr class="even">
<td>Encabezados</td>
<td>Tipo de contenido</td>
<td>aplicación/atom+xml</td>
</tr>
<tr class="odd">
<td>Cuerpo</td>
<td><p>&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</p>
<p>&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</p>
<p>xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</p>
<p>xmlns='http://www.w3.org/2005/Atom'&gt;</p>
<p>&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</p>
<p>&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</p>
<p>&lt;content type='application/xml'&gt;</p>
<p>&lt;m:properties&gt;</p>
<p>&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</p>
<p>&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</p>
<p>&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</p>
<p>&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</p>
<p>&lt;/m:properties&gt;</p>
<p>&lt;/content&gt;</p>
<p>&lt;/entry&gt;</p></td>
<td></td>
</tr>
<tr class="even">
<td>Autenticación</td>
<td>Básica</td>
<td></td>
</tr>
<tr class="odd">
<td>Nombre de usuario</td>
<td>“Complianceuser”</td>
<td></td>
</tr>
<tr class="even">
<td>Contraseña</td>
<td>“Compliancepassword”</td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a>Parámetros disponibles

<table>
<thead>
<tr class="header">
<th><strong>Parámetros</strong></th>
<th><strong>Descripción</strong></th>
<th><strong>Notas</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>&lt;d:Name&gt;&lt;/d:Name&gt;</td>
<td>Escribe un nombre único para el evento.</td>
<td>No puede contener espacios finales ni los siguientes caracteres: % * \ &amp; &lt; &gt; | # ? , : ;</td>
</tr>
<tr class="even">
<td>&lt;d:eventType&gt;&lt;/d:EventType&gt;</td>
<td>Escribe el nombre del tipo de evento (o Guid)</td>
<td>Ejemplo: "Desvinculación del empleado". El tipo de evento debe estar asociado con una etiqueta de retención.</td>
</tr>
<tr class="odd">
<td>&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</td>
<td>Escribe "ComplianceAssetId:" + Id. de empleado</td>
<td>Ejemplo:&quot;ComplianceAssetId:12345&quot;</td>
</tr>
<tr class="even">
<td>&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</td>
<td>Fecha y hora del evento</td>
<td><p>Formato: aaaa-MM-ddTHH:mm:ssZ, ejemplo:</p>
<p>2018-12-01T00:00:00Z</p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a>Códigos de respuesta

| **Código de respuesta** | **Descripción**       |
| ----------------- | --------------------- |
| 302               | Redirigir              |
| 201               | Fecha de creación               |
| 403               | Error de autorización  |
| 401               | Error de autenticación |

##### <a name="get-events-based-on-time-range"></a>Obtener eventos según el intervalo de tiempo

<table>
<thead>
<tr class="header">
<th>Método</th>
<th>GET</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>URL</td>
<td><ol start="4" type="1">
<li><p>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp; EndDateTime = 2019-16: 01</p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td>Encabezados</td>
<td>Tipo de contenido</td>
<td>aplicación/atom+xml</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Autenticación</td>
<td>Básica</td>
<td></td>
</tr>
<tr class="odd">
<td>Nombre de usuario</td>
<td>“Complianceuser”</td>
<td></td>
</tr>
<tr class="even">
<td>Contraseña</td>
<td>“Compliancepassword”</td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a>Códigos de respuesta

| **Código de respuesta** | **Descripción**                   |
| ----------------- | --------------------------------- |
| 200               | Aceptar, una lista de eventos de atom+ xml |
| 404               | No encontrado                         |
| 302               | Redirigir                          |
| 401               | Error de autorización              |
| 403               | Error de autenticación             |

##### <a name="get-an-event-by-id"></a>Obtén un objeto por id.

| Método         | GET   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| URL            | [https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\)) |                      |
| Encabezado         | Tipo de contenido                                                                                                                                                                                                                                                       | aplicación/atom+xml |
| Autenticación | Básica                                                                                                                                                                                                                                                              |                      |
| Nombre de usuario       | “Complianceuser”                                                                                                                                                                                                                                                   |                      |
| Contraseña       | “Compliancepassword”                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a>Códigos de respuesta

| **Código de respuesta** | **Descripción**                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | Aceptar, el cuerpo de la respuesta contiene el evento en atom+ xml |
| 404               | No encontrado                                            |
| 302               | Redirigir                                             |
| 401               | Error de autorización                                 |
| 403               | Error de autenticación                                |

##### <a name="get-an-event-by-name"></a>Obtén un evento por nombre

| Método         | GET       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| URL            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| Encabezados        | Tipo de contenido                                                                                                                                 | aplicación/atom+xml |
| Autenticación | Básica                                                                                                                                        |                      |
| Nombre de usuario       | “Complianceuser”                                                                                                                             |                      |
| Contraseña       | “Compliancepassword”                                                                                                                         |                      |

##### <a name="response-codes"></a>Códigos de respuesta

| **Código de respuesta** | **Descripción**                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | Aceptar, el cuerpo de la respuesta contiene el evento en atom+ xml |
| 404               | No encontrado                                            |
| 302               | Redirigir                                             |
| 401               | Error de autorización                                 |
| 403               | Error de autenticación                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a>Uso de PowerShell (ver.6 o posterior) o cualquier cliente HTTP

Paso 1: Conéctate a PowerShell.

Paso 2: Ejecuta el siguiente script.

<table>
<tbody>
<tr class="odd">
<td><p>param([string]$baseUri)</p>
<p>$userName = &quot;UserName&quot;</p>
<p>$password = &quot;Password&quot;</p>
<p>$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</p>
<p>$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</p>
<p>$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</p>
<p>Write-Host &quot;Comienza a crear un evento con el nombre: $EventName&quot;</p>
<p>$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</p>
<p>&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</p>
<p>xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</p>
<p>xmlns='http://www.w3.org/2005/Atom'&gt;</p>
<p>&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</p>
<p>&lt;actualizado&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</p>
<p>&lt;content type='application/xml'&gt;</p>
<p>&lt;m:properties&gt;</p>
<p>&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</p>
<p>&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</p>
<p>&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</p>
<p>&lt;/m:properties&gt;</p>
<p>&lt;/content&gt;</p>
<p>&lt;/entry&gt;&quot;</p>
<p>$event = $null</p>
<p>probar</p>
<p>{</p>
<p>$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</p>
<p>}</p>
<p>catch</p>
<p>{</p>
<p>$response = $_. Exception.Response</p>
<p>if($response.StatusCode -eq &quot;Redirect&quot;)</p>
<p>{</p>
<p>$url = $response.Headers.Location</p>
<p>Write-Host &quot;redirected to $url&quot;</p>
<p>$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</p>
<p>}</p>
<p>}</p>
<p>$event | fl *</p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a>Comprobar el resultado en ambas opciones.

Paso 1: Ir al Centro de seguridad y cumplimiento

Paso 2: Hacer clic en eventos debajo de Gobierno de datos

Paso 3: Comprobar que se creó el evento.

De forma similar, también se pueden usar las opciones anteriores para automatizar la retención basada en eventos para los siguientes escenarios.

### <a name="scenario-2-contracts-expiring"></a>Escenario 2: Contratos que expiran

Una organización puede tener varios registros de un único contrato con clientes, proveedores y partners. Estos documentos pueden encontrarse en una biblioteca de documentos, como SharePoint. La finalización de un contrato determina el inicio del período de retención de los documentos asociados con el contrato. Por ejemplo: todos los registros relacionados con los contratos deben conservarse durante cinco años a partir del momento en el que expira el contrato. El evento que activa el período de retención de cinco años es la expiración del contrato.

Un sistema de administración de relaciones de cliente (CRM) puede trabajar con Microsoft 365 y activar la retención de documentos del contrato.

**Configuración de retención automatizada basada en eventos para este escenario:**

![Diagrama de los funciones y tareas para escenarios de expiración del contrato](media/automate-event-driven-retention-contract-expiration.png)

  - La administración crea una biblioteca de SharePoint con carpetas diferentes para cada tipo de contrato.

  - La administración agrega archivos del contrato como contratos de licencia y contratos de desarrollo para cada carpeta del contrato.

  - La administración asigna el id. de activo a cada carpeta de contrato.

  - La administración de SSC inicia sesión en el Centro de seguridad y cumplimiento.

  - La administración de SCC crea tipos de eventos relacionados con el contrato como eventos de "Creación del contrato" y "Expiración del contrato" en el Centro de seguridad y cumplimiento.

  - La administración de SCC crea la etiqueta "Expiración del contrato" en el Centro de seguridad y cumplimiento.

  - Esta etiqueta de "Expiración del contrato" se publica y se aplican de forma manual o automática a los archivos del contrato en SharePoint.

  - El sistema de administración de contrato puede trabajar con Microsoft Flow o una aplicación similar para ejecutarse periódicamente para administrar archivos de contrato.

  - Si un contrato vence, Microsoft Flow activará la API de REST de retención basada en eventos de M365 que iniciará el reloj de retención de archivos específicos del contrato.

### <a name="scenario-3-end-of-product-manufacturing"></a>Escenario 3: Final de fabricación de productos

Una empresa de elaboración que fabrica diferentes líneas de productos crea varias especificaciones de elaboración y documentos de precios. Cuando el producto ya no se fabrica, todas las especificaciones y documentos vinculados a este producto deben conservarse durante un período específico después del final de la vida útil del producto.

Un sistema de planeación de recursos empresariales (ERP) puede trabajar con Microsoft 365 y Microsoft Flow para activar la retención.

**Configuración de retención automatizada basada en eventos para este escenario:**

![Diagrama de las funciones y tareas para escenarios de ciclo de vida del producto](media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - La administración crea carpetas de productos en el conjunto de documentos como Producto 1, Producto 2, etc.

  - La administración agrega los archivos de productos como Especificaciones de fabricación, Precio del producto y Licencias del producto a cada carpeta de producto.

  - La administración le asigna el id. de activo a cada carpeta del producto.

  - La administración de SSC inicia sesión en el Centro de seguridad y cumplimiento.

  - La administración de SCC crea tipos de eventos relacionados con el empleado como "Inicio de fabricación del producto" y "Final de fabricación del producto" en el Centro de seguridad y cumplimiento.

  - La administración de SCC crea la etiqueta "Final de fabricación del producto" en el Centro de seguridad y cumplimiento.

  - Esta etiqueta de "Final de fabricación del producto" se publica y se aplica de forma manual o automática a los archivos del producto en SharePoint

  - Los sistemas de ERP pueden funcionar con Microsoft Flow o con aplicaciones similares para ejecutarse periódicamente para administrar archivos del producto.

  - Si se termina la fabricación de un producto, Microsoft Flow activará la API de REST de retención basada en eventos de M365 que iniciará el reloj de retención de archivos específicos del producto.

## <a name="appendix"></a>Apéndice

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a>Cómo usar los resultados de respuesta Redirect 302 para llamar a la API de REST

1.  Invocar una llamada de evento de retención POST con la URL de la API de REST <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (se requieren permisos de administrador global).

2.  Comprobar el código de respuesta. Si es 302, obtener la dirección URL redirigida de la propiedad de ubicación del encabezado de respuesta.

3.  Invocar la llamada al evento de retención POST nuevamente mediante el URL redireccionado.

## <a name="credits"></a>Créditos

Este tema fue revisado por:

Antonio Maio</br>MVP de servicios y aplicaciones de Microsoft Office</br> Antonio.Maio@Protiviti.com
