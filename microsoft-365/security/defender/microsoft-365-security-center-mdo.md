---
title: Microsoft Defender voor Office 365 in Microsoft 365 Defender
description: Meer informatie over wijzigingen van het Office 365 beveiligings- en compliancecentrum naar Microsoft 365 Defender.
keywords: 'Microsoft 365 beveiliging: Aan de slag met Microsoft 365 Defender, Microsoft Defender voor Office 365, Microsoft Defender voor Eindpunt, MDO, MDE, enkel deelvenster glas, nieuwe beveiligingsportal, nieuwe defender-beveiligingsportal'
ms.date: 02/21/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.prod: m365-security
ms.technology: m365d
ms.openlocfilehash: decc991ef1d4a1b92f4e843fd39d595b9a1f7107
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964822"
---
# <a name="microsoft-defender-for-office-365-in-microsoft-365-defender"></a>Microsoft Defender voor Office 365 in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender voor Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

## <a name="quick-reference"></a>Snelzoekverwijzing

In de onderstaande tabel vindt u de wijzigingen in de navigatie tussen het Office 365 beveiligingscentrum & compliancecentrum en het Microsoft 365 Defender.

<br>

****

|[Office 365 Beveiligings- & compliance](https://protection.office.com)|[Microsoft 365 Defender](https://security.microsoft.com)|[Microsoft 365-compliancecentrum](https://compliance.microsoft.com/homepage)|[Exchange-beheercentrum](https://admin.exchange.microsoft.com/#/)|
|---|---|---|---|
|Waarschuwingen|<ul><li>[Waarschuwingsbeleid](https://security.microsoft.com/alertpolicies)</li><li>[Incidenten & waarschuwingen](https://security.microsoft.com/alerts)</li></ul>|[Pagina Waarschuwingen](https://compliance.microsoft.com/homepage)||
|Classificatie||Zie [Microsoft 365-compliancecentrum](https://compliance.microsoft.com/homepage)||
|Preventie van gegevensverlies||Zie [Microsoft 365-compliancecentrum](https://compliance.microsoft.com/homepage)||
|Records Management||Zie [Microsoft 365-compliancecentrum](https://compliance.microsoft.com/homepage)||
|Informatiebeheer||Zie [Microsoft 365-compliancecentrum](https://compliance.microsoft.com/homepage)||
|Bedreigingsbeheer|[Samenwerking via & e-mail](https://security.microsoft.com/homepage)|||
|Machtigingen|[Machtigingen & rollen](https://security.microsoft.com/emailandcollabpermissions)|Zie [Microsoft 365-compliancecentrum](https://compliance.microsoft.com/homepage)||
|E-mailstroom|||Zie [Exchange beheercentrum](https://admin.exchange.microsoft.com/#/)|
|Gegevensprivacy||Zie [Microsoft 365-compliancecentrum](https://compliance.microsoft.com/homepage)||
|Zoeken|[Controle](https://security.microsoft.com/auditlogsearch?viewid=Async%20Search)|Zoeken (zoeken naar inhoud)||
|Rapporten|[Rapport](https://security.microsoft.com/emailandcollabreport)|||
|Servicecontrole||Zie [Microsoft 365-compliancecentrum](https://compliance.microsoft.com/homepage)||
|Toezicht||Zie [Microsoft 365-compliancecentrum](https://compliance.microsoft.com/homepage)||
|eDiscovery||Zie [Microsoft 365-compliancecentrum](https://compliance.microsoft.com/homepage)||

[Microsoft 365 Defender](./overview-security-center.md) bij <https://security.microsoft.com> combineert beveiligingsmogelijkheden van bestaande Microsoft-beveiligingsportalen, waaronder het Office 365 Beveiligingscentrum & compliancecentrum. Dit verbeterde centrum helpt beveiligingsteams hun organisatie doeltreffender en efficiënter beschermen tegen bedreigingen.

Als u bekend bent met de Office 365 Security and Compliance portal (protection.office.com), beschrijft dit artikel enkele van de wijzigingen en verbeteringen in Microsoft 365 Defender.

Meer informatie over de voordelen: [Overzicht van Microsoft 365 Defender](overview-security-center.md)

Als je op zoek bent naar items gerelateerd aan compliance, bezoek dan het [Microsoft 365-compliancecentrum](https://compliance.microsoft.com/homepage).

## <a name="new-and-improved-capabilities"></a>Nieuwe en verbeterde mogelijkheden

De navigatie links, of balk snel starten, is vast bekend. Er zijn echter enkele nieuwe en bijgewerkte elementen in dit beveiligingscentrum.

Met de geïntegreerde Microsoft 365 Defender kunt u de bedreigingssignalen aan elkaar vaststeken en het volledige bereik en de impact van de bedreiging bepalen en bepalen wat de gevolgen zijn voor de organisatie.

:::image type="content" source="../../media/M365-defender-converge-experience.png" alt-text="Afbeelding van Microsoft 365 Defender geconvergeerde ervaring":::

Defender for Office 365 beschermt uw organisatie tegen schadelijke bedreigingen die worden veroorzaakt door e-mailberichten, koppelingen (URL's) en samenwerkingshulpmiddelen.

:::image type="content" source="../../media/Defender-for-O365.png" alt-text="Afbeelding van Defender voor Office 365":::

### <a name="incidents-and-alerts"></a>Incidenten en waarschuwingen

Dit brengt beheer voor incidenten en waarschuwingen samen voor e-mail, apparaten en identiteiten. Waarschuwingen zijn nu beschikbaar onder het knooppunt Onderzoek en hiermee wordt een breder zicht op een aanval gegeven. De waarschuwingspagina biedt volledige context bij een waarschuwing door signalen van een aanval te combineren om een gedetailleerd verhaal op te bouwen. Voordien waren waarschuwingen specifiek voor verschillende workloads. Een nieuwe, verenigde ervaring brengt nu een consistente weergave samen voor waarschuwingen in verschillende workloads. Je kan snel sorteren, onderzoeken en doeltreffend actie ondernemen.

- [Meer informatie over Onderzoeken](incidents-overview.md)
- [Meer informatie over het beheren van waarschuwingen](/windows/security/threat-protection/microsoft-defender-atp/review-alerts)

![De balk snel starten voor Waarschuwingen en acties](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>Opsporing

Spoor proactief dreigingen, malware en schadelijke activiteiten op in de eindpunten, Office 365 postvakken en meer met behulp van [geavanceerde opsporingsquery's](advanced-hunting-overview.md). Deze krachtige query's kunnen gebruikt worden om dreigingsindicatoren en entiteiten voor bekende en potentiële dreigingen te lokaliseren en controleren.

[Aangepaste detectieregels kunnen](/windows/security/threat-protection/microsoft-defender-atp/custom-detection-rules) worden gemaakt van geavanceerde zoekquery's om u te helpen proactief te kijken naar gebeurtenissen die een indicatie kunnen zijn van inbreukactiviteit en verkeerd geconfigureerde apparaten.

Hier is een [voorbeeld over geavanceerde jacht](advanced-hunting-example.md) in Microsoft Defender voor Office 365.  

### <a name="action-center"></a>Actiecentrum

Het Actiecentrum geeft de onderzoeken weer die aangemaakt werden door geautomatiseerde onderzoeks- en reactiefuncties. Deze geautomatiseerde self-healing in Microsoft 365 Defender kan beveiligingsteams bijstaan bij het automatisch reageren op specifieke gebeurtenissen.

Meer informatie over [actiecentrum.](m365d-action-center.md)

#### <a name="threat-analytics"></a>Dreigingsanalyse

Haal bedreigingsinformatie op via Microsoft beveiligingsonderzoeksexperten. Dreigingsanalyse helpt beveiligingsteams efficiënter omgaan met opkomende dreigingen. Dreigingsanalyse houdt in:

- E-mailgerelateerde detectie en beperkingen uit Microsoft Defender voor Office 365. Dit is bovenop de eindpuntgegevens die reeds beschikbaar zijn in Microsoft Defender voor Eindpunt.
- Incidentenweergave gerelateerd aan dreigingen.
- Geavanceerde ervaring voor snelle identificatie en gebruik van informatie waarop actie kan op uitgevoerd worden in de rapporten.

U hebt toegang tot Bedreigingsanalyse via de linkerbovenbalk in Microsoft 365 Defender of via een speciale dashboardkaart met de belangrijkste bedreigingen voor uw organisatie.

Meer informatie over het bijhouden en beantwoorden van nieuwe [bedreigingen met bedreigingsanalyse.](./threat-analytics.md)

### <a name="email--collaboration"></a>E-mail en samenwerking

Traceer en onderzoek dreigingen op e-mails van gebruikers, traceer campagnes en meer. Als je Office 365 beveiligings- en compliancecentrum reeds gebruikt hebt, zal je dit bekend zijn.

:::image type="content" source="../../media/converge-3-email-and-collab-new.png" alt-text="Het snelstartmenu voor E-mail & Collab (of MSDO), aan de linkerkant van Microsoft 365 Defender.":::

#### <a name="email-entity-page"></a>Entiteitspagina van e-mail 

Op de pagina *E-mailentiteit worden* e-mailgegevens weergegeven die in het verleden zijn verspreid over verschillende pagina's of weergaven. [](../office-365-security/mdo-email-entity-page.md) E-mails onderzoeken voor bedreigingen en trends is *gecentraliseerd*. Koptekstinformatie en preview van e-mail zijn beschikbaar via dezelfde e-mailpagina, samen met andere handige informatie over e-mails. Ook de deactiveringsstatus voor schadelijke bestandsbijlagen of URL's kunnen teruggevonden worden op het tabblad op dezelfde pagina. De E-mailentiteitspagina geeft de beheerder en beveiligingsteams de mogelijkheid om de bedreiging van e-mails en de status hiervan te begrijpen en vervolgens snel te handelen.

### <a name="access-and-reports"></a>Toegang en rapporten

Bekijk rapporten, wijzig instellingen en gebruikersrollen.

:::image type="content" source="../../media/converge-4-access-and-reporting-new.png" alt-text="Het snelstartmenu voor Microsoft 365 Defender machtigingen en rapportage, aan de linkerkant van het beveiligingscentrum.":::

> [!NOTE]
> DomainKeys Identified Mail (DKIM) zorgt ervoor dat doel-e-mailsystemen berichten vertrouwen die uitgaand zijn verzonden vanuit uw aangepaste domein.
> Voor Defender voor Office 365 gebruikers kunt  u DKIM-toetsen nu beheren en draaien via Microsoft 365 Defender: of naar <https://security.microsoft.com/threatpolicy> **Beleidsregels &** \>  \> **DKIM-beleidsregels navigeren.**
> 
> Zie [DKIM](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email)gebruiken om uitgaande e-mail te valideren die is verzonden vanuit uw aangepaste domein voor meer informatie.

## <a name="whats-changed"></a>Wat is er gewijzigd

Deze tabel is een beknopt overzicht van bedreigingsbeheer waarbij er een wijziging is opgetreden tussen het beveiligings- **& compliancecentrum** en **de Microsoft 365 Defender** portal. Klik op de snelkoppelingen om meer te lezen over deze gebieden.

<br>

****

|Gebied|Beschrijving van wijziging|
|---|---|
|[Onderzoek](../office-365-security/office-365-air.md#changes-are-coming-soon-in-your-microsoft-365-defender-portal)|Dit brengt AIR-functies samen in [Defender voor Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) en [Defender voor eindpunt](../defender-endpoint/automated-investigations.md). Met deze updates en verbeteringen kan jouw beveiligingsteam informatie bekijken over geautomatiseerde onderzoeken en herstelacties in e-mail, samenwerkingsinhoud, gebruikersaccounts en apparaten, allemaal op één plaats.|
|[Waarschuwingswachtrij](../../compliance/alert-policies.md)|Het **deelvenster Waarschuwingen weergeven** in het Office beveiligings- en compliancecentrum bevat nu koppelingen naar Microsoft 365 Defender. Klik op de **koppeling Waarschuwingspagina openen** en Microsoft 365 Defender geopend. Klik op eender welke Office 365-waarschuwing in de Waarschingswachtrij om toegang te krijgen tot de pagina **Waarschuwingen weergeven**.|
|[Aanvalssimulatietraining](../office-365-security/attack-simulation-training-insights.md)|Gebruik Aanvalssimulatietraining om realistische aanvalsscenario's uit te voeren in jouw organisatie. Met deze gesimuleerde aanvallen kan je jouw personeel trainen voordat een echte aanval jouw organisatie treft. Aanvalssimulatietraining bevat meer opties, geavanceerde rapporten en verbeterde trainingsstromen waardoor je de aanvalsscenario's en trainingsscenario's gemakkelijk kan leveren en beheren.|
|

Geen wijzigingen aan deze gebieden:

- [Verkenner](../office-365-security/threat-explorer.md)
- [Beleid en regels](../../compliance/alert-policies.md)
- [Campagne](../office-365-security/campaigns.md)
- [Inzendingen](../office-365-security/admin-submission.md)
- [Controle](./m365d-action-center.md)
- [Bedreigingstrackers](../office-365-security/threat-trackers.md)

Controleer ook de sectie **Relevante informatie** onderaan dit artikel.

> [!IMPORTANT]
> De Microsoft 365 Defender portal <https://security.microsoft.com> () combineert beveiligingsfuncties in <https://securitycenter.windows.com> en <https://protection.office.com> . Wat je te zien krijgt hangt echter af van het abonnement. Als je bijvoorbeeld enkel Microsoft Defender voor Office 365 Plan 1 of 2 hebt als alleenstaande abonnementen, zal je geen functies voor Beveiliging voor eindpunten te zien krijgen en klanten van Defender voor Office Plan 1 zullen geen items te zien krijgen zoals Dreigingsanalyse.

> [!TIP]
> Alle Exchange Online Protection (EOP)-functies worden opgenomen in Microsoft 365 Defender, omdat EOP een kernelement is van Defender voor Office 365.

## <a name="microsoft-365-defender-home-page"></a>Microsoft 365 Defender Startpagina

Op de startpagina van de portal vindt u belangrijke overzichtsinformatie over de beveiligingsstatus van uw Microsoft 365 omgeving.

Met de **Rondleiding** kan je snel de pagina's Eindpunt of E-mail en samenwerking verkennen. Merk op dat wat je te zien krijgt afhangt of je een licentie voor Defender voor Office 365 en/of Defender voor Eindpunt hebt.

Er is ook een snelkoppeling naar het **Office 365 beveiligings- en compliancecentrum** ter vergelijking. De laatste snelkoppeling is naar de pagina **Nieuw**, die recente updates beschrijft.

## <a name="related-information"></a>Gerelateerde informatie

- [Beveiligings- en compliancecentrum van Office 365 omleiden naar Microsoft 365 Defender](microsoft-365-security-mdo-redirection.md)
- [Het Actiecentrum](./m365d-action-center.md)
- [Waarschuwingen voor E-mail en samenwerking](../../compliance/alert-policies.md#default-alert-policies)
- [Aangepaste regels voor detectie](/microsoft-365/security/defender-endpoint/custom-detection-rules)
- [Een simulatie voor een phishing-aanval maken](../office-365-security/attack-simulation-training.md) en [een nettolading maken voor de training van jouw personeel](../office-365-security/attack-simulation-training-payloads.md)
