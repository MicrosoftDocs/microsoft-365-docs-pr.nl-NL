---
title: Gebruikers omleiden van het Office 365 beveiligings- en compliancecentrum naar het Microsoft 365-compliancecentrum
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: Meer informatie over het automatisch omleiden Office 365 beveiligings- en compliancecentrumgebruikers naar de Microsoft 365-compliancecentrum..
ms.collection: M365-security-compliance
ms.openlocfilehash: 62fc302f9f065ac7bb0475a6e72dc240a56a1fe1
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339404"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="851e8-103">Gebruikers omleiden van het Office 365 beveiligings- en compliancecentrum naar het Microsoft 365-compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="851e8-103">Redirect users from the Office 365 Security and Compliance center to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="851e8-104">In dit artikel wordt uitgelegd hoe automatische omleiding werkt voor gebruikers die toegang hebben tot complianceoplossingen van het Office 365 Security and Compliance Center (protection.office.com) tot de Microsoft 365-compliancecentrum (compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="851e8-104">This article explains how automatic redirection works for users accessing compliance solutions from the Office 365 Security and Compliance Center (protection.office.com) to the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="851e8-105">Wat u kunt verwachten</span><span class="sxs-lookup"><span data-stu-id="851e8-105">What to expect</span></span>

<span data-ttu-id="851e8-106">Automatische omleiding is standaard ingeschakeld voor alle gebruikers die toegang hebben tot de volgende compliancegerelateerde oplossingen in Office 365 Security and Compliance (protection.office.com):</span><span class="sxs-lookup"><span data-stu-id="851e8-106">Automatic redirection is enabled by default for all users accessing the following compliance-related solutions in Office 365 Security and Compliance (protection.office.com):</span></span>

- <span data-ttu-id="851e8-107">Preventie van gegevensverlies (DLP)</span><span class="sxs-lookup"><span data-stu-id="851e8-107">Data loss prevention (DLP)</span></span>
- <span data-ttu-id="851e8-108">Classificatie</span><span class="sxs-lookup"><span data-stu-id="851e8-108">Classification</span></span>
- <span data-ttu-id="851e8-109">Informatiebeheer</span><span class="sxs-lookup"><span data-stu-id="851e8-109">Information governance</span></span>
- <span data-ttu-id="851e8-110">Records Management</span><span class="sxs-lookup"><span data-stu-id="851e8-110">Records management</span></span>
- <span data-ttu-id="851e8-111">Communicatie compliance (voorheen 'Supervisie')</span><span class="sxs-lookup"><span data-stu-id="851e8-111">Communication compliance (formerly 'Supervision')</span></span>

