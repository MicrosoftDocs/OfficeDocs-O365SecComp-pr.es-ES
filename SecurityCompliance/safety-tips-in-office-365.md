---
title: Sugerencias de seguridad en los mensajes de correo electrónico en Office 365
ms.author: krowley
author: kccross
manager: scotv
ms.date: 10/6/2016
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
description: Presenta sugerencias de seguridad para los mensajes de correo filtrados por el filtro de correo no deseado de EOP y Office 365.
ms.openlocfilehash: 54f41d1ae0b7d0ca883bf6be7e2dbe006536d1aa
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214310"
---
# <a name="safety-tips-in-email-messages-in-office-365"></a>Sugerencias de seguridad en los mensajes de correo electrónico en Office 365

Exchange Online Protection (EOP) y Office 365 protegen contra el correo no deseado, el phishing y la prevención de malware. Hoy en día, algunos de estos ataques están tan bien diseñados que parecen legítimos. No siempre es suficiente enviar mensajes a la carpeta correo electrónico no deseado. Ahora, cuando revise el correo electrónico en Outlook o en Outlook en la web, EOP comprueba automáticamente el remitente y agrega una sugerencia de seguridad en la parte superior del correo electrónico. 
  
La sugerencia de seguridad (un mensaje codificado por colores) le avisará de los mensajes potencialmente perjudiciales. La mayoría de los mensajes de la bandeja de entrada no tienen una sugerencia de seguridad. Solo las verá cuando EOP y Office 365 tienen la información que necesita para evitar los ataques de correo no deseado, de suplantación de identidad (phishing) y de malware. Si se muestran sugerencias de seguridad en la bandeja de entrada, puede usar los siguientes ejemplos para obtener más información sobre cada tipo de sugerencia de seguridad.
  
- Correo sospechoso (sugerencia de seguridad roja).
    
    ![Captura de pantalla que muestra una sugerencia de seguridad roja.](media/5078a0be-e556-44a1-b169-09d780d26898.png)
  
    Una sugerencia de seguridad roja en un correo electrónico significa que el mensaje que ha recibido contiene algo sospechoso, como una estafa de suplantación de identidad (phishing). Le recomendamos que elimine este tipo de mensaje de correo electrónico de la bandeja de entrada sin abrirlo.
    
- Correo no deseado (sugerencia de seguridad amarilla).
    
    ![Captura de pantalla que muestra una sugerencia de seguridad amarilla.](media/793c9265-ea44-48fd-a98f-804fadd4163b.png)
  
    Una sugerencia de seguridad amarilla en un correo electrónico significa que el mensaje se ha marcado como correo no deseado. Si no reconoce y no confía en el remitente del mensaje, no descargue ningún dato adjunto ni ninguna imagen y no haga clic en ningún vínculo del mensaje. En Outlook en la web, puede hacer clic en **no es correo no deseado** en la barra amarilla de un elemento de correo no deseado para mover el mensaje a la bandeja de entrada. Si aparece la sugerencia de seguridad amarilla en un mensaje que se entregó en la bandeja de entrada, probablemente se deba a que ha deshabilitado el traslado de correo no deseado a la carpeta correo electrónico no deseado. 
    
- Correo seguro (sugerencia de seguridad verde).
    
    ![Captura de pantalla que muestra una sugerencia de seguridad de color verde.](media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)
  
    Además de los mensajes no seguros, también le mostraremos los mensajes válidos de los remitentes en los que confíe con una sugerencia de seguridad verde. Una sugerencia de seguridad verde en un correo electrónico significa que se ha comprobado el remitente del mensaje y que se ha comprobado que es seguro. Microsoft mantiene esta lista de remitentes de confianza que incluyen organizaciones financieras y otros usuarios que se falsifican o suplantan con frecuencia.
    
- Correo sin filtrar (sugerencia de seguridad gris).
    
    ![Captura de pantalla que muestra una sugerencia de seguridad gris.](media/c4d0cf8f-08e9-4c84-beee-1d9e0b022e0a.png)
  
    También le informaremos cuando omitimos la comprobación de correo, ya que procede de un remitente en el que confía en la lista de remitentes seguros o si existe una regla de flujo de correo para omitir el filtrado. 
    
    La sugerencia de seguridad gris también aparece cuando se bloquean las imágenes externas, es decir, el mensaje está en la bandeja de entrada y no parece que sea correo no deseado, pero contiene imágenes externas que no ha decidido descargar.
    
## <a name="working-with-safety-tips"></a>Trabajar con sugerencias de seguridad

Las sugerencias de seguridad siempre están habilitadas para Outlook en la web, aunque no todos los mensajes recibirán ninguna. Los administradores de Office 365 pueden desactivar sugerencias de seguridad para otros clientes de correo electrónico como Outlook. Para obtener más información, vea [habilitar o deshabilitar las sugerencias de seguridad en Office 365](enable-or-disable-safety-tips.md).
  
Si no está de acuerdo con el modo en que Office 365 y EOP clasificaron un mensaje (es decir, no es correo no deseado o no es legítimo), puede enviar los mensajes para su análisis para mejorar su experiencia. Para obtener más información, vea [informar sobre correo no deseado y estafas de suplantación de identidad en Outlook en la web](https://technet.microsoft.com/library/dn594557.aspx). También puede hacer clic en el vínculo comentarios de la sugerencia de seguridad para enviar comentarios directamente a Microsoft para ayudarnos a mejorar.
  
## <a name="see-also"></a>Consulte también

[Habilitar o deshabilitar las sugerencias de seguridad en Office 365](enable-or-disable-safety-tips.md)

