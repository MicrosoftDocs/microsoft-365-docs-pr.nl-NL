---
title: Uw beveiligings Posture beoordelen via Microsoft Secure Score
description: Hierin wordt beschreven hoe u actie onderneemt om uw Microsoft Secure score te verbeteren in het Microsoft 365-Beveiligingscentrum.
keywords: beveiliging, malware, Microsoft 365, M365, Secure Score, Security Center, verbeterings acties
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
ms.openlocfilehash: 3b913b3d53abf8c46fbcc9e053f91f512864c9d8
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315829"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Evalueer uw beveiligings Posture met Microsoft Secure Score

Secure Score van Microsoft is een afmeting van de beveiligings Posture van een organisatie, met een hoger nummer voor het uitvoeren van extra verbeterings acties. U vindt het https://security.microsoft.com/securescore in [microsoft 365 Beveiligingscentrum](overview-security-center.md).

Voor de gegevens die u nodig hebt om sneller te kunnen werken, zijn Microsoft-verduidelijkings acties ingedeeld in de volgende groepen:

* Identiteit (Azure Active Directory-accounts & rollen)
* Gegevens (Microsoft-informatiebescherming)
* Apparaat (Microsoft Defender ATP, genaamd [Microsoft Secure score voor apparaten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))
* App (e-mail en Cloud-apps, waaronder Office 365 en de beveiligingsupdates van Microsoft Cloud apps)
* Infrastructuur (geen stappen voor verbetering)

>[!NOTE]
>In de recente release van Microsoft Secure Score is een verbeterd score model vrijgegeven waarmee Microsoft Secure Score tijdelijk niet compatibel is met identiteitsbeveiliging en de Graph API. [Details weergeven](microsoft-secure-score-whats-new.md)

Kijk op de pagina Microsoft Secure Score Overview hoe punten worden verdeeld over de groepen en welke punten beschikbaar zijn. U kunt ook een overzicht van de totale score weergeven, de historische trend van uw veilige Score met benchmark-vergelijkingen en de prioriteit van verbeterings acties voor de verhoging van de score.

