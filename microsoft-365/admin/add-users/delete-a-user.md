---
title: Een gebruiker uit uw organisatie verwijderen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Meer informatie over gebruikersaccounts verwijderen. Bepaal wat u wilt doen met de e-mail van de gebruiker, de inhoud op OneDrive en of u de productlicentie wilt behouden of er niet meer voor wilt betalen.
ms.openlocfilehash: a179915ae92def2a967dc86378346bb905c923e4
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049457"
---
# <a name="delete-a-user-from-your-organization"></a>Een gebruiker uit uw organisatie verwijderen
  
||
|:-----|
|**Op zoek naar hoe u uw *eigen* Microsoft 365-gebruikersaccount verwijderen dat u op het werk of op school gebruikt? Neem contact op met de technische ondersteuning op uw werk of universiteit om deze stappen voor u uit te voeren.**|
   
## <a name="what-you-need-to-know-about-deleting-users"></a>Wat u moet weten over het verwijderen van gebruikers

- Alleen mensen met machtigingen voor algemene beheer- of gebruikersbeheer van [Microsoft 365](about-admin-roles.md) kunnen gebruikersaccounts verwijderen. 
    
- U hebt 30 dagen de tijd om het account te [herstellen](restore-user.md). Daarna worden de gegevens van de gebruiker permanent verwijderd. 
    
- Als u de OneDrive-gegevens van de gebruiker wilt behouden, verplaatst u ze naar een andere locatie. U kunt dit nog tot 30 dagen na het verwijderen van het account doen. Zie [Toegang krijgen tot de gegevens van een voormalige gebruiker en er een back-up van maken](get-access-to-and-back-up-a-former-user-s-data.md). U hoeft de SharePoint-bestanden van de gebruiker niet te verplaatsen; u hebt daar nog steeds toegang toe.
    
- Als u de e-mail van de gebruiker wilt bewaren, moet u deze naar een andere locatie verplaatsen **VOORDAT** u het account verwijdert. Als u het account al hebt verwijderd, kunt u het binnen 30 dagen herstellen en vervolgens de e-mailgegevens verplaatsen. Hierna kunt u het account verwijderen. Zie [Toegang krijgen tot de gegevens van een voormalige gebruiker en er een back-up van maken](get-access-to-and-back-up-a-former-user-s-data.md).
    
- Als u een Enterprise-abonnement hebt zoals Office 365 Enterprise E3, u de postvakgegevens van een verwijderd gebruikersaccount behouden door er een *inactief postvak van te*maken. Zie het Engelstalige artikel [Manage inactive mailboxes in Exchange Online (Inactieve postvakken beheren in Exchange Online)](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365) voor meer informatie.


## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>Globale beheerder: Verwijder een gebruiker, stop de betaling voor zijn licentie en kies u wilt doen met zijn e-mailadres en de OneDrive-inhoud

Wanneer u een gebruiker verwijdert kunt u, als u een globale beheerder bent, ook een andere gebruiker toegang geven tot zijn e-mail, en kiezen wat u wilt doen met zijn OneDrive-inhoud. 

  
### <a name="things-to-consider"></a>Aandachtspunten

Denk, voordat u begint, na over wat u wilt doen met de e-mail- en OneDrive-inhoud van de gebruiker en of u de licentie wilt behouden of hier niet meer voor wilt betalen.
  
