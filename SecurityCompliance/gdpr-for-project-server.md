---
title: RGPD para Project Server
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: ''
localization_priority: Priority
description: Obtenga información sobre cómo cumplir los requisitos de RGPD en Project Server local.
ms.openlocfilehash: aa74f29e522f24f330db6e53c7c81bc5b708bcf0
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272155"
---
# <a name="gdpr-for-project-server"></a>RGPD para Project Server

Project Server usa scripts personalizados para exportar y redactar datos de usuario en Project Web App. El proceso básico es:

1.  Busque los sitios de Project Web App en la granja de servidores.

2.  Busque los proyectos en cada sitio que contiene el usuario.

3.  Exporte y revise los tipos de datos que desee revisar.

4.  Redacte los datos según sea necesario.

Estos pasos se tratan con detalle en los siguientes artículos:

- [Exportar datos de usuario de Project Server](/Project/export-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)

- [Eliminar datos de usuario de Project Server](/Project/delete-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)


Tenga en cuenta que Project Server se basa en SharePoint Server y registra los eventos en los registros de ULS de SharePoint y la base de datos de uso. Para obtener más información, vea [RGPD para SharePoint Server](gdpr-for-sharepoint-server.md).
