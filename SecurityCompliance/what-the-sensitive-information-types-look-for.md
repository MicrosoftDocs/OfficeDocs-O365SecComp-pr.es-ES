---
title: Qué buscan los tipos de información confidencial
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
ms.assetid: fd505979-76be-4d9f-b459-abef3fc9e86b
description: Prevención de pérdida de datos (DLP) en la seguridad de Office 365 &amp; centro de cumplimiento incluye los tipos de información confidencial 80 que están listos para su uso en las directivas de DLP. En este tema se enumera todos estos tipos de información confidencial y muestra lo que busca una directiva de DLP cuando detecta cada tipo.
ms.openlocfilehash: 4b083f80e02c80053b63ee897b2515a4505c16d9
ms.sourcegitcommit: 8c5a88433cff23c59b436260808cf3d91b06fdef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/07/2018
ms.locfileid: "27194741"
---
# <a name="what-the-sensitive-information-types-look-for"></a>Qué buscan los tipos de información confidencial

Prevención de pérdida de datos (DLP) en la seguridad de Office 365 &amp; centro de cumplimiento incluye muchos tipos de información confidencial que están listos para su uso en las directivas de DLP. En este tema se enumera todos estos tipos de información confidencial y muestra lo que busca una directiva de DLP cuando detecta cada tipo. Un tipo de información confidencial se define mediante un patrón que puede identificarse mediante una expresión regular o una función. Además, como las palabras clave y sumas de comprobación de prueba puede utilizarse para identificar un tipo de información confidencial. Proximidad y nivel de confianza también se usan en el proceso de evaluación.
  
## <a name="aba-routing-number"></a>Número de enrutamiento ABA

### <a name="format"></a>Formato

9 dígitos, que pueden tener un patrón con o sin formato

### <a name="pattern"></a>Patrón

Con formato:
- Cuatro dígitos a partir de 0, 1, 2, 3, 6, 7 u 8
- Un guion
- Cuatro dígitos
- Un guion
- Un dígito

Sin formato: dígitos consecutivos 9 a partir de 0, 1, 2, 3, 6, 7 o 8 

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_aba_routing encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_ABA_Routing.

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a>Palabras clave

#### <a name="keywordabarouting"></a>Keyword_ABA_Routing

- aba
- 
aba #
- 
aba routing #
- número de enrutamiento ABA
- 
aba#
- 
abarouting#
- 
aba number
- 
abaroutingnumber
- 
american bank association routing #
- 
american bank association routing number
- 
americanbankassociationrouting#
- 
americanbankassociationroutingnumber
- 
bank routing number
- 
bankrouting#
- 
bankroutingnumber
- 
routing transit number
- 
RTN
 
   
## <a name="argentina-national-identity-dni-number"></a>Número de identidad nacional (DNI) de Argentina

### <a name="format"></a>Formato

Ocho dígitos separados por puntos

### <a name="pattern"></a>Patrón

Ocho dígitos:
- Dos dígitos
- Un punto 
- Tres dígitos
- Un punto 
- Tres dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_argentina_national_id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_argentina_national_id.

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordargentinanationalid"></a>Keyword_argentina_national_id

- Número de identidad nacional de Argentina
 
- Identidad 
- Tarjeta de identidad nacional de identificación 
- DNI
 
- Registro nacional de NIC de personas 
- Documento Nacional de Identidad
 
- Registro nacional de las personas
 
- Identidad
 
- Identificación
 
   
## <a name="australia-bank-account-number"></a>Número de cuenta bancaria de Australia

### <a name="format"></a>Formato

De 6 a 10 dígitos con o sin número de sucursal bancaria de estado

### <a name="pattern"></a>Patrón

Número de cuenta es 10 de 6 dígitos. Número de sucursal de estado de banco de Australia:
- Tres dígitos 
- Un guión  
- Tres dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_australia_bank_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_australia_bank_account_number.
- La expresión regular Regex_australia_bank_account_number_bsb encuentra contenido que coincide con el patrón.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_australia_bank_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_australia_bank_account_number.

```
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordaustraliabankaccountnumber"></a>Keyword_australia_bank_account_number

- swift bank code
- 
correspondent bank
- 
base currency
- 
usa account
- 
holder address
- 
bank address
- 
information account
- 
fund transfers
- 
bank charges
- 
bank details
- 
banking information
- 
full names
- 

iaea

   
## <a name="australia-drivers-license-number"></a>Número de licencia de conducción de Australia

### <a name="format"></a>Formato

Nueve letras y dígitos

### <a name="pattern"></a>Patrón

Nueve letras y dígitos: 

- Dos dígitos o letras (no distinguen entre mayúsculas y minúsculas) 
- Dos dígitos 
- Cinco dígitos o letras (no distinguen entre mayúsculas y minúsculas)

O bien

- 1 o 2 letras opcionales (no distingue entre mayúsculas y minúsculas)  
- 4-9 dígitos

O bien

- Nueve dígitos o letras (no distingue entre mayúsculas y minúsculas)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_australia_drivers_license_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_australia_drivers_license_number.
- No se encuentra ninguna palabra clave de Keyword_australia_drivers_license_number_exclusions.

```
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordaustraliadriverslicensenumber"></a>Keyword_australia_drivers_license_number

- international driving permits
- 
australian automobile association
- 
international driving permit
- DriverLicence
- DriverLicences
- Lic de controlador
- Driver Licence

- Driver Licences

- DriversLic
- DriversLicence
- DriversLicences
- Lic de controladores
- LIC de controladores
- Licencia de controladores
- Licencias de controladores
- Driver'Lic
- Driver'Lics
- Driver'Licence
- Driver'Licences
- Controlador ' Lic
- Controlador ' LIC
- Controlador ' licencia
- Controlador ' certificados
- Driver'sLic
- Driver'sLics
- Driver'sLicence
- Driver'sLicences
- Lic del controlador
- LIC del controlador
- Driver's Licence

- Driver's Licences

- DriverLic #
- DriverLics #
- DriverLicence #
- DriverLicences #
- Driver Lic#
- 
Driver Lics#

- Controlador certificado #
- Controlador certificados #
- DriversLic #
- DriversLics #
- DriversLicence #
- DriversLicences #
- Controladores Lic #
- Controladores LIC #
- Licencia de controladores #
- Controladores certificados #
- Driver'Lic#

- Driver'Lics#

- Driver'Licence#

- Driver'Licences#

- Driver' Lic#

- Driver' Lics#

- Controlador ' certificado #
- Controlador ' certificados #
- Driver'sLic #
- Driver'sLics #
- Driver'sLicence #
- Driver'sLicences #
- Driver's Lic#

- Driver's Lics#

- Certificado # del controlador
- El certificado # del controlador 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a>Keyword_australia_drivers_license_number_exclusions

- aaa
- DriverLicense
- DriverLicenses
- Licencia de controlador
- Licencias de controlador
- PermisoDeConducción
- DriversLicenses
- Licencia de controladores
- Licencias de controladores
- Driver'License
- Driver'Licenses
- Controlador ' licencia
- Controlador ' licencias
- Driver'sLicense
- Driver'sLicenses
- De conducir permiso
- Permisos de conducir
- DriverLicense #
- DriverLicenses #
- Controlador licencia #
- Controlador licencias #
- PermisoDeConducción #
- DriversLicenses #
- Licencia de controladores #
- Licencias de controladores #
- Driver'License#

- Driver'Licenses#

- Driver' License#

- Driver' Licenses#

- Driver'sLicense #
- Driver'sLicenses #
- Driver's License#

- 

Driver's Licenses#
   
## <a name="australia-medical-account-number"></a>Número de cuenta médica de Australia

### <a name="format"></a>Formato

Entre 10 y 11 dígitos

### <a name="pattern"></a>Patrón

Entre 10 y 11 dígitos:
- el primer dígito está en el intervalo de 2 a 6
- El noveno dígito es un dígito de comprobación
- El décimo dígito es el dígito de emisión
- El undécimo dígito (opcional) es el número individual

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_australian_medical_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_Australia_Medical_Account_Number.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_australian_medical_account_number encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="95">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="1">
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
<Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="0" maxMatches="0">
  <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordaustraliamedicalaccountnumber"></a>Keyword_Australia_Medical_Account_Number

- bank account details
- 
medicare payments
- 
mortgage account
- 
bank payments
- 
information branch
- 
credit card loan
- 
department of human services
- servicio local
- 

medicare

   
## <a name="australia-passport-number"></a>Número de pasaporte de Australia

### <a name="format"></a>Formato

Una letra seguida de siete dígitos

### <a name="pattern"></a>Patrón

Una letra (no distingue entre mayúsculas y minúsculas) seguida de siete dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_australia_passport_number encuentra contenido que coincide con el patrón.
- Se ha encontrado una palabra clave de Keyword_passport o Keyword_australia_passport_number.

```
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordpassport"></a>Keyword_passport

- Passport Number
- 
Passport No
- Passport #

- Passport#

- PassportID
- Passportno

- passportnumber

- パスポート
- パスポート番号

- パスポートのNum

- 
パスポート ＃
 
- Numéro de passeport
- 
Passeport n °
- Passeport Non

- Passeport #

- Passeport#

- PasseportNon
- Passeportn °


#### <a name="keywordaustraliapassportnumber"></a>Keyword_australia_passport_number

- passport
- 
passport details
- 
immigration and citizenship
- 
commonwealth of australia
- 
department of immigration
- 
residential address
- 
department of immigration and citizenship
- visa

- 
national identity card
- número de cuenta de Passport
- 
travel document
- 

issuing authority
   
## <a name="australia-tax-file-number"></a>Número de archivo de impuestos de Australia

### <a name="format"></a>Formato

Entre 8 y 9 dígitos

### <a name="pattern"></a>Patrón

8-9 dígitos que normalmente se presentan con espacios como sigue:
- Tres dígitos 
- Un espacio opcional 
- Tres dígitos 
- Un espacio opcional 
- 2-3 dígitos donde el último dígito es un dígito de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_australian_tax_file_number encuentra contenido que coincide con el patrón.
- No se encuentra ninguna palabra clave de Keyword_Australia_Tax_File_Number ni Keyword_number_exclusions.
- Se supera la suma de comprobación.

```
    <!-- Australia Tax File Number -->
<Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
    
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_Australia_Tax_File_Number" />
          <Match idRef="Keyword_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordaustraliataxfilenumber"></a>Keyword_Australia_Tax_File_Number

- australian business number
- 
marginal tax rate
- 
medicare levy
- 
portfolio number
- 
service veterans
- 
withholding tax
- 
individual tax return
- 

tax file number

#### <a name="keywordnumberexclusions"></a>Keyword_number_exclusions

- 00000000
- 11111111
- por 22222222
- 33333333
- 44444444
- 55555555
- 66666666
- 77777777
- 88888888
- 99999999
- 000000000
- 111111111
- 222222222
- 333333333
- 444444444
- 555555555
- 666666666
- 777777777
- 888888888
- 999999999
- 0000000000
- 1111111111
- 2222222222
- 3333333333
- 4444444444
- 5555555555
- 6666666666
- 7777777777
- 8888888888
- 9999999999
   
## <a name="belgium-national-number"></a>Número nacional de Bélgica

### <a name="format"></a>Formato

11 dígitos más delimitadores

### <a name="pattern"></a>Patrón

11 dígitos más delimitadores:
- Seis dígitos y dos puntos con el formato AA.MM.DD para la fecha de nacimiento  
- Un guión  
- Tres dígitos secuenciales (impares para hombres, pares para mujeres)  
- Un punto  
- Dos dígitos que son un dígito de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_belgium_national_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_belgium_national_number.
- Se supera la suma de comprobación.

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordbelgiumnationalnumber"></a>Keyword_belgium_national_number

- Identidad
- Registration
- Identificación 
- ID 
- Identiteitskaart
- Registratie nummer 
 
- Identificatie nummer
 
- Identiteit
- Registratie
- Identificatie

 
- Carte d’identité
 
- numéro d'immatriculation
- numéro d'identification
- 
identité
 
- inscription
 
- Identifikation
- Identifizierung
- Identifikationsnummer
- Personalausweis
- Registrierung
- Registrationsnummer

   
## <a name="brazil-cpf-number"></a>Número CPF de Brasil

### <a name="format"></a>Formato

11 dígitos incluido un dígito de control y que pueden tener o no formato

### <a name="pattern"></a>Patrón

Con formato:
- Tres dígitos 
- Un punto  
- Tres dígitos 
- Un punto  
- Tres dígitos 
- Un guión  
- Dos dígitos que son dígitos de control

