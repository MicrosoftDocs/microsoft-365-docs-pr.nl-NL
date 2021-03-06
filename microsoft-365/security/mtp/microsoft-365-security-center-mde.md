---
title: Microsoft Defender voor eindpunt in het Microsoft 365-beveiligingscentrum
description: Meer informatie over wijzigingen van het Microsoft Defender-beveiligingscentrum in het Microsoft 365-beveiligingscentrum
keywords: Aan de slag met het Microsoft 365-beveiligingscentrum, OATP, MDATP, MDO, MDE, één deelvenster met glas, geconvergeerde portal, beveiligingsportal, defender-beveiligingsportal
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 63f40ff12972695e391bd25973fd9a7195fab5b1
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515026"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a>Microsoft Defender voor eindpunt in het Microsoft 365-beveiligingscentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Van toepassing op:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)

Het verbeterde [Microsoft 365-beveiligingscentrum](overview-security-center.md) combineert beveiligingsfuncties die e-mail, samenwerking, identiteit en apparaatrisico's [https://security.microsoft.com](https://security.microsoft.com) beschermen, detecteren, onderzoeken en beantwoorden. Dit beveiligingscentrum brengt functionaliteit samen van bestaande Microsoft-beveiligingsportals, waaronder het Microsoft Defender-beveiligingscentrum en het Office 365-& compliancecentrum.

Als u bekend bent met het Microsoft Defender-beveiligingscentrum, kunt u in dit artikel enkele wijzigingen en verbeteringen in het verbeterde Microsoft 365-beveiligingscentrum beschrijven. Er zijn echter enkele nieuwe en bijgewerkte elementen waar u rekening mee moet houden.

In het verleden [was het Microsoft Defender-beveiligingscentrum](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/portal-overview) de thuisbasis voor Microsoft Defender voor het eindpunt. Beveiligingsteams in het bedrijf hebben dit gebruikt om waarschuwingen van geavanceerde permanente bedreigingsactiviteit of gegevensinbreuken te controleren en te helpen beantwoorden. Om het aantal portals te verminderen, is het Microsoft 365-beveiligingscentrum de thuisbasis voor het bewaken en beheren van de beveiliging in uw Microsoft-identiteiten, gegevens, apparaten, apps en infrastructuur.

