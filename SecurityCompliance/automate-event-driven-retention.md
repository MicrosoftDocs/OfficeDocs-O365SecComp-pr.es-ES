---
title: Retención automática controlada por eventos
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
description: En este tema se explica cómo configurar los flujos de procesos empresariales para automatizar la retención mediante eventos con la API de REST de Microsoft 365.
ms.openlocfilehash: 799f831e937d3f676bb05eb188b813b1ca23622c
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223759"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="ae68c-103">Retención automática basada en eventos</span><span class="sxs-lookup"><span data-stu-id="ae68c-103">Automate event-based retention</span></span>

<span data-ttu-id="ae68c-p101">La explosión de contenido en las organizaciones y la forma en la que se convierte en ROT (redundante obsoleto, trivial) constituye un asunto importante. Para seguir satisfaciendo los desafíos de cumplimiento legal, normativo y empresarial, las empresas deben conservar y proteger la información importante y encontrar rápidamente lo que es relevante. Conservar solo información importante y relevante es clave para el éxito del negocio.</span><span class="sxs-lookup"><span data-stu-id="ae68c-p101">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, businesses must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to a business’s success.</span></span>

<span data-ttu-id="ae68c-p102">Por lo tanto, las organizaciones pueden beneficiarse de las soluciones de retención del Centro de seguridad y cumplimiento de Office 365. La retención puede activarse con [etiquetas de retención](labels.md). Una etiqueta de retención tiene la opción de [basar el período de retención en un evento específico](event-driven-retention.md). Normalmente, el período de retención se basa en una fecha conocida, como la fecha de creación o fecha de última modificación del contenido. Sin embargo, las organizaciones también tienen requisitos para eliminar el contenido en función de la ocurrencia de un evento, como 7 años después de que un empleado deje la organización.</span><span class="sxs-lookup"><span data-stu-id="ae68c-p102">Hence organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as 7 years after an employee leaves an organization.</span></span>

<span data-ttu-id="ae68c-p103">Para garantizar que las normas eliminación de contenido cumplen con las normas, es imprescindible conocer cuándo sucede un evento. Con un volumen de contenido en rápido aumento, se torna cada vez más difícil retener y eliminar contenido de manera oportuna y que cumpla con las normas.</span><span class="sxs-lookup"><span data-stu-id="ae68c-p103">In order to ensure compliant disposal of content, it is imperative to know when an event takes place. With the volume of content increasing rapidly, it is becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="ae68c-p104">La retención basada en eventos soluciona este problema. En este tema se explica cómo configurar los flujos de procesos empresariales para automatizar la retención mediante eventos con la API de REST de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae68c-p104">Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="ae68c-116">Acerca de la retención basada en eventos</span><span class="sxs-lookup"><span data-stu-id="ae68c-116">About event-based retention</span></span>

<span data-ttu-id="ae68c-p105">Una organización puede ser pequeña, mediana o grande. La cantidad de documentos empresariales, documentos legales, archivos de empleados, contratos y documentos de productos que se crean y administran a diario aumenta enormemente.</span><span class="sxs-lookup"><span data-stu-id="ae68c-p105">An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day to day basis is increasing dramatically.</span></span>

