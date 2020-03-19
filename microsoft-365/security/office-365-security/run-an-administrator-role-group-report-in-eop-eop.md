---
title: 'Een rapport van een beheerdersrolgroep uitvoeren in EOP '
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
description: Beheerders kunnen leren hoe ze een groeprapport voor beheerdersrollen kunnen uitvoeren in Exchange Online Protection (EOP). In dit rapport wordt logboeken opgesteld wanneer een beheerder leden toevoegt aan of verwijdert uit beheerdersrolgroepen, microsoft Exchange Online Protection (EOP) elke gebeurtenis registreert.
ms.openlocfilehash: d9e7db8accae259b3eb332ce17c52c6749c2bec2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812046"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a>Een rapport van een beheerdersrolgroep uitvoeren in EOP

 Wanneer een beheerder leden toevoegt aan of verwijdert uit beheerdersrolgroepen, registreert Exchange Online Protection (EOP) elke gebeurtenis. Wanneer u een rapport van de beheerdersrolgroep uitvoert in het Exchange-beheercentrum (EAC), worden items weergegeven als zoekresultaten en de betrokken rolgroepen opgenomen, wie het lidmaatschap van de rolgroep heeft gewijzigd en wanneer en welke lidmaatschapsupdates zijn uitgevoerd. Gebruik dit rapport om wijzigingen in de beheerdersmachtigingen te controleren die zijn toegewezen aan gebruikers in uw organisatie.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Geschatte tijd om te voltooien: 2 minuten

- Zie [Exchange-beheercentrum in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md)als u het Exchange-beheercentrum wilt openen.

- U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Zie het gedeelte Rapporten van het onderwerp Functiemachtigingen in het [EOP-onderwerp](feature-permissions-in-eop.md) om te zien welke machtigingen u nodig hebt.

- Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.

> [!TIP]
> Heb je problemen? Vraag om hulp in het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>De EAC gebruiken om een rapport van de beheerdersrolgroep uit te voeren

Voer het rapport administratorrolgroep uit om binnen een bepaald tijdsbestek de wijzigingen in managementrolgroepen in uw organisatie te vinden.

1. Navigeer in de EAC naar **Compliance management** \> **Auditing**en kies Een rapport van **de beheerdersrolgroep uitvoeren.**

2. Kies de **begindatum** en **einddatum**. In het rapport wordt standaard gezocht naar wijzigingen die in de afgelopen twee weken zijn aangebracht in de rolgroepen van beheerders.

3. Als u de wijzigingen voor een specifieke rolgroep wilt weergeven, klikt u op **Rolgroepen selecteren**. Selecteer de rolgroep (of groepen) in het volgende dialoogvenster en klik op **OK**. U het veld ook leeg laten om alle gewijzigde rolgroepen te vinden.

4. Klik op **Zoeken**.

Als er wijzigingen worden gevonden met behulp van de opgegeven criteria, worden deze weergegeven in het resultatenvenster. Klik op een rolgroep in de zoekresultaten om de wijzigingen in het detailvenster weer te geven.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u een rapport van een administratorrolgroep hebt uitgevoerd, worden rolgroepen die zijn gewijzigd binnen het datumbereik weergegeven in het deelvenster zoekresultaten. Als er geen resultaten zijn, hebben er geen wijzigingen in rolgroepen plaatsgevonden binnen het opgegeven datumbereik. Als u denkt dat er resultaten moeten zijn, wijzigt u het datumbereik en voert u het rapport opnieuw uit.

## <a name="monitor-changes-to-role-group-membership"></a>Wijzigingen in het lidmaatschap van rolgroepen controleren

Wanneer leden worden toegevoegd aan of verwijderd uit een rolgroep, geven de zoekresultaten in het detailvenster aan dat het lidmaatschap van de rolgroep is bijgewerkt en worden de huidige leden weergegeven. In de resultaten wordt niet expliciet vermeld welke gebruiker is toegevoegd of verwijderd.

Als u wilt bepalen of een gebruiker is toegevoegd of verwijderd, moet u twee afzonderlijke vermeldingen in het rapport vergelijken. Laten we bijvoorbeeld de volgende logboekvermeldingen voor de **HelpDesk-rolgroep** bekijken:

> 1/27/2018 16:43 <br> Administrator (Beheerder) <br> Bijgewerkte leden: Administrator;annb,florencef;pilarp <br> 2/06/2018 10:09 AM <br> Administrator (Beheerder) <br> Bijgewerkte leden: Administrator;annb;florencef;pilarp;tonip <br> 2/19/2018 14:12 <br> Administrator (Beheerder) <br> Bijgewerkte leden: Administrator;annb;florencef;tonip

In dit voorbeeld heeft het gebruikersaccount van administrator de volgende wijzigingen aangebracht:

- Op 2/06/2018 voegden ze de gebruiker tonip toe.

- Op 2/19/2018 verwijderden ze de gebruiker pilarp.
