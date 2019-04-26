---
title: Crear sitios de grupo en un entorno de desarrollo y prueba de campaña política
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/21/2018
ms.audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom: ''
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 'Resumen: Cree sitios de grupo de SharePoint Online públicos, privados, confidenciales o extremadamente confidenciales en el entorno de desarrollo y prueba de una campaña política.'
ms.openlocfilehash: 29220c83eb207d58586b39d101e7139dc6ddf94a
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259188"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a>Crear sitios de grupo en un entorno de desarrollo y prueba de campaña política

 **Resumen:** Cree sitios de grupo de SharePoint Online públicos, privados, confidenciales o extremadamente confidenciales en un entorno de desarrollo y prueba para una campaña política. 
  
Siga las instrucciones de este artículo para crear un entorno de desarrollo y prueba que incluya los cuatro tipos distintos de sitios de grupo de SharePoint Online para la solución de [Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md). Estos sitios se describen en detalle en el tema 10, titulado **SharePoint y OneDrive para la Empresa**.
  
## <a name="phase-1-create-your-political-campaign-devtest-environment"></a>Fase 1: Crear un entorno de desarrollo y prueba de campaña política

En primer lugar, siga las instrucciones de [Configurar grupos y usuarios en un entorno de desarrollo y prueba de campaña política](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) para crear las suscripciones, los usuarios y los grupos.
  
## <a name="phase-2-create-office-365-labels"></a>Fase 2: Crear etiquetas de Office 365

En esta fase se crean las etiquetas para los diferentes niveles de seguridad de las carpetas de documentos de sitios de grupo de SharePoint Online.
  
