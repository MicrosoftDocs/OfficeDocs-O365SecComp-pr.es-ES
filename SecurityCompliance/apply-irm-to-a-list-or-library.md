---
title: Aplicar Information Rights Management (IRM) a una lista o biblioteca
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
ms.collection:
- M365-security-compliance
description: Puede usar Information Rights Management (IRM) para ayudar a controlar y proteger los archivos que se descargan de listas o bibliotecas.
ms.openlocfilehash: 3c350a3648b77992dd8e86ee47498efc327b2af8
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152342"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a>Aplicar Information Rights Management (IRM) a una lista o biblioteca

Puede usar Information Rights Management (IRM) para ayudar a controlar y proteger los archivos que se descargan de listas o bibliotecas.
  
## <a name="before-you-begin"></a>Antes de empezar

- El servicio Azure Rights Management (Azure RMS) de Azure Information Protection y el equivalente local, Active Directory Rights Management Services (AD RMS), admite Information Rights Management for sites. No se necesita ninguna instalación independiente o adicional.
    
- Antes de aplicar IRM a una lista o biblioteca, primero debe habilitarlo un administrador del sitio.
    
- Para aplicar IRM a una lista o biblioteca, debe tener permisos de administrador para dicha lista o biblioteca.
    
- Si usa SharePoint Online, es posible que los usuarios experimenten tiempos de espera al descargar archivos más grandes protegidos por IRM. Si esto ocurre, aplique la protección de IRM mediante los programas de Office y almacene archivos de mayor tamaño en una biblioteca de SharePoint que no use IRM.
    
> [!NOTE]
> Si usa SharePoint Server 2013, un administrador del servidor debe instalar protectores en todos los servidores front-end web para cada tipo de archivo que los miembros de su organización deseen proteger mediante IRM. 
  
## <a name="apply-irm-to-a-list-or-library"></a>Aplicar IRM a una lista o biblioteca
<a name="__toc256598179"> </a>

