---
title: Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.custom: TN2DMC
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
description: 'Resumen: Este artículo describe cómo usa DomainKeys Identified Mail (DKIM) con Office 365 para asegurarse de que los sistemas de correo electrónico de destino confían en los mensajes enviados desde su dominio personalizado.'
ms.openlocfilehash: 13af2ae96d8c4cbf363e1273a3d1ed5fb9be2077
ms.sourcegitcommit: 9f08af5502070a42de22b6d83e3a08c67cc0c619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/07/2018
ms.locfileid: "27201574"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain-in-office-365"></a>Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365

 **Resumen:** Este artículo describe cómo usa DomainKeys Identified Mail (DKIM) con Office 365 para asegurarse de que los sistemas de correo electrónico de destino confían en los mensajes enviados desde su dominio personalizado. 
  
Debería usar DKIM además de SPF y DMARC para ayudarle a evitar que los suplantadores de identidad envíen mensajes que parece que provienen de su dominio. DKIM le permite agregar una firma digital a los mensajes de correo electrónico en el encabezado del mensaje. Suena complicado, pero realmente no lo es. Cuando configura DKIM, autoriza su dominio para asociar, o firmar, su nombre a un mensaje de correo electrónico mediante la autenticación criptográfica. Los sistemas de correo electrónico que reciben correo electrónico desde el dominio pueden usar esta firma digital para ayudarles a determinar si el correo entrante que reciben es legítimo.
  
Básicamente, usa una clave privada para cifrar el encabezado del correo electrónico saliente del dominio. Publica una clave pública en los registros DNS del dominio que los servidores de recepción pueden usar para descodificar la firma. Usan la clave pública para comprobar que los mensajes proceden realmente de usted y no de alguien que está suplantando la identidad del dominio.
  
Office 365 configura automáticamente DKIM para dominios iniciales. El dominio inicial es el que crea Office 365 al registrarse con el servicio, por ejemplo, contoso.onmicrosoft.com. No es necesario hacer nada para configurar DKIM para el dominio inicial. Para más información sobre los dominios, vea [Preguntas más frecuentes de dominios](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).
  
También puede elegir no hacer nada acerca de DKIM para su dominio personalizado. Si no configura DKIM para su dominio personalizado, Office 365 crea un par de claves privadas y públicas, que permiten que DKIM firme y configure la directiva predeterminada de Office 365 para su dominio personalizado. Aunque esto suponga una cobertura suficiente para la mayoría de los clientes de Office 365, debería configurar manualmente DKIM para su dominio personalizado en las siguientes circunstancias:
  
- Tiene más de un dominio personalizado en Office 365
    
- También va a configurar DMARC (recomendado)
    
- Quiere tener el control sobre la clave privada
    
- Quiere personalizar los registros CNAME
    
- Quiere configurar claves de DKIM para los correos electrónicos que se originen en un dominio de terceros, por ejemplo, si usa un troyano de envío masivo de correo electrónico de terceros.
    
En este artículo:
  
- [Cómo DKIM funciona mejor que SPF solo para evitar la suplantación de identidad malintencionada en Office 365](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)
    
- [Lo que necesita hacer para configurar manualmente DKIM en Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)
    
- [Configurar DKIM para más de un dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)
    
- [Deshabilitar la directiva de firmas DKIM para un dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)
    
- [Comportamiento predeterminado para DKIM y Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)
    
- [Configurar DKIM para que un servicio de terceros pueda enviar, o suplantar, correo electrónico en nombre de su dominio personalizado](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)
    
- [Pasos siguientes: una vez configurado DKIM para Office 365](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)
    
## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing-in-office-365"></a>Cómo DKIM funciona mejor que SPF solo para evitar la suplantación de identidad malintencionada en Office 365
<a name="HowDKIMWorks"> </a>

SPF agrega información a un sobre del mensaje pero DKIM cifra realmente una firma dentro del encabezado del mensaje. Cuando reenvía un mensaje, el servidor de reenvío puede quitar partes de ese sobre del mensaje. Como la firma digital permanece en el mensaje de correo electrónico porque forma parte del encabezado del correo, DKIM funciona incluso cuando un mensaje se ha reenviado como se muestra en el siguiente ejemplo.
  
![Diagrama que muestra un mensaje reenviado que pasa por la autenticación DKIM, donde se produce un error en la comprobación de SPF.](media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)
  
