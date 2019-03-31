---
title: 'RGPD: Informes, protección y detección de en el entorno de desarrollo y pruebas de Office 365'
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: Aquí se detallan las capacidades del RGPD en Office 365.
ms.openlocfilehash: d4d4113f6d78069a150e13c32ab192571671d986
ms.sourcegitcommit: 54d58da1777eb83adb82826d1bb1adb94903c8e1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "30955283"
---
# <a name="gdpr-discovery-protection-and-reporting-in-the-office-365-devtest-environment"></a>RGPD: Informes, protección y detección de en el entorno de desarrollo y pruebas de Office 365

 **Resumen:** Aquí se detallan las capacidades del RGPD en Office 365. 
  
En este artículo se explica cómo configurar y demostrar las capacidades de informes, protección y detección de la información de identificación personal (DCP) según el Reglamento general de protección de datos (RGPD) en un entorno de desarrollo y pruebas de Office 365.
  
## <a name="phase-1-create-and-configure-your-trial-office-365-subscription"></a>Fase 1: Crear y configurar una suscripción de prueba a Office 365

Realice primero los pasos de la [fase 2 del artículo sobre el entorno de desarrollo y pruebas de Office 365](https://docs.microsoft.com/Office365/Enterprise/office-365-dev-test-environment#phase-2-create-an-office-365-trial-subscription).

Luego, realice los pasos aquí indicados para configurar el Supervisor de eDiscovery:

1. Inicie sesión en su inquilino de prueba de Office 365 con su cuenta de administrador global.
2. En la página principal de Office 365, haga clic en **Seguridad y cumplimiento**.
3. En la pestaña Seguridad y cumplimento, haga clic en **Permisos** > **Administrador de eDiscovery**.
4. Haga clic en la opción **Editar** del Administrador de eDiscovery y, luego, haga clic en **Elegir administrador de eDiscovery**.
5. Haga clic en **+ Agregar**, busque el nombre de su cuenta de administrador global y agréguela como Supervisor de eDiscovery.
6. Haga clic en **Listo** > **Guardar** > **Cerrar**.
  
## <a name="phase-2-add-personally-identifiable-information-to-your-tenant"></a>Fase 2: Agregar información de identificación personal al inquilino

En esta fase, creará un documento con DCP consistente en una serie de números de cuenta bancaria internacional (IBAN) de ejemplo y lo almacenará en un sitio de SharePoint Online de su entorno de desarrollo y pruebas de Office 365.

1. En el equipo local, abra Microsoft Word.
2. Pegue la siguiente tabla en el archivo de Word y guárdelo como "IBANs.docx" en el equipo local.
    
    Número  |País  |Código |IBAN  |
    |---------|---------|---------|---------|
    |1     |  Austria SEPA      | AT            |AT611904300234573201       |
    |2     |  Bulgaria SEPA       |BG    |BG80BNBG96611020345678      |
    |3     |  Dinamarca SEPA      |   DK      |DK5000400440116243      |
    |4     |  Finlandia SEPA      |   FI      |FI2112345600000785         |
    |5     |  Francia SEPA       |   FR      |FR1420041010050500013M02606         |
    |6     |  Alemania SEPA      |   DE      |DE89370400440532013000         |
    |7     |  Grecia SEPA       |   GR      |GR1601101250000000012300695         |
    |8     |  Italia SEPA       |    TI     |GR1601101250000000012300695         |
    |9     |  Países Bajos SEPA      |   NL      |    NL91ABNA0417164300     |
    |10     | Polonia SEPA       |  PL       | PL27114020040000300201355387        |

Nota: Este conjunto de datos de ejemplo se obtuvo a partir de información disponible públicamente y solo ha de usarse con fines de pruebas.

3. En una pestaña nueva del explorador, escriba: **https://**\<suNombreDeInquilino\>**.sharepoint.com**.
4. Haga clic en **Documentos** para abrir la biblioteca de documentos de este sitio. Si se le pide realizar un recorrido de experiencia de lista nueva, haga clic en **Siguiente** hasta que finalice.
5.  Haga clic en **Cargar** > **Archivos** y seleccione el archivo IBANs.docx que creó en el paso 2.

  
## <a name="phase-3-demonstrate-data-discovery"></a>Fase 3: Demostrar la detección de datos

En esta fase, demostrará cómo realizar una búsqueda para encontrar el documento que creó y almacenó en la fase 2 a partir de su contenido de números IBAN.

1. En la pestaña Seguridad y cumplimiento, haga clic en **Inicio** y, después, haga clic en **Búsqueda e investigación** > **Búsqueda de contenido**.
2. Haga clic en **+** para crear un elemento de búsqueda.
3. En una ventana nueva, indique la siguiente información:  
    a. Nombre: Búsqueda de IBAN  
    b. ¿Dónde desea que busquemos?: **Elegir los sitios específicos para buscar** (haga clic en **+**) y escriba la dirección URL del sitio: **https://**\<suNombreDeInquilino\>**.sharepoint.com/**.  
    c. Haga clic en **Agregar** y, luego, haga clic en **Aceptar**. Si ve una advertencia, haga clic en **Aceptar**.  
    d. Haga clic en **Siguiente** en una ventana **Nueva búsqueda**.  
    e. En **¿Qué desea que busquemos?**: **SensitiveType: "Número de cuenta bancaria internacional (IBAN)"** y, después, haga clic en **Buscar**.

4. Confirme que aparece al menos un elemento en los resultados de la **búsqueda de IBAN**.


## <a name="phase-4-create-a-custom-sensitive-information-type-via-powershell"></a>Fase 4: Crear un tipo de información confidencial a través de PowerShell

En esta fase, creará un tipo de información confidencial personalizado para la empresa ficticia Contoso Corporation con Microsoft PowerShell. Contoso usa un número de cliente de Contoso (CCN) para distinguir a cada cliente en la base de datos de clientes. Un CCN tiene la siguiente estructura:
- Dos dígitos que representan el año en el que se creó el registro.
    - Contoso fue fundado en 2002, por lo tanto, el valor mínimo posible sería 02. 
- Tres dígitos que representan la agencia asociada que creó el registro.
    - Los posibles valores de agencia están comprendidos entre 000 y 999. 
- Un carácter alfabético que representa la línea de negocio.
    - Los valores posibles son a-z y se debe distinguir mayúsculas de minúsculas.
- Un número de serie de cuatro dígitos. 
    - Los posibles valores de número de serie están comprendidos entre 0000 y 9999.   

Contoso siempre hace referencia a los clientes usando un CCN en la correspondencia interna, la correspondencia externa, los documentos y otros formularios. En dicha empresa se necesita un tipo de información confidencial personalizado que permita detectar el uso de CCN en el contenido de Office 365 para, así, poder poner en marcha medidas de protección en el uso de esta información de identificación personal.

1. Siga las instrucciones del tema [Conectarse al PowerShell del Centro de seguridad y cumplimiento de Office 365 usando la autenticación multifactor](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) y conéctese al Centro de seguridad y cumplimiento con el UPN de su cuenta de administrador global.
2. Ejecute los siguientes comandos de PowerShell.

     ```
    #Create & start search for sample data
    $searchName = "Sample Customer Information Search"
    $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
    New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
    Start-ComplianceSearch -Identity $searchName#Create & start search for sample data
    $searchName = "Sample Customer Information Search"
    $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
    New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
    Start-ComplianceSearch -Identity $searchName
    ```
3. Ejecute los siguientes comandos de PowerShell y copie los GUID generados (en el orden en que aparecen) en una instancia del Bloc de notas abierta del equipo.
    ```
    #Generate three unique GUIDs
    Write-Host "GUID1 = "([guid]::NewGuid().Guid)
    Write-Host "GUID2 = "([guid]::NewGuid().Guid)
    Write-Host "GUID3 = "([guid]::NewGuid().Guid)
    ```
4. En el equipo local, abra otra instancia del Bloc de notas y pegue el siguiente contenido:

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce"> 
    <RulePack id="GUID1">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="GUID2" />
    <Details defaultLangCode="en"> 
    <LocalizedDetails langcode="en"> 
    <PublisherName>Contoso Ltd.</PublisherName> 
    <Name>Contoso Rule Package</Name> 
    <Description>Defines Contoso's custom set of classification rules</Description>
    </LocalizedDetails>
    </Details>
    </RulePack>
    <Rules>
    <!-- Contoso Customer Number (CCN) -->
    <Entity id="GUID3" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
    <IdMatch idRef="Regex_contoso_ccn" />
    <Match idRef="Keyword_contoso_ccn" />
    <Match idRef="Regex_eu_date" />
    </Pattern>
    </Entity>
    <Regex id="Regex_contoso_ccn">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</Regex>
    <Keyword id="Keyword_contoso_ccn">
    <Group matchStyle="word">
    <Term caseSensitive="false">customer number</Term>
    <Term caseSensitive="false">customer no</Term>
    <Term caseSensitive="false">customer #</Term>
    <Term caseSensitive="false">customer#</Term>
    <Term caseSensitive="false">Contoso customer</Term>
    </Group>
    </Keyword>
    <Regex id="Regex_eu_date"> (0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)? |feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|apr(ile|il)?|abr(il)?|avril |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)? |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}</Regex>
    <LocalizedStrings>
    <Resource idRef="GUID3">
    <Name default="true" langcode="en-us">Contoso Customer Number (CCN)</Name>
    <Description default="true" langcode="en-us">Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date</Description>
    </Resource>
    </LocalizedStrings>
    </Rules>
    </RulePackage>
    ```
5. Reemplace los valores de GUID1, GUID2 y GUID3 del texto XML del paso 4 por sus valores del paso 3 y, después, guarde el contenido en el equipo local con el nombre ContosoCCN.xml.
6. Rellene la ruta de acceso al archivo ContosoCCN.xml y ejecute los siguientes comandos.
    ```
    #Create new Sensitive Information Type
    $path="<path to the ContosoCCN.xml file, such as C:\Scripts\ContosoCCN.xml>"
    New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path $path -Encoding Byte -ReadCount 0)
    ```
7. En la pestaña Seguridad y cumplimiento, haga clic en **Clasificaciones** > **Tipos de información confidencial**. El número de cliente de Contoso (CCN) debería figurar en la lista.

## <a name="phase-5-demonstrate-data-protection"></a>Fase 5: Demostrar la protección de datos

La protección de información personal en Office 365 implica el uso de funciones de prevención de pérdida de datos (DLP).  Con las directivas DLP, toda la información confidencial en Office 365 se puede proteger automáticamente.

Existen varias formas de aplicar la protección. Un nivel de protección de la información con DLP de Office 365 consiste en instruir y concienciar acerca de dónde se almacenan los datos de los residentes de la UE en su entorno y cómo sus empleados pueden tratar estos datos.

En esta fase, creará una directiva DLP y demostrará cómo se aplica al archivo IBANs.docx que almacenó en SharePoint Online en la fase 2 cuando intente enviar un correo electrónico que contiene números IBAN.

1. En la pestaña Seguridad y cumplimiento del explorador, haga clic en **Inicio**.
2. Haga clic en **Prevención de pérdida de datos** > **Directiva**.
3. Haga clic en **+ Crear una directiva**.
4. En **Empezar con una plantilla o crear una directiva personalizada**, haga clic en **Personalizada** > **Directiva personalizada** > **Siguiente**.
5. En **Dar un nombre a la directiva**, especifique los siguientes detalles y haga clic en **Siguiente**: a. Nombre: **Directiva de DCP de ciudadanos de la UE** b. Descripción: **Proteger la información de identificación personal de los ciudadanos europeos**.
6. En **Elegir ubicaciones**, seleccione **Todas las ubicaciones en Office 365**. Se incluirá el contenido del correo electrónico de Exchange y de los documentos de OneDrive y SharePoint. Tras esto, haga clic en **Siguiente**.
7. En **Personalizar el tipo de contenido que quiere proteger**, haga clic en **Buscar contenido que incluya:** y haga clic en **Editar**.
8. En **Elegir los tipos de contenido que se van a proteger**, haga clic en **Agregar** > **Tipos de información confidencial**.
9. En **Tipos de información confidencial**, haga clic en **+ Agregar**.
10. En **Tipos de información confidencial**, busque **IBAN**, active la casilla **Número de cuenta bancaria internacional (IBAN)** y, después, haga clic en **Agregar**.
11. Compruebe que el tipo de información confidencial **Número de cuenta bancaria internacional (IBAN)** se ha agregado y haga clic en **Listo**.
12. En **El contenido incluye**, confirme que se han agregado los tipos de información confidencial y, después, haga clic en **Guardar**.
13. En **Personalizar el tipo de contenido que quiere proteger**, confirme que **Buscar contenido que incluya:** contiene **Número de cuenta bancaria internacional (IBAN)** y haga clic en **Siguiente**.
14. En **Detectar cuándo el contenido compartido incluye:**, cambie el valor de **10** a **1** y, luego, haga clic en **Siguiente**.
15. En **¿Desea activar la directiva o probarla primero?**, seleccione las siguientes opciones y haga clic en **Siguiente**.  
    a. Seleccione la opción **Me gustaría probarla primero**.  
    b. Active la casilla de verificación **Mostrar sugerencias de directiva durante el modo de prueba**. 
16. En **Revisar la configuración**, revise la configuración y, tras ello, haga clic en **Crear**. Nota: Después de crear una directiva DLP, esta tardará algún tiempo en entrar en vigor.
17. En el equipo local, abra una instancia privada del explorador.
18. En la barra de direcciones, escriba **https://**\<suNombreDeInquilino\>**.sharepoint.com** e inicie sesión con su cuenta de administrador global.
19. Haga clic en **Documentos**.
20. Haga clic en el archivo "IBANs.docx". Debería aparecer "Sugerencia de directiva para IBANs.docx". El archivo IBANs.docx se ha compartido con destinatarios externos, lo cual infringe la directiva DLP. 
21. En la barra de direcciones, escriba: `https://outlook.office365.com`
22. Haga clic en **Nuevo** - **Mensaje de correo electrónico** e indique lo siguiente:  
    - **Para:** \<dirección de correo electrónico personal\>  
    - **Asunto:** Prueba de RGPD  
    - **Cuerpo:** Copie esta tabla de valores:
  
        |Número  |País  |Código |IBAN  |
        |---------|---------|---------|---------|
        |1     |  Austria SEPA      | AT            |AT611904300234573201       |
        |2     |  Bulgaria SEPA       |BG    |BG80BNBG96611020345678      |
        |3     |  Dinamarca SEPA      |   DK      |DK5000400440116243      |
        |4     |  Finlandia SEPA      |   FI      |FI2112345600000785         |
        |5     |  Francia SEPA       |   FR      |FR1420041010050500013M02606         |
        |6     |  Alemania SEPA      |   DE      |DE89370400440532013000         |
        |7     |  Grecia SEPA       |   GR      |GR1601101250000000012300695         |
        |8     |  Italia SEPA       |    TI     |GR1601101250000000012300695         |
        |9     |  Países Bajos SEPA      |   NL      |   NL91ABNA0417164300      |
        |10     | Polonia SEPA       |  PL       | PL27114020040000300201355387        |

Nota: Este conjunto de datos de ejemplo se obtuvo a partir de información disponible públicamente y solo ha de usarse con fines de pruebas.

23. Verá que la directiva DLP detecta que el cuerpo del correo contiene números IBAN y proporciona una sugerencia de directiva en la parte superior de la ventana del mensaje.
24. Cierre la instancia privada del explorador.


## <a name="phase-6-demonstrate-reporting"></a>Fase 6: Demostrar la creación de informes
 
En esta fase, demostrará cómo crear un informe de Office 365 basándose en la directiva DLP configurada en la fase 5.

   1. En la pestaña Seguridad y cumplimiento del explorador, haga clic en **Inicio**.
   2. Haga clic en **Informes** > **Panel** > **Coincidencias de directivas DLP**.
   3. La directiva DLP ayuda a detectar y proteger la información confidencial de la organización. Así, por ejemplo, en el informe se reflejará que la directiva ha detectado el documento que contiene números IBAN almacenados en SharePoint Online.
  
## <a name="see-also"></a>Consulte también

[Information Protection de Office 365 para RGPD](office-365-information-protection-for-gdpr.md)

[RGPD pata Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/gdpr?toc=/microsoft-365/enterprise/toc.json)
