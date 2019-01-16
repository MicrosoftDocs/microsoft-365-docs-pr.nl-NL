---
title: Beveiligingsinstellingen voor apps op Windows 10-pc's valideren
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Informatie over het valideren van de beveiligingsinstellingen van Microsoft 365 Business app in Windows 10-apparaten.
ms.openlocfilehash: db05c86bd75cc30e22e025034a3dab478d0f5365
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "26982702"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="1b070-103">Instellingen voor apparaatbeveiliging controleren op Windows 10-pc's</span><span class="sxs-lookup"><span data-stu-id="1b070-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="1b070-104">Controleren of Windows 10-apparaatbeleid is ingesteld</span><span class="sxs-lookup"><span data-stu-id="1b070-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="1b070-p101">Nadat u [apparaatbeleid hebt ingesteld](protection-settings-for-windows-10-pcs.md), kan het enkele uren duren voordat het beleid van kracht wordt op apparaten van gebruikers. U kunt controleren of het beleid van kracht is door verschillende schermen met Windows-instellingen te bekijken op de apparaten van gebruikers. Omdat de gebruikers niet de mogelijkheid hebben om de instellingen voor Windows Update en Windows Defender Antivirus te wijzigen op hun Windows 10-apparaten, worden veel van deze opties lichter gekleurd weergegeven.</span><span class="sxs-lookup"><span data-stu-id="1b070-p101">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices. You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices. Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, a lot of those options will be greyed out.</span></span>
  
1. <span data-ttu-id="1b070-108">Ga naar **Instellingen** \> **Update &amp; security** \> **Windows Update** \> **Opties voor opnieuw starten** en te bevestigen dat alle instellingen grijs worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="1b070-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are greyed out.</span></span> 
    
    ![All the Restart options are greyed out.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="1b070-110">Ga naar **Instellingen** \> **Update &amp; security** \> **Windows Update** \> **Geavanceerde opties** en Bevestig dat alle instellingen grijs worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="1b070-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are greyed out.</span></span> 
    
    ![Windows Advanced updates options are all greyed out.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="1b070-112">Ga naar **Instellingen** \> **Update &amp; security** \> **Windows Update** \> **Geavanceerde opties** \> **kiezen hoe updates worden geleverd**.</span><span class="sxs-lookup"><span data-stu-id="1b070-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="1b070-113">Controleer of u het bericht (in het rood) ziet dat bepaalde instellingen zijn verborgen of worden beheerd door uw organisatie en dat alle opties lichter gekleurd worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="1b070-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are greyed out.</span></span>
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="1b070-115">De Windows Defender om Beveiligingscentrum te openen, gaat u naar **Instellingen** \> **Update &amp; security** \> **Windows Defender** \> Klik **Open Windows Defender Security Center** op \> **Virus &amp; thread bescherming** \> **Virus &amp; beveiligingsinstellingen gevaar**.</span><span class="sxs-lookup"><span data-stu-id="1b070-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="1b070-116">Controleer of alle opties lichter gekleurd worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="1b070-116">Verify that all options are greyed out.</span></span> 
    
    ![The Virus and threat protection settings are greyed out.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="1b070-118">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="1b070-118">Related Topics</span></span>

[<span data-ttu-id="1b070-119">Microsoft 365 Business-documentatie en -informatiebronnen</span><span class="sxs-lookup"><span data-stu-id="1b070-119">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="1b070-120">Aan de slag met Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="1b070-120">Get started with Microsoft 365 Business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="1b070-121">Microsoft 365 Business beheren</span><span class="sxs-lookup"><span data-stu-id="1b070-121">Manage Microsoft 365 Business</span></span>](manage.md)
  
[<span data-ttu-id="1b070-122">Instellingen voor apparaatbeveiliging instellen voor Windows 10-pc's</span><span class="sxs-lookup"><span data-stu-id="1b070-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

