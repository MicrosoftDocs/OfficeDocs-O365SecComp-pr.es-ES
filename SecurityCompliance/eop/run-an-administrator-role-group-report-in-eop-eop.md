---
title: 'Ejecutar un informe de grupo de roles de administrador en EOP '
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: Los administradores pueden aprender a ejecutar un informe de grupo de roles de administrador en Exchange Online Protection (EOP). Este informe registra cuando un administrador agrega o quita miembros de grupos de roles de administrador, Microsoft Exchange Online Protection (EOP) registra cada ocurrencia.
ms.openlocfilehash: 6973574ca1eeabee85dd57bd087ba5d0675da084
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676523"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a>Ejecutar un informe de grupo de roles de administrador en EOP

 Cuando un administrador agrega o quita miembros de grupos de roles de administrador, Exchange Online Protection (EOP) registra cada ocurrencia. Al ejecutar un informe de grupo de roles de administrador en el centro de administración de Exchange (EAC), las entradas se muestran como resultados de búsqueda e incluyen los grupos de funciones afectados, quién cambió la pertenencia al grupo de roles y cuándo se realizaron las actualizaciones de pertenencia. Use este informe para supervisar los cambios en los permisos administrativos asignados a los usuarios de la organización.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Tiempo estimado para finalizar: 2 minutos

- Para abrir el centro de administración de Exchange, vea [centro de administración de Exchange en Exchange Online Protection](../exchange-admin-center-in-exchange-online-protection-eop.md).

- Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el Sección "Informes" del tema [Permisos de características en EOP](feature-permissions-in-eop.md).

- Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> ¿Problemas? Solicite ayuda en el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .
  
## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Usar el EAC para ejecutar un informe de grupo de roles de administrador

Ejecute el informe de grupo de roles de administrador para buscar los cambios en los grupos de roles de administración de la organización dentro de un período de tiempo determinado.
  
1. En el EAC, vaya a **Administración de cumplimiento** \> **Auditoría** y haga clic en **Ejecutar un informe de grupo de roles de administrador**.

2. Elija la **Fecha de inicio** y la **Fecha de finalización**. De manera predeterminada, el informe busca los cambios efectuados en los grupos de roles de administrador en las últimas dos semanas.

3. Para ver los cambios de un determinado grupo de roles, haga clic en **Seleccionar grupos de roles**. Seleccione el grupo o los grupos de roles en el siguiente cuadro de diálogo y haga clic en **Aceptar**. También puede dejar el campo en blanco para buscar todos los grupos de roles cambiados.

4. Haga clic en **Buscar**.

Si se encuentran cambios con los criterios especificados, aparecerán en el panel de resultados. Haga clic en un grupo de roles de los resultados de la búsqueda para ver los cambios en el panel de detalles.
  
## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Si se ejecutó correctamente un informe de grupo de roles de administrador, los grupos de roles que cambiaron dentro del intervalo de fechas se muestran en el panel de resultados de la búsqueda. Si no hay resultados, entonces no se hicieron cambios a los grupos de funciones dentro del intervalo de fechas especificado. Si cree que debería haber resultados, cambie el intervalo de fechas y vuelva a ejecutar el informe.
  
## <a name="monitor-changes-to-role-group-membership"></a>Supervisión de cambios en la pertenencia a grupos de funciones

Cuando se agregan miembros a un grupo de funciones, o se quitan de él, los resultados de la búsqueda mostrados en el panel de detalles indican que la pertenencia al grupo de funciones se ha actualizado y enumera los miembros actuales. En los resultados no se indica explícitamente el usuario que se agregó o quitó.
  
Para determinar si un usuario se agregó o quitó, tiene que comparar dos entradas independientes en el informe. Por ejemplo, veamos las siguientes entradas de registro para el grupo de roles **Servicio de asistencia**:
  
> 1/27/2018 4:43 PM <br> Administrador <br> Miembros actualizados: Administrator;annb,florencef;pilarp <br> 2/06/2018 10:09 A.M. <br> Administrador <br> Miembros actualizados: Administrator;annb;florencef;pilarp;tonip <br> 2/19/2018 2:12 PM <br> Administrador <br> Miembros actualizados: Administrator;annb;florencef;tonip

En este ejemplo, la cuenta de usuario Administrador realizó los siguientes cambios:
  
- El 2/06/2018 agrega el usuario tonip.

- El 2/19/2018, eliminó el usuario pilarp.
