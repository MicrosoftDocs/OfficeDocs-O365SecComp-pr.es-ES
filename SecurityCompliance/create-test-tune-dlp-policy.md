---
title: Crear, probar y optimizar una directiva DLP
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MET150
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: 'La forma más sencilla y habitual de empezar a trabajar con directivas de DLP es usar una de las plantillas incluidas en Office 365. '
ms.openlocfilehash: 250f3ec1cfa68d7980f3b4a01076f4c4d0b53a01
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410985"
---
# <a name="create-test-and-tune-a-dlp-policy"></a>Crear, probar y optimizar una directiva DLP

**Autor principal** <br/>
Paul Cunningham, MVP de Microsoft <br/>
[Práctico 365](https://practical365.com/) <br/>
[@Practical365](https://twitter.com/practical365)<br/>
__________________________________________________

La prevención de pérdida de datos es una característica de cumplimiento de Office 365 que está diseñada para ayudar a su organización a evitar la exposición intencionada o accidental de información confidencial a partes no deseadas. DLP tiene sus raíces en Exchange Server y Exchange Online, y también es aplicable en SharePoint Online y OneDrive para la empresa.

DLP utiliza un motor de análisis de contenido para examinar el contenido de los mensajes de correo electrónico y los archivos, en busca de información confidencial, como los números de tarjetas de crédito y la información de identificación personal (PII). La información confidencial no suele enviarse en el correo electrónico ni se puede incluir en documentos, sin necesidad de realizar pasos adicionales, como cifrar el mensaje o los archivos de correo electrónico. Con DLP puede detectar información confidencial y emprender acciones como:

- Registrar el evento con fines de auditoría
- Mostrar una advertencia al usuario final que está enviando el correo electrónico o compartiendo el archivo
- Bloquear activamente el correo electrónico o el uso compartido de archivos sin tener lugar

A veces, los clientes descartan DLP porque no consideran que ellos mismos tienen el tipo de datos que necesitan protección. La suposición es que los datos confidenciales, como los registros médicos o la información financiera, solo existen para las industrias como la atención médica o para las empresas que ejecutan tiendas en línea. Sin embargo, cualquier empresa puede manejar información confidencial de forma periódica, incluso si no la tiene en cuenta. Una hoja de cálculo con los nombres y las fechas de los empleados es tan importante como una hoja de cálculo con los nombres de los clientes y los detalles de las tarjetas de crédito. Además, este tipo de información tiende a flotar más de lo que esperaba, ya que los empleados se centran en silencio en las tareas cotidianas, pensando en nada de exportar un archivo CSV de un sistema y enviarlo por correo electrónico a alguien. También podría sorprenderse con la frecuencia con la que los empleados envían correos electrónicos que contienen datos de tarjetas de crédito o banca sin tener en cuenta las consecuencias.

## <a name="how-sensitive-information-is-detected-by-dlp"></a>Cómo se detecta la información confidencial mediante DLP

La información confidencial se identifica mediante coincidencia de patrón de expresiones regulares (RegEx), en combinación con otros indicadores, como la proximidad de determinadas palabras clave a los patrones coincidentes. Un ejemplo de esto son los números de tarjeta de crédito. Un número de tarjeta de crédito VISA tiene 16 dígitos. Sin embargo, estos dígitos pueden escribirse de varias maneras, como 1111-1111-1111-1111, 1111 1111 1111 1111 o 1111111111111111.

Cualquier cadena de 16 dígitos no es necesariamente un número de tarjeta de crédito, puede ser un número de incidencia de un sistema de asistencia o un número de serie de un componente de hardware. Para identificar la diferencia entre un número de tarjeta de crédito y una cadena de 16 dígitos inofensivo, se realiza un cálculo (suma de comprobación) para confirmar que los números coinciden con un patrón conocido de las diversas marcas de tarjeta de crédito.

Además, la proximidad de palabras clave como "VISA" o "AMEX", junto con los valores de proximidad a la fecha que pueden ser la fecha de expiración de la tarjeta de crédito, también se considera como una decisión sobre si los datos son un número de tarjeta de crédito o no.

Es decir, DLP suele ser lo suficientemente inteligente como para reconocer la diferencia entre estos dos textos en un correo electrónico:

- "¿Puede solicitarme un nuevo portátil. Usar mi VISAdo número 1111-1111-1111-1111, expirar 11/22 y enviarme la fecha de entrega estimada cuando la tiene. "
- "El número de serie del portátil es 2222-2222-2222-2222 y se compró en 11/2010. Por cierto, ¿se aprobó todavía mi visado de viajes? "

Una buena referencia para conservar el marcador es este [tema sobre los tipos de información confidencial](what-the-sensitive-information-types-look-for.md) que explican cómo se detecta cada tipo de información.

## <a name="where-to-start-with-data-loss-prevention"></a>Dónde comenzar con prevención de pérdida de datos

Cuando los riesgos de la filtración de datos no son totalmente obvios, es difícil averiguar dónde se debe empezar exactamente con la implementación de DLP. Afortunadamente, las directivas de DLP se pueden ejecutar en el "modo de prueba", lo que le permite evaluar su eficacia y precisión antes de activarlas.

Las directivas de DLP para Exchange Online se pueden administrar a través del centro de administración de Exchange. Sin embargo, puede configurar directivas de DLP para todas las cargas de trabajo a través del centro de seguridad & cumplimiento, de modo que esto es lo que voy a usar para las demostraciones de este artículo. En el centro de seguridad & cumplimiento, encontrará las directivas DLP en la**Directiva**de **prevención** > de pérdida de datos. Haga clic en **crear una directiva** para iniciar.

Office 365 proporciona una amplia variedad de [plantillas de directivas de DLP](what-the-dlp-policy-templates-include.md) que puede usar para crear directivas de DLP. Supongamos que es un negocio australiano. Puede filtrar las plantillas de directiva para mostrar solo las que son relevantes para Australia, que entran en las categorías generales de finanzas, médicos y salud y privacidad.

![Opción para elegir el país o la región](media/DLP-create-test-tune-choose-country.png)

Para esta demostración, elegiré datos de identificación personal (PII) de Australia, que incluye los tipos de información del número de archivo de impuestos de Australia (TFN) y el número de permiso de conducir.

![Opción para elegir una plantilla de Directiva](media/DLP-create-test-tune-choose-policy-template.png)

Asigne un nombre a la nueva Directiva de DLP. El nombre predeterminado coincidirá con la plantilla de directiva DLP, pero debe elegir un nombre más descriptivo, ya que se pueden crear varias directivas a partir de la misma plantilla.

![Opción para asignar un nombre a la Directiva](media/DLP-create-test-tune-name-policy.png)

Elija las ubicaciones a las que se aplicará la Directiva. Las directivas DLP se pueden aplicar a Exchange Online, SharePoint Online y OneDrive para la empresa. Voy a dejar esta directiva configurada para aplicarse a todas las ubicaciones.

![Opción para elegir todas las ubicaciones](media/DLP-create-test-tune-choose-locations.png)

En el primer paso de configuración de la **Directiva** , basta con aceptar los valores predeterminados por el momento. Hay una gran cantidad de personalización que puede hacer en las directivas de DLP, pero los valores predeterminados son un punto muy bueno para empezar.

![Opciones para personalizar el tipo de contenido que se va a proteger](media/DLP-create-test-tune-default-customization-settings.png)

Después de hacer clic en **siguiente** , se le mostrará una página de **configuración de directivas** adicional con más opciones de personalización. Para una directiva que solo está probando, aquí es donde puede empezar a realizar algunos ajustes.

- He desactivado las sugerencias de Directiva por ahora, que es un paso razonable que debe realizar si solo está probando cosas y no quiere mostrar nada a los usuarios todavía. Las sugerencias de directiva muestran advertencias a los usuarios de que están a punto de infringir una directiva de DLP. Por ejemplo, un usuario de Outlook verá una advertencia que indica que el archivo que ha adjuntado contiene números de tarjeta de crédito y que se rechazará el correo electrónico. El objetivo de las sugerencias de directiva es detener el comportamiento no compatible antes de que ocurra.
- También se ha reducido el número de instancias de 10 a 1, por lo que esta directiva detectará cualquier uso compartido de datos PII australianos, no solo el uso compartido de datos de forma masiva.
- También he agregado otro destinatario al correo electrónico del informe de incidentes.

![Configuración de directiva adicional](media/DLP-create-test-tune-more-policy-settings.png)

Por último, he configurado esta directiva para que se ejecute inicialmente en modo de prueba. Observe que también hay una opción para deshabilitar las sugerencias de directiva en el modo de prueba. Esto le proporciona la flexibilidad necesaria para habilitar las sugerencias de directiva en la Directiva, pero después decidir si desea mostrarlas o suprimirlas durante las pruebas.

![Opción para probar la Directiva primero](media/DLP-create-test-tune-test-mode.png)

En la pantalla finalización de la revisión, haga clic en **crear** para finalizar la creación de la Directiva.

## <a name="test-a-dlp-policy"></a>Probar una directiva DLP

La nueva Directiva de DLP empezará a surtir efecto en aproximadamente 1 hora. Puede sentarse y esperar a que se active por una actividad de usuario normal o puede intentar activarla usted mismo. Anteriormente he vinculado a este [tema sobre los tipos de información confidencial](what-the-sensitive-information-types-look-for.md), que proporciona información sobre cómo desencadenar las coincidencias de DLP.

Como ejemplo, la Directiva DLP que he creado para este artículo detectará los números de archivo de impuestos australianos (TFN). De acuerdo con la documentación, la coincidencia se basa en los siguientes criterios.

![Documentación sobre el número de archivo de impuestos de Australia](media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
Para demostrar la detección de TFN de forma bastante predecible, un correo electrónico con las palabras "número de archivo de impuestos" y una cadena de 9 dígitos en proximidad se desplazará sin problemas. La razón por la que no activa la Directiva DLP es que la cadena de 9 dígitos debe pasar la suma de comprobación que indica que es un TFN válido y no solo una cadena de números inocua.

![Número de archivo de impuestos de Australia que no pasa la suma de comprobación](media/DLP-create-test-tune-email-test1.png)

En comparación, un correo electrónico con las palabras "número de archivo de impuestos" y un TFN válido que pase la suma de comprobación activará la Directiva. Para el registro, el TFN que estoy usando se ha tomado de un sitio web que genera un TFNs válido, pero no genuino. Hay sitios similares que generan [números de tarjeta de crédito válidos pero falsos](http://www.fakecreditcardgenerator.net/). Estos sitios son muy útiles porque uno de los errores más comunes al probar una directiva DLP es usar un número falso que no es válido y no pasa la suma de comprobación (y, por lo tanto, no desencadena la Directiva).

![Número de archivo de impuestos de Australia que pasa la suma de comprobación](media/DLP-create-test-tune-email-test2.png)

El correo electrónico del informe de incidentes incluye el tipo de información confidencial que se ha detectado, el número de instancias que se han detectado y el nivel de confianza de la detección.

![Informe de incidentes que muestra el número de archivo de impuestos detectado](media/DLP-create-test-tune-email-incident-report.png)

Si deja la Directiva DLP en modo de prueba y analiza los correos electrónicos del informe de incidentes, puede empezar a familiarizarse con la precisión de la Directiva DLP y la eficacia que tendrá cuando se aplique. Además de los informes de incidentes, puede [usar los informes DLP](view-the-dlp-reports.md) para ver una vista agregada de las coincidencias de directivas en el espacio empresarial.

## <a name="tune-a-dlp-policy"></a>Ajustar una directiva DLP

Al analizar las visitas de la Directiva, es posible que desee realizar algunos ajustes en el comportamiento de las directivas. Como ejemplo sencillo, puede determinar que un TFN en el correo electrónico no es un problema (creo que sigue siendo, pero vamos a ir con él para la demostración), pero dos o más instancias son un problema. Varias instancias podrían ser un escenario arriesgado, como un empleado que envíe por correo electrónico una exportación de CSV desde la base de datos de recursos humanos a una parte externa, por ejemplo, un servicio de contabilidad externo. Definitivamente algo que preferiría detectar y bloquear.

En el centro de seguridad & cumplimiento, puede editar una directiva existente para ajustar el comportamiento.

![Opción para editar la Directiva](media/DLP-create-test-tune-edit-policy.png)
 
Puede ajustar la configuración de ubicación para que la Directiva se aplique solo a cargas de trabajo específicas o a sitios y cuentas específicos.

![Opciones para elegir ubicaciones específicas](media/DLP-create-test-tune-edit-locations.png)

También puede ajustar la configuración de la Directiva y editar las reglas para que se adapten mejor a sus necesidades.

![Opción para editar la regla](media/DLP-create-test-tune-edit-rule.png)

Al editar una regla en una directiva DLP que puede cambiar:

- Las condiciones, incluido el tipo y el número de instancias de datos confidenciales que desencadenarán la regla.
- Las acciones que se realizan, como restringir el acceso al contenido.
- Notificaciones de usuario, que son sugerencias de directiva que se muestran al usuario en su cliente de correo electrónico o explorador Web.
- Invalidaciones de usuario, que determina si los usuarios pueden optar por continuar con el correo electrónico o el uso compartido de archivos de todos modos.
- Informes de incidentes, para notificar a los administradores.

![Opciones para editar partes de una regla](media/DLP-create-test-tune-editing-options.png)

Para esta demostración, he agregado notificaciones de usuario a la Directiva (tenga cuidado de hacerlo sin el suficiente aprendizaje de reconocimiento de usuarios) y los usuarios pueden invalidar la Directiva con una justificación comercial o marcarla como falso positivo. Tenga en cuenta que también puede personalizar el correo electrónico y el texto de la sugerencia de Directiva si desea incluir información adicional sobre las directivas de la organización o solicitar a los usuarios que se pongan en contacto con el soporte técnico si tienen preguntas.

![Opciones de invalidaciones y notificaciones de usuario](media/DLP-create-test-tune-user-notifications.png)

La Directiva contiene dos reglas para controlar el volumen alto y el volumen bajo, por lo que debe asegurarse de editar ambas con las acciones que desee. Esta es una oportunidad para tratar los casos de manera diferente en función de sus características. Por ejemplo, puede permitir reemplazos para infracciones de volumen bajos, pero no permitir invalidaciones para infracciones de gran volumen.

![Una regla para grandes volúmenes y una regla para volumen bajo](media/DLP-create-test-tune-two-rules.png)

Además, si desea bloquear o restringir el acceso al contenido que infringe la Directiva, debe configurar una acción en la regla para hacerlo.

![Opción para restringir el acceso al contenido](media/DLP-create-test-tune-restrict-access-action.png)

Después de guardar los cambios en la configuración de la Directiva, también es necesario volver a la página de configuración principal de la Directiva y habilitar la opción de Mostrar sugerencias de directiva a los usuarios mientras la Directiva está en modo de prueba. Esta es una forma eficaz de introducir directivas de DLP para los usuarios finales y realizar un entrenamiento del usuario, sin arriesgar demasiados falsos positivos que afecten a su productividad.

![Opción para mostrar las sugerencias de directiva en el modo de prueba](media/DLP-create-test-tune-show-policy-tips.png)

En el lado del servidor (o en la nube si lo prefiere), es posible que el cambio no surta efecto inmediatamente, debido a diferentes intervalos de procesamiento. Si realiza un cambio de la Directiva DLP que mostrará nuevas sugerencias de directiva a un usuario, es posible que el usuario no vea los cambios de forma inmediata en el cliente de Outlook, que comprueba los cambios de Directiva cada 24 horas. Si quiere aumentar la velocidad de las pruebas, puede usar esta corrección del registro para [borrar la marca de tiempo de la última descarga de la clave PolicyNudges](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451). Outlook descargará la información más reciente de la Directiva la próxima vez que la reinicie y empiece a redactar un mensaje de correo electrónico.

Si tiene habilitadas las sugerencias de Directiva, el usuario empezará a ver sugerencias en Outlook y podrá informar de falsos positivos cuando se produzcan.

![Sugerencia de directiva con opción para notificar falso positivo](media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a>Investigar positivos falsos

Las plantillas de directivas de DLP no son perfectas directamente en el cuadro. Es probable que se produzcan falsos positivos en el entorno, por lo que es tan importante para facilitar la implementación de DLP y dedicar tiempo a probar y ajustar las directivas de forma adecuada.

Este es un ejemplo de un falso positivo. Este correo electrónico es bastante inocuo. El usuario proporciona su número de teléfono móvil a alguien e incluye su firma de correo electrónico.

![Correo electrónico que muestra información de falsos positivos](media/DLP-create-test-tune-false-positive-email.png)
 
Pero el usuario ve una sugerencia de directiva que advierte que el correo electrónico contiene información confidencial, en concreto, un número de licencia de conductor australiano.

![Opción para notificar un falso positivo en la sugerencia de Directiva](media/DLP-create-test-tune-policy-tip-closeup.png)

El usuario puede informar del falso positivo y el administrador puede comprobar por qué se ha producido. En el correo electrónico del informe de incidentes, el correo electrónico se marca como falso positivo.

![Informe de incidentes que muestra falso positivo](media/DLP-create-test-tune-false-positive-incident-report.png)

El caso de la licencia de conducir es un buen ejemplo para profundizar. La razón por la que se ha producido este falso positivo es que el tipo "licencia de conductor australiano" se desencadenará por cualquier cadena de 9 dígitos (incluso la que forme parte de una cadena de 10 dígitos), dentro de 300 caracteres de proximidad a las palabras clave "Sydney NSW" (no distingue entre mayúsculas y minúsculas). Por lo tanto, se desencadena por el número de teléfono y la firma de correo electrónico, solo porque el usuario se encuentra en Sydney.

Curiosamente, si "Sydney, NSW" tiene una coma, la Directiva DLP no se desencadena. No tengo la idea de por qué una coma tiene alguna diferencia, ni por qué otras ciudades y Estados de Australia no se incluyen en las palabras clave para el tipo de información de licencia de la conducción australiano, pero ahí va. Por lo tanto, ¿qué podemos hacer al respecto? Hay un par de opciones.

Una opción es quitar el tipo de información de licencia de la conducción australiano de la Directiva. Está ahí porque forma parte de la plantilla de directiva DLP, pero no se ve obligado a usarlo. Si solo está interesado en los números de archivo de impuestos y no en las licencias de conducir, basta con quitarlos. Por ejemplo, puede quitarla de la regla de volumen bajo de la Directiva, pero déjela en la regla de volumen alto para que se sigan detectando las listas de licencias de varios impulsores.

![Opción para eliminar el tipo de información confidencial de la regla](media/DLP-create-test-tune-delete-low-volume-rule.png)
 
Otra opción es simplemente aumentar el recuento de instancias, de modo que un bajo volumen de licencias de conducir solo se detecta cuando hay varias instancias.

![Opción para editar el recuento de instancias](media/DLP-create-test-tune-edit-instance-count.png)

Además de cambiar el recuento de instancias, también puede ajustar la precisión de coincidencia (o nivel de confianza). Si el tipo de información confidencial tiene varios patrones, puede ajustar la precisión de la coincidencia en la regla para que la regla coincida solo con modelos específicos. Por ejemplo, para ayudar a reducir los falsos positivos, puede establecer la precisión de coincidencia de la regla para que coincida solo con el patrón con el nivel de confianza más alto. Comprender cómo se calcula el nivel de confianza es un poco complicado (y más allá del alcance de esta publicación), pero esta es una buena explicación de [Cómo usar el nivel de confianza para ajustar las reglas](https://docs.microsoft.com/en-us/office365/securitycompliance/data-loss-prevention-policies#match-accuracy).

Por último, si desea que sea un poco más avanzada, puede personalizar cualquier tipo de información confidencial (por ejemplo, puede quitar "Sydney NSW" de la lista de palabras clave de la [licencia de conducción de Australia](https://docs.microsoft.com/en-us/office365/securitycompliance/what-the-sensitive-information-types-look-for#australia-drivers-license-number)) para eliminar el falso positivo que se ha activado. Para obtener información sobre cómo hacerlo con XML y PowerShell, vea este tema sobre la [Personalización de un tipo de información confidencial integrado](customize-a-built-in-sensitive-information-type.md).

## <a name="turn-off-a-dlp-policy"></a>Desactivar una directiva DLP

Cuando esté satisfecho de que su Directiva de DLP detecte de forma precisa y eficaz los tipos de información confidencial, y de que los usuarios finales estén preparados para tratar con las directivas que se encuentran en vigor, puede habilitar la Directiva.

![Opción para activar la Directiva](media/DLP-create-test-tune-turn-on-policy.png)
 
Si está esperando para ver cuándo tendrá efecto la Directiva, conéctese [a Office 365 Security _AMP_ Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) y ejecute el [cmdlet Get-DlpCompliancePolicy](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps) para ver la DistributionStatus.

![Ejecutar el cmdlet en PowerShell](media/DLP-create-test-tune-PowerShell.png)

Después de activar la Directiva DLP, debe ejecutar algunas pruebas finales de su propiedad para asegurarse de que se producen las acciones de directiva esperadas. Si intenta probar cosas como datos de tarjetas de crédito, hay sitios web en línea con información sobre cómo generar una tarjeta de crédito de ejemplo u otra información personal que pase las sumas de comprobación y active las directivas.

Las directivas que permiten invalidaciones de usuario presentan esa opción al usuario como parte de la sugerencia de directiva.

![Sugerencia de directiva que permite al usuario invalidar](media/DLP-create-test-tune-override-option.png)

Las directivas que restringen el contenido presentarán la advertencia al usuario como parte de la sugerencia de directiva e impedirán que envíen el correo electrónico.

![Sugerencia de directiva de que el contenido está restringido](media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a>Resumen

Las directivas de prevención de pérdida de datos son útiles para organizaciones de todos los tipos. La prueba de algunas directivas de DLP es un ejercicio de bajo riesgo debido al control que tiene sobre elementos como, por ejemplo, sugerencias de directivas, invalidaciones de usuarios finales e informes de incidentes. Puede probar silenciosamente algunas directivas de DLP para ver qué tipo de infracciones ya se están produciendo en su organización y, a continuación, crear directivas con tasas de falsos positivos bajos, educar a los usuarios sobre lo que se permite y no y, a continuación, implementar sus directivas DLP en el Organization.
