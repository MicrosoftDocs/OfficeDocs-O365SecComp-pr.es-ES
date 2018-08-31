---
title: Aplicar Information Rights Management (IRM) a una lista o biblioteca
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
description: Puede usar Information Rights Management (IRM) para ayudar a controlar y proteger los archivos que se descargan de listas o bibliotecas.
ms.openlocfilehash: 5a48abf13841716d4dba34311d69ca2e6a5ea422
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536126"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a>Aplicar Information Rights Management (IRM) a una lista o biblioteca

Puede usar Information Rights Management (IRM) para ayudar a controlar y proteger los archivos que se descargan de listas o bibliotecas.
  
## <a name="before-you-begin"></a>Antes de empezar

- El servicio de Azure Rights Management (RMS Azure) de protección de la información de Azure y el equivalente de locales, Active Directory Rights Management Services (AD RMS), que admite Information Rights Management para los sitios. No hay instalaciones independientes o adicionales son necesarios.
    
- Antes de aplicar IRM a una lista o biblioteca en primer lugar debe habilitarse por un administrador para el sitio.
    
- Para aplicar IRM a una lista o biblioteca, debe tener permisos de administrador para dicha lista o biblioteca.
    
- Si usa SharePoint Online, sus usuarios pueden experimentar tiempos de espera al descargar los archivos protegidos con IRM más grandes. Si esto sucede, a continuación, aplicar la protección IRM mediante el uso de los programas de Office y almacenar archivos de mayor tamaño en una biblioteca de SharePoint que no use IRM.
    
> [!NOTE]
> Si usa SharePoint Server 2013, un administrador del servidor debe instalar a protectores en todos los servidores Web front-end para cada tipo de archivo que las personas de su organización desean proteger mediante IRM. 
  
## <a name="apply-irm-to-a-list-or-library"></a>Aplicar IRM a una lista o biblioteca
<a name="__toc256598179"> </a>

