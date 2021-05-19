---
title: Stap 1 - Een werknemer stoppen met aanmelden bij Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Een voormalige werknemer blokkeren om zich aan te melden en de toegang tot Microsoft 365 blokkeren.
ms.openlocfilehash: 8eb41c3b449e63284371aaf168262307a4c21941
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535948"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a><span data-ttu-id="6e291-103">Stap 1: voorkomen dat een voormalige werknemer zich aanlogt en de toegang tot Microsoft 365 services blokkeert</span><span class="sxs-lookup"><span data-stu-id="6e291-103">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>

<span data-ttu-id="6e291-104">Als u de aanmeldingstoegang van een gebruiker onmiddellijk wilt voorkomen, moet u het wachtwoord opnieuw instellen.</span><span class="sxs-lookup"><span data-stu-id="6e291-104">If you need to immediately prevent a user's sign-in access, you should reset their password.</span></span> <span data-ttu-id="6e291-105">In deze stap dwingt u de gebruiker af te melden van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6e291-105">In this step, force a sign out of the user from Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="6e291-106">U moet een globale beheerder zijn om de aanmelding te starten.</span><span class="sxs-lookup"><span data-stu-id="6e291-106">You need to be a global administrator to initiate sign-out.</span></span>

1. <span data-ttu-id="6e291-107">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="6e291-107">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="6e291-108">Schakel het vakje naast de naam van de gebruiker in en selecteer vervolgens **Wachtwoord opnieuw instellen.**</span><span class="sxs-lookup"><span data-stu-id="6e291-108">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="6e291-109">Voer een nieuw wachtwoord in en selecteer Vervolgens **Opnieuw instellen.**</span><span class="sxs-lookup"><span data-stu-id="6e291-109">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="6e291-110">(Verzend het niet naar hen.)</span><span class="sxs-lookup"><span data-stu-id="6e291-110">(Don't send it to them.)</span></span>
4. <span data-ttu-id="6e291-111">Selecteer de naam van de gebruiker om naar het eigenschappenvenster te gaan en selecteer op het tabblad **Account** de optie **Aanmelding starten.**</span><span class="sxs-lookup"><span data-stu-id="6e291-111">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

<span data-ttu-id="6e291-112">Binnen een uur - of nadat ze de huidige Microsoft 365 pagina waarin ze zich hebben geplaatst - worden ze gevraagd zich opnieuw aan te melden.</span><span class="sxs-lookup"><span data-stu-id="6e291-112">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="6e291-113">Een toegangs token is goed voor een uur, dus de tijdlijn is afhankelijk van hoeveel tijd er nog over is op dat token en of ze buiten hun huidige webpagina navigeren.</span><span class="sxs-lookup"><span data-stu-id="6e291-113">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6e291-114">Als de gebruiker zich in Outlook op het web, gewoon in zijn postvak klikt, wordt deze mogelijk niet onmiddellijk uit het postvak geschopt.</span><span class="sxs-lookup"><span data-stu-id="6e291-114">If the user is in Outlook on the web, just clicking around in their mailbox, they may not be kicked out immediately.</span></span> <span data-ttu-id="6e291-115">Zodra ze een andere tegel selecteren, zoals OneDrive of de browser vernieuwen, wordt de aanmelding gestart.</span><span class="sxs-lookup"><span data-stu-id="6e291-115">As soon as they select a different tile, such as OneDrive, or refresh their browser, the sign-out is initiated.</span></span>
  
<span data-ttu-id="6e291-116">Zie de [cmdlet Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) als u PowerShell wilt gebruiken om een gebruiker onmiddellijk af te melden.</span><span class="sxs-lookup"><span data-stu-id="6e291-116">To use PowerShell to sign out a user immediately, see the [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet.</span></span>
  
<span data-ttu-id="6e291-117">Zie [Wat u moet weten over het beëindigen van een sessie van een werknemer](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session) voor meer informatie over hoe lang het duurt om iemand de toegang tot e-mail te ontzeggen.</span><span class="sxs-lookup"><span data-stu-id="6e291-117">For more information about how long it takes to get someone out of email, see [What you need to know about terminating an employee's email session](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span></span>

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a><span data-ttu-id="6e291-118">De toegang van een voormalige werknemer tot Microsoft 365 blokkeren</span><span class="sxs-lookup"><span data-stu-id="6e291-118">Block a former employee's access to Microsoft 365 services</span></span>

> [!IMPORTANT]
 > <span data-ttu-id="6e291-119">Het blokkeren van een account kan tot 24 uur duren.</span><span class="sxs-lookup"><span data-stu-id="6e291-119">Blocking an account can take up to 24 hours to take effect.</span></span> <span data-ttu-id="6e291-120">Als u de aanmeldingstoegang van een gebruiker onmiddellijk wilt voorkomen, volgt u de bovenstaande stappen en stelt u het wachtwoord opnieuw in.</span><span class="sxs-lookup"><span data-stu-id="6e291-120">If you need to immediately prevent a user's sign-in access, follow the steps above and reset their password.</span></span>

1. <span data-ttu-id="6e291-121">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="6e291-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="6e291-122">Selecteer de naam van de werknemer die u wilt blokkeren en selecteer onder de naam van de gebruiker het symbool voor **Deze gebruiker blokkeren.**</span><span class="sxs-lookup"><span data-stu-id="6e291-122">Select the name of the employee that you want to block, and under the user's name, select the symbol for **Block this user**.</span></span>
3. <span data-ttu-id="6e291-123">Selecteer **De gebruiker blokkeren om zich aan te melden** en selecteer opslaan. </span><span class="sxs-lookup"><span data-stu-id="6e291-123">Select **Block the user from signing in**, and then select **Save**.</span></span>

## <a name="block-a-former-employees-access-to-email-exchange-online"></a><span data-ttu-id="6e291-124">De toegang van een voormalige werknemer tot e-mail (Exchange Online) blokkeren</span><span class="sxs-lookup"><span data-stu-id="6e291-124">Block a former employee's access to email (Exchange Online)</span></span>

<span data-ttu-id="6e291-125">Als u e-mail hebt als onderdeel van uw Microsoft 365-abonnement, meld u dan aan bij het Exchange-beheercentrum en volg deze stappen om te blokkeren dat uw voormalige werknemer toegang heeft tot zijn of haar e-mail.</span><span class="sxs-lookup"><span data-stu-id="6e291-125">If you have email as part of your Microsoft 365 subscription, sign in to the Exchange admin center and follow these steps to block your former employee from accessing their email.</span></span>
  
1. <span data-ttu-id="6e291-126">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.</span><span class="sxs-lookup"><span data-stu-id="6e291-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="6e291-127">Ga in het Exchange-beheercentrum naar **Ontvangers** \> **Postvakken**.</span><span class="sxs-lookup"><span data-stu-id="6e291-127">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="6e291-128">Dubbelklik op de gebruiker en ga naar de pagina **Postvakfuncties.**</span><span class="sxs-lookup"><span data-stu-id="6e291-128">Double-click the user and go to the **Mailbox features** page.</span></span> <span data-ttu-id="6e291-129">Selecteer **onder Mobiele apparaten** de optie Uitschakelen **Exchange ActiveSync** **OWA** voor apparaten uitschakelen en antwoord **Ja** op beide wanneer u daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="6e291-129">Under **Mobile Devices**, select **Disable Exchange ActiveSync** and **Disable OWA for Devices,** and answer **Yes** to both when prompted.</span></span>
4. <span data-ttu-id="6e291-130">Selecteer **onder E-mailconnectiviteit** **de optie Uitschakelen** en antwoord **Ja** wanneer u daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="6e291-130">Under **Email Connectivity**, select **Disable** and answer **Yes** when prompted.</span></span>
