---
title: Krijg inzicht in uw beveiligingshouding via Microsoft Secure Score
description: Beschrijft hoe u actie ondernemen om uw Microsoft Secure Score te verbeteren in het Microsoft 365-beveiligingscentrum.
keywords: beveiliging, malware, Microsoft 365, M365, secure score, security center, verbeteracties
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 0ae1a196f11f383c1d3f9fd2056d5d19e7cdd6da
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/10/2020
ms.locfileid: "45095026"
---
# <a name="gain-visibility-into-your-security-posture-through-microsoft-secure-score"></a>Krijg inzicht in uw beveiligingshouding via Microsoft Secure Score

Microsoft Secure Score is een meting van de beveiligingshouding van een organisatie, waarbij een hoger aantal aangeeft dat er meer verbeteringsacties worden ondernomen. Het kan worden gevonden op https://security.microsoft.com/securescore in de [Microsoft 365 security center](overview-security-center.md).

Om u sneller te helpen met de informatie die u nodig hebt, worden de verbeteracties van Microsoft in groepen georganiseerd:

* Identiteit (Azure AD-accounts & rollen)
* Gegevens (Microsoft Information Protection)
* Apparaat (Microsoft Defender ATP, bekend als [Configuratiescore](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configuration-score))
* App (e-mail- en cloud-apps, waaronder Office 365 en Microsoft Cloud App Security)
* Infrastructuur (voorlopig geen verbeteringsacties)

