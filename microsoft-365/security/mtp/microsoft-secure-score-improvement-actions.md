---
title: Beoordeel uw beveiligingsrisico's via Microsoft Secure Score
description: Hier wordt beschreven hoe u actie onderneemt om uw Microsoft Secure Score te verbeteren in het Microsoft 365-beveiligingscentrum.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft-beveiligingsscore, Microsoft 365-beveiligingscentrum, acties voor verbetering
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 8cf416e773abc6cbe1fd891fcec9f02a5011c413
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930640"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Beoordeel uw beveiligingsrisico met Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft Secure Score is een meting van de beveiligingsrisico's van een organisatie, met een hoger getal dat aangeeft dat er meer acties zijn ondernomen. U vindt deze in https://security.microsoft.com/securescore het [Microsoft 365-beveiligingscentrum.](overview-security-center.md)

Microsoft-acties voor kwaliteitsverbetering zijn in groepen ingedeeld, om u te helpen sneller de informatie te krijgen die u nodig hebt:

* Identiteit (Azure Active Directory-accounts & rollen)
* Apparaat (Microsoft Defender voor eindpunt, ook wel [Microsoft Secure Score voor apparaten genoemd)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices)
* App (e-mail- en cloud-apps, inclusief Office 365 en Microsoft Cloud App-beveiliging)

>[!NOTE]
>In de recente release van Microsoft Secure Score is een verbeterd scoremodel uitgebracht, waardoor Microsoft Secure Score tijdelijk niet compatibel is met Identity Secure Score en de Graph API. [Details weergeven](microsoft-secure-score-whats-new.md)

Bekijk op de overzichtspagina van Microsoft Secure Score hoe punten zijn gesplitst tussen deze groepen en welke punten beschikbaar zijn. U kunt ook een volledig overzicht krijgen van de totale score, de historische trend van uw veilige score met vergelijkingen in vergelijkingen en acties ter verbetering die kunnen worden ondernomen om uw score te verbeteren.