Sin formato:
- 11 dígitos, donde los dos últimos dígitos son dígitos de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_brazil_cpf encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_brazil_cpf.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_brazil_cpf encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordbrazilcpf"></a>Keyword_brazil_cpf

- CPF
- Identificación
- Registro
- Ingresos
- Cadastro de Pessoas Físicas
 
- Imposto
 
- Identificação
 
- Inscrição
 
- Receita

 
   
## <a name="brazil-legal-entity-number-cnpj"></a>Número de entidad jurídica de Brasil (CNPJ)

### <a name="format"></a>Formato

14 dígitos que incluyen un número de registro, número de sucursal y dígitos de comprobación, además de delimitadores

### <a name="pattern"></a>Patrón
14 dígitos más delimitadores:
- Dos dígitos 
- Un punto  
- Tres dígitos 
- Un punto  
- Tres dígitos (estos ocho primeros dígitos son el número de registro)  
- Una barra diagonal  
- Número de sucursal de cuatro dígitos  
- Un guión  
- Dos dígitos que son dígitos de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_brazil_cnpj encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_brazil_cnpj.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_brazil_cnpj encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordbrazilcnpj"></a>Keyword_brazil_cnpj

- CNPJ
 
- CNPJ/MF 
- CNPJ-MF
 
- Registro nacional de entidades jurídicas
 
- Registro de contribuyentes
 
- Entidad jurídica
 
- Entidades jurídicas
 
- Estado de registro
 
- Negocio
 
- Company
- CNPJ
 
- Cadastro Nacional da Pessoa Jurídica
 
- Cadastro Geral de Contribuintes
 
- CGC
 
- Pessoa jurídica
 
- Pessoas jurídicas
 
- Situação cadastral
 
- Inscrição
 
- Empresa
 
   
## <a name="brazil-national-id-card-rg"></a>Tarjeta de identificación nacional de Brasil (RG)

### <a name="format"></a>Formato

Registro Geral (formato anterior): nueve dígitos

Registro de Identidade (RIC) (nuevo formato): 11 dígitos

### <a name="pattern"></a>Patrón

Registro de Geral (formato antiguo):
- Dos dígitos 
- Un punto  
- Tres dígitos 
- Un punto  
- Tres dígitos 
- Un guión  
- Un dígito que es un dígito de control

Registro de Identidade (RIC) (nuevo formato):
- 10 dígitos 
- Un guión  
- Un dígito que es un dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_brazil_rg encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_brazil_rg.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_brazil_rg encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordbrazilrg"></a>Keyword_brazil_rg

Cédula de identidade tarjeta de identidad nacional identificador número de rregistro registro de Iidentidade registro geral RG (esta palabra clave distingue mayúsculas de minúsculas) RIC (esta palabra clave distingue mayúsculas de minúsculas) 
   
## <a name="canada-bank-account-number"></a>Número de cuenta bancaria de Canadá

### <a name="format"></a>Formato

Siete o doce dígitos

### <a name="pattern"></a>Patrón

El número de una cuenta bancaria de Canadá contiene siete o doce dígitos.

Un número de tránsito de cuenta bancaria de Canadá es:
- Cinco dígitos 
- Un guión  
- Tres dígitos o
- Un cero "0"  
- Ocho dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_canada_bank_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_canada_bank_account_number.
- La expresión regular Regex_canada_bank_account_transit_number encuentra contenido que coincide con el patrón.

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_canada_bank_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_canada_bank_account_number.

```
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordcanadabankaccountnumber"></a>Keyword_canada_bank_account_number

- canada savings bonds
- 
canada revenue agency
- 
canadian financial institution
- 
direct deposit form
- 
canadian citizen
- 
legal representative
- 
notary public
- 
commissioner for oaths
- 
child care benefit
- 
universal child care
- 
canada child tax benefit
- 
income tax benefit
- 
harmonized sales tax
- social insurance number
- 
income tax refund
- 
child tax benefit
- 
territorial payments
- 
institution number
- 
deposit request
- 
banking information
- 

direct deposit
   
## <a name="canada-drivers-license-number"></a>Número de licencia de conductor de Canadá

### <a name="format"></a>Formato

Varía según la provincia

### <a name="pattern"></a>Patrón

Varios patrones que cubren Alberta, British Columbia, Manitoba, New Brunswick, Terranova y Labrador, Nueva Escocia, Ontario, Isla del Príncipe Eduardo, Quebec y Saskatchewan

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_[province_name]_drivers_license_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_[province_name]_drivers_license_name.
- Se encuentra una palabra clave de Keyword_canada_drivers_license.

```
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordprovincenamedriverslicensename"></a>Keyword_[province_name]_drivers_license_name

- La abreviatura de la provincia, por ejemplo, AB
- 
El nombre de la provincia, por ejemplo, Alberta

#### <a name="keywordcanadadriverslicense"></a>Keyword_canada_drivers_license

- DL
- DLS
- CDL
- CDLS
- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- DriverLicence
- DriverLicences
- Lic de controlador
- LIC de controlador
- Licencia de controlador
- Licencias de controlador
- Driver Licence

- Driver Licences

- DriversLic
- DriversLics
- DriversLicence
- DriversLicences
- PermisoDeConducción
- DriversLicenses
- Lic de controladores
- LIC de controladores
- Licencia de controladores
- Licencias de controladores
- Licencia de controladores
- Licencias de controladores
- Driver'Lic
- Driver'Lics
- Driver'License
- Driver'Licenses
- Driver'Licence
- Driver'Licences
- Controlador ' Lic
- Controlador ' LIC
- Controlador ' licencia
- Controlador ' licencias
- Controlador ' licencia
- Controlador ' certificados
- Driver'sLic
- Driver'sLics
- Driver'sLicense
- Driver'sLicenses
- Driver'sLicence
- Driver'sLicences
- Lic del controlador
- LIC del controlador
- De conducir permiso
- Permisos de conducir
- Driver's Licence

- Driver's Licences

- Permis de Conduire
- id
- identificadores de
- 
idcard number
- 
idcard numbers
- 
idcard #
- 
idcard #s
- tarjeta de idcard
- tarjetas de idcard
- idcard
- identification number

- identification numbers

- identification #

- 
identification #s
- tarjeta de identificación
- tarjetas de identificación
- 
identification
 
- DL#
- 
DLS#
 
- CDL#
 
- CDLS#
 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- DriverLicence # 
- DriverLicences # 
- Driver Lic#
- 
Driver Lics#
 
- Controlador licencia # 
- Controlador licencias # 
- Controlador licencia # 
- Controlador certificados # 
- DriversLic # 
- DriversLics # 
- PermisoDeConducción # 
- DriversLicenses # 
- DriversLicence # 
- DriversLicences # 
- Controladores Lic # 
- Controladores LIC # 
- Licencia de controladores # 
- Licencias de controladores # 
- Licencia de controladores # 
- Controladores certificados # 
- Driver'Lic#
 
- Driver'Lics#
 
- Driver'License#
 
- Driver'Licenses#
 
- Driver'Licence#
 
- Driver'Licences#
 
- Driver' Lic#
 
- Driver' Lics#
 
- Driver' License#
 
- Driver' Licenses#
 
- Controlador ' certificado # 
- Controlador ' certificados # 
- Driver'sLic # 
- Driver'sLics # 
- Driver'sLicense # 
- Driver'sLicenses # 
- Driver'sLicence # 
- Driver'sLicences # 
- Driver's Lic#
 
- Driver's Lics#
 
- Driver's License#
 
- Driver's Licenses#
 
- Certificado # del controlador 
- El certificado # del controlador 
- Permis de Conduire # 
- identificador de # 
- los identificadores de # 
- idcard card#
 
- idcard cards#
 
- idcard#
 
- identification card#
 
- identification cards#
 
- identification#
 
   
## <a name="canada-health-service-number"></a>Número de servicio de salud de Canadá

### <a name="format"></a>Formato

10 dígitos

### <a name="pattern"></a>Patrón

10 dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_canada_health_service_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_canada_health_service_number.

```
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordcanadahealthservicenumber"></a>Keyword_canada_health_service_number

- personal health number
- 
patient information
- Servicios de mantenimiento
- 
speciality services
- 
automobile accident
- 
patient hospital
- 
psychiatrist
- 
workers compensation
- 
disability
      
## <a name="canada-passport-number"></a>Número de pasaporte de Canadá

### <a name="format"></a>Formato

Dos letras mayúsculas seguidas por seis dígitos

### <a name="pattern"></a>Patrón

Dos letras mayúsculas seguidas por seis dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_canada_passport_number encuentra contenido que coincide con el patrón.
- Se ha encontrado una palabra clave de Keyword_canada_passport_number o Keyword_passport.

``` 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordcanadapassportnumber"></a>Keyword_canada_passport_number

- canadian citizenship
- 
canadian passport
- 
passport application
- 
passport photos
- 
certified translator
- 
canadian citizens
- 
processing times
- 

renewal application

#### <a name="keywordpassport"></a>Keyword_passport

- Passport Number
- 
Passport No
- Passport #

- Passport#

- PassportID
- Passportno

- passportnumber

- パスポート
- パスポート番号

- パスポートのNum

- パスポート＃

- Numéro de passeport
- 
Passeport n °
- Passeport Non

- Passeport #

- Passeport#

- PasseportNon
- 

Passeportn °
   
## <a name="canada-personal-health-identification-number-phin"></a>Número de Identificación Personal de salud en Canadá (PHIN)

### <a name="format"></a>Formato

Nueve dígitos

### <a name="pattern"></a>Patrón

Nueve dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva de DLP está seguro de que ha detectado este tipo de información confidencial al 75% if, dentro de una proximidad de 300 caracteres: la expresión regular Regex_canada_phin busca contenido que coincide con el patrón. Al menos dos palabras clave de Keyword_canada_phin o Keyword_canada_provinces se encuentran..

```
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordcanadaphin"></a>Keyword_canada_phin

- social insurance number
- 
health information act
- 
income tax information
- 
manitoba health
- 
health registration
- 
prescription purchases
- 
benefit eligibility
- 
personal health
- 
power of attorney
- 
registration number
- personal health number
- 
practitioner referral
- 
wellness professional
- 
patient referral
- 

health and wellness

#### <a name="keywordcanadaprovinces"></a>Keyword_canada_provinces

- Nunavut
- 
Quebec
- 
Northwest Territories
- 
Ontario
- 
British Columbia
- 
Alberta
- 
Saskatchewan
- 
Manitoba
- 
Yukon
- 
Newfoundland and Labrador
- 
New Brunswick
- 
Nova Scotia
- 
Prince Edward Island
- Canadá
   
## <a name="canada-social-insurance-number"></a>Número de seguridad social de Canadá

### <a name="format"></a>Formato

Nueve dígitos con guiones opcionales o espacios

### <a name="pattern"></a>Patrón

Con formato:
- Tres dígitos 
- Un guión o un espacio  
- Tres dígitos 
- Un guión o un espacio  
- Tres dígitos

Sin formato: Nueve dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_canadian_sin encuentra contenido que coincide con el patrón.
- Al menos dos de cualquier combinación de lo siguiente:
    - Se encuentra una palabra clave de Keyword_sin.
    - Se encuentra una palabra clave de Keyword_sin_collaborative.
    - La función Func_eu_date encuentra una fecha en el formato de fecha correcto.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_unformatted_canadian_sin encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_sin.
- Se supera la suma de comprobación.

```
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsin"></a>Keyword_sin

- seno 
- social insurance
 
- numero d'assurance sociale
 
- sins
 
- ssn 
- números de seguridad social 
- seguridad social 
- numero d'assurance social
 
- número de identificación nacional 
- 
national id 
- sin#
 
- soc ins
 
- social ins
 

#### <a name="keywordsincollaborative"></a>Keyword_sin_collaborative

- permiso de conducción 
- permiso de conducir 
- permiso de conducir 
- drivers licence 
- DOB
 
- Fecha de nacimiento 
- Cumpleaños  
- Fecha de nacimiento
 
   
## <a name="chile-identity-card-number"></a>Número de tarjeta de identidad de Chile

### <a name="format"></a>Formato

7-8 dígitos y delimitadores un dígito de control o una letra

### <a name="pattern"></a>Patrón

7 u 8 dígitos más delimitadores:
- 1 o 2 dígitos  
- Un punto  
- Tres dígitos 
- Un punto  
- Tres dígitos 
- Un guión  
- Un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_chile_id_card encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_chile_id_card.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_chile_id_card encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordchileidcard"></a>Keyword_chile_id_card

