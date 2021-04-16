---
title: Een gebruiker uit uw organisatie verwijderen
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Meer informatie over het verwijderen van een gebruikersaccount. Bepaal wat u moet doen met de e-mail en OneDrive-inhoud van de gebruiker. En bepaal of u de productlicentie wilt behouden of niet meer wilt betalen.
ms.openlocfilehash: d40f70534499b08073278ffc2bed2b098ae1c4da
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860735"
---
# <a name="delete-a-user-from-your-organization"></a>Een gebruiker uit uw organisatie verwijderen
  
**Wilt u weten hoe u uw *eigen* Microsoft 365-gebruikersaccount verwijdert dat u op het werk of op school gebruikt? Neem contact op met de technische ondersteuning op uw werk of op de universiteit om deze stappen voor u uit te voeren.**

## <a name="what-you-need-to-know-about-deleting-users"></a>Wat u moet weten over het verwijderen van gebruikers

- Alleen personen met globale beheerders- of gebruikersbeheermachtigingen van [Microsoft 365](about-admin-roles.md) voor het bedrijf of school kunnen gebruikersaccounts verwijderen.
- U hebt 30 dagen de tijd om het account te [herstellen](restore-user.md). Daarna worden de gegevens van de gebruiker permanent verwijderd.
- Als u de OneDrive-gegevens van de gebruiker wilt behouden, verplaatst u ze naar een andere locatie. U kunt de gegevens zelfs tot 30 dagen na het verwijderen van het account verplaatsen. Zie [Toegang krijgen tot de gegevens van een voormalige gebruiker en er een back-up van maken](get-access-to-and-back-up-a-former-user-s-data.md). U hoeft de SharePoint-bestanden van de gebruiker niet te verplaatsen; u hebt daar nog steeds toegang toe.
- Als u de e-mail van de gebruiker wilt bewaren, moet u deze naar een andere locatie verplaatsen **VOORDAT** u het account verwijdert. Als u het account al hebt verwijderd, kunt u het binnen 30 dagen herstellen en vervolgens de e-mailgegevens verplaatsen. Hierna kunt u het account verwijderen. Zie [Toegang krijgen tot de gegevens van een voormalige gebruiker en er een back-up van maken](get-access-to-and-back-up-a-former-user-s-data.md).
- Als u een Enterprise-abonnement hebt, zoals Office 365 Enterprise E3, kunt u de postvakgegevens van een verwijderd gebruikersaccount behouden door het om te zetten in een *inactief postvak.* Zie het Engelstalige artikel [Manage inactive mailboxes in Exchange Online (Inactieve postvakken beheren in Exchange Online)](../../compliance/inactive-mailboxes-in-office-365.md) voor meer informatie.

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>Globale beheerder: Verwijder een gebruiker, stop de betaling voor zijn licentie en kies u wilt doen met zijn e-mailadres en de OneDrive-inhoud

Wanneer u een gebruiker verwijdert kunt u, als u een globale beheerder bent, ook een andere gebruiker toegang geven tot zijn e-mail, en kiezen wat u wilt doen met zijn OneDrive-inhoud.

### <a name="things-to-consider"></a>Aandachtspunten

Denk, voordat u begint, na over wat u wilt doen met de e-mail- en OneDrive-inhoud van de gebruiker en of u de licentie wilt behouden of hier niet meer voor wilt betalen.
  
