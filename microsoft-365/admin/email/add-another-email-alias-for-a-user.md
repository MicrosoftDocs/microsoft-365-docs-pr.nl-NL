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
description: 'Ontdek hoe u meer dan één e-mailadres, e-mailalias genaamd, hebben gekoppeld aan uw Microsoft 365 voor bedrijven-account. '
ms.openlocfilehash: 030d8022a8503f6b383d03b0dd97720f66d8f2f6
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080013"
---
# <a name="add-another-email-alias-for-a-user"></a>Een ander e-mailalias toevoegen voor een gebruiker

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
Dit artikel is voor Microsoft 365-beheerders met zakelijke abonnementen. Het is niet bedoeld voor thuisgebruikers.
  
Een primair e-mailadres in Microsoft 365 is meestal het e-mailadres dat een gebruiker heeft toegewezen toen zijn account werd gemaakt. Wanneer de gebruiker een e-mail naar iemand anders verzendt, wordt zijn primaire e-mailadres meestal weergegeven in het veld  *Van*  in e-mailapps. Ze kunnen ook meer dan één e-mailadres hebben dat is gekoppeld aan hun Microsoft 365 voor bedrijven-account. Deze extra adressen worden aliassen genoemd. 
  
Stel dat Jenna het e-mailadres heeft jenna@contosoco.com, maar ze wil ook e-mail ontvangen op jen@contosoco.com omdat sommige mensen naar haar verwijzen met die naam. U aliassen voor haar maken, zodat beide e-mailadressen naar jenna's inbox gaan.
<br><br>  
  
U kunt maximaal 400 aliassen maken voor een gebruiker. Er worden geen extra kosten in rekening gebracht en u hoeft geen extra licenties te kopen.
  
> [!Tip]
> Als u wilt dat meerdere personen e-mail beheren die naar één e-mailadres worden verzonden, zoals info@NodPublishers.com of sales@NodPublishers.com, maakt u een gedeeld postvak. Zie [Een gedeeld postvak maken](create-a-shared-mailbox.md)voor meer informatie.
  
## <a name="add-email-aliases-to-a-user"></a>E-mailaliassen toevoegen aan een gebruiker
<a name="AddEmailPreview"> </a>

Hiervoor moet [u beheerdersmachtigingen](../add-users/about-admin-roles.md) hebben. 

  
::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

2. Selecteer op de pagina **Actieve gebruikers** de gebruiker > **E-mailaliassen beheren**. U ziet deze optie niet als de persoon geen licentie aan deze persoon heeft toegewezen. 
    
3. Selecteer **+ Voeg een alias toe** en voer een nieuwe alias voor de gebruiker in.   
    
    > [!Important] 
    > Als u het foutbericht "**Een parameter kan niet worden gevonden die overeenkomt met parameternaam 'EmailAddresses**", betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein af te ronden als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.
    
  
    > [!IMPORTANT]
    > Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen. 
  
    > [!TIP]
    > De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst. Zie Een domein toevoegen aan [Microsoft 365 als](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)u een andere domeinnaam aan de lijst wilt toevoegen. 
  
     
5. Als u klaar bent, kiest u **Wijzigingen opslaan**.
    
6. Wacht 24 uur tot de nieuwe aliassen zijn gevuld in Microsoft 365.
    
    De gebruiker heeft nu een primair adres en een alias. Alle e-mail die naar eliza Hoffman's primaire adres wordt verzonden, Eliza@NodPublishers.com en haar alias Sales@NodPublishers.com, gaan bijvoorbeeld naar Eliza's Postvak IN.
    
  
7. **Wanneer de gebruiker antwoordt, is het *van-adres* haar primaire e-mailalias.** Stel dat er een bericht naar Sales@NodPublishers.com wordt verzonden en in de inbox van Eliza wordt weergegeven. Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com. 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>. 
    
    
2. Selecteer op de pagina **Actieve gebruikers** de gebruikersnaam die u wilt bewerken.

3. Selecteer naast **Gebruikersnaam / E-mailaliassen**de optie **Bewerken**.

    > [!Important] 
    > Als u het foutbericht "**Een parameter kan niet worden gevonden die overeenkomt met parameternaam 'EmailAddresses**", betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein af te ronden als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.

4. Typ in het tekstvak onder **Alias**het eerste deel van de nieuwe e-mailalias. Als u uw eigen domein hebt toegevoegd aan Microsoft 365, u het domein voor de nieuwe e-mailalias kiezen met de vervolgkeuzelijst. Selecteer Vervolgens **Toevoegen**.

    > [!IMPORTANT]
    > Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen. 
  
    > [!TIP]
    > De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst. Zie Een domein toevoegen aan [Microsoft 365 als](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)u een andere domeinnaam aan de lijst wilt toevoegen. 

5. Wanneer u klaar bent, selecteert u **Opslaan**.

6. Wacht 24 uur tot de nieuwe aliassen zijn gevuld in Microsoft 365. 
    
    De gebruiker heeft nu een primair adres en een alias. Alle e-mail die naar eliza Hoffman's primaire adres wordt verzonden, Eliza@NodPublishers.com en haar alias Sales@NodPublishers.com, gaan bijvoorbeeld naar Eliza's Postvak IN.
    
  
7. **Wanneer de gebruiker antwoordt, is het *van-adres* haar primaire e-mailalias.** Stel dat er een bericht naar Sales@NodPublishers.com wordt verzonden en in de inbox van Eliza wordt weergegeven. Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>. 

    
2. Selecteer op de pagina **Actieve gebruikers** de gebruikersnaam die u wilt bewerken.

3. Selecteer naast **Gebruikersnaam / E-mailaliassen**de optie **Bewerken**.

    > [!Important] 
    > Als u het foutbericht "**Een parameter kan niet worden gevonden die overeenkomt met parameternaam 'EmailAddresses**", betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein af te ronden als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.

4. Typ in het tekstvak onder **Alias**het eerste deel van de nieuwe e-mailalias. Als u uw eigen domein hebt toegevoegd aan Microsoft 365, u het domein voor de nieuwe e-mailalias kiezen met de vervolgkeuzelijst. Selecteer Vervolgens **Toevoegen**.

    > [!IMPORTANT]
    > Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen. 
  
    > [!TIP]
    > De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst. Zie Een domein toevoegen aan [Microsoft 365 als](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)u een andere domeinnaam aan de lijst wilt toevoegen. 

5. Wanneer u klaar bent, selecteert u **Opslaan**.

6. Wacht 24 uur tot de nieuwe aliassen zijn gevuld in Microsoft 365. 
    
    De gebruiker heeft nu een primair adres en een alias. Alle e-mail die naar eliza Hoffman's primaire adres wordt verzonden, Eliza@NodPublishers.com en haar alias Sales@NodPublishers.com, gaan bijvoorbeeld naar Eliza's Postvak IN.
    
  
7. **Wanneer de gebruiker antwoordt, is het *van-adres* haar primaire e-mailalias.** Stel dat er een bericht naar Sales@NodPublishers.com wordt verzonden en in de inbox van Eliza wordt weergegeven. Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com. 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>Heb je 'Een parameter kan niet worden gevonden die overeenkomt met de parameternaam EmailAddresses'?


Als u het foutbericht "**Een parameter kan niet worden gevonden die overeenkomt met parameternaam EmailAddresses**" betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>Hebt u uw abonnement aangeschaft bij GoDaddy of een andere partner?


Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.
  
## <a name="related-articles"></a>Verwante artikelen

[E-mail verzenden via een ander adres](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[Een gebruikersnaam en e-mailadres wijzigen](../add-users/change-a-user-name-and-email-address.md)
  

