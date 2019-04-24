---
title: 'Centro de administración de Exchange en Exchange Online Protection  '
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: El Centro de administración de Exchange (EAC) es la consola de administración basada en web para Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 983f6fe6b9f1592115e524315c9e52e08fed5101
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256008"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a>Centro de administración de Exchange en Exchange Online Protection  

El Centro de administración de Exchange (EAC) es la consola de administración basada en web para Microsoft Exchange Online Protection (EOP). 
  
¿Está buscando la versión de Exchange 2013 de este tema? Vea [Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx).
  
¿Está buscando la versión de Exchange Online de este tema? Vea [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).
  
## <a name="accessing-the-eac"></a>Acceso a EAC

En la mayoría de los casos, los clientes de EOP obtendrán acceso al EAC a través del centro de administración 365 de Microsoft. Encontrará un vínculo a EOP en el menú desplegable del icono **Administrador**, que está al lado del icono **Yo**. Haga clic en el icono **Administrador** y seleccione **Protección en línea de Exchange** en el menú desplegable para ir al EAC. 
  
You can also access the EAC sign in page directly via the following URL: https://admin.protection.outlook.com/ecp/\<companydomain\>. For example, https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com. After specifying your user credentials you will be taken directly into the EAC.
  
## <a name="common-user-interface-elements-in-the-eac"></a>Elementos comunes de la interfaz de usuario en EAC

En esta sección se describen los elementos de la interfaz de usuario del EAC.
  
![EOP: AdminCenter](media/EOP-AdminCenter.png)
  
### <a name="feature-pane"></a>Panel de características

Este es el primer nivel de navegación para la mayoría de las tareas que realizará en el EAC. El panel de características se organiza por áreas.
  
1. **Destinatarios** Aquí es donde se muestran los usuarios internos y los contactos externos. 
    
2. **Permisos** Aquí es donde se administran los roles de administrador. 
    
3. **Administración de cumplimiento** Aquí es donde se encuentran los registros de auditoría y los informes, como el informe de grupos de roles de administrador. 
    
4. **Protección** En esta sección es donde se administra la protección antimalware y contra correo no deseado para la organización, así como los mensajes en cuarentena. 
    
5. **Flujo del correo** Aquí es donde se administran las reglas, los dominios aceptados y conectores, así como las ubicaciones en las que se realiza el seguimiento de mensajes. 
    
### <a name="tabs"></a>Pestañas

Las pestañas son el segundo nivel de navegación. Las áreas de características contienen varias pestañas y cada área representa a una característica.
  
### <a name="toolbar"></a>Barra de herramientas

Al hacer clic en la mayoría de las pestañas, verá una barra de herramientas. La barra de herramientas tiene iconos que realizan una acción específica. La siguiente tabla describe los iconos y sus acciones.
  
|**Icono**|**Nombre**|**Action**|
|:-----|:-----|:-----|
|![Agregar icono](media/ITPro-EAC-AddIcon.gif)           <br/> |Agregar, nuevo  <br/> |Utilice este icono para crear un nuevo objeto. Algunos de estos iconos tienen una flecha hacia abajo asociada donde puede hacer clic para mostrar objetos adicionales que puede crear.  <br/> |
|![Icono Editar](media/ITPro-EAC-EditIcon.gif)           <br/> |Editar  <br/> |Utilice este icono para editar un objeto.  <br/> |
|![Eliminar icono](media/ITPro-EAC-DeleteIcon.gif)           <br/> |Eliminar  <br/> |Utilice este icono para eliminar un objeto. Algunos iconos eliminados tienen una flecha hacia abajo donde puede hacer clic para mostrar opciones adicionales.  <br/> |
|![icono de Buscar](media/ITPro-EAC-.gif)           <br/> |Búsqueda  <br/> |Usar este icono para abrir una casilla de búsqueda donde puede escribir una frase de búsqueda para el objeto que desee encontrar.  <br/> |
|![Icono Actualizar](media/ITPro-EAC-RefreshIcon.gif)           <br/> |Actualizar  <br/> |Utilice este icono para actualizar la vista de lista.  <br/> |
|![Icono Más opciones](media/ITPro-EAC-MoreOptionsIcon.gif)           <br/> |Más opciones  <br/> |Use este icono para ver más acciones que puede realizar para los objetos de la pestaña. Por ejemplo, al hacer clic en este icono en **Destinatarios \> Usuarios**, se muestra la opción para realizar una **Búsqueda avanzada**.  <br/> |
|![Icono flecha arriba](media/ITPro-EAC-UpArrowIcon.gif)![Icono flecha abajo](media/ITPro-EAC-DownArrowIcon.gif)           <br/> |Flecha hacia arriba y flecha hacia abajo  <br/> |Utilice estos iconos para mover la prioridad de un objeto hacia arriba o hacia abajo.  <br/> |
|![Icono de quitar](media/ITPro-EAC-RemoveIcon.gif)           <br/> |Quitar  <br/> |Utilice este icono para quitar objetos de la lista.  <br/> |
   
