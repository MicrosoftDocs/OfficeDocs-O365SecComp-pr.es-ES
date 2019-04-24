---
title: Configurar los límites de cumplimiento para investigaciones de eDiscovery en Office 365.
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: Use límites de cumplimiento para crear límites lógicos dentro de una organización de Office 365 que controlen las ubicaciones de contenido de usuario que puede buscar un administrador de exhibición de documentos electrónicos. Los límites de cumplimiento usan el filtrado de permisos de búsqueda (también denominados filtros de seguridad de cumplimiento) para controlar los buzones de correo, los sitios de SharePoint y las cuentas de OneDrive pueden ser buscados por usuarios específicos.
ms.openlocfilehash: b23c6d0c96874fb7e6205de6bf8a7f4eb00e4254
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264672"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations-in-office-365"></a>Configurar los límites de cumplimiento para investigaciones de eDiscovery en Office 365.

Los límites de cumplimiento crean límites lógicos dentro de una organización de Office 365 que controlan las ubicaciones de contenido del usuario (como buzones de correo, sitios de SharePoint y cuentas de OneDrive) que los administradores de eDiscovery pueden buscar. Además, los límites de cumplimiento controlan quién puede tener acceso a casos de eDiscovery que se usan para administrar las investigaciones legales, de recursos humanos y de otras investigaciones dentro de la organización. La necesidad de límites de cumplimiento suele ser necesaria para las corporaciones de varias naciones que deben respetar los reglamentos y las regulaciones geográficas, y para los gobiernos, que a menudo se dividen en diferentes agencias. En Office 365, los límites de cumplimiento le ayudan a cumplir estos requisitos cuando realizan búsquedas de contenido y administran investigaciones con casos de eDiscovery.
  
Usaremos el ejemplo de la siguiente ilustración para explicar cómo funcionan los límites de cumplimiento.
  
![Los límites de cumplimiento constan de filtros de permisos de búsqueda que controlan el acceso a agencias y grupos de roles de administrador que controlan el acceso a los casos eDisocovery](media/5c206cc8-a6eb-4d6b-a3a5-21e158791f9a.png)
  
En este ejemplo, contoso LTD es una organización de Office 365 que consta de dos subsidiarias, Fourth Coffee y Coho Winery. La empresa requiere que los administradores de eDiscovery y los investigadores solo puedan realizar búsquedas en los buzones de Exchange, las cuentas de OneDrive y los sitios de SharePoint de su agencia. Además, los profesionales de la exhibición de documentos electrónicos y los investigadores solo pueden ver casos de eDiscovery en su agencia y solo pueden tener acceso a los casos de los que son miembros. Aquí se muestra cómo los límites de cumplimiento cumplen estos requisitos.
  
- La funcionalidad de filtrado de permisos de búsqueda en la búsqueda de contenido controla las ubicaciones de contenido que los administradores y los investigadores de eDiscovery pueden buscar. Esto significa que los administradores de exhibición de documentos electrónicos y los investigadores de la cuarta agencia del café solo pueden buscar ubicaciones de contenido en la sede secundaria de Fourth Coffee. La misma restricción se aplica a la subsidiaria de Coho Winery.
    
    Los grupos de roles controlan quién puede ver los casos de eDiscovery en el centro de seguridad & cumplimiento. Esto significa que los administradores y los investigadores de eDiscovery solo pueden ver los casos de eDiscovery en su agencia.
    
- Los grupos de roles también controlan quién puede asignar miembros a un caso de exhibición de documentos electrónicos. Esto significa que los administradores de eDiscovery y los investigadores solo pueden asignar miembros a los casos a los que son miembros.
    
Este es el proceso para configurar los límites de cumplimiento:
  
