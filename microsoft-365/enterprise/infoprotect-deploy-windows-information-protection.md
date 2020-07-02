---
title: 'Stap 4: Windows-gegevensbescherming configureren'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Informatie en implementatie van Windows-gegevensbescherming in Microsoft 365.
ms.openlocfilehash: c7b76ef28d41810d6e9e45e98adb7a94cf8ae2f4
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005720"
---
# <a name="step-4-configure-windows-information-protection"></a><span data-ttu-id="0c6a4-103">Stap 4: Windows-gegevensbescherming configureren</span><span class="sxs-lookup"><span data-stu-id="0c6a4-103">Step 4: Configure Windows Information Protection</span></span>

<span data-ttu-id="0c6a4-104">*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="0c6a4-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: Gegevensbescherming](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="0c6a4-106">Nu er steeds meer persoonlijke apparaten voor werk worden gebruikt, is er een verhoogd risico dat apps en apparaten vertrouwelijke bedrijfsgegevens lekken.</span><span class="sxs-lookup"><span data-stu-id="0c6a4-106">With more personal devices being used for work, there’s increased risk for apps and devices to leak private organization data.</span></span> <span data-ttu-id="0c6a4-107">Bijvoorbeeld wanneer een werknemer per ongeluk een afbeelding van een marketingplan voor een toekomstig product naar een site voor sociale media stuurt of een bestand met zeer vertrouwelijke informatie op in hun openbare cloudopslag opslaat.</span><span class="sxs-lookup"><span data-stu-id="0c6a4-107">For example, an employee inadvertently sends a picture of a marketing plan for a future product to a social media site or saves a file containing highly confidential information to their public cloud storage.</span></span> 

<span data-ttu-id="0c6a4-108">Met Windows-gegevensbescherming kunt u bescherming bieden tegen dit soort gegevenslekken op Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="0c6a4-108">Windows Information Protection (WIP) helps protect against these types of data leakage on Windows 10 devices.</span></span> <span data-ttu-id="0c6a4-109">Zie voor meer informatie [Uw ondernemingsgegevens beveiligen met Windows-gegevensbescherming](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span><span class="sxs-lookup"><span data-stu-id="0c6a4-109">For more information, see [Protect your enterprise data using WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span></span>

<span data-ttu-id="0c6a4-110">In Microsoft 365 Enterprise is Windows-gegevensbescherming een combinatie van Windows 10 Enterprise en Microsoft Intune, dat inbegrepen is in uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="0c6a4-110">In Microsoft 365 Enterprise, WIP is a combination of Windows 10 Enterprise and Microsoft Intune, which is included with your subscription.</span></span> 

<span data-ttu-id="0c6a4-111">U kunt Windows-gegevensbescherming als volgt in uw organisatie implementeren met Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="0c6a4-111">To deploy WIP in your organization with Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="0c6a4-112">Registreer uw Windows-apparaten bij Intune.</span><span class="sxs-lookup"><span data-stu-id="0c6a4-112">Enroll your Windows devices in Intune.</span></span> <span data-ttu-id="0c6a4-113">U had dit moeten hebben gedaan in [Fase 5: beheer voor mobiele apparaten](mobility-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="0c6a4-113">You should have done this in [Phase 5: Mobile Device Management](mobility-infrastructure.md).</span></span>

2. <span data-ttu-id="0c6a4-114">Maak een [Intune-beleid voor Windows-gegevensbescherming](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span><span class="sxs-lookup"><span data-stu-id="0c6a4-114">Create an [Intune policy for WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span></span>

   -    <span data-ttu-id="0c6a4-115">Controleer of u de lijst met beveiligde apps hebt ingevuld.</span><span class="sxs-lookup"><span data-stu-id="0c6a4-115">Ensure that you have filled out your Protected apps list.</span></span>
  
   - <span data-ttu-id="0c6a4-116">Kies uw Windows-gegevensbeveiligingsniveau.</span><span class="sxs-lookup"><span data-stu-id="0c6a4-116">Choose your WIP protection level.</span></span>

<span data-ttu-id="0c6a4-117">U kunt Windows-gegevensbescherming ook gebruiken met[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-configmgr).</span><span class="sxs-lookup"><span data-stu-id="0c6a4-117">You can also use WIP with [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-configmgr).</span></span> 

<span data-ttu-id="0c6a4-118">Zie [Aanbevolen procedures voor Windows-gegevensbescherming]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0c6a4-118">See [WIP best practices]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) for more information.</span></span>

<span data-ttu-id="0c6a4-119">Zie de [afsluitcriteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) voor deze stap als tussentijds controlepunt.</span><span class="sxs-lookup"><span data-stu-id="0c6a4-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="0c6a4-120">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="0c6a4-120">Next step</span></span>

|||
|:-------|:-----|
|![Stap 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="0c6a4-122">Preventie van gegevensverlies configureren</span><span class="sxs-lookup"><span data-stu-id="0c6a4-122">Configure Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|


