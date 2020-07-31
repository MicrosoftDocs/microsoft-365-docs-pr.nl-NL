---
title: Onbeheerde Windows 10-pc's en Macs beschermen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
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
description: Bescherm tegen phishing en andere aanvallen met Microsoft 365 voor campagnes.
ms.openlocfilehash: 3e0c6a52209c56e75c6ff1210f26e6926e4d7d32
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527136"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a><span data-ttu-id="1b4b5-103">Onbeheerde Windows 10-pc's en Macs beschermen</span><span class="sxs-lookup"><span data-stu-id="1b4b5-103">Protect unmanaged Windows 10 PCs and Macs</span></span>

<span data-ttu-id="1b4b5-104">U Windows 10-pc's en Macs beheren door ze in te schrijven in Microsoft Intune, waarmee u ervoor zorgen dat ze gezond en veilig zijn voordat u toegang krijgt tot gegevens in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-104">You can manage Windows 10 PCs and Macs by enrolling them in Microsoft Intune, which allows you to ensure they're healthy and secure before accessing data in your environment.</span></span> <span data-ttu-id="1b4b5-105">Veel campagnes en kleine bedrijven omvatten echter medewerkers die hun eigen apparaten (byod) meebrengen, die niet door de organisatie worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-105">However, many campaigns and small businesses include staff who bring their own devices (byod), which will not be managed by the organization.</span></span> <span data-ttu-id="1b4b5-106">Voor deze onbeheerde pc's en Macs gebruikt u dit artikel om ervoor te zorgen dat minimale beveiligingsmogelijkheden zijn geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-106">For these unmanaged PCs and Macs, use this article to ensure that minimum security capabilities are configured.</span></span> 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a><span data-ttu-id="1b4b5-107">Een computer met Windows 10 of een Mac beveiligen</span><span class="sxs-lookup"><span data-stu-id="1b4b5-107">Protect a computer running Windows 10 or a Mac</span></span>

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
<span data-ttu-id="1b4b5-108">Als uw Windows 10-pc of -Mac niet door uw organisatie wordt beheerd, moet u deze beveiligingsmogelijkheden configureren.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-108">If your Windows 10 PC or Mac is not managed by your organization, be sure to configure these security capabilities.</span></span>

## <a name="windows-10"></a>[<span data-ttu-id="1b4b5-109">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1b4b5-109">Windows 10</span></span>](#tab/Windows10)
<span data-ttu-id="1b4b5-110">**Apparaatversleuteling inschakelen**</span><span class="sxs-lookup"><span data-stu-id="1b4b5-110">**Turn on device encryption**</span></span><p>

