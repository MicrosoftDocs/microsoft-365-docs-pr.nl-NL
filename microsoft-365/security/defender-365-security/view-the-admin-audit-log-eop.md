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
description: Beheerders kunnen leren hoe ze het auditlogboek van de beheerder kunnen bekijken en doorzoeken in de zelfstandige Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5ed1d1eb121c06e6f5727e8782ba1d8bc8d23a99
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057714"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>Het auditlogboek van de beheerder bekijken in standalone EOP

**Van toepassing op**
- [Zelfstandige Exchange Online Protection](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken kunt u het Exchange-beheercentrum (EAC) of zelfstandige EOP PowerShell gebruiken om items in het beheerdersauditlogboek te zoeken en weer te geven.

Het auditlogboek van de beheerder registreert specifieke acties, op basis van zelfstandige EOP PowerShell-cmdlets, uitgevoerd door beheerders en gebruikers aan wie beheerdersbevoegdheden zijn toegewezen. Items in het auditlogboek van de beheerder geven u informatie over welke cmdlet is uitgevoerd, welke parameters zijn gebruikt, wie de cmdlet heeft uitgevoerd en welke objecten zijn beïnvloed.

> [!NOTE]
>
> - Logboekregistratie voor beheerdersaudits is standaard ingeschakeld en u kunt deze niet uitschakelen.
>
> - In het auditlogboek van de beheerder worden geen acties opgeslagen op basis van cmdlets die beginnen met de werkwoorden **Get,** **Search** of **Test.**
>
> - Controlelogboekgegevens worden 90 dagen bewaard. Wanneer een item ouder is dan 90 dagen, wordt het verwijderd

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie Exchange-beheercentrum in zelfstandige EOP om het Exchange-beheercentrum [te openen.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet machtigingen krijgen toegewezen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren. U hebt met name de rol  **Auditlogboeken** of **Alleen-weergeven auditlogboeken** nodig, die standaard zijn toegewezen aan de rollengroepen Organisatiebeheer, **Compliancebeheer** en Beveiligingsbeheerder.  Zie Machtigingen in zelfstandige [EOP](feature-permissions-in-eop.md) en Gebruik de EAC om de lijst met [leden in rollengroepen te wijzigen voor meer informatie.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Zie Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in [dit artikel.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Hebt u problemen? Vraag om hulp in het [Exchange Online Protection-forum.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>Het EAC gebruiken om het auditlogboek van de beheerder te bekijken

1. Ga in het EAC naar **Compliance management** \> **Auditing** en kies **vervolgens Het auditlogboekrapport voor** beheerders uitvoeren.

2. Kies **op de** pagina Zoeken naar wijzigingen in beheerdersrolgroepen die wordt geopend een **Begindatum** en Einddatum **(het** standaardbereik is de afgelopen twee weken) en kies **vervolgens Zoeken**. Alle configuratiewijzigingen die tijdens de opgegeven periode zijn aangebracht, worden weergegeven en kunnen worden gesorteerd aan de hand van de volgende gegevens:

   - **Datum:** De datum en tijd waarop de configuratiewijziging is aangebracht. De datum en tijd worden opgeslagen in de UTC-indeling (Coordinated Universal Time).

   - **Cmdlet:** de naam van de cmdlet die is gebruikt om de configuratie te wijzigen.

   - **Gebruiker:** De naam van het gebruikersaccount van de gebruiker die de configuratie heeft gewijzigd.

     Er worden maximaal 5000 items weergegeven op meerdere pagina's. Geef een kleiner datumbereik op als u de resultaten wilt beperken. Als u een afzonderlijk zoekresultaat selecteert, worden de volgende aanvullende gegevens weergegeven in het detailvenster:

   - **Object gewijzigd:** het object dat is gewijzigd door de cmdlet.

   - **Parameters (parameter:waarde)**: de gebruikte cmdletparameters en elke waarde die met de parameter is opgegeven.

3. Als u een specifiek auditlogboek wilt afdrukken, kiest u de knop **Afdrukken** in het detailvenster.

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>Zelfstandige EOP PowerShell gebruiken om het auditlogboek van de beheerder weer te geven

U kunt zelfstandige EOP PowerShell gebruiken om te zoeken naar controlelogboekgegevens die voldoen aan de criteria die u opgeeft. Gebruik de volgende syntaxis:

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**Opmerkingen**:

- U kunt de parameter _Parameters alleen_ samen met de _parameter Cmdlets_ gebruiken.

- Met _de parameter ObjectIds_ worden de resultaten gefilterd op het object dat door de cmdlet is gewijzigd. Een geldige waarde is afhankelijk van de manier waarop het object wordt weergegeven in het auditlogboek. Bijvoorbeeld:

  - Naam
  - Canonieke naam (bijvoorbeeld contoso.com/Users/Akia Al-Zuhairi)

  U moet waarschijnlijk andere filterparameters op deze cmdlet gebruiken om de resultaten te beperken en de typen objecten te identificeren waarin u geïnteresseerd bent.

- Met _de parameter UserIds_ worden de resultaten gefilterd door de gebruiker die de wijziging heeft aangebracht (die de cmdlet heeft gebruikt).

- Als u voor  _de parameters Begindatum_ en Einddatum een datum-/tijdwaarde zonder tijdzone opgeeft, bevindt de waarde zich in Gecoördineerde universele tijd (UTC). Als u een datum-/tijdwaarde voor deze parameter wilt opgeven, gebruikt u een van de volgende opties:

  - Geef de datum-/tijdwaarde op in UTC: bijvoorbeeld '2016-05-06 14:30:00z'.

  - Geef de datum-/tijdwaarde op als een formule die de datum/tijd in uw lokale tijdzone converteert naar UTC: `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` Bijvoorbeeld. Zie [Get-Date](/powershell/module/microsoft.powershell.utility/get-date)voor meer informatie.

- De cmdlet retourneert standaard maximaal 1.000 logboekgegevens. Gebruik de _parameter ResultSize_ om maximaal 250.000 logboekgegevens op te geven. Of gebruik de waarde om `Unlimited` alle items te retourneren.

In dit voorbeeld wordt een zoekopdracht uitgevoerd naar alle controlelogboekgegevens met de volgende criteria:

- **Begindatum**: 4 augustus 2019
- **Einddatum**: 3 oktober 2019
- **Cmdlets**: Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

Zie [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="view-details-of-audit-log-entries"></a>Details van controlelogboekgegevens weergeven

De **cmdlet Search-AdminAuditLog** retourneert de velden die worden beschreven in de sectie [Auditlog-inhoud](#audit-log-contents) verderop in dit artikel. Van de velden die door de cmdlet worden geretourneerd, bevatten twee velden, **CmdletParameters** en **ModifiedProperties,** aanvullende informatie die niet standaard wordt geretourneerd.

Als u de inhoud van de **velden CmdletParameters** en **ModifiedProperties** wilt weergeven, gebruikt u de volgende stappen.

1. Bepaal de criteria die u wilt zoeken, voer de cmdlet **Search-AdminAuditLog** uit en sla de resultaten op in een variabele met de volgende opdracht.

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. Elke auditlogboekinvoer wordt opgeslagen als een matrixelement in de variabele `$Results` . U kunt een matrixelement selecteren door de matrixelementindex op te geven. Matrixelementindexen beginnen bij nul (0) voor het eerste matrixelement. Als u bijvoorbeeld het 5e matrixelement wilt ophalen met een index van 4, gebruikt u de volgende opdracht.

    ```PowerShell
    $Results[4]
    ```

3. De vorige opdracht retourneert de logboekinvoer die is opgeslagen in matrixelement 4. Als u de inhoud van de **velden CmdletParameters** en **ModifiedProperties** voor deze logboekinvoer wilt zien, gebruikt u de volgende opdrachten.

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. Als u de inhoud van de **velden CmdletParameters** of **ModifiedParameters** wilt weergeven in een andere logboekinvoer, wijzigt u de matrixelementindex.

## <a name="audit-log-contents"></a>Inhoud van auditlogboek

Elke auditlogboekinvoer bevat de informatie die in de volgende tabel wordt beschreven. Het auditlogboek bevat een of meer auditlogboekgegevens.

****

|Veld|Beschrijving|
|---|---|
|`RunspaceId`|Dit veld wordt intern gebruikt door EOP.|
|`ObjectModified`|Dit veld bevat het object dat is gewijzigd door de cmdlet die in het veld is `CmdletName` opgegeven.|
|`CmdletName`|Dit veld bevat de naam van de cmdlet die door de gebruiker in het veld is `Caller` uitgevoerd.|
|`CmdletParameters`|Dit veld bevat de parameters die zijn opgegeven toen de cmdlet in het `CmdletName` veld werd uitgevoerd. Ook opgeslagen in dit veld, maar niet zichtbaar in de standaarduitvoer, is de waarde die is opgegeven met de parameter, indien aanwezig.|
|`ModifiedProperties`|Dit veld bevat de eigenschappen die zijn gewijzigd voor het object in het `ObjectModified` veld. Ook opgeslagen in dit veld, maar niet zichtbaar in de standaarduitvoer, zijn de oude waarde van de eigenschap en de nieuwe waarde die is opgeslagen.|
|`Caller`|Dit veld bevat het gebruikersaccount van de gebruiker die de cmdlet in het veld `CmdletName` heeft gelopen.|
|`ExternalAccess`|Dit veld wordt intern gebruikt door EOP.|
|`Succeeded`|In dit veld wordt aangegeven of de cmdlet in het `CmdletName` veld is uitgevoerd. De waarde is ofwel `True` `False` .|
|`Error`|Dit veld bevat het foutbericht dat is gegenereerd als de cmdlet in het `CmdletName` veld niet is voltooid.|
|`RunDate`|Dit veld bevat de datum en tijd waarop de cmdlet in `CmdletName` het veld is uitgevoerd. De datum en tijd worden opgeslagen in de UTC-indeling (Coordinated Universal Time).|
|`OriginatingServer`|Dit veld geeft de server aan waarop de in het veld opgegeven cmdlet `CmdletName` is uitgevoerd.|
|`ClientIP`|Dit veld wordt intern gebruikt door EOP.|
|`SessionId`|Dit veld wordt intern gebruikt door EOP.|
|`AppId`|Dit veld wordt intern gebruikt door EOP.|
|`ClientAppId`|Dit veld wordt intern gebruikt door EOP.|
|`Identity`|Dit veld wordt intern gebruikt door EOP.|
|`IsValid`|Dit veld wordt intern gebruikt door EOP.|
|`ObjectState`|Dit veld wordt intern gebruikt door EOP.|
|