- Número de identificación nacional
 
- tarjeta de identidad 
- ID 
- Identificación 
- Rol Único Nacional
 
- EJECUTAR 
- Rol Único Tributario
 
- RUT
 
- Cédula de Identidad
 
- Número De Identificación Nacional
 
- Tarjeta de identificación
 
- Identificación
 
   
## <a name="china-resident-identity-card-prc-number"></a>	Número de tarjeta de identidad de residente de China (PRC)

### <a name="format"></a>Formato

18 dígitos

### <a name="pattern"></a>Patrón

18 dígitos:
- Seis dígitos que son un código de dirección  
- Ocho dígitos en forma AAAAMMDD que son la fecha de nacimiento  
- Tres dígitos que son un código de pedido  
- Un dígito que es un dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_china_resident_id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_china_resident_id.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_china_resident_id encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

### <a name="keywordchinaresidentid"></a>Keyword_china_resident_id

- Tarjeta de identidad de residente
 
- República Popular China
 
- Tarjeta de identificación nacional
 
- 身份证  
- 居民 身份证  
- 居民身份证
 
- 鉴定

 
- 身分證  
- 居民 身份證
- 鑑定  
   
## <a name="credit-card-number"></a>Número de tarjeta de crédito

### <a name="format"></a>Formato

16 dígitos que se pueden dar formato o sin formato (dddddddddddddddd) y debe pasar la prueba Luhn.

### <a name="pattern"></a>Patrón

Patrón muy complejo y robusto que detecta las tarjetas de todas las principales marcas en todo el mundo, incluidas Visa, MasterCard, tarjeta Discover, JCB, American Express, tarjetas regalo y tarjetas diner.

### <a name="checksum"></a>Suma de comprobación

Sí, la suma de comprobación de Luhn

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_credit_card encuentra contenido que coincide con el patrón.
- Una de las siguientes opciones es verdadera:
    - Se encuentra una palabra clave de Keyword_cc_verification.
    - Se encuentra una palabra clave de Keyword_cc_name.
    - La función Func_expiration_date encuentra una fecha en el formato de fecha correcto.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_credit_card encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordccverification"></a>Keyword_cc_verification

- card verification
- card identification number
- cvn

- cid

- CVC2 obtenidos
- cvv2
- pin block

- security code

- security number

- security no

- issue number

- issue no

- cryptogramme

- numéro de sécurité

- numero de securite

- kreditkartenprüfnummer

- kreditkartenprufnummer

- prüfziffer

- prufziffer

- sicherheits Kode
- sicherheitscode

- sicherheitsnummer

- verfalldatum

- codice di verifica

- cod. sicurezza

- COD sicurezza
- 
n autorizzazione
- código

- codigo

- cod. seg

- COD seg
- código de segurança

- codigo de seguranca

- codigo de segurança

- código de seguranca

- cód. segurança

- Cod. seguranca cod. segurança
- cód. seguranca

- campo Cód. segurança
- bacalao seguranca cod segurança
- campo Cód. seguranca
- número de verificação

- numero de verificacao

- ablauf

- gültig bis

- gültigkeitsdatum

- gultig bis

- gultigkeitsdatum

- scadenza

- data scad

- fecha de expiracion

- fecha de venc

- vencimiento

- válido hasta

- valido hasta

- vto

- data de expiração

- data de expiracao

- data em que expira

- validade

- valor

- vencimento

- Venc 

#### <a name="keywordccname"></a>Keyword_cc_name

- amex
- 
american express
- americanexpress

- Visa
- mastercard

- master card

- 
mc
 
- mastercards
- 
master cards
- Club del comensal
- diners club

- dinersclub

- discover card

- discovercard

- discover cards

- JCB
- japanese card bureau

- carte blanche

- carteblanche

- credit card

- CC #
- cc #:
- 
expiration date
- exp date

- 
expiry date
- 
date d’expiration
- 
date d'exp
- 
date expiration
- bank card

- 
bankcard
- card number

- card num

- cardnumber

- cardnumbers

- card numbers

- creditcard

- credit cards

- creditcards

- ccn

- card holder

- cardholder

- card holders

- cardholders

- check card

- checkcard

- check cards

- checkcards

- debit card

- debitcard

- debit cards

- debitcards

- atm card

- atmcard

- atm cards

- atmcards

- 
enroute
- 
en route
- card type

- carte bancaire

- carte de crédit

- carte de credit

- numéro de carte

- numero de carte

- nº de la carte

- nº de carte

- kreditkarte

- karte

- karteninhaber

- karteninhabers
- kreditkarteninhaber

- kreditkarteninstitut

- kreditkartentyp

- eigentümername

- 
kartennr
 
- kartennummer
- 
kreditkartennummer
- kreditkarten nummer
- carta di credito

- carta credito

- carta
- carta n
- nr. carta

- carta n
- numero carta

- numero della carta

- numero di carta

- tarjeta credito

- tarjeta de credito

- 
tarjeta crédito
- 
tarjeta de crédito
- tarjeta de atm

- tarjeta atm

- tarjeta debito

- tarjeta de debito

- 
tarjeta débito
- 
tarjeta de débito
- nº de tarjeta

- no. de tarjeta

- No hay tarjeta de
- numero de tarjeta

- número de tarjeta

- tarjeta no

- tarjetahabiente

- cartão de crédito

- cartão de credito

- cartao de crédito

- cartao de credito

- cartão de débito

- cartao de débito

- cartão de debito

- cartao de debito

- débito automático
- debito automatico

- 
número do cartão
- 
numero do cartão
 
- número do cartao
- 
numero do cartao
- número de cartão

- numero de cartão

- número de cartao

- numero de cartao

- Nº cartão
- nº do cartao

- nº. do cartão

- No hay cartão
- No hay cartao
- no. do cartão

- 
no. do cartao
 
   
## <a name="croatia-identity-card-number"></a>Número de tarjeta de identidad de Croacia

### <a name="format"></a>Formato

Nueve dígitos

### <a name="pattern"></a>Patrón

Nueve dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_croatia_id_card encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_croatia_id_card.

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordcroatiaidcard"></a>Keyword_croatia_id_card

- Tarjeta de identidad croata
- Osobna iskaznica

   
## <a name="croatia-personal-identification-oib-number"></a>	Número de identificación personal de Croacia (OIB)

### <a name="format"></a>Formato

11 dígitos

### <a name="pattern"></a>Patrón

11 dígitos:
- 10 dígitos 
- Dígito final es un dígito de verificación para los fines de intercambio de datos internacional, las letras recursos humanos se agregan anterior a los once dígitos.

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_croatia_oib_number.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_croatia_oib_number encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordcroatiaoibnumber"></a>Keyword_croatia_oib_number

- Número de identificación personal
- Osobni identifikacijski broj
 
- OIB
 

   
## <a name="czech-personal-identity-number"></a>Número de identidad Personal checo

### <a name="format"></a>Formato

Nueve dígitos con opcional barra diagonal (formato anterior) 10 dígitos con opcional barra diagonal (nuevo formato)

### <a name="pattern"></a>Patrón

Nueve dígitos (formato anterior):
- Nueve dígitos

O bien

- Seis dígitos que representan la fecha de nacimiento
- Una barra diagonal 
- Tres dígitos

(nuevo formato) de 10 dígitos:
- 10 dígitos

O BIEN

- Seis dígitos que representan la fecha de nacimiento
- Una barra diagonal  
- Donde el último dígito es un dígito de verificación de cuatro dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva de DLP es 85% seguro de que ha detectado este tipo de información confidencial if, dentro de una proximidad de 300 caracteres: la función Func_czech_id_card busca contenido que coincide con el patrón. Se ha encontrado una palabra clave de Keyword_czech_id_card. Pasa la suma de comprobación.

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a>Palabras clave

- número de identidad personal checo
- Rodné číslo
   
## <a name="denmark-personal-identification-number"></a>Número de identificación personal de Dinamarca

### <a name="format"></a>Formato

10 dígitos que contienen un guión

### <a name="pattern"></a>Patrón

10 dígitos:
- Seis dígitos en el formato DDMMAA que son la fecha de nacimiento  
- Un guión  
- 4 dígitos en los que el último dígito es un dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva de DLP está seguro de que ha detectado este tipo de información confidencial al 75% if, dentro de una proximidad de 300 caracteres: la expresión regular Regex_denmark_id busca contenido que coincide con el patrón. Se ha encontrado una palabra clave de Keyword_denmark_id. Pasa la suma de comprobación.

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyworddenmarkid"></a>Keyword_denmark_id

- Número de identificación personal
- CPR
- Det Centrale Personregister
- Personnummer
   
## <a name="drug-enforcement-agency-dea-number"></a>Número de la Drug Enforcement Agency (DEA)

### <a name="format"></a>Formato

Dos letras seguidas de siete dígitos

### <a name="pattern"></a>Patrón

El patrón debe incluir todo lo siguiente:
- Una letra (no distingue entre mayúsculas y minúsculas) de este conjunto de letras posibles: abcdefghjklmnprstux, que es un código de inscrito 
- Una letra (no distingue entre mayúsculas y minúsculas), que es la primera letra del apellido del inscrito. 
- Siete dígitos, el último de los cuales es el dígito de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_dea_number encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

Ninguno

   
## <a name="eu-debit-card-number"></a>Tarjeta de débito de la UE

### <a name="format"></a>Formato

16 dígitos

### <a name="pattern"></a>Patrón

Patrón muy complejo y robusto

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_eu_debit_card encuentra contenido que coincide con el patrón.
- Al menos una de las siguientes opciones es verdadera:
    - Se encuentra una palabra clave de Keyword_eu_debit_card.
    - Se encuentra una palabra clave de Keyword_card_terms_dict.
    - Se encuentra una palabra clave de Keyword_card_security_terms_dict.
    - Se encuentra una palabra clave de Keyword_card_expiration_terms_dict.
    - La función Func_expiration_date encuentra una fecha en el formato de fecha correcto.
- Se supera la suma de comprobación.

