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
description: 'Overzicht: Gebruik PowerShell voor Microsoft 365 om beleidsregels voor Skype voor Bedrijven Online, beleid per gebruiker en vergaderingsinstellingen te beheren.'
ms.openlocfilehash: aea78d135a5d7ffbb5d8480c549d0fdee88f7d51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689403"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="52c26-103">Skype voor Bedrijven Online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="52c26-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="52c26-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="52c26-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="52c26-105">Een van de belangrijkste taken van een beheerder van Skype voor Bedrijven Online is beleidsbeheer.</span><span class="sxs-lookup"><span data-stu-id="52c26-105">One of the primary tasks of any Skype for Business Online administrator is managing policies.</span></span> <span data-ttu-id="52c26-106">Hoewel u sommige van deze taken kunt uitvoeren in het Microsoft 365-beheercentrum, is het uitvoeren van andere taken veel sneller en eenvoudiger in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="52c26-106">Although you can accomplish some of these tasks in the Microsoft 365 admin center, other tasks are much quicker and easier in PowerShell.</span></span> 

## <a name="before-you-start"></a><span data-ttu-id="52c26-107">Voordat u van start gaat</span><span class="sxs-lookup"><span data-stu-id="52c26-107">Before you start</span></span>

<span data-ttu-id="52c26-108">Download en installeer de [Skype voor Business Online-connectormodule](https://www.microsoft.com/download/details.aspx?id=39366) en start vervolgens uw computer opnieuw op.</span><span class="sxs-lookup"><span data-stu-id="52c26-108">Download and install the [Skype for Business Online Connector module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer.</span></span>


## <a name="connect-using-a-skype-for-business-online-administrator-account-name-and-password"></a><span data-ttu-id="52c26-109">Verbinding maken met een administrator-accountnaam en wachtwoord voor Skype voor Bedrijven Online</span><span class="sxs-lookup"><span data-stu-id="52c26-109">Connect using a Skype for Business Online administrator account name and password</span></span>

1. <span data-ttu-id="52c26-110">Open een opdrachtprompt van Windows PowerShell en voer de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="52c26-110">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="52c26-111">Typ in het dialoogvenster **Referentieaanvraag voor Windows PowerShell** uw administrator-accountnaam en wachtwoord voor Skype voor Bedrijven Online en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="52c26-111">In the **Windows PowerShell Credential Request** dialog box, type your Skype for Business Online administrator account name and password, and then click **OK**.</span></span>


## <a name="connect-using-a-skype-for-business-online-administrator-account-with-multi-factor-authentication"></a><span data-ttu-id="52c26-112">Verbinding maken met een administrator-account voor Skype voor Bedrijven Online met meervoudige verificatie</span><span class="sxs-lookup"><span data-stu-id="52c26-112">Connect using a Skype for Business Online administrator account with multi-factor authentication</span></span>

1. <span data-ttu-id="52c26-113">Open een opdrachtprompt van Windows PowerShell en voer de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="52c26-113">Open a Windows PowerShell command prompt and run the following commands:</span></span>

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="52c26-114">Voer uw administrator-accountnaam voor Skype voor Bedrijven Online in wanneer de **New-CsOnlineSession**-opdracht u hierom vraagt.</span><span class="sxs-lookup"><span data-stu-id="52c26-114">When prompted by the **New-CsOnlineSession** command, enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="52c26-115">Typ in het dialoogvenster **Aanmelden bij uw account** uw administrator-wachtwoord voor Skype voor Bedrijven Online en klik vervolgens op **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="52c26-115">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password, and then click **Sign in**.</span></span>

4. <span data-ttu-id="52c26-116">Volg de instructies in het dialoogvenster **Aanmelden bij uw account** om aanvullende verificatiegegevens op te geven, zoals een verificatiecode, en klik vervolgens op **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="52c26-116">Follow the instructions in the **Sign in to your account** dialog box to provide additional authentication information, such as a verification code, and then click **Verify**.</span></span>

<span data-ttu-id="52c26-117">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="52c26-117">For more information, see the following topics:</span></span>
  
- [<span data-ttu-id="52c26-118">Beleidsregels voor Skype voor Bedrijven Online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="52c26-118">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="52c26-119">Beleidsregels per gebruiker toewijzen voor Skype voor Bedrijven Online met PowerShell</span><span class="sxs-lookup"><span data-stu-id="52c26-119">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="52c26-120">Zie ook</span><span class="sxs-lookup"><span data-stu-id="52c26-120">See also</span></span>

[<span data-ttu-id="52c26-121">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="52c26-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="52c26-122">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="52c26-122">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="52c26-123">PowerShell-cmdlet-verwijzingen voor Skype voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="52c26-123">Skype for Business PowerShell cmdlet references</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)

