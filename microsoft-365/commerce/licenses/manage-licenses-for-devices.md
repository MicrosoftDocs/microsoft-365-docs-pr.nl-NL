---
title: Licenties voor apparaten beheren
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: 1a525117c25a2471ad696ef1447fd7e4ccb6bed0
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011183"
---
# <a name="manage-licenses-for-devices"></a>Licenties voor apparaten beheren

Als u Microsoft 365 Apps voor bedrijven (apparaat) of Microsoft 365 Apps for Education (apparaat) hebt, u licenties toewijzen aan apparaten met behulp van Azure AD-groepen. Wanneer een apparaat een licentie heeft, kan iedereen die dat apparaat gebruikt Microsoft 365 Apps voor bedrijven gebruiken (voorheen Office 365 ProPlus genoemd). Stel dat u 20 laptops en tablets hebt die door mensen in uw organisatie worden gebruikt. Wanneer u een licentie aan elk apparaat toewijst, gebruikt elke persoon die zich aanmeldt bij een van de apparaten Microsoft 365 Apps voor bedrijven zonder de noodzaak van een eigen licentie.

> [!IMPORTANT]
> Apparaatgebaseerde licenties voor Microsoft 365 Apps for Enterprise zijn alleen beschikbaar als add-on licentie voor sommige commerciële klanten en sommige klanten in het onderwijs. Voor commerciële klanten is de licentie *Microsoft 365 Apps for Enterprise (apparaat)* en is deze alleen beschikbaar via enterprise agreement/enterprise agreement subscription. Voor onderwijsklanten is de licentie *Microsoft 365 Apps for Education (apparaat)* en alleen beschikbaar via Inschrijving voor Onderwijsoplossingen (EES). Voor meer informatie, lees de blogpost over [de beschikbaarheid van het onderwijs](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/). Neem voor commerciële beschikbaarheid contact op met uw Microsoft-accountvertegenwoordiger.

Om te beginnen maakt u een groep in het Azure Active Directory-beheercentrum en wijst u apparaten toe aan de groep. Zie [Apparaatgebaseerde licenties voor Microsoft 365 Apps voor bedrijven](https://go.microsoft.com/fwlink/p/?linkid=2094216)voor meer informatie over apparaatlicenties, waaronder apparaatvereisten, welke typen groepen u gebruiken en hoe u Microsoft 365 Apps for Enterprise configureren om apparaatlicenties te gebruiken.

> [!IMPORTANT]
> U moet een globale beheerder zijn om de taken in dit artikel te voltooien.

## <a name="assign-licenses-to-devices"></a>Licenties toewijzen aan apparaten

Wanneer u licenties aan een groep toewijst, wijst u licenties toe aan alle apparaten binnen de groep. U slechts één abonnement toewijzen aan één groep.

1. Ga in het Microsoft 365-beheercentrum naar de pagina **Factureringslicenties.** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a>
2. Kies **op** de pagina Licenties de optie **Microsoft 365 Apps for Education (apparaat)** of **Microsoft 365 Apps for Enterprise (apparaat).**
3. Kies op de volgende pagina een abonnement en kies **Licenties toewijzen.**
4. Begin in het **groepsvenster licenties toewijzen aan een groepsvenster** met het typen van een groepsnaam en kies deze vervolgens uit de resultaten om deze aan de lijst toe te voegen.
5. Kies **Toewijzen**en kies **Sluiten**.

## <a name="unassign-licenses-from-devices"></a>Licenties van apparaten ongedaan maken

Wanneer u licenties uit een groep ongedaan maakt, verwijdert u de licenties van alle apparaten binnen de groep. Alle apps en de bijbehorende gegevens zijn dan alleen-lezen.

1. Ga in het beheercentrum naar de pagina **Factureringslicenties.** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a>
2. Kies **op** de pagina Licenties de optie **Microsoft 365 Apps for Education (apparaat)** of **Microsoft 365 Apps for Enterprise (apparaat).**
3. Kies op de volgende pagina een abonnement, kies **Meer acties**en kies **Licenties ongedaan maken**.
4. Kies in het dialoogvenster **Licenties zonder toewijzing** de optie **Niet-toewijzen**.