```
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordeudebitcard"></a>Keyword_eu_debit_card

- número de cuenta 
- card number
 
- card no.
 
- security number
 
- CC # 

#### <a name="keywordcardtermsdict"></a>Keyword_card_terms_dict

- acct nbr
 
- acct num
 
- acct no
 
- american express
 
- americanexpress
 
- americano espresso
 
- amex 
- atm card
 
- atm cards
 
- atm kaart
 
- atmcard
 
- atmcards
 
- atmkaart
 
- atmkaarten
 
- bancontact
 
- bank card
 
- bankkaart
 
- card holder
 
- card holders
 
- card num
 
- card number
 
- card numbers
 
- card type
 
- cardano numerico
 
- cardholder
 
- cardholders
 
- cardnumber
 
- cardnumbers
 
- carta bianca
 
- carta credito
 
- carta di credito
 
- cartao de credito
 
- cartao de crédito
 
- cartao de debito
 
- cartao de débito
 
- carte bancaire
 
- carte blanche
 
- carte bleue
 
- carte de credit
 
- carte de crédit
 
- carte di credito
 
- carteblanche
 
- cartão de credito
 
- cartão de crédito
 
- cartão de debito
 
- cartão de débito
 
- cb
 
- ccn
 
- check card
 
- check cards
 
- checkcard

- checkcards
 
- chequekaart
 
- cirrus
 
- cirrus-edc-maestro
 
- controlekaart
 
- controlekaarten
 
- credit card
 
- credit cards
 
- creditcard
 
- creditcards
 
- debetkaart
 
- debetkaarten
 
- debit card
 
- debit cards
 
- debitcard
 
- debitcards
 
- debito automatico
 
- diners club
 
- dinersclub
 
- descubrir 
- discover card
 
- discover cards
 
- discovercard
 
- discovercards
 
- débito automático
- 
edc
 
- eigentümername
 
- european debit card
 
- hoofdkaart
 
- hoofdkaarten
 
- in viaggio
 
- japanese card bureau
 
- japanse kaartdienst
 
- jcb
 
- kaart
 
- kaart num
 
- kaartaantal
 
- kaartaantallen
 
- kaarthouder
 
- kaarthouders
 
- karte
  
- karteninhaber
 
- karteninhabers
- 
kartennr
 
- kartennummer 
- kreditkarte
 
- kreditkarten nummer 
- kreditkarteninhaber
 
- kreditkarteninstitut
 
- kreditkartennummer
 
- kreditkartentyp
 
- maestro
 
- master card
 
- master cards
 
- mastercard
 
- mastercards 
- MC 
- mister cash
 
- carta n 
- carta 
- No hay tarjeta de 
- No hay cartao 
- No hay cartão 
- no. de tarjeta
 
- no. do cartao
 
- no. do cartão
 
- carta n 
- nr. carta
 
- numeri di scheda
 
- numero carta
 
- numero de cartao
 
- numero de carte
 
- numero de cartão
 
- numero de tarjeta

- numero della carta
 
- numero di carta
 
- numero di scheda
 
- numero do cartao
 
- numero do cartão
 
- numéro de carte
 
- nº carta
 
- nº de carte
 
- nº de la carte
 
- nº de tarjeta
 
- nº do cartao
 
- Nº cartão 
- nº. do cartão
 
- número de cartao
 
- número de cartão
 
- número de tarjeta
 
- número do cartao 
- scheda dell'assegno
 
- scheda dell'atmosfera
 
- scheda dell'atmosfera
 
- scheda della banca
 
- scheda di controllo
 
- scheda di debito
 
- scheda matrice
 
- schede dell'atmosfera
 
- schede di controllo
 
- schede di debito
 
- schede matrici
 
- scoprono la scheda
 
- scoprono le schede
 
- solo
 
- supporti di scheda
 
- supporto di scheda
 
- conmutador 
- tarjeta atm
 
- tarjeta credito
 
- tarjeta de atm
 
- tarjeta de credito
 
- tarjeta de debito
 
- tarjeta debito
 
- tarjeta no

- tarjetahabiente
 
- tipo della scheda
 
- ufficio giapponese della 
- scheda
 
- v pay
 
- v-pago 
- visa
 
- visa plus
 
- visa electron
 
- visto
 
- visum
 
- vpay
   

#### <a name="keywordcardsecuritytermsdict"></a>Keyword_card_security_terms_dict

- card identification number
- card verification 
- cardi la verifica
 
- cid
 
- COD seg 
- COD seguranca 
- COD segurança 
- COD sicurezza 
- cod. seg
 
- cod. seguranca
 
- cod. segurança
 
- cod. sicurezza
 
- codice di sicurezza
 
- codice di verifica
 
- codigo
 
- codigo de seguranca
 
- codigo de segurança
 
- crittogramma
 
- cryptogram
 
- cryptogramme
 
- CV2 
- cvc
 
- CVC2 obtenidos 
- cvn
 
- cvv
 
- cvv2 
- campo Cód. seguranca 
- campo Cód. segurança 
- cód. seguranca
 
- cód. segurança
 
- código
 
- código de seguranca
 
- código de segurança
 
- de kaart controle
 
- geeft nr uit
 
- issue no
 
- issue number
 
- kaartidentificatienummer
 
- kreditkartenprufnummer
 
- kreditkartenprüfnummer
 
- kwestieaantal
 
- no. dell'edizione
 
- no. di sicurezza
 
- numero de securite
 
- numero de verificacao
 
- numero dell'edizione
 
- numero di identificazione della 
- scheda
 
- numero di sicurezza
 
- numero van veiligheid
 
- numéro de sécurité
 
- nº autorizzazione
 
- número de verificação
 
- perno il blocco
 
- pin block
 
- prufziffer
 
- prüfziffer
 
- security code
 
- security no
 
- security number
 
- sicherheits kode
 
- sicherheitscode
 
- sicherheitsnummer
 
- speldblok
 
- veiligheid nr
 
- veiligheidsaantal
 
- veiligheidscode
 
- veiligheidsnummer
 
- verfalldatum
 

#### <a name="keywordcardexpirationtermsdict"></a>Keyword_card_expiration_terms_dict

- ablauf
 
- data de expiracao
 
- data de expiração
 
- data del exp
 
- data di exp
 
- data di scadenza
 
- data em que expira
 
- data scad
 
- data scadenza
 
- date de validité
 
- datum afloop
 
- datum van exp
 
- de afloop
 
- espira
 
- espira
 
- exp date
 
- exp datum
 
- expiración 
- expirar
 
- expires
 
- expiry
 
- fecha de expiracion
 
- fecha de venc
 
- gultig bis
 
- gultigkeitsdatum
 
- gültig bis
 
- gültigkeitsdatum
 
- la scadenza
 
- scadenza
 
- valable
 
- validade
 
- valido hasta
 
- valor
 
- venc
 
- vencimento
 
- vencimiento
 
- verloopt
 
- vervaldag
 
- vervaldatum
 
- vto
 
- válido hasta
 
   
## <a name="eu-drivers-license-number"></a>Número de licencia del controlador de la UE

Para obtener más información, vea el [tipo de información confidencial del número de licencia del controlador de la UE](eu-driver-s-license-number.md).
  
## <a name="eu-national-identification-number"></a>Número de identificación de la UE nacional

Para obtener más información, vea el [tipo de información confidencial del número de identificación nacional de la UE](eu-national-identification-number.md).
  
## <a name="eu-passport-number"></a>Número de cuenta de Passport de la UE

Para obtener más información, vea el [tipo de información confidencial del número de cuenta de Passport de la UE](eu-passport-number.md).
  
## <a name="eu-social-security-number-or-equivalent-id"></a>Identificador de número de seguridad Social de la UE o equivalente

Para obtener más información, vea el [número de seguridad Social de la UE o tipo de información confidencial de identificador equivalente](eu-social-security-number-or-equivalent-id.md).
  
## <a name="eu-tax-identification-number"></a>Número de identificación fiscal de la UE

Para obtener más información, vea el [tipo de información confidencial del número de identificación de impuestos de la UE](eu-tax-identification-number.md).
  
## <a name="finland-national-id"></a>Identificación nacional de Finlandia

### <a name="format"></a>Formato

Seis dígitos y un carácter que indican un siglo, más tres dígitos y un dígito de control

### <a name="pattern"></a>Patrón

El patrón debe incluir todo lo siguiente:
- Seis dígitos en el formato DDMMAA que son una fecha de nacimiento 
- Marcador del siglo (ya sea '-', '+' o 'a') 
- Número de identificación personal de tres dígitos 
- Un dígito o letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_finnish_national_id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_finnish_national_id.
- Se supera la suma de comprobación.

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

- Keyword_finnish_national_id
- 

Sosiaaliturvatunnus
- SOTU Henkilötunnus HETU
- Personbeteckning
- Personnummer
   
## <a name="finland-passport-number"></a>Número de pasaporte de Finlandia

Formato de combinación de nueve letras y dígitos combinación de patrón de nueve letras y dígitos: directiva de dos letras (no entre mayúsculas y minúsculas) siete dígitos DLP de una definición de suma de comprobación No está seguro de que ha detectado este tipo de información confidencial si al 75%, comprendido en un proximidad de 300 caracteres: la expresión regular Regex_finland_passport_number busca contenido que coincide con el patrón. Se ha encontrado una palabra clave de Keyword_finland_passport_number. <!-- Finland Passport Number --> 
 <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern> 
 </Entity> Erta pasiva de Passport de Keyword_finland_passport_number palabras clave
   
## <a name="france-drivers-license-number"></a>Número de licencia de conductor de Francia

### <a name="format"></a>Formato

12 dígitos

### <a name="pattern"></a>Patrón

12 dígitos con validación para descontar patrones similares como los números de teléfono franceses

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_french_drivers_license encuentra contenido que coincide con el patrón.
- Al menos una de las siguientes opciones es verdadera:
- Se encuentra una palabra clave de Keyword_french_drivers_license.
- La función Func_eu_date encuentra una fecha en el formato de fecha correcto.

```
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordfrenchdriverslicense"></a>Keyword_french_drivers_license

- drivers licence
- permiso de conducir
- driving licence

- licencia fuerzas
- 
permis de conduire
- 
licence number
- 
license number
- 
licence numbers
- 

license numbers

## <a name="france-national-id-card-cni"></a>Tarjeta de identificación nacional de Francia (CNI)

### <a name="format"></a>Formato

12 dígitos

### <a name="pattern"></a>Patrón

12 dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_france_cni encuentra contenido que coincide con el patrón.

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

Ninguno
   
## <a name="france-passport-number"></a>Número de pasaporte de Francia

### <a name="format"></a>Formato

Nueve dígitos y letras

### <a name="pattern"></a>Patrón

Nueve dígitos y letras:
- Dos dígitos 
- Dos letras (no distingue entre mayúsculas y minúsculas)  
- Cinco dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_fr_passport encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_passport.

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordpassport"></a>Keyword_passport

- Passport Number
- 
Passport No
- Passport #

- Passport#

- PassportID
- Passportno

- passportnumber

- パスポート
- パスポート番号

- パスポートのNum

- 
パスポート ＃
 
- Numéro de passeport
- 
Passeport n °
- Passeport Non

- Passeport #

- Passeport#

- PasseportNon
- 

Passeportn °

      
## <a name="france-social-security-number-insee"></a>Número de seguridad social de Francia (INSEE)

### <a name="format"></a>Formato

15 dígitos

### <a name="pattern"></a>Patrón

Debe coincidir uno de los dos patrones:
- 13 dígitos seguidos de un espacio seguido de dos dígitos<br/>
o
- 15 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_french_insee o Func_fr_insee busca contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_fr_insee.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_french_insee o Func_fr_insee busca contenido que coincide con el patrón.
- No se encuentra ninguna palabra clave de Keyword_fr_insee.
- Se supera la suma de comprobación.

```
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordfrinsee"></a>Keyword_fr_insee

- insee
- 
securité sociale
- 
securite sociale
- 
national id
- 
national identification
- 
numéro d'identité
- sin FEC ' identité
- 
no. d'identité
- 
numero d'identite
- No hay d'identite
- 
no. d'identite
- social security number

- 
social security code
- social insurance number
- 
le numéro d'identification nationale
- 
d'identité nationale
- 
numéro de sécurité sociale
- 
le code de la sécurité sociale
- 
numéro d'assurance sociale
- 
numéro de sécu
- 
code sécu
 
   
## <a name="german-drivers-license-number"></a>Número de licencia de conductor de Alemania

### <a name="format"></a>Formato

Combinación de 11 dígitos y letras

### <a name="pattern"></a>Patrón

11 dígitos y letras (no distingue entre mayúsculas y minúsculas):
- Un dígito o letra 
- Dos dígitos 
- Seis dígitos o letras 
- Un dígito 
- Un dígito o letra

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_german_drivers_license encuentra contenido que coincide con el patrón.
- Al menos una de las siguientes opciones es verdadera:
    - Se encuentra una palabra clave de Keyword_german_drivers_license_number.
    - Se encuentra una palabra clave de Keyword_german_drivers_license_collaborative.
    - Se encuentra una palabra clave de Keyword_german_drivers_license.
- Se supera la suma de comprobación.

```
<!-- German Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordgermandriverslicensenumber"></a>Keyword_german_drivers_license_number

- Führerschein
- 
Fuhrerschein
- Fuehrerschein
- 
Führerscheinnummer
- 
Fuhrerscheinnummer
- 
Fuehrerscheinnummer
- 
Führerschein-
 
- Fuhrerschein-
 
- Fuehrerschein-
 
- FührerscheinnummerNr
- FuhrerscheinnummerNr
- FuehrerscheinnummerNr
- FührerscheinnummerKlasse
- FuhrerscheinnummerKlasse
- FuehrerscheinnummerKlasse
- Führerschein- Nr

- Fuhrerschein- Nr

- Fuehrerschein- Nr
 
- Führerschein- Klasse
 
- Fuhrerschein- Klasse
 
- Fuehrerschein- Klasse
- FührerscheinnummerNr 
- FuhrerscheinnummerNr 
- FuehrerscheinnummerNr 
- FührerscheinnummerKlasse 
- FuhrerscheinnummerKlasse 
- FuehrerscheinnummerKlasse 
- Führerschein- Nr
 
- Fuhrerschein- Nr
 
- Fuehrerschein- Nr
 
- Führerschein- Klasse
 
- Fuhrerschein- Klasse
 
- Fuehrerschein- Klasse 
- DL 
- DLS
- 
Driv Lic
 
- Driv Licen
 
- Driv License
- 
Driv Licenses
 
- Driv Licence
 
- Driv Licences
 
- Driv Lic
 
- Driver Licen
 
- Licencia de controlador 
- Licencias de controlador 
- Driver Licence
 
- Driver Licences
 
- Lic de controladores 
- Controladores Licen 
- Licencia de controladores 
- Licencias de controladores 
- Licencia de controladores 
- Licencias de controladores 
- Lic del controlador 
- Driver's Licen
 
