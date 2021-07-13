---
title: Een gedeeld postvak maken
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: Maak gedeelde postvakken zodat meerdere personen binnen uw bedrijf de verantwoordelijkheid kunnen delen voor het lezen en beantwoorden van e-mails die naar hetzelfde adres zijn gestuurd.
ms.openlocfilehash: 6fff7b1eaa73944bc4dd744046ad97ee9d2379b1
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393185"
---
# <a name="create-a-shared-mailbox"></a>Een gedeeld postvak maken 

> [!NOTE]
> Als uw organisatie gebruikmaakt van een hybride Exchange-omgeving, moet u het on-premises Exchange-beheercentrum (EAC) gebruiken om gedeelde postvakken te maken en te beheren. [Gedeelde postvakken maken in het Exchange-beheercentrum](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)<br><br>
> Zie [Groepen vergelijken](../create-groups/compare-groups.md) als u niet zeker weet of u een gedeeld postvak of een Microsoft 365-groep voor Outlook moet maken. Momenteel is het niet mogelijk een gedeeld postvak te migreren naar een Microsoft 365-groep. Als dit iets is dat u zou willen, laat ons dat dan weten door [hier te stemmen](https://go.microsoft.com/fwlink/?linkid=871518).

Het is eenvoudig om gedeelde postvakken te maken zodat een groep e-mail kan controleren en verzenden vanaf een gemeenschappelijk e-mailadres zoals info@contoso.com. Wanneer een persoon in de groep een bericht beantwoordt dat naar het gedeelde postvak is verzonden, lijkt het e-mailbericht afkomstig te zijn van het gedeelde postvak, niet van de afzonderlijke gebruiker.

In gedeelde postvakken is een gedeelde agenda opgenomen. Veel kleine bedrijven vinden de gedeelde agenda handig omdat iedereen hier zijn afspraken kan invoeren. Als u bijvoorbeeld drie mensen hebt die klantbezoeken doen, kunnen zij allemaal de gedeelde agenda gebruiken om hun afspraken in te voeren. Dit is een handige manier om iedereen op de hoogte te houden van waar mensen zich bevinden.

Lees eerst [Meer informatie over gedeelde postvakken](about-shared-mailboxes.md) voordat u een gedeeld postvak maakt.

## <a name="create-a-shared-mailbox-and-add-members"></a>Een gedeeld postvak maken en leden toevoegen
  
1. Meld u aan met een globaal beheerdersaccount of Exchange-beheerder-account. Als het u het bericht ‘**U bent niet gemachtigd om deze pagina weer te geven of deze handeling uit te voeren**’ krijgt, dan bent u geen beheerder. 

::: moniker range="o365-worldwide"

2. Ga in het beheercentrum naar de pagina **Groepen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Gedeelde postvakken</a>.

::: moniker-end

::: moniker range="o365-germany"

2. Ga in het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=848041) naar de pagina **Groepen** \> **Gedeelde postvakken**.

::: moniker-end

::: moniker range="o365-21vianet"

2. Ga in het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=850627) naar de pagina **Groepen** \> **Gedeelde postvakken**.

::: moniker-end
    
