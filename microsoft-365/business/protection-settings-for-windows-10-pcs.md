---
title: Instellingen voor apparaatbeveiliging instellen voor Windows 10-pc's
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
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
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Meer informatie over standaard-en andere instellingen die beschikbaar zijn in Microsoft 365 Business om Windows 10-apparaten te beveiligen.
ms.openlocfilehash: ab306e3d5a6011a0e7d537c98ecca6ef49ff82d9
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575753"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="f127e-103">Instellingen voor apparaatbeveiliging instellen voor Windows 10-pc's</span><span class="sxs-lookup"><span data-stu-id="f127e-103">Set device protection settings for Windows 10 PCs</span></span>

## <a name="secure-windows-10-devices"></a><span data-ttu-id="f127e-104">Windows 10-apparaten beveiligen</span><span class="sxs-lookup"><span data-stu-id="f127e-104">Secure Windows 10 devices</span></span>

<span data-ttu-id="f127e-105">Bekijk een video over het beveiligen van Windows 10-apparaten met Microsoft 365 Business:</span><span class="sxs-lookup"><span data-stu-id="f127e-105">View a video on how to secure Windows 10 devices with Microsoft 365 Business:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <span data-ttu-id="f127e-106">Ga naar het Admin Center op <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="f127e-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="f127e-107">Kies op de linker navigatie \> **apparaatbeleidsregels** \> **toevoegen**. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f127e-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="f127e-108">Voer in het deelvenster **Beleid toevoegen** een unieke naam in voor dit beleid.</span><span class="sxs-lookup"><span data-stu-id="f127e-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="f127e-109">Kies onder **Beleidstype** **Configuratie voor Windows 10-apparaat**.</span><span class="sxs-lookup"><span data-stu-id="f127e-109">Under **Policy type**, choose **Windows 10 Device Configuration**.</span></span>
    