<span data-ttu-id="1b4b5-111">Apparaatversleuteling is beschikbaar op een breed scala aan Windows-apparaten en helpt uw gegevens te beschermen door deze te versleutelen.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-111">Device encryption is available on a wide range of Windows devices and helps protect your data by encrypting it.</span></span> <span data-ttu-id="1b4b5-112">Als u apparaatversleuteling inschakelt, hebben alleen geautoriseerde personen toegang tot uw apparaat en gegevens.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-112">If you turn on device encryption, only authorized individuals will be able to access your device and data.</span></span> <span data-ttu-id="1b4b5-113">Zie [Apparaatversleuteling inschakelen](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-113">See [turn on device encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) for instructions.</span></span>

 <span data-ttu-id="1b4b5-114">Als apparaatversleuteling niet beschikbaar is op uw apparaat, u in plaats daarvan standaard [BitLocker-versleuteling](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) inschakelen.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-114">If device encryption isn't available on your device, you can turn on standard [BitLocker encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) instead.</span></span> <span data-ttu-id="1b4b5-115">(BitLocker is niet beschikbaar op Windows 10 Home-editie.)</span><span class="sxs-lookup"><span data-stu-id="1b4b5-115">(BitLocker isn't available on Windows 10 Home edition.)</span></span> 


<span data-ttu-id="1b4b5-116">**Uw apparaat beveiligen met Windows Security**</span><span class="sxs-lookup"><span data-stu-id="1b4b5-116">**Protect your device with Windows Security**</span></span><p>
<span data-ttu-id="1b4b5-117">Als u Windows 10 hebt, krijgt u de nieuwste antivirusbeveiliging met Windows Security.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-117">If you have Windows 10, you'll get the latest antivirus protection with Windows Security.</span></span> <span data-ttu-id="1b4b5-118">Wanneer u Windows 10 voor de eerste keer opstart, staat Windows Security aan en helpt actief om uw pc te beschermen door te scannen op malware (schadelijke software), virussen en beveiligingsbedreigingen.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-118">When you start up Windows 10 for the first time, Windows Security is on and actively helping to protect your PC by scanning for malware (malicious software), viruses, and security threats.</span></span> <span data-ttu-id="1b4b5-119">Windows Security maakt gebruik van realtime beveiliging om alles wat u downloadt of uitvoert op uw pc te scannen.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-119">Windows Security uses real-time protection to scan everything you download or run on your PC.</span></span>

<span data-ttu-id="1b4b5-120">Windows Update downloadt automatisch updates voor Windows Security om uw pc veilig te houden en te beschermen tegen bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-120">Windows Update downloads updates for Windows Security automatically to help keep your PC safe and protect it from threats.</span></span>

<span data-ttu-id="1b4b5-121">Als u een eerdere versie van Windows hebt en Microsoft Security Essentials gebruikt, is het een goed idee om over te stappen naar Windows Security.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-121">If you have an earlier version of Windows and are using Microsoft Security Essentials, it's a good idea to move to Windows Security.</span></span> <span data-ttu-id="1b4b5-122">Zie [Help mijn apparaat te beschermen met Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-122">For more information, see [help protect my device with Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span></span>

<span data-ttu-id="1b4b5-123">**Windows Firewall inschakelen**</span><span class="sxs-lookup"><span data-stu-id="1b4b5-123">**Turn on Windows Firewall**</span></span><p>
<span data-ttu-id="1b4b5-124">U moet Windows Firewall altijd uitvoeren, zelfs als u een andere firewall hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-124">You should always run Windows Firewall even if you have another firewall turned on.</span></span> <span data-ttu-id="1b4b5-125">Als u Windows Firewall uitschakelt, kan uw apparaat (en uw netwerk, als u er een hebt) kwetsbaarder worden voor ongeautoriseerde toegang.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-125">Turning off Windows Firewall might make your device (and your network, if you have one) more vulnerable to unauthorized access.</span></span> <span data-ttu-id="1b4b5-126">Zie [Windows Firewall in- of uitschakelen](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) voor instructies</span><span class="sxs-lookup"><span data-stu-id="1b4b5-126">See [Turn Windows Firewall on or off](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) for instructions</span></span>

## <a name="mac"></a>[<span data-ttu-id="1b4b5-127">Mac</span><span class="sxs-lookup"><span data-stu-id="1b4b5-127">Mac</span></span>](#tab/Mac)
<span data-ttu-id="1b4b5-128">**FileVault gebruiken om uw Mac-schijf te versleutelen**</span><span class="sxs-lookup"><span data-stu-id="1b4b5-128">**Use FileVault to encrypt your Mac disk**</span></span><p>
<span data-ttu-id="1b4b5-129">Schijfversleuteling beschermt gegevens wanneer apparaten verloren gaan of worden gestolen.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-129">Disk encryption protects data when devices are lost or stolen.</span></span> <span data-ttu-id="1b4b5-130">BestandVault full-disk encryptie helpt voorkomen dat ongeautoriseerde toegang tot de informatie op uw opstartschijf.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-130">FileVault full-disk encryption helps prevent unauthorized access to the information on your startup disk.</span></span> <span data-ttu-id="1b4b5-131">Zie [FileVault gebruiken om de opstartschijf op uw Mac te versleutelen](https://support.apple.com/HT204837) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-131">See [use FileVault to encrypt the startup disk on your Mac](https://support.apple.com/HT204837) for instructions.</span></span>

<span data-ttu-id="1b4b5-132">**Bescherm je mac tegen malware**</span><span class="sxs-lookup"><span data-stu-id="1b4b5-132">**Protect your mac from malware**</span></span><p>
<span data-ttu-id="1b4b5-133">Microsoft raadt u aan betrouwbare antivirussoftware op uw Mac te installeren en te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-133">Microsoft recommends that you install and use reliable antivirus software on your Mac.</span></span> <span data-ttu-id="1b4b5-134">Zie het volgende artikel voor een lijst met keuzes: [Beste Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span><span class="sxs-lookup"><span data-stu-id="1b4b5-134">See the following article for a list of choices: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span></span>

<span data-ttu-id="1b4b5-135">U ook het risico op malware verminderen door alleen software uit betrouwbare bronnen te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-135">You can also reduce the risk of malware by using software only from reliable sources.</span></span> <span data-ttu-id="1b4b5-136">Met de instellingen in Beveiligings & privacyvoorkeuren u de softwarebronnen opgeven die op uw Mac zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-136">The settings in Security & Privacy preferences allow you to specify the sources of software installed on your Mac.</span></span> <span data-ttu-id="1b4b5-137">Zie [uw Mac beschermen tegen malware](https://support.apple.com/kb/PH25087)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-137">For more information, see [protect your Mac from malware](https://support.apple.com/kb/PH25087).</span></span>

<span data-ttu-id="1b4b5-138">**Firewallbeveiliging inschakelen**</span><span class="sxs-lookup"><span data-stu-id="1b4b5-138">**Turn on firewall protection**</span></span><p>
<span data-ttu-id="1b4b5-139">Gebruik firewall-instellingen om je Mac te beschermen tegen ongewenst contact dat door andere computers wordt gestart wanneer je verbinding hebt met internet of een netwerk.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-139">Use firewall settings to protect your Mac from unwanted contact initiated by other computers when you're connected to the Internet or a network.</span></span> <span data-ttu-id="1b4b5-140">Zonder deze bescherming is uw Mac mogelijk kwetsbaarder voor ongeautoriseerde toegang.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-140">Without this protection, your Mac might be more vulnerable to unauthorized access.</span></span> <span data-ttu-id="1b4b5-141">Zie [over de toepassing firewall](https://support.apple.com/HT201642) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="1b4b5-141">See [about the application firewall](https://support.apple.com/HT201642) for instructions.</span></span>