3. Selecteer op de pagina **Gedeelde postvakken**, **+Een postvak toevoegen**. Voer een naam in voor het gedeelde postvak. De wizard kiest vervolgens het e-mailadres, dat u echter kunt bewerken.
    
    ![Geef het gedeelde Postvak een naam.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. Kies **Toevoegen**. Het kan enkele minuten duren voordat u leden kunt toevoegen.

5. Selecteer onder **Volgende stappen**, **Leden toevoegen aan dit postvak**. Leden zijn degenen die de inkomende e-mail voor dit gedeelde postvak en de uitgaande antwoorden kunnen weergeven.

   ![Leden toevoegen, selecteren](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. Selecteer de knop **+Leden toevoegen**. Schakel het selectievakje in naast de personen die dit gedeelde postvak mogen gebruiken en selecteer **Opslaan**.

   ![Leden toevoegen aan het gedeeld postvak](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. Selecteer **Sluiten**.

U hebt een gedeeld postvak en een gedeelde agenda. Ga nu naar de volgende stap: Aanmelding voor het account van het gedeelde postvak blokkeren.

## <a name="which-permissions-should-you-use"></a>Welke machtiging moet je gebruiken?

Je kunt de volgende machtigingen gebruiken met een gedeeld postvak:

- **Volledige toegang**: Met de machtiging Volledige toegang kan een gebruiker zich aanmelden bij het gedeelde postvak en optreden als de eigenaar van dat postvak. Nadat een gebruiker het gedeelde postvak heeft geopend, kan hij agenda-items maken, taken en contactpersonen voor de agenda maken en e-mailberichten lezen, weergeven, verwijderen en wijzigen. Gebruikers met de machtiging Volledige toegang kunnen echter geen e-mail verzenden vanuit het gedeelde postvak tenzij ze ook de machtiging Verzenden als of Verzenden namens hebben.

- **Verzenden als**: Met de machtiging Verzenden als kan een gebruiker e-mailberichten vanuit het gedeelde postvak onder een andere naam verzenden. Als bijvoorbeeld Flip Schoonen zich aanmeldt bij het gedeelde postvak Afdeling Marketing en een e-mailbericht verzendt, ziet dit eruit alsof de Afdeling Marketing het e-mailbericht heeft verzonden.

- **Verzenden namens**: Met de machtiging Verzenden namens kan een gebruiker e-mailberichten verzenden namens het gedeelde postvak. Als bijvoorbeeld Ger zich aanmeldt bij het gedeelde postvak Ontvangstgebouw 32 en een e-mailbericht verzendt, ziet dit eruit alsof het e-mailbericht is verzonden door 'Ger namens Ontvangstgebouw 32'. Je kunt het Exchange-beheercentrum niet gebruiken om de machtiging Verzenden namens te verlenen. Daarvoor moet je de **Set-Mailbox**-cmdlet met de parameter _GrantSendonBehalf_ gebruiken.

### <a name="use-the-eac-to-edit-shared-mailbox-delegation"></a>Het Exchange-beheercentrum gebruiken om het delegeren voor het gedeelde postvak te bewerken

1. Ga in het Exchange-beheercentrum naar **Ontvangers** \> **Gedeeld**. Selecteer het gedeelde postvak en vervolgens **Bewerken** ![Pictogram bewerken](../../media/ITPro-EAC-EditIcon.png).

2. Klik op **Postvakdelegering**.

3. Als je de machtiging Volledige toegang of Verzenden als wilt instellen of verwijderen, klik je op **Toevoegen** ![Pictogram Toevoegen](../../media/ITPro-EAC-AddIcon.png) of **Verwijderen** ![Pictogram Verwijderen](../../media/ITPro-EAC-RemoveIcon.gif) en selecteer je de gewenste gebruikers.

   > [!NOTE]
   > Met de machtiging Volledige toegang kan een gebruiker het postvak openen en daarin items maken en wijzigen. Met de machtiging Verzenden als kan ieder andere gebruiker dan de eigenaar van het postvak e-mail vanuit dit gedeelde postvak verzenden. Beide machtigingen zijn vereist om het gedeelde postvak goed te kunnen gebruiken.

4. Selecteer **Opslaan** om de wijzigingen op te slaan.


## <a name="block-sign-in-for-the-shared-mailbox-account"></a>Aanmelding voor het account van het gedeelde postvak blokkeren

Elk gedeeld postvak heeft een bijbehorend gebruikersaccount. Is het u opgevallen dat u niet werd gevraagd een wachtwoord in te voeren toen u het gedeelde postvak maakte? Het account heeft een wachtwoord, maar dat wordt gegenereerd door het systeem (onbekend). Het is niet de bedoeling het account te gebruiken om u aan te melden in het gedeelde postvak.

En als de beheerder het wachtwoord van het gebruikersaccount van het gedeelde postvak opnieuw instelt? Of wat als een hacker zich toegang verschaft tot de referenties van het account van het gedeelde postvak? Hiermee zou het gebruikersaccount zich aan kunnen melden bij het gedeelde postvak en e-mail verzenden. Om dit te voorkomen, moet u de aanmelding voor het account die behoort bij het gedeelde postvak blokkeren.

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.
::: moniker-end

1. Zoek het account voor het gedeelde postvak in de lijst met gebruikersaccounts (verander het filter bijvoorbeeld in **Gebruikers zonder licentie**).

1. Selecteer de gebruiker om het eigenschappenvenster te openen en selecteer dan het pictogram **Deze gebruiker blokkeren** ![Schermafbeelding van het pictogram Deze gebruiker blokkeren](../../media/block-user-icon.png).

   **Opmerking**: Als het account al wordt geblokkeerd, wordt er bovenaan **Geblokkeerd** weergegeven en staat er in het pictogram **De blokkering van deze gebruiker opheffen**.

1. Selecteer in het venster **Deze gebruiker blokkeren?**, **Voorkomen dat de gebruiker zich aanmeldt** en selecteer dan **Wijzigingen opslaan**.

Zie [Gebruikersaccounts blokkeren met Office 365 PowerShell](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md) voor meer informatie over het blokkeren van accounts met Azure AD PowerShell (met inbegrip van meerdere accounts tegelijk).

## <a name="add-the-shared-mailbox-to-outlook"></a>Het gedeelde postvak toevoegen aan Outlook

Als u automatisch toewijzen voor uw bedrijf hebt ingeschakeld (iets wat de meeste mensen doen), wordt het gedeelde postvak automatisch weergegeven in de Outlook-app van uw gebruikers nadat ze Outlook hebben gesloten en opnieuw gestart. 

Automatisch toewijzen wordt ingesteld in het postvak van de gebruiker, niet het gedeelde postvak.   Dit betekent dat als u probeert een beveiligingsgroep te gebruiken om te beheren wie toegang heeft tot het gedeelde postvak, automatisch toewijzen niet werkt. Als u dus gebruik wilt maken van automatisch toewijzen, moet u de machtigingen expliciet toewijzen. Standaard is automatisch toewijzen ingeschakeld. Zie [Automatisch toewijzen verwijderen van een gedeeld postvak](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox) voor informatie over het uitschakelen.

Zie voor meer informatie over gedeelde postvakken maken in Outlook:

- <a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Een gedeeld postvak openen en gebruiken in Outlook</a>

- <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Een gedeeld postvak toevoegen aan de webversie van Outlook</a>

- <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Een gedeeld postvak toevoegen aan Outlook Mobile</a>

- <a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Een gedeelde map of gedeeld postvak openen in Outlook voor Mac</a>

- <a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Regels toevoegen aan een gedeeld postvak</a>

## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a>Een gedeeld postvak gebruiken op een mobiel apparaat (telefoon of tablet)

U kunt op twee manieren toegang krijgen tot een gedeeld postvak op een mobiel apparaat:
- Voeg het gedeelde postvak toe aan de <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">app Outlook voor iOS</a> of de <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">mobiele app voor Outlook voor Android</a>. 
    
    Zie <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Een gedeeld postvak toevoegen aan Outlook Mobile</a> voor instructies.

- Open uw browser, meld u aan en ga dan naar de webversie van Outlook. Vanuit de webversie van Outlook hebt u toegang tot het gedeelde postvak.

    Zie <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Een gedeeld postvak toevoegen aan de webversie van Outlook</a> voor instructies.
    
> [!NOTE]
> Het gedeelde postvak kan alleen worden toegevoegd aan de app Outlook voor iOS of de mobiele Outlook voor Android-app.

## <a name="use-the-shared-calendar"></a>De gedeelde agenda gebruiken

We gebruiken liever de agenda van het gedeelde Postvak dan een SharePoint-agenda voor het bijhouden van afspraken en waar personen zijn. Een gedeelde agenda is geïntegreerd met Outlook, u ontvangt herinneringen en de gedeelde agenda is veel eenvoudiger te maken en te gebruiken dan een SharePoint-agenda.

1. In de Outlook-app gaat u naar de agendaweergave en selecteert u het gedeelde postvak.

2. Wanneer u afspraken invoert, zijn deze zichtbaar voor alle gebruikers die lid zijn van het gedeelde postvak. 

3. Een lid van het gedeelde postvak kan afspraken in de agenda aanmaken, weergeven en beheren, net zoals ze dat doen voor persoonlijke afspraken. Iedereen die lid is van het gedeelde postvak kan de wijzigingen zien in de gedeelde agenda.

## <a name="related-content"></a>Verwante inhoud

[Info over gedeelde postvakken](about-shared-mailboxes.md) (artikel)\
[Een gedeeld postvak configureren](configure-a-shared-mailbox.md) (artikel)\
[Het postvak van een gebruiker converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md) (artikel)\
[Een licentie uit een gedeeld postvak verwijderen](remove-license-from-shared-mailbox.md) (artikel)\
[Problemen oplossen met gedeelde postvakken](resolve-issues-with-shared-mailboxes.md) (artikel)