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
ms.openlocfilehash: d50f35d7d5e81622eb8dfc3bbf8328a8c43e9676
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430032"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="69d4d-103">Skype voor Bedrijven Online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="69d4d-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="69d4d-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="69d4d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="69d4d-105">De beheerders van Skype voor Bedrijven Online zijn verantwoordelijk voor het beleidsbeheer.</span><span class="sxs-lookup"><span data-stu-id="69d4d-105">Skype for Business Online administrators are responsible for managing policies.</span></span> <span data-ttu-id="69d4d-106">Sommige van deze taken zijn uit te voeren in het Microsoft 365-beheercentrum. Andere taken zijn gemakkelijker uit te voeren in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69d4d-106">Although you can do some of these tasks in the Microsoft 365 admin center, others are easier to do in PowerShell.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="69d4d-107">Voordat u van start gaat</span><span class="sxs-lookup"><span data-stu-id="69d4d-107">Before you start</span></span>

<span data-ttu-id="69d4d-108">Download en installeer de [Skype voor Business Online Windows PowerShell-module](https://www.microsoft.com/download/details.aspx?id=39366) en start de computer vervolgens opnieuw op.</span><span class="sxs-lookup"><span data-stu-id="69d4d-108">Download and install the [Skype for Business Online Windows PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer.</span></span>


## <a name="connect-using-skype-for-business-online-admin-credentials"></a><span data-ttu-id="69d4d-109">Verbinding maken met de beheerdersreferenties van Skype voor Bedrijven Online</span><span class="sxs-lookup"><span data-stu-id="69d4d-109">Connect using Skype for Business Online admin credentials</span></span>

1. <span data-ttu-id="69d4d-110">Open een opdrachtpromptvenster van Windows PowerShell en voer de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="69d4d-110">Open a Windows PowerShell command prompt window and run the following commands:</span></span>
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="69d4d-111">Voer in het dialoogvenster **Referentieaanvraag voor Windows PowerShell** de naam en het wachtwoord van uw administratoraccount voor Skype voor Bedrijven Online en klik **OK**.</span><span class="sxs-lookup"><span data-stu-id="69d4d-111">In the **Windows PowerShell Credential Request** dialog box, type your Skype for Business Online administrator account name and password, and then select **OK**.</span></span>


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a><span data-ttu-id="69d4d-112">Verbinding maken met een beheerdersaccount met meervoudige verificatie</span><span class="sxs-lookup"><span data-stu-id="69d4d-112">Connect using an admin account with multi-factor authentication</span></span>

1. <span data-ttu-id="69d4d-113">Open een Windows PowerShell-opdrachtpromptvenster en voer de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="69d4d-113">Open a Windows PowerShell command prompt window, and run the following commands:</span></span>

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="69d4d-114">Voer uw administrator-accountnaam voor Skype voor Bedrijven Online in wanneer de **New-CsOnlineSession**-opdracht u hierom vraagt.</span><span class="sxs-lookup"><span data-stu-id="69d4d-114">When prompted by the **New-CsOnlineSession** command, enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="69d4d-115">Voer in het dialoogvenster **Aanmelden bij uw account** uw administrator-wachtwoord voor Skype voor Bedrijven Online en klik op **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="69d4d-115">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password and select **Sign in**.</span></span>

4. <span data-ttu-id="69d4d-116">Volg de instructies in het dialoogvenster **Aanmelden bij uw account** om verificatiegegevens toe te voegen, zoals een verificatiecode. Klik vervolgens op **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="69d4d-116">In the **Sign in to your account** dialog box, follow the instructions to add authentication information, such as a verification code, and then select **Verify**.</span></span>

<span data-ttu-id="69d4d-117">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="69d4d-117">For more information, see:</span></span>
  
- [<span data-ttu-id="69d4d-118">Beleidsregels voor Skype voor Bedrijven Online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="69d4d-118">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="69d4d-119">Beleidsregels per gebruiker toewijzen voor Skype voor Bedrijven Online met PowerShell</span><span class="sxs-lookup"><span data-stu-id="69d4d-119">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="69d4d-120">Zie ook</span><span class="sxs-lookup"><span data-stu-id="69d4d-120">See also</span></span>

[<span data-ttu-id="69d4d-121">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="69d4d-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="69d4d-122">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="69d4d-122">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="69d4d-123">PowerShell-cmdlet-verwijzingen voor Skype voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="69d4d-123">Skype for Business PowerShell cmdlet references</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
