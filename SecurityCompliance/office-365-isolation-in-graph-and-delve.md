---
title: Aislamiento de inquilinos de Office 365 en la oficina de gráfico y profundizar
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: Una explicación de aislamiento de inquilinos en el gráfico de Office y en Delve.'
ms.openlocfilehash: bdc0f34d558f25ec139861c9a91261a72418f18a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536034"
---
# <a name="tenant-isolation-in-the-office-graph-and-delve"></a>Inquilino aislamiento en Office Graph y Delve

## <a name="tenant-isolation-in-the-office-graph"></a>Aislamiento de inquilinos en el gráfico de Office
La actividad de modelos de [Gráfico de Office](https://dev.office.com/officegraph) en servicios de Office 365, incluido Exchange Online, SharePoint Online, Yammer, Skype para la empresa, Azure Active Directory y obtener más información y en los servicios externos, como otros servicios de Microsoft o servicios de otros fabricantes. Componentes del gráfico de Office se utilizan a lo largo de Office 365. En el gráfico de Office representa una colección de contenido y actividad y las relaciones entre ellas que se producen a todo el conjunto de Office. Se utiliza máquina sofisticada técnicas de aprendizaje para conectar a las personas para el contenido relevante, conversaciones y personas alrededor de ellos. Por ejemplo, el índice del inquilino en SharePoint Online tiene un índice de gráfico de Office que se usa para atender las consultas de Delve, el motor de procesamiento de análisis en SharePoint Online se usa para almacenar las señales y calcular conocimientos y Exchange Online calcula cada usuario caché del destinatario como entrada en el análisis del inquilino.

En el gráfico de Office contiene información acerca de los objetos de empresa, por ejemplo, personas y documentos, así como las relaciones y las interacciones entre estos objetos. Las relaciones y las interacciones se representan como *bordes*. En el gráfico de Office es segmentado por inquilino tal que sólo pueden existir bordes entre los *nodos* en el mismo arrendamiento. Un *nodo* es una entidad con un identificador uniforme de recursos (URI), tipo de nodo, lista de control de acceso y un conjunto de facetas que contiene *metadatos* y bordes. Cada nodo tiene asociados metadatos y bordes, organizados en *aspectos* como en el modelo común de conocimientos. *Metadatos* se denominan propiedades almacenadas en un nodo que se puede usar para la búsqueda, el filtrado o análisis dentro del gráfico de office. Un *aspecto* es una colección lógica de metadatos y bordes en un nodo. Cada faceta describe un aspecto de un nodo. 

En el gráfico de Office no incorporar todos los datos en un único repositorio; en su lugar, almacena metadatos y relaciones de los datos que residen en otro lugar. En el gráfico de Office consta de varios almacenes de datos y componentes de procesamiento:
- El almacén de gráfico inquilino proporciona almacenamiento masivo optimizado para análisis eficaz.
- La memoria caché de contenido activo proporciona rápido acceso aleatorio al nodo activo y bordes para experiencias de usuario de la unidad.
- El enrutador de entrada notifica a los componentes internos y externos de los cambios realizados en el gráfico de inquilinos.

Análisis dentro de cada carga de trabajo deducir conocimientos relevantes para los cálculos de todo el inquilino y ellos de inserción para el gráfico de inquilinos. Análisis de inquilino motivos a través de toda la actividad en un arrendamiento para producir entendimiento de los patrones de comportamiento. Por ejemplo, Exchange Online calcula la memoria caché de destinatarios para cada usuario con análisis de forma eficaz de motivo a través de cada buzón de usuario. Estos análisis por usuario producen un conjunto de *Bordes RecipientCache* en cada persona, que a su vez se insertan en el gráfico de inquilinos. De esta forma, como parte del procesamiento de análisis lo más cerca de los datos de origen como sea posible.

## <a name="tenant-isolation-in-delve"></a>Aislamiento de inquilinos en profundizar
Como se mencionó anteriormente, el gráfico de Office enciende experiencias que ayudan a las personas detectar y colaborar en actividades actuales de su empresa y proporciona una plataforma centrada en la entidad para análisis a razón sobre el contenido y la actividad a través de las cargas de trabajo y más allá de Office 365. Profundizar es el primero con esa experiencia con tecnología de en el gráfico de Office. Profundizar es una experiencia web de Office 365 que superficies contenido de Office 365 y de empresa de Yammer a los usuarios de Office 365 mediante el gráfico de Office. La experiencia web muestra datos como paneles diferentes, cada uno con un tema, como *tendencias a mi alrededor* o *modificado por mí*. Cada placa consta de varias tarjetas de documento que mostrar una imagen desde el documento y el texto del resumen. La tarjeta permite a los usuarios a realizar tareas como abrir el documento o una página de Yammer para el documento. Hay una página para cada persona de un inquilino de Office 365 que muestra los documentos más relevantes para esta persona y los iconos que pueden invocar Exchange Online o Skype para la empresa para interactuar con esa persona. Debido a que Delve se basa en la API de gráfico de Office, está enlazado con el aislamiento basado en el inquilino de esa API.