[Paso 1: identificar un atributo de usuario para definir las agencias](#step-1-identify-a-user-attribute-to-define-your-agencies)

[Paso 2: archivo a solicitud con soporte técnico de Microsoft para sincronizar el atributo de usuario con las cuentas de OneDrive](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[Paso 3: crear un grupo de roles para cada agencia](#step-3-create-a-role-group-for-each-agency)

[Paso 4: crear un filtro de permisos de búsqueda para aplicar el límite de cumplimiento](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[Paso 5: crear un caso de exhibición de documentos electrónicos para investigaciones dentro de una agencia](#step-5-create-an-ediscovery-case-for-an-intra-agency-investigations)
  
## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>Paso 1: identificar un atributo de usuario para definir las agencias

El primer paso es elegir un atributo de Azure Active Directory que se usará para definir las agencias. Este atributo se usará para crear el filtro de permisos de búsqueda que limita a un administrador de exhibición de documentos electrónicos para buscar solo las ubicaciones de contenido de los usuarios que tienen asignado un valor específico para este atributo. Por ejemplo, supongamos que contoso decide usar el atributo **Department** . El valor de este atributo para los usuarios de la subsidiaria del cuarto café `FourthCoffee` sería y el valor para los usuarios de la subsidiaria de `CohoWinery`Coho Winery sería. En el paso 4, usará este `attribute:value` par (por ejemplo, *Department: fourthcoffee* ) para limitar las ubicaciones de contenido de usuario que los administradores de eDiscovery pueden buscar. 
  
Esta es una lista de atributos de usuario de Azure Active Directory que puede usar para los límites de cumplimiento:
  
- Empresa
    
- CustomAttribute1-CustomAttribute15
    
- Departamento
    
- Oficina

- C (código de país de dos letras)
    
Aunque hay disponibles más atributos de usuario, especialmente para los buzones de Exchange, los atributos enumerados anteriormente son los únicos compatibles actualmente con OneDrive.
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>Paso 2: archivo a solicitud con soporte técnico de Microsoft para sincronizar el atributo de usuario con las cuentas de OneDrive

El siguiente paso consiste en archivar una solicitud con soporte técnico de Microsoft para sincronizar el atributo de Azure Active Directory que eligió en el paso 1 para todas las cuentas de OneDrive de la organización. Una vez que se ha producido esta sincronización, el atributo (y el valor) que eligió en el paso 1 se asignará a una propiedad administrada oculta en SharePoint con nombre `ComplianceAttribute`. Use este atributo para crear el filtro de permisos de búsqueda para OneDrive en el paso 4.
  
Incluya la siguiente información cuando envíe la solicitud a soporte técnico de Microsoft:
  
- El nombre de dominio predeterminado de su organización de Office 365
    
- El nombre del atributo de Azure Active Directory (del paso 1)
    
- El título o la descripción siguiente del propósito de la solicitud de soporte técnico: "habilitar la sincronización de OneDrive para la empresa con Azure Active Directory para filtros de seguridad de cumplimiento". Esto le ayudará a enrutar la solicitud al equipo de ingeniería de exhibición de documentos electrónicos de Office 365 que va a implementar la solicitud.
    
Una vez realizado el cambio de ingeniería y se sincronice el atributo con OneDrive, el soporte técnico de Microsoft le enviará el número de compilación en el que se realizó el cambio y una fecha de implementación estimada. Tenga en cuenta que el proceso de implementación suele tardar 4-6 semanas después de enviar la solicitud de soporte técnico.
  
 **Importante:** Puede completar el paso 3 hasta el paso 5 antes de implementar el cambio. Pero la ejecución de búsquedas de contenido no devolverá documentos de los sitios de OneDrive especificados en el filtro de permisos de búsqueda hasta que se implemente el cambio. 
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>Paso 3: crear un grupo de roles para cada agencia

El siguiente paso es crear los grupos de roles en el centro de seguridad & cumplimiento que se alinearán con las agencias. Le recomendamos que cree un nuevo grupo de roles copiando el grupo integrado de eDiscovery, que agregue los miembros apropiados y quitando roles que puedan no ser aplicables a sus necesidades. Para obtener más información acerca de los roles relacionados con la exhibición de documentos electrónicos, consulte [asignar permisos de exhibición de documentos electrónicos en el centro de cumplimiento de Office 365 Security &](assign-ediscovery-permissions.md).
  
Para crear los grupos de roles, vaya a la página de **permisos** en el centro de seguridad & cumplimiento y cree un grupo de roles para cada equipo en cada agencia que vaya a usar límites de cumplimiento y casos de exhibición de documentos electrónicos para administrar las investigaciones. 
  
Mediante el escenario de límites de cumplimiento de Contoso, es necesario crear cuatro grupos de roles y agregar los miembros apropiados a cada uno de ellos.
  
- Administradores de exhibición de documentos electrónicos de Fourth Coffee
    
- Investigadores de Fourth Coffee
    
- Administradores de exhibición de documentos electrónicos de Coho Winery
    
- Investigadores de Coho Winery
    

  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>Paso 4: crear un filtro de permisos de búsqueda para aplicar el límite de cumplimiento

Una vez que haya creado los grupos de roles para cada agencia, el siguiente paso consiste en crear los filtros de permisos de búsqueda que asocian cada grupo de funciones a su agencia específica y define el límite de cumplimiento en sí. Debe crear un filtro de permisos de búsqueda para cada agencia. Para obtener más información acerca de la creación de filtros de permisos de seguridad, vea [configurar el filtrado de permisos para búsqueda de contenido](permissions-filtering-for-content-search.md).
  
Esta es la sintaxis que se usa para crear un filtro de permisos de búsqueda usado para los límites de cumplimiento.

```
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<Compliance attribute from Step 1>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq <AttributeValue>' -or Site_Path -like <SharePointURL> *'" -Action <Action >
```
  
Esta es una descripción de cada parámetro del comando:
  
-  `FilterName`-Especifica el nombre del filtro. Use un nombre que describa o identifique la agencia en la que se usará el filtro. 
    
-  `Users`: Especifica los usuarios o grupos que obtienen este filtro aplicado a las acciones de búsqueda de contenido que realizan. Para los límites de cumplimiento, este parámetro especifica los grupos de roles (que ha creado en el paso 3) en la Agencia para la que está creando el filtro. Nota Este es un parámetro de varios valores para que pueda incluir uno o varios grupos de funciones separados por comas. 
    
-  `Filters`-Especifica los criterios de búsqueda para el filtro. Para los límites de cumplimiento, deberá definir los siguientes filtros. Cada uno se aplica a una ubicación de contenido de usuario. 
    
  -  `Mailbox`: Especifica los buzones de correo que los grupos de roles `Users` definidos en el parámetro pueden buscar. Para los límites de cumplimiento, *ComplianceAttribute* es el mismo atributo que identificó en el paso 1 y *AttributeValue* especifica la Agencia. Este filtro permite a los miembros del grupo de funciones buscar solo en los buzones de una agencia específica; por ejemplo, `"Mailbox_Department -eq 'FourthCoffee'"` . 
    
  -  `Site`: Especifica las cuentas de OneDrive que pueden buscar los grupos de `Users` roles definidos en el parámetro. Para el filtro de OneDrive, use la cadena `ComplianceAttribute`real; Esto se asignará al mismo atributo que identificó en el paso 1 y que se sincronice con las cuentas de OneDrive como resultado de la solicitud de soporte que envió en el paso 2;  *AttributeValue* especifica la Agencia. Este filtro permite que los miembros del grupo de roles solo busquen en las cuentas de OneDrive de una agencia específica; por ejemplo, `"Site_ComplianceAttribute -eq 'FourthCoffee'"`.
    
  -  `Site_Path`: Especifica los sitios de SharePoint que pueden buscar los grupos de `Users` roles definidos en el parámetro. La *SharePointURL* especifica los sitios de la agencia que pueden buscar los miembros del grupo de roles; por ejemplo,`"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`
    
-  `Action`: Especifica el tipo de acción de búsqueda de cumplimiento a la que se aplica el filtro. Por ejemplo, `-Action Search` solo aplicaría el filtro cuando los miembros de los grupos de roles definidos `Users` en el parámetro ejecuten una búsqueda de contenido. En este caso, el filtro no se aplicaría al exportar los resultados de la búsqueda. Para los límites de cumplimiento `-Action All` , use para que el filtro se aplique a todas las acciones de búsqueda. 
    
    Para obtener una lista de las acciones de búsqueda de contenido, consulte la sección "New-ComplianceSecurityFilter" en [configurar el filtrado de permisos para la búsqueda de contenido](permissions-filtering-for-content-search.md#new-compliancesecurityfilter).
    
A continuación, se muestran ejemplos de los dos filtros de permisos de búsqueda que se crearían para admitir el escenario de límites de cumplimiento de contoso.
  
 **Fourth Coffee**

```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```
   
 **Bodega Coho**

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-an-intra-agency-investigations"></a>Paso 5: crear un caso de exhibición de documentos electrónicos para investigaciones dentro de una agencia

El último paso consiste en crear un nuevo caso de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento y, a continuación, agregar el grupo de roles, que ha creado en el paso 3, como miembro del caso. Esto da como resultado dos características importantes del uso de límites de cumplimiento:
  
- Solo los miembros del grupo de roles que se agreguen al caso podrán ver y acceder al caso en el centro de seguridad & cumplimiento. Por ejemplo, si el grupo de funciones de Fourth Coffee es el único miembro de un caso, los miembros del grupo de roles de administradores de exhibición de documentos electrónicos de Fourth Coffee (o los miembros de cualquier otro grupo de roles) no podrán ver ni acceder al caso.
    
- Cuando un miembro del grupo de funciones asignado a un caso ejecuta una búsqueda asociada con el caso, solo podrá buscar en las ubicaciones de contenido de su agencia (definido por el filtro de permisos de búsqueda que creó en el paso 4).


Para crear un nuevo caso y asignar miembros:
    
1. Vaya a la página **exhibición** de documentos electrónicos en el centro de seguridad & cumplimiento y cree un nuevo caso. 
    
2. En la lista de casos de eDiscovery, haga clic en el nombre del caso que acaba de crear.
    
3. En la página desplegable **administrar este caso** , en **grupos de roles**de ![administración,](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) haga clic en agregar icono **Agregar**.
    
    ![Agregar un grupo de roles como miembro de un caso de exhibición de documentos electrónicos](media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. En la lista de grupos de roles, seleccione uno de los grupos de roles que ha creado en el paso 3 y haga clic en **Agregar**.
    
5. Haga clic en **Guardar** en el control flotante **administrar este caso** para guardar el cambio. 

## <a name="compliance-boundary-limitations"></a>Limitaciones de los límites de cumplimiento

Tenga en cuenta las siguientes limitaciones al administrar casos de eDiscovery e investigaciones que usan límites de cumplimiento.
  
- Al crear y ejecutar una búsqueda de contenido, puede seleccionar ubicaciones de contenido que están fuera de la Agencia. Sin embargo, debido al filtro de permisos de búsqueda, el contenido de esas ubicaciones no se incluirá en los resultados de la búsqueda.
    
- Los límites de cumplimiento no se aplican a las retenciones en casos de eDiscovery. Esto significa que un administrador de exhibición de documentos electrónicos en una agencia puede poner a un usuario en suspensión en una agencia diferente. Sin embargo, el límite de cumplimiento se aplicará si el administrador de exhibición de documentos electrónicos busca en las ubicaciones de contenido del usuario que se colocó en suspensión. Esto significa que el administrador de exhibición de documentos electrónicos no podrá buscar en las ubicaciones de contenido del usuario, aunque haya podido poner el usuario en espera.
    
    Además, las estadísticas de retención solo se aplicarán a las ubicaciones de contenido de la Agencia.
    
- Los filtros de permisos de búsqueda no se aplican a las carpetas públicas de Exchange.

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>Búsqueda y exportación de contenido en entornos multiGeográfico

Los filtros de permisos de búsqueda también permiten controlar dónde se enruta el contenido para la exportación y en qué centro de datos se puede buscar al buscar ubicaciones de contenido en un [entorno multigeográfico de SharePoint](https://go.microsoft.com/fwlink/?linkid=860840).
  
- **Exportar resultados** de la búsqueda: puede exportar los resultados de la búsqueda de los buzones de Exchange, los sitios de SharePoint y las cuentas de OneDrive desde un centro de información específico. Esto significa que puede especificar la ubicación del centro de recursos desde la que se exportarán los resultados de la búsqueda.

    Use el parámetro **Region** para los cmdlets **New-ComplianceSecurityFilter** o **set-ComplianceSecurityFilter** para crear o cambiar el centro de recursos al que se redirigirá la exportación.
  
    |**Valor del parámetro**|**Ubicación del centro de recursos**|
    |:-----|:-----|
    |NAM  <br/> |Norteamérica (los centros de datos reales están en los Estados Unidos)  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Asia Pacífico  <br/> |
    |CAN <br/> |Canada
    
- **Enrutar búsquedas de contenido** : puede enrutar las búsquedas de contenido de los sitios de SharePoint y las cuentas de OneDrive a un centro de datos satélite. Esto significa que puede especificar la ubicación del centro de recursos donde se ejecutarán las búsquedas.
    
    Use los siguientes valores para los valores de parámetro de **región** para controlar el centro de datos en el que se ejecutarán las búsquedas de contenido al buscar sitios de SharePoint y ubicaciones de OneDrive. Tenga en cuenta que en la tabla siguiente también se muestran las exportaciones del centro de recursos que se redirigirán. 
  
    |**Valor del parámetro**|**Ubicaciones de enrutamiento de centro de recursos para la exportación**|
    |:-----|:-----|
    |NAM  <br/> |Infórmenos  <br/> |
    |EUR  <br/> |Europa  <br/> |
    |APC  <br/> |Asia Pacífico  <br/> |
    |CAN  <br/> |Infórmenos  <br/> |
    |AUS  <br/> |Asia Pacífico  <br/> |
    |KOR  <br/> |Centro de datos predeterminado de la organización  <br/> |
    |GBR  <br/> |Europa  <br/> |
    |JPN  <br/> |Asia Pacífico  <br/> |
    |IND  <br/> |Asia Pacífico  <br/> |
    |LAM  <br/> |Infórmenos  <br/> |
   
> [!NOTE]
> Si no especifica el parámetro **Region** para un filtro de permisos de búsqueda, se buscará en la región de SharePoint predeterminada de las organizaciones y, a continuación, los resultados de la búsqueda se exportarán al centro de recursos más cercano. 
  
A continuación, se muestran ejemplos de cómo usar el parámetro **Region** al crear filtros de permisos de búsqueda para límites de cumplimiento. Esto supone que la subsidiaria de Fourth Coffee se encuentra en Norteamérica y que Coho Winery está en Europa. 
  
```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```
   
Tenga en cuenta lo siguiente cuando busque y Exporte contenido en entornos multigeográfico.
  
- El parámetro **Region** no controla las búsquedas de buzones de Exchange; se buscará en todos los centros de datos cuando se busque en buzones. Para limitar el ámbito en el que se pueden buscar los buzones de correo de **** Exchange, use el parámetro filters al crear o cambiar un filtro de permisos de búsqueda. 
    
- Si es necesario que un administrador de eDiscovery busque en varias regiones de SharePoint, deberá crear una cuenta de usuario diferente para el administrador de eDiscovery, que se puede usar en el filtro de permisos de búsqueda para especificar la región alternativa en la que el Se encuentran los sitios de SharePoint o las cuentas de OneDrive.
    
- Al buscar contenido en SharePoint y OneDrive, el parámetro **Region** dirige las búsquedas a la ubicación principal o satélite donde el administrador de eDiscovery realizará las investigaciones de eDiscovery. Si un administrador de exhibición de documentos electrónicos busca sitios de SharePoint y OneDrive fuera de la región especificada en el filtro de permisos de búsqueda, no se devolverá ningún resultado de búsqueda. 
    
- Al exportar los resultados de la búsqueda, el contenido de todas las ubicaciones de contenido (incluidos Exchange, Skype empresarial, SharePoint, OneDrive y otros servicios de Office 365 que puede buscar mediante la herramienta de búsqueda de contenido) se cargará en la ubicación de almacenamiento de Azure en el Centro de datos especificado por el parámetro **Region** . Esto permite a las organizaciones mantener el cumplimiento de las normas al no permitir que el contenido se exporte entre límites controlados. Si no se especifica ninguna región en el filtro de permisos de búsqueda, el contenido se carga en la región predeterminada de la organización. 
    
- Puede editar un filtro de permisos de búsqueda existente para agregar o cambiar la región ejecutando el siguiente comando:

    ```
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```
 
## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

 **Quién puede crear y administrar filtros de permisos de búsqueda (con los cmdlets New-ComplianceSecurityFilter y set-ComplianceSecurityFilter)?**
  
Para crear, ver y modificar los filtros de permisos de búsqueda, debe ser miembro del grupo de roles de administración de la organización en el centro de seguridad & cumplimiento.
  
 **Si se asigna un administrador de exhibición de documentos electrónicos a más de un grupo de roles que abarque varias agencias, ¿cómo buscan contenido en una agencia u otra?**
  
El administrador de eDiscovery puede agregar parámetros a la consulta de búsqueda que restringirá la búsqueda a una agencia específica. Por ejemplo, si una organización ha especificado la propiedad **CustomAttribute10** para diferenciar las agencias, pueden anexar lo siguiente a su consulta de búsqueda para buscar buzones de correo y cuentas de `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`OneDrive en una agencia específica:.
  
 **¿Qué sucede si se cambia el valor del atributo que se usa como atributo de cumplimiento en un filtro de permisos de búsqueda?**
  
Un filtro de permisos de búsqueda tarda hasta tres días en aplicar el límite de cumplimiento si se cambia el valor del atributo que se usa en el filtro. Por ejemplo, en el escenario de Contoso, supongamos que un usuario de la Agencia de la Fourth Coffee se transfiere a la Agencia de bodega Coho. Como resultado, el valor del atributo **Department** del objeto de usuario se cambia de *fourthcoffee* a *CohoWinery* . En esta situación, la exhibición de documentos electrónicos y los inversores de Fourth Coffee obtendrán los resultados de la búsqueda de ese usuario durante un máximo de 3 días después de cambiar el atributo. De forma similar, tardará hasta tres días antes de que los investigadores de eDiscovery Winery y los investigadores reciban los resultados de la búsqueda del usuario. 
  
 **¿Puede un administrador de exhibición de documentos electrónicos ver contenido de dos límites de cumplimiento independientes?**
  
Sí. Esto puede hacerse agregando el usuario a los grupos de roles que tienen visibilidad en ambas agencias.
  
 **¿Funcionan los filtros de permisos de búsqueda para las suspensiones de casos de eDiscovery, las directivas de retención de Office 365 o DLP?**
  
No, no en este momento
  
 **Si especifica una región para controlar dónde se exporta el contenido, pero no tengo una organización de SharePoint en esa región, ¿puedo seguir buscando en SharePoint?**
  
Si el área especificada en el filtro de permisos de búsqueda no existe en la organización, se buscará en la región predeterminada.
  
 **¿Cuál es el número máximo de filtros de permisos de búsqueda que se pueden crear en una organización?**
  
No hay ningún límite en el número de filtros de permisos de búsqueda que se pueden crear en una organización. Sin embargo, el rendimiento de la búsqueda se verá afectado cuando haya más de 100 filtros de permisos de búsqueda. Para mantener el número de filtros de permisos de búsqueda en la organización tan pequeños como sea posible, cree filtros que combinen las reglas para Exchange, SharePoint y OneDrive en un único filtro de permisos de búsqueda siempre que sea posible.
