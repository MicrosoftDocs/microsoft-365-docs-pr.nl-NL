---
title: Licenties voor apparaten beheren
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: Meer informatie over het toewijzen van licenties aan groepen voor gebruik met apparaten.
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: a316810e3e6ddb1373697dc56b2fccb5a32cf0b1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911480"
---
# <a name="manage-licenses-for-devices"></a>Licenties voor apparaten beheren

Als u Microsoft 365 Apps voor ondernemingen (apparaat) of Microsoft 365 Apps voor Onderwijs (apparaat) hebt, kunt u licenties toewijzen aan apparaten met Azure AD-groepen. Wanneer een apparaat een licentie heeft, kan iedereen die dat apparaat gebruikt Microsoft 365 Apps voor ondernemingen gebruiken (eerder Office 365 ProPlus genoemd). Stel dat u 20 laptops en tablets hebt die worden gebruikt door personen in uw organisatie. Wanneer u een licentie toewijst aan elk apparaat, gebruikt elke persoon die zich aanmeldt bij een van de apparaten Microsoft 365 Apps voor bedrijven zonder dat er een eigen licentie voor nodig is.

> [!IMPORTANT]
> Apparaatlicenties voor Microsoft 365 Apps voor ondernemingen zijn alleen beschikbaar als een invoeglicentie voor sommige commerciële klanten en sommige klanten in het onderwijs. Voor commerciële klanten is de licentie *Microsoft 365 Apps voor ondernemingen (apparaat)* en is deze alleen beschikbaar via Enterprise Agreement/Enterprise Agreement Subscription. Voor onderwijsklanten is de licentie *Microsoft 365 Apps voor onderwijs (apparaat)* en is deze alleen beschikbaar via Inschrijving voor Education Solutions (EES). Lees het blogbericht over beschikbaarheid [van onderwijs voor meer informatie.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/) Neem voor commerciële beschikbaarheid contact op met de vertegenwoordiger van uw Microsoft-account.

Om te beginnen maakt u een groep in het Azure Active Directory-beheercentrum en wijst u vervolgens apparaten toe aan de groep. Zie Apparaatlicenties voor [Microsoft 365 Apps](/deployoffice/device-based-licensing)voor bedrijven voor meer informatie over apparaatlicenties, inclusief apparaatvereisten, welke typen groepen u kunt gebruiken en hoe u Microsoft 365 Apps voor ondernemingen kunt configureren voor het gebruik van apparaatlicenties.

> [!IMPORTANT]
> U moet een globale beheerder zijn om de taken in dit artikel uit te voeren.

## <a name="assign-licenses-to-devices"></a>Licenties toewijzen aan apparaten

Wanneer u licenties aan een groep toewijst, wijst u licenties toe aan alle apparaten binnen de groep. U kunt slechts één abonnement toewijzen aan één groep.

1. Ga in het Microsoft 365-beheercentrum naar de pagina   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Factureringslicenties.</a>
2. Kies op **de pagina** Licenties de optie **Microsoft 365 Apps voor onderwijs (apparaat)** of **Microsoft 365 Apps voor ondernemingen (apparaat).**
3. Kies op de volgende pagina een abonnement en kies **vervolgens Licenties toewijzen.**
4. Typ een **groepsnaam** in het deelvenster Licenties toewijzen aan een groep en kies deze in de resultaten om deze toe te voegen aan de lijst.
5. Kies **Toewijzen** en kies **vervolgens Sluiten.**

## <a name="unassign-licenses-from-devices"></a>Licenties van apparaten niet toewijzen

Wanneer u licenties uit een groep opwijst, verwijdert u de licenties van alle apparaten binnen de groep. Alle apps en bijbehorende gegevens worden vervolgens alleen-lezen.

1. Ga in het beheercentrum naar de pagina   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Factureringslicenties.</a>
2. Kies op **de pagina** Licenties de optie **Microsoft 365 Apps voor onderwijs (apparaat)** of **Microsoft 365 Apps voor ondernemingen (apparaat).**
3. Kies op de volgende pagina een abonnement, kies **Meer acties** en kies vervolgens Licenties **niet toewijzen.**
4. Kies in **het dialoogvenster** Licenties niet toewijzen de optie **Niet toewijzen.**