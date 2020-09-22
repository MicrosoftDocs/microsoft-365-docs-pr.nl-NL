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
description: Beheerders kunnen Veelgestelde vragen en antwoorden over gedelegeerde beheertaken weergeven in Microsoft 365 voor Microsoft-partners en resellers.
ms.openlocfilehash: 6729f276e6afea83568ca59d3bf48c08fcd837d2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203141"
---
# <a name="delegated-administration-faq"></a>Veelgestelde vragen over gedelegeerd beheer

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Dit artikel bevat veelgestelde vragen en antwoorden over gedelegeerd beheertaken in Microsoft 365 voor Microsoft-partners en resellers. Gedelegeerd beheer bevat de mogelijkheid om de EOP-instellingen (Exchange Online Protection) voor andere tenants (bedrijven) te beheren.

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>Ik ben een wederverkoper en ik wil mijn tenants van mijn klanten beheren. Hoe werkt dit?

Als u een Microsoft-partner of-wederverkoper bent en u zich hebt aangemeld voor een Microsoft-adviseur, kunt u _gedelegeerde beheer_ mogelijkheden aanvragen in de microsoft 365-organisatie van uw klant.

Gedelegeerd beheer Hiermee kunt u Microsoft 365 (waaronder EOP-instellingen) beheren alsof u een beheerder binnen de organisatie bent. De stappen voor het configureren van gedelegeerd beheer worden beschreven in de volgende lijst:

1. Meld u aan als een [Microsoft Office 365-adviseur](https://aka.ms/cloudbenefits).

2. Registreer u voor gedelegeerd beheer. Voordat u de Tenant van een klant kunt gaan beheren, moet ze u machtigen als gedelegeerde beheerder. Voor een goedkeuring stuurt u eerst [een aanbieding voor gedelegeerd beheer](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). U kunt ook op een later tijdstip gedelegeerd beheer bieden aan uw klant.

3. Maak het gedelegeerde beheerdersaccount met behulp van de stappen in [een abonnements adviseur toevoegen, wijzigen of verwijderen](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).

Ga naar [partners: uw abonnement voor bedrijven en partners samenstellen en beheren](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) voor meer informatie over het instellen van gedelegeerd beheer.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>Ik ben een klant, geen wederverkoper. Hoe kan gedelegeerde beheerder worden ingesteld voor mijn subtenants?

Gedelegeerd beheer is alleen beschikbaar voor wederverkopers en partners. Er is echter een voorbeeld van een PowerShell-script waarmee u beleidsregels kunt toepassen op uw subtenants (bedrijven). Zie voor meer informatie [voorbeeldscript voor het toepassen van EOP-instellingen op meerdere tenants](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>Kan ik voorkomen dat mijn subtenant beheerder mijn beleid wijzigt?

Nee. Microsoft 365 biedt momenteel geen mogelijkheid.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>Kan ik op al mijn subtenants rapporteren?

De rapportage van de bedrijven die u beheert, is niet beschikbaar in de rapporten van het Microsoft 365-Beheercentrum. U kunt echter wel rapporten met [Microsoft Graph](https://docs.microsoft.com/graph/overview)weergeven.