### <a name="list-view"></a>Vista de lista

Cuando seleccione una pestaña, en la mayoría de los casos verá la vista de lista. El límite de visualización de la vista de lista del EAC es de 10.000 objetos aproximadamente. Además, la paginación se incluye para que pueda paginar los resultados.
  
### <a name="details-pane"></a>panel Detalles

Cuando seleccione un objeto de la vista de lista, la información acerca del objeto se muestra en el panel de detalles. En algunos casos, el panel de detalles incluye tareas de administración.
  
### <a name="me-tile-and-help"></a>Mosaico Yo y Ayuda

El mosaico **Yo** permite cerrar sesión en el EAC e iniciar sesión como un usuario diferente. Desde el menú desplegable en **Ayuda**![Icono de ayuda](media/ITPro-EAC-HelpIcon.gif), puede realizar las siguientes acciones: 
  
1. **Ayuda** Haga clic en ![Icono de ayuda](media/ITPro-EAC-HelpIcon.gif) para ver el contenido de la ayuda en línea. 
    
2. **Deshabilitar el globo de Ayuda** El globo de Ayuda muestra la ayuda contextual de los campos cuando crea o edita un objeto. Puede desactivar el globo de Ayuda o activarlo si estaba deshabilitado. 
    
3. **Copyright** Haga clic en este vínculo para leer el aviso de derechos de autor de Exchange Online Protection. 
    
4. **Privacidad** Haga clic para leer la directiva de privacidad de Exchange Online Protection. 
    
## <a name="supported-browsers"></a>Exploradores compatibles

Para conseguir la mejor experiencia con EAC, le recomendamos que use siempre la versión más actualizada de los exploradores, clientes de Office y aplicaciones. También le recomendamos que instale las actualizaciones de software cuando estén disponibles. Para obtener más información acerca de los navegadores compatibles y los requisitos del sistema para el servicio, vea [Requisitos del sistema de Office 365](https://go.microsoft.com/fwlink/p/?LinkID=402699). 
  
## <a name="supported-languages-in-eop"></a>Idiomas admitidos en EOP

Los siguientes idiomas están disponibles y son compatibles con Exchange Online Protection.
  
- Amhárico
    
- Árabe
    
- Vasco (Euskera)
    
- Bengalí (India)
    
- Búlgaro
    
- Catalán
    
- Chino (simplificado)
    
- Chino (tradicional)
    
- Croata
    
- Checo
    
- Danés
    
- Neerlandés
    
- Neerlandés
    
- Inglés
    
- Estonio
    
- Filipino (Filipinas)
    
- Finés
    
- Francés
    
- Gallego
    
- Alemán
    
- Griego
    
- Gujarati
    
- Hebreo
    
- Hindi
    
- Húngaro
    
- Islandés
    
- Indonesio
    
- Italiano
    
- Japonés
    
- Kannada
    
- Kazajo
    
- Kiswahili
    
- Coreano
    
- Letón
    
- Lituano
    
- Malayo (Brunei Darussalam)
    
- Malayo (Malasia)
    
- Malayalam
    
- Maratí
    
- Noruego (Bokmal)
    
- Noruego (Nynorsk)
    
- Odia
    
- Persa
    
- Polaco
    
- Portugués (Brasil)
    
- Portugués (Portugal)
    
- Rumano
    
- Ruso
    
- Serbio (cirílico, Serbia)
    
- Serbio (latino)
    
- Eslovaco
    
- Esloveno
    
- Español
    
- Sueco
    
- Tamil
    
- Telugu
    
- Tailandés
    
- Turco
    
- Ucraniano
    
- Urdu
    
- Vietnamita
    
- Galés
    

