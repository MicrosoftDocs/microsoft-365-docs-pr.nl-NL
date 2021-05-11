---
title: Stap 7 - Het gebruikersaccount van een voormalige werknemer verwijderen
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
description: Volg deze stappen om het gebruikersaccount van een voormalige werknemer te verwijderen.
ms.openlocfilehash: 0afa9b112919d2668d7553ac5bcf08e664bc1749
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244193"
---
# <a name="step-7---delete-a-former-employees-user-account"></a><span data-ttu-id="c4802-103">Stap 7 - Het gebruikersaccount van een voormalige werknemer verwijderen</span><span class="sxs-lookup"><span data-stu-id="c4802-103">Step 7 - Delete a former employee's user account</span></span>

<span data-ttu-id="c4802-104">Nadat u de gegevens van de voormalige werknemer hebt opgeslagen en beschikbaar hebt gemaakt, kunt u het account van de werknemer verwijderen.</span><span class="sxs-lookup"><span data-stu-id="c4802-104">After you've saved and accessed all the former employee's user data, you can delete the former employee's account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4802-p101">Verwijder het account niet als u doorsturen van e-mail hebt ingesteld of het account hebt omgezet naar een gedeeld postvak. Het account is nodig om het gedeelde postvak of het doorsturen van e-mail te kunnen blijven gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c4802-p101">Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.</span></span>

1. <span data-ttu-id="c4802-107">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="c4802-107">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c4802-108">Selecteer de naam van de werknemer die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="c4802-108">Select the name of the employee that you want to delete.</span></span>
3. <span data-ttu-id="c4802-109">Selecteer onder de naam van de gebruiker de optie **Gebruiker verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="c4802-109">Under the user's name, select **Delete user**.</span></span> <span data-ttu-id="c4802-110">Kies de opties die u voor deze gebruiker wilt gebruiken en selecteer **vervolgens Gebruiker verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="c4802-110">Choose the options you want for this user, and then select **Delete user**.</span></span> <span data-ttu-id="c4802-111">Als u al een andere gebruiker toegang hebt gegeven tot de e-mail en OneDrive van deze gebruiker, hoeft u dit hier niet opnieuw te doen.</span><span class="sxs-lookup"><span data-stu-id="c4802-111">If you've already given another user access to this user's email and OneDrive, you don't have to do it again here.</span></span>

<span data-ttu-id="c4802-p103">Wanneer u een gebruiker verwijdert, wordt het account inactief gedurende ongeveer 30 dagen. Tot die tijd kunt u het account herstellen. Daarna worden de gegevens permanent verwijderd.</span><span class="sxs-lookup"><span data-stu-id="c4802-p103">When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.</span></span>
  
## <a name="does-your-organization-use-active-directory"></a><span data-ttu-id="c4802-114">Maakt uw organisatie gebruik van Active Directory?</span><span class="sxs-lookup"><span data-stu-id="c4802-114">Does your organization use Active Directory?</span></span>

<span data-ttu-id="c4802-115">Als uw organisatie gebruikersaccounts synchroniseert Microsoft 365 vanuit een lokale Active Directory-omgeving, moet u deze gebruikersaccounts in uw lokale Active Directory-service verwijderen en herstellen.</span><span class="sxs-lookup"><span data-stu-id="c4802-115">If your organization synchronizes user accounts to Microsoft 365 from a local Active Directory environment, you must delete and restore those user accounts in your local Active Directory service.</span></span> <span data-ttu-id="c4802-116">U kunt ze niet verwijderen of herstellen via Office 365.</span><span class="sxs-lookup"><span data-stu-id="c4802-116">You can't delete or restore them in Office 365.</span></span>

<span data-ttu-id="c4802-117">Zie Een gebruikersaccount [verwijderen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))voor meer informatie over het verwijderen en herstellen van gebruikersaccounts in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c4802-117">To learn how to delete and restore user account in Active Directory, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>
  
