---
title: Skype voor Bedrijven Online beheren met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: Gebruik PowerShell voor Microsoft 365 om beleidsregels voor Skype voor Bedrijven Online, beleidsregels per gebruiker en vergaderingsinstellingen te beheren.
ms.openlocfilehash: 4477dadf0ea38a81ac0ae282da3f74fc12f3406f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916678"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="de549-103">Skype voor Bedrijven Online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="de549-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="de549-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="de549-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="de549-105">De beheerders van Skype voor Bedrijven Online zijn verantwoordelijk voor het beleidsbeheer.</span><span class="sxs-lookup"><span data-stu-id="de549-105">Skype for Business Online administrators are responsible for managing policies.</span></span> <span data-ttu-id="de549-106">Sommige van deze taken zijn uit te voeren in het Microsoft 365-beheercentrum. Andere taken zijn gemakkelijker uit te voeren in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de549-106">Although you can do some of these tasks in the Microsoft 365 admin center, others are easier to do in PowerShell.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="de549-107">Voordat u van start gaat</span><span class="sxs-lookup"><span data-stu-id="de549-107">Before you start</span></span>

  > [!Note]
   > <span data-ttu-id="de549-108">Skype voor Bedrijven Online-connector maakt momenteel deel uit van de nieuwste Teams PowerShell-module.</span><span class="sxs-lookup"><span data-stu-id="de549-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="de549-109">Als u de meest recente openbare versie van Teams PowerShell gebruikt, hoeft u de Skype voor Bedrijven Online-connector niet te installeren.</span><span class="sxs-lookup"><span data-stu-id="de549-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
<span data-ttu-id="de549-110">Installeer de [Teams PowerShell-module](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="de549-110">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>


## <a name="connect-using-admin-credentials"></a><span data-ttu-id="de549-111">Verbinding maken met beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="de549-111">Connect using admin credentials</span></span>

1. <span data-ttu-id="de549-112">Open een opdrachtpromptvenster van Windows PowerShell en voer de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="de549-112">Open a Windows PowerShell command prompt window and run the following commands:</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

2. <span data-ttu-id="de549-113">Voer in het dialoogvenster **Referentieaanvraag voor Windows PowerShell** de naam en het wachtwoord van uw administrator-account en selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="de549-113">In the **Windows PowerShell Credential Request** dialog box, type your administrator account name and password, and then select **OK**.</span></span>


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a><span data-ttu-id="de549-114">Verbinding maken met een beheerdersaccount met meervoudige verificatie</span><span class="sxs-lookup"><span data-stu-id="de549-114">Connect using an admin account with multi-factor authentication</span></span>

1. <span data-ttu-id="de549-115">Open een Windows PowerShell-opdrachtpromptvenster en voer de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="de549-115">Open a Windows PowerShell command prompt window, and run the following commands:</span></span>

   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

2. <span data-ttu-id="de549-116">Voer uw administrator-accountnaam voor Skype voor Bedrijven Online in wanneer u hierom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="de549-116">When prompted enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="de549-117">Voer in het dialoogvenster **Aanmelden bij uw account** uw administrator-wachtwoord voor Skype voor Bedrijven Online en klik op **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="de549-117">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password and select **Sign in**.</span></span>

4. <span data-ttu-id="de549-118">Volg de instructies in het dialoogvenster **Aanmelden bij uw account** om verificatiegegevens toe te voegen, zoals een verificatiecode. Klik vervolgens op **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="de549-118">In the **Sign in to your account** dialog box, follow the instructions to add authentication information, such as a verification code, and then select **Verify**.</span></span>

<span data-ttu-id="de549-119">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="de549-119">For more information, see:</span></span>
  
- [<span data-ttu-id="de549-120">Beleidsregels voor Skype voor Bedrijven Online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="de549-120">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="de549-121">Beleidsregels per gebruiker toewijzen voor Skype voor Bedrijven Online met PowerShell</span><span class="sxs-lookup"><span data-stu-id="de549-121">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="de549-122">Zie ook</span><span class="sxs-lookup"><span data-stu-id="de549-122">See also</span></span>

[<span data-ttu-id="de549-123">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="de549-123">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="de549-124">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="de549-124">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="de549-125">PowerShell-cmdlet-verwijzingen voor Skype voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="de549-125">Skype for Business PowerShell cmdlet references</span></span>](/powershell/module/skype/?view=skype-ps)