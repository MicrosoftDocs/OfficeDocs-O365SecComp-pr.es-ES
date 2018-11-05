---
title: Creación de un tipo personalizado de información confidencial
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Obtenga información sobre cómo crear, modificar, quitar y probar tipos personalizados de información confidencial para DLP en la interfaz gráfica de usuario del Centro de seguridad y cumplimiento de Office 365.
ms.openlocfilehash: cd7041ee9c20038fb7cb0c337f31d7cef7f7192d
ms.sourcegitcommit: ceb70ea863d8b97afea077a04fc7ec612b870695
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "25857298"
---
# <a name="create-a-custom-sensitive-information-type"></a>Crear un tipo personalizado de información confidencial

La función Prevención de pérdida de datos (DLP) de Office 365 incluye distintos [tipos de información confidencial](what-the-sensitive-information-types-look-for.md) preparados para usarlos en directivas DLP. Estos tipos integrados pueden ayudarle a identificar y proteger números de tarjetas de crédito, cuentas bancarias, pasaportes y mucho más. 

Pero, si necesita identificar y proteger otro tipo de información confidencial, como el id. de empleado o números de proyecto que usen un formato específico para su organización, puede crear un tipo personalizado de información confidencial.

Estas son las partes básicas de un tipo personalizado de información confidencial:

- **Patrón principal**: números de id. de empleado, números de proyecto, etc. Suele identificarse mediante una expresión regular (regex), pero también puede ser una lista de palabras clave.

- **Evidencia adicional**: imagine que busca un número de id. de empleado de nueve dígitos. No todos los números de nueve dígitos son números de id. de empleado, pero puede buscar texto adicional (palabras clave como “empleado”, “identificación” o “id.”, o bien otros patrones de texto basados en expresiones regulares). Esta evidencia complementaria (también conocida como _evidencia_ _corroborativa_) incrementa la probabilidad de que el número de nueve dígitos encontrado en el contenido sea realmente un número de id. de empleado.

