---
title: Configurar los límites de cumplimiento para investigaciones de eDiscovery en Office 365.
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: Use los límites de cumplimiento para crear los límites lógicos dentro de una organización de Office 365 que controlan las ubicaciones de contenido de usuario que puede buscar un administrador de exhibición de documentos electrónicos. Límites de cumplimiento usar permisos de búsqueda filtrado (también denominado conformidad seguridad filtros) para controlar qué buzones de correo, los sitios de SharePoint y OneDrive cuentas se pueden buscar por usuarios específicos.
ms.openlocfilehash: 2bebd29fa7701ba07aae7170142263aeaec5569e
ms.sourcegitcommit: c7264f3a6a97f1ff544544e2c722e7825e265fa1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2018
ms.locfileid: "26299244"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations-in-office-365"></a>Configurar los límites de cumplimiento para investigaciones de eDiscovery en Office 365.

Límites de cumplimiento creación los límites lógicos dentro de una organización de Office 365 que controlan las ubicaciones de contenido usuario (por ejemplo, buzones de correo, los sitios de SharePoint y las cuentas de OneDrive) que pueden buscar los administradores de exhibición de documentos electrónicos. Además, el cumplimiento de normas límites controlar quién puede tener acceso a los casos de exhibición de documentos electrónicos que usa para administrar el departamento jurídico, recursos humanos u otras investigaciones dentro de la organización. La necesidad de los límites de cumplimiento a menudo es necesaria para las empresas de las Naciones múltiples que tienen que respete las leyes y fronteras geográficas y para los gobiernos, que a menudo se dividen en distintos organismos. En Office 365, Ayuda de los límites de cumplimiento cumple estos requisitos al realizar búsquedas y contenido managing investigaciones con casos de exhibición de documentos electrónicos.
  
Utilizaremos el ejemplo en la siguiente ilustración para explicar cómo funcionan los límites de cumplimiento.
  
![Límites de cumplimiento constan de filtros de búsqueda de los permisos que controlar el acceso a las agencias y el rol de administrador grupos que controlan el acceso a los casos de eDisocovery](media/5c206cc8-a6eb-4d6b-a3a5-21e158791f9a.png)
  
En este ejemplo, Contoso LTD es una organización de Office 365 que consta de dos subsidiarias, cuarto café y zonas de Coho Winery. La empresa necesita que investigadores y administradores de exhibición de documentos electrónicos sólo pueden buscar los buzones de Exchange, las cuentas de OneDrive y sitios de SharePoint en su agencia. Además, los administradores de exhibición de documentos electrónicos e investigadores sólo pueden ver los casos de exhibición de documentos electrónicos en el en su agencia, y sólo puede acceder a los casos que son miembro de. Aquí es cómo los límites de cumplimiento cumplan estos requisitos.
  
- Los permisos de búsqueda funcionalidad en los controles de búsqueda de contenido de filtrado de las ubicaciones de contenido que pueden buscar investigadores y los administradores de la exhibición de documentos electrónicos. Esto significa que los administradores de exhibición de documentos electrónicos e investigadores en la Agencia cuarto café solo pueden buscar ubicaciones de contenido en la subsidiaria cuarto café. La misma restricción se aplica a la subsidiaria de Coho Winery.
    
    Función de grupos de controlar quién puede ver los casos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento. Esto significa que investigadores y los administradores de la exhibición de documentos electrónicos sólo pueden ver los casos de exhibición de documentos electrónicos en su agencia.
    
- Grupos de roles también controlan quién puede asignar miembros a un caso de exhibición de documentos electrónicos. Esto significa que investigadores y los administradores de la exhibición de documentos electrónicos sólo pueden asignar a miembros a los casos que ellos mismos son miembros de.
    
Este es el proceso para configurar los límites de cumplimiento:
  
