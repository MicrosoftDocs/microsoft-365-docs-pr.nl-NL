---
title: Veelgestelde vragen over gedelegeerd beheer
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: Dit onderwerp bevat veelgestelde vragen en antwoorden voor Microsoft-partners en resellers die gedelegeerde Microsoft 365-beheertaken willen uitvoeren.
ms.openlocfilehash: 01781437bbc7e8fe5c035ea23e4392e734e0231f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827085"
---
# <a name="delegated-administration-faq"></a>Veelgestelde vragen over gedelegeerd beheer

In dit onderwerp vindt u veelgestelde vragen en antwoorden voor Microsoft-partners en resellers die gedelegeerd beheertaken willen uitvoeren, waaronder de mogelijkheid om Exchange Online Protection (EOP) te beheren voor andere tenants (bedrijven).

## <a name="im-a-reseller-and-i-need-to-manage-my-customers-tenants-how-does-this-work"></a>Ik ben een wederverkoper en ik moet de tenants van mijn klant beheren. Hoe werkt dit?

Als u een Microsoft-partner of-wederverkoper bent en u zich hebt aangemeld voor een Microsoft-adviseur, kunt u toestemming vragen om hun Tenant te beheren in het Beheercentrum. Dit is een zogehets beheer van gedelegeerden en biedt u de mogelijkheid hun Microsoft 365-Tenant (met inbegrip van de EOP-instellingen) te beheren alsof u een beheerder binnen hun organisatie bent. De stappen voor het uitvoeren van gedelegeerd beheer zijn als volgt:

1. Meld u aan als een [Microsoft Office 365-adviseur](https://aka.ms/cloudbenefits).

2. Registreer u voor gedelegeerd beheer. Voordat u het account van een klant kunt beheren, moet ze u machtigen als gedelegeerde beheerder. Voor een goedkeuring stuurt u eerst [een aanbieding voor gedelegeerd beheer](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). (U kunt op een later tijdstip gedelegeerd beheer bieden aan uw klant.)

3. Maak het gedelegeerde beheerdersaccount met behulp van de stappen in [een abonnements adviseur toevoegen, wijzigen of verwijderen](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).

Ga naar [partners: uw abonnement voor bedrijven en partners samenstellen en beheren](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) voor meer informatie over het instellen van gedelegeerd beheer.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-sub-tenants"></a>Ik ben een klant, geen wederverkoper, en hoe kan gedelegeerde beheerder worden ingesteld voor mijn subtenants?

Gedelegeerd beheer is op dit moment alleen beschikbaar voor wederverkopers en partners. We hebben echter een voorbeeld van een Windows PowerShell-script gegeven waarmee u beleidsregels kunt toepassen op subtenants (bedrijven). Zie voor meer informatie [voorbeeldscript voor het toepassen van EOP-instellingen op meerdere tenants](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

## <a name="can-i-prevent-my-sub-tenant-admin-from-modifying-my-policy"></a>Kan ik voorkomen dat mijn subtenant beheerder mijn beleid wijzigt?

Microsoft 365 biedt momenteel geen mogelijkheid.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-sub-tenants"></a>Kan ik uitgaand rapporteren in al mijn subtenants?

U kunt op dit moment niet in de rapporten van het Microsoft 365-Beheercentrum rapporteren. U kunt dit echter doen met [Microsoft Graph](https://docs.microsoft.com/graph/overview).
