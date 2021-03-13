---
title: Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Informatie over het instellen van registersleutels om moderne verificatie in te schakelen voor apparaten waar Microsoft Office 2013 is geïnstalleerd.
ms.openlocfilehash: 2a4be82328d391db7808cb9197ce259275b567c6
ms.sourcegitcommit: bf9e0091e5bdc78d9b23be64583eb816bb059eb2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/12/2021
ms.locfileid: "50758926"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="381d4-103">Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten</span><span class="sxs-lookup"><span data-stu-id="381d4-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="381d4-104">Als u moderne verificatie wilt inschakelen voor Windows-apparaten waarop Office 2013 is geïnstalleerd, moet u bepaalde registersleutels instellen.</span><span class="sxs-lookup"><span data-stu-id="381d4-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="381d4-105">Moderne verificatie voor Office 2013-clients inschakelen</span><span class="sxs-lookup"><span data-stu-id="381d4-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="381d4-106">Moderne verificatie is al ingeschakeld voor Office 2016-clients. U hoeft geen registersleutels in te stellen voor Office 2016.</span><span class="sxs-lookup"><span data-stu-id="381d4-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="381d4-p101">Als u moderne verificatie wilt inschakelen voor Windows-apparaten, zoals laptops en tablets, waarop Microsoft Office 2013 is geïnstalleerd, moet u de volgende registersleutels instellen. De sleutels moeten worden ingesteld op elk apparaat waarop u de moderne verificatie wilt inschakelen:</span><span class="sxs-lookup"><span data-stu-id="381d4-p101">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="381d4-109">**Registersleutel**</span><span class="sxs-lookup"><span data-stu-id="381d4-109">**Registry key**</span></span>|<span data-ttu-id="381d4-110">**Type**</span><span class="sxs-lookup"><span data-stu-id="381d4-110">**Type**</span></span>|<span data-ttu-id="381d4-111">**Value**</span><span class="sxs-lookup"><span data-stu-id="381d4-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="381d4-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="381d4-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="381d4-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="381d4-113">REG_DWORD</span></span>  |<span data-ttu-id="381d4-114">1</span><span class="sxs-lookup"><span data-stu-id="381d4-114">1</span></span>  |
|<span data-ttu-id="381d4-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="381d4-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="381d4-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="381d4-116">REG_DWORD</span></span> |<span data-ttu-id="381d4-117">1</span><span class="sxs-lookup"><span data-stu-id="381d4-117">1</span></span> |
   
<span data-ttu-id="381d4-118">Nadat u de registersleutels hebt ingesteld, kunt u office 2013-apparaten-apps instellen op meervoudige verificatie [(MFA)](set-up-multi-factor-authentication.md) met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="381d4-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Microsoft 365.</span></span> 
  
<span data-ttu-id="381d4-p102">Als u momenteel bent aangemeld met een van de client-apps, moet u zich afmelden en opnieuw aanmelden om de wijziging te effectueren. Anders zijn de MRU- en roaminginstellingen niet beschikbaar tot de ADAL-identiteit is vastgesteld.</span><span class="sxs-lookup"><span data-stu-id="381d4-p102">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="381d4-121">Moderne verificatie uitschakelen op apparaten</span><span class="sxs-lookup"><span data-stu-id="381d4-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="381d4-122">Als u moderne verificatie wilt uitschakelen op een apparaat, stelt u de volgende registersleutels in op het apparaat:</span><span class="sxs-lookup"><span data-stu-id="381d4-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="381d4-123">**Registersleutel**</span><span class="sxs-lookup"><span data-stu-id="381d4-123">**Registry key**</span></span>|<span data-ttu-id="381d4-124">**Type**</span><span class="sxs-lookup"><span data-stu-id="381d4-124">**Type**</span></span>|<span data-ttu-id="381d4-125">**Value**</span><span class="sxs-lookup"><span data-stu-id="381d4-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="381d4-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="381d4-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="381d4-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="381d4-127">REG_DWORD</span></span>|<span data-ttu-id="381d4-128">0</span><span class="sxs-lookup"><span data-stu-id="381d4-128">0</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="381d4-129">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="381d4-129">Related articles</span></span>
[<span data-ttu-id="381d4-130">Aanmelden bij Office 2013 met een tweede verificatiemethode</span><span class="sxs-lookup"><span data-stu-id="381d4-130">Sign in to Office 2013 with a second verification method</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

[<span data-ttu-id="381d4-131">Outlook vraagt om wachtwoord en gebruikt geen moderne verificatie om verbinding te maken met Office 365</span><span class="sxs-lookup"><span data-stu-id="381d4-131">Outlook prompts for password and doesn't use Modern Authentication to connect to Office 365</span></span>](https://docs.microsoft.com/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled)

  
