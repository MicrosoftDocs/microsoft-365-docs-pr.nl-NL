---
title: Insider risk management Users dashboard
description: Meer informatie over insider risk management Gebruikers dashboard in Microsoft 365
keywords: Microsoft 365, intern risicobeheer, risicobeheer, naleving
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: e59fb8a32275a2ef7c4865e93400b97ad5560df5
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "52161726"
---
# <a name="insider-risk-management-users-dashboard"></a>Insider risk management Users dashboard

Het **gebruikersdashboard** is een belangrijk hulpmiddel in de insider-werkstroom voor risicobeheer en helpt onderzoekers en analisten een vollediger inzicht te krijgen in risicoactiviteiten. Dit dashboard biedt weergaven en beheerfuncties om te voldoen aan de administratieve behoeften tussen het maken van insider-beleid voor risicobeheer en het beheren van gevallen van insiderrisicobeheer.

Nadat gebruikers zijn toegevoegd aan beleidsregels voor insiderrisicobeheer, worden achtergrondprocessen automatisch gebruikersactiviteiten voor [triggeringindicatoren evalueren.](insider-risk-management-settings.md#indicators) Nadat triggering indicators aanwezig zijn, worden aan gebruikersactiviteiten risicoscores toegewezen. Sommige van deze activiteiten kunnen leiden tot een insiderrisicowaarschuwing, maar sommige activiteiten voldoen mogelijk niet aan een minimumrisicoscoreniveau en er wordt geen insiderrisicowaarschuwing gemaakt. Met **het dashboard** Gebruikers kunt u gebruikers weergeven met dit type indicatoren en risicoscores, evenals gebruikers met actieve insiderrisicowaarschuwingen.

Meer informatie over hoe gebruikers in het dashboard Gebruikers in de volgende scenario's worden weergegeven:

- Gebruikers met waarschuwingen voor actief insiderrisicobeleid
- Gebruikers met triggering-gebeurtenissen
- Gebruikers die tijdelijk zijn toegevoegd aan beleidsregels

## <a name="users-with-active-insider-risk-policy-alerts"></a>Gebruikers met waarschuwingen voor actief insiderrisicobeleid

In **het dashboard Gebruikers** worden automatisch alle gebruikers weergegeven met waarschuwingen voor actief insiderrisicobeleid. Deze gebruikers met waarschuwingen hebben zowel een triggering indicator als een activiteitsrisicoscore die voldoet aan de vereisten voor het maken van een insiderrisicowaarschuwing. Activiteiten voor deze gebruikers worden weergegeven door de gebruiker te selecteren in het **dashboard** Gebruikers en naar het tabblad **Gebruikersactiviteit te** navigeren.

## <a name="users-with-triggering-events"></a>Gebruikers met triggering-gebeurtenissen

In **het dashboard** Gebruikers worden automatisch alle gebruikers weergegeven met triggeringgebeurtenissen, maar die geen activiteitsrisicoscore hebben die een insiderrisicowaarschuwing zou maken. Een gebruiker met een gerapporteerde aftredingsdatum wordt bijvoorbeeld weergegeven omdat deze activiteit een triggeringgebeurtenis is, maar geen activiteit is met een risicoscore. Activiteiten voor deze gebruikers worden weergegeven door de gebruiker te selecteren in het **dashboard** Gebruikers en naar het tabblad **Gebruikersactiviteit te** navigeren.

## <a name="users-added-temporarily-to-policies"></a>Gebruikers die tijdelijk zijn toegevoegd aan beleidsregels

Het **dashboard Gebruikers** bevat gebruikers die zijn toegevoegd aan beleid voor insiderrisicobeheer na een ongebruikelijke gebeurtenis buiten de insider-werkstroom voor risicobeheer. Het tijdelijk toevoegen van gebruikers (vanuit het dashboard Beleid) is ook een manier om gebruikersactiviteit te gaan noteren voor een beleid voor insiderrisicobeheer voor het testen van het beleid, zelfs als een vereiste connector niet is geconfigureerd.

Wanneer een gebruiker handmatig wordt toegevoegd aan een beleid, worden de gebruikersactiviteiten van de afgelopen 90 dagen gescored en toegevoegd aan de tijdlijn **gebruikersactiviteit.** U hebt bijvoorbeeld een gebruiker die momenteel geen risicoscores heeft toegewezen voor een insiderrisicobeleid en de gebruiker heeft activiteiten met gegevenslekken gerapporteerd bij de juridische afdeling in uw organisatie. De juridische afdeling raadt u aan om nieuwe vereisten voor korte termijncontrole voor de gebruiker te configureren. U kunt de gebruiker tijdelijk toewijzen aan uw beleid voor gegevenslekken voor een bepaalde periode *(activeringsvenster).* Alle gebruikers die tijdelijk zijn toegevoegd, worden weergegeven in het **dashboard Gebruikers,** omdat triggeringgebeurtenisvereisten worden opgehefd.

>[!NOTE]
>Het kan enkele uren duren voordat nieuwe gebruikers die handmatig zijn toegevoegd, worden weergegeven in het **dashboard Gebruikers.** Het kan tot 24 uur duren voordat de activiteiten van de afgelopen 90 dagen voor deze gebruikers worden weergegeven. Als u activiteiten wilt weergeven voor handmatig toegevoegde gebruikers, selecteert u de gebruiker op het **dashboard** Gebruikers en opent u het tabblad **Gebruikersactiviteit** in het detailvenster.

De gebruiker wordt automatisch verwijderd uit het **gebruikersdashboard** en de score wordt gestopt wanneer de tijd die is gedefinieerd in het activeringsvenster **verloopt** als:

- de gebruiker geen extra triggeringgebeurtenissen of waarschuwingen voor insiderrisicobeleid heeft, en
- als de handmatig gedefinieerde **duur van het activeringsvenster** langer is dan de duur van het globale beleid **activeringsvenster.**

De **instelling activeringsvenster** met de langste  duur overschrijven altijd de instelling van het activeringsvenster met een kortere duur. U hebt bijvoorbeeld het venster  Activering geconfigureerd  op het tabblad Globale beleidstermijnen in de algemene instellingen voor insiderrisicobeheer voor 15 dagen, die automatisch worden toegepast op al uw insiderrisicobeleid. 

U voegt tijdelijk een gebruiker toe aan uw insiderrisicobeleid voor *gegevenslekken* en definieert 30 dagen als het **activeringsvenster** voor deze gebruiker. De globale **activeringsvensterinstelling** van 15 dagen wordt  overgenomen door de instelling activeringsvenster van 30 dagen voor de tijdelijk toegevoegde gebruiker te definiëren. De tijdelijk toegevoegde gebruiker blijft in het **dashboard Gebruikers en** blijft 30 dagen binnen het bereik van het beleid.

In het tegenovergestelde  scenario waarin de instelling  voor het globale activeringsvenster langer is dan de instelling  activeringsvenster die is gedefinieerd voor een tijdelijk toegevoegde gebruiker, wordt de instelling voor het activeringsvenster voor de tijdelijk toegevoegde gebruiker vervangen door de algemene instelling activeringsvenster.  De tijdelijk toegevoegde gebruiker blijft in het dashboard Gebruikers **en** is binnen bereik voor het beleid voor het aantal dagen dat is gedefinieerd in de globale **instellingen van het activeringsvenster.**

## <a name="view-user-information-on-the-users-dashboard"></a>Gebruikersgegevens weergeven op het dashboard Gebruikers

Elke gebruiker die wordt weergegeven in het **dashboard Gebruikers** heeft de volgende informatie:

- **Gebruikers:** De gebruikersnaam voor een gebruiker. Dit veld wordt geanonimiseerd als de algemene anonimisatie-instelling voor insiderrisicobeheer is ingeschakeld.
- **Risiconiveau:** Het huidige berekende risiconiveau van de gebruiker. Deze score wordt elke 24 uur berekend en gebruikt de waarschuwingsrisicoscores van alle actieve waarschuwingen die aan de gebruiker zijn gekoppeld. Voor gebruikers met alleen triggering indicators is het risiconiveau nul.
- **Actieve waarschuwingen:** het aantal actieve waarschuwingen voor alle beleidsregels.
- **Bevestigd schendingen:** Het aantal gevallen dat is opgelost als *bevestigd beleidsovertreding* voor de gebruiker.
- **Case:** De huidige actieve case voor de gebruiker.

![Dashboard gebruikers van Insider-risicobeheer](../media/insider-risk-users-dashboard.png)

>[!NOTE]
>Het aantal gebruikers dat wordt weergegeven op het **dashboard** Gebruikers kan in sommige gevallen worden beperkt, afhankelijk van het aantal actieve waarschuwingen en overeenkomende beleidsregels. Gebruikers met actieve waarschuwingen worden weergegeven op het **dashboard** Gebruikers terwijl de waarschuwingen worden gegenereerd en er kunnen zeldzame gevallen zijn wanneer het maximum aantal weergegeven gebruikers wordt bereikt. Als deze limiet wordt bereikt, worden gebruikers met actieve waarschuwingen  die niet worden weergegeven, toegevoegd aan het gebruikersdashboard, omdat bestaande gebruikerswaarschuwingen drie keer worden weergegeven.

## <a name="view-user-details"></a>Gebruikersgegevens weergeven

Als u meer informatie wilt over risicoactiviteit voor een gebruiker, opent u het deelvenster gebruikersdetails door te dubbelklikken op een gebruiker in het **gebruikersdashboard.** In het detailvenster kunt u de volgende informatie bekijken:

- **Tabblad Gebruikersprofiel**
    - **Naam en titel:** De naam en positietitel voor de gebruiker van Azure Active Directory. Deze gebruikersvelden worden geanonimiseerd of leeg als de algemene anonimisatie-instelling voor insiderrisicobeheer is ingeschakeld.
    - **Gebruikers-e-mail:** Het e-mailadres voor de gebruiker.
    - **Alias:** De netwerkalias voor de gebruiker.
    - **Organisatie of afdeling**: De organisatie of afdeling voor de gebruiker.

- **Tabblad Gebruikersactiviteit**
    - **Geschiedenis van recente gebruikersactiviteit:** hiermee worden zowel triggerindicatoren als insiderrisico-indicatoren voor gebruikersactiviteiten tot de laatste 180 dagen vermeld. Alle activiteiten die relevant zijn voor insiderrisicoindicatoren, worden ook gescored, hoewel de activiteiten al dan niet een insiderrisicowaarschuwing hebben gegenereerd. Triggering indicator examples may be a aftreding date or the last scheduled date of work for the user. Insiderrisicoindicatoren zijn activiteiten die worden bepaald als een element van risico en worden gedefinieerd in beleidsregels waarin de gebruiker is opgenomen. Gebeurtenis- en risicoactiviteiten worden vermeld met het meest recente item dat als eerste wordt vermeld.

## <a name="remove-users-from-in-scope-assignment-to-policies"></a>Gebruikers verwijderen uit in-scopetoewijzing aan beleid

Er kunnen scenario's zijn waarin u moet stoppen met het toewijzen van risicoscores aan de activiteit van een gebruiker in beleidsregels voor insiderrisicobeheer. Gebruik **Gebruikers verwijderen op** de pagina **Gebruikersdashboard** om te stoppen met het toewijzen van risicoscores voor een of meer gebruikers van alle beleidsregels voor insiderrisicobeheer waar ze momenteel onder vallen. Met deze actie worden gebruikers niet verwijderd uit de algemene beleidstoewijzing (wanneer u gebruikers of groepen toevoegt aan een beleidsconfiguratie), maar worden de gebruikers gewoon verwijderd uit actieve verwerking door beleid na de huidige triggeringgebeurtenissen. Als de gebruikers in de toekomst nog een triggeringgebeurtenis hebben, worden risicoscores van beleid automatisch opnieuw aan de gebruikers toegewezen. Bestaande waarschuwingen of gevallen voor deze gebruiker worden niet verwijderd.

>[!NOTE]
>Het kan enkele minuten duren voordat u een gebruiker uit een beleid verwijdert. Wanneer deze is voltooid, wordt de gebruiker niet meer weergegeven op de pagina Gebruikers. Als de verwijderde gebruiker actieve waarschuwingen of gevallen heeft, blijft de gebruiker op de pagina Gebruikers staan en wordt in de details voor de gebruiker weergegeven dat deze niet langer binnen het bereik van een beleid valt.

Als u gebruikers handmatig wilt verwijderen uit de status binnen het bereik in alle beleidsregels voor insiderrisicobeheer, gaat u als volgt te werk:

1. Ga in [Microsoft 365 compliancecentrum](https://compliance.microsoft.com)naar **Insider-risicobeheer** en selecteer het **tabblad Gebruikers.**
2. Selecteer in **het dashboard Gebruikers** de gebruiker of gebruikers die u wilt verwijderen uit het beleid voor insiderrisicobeheer.
3. Selecteer **Gebruikers verwijderen.**
4. Selecteer verwijderen of Annuleren  in **het deelvenster** Gebruiker verwijderen **om** de wijzigingen te verwijderen en het dialoogvenster te sluiten.
5. Selecteer **Verwijderen** in het bevestigingsvenster om de gebruiker te verwijderen.

## <a name="run-automated-tasks-with-power-automate-flows-for-a-user"></a>Geautomatiseerde taken uitvoeren met Power Automate stromen voor een gebruiker

Met aanbevolen Power Automate kunnen risicoonderzoekers en analisten snel actie ondernemen om:

- Gebruikers op de hoogte stellen wanneer ze worden toegevoegd aan een insiderrisicobeleid

Voer, beheer of maak deze Power Automate voor een insider risicobeheergebruiker:

1. Selecteer **Automatiseren** op de werkbalk gebruikersactie.
2. Kies de Power Automate stroom die u wilt uitvoeren en selecteer **vervolgens Stroom uitvoeren.**
3. Nadat de stroom is voltooid, selecteert u **Gereed**.

Zie Aan de slag met instellingen voor insider-risicobeheer voor meer Power Automate voor [insiderrisicobeheer.](insider-risk-management-settings.md#power-automate-flows-preview)