- De conducir permiso 
- Permisos de conducir 
- Driver's Licence
 
- Driver's Licences
 
- Driving Lic
 
- Driving Licen
 
- Driving License
 
- Driving Licenses
 
- Driving Licence

 
- Driving Licences

#### <a name="keywordgermandriverslicensecollaborative"></a>Keyword_german_drivers_license_collaborative

- 
Nr-Führerschein
 
- Nr-Fuhrerschein
 
- Nr-Fuehrerschein
 
- No-Führerschein
 
- No-Fuhrerschein
 
- No-Fuehrerschein
 
- N-Führerschein
 
- N-Fuhrerschein
 
- N-Fuehrerschein
- 
Nr-Führerschein
 
- Nr-Fuhrerschein
 
- Nr-Fuehrerschein
 
- No-Führerschein
 
- No-Fuhrerschein
 
- No-Fuehrerschein
 
- N-Führerschein
 
- N-Fuhrerschein
 
- N-Fuehrerschein 

#### <a name="keywordgermandriverslicense"></a>Keyword_german_drivers_license

- ausstellungsdatum
- 
ausstellungsort
- 
ausstellende behöde
- 
ausstellende behorde
- 

ausstellende behoerde
   
## <a name="german-passport-number"></a>Número de pasaporte de Alemania

### <a name="format"></a>Formato

10 dígitos o letras

### <a name="pattern"></a>Patrón

El patrón debe incluir todo lo siguiente:
- El primer carácter es un dígito o una letra de este conjunto (C, F, G, H, J, K) 
- Tres dígitos 
- Cinco dígitos o letras de este conjunto (C, -H, J-N, P, R, T, V-Z) 
- Un dígito

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_german_passport encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de cualquiera de las cinco listas de palabras clave.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_german_passport_data encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de cualquiera de las cinco listas de palabras clave.
- Se supera la suma de comprobación.

```
<!-- German Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordgermanpassport"></a>Keyword_german_passport

- reisepass
- 
reisepasse
- 
reisepassnummer
- passport
- 

passports

#### <a name="keywordgermanpassportcollaborative"></a>Keyword_german_passport_collaborative

- geburtsdatum
- ausstellungsdatum
- 
ausstellungsort

#### <a name="keywordgermanpassportnumber"></a>Keyword_german_passport_number

No-Reisepass n-Reisepass

#### <a name="keywordgermanpassport1"></a>Keyword_german_passport1

Reisepass-Nr


#### <a name="keywordgermanpassport2"></a>Keyword_german_passport2

bnationalit.t
   
## <a name="germany-identity-card-number"></a>Número de documento de identidad de Alemania

### <a name="format"></a>Formato

Desde el 1 de noviembre de 2010: nueve letras y dígitos

Desde el 1 de abril de 1987 hasta 31 dígitos de 2010:10 de octubre

### <a name="pattern"></a>Patrón

Desde el 1 de noviembre de 2010:
- Una letra (no distingue entre mayúsculas y minúsculas) 
- Ocho dígitos

Desde el 1 de abril de 1987 hasta el 31 de octubre de 2010:
- 10 dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_germany_id_card encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_germany_id_card.

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordgermanyidcard"></a>Keyword_germany_id_card

- tarjeta de identidad
- ID
- Identificación
- Personalausweis
- Identifizierungsnummer
- Ausweis
- Identifikation
   
## <a name="greece-national-id-card"></a>Tarjeta de identificación nacional de Grecia

### <a name="format"></a>Formato

Combinación de 7 u 8 letras y números más un guión

### <a name="pattern"></a>Patrón

Siete letras y números (formato antiguo):
- Una letra (cualquier letra del alfabeto griego)  
- Un guión  
- Seis dígitos

Ocho letras y números (nuevo formato):
- Dos letras cuyos caracteres en mayúscula se encuentren tanto en el alfabeto griego como latino (ABEZHIKMNOPTYX)  
- Un guión  
- Seis dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_greece_id_card encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_greece_id_card.

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordgreeceidcard"></a>Keyword_greece_id_card

- Tarjeta de identidad griega
- Tautotita
- Δελτίο αστυνομικής ταυτότητας
- Ταυτότητα
   
## <a name="hong-kong-identity-card-hkid-number"></a>Número de tarjeta de identidad de Hong Kong (HKID)

### <a name="format"></a>Formato

Combinación de 8 o 9 letras y números, más paréntesis opcionales alrededor del carácter final

### <a name="pattern"></a>Patrón

Combinación de 8 o 9 letras:
- 1 o 2 letras (no distingue entre mayúsculas y minúsculas)  
- Seis dígitos 
- El último carácter (cualquier dígito o la letra A), que es el dígito de control y, opcionalmente, se incluye entre paréntesis.

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_hong_kong_id_card encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_hong_kong_id_card.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_hong_kong_id_card encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordhongkongidcard"></a>Keyword_hong_kong_id_card

- tarjeta de identidad de Hong kong
- HKIDC
- tarjeta de Id.
- documento de identidad
- tarjeta de identidad HK
- identificador de Hong kong
- 香港身份證

- 香港永久性居民身份證

- 身份證

- 身份証
- 身分證 
- 身分証
- 香港身份証
- 香港身分證
- 香港身分証
- 香港身份證

- 香港居民身份證
- 香港居民身份証
- 香港居民身分證
- 香港居民身分証
- 香港永久性居民身份証
- 香港永久性居民身分證
- 香港永久性居民身分証
- 香港永久性居民身份證

- 香港非永久性居民身份證
- 香港非永久性居民身份証
- 香港非永久性居民身分證
- 香港非永久性居民身分証
- 香港特別行政區永久性居民身份證
- 香港特別行政區永久性居民身份証
- 香港特別行政區永久性居民身分證
- 香港特別行政區永久性居民身分証
- 香港特別行政區非永久性居民身份證
- 香港特別行政區非永久性居民身份証
- 香港特別行政區非永久性居民身分證
- 香港特別行政區非永久性居民身分証
   
## <a name="india-permanent-account-number-pan"></a>Número de cuenta permanente de India (PAN)

### <a name="format"></a>Formato

10 letras o dígitos

### <a name="pattern"></a>Patrón

10 letras o dígitos:
- Cinco letras (no distingue entre mayúsculas y minúsculas)  
- Cuatro dígitos 
- Una letra que es un dígito de control alfabético

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_india_permanent_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_india_permanent_account_number.
- Se supera la suma de comprobación.

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordindiapermanentaccountnumber"></a>Keyword_india_permanent_account_number

- Número de cuenta permanente
 
- PAN
 
   
## <a name="india-unique-identification-aadhaar-number"></a>Número de identificación único (Aadhaar) de la India

### <a name="format"></a>Formato

12 dígitos que contienen espacios o guiones opcionales

### <a name="pattern"></a>Patrón

12 dígitos:
- Cuatro dígitos 
- Un guión o un espacio opcional  
- Cuatro dígitos 
- Un guión o un espacio opcional  
- El dígito final que es el dígito de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva de DLP es 85% seguro de que ha detectado este tipo de información confidencial if, dentro de una proximidad de 300 caracteres: la función Func_india_aadhaar busca contenido que coincide con el patrón. Se ha encontrado una palabra clave de Keyword_india_aadhar. Pasa la suma de comprobación. Una directiva de DLP está seguro de que ha detectado este tipo de información confidencial al 75% if, dentro de una proximidad de 300 caracteres: la función Func_india_aadhaar busca contenido que coincide con el patrón. Pasa la suma de comprobación. <!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity>

### <a name="keywords"></a>Palabras clave
   
#### <a name="keywordindiaaadhar"></a>Keyword_india_aadhar
- Aadhar
- Aadhaar
- UID
- आधार
   
## <a name="indonesia-identity-card-ktp-number"></a>Número de tarjeta de identidad (KTP) de Indonesia

### <a name="format"></a>Formato

16 dígitos que contienen puntos opcionales

### <a name="pattern"></a>Patrón

16 dígitos:
- Código de la provincia de dos dígitos  
- Un punto (opcional)  
- Código de ciudad o regencia de dos dígitos  
- Código de subdistrito de dos dígitos  
- Un punto (opcional)  
- Seis dígitos en el formato DDMMAA que son la fecha de nacimiento  
- Un punto (opcional)  
- Cuatro dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_indonesia_id_card encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_indonesia_id_card.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_indonesia_id_card encuentra contenido que coincide con el patrón.

```
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave
   
#### <a name="keywordindonesiaidcard"></a>Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk
 
- Nomor Induk Kependudukan
 
   
## <a name="international-banking-account-number-iban"></a>Número de cuenta bancaria internacional (IBAN)

### <a name="format"></a>Formato

Código de país (dos letras) más dígitos de control (dos dígitos), más el número IBAN (hasta 30 caracteres)


### <a name="pattern"></a>Patrón

El patrón debe incluir todo lo siguiente:

- Código de país de dos letras
- Dos dígitos de control (seguidos de un espacio opcional)  
- 1-7 grupos de cuatro letras o dígitos (pueden estar separados por espacios)
- 1-3 letras o dígitos

El formato de cada país es ligeramente diferente. El tipo de información confidencial del IBAN cubre estos 60 países:

ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_iban encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

Ninguno

   
## <a name="ip-address"></a>Dirección IP

### <a name="format"></a>Formato

#### <a name="ipv4"></a>IPv4:
Patrón complejo que representa las versiones con formato (con puntos) y sin formato (sin puntos) de las direcciones IPv4

#### <a name="ipv6"></a>IPv6:
 Patrón complejo que representa el formato de números IPv6 (que incluye signos de dos puntos)

### <a name="pattern"></a>Patrón

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Para IPv6, una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_ipv6_address encuentra contenido que coincide con el patrón.
- No se encuentra ninguna palabra clave de Keyword_ipaddress.

Para IPv4, una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_ipv4_address encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_ipaddress.

Para IPv6, una directiva DLP está segura al 95% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_ipv6_address encuentra contenido que coincide con el patrón.
- No se encuentra ninguna palabra clave de Keyword_ipaddress.

```
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordipaddress"></a>Keyword_ipaddress

- IP (esta palabra clave distingue entre mayúsculas y minúsculas)
- dirección IP
 
- Direcciones IP
- internet protocol
- 
IP-כתובת ה
 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a>Clasificación internacional de enfermedades (ICD-10-CM)

### <a name="format"></a>Formato

Diccionario

### <a name="pattern"></a>Patrón

Palabra clave

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- Se ha encontrado una palabra clave de Dictionary_icd_10_cm.

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

Palabras clave

Cualquiera de los términos del diccionario de palabra clave Dictionary_icd_10_cm, que se basa en la [clasificación internacional de enfermedades, revisión décima, modificación ensayos (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). Este tipo sólo busca el término, no los códigos de seguro.

   
## <a name="international-classification-of-diseases-icd-9-cm"></a>Clasificación internacional de enfermedades (ICD-9-CM)

### <a name="format"></a>Formato

Diccionario

### <a name="pattern"></a>Patrón

Palabra clave

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- Se ha encontrado una palabra clave de Dictionary_icd_9_cm.

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palabras clave

Cualquiera de los términos del diccionario de palabra clave Dictionary_icd_9_cm, que se basa en la [clasificación internacional de enfermedades, revisión del noveno, modificación ensayos (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). Este tipo sólo busca el término, no los códigos de seguro.
   
## <a name="ireland-personal-public-service-pps-number"></a>Número de servicio público personal (PPS) de Irlanda

### <a name="format"></a>Formato

Formato antiguo (hasta el 31 de diciembre de 2012):
- Siete dígitos seguidos por 1 o 2 letras  

Nuevo formato (1 de enero de 2013 y posterior):
- Siete dígitos seguidos por dos letras

### <a name="pattern"></a>Patrón

Formato antiguo (hasta el 31 de diciembre de 2012):
- Siete dígitos  
- 1 o 2 letras (no distingue entre mayúsculas y minúsculas)  

Nuevo formato (1 de enero de 2013 y posterior):
- Siete dígitos  
- Una letra (no distingue entre mayúsculas y minúsculas) que es un dígito de control alfabético  
- La letra "A" o "H" (no distingue entre mayúsculas y minúsculas)

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_ireland_pps encuentra contenido que coincide con el patrón.
- Una de las siguientes opciones es verdadera:
    - Se encuentra una palabra clave de Keyword_ireland_pps.
    - La función Func_eu_date encuentra una fecha en el formato de fecha correcto.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_ireland_pps encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordirelandpps"></a>Keyword_ireland_pps

- Número de servicio público personal 
 
- Número de PPS
 
- Núm. PPS
 
- N.º PPS
 
- N.ro PPS
 
- PPS # 
- NPPS
 
- Tarjeta de servicios públicos
 
- Uimhir Phearsanta Seirbhíse Poiblí
 
- Uimh. PSP
 
- PSP
 
   
## <a name="israel-bank-account-number"></a>Número de cuenta bancaria de Israel

### <a name="format"></a>Formato

13 dígitos

### <a name="pattern"></a>Patrón

Con formato:
- Dos dígitos 
- Guion 
- Tres dígitos 
- Guion 
- Ocho dígitos

Sin formato:
- 	13 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_israel_bank_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_israel_bank_account_number.

```
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordisraelbankaccountnumber"></a>Keyword_israel_bank_account_number

