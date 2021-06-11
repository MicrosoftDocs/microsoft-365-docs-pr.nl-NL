---
title: Items verwijderen in de map Herstelbare items van het cloudpostvak in de wacht
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: Lees hoe beheerders items kunnen verwijderen in de map Herstelbare items van een gebruiker voor een Exchange Online postvak, zelfs als dat postvak in juridische wacht wordt geplaatst.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 776113bcd6141c4f01c2da61f0bd71f99cffd3e2
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326640"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold"></a>Items verwijderen in de map Herstelbare items van postvakken in de cloud in de wacht

De map Herstelbare items voor een Exchange Online bestaat om te beschermen tegen onbedoelde of schadelijke verwijderingen. Het wordt ook gebruikt om items op te slaan die worden bewaard en toegankelijk zijn door compliancefuncties, zoals bewaar- en eDiscovery-zoekopdrachten. In sommige gevallen hebben organisaties echter gegevens die onbedoeld zijn bewaard in de map Herstelbare items die ze moeten verwijderen. Een gebruiker kan bijvoorbeeld onbewust een e-mailbericht verzenden of doorsturen dat gevoelige informatie of informatie bevat die ernstige zakelijke gevolgen kan hebben. Zelfs als het bericht permanent wordt verwijderd, kan het voor onbepaalde tijd worden bewaard omdat er een wettelijke wacht in het postvak is geplaatst. Dit scenario wordt *gegevensmortage genoemd* omdat gegevens onbedoeld zijn overgeslagen *in* Office 365. In deze situaties kunt u items verwijderen in de map Herstelbare items van een gebruiker voor een Exchange Online-postvak, zelfs als dat postvak in de wacht wordt geplaatst met een van de verschillende functies voor het vasthouden van Office 365. Deze typen bewaringen zijn onder andere Bewaringen voor rechtszaken, In-Place bewaringen, eDiscovery-bewaringen en bewaarbeleid dat is gemaakt in het beveiligings- en compliancecentrum in Office 365 of Microsoft 365.

In dit artikel wordt uitgelegd hoe beheerders items kunnen verwijderen uit de map Herstelbare items voor postvakken in de cloud die in de wacht staan. In deze procedure wordt de toegang tot het postvak uit te sluiten en herstel van één item uit te sluiten, de beheerde mapassistent uit te sluiten om het postvak te verwerken, tijdelijk de wacht te verwijderen, items uit de map Herstelbare items te verwijderen en het postvak vervolgens terug te zetten naar de vorige configuratie. Dit is het proces:
  