![Configuración de administración de derechos de la información](media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. Vaya a la lista o biblioteca para la que desea configurar IRM.
    
2. En la cinta de opciones, haga clic en la ficha **biblioteca** y, a continuación, haga clic en **Configuración de la biblioteca**. (Si está trabajando en una lista, haga clic en la pestaña **lista** y, a continuación, haga clic en **Configuración de la lista**).
    
    ![Botones de la configuración de la biblioteca de SharePoint en la cinta de opciones](media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. En **permisos y administración**, haga clic en **Information Rights Management**. Si no aparece el vínculo Information Rights Management, IRM podría no estar habilitado para el sitio. Póngase en contacto con el administrador del servidor para ver si es posible habilitar IRM para el sitio. El vínculo Information Rights Management no aparece para bibliotecas de imágenes.
    
4. En la página **Configuración de Information Rights Management** , active la casilla de verificación **restringir el permiso a los documentos de esta biblioteca al descargarlos** para aplicar permisos restringidos a los documentos que se descargan de esta lista o biblioteca. 
    
5. En el cuadro **crear un título de directiva de permisos** , escriba un nombre descriptivo para la directiva que puede utilizar posteriormente para diferenciar esta directiva de otras directivas. Por ejemplo, puede escribir **Confidencial de la compañía** si va a aplicar permisos restringidos a una lista o biblioteca que va a contener documentos de la compañía que son confidenciales. 
    
6. En el cuadro **Agregar una descripción de la directiva de permisos** , escriba una descripción que aparecerá a las personas que utilicen esta lista o biblioteca que se explica cómo deben tratar los documentos de esta lista o biblioteca. Por ejemplo, puede escribir **discutir el contenido de este documento sólo con otros empleados** si desea restringir el acceso a la información de estos documentos a los empleados internos. 
    
7. Para aplicar restricciones adicionales a los documentos de esta lista o biblioteca, haga clic en **Mostrar opciones**y realice una de las siguientes opciones:
    
|**Para hacer esto:**|**Realice lo siguiente:**|
|:-----|:-----|
|Permitir a los usuarios imprimir documentos desde esta lista o biblioteca  <br/> |Seleccione la casilla de verificación **Permitir a los visores de impresión** .  <br/> |
|Permitir que las personas con al menos el permiso Ver elementos para ejecutar código incrustado o macros en un documento.  <br/> |Active la casilla de verificación **Permitir que los visores puedan ejecutar el lector de pantalla y la secuencia de comandos para que funcionen en los documentos descargados** .  <br/> Si selecciona esta opción, los usuarios podrían ejecutar código para extraer el contenido de un documento.           |
|Requerir que los usuarios comprueben sus credenciales a intervalos específicos.  <br/> Seleccione esta opción si desea restringir el acceso al contenido a un período de tiempo especificado. Si selecciona esta opción, las licencias de emisión de personas para obtener acceso al contenido caducará después de que el número especificado de días y personas se necesitará para devolver al servidor para comprobar sus credenciales y descargar una nueva copia.  <br/> |Seleccione el **los usuarios deben comprobar sus credenciales mediante este intervalo de (días)** casilla de verificación y, a continuación, especifique el número de días para la que desea que el documento que estén visibles.  <br/> |
| Impedir que personas cargar documentos que no admiten IRM a esta lista o biblioteca.  <br/>  Si selecciona esta opción, las personas no podrán cargar cualquiera de los siguientes tipos de archivo:  <br/>  Tipos de archivo que no tienen los protectores IRM correspondientes instalados en todos los servidores Web front-end.  <br/>  Tipos de archivo que no se puede descifrar SharePoint Server 2010.  <br/>  Tipos de archivo que están protegidos con IRM en otro programa  <br/> |Active la casilla de verificación **no permitir a los usuarios cargar documentos que no admiten IRM** .  <br/> |
|Quitar permisos restringidos de esta lista o biblioteca en una fecha específica.  <br/> |Active la casilla de verificación **dejar de restringir el acceso a la biblioteca en** y, a continuación, seleccione la fecha que desee.  <br/> |
|Control del intervalo que se almacenan en caché las credenciales para el programa que se concede bajo licencia para abrir el documento.  <br/> |En **establecer protección del grupo y un intervalo de credenciales**, escriba theinterval para almacenar en caché las credenciales en el número de días.  <br/> |
|Permitir protección del grupo de modo que los usuarios pueden compartir con los miembros del mismo grupo.  <br/> |Seleccione **Permitir protección del grupo**y escriba el nombre del grupo para el uso compartido.  <br/> |
   
8. Cuando termine de seleccionar las opciones que desee, haga clic en **Aceptar**.
  
## <a name="what-is-information-rights-management"></a>¿Qué es Information Rights Management?
<a name="__toc256598175"> </a>

Information Rights Management (IRM) permite limitar las acciones que pueden realizar los usuarios en los archivos que se han descargado de listas o bibliotecas. IRM cifra los archivos descargados y limita el conjunto de usuarios y programas permitidos para descifrar estos archivos. IRM también puede limitar los derechos de los usuarios que tienen permiso para leer los archivos, por lo que no pueden realizar acciones como imprimir copias de los archivos ni copiar texto de ellos.
  
Puede usar IRM en listas o bibliotecas para limitar la diseminación de contenido confidencial. Por ejemplo, si va a crear una biblioteca de documentos para compartir información sobre próximos productos con representantes de marketing seleccionados, puede usar IRM para evitar que a estos individuos compartan este contenido con otros empleados de la compañía.
  
En un sitio, IRM se aplica a una biblioteca o lista completa, en lugar de a archivos individuales. Esto facilita asegurar un nivel coherente de protección para un conjunto completo de documentos o archivos. IRM, por tanto, puede ayudar a su organización para aplicar las directivas corporativas que rigen el uso y diseminación de información confidencial o propietaria.
  
> [!NOTE]
> La información de esta página con respecto a Information Rights Management reemplaza los términos que hacen referencia a 'Information Rights Management' en los contratos de términos de licencia de Microsoft SharePoint Server 2013 y SharePoint Server 2016. 
  
### <a name="how-irm-can-help-protect-content"></a>Cómo puede ayudar a proteger el contenido IRM
<a name="__toc256598176"> </a>

IRM ayuda a proteger el contenido restringido de las maneras siguientes:
  
- Ayuda a evitar que un visor autorizado de copiar, modificar, imprimir, enviar por fax, o copiando y pegando el contenido para uso no autorizado
    
- Ayuda a evitar que un visor autorizado copien el contenido mediante el uso de la característica Imprimir pantalla en Microsoft Windows
    
- Ayuda a evitar que un visor no autorizado vea el contenido si se envía por correo electrónico después de descargarse desde el servidor
    
- Restringe el acceso a contenido a un período especificado de tiempo, después del cual los usuarios deben confirmar sus credenciales y descargar el contenido de nuevo
    
- Ayuda a aplicar las directivas corporativas que rigen el uso y diseminación de contenido dentro de la organización
    
### <a name="how-irm-cannot-help-protect-content"></a>Cómo IRM no puede ayudar a proteger el contenido
<a name="__toc256598177"> </a>

IRM no puede proteger contenido restringido de lo siguiente:
  
- Eliminación, robo, captura o transmisión mediante programas malintencionados como caballos de Troya, registradores y determinados tipos de spyware
    
- Pérdida o daño debido a las acciones de virus informáticos
    
- La copia manual o volver a escribir de contenido de la presentación en una pantalla
    
- Digital o fotografía de contenido que se muestra en una pantalla de película
    
- Copiar mediante el uso de programas de captura de pantalla de terceros
    
- La copia de los metadatos de contenido (valores de columna) mediante el uso de programas de captura de pantalla de terceros o acción de copiar y pegar
    
[Aplicar Information Rights Management a una lista o biblioteca](https://support.office.com/article/6714cfe3-ef39-43b0-bb65-a887726bb63c)
  
## <a name="how-irm-works-for-lists-and-libraries"></a>Cómo funciona IRM para listas y bibliotecas
<a name="__toc256598178"> </a>

Protección de IRM se aplica a los archivos en el nivel de lista o biblioteca. Cuando se habilita IRM para una biblioteca, la administración de derechos se aplica a todos los archivos en esa biblioteca. Cuando se habilita IRM para una lista, administración de derechos se aplica sólo a los archivos que están adjuntos a elementos de lista, no a los elementos de lista reales.
  
Cuando las personas descargan archivos en una biblioteca o lista habilitada con IRM, los archivos se cifran para que sólo las personas autorizadas puedan verlos. Cada archivo administrado con derechos también contiene una licencia de emisión que impone restricciones a las personas que ver el archivo. Las restricciones típicas incluyen hacer un archivo de sólo lectura, deshabilitar la copia de texto, impedir que los usuarios guardar una copia local y evitar que se imprima el archivo. Programas de cliente que pueden leer tipos de archivo compatibles con IRM utilizan la licencia de emisión dentro del archivo administrado con derechos para aplicar estas restricciones. Se trata de cómo un archivo administrado con derechos conserva su protección incluso después de se descarga desde el servidor.
  
Los tipos de restricciones que se aplican a un archivo cuando se descarga desde una lista o biblioteca se basan en los permisos del usuario individual en el sitio que contiene el archivo. En la siguiente tabla se explica cómo los permisos en los sitios se corresponden con los permisos de IRM.
  
|**Permisos**|**Permisos de IRM**|
|:-----|:-----|
|Administrar permisos, administración del sitio Web  <br/> |**Control total** (como se define mediante el programa cliente): este permiso generalmente permite a un usuario leer, editar, copiar, guardar y modificar permisos de contenido con derechos administrados.  <br/> |
|Editar elementos, administrar listas, agregar y personalizar páginas  <br/> |**Editar**, **Copiar**y **Guardar**: un usuario puede imprimir un archivo únicamente si está activada la casilla de verificación **Permitir a los usuarios para imprimir documentos** en la página Configuración de Information Rights Management para la lista o biblioteca.  <br/> |
|Ver elementos  <br/> |**Lectura**: un usuario puede leer el documento, pero no se puede copiar o modificar su contenido. Un usuario puede imprimir sólo si está activada la casilla de verificación **Permitir a los usuarios para imprimir documentos** en la página Configuración de Information Rights Management para la lista o biblioteca.<br/> |
|Otros  <br/> |No hay otros permisos se corresponden directamente con los permisos de IRM.  <br/> |
   
Cuando se habilita IRM para una lista o biblioteca de SharePoint Server 2013, solo puede proteger tipos de archivo en dicha lista o biblioteca para la que está instalado un protector en todos los servidores Web front-end. Un protector es un programa que controla el cifrado y descifrado de archivos con derechos administrados de un formato de archivo específico. SharePoint incluye protectores para los siguientes tipos de archivo:
  
- Formularios de Microsoft Office InfoPath
    
- Los formatos de archivo 97-2003 para los siguientes programas de Microsoft Office: Word, Excel y PowerPoint
    
- Los formatos Office Open XML para los siguientes programas de Microsoft Office: Word, Excel y PowerPoint
    
- El formato XML Paper Specification (XPS)
    
Si su organización planea usar IRM para proteger otros tipos de archivo además de los enumerados anteriormente, el administrador del servidor debe instalar a protectores para estos formatos de archivo adicionales.
  

