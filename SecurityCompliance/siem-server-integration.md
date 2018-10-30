---
title: Integración del servidor de SIEM con Microsoft 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 10/29/2018
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- SIEM
description: 'Resumen: Lea este artículo para obtener una visión general de la integración del servidor de SIEM con Microsoft 365.'
ms.openlocfilehash: bd512ca6d75928712e3444581a78610a0869123d
ms.sourcegitcommit: 63ed467fc3e1ab1ab9ee122df97c64737169834e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2018
ms.locfileid: "25842691"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>Integración del servidor de SIEM con las aplicaciones y servicios de Microsoft 365

## <a name="overview"></a>Información general

Si su organización usa un servidor de información de seguridad y administración de eventos (SIEM), o si va a obtener un servidor SIEM pronto, es posible que se pregunte cómo que aquí se integran con su 365 de Microsoft, incluidos Office 365 Enterprise. Si necesita un servidor SIEM depende de muchos factores, como los requisitos de seguridad de la organización. Microsoft 365 ofrece una variedad de características de seguridad. Sin embargo, si su organización tiene contenido y las aplicaciones localmente y en la nube (como en el caso de una implementación de nube híbrida), es posible que considere la posibilidad de agregar un servidor SIEM para protección adicional. O bien, si su organización tiene requisitos de seguridad muy rigurosas que debe cumplir, es posible que considere la posibilidad de agregar un servidor SIEM a su entorno.

## <a name="siem-server-integration-microsoft-365"></a>Integración del servidor de SIEM 365 de Microsoft

Un servidor SIEM puede recibir datos de una amplia variedad de aplicaciones y servicios de Microsoft 365. En la siguiente tabla se enumera varias aplicaciones junto con entradas de los servidores SIEM y dónde debe acudir para obtener más información acerca de la integración de SIEM server y servicios de Microsoft 365. 

| El servicio de Microsoft 365 o de la aplicación | Entradas de los servidores SIEM | Recursos para obtener más información |
| --- | --- | --- |
| [Protección contra amenazas avanzada de Office 365](office-365-atp.md) <br/>   o   <br/>[Inteligencia sobre amenazas de Office 365](office-365-ti.md) | Registros de auditoría | [Integración de SIEM con información sobre amenazas de Office 365 y avanzada de protección contra amenazas](siem-integration-with-office-365-ti.md) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | Integración de registro | [Integración de SIEM con seguridad de la aplicación de Microsoft en la nube](https://docs.microsoft.com/cloud-app-security/siem) |
| [Office 365 Cloud App Security](office-365-cas-overview.md) | Integración de registro | [Integrar el servidor SIEM con Office 365 Cloud App Security](integrate-your-siem-server-with-office-365-cas.md) |
| [Protección contra amenazas avanzada de Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/) | Integración de registro | [Alertas de extracción a sus herramientas SIEM](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection) |
| [Centro de seguridad de Azure](https://docs.microsoft.com/azure/security-center/security-center-intro) (Protección contra amenazas y detección de amenazas) | Alertas | [Exportación de datos de Azure seguridad a la vista previa SIEM: configuración de canalización:](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
| [Protección de identidad de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) | Registros de auditoría | [Integrar los registros de auditoría de Azure Active Directory](https://docs.microsoft.com/azure/security/security-azure-log-integration-ad) |
| [Análisis de amenazas avanzadas Azure](https://docs.microsoft.com/azure/security/azure-threat-detection) | Integración de registro | [Referencia de registro SIEM ATA](https://docs.microsoft.com/advanced-threat-analytics/cef-format-sa) |

## <a name="audit-logging-must-be-turned-on"></a>Debe estar activado el registro de auditoría

Asegúrese de que está activado el registro de auditoría antes de configurar la integración del servidor de SIEM. 

- Para SharePoint Online, OneDrive para profesionales y Azure Active Directory, [el registro de auditoría está activado en el centro de cumplimiento y seguridad](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).

- Para Exchange Online, [se activa el registro de auditoría con Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).
 
## <a name="see-also"></a>Vea también

[Adopción de la nube y soluciones híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[Guías del laboratorio de pruebas de adopción de la nube (TLG)](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


