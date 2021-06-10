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
description: 'Lees hoe u meerdere e-mailadressen, een e-mailalias, kunt toevoegen aan uw Microsoft 365 voor zakelijke account. '
ms.openlocfilehash: ec5bc69a42c5183413f11649b7d7ec6baaf40b01
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572103"
---
# <a name="add-another-email-alias-for-a-user"></a>Een ander e-mailalias toevoegen voor een gebruiker
  
Dit artikel is bedoeld Microsoft 365 beheerders die een zakelijk abonnement hebben. Het is niet bedoeld voor thuisgebruikers.
  
Een primair e-mailadres in Microsoft 365 is meestal het e-mailadres dat aan een gebruiker is toegewezen toen zijn account werd gemaakt. Wanneer de gebruiker een e-mail naar iemand anders verzendt, wordt zijn primaire e-mailadres meestal weergegeven in het veld  *Van*  in e-mailapps. Ze kunnen ook meer dan één e-mailadres hebben dat is gekoppeld aan Microsoft 365 account voor bedrijven. Deze extra adressen worden aliassen genoemd. 
  
Stel dat Jenna het e-mailadres jenna@contosoco.com, maar ze wil ook e-mail ontvangen bij jen@contosoco.com omdat sommige mensen naar haar verwijzen met die naam. U kunt aliassen voor haar maken, zodat beide e-mailadressen naar het Postvak IN van Jenna gaan.
  
U kunt maximaal 400 aliassen maken voor een gebruiker. Er worden geen extra kosten in rekening gebracht en u hoeft geen extra licenties te kopen.
  
> [!Tip]
> Als u wilt dat meerdere personen e-mail beheren die naar één e-mailadres wordt verzonden, zoals info@NodPublishers.com of sales@NodPublishers.com, maakt u een gedeeld postvak. Zie Een gedeeld [postvak maken voor meer informatie.](create-a-shared-mailbox.md)
  
## <a name="add-email-aliases-to-a-user"></a>E-mailaliassen toevoegen aan een gebruiker

Hiervoor moet [u beheerdersmachtigingen](../add-users/about-admin-roles.md) hebben. 

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
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>Hebt u 'A parameter cannot be found that matches parameter name EmailAddresses' gekregen?

Als u het foutbericht ' Er kan geen parameter worden gevonden die overeenkomt met **de parameternaam EmailAddresses'** wordt weergegeven, betekent dit dat het wat langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>Hebt u uw abonnement aangeschaft bij GoDaddy of een andere partner?


Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.

## <a name="sending-email-from-the-proxy-address-easily"></a>Eenvoudig e-mail verzenden vanaf het proxyadres

In april 2021 wordt een nieuwe functie uitgerold waarmee gebruikers eenvoudig vanuit hun aliassen kunnen verzenden wanneer ze Outlook op internet. Wanneer de functie wordt uitrolt naar een tenancy waarbij de tenantbeheerder de cmdlet gebruikt, krijgen gebruikers binnen de huurperiode toegang tot een lijst met selectievakjes waarin elke vermelding overeenkomt met een alias in de Outlook `Set-OrganizationConfig -SendFromAliasEnabled $true` instellingen. Als u een alias selecteert, wordt deze weergegeven in de vervolgkeuzekeuze in het formulier Opstellen.
  
## <a name="related-content"></a>Verwante onderwerpen

[E-mail verzenden vanaf een ander adres](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (artikel)

[Een gebruikersnaam en e-mailadres wijzigen](../add-users/change-a-user-name-and-email-address.md) (artikel)

[Doorsturen van e‑mail configureren in Microsoft 365](configure-email-forwarding.md) (artikel)