[Paso 1: Identificar un atributo de usuario para definir los organismos](#step-1-identify-a-user-attribute-to-define-your-agencies)

[Paso 2: Una solicitud con Microsoft Support para sincronizar el atributo de usuario a las cuentas de OneDrive de archivos](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[Paso 3: Crear un grupo de roles para cada agencia](#step-3-create-a-role-group-for-each-agency)

[Paso 4: Crear un filtro de permisos de búsqueda para aplicar el límite de cumplimiento](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[Paso 5: Crear un caso de exhibición de documentos electrónicos para un investigaciones dentro de un Agencia](#step-5-create-an-ediscovery-case-for-an-intra-agency-investigations)
  
## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>Paso 1: Identificar un atributo de usuario para definir los organismos

El primer paso es elegir un atributo de Active Directory de Azure para usar que definirá los organismos. Este atributo se usará para crear el filtro de permisos de búsqueda que limita una exhibición de documentos electrónicos administrador para buscar sólo las ubicaciones de contenido de los usuarios que tengan asignados un valor específico para este atributo. Por ejemplo, supongamos que Contoso decide usar el atributo de **departamento** . El valor para este atributo para los usuarios de la subsidiaria cuarto café sería `FourthCoffee` y el valor para los usuarios de la subsidiaria de Coho Winery sería `CohoWinery`. En el paso 4, utilizará este `attribute:value` par (por ejemplo, el *Departamento: FourthCoffee* ) para limitar el usuario contenido ubicaciones que pueden buscar los administradores de exhibición de documentos electrónicos. 
  
Aquí tiene una lista de atributos de usuario de Azure Active Directory que se pueden usar para los límites de cumplimiento:
  
- Company
    
- CountryCode
    
- CustomAttribute1 - CustomAttribute15
    
- Departamento
    
- Oficina
    
Si bien más atributos de usuario están disponibles, especialmente para los buzones de Exchange, los atributos enumerados anteriormente son los únicos compatibles actualmente con OneDrive.
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>Paso 2: Una solicitud con Microsoft Support para sincronizar el atributo de usuario a las cuentas de OneDrive de archivos

El siguiente paso es una solicitud con Microsoft Support para sincronizar el atributo de Azure Active Directory que haya elegido en el paso 1 a todas las cuentas de OneDrive en la organización de archivos. Después de la sincronización se produce, el atributo (y su valor) que eligió en el paso 1 se asignará a una propiedad administrada oculta en SharePoint denominado `ComplianceAttribute`. Este atributo, debe usar para crear el filtro de búsqueda de permisos para OneDrive en el paso 4.
  
Incluir la siguiente información al enviar la solicitud de soporte técnico de Microsoft:
  
- El nombre de dominio predeterminado de la organización de Office 365
    
- El nombre del atributo de Azure Active Directory (desde el paso 1)
    
- El título o la descripción del propósito de la solicitud de soporte técnico siguientes: "Habilitar OneDrive para profesionales sincronización con Azure Active Directory para cumplimiento filtros de seguridad". Esto le ayudará a enrutar la solicitud para el equipo de ingeniería de exhibición de documentos electrónicos de Office 365 que implementará la solicitud.
    
Una vez que se realiza el cambio de ingeniería y el atributo se sincroniza a OneDrive, Microsoft Support le enviará el número de compilación que se realizó el cambio en y una fecha de implementación estimado. Tenga en cuenta que el proceso de implementación realiza normalmente 4 a 6 semanas después de enviar la solicitud de soporte técnico.
  
 **Importante:** Puede completar el paso 3 al paso 5 antes de implementar el cambio. Pero que ejecuta las búsquedas de contenido no devolverá los documentos de los sitios de OneDrive especificados en el filtro de búsqueda de permisos hasta después de que se implementa el cambio. 
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>Paso 3: Crear un grupo de roles para cada agencia

El siguiente paso es crear los grupos de funciones en la seguridad de Office 365 &amp; centro de cumplimiento que va a alinear con los organismos. Le recomendamos que cree un nuevo grupo de funciones copiar el grupo de administradores de exhibición de documentos electrónicos integrados, agregando a los miembros adecuados y quitar funciones que pueden no ser aplicables a sus necesidades. Para obtener más información acerca de las funciones relacionadas con la exhibición de documentos electrónicos, vea [asignar permisos de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; centro de cumplimiento](assign-ediscovery-permissions.md).
  
Para crear los grupos de funciones, vaya a la página de **permisos** en la seguridad &amp; centro de cumplimiento y crear un grupo de roles para cada equipo en cada agencia que va a usar los límites de cumplimiento y los casos de exhibición de documentos electrónicos para administrar las investigaciones. 
  
Usa el escenario de los límites de cumplimiento de normas de Contoso, deben crearse cuatro grupos de roles y los miembros correspondientes se agregan a cada uno de ellos.
  
- Administradores de exhibición de documentos electrónicos café cuarto
    
- Cuarto investigadores café
    
- Coho Winery eDiscovery administradores
    
- Investigadores de Coho Winery
    

  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>Paso 4: Crear un filtro de permisos de búsqueda para aplicar el límite de cumplimiento
<a name="step4"> </a>

Después de crear grupos de roles para cada agencia, el siguiente paso es crear los filtros de permisos de búsqueda que asociación cada grupo de roles a su agencia específica y define el límite de cumplimiento propio. Debe crear un filtro de permisos de búsqueda para cada agencia. Para obtener más información acerca de cómo crear filtros de permisos de seguridad, vea [configurar los permisos de filtrado para la búsqueda de contenido](permissions-filtering-for-content-search.md).
  
Ésta es la sintaxis que se usa para crear un filtro de permisos de búsqueda usado para los límites de cumplimiento.

```
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<Compliance attribute from Step 1>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq <AttributeValue>' -or Site_Path -like <SharePointURL> *'" -Action <Action >
```
  
Ésta es una descripción de cada parámetro en el comando:
  
-  `FilterName`-Especifica el nombre del filtro. Usar un nombre que describe o identifica la Agencia que filtran se usará en. 
    
-  `Users`-Especifica los usuarios o grupos que obtener este filtro aplicado a las acciones de búsqueda de contenido que al llevar a cabo. Para los límites de cumplimiento, este parámetro especifica los grupos de roles (que creó en el paso 3) de la Agencia que está creando el filtro para. Tenga en cuenta que esto es un parámetro de valor múltiple, por lo que puede incluir uno o varios grupos de roles, separados por comas. 
    
-  `Filters`-Especifica los criterios de búsqueda para el filtro. Para los límites de cumplimiento, se definen los siguientes filtros. Cada uno de ellos se aplica a una ubicación de contenido de usuario. 
    
  -  `Mailbox`-Especifica los buzones que los grupos de roles definidos en el `Users` parámetro puede buscar. Para los límites de cumplimiento, *ComplianceAttribute* es el mismo atributo que ha identificado en el paso 1 y *AttributeValue* especifica la Agencia. Este filtro permitir que los miembros del grupo de roles para buscar sólo los buzones de correo en una agencia específica; Por ejemplo, `"Mailbox_Department -eq 'FourthCoffee'"` . 
    
  -  `Site`-Especifica las cuentas de OneDrive para la que los grupos de roles definidos en el `Users` parámetro puede buscar. Para el filtro OneDrive, use la cadena real `ComplianceAttribute`; Esto va a asignar al mismo atributo que ha identificado en el paso 1 y que se sincroniza con las cuentas de OneDrive como resultado de la solicitud de soporte técnico que han enviado en el paso 2;  *AttributeValue* especifica la Agencia. Este filtro permitir que los miembros del grupo de roles para buscar sólo las cuentas de OneDrive en una agencia específica; Por ejemplo, `"Site_ComplianceAttribute -eq 'FourthCoffee'"`.
    
  -  `Site_Path`-Especifica los sitios de SharePoint que los grupos de roles definidos en el `Users` parámetro puede buscar. El *SharePointURL* especifica los sitios de la Agencia que pueden buscar los miembros del grupo de roles; Por ejemplo,`Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`
    
-  `Action`-Especifica el tipo de acción de búsqueda de cumplimiento de normas que el filtro se aplica a. Por ejemplo, `-Action Search` sólo se aplicará el filtro cuando los miembros de los grupos de roles definidos en el `Users` parámetro ejecuta una búsqueda de contenido. En este caso, no se aplica el filtro al exportar los resultados de búsqueda. Para los límites de cumplimiento, use `-Action All` por lo que el filtro se aplica a todas las acciones de búsqueda. 
    
    Para obtener una lista de las acciones de búsqueda de contenido, vea la sección "New-ComplianceSecurityFilter" en [configurar los permisos de filtrado para la búsqueda de contenido](permissions-filtering-for-content-search.md#new-compliancesecurityfilter).
    
Estos son ejemplos de los filtros de búsqueda de dos permisos que se crean para admitir el escenario de los límites de cumplimiento de normas de Contoso.
  
 **Cuarto café**

```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```
   
 **Coho Winery**

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-an-intra-agency-investigations"></a>Paso 5: Crear un caso de exhibición de documentos electrónicos para un investigaciones dentro de un Agencia

El paso final consiste en crear un nuevo caso de exhibición de documentos electrónicos en la seguridad &amp; centro de cumplimiento y, a continuación, agregue el grupo de roles, que creó en el paso 3: como un miembro de las mayúsculas y minúsculas. Esto da como resultado dos características importantes del uso de los límites de cumplimiento:
  
- Sólo los miembros del grupo de roles agregado a las mayúsculas y minúsculas pueden ver y tener acceso el caso de la seguridad &amp; centro de cumplimiento. Por ejemplo, si el grupo de roles del cuarto investigadores café es el único miembro de un caso, a continuación, los miembros del grupo de roles de administradores de exhibición de documentos electrónicos de cuarto café (o los miembros de cualquier otro grupo) no puedan ver o tener acceso a las mayúsculas y minúsculas.
    
- Cuando un miembro del grupo de roles asignado a un caso ejecuta una búsqueda asociada con el caso, sólo podrán buscar las ubicaciones de contenido dentro de su agencia (que se define mediante el filtro de permisos de búsqueda que creó en el paso 4.)


Para crear un nuevo caso y asignar a los miembros:
    
1. Vaya a la página de **exhibición de documentos electrónicos** en la seguridad &amp; centro de cumplimiento y crear un nuevo caso. 
    
2. En la lista de casos de exhibición de documentos electrónicos, haga clic en el nombre del caso que acaba de crear.
    
3. En la página de emergente **administrar este caso** , bajo **grupos de roles de administrar**, haga clic en ![icono Agregar](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Agregar**.
    
    ![Agregar un grupo de roles como un miembro de un caso de exhibición de documentos electrónicos](media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. En la lista de grupos de roles, seleccione uno de los grupos de funciones que creó en el paso 3 y haga clic en **Agregar**.
    
5. Haga clic en **Guardar** en la barra flotante de **administrar este caso** para guardar el cambio. 

## <a name="compliance-boundary-limitations"></a>Limitaciones de límite de cumplimiento

Tenga las siguientes limitaciones en cuenta al administrar casos de exhibición de documentos electrónicos e investigaciones que usen de límites de cumplimiento.
  
- Al crear y ejecutar una búsqueda de contenido, puede seleccionar las ubicaciones de contenido que están fuera de la Agencia. Sin embargo, debido al filtro de permisos de búsqueda, el contenido de esas ubicaciones no se incluirán en los resultados de búsqueda.
    
- Límites de cumplimiento de normas no se aplican a las suspensiones en los casos de exhibición de documentos electrónicos. Esto significa que un administrador de exhibición de documentos electrónicos en una agencia de viajes puede colocar un usuario en una agencia de diferente en espera. Sin embargo, se aplicará el límite de cumplimiento si el Administrador de exhibición de documentos electrónicos busca en las ubicaciones de contenido del usuario que se ha puesto en espera. Esto significa que el Administrador de exhibición de documentos electrónicos no ser capaz de búsqueda de ubicaciones de contenido del usuario, incluso si fueran puedas colocar el usuario en suspensión.
    
    Además, mantenga las estadísticas sólo se aplicarán a las ubicaciones de contenido en la Agencia.
    
- No se aplican filtros de búsqueda de permisos para carpetas públicas de Exchange.

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>Búsqueda y exportación de contenido en entornos de Multi-Geo

Filtros de búsqueda de permisos también permiten controlar donde se enruta el contenido para la exportación y se puede buscar en el centro de datos al buscar en las cuentas de OneDrive y sitios de SharePoint en un [entorno de SharePoint Multi-Geo](https://go.microsoft.com/fwlink/?linkid=860840):
  
- Exportar los resultados de búsqueda de un centro de datos específico. Esto significa que puede especificar la que ubicación del centro de los datos que se van a exportar los resultados de la búsqueda.
    
- Enrutar las búsquedas de cuentas de OneDrive y sitios de SharePoint a un centro de datos de satélite. Esto significa que puede especificar la ubicación del centro de datos donde se ejecutará las búsquedas.
    
Use el parámetro de **región** para los cmdlets **New-ComplianceSecurityFilter** o **Set-ComplianceSecurityFilter** para crear o cambiar qué la exportación se enrutarán a través de centros de datos.
  
|**Valor del parámetro**|**Ubicación del centro de datos**|
|:-----|:-----|
|NAM  <br/> |América del Norte (datos reales de centros se encuentran en los Estados Unidos)  <br/> |
|EUR  <br/> |Europa  <br/> |
|APC  <br/> |Asia Pacífico  <br/> |
|CAN <br/> |Canadá
   
De forma similar, puede usar los siguientes valores para los valores de parámetro de **región** para controlar qué centro de datos que se ejecutará búsquedas de contenido al buscar en las ubicaciones de SharePoint y OneDrive. Tenga en cuenta que en la siguiente tabla muestra también qué exportaciones se enrutarán a través del centro de datos. 
  
|**Valor del parámetro**|**Ubicaciones de enrutamiento para la exportación del centro de datos**|
|:-----|:-----|
|NAM  <br/> |EE. UU.  <br/> |
|EUR  <br/> |Europa  <br/> |
|APC  <br/> |Asia Pacífico  <br/> |
|CAN  <br/> |EE. UU.  <br/> |
|AUS  <br/> |Asia Pacífico  <br/> |
|KOR  <br/> |Centro de datos de la organización de forma predeterminada  <br/> |
|GBR  <br/> |Europa  <br/> |
|JPN  <br/> |Asia Pacífico  <br/> |
|IND  <br/> |Asia Pacífico  <br/> |
|LAM  <br/> |EE. UU.  <br/> |
   
 **Nota:** Si no especifica el parámetro de región para un filtro de permisos de búsqueda, se buscará en la región de SharePoint predeterminados de las organizaciones, a continuación, se exportan los resultados de búsqueda en el centro de datos más cercano. 
  
Estos son ejemplos del uso de la **-región** parámetro al crear filtros de permiso de búsqueda de los límites de cumplimiento. Esto supone que la subsidiaria cuarto café se encuentra en Norteamérica y que Coho Winery es en Europa. 
  
```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```
   
Tenga en cuenta al buscar y exportar lo siguiente contenido en entornos de multi-ubican.
  
- El parámetro **Region** no controlar las búsquedas de buzones de Exchange; se buscará en todos los centros de datos al buscar en los buzones de correo. Para limitar el ámbito de los de Exchange que se pueden buscar en los buzones de correo, use el parámetro de **filtros** al crear o cambiar un filtro de búsqueda de permisos. 
    
- Si es necesario para una exhibición de documentos electrónicos el administrador para buscar en varias áreas de SharePoint, que necesitará para crear una cuenta de usuario diferente para ese exhibición de documentos electrónicos el administrador que se puede usar en el filtro de permisos de búsqueda para especificar la región alternativa donde el Sitios de SharePoint o OneDrive cuentas se encuentran.
    
- Cuando se busca contenido en SharePoint y OneDrive, el parámetro **Region** dirige las búsquedas en puede ser el principal o satélite ubicación donde el Administrador de exhibición de documentos electrónicos llevará a cabo investigaciones de exhibición de documentos electrónicos. Si un administrador de exhibición de documentos electrónicos busca en sitios de SharePoint y OneDrive fuera de la región que se especifica en el filtro de permisos de búsqueda, no se devolverá ningún resultado de búsqueda. 
    
- Al exportar los resultados de búsqueda, se cargará el contenido de todas las ubicaciones de contenido (incluido Exchange, Skype para profesionales, SharePoint, OneDrive y otros servicios de Office 365 que se pueden buscar mediante la herramienta de búsqueda de contenido) a la ubicación de almacenamiento de Azure en el Centro de datos que es especificado por el parámetro de **región** . Esto ayuda a las organizaciones a permanecer dentro de cumplimiento al no permitir que el contenido que se exportará a través de bordes controlados. Si no se especifica ninguna región en el filtro de permisos de búsqueda, el contenido se cargará en región predeterminados de la organización. 
    
- Puede editar un filtro existente de permisos de búsqueda para agregar o cambiar la región, ejecute el comando siguiente:

    ```
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```
 
## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

 **¿Quién puede crear y administrar los filtros de permisos de búsqueda (con los cmdlets de Set-ComplianceSecurityFilter y New-ComplianceSecurityFilter)?**
  
Para crear, ver y modificar filtros de búsqueda de permisos, tiene que ser un miembro del grupo de roles de administración de la organización en la seguridad &amp; centro de cumplimiento.
  
 **Si un administrador de exhibición de documentos electrónicos se asigna a más de un grupo de roles que abarca varias agencias, ¿cómo busca contenido en una agencia u otro?**
  
El Administrador de exhibición de documentos electrónicos puede agregar parámetros a su consulta de búsqueda que restringe la búsqueda a una agencia de específica. Por ejemplo, si una organización ha especificado la propiedad **CustomAttribute10** para diferenciar los organismos, puede anexar lo siguiente a su consulta de búsqueda para buscar los buzones de correo y las cuentas de OneDrive en una agencia específica: `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`.
  
 **¿Qué sucede si se cambia el valor del atributo que se utiliza como el atributo de cumplimiento de normas en un filtro de permisos de búsqueda?**
  
Se tarda hasta 3 días para un filtro de permisos de búsqueda para aplicar el límite de cumplimiento, si se cambia el valor del atributo que se usa en el filtro. Por ejemplo, en el escenario de Contoso supongamos que un usuario en la Agencia cuarto café se transfiere a la Agencia de Coho Winery. Como resultado, se cambia el valor del atributo de **departamento** en el objeto de usuario de *FourthCoffee* a *CohoWinery* . En esta situación, los inversores y exhibición de documentos electrónicos cuarto café obtendrá los resultados de búsqueda para ese usuario para copia de seguridad 3 días después de que se ha cambiado el atributo. De forma similar, tardar hasta 3 días antes de los administradores de exhibición de documentos electrónicos de Coho Winery e investigadores obtendrá los resultados de búsqueda para el usuario. 
  
 **¿Un administrador de exhibición de documentos electrónicos vean contenido desde dos límites de cumplimiento independiente?**
  
Sí. Esto puede realizarse mediante la adición del usuario a grupos de roles que tienen visibilidad a ambos organismos.
  
 **¿Funciona de filtros de permisos para suspensiones de casos de exhibición de documentos electrónicos, las directivas de retención de Office 365 o DLP la búsqueda?**
  
No, no en este momento
  
 **Si especifica un área de control donde se exporta contenido, pero no tengo una organización de SharePoint en esa región, ¿aún búsqueda SharePoint?**
  
Si la región especificada en el filtro de permisos de búsqueda no existe en la organización, se buscará en la región predeterminada.
  
 **¿Qué es el número máximo de filtros de permisos de búsqueda que se pueden crear en una organización?**
  
No hay ningún límite para el número de filtros de permisos de búsqueda que se pueden crear en una organización. Sin embargo, el rendimiento de la búsqueda se verán afectado cuando hay más de 100 filtros de permisos de búsqueda. Para mantener el número de filtros de búsqueda de permisos en la organización tan pequeños como sea posible, cree los filtros que se combinan las reglas para Exchange, SharePoint y OneDrive en un filtro de permisos de búsqueda único siempre que sea posible.