En este ejemplo, si solo había publicado un registro TXT de SPF en su dominio, el servidor de correo del destinatario podría haber marcado el correo electrónico como correo no deseado y generar un resultado de falso positivo. La adición de DKIM en este escenario reduce los informes de correo no deseado de falso positivo. Debido a que DKIM se basa en la criptografía de clave pública para autenticar y no solo en las direcciones IP, DKIM se considera una forma mucho más segura de autenticación que SPF. Se recomienda usar SPF y DKIM, así como DMARC, en la implementación.
  
Información esencial: DKIM usa una clave privada para insertar una firma cifrada en los encabezados del mensaje. El dominio de firma, o el dominio saliente, se inserta como el valor del campo **d=** en el encabezado. El dominio de comprobación, o dominio del destinatario, usa entonces el campo **=d** para buscar la clave pública desde DNS y autenticar el mensaje. Si el mensaje se comprueba, supera la comprobación DKIM. 
  
## <a name="what-you-need-to-do-to-manually-set-up-dkim-in-office-365"></a>Lo que necesita hacer para configurar manualmente DKIM en Office 365
<a name="SetUpDKIMO365"> </a>

Para configurar DKIM, deberá completar estos pasos:
  
- [Publicar dos registros CNAME para su dominio personalizado en DNS](use-dkim-to-validate-outbound-email.md#Publish2CNAME)
    
- [Habilitar la firma DKIM para su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)
    
### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a>Publicar dos registros CNAME para su dominio personalizado en DNS
<a name="Publish2CNAME"> </a>

Para cada dominio para el que quiera agregar una firma DKIM en DNS, necesita publicar dos registros CNAME. DNS usa un registro CNAME para especificar que el nombre canónico de un dominio es un alias de otro nombre de dominio. 
  
  Office 365 realiza la rotación de claves automática mediante los dos registros que establezca. Si ha aprovisionado dominios personalizados adicionales además del dominio inicial de Office 365, debe publicar dos registros CNAME para cada dominio adicional. Por lo tanto, si tiene dos dominios, debe publicar dos registros CNAME adicionales, y así sucesivamente. 
  
Use el formato siguiente para los registros CNAME:
  
```
Host name:          selector1._domainkey
Points to address or value: selector1-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600
```

Donde:
  
- Para Office 365, los selectores siempre serán "selector1" o "selector2". 
    
- _GuidDominio_ es el mismo que el _GuidDominio_ en el registro MX personalizado para su dominio personalizado que aparece antes de mail.protection.outlook.com. Por ejemplo, en el siguiente registro MX para el dominio contoso.com, el _GuidDominio_ es contoso-com: 
    
    ```
    contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com
    ```

- _initialDomain_ es el dominio que utiliza cuando se suscribió para Office 365. Dominios iniciales siempre finalizan en onmicrosoft.com. Para obtener información acerca de cómo determinar su dominio inicial, consulte [Preguntas más frecuentes de dominios](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).
    
Por ejemplo, si tiene un dominio inicial de cohovineyardandwinery.onmicrosoft.com y dos dominios personalizados cohovineyard.com y cohowinery.com, necesitará configurar dos registros CNAME para cada dominio adicional, un total de cuatro registros CNAME.
  
```
Host name:          selector1._domainkey
Points to address or value: **selector1-cohovineyard-com**._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: **selector2-cohovineyard-com**._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector1._domainkey
Points to address or value: **selector1-cohowinery-com**._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600
 
Host name:          selector2._domainkey
Points to address or value: **selector2-cohowinery-com**._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600
```

### <a name="enable-dkim-signing-for-your-custom-domain-in-office-365"></a>Habilitar la firma DKIM para su dominio personalizado en Office 365
<a name="EnableDKIMinO365"> </a>

Una vez que haya publicado los registros CNAME en DNS, está preparado para habilitar la firma DKIM mediante Office 365. Puede hacerlo a través del Centro de administración de Office 365 o mediante PowerShell.
  
#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-office-365-admin-center"></a>Para habilitar la firma DKIM para su dominio personalizado a través del Centro de administración de Office 365

1. [Inicie sesión en Office 365](https://support.office.microsoft.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) con su cuenta profesional o educativa. 
    
2. Seleccione el icono del iniciador de aplicaciones en la esquina superior izquierda y elija **Administración**.
    
3. En el panel de navegación inferior izquierdo, expanda **Administración** y elija **Exchange**.
    
4. Vaya a **Protección** \> **dkim**.
    
5. Seleccione el dominio para el que quiere habilitar DKIM y, después, en **Firmar los mensajes de este dominio con firmas DKIM**, elija **Habilitar**. Repita este paso para cada dominio personalizado.
    
#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a>Para habilitar la firma DKIM para su dominio personalizado mediante PowerShell

1. [Conexión a PowerShell de Exchange Online](https://technet.microsoft.com/library/jj984289.aspx).
    
2. Ejecute el comando siguiente:
    
    ```
    New-DkimSigningConfig -DomainName <domain> -Enabled $true
    ```

   Donde _dominio_ es el nombre del dominio personalizado que desea habilitar la firma para de DKIM. 
    
   Por ejemplo, para el dominio contoso.com:
    
    ```
    New-DkimSigningConfig -DomainName contoso.com -Enabled $true
    ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-office-365"></a>Para confirmar que la firma DKIM está configurada correctamente en Office 365

Espere unos minutos antes de seguir estos pasos para confirmar que ha configurado correctamente DKIM. Esto proporciona tiempo para que la información DKIM acerca del dominio se reparta por toda la red.
  
- Envíe un mensaje desde una cuenta dentro de su dominio habilitado para DKIM en Office 365 a otra cuenta de correo electrónico como outlook.com o Hotmail.com.
    
- No use una cuenta de aol.com con fines de prueba. AOL puede omitir la comprobación DKIM si se supera la comprobación SPF. Esto anulará la prueba.
    
- Abra el mensaje y observe el encabezado. Las instrucciones para ver el encabezado del mensaje variarán según el cliente de mensajería. Para obtener instrucciones acerca de cómo ver los encabezados de los mensajes en Outlook, consulte [Ver encabezados de mensajes de correo electrónico](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C).

  El mensaje con firma DKIM contendrá el nombre de host y el dominio que definió cuando publicó las entradas CNAME. El mensaje tendrá un aspecto similar al de este ejemplo: 
    
    ```
    From: Example User <example@contoso.com> 
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed; 
        s=selector1; d=contoso.com; t=1429912795; 
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type; 
        bh=<body hash>; 
        b=<signed field>;
    ```

- Busque el encabezado Authentication-Results. Aunque cada servicio de recepción usa un formato ligeramente diferente para estampar el correo entrante, el resultado debe incluir algo como **DKIM=pass** o **DKIM=OK**. 
    
## <a name="to-configure-dkim-for-more-than-one-custom-domain-in-office-365"></a>Configurar DKIM para más de un dominio personalizado en Office 365
<a name="DKIMMultiDomain"> </a>

Si en algún momento en el futuro decide agregar otro dominio personalizado y quiere habilitar DKIM para el dominio nuevo, debe completar los pasos de este artículo para cada dominio. En concreto, complete todos los pasos de [Lo que necesita hacer para configurar manualmente DKIM en Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).
  
## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain-in-office-365"></a>Deshabilitar la directiva de firmas DKIM para un dominio personalizado en Office 365
<a name="DisableDKIMSigningPolicy"> </a>

Deshabilitar la directiva de firmas no deshabilita DKIM completamente. Después de un período de tiempo, Office 365 aplicará automáticamente la directiva de Office 365 predeterminada para el dominio. Para obtener más información, consulte [Comportamiento predeterminado para DKIM y Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).
  
### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a>Para deshabilitar la directiva de firmas DKIM mediante Windows PowerShell

1. [Conexión a PowerShell de Exchange Online](https://technet.microsoft.com/library/jj984289.aspx).
    
2. Ejecute uno de los siguientes comandos para cada dominio para el que quiera deshabilitar la firma DKIM.
    
    ```
    $p=Get-DkimSigningConfig -identity <domain>
    $p[0] | set-DkimSigningConfig -enabled $false
    ```

   Por ejemplo:
    
    ```
    $p=Get-DkimSigningConfig -identity contoso.com
    $p[0] | set-DkimSigningConfig -enabled $false
    ```

   O bien
    
    ```
    Set-DkimSigningConfig -identity $p[<number>].identity -enabled $false
    ```

    Donde _number_ es el índice de la directiva. Por ejemplo: 
    
    ```
    Set-DkimSigningConfig -identity $p[0].identity -enabled $false
    ```

## <a name="default-behavior-for-dkim-and-office-365"></a>Comportamiento predeterminado para DKIM y Office 365
<a name="DefaultDKIMbehavior"> </a>

Si no habilita DKIM, Office 365 crea automáticamente una clave pública DKIM de 1024 bits para su dominio personalizado y la clave privada asociada que se almacena internamente en nuestro centro de datos. De forma predeterminada, Office 365 usa una configuración de firmas predeterminada para los dominios que no tienen una directiva local. Esto significa que si no configura DKIM, Office 365 usará su política predeterminada y se creará la clave para habilitar DKIM para el dominio.
  
Además, si deshabilita la firma DKIM después de habilitarla, después de un período de tiempo, Office 365 aplicará automáticamente la directiva predeterminada de Office 365 para el dominio.
  
En el ejemplo siguiente, suponga que Office 365 ha habilitado DKIM para fabrikam.com, no el administrador del dominio. Esto significa que los CNAME necesarios no existen en DNS. Las firmas DKIM para el correo electrónico de este dominio tendrán un aspecto similar al siguiente:
  
```
From: Second Example <second.example@fabrikam.com> 
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed; 
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795; 
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type; 
    bh=<body hash>; 
    b=<signed field>;
```

En este ejemplo, el nombre de host y el dominio contienen los valores a los que señalaría el registro CNAME si el administrador del dominio hubiera habilitado la firma DKIM para fabrikam.com. Finalmente, todos los mensajes enviados desde Office 365 contendrán una firma DKIM. Si habilita DKIM, el dominio será el mismo que el dominio que figura en la dirección del campo De:, en este caso, fabrikam.com. Si no lo hace, el dominio no se alineará y en su lugar se usará el dominio inicial de la organización. Para obtener información sobre cómo determinar el dominio inicial, vea [Preguntas más frecuentes de dominios](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).
  
## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a>Configurar DKIM para que un servicio de terceros pueda enviar, o suplantar, correo electrónico en nombre de su dominio personalizado
<a name="SetUp3rdPartyspoof"> </a>

Algunos proveedores de servicio de correo electrónico masivo o proveedores de software como servicio, le permiten configurar claves DKIM para el correo electrónico que se origina de su servicio. Esto requiere la coordinación entre el usuario y el servicio de terceros para configurar los registros DNS necesarios. No existen dos organizaciones que lo hagan exactamente de la misma manera. En su lugar, el proceso depende completamente de la organización.
  
Un mensaje de ejemplo que muestra un DKIM configurado correctamente para contoso.com y bulkemailprovider.com puede tener el aspecto siguiente:
  
```
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

En este ejemplo, para conseguir este resultado:
  
1. El proveedor de correo electrónico masivo le ha proporcionado una clave DKIM pública a Contoso.
    
2. Contoso ha publicado la clave DKIM en su registro DNS.
    
3. Al enviar el correo electrónico, el proveedor de correo electrónico masivo ha firmado la clave con la clave privada correspondiente. Al hacer esto, el proveedor de correo electrónico masivo ha adjuntado la firma DKIM al encabezado del mensaje.
    
4. Los sistemas de correo electrónico de recepción realizan una comprobación DKIM mediante la autenticación del valor d=\<dominio\> de la firma DKIM contra el dominio del campo De: (5322.From) dirección del mensaje. En este ejemplo, los valores coinciden:
    
    remitente @**contoso.com**
    
    d. =**contoso.com**
    
## <a name="next-steps-after-you-set-up-dkim-for-office-365"></a>Pasos siguientes: una vez configurado DKIM para Office 365
<a name="DKIMNextSteps"> </a>

Aunque DKIM está diseñado para ayudar a evitar la suplantación, DKIM funciona mejor con SPF y DMARC. Una vez haya configurado DKIM, si no ya configuró SPF, debe hacerlo. Para obtener una introducción rápida a SPF y para obtenerlo configurado rápidamente, vea [Set up SPF en Office 365 para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Para obtener una descripción más detallada de cómo Office 365 usa SPF, o para las implementaciones de solución de problemas o no estándar, como las implementaciones híbridas, empiece con [cómo Office 365 usa el marco de directivas de remitentes (SPF) para evitar la suplantación de identidad](how-office-365-uses-spf-to-prevent-spoofing.md). A continuación, vea [Usar DMARC para validar el correo electrónico en Office 365](use-dmarc-to-validate-email.md). [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md) incluye los campos de la sintaxis y encabezado utilizados por Office 365 para comprobaciones de DKIM. 
  

