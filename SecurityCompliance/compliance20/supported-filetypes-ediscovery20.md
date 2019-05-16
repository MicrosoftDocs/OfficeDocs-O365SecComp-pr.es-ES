---
title: Tipos de archivo admitidos en eDiscovery avanzado
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
ms.openlocfilehash: d8e9689cb04929137787225579dcda17005c8bfe
ms.sourcegitcommit: 7be8617ce75909f0fa1a2f6e72749e2ef4bb2d3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2019
ms.locfileid: "34088813"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>Tipos de archivo admitidos en eDiscovery avanzado

La exhibición avanzada de documentos electrónicos admite muchos tipos de archivos en muchos niveles diferentes, que se describen en la siguiente tabla. Esta lista no finaliza y agregamos nuevos tipos de archivo, ya que continuamos con nuestras pruebas de validación. Las tablas indican si un tipo de archivo es compatible con la extracción de texto (OCR para imágenes), que se puede ver en el visor nativo y que también es compatible con el visor de anotaciones en la exhibición avanzada de documentos electrónicos.

## <a name="archive--container"></a>Archivo/contenedor

| Tipo MIME | Identificación de archivos | Extracción de metadatos | Extracción de contenedores | Extensiones posibles |
| :- |  :- |  :- |  :- |  :- |
| application/x-7z-Compressed | Sí | Sí | Sí | .7z |
| aplicación/x-rar-comprimido | Sí | Sí | Sí | . rar |
| application/x-tar | Sí | Sí | Sí | . tar |
| aplicación/código postal | Sí | Sí | Sí | .zip |
||||||||

## <a name="database"></a>Base de datos

| Tipo MIME | Identificación de archivos | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/x-Msaccess | Sí | Sí | Sí | No | No | .mdb |
||||||||

## <a name="email"></a>Correo electrónico

| Tipo MIME | Identificación de archivos | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| aplicación/vnd. MS-Outlook | Sí | Sí | Sí | Sí | Sí | . msg |
| mensaje/rfc822 | Sí | Sí | Sí | Sí | Sí | . eml |
| texto/vCard-contacto | Sí | Sí | Sí | Sí | Sí | . vcf |
||||||||

## <a name="email-container"></a>Contenedor de correo electrónico

| Tipo MIME | Identificación de archivos | Extracción de metadatos | Extracción de contenedores | Extensiones posibles |
| :- |  :- |  :- |  :- |  :- |
| aplicación/mbox | Sí | Sí | Sí | . mbox |
| aplicación/vnd. MS-Outlook-PST | Sí | Sí | Sí | .pst |
||||||||

## <a name="html"></a>HTML

| Tipo MIME | Identificación de archivos | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| aplicación/XHTML + XML | Sí | Sí | Sí | Sí | Sí | . XHTML |
| Application/XML | Sí | Sí | Sí | Sí | Sí | . XML |
| texto/HTML | Sí | Sí | Sí | Sí | Sí | . htm;. html;. shtml |
||||||||

## <a name="image"></a>Image (Imagen)

| Tipo MIME | Identificación de archivos | Extracción de metadatos | Extracción de texto OCR | Visor nativo | Visor de anotaciones | Extensiones posibles |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Image/BMP | Sí | Sí | Sí | Sí | Sí | .bmp |
| Image/EMF | Sí | Sí | Sí | Sí | Sí | .emf |
| image/gif | Sí | Sí | Sí | Sí | Sí | .gif |
| image/jpeg | Sí | Sí | Sí | Sí | Sí | . JPEG;. jpg |
| image/png | Sí | Sí | Sí | Sí | Sí | .png |
| Image/SVG + XML | Sí | Sí | Sí | Sí | No | . svg |
| Image/TIFF | Sí | Sí | Sí | Sí | Sí | . tif |
| Image/vnd. DWG | Sí | Sí | Sí | Sí | Sí | . dwg;. DXF |
| imagen/WMF | Sí | Sí | Sí | Sí | Sí | .wmf |
||||||||

## <a name="microsoft-excel"></a>Microsoft Excel

| Tipo MIME | Identificación de archivos | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| aplicación/vnd. MS-Excel | Sí | Sí | Sí | Sí | Sí | . dat;. xls |
| Application/vnd. MS-Excel. sheet. Binary. macroenabled. 12 | Sí | Sí | Sí | Sí | No | .xlsb |
| Application/vnd. MS-Excel. sheet. macroenabled. 12 | Sí | Sí | Sí | Sí | Sí | . xlsm |
| Application/vnd. MS-Excel. template. macroenabled. 12 | Sí | Sí | Sí | No | No | . xltm |
| application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | Sí | Sí | Sí | Sí | Sí | .xlsx |
| Application/vnd. openxmlformats-officedocument. SpreadsheetML. template | Sí | Sí | Sí | Sí | Sí | . xltx |
||||||||