|||
|:-----|:-----|
|Productlicenties  <br/> |U kunt de licentie van de gebruiker verwijderen uit uw abonnementen zodat u niet langer betaalt voor deze licentie. Door deze optie te selecteren wordt de licentie automatisch verwijderd uit uw abonnementen.  <br/><br/> **U kunt de licentie niet verwijderen** als u deze hebt gekocht via een Partner of volumelicenties. Als u voor een jaarabonnement betaalt of als u in het midden van een factureringscyclus zit, kunt u de licentie niet verwijderen uit uw abonnement totdat uw verbintenis is voltooid.  <br/> |
|OneDrive-inhoud  <br/> |Als de gebruiker de bestanden in OneDrive heeft opgeslagen, kunt u een andere gebruiker toegang geven tot deze bestanden.  <br/><br/> U moet de bestanden die u wilt behouden verplaatsen binnen de bewaarperiode die is ingesteld voor de OneDrive-bestanden. **Deze bewaarperiode is standaard 30 dagen.** Als u de bestanden niet binnen de bewaarperiode verplaatst na het verwijderen van de gebruiker, zal de OneDrive-inhoud permanent worden verwijderd. Als u het aantal dagen voor het bewaren van OneDrive-bestanden voor verwijderde accounts wilt verhogen, raadpleeg dan [Bewaren OneDrive instellen voor verwijderde gebruikers](https://docs.microsoft.com/onedrive/set-retention).  <br/><br/> **Belangrijk!** Als de verwijderde gebruiker een pc gebruikte voor het downloaden van bestanden van SharePoint en OneDrive, dan is het niet mogelijk om de bestanden te wissen die deze persoon opgeslagen heeft op zijn computer. Zij zullen toegang blijven houden tot bestanden die werden gesynchroniseerd vanaf OneDrive.           |
|E-mail  <br/> | Als aan een andere gebruiker toegang wordt gegeven tot de e-mail van de verwijderde gebruiker, dan zal het postvak van de verwijderde gebruiker worden geconverteerd naar een gedeeld postvak. De nieuwe eigenaar van het postvak heeft vervolgens toegang tot het postvak en kan controleren op nieuwe e-mail. U beschikt tevens over de volgende opties:  <br/>  <br/>De weergavenaam wijzigen - Het is raadzaam de weergavenaam te wijzigen zodat het gedeelde postvak in de lijst met Actieve gebruikers gemakkelijk te herkennen is.  <br/>  Automatische antwoorden inschakelen - Wij hebben alvast een beleefd automatisch antwoord voor u geschreven. U kunt verschillende automatische antwoorden verzenden naar personen van binnen uw organisatie en personen van buiten uw organisatie.  <br/> <br/> Aliassen opschonen - Aliassen zijn extra e-mailadressen voor gebruikers. Sommige organisaties gebruiken ze niet, dus als u ze niet hebt, hoeft u hier verder niets te doen. Als de gebruiker aliassen heeft is het raadzaam deze te verwijderen zodat u deze e-mailadressen opnieuw kunt gebruiken. Anders u deze e-mailadressen pas opnieuw gebruiken als de bewaartermijn voor verwijderde postvakken is verstreken. Een verwijderd postvak blijft standaard gedurende 30 dagen herstelbaar. Zie het Engelstalig artikel [Delete or restore user mailboxes in Exchange Online ](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox) voor meer informatie. <br/> |
|Active Directory  <br/> |Als uw bedrijf gebruikmaakt van **Active Directory** die wordt gesynchroniseerd met Azure AD, moet u het gebruikersaccount verwijderen uit Active Directory. Dit is niet mogelijk via Office 365. Lees voor instructies: [Een gebruikersaccount verwijderen](https://go.microsoft.com/fwlink/p/?linkid=841808).  <br/> |
   
### <a name="get-started"></a>Aan de slag

::: moniker range="o365-worldwide"

> [!NOTE]
> Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.

::: moniker-end

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

2. Selecteer de gebruiker die u wilt verwijderen en selecteer vervolgens **Gebruiker verwijderen**.

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>Beheerder van gebruikersbeheer: Een of meer gebruikers verwijderen uit Office 365


> [!IMPORTANT]
> Verwijder het account van een gebruiker niet als je het hebt [geconverteerd naar een gedeeld postvak](../email/convert-user-mailbox-to-shared-mailbox.md) of als je e-mail doorsturen in het account hebt ingesteld. Die functies hebben nog steeds het account nodig. Voor een gedeeld postvak is geen licentie vereist. Als u het account hebt geconverteerd naar een gedeeld postvak, u [stoppen met betalen voor de licentie.](#stop-paying-for-the-license) Als u e-mail doorsturen voor het account hebt ingesteld, u de licentie niet verwijderen. Als u dit doet, wordt het doorsturen van e-mail gestopt en wordt het postvak gedeactiveerd.
  
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

1. Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten.</a> Als u deze optie niet ziet, dan bent u geen globale beheerder of factureringsbeheerder en kunt u deze stap niet uitvoeren.

2. Selecteer het abonnement (als u er meer dan een hebt) en kies vervolgens **Licenties toevoegen/verwijderen** om de licentie te verwijderen, zodat u pas betaalt wanneer u een andere medewerker aanneemt.  

   Wanneer u later de stappen doorloopt om een andere persoon aan uw bedrijf toe te voegen, wordt u gevraagd tegelijkertijd een licentie te kopen. Dat kan met één stap.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Facturering**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abonnementen</a>. Als u deze optie niet ziet, dan bent u geen globale beheerder of factureringsbeheerder en kunt u deze stap niet uitvoeren.

2. Selecteer het abonnement (als u er meer dan een hebt) en kies vervolgens **Licenties toevoegen/verwijderen** om de licentie te verwijderen, zodat u pas betaalt wanneer u een andere medewerker aanneemt.  

   Wanneer u later de stappen doorloopt om een andere persoon aan uw bedrijf toe te voegen, wordt u gevraagd tegelijkertijd een licentie te kopen. Dat kan met één stap.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Facturering**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abonnementen</a>. Als u deze optie niet ziet, dan bent u geen globale beheerder of factureringsbeheerder en kunt u deze stap niet uitvoeren.

2. Selecteer het abonnement (als u er meer dan een hebt) en kies vervolgens **Licenties toevoegen/verwijderen** om de licentie te verwijderen, zodat u pas betaalt wanneer u een andere medewerker aanneemt.  

   Wanneer u later de stappen doorloopt om een andere persoon aan uw bedrijf toe te voegen, wordt u gevraagd tegelijkertijd een licentie te kopen. Dat kan met één stap.

::: moniker-end 

## <a name="delete-many-users-at-the-same-time"></a>Meerdere gebruikers tegelijk verwijderen

Zie de [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell cmdlet.

## <a name="fix-issues-with-deleting-a-user"></a>Problemen met het verwijderen van een gebruiker oplossen

Hier volgt een overzicht van de meestvoorkomende problemen tijdens het verwijderen van een gebruiker:  
  
- **U krijgt een foutbericht met de volgende strekking: 'Gebruiker kan niet worden verwijderd. Probeer het later opnieuw.'** Controleer of E-mail doorsturen is ingesteld voor het account of dat het account is omgezet naar een gedeeld postvak. In beide gevallen treedt deze fout op. Verwijder het account niet als e-mail doorsturen is ingesteld of als het account is omgezet naar een gedeeld postvak.

- **U beschikt niet over de juiste machtigingen om een gebruiker te verwijderen**. Alleen mensen die [algemene beheerders van Microsoft 365 of beheerders van gebruikersbeheer](about-admin-roles.md) zijn, kunnen gebruikers verwijderen. Meestal is dit de technische ondersteuning van uw onderwijsinstelling of bedrijf.

- **U verwijdert de gebruiker, maar zijn of haar naam staat nog steeds in het globale adresboek**. Dit gebeurt als een bedrijf gebruikmaakt van Active Directory. U moet het gebruikersaccount uit Active Directory verwijderen. Zie het volgende TechNet-artikel voor instructies: [Gebruikersaccounts verwijderen.](https://go.microsoft.com/fwlink/p/?linkid=841808)

||
|:-----|
|**Wilt u Microsoft 365 van uw computer verwijderen? Ga naar [Uw abonnement opzeggen](../../commerce/subscriptions/cancel-your-subscription.md).**|
   
## <a name="related-articles"></a>Verwante artikelen

[Een gebruiker herstellen](restore-user.md)
  
[Een postvak definitief verwijderen](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[Een voormalige werknemer verwijderen uit Office 365](remove-former-employee.md)

[Een nieuwe werknemer toevoegen aan Office 365](add-new-employee.md)

[Een gebruikersaccount verwijderen](https://go.microsoft.com/fwlink/p/?linkid=841808): volg deze instructies als uw bedrijf gebruikmaakt van **Active Directory** die wordt gesynchroniseerd met Azure AD. Dat kan niet via Office 365.