![Startpagina beveiligde Score](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a>De huidige Score controleren

Als u op uw huidige score wilt controleren, gaat u naar de pagina Microsoft Secure Score Overview en zoekt u de tegel waarmee **u uw beveiligde Score**kunt uitchecken. Uw score wordt weergegeven als een percentage, samen met het aantal punten dat u uit een totaal aantal mogelijke punten hebt behaald.

Als u de knop **opnemen** naast de Score selecteert, kunt u ook verschillende weergaven van uw Score kiezen. De verschillende Score weergaven worden weergegeven in de grafiek op de Score tegel en het diagram uitsplitsing.

Hier volgen een aantal scores die u aan uw weergave van uw algemene score kunt toevoegen, zodat u een beeld krijgt van uw algemene score:

- **Geplande Score**: geschatte Score weergeven wanneer geplande acties zijn voltooid
- **Huidige licentie**: Score weergeven die kan worden behaald met uw huidige Microsoft-licentie
- **Behaald bare Score**: Toon Score die kan worden behaald met uw Microsoft-licenties en huidige risico acceptatie

In deze weergave ziet u hoe deze eruitziet als u alle mogelijke score weergaven hebt opgenomen:

![Uw veilige Score met inbegrip van de geplande Score, huidige licentie en behaalde score](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a>Onderneem actie om de score te verbeteren

Het **tabblad uitnodigingen bevat een lijst** met mogelijke beveiligingsaanbevelingen waarmee mogelijke aanvals vlakken worden aangegeven. Dit omvat ook hun status (voor adres, gepland, risico geaccepteerd, opgelost via een afwijkende beperking en voltooid). U kunt alle actie-verbeterings acties doorzoeken, filteren en groeperen.  

### <a name="ranking"></a>Waardering

Rangschikking is afhankelijk van het aantal Points-to-to-Points, problemen met de implementatie, de invloed van gebruikers en de complexiteit. De beste rangschikking verbeterings acties bestaan uit een groot aantal punten met minder moeilijkheidsgraad, gebruikers impact en complexiteit.

### <a name="view-improvement-action-details"></a>Details van verbeterings actie weergeven

Wanneer u een bepaalde verbeterings actie selecteert, wordt er een flyout van een volledige pagina weergegeven.  

![Voorbeeld van een vervolgactie-actie- ](../../media/secure-score/secure-score-improvement-action-details.png)
 *afbeelding 2: voorbeeld van de actie flyout*

Om de actie te voltooien, hebt u een paar opties:

* Selecteer **beheren** om het Configuratiescherm te openen en breng de wijziging aan. U krijgt dan de punten waarmee de actie te maken heeft, zichtbaar in de vlucht. De punten duren doorgaans 24 uur voor de update.

* Selecteer **delen** om de directe koppeling naar de actie voor verbetering te kopiëren. U kunt ook het platform kiezen om de koppeling te delen, zoals e-mail, Microsoft teams, Microsoft planner of ServiceNow. Als u ServiceNow selecteert, kunt u een wijzigings ticket maken dat zichtbaar is in ServiceNow en de Microsoft 365 Beveiligingscentrum start. Zie [Microsoft 365 Beveiligingscentrum en ServiceNow-integratie](tickets-security-center.md)voor meer informatie.

### <a name="choose-an-improvement-action-status"></a>De status van een verbeterings actie kiezen

Kies de gewenste statussen en leg aantekeningen voor de actie voor verbetering in.

- **Als u wilt** weten of de verbeterings actie noodzakelijk is en de planning op een bepaald moment in de toekomst op te lossen. Deze status geldt ook voor acties die als gedeeltelijk zijn gedetecteerd, maar nog niet volledig zijn voltooid.
- **Gepland** -er zijn beton plannen om de actie te voltooien.
- **Risico geaccepteerd** : beveiliging moet altijd met behulp van bruikbaarheid worden evenwichtig, en niet alle aanbevelingen werken voor uw omgeving. Als dat het geval is, kunt u ervoor kiezen om het risico of het resterende risico te accepteren en niet de actie te ondernemen. U ontvangt geen punten, maar de actie is niet meer zichtbaar in de lijst met verbeterings acties. U kunt deze actie in geschiedenis weergeven of op elk moment ongedaan maken.
- **Opgelost via** een afwijkende **beperking** -de actie voor verbetering is al geadresseerd door een toepassing of software van derden, of een intern hulpprogramma. U krijgt de punten waarmee de actie waard is, zodat uw score beter aansluit op uw totale beveiligings posture. Als het besturingselement van een derde of een interne tool niet meer wordt bedekt, kunt u een andere status kiezen. Houd er rekening mee dat Microsoft niet meer inzicht heeft in de implementatie van de implementatie als de actie voor verbetering is gemarkeerd als een van deze statussen.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Bedreiging & acties voor kwaliteitsbeheer

U kunt geen statussen kiezen voor verbeterings acties in de categorie apparaat. In plaats daarvan wordt u doorgestuurd naar de [& bijbehorende beveiligingsaanbevelingen van de beveiligings beveiligings](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) functies in het [Microsoft Defender-Beveiligingscentrum](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) , zodat u actie kunt ondernemen. De uitzondering die u hebt gekozen en rechtvaardigt, is specifiek voor die portal. Dit is niet aanwezig in de Microsoft Secure Score Portal.

#### <a name="completed-improvement-actions"></a>Voltooide stappen voor verbetering

Verbeterings acties hebben een ' voltooide ' status wanneer alle mogelijke punten voor de actie voor verbetering zijn behaald. Voltooide stappen voor verbetering worden bevestigd met Microsoft-gegevens, en u kunt de status niet wijzigen.

### <a name="assess-information-and-review-user-impact"></a>Informatie beoordelen en gevolgen van de gebruiker controleren

In de sectie **in een oogopslag** ziet u de categorie, een aanval waarmee de categorie kan worden beschermd, en het product.

Het **effect** van de gebruiker laat zien wat de gebruikers ondervinden als de actie voor verbetering wordt uitgevaardigd en de **gebruikers van invloed** zijn op de ervaring die dit heeft.

### <a name="implement-the-improvement-action"></a>De actie voor verbetering implementeren

In de sectie **implementatie** worden alle vereisten weergegeven, stapsgewijs de volgende stappen om de actie uit te voeren, de huidige implementatiestatus van de actie voor verbetering en de koppelingen meer informatie.

Voor de vereisten gelden alle licenties die moeten worden verkregen of acties die moeten worden voltooid voordat de actie actie moet worden verholpen. Zorg ervoor dat uw licentie voldoende stoelen bevat voor het voltooien van de verbeterings actie en dat deze licenties gelden voor de noodzakelijke gebruikers.  

## <a name="we-want-to-hear-from-you"></a>We horen graag van u

Als u problemen ondervindt, kunt u het ons laten weten dat u de community [beveiliging, Privacy & naleving](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . We volgen de community en bieden hulp.

## <a name="related-resources"></a>Verwante informatiebronnen

- [Overzicht van Microsoft Secure Score](microsoft-secure-score.md)
- [De geschiedenis van uw Microsoft Secure Score bijhouden en bereiken](microsoft-secure-score-history-metrics-trends.md)
- [Binnenkort beschikbaar](microsoft-secure-score-whats-coming.md)
- [Nieuwe functies](microsoft-secure-score-whats-new.md)