---
title: TLS 1.0 en 1.1 uitschakelen voor Microsoft 365
description: Beschrijft TLS 1.0 en 1.1 deprecation and disablement for Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 3d44e178d351942b4a178ddc1954ddd839665639
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161959"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a><span data-ttu-id="0bc5e-103">TLS 1.0 en 1.1 uitschakelen voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0bc5e-103">Disabling TLS 1.0 and 1.1 for Microsoft 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0bc5e-104">We hebben de uitzetting van TLS 1.0 en 1.1 tijdelijk stopgezet voor commerciële klanten vanwege COVID-19.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-104">We temporarily halted disablement of TLS 1.0 and 1.1 for commercial customers due to COVID-19.</span></span> <span data-ttu-id="0bc5e-105">Aangezien supply chains zijn aangepast en bepaalde landen een back-up openen, hebben we de implementatie van TLS 1.2 enforcement op 15 oktober 2020 opnieuw opgestart.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-105">As supply chains have adjusted and certain countries open back up, we restarted the TLS 1.2 enforcement rollout on October 15, 2020.</span></span> <span data-ttu-id="0bc5e-106">De uitrol gaat de komende weken en maanden door.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-106">Rollout will continue over the following weeks and months.</span></span>

<span data-ttu-id="0bc5e-107">Vanaf 31 oktober 2018 worden de TLS-protocollen Transport Layer Security (TLS) 1.0 en 1.1 afgeschaft voor de Microsoft 365 service.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-107">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Microsoft 365 service.</span></span> <span data-ttu-id="0bc5e-108">Het effect voor eindgebruikers is minimaal.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-108">The effect for end-users is minimal.</span></span> <span data-ttu-id="0bc5e-109">Deze wijziging is meer dan twee jaar openbaar gemaakt, met de eerste openbare aankondiging in december 2017.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-109">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="0bc5e-110">Dit artikel is alleen bedoeld voor de Office 365 lokale client met betrekking tot de Office 365-service, maar kan ook van toepassing zijn op on-premises TLS-problemen met Office en Office Online Server/Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-110">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

