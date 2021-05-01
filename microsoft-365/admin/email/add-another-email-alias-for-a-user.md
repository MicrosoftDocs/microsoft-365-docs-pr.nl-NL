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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Lees hoe u meerdere e-mailadressen, e-mailalias genoemd, kunt toevoegen aan uw Microsoft 365 voor bedrijven-account. '
ms.openlocfilehash: 00e1c55edfcfa9937ab6a18b4bf268adb858b775
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107120"
---
# <a name="add-another-email-alias-for-a-user"></a>Een ander e-mailalias toevoegen voor een gebruiker
  
Dit artikel is bedoeld Microsoft 365 beheerders die een zakelijk abonnement hebben. Het is niet bedoeld voor thuisgebruikers.
  
Een primair e-mailadres in Microsoft 365 is meestal het e-mailadres dat aan een gebruiker is toegewezen toen zijn account werd gemaakt. Wanneer de gebruiker een e-mail naar iemand anders verzendt, wordt zijn primaire e-mailadres meestal weergegeven in het veld  *Van*  in e-mailapps. Ze kunnen ook meer dan één e-mailadres hebben dat is gekoppeld aan Microsoft 365 account voor bedrijven. Deze extra adressen worden aliassen genoemd. 
  
Stel dat Jenna het e-mailadres jenna@contosoco.com, maar ze wil ook e-mail ontvangen bij jen@contosoco.com omdat sommige mensen naar haar verwijzen met die naam. U kunt aliassen voor haar maken, zodat beide e-mailadressen naar het Postvak IN van Jenna gaan.
<br><br>  
  
U kunt maximaal 400 aliassen maken voor een gebruiker. Er worden geen extra kosten in rekening gebracht en u hoeft geen extra licenties te kopen.
  
> [!Tip]
> Als u wilt dat meerdere personen e-mail beheren die naar één e-mailadres wordt verzonden, zoals info@NodPublishers.com of sales@NodPublishers.com, maakt u een gedeeld postvak. Zie Een gedeeld [postvak maken voor meer informatie.](create-a-shared-mailbox.md)
  
## <a name="add-email-aliases-to-a-user"></a>E-mailaliassen toevoegen aan een gebruiker
<a name="AddEmailPreview"> </a>

Hiervoor moet [u beheerdersmachtigingen](../add-users/about-admin-roles.md) hebben. 

  
::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

2. Selecteer op **de pagina** Actieve gebruikers de gebruiker > Gebruikersnaam en e-mail **beheren.** U ziet deze optie niet als de persoon geen licentie aan hem of haar heeft toegewezen. 
    
3. Selecteer **+ Een alias toevoegen** en voer een nieuwe alias voor de gebruiker in.   
    
    > [!Important] 
    > Als u het foutbericht 'Er kan geen parameter worden gevonden die overeenkomt met **de parameternaam 'EmailAddresses',** betekent dit dat het wat langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.
    
  
    > [!IMPORTANT]
    > Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen. 
  
    > [!TIP]
    > De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst. Zie Een domein toevoegen aan [Microsoft 365.](../setup/add-domain.md) 
  
     
5. Wanneer u klaar bent, kiest u **Wijzigingen opslaan.**
    
6. Wacht 24 uur totdat de nieuwe aliassen in de hele Microsoft 365.
    
    De gebruiker heeft nu een primair adres en een alias. Alle e-mail die naar het primaire adres van Eliza Hoffman wordt verzonden, Eliza@NodPublishers.com en haar alias, Sales@NodPublishers.com, gaat bijvoorbeeld naar het Postvak IN van Eliza.
    
  
7. **Wanneer de gebruiker antwoordt, is *het Van-adres* afhankelijk van Outlook client. Outlook op internet gebruikt u de alias waarmee de e-mail is ontvangen (we noemen dit het ping-pong-principe). Outlook bureaublad gebruikt haar primaire e-mailalias.** Stel dat een bericht wordt verzonden naar Sales@NodPublishers.com en het bericht in het Postvak IN van Eliza wordt weergegeven. Wanneer Eliza het bericht beantwoordt met Outlook bureaublad, wordt haar primaire e-mailadres weergegeven als Eliza@NodPublishers.com, niet als Sales@NodPublishers.com.
    
::: moniker-end

::: moniker range="o365-germany"
    
1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>. 
    
    
2. Selecteer op de pagina **Actieve gebruikers** de gebruikersnaam die u wilt bewerken.

3. Selecteer naast **Gebruikersnaam /E-mailalias** de optie **Bewerken.**

    > [!Important] 
    > Als u het foutbericht 'Er kan geen parameter worden gevonden die overeenkomt met **de parameternaam 'EmailAddresses',** betekent dit dat het wat langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.

