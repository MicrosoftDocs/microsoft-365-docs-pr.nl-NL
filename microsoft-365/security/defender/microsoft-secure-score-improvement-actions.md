---
title: Uw beveiligingsbeleid beoordelen via Microsoft Secure Score
description: Hier wordt beschreven hoe u actie onderneemt om uw Microsoft Secure Score te verbeteren in het Microsoft 365-beveiligingscentrum.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
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
ms.openlocfilehash: 2b211eb0f55a9fa9faad1290443d62ac406f8360
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058581"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Uw beveiligingsbeleid beoordelen met Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft Secure Score is een meting van de beveiligingsstatus van een organisatie, waarbij een hoger aantal aangeeft dat er meer verbeteracties zijn uitgevoerd. Deze is te vinden https://security.microsoft.com/securescore in het [Microsoft 365-beveiligingscentrum.](overview-security-center.md)

Om u te helpen sneller de informatie te vinden die u nodig hebt, zijn Microsoft-verbeteracties ingedeeld in groepen:

* Identiteit (Azure Active Directory-accounts & rollen)
* Apparaat (Microsoft Defender voor eindpunt, bekend als [Microsoft Secure Score voor apparaten](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))
* App (e-mail- en cloud-apps, waaronder Office 365 en Microsoft Cloud App Security)

>[!NOTE]
>In de recente release van Microsoft Secure Score is een verbeterd scoremodel uitgebracht, waardoor Microsoft Secure Score tijdelijk niet compatibel is met Identity Secure Score en de Graph API. [Details weergeven](microsoft-secure-score-whats-new.md)

Bekijk op de overzichtspagina van Microsoft Secure Score hoe punten worden gesplitst tussen deze groepen en welke punten beschikbaar zijn. U kunt ook een volledig overzicht krijgen van de totale score, de historische trend van uw veilige score met benchmarkvergelijkingen en prioriteitsverbeteringsacties die kunnen worden genomen om uw score te verbeteren.

