---
title: Een rapport met een beheerdersrolgroep uitvoeren in zelfstandige EOP
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
description: Beheerders kunnen leren hoe u een rapport met een beheerdersrolgroep uitvoert in zelfstandige Exchange Online Protection (EOP). In dit rapport wordt logboeken opgeslagen wanneer een beheerder leden toevoegt aan of verwijdert uit beheerdersrolgroepen, registreert EOP elke gebeurtenis.
ms.openlocfilehash: f5641e9900c786f976d05cdeeec148caab12a03d
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209173"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>Een rapport met een beheerdersrolgroep uitvoeren in zelfstandige EOP

In zelfstandige Exchange Online Protection -organisaties (EOP)-organisaties zonder Exchange Online-postvakken, wanneer een beheerder leden toevoegt aan of verwijdert uit administratieve rolgroepen, registreert de service elke gebeurtenis. Zie Machtigingen in zelfstandige EOP voor meer informatie over rolgroepen in zelfstandige [EOP.](feature-permissions-in-eop.md)

Wanneer u een rapport met een beheerdersrolgroep uitvoert in het Exchange-beheercentrum (EAC), worden items weergegeven als zoekresultaten en worden de betrokken rolgroepen opgenomen, wie het lidmaatschap van de rolgroep heeft gewijzigd en wanneer en welke lidmaatschapsupdates zijn uitgevoerd. Gebruik dit rapport om wijzigingen in de beheerdersmachtigingen te controleren die zijn toegewezen aan gebruikers in uw organisatie.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie [Exchange-beheercentrum in het zelfstandige EOP](exchange-admin-center-in-exchange-online-protection-eop.md)om het Exchange-beheercentrum te openen.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. U hebt in het bijzonder de rol Controlelogboeken of Alleen-weergavecontrolelogboeken nodig, die standaard zijn toegewezen aan de rolgroepen ComplianceManagement, OrganizationManagement (globale beheerders) en SecurityAdministrator. Zie [Machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en Gebruik de [EAC wijzigen de lijst met leden in rolgroepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)voor meer informatie.

- Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.

> [!TIP]
> Heb je problemen? Vraag om hulp op het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>De EAC gebruiken om een rapport van een beheerdersrolgroep uit te voeren

Voer het rapport van de groep beheerdersrollen uit om de wijzigingen in beheerrolgroepen in uw organisatie binnen een bepaald tijdsbestek te vinden.

1. Ga in de EAC naar **Compliance management** \> **Auditing**en kies **Vervolgens een rapport van de beheerdersrolgroep uitvoeren**.

2. Configureer de volgende instellingen in de pagina Zoeken naar wijzigingen in de pagina **Beheerdersrolgroepen** die wordt geopend:

   - **Begin-** en **einddatum**: Voer een datumbereik in. Standaard wordt in het rapport gezocht naar wijzigingen die in de afgelopen twee weken zijn aangebracht in beheerdersrolgroepen.

   - **Rolgroepen selecteren**: Standaard worden alle rolgroepen doorzocht. Als u de resultaten wilt filteren op specifieke rolgroepen, klikt u op **Rolgroepen selecteren**. Selecteer in het dialoogvenster dat wordt weergegeven een rolgroep en klik op **toevoegen >**. Herhaal deze stap zo vaak als nodig is en klik op **OK** als u klaar bent.

3. Klik op **Zoeken**als u klaar bent.

Als er wijzigingen worden gevonden aan de hand van de criteria die u hebt opgegeven, worden deze weergegeven in het resultatenvenster. Klik op een rolgroep in de zoekresultaten om de wijzigingen in het detailvenster te bekijken.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u een groepsrapport voor beheerdersrollen hebt uitgevoerd, worden rolgroepen die binnen het datumbereik zijn gewijzigd, weergegeven in het deelvenster zoekresultaten. Als er geen resultaten zijn, hebben er binnen het opgegeven datumbereik geen wijzigingen in rolgroepen plaatsgevonden. Als u denkt dat er resultaten moeten zijn, wijzigt u het datumbereik en voert u het rapport opnieuw uit.

## <a name="monitor-changes-to-role-group-membership"></a>Wijzigingen in het lidmaatschap van rolgroepen controleren

Wanneer leden worden toegevoegd aan of verwijderd uit een rolgroep, geven de zoekresultaten in het detailvenster aan dat het lidmaatschap van de rolgroep is bijgewerkt en worden de huidige leden weergegeven. In de resultaten wordt niet expliciet vermeld welke gebruiker is toegevoegd of verwijderd.

Als u wilt bepalen of een gebruiker is toegevoegd of verwijderd, moet u twee afzonderlijke vermeldingen in het rapport vergelijken. Laten we bijvoorbeeld de volgende logboekvermeldingen voor de **HelpDesk-rolgroep** bekijken:

> 1/27/2018 16:43 <br> Administrator (Beheerder) <br> Bijgewerkte leden: Administrator;annb,florencef;pilarp <br> 2/06/2018 10:09 <br> Administrator (Beheerder) <br> Bijgewerkte leden: Administrator;annb;florencef;pilarp;tonip <br> 2/19/2018 14:12 <br> Administrator (Beheerder) <br> Bijgewerkte leden: Administrator;annb;florencef;tonip

In dit voorbeeld heeft het gebruikersaccount van de beheerder de volgende wijzigingen aangebracht:

- Op 2/06/2018 hebben ze de user tonip toegevoegd.

- Op 2/19/2018 hebben ze de gebruiker verwijderd.

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>Zelfstandige Exchange Online PowerShell gebruiken om te zoeken naar controlelogboekvermeldingen

U Exchange Online PowerShell gebruiken om te zoeken naar controlelogboekvermeldingen die voldoen aan de criteria die u opgeeft. Zie [Logboekregistratie administratorcontrole](https://technet.microsoft.com/library/22b17eb8-d8ee-4599-b202-d6a7928c20d9.aspx)voor een lijst met zoekcriteria. Deze procedure maakt gebruik van de cmdlet **Search-AdminAuditLog** en geeft zoekresultaten weer in Exchange Online PowerShell. U deze cmdlet gebruiken wanneer u een set resultaten moet retourneren die de limieten overschrijdt die zijn gedefinieerd op de cmdlet **Nieuw-AdminAuditLogSearch** of in de EAC-controlerapportagerapporten.

Als u in het controlelogboek wilt zoeken naar criteria die u opgeeft, gebruikt u de volgende syntaxis.

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> De **cmdlet Search-AdminAuditLog** retourneert standaard maximaal 1.000 logboekvermeldingen. Gebruik de parameter _ResultSize_ om maximaal 250.000 logboekvermeldingen op te geven. Of gebruik de waarde `Unlimited` om alle items terug te sturen.

In dit voorbeeld wordt gezocht naar alle controlelogboekvermeldingen met de volgende criteria:

- **Startdatum**: 08/04/2018

- **Einddatum**: 10/03/2018

- **Gebruikers-iDs**: davids, chrisd, kima

- **Cmdlets**: **Set-Mailbox**

- **Parameters** _: SendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

In dit voorbeeld wordt gezocht naar wijzigingen die zijn aangebracht in een specifiek postvak. Dit is handig als u problemen oplost of als u informatie moet verstrekken voor een onderzoek. De volgende criteria worden gebruikt:

- **Startdatum**: 05/01/2018

- **Einddatum**: 10/03/2018

- **Object-ID**: contoso.com/Users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

Als uw zoekopdrachten veel logboekitems retourneren, raden we u aan de procedure in Exchange Online PowerShell gebruiken te gebruiken **om te zoeken naar controlelogboekvermeldingen en later** in dit onderwerp resultaten naar een ontvanger te sturen. De procedure in die sectie stuurt een XML-bestand als e-mailbijlage naar de ontvangers die u opgeeft, zodat u gemakkelijker de gegevens extraheren waarin u geïnteresseerd bent.

Zie [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-adminauditlog)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="view-details-of-audit-log-entries"></a>Details van controlelogboekvermeldingen weergeven

De cmdlet **Search-AdminAuditLog** retourneert de velden die zijn beschreven in de sectie 'Inhoud van de controlelogboek van de beheerder' van [de controlelogboekregistratie](https://technet.microsoft.com/library/22b17eb8-d8ee-4599-b202-d6a7928c20d9.aspx)van de beheerder. Van de velden die door de cmdlet worden geretourneerd, bevatten twee **velden, CmdletParameters** en **ModifiedProperties,** aanvullende informatie die standaard niet zichtbaar is.

Als u de inhoud van de velden **CmdletParameters** en **ModifiedProperties wilt** weergeven, gebruikt u de volgende stappen. U de procedure in Exchange Online PowerShell gebruiken ook gebruiken **om te zoeken naar controlelogboekvermeldingen en later** in dit onderwerp resultaten naar een ontvanger te sturen om een XML-bestand te maken.

Bij deze procedure worden de volgende begrippen gebruikt:

- [about_Arrays](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

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