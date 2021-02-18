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
description: Beheerders kunnen veelgestelde vragen en antwoorden over taken voor gedelegeerd beheer bekijken in Microsoft 365 voor partners en wederverkopers van Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 971572f8bff80da6dd63bed8958112332292feb9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288357"
---
# <a name="delegated-administration-faq"></a>Veelgestelde vragen over gedelegeerd beheer

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Dit artikel bevat veelgestelde vragen en antwoorden over taken voor gedelegeerd beheer in Microsoft 365 voor partners en wederverkopers van Microsoft. Gedelegeerd beheer omvat de mogelijkheid om Instellingen voor Exchange Online Protection (EOP) te beheren voor andere tenants (bedrijven).

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>Ik ben een wederverkoper en ik moet mijn klantten tenants beheren. Hoe werkt dit?

Als u een Microsoft-partner of -wederverkoper bent en u zich hebt  aangemeld als adviseur van Microsoft, kunt u functionaliteit voor gedelegeerd beheer aanvragen in de Microsoft 365-organisatie van uw klant.

Met gedelegeerd beheer kunt u Microsoft 365 beheren (inclusief EOP-instellingen) alsof u een beheerder binnen die organisatie bent. De stappen voor het configureren van gedelegeerd beheer worden in de volgende lijst beschreven:

1. Meld u aan als [Adviseur voor Microsoft Office 365.](https://aka.ms/cloudbenefits)

2. Meld u aan voor gedelegeerd beheer. Voordat u de tenant van een klant kunt beheren, moet deze u machtigen als gedelegeerde beheerder. Om toestemming te krijgen, moet u [ze eerst een aanbieding voor gedelegeerd beheer sturen.](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e) U kunt ook op een later tijdstip gedelegeerd beheer bieden aan uw klant.

3. Maak het account voor gedelegeerde beheerders aan met behulp van de stappen in Een abonnementsadviseur toevoegen, wijzigen [of verwijderen.](../../admin/misc/add-partner.md)

Ga [naar Partners: Bouw uw bedrijf op en beheer het partnerabonnement](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) voor meer informatie over het instellen van gedelegeerd beheer.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>Ik ben een klant, geen wederverkoper. Hoe kan ik gedelegeerde beheerder instellen voor mijn subtenants?

Gedelegeerd beheer is alleen beschikbaar voor wederverkopers en partners. Er is echter een PowerShell-voorbeeldscript om u te helpen beleid toe te passen op uw subtenants (bedrijven). Zie voorbeeldscript voor het toepassen van [EOP-instellingen op meerdere tenants voor meer informatie.](sample-script-for-applying-eop-settings-to-multiple-tenants.md)

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>Kan ik voorkomen dat mijn subtenantbeheerder mijn beleid wijzigt?

Nee. Deze mogelijkheid is momenteel niet beschikbaar in Microsoft 365.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>Kan ik samengevoegde rapportage krijgen voor al mijn subtenants?

Samengevoegde rapportage van de bedrijven die u beheert, is niet beschikbaar in rapporten in het Microsoft 365-beheercentrum. U kunt echter wel rapporten krijgen met behulp van [Microsoft Graph.](https://docs.microsoft.com/graph/overview)
