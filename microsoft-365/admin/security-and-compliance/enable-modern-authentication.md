---
title: Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Informatie over het instellen van registersleutels om moderne verificatie in te schakelen voor apparaten Microsoft Office 2013 zijn geïnstalleerd.
ms.openlocfilehash: d358cb2ffb4284a51779e5a7c1dc894052b9ebc0
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572283"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="5b86f-103">Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten</span><span class="sxs-lookup"><span data-stu-id="5b86f-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="5b86f-104">Als u moderne verificatie wilt inschakelen voor Windows-apparaten waarop Office 2013 is geïnstalleerd, moet u bepaalde registersleutels instellen.</span><span class="sxs-lookup"><span data-stu-id="5b86f-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="5b86f-105">Moderne verificatie voor Office 2013-clients inschakelen</span><span class="sxs-lookup"><span data-stu-id="5b86f-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="5b86f-106">Moderne verificatie is al ingeschakeld voor Office 2016-clients. U hoeft geen registersleutels in te stellen voor Office 2016.</span><span class="sxs-lookup"><span data-stu-id="5b86f-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="5b86f-p101">Als u moderne verificatie wilt inschakelen voor Windows-apparaten, zoals laptops en tablets, waarop Microsoft Office 2013 is geïnstalleerd, moet u de volgende registersleutels instellen. De sleutels moeten worden ingesteld op elk apparaat waarop u de moderne verificatie wilt inschakelen:</span><span class="sxs-lookup"><span data-stu-id="5b86f-p101">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="5b86f-109">**Registersleutel**</span><span class="sxs-lookup"><span data-stu-id="5b86f-109">**Registry key**</span></span>|<span data-ttu-id="5b86f-110">**Type**</span><span class="sxs-lookup"><span data-stu-id="5b86f-110">**Type**</span></span>|<span data-ttu-id="5b86f-111">**Value**</span><span class="sxs-lookup"><span data-stu-id="5b86f-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="5b86f-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="5b86f-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="5b86f-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="5b86f-113">REG_DWORD</span></span>  |<span data-ttu-id="5b86f-114">1</span><span class="sxs-lookup"><span data-stu-id="5b86f-114">1</span></span>  |
|<span data-ttu-id="5b86f-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="5b86f-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="5b86f-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="5b86f-116">REG_DWORD</span></span> |<span data-ttu-id="5b86f-117">1</span><span class="sxs-lookup"><span data-stu-id="5b86f-117">1</span></span> |
   
<span data-ttu-id="5b86f-118">Nadat u de registersleutels hebt ingesteld, kunt u Office 2013-apparaten instellen op het gebruik van meervoudige verificatie [(MFA)](set-up-multi-factor-authentication.md) met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5b86f-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Microsoft 365.</span></span> 
  
<span data-ttu-id="5b86f-p102">Als u momenteel bent aangemeld met een van de client-apps, moet u zich afmelden en opnieuw aanmelden om de wijziging te effectueren. Anders zijn de MRU- en roaminginstellingen niet beschikbaar tot de ADAL-identiteit is vastgesteld.</span><span class="sxs-lookup"><span data-stu-id="5b86f-p102">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="5b86f-121">Moderne verificatie uitschakelen op apparaten</span><span class="sxs-lookup"><span data-stu-id="5b86f-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="5b86f-122">Als u moderne verificatie wilt uitschakelen op een apparaat, stelt u de volgende registersleutels in op het apparaat:</span><span class="sxs-lookup"><span data-stu-id="5b86f-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="5b86f-123">**Registersleutel**</span><span class="sxs-lookup"><span data-stu-id="5b86f-123">**Registry key**</span></span>|<span data-ttu-id="5b86f-124">**Type**</span><span class="sxs-lookup"><span data-stu-id="5b86f-124">**Type**</span></span>|<span data-ttu-id="5b86f-125">**Value**</span><span class="sxs-lookup"><span data-stu-id="5b86f-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="5b86f-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="5b86f-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="5b86f-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="5b86f-127">REG_DWORD</span></span>|<span data-ttu-id="5b86f-128">0</span><span class="sxs-lookup"><span data-stu-id="5b86f-128">0</span></span>|
   
## <a name="related-content"></a><span data-ttu-id="5b86f-129">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="5b86f-129">Related content</span></span>

<span data-ttu-id="5b86f-130">[Meld u aan bij Office 2013 met een tweede verificatiemethode](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) (artikel)</span><span class="sxs-lookup"><span data-stu-id="5b86f-130">[Sign in to Office 2013 with a second verification method](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) (article)</span></span>

<span data-ttu-id="5b86f-131">[Outlook vraagt om wachtwoord en gebruikt geen](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) moderne verificatie om verbinding te maken met Office 365 (artikel)</span><span class="sxs-lookup"><span data-stu-id="5b86f-131">[Outlook prompts for password and doesn't use Modern Authentication to connect to Office 365](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) (article)</span></span>

