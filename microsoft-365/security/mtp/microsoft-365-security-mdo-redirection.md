---
title: Accounts van Microsoft Defender voor Office 365 omleiden naar het nieuwe Microsoft 365-beveiligingscentrum
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 30fa10e23fd6a0c92bd5a56c797d3b7ff5b4bfd6
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50416778"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a><span data-ttu-id="eb74a-104">Accounts van Microsoft Defender voor Office 365 omleiden naar het Microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="eb74a-104">Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="eb74a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="eb74a-105">**Applies to:**</span></span>

- <span data-ttu-id="eb74a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eb74a-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="eb74a-107">Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="eb74a-107">Defender for Office 365</span></span>

<span data-ttu-id="eb74a-108">In dit artikel wordt uitgelegd hoe u accounts kunt doorsturen naar het Microsoft 365-beveiligingscentrum door automatische omleiding van het voormalige Microsoft-beveiligings- en compliancecentrum (protection.office.com of securitycenter.microsoft.com) in te stellen naar het Microsoft 365-beveiligingscentrum (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="eb74a-108">This article explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Security and Compliance Center (protection.office.com or securitycenter.microsoft.com), to the Microsoft 365 security center (security.microsoft.com).</span></span>

>[!NOTE]
> <span data-ttu-id="eb74a-109">De portalomleidingsmogelijkheid is alleen beschikbaar voor klanten van Office 365 E5 en Microsoft Defender voor Office P2</span><span class="sxs-lookup"><span data-stu-id="eb74a-109">Portal redirection capability is available for Office 365 E5 and Microsoft Defender for Office P2 customers only</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="eb74a-110">Wat u kunt verwachten</span><span class="sxs-lookup"><span data-stu-id="eb74a-110">What to expect</span></span>
<span data-ttu-id="eb74a-111">Wanneer automatische omleiding is ingeschakeld en actief is, worden gebruikers die toegang hebben tot de beveiligingsfuncties in Office 365 Security and Compliance (protection.office.com) automatisch doorgestuurd naar het Microsoft 365-beveiligingscentrum ( https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="eb74a-111">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to the Microsoft 365 security center (https://security.microsoft.com).</span></span>  

<span data-ttu-id="eb74a-112">Meer informatie over wat er is gewijzigd: [Microsoft Defender voor Office 365 in het Microsoft 365-beveiligingscentrum.](microsoft-365-security-center-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="eb74a-112">Learn more about what’s changed: [Microsoft Defender for Office 365 in the Microsoft 365 security center](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="eb74a-113">Als automatische omleiding is ingeschakeld, worden gebruikers doorgestuurd naar het Microsoft 365-beveiligingscentrum wanneer ze beveiligingsfuncties in het Office 365-beveiligings- en compliancecentrum gebruiken.</span><span class="sxs-lookup"><span data-stu-id="eb74a-113">With automatic redirection turned on, users will be routed to Microsoft 365 security center when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="eb74a-114">Dit zijn onder andere mogelijkheden in de sectie Bedreigingsbeheer en het dashboard en rapporten van Bedreigingsbeheer.</span><span class="sxs-lookup"><span data-stu-id="eb74a-114">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="eb74a-115">Items in het Office 365-beveiligings- en compliancecentrum die niet gerelateerd zijn aan beveiliging, worden niet omgeleid naar het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="eb74a-115">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to the Microsoft 365 security center.</span></span>

<span data-ttu-id="eb74a-116">Items in verband met naleving vindt u in het Microsoft 365-compliancecentrum en items met betrekking tot e-mailstromen vindt u in het Exchange-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="eb74a-116">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="eb74a-117">Alle overige mogelijkheden, ongeacht of ze betrekking hebben op naleving of mogelijkheden die beide dienen, worden niet beïnvloed door omleiding.</span><span class="sxs-lookup"><span data-stu-id="eb74a-117">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="eb74a-118">Er worden beveiligingswaarschuwingen van Office 365 weergegeven in zowel het Microsoft 365-beveiligingscentrum als het Office 365-beveiligings- en compliancecentrum, zonder omleiding.</span><span class="sxs-lookup"><span data-stu-id="eb74a-118">Office 365 security alerts appear in both the Microsoft 365 security center and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="eb74a-119">Portalomleiding instellen</span><span class="sxs-lookup"><span data-stu-id="eb74a-119">Set up portal redirection</span></span>
<span data-ttu-id="eb74a-120">Om accounts te routeren naar het Microsoft 365-beveiligingscentrum op security.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="eb74a-120">To start routing accounts to the Microsoft 365 security center at security.microsoft.com:</span></span>

1. <span data-ttu-id="eb74a-121">Zorg ervoor dat u een globale beheerder bent of dat u machtigingen voor beveiligingsbeheerders hebt in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="eb74a-121">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="eb74a-122">[Meld u](https://security.microsoft.com/) aan bij het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="eb74a-122">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>
3. <span data-ttu-id="eb74a-123">Ga naar **E-mailinstellingen**  >  **& omleiding van de**  >  **samenwerkingsportal.**</span><span class="sxs-lookup"><span data-stu-id="eb74a-123">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="eb74a-124">Schakel de instelling voor automatische omleiding in op **Aan.**</span><span class="sxs-lookup"><span data-stu-id="eb74a-124">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="eb74a-125">Klik **op Inschakelen** om automatische omleiding toe te passen op de portal van het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="eb74a-125">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

> [!NOTE]
> <span data-ttu-id="eb74a-126">Nadat omleiding is ingeschakeld, worden accounts in actieve sessies terwijl deze instelling is toegepast niet uit hun sessie gerouteerd en worden ze alleen doorgestuurd naar het Microsoft 365-beveiligingscentrum nadat ze hun huidige sessie hebben afgesloten en zich opnieuw hebben aangemeld.</span><span class="sxs-lookup"><span data-stu-id="eb74a-126">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="eb74a-127">Kan ik teruggaan naar de vorige portal?</span><span class="sxs-lookup"><span data-stu-id="eb74a-127">Can I go back to using the former portal?</span></span>
<span data-ttu-id="eb74a-128">Als iets niet werkt voor u of als u iets niet kunt voltooien via de portal van het Microsoft 365-beveiligingscentrum, willen we dat graag weten via de feedbackoptie van de portal.</span><span class="sxs-lookup"><span data-stu-id="eb74a-128">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="eb74a-129">Als u problemen hebt ondervonden met omleiding, raden we u aan rechtstreeks contact op te nemen met uw PM-vriend via een persoonlijke preview of ons te laten weten via het formulier feedback geven.</span><span class="sxs-lookup"><span data-stu-id="eb74a-129">If you’ve encountered any issues with redirection, we encourage you to reach out to your PM buddy directly through private preview or let us know via the Give feedback submission form.</span></span>

<span data-ttu-id="eb74a-130">Terugkeren naar de vorige portal:</span><span class="sxs-lookup"><span data-stu-id="eb74a-130">To revert to the former portal:</span></span>

1. <span data-ttu-id="eb74a-131">[Meld u aan](https://security.microsoft.com/) bij het Microsoft 365-beveiligingscentrum als globale beheerder of gebruik en account met machtigingen voor beveiligingsbeheerders in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="eb74a-131">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="eb74a-132">**Navigeer naar**  >  **instellingen-eindpunten**  >  **algemene**  >  **portalomleiding.**</span><span class="sxs-lookup"><span data-stu-id="eb74a-132">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection**.</span></span>  

3. <span data-ttu-id="eb74a-133">Zet de instelling voor automatische omleiding op **Uit.**</span><span class="sxs-lookup"><span data-stu-id="eb74a-133">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="eb74a-134">Klik **op Uitschakelen** & feedback te delen wanneer hier om wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="eb74a-134">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="eb74a-135">Deze instelling kan op elk moment opnieuw worden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="eb74a-135">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="eb74a-136">Als de account is uitgeschakeld, worden deze niet meer doorvergeleid naar security.microsoft.com en hebt u weer toegang tot de voormalige portal, securitycenter.windows.com of securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="eb74a-136">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="eb74a-137">Gerelateerde informatie</span><span class="sxs-lookup"><span data-stu-id="eb74a-137">Related information</span></span>
- [<span data-ttu-id="eb74a-138">Overzicht van Microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="eb74a-138">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="eb74a-139">Microsoft Defender voor eindpunt in het Microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="eb74a-139">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="eb74a-140">Microsoft levert geïntegreerde SIEM en XDR om beveiligingsbewerkingen te moderniseren</span><span class="sxs-lookup"><span data-stu-id="eb74a-140">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="eb74a-141">XDR versus SIEM infographic</span><span class="sxs-lookup"><span data-stu-id="eb74a-141">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="eb74a-142">De nieuwe Defender</span><span class="sxs-lookup"><span data-stu-id="eb74a-142">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="eb74a-143">Over Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eb74a-143">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="eb74a-144">Microsoft-beveiligingsportals en -beheercentra</span><span class="sxs-lookup"><span data-stu-id="eb74a-144">Microsoft security portals and admin centers</span></span>](portals.md)