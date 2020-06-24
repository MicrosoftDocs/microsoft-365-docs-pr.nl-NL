---
title: Een voormalige werknemer verwijderen
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
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 44d96212-4d90-4027-9aa9-a95eddb367d1
description: 'Volg deze checklist om een werknemer uit Microsoft 365 te verwijderen en gegevens te beveiligen. '
ms.openlocfilehash: 51fd26835cd74fa8403437397d37395fcf1c7301
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844856"
---
# <a name="remove-a-former-employee"></a>Een voormalige werknemer verwijderen

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
## <a name="sign-out-now"></a>Nu afmelden.

::: moniker range="o365-worldwide"

Bekijk een korte video over het verwijderen van een werknemer. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

Als u deze video nuttig vond, raadpleegt u dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

Ga alsje om te voorkomen dat een werknemer zich aanmeldt:

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

2. Selecteer het vak naast de naam van de gebruiker en selecteer **Wachtwoord opnieuw instellen.**

3. Voer een nieuw wachtwoord in en selecteer **Opnieuw instellen.** (Stuur het niet naar hen.)
    
4. Selecteer de naam van de gebruiker om naar het eigenschappenvenster te gaan en selecteer op het tabblad **OneDrive** de optie **Afmelding starten**.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.

2. Selecteer de gebruiker en selecteer **Wachtwoord opnieuw instellen**.

3. Voer een nieuw wachtwoord in en selecteer **Opnieuw instellen.** (Stuur het niet naar hen.)

4. Selecteer de gebruiker opnieuw, vouw **OneDrive-instellingen**uit en selecteer **Starten** naast **Afmelden**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.

2. Selecteer de gebruiker en selecteer **Wachtwoord opnieuw instellen**.

3. Voer een nieuw wachtwoord in en selecteer **Opnieuw instellen.** (Stuur het niet naar hen.)

4. Selecteer de gebruiker opnieuw, vouw **OneDrive-instellingen**uit en selecteer **Starten** naast **Afmelden**.

::: moniker-end

    
Binnen een uur - of nadat ze de huidige Microsoft 365-pagina waarop ze zich bevinden - worden ze gevraagd om zich opnieuw aan te melden. (Een toegangstoken is goed voor een uur, dus de tijdlijn is afhankelijk van hoeveel tijd er nog over is op dat token en of ze uit hun huidige webpagina navigeren.)
  
 **WAARSCHUWING**: Als de gebruiker zich in de webversie van Outlook bevindt en met het postvak bezig is, kan het zijn dat de gebruiker niet onmiddellijk wordt geblokkeerd. Zodra ze een andere tegel selecteren, zoals OneDrive, of hun browser vernieuwen, wordt het afmelden gestart. 
  
