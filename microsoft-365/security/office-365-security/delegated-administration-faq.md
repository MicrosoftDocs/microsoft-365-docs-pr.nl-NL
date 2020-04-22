---
title: Veelgestelde vragen over gedelegeerd beheer
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
description: Dit onderwerp biedt veelgestelde vragen en antwoorden voor Microsoft-partners en resellers die gedelegeerde beheertaken willen uitvoeren, waaronder de mogelijkheid om Exchange Online Protection (EOP) voor andere tenants (bedrijven) te beheren.
ms.openlocfilehash: b79c0aba026a8d59aac338ceac0f1c4a60d71c4d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637650"
---
# <a name="delegated-administration-faq"></a>Veelgestelde vragen over gedelegeerd beheer

Dit onderwerp biedt veelgestelde vragen en antwoorden voor Microsoft-partners en resellers die gedelegeerde beheertaken willen uitvoeren, waaronder de mogelijkheid om Exchange Online Protection (EOP) voor andere tenants (bedrijven) te beheren.

**V. Ik ben een reseller en ik moet de huurders van mijn klant beheren; hoe werkt dit?**

A. Als u een Microsoft-partner of -reseller bent en u zich hebt aangemeld om Microsoft-adviseur te zijn, u toestemming vragen om hun tenant te beheren in het beheercentrum. Dit staat bekend als gedelegeerd beheer en hiermee u hun Microsoft 365-tenant (inclusief EOP-instellingen) beheren alsof u een beheerder binnen hun organisatie bent. De stappen voor het uitvoeren van gedelegeerd beheer zijn als volgt:

1. Meld u aan om [Microsoft Office 365-adviseur](https://aka.ms/cloudbenefits)te worden.

2. Meld u aan voor gedelegeerd beheer. Voordat u beginnen met het beheren van het account van een klant, moeten ze u autoriseren als gedelegeerdbeheerder. Om hun goedkeuring te verkrijgen, stuurt u hen eerst [een aanbod voor gedelegeerd beheer.](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e) (U uw klant op een later tijdstip ook gedelegeerd beheer aanbieden.)

3. Maak het gedelegeerde beheerdersaccount met de stappen in Een partner voor [abonnementsadviseur toevoegen, wijzigen of verwijderen.](https://docs.microsoft.com/office365/admin/misc/add-partner)

Partners [bezoeken: bouw uw bedrijf op en beheer het partnerabonnement](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) voor meer informatie over het instellen van gedelegeerd beheer.

**V. Ik ben een klant, geen reseller, hoe kan gedelegeerde beheerder instellen voor mijn subhuurders?**

A. Gedelegeerd beheer is op dit moment alleen beschikbaar voor resellers en partners. We hebben echter een voorbeeld van Windows PowerShell-script waarmee u beleid toepassen op uw subtenants (bedrijven). Zie [Voorbeeldscript voor het toepassen van EOP-instellingen op meerdere tenants](sample-script-for-applying-eop-settings-to-multiple-tenants.md)voor meer informatie.

**V. Kan ik voorkomen dat mijn subtenantbeheerder mijn beleid wijzigt?**

A. Microsoft 365 beschikt momenteel niet over deze mogelijkheid.

**V. Kan ik geconsolideerde rapportage krijgen over al mijn subhuurders?**

A. Geconsolideerde rapportage over de bedrijven die u beheert, is op dit moment niet beschikbaar voor de rapporten van het Microsoft 365-beheercentrum. U dit echter doen met [Microsoft Graph](https://docs.microsoft.com/graph/overview).
