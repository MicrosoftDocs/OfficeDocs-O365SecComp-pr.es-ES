---
title: Personalizar un tipo de información confidencial integrado
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Al buscar información confidencial en el contenido, es necesario describir esa información en lo que se denomina una regla. Prevención de pérdida de datos (DLP) incluye reglas para los tipos de información confidencial más comunes que se pueden usar inmediatamente. Para usar estas reglas, tendrá que incluirlas en una directiva. Quizás quiera ajustar estas reglas integradas para satisfacer las necesidades específicas de su organización; para hacerlo, puede crear un tipo de información confidencial personalizado. En este tema, se muestra cómo personalizar el archivo XML que contiene la colección de reglas existente para detectar una mayor variedad de posible información de tarjetas de crédito.
ms.openlocfilehash: 99a65e7862eb1657c73c77b526e3b82b7595d248
ms.sourcegitcommit: a5a7e43822336ed18d8f5879167766686cf6b2a3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2019
ms.locfileid: "36478159"
---
# <a name="customize-a-built-in-sensitive-information-type"></a><span data-ttu-id="86c34-107">Personalizar un tipo de información confidencial integrado</span><span class="sxs-lookup"><span data-stu-id="86c34-107">Customize a built-in sensitive information type</span></span>

<span data-ttu-id="86c34-p102">Al buscar información confidencial en el contenido, es necesario describir esa información en lo que se denomina una *regla*. Prevención de pérdida de datos (DLP) incluye reglas para los tipos de información confidencial más comunes que se pueden usar inmediatamente. Para usar estas reglas, tendrá que incluirlas en una directiva. Quizás quiera ajustar estas reglas integradas para satisfacer las necesidades específicas de su organización; para hacerlo, puede crear un tipo de información confidencial personalizado. En este tema, se muestra cómo personalizar el archivo XML que contiene la colección de reglas existente para detectar una mayor variedad de posible información de tarjetas de crédito.</span><span class="sxs-lookup"><span data-stu-id="86c34-p102">When looking for sensitive information in content, you need to describe that information in what's called a  *rule*  . Data loss prevention (DLP) includes rules for the most-common sensitive information types that you can use right away. To use these rules, you have to include them in a policy. You might find that you want to adjust these built-in rules to meet your organization's specific needs, and you can do that by creating a custom sensitive information type. This topic shows you how to customize the XML file that contains the existing rule collection to detect a wider range of potential credit-card information.</span></span> 
  
