---
title: Puntuación de seguridad de Microsoft
description: Describe la puntuación segura de 365 de Microsoft, cómo se calculan los detalles y qué administradores de seguridad pueden esperar usarlos.
keywords: seguridad, malware, Microsoft 365, M365, calificación segura, centro de seguridad, acciones de mejora
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 981cb2e6820cb349ff1e2d101bf21d592c2191c6
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001163"
---
# <a name="microsoft-secure-score"></a>Puntuación de seguridad de Microsoft

Con la puntuación segura de Microsoft en el centro de seguridad 365 de Microsoft, puede tener mayor visibilidad y control sobre la postura de seguridad de su organización. Desde un panel centralizado, puede supervisar y mejorar la seguridad de las identidades, los datos, las aplicaciones, los dispositivos y la infraestructura de Microsoft 365.

La puntuación segura de Microsoft le ofrece una visualización sólida, la integración con otros productos de Microsoft, la comparación de sus puntuaciones con otras empresas, el filtrado por categoría y mucho más. Con la herramienta, puede completar acciones de mejora de la seguridad dentro de su organización y realizar un seguimiento del historial de su puntuación. La puntuación también puede reflejar Cuándo las soluciones de terceros han tratado las acciones de mejora recomendadas.  

## <a name="how-it-works"></a>Funcionamiento

Se le proporcionan puntos para configurar las características de seguridad recomendadas, realizar tareas relacionadas con la seguridad (como ver informes) o solucionar la acción de mejora con una aplicación o un software de terceros. Algunas acciones se puntuan para su finalización parcial, como la habilitación de la autenticación multifactor (MFA) para los usuarios. La seguridad siempre debe equilibrarse con la facilidad de uso y no todas las recomendaciones funcionarán para su entorno.

## <a name="required-permissions"></a>Permisos necesarios

Actualmente, para ver la puntuación segura de Microsoft, debe tener asignado uno de los siguientes roles en Azure Active Directory:

* Administrador global
* Administrador de seguridad
* Lector de seguridad

## <a name="rich-experiences--additional-security-recommendations"></a>Experiencias enriquecidas & recomendaciones de seguridad adicionales

En la puntuación segura de Microsoft, hemos agregado recomendaciones de Azure AD, Intune y Cloud App Security con las recomendaciones del centro de seguridad de Azure y ATP de Windows Defender próximamente. También hemos agregado más recomendaciones de seguridad de Office 365. Con información adicional y una mayor visibilidad en un conjunto más amplio de productos y servicios de Microsoft, puede confiar en la administración de los informes sobre el estado de seguridad de la organización. También puede obtener su puntuación mediante la [API de Microsoft Graph](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta).

Para ayudarle a la información que necesita con mayor rapidez, las recomendaciones de Microsoft se organizan en grupos:

* Identidad (estado de protección de las cuentas y roles de Azure AD)
* Datos (estado de protección de los documentos de Office 365)
* Dispositivo (estado de protección de los dispositivos; Las acciones de mejora de ATP de Windows Defender estarán disponibles próximamente)
* Aplicación (estado de protección de las aplicaciones en la nube y el correo electrónico)
* Infraestructura (estado de protección de los recursos de Azure; próximamente)

En la página información general sobre la calificación segura de Microsoft, puede ver cómo se dividen los puntos entre estos grupos y qué puntos están disponibles. La página de información general también es la ubicación para obtener una vista completa de la puntuación total, la tendencia histórica de la puntuación segura con comparaciones de los bancos de pruebas y las acciones de mejora ordenadas por prioridad que se pueden realizar para mejorar la puntuación. Puede usar estos datos para actuar y realizar grandes diferencias en su postura de seguridad.  

![Página principal](./media/secure-score/homepage-original.png)
de M365*figura 1: Página de introducción a la calificación segura de Microsoft*

## <a name="take-action-to-improve-your-score"></a>Tomar medidas para mejorar su puntuación

La ficha acciones de mejora enumera todas las recomendaciones de seguridad que se aplican a su inquilino junto con su estado (completado, no completado, resuelto a través de terceros y omitido). Puede buscar, filtrar y agrupar todos los controles.  La clasificación se basa en la evaluación que realiza Microsoft del valor de seguridad y del esfuerzo para completarse.

