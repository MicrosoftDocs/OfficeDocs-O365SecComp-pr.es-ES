---
title: Administrador de cumplimiento de Microsoft y el RGPD
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: El administrador de cumplimiento de Microsoft es una herramienta gratuita de evaluación de riesgos basada en flujos de trabajo en el portal de confianza de servicios de Microsoft. El administrador de cumplimiento le permite realizar un seguimiento, asignar y comprobar actividades de cumplimiento normativo relacionadas con los servicios en la nube de Microsoft.
ms.openlocfilehash: a082d069aced13aa9260a1a856d942c4feb7dd4b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152102"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a>Administrador de cumplimiento de Microsoft y el RGPD

El Reglamento General de protección de datos (RGPD) aprobado por la Unión Europea puede afectar a su estrategia de cumplimiento y a las acciones de mandato necesarias para administrar la información de usuarios y clientes que se usa en el administrador de cumplimiento.

## <a name="user-privacy-settings"></a>Configuración de privacidad del usuario

Algunas reglamentaciones requieren que una organización tenga que eliminar datos del historial del usuario. El administrador de cumplimiento proporciona funciones de **configuración de privacidad del usuario** que permiten a los administradores:
  
- [Buscar un usuario](#search-for-a-user)
- [Exportar un informe de historial de datos de cuenta](#export-a-report-of-account-data-history)
- [Eliminar el historial de datos de usuarios](#delete-user-data-history)
  
## <a name="search-for-a-user"></a>Buscar un usuario

Para buscar una cuenta de usuario:
  
1. Escriba el alias de correo electrónico del usuario (la información a la izquierda del símbolo @) y elija el nombre del dominio en la lista de sufijos de dominio de la derecha. En el caso de organizaciones con varios dominios registrados, compruebe el sufijo de nombre de dominio para asegurarse de que es correcto.

2. Cuando se haya escrito correctamente el nombre de usuario, seleccione **Buscar**.

3. Para las cuentas de usuario que no se devuelven, se muestra "usuario no encontrado" en la página. Compruebe la información de la dirección de correo del usuario y realice las correcciones necesarias. Para volver a intentarlo, seleccione **Buscar**.

4. Para las cuentas de usuario devueltas, el texto del botón cambia de **búsqueda** a **borrado**. Esto indica que la cuenta de usuario devuelta es el contexto operativo de las funciones adicionales y que estas funciones se aplican a esta cuenta de usuario.

5. Para borrar los resultados de la búsqueda y buscar a otro usuario, seleccione **Borrar**.

## <a name="export-a-report-of-account-data-history"></a>Exportar un informe de historial de datos de cuenta

Para cada cuenta de usuario identificada, puede generar un informe de dependencias vinculadas a esta cuenta. Esta información le permite reasignar elementos de acción abiertos o garantizar el acceso a pruebas cargadas anteriormente.
  
 Para generar y exportar un informe:
  
1. Seleccione **exportar** para generar y descargar un informe de los elementos de acción de control del administrador de cumplimiento asignados actualmente a la cuenta de usuario devuelta y la lista de documentos cargados por dicho usuario. Si no hay ninguna acción asignada o documentos cargados, un mensaje de error indica "no hay datos para este usuario".

2. El informe se descarga en segundo plano en la ventana del explorador activa si no ve un elemento emergente de descarga que desea comprobar el historial de descargas del explorador.

3. Abra el documento para revisar los datos del informe.

> [!IMPORTANT]
> Este no es un informe histórico que conserva y muestra los cambios de estado en el historial de asignación de elementos de acción. El informe generado es una instantánea de los elementos de acción de control asignados en el momento en que se ejecuta el informe (fecha y marca de tiempo escrita en el informe). Por ejemplo, cualquier reasignación posterior de los elementos de acción dará lugar a datos diferentes del informe de instantáneas si este informe se genera de nuevo para el mismo usuario.
  
## <a name="delete-user-data-history"></a>Eliminar el historial de datos de usuarios

Establece todos los elementos de acción de control asignados al usuario devuelto en "sin asignar". Establece el valor **cargado por** en todos los documentos cargados por el usuario devuelto en ' usuario quitado '.
  
Para eliminar el elemento de acción de la cuenta de usuario y el historial de carga de documentos:
  
1. Seleccione **eliminar**.

    Se muestra un cuadro de diálogo de confirmación, "*esto quita todas las asignaciones de elementos de acción de control y el historial de carga de documentos para el usuario seleccionado. Esta acción es permanente. ¿Está seguro de que desea continuar?*"

2. Para continuar, seleccione **Aceptar**; en caso contrario, seleccione **Cancelar**.