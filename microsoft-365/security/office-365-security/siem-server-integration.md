---
title: SIEM-serverintegratie met Microsoft 365-services en -toepassingen
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Krijg een overzicht van de integratie van de SIEM-server (Security Information and Event Management) met uw Microsoft 365-cloudservices en -toepassingen
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f29da87aa6eab1852330092d93187a27b2d36eb2
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167141"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>SiEM-serverintegratie (Security Information and Event Management) met Microsoft 365-services en -toepassingen

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>Samenvatting

Gebruikt uw organisatie een SIEM-server (Security Information and Event Management) of gaat u deze gebruiken? Misschien vraagt u zich af hoe dit programma kan worden geïntegreerd met Microsoft 365 of Office 365. Dit artikel bevat een lijst met bronnen die u kunt gebruiken om uw SIEM-server te integreren met Microsoft 365-services en -toepassingen.

> [!TIP]
> Als u nog geen SIEM-server hebt en uw opties verkent, overweeg dan **[Microsoft Azure Azure.](https://docs.microsoft.com/azure/sentinel/overview)**

## <a name="do-i-need-a-siem-server"></a>Heb ik een SIEM-server nodig?

Of u een SIEM-server nodig hebt, hangt af van een groot aantal factoren, zoals de beveiligingsvereisten van uw organisatie en waar uw gegevens zich bevinden. Microsoft 365 bevat een groot aantal beveiligingsfuncties die voldoen aan de beveiligingsbehoeften van veel organisaties zonder extra servers, zoals een SIEM-server. Sommige organisaties hebben speciale omstandigheden waaronder het gebruik van een SIEM-server is vereist. Dit zijn enkele voorbeelden:

- *Fabrikam heeft* enkele inhoud en toepassingen on-premises, en sommige in de cloud (ze hebben een hybride cloudimplementatie). Fabrikam heeft een SIEM-server geïmplementeerd om beveiligingsrapporten over alle inhoud en toepassingen te krijgen.

- *Contoso* is een financiële dienstverleningsorganisatie die zeer strikte beveiligingsvereisten kent. Ze hebben een SIEM-server aan hun omgeving toegevoegd om te profiteren van de extra beveiligingsbescherming die ze vereisen.

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM-serverintegratie met Microsoft 365

Een SIEM-server kan gegevens ontvangen van diverse Microsoft 365-services en -toepassingen. De volgende tabel bevat een aantal Microsoft 365-services en -toepassingen, samen met SIEM-serverinvoer en bronnen voor meer informatie.

****

|Microsoft 365-service of -toepassing|SIEM-serverinvoer/-methoden|Informatiebronnen|
|---|---|---|
|[Microsoft Defender voor Office 365](office-365-atp.md)|Auditlogboeken|[SIEM-integratie met Microsoft Defender voor Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)|HTTPS-eindpunt gehost in Azure <p> REST API|[Waarschuwingen trekken voor uw SIEM-hulpprogramma's](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|Logboekintegratie|[SIEM-integratie met Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> Bekijk Azure [Azure](https://docs.microsoft.com/azure/sentinel/overview). Azure Azure Is voorzien van connectors voor Microsoft-oplossingen. Deze connectors zijn 'out-of-the-box' beschikbaar en bieden ondersteuning voor realtime-integratie. U kunt Azure Azure Azure Gebruiken met uw Microsoft 365 Defender-oplossingen en Microsoft 365-services, waaronder Office 365, Azure AD, Microsoft Defender voor identiteit, Microsoft Cloud App-beveiliging en meer.

### <a name="audit-logging-must-be-turned-on"></a>Auditlogregistratie moet zijn ingeschakeld

Zorg ervoor dat auditlogregistratie is ingeschakeld voordat u de SIEM-serverintegratie configureert.

- Voor SharePoint Online, OneDrive voor Bedrijven en Azure Active Directory is auditlogboekregistratie ingeschakeld in het [beveiligings- & compliancecentrum.](../../compliance/turn-audit-log-search-on-or-off.md)

- Zie Postvak controleren beheren [voor](../../compliance/enable-mailbox-auditing.md)Exchange Online.

## <a name="more-resources"></a>Meer informatie

[Beveiligingsoplossingen integreren in Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Microsoft Graph Security API-waarschuwingen integreren met een SIEM](https://docs.microsoft.com/graph/security-integration)
