---
title: SIEM-serverintegratie met Microsoft 365 services en toepassingen
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
description: Een overzicht krijgen van de siem-serverintegratie (Security Information and Event Management) met uw Microsoft 365 cloudservices en -toepassingen
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ea4d844595aaab8d8148666430187edef463b92e
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105594"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Siem-serverintegratie (Security Information and Event Management) met Microsoft 365 services en toepassingen

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>Samenvatting

Gebruikt of plant uw organisatie een SIEM-server (Security Information and Event Management) te krijgen? U vraagt zich misschien af hoe het wordt geïntegreerd met Microsoft 365 of Office 365. Dit artikel bevat een lijst met bronnen die u kunt gebruiken om uw SIEM-server te integreren met Microsoft 365 services en toepassingen.

> [!TIP]
> Als u nog geen SIEM-server hebt en uw opties verkent, kunt u het Microsoft Azure **[Schildwacht.](/azure/sentinel/overview)**

## <a name="do-i-need-a-siem-server"></a>Heb ik een SIEM-server nodig?

Of u een SIEM-server nodig hebt, hangt af van veel factoren, zoals de beveiligingsvereisten van uw organisatie en waar uw gegevens zich bevinden. Microsoft 365 bevat een groot aantal beveiligingsfuncties die voldoen aan de beveiligingsbehoeften van veel organisaties zonder extra servers, zoals een SIEM-server. Sommige organisaties hebben speciale omstandigheden waarvoor het gebruik van een SIEM-server vereist is. Dit zijn enkele voorbeelden:

- *Fabrikam* heeft een aantal on-premises inhoud en toepassingen, en sommige in de cloud (ze hebben een hybride cloudimplementatie). Om beveiligingsrapporten over al hun inhoud en toepassingen te krijgen, heeft Fabrikam een SIEM-server geïmplementeerd.
- *Contoso* is een financiële serviceorganisatie die bijzonder strenge beveiligingsvereisten heeft. Ze hebben een SIEM-server toegevoegd aan hun omgeving om te profiteren van de extra beveiliging die ze nodig hebben.

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM-serverintegratie met Microsoft 365

Een SIEM-server kan gegevens ontvangen van een groot aantal Microsoft 365 services en toepassingen. In de volgende tabel vindt u Microsoft 365 services en toepassingen, samen met SIEM-serverinvoer en -resources voor meer informatie.

<br>

****

|Microsoft 365 Service of Toepassing|SIEM-serverinvoer/-methoden|Informatiebronnen|
|---|---|---|
|[Microsoft Defender voor Office 365](defender-for-office-365.md)|Auditlogboeken|[SIEM-integratie met Microsoft Defender voor Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender voor Eindpunt](/windows/security/threat-protection/)|HTTPS-eindpunt dat wordt gehost in Azure <p> REST API|[Waarschuwingen naar uw SIEM-hulpprogramma's trekken](../defender-endpoint/configure-siem.md)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)|Logboekintegratie|[SIEM-integratie met Microsoft Cloud App Security](/cloud-app-security/siem)|
|

> [!TIP]
> Bekijk Azure [Sentinel.](/azure/sentinel/overview) Azure Sentinel wordt geleverd met connectors voor Microsoft-oplossingen. Deze connectors zijn 'out of the box' beschikbaar en bieden realtime integratie. U kunt Azure Sentinel gebruiken met uw Microsoft 365 Defender-oplossingen en Microsoft 365-services, waaronder Office 365, Azure AD, Microsoft Defender voor identiteit, Microsoft Cloud App Security en meer.

### <a name="audit-logging-must-be-turned-on"></a>Auditregistratie moet zijn ingeschakeld

Controleer of auditregistratie is ingeschakeld voordat u de SIEM-serverintegratie configureert.

- Zie Voor SharePoint Online, OneDrive voor Bedrijven en Azure Active Directory controle in- [of uitschakelen.](../../compliance/turn-audit-log-search-on-or-off.md)
- Zie Exchange Online controle van postvakken beheren voor [meer Exchange Online.](../../compliance/enable-mailbox-auditing.md)

## <a name="more-resources"></a>Meer informatie

[Beveiligingsoplossingen integreren in Azure Defender](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Microsoft-Graph beveiligings-API-waarschuwingen integreren met een SIEM](/graph/security-integration)