[Stap 1: Informatie over het postvak verzamelen](#step-1-collect-information-about-the-mailbox)

[Stap 2: Het postvak voorbereiden](#step-2-prepare-the-mailbox)

[Stap 3: Alle ophoudt uit het postvak verwijderen](#step-3-remove-all-holds-from-the-mailbox)

[Stap 4: De vertragingsvertraging uit het postvak verwijderen](#step-4-remove-the-delay-hold-from-the-mailbox)

[Stap 5: Items verwijderen in de map Herstelbare items](#step-5-delete-items-in-the-recoverable-items-folder)

[Stap 6: Het postvak terugdraaien naar de vorige status](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> De procedures die in dit artikel worden beschreven, leiden ertoe dat gegevens permanent worden verwijderd (verwijderd) uit een Exchange Online postvak. Dat betekent dat berichten die u uit de map Herstelbare items verwijdert, niet kunnen worden hersteld en niet beschikbaar zijn voor juridische detectie of andere nalevingsdoeleinden. Als u berichten wilt verwijderen uit een postvak dat in bewaring is geplaatst als onderdeel van een procesoverleg, In-Place Bewaring, eDiscovery-bewaring of bewaarbeleid dat is gemaakt in het beveiligings- en compliancecentrum, neemt u contact op met uw recordsbeheer of juridische afdelingen voordat u de bewaring verwijdert. Uw organisatie heeft mogelijk een beleid dat bepaalt of een postvak in de wacht staat of dat een incident met gegevensmortage prioriteit heeft.
  
## <a name="before-you-delete-items"></a>Voordat u items verwijdert

- Om inhoud te zoeken, moet u lid zijn van de rollengroep eDiscovery-beheerder of aan de beheerdersrol Compliance zoeken zijn toegewezen. Om berichten te verwijderen, moet u lid zijn van de rollengroep Organisatiebeheer of aan de rol Zoeken en opschonen zijn toegewezen. Zie [eDiscovery-machtigingen toewijzen in het Beveiligings- en compliancecentrum](./assign-ediscovery-permissions.md) voor informatie over het toevoegen van gebruikers aan een rollengroep.

- De procedure die in dit artikel wordt beschreven, wordt niet ondersteund voor inactieve postvakken. Dat komt omdat u een bewaring (of bewaarbeleid) niet opnieuw kunt gebruiken in een inactief postvak nadat u het hebt verwijderd. Wanneer u een greep uit een inactief postvak verwijdert, wordt het gewijzigd in een normaal, zacht verwijderd postvak en wordt het definitief verwijderd uit uw organisatie nadat het is verwerkt door de Assistent voor beheerde mappen.

- U kunt deze procedure niet uitvoeren voor een postvak dat is toegewezen bewaarinstellingen met een beleid dat is vergrendeld met Behoudsvergrendeling. Dit vergrendelingsblok voorkomt namelijk dat u het postvak verwijdert of uit het beleid sluit en dat u de assistent voor beheerde mappen in het postvak uit kunt sluiten. Zie Bewaringsvergrendeling gebruiken om wijzigingen in bewaarbeleid en bewaarlabelbeleid te beperken voor meer informatie over vergrendelingsbeleid [voor bewaring.](retention-preservation-lock.md)

- Als een postvak niet in de wacht wordt geplaatst (of als herstel van één item niet is ingeschakeld), kunt u de items verwijderen uit de map Herstelbare items. Zie E-mailberichten zoeken en verwijderen in uw organisatie voor meer informatie over hoe u dit [doet.](./search-for-and-delete-messages-in-your-organization.md)
  
## <a name="step-1-collect-information-about-the-mailbox"></a>Stap 1: Informatie over het postvak verzamelen

Deze eerste stap is het verzamelen van geselecteerde eigenschappen uit het doelpostvak die van invloed zijn op deze procedure. Schrijf deze instellingen op of sla ze op in een tekstbestand, omdat u een aantal van deze eigenschappen wijzigt en vervolgens terug gaat naar de oorspronkelijke waarden in stap 6, nadat u items uit de map Herstelbare items hebt verwijderd. Hier ziet u een lijst met de postvakeigenschappen die u moet verzamelen.
  
- *SingleItemRecoveryEnabled*  en  *RetainDeletedItemsFor*. Zo nodig schakelt u één herstel uit en verhoogt u de bewaarperiode voor verwijderde items in stap 3.

- *LitigationHoldEnabled*  en  *InPlaceHolds*. U moet alle in het postvak geplaatste items identificeren, zodat u deze tijdelijk kunt verwijderen in stap 3. Zie de [sectie Meer informatie](#more-information) voor tips over het identificeren van de type hold die mogelijk in een postvak wordt geplaatst.

Daarnaast moet u de toegangsinstellingen voor de postvakclient krijgen, zodat u deze tijdelijk kunt uitschakelen, zodat de eigenaar (of andere gebruikers) tijdens deze procedure geen toegang heeft tot het postvak. Ten slotte kunt u de huidige grootte en het huidige aantal items in de map Herstelbare items krijgen. Nadat u items in de map Herstelbare items in stap 5 hebt verwijderd, gebruikt u deze gegevens om te controleren of items zijn verwijderd.
  
1. [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Gebruik een gebruikersnaam en wachtwoord voor een beheerdersaccount dat is toegewezen aan de juiste beheerrollen in Exchange Online.

2. Voer de volgende opdracht uit om informatie te krijgen over het herstel van één item en de bewaarperiode van het verwijderde item.

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   Als herstel van één item is ingeschakeld, moet u dit uitschakelen in stap 2. Als de bewaarperiode van het verwijderde item niet is ingesteld voor 30 dagen (de maximumwaarde in Exchange Online), kunt u deze in stap 2 verhogen.

3. Voer de volgende opdracht uit om de postvaktoegangsinstellingen voor het postvak op te halen.

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   U schakelt al deze toegangsmethoden uit in stap 2.

4. Voer de volgende opdracht uit om informatie te krijgen over het bewaarbeleid dat is toegepast op het postvak.

    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```

    > [!TIP]
    > Als de eigenschap  *InPlaceHolds*  te veel waarden bevatten en niet alle waarden worden weergegeven, kunt u de opdracht uitvoeren om elke waarde op een afzonderlijke regel  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` weer te geven.
  
5. Voer de volgende opdracht uit om informatie te krijgen over bewaarbeleid voor de hele organisatie. 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```

   Als uw organisatie een bewaarbeleid voor de hele organisatie heeft, moet u het postvak uitsluiten van dit beleid in stap 3. Het kan tot 24 uur duren voordat de wijziging wordt gerepliceerd.

    > [!TIP]
    > Als de eigenschap  *InPlaceHolds*  te veel waarden bevatten en niet alle waarden worden weergegeven, kunt u de opdracht uitvoeren om elke waarde op een afzonderlijke regel  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` weer te geven. 
  
6. Voer de volgende opdracht uit om te bepalen of er een vertragingsvertraging wordt toegepast op het postvak.

   ```powershell
   Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
   ```

   Als de waarde van de eigenschap *DelayHoldApplied* of *DelayReleaseHoldApplied* is ingesteld op **Waar,** wordt een vertragingsgreep toegepast op het postvak en moet deze worden verwijderd. Zie Stap 4: De vertragingsvertraging uit het postvak verwijderen voor meer [informatie over vertragingsrederstanden.](#step-4-remove-the-delay-hold-from-the-mailbox)

   Als de waarde van een van de eigenschappen is ingesteld op **Onwaar,** wordt een vertragingsvertraging niet toegepast op het postvak en kunt u stap 4 overslaan.

7. Voer de volgende opdracht uit om de huidige grootte en het totale aantal items in mappen en submappen op te halen in de map Herstelbare items in het primaire postvak van de gebruiker.

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Als het archiefpostvak van de gebruiker is ingeschakeld, moet u de volgende opdracht uitvoeren om de grootte en het totale aantal items in mappen en submappen in de map Herstelbare items in het archiefpostvak op te halen. 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Wanneer u items verwijdert in stap 5, kunt u ervoor kiezen om items in de map Herstelbare items in het primaire archiefpostvak van de gebruiker al dan niet te verwijderen. Als archivering automatisch uitvijven is ingeschakeld voor het postvak, worden items in een postvak van het hulparchief niet verwijderd.
  
## <a name="step-2-prepare-the-mailbox"></a>Stap 2: Het postvak voorbereiden

Na het verzamelen en opslaan van informatie over het postvak, is de volgende stap het voorbereiden van het postvak door de volgende taken uit te voeren:
  
- **Schakel clienttoegang tot postvak** uit, zodat de eigenaar van het postvak geen toegang heeft tot zijn postvak en tijdens deze procedure wijzigingen aan de postvakgegevens kan aanbrengen.

- Verhoog de bewaarperiode voor verwijderde items tot 30 dagen (de maximumwaarde in Exchange Online), zodat items niet uit **de** map Herstelbare items worden verwijderd voordat u ze kunt verwijderen in stap 5.

- **Herstel van één item** uitschakelen, zodat items niet worden bewaard (voor de duur van de bewaarperiode van het verwijderde item) nadat u deze hebt verwijderd uit de map Herstelbare items in stap 5.

- **Schakel de assistent voor beheerde** mappen uit, zodat het postvak niet wordt verwerkt en de items die u verwijdert in stap 5 behouden blijft.

Voer de volgende stappen uit in Exchange Online PowerShell.
  
1. Voer de volgende opdracht uit om alle clienttoegang tot het postvak uit te schakelen. De syntaxis van de opdracht gaat ervan uit dat alle clienttoegangsmethoden zijn ingeschakeld in het postvak.

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

    > [!NOTE]
    > Het kan tot 60 minuten duren voordat alle clienttoegangsmethoden voor het postvak zijn uitgeschakeld. Houd er rekening mee dat het uitschakelen van deze toegangsmethoden de eigenaar van het postvak niet loskoppelt als deze momenteel is aangemeld. Als de eigenaar niet is aangemeld, hebben ze geen toegang meer tot hun postvak nadat deze toegangsmethoden zijn uitgeschakeld.
  
2. Voer de volgende opdracht uit om de bewaarperiode van het verwijderde item met maximaal 30 dagen te verhogen. Hiermee wordt ervan uitgenomen dat de huidige instelling kleiner is dan 30 dagen.

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. Voer de volgende opdracht uit om herstel van één item uit te schakelen.

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

    > [!NOTE]
    > Het kan tot 60 minuten duren voordat het herstel van één item is uitgeschakeld. Verwijder geen items in de map Herstelbare items totdat deze periode is verstreken. 
  
4. Voer de volgende opdracht uit om te voorkomen dat de beheerde mapassistent het postvak verwerkt. Zoals eerder uitgelegd, kunt u de assistent voor beheerde mappen alleen uitschakelen als er geen bewaarbeleid met een bewaringsvergrendeling wordt toegepast op het postvak. 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>Stap 3: Alle ophoudt uit het postvak verwijderen

De laatste stap voordat u items uit de map Herstelbare items kunt verwijderen, is alle in het postvak geplaatste items (die u hebt geïdentificeerd in stap 1) te verwijderen. Alle bewaarte items moeten worden verwijderd, zodat items niet worden bewaard nadat u ze uit de map Herstelbare items hebt verwijderd. De volgende secties bevatten informatie over het verwijderen van verschillende typen in een postvak. Zie de [sectie Meer informatie](#more-information) voor tips over het identificeren van de type hold die mogelijk in een postvak wordt geplaatst. Zie Het type wacht in een postvak Exchange Online [identificeren voor meer informatie.](identify-a-hold-on-an-exchange-online-mailbox.md)
  
> [!CAUTION]
> Neem contact op met uw recordsbeheer of juridische afdelingen voordat u een greep uit een postvak verwijdert. 
  
### <a name="litigation-hold"></a>Proces in de wacht zetten
  
Voer de volgende opdracht uit in Exchange Online PowerShell om een geschil in de wacht te zetten uit het postvak.

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

> [!NOTE]
> Net als bij het uitschakelen van de clienttoegangsmethoden en het herstel van één item, kan het tot 60 minuten duren voordat de procedure wordt verwijderd. Verwijder geen items uit de map Herstelbare items totdat deze periode is verstreken. 
  
### <a name="in-place-hold"></a>In-Place Hold
  
Voer de volgende opdracht uit in Exchange Online PowerShell om de In-Place te identificeren die in het postvak is geplaatst. Gebruik de GUID voor de In-Place Hold die u hebt geïdentificeerd in stap 1.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

Nadat u de In-Place Hold hebt gevonden, kunt u het Exchange-beheercentrum (EAC) of Exchange Online PowerShell gebruiken om het postvak uit de wacht te verwijderen. Zie Een In-Place [maken of verwijderen voor meer informatie.](/exchange/security-and-compliance/create-or-remove-in-place-holds)
  
### <a name="retention-policies-applied-to-specific-mailboxes"></a>Bewaarbeleid toegepast op specifieke postvakken
  
Voer de volgende opdracht uit in [Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell) om het bewaarbeleid te identificeren dat is toegepast op het postvak. Met deze opdracht worden ook alle Teams gespreksbewaringsbeleid dat op een postvak is toegepast, retourneerde. Gebruik de GUID (niet inclusief het of voorvoegsel) voor het bewaarbeleid dat `mbx` u hebt geïdentificeerd in stap `skp` 1.

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Nadat u het bewaarbeleid hebt geïdentificeerd, gaat u naar de pagina Bewaring van informatiebeheer in het  >   beveiligings- & compliancecentrum, bewerkt u het bewaarbeleid dat u hebt geïdentificeerd in de vorige stap en verwijdert u het postvak uit de lijst met geadresseerden die zijn opgenomen in het bewaarbeleid.
  
### <a name="organization-wide-retention-policies"></a>Bewaarbeleid voor de hele organisatie
  
Bewaarbeleid voor Exchange hele organisatie en Teams voor de hele organisatie worden toegepast op elk postvak in de organisatie. Ze worden toegepast op organisatieniveau (niet op postvakniveau) en worden geretourneerd wanneer u de **cmdlet Get-OrganizationConfig** in stap 1 uit runt. Voer de volgende opdracht uit in [Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell) om het bewaarbeleid voor de hele organisatie te identificeren. Gebruik de GUID (exclusief het voorvoegsel) voor het bewaarbeleid voor de hele organisatie dat u  `mbx` hebt geïdentificeerd in stap 1.

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Nadat u het bewaarbeleid voor de hele organisatie hebt geïdentificeerd, gaat u naar de pagina Bewaring van informatiebeheer in het Compliancecentrum voor beveiliging &, bewerkt u elk bewaarbeleid voor de hele organisatie dat u hebt geïdentificeerd in de vorige stap en voegt u het postvak toe aan de lijst met uitgesloten  >   geadresseerden. Als u dit doet, wordt het postvak van de gebruiker verwijderd uit het bewaarbeleid. Het kan tot 24 uur duren voordat de wijziging wordt gerepliceerd.

### <a name="retention-labels"></a>Retentielabels

Wanneer een gebruiker een label gebruikt dat is geconfigureerd om inhoud te behouden of te behouden en vervolgens inhoud te verwijderen naar een map of item in het postvak, is de eigenschap *ComplianceTagHoldApplied-postvak* ingesteld op **Waar.** Wanneer dit gebeurt, wordt het postvak beschouwd als in bewaring, alsof het is geplaatst in de bewaring van rechtszaken of is toegewezen aan een bewaarbeleid.

Als u de waarde van de eigenschap *ComplianceTagHoldApplied* wilt weergeven, moet u de volgende opdracht uitvoeren in Exchange Online PowerShell:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Nadat u hebt vastgesteld dat een postvak in bewaring staat omdat een bewaarlabel is toegepast op een map of item, kunt u het hulpprogramma Inhoud zoeken in het beveiligings- en compliancecentrum gebruiken om te zoeken naar gelabelde items met behulp van de zoekvoorwaarde ComplianceTag. Zie de sectie 'Zoekvoorwaarden' in [Trefwoordenquery's](keyword-queries-and-search-conditions.md#conditions-for-common-properties)en zoekvoorwaarden voor Zoeken naar inhoud voor meer informatie.

Zie Meer informatie over bewaarbeleid en bewaarlabels voor meer informatie over [etiketten.](retention.md)

### <a name="ediscovery-holds"></a>eDiscovery-bewaring
  
Voer de volgende opdrachten uit in [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) om de wacht te identificeren die is gekoppeld aan een *eDiscovery-zaak (eDiscovery-bevat)* die is toegepast op het postvak. Gebruik de GUID (exclusief het  `UniH` voorvoegsel) voor de eDiscovery-hold die u hebt geïdentificeerd in stap 1. In de tweede opdracht wordt de naam weergegeven van de eDiscovery-zaak aan de wachtlijst; met de derde opdracht wordt de naam van de wacht in de wacht gezet.
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

Nadat u de naam van de eDiscovery-zaak en de wacht hebt geïdentificeerd, gaat u naar de **eDiscovery** \> **eDiscovery-pagina** in het compliancecentrum, opent u de zaak en verwijdert u het postvak uit de wacht. Zie de sectie 'eDiscovery holds' in How to identify the type of hold placed on an Exchange Online mailbox (eDiscovery holds) voor meer informatie over het identificeren van eDiscovery-in- en [wachtvakken.](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>Stap 4: De vertragingsvertraging uit het postvak verwijderen

Nadat een type wachtstand uit een postvak is verwijderd, is de waarde van de eigenschap *DelayHoldApplied* of *DelayReleaseHoldApplied* ingesteld op **Waar.** Dit gebeurt de volgende keer dat de assistent voor beheerde mappen het postvak verwerkt en detecteert dat een wachtpost is verwijderd. Dit wordt  een vertragingsophoud genoemd en betekent dat de feitelijke verwijdering van de wachtstand 30 dagen wordt uitgesteld om te voorkomen dat gegevens definitief uit het postvak worden verwijderd. (Het doel van een vertragings hold is om beheerders de mogelijkheid te geven postvakitems te zoeken of te herstellen die worden verwijderd nadat een wachtstand is verwijderd.)  Wanneer een vertragingsvertraging in het postvak wordt geplaatst, wordt het postvak nog steeds beschouwd als in de wachtstand voor een onbeperkte duur, alsof het postvak in de wachtstand staat. Na 30 dagen verloopt de vertragingstermijn en Microsoft 365 probeert automatisch de vertragingstermijn te verwijderen (door de eigenschap *DelayHoldApplied* of *DelayReleaseHoldApplied* in te stellen op **Onwaar)** zodat de wachtstand wordt verwijderd. Zie de sectie Postvakken beheren bij vertragingsvertraging voor meer informatie over een vertragingsvertraging in Het type wachtstand in een postvak Exchange Online [identificeren.](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)

Als de waarde van de eigenschap *DelayHoldApplied* of *DelayReleaseHoldApplied* is ingesteld op **Waar,** voert u een van de volgende opdrachten uit om de vertragingsgreep te verwijderen:

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

Of

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

U moet de rol Legal Hold in Exchange Online toegewezen krijgen om de parameter *RemoveDelayHoldApplied* of *RemoveDelayReleaseHoldApplied te* gebruiken.

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>Stap 5: Items verwijderen in de map Herstelbare items

U kunt nu items in de map Herstelbare items verwijderen met de cmdlets [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) en [New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) in Security & Compliance Center PowerShell.

Als u wilt zoeken naar items die zich in de map Herstelbare items bevinden, raden we u aan een gerichte verzameling *uit te voeren.* Dit betekent dat u het bereik van uw zoekopdracht alleen beperkt tot items in de map Herstelbare items. U kunt dit doen door het script uit te voeren in [het artikel Inhoud zoeken gebruiken voor gerichte verzamelingen.](use-content-search-for-targeted-collections.md) Dit script retourneert de waarde van de eigenschap Map-id voor alle submappen in de map Herstelbare items van het doel. Vervolgens gebruikt u de map-id in een zoekquery om items in die map te retourneren.

Hier is een overzicht van het proces voor het zoeken naar en verwijderen van items in de map Herstelbare items van een gebruiker:

1. Voer het doelverzamelingsscript uit dat de map-ed's retourneert voor alle mappen in het postvak van de doelgebruiker. Het script maakt verbinding met Exchange Online PowerShell en & PowerShell in dezelfde PowerShell-sessie. Zie Het script uitvoeren voor een lijst met [mappen voor een postvak voor meer informatie.](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site)

2. Kopieer de map-eds voor alle submappen in de map Herstelbare items. U kunt ook de uitvoer van het script omleiden naar een tekstbestand.

   Hier ziet u een lijst en beschrijving van de submappen in de map Herstelbare items waar u items uit kunt zoeken en verwijderen:

   - **Verwijderingen:** bevat items waarvan de bewaarperiode voor verwijderde items niet is verlopen. Gebruikers kunnen snel verwijderde items uit deze submap herstellen met behulp van het hulpprogramma Verwijderde items herstellen in Outlook.

   - **Purges**: Bevat hard-verwijderde items waarvan de bewaarperiode van het verwijderde item is verlopen. Gebruikers kunnen items ook hard verwijderen door items uit de map Herstelbare items te verwijderen. Als het postvak in de wacht staat, blijven hard verwijderde items behouden. Deze submap is niet zichtbaar voor eindgebruikers.

   - **DiscoveryHolds:** bevat hard verwijderde items die zijn bewaard door een eDiscovery-bewaring of een bewaarbeleid. Deze submap is niet zichtbaar voor eindgebruikers.

   - **SubstraatHolds:** bevat hard verwijderde items uit Teams en andere cloud-apps die zijn bewaard door een bewaarbeleid of een ander type bewaring. Deze submap is niet zichtbaar voor eindgebruikers.

3. Gebruik de cmdlet **New-ComplianceSearch** (in Security & Compliance Center PowerShell) of gebruik het zoekprogramma Inhoud in het compliancecentrum om een inhoudszoekactie te maken die items retourneert uit de map Herstelbare items van de doelgebruiker. U kunt dit doen door mapid op te geven in de zoekquery voor alle submappen die u wilt zoeken. De volgende query retourneert bijvoorbeeld alle berichten in de submappen Purges en eDiscoveryHolds:

   ```text
   folderid:<folder ID of Purges subfolder> OR folderid:<folder ID of DiscoveryHolds subfolder>
   ```

   Zie Een map-id gebruiken of een gerichte verzameling uitvoeren voor meer informatie en voorbeelden over het uitvoeren van inhoudszoekingen die de eigenschap Map-id [gebruiken.](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection)

   > [!NOTE]
   > Als u de cmdlet **New-ComplianceSearch** gebruikt om in de map Herstelbare items te zoeken, moet u de cmdlet **Start-ComplianceSearch** gebruiken om de zoekopdracht uit te voeren.

4. Nadat u een inhoudszoekactie hebt gemaakt en hebt gevalideerd dat deze de items retourneert die u wilt verwijderen, gebruikt u de opdracht `New-ComplianceSearchAction -Purge -PurgeType HardDelete` (in Security & Compliance Center PowerShell) om de items die zijn geretourneerd door de inhoudszoekactie die u in de vorige stap hebt gemaakt, definitief te verwijderen. U kunt bijvoorbeeld een opdracht uitvoeren die lijkt op de volgende opdracht:

   ```powershell
   New-ComplianceSearchAction -SearchName "RecoverableItems" -Purge -PurgeType HardDelete
   ```

5. Er worden maximaal 10 items per postvak verwijderd wanneer u de vorige opdracht uit te voeren. Dit betekent dat u de opdracht mogelijk meerdere keren moet uitvoeren om alle items te verwijderen die u wilt verwijderen in de map `New-ComplianceSearchAction -Purge` Herstelbare items. Als u extra items wilt verwijderen, moet u eerst de vorige actie voor nalevingszoekactie verwijderen. U doet dit door de `Remove-ComplianceSearchAction` cmdlet uit te lopen. Als u bijvoorbeeld de verwijderactie wilt verwijderen die in de vorige stap is uitgevoerd, moet u de volgende opdracht uitvoeren:

   ```powershell
   Remove-ComplianceSearchAction "RecoverableItems_Purge"
   ```

   Nadat u dit hebt doen, kunt u een nieuwe actie voor nalevingszoekactie maken om meer items te verwijderen. U moet elke verwijderactie verwijderen voordat u een nieuwe actie maakt.

   Als u een lijst met de zoekacties voor naleving wilt krijgen, kunt u de `Get-ComplianceSearchAction` cmdlet uitvoeren. Purgeacties worden geïdentificeerd door `_Purge` aan de zoeknaam te worden toegevoegd.

### <a name="verify-that-items-were-deleted"></a>Controleren of items zijn verwijderd

Als u wilt controleren of u items hebt verwijderd uit de map Herstelbare items van een postvak, gebruikt u de cmdlet **Get-MailboxFolderStatistics** in Exchange Online PowerShell om de grootte en het aantal items in de map Herstelbare items te controleren. U kunt deze statistieken vergelijken met de statistieken die u hebt verzameld in stap 1.
  
Voer de volgende opdracht uit om de huidige grootte en het totale aantal items in mappen en submappen op te halen in de map Herstelbare items in het primaire postvak van de gebruiker.
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

Voer de volgende opdracht uit om de grootte en het totale aantal items in mappen en submappen in de map Herstelbare items in het archiefpostvak van de gebruiker op te halen.

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>Stap 6: Het postvak terugdraaien naar de vorige status

De laatste stap is om het postvak terug te zetten naar de vorige configuratie. Dit betekent dat u de eigenschappen die u hebt gewijzigd in stap 2, opnieuw in moet zetten en dat u de in stap 3 verwijderde ophoudt. Dit zijn:
  
- De bewaarperiode van het verwijderde item weer wijzigen in de vorige waarde. U kunt deze set ook laten zitten op 30 dagen, de maximumwaarde in Exchange Online.

- Herstel van één item opnieuw inschakelen.

- De toegangsmethoden voor de client opnieuw inschakelen, zodat de eigenaar toegang heeft tot zijn postvak.

- Het bewaarbeleid dat u hebt verwijderd opnieuw toe te passen.

- U kunt de assistent voor beheerde mappen opnieuw inschakelen om het postvak te verwerken.

> [!IMPORTANT]
> U wordt aangeraden 24 uur na het opnieuw toepassen van een bewarings- of bewaarbeleid te wachten (en te controleren of dit is gebeurd) voordat u de assistent voor beheerde mappen opnieuw inschakelen om het postvak te verwerken.
  
Voer de volgende stappen uit (in de opgegeven volgorde) in Exchange Online PowerShell.
  
1. Voer de volgende opdracht uit om de bewaarperiode van het verwijderde item weer te wijzigen in de oorspronkelijke waarde. Hiermee wordt ervan uitgenomen dat de vorige instelling minder dan 30 dagen is. bijvoorbeeld 14 dagen.

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. Voer de volgende opdracht uit om herstel van één item opnieuw in te stellen.

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. Voer de volgende opdracht uit om alle methoden voor clienttoegang opnieuw in te stellen voor het postvak.

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. U kunt de ruimten die u in stap 3 hebt verwijderd, opnieuw gebruiken. Gebruik een van de volgende procedures, afhankelijk van het type wacht.

    **Proces in de wacht zetten**

    Voer de volgende opdracht uit om een procedure voor het postvak opnieuw in te stellen.

    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **In-Place Hold**

    Gebruik de EAC (of Exchange Online PowerShell) om het postvak weer toe te voegen aan de In-Place Hold.

    **Bewaarbeleid toegepast op specifieke postvakken**

    Gebruik het Beveiligings- & compliancecentrum om het postvak weer toe te voegen aan het bewaarbeleid. Ga naar de pagina **Bewaring** van informatiebeheer in het  >   Beveiligings- & Compliancecentrum, bewerk het bewaarbeleid en voeg het postvak weer toe aan de lijst met geadresseerden waar het bewaarbeleid op is toegepast.

    **Bewaarbeleid voor de hele organisatie**

    Als u een bewaarbeleid voor de hele organisatie of Exchange hebt verwijderd door het beleid uit te sluiten, gebruikt u het Beveiligings- & Compliancecentrum om het postvak te verwijderen uit de lijst met uitgesloten gebruikers. Ga naar de **pagina Informatiebeheerretentie** in het Compliancecentrum voor beveiliging &, bewerk het bewaarbeleid voor de hele organisatie en verwijder het postvak uit de lijst met uitgesloten  >   geadresseerden. Als u dit doet, wordt het bewaarbeleid opnieuw gebruikt voor het postvak van de gebruiker.

    **eDiscovery case holds**

    Gebruik het Beveiligings- & compliancecentrum om het postvak weer toe te voegen aan de wacht die is gekoppeld aan een eDiscovery-zaak. Ga naar de **eDiscovery**  >  **eDiscovery-pagina,** open de zaak en voeg het postvak weer toe aan de wacht. 

5. Voer de volgende opdracht uit om de assistent voor beheerde mappen toe te staan het postvak opnieuw te verwerken. Zoals eerder is aangegeven, raden we u aan 24 uur te wachten nadat u een bewarings- of bewaarbeleid opnieuw hebt gebruikt (en te controleren of dit is gebeurd) voordat u de assistent voor beheerde mappen opnieuw inschakelen.

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. Als u wilt controleren of het postvak weer is teruggevormd naar de vorige configuratie, kunt u de volgende opdrachten uitvoeren en vervolgens de instellingen vergelijken met de instellingen die u hebt verzameld in stap 1.

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a>Meer informatie

Hier ziet u een tabel waarin wordt beschreven hoe u verschillende typen inhoudplaatsen kunt identificeren op basis van de waarden in de eigenschap  *InPlaceHolds*  wanneer u de **cmdlets Get-Mailbox** of **Get-OrganizationConfig** uitwerkt. Zie Het type wacht in een postvak Exchange Online [voor meer informatie.](identify-a-hold-on-an-exchange-online-mailbox.md)

Zoals eerder is uitgelegd, moet u alle bewaar- en bewaarbeleidsregels uit een postvak verwijderen voordat u items in de map Herstelbare items kunt verwijderen.
  
| Type wacht houden | Voorbeeldwaarde | De wacht houden identificeren |
|:-----|:-----|:-----|
|Proces in de wacht zetten  <br/> | `True` <br/> |De  *eigenschap LitigationHoldEnabled*  is ingesteld op  `True` .  <br/> |
|In-Place Hold  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |De  *eigenschap InPlaceHolds*  bevat de GUID van de In-Place Hold die in het postvak is geplaatst. U kunt zien dat dit een In-Place Is omdat de GUID niet begint met een voorvoegsel.  <br/> U kunt de opdracht in Exchange Online PowerShell gebruiken om informatie te krijgen over `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` de In-Place in het postvak.  <br/> |
| Bewaarbeleid in het beveiligingsbeleid & compliancecentrum toegepast op specifieke postvakken  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> of  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |Wanneer u de **cmdlet Get-Mailbox** uitwerkt, bevat de eigenschap  *InPlaceHolds*  ook GUID's van bewaarbeleid dat is toegepast op het postvak. U kunt bewaarbeleid identificeren omdat de GUID begint met het  `mbx` voorvoegsel. Als de GUID van het bewaarbeleid begint met het voorvoegsel, betekent dit dat het bewaarbeleid wordt toegepast op `skp` Skype voor Bedrijven gesprekken.  <br/> Als u het bewaarbeleid wilt identiteiten dat is toegepast op het postvak, moet u de volgende opdracht uitvoeren in Security & Compliance Center PowerShell: <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Verwijder het voorvoegsel  `mbx` of  `skp` het voorvoegsel wanneer u deze opdracht uit te voeren.  <br/> |
|Bewaarbeleid voor de hele organisatie in het beveiligings- & compliancecentrum  <br/> |Geen waarde  <br/> of  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696` (geeft aan dat het postvak is uitgesloten van een beleid voor de hele organisatie)  <br/> |Zelfs als  *de eigenschap InPlaceHolds*  leeg is wanneer u de **cmdlet Get-Mailbox** uitwerkt, is er mogelijk nog steeds een of meer bewaarbeleid voor de hele organisatie toegepast op het postvak.  <br/> Als u dit wilt controleren, kunt u de opdracht uitvoeren in Exchange Online PowerShell om een lijst te krijgen met de GUID's voor bewaarbeleid voor de hele `Get-OrganizationConfig | FL InPlaceHolds` organisatie. Het GUID voor bewaarbeleid voor de hele organisatie dat is toegepast op Exchange postvakken begint met het `mbx` voorvoegsel, bijvoorbeeld `mbxa3056bb15562480fadb46ce523ff7b02` .  <br/> Als u het bewaarbeleid voor de hele organisatie wilt identiteiten dat is toegepast op het postvak, moet u de volgende opdracht uitvoeren in Security & Compliance Center PowerShell: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Als een postvak is uitgesloten van een bewaarbeleid voor de hele organisatie, wordt de GUID voor het bewaarbeleid weergegeven in de eigenschap  *InPlaceHolds*  van het postvak van de gebruiker wanneer u de **cmdlet Get-Mailbox** uitwerkt. het wordt geïdentificeerd door het voorvoegsel,  `-mbx` bijvoorbeeld  `-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|eDiscovery case hold in the Security & Compliance Center  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |De  *eigenschap InPlaceHolds*  bevat ook de GUID van een hold die is gekoppeld aan een eDiscovery-zaak in het beveiligings- & compliancecentrum dat mogelijk in het postvak wordt geplaatst. U kunt zien dat dit een eDiscovery-zaak is, omdat de GUID begint met het  `UniH` voorvoegsel.  <br/> U kunt de cmdlet in Security & Compliance Center PowerShell gebruiken om informatie te krijgen over de eDiscovery-zaak waar de wacht in het postvak aan  `Get-CaseHoldPolicy` is gekoppeld. U kunt bijvoorbeeld de opdracht uitvoeren om de naam weer te geven van de case hold die  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` in het postvak staat. Zorg ervoor dat u het  `UniH` voorvoegsel verwijdert wanneer u deze opdracht uit te voeren.  <br/><br/> Voer de volgende opdrachten uit als u de eDiscovery-zaak wilt identiteiten waar de wacht in het postvak aan is gekoppeld:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`
