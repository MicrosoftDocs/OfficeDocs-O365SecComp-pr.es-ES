---
title: Set up Information Rights Management (IRM) in SharePoint admin center.
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: Obtenga información sobre cómo usar IRM de SharePoint Online a través de Microsoft Azure Active Directory Rights Management Services (RMS) para proteger listas y bibliotecas de documentos de SharePoint.
ms.openlocfilehash: 16a76ecda37bd5480285dd70670843a88198bdb7
ms.sourcegitcommit: a97e7da9a1f870540f0bdcba7be5fb6f8bd12f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2019
ms.locfileid: "35756852"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>Set up Information Rights Management (IRM) in SharePoint admin center.

## <a name="introduction"></a>Introducción

En SharePoint Online, la protección de IRM se aplica a los archivos en el nivel de lista y biblioteca. Antes de que su organización pueda usar la protección IRM, primero debe configurar Rights Management. IRM se basa en el servicio Azure Rights Management de Azure Information Protection para cifrar y asignar restricciones de uso. Algunos planes de Office 365 incluyen Azure Rights Management, pero no todos. Para obtener más información, lea [cómo los servicios y las aplicaciones de Office admiten Azure Rights Management](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support).
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>Activar el servicio IRM con el centro de administración de SharePoint

Para que su organización pueda proteger las listas y bibliotecas de SharePoint, debe activar primero el servicio Rights Management para su organización. Para obtener información sobre cómo ver la [activación de Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/activate-service). Debe usar una cuenta profesional o educativa que tenga privilegios de administrador global de Office 365 para habilitar el servicio Rights Management. De lo contrario, no podrá usar las características de IRM con SharePoint Online.
  
Después de activar el servicio Rights Management, inicie sesión en el centro de administración de SharePoint para activar IRM.
  
1. Inicie sesión en Office 365 como administrador global o de SharePoint.
    
2. Seleccione el icono ![del iniciador de aplicaciones el icono del iniciador de aplicaciones en Office 365](media/e5aee650-c566-4100-aaad-4cc2355d909f.png) en la esquina superior izquierda y elija **Administrador** para abrir el centro de administración de Office 365. (If you don't see the Admin tile, you don't have Office 365 administrator permissions in your organization.) 
    
3. En el panel izquierdo, elija **Centro** \> de administración de **SharePoint**.
    
4. En el panel izquierdo, elija **configuración**y, a continuación, elija **página Configuración clásica**.
    
5. En la sección **Information Rights Management (IRM)** , elija **usar el servicio de IRM especificado en la configuración**y, a continuación, elija **Actualizar configuración de IRM**. Después de actualizar la configuración de IRM, las personas de su organización pueden empezar a usar IRM en sus bibliotecas de documentos y listas de SharePoint. Sin embargo, las opciones para hacerlo pueden tardar hasta una hora en aparecer en la configuración de la biblioteca y la configuración de la lista.
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>IRM: habilitar listas y bibliotecas de documentos de SharePoint
<a name="__toc220831191"> </a>

Después de actualizar la configuración de IRM, los propietarios de sitios pueden proteger IRM las listas y bibliotecas de documentos de SharePoint. Para obtener más información, vea [aplicar Information Rights Management a una lista o biblioteca](apply-irm-to-a-list-or-library.md).
  
Cuando los propietarios de sitios habilitan IRM para una lista o biblioteca, pueden proteger los tipos de archivo admitidos en dicha lista o biblioteca. Cuando IRM está habilitado para una biblioteca, la administración de derechos se aplica a todos los archivos de esa biblioteca. Cuando se habilita IRM para una lista, la administración de derechos solo se aplica a los archivos adjuntos a los elementos de lista, no a los elementos de la lista reales.
  
Cuando los usuarios descargan archivos en una lista o biblioteca habilitada para IRM, los archivos se cifran para que solo los usuarios autorizados puedan verlos. Cada archivo administrado con derechos también contiene una licencia de emisión que impone restricciones a los usuarios que ven el archivo. Las restricciones típicas incluyen convertir un archivo en sólo lectura, deshabilitar la copia de texto, evitar que los usuarios guarden una copia local y evitar que los usuarios impriman el archivo. Los programas cliente que pueden leer tipos de archivo compatibles con IRM usan la licencia de emisión dentro del archivo administrado con derechos para aplicar estas restricciones. Este es el modo en que un archivo administrado con derechos conserva su protección incluso después de descargarlo. Para habilitar IRM en una lista o biblioteca, consulte [aplicar Information Rights Management a una lista o biblioteca](apply-irm-to-a-list-or-library.md).
  
No puede crear o editar documentos en una biblioteca habilitada para IRM con Office online. En su lugar, una persona a la vez puede descargar y editar archivos cifrados con IRM. Use la protección y desprotección para administrar la *co-autoría* o la creación en varios usuarios. 
  
Cuando descarga un archivo PDF de una biblioteca protegida con IRM, Office 365 crea un archivo PDF protegido. La extensión del archivo no cambiará, pero el archivo está protegido. Para ver este archivo, necesitará Azure Information Protection Viewer, el cliente completo de Azure Information Protection u otra aplicación que admita la visualización de archivos PDF protegidos. 
  
SharePoint Online admite el cifrado de los siguientes tipos de archivo:
  
- PDF
    
- Los formatos de archivo 97-2003 para los siguientes programas de Microsoft Office: Word, Excel y PowerPoint
    
- Formatos Office Open XML para los siguientes programas de Microsoft Office: Word, Excel y PowerPoint
    
- Formato de especificación de papel XML (XPS)
    
## <a name="next-steps"></a>Pasos siguientes
<a name="__toc220831191"> </a>

Una vez que haya habilitado IRM para SharePoint Online, puede empezar a aplicar Rights Management a listas y bibliotecas. Para obtener más información, vea [aplicar Information Rights Management a una lista o biblioteca](apply-irm-to-a-list-or-library.md).
  
El nuevo cliente de sincronización de OneDrive para Windows ahora admite la sincronización de bibliotecas de documentos de SharePoint protegidas por IRM y ubicaciones de OneDrive (siempre que la configuración de IRM de la biblioteca no esté configurada para expirar los derechos de acceso a documentos). Para obtener más información o para empezar a implementar el nuevo cliente de sincronización, vea [implementar el nuevo cliente de sincronización de OneDrive para Windows](https://support.office.com/article/3f3a511c-30c6-404a-98bf-76f95c519668).
  
[Principio de página](#introduction)  

