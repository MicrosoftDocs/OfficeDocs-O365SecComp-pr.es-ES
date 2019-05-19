---
title: Tipos de archivo admitidos en investigaciones de datos (versión preliminar)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 60e4baf2df94793b532fb4035a34ca3c7a5cd332
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153582"
---
# <a name="supported-file-types-in-data-investigations-preview"></a>Tipos de archivo admitidos en investigaciones de datos (versión preliminar)

Las investigaciones de datos (versión preliminar) admiten muchos tipos de archivos de varias formas, que se describen en la siguiente tabla. Esta lista no finaliza y agregamos nuevos tipos de archivo, ya que continuamos con nuestras pruebas de validación. La tabla también indica si se puede ver un tipo de archivo en los visores disponibles cuando se está revisando la evidencia.

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
