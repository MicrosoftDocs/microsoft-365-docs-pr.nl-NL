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
description: Beheerders kunnen leren hoe ze het logboek van de beheerderscontrole kunnen bekijken en doorzoeken in standalone Exchange Online Protection (EOP).
ms.openlocfilehash: e8c12f622c4dc382b11d03424e45c33e3afe3cbf
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613322"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>Het auditlogboek van de beheerder bekijken in standalone EOP

In zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken u het Exchange-beheercentrum (EAC) of de zelfstandige EOP PowerShell gebruiken om items in het beheerderscontrolelogboek te zoeken en weer te geven.

Het beheerderscontrolelogboek registreert specifieke acties, gebaseerd op zelfstandige EOP PowerShell-cmdlets, uitgevoerd door beheerders en gebruikers die beheerdersrechten hebben gekregen. Vermeldingen in het controlelogboek voor beheerders geven u informatie over welke cmdlet is uitgevoerd, welke parameters zijn gebruikt, wie de cmdlet heeft uitgevoerd en welke objecten zijn beïnvloed.

> [!NOTE]
> <ul><li>Logboekregistratie voor beheerderscontrole is standaard ingeschakeld en u deze niet uitschakelen.</li><li>Het controlelogboek van de beheerder registreert geen acties op basis van cmdlets die beginnen met de werkwoorden **Get,** **Search**of **Test**.</li><li>Controlelogboekgegevens worden 90 dagen bewaard. Wanneer een item ouder is dan 90 dagen, wordt het verwijderd</li></ul>

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie [Exchange-beheercentrum in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md)als u het Exchange-beheercentrum wilt openen.

- Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. U hebt specifiek de rol Auditlogboeken of Controlelogboeken alleen weergeven nodig, die standaard zijn toegewezen aan de rolgroepen ComplianceManagement, OrganizationManagement (global admins) en SecurityAdministrator. Zie [Machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en Gebruik de EAC voor meer informatie [de lijst met leden in rolgroepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)wijzigen.

- Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.

> [!TIP]
> Heb je problemen? Vraag om hulp in het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>De EAC gebruiken om het controlelogboek voor beheerders te bekijken

1. Ga in de EAC naar **Compliance management** \> **Auditing**en kies **vervolgens Het controlelogboek uitvoeren**van de beheerder .

2. Kies in de pagina Zoeken naar wijzigingen in de pagina **beheerdersrolgroepen** die wordt geopend een **begindatum** en **einddatum** (het standaardbereik is de afgelopen twee weken) en kies **Zoeken**. Alle configuratiewijzigingen die tijdens de opgegeven periode zijn aangebracht, worden weergegeven en kunnen worden gesorteerd met behulp van de volgende informatie:

   - **Datum**: de datum en tijd waarop de configuratiewijziging is aangebracht. De datum en tijd worden opgeslagen in de indeling Coordinated Universal Time (UTC).

   - **Cmdlet**: De naam van de cmdlet die werd gebruikt om de configuratie te wijzigen.

   - **Gebruiker**: De naam van het gebruikersaccount van de gebruiker die de configuratiewijziging heeft aangebracht.

     Op meerdere pagina's worden maximaal 5000 inzendingen weergegeven. Geef een kleiner datumbereik op als u uw resultaten wilt beperken. Als u een individueel zoekresultaat selecteert, wordt de volgende aanvullende informatie weergegeven in het detailvenster:

   - **Object gewijzigd**: het object dat is gewijzigd door de cmdlet.

   - **Parameters (parameter:waarde)**: de gebruikte cmdletparameters en de waarde die is opgegeven met de parameter.

3. Als u een specifiek controlelogboekbericht wilt afdrukken, kiest u de knop **Afdrukken** in het detailvenster.

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>Zelfstandige EOP PowerShell gebruiken om het controlelogboek van de beheerder weer te geven

U standalone EOP PowerShell gebruiken om te zoeken naar controlelogboekvermeldingen die voldoen aan de criteria die u opgeeft. Gebruik de volgende syntaxis:

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**Opmerkingen**:

- U de parameter _Parameters_ alleen gebruiken samen met de parameter _Cmdlets._

- De parameter _ObjectIds filtert_ de resultaten op het object dat is gewijzigd door de cmdlet. Een geldige waarde is afhankelijk van de manier waarop het object wordt weergegeven in het controlelogboek. Bijvoorbeeld:

  - Name
  - Canonieke voorname naam (bijvoorbeeld contoso.com/Users/Akia Al-Zuhairi)

  U zult waarschijnlijk andere filterparameters op deze cmdlet moeten gebruiken om de resultaten te beperken en de typen objecten te identificeren waarin u geïnteresseerd bent.

- De parameter _UserIds filtert_ de resultaten door de gebruiker die de wijziging heeft aangebracht (wie de cmdlet heeft uitgevoerd).

- Als u voor de parameters _StartDate_ en _EndDate_ een datum-/tijdwaarde opgeeft zonder tijdzone, staat de waarde in Gecoördineerde Universele Tijd (UTC). Als u een datum-/tijdwaarde voor deze parameter wilt opgeven, gebruikt u een van de volgende opties:

  - Geef de datum/tijdwaarde op in UTC: Bijvoorbeeld '2016-05-06 14:30:00z'.

  - Geef de datum-/tijdwaarde op als een formule die de datum/tijd in uw lokale tijdzone omzet in UTC: bijvoorbeeld `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` . Zie [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date)voor meer informatie.

- De cmdlet retourneert standaard maximaal 1.000 logboekvermeldingen. Gebruik de parameter _ResultSize_ om maximaal 250.000 logboekvermeldingen op te geven. Of gebruik de waarde `Unlimited` om alle vermeldingen terug te sturen.

In dit voorbeeld wordt gezocht naar alle controlelogboekvermeldingen met de volgende criteria:

- **Startdatum**: 4 augustus 2019
- **Einddatum**: 3 oktober 2019
- **Cmdlets**: Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

Zie [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)voor gedetailleerde syntaxis- en parametergegevens .

### <a name="view-details-of-audit-log-entries"></a>Details van controlelogboekvermeldingen weergeven

De cmdlet **ZoekadminLog** retourneert later in dit onderwerp de velden die zijn beschreven in de sectie [Inhoud van het controlelogboek.](#audit-log-contents) Van de velden die door de cmdlet worden geretourneerd, bevatten twee velden, **CmdletParameters** en **ModifiedProperties,** aanvullende informatie die niet standaard wordt geretourneerd.

Als u de inhoud van de velden **CmdletParameters** en **ModifiedProperties wilt weergeven,** gebruikt u de volgende stappen.

1. Bepaal de criteria waar u naar wilt zoeken, voer de cmdlet **Search-AdminAuditLog** uit en sla de resultaten op in een variabele met de volgende opdracht.

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. Elke controlelogboekvermelding wordt opgeslagen als een arrayelement in de variabele `$Results` . U een matrixelement selecteren door de matrixelementindex op te geven. Matrixelementenindexen beginnen bij nul (0) voor het eerste matrixelement. Als u bijvoorbeeld het vijfde matrixelement, dat een index van 4 heeft, wilt ophalen, gebruikt u de volgende opdracht.

    ```PowerShell
    $Results[4]
    ```

3. De vorige opdracht retourneert de logboekvermelding die is opgeslagen in matrixelement 4. Als u de inhoud van de velden **CmdletParameters** en **ModifiedProperties** voor dit logboek wilt bekijken, gebruikt u de volgende opdrachten.

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. Als u de inhoud van de velden **CmdletParameters** of **ModifiedParameters** in een ander logboek wilt weergeven, wijzigt u de matrixelementindex.

## <a name="audit-log-contents"></a>Inhoud van controlelogboek

Elke controlelogboekvermelding bevat de informatie die in de volgende tabel wordt beschreven. Het controlelogboek bevat een of meer controlelogboekgegevens.

|||
|---|---|
|**Veld**|**Beschrijving**|
|`RunspaceId`|Dit veld wordt intern gebruikt door EOP.|
|`ObjectModified`|Dit veld bevat het object dat is gewijzigd door de cmdlet die in het `CmdletName` veld is opgegeven.|
|`CmdletName`|Dit veld bevat de naam van de cmdlet die door de gebruiker in het veld is `Caller` uitgevoerd.|
|`CmdletParameters`|Dit veld bevat de parameters die zijn opgegeven toen de cmdlet in het `CmdletName` veld werd uitgevoerd. Ook opgeslagen in dit veld, maar niet zichtbaar in de standaarduitvoer, is de waarde die is opgegeven met de parameter, indien aanwezig.|
|`ModifiedProperties`|Dit veld bevat de eigenschappen die zijn gewijzigd op het object in het `ObjectModified` veld. Ook opgeslagen in dit veld, maar niet zichtbaar in de standaarduitvoer, zijn de oude waarde van de eigenschap en de nieuwe waarde die is opgeslagen.|
|`Caller`|Dit veld bevat het gebruikersaccount van de gebruiker die de cmdlet in het veld heeft `CmdletName` uitgevoerd.|
|`ExternalAccess`|Dit veld wordt intern gebruikt door EOP.|
|`Succeeded`|Met dit veld wordt aangegeven of de cmdlet in het `CmdletName` veld is uitgevoerd. De waarde is `True` een van beide of `False` .|
|`Error`|Dit veld bevat het foutbericht dat is gegenereerd als de cmdlet in het `CmdletName` veld niet is voltooid.|
|`RunDate`|Dit veld bevat de datum en tijd waarop de cmdlet in het `CmdletName` veld is uitgevoerd. De datum en tijd worden opgeslagen in de indeling Coordinated Universal Time (UTC).|
|`OriginatingServer`|Dit veld geeft de server aan waarop de cmdlet die in het `CmdletName` veld is opgegeven, is uitgevoerd.|
|`ClientIP`|Dit veld wordt intern gebruikt door EOP.|
|`SessionId`|Dit veld wordt intern gebruikt door EOP.|
|`AppId`|Dit veld wordt intern gebruikt door EOP.|
|`ClientAppId`|Dit veld wordt intern gebruikt door EOP.|
|`Identity`|Dit veld wordt intern gebruikt door EOP.|
|`IsValid`|Dit veld wordt intern gebruikt door EOP.|
|`ObjectState`|Dit veld wordt intern gebruikt door EOP.|
|
