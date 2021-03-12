---
title: Accounts omleiden van Microsoft Defender voor Eindpunt naar het Microsoft 365-beveiligingscentrum
description: Accounts en sessies omleiden van het Defender voor Eindpunt naar het Microsoft 365-beveiligingscentrum.
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
ms.openlocfilehash: 626bc9950512438bfa43e6500adf72940ddcbfec
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727563"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-the-microsoft-365-security-center"></a><span data-ttu-id="20abb-104">Accounts omleiden van Microsoft Defender voor Eindpunt naar het Microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="20abb-104">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="20abb-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="20abb-105">**Applies to:**</span></span>
- <span data-ttu-id="20abb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20abb-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="20abb-107">Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="20abb-107">Defender for Endpoint</span></span>

<span data-ttu-id="20abb-108">In overeenstemming met de cross-domain-benadering van Microsoft voor bedreigingsbeveiliging met SIEM en XDR (Extended detection and response), hebben we Microsoft Defender Advanced Threat Protection omgedoopt tot Microsoft Defender voor Eindpunt en samengevoegd tot één geïntegreerde portal: het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="20abb-108">In alignment with Microsoft’s cross-domain approach to threat protection with SIEM and Extended detection and response (XDR), we’ve rebranded Microsoft Defender Advanced Threat Protection as Microsoft Defender for Endpoint and unified it into a single integrated portal - the Microsoft 365 security center.</span></span>