1. Si es necesario, inicie sesión en el centro de administración con las credenciales de la cuenta de administrador global de la suscripción de evaluación. Para obtener ayuda, vea [Dónde iniciar sesión en Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. En la pestaña **Inicio de Microsoft Office**, haga clic en el icono **Administrador**.
    
3. En la nueva pestaña **Centro de administración de Office** del explorador, haga clic en **Centros de administración Seguridad &amp; Cumplimiento**.
    
4. En la nueva pestaña **Inicio - Seguridad y cumplimiento** del explorador, haga clic en **Clasificaciones > Etiquetas**.
    
5. En el panel **Inicio > Etiquetas**, haga clic en **Crear una etiqueta**.
    
6. En el panel **Asignar un nombre a la etiqueta**, escriba **Interna** y haga clic en **Siguiente**.
    
7. En el panel **Configuración de etiquetas**, haga clic en **Siguiente**.
    
8. En el panel **Revise su configuración**, haga clic en **Crear esta etiqueta** y luego en **Cerrar**.
    
9. Repita los pasos del 5 al 8 para estas etiquetas adicionales:
    
  - Private
    
  - Confidencial
    
  - Extremadamente confidencial
    
10. En el panel **Inicio > Etiquetas**, haga clic para **Publish labels** (Publicar etiquetas).
    
11. En el panel **Elegir etiquetas para publicar**, haga clic en **Elegir etiquetas para publicar**.
    
12. En el panel de **elección de etiquetas**, haga clic en **Agregar** y seleccione las cuatro etiquetas.
    
13. Haga clic en **Listo**.
    
14. En el panel **Elegir etiquetas para publicar**, haga clic en **Siguiente**.
    
15. En el panel **Elegir ubicaciones**, haga clic en **Siguiente**.
    
16. En el panel **Escriba un nombre para la directiva**, escriba **Campaña** en **Nombre** y haga clic en **Siguiente**.
    
17. En el panel **Revise su configuración**, haga clic en **Publicar etiquetas** y luego en **Cerrar**.
    
## <a name="phase-3-create-your-sharepoint-online-team-sites"></a>Fase 3: Crear los sitios de grupo de SharePoint Online

En esta fase se crean y configuran los sitios de grupo de SharePoint Online para la campaña política correspondientes a los cuatro tipos de sitios de grupo de SharePoint Online.
  
### <a name="campaign-wide-team-site"></a>Sitio de grupo de toda la campaña

Para crear un sitio de grupo público de línea base de SharePoint Online, haga lo siguiente:
  
1. Si es necesario, use un explorador en el equipo local e inicie sesión en el centro de administración ([https://admin.microsoft.com](https://admin.microsoft.com)) con la cuenta de administrador global.
    
2. En la lista de iconos, haga clic en **SharePoint**.
    
3. En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.
    
4. En la página **Crear un sitio**, haga clic en **Sitio de grupo**.
    
5. En **Nombre del sitio**, escriba **Toda la campaña**. 
    
6. En **Team site description** (Descripción del sitio de grupo), escriba **Sitio de SharePoint para toda la campaña**.
    
7. En **Configuración de privacidad**, seleccione **Public – anyone in the organization can access this site** (Público: cualquier usuario de la organización tiene acceso a este sitio) y haga clic en **Siguiente**.
    
8. En el panel **Who do you want to add?** (Usuarios que quiere agregar), haga clic en **Finalizar**.
    
Después, configure la carpeta de documentos del sitio de grupo Toda la campaña con la etiqueta Interna.
  
1. En la pestaña **Toda la campaña-Inicio** del explorador, haga clic en **Documentos**.
    
2. Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.
    
3. En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).
    
4. En **Configuración-Aplicar etiqueta**, seleccione **Interna** y haga clic en **Guardar**.
    
### <a name="campaign-project-1-team-site"></a>Sitio de grupo del proyecto de campaña 1

Para crear un sitio de grupo privado de línea base de SharePoint Online para un proyecto dentro de la organización, haga lo siguiente:
  
1. Si es necesario, use un explorador en el equipo local e inicie sesión en el centro de administración ([https://admin.microsoft.com](https://admin.microsoft.com)) con la cuenta de administrador global.
    
2. En la lista de iconos, haga clic en **SharePoint**.
    
3. En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.
    
4. En la página **Crear un sitio**, haga clic en **Sitio de grupo**.
    
5. En **Nombre del sitio**, escriba **Proyecto de campaña 1**. 
    
6. En **Team site description** (Descripción del sitio de grupo), escriba **Sitio de SharePoint para el proyecto de campaña 1**.
    
7. En **Configuración de privacidad**, seleccione **Private - only members can access this site** (Privado: solo los miembros tienen acceso a este sitio) y haga clic en **Siguiente**.
    
8. En el panel **Who do you want to add?** (Usuarios que quiere agregar), haga clic en **Finalizar**.
    
Después, configure la carpeta de documentos del sitio de grupo Proyecto de campaña 1 con la etiqueta Privada.
  
1. En la pestaña **Proyecto de campaña 1-Inicio** del explorador, haga clic en **Documentos**.
    
2. Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.
    
3. En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).
    
4. En **Configuración-Aplicar etiqueta**, seleccione **Privado** y haga clic en **Guardar**.
    
### <a name="campaign-marketing-team-site"></a>Sitio de grupo Marketing de la campaña

Para crear un sitio de grupo aislado de SharePoint Online de nivel confidencial para recursos de marketing de la campaña, haga lo siguiente:
  
1. Abra un explorador en el equipo local e inicie sesión en el centro de administración ([https://admin.microsoft.com](https://admin.microsoft.com)) con la cuenta de administrador global.
    
2. En la lista de iconos, haga clic en **SharePoint**.
    
3. En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.
    
4. En la página **Crear un sitio**, haga clic en **Sitio de grupo**.
    
5. En **Team site name** (Nombre del sitio de grupo), escriba **Marketing de la campaña**.
    
6. En **Team site description** (Descripción del sitio de grupo), escriba **Sitio de SharePoint para marketing de la campaña (confidencial)**.
    
7.  En **Configuración de privacidad**, seleccione **Private - only members can access this site** (Privado: solo los miembros tienen acceso a este sitio) y haga clic en **Siguiente**.
    
8. En el panel **Who do you want to add?** (Usuarios que quiere agregar), haga clic en **Finalizar**.
    
9. En la barra de herramientas de la nueva pestaña **Campaign marketing** (Marketing de la campaña) del explorador, haga clic en el icono de configuración y luego en **Permisos del sitio**.
    
10. En el panel **Permisos del sitio**, haga clic en **Advanced permissions settings** (Configuración de permisos avanzada).
    
11. En la nueva pestaña **Permisos** del explorador, haga clic en **Configuración de solicitud de acceso**.
    
12. En el cuadro de diálogo **Configuración de solicitud de acceso**, desactive **Permitir que los miembros compartan el sitio y archivos y carpetas individuales** y **Permitir a los miembros invitar a otros al grupo de miembros del sitio**, escriba **ITAdmin1@**<your organization name> **.onmicrosoft.com** en **Enviar todas las solicitudes de acceso** y luego haga clic en **Aceptar**.
    
13. Haga clic en **Marketing de la campaña-Miembros** en la lista.
    
14. En la página **Personas y grupos**, haga clic en **Nuevo**.
    
15. En el cuadro de diálogo **Compartir**, escriba **Personal directivo y estratégico**, selecciónelo y haga clic en **Compartir**.
    
16. Repita los pasos 14 y 15 para grupo **Personal de Análisis** y la cuenta de usuario **Regular1**.
    
17. Haga clic en el botón Atrás del explorador.
    
18. Haga clic en **Marketing de la campaña-Propietarios** en la lista.
    
19. En la página **Personas y grupos**, haga clic en **Nuevo**.
    
20. En el cuadro de diálogo **Compartir**, escriba **Personal de TI**, selecciónelo y haga clic en **Compartir**.
    
21. Haga clic en el botón Atrás del explorador.
    
22. Cierre la pestaña **Personas y grupos** del explorador, haga clic en la pestaña **Marketing de la campaña-Inicio** del explorador y cierre el panel **Permisos del sitio**.
    
Estos son los resultados de la configuración de los permisos:
  
- El grupo **Marketing de la campaña-Miembros** de SharePoint solo contiene el grupo **Personal directivo y estratégico** (que contiene las cuentas de usuario Candidate, ChiefOfStaff y Strategic1), el grupo **Marketing de la campaña** (que contiene la cuenta de usuario de administrador global), el grupo **Personal de Análisis** (que contiene la cuenta de usuario DataScientist1) y la cuenta de usuario**Regular1**.
    
- El grupo **Marketing de la campaña-Propietarios** de SharePoint solo contiene el grupo **Personal de TI** (que solo contiene las cuentas de usuario ITAdmin1 y ITAdmin2).
    
- El grupo **Marketing de la campaña-Visitantes** de SharePoint no contiene grupos ni cuentas de usuario.
    
- Los miembros no pueden modificar los permisos de nivel de sitio (esto solo pueden hacerlo los miembros del grupo **Marketing de la campaña-Propietarios**).
    
- Otras cuentas de usuario no pueden acceder al sitio ni a sus recursos, pero pueden pedir acceso al sitio, que enviará un correo electrónico al buzón de la cuenta de usuario ITAdmin1.
    
Después, configure la carpeta de documentos del sitio de grupo Marketing de la campaña con la etiqueta Confidencial.
  
1. En la pestaña **Marketing de la campaña-Inicio** del explorador, haga clic en **Documentos**.
    
2. Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.
    
3. En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).
    
4. En **Configuración-Aplicar etiqueta**, seleccione **Confidencial** y haga clic en **Guardar**.
    
Después, configure una directiva de prevención de pérdida de datos (DLP) que notifique a los usuarios cada vez que compartan un documento en un sitio de grupo de SharePoint Online con la etiqueta Confidencial fuera de la organización. Esta directiva DLP se aplicará a los recursos del sitio Marketing de la campaña.
  
1. En la pestaña **Inicio de Microsoft Office** del explorador, haga clic en el icono **Seguridad y cumplimiento**.
    
2. En la nueva pestaña **Seguridad y cumplimiento** del explorador, haga clic en **Prevención de pérdida de datos > Directiva**.
    
3. En el panel **Prevención de pérdida de datos**, haga clic en **+ Crear una directiva**.
    
4. En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.
    
5. En el panel **Escriba un nombre para la directiva**, escriba **Sitios de grupo de SharePoint Online de etiqueta Confidencial** en **Nombre** y haga clic en **Siguiente**.
    
6. En el panel **Elegir ubicaciones**, haga clic en **Let me choose specific locations** (Permitir elegir ubicaciones concretas) y luego en **Siguiente**.
    
7. En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange** y **Cuentas de OneDrive** y haga clic en **Siguiente**.
    
8. En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Editar**.
    
9. En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas**.
    
10. En el panel **Etiquetas**, haga clic en **+ Agregar**, seleccione la etiqueta **Confidencial**, haga clic en **Agregar** y luego en **Listo**.
    
11. En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.
    
12. En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Siguiente**.
    
13. En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), haga clic en **Customize the tip and email** (Personalizar la sugerencia y el correo electrónico).
    
14. En el panel **Customize policy tips and email notifications** (Personalizar sugerencias de directiva y notificaciones de correo electrónico), haga clic en **Customize the policy tip text** (Personalizar el texto de la sugerencia de directiva).
    
15. En el cuadro de texto, escriba o pegue lo siguiente:
    
  - Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en Archivo, Proteger documento y Cifrar con contraseña y, luego, especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.
    
16. Haga clic en **Aceptar**.
    
17. En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), desactive la casilla **Block people from sharing, and restrict access to shared content** (Evitar que los usuarios puedan compartir y restringir el acceso al contenido compartido) y haga clic en **Siguiente**.
    
18. En el panel **Do you want to turn on the policy or test things out first?** (¿Desea activar la directiva o probarla primero?), haga clic en **Yes, turn it on right away** (Sí, activarla inmediatamente) y luego en **Siguiente**.
    
19. En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.
    
### <a name="campaign-strategy-team-site"></a>Sitio de grupo Estrategia de la campaña

Para crear un sitio de grupo aislado de SharePoint Online de nivel extremadamente confidencial para recursos estratégicos de la campaña, haga lo siguiente:
  
1. Si es necesario, use un explorador en el equipo local e inicie sesión en el centro de administración ([https://admin.microsoft.com](https://admin.microsoft.com)) con la cuenta de administrador global.
    
2. En la lista de iconos, haga clic en **SharePoint**.
    
3. En la nueva pestaña **SharePoint** del explorador, haga clic en **+ Crear sitio**.
    
4. En la página **Crear un sitio**, haga clic en **Sitio de grupo**.
    
5. En **Team site name** (Nombre del sitio de grupo), escriba **Estrategia de la campaña**.
    
6. En **Team site description** (Descripción de sitio de grupo), escriba **Sitio de SharePoint para la estrategia de la campaña (extremadamente confidencial)**.
    
7.  En **Configuración de privacidad**, seleccione **Private - only members can access this site** (Privado: solo los miembros tienen acceso a este sitio) y haga clic en **Siguiente**.
    
8. En el panel **Who do you want to add?** (Usuarios que quiere agregar), haga clic en **Finalizar**.
    
9. En la barra de herramientas de la nueva pestaña **Estrategia de la campaña** del explorador, haga clic en el icono de configuración y luego en **Permisos del sitio**.
    
10. En el panel **Permisos del sitio**, haga clic en **Advanced permissions settings** (Configuración de permisos avanzada).
    
11. En la nueva pestaña **Permisos** del explorador, haga clic en **Configuración de solicitud de acceso**.
    
12. En el cuadro de diálogo **Configuración de solicitud de acceso**, desactive **Permitir que los miembros compartan el sitio y archivos y carpetas individuales** y **Permitir a los miembros invitar a otros al grupo de miembros del sitio** (de forma que las tres casillas estén desactivadas) y haga clic en **Aceptar**.
    
13. Haga clic en **Estrategia de la campaña-Miembros** en la lista.
    
14. En la página **Personas y grupos**, haga clic en **Nuevo**.
    
15. En el cuadro de diálogo **Compartir**, escriba **Personal directivo y estratégico**, selecciónelo y haga clic en **Compartir**.
    
16. Haga clic en **Estrategia de la campaña-Propietarios** en la lista.
    
17. En la página **Personas y grupos**, haga clic en **Nuevo**.
    
18. En el cuadro de diálogo **Compartir**, escriba **Personal de TI**, selecciónelo y haga clic en **Compartir**.
    
19. Haga clic en el botón Atrás del explorador.
    
20. Cierre la pestaña **Personas y grupos** del explorador, haga clic en la pestaña **-Inicio** del explorador y cierre el panel **Permisos del sitio**.
    
Estos son los resultados de la configuración de los permisos:
  
- El grupo **Estrategia de la campaña-Miembros** de SharePoint solo contiene el grupo **Personal directivo y estratégico** [Directivos] \(que solo contiene las cuentas de usuario Candidate, ChiefOfStaff, and Strategic1) y el grupo **Estrategia de la campaña** (que solo contiene la cuenta de usuario de administrador global).
    
- El grupo **Estrategia de la campaña-Propietarios** de SharePoint solo contiene el grupo **Personal de TI** (que solo contiene las cuentas de usuario ITAdmin1 y ITAdmin2).
    
- El grupo **Estrategia de la campaña-Visitantes** de SharePoint no contiene grupos ni cuentas de usuario.
    
- Los miembros no pueden modificar los permisos de nivel de sitio (esto solo pueden hacerlo los miembros del grupo **Estrategia de la campaña-Propietarios**).
    
- Otras cuentas de usuario no tienen acceso al sitio o a sus recursos ni pedir acceso al sitio. Los permisos adicionales para el sitio deben ser asignados por el administrador global o por un miembro del grupo **Estrategia de la campaña-Propietarios**.
    
Después, configure la carpeta de documentos del sitio de grupo Estrategia de la campaña con la etiqueta Extremadamente confidencial.
  
1. En la pestaña **Estrategia de la campaña-Inicio** del explorador, haga clic en **Documentos**.
    
2. Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.
    
3. En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).
    
4. En **Configuración-Aplicar etiqueta**, seleccione **Extremadamente confidencial** y haga clic en **Guardar**.
    
Después, configure una directiva DLP que bloquee a los usuarios cuando compartan un documento en un sitio de grupo de SharePoint Online con la etiqueta Extremadamente confidencial fuera de la organización. Esta directiva DLP se aplicará a los recursos del sitio Estrategia de la campaña.
  
1. Si fuera necesario, use un explorador en el equipo local e inicie sesión en el centro de administración ([https://admin.microsoft.com](https://admin.microsoft.com)) con una cuenta que tenga el rol Administrador de seguridad o Administrador de la compañía.
    
2. En la pestaña **Inicio de Microsoft Office** del explorador, haga clic en el icono de **Seguridad y cumplimiento**.
    
3. En la nueva pestaña **Seguridad y cumplimiento** del explorador, haga clic en **Prevención de pérdida de datos > Directiva**.
    
4. En el panel **Prevención de pérdida de datos**, haga clic en **+ Crear una directiva**.
    
5. En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.
    
6. En el panel **Escriba un nombre para la directiva**, escriba **Sitios de grupo de SharePoint Online de etiqueta Extremadamente confidencial** en **Nombre** y haga clic en **Siguiente**.
    
7. En el panel **Elegir ubicaciones**, haga clic en **Let me choose specific locations** (Permitir elegir ubicaciones concretas) y luego en **Siguiente**.
    
8. En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange** y **Cuentas de OneDrive** y haga clic en **Siguiente**.
    
9. En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Editar**.
    
10. En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas**.
    
11. En el panel **Etiquetas**, haga clic en **+ Agregar**, seleccione la etiqueta **Extremadamente confidencial**, haga clic en **Agregar** y luego en **Listo**.
    
12. En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.
    
13. En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Siguiente**.
    
14. En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), haga clic en **Customize the tip and email** (Personalizar la sugerencia y el correo electrónico).
    
15. En el panel **Customize policy tips and email notifications** (Personalizar sugerencias de directiva y notificaciones de correo electrónico), haga clic en **Customize the policy tip text** (Personalizar el texto de la sugerencia de directiva).
    
16. En el cuadro de texto, escriba o pegue lo siguiente:
    
  - Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en Archivo, Proteger documento y Cifrar con contraseña y, luego, especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.
    
17. Haga clic en **Aceptar**.
    
18. En el panel **What do you want to do if we detect sensitive info?** (¿Qué desea hacer si se detecta información confidencial?), seleccione **Require a business justification to override** (Exigir una justificación de empresa para invalidar) y haga clic en **Siguiente**.
    
19. En el panel **Do you want to turn on the policy or test things out first?** (¿Desea activar la directiva o probarla primero?), haga clic en **Yes, turn it on right away** (Sí, activarla inmediatamente) y luego en **Siguiente**.
    
20. En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.
    
Siga las instrucciones de [Activate Azure RMS with the Microsoft 365 admin center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365) (Activación de Azure RMS con el Centro de administración de Microsoft 365).
  
Después, siga estos pasos para configurar Azure Information Protection con una nueva directiva con ámbito y la subetiqueta de protección y permisos:
  
1. Inicie sesión en el centro de administración con una cuenta que tenga el rol de Administrador de seguridad o Administrador de la compañía. Para obtener ayuda, vea [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).
    
2. En una pestaña independiente del explorador, vaya a Azure Portal ([https://portal.azure.com](https://portal.azure.com)).
    
3. Si es la primera vez que configura Azure Information Protection, vea [estas instrucciones](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).
    
4. En el panel de lista, haga clic en **Más servicios**, escriba **information** y haga clic en **Azure Information Protection**.

5. Haga clic en **Etiquetas**.
    
6. Haga clic con el botón derecho en la etiqueta **Extremadamente confidencial** y después seleccione **Agregar una subetiqueta**.
    
7. Escriba **Estrategia de la campaña** en **Nombre** y **Etiqueta para los documentos del sitio de grupo de estrategia de la campaña** en **Descripción**.
    
8. En **Establecer permisos para documentos y correos electrónicos que contengan esta etiqueta**, haga clic en **Proteger**.
    
9. En la sección **Protección**, haga clic en **Azure (clave de nube)**.
    
10. En la hoja **Protección**, en **Configuración de protección**, haga clic en **+ Agregar permisos**.
    
11. En la hoja **Agregar permisos**, en **Especificar usuarios y grupos**, haga clic en **+ Examinar directorio**.
    
12. En el panel **Usuarios y grupos de AAD**, seleccione **Personal directivo y estratégico** y haga clic en **Seleccionar**.
    
13. En **Seleccionar permisos del conjunto predefinido o personalizado**, haga clic en **Personalizar** y después active las casillas **Ver derechos**, **Editar contenido**, **Guardar**, **Responder** y **Responder a todos**.
    
14. Haga clic en **Aceptar** dos veces.
    
15. En la hoja **Subetiqueta**, haga clic en **Guardar** y, después, seleccione **Aceptar**.

16. En la hoja **Azure Information Protection**, haga clic en **Directivas > + Agregar una directiva**.
    
17. Escriba **Estrategia de la campaña** en **Nombre** y **Documentos del sitio de grupo de estrategia de la campaña** en **Descripción**.
    
18. Haga clic en **Seleccionar a qué usuarios o grupos se aplica esta directiva > Usuarios o grupos** y seleccione **Personal directivo y estratégico**.
    
19. Haga clic en **Seleccionar > Aceptar**.

20. Haga clic en **Agregar o quitar etiquetas**. En el panel **Directiva: Agregar o quitar etiquetas**, seleccione **Estrategia de la campaña** y después haga clic en **Aceptar**.   

21. Haga clic en **Guardar**y después en **Aceptar**.
  
Ahora ya puede crear documentos en estos cuatro sitios y probar el acceso a ellos con diferentes cuentas de usuario. 
  
Para proteger un documento con Azure Information Protection y esta nueva etiqueta, debe [instalar el cliente de Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/install-client-app) en un equipo de prueba, instalar Office desde el Centro de administración y luego iniciar sesión desde Microsoft Word con una cuenta del grupo **Personal directivo y estratégico** de la suscripción de evaluación.
  
## <a name="see-also"></a>Vea también

[Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[Configurar grupos y usuarios en un entorno de desarrollo y prueba de campaña política](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)
  
[Guías del entorno de pruebas de adopción de la nube (TLG)](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
[Adopción de la nube y soluciones híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




