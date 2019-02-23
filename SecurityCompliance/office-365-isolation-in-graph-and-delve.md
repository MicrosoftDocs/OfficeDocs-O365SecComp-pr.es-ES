---
title: Aislamiento de inquilino de Office 365 en Office Graph y Delve
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 'Resumen: explicación del aislamiento de inquilinos en Office Graph y en Delve.'
ms.openlocfilehash: cb1b432dccff6c4f890ef4aeb8ea4c19989b09d5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216810"
---
# <a name="tenant-isolation-in-the-office-graph-and-delve"></a>Aislamiento del inquilino en Office Graph y Delve

## <a name="tenant-isolation-in-the-office-graph"></a>Aislamiento de inquilinos en Office Graph
La actividad de los modelos de [Office Graph](https://dev.office.com/officegraph) en los servicios de Office 365, incluidos Exchange Online, SharePoint Online, Yammer, Skype empresarial, Azure Active Directory, etc., y en servicios externos, como otros servicios de Microsoft o servicios de terceros. Los componentes de Office Graph se usan en Office 365. Office Graph representa una colección de contenido y actividad, así como las relaciones entre ellos que se producen en todo el conjunto de aplicaciones de Office. Utiliza técnicas de aprendizaje de máquinas sofisticadas para conectar a las personas con el contenido relevante, las conversaciones y las personas que lo rodean. Por ejemplo, el índice de inquilino de SharePoint Online tiene un índice de Office Graph que se usa para atender las consultas de Delve, el motor de procesamiento de análisis de SharePoint Online se usa para almacenar señales y calcular información, y Exchange Online calcula el de cada usuario. caché de destinatarios como entrada en análisis de inquilino.

Office Graph contiene información sobre objetos de empresa, como personas y documentos, así como las relaciones y las interacciones entre estos objetos. Las relaciones y las interacciones se representan como *bordes*. Office Graph está segmentado por el inquilino, de modo que los bordes solo pueden existir entre *nodos* del mismo arrendamiento. Un *nodo* es una entidad con un identificador uniforme de recursos (URI), un tipo de nodo, una lista de control de acceso y un conjunto ** de facetas que contienen metadatos y bordes. Cada nodo tiene asociados metadatos y bordes, organizados en *facetas* como en el modelo de conocimientos común. ** Los metadatos son propiedades con nombre almacenadas en un nodo que se puede usar para realizar búsquedas, filtros o análisis dentro de Office Graph. Una *faceta* es una colección lógica de metadatos y bordes en un nodo. Cada faceta describe un aspecto de un nodo. 

Office Graph no incorpora todos los datos en un único repositorio; en su lugar, almacena metadatos y relaciones sobre los datos que residen en otro lugar. Office Graph consta de varios almacenes de datos y componentes de procesamiento:
- El almacén de gráficos de inquilinos proporciona almacenamiento masivo optimizado para análisis eficientes.
- La memoria caché de contenido activo proporciona un acceso aleatorio rápido al nodo activo y a los bordes para impulsar la experiencia del usuario.
- El enrutador de entrada notifica los componentes internos y externos de los cambios en el gráfico de inquilino.

Los análisis de cada carga de trabajo deducen información relevante para los cálculos de todo el inquilino y las envían al gráfico de inquilinos. Motivos de análisis de inquilinos de toda la actividad en un arrendamiento para generar información sobre patrones de comportamiento. Por ejemplo, Exchange Online calcula la caché de destinatarios para cada usuario con análisis que pueda ser una razón eficaz sobre el buzón de correo de cada usuario. Estos análisis por usuario generan un conjunto de *bordes RecipientCache* en cada persona, que a su vez se insertan en el gráfico de inquilino. Esto mantiene la mayor parte del procesamiento de análisis tan cerca de los datos de origen como sea posible.

## <a name="tenant-isolation-in-delve"></a>Aislamiento de inquilinos en Delve
Como se mencionó anteriormente, Office Graph impulsa experiencias que ayudan a los usuarios a descubrir y colaborar en actividades actuales en su empresa, y proporciona una plataforma centrada en la entidad para análisis y la razón sobre el contenido y la actividad en las cargas de trabajo y más allá de Office 365. Delve es la primera experiencia de este tipo con tecnología de Office Graph. Delve es una experiencia web de Office 365 que muestra el contenido de los usuarios de Office 365 y Yammer Enterprise a Office 365 a través de Office Graph. La experiencia web muestra los datos como paneles diferentes, cada uno de ellos con un tema concreto, como la *tendencia a mí* o *modificado por mí*. Cada panel consta de varias tarjetas de documento que muestran texto de Resumen y una imagen del documento. La tarjeta permite a los usuarios realizar acciones como abrir el documento o una página de Yammer para el documento. Hay una página para cada persona en un inquilino de Office 365 que muestra los documentos más relevantes para esta persona, así como los iconos que pueden invocar Exchange online o Skype empresarial para interactuar con esa persona. Debido a que Delve se basa en la API de Office Graph, está enlazado por el aislamiento basado en inquilino de la API.