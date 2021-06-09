---
title: Accounts omleiden van Office 365 beveiligings- en compliancecentrum naar de nieuwe Microsoft 365 Defender
description: Omleiden van defender voor Office 365 naar Microsoft 365 Defender.
keywords: Microsoft 365 Defender, Aan de slag met Microsoft 365 Defender, omleiding van het beveiligingscentrum
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f13e8235eb5f70e2d851b9b8b7600913d4e4023f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842516"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a><span data-ttu-id="1dff0-104">Accounts omleiden van Office 365 beveiligings- en compliancecentrum naar Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1dff0-104">Redirecting accounts from Office 365 Security and Compliance Center to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1dff0-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="1dff0-105">**Applies to:**</span></span>

- <span data-ttu-id="1dff0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1dff0-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="1dff0-107">Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="1dff0-107">Defender for Office 365</span></span>

<span data-ttu-id="1dff0-108">In dit artikel wordt uitgelegd hoe u accounts kunt doorsturen naar Microsoft 365 Defender door automatische omleiding in te stellen van het voormalige Office 365 Security and Compliance Center (protection.office.com) naar Microsoft 365 Defender (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="1dff0-108">This article explains how to route accounts to Microsoft 365 Defender by enabling automatic redirection from the former Office 365 Security and Compliance Center (protection.office.com), to Microsoft 365 Defender (security.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="1dff0-109">Wat u kunt verwachten</span><span class="sxs-lookup"><span data-stu-id="1dff0-109">What to expect</span></span>
<span data-ttu-id="1dff0-110">Wanneer automatische omleiding is ingeschakeld en actief is, worden gebruikers die toegang hebben tot de beveiligingsgerelateerde mogelijkheden in Office 365 Security and Compliance (protection.office.com), automatisch doorgestuurd naar Microsoft 365 Defender ( https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="1dff0-110">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to Microsoft 365 Defender (https://security.microsoft.com).</span></span>  

<span data-ttu-id="1dff0-111">Meer informatie over wat er is gewijzigd: [Microsoft Defender voor Office 365 in Microsoft 365 Defender.](microsoft-365-security-center-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="1dff0-111">Learn more about what’s changed: [Microsoft Defender for Office 365 in Microsoft 365 Defender](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="1dff0-112">Wanneer automatische omleiding is ingeschakeld, worden gebruikers doorgestuurd naar Microsoft 365 Defender wanneer ze beveiligingsfuncties gebruiken in het Office 365 Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="1dff0-112">With automatic redirection turned on, users will be routed to Microsoft 365 Defender when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="1dff0-113">Deze omvatten mogelijkheden in de sectie Bedreigingsbeheer en het dashboard bedreigingsbeheer en rapporten.</span><span class="sxs-lookup"><span data-stu-id="1dff0-113">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="1dff0-114">Items in het Office 365 beveiligings- en compliancecentrum die geen verband houden met beveiliging, worden niet omgeleid naar Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="1dff0-114">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to Microsoft 365 Defender.</span></span>

<span data-ttu-id="1dff0-115">Compliancegerelateerde items vindt u in het Microsoft 365 compliancecentrum en gerelateerde items voor e-mailstroom vindt u in het Exchange beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="1dff0-115">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="1dff0-116">Alle andere mogelijkheden, ongeacht of deze betrekking hebben op naleving of mogelijkheden die beide van pas komen, worden niet beïnvloed door omleiding.</span><span class="sxs-lookup"><span data-stu-id="1dff0-116">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="1dff0-117">Office 365 beveiligingswaarschuwingen worden weergegeven in zowel Microsoft 365 Defender als Office 365 beveiligings- en compliancecentrum, zonder omleiding.</span><span class="sxs-lookup"><span data-stu-id="1dff0-117">Office 365 security alerts appear in both Microsoft 365 Defender and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="1dff0-118">Portalomleiding instellen</span><span class="sxs-lookup"><span data-stu-id="1dff0-118">Set up portal redirection</span></span>
<span data-ttu-id="1dff0-119">Als u wilt beginnen met het routeren van accounts Microsoft 365 Defender op security.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="1dff0-119">To start routing accounts to Microsoft 365 Defender at security.microsoft.com:</span></span>

1. <span data-ttu-id="1dff0-120">Zorg ervoor dat u een globale beheerder bent of beveiligingsbeheerdersmachtigingen hebt in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1dff0-120">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="1dff0-121">[Meld u aan](https://security.microsoft.com/) bij Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="1dff0-121">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender.</span></span>
3. <span data-ttu-id="1dff0-122">Navigeer **naar Instellingen**  >  **e-mail & portal**  >  **omleiding van de portal voor samenwerking.**</span><span class="sxs-lookup"><span data-stu-id="1dff0-122">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="1dff0-123">Schakel de instelling Automatische omleiding in op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="1dff0-123">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="1dff0-124">Klik **op Inschakelen** om automatische omleiding toe te passen op Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="1dff0-124">Click **Enable** to apply automatic redirection to Microsoft 365 Defender.</span></span>

> [!NOTE]
> <span data-ttu-id="1dff0-125">Nadat omleiding is ingeschakeld, worden accounts in actieve sessies, terwijl deze instelling is toegepast, niet uit hun sessie weggestuurd en worden ze alleen doorgestuurd naar Microsoft 365 Defender nadat ze hun huidige sessie hebben afgesloten en zich opnieuw hebben aangemeld.</span><span class="sxs-lookup"><span data-stu-id="1dff0-125">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to Microsoft 365 Defender after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="1dff0-126">Kan ik teruggaan naar het gebruik van de voormalige portal?</span><span class="sxs-lookup"><span data-stu-id="1dff0-126">Can I go back to using the former portal?</span></span>
<span data-ttu-id="1dff0-127">Als iets niet werkt voor u of als er iets is dat u niet kunt voltooien via Microsoft 365 Defender, willen we dit horen met de feedbackoptie voor de portal.</span><span class="sxs-lookup"><span data-stu-id="1dff0-127">If something isn’t working for you or if there’s anything you’re unable to complete through Microsoft 365 Defender, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="1dff0-128">Als u problemen hebt ondervonden met omleiding, laat het ons dan weten.</span><span class="sxs-lookup"><span data-stu-id="1dff0-128">If you’ve encountered any issues with redirection, please let us know.</span></span>

<span data-ttu-id="1dff0-129">Terugkeren naar de voormalige portal:</span><span class="sxs-lookup"><span data-stu-id="1dff0-129">To revert to the former portal:</span></span>

1. <span data-ttu-id="1dff0-130">[Meld u](https://security.microsoft.com/) aan bij Microsoft 365 Defender als globale beheerder of gebruik en account met machtigingen voor beveiligingsbeheerders in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1dff0-130">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="1dff0-131">Navigeer **naar Instellingen**  >  **e-mail & portal**  >  **omleiding van de portal voor samenwerking.**</span><span class="sxs-lookup"><span data-stu-id="1dff0-131">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>   

3. <span data-ttu-id="1dff0-132">Schakel de instelling Automatische omleiding in op **Uit.**</span><span class="sxs-lookup"><span data-stu-id="1dff0-132">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="1dff0-133">Klik **op Uitschakelen** & feedback delen wanneer u daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="1dff0-133">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="1dff0-134">Deze instelling kan op elk moment opnieuw worden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="1dff0-134">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="1dff0-135">Nadat accounts zijn uitgeschakeld, worden accounts niet meer doorgeleid naar security.microsoft.com en hebt u opnieuw toegang tot de voormalige portal, securitycenter.windows.com of securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1dff0-135">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal—securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="1dff0-136">Gerelateerde informatie</span><span class="sxs-lookup"><span data-stu-id="1dff0-136">Related information</span></span>
- [<span data-ttu-id="1dff0-137">Microsoft 365 Overzicht van Defender</span><span class="sxs-lookup"><span data-stu-id="1dff0-137">Microsoft 365 Defender overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="1dff0-138">Microsoft Defender voor Eindpunt in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1dff0-138">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="1dff0-139">Microsoft levert geïntegreerde SIEM en XDR om beveiligingsbewerkingen te moderniseren</span><span class="sxs-lookup"><span data-stu-id="1dff0-139">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="1dff0-140">XDR versus SIEM infographic</span><span class="sxs-lookup"><span data-stu-id="1dff0-140">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="1dff0-141">De Nieuwe Defender</span><span class="sxs-lookup"><span data-stu-id="1dff0-141">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="1dff0-142">Over Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1dff0-142">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="1dff0-143">Microsoft-beveiligingsportalen en beheercentra</span><span class="sxs-lookup"><span data-stu-id="1dff0-143">Microsoft security portals and admin centers</span></span>](portals.md)