|Item | Beschrijving |
|:-----|:-----|
|Productlicenties  <br/> |U kunt de licentie van de gebruiker verwijderen uit uw abonnementen zodat u niet langer betaalt voor deze licentie. Door deze optie te selecteren wordt de licentie automatisch verwijderd uit uw abonnementen.  <br/><br/> **U kunt de licentie niet verwijderen** als u deze hebt gekocht via een Partner of volumelicenties. Als u betaalt voor een jaarabonnement of als u bezig bent met een factureringscyclus, kunt u de licentie pas uit uw abonnement verwijderen als uw verbintenis is voltooid.  <br/> |
|OneDrive-inhoud  <br/> |Als de gebruiker de bestanden in OneDrive heeft opgeslagen, kunt u een andere gebruiker toegang geven tot deze bestanden.  <br/><br/> U moet de bestanden die u wilt behouden verplaatsen binnen de bewaarperiode die is ingesteld voor de OneDrive-bestanden. **Deze bewaarperiode is standaard 30 dagen.** Als u de bestanden niet binnen de bewaarperiode verplaatst na het verwijderen van de gebruiker, zal de OneDrive-inhoud permanent worden verwijderd. Als u het aantal dagen voor het bewaren van OneDrive-bestanden voor verwijderde accounts wilt verhogen, raadpleeg dan [Bewaren OneDrive instellen voor verwijderde gebruikers](/onedrive/set-retention).  <br/><br/> **Belangrijk!** Als de verwijderde gebruiker een pc gebruikte voor het downloaden van bestanden van SharePoint en OneDrive, dan is het niet mogelijk om de bestanden te wissen die deze persoon opgeslagen heeft op zijn computer. Zij zullen toegang blijven houden tot bestanden die werden gesynchroniseerd vanaf OneDrive.           |
|E-mail  <br/> | Als aan een andere gebruiker toegang wordt gegeven tot de e-mail van de verwijderde gebruiker, dan zal het postvak van de verwijderde gebruiker worden geconverteerd naar een gedeeld postvak. De nieuwe eigenaar van het postvak heeft vervolgens toegang tot het postvak en kan controleren op nieuwe e-mail. U beschikt tevens over de volgende opties:  <br/>  <br/>De weergavenaam wijzigen: u wordt aangeraden de weergavenaam te wijzigen, zodat het gedeelde postvak gemakkelijk kan worden gevonden in de lijst **Actieve** gebruikers.  <br/>  Automatische antwoorden inschakelen - Wij hebben alvast een beleefd automatisch antwoord voor u geschreven. U kunt verschillende automatische antwoorden verzenden naar personen binnen uw organisatie en personen van buiten uw organisatie.  <br/> <br/> Aliassen opschonen - Aliassen zijn extra e-mailadressen voor gebruikers. Sommige organisaties gebruiken ze niet, dus als u ze niet hebt, hoeft u hier verder niets te doen. Als de gebruiker wel aliassen heeft, wordt u aangeraden deze te verwijderen, zodat u deze e-mailadressen opnieuw kunt gebruiken. Anders kunt u deze e-mailadressen pas opnieuw gebruiken als de bewaarperiode voor verwijderde postvakken is verstreken. Een verwijderd postvak blijft standaard gedurende 30 dagen herstelbaar. Zie het Engelstalig artikel [Delete or restore user mailboxes in Exchange Online ](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox) voor meer informatie. <br/> |
|Active Directory  <br/> |Als uw bedrijf gebruikmaakt van **Active Directory** die wordt gesynchroniseerd met Azure AD, moet u het gebruikersaccount verwijderen uit Active Directory. Dit is niet mogelijk via Office 365. Lees voor instructies: [Een gebruikersaccount verwijderen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).  <br/> |

### <a name="get-started"></a>Aan de slag

Omdat de begeleide ervaring stap voor stap uitlegt hoe u de gebruiker verwijdert, gaat u als volgt aan de slag.

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.

::: moniker-end

2. Selecteer de gebruiker die u wilt verwijderen en selecteer **vervolgens Gebruiker verwijderen.**

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>Beheerder van gebruikersbeheer: Een of meer gebruikers verwijderen uit Office 365

