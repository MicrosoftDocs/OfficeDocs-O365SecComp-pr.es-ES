---
title: Establecer seguridad de Information Rights Management (IRM) en el centro de administración de SharePoint
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: Obtenga información sobre cómo usar IRM de SharePoint Online a través de Microsoft Azure Active Directory Rights Management Services (RMS) para proteger las bibliotecas de documentos y listas de SharePoint.
ms.openlocfilehash: dea8c71ce67207b3c40a1f934f90e63740f70f29
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536198"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>Establecer seguridad de Information Rights Management (IRM) en el centro de administración de SharePoint

Dentro de SharePoint Online, la protección de IRM se aplica a los archivos en el nivel de lista y biblioteca. Antes de que su organización puede usar la protección de IRM, debe configurar Rights Management. IRM se basa en el servicio de administración de derechos de Azure de protección de la información de Azure para cifrar y asignar restricciones de uso. Algunos planes de Office 365 incluyen Azure Rights Management, pero no todas. Para obtener más información, lea [los servicios y aplicaciones de Office cómo admiten Azure Rights Management](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support).
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>Activar servicio de IRM mediante el centro de administración de SharePoint

Antes de que su organización puede bibliotecas y listas de SharePoint de protección de IRM, primero debe activar el servicio de administración de derechos para su organización. Para obtener más información vea cómo [Activar Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/activate-service). Debe usar una cuenta de trabajo o escuela que tiene privilegios de administrador global de Office 365 para habilitar el servicio de administración de derechos. De lo contrario, no podrá usar las características de IRM con SharePoint Online.
  
Después de activar el servicio de administración de derechos, inicie sesión en el centro de administración de SharePoint para activar IRM.
  
1. Inicie sesión en Office 365 como administrador global o de SharePoint.
    
2. Seleccione el icono del iniciador de aplicaciones ![El icono del iniciador de aplicaciones de Office 365](media/e5aee650-c566-4100-aaad-4cc2355d909f.png) en la esquina superior izquierda y elija **Administración** para abrir el centro de administración de Office 365. (Si no ve el icono de Administrador, no tiene permisos de administrador de Office 365 en su organización). 
    
3. En el panel izquierdo, elija **centros de administración** \> **SharePoint**.
    
4. En el panel izquierdo, elija **configuración**.
    
5. En la sección **Information Rights Management (IRM)** , elija **usar el servicio IRM especificado en su configuración**y, a continuación, elija **Actualizar la configuración de IRM**. Después de actualizar la configuración de IRM, las personas de su organización pueden empezar a usar IRM en sus bibliotecas de documentos y listas de SharePoint. Sin embargo, las opciones para hacerlo pueden tardar hasta una hora que aparezca en configuración de la biblioteca y la configuración de la lista.
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>Listas y bibliotecas de documentos de SharePoint para habilitar IRM
<a name="__toc220831191"> </a>

Después de actualizar la configuración de IRM, los propietarios de sitios pueden proteger con IRM sus listas de SharePoint y las bibliotecas de documentos. Para obtener más información, vea [Aplicar Information Rights Management a una lista o biblioteca](apply-irm-to-a-list-or-library.md).
  
Cuando los propietarios de sitios habilita IRM para una lista o biblioteca, se pueden proteger los tipos de archivo admitidos en dicha lista o biblioteca. Cuando se habilita IRM para una biblioteca, la administración de derechos se aplica a todos los archivos en esa biblioteca. Cuando se habilita IRM para una lista, administración de derechos se aplica sólo a los archivos que están adjuntos a elementos de lista, no a los elementos de lista reales.
  
Cuando las personas descargan archivos en una biblioteca o lista habilitada con IRM, los archivos se cifran para que sólo las personas autorizadas puedan verlos. Cada archivo administrado con derechos también contiene una licencia de emisión que impone restricciones a las personas que ver el archivo. Las restricciones típicas incluyen hacer un archivo de sólo lectura, deshabilitar la copia de texto, impedir que los usuarios guardar una copia local y evitar que se imprima el archivo. Programas de cliente que pueden leer tipos de archivo compatibles con IRM utilizan la licencia de emisión dentro del archivo administrado con derechos para aplicar estas restricciones. Se trata de cómo un archivo administrado con derechos conserva su protección incluso después de descargarlo. Para habilitar IRM en una lista o biblioteca, vea [Aplicar Information Rights Management a una lista o biblioteca](apply-irm-to-a-list-or-library.md).
  
No se puede crear o editar documentos en una biblioteca de IRM habilitado con Office Online. En su lugar, una persona a la vez puede descargar y editar los archivos cifrados mediante IRM. Usar protección y desprotección para administrar la *co-autoría* o creación a través de varios usuarios. 
  
Cuando se descarga un archivo PDF desde una biblioteca de protegidos por IRM, Office 365 crea un archivo PDF protegido. No cambie la extensión del archivo, pero el archivo está protegido. Para ver este archivo necesitará el Visor de protección de la información de Azure, el cliente de protección de la información de Azure completo, u otra aplicación que admita la visualización de archivos PDF protegidos. 
  
SharePoint Online admite el cifrado de los tipos de archivo siguientes:
  
- PDF
    
- Los formatos de archivo 97-2003 para los siguientes programas de Microsoft Office: Word, Excel y PowerPoint
    
- Formatos Office Open XML para los siguientes programas de Microsoft Office: Word, Excel y PowerPoint
    
- El formato XML Paper Specification (XPS)
    
## <a name="next-steps"></a>Pasos siguientes
<a name="__toc220831191"> </a>

Una vez que se ha habilitado IRM para SharePoint Online, puede iniciar la aplicación de administración de derechos a las listas y bibliotecas. Para obtener información, vea [Aplicar Information Rights Management a una lista o biblioteca](apply-irm-to-a-list-or-library.md).
  
El nuevo cliente de sincronización de OneDrive para Windows ahora admite la sincronización de las bibliotecas de documentos de SharePoint protegidos por IRM y ubicaciones de OneDrive (siempre que no se establece la configuración de IRM para la biblioteca que contiene que expirarán los derechos de acceso del documento). Para obtener más información, o para empezar a implementar al cliente de sincronización nueva, vea [implementar el nuevo cliente de sincronización de OneDrive para Windows](https://support.office.com/article/3f3a511c-30c6-404a-98bf-76f95c519668).
  
[Parte superior de la página](set-up-irm-in-sp-admin-center.md#__top)
  

