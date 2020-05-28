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
ms.openlocfilehash: 293ad26645aa3b190c25271273b29ac6c4ec8ed0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387043"
---
# <a name="remove-a-former-employee"></a>Een voormalige werknemer verwijderen

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
## <a name="sign-out-now"></a>Nu afmelden.

::: moniker range="o365-worldwide"

> [!NOTE]
> Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.

Bekijk een korte video over het verwijderen van een werknemer. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

Als u deze video nuttig vond, raadpleegt u dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

Ga als u een werknemer verwijderen:

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

2. Selecteer het vak naast de naam van de gebruiker en selecteer **Wachtwoord opnieuw instellen**.

3. Voer een nieuw wachtwoord in en selecteer **Opnieuw instellen**. (Stuur het niet naar hen.)
    
4. Selecteer de naam van de gebruiker om naar het eigenschappenvenster te gaan en selecteer op het tabblad **OneDrive** de optie **Afmelding initiëren**.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.

2. Selecteer de gebruiker en selecteer **Wachtwoord opnieuw instellen**.

3. Voer een nieuw wachtwoord in en selecteer **Opnieuw instellen**. (Stuur het niet naar hen.)

4. Selecteer de gebruiker opnieuw, vouw **OneDrive-instellingen**uit en selecteer **Starten** naast **Afmelden**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.

2. Selecteer de gebruiker en selecteer **Wachtwoord opnieuw instellen**.

3. Voer een nieuw wachtwoord in en selecteer **Opnieuw instellen**. (Stuur het niet naar hen.)

4. Selecteer de gebruiker opnieuw, vouw **OneDrive-instellingen**uit en selecteer **Starten** naast **Afmelden**.

::: moniker-end

    
Binnen een uur - of nadat ze de huidige Microsoft 365-pagina hebben verlaten waarop ze zich bevinden - wordt ze gevraagd om zich opnieuw aan te melden. (Een toegangstoken is goed voor een uur, dus de tijdlijn is afhankelijk van hoeveel tijd er nog over is op dat token en of ze uit hun huidige webpagina navigeren.)
  
 **WAARSCHUWING**: Als de gebruiker zich in de webversie van Outlook bevindt en met het postvak bezig is, kan het zijn dat de gebruiker niet onmiddellijk wordt geblokkeerd. Zodra ze een andere tegel selecteren, zoals OneDrive, of hun browser vernieuwen, wordt de afmelding gestart. 
  
