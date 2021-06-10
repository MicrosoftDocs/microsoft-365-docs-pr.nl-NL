---
title: Niet-beheerde Windows 10 pc's en Macs beveiligen
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Bescherm onmanaged of bring-your-own devices (BYOD) met Microsoft 365.
ms.openlocfilehash: 430f5446f86c26cb1f0fd1c7f34613cddec473b2
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398251"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a><span data-ttu-id="4adc1-103">Niet-beheerde Windows 10 pc's en Macs beveiligen</span><span class="sxs-lookup"><span data-stu-id="4adc1-103">Protect unmanaged Windows 10 PCs and Macs</span></span>

<span data-ttu-id="4adc1-104">U kunt Windows 10 pc's en Macs beheren door ze in te schrijven in Microsoft Intune, zodat u ervoor kunt zorgen dat ze gezond en veilig zijn voordat u toegang krijgt tot gegevens in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="4adc1-104">You can manage Windows 10 PCs and Macs by enrolling them in Microsoft Intune, which allows you to ensure they're healthy and secure before accessing data in your environment.</span></span> <span data-ttu-id="4adc1-105">Veel campagnes en kleine bedrijven bevatten echter medewerkers die hun eigen apparaten (BYOD) meenemen, die niet door de organisatie worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="4adc1-105">However, many campaigns and small businesses include staff who bring their own devices (BYOD), which will not be managed by the organization.</span></span> <span data-ttu-id="4adc1-106">Voor deze niet-bemande pc's en Macs gebruikt u dit artikel om ervoor te zorgen dat minimale beveiligingsmogelijkheden zijn geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="4adc1-106">For these unmanaged PCs and Macs, use this article to ensure that minimum security capabilities are configured.</span></span>

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a><span data-ttu-id="4adc1-107">Een computer met een mac Windows 10 of een Mac beveiligen</span><span class="sxs-lookup"><span data-stu-id="4adc1-107">Protect a computer running Windows 10 or a Mac</span></span>

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
<span data-ttu-id="4adc1-108">Als uw Windows 10 pc of Mac niet wordt beheerd door uw organisatie, moet u deze beveiligingsmogelijkheden configureren.</span><span class="sxs-lookup"><span data-stu-id="4adc1-108">If your Windows 10 PC or Mac is not managed by your organization, be sure to configure these security capabilities.</span></span>

## <a name="windows-10"></a>[<span data-ttu-id="4adc1-109">Windows 10</span><span class="sxs-lookup"><span data-stu-id="4adc1-109">Windows 10</span></span>](#tab/Windows10)

<span data-ttu-id="4adc1-110">**Apparaatversleuteling in- en uit-**</span><span class="sxs-lookup"><span data-stu-id="4adc1-110">**Turn on device encryption**</span></span><p>

<span data-ttu-id="4adc1-111">Apparaatversleuteling is beschikbaar op een groot aantal Windows apparaten en helpt uw gegevens te beschermen door deze te versleutelen.</span><span class="sxs-lookup"><span data-stu-id="4adc1-111">Device encryption is available on a wide range of Windows devices and helps protect your data by encrypting it.</span></span> <span data-ttu-id="4adc1-112">Als u apparaatversleuteling in bedrijf neemt, hebben alleen geautoriseerde personen toegang tot uw apparaat en gegevens.</span><span class="sxs-lookup"><span data-stu-id="4adc1-112">If you turn on device encryption, only authorized individuals will be able to access your device and data.</span></span> <span data-ttu-id="4adc1-113">Zie [Apparaatversleuteling in- en](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) uit te zetten voor instructies.</span><span class="sxs-lookup"><span data-stu-id="4adc1-113">See [turn on device encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) for instructions.</span></span>

 <span data-ttu-id="4adc1-114">Als apparaatversleuteling niet beschikbaar is op uw apparaat, kunt u in plaats daarvan standaardversleuteling [BitLocker in.](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption)</span><span class="sxs-lookup"><span data-stu-id="4adc1-114">If device encryption isn't available on your device, you can turn on standard [BitLocker encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) instead.</span></span> <span data-ttu-id="4adc1-115">(BitLocker is niet beschikbaar op Windows 10 Home editie.)</span><span class="sxs-lookup"><span data-stu-id="4adc1-115">(BitLocker isn't available on Windows 10 Home edition.)</span></span> 