- Bank Account Number
 
- Bank Account
 
- Account Number
 
- מספר חשבון בנק
 
   
## <a name="israel-national-id"></a>Identificación nacional de Israel

### <a name="format"></a>Formato

Nueve dígitos

### <a name="pattern"></a>Patrón

Nueve dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_israeli_national_id_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_Israel_National_ID.
- Se supera la suma de comprobación.

```
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordisraelnationalid"></a>Keyword_Israel_National_ID

- מספר זהות
 
- National ID Number
   
## <a name="italy-drivers-license-number"></a>Número de licencia de conductor de Italia

### <a name="format"></a>Formato

Una combinación de 10 letras y dígitos

### <a name="pattern"></a>Patrón

- Una combinación de 10 letras y dígitos:
- Una letra (no distingue entre mayúsculas y minúsculas) 
- La letra "A" o "V" (no distingue entre mayúsculas y minúsculas) 
- Siete letras (no distinguen entre mayúsculas y minúsculas), dígitos o caracteres de subrayado 
- Una letra (no distingue entre mayúsculas y minúsculas)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_italy_drivers_license_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_italy_drivers_license_number.

```
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyworditalydriverslicensenumber"></a>Keyword_italy_drivers_license_number

- numero di patente di guida
 
- patente di guida
 
   
## <a name="japan-bank-account-number"></a>Número de cuenta bancaria de Japón

### <a name="format"></a>Formato

Siete u ocho dígitos

### <a name="pattern"></a>Patrón

Número de cuenta bancaria:
- Siete u ocho dígitos
- Código de sucursal del banco:
- Cuatro dígitos 
- Un espacio o un guion (opcional) 
- Tres dígitos

Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_jp_bank_account encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_jp_bank_account.
- Una de las siguientes opciones es verdadera:
- La función Func_jp_bank_account_branch_code encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_jp_bank_branch_code.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_jp_bank_account encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_jp_bank_account.

```
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordjpbankaccount"></a>Keyword_jp_bank_account

- Checking Account Number
 
- Checking Account
 
- Checking Account #
 
- Checking Acct Number
 
- Checking Acct #
 
- Checking Acct No.
 
- Checking Account No.
 
- Bank Account Number
 
- Bank Account
 
- Bank Account #
 
- Bank Acct Number
 
- Bank Acct #
 
- Bank Acct No.
 
- Bank Account No.
 
- Savings Account Number
 
- Cuenta de ahorro 
- Savings Account #
 
- Savings Acct Number
 
- Savings Acct #
 
- Savings Acct No.
 
- Savings Account No.
 
- Debit Account Number
 
- Debit Account
 
- Debit Account #
 
- Debit Acct Number
 
- Debit Acct #
 
- Debit Acct No.
 
- Debit Account No.
 
- 口座番号を当座預金口座の確認
 
- ＃アカウントの確認、勘定番号の確認
 
- ＃勘定の確認
 
- 勘定番号の確認
 
- 口座番号の確認
 
- 銀行口座番号 
- 銀行口座 
- 銀行口座＃
 
- 銀行の勘定番号
 
- 銀行のacct＃
 
- 銀行の勘定いいえ
 
- 銀行口座番号
- 
普通預金口座番号
 
- 預金口座
 
- 貯蓄口座＃
 
- 貯蓄勘定の数
 
- 貯蓄勘定＃
 
- 貯蓄勘定番号
 
- 普通預金口座番号
 
- 引き落とし口座番号
 
- 口座番号 
- 口座番号＃
 
- デビットのacct番号
 
- デビット勘定＃
 
- デビットACCTの番号
 
- デビット口座番号
 

#### <a name="keywordjpbankbranchcode"></a>Keyword_jp_bank_branch_code

Otemachi

## <a name="japan-drivers-license-number"></a>Número de licencia de conductor de Japón

### <a name="format"></a>Formato

12 dígitos

### <a name="pattern"></a>Patrón

12 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_jp_drivers_license_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_jp_drivers_license_number.

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordjpdriverslicensenumber"></a>Keyword_jp_drivers_license_number

- dl# 
- DL # 
- dls# 
- LISTAS DE DISTRIBUCIÓN # 
- permiso de conducción 
- permisos de conducción 
- permiso de conducir 
- permiso de conducción 
- permisos de conducir 
- permisos de conducción 
- driving licence
 
- lic# 
- LIC # 
- lics# 
- identificador de estado 
- state identification
 
- state identification number
 
- 低所得国＃
 
- 免許証 
- 状態ID
- 
状態の識別
 
- 状態の識別番号
 
- 運転免許 
- 運転免許証 
- 運転免許証番号 
   
## <a name="japan-passport-number"></a>Número de pasaporte de Japón

### <a name="format"></a>Formato

Dos letras seguidas de siete dígitos

### <a name="pattern"></a>Patrón

Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por siete dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_jp_passport encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_jp_passport.

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordjppassport"></a>Keyword_jp_passport

- パスポート
 
- パスポート番号
 
- パスポートのNum
 
- パスポート＃
 
   
## <a name="japan-resident-registration-number"></a>Número de registro de residente de Japón

### <a name="format"></a>Formato

11 dígitos

### <a name="pattern"></a>Patrón

11 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_jp_resident_registration_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_jp_resident_registration_number.

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordjpresidentregistrationnumber"></a>Keyword_jp_resident_registration_number

- Resident Registration Number
- Resident Register Number
 
- Residents Basic Registry Number
 
- Resident Registration No.
 
- Resident Register No.
 
- Residents Basic Registry No.
 
- Basic Resident Register No.
 
- 住民登録番号、登録番号をレジデント
 
- 住民基本登録番号、登録番号
 
- 住民基本レジストリ番号を常駐
 
- 登録番号を常駐住民基本台帳登録番号
 

   
## <a name="japan-social-insurance-number-sin"></a>Número de Seguridad Social de Japón (SIN)

### <a name="format"></a>Formato

De 7 a 12 dígitos

### <a name="pattern"></a>Patrón

7-12 dígitos:
- Cuatro dígitos 
- Un guion (opcional) 
- Seis dígitos o
- De 7 a 12 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_jp_sin encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_jp_sin.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_jp_sin_pre_1997 encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_jp_sin.

```
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordjpsin"></a>Keyword_jp_sin

- Social Insurance No.
 
- Social Insurance Num
 
- Social Insurance Number
 
- 社会保険のテンキー
 
- 社会保険番号
 

## <a name="japanese-residence-card-number"></a>Número de tarjeta de residencia en japonés

### <a name="format"></a>Formato

12 letras y dígitos

### <a name="pattern"></a>Patrón

12 letras y dígitos:
- Dos letras (no distingue entre mayúsculas y minúsculas) 
- Ocho dígitos 
- Dos letras (no distingue entre mayúsculas y minúsculas) 

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_jp_residence_card_number busca contenido que coincide con el patrón.
- Se ha encontrado una palabra clave de Keyword_jp_residence_card_number.

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordjpresidencecardnumber"></a>Keyword_jp_residence_card_number

- Número de tarjeta de residencia
- No de tarjetas de residencia
- Número de la tarjeta de residencia
- 在留カード番号
   
## <a name="malaysia-id-card-number"></a>Número de la tarjeta de identificación de Malasia

### <a name="format"></a>Formato

12 dígitos que contienen guiones opcionales

### <a name="pattern"></a>Patrón

12 dígitos:
- Seis dígitos en el formato DDMMAA que son la fecha de nacimiento  
- Un guión (opcional)  
- Código de dos letras del lugar de nacimiento  
- Un guión (opcional)  
- Tres dígitos aleatorios  
- Código de género de un dígito

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_malaysia_id_card_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_malaysia_id_card_number.

```
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave
   
#### <a name="keywordmalaysiaidcardnumber"></a>Keyword_malaysia_id_card_number

- tarjeta de aplicación digital
- / c
- / c no
- IC
- IC sin
- tarjeta de Id.
- Tarjeta de identificación
- documento de identidad
- k/p
- k/p no
- kad akuan diri
- kad aplikasi digital
- kad pengenalan Malasia
- KP
- KP no
- mykad
- mykas
- mykid
- mypr
- mytentera
- tarjeta de identidad de Malasia
- malasio tarjeta de identidad
- nric
- tarjeta de identificación personal
   
## <a name="netherlands-citizens-service-bsn-number"></a>Número de servicio del ciudadano (BSN) de Países Bajos

### <a name="format"></a>Formato

8 o 9 dígitos que contienen espacios opcionales

### <a name="pattern"></a>Patrón

8 o 9 dígitos:
- Tres dígitos 
- Un espacio (opcional)  
- Tres dígitos 
- Un espacio (opcional)  
- 2 o 3 dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_netherlands_bsn encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_netherlands_bsn.
- La función Func_eu_date2 encuentra una fecha en el formato de fecha correcto.
- Se supera la suma de comprobación.

```
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordnetherlandsbsn"></a>Keyword_netherlands_bsn

- Número de servicio de ciudadanía
 
- BSN

 
- Burgerservicenummer
 
- Sofinummer
 
- Persoonsgebonden nummer
 
- Persoonsnummer
    

   
## <a name="new-zealand-ministry-of-health-number"></a>Número de Ministerio de salud de Nueva Zelanda

### <a name="format"></a>Formato

Tres letras, un espacio (opcional) y cuatro dígitos

### <a name="pattern"></a>Patrón

Tres letras (no distinguir mayúsculas de minúsculas) un cuatro dígitos (opcional) espacio

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_new_zealand_ministry_of_health_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_nz_terms.
- Se supera la suma de comprobación.

```
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

Palabras clave

Keyword_nz_terms

- NHI
 
- Nueva Zelanda 
- Mantenimiento 
- tratamiento
 
   
## <a name="norway-identification-number"></a>Número de identificación de Noruega

### <a name="format"></a>Formato

11 dígitos

### <a name="pattern"></a>Patrón

11 dígitos:
- Seis dígitos en el formato DDMMAA que son la fecha de nacimiento  
- Número individual de tres dígitos  
- Dos dígitos de control

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_norway_id_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_norway_id_number.
- Se supera la suma de comprobación.
- Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_norway_id_numbe encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordnorwayidnumber"></a>Keyword_norway_id_number

- Número de identificación personal
- Número de id. noruego
- Número de id.
- Identificación
- Personnummer
- Fødselsnummer

   
## <a name="philippines-unified-multi-purpose-id-number"></a>Número de id. universal unificado de Filipinas

### <a name="format"></a>Formato

12 dígitos separados por guiones

### <a name="pattern"></a>Patrón

12 dígitos:
- Cuatro dígitos 
- Un guión  
- Siete dígitos  
- Un guión  
- Un dígito

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_philippines_unified_id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_philippines_id.

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave
   
#### <a name="keywordphilippinesid"></a>Keyword_philippines_id

- Id. universal unificado
 
- UMID
 
- tarjeta de identidad 
- Pinag-isang Multi-Layunin ID
   
## <a name="poland-identity-card"></a>Tarjeta de identificación de Polonia

### <a name="format"></a>Formato

Tres letras y seis dígitos

### <a name="pattern"></a>Patrón

Tres letras (no distingue entre mayúsculas y minúsculas) seguidas por seis dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva de DLP está seguro de que ha detectado este tipo de información confidencial al 75% if, dentro de una proximidad de 300 caracteres: la función Func_polish_national_id busca contenido que coincide con el patrón. Se ha encontrado una palabra clave de Keyword_polish_national_id_passport_number. Pasa la suma de comprobación.

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordpolishnationalidpassportnumber"></a>Keyword_polish_national_id_passport_number

- Dowód osobisty
- Número dowodu osobistego
- Nazwa número dowodu osobistego
- Nazwa nr dowodu osobistego
- Nazwa i nr dowodu tożsamości

- Dowód Tożsamości

- dow. os.


   
## <a name="poland-national-id-pesel"></a>Identificación nacional de Polonia (PESEL)

### <a name="format"></a>Formato

11 dígitos

### <a name="pattern"></a>Patrón

11 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_pesel_identification_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_pesel_identification_number.
- Se supera la suma de comprobación.

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordpeselidentificationnumber"></a>Keyword_pesel_identification_number

- Nr PESEL
- PESEL   

   
## <a name="poland-passport"></a>Pasaporte de Polonia

### <a name="format"></a>Formato

Dos letras y siete dígitos

### <a name="pattern"></a>Patrón

Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por siete dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_polish_passport_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_polish_national_id_passport_number.
- Se supera la suma de comprobación.

```
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordpolishnationalidpassportnumber"></a>Keyword_polish_national_id_passport_number