Zie de cmdlet [Revoke-AzureADUserAllRefreshToken](https://go.microsoft.com/fwlink/?linkid=841345) als u PowerShell wilt gebruiken om een gebruiker onmiddellijk af te melden. 
  
Zie [Wat u moet weten over het beëindigen van een sessie van een werknemer](#what-you-need-to-know-about-terminating-an-employees-email-session) voor meer informatie over hoe lang het duurt om iemand de toegang tot e-mail te ontzeggen.
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>Overzicht van alle stappen voor het verwijderen van een werknemer en het beveiligen van gegevens
<a name="bkmk_now"> </a>

Een vraag die we vaak krijgen is: "Wat moet ik doen om gegevens te beschermen wanneer een werknemer de organisatie verlaat?" In dit artikel wordt uitgelegd hoe u de toegang tot Microsoft 365 blokkeren en welke stappen u moet ondernemen om uw gegevens te beveiligen.
  
> [!NOTE]
> Als u een globale beheerder bent, u de werknemer verwijderen, zijn e-mail doorsturen en kiezen wat u met zijn OneDrive-inhoud wilt doen met de nieuwe begeleide ervaring. Zie [Globale beheerder: Een gebruiker verwijderen voor](remove-former-employee.md)meer informatie. We raden u echter aan alle aanvullende stappen te voltooien die hier worden vermeld om ervoor te zorgen dat de werknemer geen toegang heeft tot de gegevens van uw bedrijf. 
  
Hier volgt een kort overzicht. Elke stap in dit artikel wordt tot in detail beschreven.
  
|||
|:-----|:-----|
|**Stap** <br/> |**Reden** <br/> |
|1. [De inhoud van het postvak van een voormalige werknemer opslaan](#save-the-contents-of-a-former-employees-mailbox) <br/> |Dit is handig voor degene die het werk van de werknemer overneemt, of in geval van juridische procedures.  <br/> |
|2. [E-mail van een voormalige werknemer doorsturen naar een andere werknemer of converteren naar een gedeeld postvak](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |Hiermee kunt u het e-mailadres van een voormalige werknemer actief houden. Als er klanten of partners zijn die hun e-mail nog steeds naar het vorige adres van de werknemer verzenden, komen ze hiermee terecht bij de persoon die het werk overneemt.  <br/> |
|3. [Het mobiele apparaat van een voormalige werknemer wissen en blokkeren](#wipe-and-block-a-former-employees-mobile-device) <br/> |Verwijdert de zakelijke gegevens van de telefoon of tablet.  <br/> |
|4. [De toegang van een voormalige werknemer tot Microsoft 365-gegevens blokkeren](#block-a-former-employees-access-to-microsoft-365-data)<br/> |Het voorkomt dat de persoon toegang heeft tot zijn oude Microsoft 365-postvak en gegevens.  <br/><br/> **Tip:** Wanneer u de toegang van een gebruiker blokkeert, betaalt u nog steeds voor zijn of haar licentie. Verwijder de licentie uit uw abonnement als u er niet meer voor wilt betalen ( stap 5).           |
|5. [OneDrive-inhoud van de werknemer verplaatsen](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |Als u alleen de licentie van een gebruiker verwijdert maar niet het account, blijft de inhoud van de OneDrive van de gebruiker nog maximaal dertig dagen toegankelijk.  <br/><br/> Voordat u het account verwijdert, kunt u de inhoud van zijn of haar OneDrive het beste verplaatsen naar een andere locatie waartoe u eenvoudig toegang hebt. Nadat u het account van een werknemer verwijdert, blijft de inhoud van zijn of haar OneDrive nog **30** dagen behouden. Tijdens deze dertig dagen kunt u het account van de gebruiker echter herstellen en toegang krijgen tot de inhoud van zijn of haar OneDrive. Als u het account van de gebruiker herstelt, hebt u nog maximaal dertig dagen toegang tot de inhoud in OneDrive.  <br/> |
|5a. Wat gebeurt er als de persoon zijn of haar persoonlijke computer heeft gebruikt om toegang te krijgen tot OneDrive en SharePoint?  <br/> |Als iemand een pc in plaats van een door het bedrijf verstrekte computer heeft gebruikt om bestanden te downloaden van OneDrive en SharePoint, is het niet mogelijk om de bestanden te wissen die deze persoon heeft opgeslagen.  <br/><br/> Deze persoon blijft toegang houden tot bestanden die met de computer van deze persoon zijn gesynchroniseerd.  <br/> |
|6. [De Microsoft 365-licentie verwijderen en verwijderen van een voormalige werknemer](#remove-and-delete-the-microsoft-365-license-from-a-former-employee)<br/> |Als u een licentie verwijdert, kunt u deze aan iemand anders toewijzen. U kunt de licentie ook wissen, zodat u er niet voor hoeft te betalen totdat u een andere persoon inhuurt.  <br/><br/> Als u een licentie verwijdert of wist, worden de oude e-mailberichten, de contactpersonen en de agenda van de gebruiker gedurende **30 dagen** bewaard. Daarna worden ze definitief gewist. Als u de licentie van een gebruiker verwijdert of wist, maar het account niet wist, blijft de inhoud van de OneDrive van de gebruiker nog maximaal dertig dagen toegankelijk.  <br/> |
|7. [Het gebruikersaccount van een voormalige werknemer verwijderen](#delete-a-former-employees-user-account)<br/> |Hiermee wordt het account verwijderd uit uw beheercentrum. Houdt alles schoon.  <br/> |
   
## <a name="save-the-contents-of-a-former-employees-mailbox"></a>De inhoud van het postvak van een voormalige werknemer opslaan
<a name="bkmk_preserve"> </a>

U kunt de inhoud van het postvak van de voormalige werknemer op twee manieren opslaan:
  
1. Voeg het e-mailadres van de voormalige werknemer toe aan uw versie van Outlook 2013 of 2016 en exporteer de gegevens naar een PST-bestand. U kunt de gegevens ook in een ander e-mailaccount importeren. Zie hiervoor [Toegang krijgen tot de gegevens van een voormalige gebruiker en er een back-up van maken](get-access-to-and-back-up-a-former-user-s-data.md).
    
    OF
    
2. Pas bewaring van postvakgegevens vanwege juridische procedure of een in-place bewaring op het postvak toe voordat u het gebruikersaccount verwijdert. Dit is veel ingewikkelder dan de eerste optie, maar wel de moeite waard indien: uw Enterprise-abonnement een archiveerfunctie en juridische bewaring omvat, bewaren van postvakgegevens vanwege juridische procedure mogelijk is, en u een technisch sterke IT-afdeling hebt.
    
    Als u het postvak hebt omgezet in een 'inactief postvak', kunnen beheerders, compliance officers of recordbeheerders hulpprogramma's van In-Place eDiscovery in Exchange Online gebruiken om de inhoud te openen en te doorzoeken.
    
    Inactieve postvakken kunnen geen e-mail ontvangen en worden niet weergegeven in het gedeelde adresboek van uw organisatie of in andere lijsten.
    
    Zie [Inactieve postvakken beheren in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)voor meer informatie over het plaatsen van een blokkering in een postvak .
    
## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>E-mail van een voormalige werknemer doorsturen naar een andere werknemer of converteren naar een gedeeld postvak
<a name="bkmk_forward"> </a>

In deze stap wijst u het e-mailadres van de voormalige werknemer toe aan een andere werknemer of [converteert u het postvak van de gebruiker naar een gedeeld postvak](../email/convert-user-mailbox-to-shared-mailbox.md) dat u hebt gemaakt. 
  
- Het maken van een gedeeld postvak is goedkoper omdat u niet voor een licentie hoeft te betalen, **mits het postvak kleiner is dan 50 GB**. Boven de 50 GB moet u er een licentie voor toewijzen. 
    
- Als u het postvak converteert naar een gedeeld postvak, zijn ook alle oude e-mails beschikbaar. Deze kunnen veel ruimte in beslag nemen.
    
- Als u e-mail doorsturen hebt ingesteld, worden alleen  *nieuwe*  e-mails die naar de voormalige werknemer worden verzonden, nu naar de huidige werknemer gestuurd. 
    
- Voor het doorsturen van e-mail is vereist dat het account van de voormalige werknemer een licentie heeft.
    
 > [!IMPORTANT] 
 > Als u e-mail doorstuur of een gedeeld postvak instelt, verwijdert u aan het einde het account van de voormalige werknemer niet. Het account moet aanwezig zijn om het doorsturen van e-mail of het gedeelde postvak te bevestigen. 

::: moniker range="o365-worldwide"  

> [!NOTE]
> Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

2. Selecteer de naam van de werknemer die u wilt blokkeren en selecteer vervolgens het tabblad **E-mail.**

3. Selecteer **E-mail doorsturen onder E-mail doorsturen**de optie **E-mail doorsturen beheren**.

4. Schakel **Alle naar dit postvak verzonden e-mail doorsturen** in. Typ in het vak **Doorstuuradres** het e-mailadres van de huidige werknemer (of het gedeelde postvak) waarnaar de nieuwe e-mail wordt doorgestuurd. 
  
5. Kies **Opslaan**. 
    
6. Vergeet niet dat u het account van de voormalige werknemer dient te behouden.
 
::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.

2. Selecteer de werknemer die u wilt blokkeren en vouw **e-mailinstellingen**uit .

3. Selecteer naast **E-mail doorsturen**de optie **Bewerken**.

4. Schakel **Alle naar dit postvak verzonden e-mail doorsturen** in. Typ in het vak **Doorstuuradres** het e-mailadres van de huidige werknemer (of het gedeelde postvak) waarnaar de nieuwe e-mail wordt doorgestuurd. 
  
5. Kies **Opslaan**. 
    
6. Vergeet niet dat u het account van de voormalige werknemer dient te behouden.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.

2. Selecteer de werknemer die u wilt blokkeren en vouw **e-mailinstellingen**uit .

3. Selecteer naast **E-mail doorsturen**de optie **Bewerken**.

4. Schakel **Alle naar dit postvak verzonden e-mail doorsturen** in. Typ in het vak **Doorstuuradres** het e-mailadres van de huidige werknemer (of het gedeelde postvak) waarnaar de nieuwe e-mail wordt doorgestuurd. 
  
5. Kies **Opslaan**. 
    
6. Vergeet niet dat u het account van de voormalige werknemer dient te behouden.

::: moniker-end


    
## <a name="wipe-and-block-a-former-employees-mobile-device"></a>Het mobiele apparaat van een voormalige werknemer wissen en blokkeren
<a name="bkmk_mobile"> </a>

Als de voormalige werknemer een telefoon van de zaak had, kunt u deze via het Exchange-beheercentrum wissen en blokkeren om alle bedrijfsgegevens van het apparaat te verwijderen zodat het apparaat geen verbinding meer kan maken met Office 365.
  

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.

3. Ga in het Exchange-beheercentrum naar **Ontvangers** \> **Postvakken**. 
    
4. Selecteer de gebruiker en selecteer onder **Mobiele apparaten**de optie **Details weergeven**. 
    
5. Selecteer op de pagina **Details van mobiele apparaten** onder Mobiele **apparaten**het mobiele apparaat, selecteer Apparaat wissen van **gegevenswissen** ![ en selecteer Vervolgens ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) **Blokkeren**. 
    
6. Kies **Opslaan**. 
    
    **Tip**: zorg ervoor dat u de gebruiker geen toegang meer verleent tot uw on-premises Blackberry Enterprise Service. U moet ook alle Blackberry-apparaten voor de gebruiker uitschakelen. Raadpleeg de beheerhandleiding voor de Blackberry Business Cloud Services als u specifieke stappen moet uitvoeren voor het uitschakelen van de gebruiker. 
    
## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>De toegang van een voormalige werknemer tot Microsoft 365-gegevens blokkeren
<a name="bkmk_block"> </a>

 > [!IMPORTANT] 
 > Het blokkeren van een account kan tot 24 uur duren voordat deze van kracht wordt. Als u onmiddellijk de aanmeldingstoegang van een gebruiker moet voorkomen, moet u [het wachtwoord opnieuw instellen](reset-passwords.md) en vervolgens een eenmalige gebeurtenis starten die hen afmeldt bij Microsoft 365-sessies op alle apparaten. Zie [Meld je nu af!](#sign-out-now)
 

::: moniker range="o365-worldwide"

> [!NOTE]
> Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

2. Selecteer de naam van de werknemer die u wilt blokkeren en selecteer onder de naam van de gebruiker het symbool voor **Deze gebruiker blokkeren.**

3. Selecteer **De gebruiker blokkeren van aanmelden**en selecteer **Opslaan**. 

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.

2. Selecteer de werknemer die u wilt blokkeren en selecteer **Vervolgens Aanmelding blokkeren**.

3. Selecteer **De gebruiker blokkeren van aanmelden**en selecteer **Opslaan**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.

2. Selecteer de werknemer die u wilt blokkeren en selecteer **Vervolgens Aanmelding blokkeren**.

3. Selecteer **De gebruiker blokkeren van aanmelden**en selecteer **Opslaan**. 

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>De toegang van een voormalige werknemer tot e-mail (Exchange Online) blokkeren
<a name="bkmk_block_email"> </a>

Als u e-mail hebt als onderdeel van uw Microsoft 365-abonnement, moet u zich aanmelden bij het Exchange-beheercentrum om deze stappen te volgen om te voorkomen dat uw voormalige werknemer toegang krijgt tot zijn of haar e-mail.
  

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.
     
2. Ga in het Exchange-beheercentrum naar **Ontvangers** \> **Postvakken**. 
    
3. Dubbelklik op de gebruiker en ga naar de pagina **Postvakfuncties.** Schakel **onder Mobiele apparaten**Exchange **ActiveSync uit en** **OWA uitschakelen voor apparaten** in en antwoord op beide wanneer u **daarom** wordt gevraagd. 
    
4. Selecteer **Onder E-mailconnectiviteit**de optie **Ja uitschakelen** en beantwoorden wanneer daarom wordt gevraagd. **Yes** 
    
## <a name="remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>De Microsoft 365-licentie verwijderen en verwijderen van een voormalige werknemer
<a name="bkmk_remove"> </a>

U blijft dus niet betalen voor een licentie nadat iemand uw organisatie verlaat, u moet de Microsoft 365-licentie verwijderen en deze vervolgens uit uw abonnement verwijderen. Als u de licentie niet uit het abonnement verwijdert, kunt u deze aan een andere gebruiker toewijzen.
  
Als u de licentie verwijdert, worden alle gegevens van die gebruiker gedurende dertig dagen bewaard. U kunt de gegevens [openen](get-access-to-and-back-up-a-former-user-s-data.md) of het account [herstellen](restore-user.md) als de gebruiker terugkeert. Na 30 dagen worden alle gegevens van de gebruiker (behalve documenten die zijn opgeslagen in SharePoint Online) definitief verwijderd van Microsoft 365 en kunnen ze niet worden hersteld. 

::: moniker range="o365-worldwide"

> [!NOTE]
> Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

2. Selecteer de naam van de werknemer die u wilt blokkeren en selecteer vervolgens het tabblad **Licenties en apps.**

4. Schakel de selectievakjes voor de licentie(s) die u wilt verwijderen uit en selecteer **Wijzigingen opslaan**.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.

2. Selecteer de werknemer die u wilt blokkeren en **selecteer**vervolgens bewerken naast **Productlicenties**.

3. Schakel op de pagina **Productlicenties** de licentie(s) die u wilt verwijderen in en selecteer **Opslaan**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.

2. Selecteer de werknemer die u wilt blokkeren en **selecteer**vervolgens bewerken naast **Productlicenties**.

3. Schakel op de pagina **Productlicenties** de licentie(s) die u wilt verwijderen in en selecteer **Opslaan**.

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
    
2. Selecteer **Licenties toevoegen/verwijderen** om de licentie te verwijderen, zodat u er pas voor betaalt als u een andere persoon inhuurt.

Wanneer u een andere persoon aan uw bedrijf [toevoegt,](add-users.md) wordt u gevraagd om tegelijkertijd een licentie te kopen, met slechts één stap!
    
Zie [Licenties toewijzen aan gebruikers in Microsoft 365 voor Bedrijven](../manage/assign-licenses-to-users.md)en Licenties verwijderen van gebruikers in Microsoft 365 voor Bedrijven voor meer informatie over het beheren van gebruikerslicenties voor Microsoft [365 voor Bedrijven.](../manage/remove-licenses-from-users.md)
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>Invloed van een verwijderd werknemersaccount op Skype voor Bedrijven
<a name="bkmk_remove"> </a>

Als u een licentie uit Office 365 verwijdert, wordt het aan de gebruiker gekoppelde PSTN-nummer vrijgegeven. U kunt het toewijzen aan een andere gebruiker.
  
Als de gebruiker tot een wachtrijgroep behoort, is de gebruiker geen geldig doel meer van de oproepwachtrijagenten. Daarom raden we u aan de gebruiker ook te verwijderen uit de groepen die aan de oproepwachtrij zijn gekoppeld. 
  
## <a name="delete-a-former-employees-user-account"></a>Het gebruikersaccount van een voormalige werknemer verwijderen
<a name="bkmk_delete"> </a>

Nadat u de gegevens van de voormalige werknemer hebt opgeslagen en beschikbaar hebt gemaakt, kunt u het account van de werknemer verwijderen.
  
Verwijder het account niet als u doorsturen van e-mail hebt ingesteld of het account hebt omgezet naar een gedeeld postvak. Het account is nodig om het gedeelde postvak of het doorsturen van e-mail te kunnen blijven gebruiken.

::: moniker range="o365-worldwide"

> [!NOTE]
> Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

2. Selecteer de naam van de werknemer die u wilt verwijderen.

3. Selecteer onder de naam van de gebruiker het symbool voor **Gebruiker verwijderen**. Kies de gewenste opties voor deze gebruiker en selecteer **Vervolgens Gebruiker verwijderen**.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.

2. Selecteer de naam van de werknemer die u wilt verwijderen.

3. Selecteer gebruiker **verwijderen**boven aan de pagina . Kies de gewenste opties voor deze gebruiker en selecteer **Vervolgens Gebruiker verwijderen**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.

2. Selecteer de naam van de werknemer die u wilt verwijderen.

3. Selecteer gebruiker **verwijderen**boven aan de pagina . Kies de gewenste opties voor deze gebruiker en selecteer **Vervolgens Gebruiker verwijderen**.

::: moniker-end

Wanneer u een gebruiker verwijdert, wordt het account inactief gedurende ongeveer 30 dagen. Tot die tijd kunt u het account herstellen. Daarna worden de gegevens permanent verwijderd.
  
### <a name="does-your-organization-use-active-directory"></a>Maakt uw organisatie gebruik van Active Directory?

Als uw organisatie gebruikersaccounts synchroniseert met Microsoft 365 vanuit een lokale Active Directory-omgeving, moet u deze gebruikersaccounts in uw lokale Active Directory-service verwijderen en herstellen. U kunt ze niet verwijderen of herstellen via Office 365.
  
Lees voor instructies dit artikel: [Een gebruikersaccount verwijderen](https://go.microsoft.com/fwlink/?linkid=841808).
  
Als u Azure Active Directory gebruikt, raadpleegt u de PowerShell-cmdlet [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230). 
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>Wat u moet weten over het beëindigen van een sessie van een werknemer
<a name="bkmk_session"> </a>

Zo ontzegt u een werknemer de toegang tot e-mail (Exchange).
  
|||
|:-----|:-----|
|**Wat u kunt doen** <br/> |**Hoe u dat kunt doen** <br/> |
|Een sessie beëindigen (zoals voor de webversie van Outlook, Outlook, Exchange Active Sync, enzovoort) en een nieuwe sessie geforceerd openen  <br/> |Wachtwoord opnieuw instellen  <br/> |
|Een sessie beëindigen en toegang blokkeren voor toekomstige sessies (voor alle protocollen)  <br/> |Schakel het account uit. Bijvoorbeeld als volgt (in het Exchange-beheercentrum of via PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|De sessie voor een bepaald protocol (zoals ActiveSync) beëindigen  <br/> |Schakel het protocol uit. Bijvoorbeeld als volgt (in het Exchange-beheercentrum of via PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |
   
De bovenstaande bewerkingen kunnen op drie locaties worden uitgevoerd:
  
|||
|:-----|:-----|
|**Als u de sessie hier beëindigt** <br/> |**Hoe lang dit duurt** <br/> |
|In het Exchange-beheercentrum of via PowerShell  <br/> |Verwachte vertraging is korter dan 30 minuten  <br/> |
|In het Azure Active Directory-beheercentrum  <br/> |Verwachte vertraging is 60 minuten  <br/> |
|In een lokale omgeving  <br/> |Verwachte vertraging is 3 uur of langer  <br/> |
   
### <a name="how-to-get-fastest-response-for-account-termination"></a>Zo krijgt u de snelste reactie voor het beëindigen van een account

 **Snelst**: maak gebruik van het Exchange-beheercentrum (gebruik PowerShell) of van het Azure Active Directory-beheercentrum. In een on-premises omgeving kan het enkele uren duren om de wijziging via DirSync te synchroniseren. 
  
 **Snelst voor een gebruiker met aanwezigheid on-premises en in het Exchange-Datacenter**: Beëindig de sessie met behulp van het Azure Active Directory-beheercentrum/Exchange-beheercentrum, en breng de wijziging OOK aan in de on-premises omgeving. Anders worden de wijzigingen in het Azure Active Directory-beheercentrum/Exchange-beheercentrum overschreven door DirSync. 
  
## <a name="related-articles"></a>Verwante artikelen

[Een gebruiker herstellen](restore-user.md)
  