<span data-ttu-id="20abb-109">In deze handleiding wordt uitgelegd hoe u accounts kunt doorsturen naar het Microsoft 365-beveiligingscentrum door automatische omleiding vanuit de voormalige Microsoft Defender voor Eindpunt-portal (securitycenter.windows.com of securitycenter.microsoft.com) in te stellen naar de Microsoft 365-portal voor beveiligingscentrum (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="20abb-109">This guide explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Defender for Endpoint portal (securitycenter.windows.com or securitycenter.microsoft.com), to the Microsoft 365 security center portal (security.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="20abb-110">Microsoft Defender voor Eindpunt in het Microsoft 365-beveiligingscentrum ondersteunt het verlenen van toegang tot beheerde beveiligingsserviceproviders [(MSSP's)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) op dezelfde manier als toegang wordt verleend in het [Microsoft Defender-beveiligingscentrum.](https://docs.microsoft.com/microsoft-365/security/mtp/mssp-access)</span><span class="sxs-lookup"><span data-stu-id="20abb-110">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same that way access is [granted in the Microsoft Defender security center](https://docs.microsoft.com/microsoft-365/security/mtp/mssp-access).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="20abb-111">Wat u kunt verwachten</span><span class="sxs-lookup"><span data-stu-id="20abb-111">What to expect</span></span>
<span data-ttu-id="20abb-112">Wanneer automatische omleiding is ingeschakeld, worden accounts die toegang hebben tot de voormalige Microsoft Defender voor Eindpunt-portal bij securitycenter.windows.com of securitycenter.microsoft.com, automatisch doorgestuurd naar de microsoft 365-beveiligingscentrumportal op security.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="20abb-112">Once automatic redirection is enabled, accounts accessing the former Microsoft Defender for Endpoint portal at securitycenter.windows.com or securitycenter.microsoft.com, will be automatically routed to the Microsoft 365 security center portal at security.microsoft.com.</span></span>
 
<span data-ttu-id="20abb-113">Meer informatie over wat er is gewijzigd: [Microsoft Defender voor Eindpunt in het Microsoft 365-beveiligingscentrum.](microsoft-365-security-center-mde.md)</span><span class="sxs-lookup"><span data-stu-id="20abb-113">Learn more about what’s changed: [Microsoft Defender for Endpoint in the Microsoft 365 security center](microsoft-365-security-center-mde.md).</span></span>

<span data-ttu-id="20abb-114">Dit omvat omleiding voor directe toegang tot de voormalige portal via de browser, inclusief koppelingen naar de voormalige securitycenter.windows.com-portal, zoals koppelingen in e-mailmeldingen en koppelingen die worden geretourneerd door SIEM API-oproepen.</span><span class="sxs-lookup"><span data-stu-id="20abb-114">This includes redirection for direct access to the former portal via browser, including links pointing towards the former securitycenter.windows.com portal - such as links in email notifications, and links returned by SIEM API calls.</span></span>  

 <span data-ttu-id="20abb-115">Externe koppelingen van e-mailmeldingen of SIEM-API's bevatten momenteel koppelingen naar beide portals.</span><span class="sxs-lookup"><span data-stu-id="20abb-115">External links from email notifications or SIEM APIs currently contain links to both portals.</span></span> <span data-ttu-id="20abb-116">Wanneer omleiding is ingeschakeld, verwijzen beide koppelingen naar het Microsoft 365-beveiligingscentrum totdat de oude koppeling uiteindelijk wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="20abb-116">Once redirection is enabled, both links will point to the Microsoft 365 security center until the old link is eventually removed.</span></span> <span data-ttu-id="20abb-117">We raden u aan de nieuwe koppeling te gebruiken die verwijst naar het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="20abb-117">We encourage you to adopt the new link pointing to the Microsoft 365 security center.</span></span>

<span data-ttu-id="20abb-118">Raadpleeg de onderstaande tabel voor meer informatie over koppelingen en routering.</span><span class="sxs-lookup"><span data-stu-id="20abb-118">Refer to the table below for more on links and routing.</span></span>
## <a name="siem-api-routing"></a><span data-ttu-id="20abb-119">SIEM API-routering</span><span class="sxs-lookup"><span data-stu-id="20abb-119">SIEM API routing</span></span>

|<span data-ttu-id="20abb-120">**Eigenschap**</span><span class="sxs-lookup"><span data-stu-id="20abb-120">**Property**</span></span>  |<span data-ttu-id="20abb-121">**Bestemming wanneer omleiding UIT is**</span><span class="sxs-lookup"><span data-stu-id="20abb-121">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="20abb-122">**Doel wanneer omleiding AAN is**</span><span class="sxs-lookup"><span data-stu-id="20abb-122">**Destination when redirection is ON**</span></span> | 
|---------|---------|---------|
| <span data-ttu-id="20abb-123">LinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="20abb-123">LinkToWDATP</span></span> | <span data-ttu-id="20abb-124">Waarschuwingspagina in securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="20abb-124">Alert page in securitycenter.windows.com</span></span> | <span data-ttu-id="20abb-125">Waarschuwingspagina in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="20abb-125">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="20abb-126">IncidentLinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="20abb-126">IncidentLinkToWDATP</span></span> | <span data-ttu-id="20abb-127">Pagina Incident in securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="20abb-127">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="20abb-128">Pagina Incident in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="20abb-128">Incident page in security.microsoft.com</span></span>  |
| <span data-ttu-id="20abb-129">LinkToMTP</span><span class="sxs-lookup"><span data-stu-id="20abb-129">LinkToMTP</span></span> | <span data-ttu-id="20abb-130">Waarschuwingspagina in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="20abb-130">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="20abb-131">Waarschuwingspagina in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="20abb-131">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="20abb-132">IncidentLinkToMTP</span><span class="sxs-lookup"><span data-stu-id="20abb-132">IncidentLinkToMTP</span></span> | <span data-ttu-id="20abb-133">Pagina Incident in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="20abb-133">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="20abb-134">Pagina Incident in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="20abb-134">Incident page in security.microsoft.com</span></span>  

## <a name="email-alert-notifications"></a><span data-ttu-id="20abb-135">Meldingen van e-mailmeldingen</span><span class="sxs-lookup"><span data-stu-id="20abb-135">Email alert notifications</span></span>

|<span data-ttu-id="20abb-136">**Eigenschap**</span><span class="sxs-lookup"><span data-stu-id="20abb-136">**Property**</span></span>  |<span data-ttu-id="20abb-137">**Bestemming wanneer omleiding UIT is**</span><span class="sxs-lookup"><span data-stu-id="20abb-137">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="20abb-138">**Doel wanneer omleiding AAN is**</span><span class="sxs-lookup"><span data-stu-id="20abb-138">**Destination when redirection is ON**</span></span> |
|---------|---------|---------|
| <span data-ttu-id="20abb-139">Waarschuwingspagina</span><span class="sxs-lookup"><span data-stu-id="20abb-139">Alert page</span></span>  | <span data-ttu-id="20abb-140">Waarschuwingspagina in securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="20abb-140">Alert page in securitycenter.windows.com</span></span>  | <span data-ttu-id="20abb-141">Waarschuwingspagina in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="20abb-141">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="20abb-142">Pagina Incident</span><span class="sxs-lookup"><span data-stu-id="20abb-142">Incident page</span></span>  |<span data-ttu-id="20abb-143">Pagina Incident in securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="20abb-143">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="20abb-144">Pagina Incident in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="20abb-144">Incident page in security.microsoft.com</span></span>  
| <span data-ttu-id="20abb-145">Waarschuwingspagina in de portal van het beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="20abb-145">Alert page in security center portal</span></span> | <span data-ttu-id="20abb-146">Waarschuwingspagina in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="20abb-146">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="20abb-147">Waarschuwingspagina in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="20abb-147">Alert page in security.microsoft.com</span></span> | 
| <span data-ttu-id="20abb-148">Pagina Incident in de portal van het beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="20abb-148">Incident page in security center portal</span></span> | <span data-ttu-id="20abb-149">Pagina Incident in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="20abb-149">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="20abb-150">Pagina Incident in security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="20abb-150">Incident page in security.microsoft.com</span></span>  |

## <a name="when-does-this-take-effect"></a><span data-ttu-id="20abb-151">Wanneer wordt dit van kracht?</span><span class="sxs-lookup"><span data-stu-id="20abb-151">When does this take effect?</span></span> 
<span data-ttu-id="20abb-152">Wanneer deze update is ingeschakeld, kan deze update vrijwel direct van kracht worden voor sommige accounts.</span><span class="sxs-lookup"><span data-stu-id="20abb-152">Once enabled, this update might take effect almost immediately for some accounts.</span></span> <span data-ttu-id="20abb-153">Het kan echter langer duren om de omleiding door te laten gaan naar elk account in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="20abb-153">But the redirection might take longer to propagate to every account in your organization.</span></span> <span data-ttu-id="20abb-154">Accounts in actieve sessies terwijl deze instelling wordt toegepast, worden niet uit hun sessie weggestuurd en worden alleen doorgestuurd naar het Microsoft 365-beveiligingscentrum nadat ze hun huidige sessie hebben afgesloten en zich opnieuw hebben aangemeld.</span><span class="sxs-lookup"><span data-stu-id="20abb-154">Accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="20abb-155">Portalomleiding instellen</span><span class="sxs-lookup"><span data-stu-id="20abb-155">Set up portal redirection</span></span>
<span data-ttu-id="20abb-156">Als u wilt beginnen met het routeren van accounts naar het Microsoft 365-beveiligingscentrum:</span><span class="sxs-lookup"><span data-stu-id="20abb-156">To start routing accounts to the Microsoft 365 security center:</span></span>
1. <span data-ttu-id="20abb-157">Zorg ervoor dat u een globale beheerder bent of beveiligingsbeheerdersmachtigingen hebt in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="20abb-157">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory</span></span> 

2. <span data-ttu-id="20abb-158">[Meld u](https://security.microsoft.com/) aan bij het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="20abb-158">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>

3. <span data-ttu-id="20abb-159">Ga naar **Instellingen**  >  **Eindpunten**  >  **Algemene**  >  **portalomleiding of** klik [hier.](https://security.microsoft.com/preferences2/portal_redirection)</span><span class="sxs-lookup"><span data-stu-id="20abb-159">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [click here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

4. <span data-ttu-id="20abb-160">Schakel de instelling Automatische omleiding in op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="20abb-160">Toggle the Automatic redirection setting to **On**.</span></span>

5. <span data-ttu-id="20abb-161">Klik **op Inschakelen** om automatische omleiding toe te passen op de portal van het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="20abb-161">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

>[!IMPORTANT]
><span data-ttu-id="20abb-162">Als u deze instelling inschakelen, worden actieve gebruikerssessies niet beëindigd.</span><span class="sxs-lookup"><span data-stu-id="20abb-162">Enabling this setting will not terminate active user sessions.</span></span> <span data-ttu-id="20abb-163">Accounts die in een actieve sessie zitten terwijl deze instelling wordt toegepast, worden alleen doorgestuurd naar het Microsoft 365-beveiligingscentrum nadat ze hun huidige sessie hebben afgesloten en zich opnieuw hebben aangemeld.</span><span class="sxs-lookup"><span data-stu-id="20abb-163">Accounts who are in an active session while this setting is applied will only be directed to the Microsoft 365 security center after ending their current session and signing in again.</span></span>

>[!NOTE]
><span data-ttu-id="20abb-164">U moet een globale beheerder zijn of beveiligingsbeheerdersmachtigingen hebben in Azure Active Directory om deze instelling in of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="20abb-164">You must be a global administrator or have security administrator permissions in Azure Active Directory to enable or disable this setting.</span></span>  

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="20abb-165">Kan ik teruggaan naar het gebruik van de voormalige portal?</span><span class="sxs-lookup"><span data-stu-id="20abb-165">Can I go back to using the former portal?</span></span>
<span data-ttu-id="20abb-166">Als iets niet werkt voor u of als er iets is dat u niet kunt voltooien via de portal van het Microsoft 365-beveiligingscentrum, willen we dit graag horen.</span><span class="sxs-lookup"><span data-stu-id="20abb-166">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it.</span></span> <span data-ttu-id="20abb-167">Als u problemen hebt ondervonden met omleiding, raden we u aan ons dit te laten weten via het formulier Feedback indienen.</span><span class="sxs-lookup"><span data-stu-id="20abb-167">If you’ve encountered any issues with redirection, we encourage you to let us know by using the Give feedback submission form.</span></span>

<span data-ttu-id="20abb-168">Terugkeren naar de voormalige Microsoft Defender for Endpoint-portal:</span><span class="sxs-lookup"><span data-stu-id="20abb-168">To revert to the former Microsoft Defender for Endpoint portal:</span></span>

1. <span data-ttu-id="20abb-169">[Meld u aan](https://security.microsoft.com/) bij het Microsoft 365-beveiligingscentrum als globale beheerder of gebruik en account met machtigingen voor beveiligingsbeheerders in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="20abb-169">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="20abb-170">Ga naar **Instellingen**  >  **Eindpunten**  >  **Algemene**  >  **portalomleiding** of [open de pagina hier.](https://security.microsoft.com/preferences2/portal_redirection)</span><span class="sxs-lookup"><span data-stu-id="20abb-170">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [open the page here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

3. <span data-ttu-id="20abb-171">Schakel de instelling Automatische omleiding in op **Uit.**</span><span class="sxs-lookup"><span data-stu-id="20abb-171">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="20abb-172">Klik **op Uitschakelen** & feedback delen wanneer u daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="20abb-172">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="20abb-173">Deze instelling kan op elk moment opnieuw worden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="20abb-173">This setting can be enabled again at any time.</span></span> 

<span data-ttu-id="20abb-174">Nadat accounts zijn uitgeschakeld, worden accounts niet meer doorgeleid naar security.microsoft.com en hebt u opnieuw toegang tot de voormalige portal- securitycenter.windows.com of securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="20abb-174">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span> 

## <a name="related-information"></a><span data-ttu-id="20abb-175">Gerelateerde informatie</span><span class="sxs-lookup"><span data-stu-id="20abb-175">Related information</span></span>
- [<span data-ttu-id="20abb-176">Overzicht van Microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="20abb-176">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="20abb-177">Microsoft Defender voor Eindpunt in het Microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="20abb-177">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="20abb-178">Microsoft levert geïntegreerde SIEM en XDR om beveiligingsbewerkingen te moderniseren</span><span class="sxs-lookup"><span data-stu-id="20abb-178">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="20abb-179">XDR versus SIEM infographic</span><span class="sxs-lookup"><span data-stu-id="20abb-179">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="20abb-180">De Nieuwe Defender</span><span class="sxs-lookup"><span data-stu-id="20abb-180">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="20abb-181">Over Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20abb-181">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="20abb-182">Microsoft-beveiligingsportalen en beheercentra</span><span class="sxs-lookup"><span data-stu-id="20abb-182">Microsoft security portals and admin centers</span></span>](portals.md)