Microsoft Defender for Endpoint in het Microsoft 365-beveiligingscentrum ondersteunt het verlenen van toegang aan [MSSP's (Managed Security Service Providers)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) op dezelfde manier als toegang wordt verleend in het [Microsoft Defender-beveiligingscentrum.](mssp-access.md)


> [!IMPORTANT]
> Wat u in het Microsoft 365-beveiligingscentrum ziet, is afhankelijk van uw huidige abonnementen. Als u bijvoorbeeld geen licentie voor Microsoft Defender voor Office 365 hebt, wordt de sectie E-mail & Samenwerking niet weergegeven.

>[!Note]
>De nieuwe geïntegreerde portal is niet beschikbaar voor: Amerikaanse Government Community Cloud (GCC) US Government Community Cloud High (GCC High) Amerikaanse department of Defense All Amerikaanse overheidsinstellingen met commerciële licenties

Bekijk het verbeterde Microsoft 365-beveiligingscentrum: [https://security.microsoft.com](https://security.microsoft.com)

Meer informatie over de voordelen: [Overzicht van het Microsoft 365-beveiligingscentrum](overview-security-center.md)

## <a name="whats-changed"></a>Wat is er gewijzigd?

Deze tabel is een beknopt overzicht van de wijzigingen tussen het Microsoft Defender-beveiligingscentrum en het Microsoft 365-beveiligingscentrum.

### <a name="alerts-and-actions"></a>Waarschuwingen en acties

|**Gebied**  |**Beschrijving van wijziging**  |
|---------|---------|
| [Incidenten & waarschuwingen](incidents-overview.md)  | In het Microsoft 365-beveiligingscentrum kunt u incidenten en waarschuwingen voor al uw eindpunten, e-mailadressen en identiteiten beheren. We hebben de ervaring geconvergeerd om u te helpen gerelateerde gebeurtenissen gemakkelijker te vinden. Zie Overzicht van [incidenten voor meer informatie.](incidents-overview.md)   |
| [Op zoek naar](advanced-hunting-overview.md)  |  Als u aangepaste detectieregels wijzigt die zijn gemaakt in Microsoft Defender for Endpoint, worden deze automatisch verplaatst naar Microsoft 365 Defender. De bijbehorende waarschuwingen worden ook weergegeven in Microsoft 365 Defender. Lees aangepaste detectieregels migreren voor meer informatie over [deze wijzigingen.](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules) De `DeviceAlertEvents` tabel voor geavanceerd zoeken is niet beschikbaar in Microsoft 365 Defender. Als u een query wilt uitvoeren op apparaatspecifieke waarschuwingsgegevens in Microsoft 365 Defender, kunt u de tabellen en de tabellen gebruiken om nog meer informatie uit een reeks `AlertInfo` `AlertEvidence` bronnen op te vragen. Maak uw volgende apparaatgerelateerde query door [query's schrijven zonder DeviceAlertEvents te volgen.](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents)|
|[Actiecentrum](mtp-action-center.md)    | Toont acties in behandeling en voltooid die zijn uitgevoerd na geautomatiseerde onderzoeken en herstelacties. Voorheen vermeldde het actiecentrum in het Microsoft Defender-beveiligingscentrum acties in behandeling en voltooid voor herstelacties die alleen op apparaten werden uitgevoerd, terwijl Geautomatiseerde onderzoeken waarschuwingen en status vermeldden. In het verbeterde Microsoft 365-beveiligingscentrum zijn in het Actiecentrum herstelacties en onderzoeken voor e-mail, apparaten en gebruikers samengekomen, allemaal op één locatie.  |
| [Dreigingsanalyse](threat-analytics.md) |  Verplaatst naar de bovenkant van de navigatiebalk voor eenvoudigere detectie en gebruik. Bevat nu bedreigingsgegevens voor eindpunten en e-mail en samenwerking.    |

### <a name="endpoints"></a>Eindpunten

|**Gebied**  |**Beschrijving van wijziging**  |
|---------|---------|
|Zoeken   |  In plaats van in de kop te staan, wordt de zoekbalk van Microsoft Defender voor eindpunt verplaatst naar de sectie Eindpunten. U kunt nog steeds zoeken naar apparaten, bestanden, gebruikers, URL's, INTERNETproviders, beveiligingsproblemen, software en aanbevelingen.  |
|[Dashboard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  Dit is het dashboard voor beveiligingsbewerkingen. Bekijk een overzicht van het aantal actieve waarschuwingen dat is geactiveerd, welke apparaten risico lopen, welke gebruikers een risico lopen en wat het niveau van ernst is voor waarschuwingen, apparaten en gebruikers. U kunt ook zien of er apparaten zijn met sensorproblemen, uw algehele service status en hoe er niet-opgeloste waarschuwingen zijn gedetecteerd. |
|Apparaatvoorraad | Geen wijzigingen. |
|[Beveiligingsprobleembeheer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    De naam is ingekort om in het navigatiedeelvenster te passen. Het is dezelfde als de sectie Risico- en beveiligingsprobleembeheer, met alle pagina's eronder.     |
| Partners en API's | Geen wijzigingen. |
| Evaluaties & zelfstudies    |     Nieuwe test- en leermogelijkheden.     |
| Configuratiebeheer   |  Geen wijzigingen.  |

> [!NOTE]
> **Automatisch onderzoek en herstel maakt** nu deel uit van incidenten. U kunt gebeurtenissen voor automatisch onderzoek en herstel bekijken op het **tabblad Incident > onderzoek.**

### <a name="access-and-reporting"></a>Toegang en rapportage

|**Gebied**  |**Beschrijving van wijziging**  |
|---------|---------|
| Rapporten  | Bekijk rapporten voor eindpunten en e-& samenwerking, waaronder bedreigingsbeveiliging, apparaat status en naleving en kwetsbaar apparaten. |
| Gezondheid  |  Koppelingen naar de pagina 'Service status' in het [Microsoft 365-beheercentrum.](https://admin.microsoft.com/) |
| Instellingen |  Beheer uw instellingen voor het Microsoft 365-beveiligingscentrum, Microsoft 365 Defender, Eindpunten, E-mail & samenwerking, Identiteiten en Apparaatdetectie.   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a>Microsoft 365-beveiligingsnavigatie en -mogelijkheden

Het linkernavigatiedeelvenster of de werkbalk Snel starten ziet er vertrouwd uit. Dit beveiligingscentrum bevat echter enkele nieuwe en bijgewerkte elementen.

### <a name="incidents-and-alerts"></a>Incidenten en waarschuwingen

Brengt incident- en waarschuwingsbeheer samen voor uw e-mail, apparaten en identiteiten. De waarschuwingspagina biedt volledige context voor de waarschuwing door het combineren van aanvallen om een gedetailleerd verhaal op te bouwen. Een nieuwe, geïntegreerde ervaring biedt nu een consistente weergave van waarschuwingen voor werkbelastingen. U kunt snel triage, onderzoek doen en effectieve acties ondernemen.

- [Meer informatie over incidenten](incidents-overview.md)
- [Meer informatie over het beheren van waarschuwingen](investigate-alerts.md)

![De werkbalk Snel starten voor waarschuwingen en acties](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>Op zoek naar

U kunt proactief zoeken naar bedreigingen, malware en schadelijke activiteiten in uw eindpunten, Office 365-postvakken en meer met behulp van geavanceerde [zoekquery's.](advanced-hunting-overview.md) Deze krachtige query's kunnen worden gebruikt om bedreigingsindicatoren en entiteiten voor zowel bekende als potentiële bedreigingen te zoeken en te controleren.

[Aangepaste detectieregels](custom-detection-rules.md) kunnen worden gemaakt van geavanceerde zoekquery's om u te helpen proactief te letten op gebeurtenissen die mogelijk te maken hebben met inbreuken en onjuist geconfigureerde apparaten.


### <a name="action-center"></a>Actiecentrum

In het actiecentrum ziet u de onderzoeken die zijn gemaakt door geautomatiseerde onderzoeks- en antwoordmogelijkheden. Met deze automatische, zelf-herstel in Microsoft 365 Defender kunnen beveiligingsteams worden geholpen door automatisch te reageren op specifieke gebeurtenissen.

[Meer informatie over het Actiecentrum](mtp-action-center.md)

### <a name="threat-analytics"></a>Bedreigingsanalyse

Krijg bedreigingsinformatie van deskundige Microsoft-beveiligingsonderzoekers. Met Bedreigingsanalyse kunnen beveiligingsteams efficiënter werken met nieuwe bedreigingen. Bedreigingsanalyse omvat:

- E-maildetectie en risicobeperking van Microsoft Defender voor Office 365. Dit komt naast de eindpuntgegevens die al beschikbaar zijn van Microsoft Defender voor Eindpunt.
- Weergave incidenten met betrekking tot de bedreigingen.
- Verbeterde ervaring voor het snel identificeren en gebruiken van informatie die door een actie kan worden ondernomen in de rapporten.

U kunt bedreigingsanalyse openen vanaf de navigatiebalk linksboven in het Microsoft 365-beveiligingscentrum of vanaf een speciale dashboardkaart met de belangrijkste bedreigingen voor uw organisatie.

Meer informatie over het volgen [en reageren op nieuwe bedreigingen met bedreigingsanalyse](https://docs.microsoft.com/microsoft-365/security/mtp/threat-analytics)

### <a name="endpoints-section"></a>Sectie Eindpunten

Bekijk en beheer de beveiliging van eindpunten in uw organisatie. Als u het Microsoft Defender-beveiligingscentrum hebt gebruikt, zal dit u bekend voorkomen.

![De werkbalk Snel starten van eindpunten](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a>Access en rapporten

Rapporten weergeven, uw instellingen wijzigen en gebruikersrollen wijzigen.

![De werkbalk Snelstarten voor Access en rapportage](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a>SIEM API-verbindingen

Als u de [DEFENDER for Endpoint SIEM-API](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md)gebruikt, kunt u dat blijven doen. We hebben nieuwe koppelingen toegevoegd op de API-nettolading die naar de waarschuwingspagina of de incidentpagina in de Microsoft 365-beveiligingsportal wijzen. Nieuwe API-velden zijn LinkToMTP en IncidentLinkToMTP. Zie Accounts van Microsoft Defender for [Endpoint omleiden naar het Microsoft 365-beveiligingscentrum](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)voor meer informatie.

### <a name="email-alerts"></a>E-mailwaarschuwingen

U kunt e-mailwaarschuwingen blijven gebruiken voor Defender voor eindpunt. We hebben nieuwe koppelingen toegevoegd in de e-mailberichten die wijzen naar de waarschuwingspagina of de pagina met incidenten in het Microsoft 365-beveiligingscentrum. Zie Accounts van Microsoft Defender for [Endpoint omleiden naar het Microsoft 365-beveiligingscentrum](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)voor meer informatie.

## <a name="related-information"></a>Verwante informatie

- [Microsoft 365-beveiligingscentrum](overview-security-center.md)
- [Microsoft Defender voor eindpunt in het Microsoft 365-beveiligingscentrum](microsoft-365-security-center-mde.md)
- [Accounts van Microsoft Defender voor eindpunt omleiden naar het Microsoft 365-beveiligingscentrum](microsoft-365-security-mde-redirection.md)