![Startpagina van Secure Score](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a>Uw huidige score controleren

Als u uw huidige score wilt controleren, gaat u naar de overzichtspagina van Microsoft Secure Score en gaat u naar de tegel met de naam **Uw veilige score.** Uw score wordt weergegeven als een percentage, samen met het aantal punten dat u hebt bereikt buiten de totale mogelijke punten.

Als u bovendien de  knop Opnemen naast uw score selecteert, kunt u verschillende weergaven van uw score kiezen. Deze verschillende scoreweergaven worden weergegeven in de grafiek op de scoretegel en het puntverdelingsdiagram.

De volgende scores zijn scores die u kunt toevoegen aan uw weergave van uw totale score om u een vollediger beeld te geven van uw totale score:

- **Geplande score:** geplande score tonen wanneer geplande acties zijn voltooid
- **Huidige licentiescore:** score laten zien die kan worden bereikt met uw huidige Microsoft-licentie
- **Haalbare score:** score laten zien die kan worden bereikt met uw Microsoft-licenties en huidige acceptatie van risico's

Deze weergave ziet er zo uit als u alle mogelijke scoreweergaven hebt opgenomen:

![Uw veilige score, inclusief geplande score, huidige licentiescore en haalbare score](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a>Actie ondernemen om uw score te verbeteren

Op **het tabblad Acties voor** verbetering worden de beveiligingsaanbevelingen weergegeven die mogelijke aanvalsoppervlakken kunnen aanpakken. Het bevat ook hun status (om te adressering, gepland, geaccepteerd risico, opgelost via derden, opgelost door middel van alternatieve mitigatie en voltooid). U kunt alle verbeteracties zoeken, filteren en groeperen.  

### <a name="ranking"></a>Rangschikking

Classificatie is gebaseerd op het aantal punten dat nog moet worden bereikt, implementatieproblemen, gebruikerseffect en complexiteit. De best gerangschikte verbeteringsacties hebben een groot aantal punten dat overblijft met lage problemen, gebruikerseffecten en complexiteit.

### <a name="view-improvement-action-details"></a>Details van actie voor verbetering weergeven

Wanneer u een specifieke verbeteringsactie selecteert, wordt een volledige pagina-flyout weergegeven.  

![Voorbeeld van actie-flyout voor verbeteractie](../../media/secure-score/secure-score-improvement-action-details.png)

Als u de actie wilt voltooien, hebt u een paar opties:

- Selecteer **Beheren** om naar het configuratiescherm te gaan en de wijziging aan te brengen. U krijgt dan de punten die de actie waard is, zichtbaar in de fly out. Het bijwerken van punten duurt meestal ongeveer 24 uur.

- Selecteer **Delen** om de directe koppeling naar de verbeteringsactie te kopiëren. U kunt ook het platform kiezen om de koppeling te delen, zoals e-mail, Microsoft Teams, Microsoft Planner of ServiceNow. Als u ServiceNow selecteert, kunt u een wijzigingsticket maken dat zichtbaar is in ServiceNow en het Microsoft 365-beveiligingscentrum thuis. Zie Microsoft [365-beveiligingscentrum en ServiceNow-integratie](./tickets.md)voor meer informatie.

Voeg **Notities toe** om de voortgang bij te houden of iets anders waar u opmerkingen over wilt maken. Als u uw eigen **tags toevoegt aan** de actie voor verbetering, kunt u filteren op deze tags.

### <a name="choose-an-improvement-action-status"></a>Een actiestatus voor verbetering kiezen

Kies eventuele statussen en noteert notities die specifiek zijn voor de verbeteringsactie.

- **Adres:** u erkent dat de verbeteringsactie nodig is en bent van plan deze op een bepaald moment in de toekomst aan te pakken. Deze status is ook van toepassing op acties die worden gedetecteerd als gedeeltelijk, maar niet volledig zijn voltooid.
- **Gepland:** er zijn concrete plannen om de verbeteringsactie te voltooien.
- **Risico geaccepteerd:** beveiliging moet altijd in balans zijn met bruikbaarheid en niet elke aanbeveling werkt voor uw omgeving. Als dat het geval is, kunt u ervoor kiezen om het risico of het resterende risico te accepteren en de verbeteringsactie niet uit te voeren. U krijgt geen punten, maar de actie is niet meer zichtbaar in de lijst met verbeteracties. U kunt deze actie op elk moment in de geschiedenis bekijken of ongedaan maken.
- **Opgelost via derden en** **opgelost** door middel van alternatieve mitigatie: de verbeteringsactie is al opgelost door een toepassing of software van derden of een intern hulpprogramma. U krijgt de punten die de actie waard is, zodat uw score beter uw algehele beveiligingshouding weerspiegelt. Als het besturingselement niet meer wordt bedekt door een externe of interne tool, kunt u een andere status kiezen. Houd er rekening mee dat Microsoft geen inzicht heeft in de volledigheid van de implementatie als de verbeteringsactie is gemarkeerd als een van deze statussen.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Acties & beveiligingsprobleembeheer

Voor verbeteracties in de categorie 'Apparaat' kunt u geen statussen kiezen. In plaats daarvan wordt u doorgestuurd naar de beveiligingsaanbeveling voor bedreigings- en beveiligingsrisico's [in](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) het [Microsoft Defender-beveiligingscentrum](/windows/security/threat-protection/microsoft-defender-atp/use) om actie te ondernemen. De uitzondering die u kiest en uitvulling die u schrijft, is specifiek voor die portal. Deze is niet aanwezig in de Microsoft Secure Score-portal.

#### <a name="completed-improvement-actions"></a>Acties voor voltooide verbetering

Verbeteracties hebben een 'voltooide' status zodra alle mogelijke punten voor de verbeteringsactie zijn bereikt. Voltooide verbeteracties worden bevestigd hoewel Microsoft-gegevens en u kunt de status niet wijzigen.

### <a name="assess-information-and-review-user-impact"></a>Informatie beoordelen en de impact van de gebruiker controleren

In de sectie **Met de naam In één** oogopslag ziet u de categorie, de aanvallen die het kan beschermen tegen en het product.

**Gebruikersimpact** is wat de gebruikers zullen ervaren als  de verbeteringsactie wordt aan genomen en gebruikers die worden beïnvloed, de personen zijn die worden beïnvloed.

### <a name="implement-the-improvement-action"></a>De verbeteringsactie implementeren

In **de sectie** Implementatie ziet u alle vereisten, stapsgewijs volgende stappen om de verbeteringsactie, de huidige implementatiestatus van de verbeteringsactie en meer koppelingen te voltooien.

Vereisten zijn licenties die nodig zijn of acties die moeten worden voltooid voordat de verbeteringsactie wordt aangepakt. Zorg ervoor dat u voldoende seats in uw licentie hebt om de verbeteringsactie uit te voeren en dat deze licenties worden toegepast op de benodigde gebruikers.  

## <a name="we-want-to-hear-from-you"></a>Wij horen graag van u

Als u problemen hebt, laat het ons weten door een bericht te plaatsen in de [beveiligings-, privacy- & Compliance-community.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) We houden de community in de gaten en bieden hulp.

## <a name="related-resources"></a>Verwante informatiebronnen

- [Overzicht van Microsoft Secure Score](microsoft-secure-score.md)
- [Uw Microsoft Secure Score-geschiedenis bijhouden en doelstellingen behalen](microsoft-secure-score-history-metrics-trends.md)
- [Binnenkort beschikbaar](microsoft-secure-score-whats-coming.md)
- [Wat is er nieuw](microsoft-secure-score-whats-new.md)