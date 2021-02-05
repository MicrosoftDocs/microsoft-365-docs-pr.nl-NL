---
title: Een ander e-mailalias toevoegen voor een gebruiker
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
ms.custom:
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Lees hoe u meer dan één e-mailadres, de zogenaamde e-mailalias, kunt hebben dat is gekoppeld aan uw Microsoft 365 voor Bedrijven-account. '
ms.openlocfilehash: afb576a0499577b910fe3ed14eff75ae0a52b394
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114031"
---
# <a name="add-another-email-alias-for-a-user"></a>Een ander e-mailalias toevoegen voor een gebruiker

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end
  
Dit artikel is bedoeld voor Microsoft 365-beheerders die een zakelijk abonnement hebben. Het is niet bedoeld voor thuisgebruikers.
  
Een primair e-mailadres in Microsoft 365 is meestal het e-mailadres dat aan een gebruiker is toegewezen toen het account werd gemaakt. Wanneer de gebruiker een e-mail naar iemand anders verzendt, wordt zijn primaire e-mailadres meestal weergegeven in het veld  *Van*  in e-mailapps. Ze kunnen ook meerdere e-mailadressen hebben die zijn gekoppeld aan hun Microsoft 365 voor Bedrijven-account. Deze extra adressen worden aliassen genoemd. 
  
Stel dat Mensje het e-mailadres jenna@contosoco.com heeft, maar ze wil ook e-mail ontvangen bij jen@contosoco.com omdat sommige mensen naar haar verwijzen met die naam. U kunt aliassen voor haar maken, zodat beide e-mailadressen in het Postvak IN van E-mail komen.
<br><br>  
  
U kunt maximaal 400 aliassen maken voor een gebruiker. Er worden geen extra kosten in rekening gebracht en u hoeft geen extra licenties te kopen.
  
> [!Tip]
> Als u wilt dat meerdere personen e-mail beheren die wordt verzonden naar één e-mailadres, zoals info@NodPublishers.com of sales@NodPublishers.com, maakt u een gedeeld postvak. Zie Een gedeeld postvak [maken voor meer informatie.](create-a-shared-mailbox.md)
  
## <a name="add-email-aliases-to-a-user"></a>E-mailaliassen toevoegen aan een gebruiker
<a name="AddEmailPreview"> </a>

U moet [beheerdersmachtigingen hebben](../add-users/about-admin-roles.md) om dit te kunnen doen. 

  
::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

2. Selecteer op **de pagina Actieve** gebruikers de gebruiker > **e-mailaliassen beheren.** U ziet deze optie niet als er geen licentie aan de persoon is toegewezen. 
    
3. Selecteer **+ Een alias toevoegen** en voer een nieuwe alias voor de gebruiker in.   
    
    > [!Important] 
    > Als het foutbericht 'Een parameter die overeenkomt met **de parameternaam 'EmailAddresses'** kan niet worden gevonden, wordt weergegeven, betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.
    
  
    > [!IMPORTANT]
    > Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen. 
  
    > [!TIP]
    > De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst. Zie Een domein toevoegen aan [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)als u een andere domeinnaam aan de lijst wilt toevoegen. 
  
     
5. Wanneer u klaar bent, kiest u **Wijzigingen opslaan.**
    
6. Wacht 24 uur totdat de nieuwe aliassen zijn ingevuld in Microsoft 365.
    
    De gebruiker krijgt nu een primair adres en een alias. Zo gaat alle e-mail die wordt verzonden naar het primaire adres van Eliza Eliza@NodPublishers.com, Eliza@NodPublishers.com en haar alias, Sales@NodPublishers.com, naar het Postvak IN van Eliza.
    
  
7. **Wanneer de gebruiker antwoordt, wordt het *Van-adres*  haar primaire e-mailalias.** Stel, er wordt een bericht naar het Sales@NodPublishers.com verzonden en het bericht komt binnen in het Postvak IN van Eliza. Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com. 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>. 
    
    
2. Selecteer op de pagina **Actieve gebruikers** de gebruikersnaam die u wilt bewerken.