<span data-ttu-id="c4802-118">Zie de cmdlet Remove-MsolUser PowerShell Azure Active Directory u de powershell-cmdlet [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c4802-118">If you're using Azure Active Directory, see the [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell cmdlet.</span></span>
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a><span data-ttu-id="c4802-119">Wat u moet weten over het beëindigen van een sessie van een werknemer</span><span class="sxs-lookup"><span data-stu-id="c4802-119">What you need to know about terminating an employee's email session</span></span>

<span data-ttu-id="c4802-120">Zo ontzegt u een werknemer de toegang tot e-mail (Exchange).</span><span class="sxs-lookup"><span data-stu-id="c4802-120">Here's information about how to get an employee out of email (Exchange).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c4802-121">**Wat u kunt doen**</span><span class="sxs-lookup"><span data-stu-id="c4802-121">**What you can do**</span></span> <br/> |<span data-ttu-id="c4802-122">**Hoe u dat kunt doen**</span><span class="sxs-lookup"><span data-stu-id="c4802-122">**How you do it**</span></span> <br/> |
|<span data-ttu-id="c4802-123">Een sessie beëindigen (zoals voor de webversie van Outlook, Outlook, Exchange Active Sync, enzovoort) en een nieuwe sessie geforceerd openen</span><span class="sxs-lookup"><span data-stu-id="c4802-123">Terminate a session (such as Outlook on the web, Outlook, Exchange active sync, etc.) and force to open a new session</span></span>  <br/> |<span data-ttu-id="c4802-124">Wachtwoord opnieuw instellen</span><span class="sxs-lookup"><span data-stu-id="c4802-124">Reset password</span></span>  <br/> |
|<span data-ttu-id="c4802-125">Een sessie beëindigen en toegang blokkeren voor toekomstige sessies (voor alle protocollen)</span><span class="sxs-lookup"><span data-stu-id="c4802-125">Terminate a session and block access to future sessions (for all protocols)</span></span>  <br/> |<span data-ttu-id="c4802-126">Schakel het account uit.</span><span class="sxs-lookup"><span data-stu-id="c4802-126">Disable the account.</span></span> <span data-ttu-id="c4802-127">Bijvoorbeeld(in het Exchange beheercentrum of met PowerShell):</span><span class="sxs-lookup"><span data-stu-id="c4802-127">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|<span data-ttu-id="c4802-128">De sessie voor een bepaald protocol (zoals ActiveSync) beëindigen</span><span class="sxs-lookup"><span data-stu-id="c4802-128">Terminate the session for a particular protocol (such as ActiveSync)</span></span>  <br/> |<span data-ttu-id="c4802-129">Schakel het protocol uit.</span><span class="sxs-lookup"><span data-stu-id="c4802-129">Disable the protocol.</span></span> <span data-ttu-id="c4802-130">Bijvoorbeeld(in het Exchange beheercentrum of met PowerShell):</span><span class="sxs-lookup"><span data-stu-id="c4802-130">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

<span data-ttu-id="c4802-131">De bovenstaande bewerkingen kunnen op drie plaatsen worden uitgevoerd:</span><span class="sxs-lookup"><span data-stu-id="c4802-131">The above operations can be done in three places:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c4802-132">**Als u de sessie hier beëindigt**</span><span class="sxs-lookup"><span data-stu-id="c4802-132">**If you terminate the session here**</span></span> <br/> |<span data-ttu-id="c4802-133">**Hoe lang dit duurt**</span><span class="sxs-lookup"><span data-stu-id="c4802-133">**How long it takes**</span></span> <br/> |
|<span data-ttu-id="c4802-134">In het Exchange-beheercentrum of via PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4802-134">In the Exchange admin center or using PowerShell</span></span>  <br/> |<span data-ttu-id="c4802-135">Verwachte vertraging is korter dan 30 minuten</span><span class="sxs-lookup"><span data-stu-id="c4802-135">Expected delay is within 30 min</span></span>  <br/> |
|<span data-ttu-id="c4802-136">In het Azure Active Directory-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="c4802-136">In the Azure Active Directory admin center</span></span>  <br/> |<span data-ttu-id="c4802-137">Verwachte vertraging is 60 minuten</span><span class="sxs-lookup"><span data-stu-id="c4802-137">Expected delay is 60 min</span></span>  <br/> |
|<span data-ttu-id="c4802-138">In een lokale omgeving</span><span class="sxs-lookup"><span data-stu-id="c4802-138">In an on-premises environment</span></span>  <br/> |<span data-ttu-id="c4802-139">Verwachte vertraging is 3 uur of langer</span><span class="sxs-lookup"><span data-stu-id="c4802-139">Expected delay is 3 hours or more</span></span>  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a><span data-ttu-id="c4802-140">Zo krijgt u de snelste reactie voor het beëindigen van een account</span><span class="sxs-lookup"><span data-stu-id="c4802-140">How to get fastest response for account termination</span></span>

 <span data-ttu-id="c4802-p107">**Snelst**: maak gebruik van het Exchange-beheercentrum (gebruik PowerShell) of van het Azure Active Directory-beheercentrum. In een on-premises omgeving kan het enkele uren duren om de wijziging via DirSync te synchroniseren.</span><span class="sxs-lookup"><span data-stu-id="c4802-p107">**Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync.</span></span>
  
 <span data-ttu-id="c4802-p108">**Snelst voor een gebruiker met aanwezigheid on-premises en in het Exchange-Datacenter**: Beëindig de sessie met behulp van het Azure Active Directory-beheercentrum/Exchange-beheercentrum, en breng de wijziging OOK aan in de on-premises omgeving. Anders worden de wijzigingen in het Azure Active Directory-beheercentrum/Exchange-beheercentrum overschreven door DirSync.</span><span class="sxs-lookup"><span data-stu-id="c4802-p108">**Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="c4802-145">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="c4802-145">Related articles</span></span>

[<span data-ttu-id="c4802-146">Een gebruiker herstellen</span><span class="sxs-lookup"><span data-stu-id="c4802-146">Restore a user</span></span>](restore-user.md)