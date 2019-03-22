---
title: Tipos de archivo admitidos en eDiscovery avanzado (versión preliminar)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 7955debee750019d60b8016d736ba50f1ff70bce
ms.sourcegitcommit: cf9d9b545a7c153d314aa9c08c7fb16fcd785b3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2019
ms.locfileid: "30737710"
---
# <a name="supported-file-types-in-advanced-ediscovery-preview"></a>Tipos de archivo admitidos en eDiscovery avanzado (versión preliminar)

La exhibición avanzada de documentos electrónicos (versión preliminar) admite muchos tipos de archivos en muchos niveles diferentes, que se describen en la siguiente tabla. Esta lista no finaliza y agregamos nuevos tipos de archivo, ya que continuamos con nuestras pruebas de validación. La tabla también indica si un tipo de archivo se puede ver en los visores disponibles en eDiscovery (versión preliminar).

| Tipo MIME | Clase File | Visor nativo | Visor de texto | Visor de anotaciones | Extracción de contenedores | Extensiones |
| :- | :- | :- | :- | :- | :- | :- |
| application/msword | Document | Sí | Sí | Sí | No | . doc;. dat |
| application/pdf | Document | Sí | Sí | Sí | No | .pdf |
| aplicación/RTF | Document | Sí | Sí | Sí | No | . rtf;. doc |
| aplicación/vnd. MS-Excel | Document | Sí | Sí | Sí | No | . xls;. dat |
| Application/vnd. MS-Excel. sheet. Binary. macroenabled. 12 | Formato de la productividad y el documento abierto | Sí | Sí | No | No | .xlsb |
| Application/vnd. MS-Excel. sheet. macroenabled. 12 | Document | Sí | Sí | Sí | No | . xlsm |
| Application/vnd. MS-Excel. template. macroenabled. 12 | Formato de la productividad y el documento abierto | No | Sí | No | No | . xltm |
| aplicación/vnd. MS-Outlook | Productividad | No | No | No | No | . msg |
| aplicación/vnd. MS-Outlook-PST | Productividad y colaboración | No | No | No | Sí | .pst |
| aplicación/vnd. MS-PowerPoint | Document | Sí | Sí | Sí | No | . ppt;. PPS;. pase |
| Application/vnd. MS-Word. Document. macroenabled. 12 | Document | Sí | Sí | Sí | No | .docm |
| Application/vnd. MS-Word. template. macroenabled. 12 | Document | Sí | Sí | Sí | No | . dotm |
| Application/vnd. oasis. opendocument. Text | Document | Sí | Sí | Sí | No | ODT  |
| application/vnd.openxmlformats-officedocument.presentationml.presentation | Document | Sí | Sí | Sí | No | .pptx |
| Application/vnd. openxmlformats-officedocument. presentationml. Slideshow | Formato de la productividad y el documento abierto | Sí | Sí | Sí | No | . ppsx |
| Application/vnd. openxmlformats-officedocument. presentationml. template | Document | Sí | Sí | Sí | No | . potx |
| application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | Document | Sí | Sí | Sí | No | .xlsx |
| Application/vnd. openxmlformats-officedocument. SpreadsheetML. template | Document | Sí | Sí | Sí | No | . xltx |
| application/vnd.openxmlformats-officedocument.wordprocessingml.document | Document | Sí | Sí | Sí | No | .docx |
| Application/vnd. openxmlformats-officedocument. WordprocessingML. template | Document | Sí | Sí | Sí | No | . dotx |
| aplicación/vnd. Visio | Document | Sí | Sí | Sí | No | . VSD |
| application/x-7z-Compressed | Archivo/contenedor | No | No | No | Sí | .7z |
| aplicación/XHTML + XML | Document | Sí | Sí | Sí | No | . XHTML |
| Application/XML | Document | Sí | Sí | Sí | No | . XML |
| application/x-Msaccess | Document | Sí | Sí | Sí | No | .mdb |
| application/x-mspublisher | Document | Sí | Sí | Sí | No | . pub |
| aplicación/x-rar-comprimido | Archivo/contenedor | No | No | No | Sí | . rar |
| aplicación/código postal | Archivo/contenedor | No | No | No | Sí | .zip |
| Image/BMP | Image (Imagen) | Sí | Sí | Sí | No | .bmp |
| Image/EMF | Image (Imagen) | Sí | Sí | Sí | No | .emf |
| image/gif | Document | Sí | Sí | Sí | No | .gif |
| image/jpeg | Image (Imagen) | Sí | Sí | Sí | No | . jpg;. JPEG;. dat;. jpgt |
| image/png | Image (Imagen) | Sí | Sí | Sí | No | .png |
| Image/TIFF | Image (Imagen) | Sí | Sí | Sí | No | . tif |
| Image/vnd. DWG | Document | Sí | Sí | Sí | No | . dwg;. ficheros |
| imagen/WMF | Document | Sí | Sí | Sí | No | .wmf |
| mensaje/rfc822 | Productividad y colaboración | No | No | No | No | . eml |
| texto/CSV | Document | Sí | Sí | Sí | No | . csv |
| texto/HTML | Document | Sí | Sí | Sí | No | . html;. shtml;. htm |
| texto/sin formato | Document | Sí | Sí | Sí | No | . txt;. CSS;. con;. pl;. csv;. dat |
| texto/vCard-contacto | Document | Sí | Sí | Sí | No | . vcf |
||||||||