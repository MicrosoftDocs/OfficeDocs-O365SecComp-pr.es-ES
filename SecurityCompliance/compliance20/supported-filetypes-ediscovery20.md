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
ms.openlocfilehash: 8b5651e7e1f1e15aae34a3100b25564f0b84abb7
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296163"
---
# <a name="supported-file-types-in-advanced-ediscovery-preview"></a>Tipos de archivo admitidos en eDiscovery avanzado (versión preliminar)


| Tipo MIME | Clase File (es decir, imagen, archivo, correo electrónico, documento de Office, etc.) | Visor nativo | Text | Visor de anotaciones | Extracción de contenedores | Extensiones posibles |
| :- | :- | :- | :- | :- | :- | :- |
| aplicación/MSWord | Documento | Sí | Sí  | Sí | No | . doc;. dat |
| application/pdf | Documento | Sí | Sí  | Sí | No | .pdf |
| aplicación/RTF | Documento | Sí | Sí  | Sí | No | . rtf;. doc |
| aplicación/vnd. MS-Excel | Documento | Sí | Sí  | Sí | No | . xls;. dat |
| Application/vnd. MS-Excel. sheet. Binary. macroenabled. 12 | Formato de la productividad y el documento abierto | Sí | Sí | No | No | .xlsb |
| Application/vnd. MS-Excel. sheet. macroenabled. 12 | Documento | Sí | Sí  | Sí | No | .xlsm |
| Application/vnd. MS-Excel. template. macroenabled. 12 | Formato de la productividad y el documento abierto | No | Sí | No | No | .xltm |
| aplicación/vnd. MS-Outlook | Productividad | No | No | No | No | . msg |
| aplicación/vnd. MS-Outlook-PST | Productividad y colaboración | No | No | No | Sí | .pst |
| aplicación/vnd. MS-PowerPoint | Documento | Sí | Sí  | Sí | No | . ppt;. PPS;. pase |
| Application/vnd. MS-Word. Document. macroenabled. 12 | Documento | Sí | Sí  | Sí | No | .docm |
| Application/vnd. MS-Word. template. macroenabled. 12 | Documento | Sí | Sí  | Sí | No | .dotm |
| Application/vnd. oasis. opendocument. Text | Documento | Sí | Sí  | Sí | No | ODT  |
| aplicación/vnd. openxmlformats-officedocument. presentationml. Presentation | Documento | Sí | Sí  | Sí | No | .pptx |
| Application/vnd. openxmlformats-officedocument. presentationml. Slideshow | Formato de la productividad y el documento abierto | Sí | Sí  | Sí | No | . ppsx |
| Application/vnd. openxmlformats-officedocument. presentationml. template | Documento | Sí | Sí  | Sí | No | .potx |
| Application/vnd. openxmlformats-officedocument. SpreadsheetML. sheet | Documento | Sí | Sí  | Sí | No | .xlsx |
| Application/vnd. openxmlformats-officedocument. SpreadsheetML. template | Documento | Sí | Sí  | Sí | No | .xltx |
| Application/vnd. openxmlformats-officedocument. WordprocessingML. Document | Documento | Sí | Sí  | Sí | No | .docx |
| Application/vnd. openxmlformats-officedocument. WordprocessingML. template | Documento | Sí | Sí  | Sí | No | .dotx |
| aplicación/vnd. Visio | Documento | Sí | Sí  | Sí | No | .vsd |
| application/x-7z-Compressed | Archivo/contenedor | No | No | No | Sí | .7z |
| aplicación/XHTML + XML | Documento | Sí | Sí  | Sí | No | . XHTML |
| Application/XML | Documento | Sí | Sí  | Sí | No | .xml |
| application/x-Msaccess | Documento | Sí | Sí  | Sí | No | .mdb |
| application/x-mspublisher | Documento | Sí | Sí  | Sí | No | . pub |
| aplicación/x-rar-comprimido | Archivo/contenedor | No | No | No | Sí | . rar |
| aplicación/código postal | Archivo/contenedor | No | No | No | Sí | .zip |
| Image/BMP | Image (Imagen) | Sí | Sí  | Sí | No | .bmp |
| Image/EMF | Image (Imagen) | Sí | Sí  | Sí | No | .emf |
| imagen/GIF | Documento | Sí | Sí  | Sí | No | .gif |
| image/JPEG | Image (Imagen) | Sí | Sí  | Sí | No | . jpg;. JPEG;. dat;. jpgt |
| imagen/PNG | Image (Imagen) | Sí | Sí  | Sí | No | .png |
| Image/TIFF | Image (Imagen) | Sí | Sí  | Sí | No | .tif |
| Image/vnd. DWG | Documento | Sí | Sí  | Sí | No | . dwg;. ficheros |
| imagen/WMF | Documento | Sí | Sí  | Sí | No | .wmf |
| mensaje/rfc822 | Productividad y colaboración | No | No | No | No | . eml |
| texto/CSV | Documento | Sí | Sí  | Sí | No | .csv |
| texto/HTML | Documento | Sí | Sí  | Sí | No | . html;. shtml;. htm |
| texto/sin formato | Documento | Sí | Sí  | Sí | No | . txt;. CSS;. con;. pl;. csv;. dat |
| texto/vCard-contacto | Documento | Sí | Sí  | Sí | No | . vcf |