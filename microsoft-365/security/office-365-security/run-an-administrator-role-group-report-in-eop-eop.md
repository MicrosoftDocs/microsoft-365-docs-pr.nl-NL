---
title: Een rapport over groepen met beheerdersrollen uitvoeren in standalone EOP
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
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u een beheerdersrolgroeprapport uitvoert in standalone Exchange Online Protection (EOP). Dit rapport logt wanneer een beheerder leden toevoegt aan of leden verwijdert uit beheerdersrolgroepen, EOP registreert elke gebeurtenis.
ms.openlocfilehash: 0c504460657a153aad7d3dd065c81007a68ba916
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587362"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>Een rapport over groepen met beheerdersrollen uitvoeren in standalone EOP

In zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken, wanneer een beheerder leden toevoegt aan of leden uit beheerdersgroepen verwijdert, registreert de service elke gebeurtenis. Zie [Machtigingen in zelfstandige EOP](feature-permissions-in-eop.md)voor meer informatie over rolgroepen in standalone EOP.

Wanneer u een beheerdersrolgroeprapport uitvoert in het Exchange-beheercentrum (EAC), worden vermeldingen weergegeven als zoekresultaten en worden de betrokken rolgroepen opgenomen, die het lidmaatschap van de rolgroep hebben gewijzigd en wanneer en welke lidmaatschapsupdates zijn uitgevoerd. Gebruik dit rapport om wijzigingen in de beheerdersmachtigingen te controleren die zijn toegewezen aan gebruikers in uw organisatie.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie [Exchange-beheercentrum in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md)als u het Exchange-beheercentrum wilt openen.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. U hebt specifiek de rol Auditlogboeken of Controlelogboeken alleen weergeven nodig, die standaard zijn toegewezen aan de rolgroepen ComplianceManagement, OrganizationManagement (global admins) en SecurityAdministrator. Zie [Machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en Gebruik de EAC voor meer informatie [de lijst met leden in rolgroepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)wijzigen.

- Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.

> [!TIP]
> Heb je problemen? Vraag om hulp in het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>De EAC gebruiken om een rapport over een beheerdersrolgroep uit te voeren

Voer het rapport van de beheerdersrolgroep uit om de wijzigingen in beheerrolgroepen in uw organisatie binnen een bepaald tijdsbestek te vinden.

1. Ga in de EAC naar **Compliance management** \> **Auditing**en kies **vervolgens Een beheerdersrolgroeprapport uitvoeren**.

2. Configureer in de pagina Zoeken naar wijzigingen in de pagina **beheerdersrolgroepen** die wordt geopend de volgende instellingen:

   - **Begindatum** en **einddatum**: Voer een datumbereik in. Standaard zoekt het rapport naar wijzigingen die in de afgelopen twee weken zijn aangebracht in beheerdersrolgroepen.

   - **Rolgroepen selecteren:** Standaard worden alle rolgroepen doorzocht. Als u de resultaten wilt filteren op specifieke rolgroepen, klikt u op **Rolgroepen selecteren**. Selecteer in het dialoogvenster dat wordt weergegeven een rolgroep en klik op **toevoegen ->**. Herhaal deze stap zo vaak als nodig is en klik op **OK** wanneer u klaar bent.

3. Klik op **Zoeken**als u klaar bent.

Als er wijzigingen worden gevonden met behulp van de criteria die u hebt opgegeven, worden deze weergegeven in het resultatenvenster. Klik op een rolgroep in de zoekresultaten om de wijzigingen in het detailvenster weer te geven.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u een rapport van de beheerdersrolgroep hebt uitgevoerd, worden rolgroepen die binnen het datumbereik zijn gewijzigd, weergegeven in het deelvenster zoekresultaten. Als er geen resultaten zijn, hebben er geen wijzigingen plaatsgevonden in rolgroepen binnen het opgegeven datumbereik. Als u denkt dat er resultaten moeten zijn, wijzigt u het datumbereik en voert u het rapport opnieuw uit.

## <a name="monitor-changes-to-role-group-membership"></a>Wijzigingen in het lidmaatschap van de rolgroep controleren

Wanneer leden worden toegevoegd aan of verwijderd uit een rolgroep, geven de zoekresultaten die in het detailvenster worden weergegeven aan dat het lidmaatschap van de rolgroep is bijgewerkt en worden de huidige leden weergegeven. In de resultaten wordt niet expliciet vermeld welke gebruiker is toegevoegd of verwijderd.

Als u wilt bepalen of een gebruiker is toegevoegd of verwijderd, moet u twee afzonderlijke vermeldingen in het rapport vergelijken. Laten we bijvoorbeeld eens kijken naar de volgende logboekvermeldingen voor de **rolgroep HelpDesk:**

> 1/27/2018 16:43 <br> Administrator (Beheerder) <br> Bijgewerkte leden: Administrator;annb,florencef;pilarp <br> 2/06/2018 10:09 <br> Administrator (Beheerder) <br> Bijgewerkte leden: Administrator;annb;florencef;pilarp;tonip <br> 19-19-2018 14:12 uur <br> Administrator (Beheerder) <br> Bijgewerkte leden: Administrator;annb;florencef;tonip

In dit voorbeeld heeft het gebruikersaccount van de beheerder de volgende wijzigingen aangebracht:

- Op 2/06/2018 voegden ze de gebruiker tonip toe.

- Op 2/19/2018 verwijderden ze de gebruiker pilarp.

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>Zelfstandige Exchange Online PowerShell gebruiken om te zoeken naar controlelogboekvermeldingen

U Exchange Online PowerShell gebruiken om te zoeken naar controlelogboekvermeldingen die voldoen aan de criteria die u opgeeft. Zie [Zoek-AdminAuditLog-zoekcriteria](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)voor een lijst met zoekcriteria. Deze procedure maakt gebruik van de cmdlet **Search-AdminAuditLog** en geeft zoekresultaten weer in Exchange Online PowerShell. U deze cmdlet gebruiken wanneer u een set resultaten moet retourneren die de limieten overschrijdt die zijn gedefinieerd in de cmdlet **New-AdminAuditLogSearch** of in de EAC Audit Reporting-rapporten.

Als u in het controlelogboek wilt zoeken naar criteria die u opgeeft, gebruikt u de volgende syntaxis.

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> De cmdlet **Search-AdminAuditLog** retourneert standaard maximaal 1.000 logboekvermeldingen. Gebruik de parameter _ResultSize_ om maximaal 250.000 logboekvermeldingen op te geven. Of gebruik de waarde `Unlimited` om alle vermeldingen terug te sturen.

In dit voorbeeld wordt gezocht naar alle controlelogboekvermeldingen met de volgende criteria:

- **Startdatum**: 08/04/2018

- **Einddatum**: 10/03/2018

- **Gebruikers-id's**: davids, chrisd, kima

- **Cmdlets**: **Set-Mailbox**

- **Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

In dit voorbeeld wordt gezocht naar wijzigingen in een specifiek postvak. Dit is handig als u problemen opgaat of als u informatie moet verstrekken voor een onderzoek. De volgende criteria worden gebruikt:

- **Startdatum**: 05/01/2018

- **Einddatum**: 10/03/2018

- **Object-id**: contoso.com/Users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

Als uw zoekopdrachten veel logboekvermeldingen retourneren, raden we u aan de procedure in Exchange Online PowerShell te gebruiken **om te zoeken naar controlelogboekvermeldingen en** resultaten later in dit onderwerp naar een ontvanger te sturen. De procedure in die sectie stuurt een XML-bestand als e-mailbijlage naar de ontvangers die u opgeeft, zodat u gemakkelijker de gegevens extraheren waarin u geïnteresseerd bent.

Zie [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)voor gedetailleerde syntaxis- en parametergegevens .

### <a name="view-details-of-audit-log-entries"></a>Details van controlelogboekvermeldingen weergeven

De cmdlet **ZoekadminLog** retourneert de velden die zijn beschreven in [de inhoud van het controlelogboek](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents). Van de velden die door de cmdlet worden geretourneerd, bevatten twee velden, **CmdletParameters** en **ModifiedProperties,** aanvullende informatie die standaard niet zichtbaar is.

Als u de inhoud van de velden **CmdletParameters** en **ModifiedProperties wilt weergeven,** gebruikt u de volgende stappen. U de procedure in Exchange Online PowerShell gebruiken gebruiken **om te zoeken naar controlelogboekvermeldingen en resultaten later** in dit onderwerp naar een ontvanger te sturen om een XML-bestand te maken.

Bij deze procedure worden de volgende begrippen gebruikt:

- [about_Arrays](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

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