<span data-ttu-id="4adc1-116">**Uw apparaat beveiligen met Windows-beveiliging**</span><span class="sxs-lookup"><span data-stu-id="4adc1-116">**Protect your device with Windows Security**</span></span><p>
<span data-ttu-id="4adc1-117">Als u Windows 10 hebt, krijgt u de nieuwste antivirusbeveiliging met Windows-beveiliging.</span><span class="sxs-lookup"><span data-stu-id="4adc1-117">If you have Windows 10, you'll get the latest antivirus protection with Windows Security.</span></span> <span data-ttu-id="4adc1-118">Wanneer u de Windows 10 voor het eerst start, is Windows-beveiliging actief bezig met het beschermen van uw pc door te scannen op malware (schadelijke software), virussen en beveiligingsrisico's.</span><span class="sxs-lookup"><span data-stu-id="4adc1-118">When you start up Windows 10 for the first time, Windows Security is on and actively helping to protect your PC by scanning for malware (malicious software), viruses, and security threats.</span></span> <span data-ttu-id="4adc1-119">Windows-beveiliging realtime beveiliging gebruikt om alles wat u downloadt of op uw pc uit te voeren, te scannen.</span><span class="sxs-lookup"><span data-stu-id="4adc1-119">Windows Security uses real-time protection to scan everything you download or run on your PC.</span></span>

<span data-ttu-id="4adc1-120">Windows Updates voor downloads voor Windows-beveiliging automatisch bijwerken om uw pc veilig te houden en te beschermen tegen bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="4adc1-120">Windows Update downloads updates for Windows Security automatically to help keep your PC safe and protect it from threats.</span></span>

<span data-ttu-id="4adc1-121">Als u een eerdere versie van Windows en Microsoft Security Essentials gebruikt, is het een goed idee om naar een andere Windows-beveiliging.</span><span class="sxs-lookup"><span data-stu-id="4adc1-121">If you have an earlier version of Windows and are using Microsoft Security Essentials, it's a good idea to move to Windows Security.</span></span> <span data-ttu-id="4adc1-122">Zie Voor meer informatie help [mijn apparaat te beveiligen met Windows-beveiliging.](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)</span><span class="sxs-lookup"><span data-stu-id="4adc1-122">For more information, see [help protect my device with Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span></span>

<span data-ttu-id="4adc1-123">**De firewall Windows in-**</span><span class="sxs-lookup"><span data-stu-id="4adc1-123">**Turn on Windows Firewall**</span></span><p>
<span data-ttu-id="4adc1-124">U moet altijd Windows Firewall uitvoeren, zelfs als u een andere firewall hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="4adc1-124">You should always run Windows Firewall even if you have another firewall turned on.</span></span> <span data-ttu-id="4adc1-125">Als u Windows firewall uitschakelen, is uw apparaat (en uw netwerk, als u er een hebt) kwetsbaarder voor onbevoegde toegang.</span><span class="sxs-lookup"><span data-stu-id="4adc1-125">Turning off Windows Firewall might make your device (and your network, if you have one) more vulnerable to unauthorized access.</span></span> <span data-ttu-id="4adc1-126">Zie [Firewall Windows in- of uitschakelen voor](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) instructies.</span><span class="sxs-lookup"><span data-stu-id="4adc1-126">See [Turn Windows Firewall on or off](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) for instructions.</span></span>

## <a name="mac"></a>[<span data-ttu-id="4adc1-127">Mac</span><span class="sxs-lookup"><span data-stu-id="4adc1-127">Mac</span></span>](#tab/Mac)

