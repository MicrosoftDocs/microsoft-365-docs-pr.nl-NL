---
title: Nieuwe bedreigingen bijhouden en beantwoorden met bedreigingsanalyse
ms.reviewer: ''
description: Meer informatie over nieuwe bedreigingen en aanvalstechnieken en hoe u deze kunt stoppen. Beoordeel de impact ervan op uw organisatie en evalueer uw organisatiebestendigheid.
keywords: bedreigingsanalyse, risicoanalyse, Microsoft 365 Defender, M365D, mitigatiestatus, veilige configuratie, Microsoft Defender voor Office 365, Microsoft Defender voor Office 365 threat analytics, MDO threat analytics, geïntegreerde MDE en MDO threat analytics data, threat analytics data integration, integrated Microsoft 365 Defender threat analytics
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 288be30aa9592ba7feed92b9ad49955406f59f10
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918796"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a>Nieuwe bedreigingen bijhouden en beantwoorden met bedreigingsanalyse 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

> Wilt u Microsoft 365 Defender ervaren? U kunt [het project evalueren in een labomgeving](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab) of uw [pilotproject uitvoeren in productie.](./mtp-pilot.md?ocid=cx-evalpilot)
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]


Bedreigingsanalyse is onze in-product threat intelligence-oplossing van deskundige Microsoft-beveiligingsonderzoekers, ontworpen om beveiligingsteams te helpen zo efficiënt mogelijk te werken terwijl ze geconfronteerd worden met nieuwe bedreigingen, zoals:

- Actieve bedreigingsacteurs en hun campagnes
- Populaire en nieuwe aanvalstechnieken
- Kritieke beveiligingslekken
- Veelvoorkomende aanvalsoppervlakken
- Voorkomende malware

Bekijk deze korte video voor meer informatie over hoe u met bedreigingsanalyse de meest recente bedreigingen kunt bijhouden en stoppen.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWwJfU]

U hebt toegang tot bedreigingsanalyse via de linkerbovenhoek van de navigatiebalk van de Microsoft 365-beveiligingsportal of via een speciale dashboardkaart met de belangrijkste bedreigingen in uw organisatie. Als u inzicht krijgt in actieve of lopende campagnes en weet wat u moet doen via bedreigingsanalyses, kunt u uw beveiligingsteam voorzien van weloverwogen beslissingen. 

![Afbeelding van het dashboard bedreigingsanalyse](../../media/threat-analytics/ta_inlandingpage_mtp.png)

_Waar toegang tot bedreigingsanalyse_

Met geavanceerdere tegenstanders en nieuwe bedreigingen die regelmatig en regelmatig verschijnen, is het essentieel om snel te kunnen:

- Nieuwe bedreigingen identificeren en erop reageren 
- Informatie over of u momenteel wordt aangevallen
- Het effect van de bedreiging voor uw activa beoordelen
- Uw tolerantie voor of blootstelling aan de bedreigingen controleren
- Identificeer de risicobeperkings-, herstel- of preventieacties die u kunt ondernemen om de bedreigingen te stoppen of te bevatten

Elk rapport bevat een analyse van een bijgespoorde bedreiging en uitgebreide richtlijnen voor het beschermen tegen die bedreiging. Het bevat ook gegevens uit uw netwerk, waarmee wordt aangegeven of de bedreiging actief is en of u over toepasselijke beveiliging beschikt.

## <a name="view-the-threat-analytics-dashboard"></a>Het dashboard bedreigingsanalyse bekijken

