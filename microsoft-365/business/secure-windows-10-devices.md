---
title: Windows 10-apparaten beveiligen
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: Meer informatie over het configureren van de instellingen van het standaardapparaatbeleid dat een Windows 10-apparaat ontvangt bij het aanmelden bij hun werk- of schoolaccount.
ms.openlocfilehash: 85383b1e1d2f2af3fd49d4a0c56c5d99586d607d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912605"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="a5887-103">Windows 10-apparaten beveiligen</span><span class="sxs-lookup"><span data-stu-id="a5887-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="a5887-104">Dit artikel is van toepassing op Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="a5887-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="a5887-105">De instellingen die u hier configureert, maken deel uit van het standaardapparaatbeleid voor Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a5887-105">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="a5887-106">Alle gebruikers die een Windows 10-apparaat, inclusief mobiele apparaten en pc's, verbinden door zich aan te melden met hun werkaccount, ontvangen automatisch deze instellingen.</span><span class="sxs-lookup"><span data-stu-id="a5887-106">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="a5887-107">Het is raadzaam om het standaardbeleid tijdens de installatie te accepteren en later beleidsregels toe te voegen die zijn afgestemd op specifieke groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="a5887-107">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="a5887-108">Instellingen voor het beveiligen van Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="a5887-108">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="a5887-p102">Alle instellingen zijn standaard **ingeschakeld**. De volgende instellingen zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="a5887-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a5887-111">Instelling</span><span class="sxs-lookup"><span data-stu-id="a5887-111">Setting</span></span>  <br/> |<span data-ttu-id="a5887-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="a5887-112">Description</span></span>  <br/> |
|<span data-ttu-id="a5887-113">Bescherm pc's tegen virussen en andere bedreigingen met Windows Defender-antivirussoftware</span><span class="sxs-lookup"><span data-stu-id="a5887-113">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="a5887-114">Daarvoor moet Windows Defender-antivirussoftware zijn ingeschakeld om pc's te beschermen tegen de gevaren die verbinding met internet met zich meebrengt.</span><span class="sxs-lookup"><span data-stu-id="a5887-114">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="a5887-115">Bescherm pc's tegen internetdreigingen in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a5887-115">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="a5887-116">Hiermee worden instellingen in Edge ingeschakeld die gebruikers helpen beschermen tegen schadelijke websites en downloads.</span><span class="sxs-lookup"><span data-stu-id="a5887-116">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="a5887-117">Bestanden en mappen op pc's beschermen tegen onbevoegde toegang met BitLocker</span><span class="sxs-lookup"><span data-stu-id="a5887-117">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="a5887-118">Bitlocker beschermt gegevens door de harde schijven van de computer te versleutelen en te beschermen tegen blootstelling van gegevens als een computer zoekraakt of wordt gestolen.</span><span class="sxs-lookup"><span data-stu-id="a5887-118">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen.</span></span> <span data-ttu-id="a5887-119">Zie Veelgestelde vragen [over Bitlocker voor meer informatie.](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)</span><span class="sxs-lookup"><span data-stu-id="a5887-119">For more information, see [Bitlocker FAQ](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).</span></span>  <br/> |
|<span data-ttu-id="a5887-120">Apparaatscherm uitschakelen indien inactief gedurende deze periode</span><span class="sxs-lookup"><span data-stu-id="a5887-120">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="a5887-p104">Hiermee weet u zeker dat bedrijfsgegevens beveiligd zijn als een gebruiker niet actief is. Een gebruiker kan in een openbare locatie werken, zoals een café, en even weggaan of afgeleid worden, waardoor de informatie op het apparaat gemakkelijk door onbekenden bekeken kan worden. Met deze instelling kunt u bepalen hoelang de gebruiker inactief kan zijn voordat het scherm wordt uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a5887-p104">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|