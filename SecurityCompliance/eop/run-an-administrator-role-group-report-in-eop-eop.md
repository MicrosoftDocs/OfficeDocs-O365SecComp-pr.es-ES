---
title: 'Ejecutar un informe de grupo de roles de administrador en EOP '
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: Cuando un administrador agrega o quita miembros de grupos de roles de administrador, Microsoft Exchange Online Protection (EOP) registra todas las ocurrencias.
ms.openlocfilehash: 752def771d95fcfbb3f7cbe0bc86a33b3967716d
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692719"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a>Ejecutar un informe de grupo de roles de administrador en EOP 

 Cuando un administrador agrega o quita miembros de grupos de roles de administrador, Microsoft Exchange Online Protection (EOP) registra todas las ocurrencias. Si se ejecuta un informe de grupo de roles de administrador en el Centro de administración de Exchange, las entradas se muestran como resultados de búsqueda e incluyen los grupos de roles afectados, quién cambió la pertenencia a un grupo de roles y cuándo, y las pertenencias que se actualizaron. Use este informe para supervisar los cambios en los permisos administrativos asignados a los usuarios de la organización.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Tiempo estimado para finalizar: 2 minutos
    
- Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el Sección "Informes" del tema [Permisos de características en EOP](feature-permissions-in-eop.md). 
    
- Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte **Keyboard shortcuts in Exchange 2013**.
    
> [!TIP]
> ¿Tiene algún problema? Solicite ayuda en los foros de Exchange. Visite los foros en [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Usar el EAC para ejecutar un informe de grupo de roles de administrador

Ejecute el informe de grupo de roles de administrador para ver los cambios hechos en los grupos de roles de administración de la organización en un período específico.
  
1. En el EAC, vaya a **Administración de cumplimiento** \> **Auditoría** y haga clic en **Ejecutar un informe de grupo de roles de administrador**.
    
2. Elija la **Fecha de inicio** y la **Fecha de finalización**. De manera predeterminada, el informe busca los cambios efectuados en los grupos de roles de administrador en las últimas dos semanas.
    
3. Para ver los cambios de un determinado grupo de roles, haga clic en **Seleccionar grupos de roles**. Seleccione el grupo o los grupos de roles en el siguiente cuadro de diálogo y haga clic en **Aceptar**. También puede dejar el campo en blanco para buscar todos los grupos de roles cambiados.
    
4. Haga clic en **Buscar**.
    
Si se encuentran cambios con los criterios especificados, aparecerán en el panel de resultados. Haga clic en un grupo de roles de los resultados de la búsqueda para ver los cambios en el panel de detalles.
  
## <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se completó correctamente?

Si se ejecutó correctamente un informe de grupo de roles de administrador, los grupos de roles que cambiaron dentro del intervalo de fechas se muestran en el panel de resultados de la búsqueda. Si no hay resultados, entonces no se hicieron cambios a los grupos de funciones dentro del intervalo de fechas especificado. Si cree que debería haber resultados, cambie el intervalo de fechas y vuelva a ejecutar el informe.
  
## <a name="monitor-changes-to-role-group-membership"></a>Supervisión de cambios en la pertenencia a grupos de funciones

Cuando se agregan miembros a un grupo de funciones, o se quitan de él, los resultados de la búsqueda mostrados en el panel de detalles indican que la pertenencia al grupo de funciones se ha actualizado y enumera los miembros actuales. En los resultados no se indica explícitamente el usuario que se agregó o quitó.
  
Para determinar si un usuario se agregó o quitó, tiene que comparar dos entradas independientes en el informe. Por ejemplo, veamos las siguientes entradas de registro para el grupo de roles **Servicio de asistencia**: 
  
 **27/01/2013 16:43:00**
  
 **Administrador**
  
 **Miembros actualizados: Administrator;annb,florencef;pilarp**
  
 **06/02/2013 10:09:00**
  
 **Administrador**
  
 **Miembros actualizados: Administrator;annb;florencef;pilarp;tonip**
  
 **19/02/2013 14:12**
  
 **Administrador**
  
 **Miembros actualizados: Administrator;annb;florencef;tonip**
  
En este ejemplo, la cuenta de usuario Administrador realizó los siguientes cambios:
  
- El 06/02/2013, agregó al usuario tonip.
    
- El 19/02/2013, quitó al usuario pilarp.
    

