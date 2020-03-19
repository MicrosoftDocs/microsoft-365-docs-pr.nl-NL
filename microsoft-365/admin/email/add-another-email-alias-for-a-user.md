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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Meer informatie over hoe u meer dan één e-mailadres, de zogenaamde e-mailalias, hebben die is gekoppeld aan uw Office 365 voor Bedrijven-account. '
ms.openlocfilehash: 10f219f380d30a5ee8e9822e7a35ee533d165c33
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42810519"
---
# <a name="add-another-email-alias-for-a-user"></a>Een ander e-mailalias toevoegen voor een gebruiker
  
Dit artikel is voor Office 365-beheerders die zakelijke abonnementen hebben. Het is niet bedoeld voor thuisgebruikers.
  
Een primair e-mailadres in Office 365 is meestal het e-mailadres dat een gebruiker heeft toegewezen toen zijn account werd gemaakt. Wanneer de gebruiker een e-mail naar iemand anders verzendt, wordt zijn primaire e-mailadres meestal weergegeven in het veld  *Van*  in e-mailapps. Gebruikers kunnen ook meerdere e-mailadressen koppelen aan hun Office 365 voor Bedrijven-account. Deze extra adressen worden aliassen genoemd. 
  
Stel dat Jenna het e-mailadres jenna@contosoco.com heeft, maar ze wil ook e-mail ontvangen op jen@contosoco.com omdat sommige mensen naar haar verwijzen met die naam. Je aliassen voor haar maken, zodat beide e-mailadressen naar Jenna's inbox gaan.
<br><br>  
  
U kunt maximaal 400 aliassen maken voor een gebruiker. Er worden geen extra kosten in rekening gebracht en u hoeft geen extra licenties te kopen.
  
> [!Tip]
> Als u wilt dat meerdere personen e-mail beheren die naar één e-mailadres wordt verzonden, zoals info@NodPublishers.com of sales@NodPublishers.com, maakt u een gedeeld postvak. Zie [Een gedeeld postvak maken](create-a-shared-mailbox.md)voor meer informatie.
  
## <a name="add-email-aliases-to-a-user"></a>E-mailaliassen toevoegen aan een gebruiker
<a name="AddEmailPreview"> </a>

Je moet [beheerdersmachtigingen](../add-users/about-admin-roles.md) hebben om dit te doen. 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

2. Selecteer op de pagina **Actieve gebruikers** de gebruiker > **E-mailaliassen beheren**. U ziet deze optie niet als de persoon geen licentie heeft die aan hem is toegewezen. 
    
3. Selecteer **+ Voeg een alias toe** en voer een nieuwe alias in voor de gebruiker.   
    
    > [!Important] 
    > Als u het foutbericht "**Een parameter niet kan worden gevonden die overeenkomt met de parameternaam 'E-mailadressen',** betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.
    
  
    > [!IMPORTANT]
    > Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen. 
  
    > [!TIP]
    > De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst. Zie Een domein toevoegen aan [Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx)als u een andere domeinnaam aan de lijst wilt toevoegen. 
  
     
5. Wanneer u klaar bent, kiest u **Wijzigingen opslaan**.
    
6. Wacht 24 uur totdat de nieuwe aliassen volledig zijn verwerkt in Office 365.
    
    De gebruiker heeft nu een primair adres en een alias. Alle e-mail die naar eliza Hoffman's primaire adres wordt verzonden, Eliza@NodPublishers.com en haar alias, Sales@NodPublishers.com, gaan bijvoorbeeld naar Eliza's Inbox.
    
  
7. **Wanneer de gebruiker antwoordt, is het *adres van* het adres haar primaire e-mailalias.** Stel dat er een bericht naar Sales@NodPublishers.com wordt verzonden en dat het in eliza's postvak IN wordt weergegeven. Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com. 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>. 
    
    
2. Selecteer op de pagina **Actieve gebruikers** de gebruikersnaam die u wilt bewerken.

