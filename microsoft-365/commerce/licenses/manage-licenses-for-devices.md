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
ms.openlocfilehash: 29bd56ccff01d8c21cc67d1188fa21e338fb4b7e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638181"
---
# <a name="manage-licenses-for-devices"></a>Licenties voor apparaten beheren

Als u Microsoft 365-apps hebt voor Enterprise (hardware) of Microsoft 365-apps voor onderwijs (apparaat), kunt u licenties toewijzen aan apparaten via Azure AD-groepen. Wanneer een apparaat een licentie heeft, kan iedereen die dit apparaat gebruikt, Microsoft 365-apps gebruiken voor Enterprise (eerder Office 365 ProPlus). Stel, u hebt 20 laptops en tablets die door mensen in uw organisatie worden gebruikt. Wanneer u aan elk apparaat een licentie toewijst, gebruikt elke persoon die zich aanmeldt op een van de apparaten Microsoft 365-apps voor Enterprise zonder dat u een licentie nodig hebt.

> [!IMPORTANT]
> Licenties op basis van apparaten op basis van Microsoft 365-apps voor ondernemingen is alleen beschikbaar als een licentie voor de invoegtoepassing voor sommige commerciële klanten en sommige education-klanten. Voor commerciële klanten is de licentie *Microsoft 365-apps voor Enterprise (apparaat)* en is alleen beschikbaar via een Enterprise Agreement/Enterprise Agreement-abonnement. Voor onderwijs klanten is de licentie *Microsoft 365-apps voor onderwijs (apparaat)* en is alleen beschikbaar via inschrijving voor onderwijs oplossingen (EES). Lees voor meer informatie het blogbericht over de [beschikbaarheid](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/)van de opleiding. Neem contact op met de vertegenwoordiger van uw Microsoft-account voor commerciële beschikbaarheid.

Als u wilt beginnen, maakt u een groep in het Azure Active Directory-Beheercentrum en wijst u vervolgens apparaten toe aan de groep. Zie [licenties voor Microsoft 365-apps voor ondernemingen voor](https://go.microsoft.com/fwlink/p/?linkid=2094216)meer informatie over licenties voor apparaten, waaronder hardwarevereisten, welke soorten groepen u kunt gebruiken en hoe u microsoft 365-apps voor Enterprise kunt configureren voor het gebruik van licenties voor het gebruik van een apparaat.

> [!IMPORTANT]
> U moet een globale beheerder zijn om de taken in dit artikel uit te voeren.

## <a name="assign-licenses-to-devices"></a>Licenties toewijzen aan apparaten

Wanneer u licenties toewijst aan een groep, kunt u een licentie toewijzen aan alle apparaten in de groep. U kunt slechts één abonnement toewijzen aan een enkele groep.

1. Ga in het Microsoft 365-Beheercentrum naar de pagina **facturerings**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenties</a> .
2. Kies op de pagina **licenties** de optie **Microsoft 365 apps for education (hardware)** of **Microsoft 365-apps voor Enterprise (apparaat)**.
3. Kies een abonnement op de volgende pagina en kies vervolgens **licenties toewijzen**.
4. In het deelvenster **licenties toewijzen aan een groep** begint u met het typen van de naam van een groep en kiest u deze van de resultaten om deze aan de lijst toe te voegen.
5. Kies **toewijzen**en kies vervolgens **sluiten**.

## <a name="unassign-licenses-from-devices"></a>Licenties van apparaten intrekken

Wanneer u licenties van een groep intrekken, verwijdert u de licenties van alle apparaten in de groep. Alle apps en de bijbehorende gegevens zijn dan alleen-lezen.

1. Ga in het Beheercentrum naar de pagina **factuur**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenties</a> .
2. Kies op de pagina **licenties** de optie **Microsoft 365 apps for education (hardware)** of **Microsoft 365-apps voor Enterprise (apparaat)**.
3. Kies een abonnement op de volgende pagina, kies **meer acties**en kies vervolgens **licenties intrekken**.
4. Kies in het dialoogvenster **licenties intrekken** de optie **intrekken opheffen**.