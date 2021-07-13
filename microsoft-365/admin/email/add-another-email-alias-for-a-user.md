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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Meer informatie over hoe u meer dan één e-mailadres, een e-mailalias genaamd, kunt hebben dat is gekoppeld aan uw Microsoft 365 voor Bedrijven-account. '
ms.openlocfilehash: ab1a7b846bb35cce4656a3a5edf941961f5398c2
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394025"
---
# <a name="add-another-email-alias-for-a-user"></a>Een ander e-mailalias toevoegen voor een gebruiker
  
Dit artikel is bedoeld voor Microsoft 365 beheerders die zakelijke abonnementen hebben. Het is niet bedoeld voor thuisgebruikers.
  
Een primair e-mailadres in Microsoft 365 is meestal het e-mailadres dat aan een gebruiker is toegewezen toen het account werd gemaakt. Wanneer de gebruiker een e-mail naar iemand anders verzendt, wordt zijn primaire e-mailadres meestal weergegeven in het veld  *Van*  in e-mailapps. Ze kunnen ook meer dan één e-mailadres hebben dat is gekoppeld aan hun Microsoft 365 voor Bedrijven-account. Deze extra adressen worden aliassen genoemd. 
  
Laten we bijvoorbeeld aannemen dat Jenna het e-mailadres jenna@contosoco.com heeft, maar ze wil ook e-mail ontvangen op jen@contosoco.com, omdat sommige mensen naar haar verwijzen met die naamn. U kunt aliassen voor haar maken, zodat beide e-mailadressen naar het Postvak IN van Jenna gaan.
  
U kunt maximaal 400 aliassen maken voor een gebruiker. Er worden geen extra kosten in rekening gebracht en u hoeft geen extra licenties te kopen.
  
> [!Tip]
> Als u wilt dat meerdere personen e-mailberichten beheren die naar één e-mailadres worden verzonden, zoals info@NodPublishers.com of sales@NodPublishers.com, maakt u een gedeeld postvak. Zie [Een gedeeld postvak maken](create-a-shared-mailbox.md)voor meer informatie.
  
## <a name="add-email-aliases-to-a-user"></a>E-mailaliassen toevoegen aan een gebruiker

U moet [beheerdersmachtigingen](../add-users/about-admin-roles.md) hebben om deze stappen uit te voeren.  

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

2. Selecteer op de pagina **Actieve gebruikers** de gebruiker > **Gebruikersnaam en e-mailadres beheren**. Deze optie wordt niet weergegeven als er geen licentie aan de persoon is toegewezen. 
    
3. Selecteer **+ Een alias toevoegen** en voer een nieuwe alias in voor de gebruiker.   
    
    > [!Important] 
    > Als het foutbericht '**Een parameter die overeenkomt met de parameternaam 'EmailAddresses' kan niet worden gevonden**' wordt weergegeven, betekent dit dat het nog wat tijd nodig heeft om uw tenant of uw aangepaste domein in te stellen, als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.
    
  
    > [!IMPORTANT]
    > Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen. 
  
    > [!TIP]
    > De e-mailalias moet eindigen op een domein uit de vervolgkeuzelijst. Zie [Een extra domein toevoegen aan Microsoft 365](../setup/add-domain.md) voor informatie over het toevoegen van een andere domeinnaam aan de lijst. 
  
     
5. Kies **Wijzigingen opslaan** wanneer u klaar bent.
    
6. Wacht 24 uur totdat de nieuwe aliassen volledig zijn verwerkt in Microsoft 365. 
    
    De gebruiker heeft nu een primair adres en een alias. Alle e-mailberichten die worden verzonden naar het primaire adres van Eliza Hoffman, Eliza@NodPublishers.com en haar alias, Sales@NodPublishers.com, gaan bijvoorbeeld naar het Postvak IN van Eliza.
    
  
7. **Wanneer de gebruiker antwoordt, is het *Van* -adres afhankelijk van haar Outlook-client. De webversie van Outlook gebruikt de alias waarop het e-mailbericht is ontvangen (dit wordt het ping-pong-principe noemen). De bureaubladversie van Outlook gebruikt haar primaire e-mailalias.** Stel dat er een bericht wordt verzonden naar Sales@Contoso.com en dat dit bericht binnenkomt in het Postvak IN van Eliza. Wanneer Eliza het bericht beantwoordt via de bureaubladversie van Outlook, wordt haar primaire e-mailadres weergegeven als Eliza@NodPublishers.com, niet als Sales@NodPublishers.com.
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>Wordt het foutbericht 'Een parameter die overeenkomt met de parameternaam 'EmailAddresses' kan niet worden gevonden' weergegeven?

Als het foutbericht '**Een parameter die overeenkomt met de parameternaam 'EmailAddresses' kan niet worden gevonden**' wordt weergegeven, betekent dit dat het nog wat tijd nodig heeft om uw tenant of uw aangepaste domein in te stellen, als u er onlangs een hebt toegevoegd. Het instellen kan 4 uur duren. Wacht even, zodat de instellingsprocedure kan worden voltooid en probeer het vervolgens opnieuw. Als het probleem aanhoudt, bel dan de Ondersteuning; zij voeren dan een volledige synchronisatie voor u uit.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>Hebt u uw abonnement aangeschaft bij GoDaddy of een andere partner?


Als u uw abonnement bij GoDaddy of een andere partner hebt aangeschaft, moet u naar de beheerconsole van GoDaddy of de andere partner gaan om de nieuwe alias als het primaire e-mailadres in te stellen.

## <a name="sending-email-from-the-proxy-address-easily"></a>Eenvoudig e-mail verzenden vanaf het proxyadres

In juli 2021 wordt een nieuwe functie uitgerold waarmee gebruikers eenvoudig vanuit hun aliassen kunnen verzenden wanneer ze webversie van Outlook. Wanneer de functie wordt uitgerold naar een tenancy waarbij de tenantbeheerder de cmdlet `Set-OrganizationConfig -SendFromAliasEnabled $true` gebruikt, krijgen gebruikers binnen de tenancy toegang tot een lijst met selectievakjes waarbij elke vermelding overeenkomt met een alias in hun Outlook-instellingen. Als u een alias selecteert, wordt deze weergegeven in de vervolgkeuzelijst Van in het formulier Opstellen.
  
## <a name="related-content"></a>Verwante inhoud

[E-mail verzenden vanaf een ander adres](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (artikel)

[Een gebruikersnaam en e-mailadres wijzigen](../add-users/change-a-user-name-and-email-address.md) (artikel)

[Doorsturen van e‑mail configureren in Microsoft 365](configure-email-forwarding.md) (artikel)
