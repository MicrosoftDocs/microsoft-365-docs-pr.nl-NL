---
title: Een gedeeld postvak maken
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: Maak gedeelde postvakken zodat meerdere personen binnen uw bedrijf de verantwoordelijkheid kunnen delen voor het lezen en beantwoorden van e-mails die naar hetzelfde adres zijn gestuurd.
ms.openlocfilehash: 331f5f320f9b57ee503734f57ed8d804e9ad04e3
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432287"
---
# <a name="create-a-shared-mailbox"></a>Een gedeeld postvak maken 

> [!NOTE]
> Als uw organisatie gebruikmaakt van een hybride Exchange-omgeving, moet u het on-premises Exchange-beheercentrum (EAC) gebruiken om gedeelde postvakken te maken en te beheren. [Gedeelde postvakken maken in het Exchange-beheercentrum](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)<br><br>
> Zie [Groepen vergelijken](../create-groups/compare-groups.md) als u niet zeker weet of u een gedeeld postvak of een Microsoft 365-groep voor Outlook moet maken. Momenteel is het niet mogelijk een gedeeld postvak te migreren naar een Microsoft 365-groep. Als dit iets is dat u zou willen, laat ons dat dan weten door [hier te stemmen](https://go.microsoft.com/fwlink/?linkid=871518).

It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.

Gedeelde postvakken hebben een gedeelde agenda. Veel kleine bedrijven vinden de gedeelde agenda handig omdat iedereen hier zijn afspraken kan invoeren. Als u bijvoorbeeld drie mensen hebt die klantbezoeken doen, kunnen zij allemaal de gedeelde agenda gebruiken om hun afspraken in te voeren. Dit is een handige manier om iedereen op de hoogte te houden van waar mensen zich bevinden.

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

## <a name="block-sign-in-for-the-shared-mailbox-account"></a>Aanmelding voor het account van het gedeelde postvak blokkeren

Elk gedeeld postvak heeft een bijbehorend gebruikersaccount. Is het u opgevallen dat u niet werd gevraagd een wachtwoord in te voeren toen u het gedeelde postvak maakte? Het account heeft een wachtwoord, maar dat wordt gegenereerd door het systeem (onbekend). Het is niet de bedoeling het account te gebruiken om u aan te melden in het gedeelde postvak.

En als de beheerder het wachtwoord van het gebruikersaccount van het gedeelde postvak opnieuw instelt? Of wat als een hacker zich toegang verschaft tot de referenties van het account van het gedeelde postvak? Hiermee zou het gebruikersaccount zich aan kunnen melden bij het gedeelde postvak en e-mail verzenden. Om dit te voorkomen, moet u de aanmelding voor het account die behoort bij het gedeelde postvak blokkeren.

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

2. Zoek het account voor het gedeelde postvak in de lijst met gebruikersaccounts (verander het filter bijvoorbeeld in **Gebruikers zonder licentie**).

3. Selecteer de gebruiker om het eigenschappenvenster te openen en selecteer dan het pictogram **Deze gebruiker blokkeren** ![Schermafbeelding van het pictogram Deze gebruiker blokkeren](../../media/block-user-icon.png).

   **Opmerking**: Als het account al wordt geblokkeerd, wordt er bovenaan **Geblokkeerd** weergegeven en staat er in het pictogram **De blokkering van deze gebruiker opheffen**.

4. Selecteer in het venster **Deze gebruiker blokkeren?**, **Voorkomen dat de gebruiker zich aanmeldt** en selecteer dan **Wijzigingen opslaan**.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.

2. Zoek het account voor het gedeelde postvak in de lijst met gebruikersaccounts (verander de weergave bijvoorbeeld in **Gebruikers zonder licentie**) en selecteer dan het account.

3. Selecteer in het eigenschappendeelvenster **Aanmelding blokkeren**.

    **Opmerking:** Als het account al is geblokkeerd, staat er op de knop **Blokkering opheffen**.

4. Controleer in het deelvenster **Aanmeldstatus bewerken** dat Voorkomen dat de gebruiker zich aanmeldt is geselecteerd, selecteer **Opslaan** en vervolgens **Sluiten**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.

2. Zoek het account voor het gedeelde postvak in de lijst met gebruikersaccounts (verander de weergave bijvoorbeeld in **Gebruikers zonder licentie**) en selecteer dan het account.

3. Selecteer in het eigenschappendeelvenster **Aanmelding blokkeren**.

    **Opmerking:** Als het account al is geblokkeerd, staat er op de knop **Blokkering opheffen**.

4. Controleer in het deelvenster **Aanmeldstatus bewerken** dat Voorkomen dat de gebruiker zich aanmeldt is geselecteerd, selecteer **Opslaan** en vervolgens **Sluiten**.
::: moniker-end

Zie [Gebruikersaccounts blokkeren met Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell) voor meer informatie over het blokkeren van accounts met Azure AD PowerShell (met inbegrip van meerdere accounts tegelijk).

## <a name="add-the-shared-mailbox-to-outlook"></a>Het gedeelde postvak toevoegen aan Outlook

Als u automatisch toewijzen voor uw bedrijf hebt ingeschakeld (iets wat de meeste mensen doen), wordt het gedeelde postvak automatisch weergegeven in de Outlook-app van uw gebruikers nadat ze Outlook hebben gesloten en opnieuw gestart. 

Automatisch toewijzen wordt ingesteld in het postvak van de gebruiker, niet het gedeelde postvak.   Dit betekent dat als u probeert een beveiligingsgroep te gebruiken om te beheren wie toegang heeft tot het gedeelde postvak, automatisch toewijzen niet werkt. Als u dus gebruik wilt maken van automatisch toewijzen, moet u de machtigingen expliciet toewijzen. Standaard is automatisch toewijzen ingeschakeld. Zie [Automatisch toewijzen verwijderen van een gedeeld postvak](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox) voor informatie over het uitschakelen.

Zie voor meer informatie over gedeelde postvakken maken in Outlook:

- <a href="https://support.office.com/article/d94a8e9e-21f1-4240-808b-de9c9c088afd.aspx" target="_blank">Een gedeeld postvak openen en gebruiken in Outlook</a>

- <a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Een gedeeld postvak toevoegen aan de webversie van Outlook</a>

- <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Een gedeeld postvak toevoegen aan Outlook Mobile</a>

- <a href="https://support.office.com/article/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2.aspx" target="_blank">Een gedeelde map of gedeeld postvak openen in Outlook voor Mac</a>

- <a href="https://support.office.com/article/b0963400-2a51-4c64-afc7-b816d737d164.aspx" target="_blank">Regels toevoegen aan een gedeeld postvak</a>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a>Een gedeeld postvak gebruiken op een mobiel apparaat (telefoon of tablet)

U kunt op twee manieren toegang krijgen tot een gedeeld postvak op een mobiel apparaat:
- Voeg het gedeelde postvak toe aan de <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">app Outlook voor iOS</a> of de <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">mobiele app voor Outlook voor Android</a>. 
    
    Zie <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Een gedeeld postvak toevoegen aan Outlook Mobile</a> voor instructies.

- Open uw browser, meld u aan en ga dan naar de webversie van Outlook. Vanuit de webversie van Outlook hebt u toegang tot het gedeelde postvak.

    Zie <a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Een gedeeld postvak toevoegen aan de webversie van Outlook</a> voor instructies.

## <a name="use-the-shared-calendar"></a>De gedeelde agenda gebruiken

Wanneer u een gedeeld postvak maakt, maakt u automatisch een gedeelde agenda. We gebruiken liever de agenda van het gedeelde Postvak dan een SharePoint-agenda voor het bijhouden van afspraken en waar personen zijn. Een gedeelde agenda is geïntegreerd met Outlook en is veel eenvoudiger te gebruiken dan een SharePoint-agenda.

1. In de Outlook-app gaat u naar de agendaweergave en selecteert u het gedeelde postvak.

2. Wanneer u afspraken invoert, zijn deze zichtbaar voor alle gebruikers die lid zijn van het gedeelde postvak. 

3. Een lid van het gedeelde postvak kan afspraken in de agenda aanmaken, weergeven en beheren, net zoals ze dat doen voor persoonlijke afspraken. Iedereen die lid is van het gedeelde postvak kan de wijzigingen zien in de gedeelde agenda.

## <a name="related-articles"></a>Verwante artikelen

[Meer over gedeelde postvakken](about-shared-mailboxes.md)

[Een gedeeld postvak configureren](configure-a-shared-mailbox.md)

[Een gebruikerspostvak converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md)

[Een licentie uit een gedeeld postvak verwijderen](remove-license-from-shared-mailbox.md)

[Problemen oplossen met gedeelde postvakken](resolve-issues-with-shared-mailboxes.md)