<span data-ttu-id="851e8-112">Gebruikers worden automatisch doorgeleid naar dezelfde complianceoplossingen in de Microsoft 365-compliancecentrum (compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="851e8-112">Users are automatically routed to the same compliance solutions in the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="851e8-113">Voor andere complianceoplossingen in het Office 365 Beveiligings- en compliancecentrum blijven gebruikers deze oplossingen beheren in het Microsoft 365-compliancecentrum of het Office 365 Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="851e8-113">For other compliance solutions included in the Office 365 Security and Compliance Center, users will continue to manage these solutions in either the Microsoft 365 compliance center or the Office 365 Security and Compliance Center.</span></span> <span data-ttu-id="851e8-114">De automatische omleiding voor deze complianceoplossingen is binnenkort beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="851e8-114">The automatic redirection for these compliance solutions will be available soon.</span></span>

<span data-ttu-id="851e8-115">Met deze functie en bijbehorende besturingselementen wordt de automatische omleiding van beveiligingsfuncties voor Microsoft Defender niet ingeschakeld voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="851e8-115">This feature and associated controls does not enable the automatic redirection of Security features for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="851e8-116">Als u de omleiding voor beveiligingsfuncties wilt inschakelen, zie Accounts van Microsoft Defender omleiden voor Office 365 naar het [Microsoft 365 beveiligingscentrum](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="851e8-116">To enable the redirection for security features, see [Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) for details.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="851e8-117">Kan ik teruggaan naar het gebruik van de voormalige portal?</span><span class="sxs-lookup"><span data-stu-id="851e8-117">Can I go back to using the former portal?</span></span>

<span data-ttu-id="851e8-118">Als iets niet werkt voor u of als er iets is dat u niet kunt voltooien via de Microsoft 365-compliancecentrum-portal, kunt u de automatische omleiding tijdelijk uitschakelen voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="851e8-118">If something isn't working for you or if there's anything you're unable to complete through the Microsoft 365 compliance center portal, you can temporarily disable the automatic redirection for all users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="851e8-119">De Microsoft 365-compliancecentrum is de vervangingsbeheerportal voor complianceoplossingen die momenteel worden beheerd in Office 365 beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="851e8-119">The Microsoft 365 compliance center is the replacement management portal for compliance solutions currently managed in the Office 365 Security and Compliance center.</span></span> <span data-ttu-id="851e8-120">Alle Microsoft 365 complianceoplossingen worden uitsluitend in de Microsoft 365-compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="851e8-120">All Microsoft 365 compliance solutions will be managed solely in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="851e8-121">Het uitschakelen van omleiding naar de Microsoft 365-compliancecentrum moet een oplossing voor de korte termijn zijn.</span><span class="sxs-lookup"><span data-stu-id="851e8-121">Disabling redirection to the Microsoft 365 compliance center should be a short-term solution.</span></span>

<span data-ttu-id="851e8-122">Als u wilt teruggaan naar het Office 365 Beveiligings- en compliancecentrum (protection.microsoft.com) voor alle gebruikers, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="851e8-122">To switch back to the Office 365 Security and Compliance center (protection.microsoft.com) for all users, complete the following steps:</span></span>

1. <span data-ttu-id="851e8-123">Meld u aan bij [de Microsoft 365-compliancecentrum](https://compliance.microsoft.com) globale beheerder of gebruik een account met compliancebeheerdersmachtigingen in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="851e8-123">Sign in to the [Microsoft 365 compliance center](https://compliance.microsoft.com) as a global administrator or using any account with compliance administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="851e8-124">Navigeer **naar Instellingen**  >  **omleiding van het compliancecentrum**.</span><span class="sxs-lookup"><span data-stu-id="851e8-124">Navigate to **Settings** > **Compliance center redirection**.</span></span>
3. <span data-ttu-id="851e8-125">Schakel de instelling Automatische omleiding in op **Uit.**</span><span class="sxs-lookup"><span data-stu-id="851e8-125">Toggle the Automatic redirection setting to **Off**.</span></span>
4. <span data-ttu-id="851e8-126">Selecteer **Uitschakelen en** feedback delen wanneer u daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="851e8-126">Select **Turn off** and share feedback when prompted.</span></span>

<span data-ttu-id="851e8-127">Wanneer deze is uitgeschakeld, worden gebruikers niet meer doorgestuurd naar compliance.microsoft.com en worden ze doorgestuurd naar het Office 365 Security and Compliance center (protection.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="851e8-127">Once disabled, users will no longer be routed to compliance.microsoft.com and they will be directed to the Office 365 Security and Compliance center (protection.microsoft.com).</span></span> <span data-ttu-id="851e8-128">Deze instelling kan op elk moment opnieuw worden ingeschakeld door globale beheerders of compliancebeheerders.</span><span class="sxs-lookup"><span data-stu-id="851e8-128">This setting can be enabled again at any time by Global or Compliance admins.</span></span>

## <a name="related-information"></a><span data-ttu-id="851e8-129">Gerelateerde informatie</span><span class="sxs-lookup"><span data-stu-id="851e8-129">Related information</span></span>

- [<span data-ttu-id="851e8-130">Microsoft 365-compliancecentrum overzicht</span><span class="sxs-lookup"><span data-stu-id="851e8-130">Microsoft 365 compliance center overview</span></span>](/microsoft-365/compliance/microsoft-365-compliance-center)