- **Proximidad de caracteres**: tiene sentido que, cuanto más próximos estén entre sí el patrón principal y la evidencia complementaria, más probabilidades habrá de que el contenido detectado sea lo que busca. Puede especificar la distancia de caracteres entre el patrón principal y la evidencia complementaria (también conocida como _ventana de proximidad_), como se muestra en el diagrama siguiente:

    ![Diagrama de evidencia corroborativa y ventana de proximidad](media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- **Nivel de confianza**: cuantas más evidencias complementarias tenga, mayor será la probabilidad de que una coincidencia contenga la información confidencial que busca. Puede asignar mayores niveles de confianza a las coincidencias detectadas mediante el uso de más evidencias.

  Cuando esté conforme, un patrón devolverá un recuento y un nivel de confianza, que podrá usar en las condiciones de las directivas DLP. Al agregar a una directiva DLP una condición para detectar un tipo de información confidencial, puede editar el recuento y el nivel de confianza, como se muestra en el diagrama siguiente:

    ![Opciones de precisión de coincidencia y recuento de instancias](media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

Para crear tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento de Office 365, use una de estas opciones:

- **Interfaz de usuario**: este método es más sencillo y rápido, pero tiene menos opciones de configuración que si usa PowerShell. En el resto de este tema, se describen estos procedimientos.

- **PowerShell**: para usar este método, primero tiene que crear un archivo XML (denominado _paquete de reglas_) que contiene uno o más tipos de información confidencial y, después, usará PowerShell para importar el paquete de reglas (importar el paquete de reglas es complicado en comparación con la creación del paquete de reglas). Este método es mucho más complejo que si se usa la interfaz de usuario, pero ofrece más opciones de configuración. Para obtener instrucciones, vea [Crear un tipo personalizado de información confidencial en PowerShell del Centro de seguridad y cumplimiento de Office 365](create-a-custom-sensitive-information-type-in-scc-powershell.md).

En la tabla siguiente, se describen las principales diferencias:

|Tipos personalizados de información confidencial en la interfaz de usuario|Tipos personalizados de información confidencial en PowerShell|
|:-----|:-----|
|El nombre y la descripción están en un idioma.|Admite varios idiomas para Nombre y Descripción.|
|Admite un patrón (el patrón principal).|Admite varios patrones, además del patrón principal.|
|Las evidencias complementarias pueden ser: <br/>• Expresiones regulares <br/>• Palabras clave <br/>• Diccionarios de palabras clave|Las evidencias complementarias pueden ser: <br/>• Expresiones regulares <br/>• Palabras clave <br/>• Diccionarios de palabras clave <br/>• [Funciones de DLP integradas](what-the-dlp-functions-look-for.md)|
|El nivel de confianza se puede configurar para el tipo de información confidencial.|El nivel de confianza se puede configurar para el tipo de información confidencial y cada patrón individual que contenga.|
|La coincidencia de patrones necesita la detección del patrón principal y todas las evidencias complementarias (se usa el operador AND implícito).|La coincidencia de patrones necesita la detección del patrón principal y una cantidad configurable de evidencias complementarias (pueden usarse los operadores AND y OR implícitos).|

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Para abrir el Centro de seguridad y cumplimiento, vea [Ir al Centro de seguridad y cumplimiento de Office 365](go-to-the-securitycompliance-center.md).

- Para usar los tipos personalizados de información confidencial, es necesario estar familiarizado con el uso de expresiones regulares (regex). Para obtener más información sobre el motor de regex de .NET usado para procesar el texto, vea [Expresiones regulares de .NET](https://docs.microsoft.com/dotnet/standard/base-types/regular-expressions).

  Los servicios de soporte técnico y atención al cliente de Microsoft no pueden proporcionarle definiciones personalizadas de coincidencia de contenido (mediante la creación de clasificaciones personalizadas o patrones de expresiones regulares). Los ingenieros de soporte técnico pueden proporcionar soporte limitado para la característica (por ejemplo, pueden proporcionar patrones de expresiones regulares de ejemplo con fines de prueba, o bien ayudarle en la solución de problemas de un patrón de expresión regular existente que no se desencadene del modo previsto), pero no pueden ofrecer garantías de que cualquier desarrollo de coincidencia de contenido personalizado se adapte a sus requisitos u obligaciones.

- Para obtener más información sobre el motor de regex de .NET usado para el procesamiento de texto, vea [Expresiones regulares en .NET](https://docs.microsoft.com/dotnet/standard/base-types/regular-expressions).

- DLP usa el rastreador de búsqueda para identificar y clasificar información confidencial en sitios de SharePoint Online OneDrive para la Empresa. Para identificar el nuevo tipo personalizado de información confidencial en contenido existente, es necesario volver a rastrear el contenido. El contenido se vuelve a rastrear basándose en una programación, pero puede volverlo a rastrear de forma manual para una colección de sitios, una lista o una biblioteca. Para obtener más información, vea [Solicitar de forma manual el rastreo y la nueva indexación de un sitio, biblioteca o lista](https://docs.microsoft.com/sharepoint/crawl-site-content).

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a>Crear tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento

En el Centro de seguridad y cumplimiento, vaya a **Clasificaciones** \> **Tipos de información confidencial** y haga clic en **Crear**.

Las opciones pueden entenderse fácilmente y se explican en la página asociada del asistente:

- **Nombre**

- **Descripción**

- **Proximidad**

- **Nivel de confianza**

- **Elemento de patrón principal** (palabras clave, expresión regular o diccionario)

- Opcional: **elementos de patrón complementarios** (palabras clave, expresión regular o diccionario) y un valor correspondiente de **Costo mínimo**.

Imagine el escenario siguiente: quiere usar un tipo personalizado de información confidencial que detecte números de empleado de nueve dígitos en el contenido, así como las palabras clave “id. de empleado” e “identificación”. Para crear este tipo personalizado de información confidencial, siga este procedimiento:

1. En el Centro de seguridad y cumplimiento, vaya a **Clasificaciones** \> **Tipos de información confidencial** y haga clic en **Crear**.

2. En la página **Seleccionar un nombre y una descripción**, escriba los valores siguientes:

  - **Nombre**: id. de empleado.

  - **Descripción**: detectar números de id. de empleado de Contoso de nueve dígitos.

  Cuando termine, haga clic en **Siguiente**.

3. En la página **Requisitos de coincidencia**, haga clic en **Agregar un elemento** y configure las opciones siguientes:

  - **Detectar contenido que contenga**:
 
    a. Haga clic en **Cualquiera de estos** y seleccione **Expresión regular**.

    b. En el cuadro Expresión regular, escriba `(\s)(\d{9})(\s)` (números de nueve dígitos rodeados por espacios en blanco).
  
  - **Elementos complementarios**: haga clic en **Agregar elementos complementarios** y seleccione **Contiene esta lista de palabras clave**.

  - En el área **Contiene esta lista de palabras clave**, configure las opciones siguientes:

    - **Lista de palabras clave**: escriba el valor “empleado,id.,identificación”.

    - **Recuento mínimo**: deje el valor predeterminado (1).

  - No modifique el valor predeterminado de **Nivel de confianza** (60). 

  - No modifique el valor predeterminado de **Proximidad de caracteres** (300).

  Cuando termine, haga clic en **Siguiente**.

4. En la página **Revisar y finalizar**, revise la configuración y, después, haga clic en **Finalizar**.

5. En la página siguiente, puede probar el nuevo tipo personalizado de información confidencial. Para obtener más información, vea [Probar tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento](#test-custom-sensitive-information-types-in-the-security--compliance-center). De lo contrario, haga clic en **Cancelar**.

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?

Para comprobar si un tipo de información confidencial se creó correctamente, siga uno de estos procedimientos:

  - Vaya a **Clasificaciones** \> **Tipos de información confidencial** y asegúrese de que en la lista se muestre el nuevo tipo personalizado de información confidencial.

  - Pruebe el nuevo tipo personalizado de información confidencial. Para obtener más información, vea [Probar tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento](#test-custom-sensitive-information-types-in-the-security--compliance-center).

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a>Modificar tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento

**Nota**: Solo se pueden modificar los tipos personalizados de información confidencial; no se pueden modificar los tipos de información confidencial integrados. Pero puede usar PowerShell para exportar los tipos personalizados de información confidencial integrados, personalizarlos y, después, importarlos como tipos personalizados de información confidencial. Para obtener más información, vea [Personalizar un tipo de información confidencial integrado](customize-a-built-in-sensitive-information-type.md).

En el Centro de seguridad y cumplimiento, vaya a **Clasificaciones** \> **Tipos de información confidencial** y seleccione el tipo personalizado de información confidencial que quiera modificar.

Verá las mismas opciones disponibles que al crear el tipo personalizado de información confidencial en el Centro de seguridad y cumplimiento. Para obtener más información, vea [Crear tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento](#create-custom-sensitive-information-types-in-the-security--compliance-center).

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?

Para comprobar si un tipo de información confidencial se modificó correctamente, siga uno de estos procedimientos:

  - Vaya a **Clasificaciones** \> **Tipos de información confidencial** para comprobar las propiedades del tipo personalizado de información confidencial modificado.

  - Pruebe el tipo personalizado de información confidencial modificado. Para obtener más información, vea [Probar tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento](#test-custom-sensitive-information-types-in-the-security--compliance-center).

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a>Quitar tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento 

**Notas**:

- Solo se pueden quitar los tipos personalizados de información confidencial; no se pueden quitar los tipos de información confidencial integrados.

- Antes de quitar un tipo personalizado de información confidencial, asegúrese de que ninguna de las directivas DLP o reglas de flujo del correo de Exchange (también conocidas como reglas de transporte) hagan referencia al tipo de información confidencial.

1. En el Centro de seguridad y cumplimiento, vaya a **Clasificaciones** \> **Tipos de información confidencial** y seleccione uno o más tipos personalizados de información confidencial que quiera quitar.

2. En el control flotante, haga clic en **Eliminar** (o en **Eliminar tipos de información confidencial**, si seleccionó más de uno).

3. Haga clic en **Sí** en el mensaje de advertencia que se muestre.

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?

Para comprobar si un tipo personalizado de información confidencial se quitó correctamente, vaya a **Clasificaciones** \> **Tipos de información confidencial** y asegúrese de que el tipo personalizado de información confidencial ya no se muestre en la lista.


## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a>Probar tipos personalizados de información confidencial en el Centro de seguridad y cumplimiento

1. En el Centro de seguridad y cumplimiento, vaya a **Clasificaciones** \> **Tipos de información confidencial**.

2. Seleccione uno o más tipos personalizados de información confidencial que quiera probar. En el control flotante que se abra, haga clic en **Probar tipo** (o en **Probar tipos de información confidencial**, si seleccionó un más de uno).

3. En la página que se abra, cargue un documento para realizar la prueba (puede arrastrar y colocar un archivo, o bien puede hacer clic en **Examinar** y seleccionar un archivo).

4. Haga clic en el botón **Probar** para probar el documento y ver si hay coincidencias de patrones en el archivo.