5. <span data-ttu-id="f127e-p101">Vouw **Windows 10-apparaten beveiligen** uit \> configureer de instellingen op de manier die u wilt. Zie [Beschikbare instellingen](#available-settings) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f127e-p101">Expand **Secure Windows 10 Devices** \> configure the settings how you would like. See [Available settings](#available-settings) for more information.</span></span> 
    
    <span data-ttu-id="f127e-112">U kunt altijd de koppeling **Standaardwaarden herstellen** gebruiken om terug te keren naar de standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="f127e-112">You can alway use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. <span data-ttu-id="f127e-p102">Bepaal nu **Voor wie zijn deze instellingen?** Als u niet de standaardbeveiligingsgroep **Alle gebruikers** wilt gebruiken, kies **Wijzigen**, zoek de beveiligingsgroep die deze instellingen ontvangt \> **Selecteer**.</span><span class="sxs-lookup"><span data-stu-id="f127e-p102">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="f127e-116">Kies ten slotte, **Klaar** om het beleid op te slaan en dit toe te wijzen aan apparaten.</span><span class="sxs-lookup"><span data-stu-id="f127e-116">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="f127e-117">Beschikbare instellingen</span><span class="sxs-lookup"><span data-stu-id="f127e-117">Available settings</span></span>

<span data-ttu-id="f127e-p103">Alle instellingen zijn standaard **ingeschakeld**. De volgende instellingen zijn beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="f127e-p103">By default all settings are **On**. The following settings are available.</span></span>
  
<span data-ttu-id="f127e-120">Zie [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) (Hoe beveiligingsfuncties in Microsoft 365 Business zijn toegewezen aan Intune-instellingen) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f127e-120">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f127e-121">Instelling</span><span class="sxs-lookup"><span data-stu-id="f127e-121">Setting</span></span>  <br/> |<span data-ttu-id="f127e-122">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f127e-122">Description</span></span>  <br/> |
|<span data-ttu-id="f127e-123">Bescherm pc's tegen virussen en andere bedreigingen met Windows Defender-antivirussoftware</span><span class="sxs-lookup"><span data-stu-id="f127e-123">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="f127e-124">Daarvoor moet Windows Defender-antivirussoftware zijn ingeschakeld om pc's te beschermen tegen de gevaren die verbinding met internet met zich meebrengt.</span><span class="sxs-lookup"><span data-stu-id="f127e-124">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="f127e-125">Bescherm pc's tegen internetdreigingen in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f127e-125">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="f127e-126">Hiermee worden instellingen in Edge ingeschakeld die gebruikers helpen beschermen tegen schadelijke websites en downloads.</span><span class="sxs-lookup"><span data-stu-id="f127e-126">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="f127e-127">Gebruik regels die de kwetsbaarheid voor aanvallen van apparaten verminderen</span><span class="sxs-lookup"><span data-stu-id="f127e-127">Use rules that reduce the attack surface of devices</span></span>  <br/> |<span data-ttu-id="f127e-p104">Wanneer deze optie is ingeschakeld, kunnen hiermee acties en apps worden geblokkeerd die doorgaans door malware worden gebruikt om apparaten te infecteren. Deze instelling is alleen beschikbaar als Windows Defender Antivirus is ingesteld op Aan. Zie [Kwetsbaarheid voor aanvallen verminderen](https://go.microsoft.com/fwlink/?linkid=870417) voor meer informatie.  </span><span class="sxs-lookup"><span data-stu-id="f127e-p104">When turned On, attack surface reduction helps block actions and apps typically used by malware to infect devices. This setting is only available if Windows Defender Antivirus is set to On. See [Reduce attack surfaces](https://go.microsoft.com/fwlink/?linkid=870417) to learn more.  </span></span><br/> |
|<span data-ttu-id="f127e-131">Mappen beschermen tegen bedreigingen, zoals ransomware</span><span class="sxs-lookup"><span data-stu-id="f127e-131">Protect folders from threats such as ransomware</span></span>  <br/> |<span data-ttu-id="f127e-p105">Deze instelling maakt gebruik van gecontroleerde mappentoegang om bedrijfsgegevens te beschermen tegen wijzigingen die worden aangebracht door verdachte of kwaadaardige apps, zoals ransomware. Deze typen apps worden geblokkeerd zodat er geen wijzigingen in beveiligde mappen kunnen worden aangebracht. Deze instelling is alleen beschikbaar als Windows Defender Antivirus is ingesteld op Aan. Zie [Mappen beveiligen met gecontroleerde mappentoegang](https://go.microsoft.com/fwlink/?linkid=870418) voor meer informatie.  </span><span class="sxs-lookup"><span data-stu-id="f127e-p105">This setting uses controlled folder access to protect company data from modification by suspicious or malicious apps, such as ransomware. These types of apps are blocked from making changes in protected folders. This setting is only available if Windows Defender Antivirus is set to On. See [Protect folders with COntrolled folder access](https://go.microsoft.com/fwlink/?linkid=870418) to learn more.  </span></span><br/> |
|<span data-ttu-id="f127e-136">Netwerktoegang tot mogelijke schadelijke inhoud op internet voorkomen</span><span class="sxs-lookup"><span data-stu-id="f127e-136">Prevent network access to potentially malicious content on the Internet</span></span>  <br/> |<span data-ttu-id="f127e-p106">Gebruik deze instelling om uitgaande gebruikersverbindingen met internetlocaties met een slechte reputatie te blokkeren waarop mogelijk phishing-praktijken, misbruik of andere schadelijke inhoud worden uitgevoerd. Deze instelling is alleen beschikbaar als Windows Defender Antivirus is ingesteld op Aan. Zie [Uw netwerk beveiligen](https://go.microsoft.com/fwlink/?linkid=870419) voor meer informatie.  </span><span class="sxs-lookup"><span data-stu-id="f127e-p106">Use this setting to block outbound user connections to low-reputation Internet locations that may host phishing scams, exploits or other malicious content. This setting is only available if Windows Defender Antivirus is set to On. See [Protect your network](https://go.microsoft.com/fwlink/?linkid=870419) for more information.  </span></span><br/> |
|<span data-ttu-id="f127e-140">Bestanden en mappen op pc's beschermen tegen onbevoegde toegang met BitLocker</span><span class="sxs-lookup"><span data-stu-id="f127e-140">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="f127e-p107">Bitlocker beschermt gegevens door de harde schijven van de computer te versleutelen en te beschermen tegen blootstelling van gegevens als een computer zoekraakt of wordt gestolen. Zie [Veelgestelde vragen over Bitlocker](https://go.microsoft.com/fwlink/?linkid=871000) voor meer informatie.  </span><span class="sxs-lookup"><span data-stu-id="f127e-p107">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen. See [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000) for more information.  </span></span><br/> |
|<span data-ttu-id="f127e-143">Gebruikers toestaan om apps te downloaden vanuit de Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="f127e-143">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="f127e-p108">Hiermee kunnen gebruikers apps downloaden en installeren vanuit de Microsoft Store. Omdat apps kunnen variëren van spelletjes tot productiviteitsprogramma's, laten we deze instelling **ingeschakeld**, maar u kunt de instelling uitschakelen voor extra beveiliging.  </span><span class="sxs-lookup"><span data-stu-id="f127e-p108">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="f127e-146">Gebruikers toestaan om Cortana te openen</span><span class="sxs-lookup"><span data-stu-id="f127e-146">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="f127e-p109">Cortana kan bijzonder handig zijn. Het programma kan instellingen inschakelen of uitschakelen, aanwijzingen geven en ervoor zorgen dat u altijd op tijd bent voor afspraken. Daarom laten we het standaard **ingeschakeld**.  </span><span class="sxs-lookup"><span data-stu-id="f127e-p109">Cortana can be very helpful! She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.  </span></span><br/> |
|<span data-ttu-id="f127e-149">Gebruikers toestaan om Windows-tips en reclame van Microsoft te ontvangen</span><span class="sxs-lookup"><span data-stu-id="f127e-149">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="f127e-150">Windows-tips kunnen handig zijn en gebruikers op weg helpen wanneer er nieuwe functies beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="f127e-150">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="f127e-151">Windows 10-apparaten automatisch bijwerken</span><span class="sxs-lookup"><span data-stu-id="f127e-151">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="f127e-152">Hiermee ontvangen Windows 10-apparaten automatisch de nieuwste updates.</span><span class="sxs-lookup"><span data-stu-id="f127e-152">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
|<span data-ttu-id="f127e-153">Apparaatscherm uitschakelen indien inactief gedurende deze periode</span><span class="sxs-lookup"><span data-stu-id="f127e-153">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="f127e-p110">Hiermee weet u zeker dat bedrijfsgegevens beveiligd zijn als een gebruiker niet actief is. Een gebruiker kan in een openbare locatie werken, zoals een café, en even weggaan of afgeleid worden, waardoor de informatie op het apparaat gemakkelijk door onbekenden bekeken kan worden. Met deze instelling kunt u bepalen hoelang de gebruiker inactief kan zijn voordat het scherm wordt uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="f127e-p110">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
   
  

