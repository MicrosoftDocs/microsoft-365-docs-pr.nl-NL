---
title: Overzicht van instellingen
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Overzicht van de installatie stappen voor Microsoft 365 Business.
ms.openlocfilehash: 425c465262c266ca764ae8c7a52130903fa635a5
ms.sourcegitcommit: 8fda7852b2a5baa92b8a365865b014ea6d100bbc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/03/2019
ms.locfileid: "39812773"
---
# <a name="overview-of-setup"></a><span data-ttu-id="25daa-103">Overzicht van instellingen</span><span class="sxs-lookup"><span data-stu-id="25daa-103">Overview of setup</span></span>

<span data-ttu-id="25daa-104">De meeste installatie stappen kunnen worden uitgevoerd in de installatiewizard, maar de andere opties worden ook weergegeven.</span><span class="sxs-lookup"><span data-stu-id="25daa-104">Most of the setup steps can be done in the setup wizard, but the other options are also listed.</span></span>

## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="25daa-105">Stap 1: Voeg uw domein en gebruikers toe</span><span class="sxs-lookup"><span data-stu-id="25daa-105">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="25daa-106">**[Voeg uw domein toe](set-up.md#add-your-domain-to-personalize-sign-in)** (als u uw domein heeft gekocht tijdens het [Aanmelden](sign-up.md), is deze stap al gedaan.)</span><span class="sxs-lookup"><span data-stu-id="25daa-106">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="25daa-107">**Gebruikers toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="25daa-107">**Add users**.</span></span> <span data-ttu-id="25daa-108">U op de volgende drie manieren gebruikers toevoegen:</span><span class="sxs-lookup"><span data-stu-id="25daa-108">You can add users in any of the three ways:</span></span>
        - <span data-ttu-id="25daa-109">In de [wizard](set-up.md#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="25daa-109">In the [wizard](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="25daa-110">Gebruik adreslijstsynchronisatie om [gebruikers toe te voegen met behulp van Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) als u een on-premises Active Directory hebt.</span><span class="sxs-lookup"><span data-stu-id="25daa-110">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="25daa-111">U ook [gebruikers later toevoegen](add-users-m365b.md) in het Admin Center.</span><span class="sxs-lookup"><span data-stu-id="25daa-111">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="25daa-112">Stap 2: beveiligingsbeleid instellen en apparaten configureren</span><span class="sxs-lookup"><span data-stu-id="25daa-112">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="25daa-113">Gebruik de [wizard Setup](set-up.md#protect-your-organization) om apparaatbeleid te configureren.</span><span class="sxs-lookup"><span data-stu-id="25daa-113">Use the [Setup wizard](set-up.md#protect-your-organization) to configure device policies.</span></span> 
  - <span data-ttu-id="25daa-114">U ook meer toevoegen of later bewerken in het [Beheercentrum](view-policies-and-devices.md) en in de [intune-Portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span><span class="sxs-lookup"><span data-stu-id="25daa-114">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="25daa-115">De instelwizard stelt ook de instellingen voor preventie van bescherming en gegevensverlies in.</span><span class="sxs-lookup"><span data-stu-id="25daa-115">The setup wizard will also set up basic threat protection and data loss prevention settings.</span></span>
  
  <span data-ttu-id="25daa-116">Naast de beveiligingsinstellingen in de installatiewizard u de beveiliging verhogen door de volgende instellingen toe te voegen:</span><span class="sxs-lookup"><span data-stu-id="25daa-116">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

      - <span data-ttu-id="25daa-117">**E-malware bescherming**</span><span class="sxs-lookup"><span data-stu-id="25daa-117">**Email malware protection**</span></span>
      - <span data-ttu-id="25daa-118">**ATP anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="25daa-118">**ATP anti-phishing**</span></span>
      - <span data-ttu-id="25daa-119">**Exchange Online Archiving**</span><span class="sxs-lookup"><span data-stu-id="25daa-119">**Exchange Online Archiving**</span></span>
      - <span data-ttu-id="25daa-120">**Azure Information Protection (Plan1**)</span><span class="sxs-lookup"><span data-stu-id="25daa-120">**Azure Information Protection (Plan1**)</span></span>

          <span data-ttu-id="25daa-121">Om aan de slag te gaan, [stelt u Geavanceerd beveiligingsbeleid in](set-up-advanced-security.md).</span><span class="sxs-lookup"><span data-stu-id="25daa-121">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

        <span data-ttu-id="25daa-122">Zie ook [de Top 10-manieren om uw Microsoft 365-bedrijf te beveiligen](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) voor een roadmap van de beste beveiligingspraktijken.</span><span class="sxs-lookup"><span data-stu-id="25daa-122">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="25daa-123">Stap 3: Windows 10-apparaten instellen en beheren</span><span class="sxs-lookup"><span data-stu-id="25daa-123">Step 3: Set up and manage Windows 10 devices</span></span>

<span data-ttu-id="25daa-124">Nadat u de wizard instellen hebt uitgevoerd, wilt u alle Windwos 10-computers in uw organisatie proctect.</span><span class="sxs-lookup"><span data-stu-id="25daa-124">After you run the set up wizard, you will want to proctect all the Windwos 10 computers in your organization.</span></span>
  
- <span data-ttu-id="25daa-125">Windows 10 Pro is een [vereiste](pre-requisites-for-data-protection.md) voor microsoft 365 Business, maar als u Windows 7 Pro, Windows 8 Pro of Windows 8,1 Pro hebt, geeft uw abonnement u recht op een [upgrade naar Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span><span class="sxs-lookup"><span data-stu-id="25daa-125">Windows 10 Pro is a [prerequisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
- <span data-ttu-id="25daa-126">Volg de stappen in [beveiligde Windows 10-pc's](secure-win-10-pcs.md) om beleid in te stellen voor Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="25daa-126">Follow the steps in [secure Windows 10 PCs](secure-win-10-pcs.md) to set up policies for Windows 10 devices.</span></span>

<span data-ttu-id="25daa-127">Wanneer u lid wordt van een Windows 10-apparaat naar Azure AD, wordt het beleid dat u voor Windows 10-computers hebt ingesteld op deze toegepast.</span><span class="sxs-lookup"><span data-stu-id="25daa-127">When you join a Windows 10 device to Azure AD, the policies you set for Windows 10 computers get applied to it.</span></span> <span data-ttu-id="25daa-128">Zie [Windows-apparaten instellen voor Microsoft 365 zakelijke gebruikers](set-up-windows-devices.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="25daa-128">For more information, see [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md).</span></span>

## <a name="step-4-install-office-365-business"></a><span data-ttu-id="25daa-129">Stap 4: Installeer Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="25daa-129">Step 4: Install Office 365 Business</span></span>
- <span data-ttu-id="25daa-130">U Office op de Windows-apparaten automatisch installeren met behulp van de [wizard Setup](set-up.md#deploy-office-365-client-apps).</span><span class="sxs-lookup"><span data-stu-id="25daa-130">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="25daa-131">Laat gebruikers [Office-apps](https://docs.microsoft.com/office365/admin/setup/install-applications) voor Windows en apparaten installeren.</span><span class="sxs-lookup"><span data-stu-id="25daa-131">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="25daa-132">Geavanceerde</span><span class="sxs-lookup"><span data-stu-id="25daa-132">Advanced</span></span>
- <span data-ttu-id="25daa-133">**Autopilot gebruiken om nieuwe apparaten in te stellen**</span><span class="sxs-lookup"><span data-stu-id="25daa-133">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="25daa-134">U [Windows Autopilot](add-autopilot-devices-and-profile.md) gebruiken voor het automatisch vooraf configureren van **nieuwe** Windows 10-apparaten voor een gebruiker, maar het is misschien gemakkelijker om een [partner](https://www.microsoft.com/solution-providers/search) die dit voor u kan doen.</span><span class="sxs-lookup"><span data-stu-id="25daa-134">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="25daa-135">U ook naar de [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)gaan en een cloudtechnologie-expert vragen om nieuwe apparaten in te stellen die u aanschaft.</span><span class="sxs-lookup"><span data-stu-id="25daa-135">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598), and ask a cloud technology expert to set up new devices that you purchase.</span></span>

- <span data-ttu-id="25daa-136">**Toegang tot on-premises bronnen**</span><span class="sxs-lookup"><span data-stu-id="25daa-136">**Access on-premises resources**</span></span>

     - <span data-ttu-id="25daa-137">Als uw organisatie gebruikmaakt van on-premises Windows Server Active Directory, u Microsoft 365 Business instellen om uw Windows 10-apparaten te beveiligen, terwijl u nog steeds toegang hebt tot on-premises bronnen waarvoor lokale verificatie is vereist.</span><span class="sxs-lookup"><span data-stu-id="25daa-137">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="25daa-138">Volg de stappen in [Windows 10-apparaten met een domein verbinding inschakelen die door Microsoft 365 Business worden beheerd](manage-windows-devices.md) om dit in te stellen.</span><span class="sxs-lookup"><span data-stu-id="25daa-138">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="25daa-139">Dit is de voorkeursmethode en apparaten in deze status worden hybride Azure AD gekoppelde apparaten genoemd.</span><span class="sxs-lookup"><span data-stu-id="25daa-139">This is the preferred method, and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="25daa-140">Als uw bedrijf een lokale Active Directory heeft die bepaalde on-premises bronnen bevat (zoals bestandsshares en printers), u uw Azure AD-gekoppelde apparaten toegang geven tot deze resources door de stappen hier te volgen: [toegang tot on-premises resources van een Azure AD-apparaat in Microsoft 365 Business](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="25daa-140">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers), you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="25daa-141">Zie ook</span><span class="sxs-lookup"><span data-stu-id="25daa-141">See also</span></span>

[<span data-ttu-id="25daa-142">Microsoft 365 zakelijke trainingsvideo's</span><span class="sxs-lookup"><span data-stu-id="25daa-142">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
