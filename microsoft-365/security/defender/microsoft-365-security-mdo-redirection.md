---
title: Accounts omleiden van Microsoft Defender voor Office 365 naar het nieuwe Microsoft 365-beveiligingscentrum
description: Omleiden van Defender voor Office 365 naar het Microsoft 365-beveiligingscentrum.
keywords: Microsoft 365-beveiligingscentrum, Aan de slag met het Microsoft 365-beveiligingscentrum, omleiding van het beveiligingscentrum
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
ms.openlocfilehash: ce8c178b4c46a00b83833f008080b776f4dc7e60
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058582"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a><span data-ttu-id="1e7e2-104">Accounts omleiden van Microsoft Defender voor Office 365 naar het Microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="1e7e2-104">Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1e7e2-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="1e7e2-105">**Applies to:**</span></span>

- <span data-ttu-id="1e7e2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e7e2-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="1e7e2-107">Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="1e7e2-107">Defender for Office 365</span></span>

<span data-ttu-id="1e7e2-108">In dit artikel wordt uitgelegd hoe u accounts kunt doorsturen naar het Microsoft 365-beveiligingscentrum door automatische omleiding vanuit het voormalige Microsoft Security and Compliance Center (protection.office.com of securitycenter.microsoft.com) in te stellen naar het Microsoft 365-beveiligingscentrum (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="1e7e2-108">This article explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Security and Compliance Center (protection.office.com or securitycenter.microsoft.com), to the Microsoft 365 security center (security.microsoft.com).</span></span>

>[!NOTE]
> <span data-ttu-id="1e7e2-109">Portal redirection capability is available for Office 365 E5 and Microsoft Defender for Office P2 customers only</span><span class="sxs-lookup"><span data-stu-id="1e7e2-109">Portal redirection capability is available for Office 365 E5 and Microsoft Defender for Office P2 customers only</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="1e7e2-110">Wat u kunt verwachten</span><span class="sxs-lookup"><span data-stu-id="1e7e2-110">What to expect</span></span>
<span data-ttu-id="1e7e2-111">Wanneer automatische omleiding is ingeschakeld en actief is, worden gebruikers die toegang hebben tot de beveiligingsgerelateerde mogelijkheden in Office 365 Security and Compliance (protection.office.com), automatisch doorgestuurd naar het Microsoft 365-beveiligingscentrum ( https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="1e7e2-111">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to the Microsoft 365 security center (https://security.microsoft.com).</span></span>  

<span data-ttu-id="1e7e2-112">Meer informatie over wat er is gewijzigd: [Microsoft Defender voor Office 365 in het Microsoft 365-beveiligingscentrum.](microsoft-365-security-center-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="1e7e2-112">Learn more about what’s changed: [Microsoft Defender for Office 365 in the Microsoft 365 security center](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="1e7e2-113">Wanneer automatische omleiding is ingeschakeld, worden gebruikers doorgestuurd naar het Microsoft 365-beveiligingscentrum wanneer ze beveiligingsfuncties gebruiken in het Office 365-beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="1e7e2-113">With automatic redirection turned on, users will be routed to Microsoft 365 security center when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="1e7e2-114">Deze omvatten mogelijkheden in de sectie Bedreigingsbeheer en het dashboard bedreigingsbeheer en rapporten.</span><span class="sxs-lookup"><span data-stu-id="1e7e2-114">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="1e7e2-115">Items in het Office 365-beveiligings- en compliancecentrum die geen verband houden met beveiliging, worden niet omgeleid naar het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="1e7e2-115">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to the Microsoft 365 security center.</span></span>

<span data-ttu-id="1e7e2-116">Compliance-gerelateerde items vindt u in het Microsoft 365-compliancecentrum en gerelateerde items voor e-mailstroom vindt u in het Exchange-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="1e7e2-116">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="1e7e2-117">Alle andere mogelijkheden, ongeacht of deze betrekking hebben op naleving of mogelijkheden die beide van pas komen, worden niet beïnvloed door omleiding.</span><span class="sxs-lookup"><span data-stu-id="1e7e2-117">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="1e7e2-118">Beveiligingswaarschuwingen voor Office 365 worden weergegeven in zowel het Microsoft 365-beveiligingscentrum als het Office 365-beveiligings- en compliancecentrum, zonder omleiding.</span><span class="sxs-lookup"><span data-stu-id="1e7e2-118">Office 365 security alerts appear in both the Microsoft 365 security center and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="1e7e2-119">Portalomleiding instellen</span><span class="sxs-lookup"><span data-stu-id="1e7e2-119">Set up portal redirection</span></span>
<span data-ttu-id="1e7e2-120">Als u wilt beginnen met het routeren van accounts naar het Microsoft 365-beveiligingscentrum op security.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="1e7e2-120">To start routing accounts to the Microsoft 365 security center at security.microsoft.com:</span></span>

1. <span data-ttu-id="1e7e2-121">Zorg ervoor dat u een globale beheerder bent of beveiligingsbeheerdersmachtigingen hebt in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1e7e2-121">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="1e7e2-122">[Meld u](https://security.microsoft.com/) aan bij het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="1e7e2-122">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>
3. <span data-ttu-id="1e7e2-123">Ga naar **Instellingen**  >  **E-mail & portal**  >  **omleiding van samenwerking**.</span><span class="sxs-lookup"><span data-stu-id="1e7e2-123">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="1e7e2-124">Schakel de instelling Automatische omleiding in op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="1e7e2-124">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="1e7e2-125">Klik **op Inschakelen** om automatische omleiding toe te passen op de portal van het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="1e7e2-125">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

> [!NOTE]
> <span data-ttu-id="1e7e2-126">Nadat omleiding is ingeschakeld, worden accounts in actieve sessies, terwijl deze instelling is toegepast, niet uit hun sessie weggestuurd en worden ze alleen doorgestuurd naar het Microsoft 365-beveiligingscentrum nadat ze hun huidige sessie hebben afgesloten en zich opnieuw hebben aangemeld.</span><span class="sxs-lookup"><span data-stu-id="1e7e2-126">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="1e7e2-127">Kan ik teruggaan naar het gebruik van de voormalige portal?</span><span class="sxs-lookup"><span data-stu-id="1e7e2-127">Can I go back to using the former portal?</span></span>
<span data-ttu-id="1e7e2-128">Als iets niet werkt voor u of als er iets is dat u niet kunt voltooien via de portal van het Microsoft 365-beveiligingscentrum, willen we dit horen met behulp van de portalfeedbackoptie.</span><span class="sxs-lookup"><span data-stu-id="1e7e2-128">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="1e7e2-129">Als u problemen hebt ondervonden met omleiding, raden we u aan rechtstreeks contact op te nemen met uw PM-vriend via een privévoorbeeld of ons dit te laten weten via het formulier Feedback indienen.</span><span class="sxs-lookup"><span data-stu-id="1e7e2-129">If you’ve encountered any issues with redirection, we encourage you to reach out to your PM buddy directly through private preview or let us know via the Give feedback submission form.</span></span>

<span data-ttu-id="1e7e2-130">Terugkeren naar de voormalige portal:</span><span class="sxs-lookup"><span data-stu-id="1e7e2-130">To revert to the former portal:</span></span>

1. <span data-ttu-id="1e7e2-131">[Meld u aan](https://security.microsoft.com/) bij het Microsoft 365-beveiligingscentrum als globale beheerder of gebruik en account met machtigingen voor beveiligingsbeheerders in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1e7e2-131">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="1e7e2-132">Ga naar **Instellingen**  >  **Eindpunten**  >  **Algemene**  >  **portal omleiding**.</span><span class="sxs-lookup"><span data-stu-id="1e7e2-132">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection**.</span></span>  

3. <span data-ttu-id="1e7e2-133">Schakel de instelling Automatische omleiding in op **Uit.**</span><span class="sxs-lookup"><span data-stu-id="1e7e2-133">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="1e7e2-134">Klik **op Uitschakelen** & feedback delen wanneer u daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="1e7e2-134">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="1e7e2-135">Deze instelling kan op elk moment opnieuw worden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="1e7e2-135">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="1e7e2-136">Nadat accounts zijn uitgeschakeld, worden accounts niet meer doorgeleid naar security.microsoft.com en hebt u opnieuw toegang tot de voormalige portal- securitycenter.windows.com of securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1e7e2-136">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="1e7e2-137">Gerelateerde informatie</span><span class="sxs-lookup"><span data-stu-id="1e7e2-137">Related information</span></span>
- [<span data-ttu-id="1e7e2-138">Overzicht van Microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="1e7e2-138">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="1e7e2-139">Microsoft Defender voor Eindpunt in het Microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="1e7e2-139">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="1e7e2-140">Microsoft levert geïntegreerde SIEM en XDR om beveiligingsbewerkingen te moderniseren</span><span class="sxs-lookup"><span data-stu-id="1e7e2-140">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="1e7e2-141">XDR versus SIEM infographic</span><span class="sxs-lookup"><span data-stu-id="1e7e2-141">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="1e7e2-142">De Nieuwe Defender</span><span class="sxs-lookup"><span data-stu-id="1e7e2-142">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="1e7e2-143">Over Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e7e2-143">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="1e7e2-144">Microsoft-beveiligingsportalen en beheercentra</span><span class="sxs-lookup"><span data-stu-id="1e7e2-144">Microsoft security portals and admin centers</span></span>](portals.md)