<span data-ttu-id="ae68c-p106">Por ejemplo, cada día, decenas y cientos de empleados se unen a organizaciones y las dejan. El departamento de RR. HH. sigue creando, actualizando o eliminando documentos relacionados con los empleados según los requisitos empresariales. Este proceso está sujeto a las distintas directivas de retención indicadas para la empresa:</span><span class="sxs-lookup"><span data-stu-id="ae68c-p106">For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="ae68c-p107">**El período de retención de contenido puede ser una fecha conocida**, como la fecha en la que se creó, modificó por última vez o etiquetó el contenido. Por ejemplo, puedes retener documentos durante siete años después de su creación y luego eliminarlos.</span><span class="sxs-lookup"><span data-stu-id="ae68c-p107">**The period of retention for content can be a known date** such as the date the content was created, last modified or labeled. For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="ae68c-p108">**El período de retención de contenido también puede ser una fecha desconocida**. Por ejemplo, con las etiquetas de retención, también puedes basar un período de retención en el momento en el que se produce un tipo de evento específico, como cuando un empleado deja la organización.</span><span class="sxs-lookup"><span data-stu-id="ae68c-p108">**The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="ae68c-p109">El evento desencadena el inicio del período de retención y a todo el contenido con una etiqueta aplicada para ese tipo de evento se le aplican las acciones de retención de la etiqueta. Esto se denomina retención basada en eventos: para obtener más información, consulta [Introducción a la retención basada en eventos](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="ae68c-p109">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention - to learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="ae68c-128">Configuración de la retención basada en eventos</span><span class="sxs-lookup"><span data-stu-id="ae68c-128">Set up event-based retention</span></span>

<span data-ttu-id="ae68c-129">Esta sección describe lo que es necesario realizar antes de retener contenido.</span><span class="sxs-lookup"><span data-stu-id="ae68c-129">This section describes what needs to be done prior to retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="ae68c-130">Identificación de funciones</span><span class="sxs-lookup"><span data-stu-id="ae68c-130">Identify roles</span></span>

<span data-ttu-id="ae68c-131">Identifica las diferentes funciones en una organización que realizan tareas de administración de registros que serían responsables de una retención eficaz y eficiente de los documentos empresariales.</span><span class="sxs-lookup"><span data-stu-id="ae68c-131">Identify the different roles in an organization that perform Record Management tasks that would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="ae68c-132">**Rol**</span><span class="sxs-lookup"><span data-stu-id="ae68c-132">**Persona**</span></span>| <span data-ttu-id="ae68c-133">**Función**</span><span class="sxs-lookup"><span data-stu-id="ae68c-133">**Role**</span></span>|
  | - | - |
  | <span data-ttu-id="ae68c-134">Administración del Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="ae68c-134">Security & Compliance Center admin</span></span> | <span data-ttu-id="ae68c-135">Crea tipos de eventos de retención, etiquetas de retención y repositorios de registros en SharePoint</span><span class="sxs-lookup"><span data-stu-id="ae68c-135">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="ae68c-136">Administrador de registros</span><span class="sxs-lookup"><span data-stu-id="ae68c-136">Records Manager</span></span>                                  | <span data-ttu-id="ae68c-137">Proporciona detalles de cumplimiento y guías de políticas de retención y programaciones de retención</span><span class="sxs-lookup"><span data-stu-id="ae68c-137">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="ae68c-138">Administrador del sistema (empresa)</span><span class="sxs-lookup"><span data-stu-id="ae68c-138">System Admin (business)</span></span>                          | <span data-ttu-id="ae68c-139">Configura y administra sistemas externos para que funcionen con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ae68c-139">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="ae68c-140">Trabajador de información</span><span class="sxs-lookup"><span data-stu-id="ae68c-140">Information Worker</span></span>                               | <span data-ttu-id="ae68c-141">Administra el ciclo de vida de los procesos de su empresa (Recursos Humanos, Finanzas, TI, etc.)</span><span class="sxs-lookup"><span data-stu-id="ae68c-141">Manages the lifecycle of their business process (HR, Finance, IT etc)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="ae68c-142">Configuración del Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="ae68c-142">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="ae68c-143">La administración del cumplimiento crea un tipo de evento, como el final de una relación laboral, la finalización del contrato o el final de fabricación del producto (consulta el proceso paso a paso en el artículo [Retención de eventos](https://docs.microsoft.com/es-ES/office365/securitycompliance/event-driven-retention)</span><span class="sxs-lookup"><span data-stu-id="ae68c-143">Compliance admin creates an event type – for example, Employee Termination or Contract Expiration or End of Product Manufacturing (Please refer to step by step process in [Event retention article](https://docs.microsoft.com/es-ES/office365/securitycompliance/event-driven-retention)</span></span>
    
1. <span data-ttu-id="ae68c-144">La administración de cumplimiento crea una etiqueta de retención basada en un evento y asocia la etiqueta con un tipo de evento</span><span class="sxs-lookup"><span data-stu-id="ae68c-144">Compliance admin creates a retention label based on an event and associates the label with an event type</span></span>
    
1. <span data-ttu-id="ae68c-145">Hay 4 tipos de desencadenadores para las etiquetas de retención:</span><span class="sxs-lookup"><span data-stu-id="ae68c-145">There are 4 types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="ae68c-146">Fecha de creación</span><span class="sxs-lookup"><span data-stu-id="ae68c-146">Create date</span></span>
                
    1. <span data-ttu-id="ae68c-147">Última modificación</span><span class="sxs-lookup"><span data-stu-id="ae68c-147">Last modified</span></span>
                
    1. <span data-ttu-id="ae68c-148">Fecha de la etiqueta (cuando se etiquetó el contenido)</span><span class="sxs-lookup"><span data-stu-id="ae68c-148">Label date (when the content was labeled)</span></span>
                
    1. <span data-ttu-id="ae68c-149">Basado en eventos</span><span class="sxs-lookup"><span data-stu-id="ae68c-149">Event-based</span></span>
    
1. <span data-ttu-id="ae68c-150">La administración del cumplimiento publica la etiqueta</span><span class="sxs-lookup"><span data-stu-id="ae68c-150">Compliance admin publishes the label</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="ae68c-151">Configurar SharePoint</span><span class="sxs-lookup"><span data-stu-id="ae68c-151">Set up SharePoint</span></span>
   
<span data-ttu-id="ae68c-152">Para crear un repositorio de registros, la administración del cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="ae68c-152">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="ae68c-153">Crea un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ae68c-153">Creates a SharePoint site.</span></span>

1. <span data-ttu-id="ae68c-154">Realiza una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ae68c-154">Does one of the following:</span></span>
        
    - <span data-ttu-id="ae68c-p110">Crea una biblioteca de SharePoint: establece una etiqueta basada en eventos en el nivel de la biblioteca. Para obtener más información, consulta [Aplicar una etiqueta de retención predeterminada a todo el contenido de una biblioteca, carpeta o conjunto de documentos de SharePoint](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="ae68c-p110">Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
    - <span data-ttu-id="ae68c-p111">Establece conjunto de documentos en SharePoint. Para obtener más información, consulta [Introducción a los conjuntos de documentos](https://support.office.com/es-ES/article/Introduction-to-Document-Sets-3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span><span class="sxs-lookup"><span data-stu-id="ae68c-p111">Sets up a Document set in SharePoint. For more information, see [Introduction to document sets](https://support.office.com/es-ES/article/Introduction-to-Document-Sets-3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span></span>
      
1. <span data-ttu-id="ae68c-p112">Asigna el Id. de activo (el id. de activo es un nombre o código de producto que usa la organización, por ejemplo, el número de empleado pueden ser un id. de activo) para cada conjunto de documentos del empleado (al asignar el id. de activo a la carpeta, todos los elementos de esa carpeta heredan automáticamente el mismo id de activo. Esto significa que el mismo evento puede desencadenar el período de retención de todos los elementos.</span><span class="sxs-lookup"><span data-stu-id="ae68c-p112">Assigns Asset Id (asset ID is a product name or code used by the organization, for example, Employee number can be an asset id) to each employee document set (By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID. This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="ae68c-161">Formas de desencadenar la retención basada en eventos</span><span class="sxs-lookup"><span data-stu-id="ae68c-161">Ways to trigger event-based retention</span></span>

<span data-ttu-id="ae68c-162">Existen dos formas de desencadenar la retención basada en eventos:</span><span class="sxs-lookup"><span data-stu-id="ae68c-162">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="ae68c-p113">**Con la interfaz de usuario del Centro de cumplimiento y seguridad** Este es un proceso que puede usarse para conservar menos contenido por vez o cuando la frecuencia que activa la retención es ocasional (mensual o anual). Para obtener más información sobre este método, consulta [Introducción a la retención basada en eventos](event-driven-retention.md). Sin embargo, esta forma de activar la retención puede requerir demasiado tiempo y ser propensa a errores, por lo que se reduce la escalabilidad. Por lo tanto, una solución perfecta y automatizada para activar la retención puede mejorar la seguridad y el cumplimiento de datos.</span><span class="sxs-lookup"><span data-stu-id="ae68c-p113">**Using Security & Compliance Center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention is not often, such as monthly or yearly. For more information on this method, see [Overview of event-driven retention](event-driven-retention.md). However, this way to trigger retention can be time-consuming and prone to error, thus stunting scalability. Therefore, an automated, seamless solution to trigger retention can enhance the security and compliance of data.</span></span>

- <span data-ttu-id="ae68c-p114">**Con una API de REST de M365** Este proceso puede usarse cuando se deben retener grandes cantidades de contenido a la vez o cuando la frecuencia para activar la retención es asidua (diaria o semanal). El flujo detecta cuando un evento se ejecuta en el sistema de línea de negocio y crea automáticamente un evento relacionado en el Centro de seguridad y cumplimiento. No es necesario crear manualmente un evento en la interfaz de usuario cada vez que se produce un evento.</span><span class="sxs-lookup"><span data-stu-id="ae68c-p114">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="ae68c-170">Hay dos opciones para usar la API de REST:</span><span class="sxs-lookup"><span data-stu-id="ae68c-170">There are two options for using the REST API:</span></span>

- <span data-ttu-id="ae68c-p115">**Microsoft Flow o una aplicación similar** pueden usarse para activar la ocurrencia de un evento de forma automática. Microsoft Flow es un orquestador para conectarse a otros sistemas. Para usar Microsoft Flow no es necesaria una solución personalizada.</span><span class="sxs-lookup"><span data-stu-id="ae68c-p115">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically. Microsoft Flow is an orchestrator for connecting to other systems. Using Microsoft Flow does not require a custom solution.</span></span>

- <span data-ttu-id="ae68c-174">**PowerShell o un cliente de HTTP para llamar a la API de REST** Usar PowerShell (versión 6 o posterior) para pedirle a la API de REST de Microsoft 365 que cree eventos.</span><span class="sxs-lookup"><span data-stu-id="ae68c-174">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="ae68c-p116">Una API de Rest es un punto de conexión de servicio compatible con conjuntos de operaciones de HTTP (métodos), que aportan acceso para crear, recuperar, actualizar o eliminar a los recursos del servicio: para obtener más información, consulta [Componentes de una solicitud o respuesta de API de REST](https://docs.microsoft.com/es-ES/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse). En este caso, con la API de REST de Microsoft 365, los eventos se pueden crear y recuperar con las operaciones (métodos) POST y GET.</span><span class="sxs-lookup"><span data-stu-id="ae68c-p116">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources - for more information, see [Components of a REST API request/response](https://docs.microsoft.com/es-ES/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse). In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="ae68c-177">Escenarios de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae68c-177">Example scenarios</span></span>

<span data-ttu-id="ae68c-178">Consideremos los siguientes escenarios.</span><span class="sxs-lookup"><span data-stu-id="ae68c-178">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="ae68c-179">Escenario 1: Empleados que dejan la organización</span><span class="sxs-lookup"><span data-stu-id="ae68c-179">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="ae68c-p117">Una organización crea y almacena numerosos documentos relacionados con los empleados para cada empleado. Estos documentos se administran y conservan mientras dura el vínculo laboral con cada empleado. Sin embargo, cuando el empleado se va de la organización o cuando lo echan, es una obligación legal y un requisito de la empresa conservar los documentos del empleado durante un período establecido.</span><span class="sxs-lookup"><span data-stu-id="ae68c-p117">An organization creates and stores numerous employee related documents per employee. These documents are managed and retained during the employment of each employee. However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="ae68c-183">Ahora si varios empleados dejan la organización todos los días, la organización debe activar el reloj de retención de cientos o miles de documentos cada día.</span><span class="sxs-lookup"><span data-stu-id="ae68c-183">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="ae68c-p118">Además, se debe calcular el período de retención de cada uno de estos empleados con el siguiente formato: fecha de despido del empleado + número de días, meses o años en función del tipo de registro del empleado. Por ejemplo, es posible que la compensación y la tramitación de beneficios del mismo empleado necesiten retenciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="ae68c-p118">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months or years based on the type of the employee record. For example, worker’s compensation of the employee vs benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="ae68c-p119">El siguiente diagrama muestra cómo puede haber varias etiquetas asociadas a un solo evento. Aquí todos los archivos debajo de la etiqueta de compensación del trabajador y todos los archivos debajo de la etiqueta de beneficios del empleado están asociados con un evento único que es la desvinculación del empleado de la organización. Cada uno de estos archivos tiene un reloj de retención diferente. Por lo tanto, cuando un empleado abandona la organización, los archivos dentro de cada etiqueta tiene un período de retención diferente. Activar todos estos relojes de retención diferentes para cada tipo de archivo o etiqueta de cada empleado es una tarea muy difícil. Imagina realizar esta acción para varios empleados.</span><span class="sxs-lookup"><span data-stu-id="ae68c-p119">The diagram below shows how there can be multiple labels that are associated with a single event. Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event which is the employee leaving the organization. Each of these different files have different retention clocks. So, when an employee leaves the organization, these files within each label experience a different retention period. To trigger all these different retention clocks for each file type or label for each employee is a very challenging task. Imagine doing this for multiple employees.</span></span>

![Diagrama de tipo de evento, evento y etiquetas](media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="ae68c-193">Por lo tanto, un proceso automatizado para activar estos relojes de retención diferentes para varios empleados permitirá ahorrar tiempo, evitar errores y lograr una alta eficiencia.</span><span class="sxs-lookup"><span data-stu-id="ae68c-193">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free and extremely efficient .</span></span>

<span data-ttu-id="ae68c-194">**Configuración de retención automatizada basada en eventos para este escenario:**</span><span class="sxs-lookup"><span data-stu-id="ae68c-194">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de funciones y acciones para el escenario del empleado que deja la organización](media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="ae68c-196">La administración crea carpetas del empleado en un conjunto de documentos denominado Naiara Padilla, David Pulido.</span><span class="sxs-lookup"><span data-stu-id="ae68c-196">Admin c reates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="ae68c-197">La administración agrega archivos del empleado, como los de beneficios, nómina o compensación del trabajador a cada carpeta de empleado.</span><span class="sxs-lookup"><span data-stu-id="ae68c-197">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder</span></span>

  - <span data-ttu-id="ae68c-198">La administración asigna el id. de activo a la carpeta de cada empleado.</span><span class="sxs-lookup"><span data-stu-id="ae68c-198">Admin assigns Asset Id to each employee folder.</span></span> 

  - <span data-ttu-id="ae68c-199">Administración de SCC inicia</span><span class="sxs-lookup"><span data-stu-id="ae68c-199">SCC Admin l</span></span>

  - <span data-ttu-id="ae68c-200">sesión en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="ae68c-200">ogs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="ae68c-201">La administración de SCC crea tipos de eventos relacionados con el empleado como “Desvinculación del empleado”, “Contratación del empleados” en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="ae68c-201">SCC Admin creates employee related events types such as “Employee Termination”, “Employee Hire” events in Security and Compliance Center.</span></span>

  - <span data-ttu-id="ae68c-202">La administración de SCC crea la etiqueta de "Retención de empleados" en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="ae68c-202">SCC Admin creates “Employee Retention” label in Security and Compliance Center.</span></span>

  - <span data-ttu-id="ae68c-203">Esta etiqueta de "Retención de empleados" se publica y se aplican manual o automáticamente a los archivos de empleado en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ae68c-203">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint</span></span>

  - <span data-ttu-id="ae68c-204">Un sistema de administración de Recursos Humanos como Workday puede trabajar con Microsoft Flow para ejecutarse periódicamente para administrar archivos del empleado.</span><span class="sxs-lookup"><span data-stu-id="ae68c-204">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files</span></span>

  - <span data-ttu-id="ae68c-205">Cuando un empleado deja la organización, Flow activa la API de REST de retención basada en eventos de M365 que inicia el reloj de retención de archivos específicos del empleado.</span><span class="sxs-lookup"><span data-stu-id="ae68c-205">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="ae68c-206">Usar Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="ae68c-206">Using Microsoft Flow</span></span>

<span data-ttu-id="ae68c-207">Paso 1: crear un flujo para crear un evento mediante la API de REST de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ae68c-207">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![Usar Flow para crear un evento](media/automate-event-driven-retention-flow-1.png)

![Usar Flow para llamar a la API de REST](media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="ae68c-210">Crear un evento</span><span class="sxs-lookup"><span data-stu-id="ae68c-210">Create an event</span></span>

<span data-ttu-id="ae68c-211">Código de ejemplo para llamar a la API de REST</span><span class="sxs-lookup"><span data-stu-id="ae68c-211">Sample code to call the REST API</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ae68c-212">Método</span><span class="sxs-lookup"><span data-stu-id="ae68c-212">Method</span></span></th>
<th><span data-ttu-id="ae68c-213">POST</span><span class="sxs-lookup"><span data-stu-id="ae68c-213">POST</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ae68c-214">URL</span><span class="sxs-lookup"><span data-stu-id="ae68c-214">URL</span></span></td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent)</td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ae68c-215">Encabezados</span><span class="sxs-lookup"><span data-stu-id="ae68c-215">Headers</span></span></td>
<td><span data-ttu-id="ae68c-216">Tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="ae68c-216">Content-Type</span></span></td>
<td><span data-ttu-id="ae68c-217">aplicación/atom+xml</span><span class="sxs-lookup"><span data-stu-id="ae68c-217">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ae68c-218">Cuerpo</span><span class="sxs-lookup"><span data-stu-id="ae68c-218">Body</span></span></td>
<td><p><span data-ttu-id="ae68c-219">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-219">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="ae68c-220">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="ae68c-220">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="ae68c-221">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="ae68c-221">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="ae68c-222">xmlns='http://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-222">xmlns='http://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="ae68c-223">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-223">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="ae68c-224">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-224">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="ae68c-225">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-225">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="ae68c-226">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-226">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="ae68c-227">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-227">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="ae68c-228">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-228">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="ae68c-229">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-229">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="ae68c-230">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-230">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span></span></p>
<p><span data-ttu-id="ae68c-231">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-231">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="ae68c-232">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-232">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="ae68c-233">&lt;/entry&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-233">&lt;/entry&gt;</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ae68c-234">Autenticación</span><span class="sxs-lookup"><span data-stu-id="ae68c-234">Authentication</span></span></td>
<td><span data-ttu-id="ae68c-235">Básica</span><span class="sxs-lookup"><span data-stu-id="ae68c-235">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ae68c-236">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="ae68c-236">Username</span></span></td>
<td><span data-ttu-id="ae68c-237">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="ae68c-237">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ae68c-238">Contraseña</span><span class="sxs-lookup"><span data-stu-id="ae68c-238">Password</span></span></td>
<td><span data-ttu-id="ae68c-239">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="ae68c-239">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a><span data-ttu-id="ae68c-240">Parámetros disponibles</span><span class="sxs-lookup"><span data-stu-id="ae68c-240">Available parameters</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ae68c-241"><strong>Parámetros</strong></span><span class="sxs-lookup"><span data-stu-id="ae68c-241"><strong>Parameters</strong></span></span></th>
<th><span data-ttu-id="ae68c-242"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="ae68c-242"><strong>Description</strong></span></span></th>
<th><span data-ttu-id="ae68c-243"><strong>Notas</strong></span><span class="sxs-lookup"><span data-stu-id="ae68c-243"><strong>Notes</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ae68c-244">&lt;d:Name&gt;&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-244">&lt;d:Name&gt;&lt;/d:Name&gt;</span></span></td>
<td><span data-ttu-id="ae68c-245">Escribe un nombre único para el evento.</span><span class="sxs-lookup"><span data-stu-id="ae68c-245">Provide a unique name for the event,</span></span></td>
<td><span data-ttu-id="ae68c-p120">No puede contener espacios finales ni los siguientes caracteres: % \* \ &amp; &lt; &gt; | # ? , : ;</span><span class="sxs-lookup"><span data-stu-id="ae68c-p120">Cannot contain trailing spaces, and the following characters: % \* \ &amp; &lt; &gt; | # ? , : ;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ae68c-248">&lt;d:eventType&gt;&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-248">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span></span></td>
<td><span data-ttu-id="ae68c-249">Escribe el nombre del tipo de evento (o Guid)</span><span class="sxs-lookup"><span data-stu-id="ae68c-249">Enter event type name (or Guid),</span></span></td>
<td><span data-ttu-id="ae68c-p121">Ejemplo: "Desvinculación del empleado". El tipo de evento debe estar asociado con una etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="ae68c-p121">Example: “Employee termination”. Event type has to be associated with a retention label.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ae68c-252">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-252">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span></span></td>
<td><span data-ttu-id="ae68c-253">Escribe "ComplianceAssetId:" + Id. de empleado</span><span class="sxs-lookup"><span data-stu-id="ae68c-253">Enter “ComplianceAssetId:” + employee Id</span></span></td>
<td><span data-ttu-id="ae68c-254">Ejemplo:&quot;ComplianceAssetId:12345&quot;</span><span class="sxs-lookup"><span data-stu-id="ae68c-254">Example:&quot;ComplianceAssetId:12345&quot;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ae68c-255">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-255">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span></span></td>
<td><span data-ttu-id="ae68c-256">Fecha y hora del evento</span><span class="sxs-lookup"><span data-stu-id="ae68c-256">Event Date and Time</span></span></td>
<td><p><span data-ttu-id="ae68c-257">Formato: aaaa-MM-ddTHH:mm:ssZ, ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ae68c-257">Format: yyyy-MM-ddTHH:mm:ssZ, Example:</span></span></p>
<p><span data-ttu-id="ae68c-258">2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="ae68c-258">2018-12-01T00:00:00Z</span></span></p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="ae68c-259">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="ae68c-259">Response codes</span></span>

| <span data-ttu-id="ae68c-260">**Código de respuesta**</span><span class="sxs-lookup"><span data-stu-id="ae68c-260">**Response Code**</span></span> | <span data-ttu-id="ae68c-261">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ae68c-261">**Description**</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="ae68c-262">302</span><span class="sxs-lookup"><span data-stu-id="ae68c-262">302</span></span>               | <span data-ttu-id="ae68c-263">Redirigir</span><span class="sxs-lookup"><span data-stu-id="ae68c-263">Redirect</span></span>              |
| <span data-ttu-id="ae68c-264">201</span><span class="sxs-lookup"><span data-stu-id="ae68c-264">201</span></span>               | <span data-ttu-id="ae68c-265">Fecha de creación</span><span class="sxs-lookup"><span data-stu-id="ae68c-265">Created</span></span>               |
| <span data-ttu-id="ae68c-266">403</span><span class="sxs-lookup"><span data-stu-id="ae68c-266">403</span></span>               | <span data-ttu-id="ae68c-267">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="ae68c-267">Authorization Failed</span></span>  |
| <span data-ttu-id="ae68c-268">401</span><span class="sxs-lookup"><span data-stu-id="ae68c-268">401</span></span>               | <span data-ttu-id="ae68c-269">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="ae68c-269">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="ae68c-270">Obtener eventos según el intervalo de tiempo</span><span class="sxs-lookup"><span data-stu-id="ae68c-270">Get Events based on time range</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ae68c-271">Método</span><span class="sxs-lookup"><span data-stu-id="ae68c-271">Method</span></span></th>
<th><span data-ttu-id="ae68c-272">GET</span><span class="sxs-lookup"><span data-stu-id="ae68c-272">GET</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ae68c-273">URL</span><span class="sxs-lookup"><span data-stu-id="ae68c-273">URL</span></span></td>
<td><ol start="4" type="1">
<li><p><span data-ttu-id="ae68c-274">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp; EndDateTime = 2019-16: 01</span><span class="sxs-lookup"><span data-stu-id="ae68c-274">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span></span></p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ae68c-275">Encabezados</span><span class="sxs-lookup"><span data-stu-id="ae68c-275">Headers</span></span></td>
<td><span data-ttu-id="ae68c-276">Tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="ae68c-276">Content-Type</span></span></td>
<td><span data-ttu-id="ae68c-277">aplicación/atom+xml</span><span class="sxs-lookup"><span data-stu-id="ae68c-277">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ae68c-278">Autenticación</span><span class="sxs-lookup"><span data-stu-id="ae68c-278">Authentication</span></span></td>
<td><span data-ttu-id="ae68c-279">Básica</span><span class="sxs-lookup"><span data-stu-id="ae68c-279">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ae68c-280">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="ae68c-280">Username</span></span></td>
<td><span data-ttu-id="ae68c-281">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="ae68c-281">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ae68c-282">Contraseña</span><span class="sxs-lookup"><span data-stu-id="ae68c-282">Password</span></span></td>
<td><span data-ttu-id="ae68c-283">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="ae68c-283">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="ae68c-284">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="ae68c-284">Response codes</span></span>

| <span data-ttu-id="ae68c-285">**Código de respuesta**</span><span class="sxs-lookup"><span data-stu-id="ae68c-285">**Response Code**</span></span> | <span data-ttu-id="ae68c-286">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ae68c-286">**Description**</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="ae68c-287">200</span><span class="sxs-lookup"><span data-stu-id="ae68c-287">200</span></span>               | <span data-ttu-id="ae68c-288">Aceptar, una lista de eventos de atom+ xml</span><span class="sxs-lookup"><span data-stu-id="ae68c-288">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="ae68c-289">404</span><span class="sxs-lookup"><span data-stu-id="ae68c-289">404</span></span>               | <span data-ttu-id="ae68c-290">No encontrado</span><span class="sxs-lookup"><span data-stu-id="ae68c-290">Not found</span></span>                         |
| <span data-ttu-id="ae68c-291">302</span><span class="sxs-lookup"><span data-stu-id="ae68c-291">302</span></span>               | <span data-ttu-id="ae68c-292">Redirigir</span><span class="sxs-lookup"><span data-stu-id="ae68c-292">Redirect</span></span>                          |
| <span data-ttu-id="ae68c-293">401</span><span class="sxs-lookup"><span data-stu-id="ae68c-293">401</span></span>               | <span data-ttu-id="ae68c-294">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="ae68c-294">Authorization Failed</span></span>              |
| <span data-ttu-id="ae68c-295">403</span><span class="sxs-lookup"><span data-stu-id="ae68c-295">403</span></span>               | <span data-ttu-id="ae68c-296">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="ae68c-296">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="ae68c-297">Obtén un objeto por id.</span><span class="sxs-lookup"><span data-stu-id="ae68c-297">Get an event by ID</span></span>

| <span data-ttu-id="ae68c-298">Método</span><span class="sxs-lookup"><span data-stu-id="ae68c-298">Method</span></span>         | <span data-ttu-id="ae68c-299">GET</span><span class="sxs-lookup"><span data-stu-id="ae68c-299">GET</span></span>   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| <span data-ttu-id="ae68c-300">URL</span><span class="sxs-lookup"><span data-stu-id="ae68c-300">URL</span></span>            | <span data-ttu-id="ae68c-301">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span><span class="sxs-lookup"><span data-stu-id="ae68c-301">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span></span> |                      |
| <span data-ttu-id="ae68c-302">Encabezado</span><span class="sxs-lookup"><span data-stu-id="ae68c-302">Header</span></span>         | <span data-ttu-id="ae68c-303">Tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="ae68c-303">Content-Type</span></span>                                                                                                                                                                                                                                                       | <span data-ttu-id="ae68c-304">aplicación/atom+xml</span><span class="sxs-lookup"><span data-stu-id="ae68c-304">application/atom+xml</span></span> |
| <span data-ttu-id="ae68c-305">Autenticación</span><span class="sxs-lookup"><span data-stu-id="ae68c-305">Authentication</span></span> | <span data-ttu-id="ae68c-306">Básica</span><span class="sxs-lookup"><span data-stu-id="ae68c-306">Basic</span></span>                                                                                                                                                                                                                                                              |                      |
| <span data-ttu-id="ae68c-307">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="ae68c-307">Username</span></span>       | <span data-ttu-id="ae68c-308">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="ae68c-308">“Complianceuser”</span></span>                                                                                                                                                                                                                                                   |                      |
| <span data-ttu-id="ae68c-309">Contraseña</span><span class="sxs-lookup"><span data-stu-id="ae68c-309">Password</span></span>       | <span data-ttu-id="ae68c-310">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="ae68c-310">“Compliancepassword”</span></span>                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a><span data-ttu-id="ae68c-311">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="ae68c-311">Response codes</span></span>

| <span data-ttu-id="ae68c-312">**Código de respuesta**</span><span class="sxs-lookup"><span data-stu-id="ae68c-312">**Response Code**</span></span> | <span data-ttu-id="ae68c-313">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ae68c-313">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="ae68c-314">200</span><span class="sxs-lookup"><span data-stu-id="ae68c-314">200</span></span>               | <span data-ttu-id="ae68c-315">Aceptar, el cuerpo de la respuesta contiene el evento en atom+ xml</span><span class="sxs-lookup"><span data-stu-id="ae68c-315">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="ae68c-316">404</span><span class="sxs-lookup"><span data-stu-id="ae68c-316">404</span></span>               | <span data-ttu-id="ae68c-317">No encontrado</span><span class="sxs-lookup"><span data-stu-id="ae68c-317">Not found</span></span>                                            |
| <span data-ttu-id="ae68c-318">302</span><span class="sxs-lookup"><span data-stu-id="ae68c-318">302</span></span>               | <span data-ttu-id="ae68c-319">Redirigir</span><span class="sxs-lookup"><span data-stu-id="ae68c-319">Redirect</span></span>                                             |
| <span data-ttu-id="ae68c-320">401</span><span class="sxs-lookup"><span data-stu-id="ae68c-320">401</span></span>               | <span data-ttu-id="ae68c-321">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="ae68c-321">Authorization Failed</span></span>                                 |
| <span data-ttu-id="ae68c-322">403</span><span class="sxs-lookup"><span data-stu-id="ae68c-322">403</span></span>               | <span data-ttu-id="ae68c-323">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="ae68c-323">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="ae68c-324">Obtén un evento por nombre</span><span class="sxs-lookup"><span data-stu-id="ae68c-324">Get an event by name</span></span>

| <span data-ttu-id="ae68c-325">Método</span><span class="sxs-lookup"><span data-stu-id="ae68c-325">Method</span></span>         | <span data-ttu-id="ae68c-326">GET</span><span class="sxs-lookup"><span data-stu-id="ae68c-326">GET</span></span>       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| <span data-ttu-id="ae68c-327">URL</span><span class="sxs-lookup"><span data-stu-id="ae68c-327">URL</span></span>            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| <span data-ttu-id="ae68c-328">Encabezados</span><span class="sxs-lookup"><span data-stu-id="ae68c-328">Headers</span></span>        | <span data-ttu-id="ae68c-329">Tipo de contenido</span><span class="sxs-lookup"><span data-stu-id="ae68c-329">Content-Type</span></span>                                                                                                                                 | <span data-ttu-id="ae68c-330">aplicación/atom+xml</span><span class="sxs-lookup"><span data-stu-id="ae68c-330">application/atom+xml</span></span> |
| <span data-ttu-id="ae68c-331">Autenticación</span><span class="sxs-lookup"><span data-stu-id="ae68c-331">Authentication</span></span> | <span data-ttu-id="ae68c-332">Básica</span><span class="sxs-lookup"><span data-stu-id="ae68c-332">Basic</span></span>                                                                                                                                        |                      |
| <span data-ttu-id="ae68c-333">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="ae68c-333">Username</span></span>       | <span data-ttu-id="ae68c-334">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="ae68c-334">“Complianceuser”</span></span>                                                                                                                             |                      |
| <span data-ttu-id="ae68c-335">Contraseña</span><span class="sxs-lookup"><span data-stu-id="ae68c-335">Password</span></span>       | <span data-ttu-id="ae68c-336">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="ae68c-336">“Compliancepassword”</span></span>                                                                                                                         |                      |

##### <a name="response-codes"></a><span data-ttu-id="ae68c-337">Códigos de respuesta</span><span class="sxs-lookup"><span data-stu-id="ae68c-337">Response codes</span></span>

| <span data-ttu-id="ae68c-338">**Código de respuesta**</span><span class="sxs-lookup"><span data-stu-id="ae68c-338">**Response Code**</span></span> | <span data-ttu-id="ae68c-339">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ae68c-339">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="ae68c-340">200</span><span class="sxs-lookup"><span data-stu-id="ae68c-340">200</span></span>               | <span data-ttu-id="ae68c-341">Aceptar, el cuerpo de la respuesta contiene el evento en atom+ xml</span><span class="sxs-lookup"><span data-stu-id="ae68c-341">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="ae68c-342">404</span><span class="sxs-lookup"><span data-stu-id="ae68c-342">404</span></span>               | <span data-ttu-id="ae68c-343">No encontrado</span><span class="sxs-lookup"><span data-stu-id="ae68c-343">Not found</span></span>                                            |
| <span data-ttu-id="ae68c-344">302</span><span class="sxs-lookup"><span data-stu-id="ae68c-344">302</span></span>               | <span data-ttu-id="ae68c-345">Redirigir</span><span class="sxs-lookup"><span data-stu-id="ae68c-345">Redirect</span></span>                                             |
| <span data-ttu-id="ae68c-346">401</span><span class="sxs-lookup"><span data-stu-id="ae68c-346">401</span></span>               | <span data-ttu-id="ae68c-347">Error de autorización</span><span class="sxs-lookup"><span data-stu-id="ae68c-347">Authorization Failed</span></span>                                 |
| <span data-ttu-id="ae68c-348">403</span><span class="sxs-lookup"><span data-stu-id="ae68c-348">403</span></span>               | <span data-ttu-id="ae68c-349">Error de autenticación</span><span class="sxs-lookup"><span data-stu-id="ae68c-349">Authentication Failed</span></span>                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a><span data-ttu-id="ae68c-350">Uso de PowerShell (ver.6 o posterior) o cualquier cliente HTTP</span><span class="sxs-lookup"><span data-stu-id="ae68c-350">Using PowerShell (ver.6 or higher) or any HTTP client</span></span>

<span data-ttu-id="ae68c-351">Paso 1: Conéctate a PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae68c-351">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="ae68c-352">Paso 2: Ejecuta el siguiente script.</span><span class="sxs-lookup"><span data-stu-id="ae68c-352">Step 2: Run the following script.</span></span>

<table>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae68c-353">param([string]$baseUri)</span><span class="sxs-lookup"><span data-stu-id="ae68c-353">param([string]$baseUri)</span></span></p>
<p><span data-ttu-id="ae68c-354">$userName = &quot;UserName&quot;</span><span class="sxs-lookup"><span data-stu-id="ae68c-354">$userName = &quot;UserName&quot;</span></span></p>
<p><span data-ttu-id="ae68c-355">$password = &quot;Password&quot;</span><span class="sxs-lookup"><span data-stu-id="ae68c-355">$password = &quot;Password&quot;</span></span></p>
<p><span data-ttu-id="ae68c-356">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span><span class="sxs-lookup"><span data-stu-id="ae68c-356">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span></span></p>
<p><span data-ttu-id="ae68c-357">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span><span class="sxs-lookup"><span data-stu-id="ae68c-357">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span></span></p>
<p><span data-ttu-id="ae68c-358">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span><span class="sxs-lookup"><span data-stu-id="ae68c-358">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span></span></p>
<p><span data-ttu-id="ae68c-359">Write-Host &quot;Comienza a crear un evento con el nombre: $EventName&quot;</span><span class="sxs-lookup"><span data-stu-id="ae68c-359">Write-Host &quot;Start to create an event with name: $EventName&quot;</span></span></p>
<p><span data-ttu-id="ae68c-360">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-360">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="ae68c-361">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="ae68c-361">&lt;entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="ae68c-362">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="ae68c-362">xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="ae68c-363">xmlns='http://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-363">xmlns='http://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="ae68c-364">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-364">&lt;category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="ae68c-365">&lt;actualizado&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-365">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="ae68c-366">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-366">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="ae68c-367">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-367">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="ae68c-368">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-368">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="ae68c-369">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-369">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="ae68c-370">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-370">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="ae68c-371">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-371">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="ae68c-372">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="ae68c-372">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="ae68c-373">&lt;/entry&gt;&quot;</span><span class="sxs-lookup"><span data-stu-id="ae68c-373">&lt;/entry&gt;&quot;</span></span></p>
<p><span data-ttu-id="ae68c-374">$event = $null</span><span class="sxs-lookup"><span data-stu-id="ae68c-374">$event = $null</span></span></p>
<p><span data-ttu-id="ae68c-375">probar</span><span class="sxs-lookup"><span data-stu-id="ae68c-375">try</span></span></p>
<p><span data-ttu-id="ae68c-376">{</span><span class="sxs-lookup"><span data-stu-id="ae68c-376">{</span></span></p>
<p><span data-ttu-id="ae68c-377">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="ae68c-377">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="ae68c-378">}</span><span class="sxs-lookup"><span data-stu-id="ae68c-378">}</span></span></p>
<p><span data-ttu-id="ae68c-379">catch</span><span class="sxs-lookup"><span data-stu-id="ae68c-379">catch</span></span></p>
<p><span data-ttu-id="ae68c-380">{</span><span class="sxs-lookup"><span data-stu-id="ae68c-380">{</span></span></p>
<p><span data-ttu-id="ae68c-381">$response = $_. Exception.Response</span><span class="sxs-lookup"><span data-stu-id="ae68c-381">$response = $_.Exception.Response</span></span></p>
<p><span data-ttu-id="ae68c-382">if($response.StatusCode -eq &quot;Redirect&quot;)</span><span class="sxs-lookup"><span data-stu-id="ae68c-382">if($response.StatusCode -eq &quot;Redirect&quot;)</span></span></p>
<p><span data-ttu-id="ae68c-383">{</span><span class="sxs-lookup"><span data-stu-id="ae68c-383">{</span></span></p>
<p><span data-ttu-id="ae68c-384">$url = $response.Headers.Location</span><span class="sxs-lookup"><span data-stu-id="ae68c-384">$url = $response.Headers.Location</span></span></p>
<p><span data-ttu-id="ae68c-385">Write-Host &quot;redirected to $url&quot;</span><span class="sxs-lookup"><span data-stu-id="ae68c-385">Write-Host &quot;redirected to $url&quot;</span></span></p>
<p><span data-ttu-id="ae68c-386">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="ae68c-386">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="ae68c-387">}</span><span class="sxs-lookup"><span data-stu-id="ae68c-387">}</span></span></p>
<p><span data-ttu-id="ae68c-388">}</span><span class="sxs-lookup"><span data-stu-id="ae68c-388">}</span></span></p>
<p><span data-ttu-id="ae68c-389">$event | fl \*</span><span class="sxs-lookup"><span data-stu-id="ae68c-389">$event | fl \*</span></span></p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="ae68c-390">Comprobar el resultado en ambas opciones.</span><span class="sxs-lookup"><span data-stu-id="ae68c-390">Verify the outcome in both options</span></span>

<span data-ttu-id="ae68c-391">Paso 1: Ir al Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="ae68c-391">Step 1: Go to Security & Compliance Center</span></span>

<span data-ttu-id="ae68c-392">Paso 2: Hacer clic en eventos debajo de Gobierno de datos</span><span class="sxs-lookup"><span data-stu-id="ae68c-392">Step 2: Click on Events under Data Governance</span></span>

<span data-ttu-id="ae68c-393">Paso 3: Comprobar que se creó el evento.</span><span class="sxs-lookup"><span data-stu-id="ae68c-393">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="ae68c-394">De forma similar, también se pueden usar las opciones anteriores para automatizar la retención basada en eventos para los siguientes escenarios.</span><span class="sxs-lookup"><span data-stu-id="ae68c-394">Similarly, the above options to automate event based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="ae68c-395">Escenario 2: Contratos que expiran</span><span class="sxs-lookup"><span data-stu-id="ae68c-395">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="ae68c-p122">Una organización puede tener varios registros de un único contrato con clientes, proveedores y partners. Estos documentos pueden encontrarse en una biblioteca de documentos, como SharePoint. La finalización de un contrato determina el inicio del período de retención de los documentos asociados con el contrato. Por ejemplo: todos los registros relacionados con los contratos deben conservarse durante cinco años a partir del momento en el que expira el contrato. El evento que activa el período de retención de cinco años es la expiración del contrato.</span><span class="sxs-lookup"><span data-stu-id="ae68c-p122">An organization can have multiple records for a single contract with customers, vendors and partners. These documents can reside in a document library like SharePoint. The ending of a contract determines the start of the retention period of the documents associated with the contract. For example: all records related to contracts need to be retained for five years from the time the contract expires. The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="ae68c-401">Un sistema de administración de relaciones de cliente (CRM) puede trabajar con Microsoft 365 y activar la retención de documentos del contrato.</span><span class="sxs-lookup"><span data-stu-id="ae68c-401">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents</span></span>

<span data-ttu-id="ae68c-402">**Configuración de retención automatizada basada en eventos para este escenario:**</span><span class="sxs-lookup"><span data-stu-id="ae68c-402">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de los funciones y tareas para escenarios de expiración del contrato](media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="ae68c-404">La administración crea una biblioteca de SharePoint con carpetas diferentes para cada tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="ae68c-404">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="ae68c-405">La administración agrega archivos del contrato como contratos de licencia y contratos de desarrollo para cada carpeta del contrato.</span><span class="sxs-lookup"><span data-stu-id="ae68c-405">Admin adds contract files such as License Contracts, Development Contracts to each contract folder</span></span>

  - <span data-ttu-id="ae68c-406">La administración asigna el id. de activo a cada carpeta de contrato.</span><span class="sxs-lookup"><span data-stu-id="ae68c-406">Admin assigns Asset Id to each contract folder</span></span>

  - <span data-ttu-id="ae68c-407">La administración de SSC inicia sesión en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="ae68c-407">SCC Admin logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="ae68c-408">La administración de SCC crea tipos de eventos relacionados con el contrato como eventos de "Creación del contrato" y "Expiración del contrato" en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="ae68c-408">SCC Admin creates contract related events types such as “Contract Creation”, “Contract Expiration” events in Security and Compliance Center.</span></span>

  - <span data-ttu-id="ae68c-409">La administración de SCC crea la etiqueta "Expiración del contrato" en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="ae68c-409">SCC Admin creates “Contract Expiration” label in Security and Compliance Center.</span></span>

  - <span data-ttu-id="ae68c-410">Esta etiqueta de "Expiración del contrato" se publica y se aplican de forma manual o automática a los archivos del contrato en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ae68c-410">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint</span></span>

  - <span data-ttu-id="ae68c-411">El sistema de administración de contrato puede trabajar con Microsoft Flow o una aplicación similar para ejecutarse periódicamente para administrar archivos de contrato.</span><span class="sxs-lookup"><span data-stu-id="ae68c-411">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files</span></span>

  - <span data-ttu-id="ae68c-412">Si un contrato vence, Microsoft Flow activará la API de REST de retención basada en eventos de M365 que iniciará el reloj de retención de archivos específicos del contrato.</span><span class="sxs-lookup"><span data-stu-id="ae68c-412">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="ae68c-413">Escenario 3: Final de fabricación de productos</span><span class="sxs-lookup"><span data-stu-id="ae68c-413">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="ae68c-p123">Una empresa de elaboración que fabrica diferentes líneas de productos crea varias especificaciones de elaboración y documentos de precios. Cuando el producto ya no se fabrica, todas las especificaciones y documentos vinculados a este producto deben conservarse durante un período específico después del final de la vida útil del producto.</span><span class="sxs-lookup"><span data-stu-id="ae68c-p123">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="ae68c-416">Un sistema de planeación de recursos empresariales (ERP) puede trabajar con Microsoft 365 y Microsoft Flow para activar la retención.</span><span class="sxs-lookup"><span data-stu-id="ae68c-416">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="ae68c-417">**Configuración de retención automatizada basada en eventos para este escenario:**</span><span class="sxs-lookup"><span data-stu-id="ae68c-417">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![Diagrama de las funciones y tareas para escenarios de ciclo de vida del producto](media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="ae68c-419">La administración crea carpetas de productos en el conjunto de documentos como Producto 1, Producto 2, etc.</span><span class="sxs-lookup"><span data-stu-id="ae68c-419">Admin creates product folders in the Document set such as Product 1, Product 2, etc.</span></span>

  - <span data-ttu-id="ae68c-420">La administración agrega los archivos de productos como Especificaciones de fabricación, Precio del producto y Licencias del producto a cada carpeta de producto.</span><span class="sxs-lookup"><span data-stu-id="ae68c-420">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder</span></span>

  - <span data-ttu-id="ae68c-421">La administración le asigna el id. de activo a cada carpeta del producto.</span><span class="sxs-lookup"><span data-stu-id="ae68c-421">Admin assigns Asset Id to each productfolder.</span></span>

  - <span data-ttu-id="ae68c-422">La administración de SSC inicia sesión en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="ae68c-422">SCC Admin logs into the Security & Compliance Center</span></span>

  - <span data-ttu-id="ae68c-423">La administración de SCC crea tipos de eventos relacionados con el empleado como "Inicio de fabricación del producto" y "Final de fabricación del producto" en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="ae68c-423">SCC Admin creates employee related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events in Security and Compliance Center.</span></span>

  - <span data-ttu-id="ae68c-424">La administración de SCC crea la etiqueta "Final de fabricación del producto" en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="ae68c-424">SCC Admin creates “End of Product Manufacturing” label in Security and Compliance Center.</span></span>

  - <span data-ttu-id="ae68c-425">Esta etiqueta de "Final de fabricación del producto" se publica y se aplica de forma manual o automática a los archivos del producto en SharePoint</span><span class="sxs-lookup"><span data-stu-id="ae68c-425">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint</span></span>

  - <span data-ttu-id="ae68c-426">Los sistemas de ERP pueden funcionar con Microsoft Flow o con aplicaciones similares para ejecutarse periódicamente para administrar archivos del producto.</span><span class="sxs-lookup"><span data-stu-id="ae68c-426">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files</span></span>

  - <span data-ttu-id="ae68c-427">Si se termina la fabricación de un producto, Microsoft Flow activará la API de REST de retención basada en eventos de M365 que iniciará el reloj de retención de archivos específicos del producto.</span><span class="sxs-lookup"><span data-stu-id="ae68c-427">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="ae68c-428">Apéndice</span><span class="sxs-lookup"><span data-stu-id="ae68c-428">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="ae68c-429">Cómo usar los resultados de respuesta Redirect 302 para llamar a la API de REST</span><span class="sxs-lookup"><span data-stu-id="ae68c-429">Using Redirect 302 response results to call the REST API</span></span>

1.  <span data-ttu-id="ae68c-430">Invocar una llamada de evento de retención POST con la URL de la API de REST <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (se requieren permisos de administrador global).</span><span class="sxs-lookup"><span data-stu-id="ae68c-430">Invoke a POST retention event call using the REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (Global Admin permissions are required)</span></span>

2.  <span data-ttu-id="ae68c-p124">Comprobar el código de respuesta. Si es 302, obtener la dirección URL redirigida de la propiedad de ubicación del encabezado de respuesta.</span><span class="sxs-lookup"><span data-stu-id="ae68c-p124">Check the response code. If it’s 302, then get the redirected URL from Location property of the response header</span></span>

3.  <span data-ttu-id="ae68c-433">Invocar la llamada al evento de retención POST nuevamente mediante el URL redireccionado.</span><span class="sxs-lookup"><span data-stu-id="ae68c-433">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="ae68c-434">Créditos</span><span class="sxs-lookup"><span data-stu-id="ae68c-434">Credits</span></span>

<span data-ttu-id="ae68c-435">Este tema fue revisado por:</span><span class="sxs-lookup"><span data-stu-id="ae68c-435">This topic was reviewed by:</span></span>

<span data-ttu-id="ae68c-436">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="ae68c-436">Antonio Maio</span></span><br/><span data-ttu-id="ae68c-437">MVP de servicios y aplicaciones de Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="ae68c-437">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="ae68c-438">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="ae68c-438">Antonio.Maio@Protiviti.com</span></span>
