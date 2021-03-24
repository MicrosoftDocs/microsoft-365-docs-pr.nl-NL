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
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen veelgestelde vragen en antwoorden bekijken over gedelegeerde beheertaken in Microsoft 365 voor Microsoft-partners en wederverkopers.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 82fa70a8025f67610032ba59368bc74789b60f84
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058906"
---
# <a name="delegated-administration-faq"></a>Veelgestelde vragen over gedelegeerd beheer

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Dit artikel bevat veelgestelde vragen en antwoorden over gedelegeerde beheertaken in Microsoft 365 voor Microsoft-partners en wederverkopers. Gedelegeerd beheer omvat de mogelijkheid om EOP-instellingen (Exchange Online Protection) voor andere tenants (bedrijven) te beheren.

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>Ik ben een wederverkoper en ik moet mijn klantten tenants beheren. Hoe werkt dit?

Als u een Microsoft-partner of wederverkoper bent en u zich hebt aangemeld om een Microsoft-adviseur te worden, kunt u gedelegeerde beheermogelijkheden aanvragen in _de_ Microsoft 365-organisatie van uw klant.

Met gedelegeerd beheer kunt u Microsoft 365 (inclusief EOP-instellingen) beheren alsof u een beheerder binnen die organisatie bent. De stappen voor het configureren van gedelegeerd beheer worden in de volgende lijst beschreven:

1. Meld u aan als adviseur van [Microsoft Office 365.](https://partner.microsoft.com/?cloudbenefits)

2. Meld u aan voor gedelegeerd beheer. Voordat u de tenant van een klant kunt beheren, moet deze u machtigen als gedelegeerde beheerder. Om hun goedkeuring te verkrijgen, stuurt [u ze eerst een aanbieding voor gedelegeerd beheer.](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e) U kunt ook gedelegeerd beheer aanbieden aan uw klant op een later tijdstip.

3. Maak het gedelegeerde beheerdersaccount met de stappen in Een partner voor abonnementsadviseur [toevoegen, wijzigen of verwijderen.](../../admin/misc/add-partner.md)

Ga [naar Partners: Bouw uw bedrijf en beheer partnerabonnement voor](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) meer informatie over het instellen van gedelegeerd beheer.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>Ik ben een klant, geen wederverkoper. Hoe kan ik gedelegeerde beheerder instellen voor mijn subtenants?

Gedelegeerd beheer is alleen beschikbaar voor wederverkopers en partners. Er is echter een voorbeeldscript van PowerShell dat u helpt beleid toe te passen op uw subtenants (bedrijven). Zie Voorbeeldscript voor het toepassen van [EOP-instellingen op meerdere tenants voor meer informatie.](sample-script-for-applying-eop-settings-to-multiple-tenants.md)

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>Kan ik voorkomen dat mijn subtenantbeheerder mijn beleid wijzigt?

Nee. Microsoft 365 heeft deze mogelijkheid momenteel niet.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>Kan ik samengevoegde rapporten krijgen over al mijn subtenants?

Geconsolideerde rapportage voor alle bedrijven die u beheert, is niet beschikbaar in microsoft 365-beheercentrumrapporten. U kunt echter rapporten krijgen met Behulp van [Microsoft Graph.](/graph/overview)