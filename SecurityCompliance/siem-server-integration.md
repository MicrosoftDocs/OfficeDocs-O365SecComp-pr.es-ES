---
title: Integración del servidor SIEM con Microsoft 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 10/29/2018
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- SIEM
description: 'Resumen: Lea este artículo para obtener información general sobre la integración del servidor SIEM con Microsoft 365.'
ms.openlocfilehash: 4b9b631ab27d777be610ed3b954acc7b2c3bdf50
ms.sourcegitcommit: 1c73c2f83703af0a30a5b0633db00d8e0e6b39b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2019
ms.locfileid: "30241882"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>Integración del servidor de SIEM con los servicios y aplicaciones de Microsoft 365

## <a name="overview"></a>Información general

Si su organización usa un servidor de administración de eventos e información de seguridad (SIEM), o si tiene previsto obtener un servidor de SIEM en breve, es posible que se pregunte cómo se integrará con el 365 de Microsoft, incluido Office 365 Enterprise. Si necesita un servidor de SIEM depende de muchos factores, como los requisitos de seguridad de la organización. Microsoft 365 ofrece una amplia variedad de características de seguridad; sin embargo, si su organización tiene contenido y aplicaciones locales y en la nube (como en el caso de una implementación de nube híbrida), puede considerar la posibilidad de agregar un servidor SIEM para una protección adicional. O bien, si su organización tiene unos requisitos de seguridad especialmente estrictos que debe cumplir, puede considerar la posibilidad de agregar un servidor SIEM a su entorno.

## <a name="siem-server-integration-microsoft-365"></a>Integración del servidor de SIEM Microsoft 365

Un servidor de SIEM puede recibir datos de una amplia variedad de aplicaciones y servicios de Microsoft 365. En la siguiente tabla se enumeran varios servicios y aplicaciones de Microsoft 365 junto con entradas del servidor SIEM y dónde obtener más información sobre la integración del servidor de SIEM. 

| Servicio o aplicación de Microsoft 365 | Entradas del servidor SIEM | Recursos para obtener más información |
| --- | --- | --- |
| [Protección contra amenazas avanzada de Office 365](office-365-atp.md) <br/>   o   <br/>[Inteligencia sobre amenazas de Office 365](office-365-ti.md) | Registros de auditoría | [Integración de SIEM con Office 365 Threat Intelligence y protección contra amenazas avanzada](siem-integration-with-office-365-ti.md) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | Integración de registros | [Integración de SIEM con Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/siem) |
| [Office 365 Cloud App Security](office-365-cas-overview.md) | Integración de registros | [Integrar el servidor SIEM con Office 365 Cloud App Security](integrate-your-siem-server-with-office-365-cas.md) |
| [Protección contra amenazas avanzada de Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/) | Integración de registros | [Extraer alertas a las herramientas de SIEM](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection) |
| [Centro de seguridad de Azure](https://docs.microsoft.com/azure/security-center/security-center-intro) (Protección contra amenazas y detección de amenazas) | Alertas | [Exportación de datos de seguridad de Azure a SIEM-configuración de canalización-vista previa](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
| [Protección de identidad de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) | Registros de auditoría | [Integración de los registros de auditoría de Azure Active Directory](https://docs.microsoft.com/azure/security/security-azure-log-integration-ad) |
| [Análisis de amenazas avanzadas de Azure](https://docs.microsoft.com/azure/security/azure-threat-detection) | Integración de registros | [Referencia de registro SIEM de ATA](https://docs.microsoft.com/advanced-threat-analytics/cef-format-sa) |

## <a name="audit-logging-must-be-turned-on"></a>El registro de auditoría debe estar activado

Asegúrese de que el registro de auditoría esté activado antes de configurar la integración del servidor SIEM. 

- En SharePoint Online, OneDrive para la empresa y Azure Active Directory, [el registro de auditoría está activado en el centro de seguridad _AMP_ cumplimiento](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).

- Para Exchange Online, el [registro de auditoría está activado con Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).
 
## <a name="see-also"></a>Vea también

[Adopción de la nube y soluciones híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[Guías del laboratorio de pruebas de adopción de la nube (TLG)](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


