---
title: " Siem-serverintegratie (Security Information and Event Management) met Microsoft 365-services en -toepassingen"
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: Krijg een overzicht van siem-serverintegratie (Security Information and Event Management) met uw Microsoft 365-cloudservices en -toepassingen
ms.openlocfilehash: a4ef144d02ebf0481481861c3dfa60a43b4f3ace
ms.sourcegitcommit: a7b2cd892cb65a61ee246268e1af2f8b9e526f6b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2020
ms.locfileid: "43081218"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Siem-serverintegratie (Security Information and Event Management) met Microsoft 365-services en -toepassingen

## <a name="summary"></a>Samenvatting

Gebruikt of is uw organisatie van plan om een SIEM-server (Security Information and Event Management) te krijgen? U vraagt zich misschien af hoe het integreert met Microsoft 365 of Office 365. In dit artikel vindt u een lijst met bronnen die u gebruiken om uw SIEM-server te integreren met Microsoft 365-services en -toepassingen.

> [!TIP]
> Als u nog geen SIEM-server hebt en uw opties verkent, u **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)** overwegen.

## <a name="do-i-need-a-siem-server"></a>Heb ik een SIEM-server nodig?

Of u een SIEM-server nodig hebt, hangt af van vele factoren, zoals de beveiligingsvereisten van uw organisatie en waar uw gegevens zich bevinden. Microsoft 365 bevat een breed scala aan beveiligingsfuncties die voldoen aan de beveiligingsbehoeften van veel organisaties zonder extra servers, zoals een SIEM-server. Sommige organisaties hebben speciale omstandigheden die het gebruik van een SIEM-server vereisen. Dit zijn enkele voorbeelden:

- *Fabrikam* heeft een aantal inhoud en applicaties on premises, en sommige in de cloud (ze hebben een hybride cloud implementatie). Om beveiligingsrapporten over al hun inhoud en toepassingen te krijgen, heeft Fabrikam een SIEM-server geïmplementeerd.

- *Contoso* is een financiële dienstverlener met bijzonder strenge veiligheidseisen. Ze hebben een SIEM-server aan hun omgeving toegevoegd om te profiteren van de extra beveiligingsbeveiliging die ze nodig hebben.

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM-serverintegratie met Microsoft 365

Een SIEM-server kan gegevens ontvangen van een breed scala aan Microsoft 365-services en -toepassingen. In de volgende tabel worden verschillende Microsoft 365-services en -toepassingen weergegeven, samen met SIEM-serveringangen en -bronnen voor meer informatie.

||||
|---|---|---|
|**Microsoft 365-service of -toepassing**|**SIEM-serveringangen/-methoden**|**Bronnen voor meer informatie**|
|[Geavanceerde bedreigingsbeveiliging van Office 365](office-365-atp.md)|Controlelogboeken|[SIEM-integratie met Geavanceerde bedreigingsbeveiliging van Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/)|HTTPS-eindpunt gehost in Azure <br/>REST-API|[Waarschuwingen voor uw SIEM-hulpprogramma's weergeven](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[Beveiliging van Microsoft Cloud-apps](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|Logintegratie|[SIEM-integratie met Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> Neem een kijkje op [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview). Azure Sentinel wordt geleverd met connectors voor Microsoft-oplossingen. Deze connectoren zijn beschikbaar "out of the box" en zorgen voor real-time integratie. U Azure Sentinel gebruiken met uw Microsoft Threat Protection-oplossingen en Microsoft 365-services, waaronder Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security en meer.

### <a name="audit-logging-must-be-turned-on"></a>Controlelogboekregistratie moet zijn ingeschakeld

Controleer of de controlelogboekregistratie is ingeschakeld voordat u siem-serverintegratie configureert.

- Voor SharePoint Online, OneDrive voor Bedrijven en Azure Active Directory [is controlelogboekregistratie ingeschakeld in het Beveiligingscentrum & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).

- Zie [Postvakcontrole beheren](../../compliance/enable-mailbox-auditing.md)voor Exchange Online .

## <a name="more-resources"></a>Meer informatie

[Beveiligingsoplossingen integreren in Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Microsoft Graph Security API-waarschuwingen integreren met een SIEM](https://docs.microsoft.com/graph/security-integration)
