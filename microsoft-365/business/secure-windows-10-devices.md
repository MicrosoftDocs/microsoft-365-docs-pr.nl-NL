---
title: Windows 10-apparaten beveiligen
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: 'Meer informatie over standaard-en andere instellingen voor het beveiligen van Windows 10-apparaten. '
ms.openlocfilehash: c2607b026bca582afcea76d4c0b3e8088c00252d
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288640"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="519db-103">Windows 10-apparaten beveiligen</span><span class="sxs-lookup"><span data-stu-id="519db-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="519db-p101">De instellingen die u hier configureert, maken deel uit van het standaardapparaatbeleid voor Windows 10. Alle gebruikers die verbinding maken via een Windows 10-apparaat - mobiele apparaten en pc's inbegrepen - door zich aan te melden met hun werkaccount, ontvangen automatisch deze instellingen. Het is raadzaam om het standaardbeleid tijdens de installatie te accepteren en later beleidsregels toe te voegen die zijn afgestemd op specifieke groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="519db-p101">The settings that you configure here are part of the default device policy for Windows 10. All users that connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account, will automatically receive these settings. We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="519db-107">Instellingen voor het beveiligen van Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="519db-107">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="519db-p102">Alle instellingen zijn standaard **ingeschakeld**. De volgende instellingen zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="519db-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="519db-110">Instelling</span><span class="sxs-lookup"><span data-stu-id="519db-110">Setting</span></span>  <br/> |<span data-ttu-id="519db-111">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="519db-111">Description</span></span>  <br/> |
|<span data-ttu-id="519db-112">Bescherm pc's tegen virussen en andere bedreigingen met Windows Defender-antivirussoftware</span><span class="sxs-lookup"><span data-stu-id="519db-112">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="519db-113">Daarvoor moet Windows Defender-antivirussoftware zijn ingeschakeld om pc's te beschermen tegen de gevaren die verbinding met internet met zich meebrengt.</span><span class="sxs-lookup"><span data-stu-id="519db-113">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="519db-114">Bescherm pc's tegen internetdreigingen in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="519db-114">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="519db-115">Hiermee worden instellingen in Edge ingeschakeld die gebruikers helpen beschermen tegen schadelijke websites en downloads.</span><span class="sxs-lookup"><span data-stu-id="519db-115">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="519db-116">Apparaatscherm uitschakelen indien inactief gedurende deze periode</span><span class="sxs-lookup"><span data-stu-id="519db-116">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="519db-p103">Hiermee weet u zeker dat bedrijfsgegevens beveiligd zijn als een gebruiker niet actief is. Een gebruiker kan in een openbare locatie werken, zoals een café, en even weggaan of afgeleid worden, waardoor de informatie op het apparaat gemakkelijk door onbekenden bekeken kan worden. Met deze instelling kunt u bepalen hoelang de gebruiker inactief kan zijn voordat het scherm wordt uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="519db-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="519db-120">Gebruikers toestaan om apps te downloaden vanuit de Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="519db-120">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="519db-p104">Hiermee kunnen gebruikers apps downloaden en installeren vanuit de Microsoft Store. Omdat apps kunnen variëren van spelletjes tot productiviteitsprogramma's, laten we deze instelling **ingeschakeld**, maar u kunt de instelling uitschakelen voor extra beveiliging.  </span><span class="sxs-lookup"><span data-stu-id="519db-p104">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="519db-123">Gebruikers toestaan om Cortana te openen</span><span class="sxs-lookup"><span data-stu-id="519db-123">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="519db-p105">Cortana kan bijzonder handig zijn. Het programma kan instellingen inschakelen of uitschakelen, aanwijzingen geven en ervoor zorgen dat u altijd op tijd bent voor afspraken. Daarom laten we het standaard **ingeschakeld**.  </span><span class="sxs-lookup"><span data-stu-id="519db-p105">Cortana can be very helpful! She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.  </span></span><br/> |
|<span data-ttu-id="519db-126">Gebruikers toestaan om Windows-tips en reclame van Microsoft te ontvangen</span><span class="sxs-lookup"><span data-stu-id="519db-126">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="519db-127">Windows-tips kunnen handig zijn en gebruikers op weg helpen wanneer er nieuwe functies beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="519db-127">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="519db-128">Windows 10-apparaten automatisch bijwerken</span><span class="sxs-lookup"><span data-stu-id="519db-128">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="519db-129">Hiermee ontvangen Windows 10-apparaten automatisch de nieuwste updates.</span><span class="sxs-lookup"><span data-stu-id="519db-129">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
   

