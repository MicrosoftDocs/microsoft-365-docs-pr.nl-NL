---
title: Bekijk het logboek voor beheerderscontrole in zelfstandige EOP
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
description: Beheerders kunnen leren hoe ze het beheercontrolelogboek in de zelfstandige Exchange Online Protection (EOP) kunnen bekijken en doorzoeken.
ms.openlocfilehash: 3aedebc97ccd32c1641510017a276ddbe4770633
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208474"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>Bekijk het logboek voor beheerderscontrole in zelfstandige EOP

In zelfstandige Exchange Online Protection-organisaties (EOP)-organisaties zonder Exchange Online-postvakken u het Exchange-beheercentrum (EAC) of de zelfstandige EOP PowerShell gebruiken om items in het beheercontrolelogboek te zoeken en weer te geven.

Het beheercontrolelogboek registreert specifieke acties op basis van zelfstandige EOP PowerShell-cmdlets, uitgevoerd door beheerders en gebruikers aan welke beheerders beheerdersbevoegdheden zijn toegewezen. Vermeldingen in het beheercontrolelogboek geven u informatie over welke cmdlet werd uitgevoerd, welke parameters werden gebruikt, wie de cmdlet heeft uitgevoerd en welke objecten zijn beïnvloed.

> [!NOTE]
> <ul><li>Logboekregistratie voor beheerderscontrole is standaard ingeschakeld en u deze niet uitschakelen.</li><li>Het beheercontrolelogboek registreert geen acties op basis van cmdlets die beginnen met de werkwoorden **Get,** **Search**of **Test**.</li><li>Controlelogboekvermeldingen worden 90 dagen bewaard. Wanneer een item ouder is dan 90 dagen, wordt het verwijderd</li></ul>

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie [Exchange-beheercentrum in het zelfstandige EOP](exchange-admin-center-in-exchange-online-protection-eop.md)om het Exchange-beheercentrum te openen.

