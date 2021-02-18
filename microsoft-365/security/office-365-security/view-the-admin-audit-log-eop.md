---
title: Het auditlogboek van de beheerder bekijken in standalone EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Beheerders kunnen informatie krijgen over het weergeven en doorzoeken van het auditlogboek voor beheerders in de zelfstandige Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab6bf0a2739a88a075b636b990539b24006f3e63
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286475"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>Het auditlogboek van de beheerder bekijken in standalone EOP

**Van toepassing op**
- [Zelfstandige versie van Exchange Online Protection](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken kunt u het Exchange-beheercentrum (EAC) of de zelfstandige EOP PowerShell gebruiken om vermeldingen te zoeken en weer te geven in het auditlogboek voor beheerders.

In het auditlogboek voor beheerders worden specifieke acties op basis van zelfstandige EOP PowerShell-cmdlets, uitgevoerd door beheerders en gebruikers aan wie beheerdersbevoegdheden zijn toegewezen. Vermeldingen in het auditlogboek voor beheerders bevatten informatie over welke cmdlet is uitgevoerd, welke parameters zijn gebruikt, wie de cmdlet heeft uitgevoerd en welke objecten zijn beïnvloed.

> [!NOTE]
>
> - Logboekregistratie door beheerders is standaard ingeschakeld en u kunt deze functie niet uitschakelen.
>
> - In het auditlogboek voor beheerders worden geen acties opgeslagen op basis van cmdlets die beginnen met de werkwoorden **Get,** **Search** of **Test.**
>
> - Vermeldingen in het auditlogboek worden 90 dagen bewaard. Wanneer een item ouder is dan 90 dagen, wordt het verwijderd

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Als u het Exchange-beheercentrum wilt openen, gaat u naar [het Exchange-beheercentrum in de zelfstandige EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet machtigingen toegewezen krijgen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren. U hebt met name de rol **Auditlogboeken** of Auditlogboeken voor alleen **weergeven**  nodig, die standaard zijn toegewezen aan de rollengroepen Organisatiebeheer, Compliancebeheer en Beveiligingsbeheerder. Zie Machtigingen in zelfstandige EOP en gebruik het [EAC](feature-permissions-in-eop.md) om de lijst met leden [in rollengroepen te wijzigen voor meer informatie.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Zie Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor informatie over [sneltoetsen](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)die van toepassing kunnen zijn op de procedures in dit artikel.

> [!TIP]
> Hebt u problemen? Vraag om hulp op het forum [van Exchange Online Protection.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>Het Exchange-beheercentrum gebruiken om het auditlogboek voor beheerders te bekijken

1. Ga in het Exchange-beheercentrum naar **Controle van** nalevingsbeheer en kies vervolgens Het auditlogboekrapport \> voor beheerders **uitvoeren.**

2. Kies op **de pagina** Zoeken naar wijzigingen in beheerdersrolgroepen die wordt geopend een **begin-** en einddatum **(het** standaardbereik is de afgelopen twee weken) en kies vervolgens **Zoeken.** Alle configuratiewijzigingen die zijn aangebracht in de opgegeven periode, worden weergegeven en kunnen worden gesorteerd op basis van de volgende informatie:

   - **Datum:** de datum en tijd waarop de configuratiewijziging is aangebracht. De datum en tijd worden opgeslagen in de indeling Coordinated Universal Time (UTC).

   - **Cmdlet:** de naam van de cmdlet die is gebruikt om de configuratie aan te brengen.

   - **Gebruiker:** de naam van het gebruikersaccount van de gebruiker die de configuratiewijziging heeft aangebracht.

     Er worden maximaal 5000 vermeldingen weergegeven op meerdere pagina's. Geef een kleiner datumbereik op als u de resultaten wilt beperken. Als u een afzonderlijk zoekresultaat selecteert, wordt de volgende aanvullende informatie weergegeven in het detailvenster:

   - **Object gewijzigd:** het object dat is gewijzigd door de cmdlet.

   - **Parameters (parameter:waarde)**: de cmdlet-parameters die zijn gebruikt, en elke waarde die is opgegeven met de parameter.

3. Als u een specifieke auditlogboekinvoer wilt afdrukken, kiest u **de knop Afdrukken** in het detailvenster.

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>Zelfstandige EOP PowerShell gebruiken om het auditlogboek voor beheerders te bekijken

U kunt zelfstandige EOP PowerShell gebruiken om te zoeken naar vermeldingen in het auditlogboek die voldoen aan de criteria die u opgeeft. Gebruik de volgende syntaxis:

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**Opmerkingen**:

- U kunt de parameter _Parameters alleen_ samen met de _cmdlets-parameter_ gebruiken.

- Met de parameter _ObjectIds_ worden de resultaten gefilterd op het object dat door de cmdlet is gewijzigd. Een geldige waarde is afhankelijk van de manier waarop het object wordt weergegeven in het auditlogboek. Bijvoorbeeld:

  - Naam
  - Canonieke distinguished name (bijvoorbeeld contoso.com/Users/Akia Al-Zuhairi)

  Waarschijnlijk moet u andere filterparameters voor deze cmdlet gebruiken om de resultaten te beperken en de typen objecten te identificeren waarin u geïnteresseerd bent.

- Met _de parameter UserIds_ worden de resultaten gefilterd door de gebruiker die de wijziging heeft aangebracht (die de cmdlet heeft gemaakt).

- Als u voor de _parameters_ _Begindatum_ en Einddatum een datum/tijd-waarde opgeeft zonder tijdzone, bevindt de waarde zich in Coordinated Universal Time (UTC). Als u een datum/tijd-waarde wilt opgeven voor deze parameter, gebruikt u een van de volgende opties:

  - Geef de datum/tijd-waarde in UTC op: bijvoorbeeld "2016-05-06 14:30:00z".

  - Geef de datum/tijd-waarde op als een formule die de datum/tijd in uw lokale tijdzone converteert naar UTC, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` bijvoorbeeld. Zie [Get-Date voor meer informatie.](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date)

- De cmdlet retourneert standaard maximaal 1000 logboekgegevens. Gebruik de _parameter ResultSize_ om maximaal 250.000 logboekgegevens op te geven. Of gebruik de waarde om `Unlimited` alle items te retourneren.

In dit voorbeeld wordt een zoekopdracht uitgevoerd naar alle vermeldingen in het auditlogboek met de volgende criteria:

- **Begindatum:** 4 augustus 2019
- **Einddatum:** 3 oktober 2019
- **Cmdlets:** Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

Zie [Search-AdminAuditLog voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)

### <a name="view-details-of-audit-log-entries"></a>Details van vermeldingen in het auditlogboek weergeven

De **cmdlet Search-AdminAuditLog** retourneert de velden die worden beschreven in de sectie [Auditlogboekinhoud](#audit-log-contents) verderop in dit artikel. Van de velden die worden geretourneerd door de cmdlet, bevatten twee velden, **CmdletParameters** en **ModifiedProperties,** aanvullende informatie die niet standaard wordt geretourneerd.

Als u de inhoud van de **velden CmdletParameters** en **ModifiedProperties** wilt weergeven, gebruikt u de volgende stappen.

1. Bepaal de criteria die u wilt zoeken, voer de cmdlet **Search-AdminAuditLog** uit en sla de resultaten op in een variabele met behulp van de volgende opdracht.

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. Elke vermelding in het auditlogboek wordt opgeslagen als een matrixelement in de `$Results` variabele. U kunt een matrixelement selecteren door de index van het matrixelement op te geven. Indexen van matrixelementen beginnen bij nul (0) voor het eerste matrixelement. Als u bijvoorbeeld het vijfde matrixelement wilt ophalen, dat een index van 4 bevat, gebruikt u de volgende opdracht.

    ```PowerShell
    $Results[4]
    ```

3. De vorige opdracht retourneert de logboekinvoer die is opgeslagen in matrixelement 4. Gebruik de volgende opdrachten om de inhoud van de velden **CmdletParameters** en **ModifiedProperties** voor deze logboekinvoer te bekijken.

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. Als u de inhoud van de **velden CmdletParameters** of **ModifiedParameters** wilt weergeven in een andere logboekinvoer, wijzigt u de index van het matrixelement.

## <a name="audit-log-contents"></a>Inhoud van auditlogboek

Elke vermelding in het auditlogboek bevat de gegevens die in de volgende tabel worden beschreven. Het auditlogboek bevat een of meer vermeldingen in het auditlogboek.

****

|Veld|Beschrijving|
|---|---|
|`RunspaceId`|Dit veld wordt intern gebruikt door EOP.|
|`ObjectModified`|Dit veld bevat het object dat is gewijzigd door de cmdlet die in het veld is `CmdletName` opgegeven.|
|`CmdletName`|Dit veld bevat de naam van de cmdlet die door de gebruiker in het veld is `Caller` uitgevoerd.|
|`CmdletParameters`|Dit veld bevat de parameters die zijn opgegeven toen de cmdlet in het `CmdletName` veld werd uitgevoerd. Ook in dit veld opgeslagen, maar niet zichtbaar in de standaarduitvoer, is de waarde die is opgegeven met de parameter, indien aanwezig.|
|`ModifiedProperties`|Dit veld bevat de eigenschappen die zijn gewijzigd voor het object in het `ObjectModified` veld. Ook opgeslagen in dit veld, maar niet zichtbaar in de standaarduitvoer, zijn de oude waarde van de eigenschap en de nieuwe waarde die is opgeslagen.|
|`Caller`|Dit veld bevat het gebruikersaccount van de gebruiker die de cmdlet heeft opgeslagen in het `CmdletName` veld.|
|`ExternalAccess`|Dit veld wordt intern gebruikt door EOP.|
|`Succeeded`|Dit veld geeft aan of de cmdlet in het `CmdletName` veld zonder succes is uitgevoerd. De waarde is `True` `False` ofwel.|
|`Error`|Dit veld bevat het foutbericht dat wordt gegenereerd als de cmdlet in het `CmdletName` veld niet kan worden voltooid.|
|`RunDate`|Dit veld bevat de datum en tijd waarop de cmdlet in het `CmdletName` veld is uitgevoerd. De datum en tijd worden opgeslagen in de indeling Coordinated Universal Time (UTC).|
|`OriginatingServer`|Dit veld geeft de server aan waarop de in het veld opgegeven cmdlet `CmdletName` is uitgevoerd.|
|`ClientIP`|Dit veld wordt intern gebruikt door EOP.|
|`SessionId`|Dit veld wordt intern gebruikt door EOP.|
|`AppId`|Dit veld wordt intern gebruikt door EOP.|
|`ClientAppId`|Dit veld wordt intern gebruikt door EOP.|
|`Identity`|Dit veld wordt intern gebruikt door EOP.|
|`IsValid`|Dit veld wordt intern gebruikt door EOP.|
|`ObjectState`|Dit veld wordt intern gebruikt door EOP.|
|
