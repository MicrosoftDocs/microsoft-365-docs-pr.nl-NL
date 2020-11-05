---
title: SIEM Server-integratie met Microsoft 365-Services en-toepassingen
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
- seo-marvel-apr2020
description: Een overzicht van beveiligings-en SIEM-Serverintegratie met Microsoft 365-cloudservices en-toepassingen
ms.openlocfilehash: 17e21d19463187744afe855b2304ac71956545d2
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919761"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Beveiligingsinformatie en Gebeurtenissenbeheer (SIEM) Serverintegratie met Microsoft 365-Services en-toepassingen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="summary"></a>Samenvatting

Maakt uw organisatie gebruik van of planning voor een beveiligings-of SIEM-server? U vraagt zich wellicht af hoe dit wordt geïntegreerd met Microsoft 365 of Office 365. Dit artikel bevat een overzicht van bronnen die u kunt gebruiken om uw SIEM server te integreren met Microsoft 365-Services en-toepassingen.

> [!TIP]
> Als u nog geen SIEM-server hebt en uw opties wilt bekijken, kunt u overwegen **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.

## <a name="do-i-need-a-siem-server"></a>Heb ik een SIEM-server nodig?

Of u een SIEM-server nodig hebt, is afhankelijk van het aantal factoren, zoals de beveiligingsvereisten van uw organisatie en de locatie waar uw gegevens zich bevinden. Microsoft 365 omvat een groot aantal beveiligingsfuncties die voldoen aan de behoeften van een groot aantal organisaties zonder extra servers, zoals een SIEM-server. Sommige organisaties hebben speciale omstandigheden waarvoor het gebruik van een SIEM-server is vereist. Dit zijn enkele voorbeelden:

- *Fabrikam* heeft bepaalde inhoud en toepassingen on-premises en in de Cloud (deze hebben een hybride implementatie van de Cloud). Fabrikam heeft een SIEM-server geïmplementeerd voor het uitvoeren van beveiligingsrapporten over al hun inhoud en toepassingen.

- *Contoso* is een organisatie met een financiële dienst die zeer stringente beveiligingsvereisten biedt. Ze hebben een SIEM-server toegevoegd aan de omgeving om gebruik te kunnen maken van de extra beveiligings bescherming die ze nodig hebben.

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM Server-integratie met Microsoft 365

Een SIEM-server kan gegevens ontvangen van diverse Microsoft 365-Services en-toepassingen. In de volgende tabel vindt u een overzicht van diverse Microsoft 365-Services en-toepassingen, samen met SIEM-server ingangen en bronnen voor meer informatie.

****

|Microsoft 365-service of-toepassing|SIEM-server ingangen/-methoden|Informatiebronnen|
|---|---|---|
|[Microsoft Defender voor Office 365](office-365-atp.md)|Controlelogboeken|[SIEM-integratie met Microsoft Defender voor Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender voor Eindpunt ](https://docs.microsoft.com/windows/security/threat-protection/)|HTTPS-eindpunt gehost in azure <br/>REST-API|[Waarschuwingen aantrekken voor uw SIEM-hulpmiddelen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|Integratie van logboek|[SIEM-integratie met Microsoft Cloud-app-beveiliging](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> Bekijk [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview). Azure Sentinel wordt geleverd met connectors voor Microsoft-oplossingen. Deze verbindingslijnen bevinden zich in de loop van het vak en geven de mogelijkheid om in realtime te integreren. U kunt Azure Sentinel gebruiken met uw Microsoft 365 Defender-oplossingen en Microsoft 365-Services, waaronder Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud app Security en meer.

### <a name="audit-logging-must-be-turned-on"></a>Controlelogboekregistratie moet zijn ingeschakeld

Zorg ervoor dat het logboekregistratie van gebeurtenissen is ingeschakeld voordat u SIEM Server-integratie configureert.

- Voor SharePoint Online, OneDrive voor bedrijven en Azure Active Directory [is controlelogboekregistratie ingeschakeld in het beveiligings & nalevings centrum](../../compliance/turn-audit-log-search-on-or-off.md).

- Voor Exchange Online raadpleegt u [Postvak controle beheren](../../compliance/enable-mailbox-auditing.md).

## <a name="more-resources"></a>Meer informatie

[Beveiligingsoplossingen in azure Defender integreren](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Microsoft Graph beveiligings API-waarschuwingen integreren met een SIEM](https://docs.microsoft.com/graph/security-integration)