- Zie Verbinding maken met Exchange [Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)als u verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. U hebt in het bijzonder de rol Controlelogboeken of Alleen-weergavecontrolelogboeken nodig, die standaard zijn toegewezen aan de rolgroepen ComplianceManagement, OrganizationManagement (globale beheerders) en SecurityAdministrator. Zie [Machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en Gebruik de [EAC wijzigen de lijst met leden in rolgroepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)voor meer informatie.

- Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.

> [!TIP]
> Heb je problemen? Vraag om hulp op het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>De EAC gebruiken om het controlelogboek van de beheerder weer te geven

1. Ga in de EAC naar **Compliance management** \> **Auditing**en kies **Vervolgens het rapport Beheercontrole uitvoeren**.

2. Kies in de pagina **Zoeken naar wijzigingen in beheerdersrolgroepen** die wordt geopend een **begindatum** en **einddatum** (het standaardbereik is de afgelopen twee weken) en kies **Vervolgens Zoeken**. Alle configuratiewijzigingen die tijdens de opgegeven periode zijn aangebracht, worden weergegeven en kunnen worden gesorteerd met behulp van de volgende informatie:

   - **Datum:** de datum en tijd waarop de configuratiewijziging is aangebracht. De datum en tijd worden opgeslagen in de indeling Coordinated Universal Time (UTC).

   - **Cmdlet**: De naam van de cmdlet die werd gebruikt om de configuratie te wijzigen.

   - **Gebruiker:** de naam van het gebruikersaccount van de gebruiker die de configuratie heeft gewijzigd.

     Op meerdere pagina's worden maximaal 5000 vermeldingen weergegeven. Geef een kleiner datumbereik op als u uw resultaten wilt beperken. Als u een afzonderlijk zoekresultaat selecteert, wordt de volgende aanvullende informatie weergegeven in het detailvenster:

   - **Object gewijzigd**: het object dat is gewijzigd door de cmdlet.

   - **Parameters (parameter:waarde):** de cmdletparameters die zijn gebruikt en elke waarde die met de parameter is opgegeven.

3. Als u een specifieke controlelogboekvermelding wilt afdrukken, kiest u de knop **Afdrukken** in het detailvenster.

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>Gebruik standalone EOP PowerShell om het beheercontrolelogboek weer te geven

U standalone EOP PowerShell gebruiken om te zoeken naar controlelogboekvermeldingen die voldoen aan de criteria die u opgeeft. Gebruik de volgende syntaxis:

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**Opmerkingen**:

- U de parameter _Parameters_ alleen gebruiken samen met de parameter _Cmdlets._

- De parameter _ObjectIds filtert_ de resultaten door het object dat is gewijzigd door de cmdlet. Een geldige waarde is afhankelijk van hoe het object wordt weergegeven in het controlelogboek. Bijvoorbeeld:

  - Name
  - Canonieke voornaam (bijvoorbeeld contoso.com/Users/Akia Al-Zuhairi)

  U zult waarschijnlijk andere filterparameters op deze cmdlet moeten gebruiken om de resultaten te beperken en de typen objecten te identificeren waarin u geïnteresseerd bent.

- De parameter _UserIds filtert_ de resultaten door de gebruiker die de wijziging heeft aangebracht (die de cmdlet heeft uitgevoerd).

- Als u voor de parameters _StartDate_ en _EndDate_ een datum-/tijdwaarde opgeeft zonder tijdzone, is de waarde in Coordinated Universal Time (UTC). Als u een datum-tijdwaarde voor deze parameter wilt opgeven, gebruikt u een van de volgende opties:

  - Geef de datum/tijdwaarde op in UTC: '2016-05-06 14:30:00z'.

  - Geef de datum/tijdwaarde op als een formule die de datum/tijd in uw lokale tijdzone omzet in UTC: bijvoorbeeld `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` . Zie [Datum op de dag komen](https://go.microsoft.com/fwlink/p/?LinkID=113313)voor meer informatie.

- De cmdlet retourneert standaard maximaal 1.000 logboekvermeldingen. Gebruik de parameter _ResultSize_ om maximaal 250.000 logboekvermeldingen op te geven. Of gebruik de waarde `Unlimited` om alle items terug te sturen.

In dit voorbeeld wordt gezocht naar alle controlelogboekvermeldingen met de volgende criteria:

- **Startdatum**: 4 augustus 2019
- **Einddatum**: 3 oktober 2019
- **Cmdlets**: Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

Zie [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-adminauditlog)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="view-details-of-audit-log-entries"></a>Details van controlelogboekvermeldingen weergeven

De cmdlet **Search-AdminAuditLog** retourneert de velden die later in dit onderwerp in de [inhoudssectie van het logboek controleren](#audit-log-contents) worden beschreven. Van de velden die door de cmdlet worden geretourneerd, bevatten twee **velden, CmdletParameters** en **ModifiedProperties,** aanvullende informatie die niet standaard wordt geretourneerd.

Als u de inhoud van de velden **CmdletParameters** en **ModifiedProperties wilt** weergeven, gebruikt u de volgende stappen.

1. Bepaal de criteria die u wilt zoeken, voer de cmdlet **Search-AdminAuditLog** uit en bewaar de resultaten in een variabele met de volgende opdracht.

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. Elke controlelogboekvermelding wordt opgeslagen als een arrayelement in de variabele `$Results` . U een arrayelement selecteren door de arrayelementindex op te geven. Arrayelementindexen beginnen bij nul (0) voor het eerste matrixelement. Als u bijvoorbeeld het 5e arrayelement wilt ophalen, dat een index van 4 heeft, gebruikt u de volgende opdracht.

    ```PowerShell
    $Results[4]
    ```

3. Met de vorige opdracht wordt de logboekinvoer geretourneerd die is opgeslagen in arrayelement 4. Als u de inhoud van de velden **CmdletParameters** en **ModifiedProperties** voor deze logboekvermelding wilt bekijken, gebruikt u de volgende opdrachten.

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. Als u de inhoud van de velden **CmdletParameters** of **ModifiedParameters** in een andere logboekvermelding wilt weergeven, wijzigt u de arrayelementindex.

## <a name="audit-log-contents"></a>Inhoud van controlelogboeken

Elke controlelogvermelding bevat de informatie die in de volgende tabel wordt beschreven. Het controlelogboek bevat een of meer controlelogboekvermeldingen.

|||
|---|---|
|**Veld**|**Beschrijving**|
|`RunspaceId`|Dit veld wordt intern gebruikt door EOP.|
|`ObjectModified`|Dit veld bevat het object dat is gewijzigd door de cmdlet die in het veld is `CmdletName` opgegeven.|
|`CmdletName`|Dit veld bevat de naam van de cmdlet die door de gebruiker in het veld is `Caller` uitgevoerd.|
|`CmdletParameters`|Dit veld bevat de parameters die zijn opgegeven toen de cmdlet in het `CmdletName` veld werd uitgevoerd. Ook opgeslagen in dit veld, maar niet zichtbaar in de standaarduitvoer, is de waarde die is opgegeven met de parameter, indien aanwezig.|
|`ModifiedProperties`|Dit veld bevat de eigenschappen die zijn gewijzigd op het object in het `ObjectModified` veld. Ook opgeslagen in dit veld, maar niet zichtbaar in de standaarduitvoer, zijn de oude waarde van de eigenschap en de nieuwe waarde die is opgeslagen.|
|`Caller`|Dit veld bevat het gebruikersaccount van de gebruiker die de cmdlet in het veld heeft `CmdletName` uitgevoerd.|
|`ExternalAccess`|Dit veld wordt intern gebruikt door EOP.|
|`Succeeded`|Dit veld geeft aan of de cmdlet in het `CmdletName` veld is uitgevoerd. De waarde is of `True` `False` .|
|`Error`|Dit veld bevat het foutbericht dat is gegenereerd als de cmdlet in het `CmdletName` veld niet is voltooid.|
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