- Número paszportu
- Paszportu nr.
- Paszport

   
## <a name="portugal-citizen-card-number"></a>Número de tarjeta del ciudadano de Portugal

### <a name="format"></a>Formato

Ocho dígitos

### <a name="pattern"></a>Patrón

Ocho dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_portugal_citizen_card encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_portugal_citizen_card.

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordportugalcitizencard"></a>Keyword_portugal_citizen_card

- Tarjeta del ciudadano
- Tarjeta de id. nacional
- CC
- Cartão de Cidadão
- Bilhete de Identidade
   
## <a name="saudi-arabia-national-id"></a>Identificación nacional de Arabia Saudí

### <a name="format"></a>Formato

10 dígitos

### <a name="pattern"></a>Patrón

10 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_saudi_arabia_national_id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_saudi_arabia_national_id.

```
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordsaudiarabianationalid"></a>Keyword_saudi_arabia_national_id

- Identification Card
 
- I card number
 
- número de Id. 
- الوطنية الهوية بطاقة رقم
 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a>Número de tarjeta de identidad de registro nacional (NRIC) de Singapur

### <a name="format"></a>Formato

Nueve letras y dígitos

### <a name="pattern"></a>Patrón

- Nueve letras y dígitos:
- La letra "F", "G", "S", o "T" (no distingue entre mayúsculas y minúsculas)  
- Siete dígitos  
- Un dígito de control alfabético

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_singapore_nric encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_singapore_nric.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_singapore_nric encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave
   
#### <a name="keywordsingaporenric"></a>Keyword_singapore_nric

- Tarjeta de identidad de registro nacional
 
- Número de tarjeta de identidad
 
- NRIC
 
- IC
 
- Número de identificación de extranjeros
 
- FIN
 
- 身份证  
- 身份證
 
   
## <a name="south-africa-identification-number"></a>Número de identificación de Sudáfrica

### <a name="format"></a>Formato

13 dígitos que pueden contener espacios

### <a name="pattern"></a>Patrón

13 dígitos:
- Seis dígitos en el formato DDMMAA que son la fecha de nacimiento  
- Cuatro dígitos 
- Un indicador de ciudadanía de un solo dígito  
- El dígito "8" o "9"  
- Un dígito que es un dígito de suma de comprobación

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_south_africa_identification_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_south_africa_identification_number.
- Se supera la suma de comprobación.

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave
   
#### <a name="keywordsouthafricaidentificationnumber"></a>Keyword_south_africa_identification_number

- tarjeta de identidad
- ID
- Identificación 
   
## <a name="south-korea-resident-registration-number"></a>Número de registro de residente de Corea del Sur

### <a name="format"></a>Formato

13 dígitos que contienen un guión

### <a name="pattern"></a>Patrón

13 dígitos:
- Seis dígitos en el formato DDMMAA que son la fecha de nacimiento  
- Un guión  
- Un dígito determinado por el siglo y el sexo  
- Código de región de nacimiento de cuatro dígitos  
- Un dígito que se usa para diferenciar a las personas para las cuales los números anteriores son idénticos  
- Un dígito de control.

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_south_korea_resident_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_south_korea_resident_number.
- Se supera la suma de comprobación.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_south_korea_resident_number encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave
   
#### <a name="keywordsouthkorearesidentnumber"></a>Keyword_south_korea_resident_number

- Tarjeta de id. nacional
 
- Número de registro de ciudadano
 
- Jumin deungnok beonho
 
- RRN
 
- 주민등록번호
   
## <a name="spain-social-security-number-ssn"></a>Número de seguridad social de España (NSS)

### <a name="format"></a>Formato

11 o 12 dígitos

### <a name="pattern"></a>Patrón

12 de 11 dígitos:
- Dos dígitos 
- Una barra diagonal (opcional) 
- 7-8 dígitos 
- Una barra diagonal (opcional) 
- Dos dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_spanish_social_security_number encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

Ninguno
   
## <a name="sweden-national-id"></a>Identificación nacional de Suecia

### <a name="format"></a>Formato

10 o 12 dígitos y un delimitador opcional

### <a name="pattern"></a>Patrón

10 o 12 dígitos y un delimitador opcional:
- 2-4 dígitos (opcionales) 
- Seis dígitos en fecha de formato AAMMDD 
- Delimitador de "-" o "+" (opcional), más
- Cuatro dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_swedish_national_identifier encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

No
   
## <a name="sweden-passport-number"></a>Número de pasaporte de Suecia

### <a name="format"></a>Formato

Ocho dígitos

### <a name="pattern"></a>Patrón

Ocho dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_sweden_passport_number encuentra contenido que coincide con el patrón.
- Una de las siguientes opciones es verdadera:
    - Se encuentra una palabra clave de Keyword_passport.
    - Se encuentra una palabra clave de Keyword_sweden_passport.

```
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave
   
#### <a name="keywordswedenpassport"></a>Keyword_sweden_passport

- visa requirements
 
- Alien Registration Card
 
- Schengen visas
 
- Schengen visa
 
- Visa Processing
 
- Visa Type
 
- Single Entry
 
- Multiple Entry
 
- G3 Processing Fees

 

#### <a name="keywordpassport"></a>Keyword_passport

- Passport Number 
- 
Passport No 
- Passport #
 
- Passport#
 
- PassportID 
- Passportno
 
- passportnumber
 
- パスポート 
- パスポート番号
 
- パスポートのNum
 
- パスポート＃
 
- Numéro de passeport 
- 
Passeport n ° 
- Passeport Non
 
- Passeport #
 
- Passeport#
 
- PasseportNon 
- Passeportn °
 
   
## <a name="swift-code"></a>Código SWIFT

### <a name="format"></a>Formato

Cuatro letras seguidas de 5 a 31 letras o dígitos

### <a name="pattern"></a>Patrón

Cuatro letras seguidas de 5-31 letras o dígitos:
- Código del banco de cuatro letras (no distingue entre mayúsculas y minúsculas) 
- Un espacio opcional 
- 4-28 letras o dígitos (el número básico de cuenta bancaria (BBAN)) 
- Un espacio opcional 
- 1-3 letras o dígitos (el resto del BBAN)

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_swift encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_swift.

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave
   
#### <a name="keywordswift"></a>Keyword_swift

- international organization for standardization 9362
 
- iso 9362
 
- iso9362 
- SWIFT\# 
- swiftcode
 
- swiftnumber
 
- swiftroutingnumber
 
- código SWIFT 
- swift number #
 
- swift routing number
 
- bic number
 
- bic code
 
- BIC\# 
- BIC\# 
- bank identifier code
 
- 標準化9362 
- 迅速＃
 
- SWIFTコード
 
- SWIFT番号
 
- 迅速なルーティング番号
 
- BIC番号
 
- BICコード
 
- 銀行識別コードのための国際組織
 
- Organisation internationale de normalisation 9362
 
- rapide\# 
- code SWIFT
 
- le numéro de swift
 
- swift numéro d'acheminement
 
- le numéro BIC
 
- \#BIC 
- code identificateur de banque
 
   
## <a name="taiwan-national-id"></a>Identificación nacional de Taiwán

### <a name="format"></a>Formato

Una letra  seguida de nueve dígitos

### <a name="pattern"></a>Patrón

Una letra seguida de nueve dígitos:
- Una letra (en inglés, no distingue mayúsculas de minúsculas) 
- El dígito "1" o "2" 
- Ocho dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_taiwanese_national_id encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_taiwanese_national_id.
- Se supera la suma de comprobación.

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordtaiwanesenationalid"></a>Keyword_taiwanese_national_id

- 身份證字號
 
- 身份證
 
- 身份證號碼
 
- 身份證號
 
- 身分證字號
 
- 身分證  
- 身分證號碼
 
- 身份證號
 
- 身分證統一編號
 
- 國民身分證統一編號
 
- 簽名
 
- 蓋章
 
- 簽名或蓋章

 
- 簽章   
   
## <a name="taiwan-passport-number"></a>Número de pasaporte de Taiwán

### <a name="format"></a>Formato

- Número de pasaporte biométrica: nueve dígitos
- Número de cuenta de passport no biométrica: nueve dígitos

### <a name="pattern"></a>Patrón
Número de cuenta de passport biométrica:
- El dígito "3"  
- Ocho dígitos

Número de cuenta de passport no biométrica:
- Nueve dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_taiwan_passport encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_taiwan_passport.

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordtaiwanpassport"></a>Keyword_taiwan_passport

- Número de pasaporte ROC
 
- Número de cuenta de Passport 
- Cuenta de Passport no 
- N.ro pasaporte
 
- Passport #
 
- 护照
 
- 中華民國護照
 
- Zhōnghuá Mínguó hùzhào
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>Número de certificado de residente (ARC/TARC) de Taiwán

### <a name="format"></a>Formato

10 letras y dígitos

### <a name="pattern"></a>Patrón

10 letras y dígitos:
- Dos letras (no distingue entre mayúsculas y minúsculas)  
- Ocho dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_taiwan_resident_certificate encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_taiwan_resident_certificate.

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordtaiwanresidentcertificate"></a>Keyword_taiwan_resident_certificate

- Certificado de residente
 
- Cert residente 
- Cert. residente
 
- Tarjeta de identificación 
- Certificado de residente extranjero
 
- ARC
 
- Certificado de residente en el área de Taiwán
 
- TARC
 
- 居留證
 
- 外僑居留證
 
- 台灣地區居留證
 

## <a name="thai-population-identification-code"></a>Código de identificación de población tailandés

### <a name="format"></a>Formato

13 dígitos

### <a name="pattern"></a>Patrón

13 dígitos:
- Primer dígito no es 0 o 9 
- 12 dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_Thai_Citizen_Id busca contenido que coincide con el patrón.
- Se ha encontrado una palabra clave de Keyword_Thai_Citizen_Id.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_Thai_Citizen_Id busca contenido que coincide con el patrón.

```
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordthaicitizenid"></a>Keyword_Thai_Citizen_Id

- Número de id.
- Número de identificación
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน
  
## <a name="turkish-national-identification-number"></a>Número de identificación nacional turco

### <a name="format"></a>Formato

11 dígitos

### <a name="pattern"></a>Patrón

11 dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_Turkish_National_Id busca contenido que coincide con el patrón.
- Se ha encontrado una palabra clave de Keyword_Turkish_National_Id.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_Turkish_National_Id busca contenido que coincide con el patrón.

```
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordturkishnationalid"></a>Keyword_Turkish_National_Id

- TC Kimlik n
- Numarası Kimlik TC
- Vatandaşlık numarası
- Vatandaşlık no

## <a name="uk-drivers-license-number"></a>Número de licencia de conductor de Reino Unido

### <a name="format"></a>Formato

Combinación de 18 letras y dígitos en el formato especificado

### <a name="pattern"></a>Patrón

18 letras y dígitos:
- Cinco letras (no distinguen entre mayúsculas y minúsculas) o el dígito "9" en lugar de una letra 
- Un dígito 
- Cinco dígitos en el formato de fecha DDMMA para la fecha de nacimiento 
- Dos letras (no distinguen entre mayúsculas y minúsculas) o el dígito "9" en lugar de una letra 
- Cinco dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_uk_drivers_license encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_uk_drivers_license.
- Se supera la suma de comprobación.

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordukdriverslicense"></a>Keyword_uk_drivers_license

- DVLA
 
- light vans
 
- quadbikes
 
- motor cars
 
- 125CC 
- sidecar
 
- tricycles
 
- motorcycles
 
- photocard licence
 
- learner drivers
 
- licence holder
 
- licence holders
 
- driving licences
 
- driving licence
 