La puntuación segura de Microsoft no realiza un seguimiento de las acciones etiquetadas como [no puntuadas]. Puede seguir realizando acciones pero su finalización no afectará a su calificación. Si una acción hace un seguimiento de la puntuación segura de Microsoft en el futuro y ya la ha completado, la puntuación segura reflejará automáticamente el cambio.

Al hacer clic en una acción de mejora, aparece una volar hacia fuera. Para completar la acción, tiene algunas opciones:

1. Seleccione **Ver configuración** para ir a la pantalla de configuración y realizar el cambio. A continuación, obtendrá los puntos que merece la acción, visible en la parte superior de la volando. Los puntos pueden tardar hasta 24 horas en actualizarse.

2. Seleccione **resolver a través de terceros** porque la acción de mejora ya ha sido tratada por una aplicación o software de terceros. Obtendrá los puntos que merece la acción, de modo que la puntuación segura refleje mejor su postura de seguridad general. Si un tercero ya no cubre el control, puede marcar la acción de mejora como no completada. Tenga en cuenta que Microsoft no tendrá visibilidad sobre si se cumplen los requisitos de calificación si la acción de mejora se ha marcado como resuelta a través de terceros.

3. Seleccione **omitir** porque decidió aceptar el riesgo y no pasar la acción de mejora. Una vez que ignore una acción de mejora, se reducirá el número total de puntos de calificación seguros que puede alcanzar. Puede ver esta acción en el historial o deshacerla en cualquier momento.

4. Seleccione **revisar** porque la acción de mejora requiere que Revise regularmente una parte del entorno para obtener y conservar puntos. Por ejemplo, las reglas de reenvío de buzones deben revisarse cada semana para asegurarse de que los datos no se están exfiltrando desde la red. No es necesario realizar ningún cambio, pero se debe realizar una acción. Si revisa las reglas con regularidad, recibirá los puntos. Si no es así, se reducirá la puntuación.

![Página principal de M365](./media/secure-score/secure-score1x450.png) ![Página principal de M365](./media/secure-score/secure-score2x450.png)

*Figuras 2 & 3: controles flotantes de acciones de mejora*

## <a name="monitor-improvements-over-time"></a>Supervisar las mejoras a lo largo del tiempo

Puede ver un gráfico de la puntuación de su organización con el tiempo en la ficha **historial** . Esta vista incluye la media global, la media de la industria y un recuento de asientos similar, junto con todas las acciones realizadas en el intervalo de tiempo seleccionado. También puede personalizar un intervalo de fechas y filtrar por categoría.

La puntuación se calcula una vez al día (alrededor de 1:00 A.M. PST). Si realiza un cambio en una acción medida, la puntuación se actualizará automáticamente el día siguiente. También es importante tener en cuenta que otros portales muestran partes de la puntuación segura de Microsoft (como el centro de seguridad de Windows Defender). Si completa una acción de mejora y la puntuación aumenta en estos portales, la puntuación actualizada puede tardar hasta 24 horas en mostrarse en el centro de seguridad de Microsoft 365.  

## <a name="risk-awareness"></a>Conocimiento de riesgos

La puntuación segura de Microsoft es un resumen numérico de su postura de seguridad en función de las configuraciones del sistema, el comportamiento del usuario y otras medidas relacionadas con la seguridad; no es una medida absoluta de la probabilidad de que se infrinja el sistema o sus datos. En su lugar, representa en qué medida ha adoptado controles de seguridad en su entorno de Microsoft, lo que puede ayudar a compensar el riesgo de infracciones. Ningún servicio en línea está completamente inmune a las infracciones de seguridad y la puntuación segura no se debe interpretar como una garantía contra la infracción de seguridad de ninguna manera.

## <a name="we-want-to-hear-from-you"></a>Queremos conocer su opinión

Si tiene algún problema, háganoslo saber mediante la publicación de la comunidad de [seguridad, privacidad _AMP_ cumplimiento](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Estamos supervisando la comunidad y le proporcionaremos ayuda.