3. Selecteer Bewerken **naast Gebruikersnaam/E-mailaliassen.** 

    > [!Important] 
    > Als het foutbericht 'Een parameter die overeenkomt met **de parameternaam 'EmailAddresses'** kan niet worden gevonden, wordt weergegeven, betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.

4. Typ in het tekstvak onder **Alias** het eerste deel van de nieuwe e-mailalias. Als u uw eigen domein hebt toegevoegd aan Microsoft 365, kunt u het domein voor de nieuwe e-mailalias kiezen in de vervolgkeuzelijst. Selecteer vervolgens **Toevoegen.**

    > [!IMPORTANT]
    > Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen. 
  
    > [!TIP]
    > De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst. Zie Een domein toevoegen aan [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)als u een andere domeinnaam aan de lijst wilt toevoegen. 

5. Selecteer Opslaan wanneer u **klaar bent.**

6. Wacht 24 uur totdat de nieuwe aliassen zijn ingevuld in Microsoft 365. 
    
    De gebruiker krijgt nu een primair adres en een alias. Zo gaat alle e-mail die wordt verzonden naar het primaire adres van Eliza Eliza@NodPublishers.com, Eliza@NodPublishers.com en haar alias, Sales@NodPublishers.com, naar het Postvak IN van Eliza.
    
  
7. **Wanneer de gebruiker antwoordt, wordt het *Van-adres*  haar primaire e-mailalias.** Stel, er wordt een bericht naar het Sales@NodPublishers.com verzonden en het bericht komt binnen in het Postvak IN van Eliza. Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>. 

    
2. Selecteer op de pagina **Actieve gebruikers** de gebruikersnaam die u wilt bewerken.

3. Selecteer Bewerken **naast Gebruikersnaam/E-mailaliassen.** 

    > [!Important] 
    > Als het foutbericht 'Een parameter die overeenkomt met **de parameternaam 'EmailAddresses'** kan niet worden gevonden, wordt weergegeven, betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.

4. Typ in het tekstvak onder **Alias** het eerste deel van de nieuwe e-mailalias. Als u uw eigen domein hebt toegevoegd aan Microsoft 365, kunt u het domein voor de nieuwe e-mailalias kiezen in de vervolgkeuzelijst. Selecteer vervolgens **Toevoegen.**

    > [!IMPORTANT]
    > Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen. 
  
    > [!TIP]
    > De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst. Zie Een domein toevoegen aan [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)als u een andere domeinnaam aan de lijst wilt toevoegen. 

5. Selecteer Opslaan wanneer u **klaar bent.**

6. Wacht 24 uur totdat de nieuwe aliassen zijn ingevuld in Microsoft 365. 
    
    De gebruiker krijgt nu een primair adres en een alias. Zo gaat alle e-mail die wordt verzonden naar het primaire adres van Eliza Eliza@NodPublishers.com, Eliza@NodPublishers.com en haar alias, Sales@NodPublishers.com, naar het Postvak IN van Eliza.
    
  
7. **Wanneer de gebruiker antwoordt, wordt het *Van-adres*  haar primaire e-mailalias.** Stel, er wordt een bericht naar het Sales@NodPublishers.com verzonden en het bericht komt binnen in het Postvak IN van Eliza. Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com. 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>Wordt het bericht 'Een parameter die overeenkomt met de parameternaam EmailAddresses kan niet worden gevonden' krijgt?


Als het foutbericht 'Er kan geen parameter worden gevonden die overeenkomt met **de parameternaam EmailAddresses'** wordt weergegeven, betekent dit dat het wat langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>Hebt u uw abonnement aangeschaft bij GoDaddy of een andere partner?


Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.
  
## <a name="related-articles"></a>Verwante artikelen

[E-mail verzenden via een ander adres](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[Een gebruikersnaam en e-mailadres wijzigen](../add-users/change-a-user-name-and-email-address.md)
  

