---
title: Crear, probar y optimizar una directiva DLP
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: 'La forma más sencilla, más comunes para empezar a trabajar con directivas de DLP es utilizar una de las plantillas incluidas en Office 365. '
ms.openlocfilehash: 1d4697811a5d8dd426fed80d3d60bcd2fbea6335
ms.sourcegitcommit: 42c7ad69f95fc4d2de13293b39cc44931b9f82e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2018
ms.locfileid: "26522792"
---
# <a name="create-test-and-tune-a-dlp-policy"></a>Crear, probar y optimizar una directiva DLP

**Autor de entidad de seguridad** </br>
Paul Cunningham, MVP de Microsoft </br>
[365 práctico](https://practical365.com/) </br>
[@Practical365](https://twitter.com/practical365)</br>
__________________________________________________

Prevención de pérdida de datos es una característica de cumplimiento de normas de Office 365 diseñada para ayudar a su organización a evitar la exposición accidental o intencionada de información confidencial a partes no deseadas. DLP tiene sus raíces en Exchange Server y Exchange Online y también es aplicable en SharePoint Online y OneDrive para la empresa.

DLP utiliza un motor de análisis de contenido para examinar el contenido de los mensajes de correo electrónico y archivos, busca información confidencial, como números de tarjeta de crédito y la información de identificación personal (PII). Información confidencial debe normalmente no enviarse por correo electrónico, o incluido en los documentos, sin realizar pasos adicionales, como cifrar el mensaje de correo electrónico o los archivos. Uso de DLP puede detectar información confidencial y tomar medidas tales como:

- Registrar el evento con fines de auditoría
- Mostrar una advertencia para el usuario final que envía el correo electrónico o compartir el archivo
- Activamente para bloquear el correo electrónico o el archivo de produciendo el uso compartido

En ocasiones, los clientes descartar DLP debido a que no consideran que tengan el tipo de datos que necesita protección. La suposición es que los datos confidenciales, como registros médicos o información financiera, sólo existen para industrias como atención médica o para empresas que se ejecutan las tiendas en línea. Pero cualquier negocio puede controlar la información confidencial de forma regular, incluso si éste no darse cuenta. Una hoja de cálculo de nombres de los empleados y las fechas de nacimiento son simplemente como confidenciales como una hoja de cálculo de nombres de los clientes y los detalles de la tarjeta de crédito. Y este tipo de información tiende a float alrededor de más de lo esperado, como los empleados ir modo silencioso acerca de las tareas del día a día, nada de exportación pensando en un archivo CSV de un sistema y enviar por correo electrónico a una persona. Es posible también que sorpresa ¿con qué frecuencia los empleados envían mensajes de correo electrónico que contiene la tarjeta de crédito o detalles de banca sin tener en cuenta las consecuencias.

## <a name="how-sensitive-information-is-detected-by-dlp"></a>Cómo se detecta información confidencial DLP

Información confidencial se identifica mediante la coincidencia patrón de expresión regular (RegEx), en combinación con otros indicadores, como la proximidad de ciertas palabras clave para los patrones de coincidencia. Un ejemplo de esto es números de tarjeta de crédito. Un número de tarjeta de crédito VISA tiene 16 dígitos. Sin embargo, esos dígitos pueden escribirse en formas diferentes, como 1111-1111-1111-1111 1111 1111 1111 1111 o 1111111111111111.

Cualquier cadena de 16 dígitos no es necesariamente un número de tarjeta de crédito, podría ser un número de vale de un sistema de Ayuda de escritorio o un número de serie de un componente de hardware. Para indicar la diferencia entre un número de tarjeta de crédito y una cadena de 16 dígitos inocua, un cálculo es realizan (suma de comprobación) para confirmar que los números coinciden con un patrón conocido de las diversas marcas de tarjeta de crédito.

Además, también se considera que la proximidad de las palabras clave, como "VISA" o "AMEX", junto con la proximidad a los valores de fecha que es posible que la fecha de caducidad de la tarjeta de crédito, tomar una decisión sobre si los datos están un número de tarjeta de crédito o no.

En otras palabras, DLP es normalmente lo suficientemente inteligente como para reconocer la diferencia entre estos dos textos de un correo electrónico:

- "Puede pedido me nuevo portátil. Usar mi número VISA 1111-1111-1111-1111, 11/22, expiración y Enviarme la fecha de entrega estimada cuando haya."
- "Mi número de serie de portátiles es 2222-2222-2222-2222 y lo adquirió en 11/2010. Por cierto, es mi visa de viaje aprobado todavía?"

Una buena referencia para mantener con marcador es este [tema en tipos de información confidencial](what-the-sensitive-information-types-look-for.md) que se explica cómo se detecta cada tipo de información.

## <a name="where-to-start-with-data-loss-prevention"></a>Dónde empezar con la prevención de pérdida de datos

Cuando los riesgos de pérdida de datos no son totalmente obvios, es difícil averiguar donde exactamente debe comenzar con la implementación de DLP. Afortunadamente, se pueden ejecutar las directivas de DLP en "modo de prueba", lo que permite evaluar su eficacia y exactitud antes de activarlas.

Las directivas de DLP para Exchange Online se pueden administrar mediante el centro de administración de Exchange. Pero puede configurar directivas de DLP para todas las cargas de trabajo a través de la seguridad y el centro de cumplimiento, por lo es lo que debe usar para demostraciones en este artículo. En el centro de cumplimiento y seguridad encontrará las directivas de DLP en **prevención de pérdida de datos** > **Directiva**. Haga clic en **crear una directiva** para iniciar.

Office 365 proporciona una gama de [plantillas de directiva de DLP](what-the-dlp-policy-templates-include.md) que puede utilizar para crear directivas de DLP. Supongamos que tenga un negocio australiano. Puede filtrar las plantillas de directiva para mostrar sólo los que son relevantes para Australia, que se dividen en las categorías generales de financiero, médicos y mantenimiento y de privacidad.

![Opción para elegir el país o región](media/DLP-create-test-tune-choose-country.png)

Para esta demostración elegir datos australiano personalmente identificable información (PII), que incluye los tipos de información del número de licencia del controlador y número de identificación de impuesto australiano (TFN).

![Opción para elegir una plantilla de directiva](media/DLP-create-test-tune-choose-policy-template.png)

Asigne un nombre de la nueva directiva DLP. El nombre predeterminado coincidirá con la plantilla de directiva DLP, pero debe elegir un nombre más descriptivo de su elección, debido a que se pueden crear varias directivas desde la misma plantilla.

![Para asignar un nombre de la directiva](media/DLP-create-test-tune-name-policy.png)

Elija las ubicaciones que se aplicará la directiva. Pueden aplicar las directivas de DLP a Exchange Online, SharePoint Online y OneDrive para la empresa. Voy a dejar esta directiva configurada para aplicar a todas las ubicaciones.

![Opción para elegir todas las ubicaciones](media/DLP-create-test-tune-choose-locations.png)

En el primer paso de la **Configuración de directiva** sólo acepte los valores predeterminados por ahora. Hay una gran cantidad de personalización que se pueden hacer en las directivas de DLP, pero los valores predeterminados son un punto de partida de forma precisa.

![Opciones para personalizar el tipo de contenido que se protegerán](media/DLP-create-test-tune-default-customization-settings.png)

Tras hacer clic en **siguiente** aparecerá una página de **Configuración de directiva** adicional con más opciones de personalización. Para una directiva que se está probando acaba, aquí es donde puede empezar a realizar algunos ajustes.

- Se desactivaron sugerencias de directiva para ahora, que constituye un paso razonable que se realizarán si sólo se está probando cosas y no desea mostrar nada a los usuarios aún. Sugerencias de directiva mostrar advertencias a los usuarios que están a punto de infringir una directiva de DLP. Por ejemplo, un usuario de Outlook ve una advertencia de que el archivo que han adjuntado contiene los números de tarjeta de crédito y hará que su mensaje de correo electrónico se rechaza. El objetivo de sugerencias de directiva es detener el comportamiento que no son compatibles con antes de que suceda.
- También he reduce el número de instancias de 10 a 1, para que esta directiva detectará cualquier uso compartido de datos PII australiano, no sólo de forma masiva de los datos de uso compartido.
- También he agregado a otro destinatario para el correo electrónico de informe del incidente.

![Configuración de directivas adicionales](media/DLP-create-test-tune-more-policy-settings.png)

Por último, he configurado esta directiva para que se ejecute en modo de prueba inicialmente. Tenga en cuenta también es una opción aquí para deshabilitar sugerencias de directivas mientras se encuentra en modo de prueba. Esto le ofrece la flexibilidad de tener sugerencias de directiva habilitadas en la directiva, pero, a continuación, decida si desea mostrar o suprimir ellos durante las pruebas.

![Opción para probar la directiva en primer lugar](media/DLP-create-test-tune-test-mode.png)

En la pantalla de revisión final haga clic en **crear** para terminar de crear la directiva.

## <a name="test-a-dlp-policy"></a>Probar una directiva de DLP

La nueva directiva DLP comenzará surta efecto dentro de aproximadamente 1 hora. Puede sentarse y esperar a que se desencadena por actividad de usuario normal, o puede que intenta desencadenar usted mismo. Anteriormente vinculados a este [tema en tipos de información confidencial](what-the-sensitive-information-types-look-for.md), que proporciona información acerca de cómo activar las coincidencias de DLP.

Por ejemplo, la directiva DLP que creé para este artículo detectará los números de archivo de impuesto australiano (TFN). Según la documentación, la coincidencia se basa en los siguientes criterios.

![Documentación sobre el número de archivo de impuestos de Australia](media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
Para demostrar la detección TFN de forma directa en su lugar, se gobernar un correo electrónico con las palabras "Número de archivo de impuestos" y una cadena de 9 dígitos cerca de a través de sin ningún problema. La razón por la que no activa la directiva de DLP es que la cadena de 9 dígitos debe pasar la suma de comprobación que indica que es un TFN válido y no sólo una cadena inocua de números.

![Número de archivo de impuestos de Australia que no pasan la suma de comprobación](media/DLP-create-test-tune-email-test1.png)

En comparación, un correo electrónico con las palabras "Número de archivo de impuestos" y un TFN válido que pasa la suma de comprobación activarán la directiva. Para el registro, el TFN estoy usando ha atendido desde un sitio Web que genera válido, pero no original, TFNs. Hay sitios similares que generan [los números de tarjeta de crédito válido pero falsos](http://www.fakecreditcardgenerator.net/). Dichos sitios son muy útiles porque uno de los errores más comunes al probar una directiva de DLP está usando un número falso que no es válido y no se transfiera la suma de comprobación (y, por tanto, no se activarán de la directiva).

![Número de archivo de impuestos de Australia que pasa la suma de comprobación](media/DLP-create-test-tune-email-test2.png)

El correo electrónico de informe del incidente incluye el tipo de información confidencial que se detectó, ¿cuántas instancias se han detectado y el nivel de confianza de la detección.

![Informe del incidente que muestra el número de archivo de impuestos detectado](media/DLP-create-test-tune-email-incident-report.png)

Si deja la directiva de DLP en modo de prueba y analizar los mensajes de correo electrónico de informe del incidente, puede empezar a hacerse una idea de la precisión de la directiva de DLP y cómo eficaz será cuando se aplica. Además de los informes de incidentes, puede [utilizar los informes DLP](view-the-dlp-reports.md) para ver una vista agregada de coincidencias de directivas a través de su inquilino.

## <a name="tune-a-dlp-policy"></a>Optimización de una directiva de DLP

Es posible que desee realizar algunos ajustes en el comportamiento de las directivas como analizar los aciertos de directiva. Como un ejemplo sencillo, es posible que determine que uno TFN en el correo electrónico no es un problema (creo que aún es pero vamos con él con fines de demostración), pero dos o más instancias es un problema. Varias instancias podrían ser un escenario arriesgado, como un empleado un correo electrónico a una exportación CSV desde la base de datos de recursos humanos a una parte externa, por ejemplo un servicio de contabilidad externo. Definitivamente algo prefiere detectar y bloquear.

En el centro de cumplimiento y seguridad puede editar una directiva existente para ajustar el comportamiento.

![Opción de directiva de edición](media/DLP-create-test-tune-edit-policy.png)
 
Puede ajustar la configuración de ubicación para que la directiva se aplica únicamente a las cargas de trabajo específicas o a las cuentas y sitios específicos.

![Opciones para elegir ubicaciones específicas](media/DLP-create-test-tune-edit-locations.png)

También puede ajustar la configuración de directiva y editar las reglas para que se adapte mejor a sus necesidades.

![Opción para editar regla](media/DLP-create-test-tune-edit-rule.png)

Puede cambiar cuando se edita una regla dentro de una directiva de DLP:

- Las condiciones, incluido el tipo y el número de instancias de datos confidenciales que se activarán la regla.
- Las acciones que se toman, como la restricción del acceso al contenido.
- Notificaciones de usuario, que son sugerencias de directiva que se muestran al usuario en su explorador web o el cliente de correo electrónico.
- Invalida el usuario, lo que determina si los usuarios pueden elegir continuar con su correo electrónico o archivo de uso compartido de todos modos.
- Informes de incidentes, para notificar a los administradores.

![Opciones para editar elementos de una regla](media/DLP-create-test-tune-editing-options.png)

Para esta demostración he agregado notificaciones de usuario a la directiva (tenga cuidado de hacerlo sin aprendizaje de conocimiento del usuario adecuada), y permite a los usuarios invalidar la directiva con una justificación comercial o por marcar como falso positivo. Tenga en cuenta que también puede personalizar el texto de sugerencia de correo electrónico y la directiva si desea incluir cualquier información adicional acerca de las directivas de su organización, o solicitar a los usuarios ponerse en contacto con soporte técnico si tienen preguntas.

![Opciones para las notificaciones de usuario y reemplazos](media/DLP-create-test-tune-user-notifications.png)

La directiva contiene dos reglas para el control de gran volumen y bajo volumen, por lo que debe asegurarse de ambos, con las acciones que desee editar. Esto es una oportunidad para tratar casos de manera diferente dependiendo de sus características. Por ejemplo, podría permitir reemplazos para las infracciones de bajo volumen, pero no permitir reemplazos para las infracciones de gran volumen.

![Una regla para una regla para el volumen bajo y de gran volumen](media/DLP-create-test-tune-two-rules.png)

También, si desea bloquear realmente o restringir el acceso al contenido que se encuentra en infracción de directiva, debe configurar una acción de la regla para hacerlo.

![Opción para restringir el acceso al contenido](media/DLP-create-test-tune-restrict-access-action.png)

Después de guardar dichos cambios a la configuración de directiva, también necesita volver a la página principal de configuración de la directiva y habilitar la opción para mostrar sugerencias de directiva a los usuarios mientras la directiva está en modo de prueba. Esto es una forma eficaz para presentar las directivas de DLP a los usuarios finales y hacer aprendizaje de conocimiento del usuario, sin poner en peligro demasiados falsos positivos que afectan a su productividad.

![Opción para mostrar sugerencias de directivas en modo de prueba](media/DLP-create-test-tune-show-policy-tips.png)

En el lado del servidor (o la parte de la nube, si lo prefiere) el cambio posible no tenga efecto inmediatamente, debido a distintos intervalos de procesamiento. Si realiza un cambio de directiva DLP que mostrará nuevas sugerencias de directiva a un usuario, el usuario no puede ver los cambios surtan efecto inmediatamente en su cliente de Outlook, que comprueba si hay cambios en la directiva cada 24 horas. Si desea acelerar el proceso para las pruebas, puede usar esta revisión del registro para [Borrar la última marca de tiempo de descarga de la clave PolicyNudges](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451). Outlook descargará la información más reciente de la directiva la próxima vez reinicie y empezar a redactar un mensaje de correo electrónico.

Si tiene sugerencias de directiva habilitadas, el usuario comenzará a ver las sugerencias en Outlook y puede informar falsos positivos para cuando se produzcan.

![Sugerencia de directiva con la opción de falso positivo](media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a>Investigar falsos positivos

Plantillas de directiva de DLP no son perfectas listo. Es probable que encontrará algunos falsos positivos que se producen en el entorno, que es la razón por la que es tan importante facilitar la forma en una implementación de DLP, teniendo el tiempo para probar y ajustar las directivas de adecuadamente.

Este es un ejemplo de un falso positivo. Este correo electrónico es un proceso bastante inocua. El usuario es proporcionar su número de teléfono móvil a una persona y, incluida su firma de correo electrónico.

![Correo electrónico que muestra la información positivo falso](media/DLP-create-test-tune-false-positive-email.png)
 
Pero el usuario ve una sugerencia de directiva que se les advierta de que el correo electrónico contiene información confidencial, en concreto, el número de licencias de un controlador australiano.

![Opción de falso positivo en la sugerencia de directiva](media/DLP-create-test-tune-policy-tip-closeup.png)

El usuario puede informar el falso positivo, y el administrador puede buscar en ¿por qué se ha producido. En el correo electrónico de informe del incidente, el correo electrónico se marca como falso positivo.

![Informe del incidente que muestra de falsos positivos](media/DLP-create-test-tune-false-positive-incident-report.png)

Caso de licencia de este controlador es un buen ejemplo para profundizar en. La razón este falso positivo se ha producido es que el tipo se activará por cualquier cadena 9 dígitos (incluso uno que forma parte de una cadena de 10 dígitos), "del controlador australiano licencia" dentro de proximidad de 300 caracteres para las palabras clave "Sidney nsw" (no entre mayúsculas y minúsculas). Por lo que se desencadena por la firma de correo electrónico y número de teléfono, ya que el usuario se encuentra en Sidney.

Es interesante comprobar que, si "Sidney, NSW" tiene una coma, no se desencadena la directiva de DLP. Tienen ni idea de por qué una coma realiza alguna diferencia aquí, ni ¿por qué no se incluyen otras ciudades y Estados en Australia en las palabras clave para el tipo de información de licencia del controlador australiano, pero ahí está. Por lo tanto, ¿cómo podemos acerca de él? Hay un par de opciones.

Una opción consiste en quitar el tipo de información de licencia del controlador australiano de la directiva. Está en allí porque es parte de la plantilla de directiva DLP, pero no nos estamos obligados a usarlo. Si sólo está interesado en los números de archivo fiscal y no los permisos de conducir, solo puede hacerlo. Por ejemplo, puede quitarlo de la regla de baja volumen en la directiva, pero dejarla en la regla de gran volumen para que aún se detectan las listas de varias licencias de controladores.

![Opción para eliminar el tipo de información confidencial de regla](media/DLP-create-test-tune-delete-low-volume-rule.png)
 
Otra opción es simplemente aumentar el número de instancia, por lo que solo se detectó un volumen bajo de licencias del controlador cuando hay varias instancias.

![Opción para editar la cuenta de instancias](media/DLP-create-test-tune-edit-instance-count.png)

Además de cambiar el número de instancia, también puede ajustar la precisión de coincidencia (o nivel de confianza). Si el tipo de información confidencial tiene varios patrones, puede ajustar la precisión de coincidencia en la regla para que la regla coincida con sólo los patrones específicos. Por ejemplo, para ayudar a reducir los falsos positivos, puede establecer la precisión de coincidencia de la regla de modo que coincida con sólo el patrón con el mayor nivel de confianza. Descripción de cómo se calcula el nivel de confianza es un poco complicada (y más allá del ámbito de esta entrada), pero aquí es una buena explicación de [cómo usar el nivel de confianza para ajustar las reglas](https://docs.microsoft.com/en-us/office365/securitycompliance/data-loss-prevention-policies#match-accuracy).

Por último, si desea obtener incluso un poco más avanzada, puede personalizar cualquier tipo de información confidencial, por ejemplo, puede quitar "Sidney NSW" de la lista de palabras clave de [licencia del controlador australiano](https://docs.microsoft.com/en-us/office365/securitycompliance/what-the-sensitive-information-types-look-for#australia-drivers-license-number), para eliminar el falso positivo desencadena por encima. Para obtener información sobre cómo hacerlo mediante XML y PowerShell, vea este tema acerca de [cómo personalizar un tipo de información confidencial integradas](customize-a-built-in-sensitive-information-type.md).

## <a name="turn-off-a-dlp-policy"></a>Desactivar una directiva DLP

Cuando esté satisfecho de que su directiva DLP es precisa y detecten eficazmente los tipos de información confidencial, y que los usuarios finales están listos para abordar los problemas con las directivas que se está en su lugar, a continuación, puede habilitar la directiva.

![Opción para activar la directiva](media/DLP-create-test-tune-turn-on-policy.png)
 
Si está esperando para ver cuándo se surta efecto, [Conectar a Office 365 seguridad & PowerShell de centro de cumplimiento de normas](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) y ejecute el [cmdlet Get-DlpCompliancePolicy](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps) para ver el DistributionStatus la directiva.

![Ejecuta el cmdlet de PowerShell](media/DLP-create-test-tune-PowerShell.png)

Después de activar la directiva DLP, debe ejecutar algunas pruebas finales de su propio para realizar Asegúrese de que se están produciendo las acciones de directiva esperado. Si está intentando probar cosas como datos de tarjeta de crédito, hay sitios Web en línea con información sobre cómo generar ejemplo tarjeta de crédito u otra información personal que va a pasar las sumas de comprobación y desencadenar sus directivas.

Las directivas que permiten invalidaciones de usuario le presentará esta opción para el usuario como parte de la sugerencia de directiva.

![Sugerencia de directiva que permite el reemplazo de usuario](media/DLP-create-test-tune-override-option.png)

Las directivas que restringen el contenido va a presentar la advertencia al usuario como parte de la sugerencia de directiva e impedir que enviar el correo electrónico.

![Sugerencia de directiva que el contenido está restringido](media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a>Resumen

Directivas de prevención de pérdida de datos son útiles para las organizaciones de todos los tipos. Probar algunas directivas DLP es un ejercicio de bajo riesgo debido al control que tiene sobre aspectos como sugerencias de directiva, los reemplazos de usuario final e informes de incidentes. Modo silencioso, puede probar algunas directivas de DLP para ver qué tipo de las infracciones ya se están produciendo en la organización, y, a continuación, directivas de naves con baja tasas de falsos positivos, enseñar a los usuarios en lo que está permitido y no permitido y, a continuación, desplegar las directivas de DLP a la organización.
