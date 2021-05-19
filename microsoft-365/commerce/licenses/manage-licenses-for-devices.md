---
title: Licenties voor apparaten beheren
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: shegu, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: Meer informatie over het toewijzen van licenties aan groepen voor gebruik met apparaten.
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_licensing
search.appverid: MET150
ms.date: 03/17/2021
ms.openlocfilehash: c590c2d47699c4c3cbea4b5145bea9e7c9fc79ec
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535660"
---
# <a name="manage-licenses-for-devices"></a>Licenties voor apparaten beheren

Als u een Microsoft 365-apps voor ondernemingen (apparaat) of Microsoft 365-apps voor Onderwijs (apparaat) hebt, kunt u licenties toewijzen aan apparaten met Azure AD-groepen. Wanneer een apparaat een licentie heeft, kan iedereen die dat apparaat gebruikt, Microsoft 365-apps voor ondernemingen gebruiken (eerder benoemd Office 365 ProPlus). Stel dat u 20 laptops en tablets hebt die worden gebruikt door personen in uw organisatie. Wanneer u een licentie toewijst aan elk apparaat, gebruikt elke persoon die zich aanmeldt bij een van de apparaten Microsoft 365-apps voor ondernemingen zonder dat er een eigen licentie nodig is.

> [!IMPORTANT]
> Apparaatlicenties voor Microsoft 365-apps voor ondernemingen is alleen beschikbaar als invoeglicentie voor sommige commerciële klanten en sommige klanten van het onderwijs. Voor commerciële klanten is de licentie Microsoft 365-apps voor ondernemingen *(apparaat)* en is deze alleen beschikbaar via Enterprise Agreement/Enterprise Agreement-abonnement. Voor onderwijsklanten is de licentie Microsoft 365-apps voor onderwijs *(apparaat)* en is deze alleen beschikbaar via Inschrijving voor Education Solutions (EES). Lees het blogbericht over beschikbaarheid [van onderwijs voor meer informatie.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education) Neem voor commerciële beschikbaarheid contact op met de vertegenwoordiger van uw Microsoft-account.

Om te beginnen maakt u een groep in het Azure Active Directory beheercentrum en wijst u vervolgens apparaten toe aan de groep. Zie Apparaatlicenties voor Microsoft 365-apps voor ondernemingen voor meer informatie over apparaatlicenties, inclusief apparaatvereisten, welke typen groepen u kunt gebruiken en hoe u Microsoft 365-apps voor ondernemingen [Microsoft 365-apps voor ondernemingen](/deployoffice/device-based-licensing)configureert voor het gebruik van apparaatlicenties.

> [!IMPORTANT]
> U moet een globale beheerder zijn om de taken in dit artikel uit te voeren.

## <a name="assign-licenses-to-devices"></a>Licenties toewijzen aan apparaten

Wanneer u licenties aan een groep toewijst, wijst u licenties toe aan alle apparaten binnen de groep. U kunt slechts één abonnement toewijzen aan één groep.

1. Ga in Microsoft 365 beheercentrum naar de pagina   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Factureringslicenties.</a>
2. Kies op **de pagina** Licenties de Microsoft 365-apps voor **onderwijs (apparaat)** of **Microsoft 365-apps voor ondernemingen (apparaat)**.
3. Kies op de volgende pagina een abonnement en kies **vervolgens Licenties toewijzen.**
4. Typ een **groepsnaam** in het deelvenster Licenties toewijzen aan een groep en kies deze in de resultaten om deze toe te voegen aan de lijst.
5. Kies **Toewijzen** en kies **vervolgens Sluiten.**

## <a name="unassign-licenses-from-devices"></a>Licenties van apparaten niet toewijzen

Wanneer u licenties uit een groep opwijst, verwijdert u de licenties van alle apparaten binnen de groep. Alle apps en bijbehorende gegevens worden vervolgens alleen-lezen.

1. Ga in het beheercentrum naar de pagina   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Factureringslicenties.</a>
2. Kies op **de pagina** Licenties de Microsoft 365-apps voor **onderwijs (apparaat)** of **Microsoft 365-apps voor ondernemingen (apparaat)**.
3. Kies op de volgende pagina een abonnement, selecteer de drie puntjes (meer acties) en kies vervolgens Licenties niet **toewijzen.**
4. Kies in **het dialoogvenster** Licenties niet toewijzen de optie **Niet toewijzen.**