4. Typ in het tekstvak onder **Alias** het eerste deel van de nieuwe e-mailalias. Als u uw eigen domein hebt toegevoegd aan Microsoft 365, kunt u het domein voor de nieuwe e-mailalias kiezen in de vervolgkeuzelijst. Selecteer vervolgens **Toevoegen.**

    > [!IMPORTANT]
    > Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen. 
  
    > [!TIP]
    > De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst. Zie Een domein toevoegen aan [Microsoft 365.](../setup/add-domain.md) 

5. Wanneer u klaar bent, selecteert u **Opslaan.**

6. Wacht 24 uur totdat de nieuwe aliassen in de hele Microsoft 365. 
    
    De gebruiker heeft nu een primair adres en een alias. Alle e-mail die naar het primaire adres van Eliza Hoffman wordt verzonden, Eliza@NodPublishers.com en haar alias, Sales@NodPublishers.com, gaat bijvoorbeeld naar het Postvak IN van Eliza.
    
  
7. **Wanneer de gebruiker antwoordt, is *het Van-adres* afhankelijk van Outlook client. Outlook op internet gebruikt u de alias waarmee de e-mail is ontvangen (we noemen dit het ping-pong-principe). Outlook bureaublad gebruikt haar primaire e-mailalias.** Stel dat een bericht wordt verzonden naar Sales@NodPublishers.com en het bericht in het Postvak IN van Eliza wordt weergegeven. Wanneer Eliza het bericht beantwoordt met Outlook bureaublad, wordt haar primaire e-mailadres weergegeven als Eliza@NodPublishers.com, niet als Sales@NodPublishers.com.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>. 

    
2. Selecteer op de pagina **Actieve gebruikers** de gebruikersnaam die u wilt bewerken.

3. Selecteer naast **Gebruikersnaam /E-mailalias** de optie **Bewerken.**

    > [!Important] 
    > Als u het foutbericht 'Er kan geen parameter worden gevonden die overeenkomt met **de parameternaam 'EmailAddresses',** betekent dit dat het wat langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.

4. Typ in het tekstvak onder **Alias** het eerste deel van de nieuwe e-mailalias. Als u uw eigen domein hebt toegevoegd aan Microsoft 365, kunt u het domein voor de nieuwe e-mailalias kiezen in de vervolgkeuzelijst. Selecteer vervolgens **Toevoegen.**

    > [!IMPORTANT]
    > Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen. 
  
    > [!TIP]
    > De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst. Zie Een domein toevoegen aan [Microsoft 365.](../setup/add-domain.md) 

5. Wanneer u klaar bent, selecteert u **Opslaan.**

6. Wacht 24 uur totdat de nieuwe aliassen in de hele Microsoft 365. 
    
    De gebruiker heeft nu een primair adres en een alias. Alle e-mail die naar het primaire adres van Eliza Hoffman wordt verzonden, Eliza@NodPublishers.com en haar alias, Sales@NodPublishers.com, gaat bijvoorbeeld naar het Postvak IN van Eliza.
    
  
7. **Wanneer de gebruiker antwoordt, is *het Van-adres* afhankelijk van Outlook client. Outlook op internet gebruikt u de alias waarmee de e-mail is ontvangen (we noemen dit het ping-pong-principe). Outlook bureaublad gebruikt haar primaire e-mailalias.** Stel dat een bericht wordt verzonden naar Sales@NodPublishers.com en het bericht in het Postvak IN van Eliza wordt weergegeven. Wanneer Eliza het bericht beantwoordt met Outlook bureaublad, wordt haar primaire e-mailadres weergegeven als Eliza@NodPublishers.com, niet als Sales@NodPublishers.com.

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>Hebt u 'A parameter cannot be found that matches parameter name EmailAddresses' gekregen?


Als u het foutbericht ' Er kan geen parameter worden gevonden die overeenkomt met **de parameternaam EmailAddresses'** wordt weergegeven, betekent dit dat het wat langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>Hebt u uw abonnement aangeschaft bij GoDaddy of een andere partner?


Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.

## <a name="sending-email-from-the-proxy-address-easily"></a>Eenvoudig e-mail verzenden vanaf het proxyadres

In april 2021 wordt een nieuwe functie uitgerold waarmee gebruikers eenvoudig vanuit hun aliassen kunnen verzenden wanneer ze Outlook op internet. Wanneer de functie wordt uitrolt naar een tenancy waarbij de tenantbeheerder de cmdlet gebruikt, krijgen gebruikers binnen de huurperiode toegang tot een lijst met selectievakjes waarin elke vermelding overeenkomt met een alias in de Outlook `Set-OrganizationConfig -SendFromAliasEnabled $true` instellingen. Als u een alias selecteert, wordt deze weergegeven in de vervolgkeuzekeuze in het formulier Opstellen.
  
## <a name="related-articles"></a>Verwante artikelen

[E-mail verzenden via een ander adres](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[Een gebruikersnaam en e-mailadres wijzigen](../add-users/change-a-user-name-and-email-address.md)