>[!NOTE]
>In de recente release van Microsoft Secure Score is een verbeterd scoremodel uitgebracht waardoor Microsoft Secure Score tijdelijk niet compatibel is met Identity Secure Score en de Graph API. [Details weergeven](microsoft-secure-score.md#incompatibility-with-identity-secure-score-and-graph-api)

Op de overzichtspagina van Microsoft Secure Score u zien hoe punten worden verdeeld tussen deze groepen en welke punten beschikbaar zijn. De overzichtspagina is ook de plek om een all-up weergave te krijgen van de totale score, historische trend van uw veilige score met benchmarkvergelijkingen en geprioriteerde verbeteracties die kunnen worden genomen om uw score te verbeteren.

![Startpagina beveiligde score](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a>Uw huidige score controleren

Als u uw huidige score wilt controleren, gaat u naar de overzichtspagina van microsoft secure score en zoekt u naar de tegel met de tekst **Uw veilige score.** Uw score wordt weergegeven als een percentage, samen met het aantal punten dat u hebt bereikt uit een totaal mogelijke punten.

Als u bovendien de knop **Opnemen** naast uw score selecteert, u verschillende weergaven van uw score kiezen. Deze verschillende scoreweergaven worden weergegeven in de grafiek op de scoretegel en het puntuitsplitsingsdiagram.

De volgende scores zijn scores die u toevoegen aan uw weergave van uw algemene score om u een vollediger beeld van uw totale score te geven:

- **Geplande score**: Verwachte score weergeven wanneer geplande acties zijn voltooid
- **Huidige licentiescore**: Score weergeven die kan worden bereikt met uw huidige Microsoft-licentie
- **Haalbare score**: Score weergeven die kan worden bereikt met uw Microsoft-licenties en de huidige risicoacceptatie

Dit is hoe het eruit zal zien als je alle mogelijke scoreweergaven hebt opgenomen:

![Uw veilige score inclusief geplande score, huidige licentiescore en haalbare score](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a>Onderneem actie om je score te verbeteren

Op het tabblad **Verbeteracties** worden de beveiligingsaanbevelingen weergegeven die mogelijke aanvalsoppervlakken aanpakken, samen met hun status (om aan te pakken, gepland, risico geaccepteerd, opgelost via derden, opgelost door alternatieve mitigatie en voltooid). U alle verbeteracties zoeken, filteren en groeperen.  

### <a name="ranking"></a>Ranking

Ranking is gebaseerd op het aantal resterende punten dat nog moet worden bereikt, implementatieproblemen, gebruikersimpact en complexiteit. De hoogst gerangschikte verbeteringsacties hebben een groot aantal punten die met lage moeilijkheidsgraad, gebruikerseffect, en ingewikkeldheid blijven.

### <a name="view-improvement-action-details"></a>Details van de verbeteringsactie weergeven

Wanneer u een specifieke verbeteringsactie selecteert, wordt een flyout voor de volledige pagina weergegeven.  

![Voorbeeld van flyout van de actie voor verbetering ](../../media/secure-score/secure-score-improvement-action-details.png)
 *figuur 2: Flyout voor de actie verbetering*

Als u de actie wilt voltooien, hebt u een aantal opties:

* Selecteer **Beheren** om het configuratiescherm te gaan en de wijziging aan te brengen. U krijgt dan de punten die de actie waard is, zichtbaar in de fly out. Punten duren over het algemeen ongeveer 24 uur om te updaten.

* Selecteer **Delen** om de directe koppeling naar de verbeteringsactie te kopiëren of kies het platform om de koppeling te delen, zoals e-mail, Microsoft Teams, Microsoft Planner of ServiceNow. Als u ServiceNow selecteert, u een wijzigingsticket maken dat zichtbaar is in ServiceNow en het microsoft 365-beveiligingscentrum thuis. Zie [Microsoft 365-beveiligingscentrum en ServiceNow-integratie](tickets-security-center.md)voor meer informatie.

### <a name="choose-an-improvement-action-status"></a>Een status voor verbeteringsactie kiezen

Kies statussen en nota's die specifiek zijn voor de verbeteringsactie. De beelden die u selecteren zijn de volgende:

* **Aan te pakken** - U erkent dat de verbetering actie nodig is en van plan om het aan te pakken op een bepaald punt in de toekomst. Deze status is ook van toepassing op acties die gedeeltelijk worden gedetecteerd, maar niet volledig zijn voltooid.
* **Gepland** — Er zijn concrete plannen om de verbeteractie af te ronden.
* **Geaccepteerde risico's** — Beveiliging moet altijd in evenwicht zijn met bruikbaarheid, en niet elke aanbeveling zal werken voor uw omgeving. Wanneer dat het geval is, u ervoor kiezen om het risico, of het resterende risico te accepteren, en niet de verbetering actie uit te voeren. U krijgt geen punten, maar de actie is niet langer zichtbaar in de lijst met verbeteracties. U deze actie in de geschiedenis bekijken of op elk gewenst moment ongedaan maken.
* **Opgelost via derden** en **opgelost door alternatieve mitigatie** - De verbeteringsactie is al verholpen door een toepassing of software van derden of een intern hulpmiddel. U krijgt de punten die de actie waard is, zodat uw score beter weerspiegelt uw algehele veiligheid houding. Als een derde partij of intern gereedschap het besturingselement niet meer dekt, u een andere status kiezen. Houd er rekening mee dat Microsoft geen inzicht heeft in de volledigheid van de implementatie als de verbeteringsactie is gemarkeerd als een van deze statussen.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Verbeteracties voor & vulnerability management

Voor verbeteracties in de categorie 'Apparaat' u geen statussen kiezen. In plaats daarvan wordt u doorverwezen naar de bijbehorende [beveiligingsaanbeveling voor Threat & Vulnerability Management (TVM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in het [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) om actie te ondernemen. De uitzondering die u kiest en rechtvaardiging die u schrijft, is specifiek voor die portal en is niet aanwezig in de Microsoft Secure Score-portal.

#### <a name="completed-improvement-actions"></a>Voltooide verbeteringsacties

Verbeteringsacties hebben een "voltooide" status zodra alle mogelijke punten voor de verbeteringsactie zijn bereikt. Voltooide verbeteringsacties worden bevestigd met Microsoft-gegevens en u de status niet wijzigen.

### <a name="assess-information-and-review-user-impact"></a>Informatie beoordelen en de impact van de gebruiker beoordelen

De **in één oogopslag** sectie vertelt u de categorie, aanvallen die het kan beschermen tegen, en het product.

De **impact van** de gebruiker laat zien wat de gebruikers zullen ervaren als de verbeteringsactie wordt uitgevoerd en gebruikers die er last **van** hebben, laat zien wie deze zal ervaren.

### <a name="implement-the-improvement-action"></a>De verbeteringsactie uitvoeren

In de sectie **Implementatie** worden alle vereisten weergegeven, stap voor stap volgende stappen om de verbeteringsactie te voltooien, de huidige implementatiestatus van de verbeteringsactie en meer koppelingen.

Voorwaarde is dat er licenties moeten worden verkregen of acties die moeten worden voltooid voordat de verbeteringsactie wordt aangepakt. Zorg ervoor dat u voldoende plaatsen in uw licentie hebt om de verbeteringsactie te voltooien en dat deze licenties worden toegepast op de benodigde gebruikers.  

## <a name="we-want-to-hear-from-you"></a>We willen graag van u horen

Als je problemen hebt, laat het ons weten door een bericht te plaatsen in de [community Beveiliging, privacy & Compliance.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) We houden de gemeenschap in de gaten en zullen hulp bieden.

## <a name="related-resources"></a>Verwante informatiebronnen

- [Overzicht van Microsoft Secure Score](microsoft-secure-score.md)
- [Uw Microsoft Secure Score-geschiedenis bijhouden en doelen bereiken](microsoft-secure-score-history-metrics-trends.md)
- [Binnenkort beschikbaar](microsoft-secure-score-whats-coming.md)