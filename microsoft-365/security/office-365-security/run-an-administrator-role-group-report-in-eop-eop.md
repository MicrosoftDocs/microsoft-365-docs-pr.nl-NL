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
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe ze een beheerdersrolgroeprapport kunnen uitvoeren in zelfstandige Exchange Online Protection (EOP). Dit rapport wordt logboeken wanneer een beheerder leden toevoegt aan of verwijdert uit beheerdersrollengroepen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0281dcb13f5cee0ba8db8c4faed5054f481337cf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908792"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>Een rapport over groepen met beheerdersrollen uitvoeren in standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
-  [Zelfstandige Exchange Online Protection](exchange-online-protection-overview.md)

In zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, wanneer een beheerder leden toevoegt aan of verwijdert uit beheerdersrollengroepen, registreert de service elk exemplaar. Zie Machtigingen in zelfstandige EOP voor meer informatie over rollengroepen in zelfstandige [EOP.](feature-permissions-in-eop.md)

Wanneer u een rapport van een beheerdersrolgroep in het Exchange-beheercentrum (EAC) uitvoert, worden items weergegeven als zoekresultaten en worden de betrokken rollengroepen weergegeven, wie het lidmaatschap van de rollengroep heeft gewijzigd en wanneer en welke lidmaatschapsupdates zijn uitgevoerd. Gebruik dit rapport om wijzigingen in de beheerdersmachtigingen te controleren die zijn toegewezen aan gebruikers in uw organisatie.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie Exchange-beheercentrum in zelfstandige EOP om het Exchange-beheercentrum [te openen.](exchange-admin-center-in-exchange-online-protection-eop.md)

