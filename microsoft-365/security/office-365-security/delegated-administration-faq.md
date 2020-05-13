---
title: Veelgestelde vragen over gedelegeerd beheer
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
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: Dit onderwerp bevat veelgestelde vragen en antwoorden voor Microsoft-partners en resellers die gedelegeerde Microsoft 365-beheertaken willen uitvoeren.
ms.openlocfilehash: d1522973292b290fd9f66f534ca23aeaa55ee756
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209521"
---
# <a name="delegated-administration-faq"></a>Veelgestelde vragen over gedelegeerd beheer

Dit onderwerp biedt veelgestelde vragen en antwoorden voor Microsoft-partners en resellers die gedelegeerde beheertaken willen uitvoeren, waaronder de mogelijkheid om Exchange Online Protection (EOP) voor andere tenants (bedrijven) te beheren.

## <a name="im-a-reseller-and-i-need-to-manage-my-customers-tenants-how-does-this-work"></a>Ik ben een reseller en ik moet de huurders van mijn klant beheren; hoe werkt dit?

Als u een Microsoft-partner of -reseller bent en u zich hebt aangemeld om Microsoft-adviseur te zijn, u toestemming vragen om hun tenant te beheren in het beheercentrum. Dit staat bekend als gedelegeerd beheer en hiermee u hun Microsoft 365-tenant (inclusief EOP-instellingen) beheren alsof u een beheerder binnen hun organisatie bent. De stappen voor het uitvoeren van gedelegeerd beheer zijn als volgt:

1. Meld u aan om [Microsoft Office 365-adviseur](https://aka.ms/cloudbenefits)te worden.

2. Meld u aan voor gedelegeerd beheer. Voordat u beginnen met het beheren van het account van een klant, moeten ze u autoriseren als gedelegeerdbeheerder. Om hun goedkeuring te verkrijgen, stuurt u hen eerst [een aanbod voor gedelegeerd beheer.](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e) (U uw klant op een later tijdstip ook gedelegeerd beheer aanbieden.)

3. Maak het gedelegeerde beheerdersaccount met de stappen in Een partner voor [abonnementsadviseur toevoegen, wijzigen of verwijderen.](https://docs.microsoft.com/office365/admin/misc/add-partner)

Partners [bezoeken: bouw uw bedrijf op en beheer het partnerabonnement](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) voor meer informatie over het instellen van gedelegeerd beheer.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-sub-tenants"></a>Ik ben een klant, geen reseller, hoe kan gedelegeerde beheerder instellen voor mijn subhuurders?

Gedelegeerd beheer is op dit moment alleen beschikbaar voor resellers en partners. We hebben echter een voorbeeld van Windows PowerShell-script waarmee u beleid toepassen op uw subtenants (bedrijven). Zie [Voorbeeldscript voor het toepassen van EOP-instellingen op meerdere tenants](sample-script-for-applying-eop-settings-to-multiple-tenants.md)voor meer informatie.

## <a name="can-i-prevent-my-sub-tenant-admin-from-modifying-my-policy"></a>Kan ik voorkomen dat mijn subtenantbeheerder mijn beleid wijzigt?

Microsoft 365 beschikt momenteel niet over deze mogelijkheid.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-sub-tenants"></a>Kan ik geconsolideerde rapportage krijgen voor al mijn subhuurders?

Geconsolideerde rapportage over de bedrijven die u beheert, is op dit moment niet beschikbaar voor de rapporten van het Microsoft 365-beheercentrum. U dit echter doen met [Microsoft Graph](https://docs.microsoft.com/graph/overview).
