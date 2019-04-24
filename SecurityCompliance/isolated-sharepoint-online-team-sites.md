---
title: Sitios de grupo de SharePoint Online aislados
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: 'Resumen: obtenga información sobre los usos de sitios de grupo de SharePoint Online aislados.'
ms.openlocfilehash: 17e6fffc72a366d2cbb2c96e2b6bc812d0670e94
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32253928"
---
# <a name="isolated-sharepoint-online-team-sites"></a>Sitios de grupo de SharePoint Online aislados

 **Resumen:** obtenga información sobre los usos de sitios de grupo de SharePoint Online aislados.
  
Los sitios de grupo de SharePoint Online son una forma sencilla de crear rápidamente un espacio para la colaboración en notas, documentos, artículos, calendarios y otros recursos en Microsoft Office 365. Los sitios de grupo de SharePoint Online se basan en un grupo de Office 365 y tienen un modelo de administración simplificado para permitir la colaboración abierta con un conjunto privado de miembros del grupo o con toda la organización. Un sitio de grupo predeterminado de SharePoint Online permite a los miembros del grupo de Office 365 invitar a otros usuarios y controlar la configuración de los permisos.
  
Pero, en algunos casos, puede que quiera crear un sitio de grupo de SharePoint Online para colaborar en el que los permisos del sitio se controlen de forma más estricta con pertenencia a grupos y niveles de permisos de SharePoint Online, que solo pueden controlar los administradores de SharePoint. Esto se denomina un sitio aislado, que está aislado para el conjunto de usuarios que colaboran, visualizan sus contenidos o administran el sitio. Puede que necesite usar un sitio aislado en estos casos:
  
- Un proyecto secreto en su organización.
    
- La ubicación de propiedad intelectual altamente confidencial o valiosa para su organización.
    
- Los recursos de una acción legal realizada por su organización o por la organización que sea objeto de esa acción legal.
    
- Para compartir una suscripción de Office 365 entre varias organizaciones que se superpongan parcialmente, pero que, en su mayoría, existan como entidades empresariales separadas.
    
Estos son los requisitos para un sitio aislado:
  
- Solo los administradores de SharePoint Online pueden administrar el sitio, como la pertenencia a grupos para el acceso al sitio y la configuración de permisos personalizados.
    
- Los miembros del sitio no pueden invitar a otros miembros al sitio de grupo.
    
- Los usuarios que no sean miembros del sitio aislado no pueden solicitar acceso al sitio. Recibirán una página web de acceso denegado cuando intenten obtener acceso a cualquier dirección URL asociada con el sitio.
    
La ventaja de exigir un control de acceso centralizado y permisos personalizados por los administradores de SharePoint Online es que el sitio permanecerá aislado con el paso del tiempo. Por ejemplo, los miembros actuales no pueden, ya sea de forma intencionada o por error, invitar o configurar permisos personalizados para otros usuarios de la suscripción de Office 365 que no tendrían que ser miembros del sitio.
  
Un sitio aislado se puede usar con otras características, como:
  
- Information Rights Management, para garantizar que los recursos del sitio permanezcan cifrados, incluso si se descargan localmente y se cargan en otro sitio que esté disponible para toda la organización.
    
- Prevención de pérdida de datos para impedir que los usuarios envíen los recursos del sitio, como archivos, por correo electrónico.
    
## <a name="next-steps"></a>Pasos siguientes

Para probar un sitio de grupo de SharePoint Online aislado en una suscripción de prueba, vea las instrucciones paso a paso en [Entorno de desarrollo y pruebas en un sitio de grupo aislado de SharePoint Online](isolated-sharepoint-online-team-site-dev-test-environment.md).
  
Cuando esté preparado para implementar un sitio de grupo de SharePoint Online aislado en producción, vea las consideraciones de diseño paso a paso en [Diseñar un sitio de grupo aislado de SharePoint Online](design-an-isolated-sharepoint-online-team-site.md).
  
## <a name="see-also"></a>Vea también

[Diseñar un sitio de grupo de SharePoint Online aislado](design-an-isolated-sharepoint-online-team-site.md)
  
[Administrar un sitio de grupo de SharePoint Online aislado](manage-an-isolated-sharepoint-online-team-site.md)

[Implementar un sitio de grupo de SharePoint Online aislado](deploy-an-isolated-sharepoint-online-team-site.md)