![Configuración de Information Rights Management](media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. Vaya a la lista o biblioteca para la que desea configurar IRM.
    
2. En la cinta, haga clic en la pestaña **biblioteca** y, a continuación, haga clic en **configuración de biblioteca**. (Si está trabajando en una lista, haga clic en la pestaña **lista** y, a continuación, haga clic en configuración de la **lista**).
    
    ![Botones de configuración de la biblioteca de SharePoint en la cinta](media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. En **permisos y administración**, haga clic en **Information Rights Management**. Si no aparece el vínculo Information Rights Management, es posible que IRM no esté habilitado para su sitio. Póngase en contacto con el administrador del servidor para ver si es posible habilitar IRM en el sitio. El vínculo Information Rights Management no aparece para las bibliotecas de imágenes.
    
4. En la página **configuración de Information Rights Management** , active la casilla de verificación restringir permisos de acceso **a los documentos de esta biblioteca** al descargarlos para aplicar permisos restringidos a los documentos que se descargan de esta lista o biblioteca. 
    
5. En el cuadro **crear un título de directiva de permisos** , escriba un nombre descriptivo para la Directiva que puede usar más adelante para diferenciar esta directiva de otras directivas. Por ejemplo, puede escribir la **información confidencial** de la empresa si está aplicando permisos restringidos a una lista o biblioteca que contendrá documentos de la compañía que son confidenciales. 
    
6. En el cuadro **Agregar una descripción de directiva de permisos** , escriba una descripción que se mostrará a las personas que usan esta lista o biblioteca que explica cómo deben administrar los documentos de esta lista o biblioteca. Por ejemplo, puede escribir **discutir el contenido de este documento sólo con otros empleados** si desea restringir el acceso a la información de estos documentos a los empleados internos. 
    
7. Para aplicar otras restricciones a los documentos de esta lista o biblioteca, haga clic en **Mostrar opciones**y realice una de las acciones siguientes:
    
|**Para ello:**|**Haga lo siguiente:**|
|:-----|:-----|
|Permitir que los usuarios impriman documentos desde esta lista o biblioteca  <br/> |Active la casilla de verificación permitir que los **visores** impriman.  <br/> |
|Permitir que los usuarios con al menos el permiso ver elementos ejecuten código insertado o macros en un documento.  <br/> |Active la casilla permitir que los **visores ejecuten el script y el lector de pantalla para que funcionen en los documentos** descargados.  <br/> Si selecciona esta opción, los usuarios podrían ejecutar código para extraer el contenido de un documento.           |
|Requerir que los usuarios comprueben sus credenciales en intervalos específicos.  <br/> Seleccione esta opción si desea restringir el acceso al contenido a un período de tiempo especificado. Si selecciona esta opción, las licencias de emisión de los usuarios para obtener acceso al contenido expirarán después del número de días especificado, y se requerirá a los usuarios que vuelvan al servidor para comprobar sus credenciales y descargar una nueva copia.  <br/> |Seleccione la casilla los **usuarios deben comprobar sus credenciales mediante este intervalo (días)** y, a continuación, especifique el número de días durante los que desea que el documento esté visible.  <br/> |
| Impedir que los usuarios carguen documentos que no admiten IRM en esta lista o biblioteca.  <br/>  Si selecciona esta opción, los usuarios no podrán cargar ninguno de los siguientes tipos de archivo:  <br/>  Tipos de archivo que no tienen los protectores IRM correspondientes instalados en todos los servidores web Front-end.  <br/>  Tipos de archivo que SharePoint Server 2010 no puede descifrar.  <br/>  Tipos de archivo que están protegidos por IRM en otro programa  <br/> |Active la casilla **no permitir a los usuarios cargar documentos que no admitan IRM** .  <br/> |
|Quitar permisos restringidos de esta lista o biblioteca en una fecha específica.  <br/> |Active la casilla de verificación **detener la restricción de acceso a la biblioteca en** y, a continuación, seleccione la fecha que desee.  <br/> |
|Controle el intervalo en el que se almacenan en caché las credenciales del programa que tiene licencia para abrir el documento.  <br/> |En **establecer el intervalo de protección y credenciales de grupo**, escriba el intervalo para almacenar en caché las credenciales en número de días.  <br/> |
|Permitir la protección de grupos para que los usuarios puedan compartir con miembros del mismo grupo.  <br/> |Seleccione **permitir la protección del grupo**y escriba el nombre del grupo para compartir.  <br/> |
   
8. Una vez que haya terminado de seleccionar las opciones que desee, haga clic en **Aceptar**.
  
## <a name="what-is-information-rights-management"></a>¿Qué es Information Rights Management?
<a name="__toc256598175"> </a>

Information Rights Management (IRM) permite limitar las acciones que los usuarios pueden realizar en los archivos que se han descargado de listas o bibliotecas. IRM cifra los archivos descargados y limita el conjunto de usuarios y programas que pueden descifrarlos. IRM también puede limitar los derechos de los usuarios con permiso para leer archivos, de modo que no puedan realizar acciones como, por ejemplo, imprimir copias o copiar el texto de los mismos.
  
Puede usar IRM en listas o bibliotecas para limitar la difusión de contenido confidencial. Por ejemplo, si va a crear una biblioteca de documentos para compartir información sobre productos próximos con representantes de marketing seleccionados, puede usar IRM para evitar que estos usuarios compartan este contenido con otros empleados de la compañía.
  
En un sitio, se aplica IRM a una lista o biblioteca completa, en lugar de a archivos individuales. Esto hace que sea más fácil garantizar un nivel de protección coherente para todo un conjunto de documentos o archivos. Por lo tanto, IRM puede ayudar a su organización a exigir directivas corporativas que rijan el uso y la divulgación de información confidencial o de propiedad.
  
> [!NOTE]
> La información de esta página sobre Information Rights Management reemplaza a los términos que hacen referencia a ' Information Rights Management ' en los contratos de términos de licencia de Microsoft SharePoint Server 2013 y SharePoint Server 2016. 
  
### <a name="how-irm-can-help-protect-content"></a>Cómo puede ayudarle IRM a proteger el contenido
<a name="__toc256598176"> </a>

IRM ayuda a proteger el contenido restringido de las siguientes maneras:
  
- Ayuda a evitar que un visor autorizado copie, modifique, imprima, envíe por fax o copie y pegue el contenido para uso no autorizado
    
- Ayuda a evitar que un visor autorizado copie el contenido mediante la característica imprimir pantalla de Microsoft Windows
    
- Ayuda a evitar que un visor no autorizado vea el contenido si se envía en un correo electrónico después de descargarlo del servidor
    
- Restringe el acceso al contenido a un período de tiempo especificado, tras lo cual los usuarios deben confirmar sus credenciales y descargar el contenido de nuevo
    
- Ayuda a exigir directivas corporativas que rijan el uso y la difusión de contenido dentro de la organización
    
### <a name="how-irm-cannot-help-protect-content"></a>Cómo IRM no puede ayudar a proteger el contenido
<a name="__toc256598177"> </a>

IRM no puede proteger el contenido restringido de lo siguiente:
  
- Borrado, robo, captura o transmisión por parte de programas malintencionados como troyanos, registradores de pulsaciones de teclas y determinados tipos de spyware
    
- Pérdida o corrupción debido a las acciones de los virus informáticos
    
- Copia manual o reescritura del contenido de la pantalla en una pantalla
    
- Fotografía digital o en película de contenido que se muestra en una pantalla
    
- Copia mediante el uso de programas de captura de pantalla de terceros
    
- Copia de metadatos de contenido (valores de columna) mediante el uso de programas de captura de pantalla de terceros o acción de copiar y pegar
    
[Aplicar Information Rights Management a una lista o biblioteca](https://support.office.com/article/6714cfe3-ef39-43b0-bb65-a887726bb63c)
  
## <a name="how-irm-works-for-lists-and-libraries"></a>Cómo funciona IRM en listas y bibliotecas
<a name="__toc256598178"> </a>

La protección de IRM se aplica a los archivos en el nivel de lista o biblioteca. Cuando IRM está habilitado para una biblioteca, la administración de derechos se aplica a todos los archivos de esa biblioteca. Cuando IRM está habilitado para una lista, la administración de derechos solo se aplica a los archivos que están adjuntos a elementos de lista, no a los elementos de lista reales.
  
Cuando los usuarios descargan archivos en una lista o biblioteca habilitada para IRM, los archivos se cifran para que solo los usuarios autorizados puedan verlos. Cada archivo administrado con derechos también contiene una licencia de emisión que impone restricciones a los usuarios que ven el archivo. Las restricciones típicas incluyen convertir un archivo en sólo lectura, deshabilitar la copia de texto, evitar que los usuarios guarden una copia local y evitar que los usuarios impriman el archivo. Los programas cliente que pueden leer tipos de archivo compatibles con IRM usan la licencia de emisión dentro del archivo administrado con derechos para aplicar estas restricciones. Este es el modo en que un archivo administrado con derechos conserva su protección incluso después de que se descarga del servidor.
  
Los tipos de restricciones que se aplican a un archivo cuando se descarga de una lista o biblioteca se basan en los permisos del usuario individual en el sitio que contiene el archivo. En la tabla siguiente se explica cómo se corresponden los permisos de los sitios con los permisos de IRM.
  
|**Permisos**|**Permisos de IRM**|
|:-----|:-----|
|Administrar permisos, administrar sitio web  <br/> |**Control total** (tal y como lo define el programa cliente): este permiso suele permitir a un usuario leer, editar, copiar, guardar y modificar los permisos del contenido administrado con derechos.  <br/> |
|Editar elementos, administrar listas, agregar y personalizar páginas  <br/> |**Editar**, **copiar**y **Guardar**: un usuario puede imprimir un archivo sólo si la casilla de verificación **permitir que los usuarios impriman documentos** está activada en la página Configuración de Information Rights Management para la lista o biblioteca.  <br/> |
|Ver elementos  <br/> |**Read**: un usuario puede leer el documento, pero no puede copiar ni modificar su contenido. Un usuario solo puede imprimir si la casilla **permitir que los usuarios impriman documentos** está activada en la página Configuración de Information Rights Management para la lista o biblioteca.  <br/> |
|Otros  <br/> |Ningún otro permiso corresponde directamente a los permisos de IRM.  <br/> |
   
Cuando habilita IRM para una lista o biblioteca en SharePoint Server 2013, solo puede proteger los tipos de archivo de dicha lista o biblioteca para los que está instalado un protector en todos los servidores web Front-end. Un protector es un programa que controla el cifrado y descifrado de los archivos administrados con derechos de un formato de archivo específico. SharePoint incluye protectores para los siguientes tipos de archivo:
  
- Formularios de Microsoft Office InfoPath
    
- Los formatos de archivo 97-2003 para los siguientes programas de Microsoft Office: Word, Excel y PowerPoint
    
- Formatos Office Open XML para los siguientes programas de Microsoft Office: Word, Excel y PowerPoint
    
- Formato de especificación de papel XML (XPS)
    
Si su organización tiene previsto usar IRM para proteger cualquier otro tipo de archivo además de los enumerados anteriormente, el administrador del servidor debe instalar protectores para estos formatos de archivo adicionales.
  