- U moet machtigingen krijgen toegewezen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren. U hebt met name de rol  **Auditlogboeken** of **Alleen-weergeven auditlogboeken** nodig, die standaard zijn toegewezen aan de rollengroepen Organisatiebeheer, **Compliancebeheer** en Beveiligingsbeheerder.  Zie Machtigingen in zelfstandige [EOP](feature-permissions-in-eop.md) en Gebruik de EAC om de lijst met [leden in rollengroepen te wijzigen voor meer informatie.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Zie Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in [dit artikel.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Hebt u problemen? Vraag om hulp in het [Exchange Online Protection-forum.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Het EAC gebruiken om een beheerdersrolgroeprapport uit te voeren

Voer het rapport beheerdersrolgroep uit om de wijzigingen in beheerrolgroepen binnen een bepaald tijdsbestek te vinden.

1. Ga in het EAC naar **Compliance management** \> **Auditing** en kies **vervolgens Een beheerdersrolgroeprapport uitvoeren.**

2. Configureer de volgende instellingen op de pagina Zoeken naar wijzigingen in **beheerdersrolgroepen** die worden geopend:

   - **Begindatum** en **einddatum:** Voer een datumbereik in. Standaard wordt in het rapport gezocht naar wijzigingen die zijn aangebracht in beheerdersrolgroepen in de afgelopen twee weken.

   - **Rolgroepen selecteren:** standaard worden alle rollengroepen doorzocht. Als u de resultaten wilt filteren op specifieke rollengroepen, klikt **u op Rolgroepen selecteren.** Selecteer in het dialoogvenster dat wordt weergegeven een rollengroep en klik **op Toevoegen ->.** Herhaal deze stap zo vaak als nodig en klik op **OK** wanneer u klaar bent.

3. Wanneer u klaar bent, klikt u op **Zoeken**.

Als er wijzigingen worden gevonden aan de hand van de criteria die u hebt opgegeven, worden deze weergegeven in het resultatenvenster. Klik op een rollengroep in de zoekresultaten om de wijzigingen in het detailvenster weer te geven.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u een rapport met beheerdersrolgroepen hebt uitgevoerd, worden rollengroepen die binnen het datumbereik zijn gewijzigd, weergegeven in het deelvenster zoekresultaten. Als er geen resultaten zijn, zijn er geen wijzigingen in rollengroepen doorgevoerd binnen het opgegeven datumbereik. Als u denkt dat er resultaten moeten zijn, wijzigt u het datumbereik en wordt het rapport opnieuw uitgevoerd.

## <a name="monitor-changes-to-role-group-membership"></a>Wijzigingen in lidmaatschap van rollengroep controleren

Wanneer leden worden toegevoegd aan of verwijderd uit een rollengroep, geven de zoekresultaten die worden weergegeven in het detailvenster aan dat het lidmaatschap van de rollengroep is bijgewerkt en de huidige leden worden weergegeven. In de resultaten wordt niet expliciet vermeld welke gebruiker is toegevoegd of verwijderd.

Als u wilt bepalen of een gebruiker is toegevoegd of verwijderd, moet u twee afzonderlijke vermeldingen in het rapport vergelijken. Laten we bijvoorbeeld de volgende logboekgegevens voor de **helpdesk-rollengroep** bekijken:

> 27-17-2018 16:43 uur <br> Administrator (Beheerder) <br> Bijgewerkte leden: Administrator;annb,firenzev;pilarp <br> 06-2018 10:09 <br> Administrator (Beheerder) <br> Bijgewerkte leden: Administrator;annb;florencef;pilarp;tonip <br> 19-2-2018 14:12 <br> Administrator (Beheerder) <br> Bijgewerkte leden: Administrator;annb;firenip;tonip

In dit voorbeeld heeft het gebruikersaccount beheerder de volgende wijzigingen aangebracht:

- Op 06-2-2018 hebben ze de gebruikers-tonip toegevoegd.
- Op 19-2-2-2018 hebben ze de gebruikers pilarp verwijderd.

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>Zelfstandige Exchange Online PowerShell gebruiken om te zoeken naar auditlogboekgegevens

U kunt Exchange Online PowerShell gebruiken om te zoeken naar auditlogboekgegevens die voldoen aan de criteria die u opgeeft. Zie Zoekcriteria voor [Search-AdminAuditLog voor](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)een lijst met zoekcriteria. In deze procedure wordt de **cmdlet Search-AdminAuditLog** gebruikt en worden zoekresultaten weergegeven in Exchange Online PowerShell. U kunt deze cmdlet gebruiken wanneer u een reeks resultaten wilt retourneren die de limieten overschrijdt die zijn gedefinieerd op de cmdlet **New-AdminAuditLogSearch** of in de EAC-auditrapportagerapporten.

Als u in het auditlogboek wilt zoeken naar criteria die u opgeeft, gebruikt u de volgende syntaxis.

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> De **cmdlet Search-AdminAuditLog** retourneert standaard maximaal 1.000 logboekgegevens. Gebruik de _parameter ResultSize_ om maximaal 250.000 logboekgegevens op te geven. Of gebruik de waarde om `Unlimited` alle items te retourneren.

In dit voorbeeld wordt een zoekopdracht uitgevoerd naar alle controlelogboekgegevens met de volgende criteria:

- **Begindatum**: 08-04-2018
- **Einddatum**: 03-10-2018
- **Gebruikers-ID's:** `davids` `chrisd` , , `kima`
- **Cmdlets**: **Postvak instellen**
- **Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

In dit voorbeeld wordt gezocht naar wijzigingen in een specifiek postvak. Dit is handig als u problemen oplost of als u informatie wilt verstrekken voor een onderzoek. De volgende criteria worden gebruikt:

- **Begindatum**: 05-01-2018
- **Einddatum**: 03-10-2018
- **Object-id:** contoso.com/Users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

Als uw zoekopdrachten veel logboekgegevens retourneren, raden we u aan de procedure in **Exchange Online PowerShell** te gebruiken om te zoeken naar auditlogboekgegevens en resultaten te verzenden naar een geadresseerde verderop in dit artikel. Met de procedure in die sectie wordt een XML-bestand als e-mailbijlage verzonden naar de geadresseerden die u opgeeft, zodat u gemakkelijker de gegevens kunt oppakken waarin u geïnteresseerd bent.

Zie [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="view-details-of-audit-log-entries"></a>Details van controlelogboekgegevens weergeven

De **cmdlet Search-AdminAuditLog** retourneert de velden die worden beschreven in [de inhoud van het auditlogboek.](/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents) Van de velden die door de cmdlet worden geretourneerd, bevatten twee velden, **CmdletParameters** en **ModifiedProperties,** aanvullende informatie die standaard niet kan worden weergegeven.

Als u de inhoud van de **velden CmdletParameters** en **ModifiedProperties** wilt weergeven, gebruikt u de volgende stappen. U kunt de procedure in **Exchange Online PowerShell** ook gebruiken om te zoeken naar auditlogboekgegevens en resultaten te verzenden naar een geadresseerde verderop in dit artikel om een XML-bestand te maken.

In deze procedure worden de volgende concepten gebruikt:

- [about_Arrays](/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](/powershell/module/microsoft.powershell.core/about/about_variables)

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