3. Selecteer naast **Gebruikersnaam / E-mailaliassen**de optie **Bewerken**.

    > [!Important] 
    > Als u het foutbericht "**Een parameter niet kan worden gevonden die overeenkomt met de parameternaam 'E-mailadressen',** betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.

4. Typ in het tekstvak onder **Alias**het eerste deel van de nieuwe e-mailalias. Als u uw eigen domein hebt toegevoegd aan Office 365, kunt u het domein voor de nieuwe e-mailalias kiezen in de vervolgkeuzelijst. Selecteer Vervolgens **Toevoegen**.

    > [!IMPORTANT]
    > Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen. 
  
    > [!TIP]
    > De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst. Zie Een domein toevoegen aan [Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx)als u een andere domeinnaam aan de lijst wilt toevoegen. 

5. Als u klaar bent, selecteert u **Opslaan**.

6. Wacht 24 uur totdat de nieuwe aliassen volledig zijn verwerkt in Office 365. 
    
    De gebruiker heeft nu een primair adres en een alias. Alle e-mail die naar eliza Hoffman's primaire adres wordt verzonden, Eliza@NodPublishers.com en haar alias, Sales@NodPublishers.com, gaan bijvoorbeeld naar Eliza's Inbox.
    
  
7. **Wanneer de gebruiker antwoordt, is het *adres van* het adres haar primaire e-mailalias.** Stel dat er een bericht naar Sales@NodPublishers.com wordt verzonden en dat het in eliza's postvak IN wordt weergegeven. Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>. 

    
2. Selecteer op de pagina **Actieve gebruikers** de gebruikersnaam die u wilt bewerken.

3. Selecteer naast **Gebruikersnaam / E-mailaliassen**de optie **Bewerken**.

    > [!Important] 
    > Als u het foutbericht "**Een parameter niet kan worden gevonden die overeenkomt met de parameternaam 'E-mailadressen',** betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.

4. Typ in het tekstvak onder **Alias**het eerste deel van de nieuwe e-mailalias. Als u uw eigen domein hebt toegevoegd aan Office 365, kunt u het domein voor de nieuwe e-mailalias kiezen in de vervolgkeuzelijst. Selecteer Vervolgens **Toevoegen**.

    > [!IMPORTANT]
    > Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen. 
  
    > [!TIP]
    > De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst. Zie Een domein toevoegen aan [Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx)als u een andere domeinnaam aan de lijst wilt toevoegen. 

5. Als u klaar bent, selecteert u **Opslaan**.

6. Wacht 24 uur totdat de nieuwe aliassen volledig zijn verwerkt in Office 365. 
    
    De gebruiker heeft nu een primair adres en een alias. Alle e-mail die naar eliza Hoffman's primaire adres wordt verzonden, Eliza@NodPublishers.com en haar alias, Sales@NodPublishers.com, gaan bijvoorbeeld naar Eliza's Inbox.
    
  
7. **Wanneer de gebruiker antwoordt, is het *adres van* het adres haar primaire e-mailalias.** Stel dat er een bericht naar Sales@NodPublishers.com wordt verzonden en dat het in eliza's postvak IN wordt weergegeven. Wanneer Jacobje het bericht beantwoordt, wordt het primaire e-mailadres weergegeven als de afzender, niet Verkoop@NodPublishers.com. 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>Heb je "Een parameter kan niet worden gevonden die overeenkomt met parameter naam EmailAddresses"?


Als u het foutbericht "**Een parameter kan worden gevonden die overeenkomt met de parameternaam EmailAddresses**" betekent dit dat het iets langer duurt om het instellen van uw tenant of uw aangepaste domein te voltooien als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>Hebt u uw abonnement aangeschaft bij GoDaddy of een andere partner?


Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.
  
## <a name="related-articles"></a>Verwante artikelen

[E-mail verzenden via een ander adres](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[Een gebruikersnaam en e-mailadres wijzigen](../add-users/change-a-user-name-and-email-address.md)
  