Zie de cmdlet [Revoke-AzureADUserAllRefreshToken](https://go.microsoft.com/fwlink/?linkid=841345) als u PowerShell wilt gebruiken om een gebruiker onmiddellijk af te melden. 
  
Zie [Wat u moet weten over het beëindigen van een sessie van een werknemer](#what-you-need-to-know-about-terminating-an-employees-email-session) voor meer informatie over hoe lang het duurt om iemand de toegang tot e-mail te ontzeggen.
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>Overzicht van alle stappen voor het verwijderen van een werknemer en het beveiligen van gegevens
<a name="bkmk_now"> </a>

Een vraag die we vaak krijgen is: "Wat moet ik doen om gegevens te beschermen wanneer een werknemer de organisatie verlaat?" In dit artikel wordt uitgelegd hoe u de toegang tot Microsoft 365 blokkeren en welke stappen u moet nemen om uw gegevens te beveiligen.
  
> [!NOTE]
> Als u een globale beheerder bent, u de werknemer verwijderen, hun e-mail doorsturen en kiezen wat u met zijn OneDrive-inhoud moet doen met behulp van de nieuwe begeleide ervaring. Zie [Globale beheerder: Een gebruiker verwijderen voor](remove-former-employee.md)meer informatie. We raden u echter aan alle aanvullende stappen die hier worden vermeld, in te vullen om ervoor te zorgen dat de werknemer geen toegang heeft tot de gegevens van uw bedrijf. 
  
Here's a quick overview. Each step is explained in detail in this article.
  
|||
|:-----|:-----|
|**Stap** <br/> |**Reden** <br/> |
|1. [De inhoud van het postvak van een voormalige werknemer opslaan](#save-the-contents-of-a-former-employees-mailbox) <br/> |Dit is handig voor degene die het werk van de werknemer overneemt, of in geval van juridische procedures.  <br/> |
|2. [E-mail van een voormalige werknemer doorsturen naar een andere werknemer of converteren naar een gedeeld postvak](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.  <br/> |
|3. [Het mobiele apparaat van een voormalige werknemer wissen en blokkeren](#wipe-and-block-a-former-employees-mobile-device) <br/> |Verwijdert de zakelijke gegevens van de telefoon of tablet.  <br/> |
|4. [De toegang van een voormalige werknemer tot Microsoft 365-gegevens blokkeren](#block-a-former-employees-access-to-microsoft-365-data)<br/> |Het voorkomt dat de persoon toegang heeft tot zijn oude Microsoft 365-postvak en gegevens.  <br/><br/> **Tip:** Wanneer u de toegang van een gebruiker blokkeert, betaalt u nog steeds voor zijn of haar licentie. Verwijder de licentie uit uw abonnement als u er niet meer voor wilt betalen ( stap 5).           |
|5. [OneDrive-inhoud van de werknemer verplaatsen](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |Als u alleen de licentie van een gebruiker verwijdert maar niet het account, blijft de inhoud van de OneDrive van de gebruiker nog maximaal dertig dagen toegankelijk.  <br/><br/> Before you delete the account, you should move the content of their OneDrive to another location that's easy for you to access. After you delete an employee's account, the content in their OneDrive is retained for **30** days. During that 30 days, however, you can restore the user's account, and gain access to their OneDrive content. If you restore the user's account, the OneDrive content will remain accessible to you even after 30 days.  <br/> |
|5a. What if the person used their personal computer to access OneDrive and SharePoint?  <br/> |Als iemand een pc in plaats van een door het bedrijf verstrekte computer heeft gebruikt om bestanden te downloaden van OneDrive en SharePoint, is het niet mogelijk om de bestanden te wissen die deze persoon heeft opgeslagen.  <br/><br/> Deze persoon blijft toegang houden tot bestanden die met de computer van deze persoon zijn gesynchroniseerd.  <br/> |
|6. [De Microsoft 365-licentie verwijderen en verwijderen van een voormalige werknemer](#remove-and-delete-the-microsoft-365-license-from-a-former-employee)<br/> |When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person.  <br/><br/> When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  <br/> |
|7. [Het gebruikersaccount van een voormalige werknemer verwijderen](#delete-a-former-employees-user-account)<br/> |Hiermee wordt het account verwijderd uit uw beheercentrum. Houdt alles schoon.  <br/> |
   
## <a name="save-the-contents-of-a-former-employees-mailbox"></a>De inhoud van het postvak van een voormalige werknemer opslaan
<a name="bkmk_preserve"> </a>

U kunt de inhoud van het postvak van de voormalige werknemer op twee manieren opslaan:
  
1. Add the former employee's email address to your version of Outlook 2013 or 2016, and then export the data to a .pst file. You can import the data to another email account as needed. To learn how to do this, see [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).
    
    OF
    
2. Place a Litigation Hold or In-Place Hold on the mailbox before the deleting the user account. This is much more complicated than the first option but worth doing if: your Enterprise plan includes archiving and legal hold, litigation is a possibility, and you have a technically strong IT department.
    
    Als u het postvak hebt omgezet in een 'inactief postvak', kunnen beheerders, compliance officers of recordbeheerders hulpprogramma's van In-Place eDiscovery in Exchange Online gebruiken om de inhoud te openen en te doorzoeken.
    
    Inactieve postvakken kunnen geen e-mail ontvangen en worden niet weergegeven in het gedeelde adresboek van uw organisatie of in andere lijsten.
    
    Zie [Inactieve postvakken beheren in Exchange Online voor](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)meer informatie over het plaatsen van een blokkering in een postvak.
    
## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>E-mail van een voormalige werknemer doorsturen naar een andere werknemer of converteren naar een gedeeld postvak
<a name="bkmk_forward"> </a>

In deze stap wijst u het e-mailadres van de voormalige werknemer toe aan een andere werknemer of [converteert u het postvak van de gebruiker naar een gedeeld postvak](../email/convert-user-mailbox-to-shared-mailbox.md) dat u hebt gemaakt. 
  
- Creating a shared mailbox is the less expensive way to go because you won't have to pay for a license **as long as the mailbox is smaller than 50GB**. Over 50GB and you'll need to assign a license to it. 
    
- If you convert the mailbox to a shared mailbox, all the old email will be available, too. This can take up a lot of space.
    
- Als u e-mail doorsturen hebt ingesteld, worden alleen  *nieuwe*  e-mails die naar de voormalige werknemer worden verzonden, nu naar de huidige werknemer gestuurd. 
    
- Voor het doorsturen van e-mail is vereist dat het account van de voormalige werknemer een licentie heeft.
    
 > [!IMPORTANT] 
 > Als u e-mail doorstuurt of een gedeeld postvak, verwijdert u uiteindelijk het account van de vorige werknemer niet. Het account moet aanwezig zijn om het doorsturen van e-mail of het gedeelde postvak te bevestigen. 

::: moniker range="o365-worldwide"  

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

2. Selecteer de naam van de werknemer die u wilt blokkeren en selecteer het tabblad **E-mail.**

3. Selecteer onder **E-mail doorsturen**de optie **E-mail doorsturen beheren**.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Kies **Opslaan**. 
    
6. Vergeet niet dat u het account van de voormalige werknemer dient te behouden.
 
::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.

2. Selecteer de werknemer die u wilt blokkeren en uitvouwen **e-mailinstellingen**.

3. **Selecteer**bewerken naast **e-mail doorsturen**.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Kies **Opslaan**. 
    
6. Vergeet niet dat u het account van de voormalige werknemer dient te behouden.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.

2. Selecteer de werknemer die u wilt blokkeren en uitvouwen **e-mailinstellingen**.

3. **Selecteer**bewerken naast **e-mail doorsturen**.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Kies **Opslaan**. 
    
6. Vergeet niet dat u het account van de voormalige werknemer dient te behouden.

::: moniker-end


    
## <a name="wipe-and-block-a-former-employees-mobile-device"></a>Het mobiele apparaat van een voormalige werknemer wissen en blokkeren
<a name="bkmk_mobile"> </a>

Als de voormalige werknemer een telefoon van de zaak had, kunt u deze via het Exchange-beheercentrum wissen en blokkeren om alle bedrijfsgegevens van het apparaat te verwijderen zodat het apparaat geen verbinding meer kan maken met Office 365.
  

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.

3. Ga in het Exchange-beheercentrum naar **Ontvangers** \> **Postvakken**. 
    
4. Selecteer de gebruiker en selecteer onder **Mobiele apparaten**de optie **Details weergeven**. 
    
5. Selecteer op de pagina **Details van mobiele apparaten** onder Mobiele **apparaten**de optie **Wipe Data** ![ Gegevensvegende apparaat wissen ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) en selecteer **Vervolgens Blokkeren**. 
    
6. Kies **Opslaan**. 
    
    **Tip**: Be sure you remove or disable the user from your on-premises Blackberry Enterprise Service. You should also disable any Blackberry devices for the user. Refer to the Blackberry Business Cloud Services Administration Guide if you need specific steps on how to disable the user. 
    
## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>De toegang van een voormalige werknemer tot Microsoft 365-gegevens blokkeren
<a name="bkmk_block"> </a>

 > [!IMPORTANT] 
 > Het blokkeren van een account kan tot 24 uur duren. Als u de aanmeldingstoegang van een gebruiker onmiddellijk moet voorkomen, moet u [het wachtwoord opnieuw instellen](reset-passwords.md) en vervolgens een eenmalige gebeurtenis starten die deze tijd afmeldt bij Microsoft 365-sessies op alle apparaten. Zie [Nu afmelden!](#sign-out-now)
 

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

2. Selecteer de naam van de werknemer die u wilt blokkeren en selecteer onder de naam van de gebruiker het symbool voor **Deze gebruiker blokkeren.**

3. Selecteer **De gebruiker blokkeren om zich aan te melden**en selecteer **Opslaan**. 

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.

2. Selecteer de werknemer die u wilt blokkeren en selecteer **Aanmelding blokkeren.**

3. Selecteer **De gebruiker blokkeren om zich aan te melden**en selecteer **Opslaan**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.

2. Selecteer de werknemer die u wilt blokkeren en selecteer **Aanmelding blokkeren.**

3. Selecteer **De gebruiker blokkeren om zich aan te melden**en selecteer **Opslaan**. 

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>De toegang van een voormalige werknemer tot e-mail (Exchange Online) blokkeren
<a name="bkmk_block_email"> </a>

Als u e-mail hebt als onderdeel van uw Microsoft 365-abonnement, moet u zich aanmelden bij het Exchange-beheercentrum om deze stappen te volgen om te voorkomen dat uw voormalige werknemer toegang krijgt tot zijn e-mail.
  

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.
     
2. Ga in het Exchange-beheercentrum naar **Ontvangers** \> **Postvakken**. 
    
3. Dubbelklik op de gebruiker en ga naar de pagina Met de onderdelen **postvak.** Selecteer onder **Mobiele apparaten** **Exchange ActiveSync uitschakelen** en **OWA uitschakelen voor apparaten** en antwoord **ja** op beide wanneer daarom wordt gevraagd. 
    
4. Selecteer onder **Verbinding met e-mail**de optie **Uitschakelen** en beantwoorden **ja** wanneer daarom wordt gevraagd. 
    
## <a name="remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>De Microsoft 365-licentie verwijderen en verwijderen van een voormalige werknemer
<a name="bkmk_remove"> </a>

U hoeft dus niet te blijven betalen voor een licentie nadat iemand uw organisatie heeft verlaten, maar moet de Microsoft 365-licentie verwijderen en deze vervolgens uit uw abonnement verwijderen. Als u de licentie niet uit het abonnement verwijdert, kunt u deze aan een andere gebruiker toewijzen.
  
Als u de licentie verwijdert, worden alle gegevens van die gebruiker gedurende dertig dagen bewaard. U kunt de gegevens [openen](get-access-to-and-back-up-a-former-user-s-data.md) of het account [herstellen](restore-user.md) als de gebruiker terugkeert. Na 30 dagen worden alle gegevens van de gebruiker (behalve documenten die zijn opgeslagen op SharePoint Online) permanent verwijderd uit Microsoft 365 en kunnen ze niet worden hersteld. 

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

2. Selecteer de naam van de werknemer die u wilt blokkeren en selecteer het tabblad **Licenties en Apps.**

4. Schakel de selectievakjes uit voor de licentie(s) die u wilt verwijderen en selecteer **Wijzigingen opslaan**.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.

2. Selecteer de werknemer die u wilt blokkeren en selecteer vervolgens naast **Productlicenties** **Bewerken**.

3. Schakel op de pagina **Productlicenties** de licentie(s) die u wilt verwijderen uit en selecteer **Opslaan.**

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.

2. Selecteer de werknemer die u wilt blokkeren en selecteer vervolgens naast **Productlicenties** **Bewerken**.

3. Schakel op de pagina **Productlicenties** de licentie(s) die u wilt verwijderen uit en selecteer **Opslaan.**

::: moniker-end


**Als u het aantal licenties wilt verminderen waarvoor u betaalt** totdat u een andere persoon inhuurt, gaat u als volgt te werk: 

::: moniker range="o365-worldwide"



1. Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.


::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Facturering**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abonnementen</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Facturering**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abonnementen</a>.

::: moniker-end
    
2. Selecteer **Licenties toevoegen/verwijderen** om de licentie te verwijderen, zodat u deze pas betaalt als u een andere persoon hebt ingehuurd.

Wanneer u een andere persoon aan uw bedrijf [toevoegt,](add-users.md) wordt u gevraagd om tegelijkertijd een licentie te kopen, met slechts één stap!
    
Zie [Licenties toewijzen aan gebruikers in Microsoft 365 voor bedrijven](../manage/assign-licenses-to-users.md)en [Licenties verwijderen van gebruikers in Microsoft 365 voor bedrijven en Licenties verwijderen van gebruikers in Microsoft 365 voor bedrijven](../manage/remove-licenses-from-users.md).
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>Invloed van een verwijderd werknemersaccount op Skype voor Bedrijven
<a name="bkmk_remove"> </a>

When you remove a user's license from Office 365, the PSTN calling number associated with the user will be released. You can assign it to another user.
  
If the user belongs to a queue group, they will no longer be a viable target of the call queue agents. So, we recommend also removing the user from the groups associated with the call queue. 
  
## <a name="delete-a-former-employees-user-account"></a>Het gebruikersaccount van een voormalige werknemer verwijderen
<a name="bkmk_delete"> </a>

Nadat u de gegevens van de voormalige werknemer hebt opgeslagen en beschikbaar hebt gemaakt, kunt u het account van de werknemer verwijderen.
  
Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

2. Selecteer de naam van de werknemer die u wilt verwijderen.

3. Selecteer onder de naam van de gebruiker het symbool voor **Gebruiker verwijderen**. Kies de gewenste opties voor deze gebruiker en selecteer **Gebruiker verwijderen**.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.

2. Selecteer de naam van de werknemer die u wilt verwijderen.

3. Selecteer gebruiker **verwijderen**boven aan de pagina. Kies de gewenste opties voor deze gebruiker en selecteer **Gebruiker verwijderen**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.

2. Selecteer de naam van de werknemer die u wilt verwijderen.

3. Selecteer gebruiker **verwijderen**boven aan de pagina. Kies de gewenste opties voor deze gebruiker en selecteer **Gebruiker verwijderen**.

::: moniker-end

When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.
  
### <a name="does-your-organization-use-active-directory"></a>Maakt uw organisatie gebruik van Active Directory?

Als uw organisatie gebruikersaccounts synchroniseert met Microsoft 365 vanuit een lokale Active Directory-omgeving, moet u deze gebruikersaccounts verwijderen en herstellen in uw lokale Active Directory-service. U kunt ze niet verwijderen of herstellen via Office 365.
  
Lees voor instructies dit artikel: [Een gebruikersaccount verwijderen](https://go.microsoft.com/fwlink/?linkid=841808).
  
Als u Azure Active Directory gebruikt, raadpleegt u de PowerShell-cmdlet [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230). 
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>Wat u moet weten over het beëindigen van een sessie van een werknemer
<a name="bkmk_session"> </a>

Zo ontzegt u een werknemer de toegang tot e-mail (Exchange).
  
|||
|:-----|:-----|
|**Wat u kunt doen** <br/> |**Hoe u dat kunt doen** <br/> |
|Een sessie beëindigen (zoals voor de webversie van Outlook, Outlook, Exchange Active Sync, enzovoort) en een nieuwe sessie geforceerd openen  <br/> |Wachtwoord opnieuw instellen  <br/> |
|Een sessie beëindigen en toegang blokkeren voor toekomstige sessies (voor alle protocollen)  <br/> |Disable the account. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|De sessie voor een bepaald protocol (zoals ActiveSync) beëindigen  <br/> |Disable the protocol. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |
   
De bovenstaande bewerkingen kunnen op drie locaties worden uitgevoerd:
  
|||
|:-----|:-----|
|**Als u de sessie hier beëindigt** <br/> |**Hoe lang dit duurt** <br/> |
|In het Exchange-beheercentrum of via PowerShell  <br/> |Verwachte vertraging is korter dan 30 minuten  <br/> |
|In het Azure Active Directory-beheercentrum  <br/> |Verwachte vertraging is 60 minuten  <br/> |
|In een lokale omgeving  <br/> |Verwachte vertraging is 3 uur of langer  <br/> |
   
### <a name="how-to-get-fastest-response-for-account-termination"></a>Zo krijgt u de snelste reactie voor het beëindigen van een account

 **Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync. 
  
 **Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync. 
  
## <a name="related-articles"></a>Verwante artikelen

[Een gebruiker herstellen](restore-user.md)
  