<span data-ttu-id="0bc5e-111">Voor SharePoint en OneDrive moet u .NET bijwerken en configureren om TLS 1.2 te ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-111">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="0bc5e-112">Zie [TLS 1.2 inschakelen](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)op clients voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-112">For information, see [How to enable TLS 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="office-365-and-tls-overview"></a><span data-ttu-id="0bc5e-113">Office 365 en TLS-overzicht</span><span class="sxs-lookup"><span data-stu-id="0bc5e-113">Office 365 and TLS overview</span></span>

<span data-ttu-id="0bc5e-114">De Office client is afhankelijk van de Windows webservice (WINHTTP) voor het verzenden en ontvangen van verkeer via TLS-protocollen.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-114">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="0bc5e-115">De Office client kan TLS 1.2 gebruiken als de webservice van de lokale computer TLS 1.2 kan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-115">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="0bc5e-116">Alle Office-clients kunnen TLS-protocollen gebruiken, omdat TLS- en SSL-protocollen deel uitmaken van het besturingssysteem en niet specifiek zijn voor de Office client.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-116">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="0bc5e-117">Op Windows 8 en latere versies</span><span class="sxs-lookup"><span data-stu-id="0bc5e-117">On Windows 8 and later versions</span></span>

<span data-ttu-id="0bc5e-118">Standaard zijn de TLS 1.2- en 1.1-protocollen beschikbaar als er geen netwerkapparaten zijn geconfigureerd om TLS 1.2-verkeer te weigeren.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-118">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="0bc5e-119">Op Windows 7</span><span class="sxs-lookup"><span data-stu-id="0bc5e-119">On Windows 7</span></span>

<span data-ttu-id="0bc5e-120">TLS 1.1- en 1.2-protocollen zijn niet beschikbaar zonder de [KB 3140245-update.](https://support.microsoft.com/help/3140245)</span><span class="sxs-lookup"><span data-stu-id="0bc5e-120">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="0bc5e-121">De update lost dit probleem op en voegt de volgende register subsleutel toe:</span><span class="sxs-lookup"><span data-stu-id="0bc5e-121">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="0bc5e-122">Windows 7 gebruikers die deze update niet hebben, worden beïnvloed vanaf 31 oktober 2018.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-122">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="0bc5e-123">[KB 3140245](https://support.microsoft.com/help/3140245) heeft informatie over het wijzigen van WINHTTP-instellingen om TLS-protocollen in te stellen.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-123">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="0bc5e-124">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="0bc5e-124">More information</span></span>

<span data-ttu-id="0bc5e-125">De waarde van de **registersleutel DefaultSecureProtocols** die in het KB-artikel wordt beschreven, bepaalt welke netwerkprotocollen kunnen worden gebruikt:</span><span class="sxs-lookup"><span data-stu-id="0bc5e-125">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="0bc5e-126">StandaardSecureProtocols-waarde</span><span class="sxs-lookup"><span data-stu-id="0bc5e-126">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="0bc5e-127">Protocol ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="0bc5e-127">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="0bc5e-128">0x00000008</span><span class="sxs-lookup"><span data-stu-id="0bc5e-128">0x00000008</span></span>|<span data-ttu-id="0bc5e-129">Standaard SSL 2.0 inschakelen</span><span class="sxs-lookup"><span data-stu-id="0bc5e-129">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="0bc5e-130">0x00000020</span><span class="sxs-lookup"><span data-stu-id="0bc5e-130">0x00000020</span></span>|<span data-ttu-id="0bc5e-131">Standaard SSL 3.0 inschakelen</span><span class="sxs-lookup"><span data-stu-id="0bc5e-131">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="0bc5e-132">0x00000080</span><span class="sxs-lookup"><span data-stu-id="0bc5e-132">0x00000080</span></span>|<span data-ttu-id="0bc5e-133">Standaard TLS 1.0 inschakelen</span><span class="sxs-lookup"><span data-stu-id="0bc5e-133">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="0bc5e-134">0x00000200</span><span class="sxs-lookup"><span data-stu-id="0bc5e-134">0x00000200</span></span>|<span data-ttu-id="0bc5e-135">Standaard TLS 1.1 inschakelen</span><span class="sxs-lookup"><span data-stu-id="0bc5e-135">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="0bc5e-136">0x00000800</span><span class="sxs-lookup"><span data-stu-id="0bc5e-136">0x00000800</span></span>|<span data-ttu-id="0bc5e-137">Standaard TLS 1.2 inschakelen</span><span class="sxs-lookup"><span data-stu-id="0bc5e-137">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="0bc5e-138">Office clients en TLS-registersleutels</span><span class="sxs-lookup"><span data-stu-id="0bc5e-138">Office clients and TLS registry keys</span></span>

<span data-ttu-id="0bc5e-139">U kunt verwijzen naar [KB 4057306 Voorbereidingen](https://support.microsoft.com/help/4057306)treffen voor het verplichte gebruik van TLS 1.2 in Office 365.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-139">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="0bc5e-140">Dit is een algemeen artikel voor IT-beheerders en het is officiële documentatie over de wijziging van TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-140">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="0bc5e-141">In de volgende tabel ziet u de juiste registersleutelwaarden in Office 365 clients na 31 oktober 2018.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-141">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="0bc5e-142">Ingeschakelde protocollen voor Office 365 service na 31 oktober 2018</span><span class="sxs-lookup"><span data-stu-id="0bc5e-142">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="0bc5e-143">Hexadecimale waarde</span><span class="sxs-lookup"><span data-stu-id="0bc5e-143">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="0bc5e-144">TLS 1.0 + 1,1 + 1,2</span><span class="sxs-lookup"><span data-stu-id="0bc5e-144">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="0bc5e-145">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="0bc5e-145">0x00000A80</span></span>|
|<span data-ttu-id="0bc5e-146">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="0bc5e-146">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="0bc5e-147">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="0bc5e-147">0x00000A00</span></span>|
|<span data-ttu-id="0bc5e-148">TLS 1.0 + 1,2</span><span class="sxs-lookup"><span data-stu-id="0bc5e-148">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="0bc5e-149">0x00000880</span><span class="sxs-lookup"><span data-stu-id="0bc5e-149">0x00000880</span></span>|
|<span data-ttu-id="0bc5e-150">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="0bc5e-150">TLS 1.2</span></span>|<span data-ttu-id="0bc5e-151">0x00000800</span><span class="sxs-lookup"><span data-stu-id="0bc5e-151">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="0bc5e-152">Gebruik de SSL 2.0- en 3.0-protocollen niet, die ook kunnen worden ingesteld met de **defaultsecureProtocols-toets.**</span><span class="sxs-lookup"><span data-stu-id="0bc5e-152">Don't use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="0bc5e-153">SSL 2.0 en 3.0 worden beschouwd als verouderde en onveilige protocollen.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-153">SSL 2.0 and 3.0 are considered outdated and insecure protocols.</span></span> <span data-ttu-id="0bc5e-154">De beste manier is om het gebruik van SSL 2.0 en SSL 3.0 te beëindigen, hoewel de beslissing om dit te doen uiteindelijk afhangt van wat het beste aan uw productbehoeften voldoet.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-154">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="0bc5e-155">Zie [KB 3009008](https://support.microsoft.com/help/3009008)voor meer informatie over SSL 3.0-beveiligingslekken.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-155">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="0bc5e-156">U kunt de standaardinstelling Windows rekenmachine in de programmeermodus gebruiken om dezelfde registersleutelwaarden voor verwijzingen in te stellen.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-156">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="0bc5e-157">Zie KB 3140245 Update voor het inschakelen van [TLS 1.1 en TLS 1.2](https://support.microsoft.com/help/3140245)als standaardveilige protocollen in WinHTTP in Windows.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-157">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="0bc5e-158">Ongeacht of de Windows 7-update[(KB 3140245)](https://support.microsoft.com/help/3140245)is geïnstalleerd of niet, is de register subsleutel DefaultSecureProtocols niet aanwezig en moet deze handmatig of via een groepsbeleidsobject (GPO) worden toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-158">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="0bc5e-159">Tenzij u moet aanpassen welke veilige protocollen zijn ingeschakeld of beperkt, is deze sleutel niet vereist.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-159">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="0bc5e-160">U hebt alleen de update Windows 7 SP1[(KB 3140245)](https://support.microsoft.com/help/3140245)nodig.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-160">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a><span data-ttu-id="0bc5e-161">De .NET Framework bijwerken en configureren voor ondersteuning van TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="0bc5e-161">Update and configure the .NET Framework to support TLS 1.2</span></span>

<span data-ttu-id="0bc5e-162">U moet toepassingen bijwerken die via TLS 1.0 Microsoft 365 TLS 1.1 of TLS 1.1 bellen om TLS 1.2 te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-162">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="0bc5e-163">.NET 4.5 is standaard ingesteld op TLS 1.1.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-163">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="0bc5e-164">Zie Transport Layer Security [(TLS) 1.2](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)op clients inschakelen als u uw .NET-configuratie wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-164">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="0bc5e-165">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="0bc5e-165">More information</span></span>

<span data-ttu-id="0bc5e-166">Zie Voorbereiden op het verplichte gebruik van [TLS 1.2 in](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)Office 365.</span><span class="sxs-lookup"><span data-stu-id="0bc5e-166">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>