<span data-ttu-id="86c34-p103">Puede usar este ejemplo y aplicarlo en otros tipos de información confidencial integrados. Para obtener una lista de los tipos de información confidencial predeterminados y las definiciones XML, vea el tema [Información que buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="86c34-p103">You can take this example and apply it to other built-in sensitive information types. For a list of default sensitive information types and XML definitions, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span> 
  
## <a name="export-the-xml-file-of-the-current-rules"></a><span data-ttu-id="86c34-115">Exportar el archivo XML de las reglas actuales</span><span class="sxs-lookup"><span data-stu-id="86c34-115">Export the XML file of the current rules</span></span>

<span data-ttu-id="86c34-116">Para exportar el archivo XML, necesita [conectarse al Centro de seguridad y cumplimiento mediante PowerShell remoto](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="86c34-116">To export the XML, you need to [connect to the Security and Compliance Center via Remote PowerShell.](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="86c34-p104">En el símbolo del sistema de PowerShell, escriba lo siguiente para mostrar en pantalla las reglas de la organización. Si no creó sus propias reglas, solo verá las reglas integradas y predeterminadas con la etiqueta “Paquete de reglas de Microsoft”.</span><span class="sxs-lookup"><span data-stu-id="86c34-p104">In the PowerShell, type the following to display your organization's rules on screen. If you haven't created your own, you'll only see the default, built-in rules, labeled "Microsoft Rule Package."</span></span>

```powershell
Get-DlpSensitiveInformationTypeRulePackage
```    
2. <span data-ttu-id="86c34-p105">Guarde las reglas de la organización en una variable, escribiendo lo siguiente. Almacenar algo en una variable hace que el contenido sea fácilmente disponible más tarde en un formato que funciona para comandos remotos de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="86c34-p105">Store your organization's rules in a in a variable by typing the following. Storing something in a variable makes it easily available later in a format that works for remote PowerShell commands.</span></span>

```powershell    
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
```
    
3. <span data-ttu-id="86c34-p106">Para crear un archivo XML con formato que contenga todos los datos, escriba lo siguiente. (`Set-content` es la parte del cmdlet que escribe el código XML en el archivo).</span><span class="sxs-lookup"><span data-stu-id="86c34-p106">Make a formatted XML file with all that data by typing the following. ( `Set-content` is the part of the cmdlet that writes the XML to the file.)</span></span> 
    
```powershell
Set-Content -path C:\custompath\exportedRules.xml -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
```

> [!IMPORTANT]
> <span data-ttu-id="86c34-p107">Asegúrese de usar la ubicación del archivo donde realmente se almacene el paquete de reglas. `C:\custompath\` es un marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="86c34-p107">Make sure that you use the file location where your rule pack is actually stored.  `C:\custompath\` is a placeholder.</span></span> 
  
## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a><span data-ttu-id="86c34-125">Encontrar en el archivo XML la regla que quiera modificar</span><span class="sxs-lookup"><span data-stu-id="86c34-125">Find the rule that you want to modify in the XML</span></span>

<span data-ttu-id="86c34-p108">Los cmdlets anteriores exportaron toda la *colección de reglas*, que incluye las reglas predeterminadas que proporcionamos. Después, tendrá que buscar específicamente la regla de Número de tarjeta de crédito que quiere modificar.</span><span class="sxs-lookup"><span data-stu-id="86c34-p108">The cmdlets above exported the entire  *rule collection*  , which includes the default rules we provide. Next you'll need to look specifically for the Credit Card Number rule that you want to modify.</span></span> 
  
1. <span data-ttu-id="86c34-128">Use un editor de texto para abrir el archivo XML exportado en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="86c34-128">Use a text editor to open the XML file that you exported in the previous section.</span></span>
    
2. <span data-ttu-id="86c34-p109">Desplácese hasta la etiqueta `<Rules>` que se encuentra al principio de la sección que contiene las reglas de DLP. Como el archivo XML contiene la información de toda la colección de reglas, también contiene otra información al principio que necesita pasar para llegar a las reglas.</span><span class="sxs-lookup"><span data-stu-id="86c34-p109">Scroll down to the  `<Rules>` tag, which is the start of the section that contains the DLP rules. (Because this XML file contains the information for the entire rule collection, it contains other information at the top that you need to scroll past to get to the rules.)</span></span>
    
3. <span data-ttu-id="86c34-p110">Busque *Func_credit_card* para encontrar la definición de la regla de Número de tarjeta de crédito. En el XML, los nombres de regla no pueden contener espacios, por lo que normalmente estos se reemplazan por caracteres de subrayado y, a veces, los nombres de regla se abrevian. Un ejemplo de esto es la regla del Número del seguro social de EE. UU., que se abrevia como “SSN”. El código XML de la regla del Número de tarjeta de crédito debería tener el aspecto del ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="86c34-p110">Look for  *Func_credit_card*  to find the Credit Card Number rule definition. (In the XML, rule names can't contain spaces, so the spaces are usually replaced with underscores, and rule names are sometimes abbreviated. An example of this is the U.S. Social Security number rule, which is abbreviated "SSN." The Credit Card Number rule XML should look like the following code sample.</span></span>
    
  ```xml
  <Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085"
         patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
         <IdMatch idRef="Func_credit_card" />
          <Any minMatches="1">
            <Match idRef="Keyword_cc_verification" />
            <Match idRef="Keyword_cc_name" />
            <Match idRef="Func_expiration_date" />
          </Any>
        </Pattern>
      </Entity>
  ```

<span data-ttu-id="86c34-p111">Ahora que ha encontrado la definición de la regla de Número de tarjeta de crédito en el XML, puede personalizar el XML de la regla para que se adapte a sus necesidades. Para un repaso de las definiciones XML, vea el [Glosario de términos](#term-glossary) al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="86c34-p111">Now that you have located the Credit Card Number rule definition in the XML, you can customize the rule's XML to meet your needs. (For a refresher on the XML definitions, see the [Term glossary](#term-glossary) at the end of this topic.)</span></span>
  
## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a><span data-ttu-id="86c34-137">Modificar el código XML y crear un tipo de información confidencial</span><span class="sxs-lookup"><span data-stu-id="86c34-137">Modify the XML and create a new sensitive information type</span></span>

<span data-ttu-id="86c34-p112">En primer lugar, necesita crear un tipo de información confidencial, ya que las reglas predeterminadas no se pueden modificar directamente. Puede realizar una amplia variedad de acciones con los tipos de información confidencial personalizados, tal y como se describe en [Crear un tipo personalizado de información confidencial en PowerShell del Centro de seguridad y cumplimiento](create-a-custom-sensitive-information-type-in-scc-powershell.md). En este ejemplo, realizaremos pasos sencillos: solo se eliminarán las evidencias corroborativas y se agregarán palabras clave a la regla “Número de tarjeta de crédito”.</span><span class="sxs-lookup"><span data-stu-id="86c34-p112">First, you need to create a new sensitive information type because you can't directly modify the default rules. You can do a wide variety of things with custom sensitive information types, which are outlined in [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md). For this example, we'll keep it simple and only remove corroborative evidence and add keywords to the Credit Card Number rule.</span></span>
  
<span data-ttu-id="86c34-p113">Todas las definiciones de regla XML se basan en la siguiente plantilla general. Tiene que copiar y pegar el XML de definición de Número de tarjeta de crédito en la plantilla, modificar algunos valores (tenga en cuenta los marcadores de posición ". . ." en el siguiente ejemplo) y, después, cargar el XML modificado como una nueva regla que se pueda usar en directivas.</span><span class="sxs-lookup"><span data-stu-id="86c34-p113">All XML rule definitions are built on the following general template. You need to copy and paste the Credit Card Number definition XML in the template, modify some values (notice the ". . ." placeholders in the following example), and then upload the modified XML as a new rule that can be used in policies.</span></span>
  
```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." /> 
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
   <!-- Paste the Credit Card Number rule definition here.--> 
      <LocalizedStrings>
         <Resource idRef=". . .">
           <Name default="true" langcode=" . . . ">. . .</Name>
           <Description default="true" langcode=". . ."> . . .</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

<span data-ttu-id="86c34-p114">Ahora tiene algo parecido al siguiente XML. Como los paquetes de reglas y las reglas se identifican por sus GUID únicos, tiene que generar dos GUID: uno para el paquete de reglas y otro para reemplazar el GUID de la regla del Número de tarjeta de crédito. El GUID del ID de entidad en el ejemplo de código siguiente es el que se usa para nuestra definición de regla integrada que tiene que reemplazar. Hay varias maneras de generar GUID, pero puede hacerlo fácilmente en PowerShell escribiendo **[guid]::NewGuid()**.</span><span class="sxs-lookup"><span data-stu-id="86c34-p114">Now, you have something that looks similar to the following XML. Because rule packages and rules are identified by their unique GUIDs, you need to generate two GUIDs: one for the rule package and one to replace the GUID for the Credit Card Number rule. (The GUID for the entity ID in the following code sample is the one for our built-in rule definition, which you need to replace with a new one.) There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span></span> 
  
```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
  <RulePack id="8aac8390-e99f-4487-8d16-7f0cdee8defc">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="8d34806e-cd65-4178-ba0e-5d7d712e5b66" />
    <Details defaultLangCode="en">
      <LocalizedDetails langcode="en">
        <PublisherName>Contoso Ltd.</PublisherName>
        <Name>Financial Information</Name>
        <Description>Modified versions of the Microsoft rule package</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f"
       patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
      <LocalizedStrings>
         <Resource idRef="db80b3da-0056-436e-b0ca-1f4cf7080d1f"> 
<!-- This is the GUID for the preceding Credit Card Number entity because the following text is for that Entity. -->
           <Name default="true" langcode="en-us">Modified Credit Card Number</Name>
           <Description default="true" langcode="en-us">Credit Card Number that looks for additional keywords, and another version of Credit Card Number that doesn't require keywords (but has a lower confidence level)</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a><span data-ttu-id="86c34-150">Quitar el requisito de evidencias corroborativas de un tipo de información confidencial</span><span class="sxs-lookup"><span data-stu-id="86c34-150">Remove the corroborative evidence requirement from a sensitive information type</span></span>

<span data-ttu-id="86c34-151">Ahora que tiene un tipo de información confidencial que puede cargar al Centro de seguridad &amp; cumplimiento, el siguiente paso es hacer que la regla sea más específica.</span><span class="sxs-lookup"><span data-stu-id="86c34-151">Now that you have a new sensitive information type that you're able to upload to your Exchange environment, the next step is to make the rule more specific.</span></span> <span data-ttu-id="86c34-152">Modifique la regla para que solo busque un número de 16 dígitos que pasa la suma de comprobación pero no requiere evidencia corroborativa adicional (como las palabras clave).</span><span class="sxs-lookup"><span data-stu-id="86c34-152">Modify the rule so that it only looks for a 16-digit number that passes the checksum but doesn't require additional (corroborative) evidence (for example keywords).</span></span> <span data-ttu-id="86c34-153">Para ello, tiene que quitar la parte del código XML que busca la evidencia corroborativa.</span><span class="sxs-lookup"><span data-stu-id="86c34-153">To do this, you need to remove the part of the XML that looks for corroborative evidence.</span></span> <span data-ttu-id="86c34-154">La evidencia corroborativa es muy útil para reducir los falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="86c34-154">Corroborative evidence is very helpful in reducing false positives.</span></span> <span data-ttu-id="86c34-155">En este caso, suelen haber determinadas palabras clave o una fecha de expiración cerca del número de la tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="86c34-155">In this case there are usually certain keywords or an expiration date near the credit card number.</span></span> <span data-ttu-id="86c34-156">Si quita esa evidencia, debe ajustar también la seguridad que tiene de haber encontrado un número de tarjeta de crédito. Para ello, reduzca `confidenceLevel`, que es 85 en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="86c34-156">If you remove that evidence, you should also adjust how confident you are that you found a credit card number by lowering the confidenceLevel`confidenceLevel`, which is 85 in the example.</span></span>
  
```xml
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a><span data-ttu-id="86c34-157">Buscar palabras clave específicas de la organización</span><span class="sxs-lookup"><span data-stu-id="86c34-157">Look for keywords that are specific to your organization</span></span>

<span data-ttu-id="86c34-p116">Puede que quiera exigir evidencias corroborativas, pero con palabras clave diferentes o adicionales, y quizás quiera cambiar dónde buscar esa evidencia. Puede ajustar el valor de `patternsProximity` para aumentar o reducir el radio donde se buscará la evidencia corroborativa alrededor del número de 16 dígitos. Para agregar sus propias palabras clave, necesita definir una lista de palabras clave y hacer referencia a ella en su regla. El siguiente código XML agrega las palabras clave “company card” y “Contoso card” para que los mensajes que contengan esas frases a menos de 150 caracteres de un número de tarjeta de crédito se identifiquen como un número de tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="86c34-p116">You might want to require corroborative evidence but want different or additional keywords, and perhaps you want to change where to look for that evidence. You can adjust the  `patternsProximity` to expand or shrink the window for corroborative evidence around the 16-digit number. To add your own keywords, you need to define a keyword list and reference it within your rule. The following XML adds the keywords "company card" and "Contoso card" so that any message that contains those phrases within 150 characters of a credit card number will be identified as a credit card number.</span></span>
  
```xml
<Rules>
<! -- Modify the patternsProximity to be "150" rather than "300." -->
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="150" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
<!-- Add the following XML, which references the keywords at the end of the XML sample. -->
          <Match idRef="My_Additional_Keywords" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
<!-- Add the following XML, and update the information inside the <Term> tags with the keywords that you want to detect. -->
    <Keyword id="My_Additional_Keywords">
      <Group matchStyle="word">
        <Term caseSensitive="false">company card</Term>
        <Term caseSensitive="false">Contoso card</Term>
      </Group>
    </Keyword>
```

## <a name="upload-your-rule"></a><span data-ttu-id="86c34-162">Cargar la regla</span><span class="sxs-lookup"><span data-stu-id="86c34-162">Upload your rule</span></span>

<span data-ttu-id="86c34-163">Para cargar la regla, siga el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="86c34-163">To upload your rule, you need to do the following.</span></span>
  
1. <span data-ttu-id="86c34-p117">Guárdela como un archivo .xml con codificación Unicode. Es importante porque la regla no funcionará si se guarda con una codificación diferente.</span><span class="sxs-lookup"><span data-stu-id="86c34-p117">Save it as an .xml file with Unicode encoding. This is important because the rule won't work if the file is saved with a different encoding.</span></span>
    
2. [<span data-ttu-id="86c34-166">Conectarse al Centro de seguridad y cumplimiento con PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="86c34-166">Connect to the Security and Compliance Center via Remote PowerShell.</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
3. <span data-ttu-id="86c34-167">En el símbolo del sistema de PowerShell, escriba lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="86c34-167">In the PowerShell, type the following.</span></span>

```powershell    
New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte).
```
> [!IMPORTANT]
> <span data-ttu-id="86c34-p118">Asegúrese de usar la ubicación del archivo donde realmente se almacene el paquete de reglas. `C:\custompath\` es un marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="86c34-p118">Make sure that you use the file location where your rule pack is actually stored.  `C:\custompath\` is a placeholder.</span></span> 
  
4. <span data-ttu-id="86c34-170">Para confirmar, escriba “Y” y presione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="86c34-170">To confirm, type Y, and then press **Enter**.</span></span>
5. <span data-ttu-id="86c34-171">Compruebe que la nueva regla se haya cargado y que se muestre el nombre escribiendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="86c34-171">Verify that your new rule was uploaded and it's display name by typing:</span></span>

```powershell
Get-DlpSensitiveInformationType
```

<span data-ttu-id="86c34-p119">Para empezar a usar la nueva regla para detectar información confidencial, tiene que agregarla a una directiva DLP. Para obtener información sobre cómo agregar la regla a una directiva, vea [Crear una directiva DLP a partir de una plantilla](create-a-dlp-policy-from-a-template.md).</span><span class="sxs-lookup"><span data-stu-id="86c34-p119">To start using the new rule to detect sensitive information, you need to add the rule to a DLP policy. To learn how to add the rule to a policy, see [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md).</span></span>
  
## <a name="term-glossary"></a><span data-ttu-id="86c34-174">Glosario de términos</span><span class="sxs-lookup"><span data-stu-id="86c34-174">Term glossary</span></span>

<span data-ttu-id="86c34-175">Estas son las definiciones de los términos que encontró en este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="86c34-175">These are the definitions for the terms you encountered during this procedure.</span></span>
  
|<span data-ttu-id="86c34-176">**Término**</span><span class="sxs-lookup"><span data-stu-id="86c34-176">**Term**</span></span>|<span data-ttu-id="86c34-177">**Definición**</span><span class="sxs-lookup"><span data-stu-id="86c34-177">**Definition**</span></span>|
|:-----|:-----|
|<span data-ttu-id="86c34-178">Entidad</span><span class="sxs-lookup"><span data-stu-id="86c34-178">Entity</span></span>|<span data-ttu-id="86c34-p120">Las entidades son lo que llamamos tipos de información confidencial, como números de tarjeta de crédito. Cada entidad tiene un GUID único como ID. Si copia un GUID y lo busca en el código XML, encontrará la definición de regla XML y todas las traducciones localizadas de esa regla XML. Para encontrar esta definición, puede buscar el GUID de la traducción y, después, buscar por ese GUID.</span><span class="sxs-lookup"><span data-stu-id="86c34-p120">Entities are what we call sensitive information types, such as credit card numbers. Each entity has a unique GUID as its ID. If you copy a GUID and search for it in the XML, you'll find the XML rule definition and all the localized translations of that XML rule. You can also find this definition by locating the GUID for the translation and then searching for that GUID.</span></span>|
|<span data-ttu-id="86c34-183">Funciones</span><span class="sxs-lookup"><span data-stu-id="86c34-183">Functions</span></span>|<span data-ttu-id="86c34-p121">El archivo XML hace referencia a `Func_credit_card`, que es una función en código compilado. Las funciones se usan para ejecutar expresiones regulares complejas y verificar que las sumas de comprobación de nuestras reglas integradas coinciden). Como esto se produce en el código, algunas de las variables no aparecen en el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="86c34-p121">The XML file references  `Func_credit_card`, which is a function in compiled code. Functions are used to run complex regexes and verify that checksums match for our built-in rules.) Because this happens in the code, some of the variables don't appear in the XML file.</span></span>|
|<span data-ttu-id="86c34-186">IdMatch</span><span class="sxs-lookup"><span data-stu-id="86c34-186">IdMatch</span></span>|<span data-ttu-id="86c34-187">Este es el identificador para el que el patrón está intentando encontrar coincidencias, por ejemplo, un número de tarjeta de crédito.</span><span class="sxs-lookup"><span data-stu-id="86c34-187">This is the identifier that the pattern is to trying to match—for example, a credit card number.</span></span>|
|<span data-ttu-id="86c34-188">Listas de palabras clave</span><span class="sxs-lookup"><span data-stu-id="86c34-188">Keyword lists</span></span>|<span data-ttu-id="86c34-p122">El archivo XML también hace referencia a `keyword_cc_verification` y `keyword_cc_name`, que son listas de palabras clave en las que buscamos coincidencias dentro de `patternsProximity` para la entidad. Actualmente no se muestran en el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="86c34-p122">The XML file also references  `keyword_cc_verification` and  `keyword_cc_name`, which are lists of keywords from which we are looking for matches within the  `patternsProximity` for the entity. These aren't currently displayed in the XML.</span></span>|
|<span data-ttu-id="86c34-191">Pattern</span><span class="sxs-lookup"><span data-stu-id="86c34-191">Pattern</span></span>|<span data-ttu-id="86c34-192">El patrón contiene la lista de lo que el tipo confidencial está buscando.</span><span class="sxs-lookup"><span data-stu-id="86c34-192">The pattern contains the list of what the sensitive type is looking for.</span></span> <span data-ttu-id="86c34-193">Incluye palabras clave, regex y funciones internas que realizan tareas como verificar sumas de comprobación.</span><span class="sxs-lookup"><span data-stu-id="86c34-193">This includes keywords, regexes, and internal functions (that perform tasks like verifying checksums).</span></span> <span data-ttu-id="86c34-194">Los tipos de información confidencial pueden tener varios patrones con confianzas únicas.</span><span class="sxs-lookup"><span data-stu-id="86c34-194">Sensitive information types can have multiple patterns with unique confidences.</span></span> <span data-ttu-id="86c34-195">Esto resulta útil para crear un tipo de información confidencial que devuelve una confianza alta si se encuentra evidencia confirmativa y una confianza menor si se encuentra poca o ninguna evidencia confirmativa.</span><span class="sxs-lookup"><span data-stu-id="86c34-195">This is useful when creating a sensitive information type that returns a high confidence if corroborative evidence is found and a lower confidence if little or no corroborative evidence is found.</span></span>|
|<span data-ttu-id="86c34-196">Patrón confidenceLevel</span><span class="sxs-lookup"><span data-stu-id="86c34-196">Pattern confidenceLevel</span></span>|<span data-ttu-id="86c34-p124">Este es el nivel de confianza en el que el motor de DLP encontró una coincidencia. Este nivel de confianza está asociado con una coincidencia del patrón si se cumplen los requisitos del patrón. Esta es la medida de la confianza que debe tener en cuenta al usar las reglas de flujo de correo de Exchange (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="86c34-p124">This is the level of confidence that the DLP engine found a match. This level of confidence is associated with a match for the pattern if the pattern's requirements are met. This is the confidence measure you should consider when using Exchange mail flow rules (also known as transport rules).</span></span>|
|<span data-ttu-id="86c34-200">patternsProximity</span><span class="sxs-lookup"><span data-stu-id="86c34-200">patternsProximity</span></span>|<span data-ttu-id="86c34-201">Cuando encontramos lo que parece un patrón de número de tarjeta de crédito, `patternsProximity` es la proximidad alrededor de la cual buscaremos una evidencia corroborativa.</span><span class="sxs-lookup"><span data-stu-id="86c34-201">When we find what looks like a credit card number pattern,  `patternsProximity` is the proximity around that number where we'll look for corroborative evidence.</span></span>|
|<span data-ttu-id="86c34-202">recommendedConfidence</span><span class="sxs-lookup"><span data-stu-id="86c34-202">recommendedConfidence</span></span>|<span data-ttu-id="86c34-p125">Este es el nivel de confianza que le recomendamos para esta regla. La confianza recomendada se aplica a entidades y afinidades. En el caso de las entidades, este número nunca se evalúa según el valor de `confidenceLevel` del patrón. Es simplemente una sugerencia para ayudar a elegir un nivel de confianza si quiere aplicar uno. Para las afinidades, el valor de `confidenceLevel` del patrón necesita ser mayor que el número de `recommendedConfidence` para que se invoque una acción de regla de flujo de correo. El valor de `recommendedConfidence` es el nivel de confianza predeterminado que se usa en las reglas de flujo de correo que invoca una acción. Si quiere, puede cambiar manualmente la regla de flujo de correo para que, en su lugar, se invoque según el nivel de confianza del patrón.</span><span class="sxs-lookup"><span data-stu-id="86c34-p125">This is the confidence level we recommend for this rule. The recommended confidence applies to entities and affinities. For entities, this number is never evaluated against the  `confidenceLevel` for the pattern. It's merely a suggestion to help you choose a confidence level if you want to apply one. For affinities, the  `confidenceLevel` of the pattern must be higher than the  `recommendedConfidence` number for a mail flow rule action to be invoked. The  `recommendedConfidence` is the default confidence level used in mail flow rules that invokes an action. If you want, you can manually change the mail flow rule to be invoked based off the pattern's confidence level, instead.</span></span>|
   
## <a name="for-more-information"></a><span data-ttu-id="86c34-210">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="86c34-210">For more information</span></span>

- [<span data-ttu-id="86c34-211">Información que buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="86c34-211">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    
- [<span data-ttu-id="86c34-212">Crear un tipo de información confidencial personalizado</span><span class="sxs-lookup"><span data-stu-id="86c34-212">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
    
- [<span data-ttu-id="86c34-213">Información general sobre las directivas de prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="86c34-213">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