![Secure Score-startpagina](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a>Uw huidige score controleren

Als u uw huidige score wilt bekijken, gaat u naar de overzichtspagina van Microsoft Secure Score en kijkt u naar de tegel met de naam **Uw veilige score.** Uw score wordt weergegeven als een percentage, samen met het aantal punten dat u hebt bereikt van het totaal aantal mogelijke punten.

Als u bovendien de knop Opnemen **naast** uw score selecteert, kunt u verschillende weergaven van uw score kiezen. Deze verschillende scoreweergaven worden weergegeven in de grafiek op de scoretegel en in het uitsplitsingsdiagram.

Hieronder vindt u de scores die u kunt toevoegen aan uw weergave van uw algehele score, zodat u een vollediger beeld krijgt van uw algehele score:

- **Geplande score:** de geplande score tonen wanneer geplande acties zijn voltooid
- **Huidige licentiescore:** score tonen die kan worden bereikt met uw huidige Microsoft-licentie
- **Haalbare score:** toon een score die kan worden bereikt met uw Microsoft-licenties en huidige acceptatie van risico's

Deze weergave ziet er zo uit als u alle mogelijke scoreweergaven hebt opgenomen:

![Uw veilige score inclusief de geplande score, de huidige licentiescore en de haalbare score](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a>Actie ondernemen om uw score te verbeteren

Op **het tabblad Acties voor** verbetering worden de beveiligingsaanbevelingen vermeld die mogelijke aanvallen aanpakken. Het omvat ook hun status (te adressering, gepland, geaccepteerd risico, opgelost via derden, opgelost via alternatieve risicobeperking en voltooid). U kunt alle acties ter verbetering zoeken, filteren en groeperen.  

### <a name="ranking"></a>Classificatie

De classificatie is gebaseerd op het aantal punten dat nog moet worden bereikt, problemen met de implementatie, de gevolgen en complexiteit van de gebruiker. Bij de acties voor kwaliteitsverbetering blijft een groot aantal punten over met lage problemen, gevolgen en complexiteit van de gebruiker.

### <a name="view-improvement-action-details"></a>Details van actie voor kwaliteitsverbetering weergeven

Wanneer u een specifieke actie voor verbetering selecteert, wordt een flyout voor een volledige pagina weergegeven.  

![Voorbeeld van flyout actie voor verbetering](../../media/secure-score/secure-score-improvement-action-details.png)

Als u de actie wilt voltooien, hebt u een aantal opties:

- Selecteer **Beheren om** naar het configuratiescherm te gaan en de wijziging aan te brengen. Vervolgens krijgt u de punten die de actie waard is, zichtbaar in de fly-out. Over het algemeen duurt het ongeveer 24 uur voordat de punten zijn bijgewerkt.

- Selecteer **Delen** om de directe koppeling naar de actie voor kwaliteitsverbetering te kopiëren. U kunt ook het platform kiezen waarop u de koppeling wilt delen, zoals e-mail, Microsoft Teams, Microsoft Planner of ServiceNow. Als u Nu kiezen voor ServiceNow, kunt u een wijzigingsticket maken dat zichtbaar is in ServiceNow en in het Microsoft 365-beveiligingscentrum. Zie het [Microsoft 365-beveiligingscentrum en de servicenow-integratie](tickets-security-center.md)voor meer informatie.

Voeg **notities** toe om de voortgang bij te houden of iets anders waar u opmerkingen bij wilt plaatsen. Als u uw eigen **tags aan de** actie voor kwaliteitsverbetering toevoegt, kunt u op deze tags filteren.

### <a name="choose-an-improvement-action-status"></a>Een status voor een actie voor kwaliteitsverbetering kiezen

Kies eventuele statussen en noteert notities die specifiek zijn voor de verbeteringsactie.

- **Ter geadresseerde:** u erkent dat de actie voor verbetering noodzakelijk is en bent van plan deze op een bepaald moment in de toekomst te gaan aanpakken. Deze status geldt ook voor acties die worden gedetecteerd als gedeeltelijk, maar niet volledig voltooid.
- **Gepland:** er zijn concrete plannen om de actie voor kwaliteitsverbetering uit te voeren.
- **Risico geaccepteerd:** beveiliging moet altijd in balans zijn met bruikbaarheid en niet elke aanbeveling werkt voor uw omgeving. Wanneer dit het geval is, kunt u ervoor kiezen om het risico of het resterende risico te accepteren en de actie voor verbetering niet uit te voeren. U krijgt geen punten, maar de actie is niet meer zichtbaar in de lijst met acties voor kwaliteitsverbetering. U kunt deze actie op elk moment in de geschiedenis bekijken of ongedaan maken.
- **Opgelost via derden en** opgelost via alternatieve risicobeperking-  De actie voor verbetering is al opgelost door een toepassing of software van derden, of een intern hulpprogramma. U krijgt de punten die de actie waard is, zodat uw score beter uw algehele beveiligingsovername weerspiegelt. Als een derde partij of intern hulpprogramma het beheer niet meer dekt, kunt u een andere status kiezen. Houd er rekening mee dat Microsoft geen inzicht heeft in de volledigheid van de implementatie als de actie voor verbetering is gemarkeerd als een van deze statussen.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Acties & beveiligingsprobleembeheer te verbeteren

Voor acties ter verbetering in de categorie 'Apparaat' kunt u geen statussen kiezen. In plaats daarvan wordt u doorgestuurd naar de beveiligingsaanbeveling voor risico- en beveiligingsrisicobeheer [in](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) het [Microsoft Defender-beveiligingscentrum](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) om actie te ondernemen. De uitzondering die u kiest en uitvulling die u schrijft, is specifiek voor die portal. Deze is niet aanwezig in de Microsoft Secure Score-portal.

#### <a name="completed-improvement-actions"></a>Voltooide acties voor verbetering

Acties ter verbetering hebben een 'voltooide' status zodra alle mogelijke punten voor de actie voor verbetering zijn bereikt. Voltooide acties ter verbetering worden bevestigd hoewel Microsoft-gegevens en u kunt de status niet wijzigen.

### <a name="assess-information-and-review-user-impact"></a>Informatie beoordelen en de gevolgen van gebruikers bekijken

De sectie met **de naam In één oogopslag** geeft de categorie aan, aanvallen die het kan beschermen tegen en het product.

**Gebruikersim** impact is wat de gebruikers zullen ervaren als de actie voor verbetering wordt van invloed is en **Gebruikers** zijn de personen die worden beïnvloed.

### <a name="implement-the-improvement-action"></a>De actie voor verbetering implementeren

In **de** sectie Implementatie worden alle vereisten bewaarde, stapsgewijs volgende stappen om de actie voor verbetering uit te voeren, de huidige implementatiestatus van de actie voor verbetering en koppelingen voor meer informatie.

Vereisten zijn onder andere licenties die nodig zijn of acties die moeten worden voltooid voordat de actie voor verbetering wordt aangepakt. Zorg ervoor dat uw licentie voldoende seats heeft om de actie voor kwaliteitsverbetering uit te voeren en dat deze licenties worden toegepast op de benodigde gebruikers.  

## <a name="we-want-to-hear-from-you"></a>Wij horen graag van u

Als u problemen hebt, laat het ons dan weten door berichten te plaatsen in de community [over beveiliging, & compliance.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) We houden de community in de gaten en bieden hulp.

## <a name="related-resources"></a>Verwante informatiebronnen

- [Overzicht van Microsoft Secure Score](microsoft-secure-score.md)
- [Uw geschiedenis van Microsoft Secure Score bijhouden en doelstellingen behalen](microsoft-secure-score-history-metrics-trends.md)
- [Binnenkort beschikbaar](microsoft-secure-score-whats-coming.md)
- [Wat is er nieuw](microsoft-secure-score-whats-new.md)
