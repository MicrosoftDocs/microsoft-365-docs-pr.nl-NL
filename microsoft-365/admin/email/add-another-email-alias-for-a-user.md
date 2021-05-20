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
description: 'Meer informatie over hoe u meer dan één e-mailadres, een e-mailalias genaamd, kunt hebben dat is gekoppeld aan uw Microsoft 365 voor bedrijven-account. '
ms.openlocfilehash: ec5bc69a42c5183413f11649b7d7ec6baaf40b01
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572103"
---
# <a name="add-another-email-alias-for-a-user"></a>Een ander e-mailalias toevoegen voor een gebruiker
  
Dit artikel is voor Microsoft 365 beheerders met zakelijke abonnementen. Het is niet bedoeld voor thuisgebruikers.
  
Een primair e-mailadres in Microsoft 365 is meestal het e-mailadres dat een gebruiker is toegewezen toen zijn of haar account werd gemaakt. Wanneer de gebruiker een e-mail naar iemand anders verzendt, wordt zijn primaire e-mailadres meestal weergegeven in het veld  *Van*  in e-mailapps. Ze kunnen ook meer dan één e-mailadres hebben dat is gekoppeld aan hun Microsoft 365 voor zakelijke account. Deze extra adressen worden aliassen genoemd. 
  
Stel dat Jenna het e-mailadres jenna@contosoco.com heeft, maar ze wil ook e-mail ontvangen op jen@contosoco.com omdat sommige mensen naar haar verwijzen met die naam. Je kunt aliassen voor haar maken, zodat beide e-mailadressen naar Jenna's inbox gaan.
  
U kunt maximaal 400 aliassen maken voor een gebruiker. Er worden geen extra kosten in rekening gebracht en u hoeft geen extra licenties te kopen.
  
> [!Tip]
> Als u wilt dat meerdere mensen e-mail beheren die naar één e-mailadres is verzonden, zoals info@NodPublishers.com of sales@NodPublishers.com, maakt u een gedeeld postvak. Zie Een [gedeeld postvak maken](create-a-shared-mailbox.md)voor meer informatie.
  
## <a name="add-email-aliases-to-a-user"></a>E-mailaliassen toevoegen aan een gebruiker

U moet [beheerdersmachtigingen](../add-users/about-admin-roles.md) hebben om dit te doen. 

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

2. Selecteer op de pagina **Actieve gebruikers** de gebruiker > Gebruikersnaam **en e-mail beheren**. U ziet deze optie niet als de persoon geen licentie heeft toegewezen. 
    
3. Selecteer **+ Voeg een alias toe** en voer een nieuwe alias voor de gebruiker in.   
    
    > [!Important] 
    > Als u het foutbericht '**Er kan geen parameter worden gevonden die overeenkomt met de parameternaam 'EmailAddresses'** krijgt, betekent dit dat het iets langer duurt om het instellen van uw Tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.
    
  
    > [!IMPORTANT]
    > Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen. 
  
    > [!TIP]
    > De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst. Zie Een domein toevoegen aan Microsoft 365 als u een andere domeinnaam aan de lijst [wilt toevoegen.](../setup/add-domain.md) 
  
     
5. Als u klaar bent, kiest u **Wijzigingen opslaan**.
    
6. Wacht 24 uur tot de nieuwe aliassen in Microsoft 365 worden ingevuld.
    
    De gebruiker heeft nu een primair adres en een alias. Alle e-mail die naar het primaire adres van Eliza Hoffman wordt verzonden, Eliza@NodPublishers.com, en haar alias, Sales@NodPublishers.com, gaan bijvoorbeeld naar Eliza's Inbox.
    
  
7. **Wanneer de gebruiker antwoordt, is het *van-adres* afhankelijk van haar Outlook client. Outlook op het web gebruiken de alias waarbij de e-mail is ontvangen (we noemen dit het pingpongprincipe). Outlook bureaublad gebruikt haar primaire e-mailalias.** Stel dat er een bericht naar Sales@NodPublishers.com wordt gestuurd en dat het in eliza's inbox terechtkomt. Wanneer Eliza het bericht beantwoordt met Outlook bureaublad, wordt haar primaire e-mailadres weergegeven als Eliza@NodPublishers.com, niet Sales@NodPublishers.com.
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>Hebt u 'Er kan geen parameter worden gevonden die overeenkomt met parameternaam EmailAddresses'?

Als u het foutbericht '**Er kan geen parameter worden gevonden die overeenkomt met parameternaam EmailAddresses**' wordt weergegeven, betekent dit dat het iets langer duurt om uw Tenant of uw aangepaste domein in te stellen als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>Hebt u uw abonnement aangeschaft bij GoDaddy of een andere partner?


Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.

## <a name="sending-email-from-the-proxy-address-easily"></a>Eenvoudig e-mail verzenden vanaf het proxyadres

In april 2021 wordt een nieuwe functie uitgerold waarmee gebruikers eenvoudig vanuit hun aliassen kunnen verzenden wanneer ze Outlook op internet gebruiken. Wanneer de functie wordt uitgerold naar een pacht waarbij de tenantbeheerder de `Set-OrganizationConfig -SendFromAliasEnabled $true` cmdlet gebruikt, krijgen gebruikers binnen de huurovereenkomst toegang tot een lijst met selectievakjes waarbij elke vermelding overeenkomt met een alias in hun Outlook instellingen. Als u een alias selecteert, wordt deze weergegeven in de vervolgkeuzelijst Van in het formulier Opstellen.
  
## <a name="related-content"></a>Verwante onderwerpen

[E-mail verzenden vanaf een ander adres](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (artikel)

[Een gebruikersnaam en e-mailadres wijzigen](../add-users/change-a-user-name-and-email-address.md) (artikel)

[E-mail doorsturen configureren in Microsoft 365](configure-email-forwarding.md) (artikel)