In het dashboard bedreigingsanalyse[(security.microsoft.com/threatanalytics3)](https://security.microsoft.com/threatanalytics3)worden de rapporten belicht die het meest relevant zijn voor uw organisatie. De bedreigingen worden in de volgende secties samengevat:

- **Meest recente bedreigingen:** bevat de meest recent gepubliceerde of bijgewerkte bedreigingsrapporten, samen met het aantal actieve en opgeloste waarschuwingen.
- **Bedreigingen met een hoge** impact : hier worden de bedreigingen vermeld die de grootste impact hebben op uw organisatie. In deze sectie worden eerst bedreigingen met het hoogste aantal actieve en opgeloste waarschuwingen vermeld.
- **Overzicht van** bedreigingen: geeft de algehele impact van alle bijgespoorde bedreigingen door het aantal bedreigingen met actieve en opgeloste waarschuwingen weer te geven.

Selecteer een bedreiging in het dashboard om het rapport voor die bedreiging weer te geven.

![Schermafbeelding van het dashboard bedreigingsanalyse](../../media/threat-analytics/ta_dashboard_mtp.png)

_Dashboard Bedreigingsanalyse. U kunt ook op het pictogram Zoeken klikken om een sleutel te geven in een trefwoord dat betrekking heeft op het rapport bedreigingsanalyse dat u wilt lezen._ 

## <a name="view-a-threat-analytics-report"></a>Een bedreigingsanalyserapport weergeven

Elk bedreigingsanalyserapport bevat informatie in verschillende secties: 

- [**Overzicht**](#overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses) 
- [**Analistrapport**](#analyst-report-get-expert-insight-from-microsoft-security-researchers)
- [**Gerelateerde incidenten**](#related-incidents-view-and-manage-related-incidents)
- [**Beïnvloede activa**](#impacted-assets-get-list-of-impacted-devices-and-mailboxes)
- [**E-mailpogingen voorkomen**](#prevented-email-attempts-view-blocked-or-junked-threat-emails)
- [**Risico's**](#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a>Overzicht: Snel inzicht krijgen in de bedreiging, de impact ervan beoordelen en verdedigingslinie bekijken

De **sectie** Overzicht bevat een voorbeeld van het gedetailleerde analistenrapport. Het bevat ook grafieken die de impact van de bedreiging voor uw organisatie en uw blootstelling markeren via verkeerd geconfigureerde en ongepatchte apparaten.

![Afbeelding van de overzichtssectie van een rapport voor bedreigingsanalyse](../../media/threat-analytics/ta_overview_mtp.png)

_Overzichtssectie van een rapport voor bedreigingsanalyse_

#### <a name="assess-impact-on-your-organization"></a>De impact op uw organisatie beoordelen
Elk rapport bevat grafieken die zijn ontworpen om informatie te verstrekken over de invloed van een bedreiging op de organisatie:
- **Gerelateerde incidenten**: geeft een overzicht van de impact van de bijgespoorde bedreiging voor uw organisatie met de volgende gegevens:
  - Aantal actieve waarschuwingen en het aantal actieve incidenten dat aan deze meldingen is gekoppeld
  - Ernst van actieve incidenten
- **Waarschuwingen in de tijd**: toont het aantal gerelateerde **actieve** en **opgeloste** waarschuwingen in de tijd. Het aantal opgeloste waarschuwingen geeft aan hoe snel uw organisatie reageert op waarschuwingen die zijn gekoppeld aan een bedreiging. In het ideale kader moet de grafiek binnen enkele dagen waarschuwingen weergeven die zijn opgelost.
- **Beïnvloede activa:** toont het aantal verschillende apparaten en e-mailaccounts (postvakken) dat momenteel ten minste één actieve waarschuwing aan de bijgespoorde bedreiging heeft gekoppeld. Waarschuwingen worden geactiveerd voor postvakken die e-mailberichten met bedreigingen hebben ontvangen. Controleer zowel het beleid op organisatie- als gebruikersniveau voor overschrijven die de bezorging van e-mailberichten met bedreigingen veroorzaken.
- **E-mailpogingen voorkomen:** toont het aantal e-mailberichten van de afgelopen zeven dagen dat vóór de bezorging is geblokkeerd of die zijn bezorgd in de map ongewenste e-mail.

#### <a name="review-security-resilience-and-posture"></a>Beveiligingsweerbaarheid en -houding controleren
Elk rapport bevat grafieken die een overzicht geven van hoe veerkrachtig uw organisatie is tegen een bepaalde bedreiging:
- **Veilige configuratiestatus:** toont het aantal apparaten met verkeerd geconfigureerde beveiligingsinstellingen. Pas de aanbevolen beveiligingsinstellingen toe om de bedreiging te beperken. Apparaten worden beschouwd **als Veilig** als ze alle _bijgespoorde_ instellingen hebben toegepast.
- **Beveiligingspatchingstatus**: geeft het aantal kwetsbare apparaten weer. Pas beveiligingsupdates of patches toe om beveiligingsproblemen aan te pakken die door de bedreiging worden misbruikt.

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a>Analistrapport: Krijg inzicht van microsoft-beveiligingsonderzoekers
Lees in **de sectie Rapportanalist** de gedetailleerde expert-write-up door. De meeste rapporten bevatten gedetailleerde beschrijvingen van aanvalsketens, waaronder tactieken en technieken die zijn toegesneden op het MITRE ATT&CK-framework, uitgebreide lijsten met aanbevelingen en krachtige richtlijnen voor het zoeken naar [bedreigingen.](advanced-hunting-overview.md)

[Meer informatie over het analistenrapport](threat-analytics-analyst-reports.md)

### <a name="related-incidents-view-and-manage-related-incidents"></a>Verwante incidenten: Gerelateerde incidenten weergeven en beheren
Het **tabblad Gerelateerde incidenten** bevat de lijst met alle incidenten met betrekking tot de bijgespoorde bedreiging. U kunt incidenten toewijzen of waarschuwingen beheren die aan elk incident zijn gekoppeld. 

![Afbeelding van de sectie verwante incidenten van een rapport over bedreigingsanalyse](../../media/threat-analytics/ta_related_incidents_mtp.png)

_Sectie Verwante incidenten van een rapport over bedreigingsanalyse_

### <a name="impacted-assets-get-list-of-impacted-devices-and-mailboxes"></a>Beïnvloede activa: Lijst met beïnvloede apparaten en postvakken
Een activum wordt als beïnvloed beschouwd als het wordt beïnvloed door een actieve, niet-opgeloste waarschuwing. Het **tabblad Beïnvloede activa** bevat de volgende typen beïnvloede activa:
- **Beïnvloede apparaten:** eindpunten met niet-opgeloste waarschuwingen van Microsoft Defender voor eindpunten. Deze waarschuwingen worden meestal gebruikt voor waarnemingen van bekende bedreigingsindicatoren en -activiteiten.
- **Beïnvloede postvakken:** postvakken die e-mailberichten hebben ontvangen die microsoft Defender voor Office 365-waarschuwingen hebben geactiveerd. Hoewel de meeste berichten die waarschuwingen activeren meestal worden geblokkeerd, kunnen beleidsregels op gebruikers- of organisatieniveau filters overschrijven.

![Afbeelding van de sectie beïnvloede activa van een bedreigingsanalyserapport](../../media/threat-analytics/ta_impacted_assets_mtp.png)

_Sectie Beïnvloede activa van een rapport voor bedreigingsanalyse_

### <a name="prevented-email-attempts-view-blocked-or-junked-threat-emails"></a>E-mailpogingen voorkomen: geblokkeerde of ongewenste e-mailberichten weergeven
Microsoft Defender voor Office 365 blokkeert meestal e-mailberichten met bekende bedreigingsindicatoren, waaronder schadelijke koppelingen of bijlagen. In sommige gevallen worden met proactieve filtermechanismen die controleren op verdachte inhoud, in plaats daarvan e-mailberichten met bedreigingen naar de map ongewenste e-mail verzonden. In beide gevallen is de kans op het starten van malwarecode voor bedreigingen op het apparaat kleiner.

Op **het tabblad Pogingen voor e-mail** voorkomen worden alle e-mailberichten weergegeven die vóór de bezorging zijn geblokkeerd of die door Microsoft Defender voor Office 365 naar de map ongewenste e-mail zijn verzonden. 

![Afbeelding van de sectie verhinderde e-mailpogingen van een rapport voor bedreigingsanalyse](../../media/threat-analytics/ta_prevented_email_attempts_mtp.png)

_Sectie E-mailpogingen voorkomen in een rapport voor bedreigingsanalyse_

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a>Risicobeperking: Lijst met risico's en de status van uw apparaten controleren
Bekijk in **de sectie Mitigaties** de lijst met specifieke actie-aanbevelingen die u kunnen helpen uw organisatieweerbaarheid tegen de bedreiging te vergroten. De lijst met bijgespoorde risico's bevat:

- **Beveiligingsupdates**: implementatie van ondersteunde softwarebeveiligingsupdates voor beveiligingsproblemen die zijn gevonden op onboarded-apparaten
- **Ondersteunde beveiligingsconfiguraties**
  - Beveiliging in de cloud  
  - Potentieel ongewenste toepassingsbeveiliging (PUA)
  - Realtime beveiliging
 
Mitigatiegegevens in deze [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)sectie bevatten gegevens van bedreigings- en kwetsbaarheidsbeheer, die ook gedetailleerde inzoomgegevens bevatten van verschillende koppelingen in het rapport.

![Afbeelding van de sectie risicobeperking van een bedreigingsanalyserapport met veilige configuratiegegevens Afbeelding van de sectie risicobeperking van een rapport met ](../../media/threat-analytics/ta_mitigations_mtp.png)
 ![ beveiligingsdetails](../../media/threat-analytics/ta_mitigations_mtp2.png)

_Sectie Risicobeperking van een rapport voor bedreigingsanalyse_

## <a name="additional-report-details-and-limitations"></a>Aanvullende rapportdetails en -beperkingen
>[!NOTE]
>Als onderdeel van de geïntegreerde beveiligingservaring is bedreigingsanalyse nu niet alleen beschikbaar voor Microsoft Defender voor Eindpunt, maar ook voor licentiehouders van Microsoft Defender voor Office E5.
>Als u de Microsoft 365-beveiligingsportal (Microsoft 365 Defender) niet gebruikt, kunt u ook de rapportdetails (zonder de Microsoft Defender voor Office-gegevens) zien in de Microsoft Defender-beveiligingscentrumportal (Microsoft Defender voor Eindpunt). 

Voor toegang tot het rapport Bedreigingsanalyse hebt u bepaalde rollen en machtigingen nodig. Zie [Aangepaste rollen in op rollen gebaseerd toegangsbeheer voor Microsoft 365 Defender voor](custom-roles.md) meer informatie.
  - Als u waarschuwingen, incidenten of beïnvloede activagegevens wilt weergeven, moet u machtigingen hebben voor Microsoft Defender voor Office of Microsoft Defender voor eindpuntwaarschuwingen, of beide.
  - Als u verhinderde e-mailpogingen wilt bekijken, moet u machtigingen hebben voor microsoft Defender voor Office-gegevens. 
  - Als u risicobeperking wilt weergeven, moet u over machtigingen voor gegevens voor bedreigings- en kwetsbaarheidsbeheer in Microsoft Defender voor Eindpunt zijn.

Houd rekening met de volgende factoren bij het bekijken van de bedreigingsanalysegegevens:
- Grafieken geven alleen risico's weer die worden bijgespoord. Controleer het rapportoverzicht op aanvullende risico's die niet in de grafieken worden weergegeven.
- Risicobeperking garandeert geen volledige tolerantie. De geleverde risico's weerspiegelen de best mogelijke acties die nodig zijn om de tolerantie te verbeteren.
- Apparaten worden geteld als 'niet beschikbaar' als ze geen gegevens naar de service hebben verzonden.
- Antivirusgerelateerde statistieken zijn gebaseerd op de antivirusinstellingen van Microsoft Defender. Apparaten met antivirusoplossingen van derden kunnen worden weergegeven als 'blootgesteld'.

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief bedreigingen zoeken met geavanceerde jacht](advanced-hunting-overview.md) 
- [De sectie Analistrapport begrijpen](threat-analytics-analyst-reports.md)
- [Beveiligingszwakheden en blootstellingen beoordelen en oplossen](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)