- dual control car
 
   
## <a name="uk-electoral-roll-number"></a>Número de registro electoral de Reino Unido

### <a name="format"></a>Formato

Dos letras seguidas por entre 1 y 4 dígitos

### <a name="pattern"></a>Patrón

Dos letras (no distingue entre mayúsculas y minúsculas) seguidas por entre 1 y 4 números

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_uk_electoral encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_uk_electoral.

```
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordukelectoral"></a>Keyword_uk_electoral

- council nomination
 
- nomination form
 
- electoral register

 
- electoral roll

   
## <a name="uk-national-health-service-number"></a>Número de Servicio Nacional de Salud de Reino Unido

### <a name="format"></a>Formato

De 10 a 17 dígitos separados por espacios

### <a name="pattern"></a>Patrón

10-17 dígitos:
- 3 o 10 dígitos 
- Un espacio 
- Tres dígitos 
- Un espacio 
- Cuatro dígitos

### <a name="checksum"></a>Suma de comprobación

Sí

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_uk_nhs_number encuentra contenido que coincide con el patrón.
- Una de las siguientes opciones es verdadera:
    - Se encuentra una palabra clave de Keyword_uk_nhs_number.
    - Se encuentra una palabra clave de Keyword_uk_nhs_number1.
    - Se encuentra una palabra clave de Keyword_uk_nhs_number_dob.
- Se supera la suma de comprobación.

```
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave
   
#### <a name="keyworduknhsnumber"></a>Keyword_uk_nhs_number

- national health service
 
- nhs
 
- health services authority

 
- health authority

#### <a name="keyworduknhsnumber1"></a>Keyword_uk_nhs_number1

- patient id
 
- patient identification
 
- patient no

 
- patient number

#### <a name="keyworduknhsnumberdob"></a>Keyword_uk_nhs_number_dob

- DG 
- DOB
 
- D.O.B 
- Fecha de nacimiento
 
- Fecha de nacimiento
 
   
## <a name="uk-national-insurance-number-nino"></a>Número de seguro nacional de Reino Unido (NINO)

### <a name="format"></a>Formato

los 7 caracteres o 9 separadas por espacios o guiones

### <a name="pattern"></a>Patrón

Dos modelos posibles:

- Dos letras (NINOs válidos utilizar sólo determinados caracteres en este prefijo, que valida este patrón; no mayúsculas de minúsculas)
- Seis dígitos
- Puede ser 'A', 'B', 'C', o tenía ' (como el prefijo, sólo ciertos caracteres se permiten en el sufijo; no distingue mayúsculas de minúsculas)

O BIEN

- Dos letras
- Un espacio o un guion
- Dos dígitos
- Un espacio o un guion
- Dos dígitos
- Un espacio o un guion
- Dos dígitos
- Un espacio o un guion
- Puede ser 'A', 'B', 'C', o tenía '

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_uk_nino encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_uk_nino.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_uk_nino encuentra contenido que coincide con el patrón.
- No se encuentra ninguna palabra clave de Keyword_uk_nino.

```
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyworduknino"></a>Keyword_uk_nino

- national insurance number
 
- national insurance contributions
 
- protection act
 
- insurance
 
- social security number
 
- insurance application
 
- medical application
 
- social insurance
 
- medical attention
 
- seguridad social 
- great britain
 
- insurance
    
   
## <a name="us--uk-passport-number"></a>Número de pasaporte EE. UU. / Reino Unido

### <a name="format"></a>Formato

Nueve dígitos

### <a name="pattern"></a>Patrón

Nueve dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_usa_uk_passport encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_passport.

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordpassport"></a>Keyword_passport

- Passport Number 
- 
Passport No 
- Passport #
 
- Passport#
 
- PassportID 
- Passportno
 
- passportnumber
 
- パスポート 
- パスポート番号
 
- パスポートのNum
 
- パスポート＃
 
- Numéro de passeport 
- 
Passeport n ° 
- Passeport Non
 
- Passeport #
 
- Passeport#
 
- PasseportNon 
- Passeportn °
 
   
## <a name="us-bank-account-number"></a>Número de cuenta bancaria de EE. UU.

### <a name="format"></a>Formato

Entre 8 y 17 dígitos

### <a name="pattern"></a>Patrón

Entre 8 y 17 dígitos consecutivos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La expresión regular Regex_usa_bank_account_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_usa_Bank_Account.

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordusabankaccount"></a>Keyword_usa_Bank_Account

- Checking Account Number
 
- Checking Account
 
- Checking Account #
 
- Checking Acct Number
 
- Checking Acct #
 
- Checking Acct No.
 
- Checking Account No.
 
- Bank Account Number
 
- Bank Account #
 
- Bank Acct Number
 
- Bank Acct #
 
- Bank Acct No.
 
- Bank Account No.
 
- Savings Account Number
 
- Savings Account.
 
- Savings Account #
 
- Savings Acct Number
 
- Savings Acct #
 
- Savings Acct No.
 
- Savings Account No.
 
- Debit Account Number
 
- Debit Account
 
- Debit Account #
 
- Debit Acct Number
 
- Debit Acct #
 
- Debit Acct No.
 
- Debit Account No.
 
   
## <a name="us-drivers-license-number"></a>Número de licencia de conductor de EE. UU.

### <a name="format"></a>Formato

Depende del estado

### <a name="pattern"></a>Patrón

Depende del estado, por ejemplo, Nueva York:
- Nueve dígitos como ddd ddd ddd coinciden con el formato.
- Nueve dígitos como ddddddddd no coinciden con el formato.

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_new_york_drivers_license_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_[state_name]_drivers_license_name.
- Se encuentra una palabra clave de Keyword_us_drivers_license.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_new_york_drivers_license_number encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_[state_name]_drivers_license_name.
- Se encuentra una palabra clave de Keyword_us_drivers_license_abbreviations.
- No se encuentra ninguna palabra clave de Keyword_us_drivers_license.

```
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordusdriverslicenseabbreviations"></a>Keyword_us_drivers_license_abbreviations

- DL 
- DLS 
- CDL 
- CDLS 
- ID 
- Identificadores de 
- DL# 
- 
DLS#
 
- CDL#
 
- CDLS#
 
- ID#
- 
IDs#
 
- número de Id. 
- ID numbers
 
- LIC 
- LIC#
 

#### <a name="keywordusdriverslicense"></a>Keyword_us_drivers_license

- DriverLic 
- DriverLics 
- DriverLicense 
- DriverLicenses 
- Lic de controlador 
- LIC de controlador 
- Licencia de controlador 
- Licencias de controlador 
- DriversLic 
- DriversLics 
- PermisoDeConducción 
- DriversLicenses 
- Lic de controladores 
- LIC de controladores 
- Licencia de controladores 
- Licencias de controladores 
- Driver'Lic 
- Driver'Lics 
- Driver'License 
- Driver'Licenses 
- Controlador ' Lic 
- Controlador ' LIC 
- Controlador ' licencia 
- Controlador ' licencias
- Driver'sLic 
- Driver'sLics 
- Driver'sLicense 
- Driver'sLicenses 
- Lic del controlador 
- LIC del controlador 
- De conducir permiso 
- Permisos de conducir 
- identification number
 
- identification numbers
 
- identification #
 
- tarjeta de Id. 
- identificador de tarjetas 
- tarjeta de identificación 
- tarjetas de identificación 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- Driver Lic# 
- 
Driver Lics#
 
- Controlador licencia # 
- Controlador licencias # 
- DriversLic # 
- DriversLics # 
- PermisoDeConducción # 
- DriversLicenses # 
- Controladores Lic # 
- Controladores LIC # 
- Licencia de controladores # 
- Licencias de controladores # 
- Driver'Lic#
 
- Driver'Lics#
 
- Driver'License#
 
- Driver'Licenses#
 
- Driver' Lic#
 
- Driver' Lics#
 
- Driver' License#
 
- Driver' Licenses#
 
- Driver'sLic # 
- Driver'sLics # 
- Driver'sLicense # 
- Driver'sLicenses # 
- Driver's Lic#
 
- Driver's Lics#
 
- Driver's License#
 
- Driver's Licenses#
 
- tarjeta de identificación # 
- id cards#
 
- identification card#
 
- identification cards#
 


#### <a name="keywordstatenamedriverslicensename"></a>Keyword_[state_name]_drivers_license_name

- Abreviatura del estado (por ejemplo, "NY")
 
- Nombre del estado (por ejemplo, "New York")
    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a>Número de identificación de contribuyente individual (ITIN) de EE. UU.

### <a name="format"></a>Formato

Nueve dígitos que empiezan con un "9" y contienen un "7" u "8" como cuarto dígito; se puede optar por un formato con espacios o guiones

### <a name="pattern"></a>Patrón

Con formato:
- El dígito "9" 
- Dos dígitos 
- Un espacio o un guion 
- Un "7" o "8" 
- Un dígito 
- Un espacio o un guion 
- Cuatro dígitos

Sin formato:
- El dígito "9" 
- Dos dígitos 
- Un "7" o "8" 
- Cinco dígitos

### <a name="checksum"></a>Suma de comprobación

No

### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_formatted_itin encuentra contenido que coincide con el patrón.
- Al menos una de las siguientes opciones es verdadera:
    - Se encuentra una palabra clave de Keyword_itin.
    - La función Func_us_address encuentra una dirección en el formato de fecha correcto.
    - La función Func_us_date encuentra una fecha en el formato de fecha correcto.
    - Se encuentra una palabra clave de Keyword_itin_collaborative.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_unformatted_itin encuentra contenido que coincide con el patrón.
- Al menos una de las siguientes opciones es verdadera:
    - Se encuentra una palabra clave de Keyword_itin_collaborative.
    - La función Func_us_address encuentra una dirección en el formato de fecha correcto.
    - La función Func_us_date encuentra una fecha en el formato de fecha correcto.

```
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keyworditin"></a>Keyword_itin

- taxpayer
 
- tax id
 
- tax identification
 
- itin
 
- ssn 
- tin
 
- seguridad social 
- tax payer
 
- itins
 
- taxid

 
- individual taxpayer
 

#### <a name="keyworditincollaborative"></a>Keyword_itin_collaborative

- License 
- DL 
- DOB
 
- Fecha de nacimiento 
- Cumpleaños  
- Fecha de nacimiento
 
   
## <a name="us-social-security-number-ssn"></a>Número de seguridad social (SSN) de EE. UU.

### <a name="format"></a>Formato

9 dígitos, que pueden ser un patrón con o sin formato

> [!NOTE]
> Si se ha emitido antes de mediados de 2011, el SSN tiene un formato seguro en aquellas partes del número que deben incluirse dentro de ciertos rangos para que sean válidas (pero no hay ninguna suma de comprobación).

### <a name="pattern"></a>Patrón

Cuatro funciones buscan SSN en cuatro patrones diferentes:
- Func_ssn busca SSN con formato seguro anteriores a 2011 y formateados con guiones o espacios (ddd-dd-dddd O ddd dd dddd)
- Func_unformatted_ssn busca SSN con formato seguro anteriores a 2011 y formateados de manera no específica como nueve dígitos consecutivos (ddddddddd)
- Func_randomized_formatted_ssn busca SSN posteriores a 2011 y formateados con guiones o espacios (ddd-dd-dddd O ddd dd dddd)
- Func_randomized_unformatted_ssn busca SSN posteriores a 2011 y formateados de manera no específica como nueve dígitos consecutivos (ddddddddd)

### <a name="checksum"></a>Suma de comprobación

No


### <a name="definition"></a>Definición

Una directiva DLP está segura al 85% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_ssn encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_ssn.

Una directiva DLP está segura al 75% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_unformatted_ssn busca contenido que coincida con el patrón.
- Se encuentra una palabra clave de Keyword_ssn.

Una directiva DLP está segura al 65% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_randomized_formatted_ssn encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_ssn.
- La función Func_ssn no encuentra contenido que coincide con el patrón.

Una directiva DLP está segura al 55% de que este tipo de información confidencial se detecta si, en una proximidad de 300 caracteres:
- La función Func_randomized_unformatted_ssn encuentra contenido que coincide con el patrón.
- Se encuentra una palabra clave de Keyword_ssn.
- La función Func_unformatted_ssn no encuentra contenido que coincide con el patrón.

```
<!-- U.S. Social Security Number (SSN) -->
    <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_ssn" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palabras clave

#### <a name="keywordssn"></a>Keyword_ssn

- Social Security
 
- Social Security#
 
- Soc Sec
 
- SSN 
- SSNS
 
- SSN#
 
- SS#
 
- SSID
 
   