> [!IMPORTANT]
> Verwijder het account van een gebruiker niet [](../email/convert-user-mailbox-to-shared-mailbox.md) als u het hebt geconverteerd naar een gedeeld postvak of als u het doorsturen van e-mail in het account hebt ingesteld. Deze functies hebben het account nog steeds nodig. Voor een gedeeld postvak is geen licentie vereist. Als u het account hebt geconverteerd naar een gedeeld postvak, kunt [u stoppen met betalen voor de licentie.](#stop-paying-for-the-license) Als u het doorsturen van e-mail in het account hebt ingesteld, kunt u de licentie niet verwijderen. Als u dit doet, wordt het doorsturen van e-mail gestopt en wordt het postvak gedeactiveerd.
  
::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.  

2. Selecteer de namen van de gebruikers die u wilt verwijderen, selecteer **Meer opties** (**...**) en kies vervolgens **Gebruiker verwijderen**.

   Hoewel u het account van de gebruiker hebt verwijderd, **betaalt u nog steeds voor de licentie**.  Zie de volgende procedure om de betaling voor de licentie stop te zetten.  U kunt de licentie ook toewijzen aan een andere gebruiker. Deze wordt niet automatisch aan iemand toegewezen.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.

2. Selecteer de namen van de gebruikers die u wilt verwijderen en kies **Gebruikers verwijderen** in het deelvenster **Bulkacties**.

   Hoewel u het account van de gebruiker hebt verwijderd, **betaalt u nog steeds voor de licentie**.  Zie de volgende procedure om de betaling voor de licentie stop te zetten.  U kunt de licentie ook toewijzen aan een andere gebruiker. Deze wordt niet automatisch aan iemand toegewezen.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.

2. Selecteer de namen van de gebruikers die u wilt verwijderen en kies **Gebruikers verwijderen** in het deelvenster **Bulkacties**.

   Hoewel u het account van de gebruiker hebt verwijderd, **betaalt u nog steeds voor de licentie**.  Zie de volgende procedure om de betaling voor de licentie stop te zetten.  U kunt de licentie ook toewijzen aan een andere gebruiker. Deze wordt niet automatisch aan iemand toegewezen.

::: moniker-end

### <a name="stop-paying-for-the-license"></a>Stoppen met betalen voor de licentie

Het aantal licenties beperken is een afzonderlijke stap die alleen kan worden uitgevoerd door de globale beheerder of de factureringsbeheerder.
  
::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>. Als u deze optie niet ziet, dan bent u geen globale beheerder of factureringsbeheerder en kunt u deze stap niet uitvoeren.

2. Selecteer op **het** tabblad Producten het abonnement waar u licenties voor wilt verwijderen.

3. Selecteer **Licenties verwijderen** op de pagina met abonnementdetails.

4. Voer in **het deelvenster** Licenties verwijderen onder  **Nieuw** aantal in het vak Totaal aantal licenties het totale aantal licenties in dat u voor dit abonnement wilt gebruiken. Als u bijvoorbeeld 100 licenties hebt en u er vijf wilt verwijderen, voert u 95 in.

5. Klik op **Opslaan**.

Wanneer u later de stappen doorloopt om een andere persoon aan uw bedrijf toe te voegen, wordt u gevraagd tegelijkertijd een licentie te kopen. Dat kan met één stap.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abonnementen</a>. Als u deze optie niet ziet, dan bent u geen globale beheerder of factureringsbeheerder en kunt u deze stap niet uitvoeren.

2. Selecteer het abonnement (als u er meer dan een hebt) en kies vervolgens **Licenties toevoegen/verwijderen** om de licentie te verwijderen, zodat u pas betaalt wanneer u een andere medewerker aanneemt.  

   Wanneer u later de stappen doorloopt om een andere persoon aan uw bedrijf toe te voegen, wordt u gevraagd tegelijkertijd een licentie te kopen. Dat kan met één stap.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abonnementen</a>. Als u deze optie niet ziet, dan bent u geen globale beheerder of factureringsbeheerder en kunt u deze stap niet uitvoeren.

2. Selecteer het abonnement (als u er meer dan een hebt) en kies vervolgens **Licenties toevoegen/verwijderen** om de licentie te verwijderen, zodat u pas betaalt wanneer u een andere medewerker aanneemt.  

   Wanneer u later de stappen doorloopt om een andere persoon aan uw bedrijf toe te voegen, wordt u gevraagd tegelijkertijd een licentie te kopen. Dat kan met één stap.

::: moniker-end

## <a name="delete-many-users-at-the-same-time"></a>Meerdere gebruikers tegelijk verwijderen

Zie de [Remove-MsolUser](https://docs.microsoft.com/powershell/module/msonline/remove-msoluser) PowerShell cmdlet.

## <a name="fix-issues-with-deleting-a-user"></a>Problemen met het verwijderen van een gebruiker oplossen

Hier volgt een overzicht van de meestvoorkomende problemen tijdens het verwijderen van een gebruiker:  
  
- **Er wordt een foutbericht weergegeven met de tekst 'Gebruiker kan niet worden verwijderd. Probeer het later opnieuw.'** Controleer of het account e-mail doorsturen heeft ingesteld of dat het is geconverteerd naar een gedeeld postvak. Beide problemen veroorzaken deze fout. Verwijder het account niet als het e-mail doorsturen heeft of als het is geconverteerd naar een gedeeld postvak.

- **U beschikt niet over de juiste machtigingen om een gebruiker te verwijderen**. Alleen personen die globale [beheerders van Microsoft 365](about-admin-roles.md) of beheerders van gebruikersbeheer zijn, kunnen gebruikers verwijderen. Meestal is dit de technische ondersteuning van uw onderwijsinstelling of bedrijf.

- **U verwijdert de gebruiker, maar zijn of haar naam staat nog steeds in het globale adresboek**. Dit gebeurt als een bedrijf gebruikmaakt van Active Directory. U moet het gebruikersaccount verwijderen uit Active Directory. Zie Een gebruikersaccount [verwijderen voor instructies.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))

**Wilt u Microsoft 365 van uw computer verwijderen? Ga naar [Uw abonnement opzeggen.](../../commerce/subscriptions/cancel-your-subscription.md)**

## <a name="related-articles"></a>Verwante artikelen

[Een gebruiker herstellen](restore-user.md)
  
[Een postvak definitief verwijderen](/exchange/permanently-delete-a-mailbox-exchange-2013-help)

[Een voormalige werknemer verwijderen uit Office 365](remove-former-employee.md)

[Een nieuwe werknemer toevoegen aan Office 365](add-new-employee.md)

[Een gebruikersaccount verwijderen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)): volg deze instructies als uw bedrijf gebruikmaakt van **Active Directory** die wordt gesynchroniseerd met Azure AD. Dat kan niet via Office 365.