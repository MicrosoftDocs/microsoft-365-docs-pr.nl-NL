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
description: Beheerders kunnen informatie krijgen over het uitvoeren van een beheerdersrolgroepsrapport in de zelfstandige Versie van Exchange Online Protection (EOP). Dit rapport logboeken wanneer een beheerder leden toevoegt aan of verwijdert uit beheerdersrolgroepen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d778e807a087a5e29b31645457d4a81bd05c5649
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288017"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>Een rapport over groepen met beheerdersrollen uitvoeren in standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
-  [Zelfstandige versie van Exchange Online Protection](exchange-online-protection-overview.md)

Als een beheerder in zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken leden toevoegt aan of verwijdert uit beheerrolgroepen, wordt elke gebeurtenis in de servicelogboeken bij de service logboeken geplaatst. Zie Machtigingen in de zelfstandige EOP voor meer informatie over rollengroepen [in zelfstandige EOP.](feature-permissions-in-eop.md)

Wanneer u een rapport voor een beheerdersrolgroep in het Exchange-beheercentrum (EAC) runt, worden vermeldingen weergegeven als zoekresultaten en worden de betrokken rollengroepen vermeld, wie het lidmaatschap van de rollengroep heeft gewijzigd en wanneer en welke lidmaatschapsupdates zijn aangebracht. Gebruik dit rapport om wijzigingen bij te houden in de beheerdersmachtigingen die zijn toegewezen aan gebruikers in uw organisatie.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Als u het Exchange-beheercentrum wilt openen, gaat u naar [het Exchange-beheercentrum in de zelfstandige EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- U moet machtigingen toegewezen krijgen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren. U hebt met name de rol  **Auditlogboeken** of Auditlogboeken voor alleen **weergeven** nodig, die standaard zijn toegewezen aan de rollengroepen Organisatiebeheer,  **Compliancebeheer** en Beveiligingsbeheerder. Zie Machtigingen in zelfstandige EOP en gebruik het [EAC](feature-permissions-in-eop.md) om de lijst met leden [in rollengroepen te wijzigen voor meer informatie.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Zie Sneltoetsen voor het [Exchange-beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)voor informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit artikel.

> [!TIP]
> Hebt u problemen? Vraag om hulp op het forum [van Exchange Online Protection.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Het EAC gebruiken om een beheerdersrolgroepsrapport uit te voeren

Voer het rapport beheerdersrolgroep uit om de wijzigingen in beheerrolgroepen binnen een bepaalde periode te vinden.

1. Ga in het Beheerbeheer naar  \> **Auditing** en **kies Een beheerdersrolgroepsrapport uitvoeren.**

2. Configureer **de volgende instellingen op** de pagina Zoeken naar wijzigingen in beheerdersrolgroepen die wordt geopend:

   - **Begindatum** **en einddatum:** voer een datumbereik in. In het rapport wordt standaard gezocht naar wijzigingen die in de afgelopen twee weken zijn aangebracht in beheerdersrolgroepen.

   - **Rollengroepen selecteren:** standaard worden alle rollengroepen doorzocht. Als u de resultaten wilt filteren op specifieke rollengroepen, klikt u **op Rollengroepen selecteren.** Selecteer een rollengroep in het dialoogvenster dat wordt weergegeven en klik op **toevoegen ->.** Herhaal deze stap zo vaak als nodig is en klik op **OK** wanneer u klaar bent.

3. Klik op Zoeken wanneer u klaar **bent.**

Als er wijzigingen worden gevonden aan de hand van de criteria die u hebt opgegeven, worden deze weergegeven in het deelvenster met resultaten. Klik op een rollengroep in de zoekresultaten om de wijzigingen in het detailvenster te bekijken.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u een rapport met beheerdersrolgroepen hebt uitgevoerd, worden rollengroepen die zijn gewijzigd binnen het datumbereik weergegeven in het deelvenster met zoekresultaten. Als er geen resultaten zijn, hebben er geen wijzigingen in rollengroepen plaatsgevonden binnen het opgegeven datumbereik. Als u denkt dat er resultaten moeten zijn, wijzigt u het datumbereik en voer u het rapport opnieuw uit.

## <a name="monitor-changes-to-role-group-membership"></a>Wijzigingen in lidmaatschap van rollengroep controleren

Wanneer leden worden toegevoegd aan of verwijderd uit een rollengroep, geven de zoekresultaten in het detailvenster aan dat het lidmaatschap van de rollengroep is bijgewerkt en dat de huidige leden worden weergegeven. In de resultaten wordt niet expliciet vermeld welke gebruiker is toegevoegd of verwijderd.

Om te bepalen of een gebruiker is toegevoegd of verwijderd, moet u twee afzonderlijke vermeldingen in het rapport vergelijken. Bekijk bijvoorbeeld de volgende logboekgegevens voor de **HelpDesk-rollengroep:**

> 27-1-2018 16:43 uur <br> Administrator (Beheerder) <br> Bijgewerkte leden: Administrator;annb,provider;pilarp <br> 06-02-2018 10:09 uur <br> Administrator (Beheerder) <br> Bijgewerkte leden: Administrator;annb;administratorf;pilarp;tonip <br> 19-2-2018 14:12 uur <br> Administrator (Beheerder) <br> Bijgewerkte leden: Administrator;annb;administratorf;tonip

In dit voorbeeld heeft het gebruikersaccount van de beheerder de volgende wijzigingen aangebracht:

- Op 6-2-2018 is de tonip van de gebruiker toegevoegd.
- Op 19-2-2018 wordt de gebruiker pilarp verwijderd.

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>Zelfstandige Exchange Online PowerShell gebruiken om te zoeken naar vermeldingen in het auditlogboek

U kunt Exchange Online PowerShell gebruiken om te zoeken naar vermeldingen in het auditlogboek die voldoen aan de criteria die u opgeeft. Zie zoekcriteria in [Search-AdminAuditLog voor een lijst met zoekcriteria.](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet) Voor deze procedure wordt de cmdlet **Search-AdminAuditLog** gebruikt en worden zoekresultaten weergegeven in Exchange Online PowerShell. U kunt deze cmdlet gebruiken als u een set resultaten wilt retourneren die de limieten overschrijdt die zijn gedefinieerd voor de cmdlet **New-AdminAuditLogSearch** of in de rapporten van de EAC-auditrapportage.

Gebruik de volgende syntaxis om in het auditlogboek te zoeken naar criteria die u opgeeft.

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> De **cmdlet Search-AdminAuditLog** retourneert standaard maximaal 1000 logboekgegevens. Gebruik de _parameter ResultSize_ om maximaal 250.000 logboekgegevens op te geven. Of gebruik de waarde om `Unlimited` alle items te retourneren.

In dit voorbeeld wordt een zoekopdracht uitgevoerd naar alle vermeldingen in het auditlogboek met de volgende criteria:

- **Begindatum:** 04-08-2018
- **Einddatum:** 3-10-2018
- **Gebruikers-ids:** `davids` `chrisd` , `kima`
- **Cmdlets:** **Set-Mailbox**
- **Parameters:** _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

In dit voorbeeld wordt gezocht naar wijzigingen in een specifiek postvak. Dit is handig als u aan het oplossen van problemen werkt of als u informatie moet geven voor een onderzoek. De volgende criteria worden gebruikt:

- **Begindatum:** 01-05-2018
- **Einddatum:** 3-10-2018
- **Object-id:** contoso.com/Users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

Als uw zoekopdrachten veel logboekgegevens retourneren, raden we u aan de procedure in **Exchange Online PowerShell** te gebruiken om te zoeken naar vermeldingen in het auditlogboek en resultaten te verzenden naar een geadresseerde verderop in dit artikel. Met de procedure in die sectie wordt een XML-bestand als e-mailbijlage verzonden naar de geadresseerden die u opgeeft, zodat u de geïnteresseerde gegevens gemakkelijker kunt extraheren.

Zie [Search-AdminAuditLog voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)

### <a name="view-details-of-audit-log-entries"></a>Details van vermeldingen in het auditlogboek weergeven

De **cmdlet Search-AdminAuditLog** retourneert de velden die worden beschreven in de inhoud van het [auditlogboek.](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents) Van de velden die worden geretourneerd door de cmdlet, bevatten twee velden, **CmdletParameters** en **ModifiedProperties,** aanvullende informatie die niet standaard kan worden weergegeven.

Als u de inhoud van de **velden CmdletParameters** en **ModifiedProperties** wilt weergeven, gebruikt u de volgende stappen. U kunt ook de procedure in **Exchange Online PowerShell** gebruiken om te zoeken naar vermeldingen in het auditlogboek en resultaten te verzenden naar een geadresseerde verderop in dit artikel om een XML-bestand te maken.

Voor deze procedure worden de volgende concepten gebruikt:

- [about_Arrays](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. Bepaal de criteria die u wilt zoeken, voer de cmdlet **Search-AdminAuditLog** uit en sla de resultaten op in een variabele met behulp van de volgende opdracht.

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. Elke auditlogboekinvoer wordt opgeslagen als een matrixelement in de `$Results` variabele. U kunt een matrixelement selecteren door de index van het matrixelement op te geven. Indexen van matrixelementen beginnen bij nul (0) voor het eerste matrixelement. Als u bijvoorbeeld het vijfde matrixelement wilt ophalen, dat een index van 4 bevat, gebruikt u de volgende opdracht.

   ```PowerShell
   $Results[4]
   ```

3. De vorige opdracht retourneert de logboekinvoer die is opgeslagen in matrixelement 4. Gebruik de volgende opdrachten om de inhoud van de velden **CmdletParameters** en **ModifiedProperties** voor deze logboekinvoer te bekijken.

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. Als u de inhoud van de **velden CmdletParameters** of **ModifiedParameters** wilt weergeven in een andere logboekinvoer, wijzigt u de index van het matrixelement.