<span data-ttu-id="4adc1-128">**FileVault gebruiken om uw Mac-schijf te versleutelen**</span><span class="sxs-lookup"><span data-stu-id="4adc1-128">**Use FileVault to encrypt your Mac disk**</span></span><p>
<span data-ttu-id="4adc1-129">Schijfversleuteling beschermt gegevens wanneer apparaten verloren gaan of worden gestolen.</span><span class="sxs-lookup"><span data-stu-id="4adc1-129">Disk encryption protects data when devices are lost or stolen.</span></span> <span data-ttu-id="4adc1-130">FileVault-versleuteling op volledige schijf helpt voorkomen dat onbevoegden toegang hebben tot de gegevens op de opstartschijf.</span><span class="sxs-lookup"><span data-stu-id="4adc1-130">FileVault full-disk encryption helps prevent unauthorized access to the information on your startup disk.</span></span> <span data-ttu-id="4adc1-131">Zie [FileVault gebruiken om de opstartschijf](https://support.apple.com/HT204837) op uw Mac te versleutelen voor instructies.</span><span class="sxs-lookup"><span data-stu-id="4adc1-131">See [use FileVault to encrypt the startup disk on your Mac](https://support.apple.com/HT204837) for instructions.</span></span>

<span data-ttu-id="4adc1-132">**Uw Mac beschermen tegen malware**</span><span class="sxs-lookup"><span data-stu-id="4adc1-132">**Protect your mac from malware**</span></span><p>
<span data-ttu-id="4adc1-133">Microsoft raadt u aan betrouwbare antivirussoftware op uw Mac te installeren en te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="4adc1-133">Microsoft recommends that you install and use reliable antivirus software on your Mac.</span></span> <span data-ttu-id="4adc1-134">Zie het volgende artikel voor een lijst met opties: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span><span class="sxs-lookup"><span data-stu-id="4adc1-134">See the following article for a list of choices: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span></span>

<span data-ttu-id="4adc1-135">U kunt ook het risico op malware beperken door software alleen te gebruiken uit betrouwbare bronnen.</span><span class="sxs-lookup"><span data-stu-id="4adc1-135">You can also reduce the risk of malware by using software only from reliable sources.</span></span> <span data-ttu-id="4adc1-136">Met de instellingen in & privacyvoorkeuren kunt u opgeven welke softwarebronnen op uw Mac zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="4adc1-136">The settings in Security & Privacy preferences allow you to specify the sources of software installed on your Mac.</span></span> <span data-ttu-id="4adc1-137">Zie uw Mac beschermen [tegen malware voor meer informatie.](https://support.apple.com/kb/PH25087)</span><span class="sxs-lookup"><span data-stu-id="4adc1-137">For more information, see [protect your Mac from malware](https://support.apple.com/kb/PH25087).</span></span>

<span data-ttu-id="4adc1-138">**Firewallbeveiliging in- en uit-**</span><span class="sxs-lookup"><span data-stu-id="4adc1-138">**Turn on firewall protection**</span></span><p>
<span data-ttu-id="4adc1-139">Gebruik firewallinstellingen om uw Mac te beschermen tegen ongewenste contactpersonen die door andere computers worden gestart wanneer u verbinding hebt met internet of een netwerk.</span><span class="sxs-lookup"><span data-stu-id="4adc1-139">Use firewall settings to protect your Mac from unwanted contact initiated by other computers when you're connected to the Internet or a network.</span></span> <span data-ttu-id="4adc1-140">Zonder deze beveiliging is uw Mac mogelijk kwetsbaarder voor onbevoegde toegang.</span><span class="sxs-lookup"><span data-stu-id="4adc1-140">Without this protection, your Mac might be more vulnerable to unauthorized access.</span></span> <span data-ttu-id="4adc1-141">Zie [de toepassingsfirewall voor](https://support.apple.com/HT201642) instructies.</span><span class="sxs-lookup"><span data-stu-id="4adc1-141">See [about the application firewall](https://support.apple.com/HT201642) for instructions.</span></span>
