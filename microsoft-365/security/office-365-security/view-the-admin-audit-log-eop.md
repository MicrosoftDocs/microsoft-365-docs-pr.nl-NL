---
title: Het auditlogboek van de beheerder bekijken in standalone EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Beheerders kunnen leren hoe u het auditlogboek van de beheerder kunt weergeven en doorzoeken op zelfstandige Exchange Online Protection (EOP).
ms.openlocfilehash: 171f3ec531b232ca796232ab26caefbee8afc75c
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653495"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>Het auditlogboek van de beheerder bekijken in standalone EOP

In zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken, kunt u de PowerShell-of zelfstandige EOP PowerShell gebruiken om vermeldingen te zoeken en te bekijken in het controlelogboek van de beheerder.

In het auditlogboek voor beheerders worden specifieke acties vastgelegd op basis van zelfstandige EOP PowerShell-cmdlets, die worden uitgevoerd door beheerders en gebruikers aan wie beheerdersbevoegdheden zijn toegewezen. Vermeldingen in het controlelogboek van de beheerder biedt informatie over de uitvoering van de cmdlet, de parameters die zijn gebruikt om de cmdlet uit te voeren en welke objecten werden beïnvloed.

> [!NOTE]
>
> - Logboekregistratie van beheerders is standaard ingeschakeld, en u kunt deze niet uitschakelen.
>
> - Het controlelogboek van de beheerder recordeert geen acties op basis van cmdlets die beginnen met de werkwoorden **Get**, **Search**of **test**.
>
> - Audit logboekvermeldingen worden gedurende 90 dagen bewaard. Wanneer een item ouder is dan 90 dagen, wordt dit verwijderd

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Om het Exchange-Beheercentrum te openen, raadpleegt u het [Exchange-Beheercentrum in zelfstandige EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. Specifiek hebt u de rol Auditlogboeken of alleen-lezen rollen nodig die zijn toegewezen aan de ComplianceManagement, de organizationmanagement (globale beheerders) en SecurityAdministrator rollen groepen. Zie voor meer informatie [machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en [Gebruik de lijst met wijzigingen in de lijst met leden van rollen groepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Zie toetscombinaties [voor het Exchange-Beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)voor informatie over toetscombinaties die van toepassing kunnen zijn op de procedures in dit onderwerp.

> [!TIP]
> Problemen? Vraag om hulp op het forum van [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>Het controlelogboek van de beheerder weergeven via het Exchange-beheer logboek

1. Ga in het Exchange-Beheercentrum naar **compliance** \> - **controle**en kies vervolgens **het controleverslag rapport van de beheerder uitvoeren**.

2. Kies een **begindatum** en **einddatum** in de pagina **rollen groepen zoeken naar beheerders** die worden geopend (het standaardbereik is de afgelopen twee weken) en kies vervolgens **zoeken**. Alle configuratie aangebrachte wijzigingen in de opgegeven periode worden weergegeven en kunnen worden gesorteerd met behulp van de volgende informatie:

   - **Datum**: de datum en tijd waarop de configuratiewijziging is aangebracht. De datum en tijd worden opgeslagen in de UTC-indeling (Coordinated Universal Time).

   - **Cmdlet**: de naam van de cmdlet die werd gebruikt om de configuratiewijziging te maken.

   - **Gebruiker**: de naam van het gebruikersaccount van de gebruiker die de configuratiewijziging heeft aangebracht.

     Maximaal 5000 vermeldingen worden op meerdere pagina's weergegeven. Geef een kleiner datumbereik op als u de resultaten wilt verfijnen. Als u een individueel zoekresultaat selecteert, worden de volgende aanvullende informatie weergegeven in het detailvenster:

   - **Object gewijzigd**: het object dat door de cmdlet is gewijzigd.

   - **Parameters (parameter: waarde)**: de cmdlet-parameters die zijn gebruikt, en elk van de waarden die u hebt opgegeven met de parameter.

3. Als u een bepaald auditlogboek wilt afdrukken, kiest u de knop **afdrukken** in het deelvenster Details.

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>Standalone EOP PowerShell gebruiken voor het weergeven van het auditlogboek voor beheerders

U kunt zelfstandige EOP PowerShell gebruiken om te zoeken naar controlelogboekvermeldingen die voldoen aan de criteria die u opgeeft. Gebruik de volgende syntaxis:

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**Opmerkingen**:

- U kunt de parameter _parameters_ alleen gebruiken in combinatie met de _cmdlets_ -parameter.

- Met de _ObjectIds_ -parameter wordt de resultaten gefilterd op het object dat door de cmdlet is gewijzigd. Een geldige waarde is afhankelijk van de manier waarop het object in het auditlogboek wordt weergegeven. Bijvoorbeeld:

  - Naam
  - Canonieke DN-naam (bijvoorbeeld contoso.com/Users/Akia al-Zuhairi)

  Waarschijnlijk moet u andere filterparameters voor deze cmdlet gebruiken om de resultaten te verfijnen en de typen objecten te bepalen waarin u bent geïnteresseerd.

- Met de parameter _UserID_ worden de resultaten gefilterd door de gebruiker die de wijziging heeft aangebracht (wie de cmdlet uitvoert).

- Als u een datum/tijd-waarde opgeeft zonder een tijdzone, wordt de waarde voor _begin_ datum en _eind_ datum geutc (Coordinated Universal Time). Gebruik een van de volgende opties als u een datum/tijdwaarde wilt opgeven voor deze parameter:

  - Geef de datum/tijdwaarde in UTC op: bijvoorbeeld: ' 2016-05-06 14:30:00Z '.

  - Geef een waarde op voor datum/tijd in de vorm van een formule waarmee de datum/tijd in de lokale tijdzone wordt geconverteerd naar UTC: bijvoorbeeld `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` . Zie [versneld](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date)voor meer informatie.

- De cmdlet retourneert standaard een maximum van 1.000 logboekvermeldingen. Gebruik de parameter _ResultSize_ om maximaal 250.000 logboekvermeldingen op te geven. Of gebruik de waarde `Unlimited` om alle items te retourneren.

In dit voorbeeld wordt een zoekopdracht uitgevoerd naar alle controlelogboekvermeldingen met de volgende criteria:

- **Begindatum**: 4 augustus 2019
- **Einddatum**: 3 oktober 2019
- **Cmdlets**: Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

Zie [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="view-details-of-audit-log-entries"></a>Details van controlelogboekvermeldingen weergeven

Met de cmdlet **Search-AdminAuditLog** worden de velden geretourneerd die worden beschreven in de sectie inhoud van het [audit logboek](#audit-log-contents) verderop in dit onderwerp. Van de velden die worden geretourneerd door de cmdlets, twee velden, **CmdletParameters** en **ModifiedProperties**, bevatten aanvullende informatie die standaard niet wordt weergegeven.

Voer de volgende stappen uit om de inhoud van de velden **CmdletParameters** en **ModifiedProperties** weer te geven.

1. Bepaal de criteria waarnaar u wilt zoeken, voer de **Search-AdminAuditLog-** cmdlet uit en sla de resultaten op in een variabele met behulp van de volgende opdracht.

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. Elk item in het auditlogboek wordt opgeslagen als een matrixelement in de variabele `$Results` . U kunt een matrixelement selecteren door de index van het matrixelement op te geven. Matrixelement indexen beginnen op nul (0) voor het eerste matrixelement. Als u bijvoorbeeld een vijfde matrixelement wilt ophalen met een index van 4, gebruikt u de volgende opdracht.

    ```PowerShell
    $Results[4]
    ```

3. Met de vorige opdracht wordt de logboekvermelding geretourneerd die is opgeslagen in het matrixelement 4. Ga als volgt te werk om de inhoud van de velden **CmdletParameters** en **ModifiedProperties** voor dit logboekitem te bekijken.

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. Als u de inhoud van de **CmdletParameters** -of **ModifiedParameters** -velden in een andere vermelding in het logboek wilt weergeven, wijzigt u de index van het matrixelement.

## <a name="audit-log-contents"></a>Inhoud van het controlelogboek

Elke vermelding in het auditlogboek bevat de informatie die in de volgende tabel wordt beschreven. Het auditlogboek bevat een of meer controlelogboekvermeldingen.

****

|Vult|Beschrijving|
|---|---|
|`RunspaceId`|Dit veld wordt intern gebruikt door EOP.|
|`ObjectModified`|Dit veld bevat het object dat door de cmdlet die is opgegeven in het `CmdletName` veld is gewijzigd.|
|`CmdletName`|Dit veld bevat de naam van de cmdlet die de gebruiker heeft uitgevoerd in het `Caller` veld.|
|`CmdletParameters`|Dit veld bevat de parameters die zijn opgegeven tijdens het uitvoeren van de cmdlet in het `CmdletName` veld. Ook opgeslagen in dit veld, maar niet zichtbaar in de standaarduitvoer, is de waarde die is opgegeven bij de parameter, indien van toepassing.|
|`ModifiedProperties`|Dit veld bevat de eigenschappen die zijn gewijzigd voor het object in het `ObjectModified` veld. Ook opgeslagen in dit veld, maar niet zichtbaar in de standaarduitvoer, zijn de oude waarde van de eigenschap en de nieuwe waarde die werd opgeslagen.|
|`Caller`|Dit veld bevat het gebruikersaccount van de gebruiker die de cmdlet heeft uitgevoerd in het `CmdletName` veld.|
|`ExternalAccess`|Dit veld wordt intern gebruikt door EOP.|
|`Succeeded`|In dit veld wordt aangegeven of de cmdlet in het `CmdletName` veld is uitgevoerd. De waarde is ofwel `True` of `False` .|
|`Error`|Dit veld bevat het foutbericht dat wordt gegenereerd als de cmdlet in het `CmdletName` veld kon niet worden voltooid.|
|`RunDate`|Dit veld bevat de datum en tijd waarop de cmdlet in het `CmdletName` veld is uitgevoerd. De datum en tijd worden opgeslagen in de UTC-indeling (Coordinated Universal Time).|
|`OriginatingServer`|In dit veld wordt de server aangegeven waarop de cmdlet die in het veld is opgegeven, wordt `CmdletName` uitgevoerd.|
|`ClientIP`|Dit veld wordt intern gebruikt door EOP.|
|`SessionId`|Dit veld wordt intern gebruikt door EOP.|
|`AppId`|Dit veld wordt intern gebruikt door EOP.|
|`ClientAppId`|Dit veld wordt intern gebruikt door EOP.|
|`Identity`|Dit veld wordt intern gebruikt door EOP.|
|`IsValid`|Dit veld wordt intern gebruikt door EOP.|
|`ObjectState`|Dit veld wordt intern gebruikt door EOP.|
|