## <a name="microsoft-powerpoint"></a>Microsoft Powerpoint

| Tipo MIME | Identificación de archivos | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| aplicación/vnd. MS-PowerPoint | Sí | Sí | Sí | Sí | Sí | . pot;. PPS;. ppt |
| application/vnd.openxmlformats-officedocument.presentationml.presentation | Sí | Sí | Sí | Sí | Sí | .pptx |
| Application/vnd. openxmlformats-officedocument. presentationml. Slideshow | Sí | Sí | Sí | Sí | Sí | . ppsx |
| Application/vnd. openxmlformats-officedocument. presentationml. template | Sí | Sí | Sí | Sí | Sí | . potx |
||||||||

## <a name="microsoft-publisher"></a>Microsoft Publisher

| Tipo MIME | Identificación de archivos | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/x-mspublisher | Sí | Sí | Sí | Sí | Sí | . pub |
||||||||

## <a name="microsoft-visio"></a>Microsoft Visio

| Tipo MIME | Identificación de archivos | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Application/vnd. ms-Visio. Drawing | Sí | Sí | Sí | Sí | No |  |
| aplicación/vnd. Visio | Sí | Sí | Sí | Sí | Sí | . VSD |
||||||||

## <a name="microsoft-word"></a>Microsoft Word

| Tipo MIME | Identificación de archivos | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/msword | Sí | Sí | Sí | Sí | Sí | . dat;. doc |
| aplicación/RTF | Sí | Sí | Sí | Sí | Sí | . doc;. rtf |
| Application/vnd. MS-Word. Document. macroenabled. 12 | Sí | Sí | Sí | Sí | Sí | .docm |
| Application/vnd. MS-Word. template. macroenabled. 12 | Sí | Sí | Sí | Sí | Sí | . dotm |
| application/vnd.openxmlformats-officedocument.wordprocessingml.document | Sí | Sí | Sí | Sí | Sí | .docx |
| Application/vnd. openxmlformats-officedocument. WordprocessingML. template | Sí | Sí | Sí | Sí | Sí | . dotx |
||||||||

## <a name="microsoft-works"></a>Microsoft Works

| Tipo MIME | Identificación de archivos | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Application/vnd. ms-Works-SS | Sí | Sí | No | No | No | . WPS |
| aplicación/vnd. ms-Works-WP | Sí | Sí | No | No | No | . WPS |
||||||||

## <a name="open-document-format"></a>Formato de documento abierto

| Tipo MIME | Identificación de archivos | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| Application/vnd. oasis. opendocument. Text | Sí | Sí | Sí | Sí | Sí | . odt |
||||||||

## <a name="other"></a>Otros

| Tipo MIME | Identificación de archivos | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/json | Sí | Sí | Sí | Sí | Sí | No aplicable |
| aplicación/vnd. ms-Graph | Sí | Sí | No | No | No |  |
| Application/winhlp | Sí | Sí | No | No | No | .hlp |
| aplicación/x-TNEF | Sí | Sí | No | No | No |  |
||||||||

## <a name="plain-text"></a>Texto sin formato

| Tipo MIME | Identificación de archivos | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| texto/CSV | Sí | Sí | Sí | Sí | Sí | . csv |
| texto/sin formato | Sí | Sí | Sí | Sí | Sí | . con;. CSS;. csv;. dat;. pl;. txt |
||||||||

## <a name="portable-document-format"></a>Portable Document Format

| Tipo MIME | Identificación de archivos | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/pdf | Sí | Sí | Sí | Sí | Sí | .pdf |
||||||||

## <a name="word-perfect"></a>Word Perfect

| Tipo MIME | Identificación de archivos | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| aplicación/vnd. WordPerfect; version = 5.0 | Sí | Sí | Sí | No | No | . wpd |
| aplicación/vnd. WordPerfect; versión = 5.1 | Sí | Sí | Sí | No | No | . wpd |
| aplicación/vnd. WordPerfect; versión = 6. x | Sí | Sí | Sí | No | No | . wpd |
||||||||

## <a name="word-pro"></a>Word Pro

| Tipo MIME | Identificación de archivos | Extracción de metadatos | Extracción de texto | Visor nativo | Visor de anotaciones | Extensiones posibles |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| aplicación/vnd. Lotus-WordPro | Sí | Sí | No | No | No | . LWP |
||||||||
