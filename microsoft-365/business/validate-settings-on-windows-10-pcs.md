---
title: Beveiligingsinstellingen voor apps op Windows 10-pc's valideren
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Lees hoe u controleren of de instellingen voor de beveiliging van microsoft 365 voor bedrijven-apps van kracht zijn geworden op de Windows 10-apparaten van uw gebruikers.
ms.openlocfilehash: b63681f040b0fe49127693e9cb7aac7ba6c41af6
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635699"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="b0cdd-103">Instellingen voor apparaatbeveiliging controleren op Windows 10-pc's</span><span class="sxs-lookup"><span data-stu-id="b0cdd-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="b0cdd-104">Controleren of Windows 10-apparaatbeleid is ingesteld</span><span class="sxs-lookup"><span data-stu-id="b0cdd-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="b0cdd-105">Nadat u [apparaatbeleid hebt ingesteld](protection-settings-for-windows-10-pcs.md), kan het enkele uren duren voordat het beleid van kracht wordt op apparaten van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="b0cdd-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="b0cdd-106">U kunt controleren of het beleid van kracht is door verschillende schermen met Windows-instellingen te bekijken op de apparaten van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="b0cdd-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="b0cdd-107">Omdat de gebruikers de instellingen voor Windows Update en Windows Defender Antivirus op hun Windows 10-apparaten niet kunnen wijzigen, worden veel opties grijs weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b0cdd-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="b0cdd-108">Ga naar **Instellingen** \> \*\*Update-beveiligingsupdate &amp; \*\* \> **Windows Update** \> **Startopties opnieuw op** en controleer of alle instellingen grijs zijn.</span><span class="sxs-lookup"><span data-stu-id="b0cdd-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![Alle opties voor opnieuw opstarten worden grijs weergegeven.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="b0cdd-110">Ga naar **Instellingen** \> **Update &amp; beveiligingsupdate** \> **De geavanceerde opties** voor Windows **Update** \> en controleer of alle instellingen grijs zijn weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b0cdd-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Windows Advanced-updatesopties zijn allemaal grijs weergegeven.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="b0cdd-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span><span class="sxs-lookup"><span data-stu-id="b0cdd-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="b0cdd-113">Controleer of u het bericht (in het rood) zien dat sommige instellingen door uw organisatie worden verborgen of beheerd en dat alle opties grijs worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b0cdd-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="b0cdd-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span><span class="sxs-lookup"><span data-stu-id="b0cdd-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="b0cdd-116">Controleer of alle opties grijs zijn weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b0cdd-116">Verify that all options are grayed out.</span></span> 
    
    ![De instellingen voor virus- en bedreigingsbeveiliging worden grijs weergegeven.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="b0cdd-118">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b0cdd-118">Related Topics</span></span>

[<span data-ttu-id="b0cdd-119">Microsoft 365 voor bedrijfsdocumentatie en -bronnen</span><span class="sxs-lookup"><span data-stu-id="b0cdd-119">Microsoft 365 for business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="b0cdd-120">Aan de slag met Microsoft 365 voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="b0cdd-120">Get started with Microsoft 365 for business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="b0cdd-121">Microsoft 365 voor bedrijven beheren</span><span class="sxs-lookup"><span data-stu-id="b0cdd-121">Manage Microsoft 365 for business</span></span>](manage.md)
  
[<span data-ttu-id="b0cdd-122">Instellingen voor apparaatbeveiliging instellen voor Windows 10-pc's</span><span class="sxs-lookup"><span data-stu-id="b0cdd-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

