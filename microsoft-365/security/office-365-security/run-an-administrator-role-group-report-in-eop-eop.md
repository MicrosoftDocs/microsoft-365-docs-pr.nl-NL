---
title: Een rapport over groepen met beheerdersrollen uitvoeren in EOP
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
description: In dit artikel leert u hoe u een rapport met een beheerdersrolgroep uitvoert in Exchange Online Protection (EOP).
ms.openlocfilehash: d3c4db8079a71ba054f323617d3ade65083a3a04
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034454"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a>Een rapport over groepen met beheerdersrollen uitvoeren in EOP

 Wanneer een beheerder leden toevoegt aan of verwijdert uit beheerdersrolgroepen, registreert Exchange Online Protection (EOP) elke gebeurtenis. Wanneer u een rapport met een beheerdersrolgroep uitvoert in het Exchange-beheercentrum (EAC), worden items weergegeven als zoekresultaten en worden de betrokken rolgroepen opgenomen, wie het lidmaatschap van de rolgroep heeft gewijzigd en wanneer en welke lidmaatschapsupdates zijn uitgevoerd. Gebruik dit rapport om wijzigingen in de beheerdersmachtigingen te controleren die zijn toegewezen aan gebruikers in uw organisatie.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Geschatte tijd om te voltooien: 2 minuten

- Zie [Exchange-beheercentrum in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md)als u het Exchange-beheercentrum wilt openen.

- U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Zie het gedeelte 'Rapporten' van het onderwerp [Functiemachtigingen in het EOP-onderwerp](feature-permissions-in-eop.md) om te zien welke machtigingen u nodig hebt.

- Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.

> [!TIP]
> Heb je problemen? Vraag om hulp op het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>De EAC gebruiken om een rapport van een beheerdersrolgroep uit te voeren

Voer het rapport van de groep beheerdersrollen uit om de wijzigingen in beheerrolgroepen in uw organisatie binnen een bepaald tijdsbestek te vinden.

1. Navigeer in de EAC naar \> **Compliancemanagementcontrole**en kies **Een rapport met een beheerdersrolgroep uitvoeren**. **Compliance management**

2. Kies de **begindatum** en **einddatum**. Standaard wordt in het rapport gezocht naar wijzigingen die in de afgelopen twee weken zijn aangebracht in beheerdersrolgroepen.

3. Als u de wijzigingen voor een specifieke rolgroep wilt weergeven, klikt u op **Rolgroepen selecteren**. Selecteer de rolgroep (of groepen) in het volgende dialoogvenster en klik op **OK**. U het veld ook leeg laten om alle gewijzigde rolgroepen te vinden.

4. Klik **op Zoeken**.

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
