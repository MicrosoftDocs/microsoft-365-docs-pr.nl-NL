---
title: Een rapport over groepen met beheerdersrollen uitvoeren in standalone EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u een groepsrapport met beheerdersrollen uitvoert in zelfstandige Exchange Online Protection (EOP). Dit rapport meldt wanneer een beheerder leden toevoegt aan of verwijdert uit groepen beheerdersrollen.
ms.openlocfilehash: cd7ca13a3d863240a0f2608ed13321cbe3d50ad2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659259"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>Een rapport over groepen met beheerdersrollen uitvoeren in standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Bij zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken, wanneer een beheerder leden toevoegt aan of verwijdert uit groepen met administratieve rollen, wordt elk exemplaar in de service geregistreerd. Zie [machtigingen in zelfstandige EOP](feature-permissions-in-eop.md)voor meer informatie over rollen groepen in zelfstandige EOP.

Wanneer u een rapport in het rollencentrum van de beheerder uitvoert in het Exchange-Beheercentrum, worden vermeldingen weergegeven als zoekresultaten en worden de betreffende Rolgroepen opgenomen, die het lidmaatschap van rollen groepen en wanneer ze zijn gewijzigd en welke lidmaatschaps updates zijn aangebracht. Gebruik dit rapport om wijzigingen aan te brengen in de beheerdersmachtigingen die zijn toegewezen aan gebruikers in uw organisatie.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Om het Exchange-Beheercentrum te openen, raadpleegt u het [Exchange-Beheercentrum in zelfstandige EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- U moet machtigingen zijn toegewezen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren. Specifiek hebt u de rol **audit** Logboeken of **alleen-lezen** rollen nodig die zijn toegewezen aan de rollen groepen **Organisatiebeheer**, **Compliance Management** en **beveiligingsbeheerder** . Zie voor meer informatie [machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en [Gebruik de lijst met wijzigingen in de lijst met leden van rollen groepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Zie toetscombinaties [voor het Exchange-Beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)voor informatie over toetscombinaties die van toepassing kunnen zijn op de procedures in dit artikel.

> [!TIP]
> Problemen? Vraag om hulp op het forum van [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Het rapport van de rollen groep in de lijst met beheerders uitvoeren

Voer het rapport rollen groep van beheerder uit om de wijzigingen in rollen groepen binnen een bepaald tijdsbestek te vinden.

1. Ga in het Exchange-Beheercentrum naar **nalevings beheer** \> en kies vervolgens **een beheerrapport** van de beheerderrol.

2. Configureer de volgende instellingen op de pagina **rollen groepen zoeken naar beheerders** die wordt geopend:

   - **Begindatum** en **einddatum**: Voer een datumbereik in. Standaard wordt in de lijst in de afgelopen twee weken gezocht naar wijzigingen in rollen groepen met beheerders.

   - **Rollen groepen selecteren**: standaard worden alle rollen groepen gezocht. Als u de resultaten wilt filteren op specifieke rollen groepen, klikt u op **rollen groepen selecteren**. Selecteer in het dialoogvenster dat wordt weergegeven een rolgroep en klik op **add->**. Herhaal deze stap zo vaak als nodig is en klik op **OK** wanneer u klaar bent.

3. Wanneer u klaar bent, klikt u op **zoeken**.

Als er wijzigingen zijn gevonden met de criteria die u hebt opgegeven, worden deze weergegeven in het deelvenster resultaten. Klik in de zoekresultaten op een rolgroep om de wijzigingen weer te geven in het detailvenster.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u het rapport rollen groep van beheerder hebt uitgevoerd, worden rollen groepen die zijn gewijzigd in het datumbereik weergegeven in het deelvenster Zoekresultaten. Als er geen resultaten zijn, zijn er geen wijzigingen in rollen groepen binnen het opgegeven datumbereik. Als u denkt dat er resultaten moeten zijn, wijzigt u het datumbereik en voert u het rapport opnieuw uit.

## <a name="monitor-changes-to-role-group-membership"></a>Wijzigingen in lidmaatschap van rollen groepen controleren

Wanneer leden worden toegevoegd aan of verwijderd uit een rollen groep, wordt in de zoekresultaten die in het detailvenster worden weergegeven, aangegeven dat het lidmaatschap van de rollen groep is bijgewerkt en worden de huidige leden weergegeven. De resultaten hebben geen expliciete gevolgen voor het toevoegen of verwijderen van een gebruiker.

Als u wilt bepalen of een gebruiker is toegevoegd of verwijderd, moet u twee afzonderlijke items in het rapport vergelijken. Laten we bijvoorbeeld kijken naar de volgende logboekvermeldingen voor de rollen groep **helpdesk** :

> 1/27/2018 4:43 PM <br> Administrator (Beheerder) <br> Bijgewerkte leden: beheerder; ANNB, florencef; pilarp <br> 2/06/2018 10:09 AM <br> Administrator (Beheerder) <br> Bijgewerkte leden: beheerder; ANNB; florencef; pilarp; tonip <br> 2/19/2018 2:12 PM <br> Administrator (Beheerder) <br> Bijgewerkte leden: beheerder; ANNB; florencef; tonip

In dit voorbeeld hebben we de volgende wijzigingen aangebracht in het gebruikersaccount van de beheerder:

- Op 2/06/2018 hebben ze de gebruikers tonip toegevoegd.
- Op 2/19/2018 hebben ze de gebruiker pilarp verwijderd.

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>Zelfstandige Exchange Online PowerShell gebruiken om te zoeken naar controlelogboekvermeldingen

U kunt Exchange Online PowerShell gebruiken om te zoeken naar controlelogboekvermeldingen die voldoen aan de criteria die u opgeeft. Zie Zoek [criteria zoeken in AdminAuditLog](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)voor een overzicht van zoekcriteria. Deze procedure gebruikt de **Search-AdminAuditLog-** cmdlet en toont zoekresultaten in Exchange Online PowerShell. U kunt deze cmdlet gebruiken wanneer u een reeks resultaten moet retourneren die de limieten voor de **New-AdminAuditLogSearch-** cmdlet of de rapporten van de audittrail-controlerapporten overschrijden.

Gebruik de volgende syntaxis om in het auditlogboek te zoeken naar criteria die u opgeeft.

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> Met de cmdlet **Search-AdminAuditLog** wordt standaard een maximum van 1.000-logboekvermeldingen geretourneerd. Gebruik de parameter _ResultSize_ om maximaal 250.000 logboekvermeldingen op te geven. Of gebruik de waarde `Unlimited` om alle items te retourneren.

In dit voorbeeld wordt een zoekopdracht uitgevoerd naar alle controlelogboekvermeldingen met de volgende criteria:

- **Begindatum**: 08/04/2018
- **Einddatum**: 10/03/2018
- **Gebruikers-id's**: `davids` , `chrisd``kima`
- **Cmdlets**: **set-mailbox**
- **Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

In dit voorbeeld wordt gezocht naar wijzigingen die zijn aangebracht in een specifiek postvak. Dit is handig als u problemen ondervindt of als u informatie over een onderzoek moet invoeren. De volgende criteria worden gebruikt:

- **Begindatum**: 05/01/2018
- **Einddatum**: 10/03/2018
- **Object-id**: contoso.com/users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

Als u in uw zoekopdrachten een groot aantal logboekvermeldingen oplevert, is het raadzaam de procedure te volgen die wordt beschreven in **Exchange Online PowerShell gebruiken om te zoeken naar controlelogboekvermeldingen en om resultaten naar een geadresseerde te verzenden** verderop in dit artikel. De procedure in dat sectie verzendt een XML-bestand als e-mailbijlage bij de geadresseerden die u opgeeft, zodat u gemakkelijker de gewenste gegevens kunt extraheren.

Zie [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="view-details-of-audit-log-entries"></a>Details van controlelogboekvermeldingen weergeven

Met de cmdlet **Search-AdminAuditLog** worden de velden geretourneerd die zijn beschreven in de inhoud van het [controlelogboek](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents). Van de velden die worden geretourneerd door de cmdlets, twee velden, **CmdletParameters** en **ModifiedProperties**, bevatten aanvullende informatie die standaard niet kan worden bekeken.

Voer de volgende stappen uit om de inhoud van de velden **CmdletParameters** en **ModifiedProperties** weer te geven. U kunt ook de procedure in **Exchange Online PowerShell gebruiken om te zoeken naar controlelogboekvermeldingen en de resultaten naar een geadresseerde te verzenden** verderop in dit artikel als u een XML-bestand wilt maken.

Deze procedure gebruikt de volgende concepten:

- [about_Arrays](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

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
