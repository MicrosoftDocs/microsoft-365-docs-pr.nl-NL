---
title: Netwerkverbindingen van Microsoft Defender Antivirus configureren en valideren
description: Configureer en test uw verbinding met de Microsoft Defender Antivirus cloudbeveiligingsservice.
keywords: antivirus, Microsoft Defender Antivirus, antimalware, beveiliging, defender, cloud, agressiviteit, beschermingsniveau
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 5e754c2f4b5406d4b91ef624415f3819d3171305
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536020"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a><span data-ttu-id="77ade-104">Netwerkverbindingen van Microsoft Defender Antivirus configureren en valideren</span><span class="sxs-lookup"><span data-stu-id="77ade-104">Configure and validate Microsoft Defender Antivirus network connections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="77ade-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="77ade-105">**Applies to:**</span></span>

- [<span data-ttu-id="77ade-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="77ade-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="77ade-107">Als u Microsoft Defender Antivirus beveiliging in de cloud goed wilt laten werken, moet u uw netwerk zo configureren dat verbindingen tussen uw eindpunten en bepaalde Microsoft-servers worden toegestaan.</span><span class="sxs-lookup"><span data-stu-id="77ade-107">To ensure Microsoft Defender Antivirus cloud-delivered protection works properly, you need to configure your network to allow connections between your endpoints and certain Microsoft servers.</span></span> <span data-ttu-id="77ade-108">In dit artikel worden de verbindingen vermeld die moeten worden toegestaan, bijvoorbeeld met behulp van firewallregels, en worden instructies gegeven voor het valideren van uw verbinding.</span><span class="sxs-lookup"><span data-stu-id="77ade-108">This article lists the connections that must be allowed, such as by using firewall rules, and provides instructions for validating your connection.</span></span> <span data-ttu-id="77ade-109">Als u uw beveiliging correct configureert, kunt u ervoor zorgen dat u de beste waarde ontvangt van uw beveiligingsservices die in de cloud worden geleverd.</span><span class="sxs-lookup"><span data-stu-id="77ade-109">Configuring your protection properly helps ensure that you receive the best value from your cloud-delivered protection services.</span></span>

<span data-ttu-id="77ade-110">Zie het blogbericht [Belangrijke wijzigingen in het eindpunt van Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) voor meer informatie over netwerkconnectiviteit.</span><span class="sxs-lookup"><span data-stu-id="77ade-110">See the blog post [Important changes to Microsoft Active Protection Services endpoint](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) for some details about network connectivity.</span></span>

> [!TIP]
> <span data-ttu-id="77ade-111">U kunt ook naar de demowebsite [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) van Microsoft Defender voor Eindpunt demo.wd.microsoft.com om te bevestigen dat de volgende functies werken:</span><span class="sxs-lookup"><span data-stu-id="77ade-111">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
>
> - <span data-ttu-id="77ade-112">Cloudbeveiliging</span><span class="sxs-lookup"><span data-stu-id="77ade-112">Cloud-delivered protection</span></span>
> - <span data-ttu-id="77ade-113">Snel leren (inclusief blok op het eerste gezicht)</span><span class="sxs-lookup"><span data-stu-id="77ade-113">Fast learning (including block at first sight)</span></span>
> - <span data-ttu-id="77ade-114">Mogelijk ongewenste blokkering van toepassingen</span><span class="sxs-lookup"><span data-stu-id="77ade-114">Potentially unwanted application blocking</span></span>

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a><span data-ttu-id="77ade-115">Verbindingen met de Microsoft Defender Antivirus cloudservice toestaan</span><span class="sxs-lookup"><span data-stu-id="77ade-115">Allow connections to the Microsoft Defender Antivirus cloud service</span></span>

<span data-ttu-id="77ade-116">De Microsoft Defender Antivirus cloudservice biedt snelle, sterke beveiliging voor uw eindpunten.</span><span class="sxs-lookup"><span data-stu-id="77ade-116">The Microsoft Defender Antivirus cloud service provides fast, strong protection for your endpoints.</span></span> <span data-ttu-id="77ade-117">Het inschakelen van de door de cloud geleverde beveiligingsservice is optioneel, maar het wordt ten zeerste aanbevolen omdat deze belangrijke bescherming biedt tegen malware op uw eindpunten en in uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="77ade-117">Enabling the cloud-delivered protection service is optional, however it's highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

> [!NOTE]
> <span data-ttu-id="77ade-118">De Microsoft Defender Antivirus cloudservice is een mechanisme voor het leveren van bijgewerkte beveiliging voor uw netwerk en eindpunten.</span><span class="sxs-lookup"><span data-stu-id="77ade-118">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="77ade-119">Hoewel het een cloudservice wordt genoemd, is het niet alleen beveiliging voor bestanden die zijn opgeslagen in de cloud, maar wordt gebruikgemaakt van gedistribueerde resources en machine learning om uw eindpunten te beschermen tegen een snelheid die veel sneller is dan traditionele beveiligingsinformatie-updates.</span><span class="sxs-lookup"><span data-stu-id="77ade-119">Although it's called a cloud service, it's not simply protection for files stored in the cloud, rather it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="77ade-120">Zie [Beveiliging in de cloud](enable-cloud-protection-microsoft-defender-antivirus.md) inschakelen voor meer informatie over het inschakelen van de service met Intune, Microsoft Endpoint Configuration Manager, Groepsbeleid, PowerShell-cmdlets of op afzonderlijke clients in de Windows-beveiliging app.</span><span class="sxs-lookup"><span data-stu-id="77ade-120">See [Enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) for details on enabling the service with Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, or on individual clients in the Windows Security app.</span></span> 

<span data-ttu-id="77ade-121">Nadat u de service hebt ingeschakeld, moet u mogelijk uw netwerk of firewall configureren om verbindingen tussen de service en uw eindpunten toe te staan.</span><span class="sxs-lookup"><span data-stu-id="77ade-121">After you've enabled the service, you may need to configure your network or firewall to allow connections between it and your endpoints.</span></span>

<span data-ttu-id="77ade-122">Omdat uw beveiliging een cloudservice is, moeten computers toegang hebben tot internet en de Microsoft Defender voor Office 365 machine learning-services.</span><span class="sxs-lookup"><span data-stu-id="77ade-122">Because your protection is a cloud service, computers must have access to the internet and reach the Microsoft Defender for Office 365 machine learning services.</span></span> <span data-ttu-id="77ade-123">Sluit de URL niet uit `*.blob.core.windows.net` van een netwerkcontrole.</span><span class="sxs-lookup"><span data-stu-id="77ade-123">Don't exclude the URL `*.blob.core.windows.net` from any kind of network inspection.</span></span> 

<span data-ttu-id="77ade-124">De onderstaande tabel bevat de services en bijbehorende URL's.</span><span class="sxs-lookup"><span data-stu-id="77ade-124">The table below lists the services and their associated URLs.</span></span> <span data-ttu-id="77ade-125">Zorg ervoor dat er geen firewall- of netwerkfilterregels zijn die toegang tot deze URL's weigeren, of u moet mogelijk een regel voor toestaan speciaal voor hen maken (met uitzondering van de `*.blob.core.windows.net` URL).</span><span class="sxs-lookup"><span data-stu-id="77ade-125">Make sure that there are no firewall or network filtering rules denying access to these URLs, or you may need to create an allow rule specifically for them (excluding the URL `*.blob.core.windows.net`).</span></span> <span data-ttu-id="77ade-126">Hieronder vermelden URL's gebruiken poort 443 voor communicatie.</span><span class="sxs-lookup"><span data-stu-id="77ade-126">Below mention URLs are using port 443 for communication.</span></span>


| <span data-ttu-id="77ade-127">**Service**</span><span class="sxs-lookup"><span data-stu-id="77ade-127">**Service**</span></span>| <span data-ttu-id="77ade-128">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="77ade-128">**Description**</span></span> |<span data-ttu-id="77ade-129">**URL**</span><span class="sxs-lookup"><span data-stu-id="77ade-129">**URL**</span></span> |
| :--: | :-- | :-- |
| <span data-ttu-id="77ade-130">Microsoft Defender Antivirus door de cloud geleverde beveiligingsservice, ook wel Microsoft Active Protection Service (KAARTEN)</span><span class="sxs-lookup"><span data-stu-id="77ade-130">Microsoft Defender Antivirus cloud-delivered protection service, also referred to as Microsoft Active Protection Service (MAPS)</span></span>|<span data-ttu-id="77ade-131">Gebruikt door Microsoft Defender Antivirus om beveiliging in de cloud te bieden</span><span class="sxs-lookup"><span data-stu-id="77ade-131">Used by Microsoft Defender Antivirus to provide cloud-delivered protection</span></span>|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| <span data-ttu-id="77ade-132">Microsoft Update Service (MU)</span><span class="sxs-lookup"><span data-stu-id="77ade-132">Microsoft Update Service (MU)</span></span> <br/> <span data-ttu-id="77ade-133">Windows Updateservice (WU)</span><span class="sxs-lookup"><span data-stu-id="77ade-133">Windows Update Service (WU)</span></span>|  <span data-ttu-id="77ade-134">Beveiligingsinformatie en productupdates</span><span class="sxs-lookup"><span data-stu-id="77ade-134">Security intelligence and product updates</span></span>   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> <span data-ttu-id="77ade-135">Zie [Verbindings-eindpunten voor Windows Update voor meer informatie](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span><span class="sxs-lookup"><span data-stu-id="77ade-135">For details see [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span></span>|
|<span data-ttu-id="77ade-136">Beveiligingsinformatieupdates Alternatieve downloadlocatie (ADL)</span><span class="sxs-lookup"><span data-stu-id="77ade-136">Security intelligence updates Alternate Download Location (ADL)</span></span>|   <span data-ttu-id="77ade-137">Alternatieve locatie voor Microsoft Defender Antivirus beveiligingsintelligentieupdates als de geïnstalleerde beveiligingsintelligentie verouderd is (7 of meer dagen achter)</span><span class="sxs-lookup"><span data-stu-id="77ade-137">Alternate location for Microsoft Defender Antivirus Security intelligence updates if the installed Security intelligence is out of date (7 or more days behind)</span></span>|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br>  `go.microsoft.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| <span data-ttu-id="77ade-138">Opslag voor malware indienen</span><span class="sxs-lookup"><span data-stu-id="77ade-138">Malware submission storage</span></span>|<span data-ttu-id="77ade-139">Upload locatie voor bestanden die zijn ingediend bij Microsoft via het formulier Voorzending of automatische voorbeeldinzending</span><span class="sxs-lookup"><span data-stu-id="77ade-139">Upload location for files submitted to Microsoft via the Submission form or automatic sample submission</span></span>    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| <span data-ttu-id="77ade-140">Intrekkingslijst voor certificaten (CRL)</span><span class="sxs-lookup"><span data-stu-id="77ade-140">Certificate Revocation List (CRL)</span></span>|<span data-ttu-id="77ade-141">Gebruikt door Windows bij het maken van de SSL-verbinding met KAARTEN voor het bijwerken van de CRL</span><span class="sxs-lookup"><span data-stu-id="77ade-141">Used by Windows when creating the SSL connection to MAPS for updating the CRL</span></span>   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| <span data-ttu-id="77ade-142">Symbol Store</span><span class="sxs-lookup"><span data-stu-id="77ade-142">Symbol Store</span></span>|<span data-ttu-id="77ade-143">Gebruikt door Microsoft Defender Antivirus om bepaalde kritieke bestanden te herstellen tijdens herstelstromen</span><span class="sxs-lookup"><span data-stu-id="77ade-143">Used by Microsoft Defender Antivirus to restore certain critical files during remediation flows</span></span>  | `https://msdl.microsoft.com/download/symbols` |
| <span data-ttu-id="77ade-144">Universele telemetrieclient</span><span class="sxs-lookup"><span data-stu-id="77ade-144">Universal Telemetry Client</span></span>| <span data-ttu-id="77ade-145">Gebruikt door Windows om diagnostische gegevens van de client te verzenden; Microsoft Defender Antivirus telemetrie gebruikt voor productkwaliteitscontroledoeleinden</span><span class="sxs-lookup"><span data-stu-id="77ade-145">Used by Windows to send client diagnostic data; Microsoft Defender Antivirus uses telemetry for product quality monitoring purposes</span></span>   | <span data-ttu-id="77ade-146">De update gebruikt SSL (TCP-poort 443) om manifesten te downloaden en diagnostische gegevens te uploaden naar Microsoft met de volgende DNS-eindpunten:   `vortex-win.data.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="77ade-146">The update uses SSL (TCP Port 443) to download manifests and upload diagnostic data to Microsoft that uses the following DNS endpoints:   `vortex-win.data.microsoft.com`</span></span> <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a><span data-ttu-id="77ade-147">Verbindingen tussen uw netwerk en de cloud valideren</span><span class="sxs-lookup"><span data-stu-id="77ade-147">Validate connections between your network and the cloud</span></span>

<span data-ttu-id="77ade-148">Nadat u de url's hierboven hebt toestaan, kunt u testen of u verbinding hebt met de Microsoft Defender Antivirus-cloudservice en correct gegevens rapporteert en ontvangt om ervoor te zorgen dat u volledig bent beveiligd.</span><span class="sxs-lookup"><span data-stu-id="77ade-148">After allowing the URLs listed above, you can test if you're connected to the Microsoft Defender Antivirus cloud service and are correctly reporting and receiving information to ensure you're fully protected.</span></span>

<span data-ttu-id="77ade-149">**Gebruik het cmdline-hulpprogramma om beveiliging in de cloud te valideren:**</span><span class="sxs-lookup"><span data-stu-id="77ade-149">**Use the cmdline tool to validate cloud-delivered protection:**</span></span>

<span data-ttu-id="77ade-150">Gebruik het volgende argument met Microsoft Defender Antivirus command-line utility () om te controleren of uw netwerk kan communiceren met de `mpcmdrun.exe` Microsoft Defender Antivirus cloudservice:</span><span class="sxs-lookup"><span data-stu-id="77ade-150">Use the following argument with the Microsoft Defender Antivirus command-line utility (`mpcmdrun.exe`) to verify that your network can communicate with the Microsoft Defender Antivirus cloud service:</span></span>

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> <span data-ttu-id="77ade-151">U moet een versie op beheerdersniveau van de opdrachtprompt openen.</span><span class="sxs-lookup"><span data-stu-id="77ade-151">You need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="77ade-152">Klik met de rechtermuisknop op het item in het menu Start, klik op **Uitvoeren als beheerder** en klik op **Ja** bij de machtigingenprompt.</span><span class="sxs-lookup"><span data-stu-id="77ade-152">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span> <span data-ttu-id="77ade-153">Deze opdracht werkt alleen op Windows 10, versie 1703 of hoger.</span><span class="sxs-lookup"><span data-stu-id="77ade-153">This command will only work on Windows 10, version 1703 or higher.</span></span>

<span data-ttu-id="77ade-154">Zie De Microsoft Defender Antivirus [beheren mpcmdrun.exe opdrachtregel](command-line-arguments-microsoft-defender-antivirus.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="77ade-154">For more information, see [Manage Microsoft Defender Antivirus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="77ade-155">**Probeer een nep-malwarebestand van Microsoft te downloaden:**</span><span class="sxs-lookup"><span data-stu-id="77ade-155">**Attempt to download a fake malware file from Microsoft:**</span></span>

<span data-ttu-id="77ade-156">U kunt een voorbeeldbestand downloaden dat Microsoft Defender Antivirus wordt gedetecteerd en geblokkeerd als u goed bent verbonden met de cloud.</span><span class="sxs-lookup"><span data-stu-id="77ade-156">You can download a sample file that Microsoft Defender Antivirus will detect and block if you're properly connected to the cloud.</span></span>

<span data-ttu-id="77ade-157">Download het bestand door naar [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .</span><span class="sxs-lookup"><span data-stu-id="77ade-157">Download the file by visiting [https://aka.ms/ioavtest](https://aka.ms/ioavtest).</span></span>

> [!NOTE]
> <span data-ttu-id="77ade-158">Dit bestand is geen echt stukje malware.</span><span class="sxs-lookup"><span data-stu-id="77ade-158">This file is not an actual piece of malware.</span></span> <span data-ttu-id="77ade-159">Het is een nepbestand dat is ontworpen om te testen of u goed verbonden bent met de cloud.</span><span class="sxs-lookup"><span data-stu-id="77ade-159">It's a fake file that is designed to test if you're properly connected to the cloud.</span></span>

<span data-ttu-id="77ade-160">Als u goed bent verbonden, ziet u een waarschuwing voor Microsoft Defender Antivirus melding.</span><span class="sxs-lookup"><span data-stu-id="77ade-160">If you're properly connected, you'll see a warning Microsoft Defender Antivirus notification.</span></span>

<span data-ttu-id="77ade-161">Als u een Microsoft Edge gebruikt, ziet u ook een meldingsbericht:</span><span class="sxs-lookup"><span data-stu-id="77ade-161">If you're using Microsoft Edge, you'll also see a notification message:</span></span>

![Microsoft Edge de gebruiker informeren dat malware is gevonden](images/defender/wdav-bafs-edge.png)

<span data-ttu-id="77ade-163">Een soortgelijk bericht treedt op als u Internet Explorer gebruikt:</span><span class="sxs-lookup"><span data-stu-id="77ade-163">A similar message occurs if you're using Internet Explorer:</span></span>

![Microsoft Defender Antivirus de gebruiker te informeren dat malware is gevonden](images/defender/wdav-bafs-ie.png)

<span data-ttu-id="77ade-165">U ziet ook een detectie onder In quarantaine geplaatste **bedreigingen** in de sectie **Scangeschiedenis** in de Windows-beveiliging app:</span><span class="sxs-lookup"><span data-stu-id="77ade-165">You'll also see a detection under **Quarantined threats** in the **Scan history** section in the Windows Security app:</span></span>

1. <span data-ttu-id="77ade-166">Open de Windows-beveiliging app door op het schildpictogram in de taakbalk te klikken of door te zoeken in het startmenu voor **Defender.**</span><span class="sxs-lookup"><span data-stu-id="77ade-166">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="77ade-167">Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk) en vervolgens het label **Scangeschiedenis:**</span><span class="sxs-lookup"><span data-stu-id="77ade-167">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Scan history** label:</span></span>

    ![Schermafbeelding van het label Geschiedenis scannen in de Windows-beveiliging app](images/defender/wdav-history-wdsc.png)

3. <span data-ttu-id="77ade-169">Selecteer onder **de sectie In quarantaine geplaatste** bedreigingen de optie Volledige geschiedenis **bekijken** om de gedetecteerde nep-malware te zien.</span><span class="sxs-lookup"><span data-stu-id="77ade-169">Under the **Quarantined threats** section, select **See full history** to see the detected fake malware.</span></span>

   > [!NOTE]
   > <span data-ttu-id="77ade-170">Versies van Windows 10 versie 1703 hebben een andere gebruikersinterface.</span><span class="sxs-lookup"><span data-stu-id="77ade-170">Versions of Windows 10 before version 1703 have a different user interface.</span></span> <span data-ttu-id="77ade-171">Zie [Microsoft Defender Antivirus in de Windows-beveiliging app](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="77ade-171">See [Microsoft Defender Antivirus in the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

   <span data-ttu-id="77ade-172">In Windows gebeurtenislogboek wordt ook Windows Defender [clientgebeurtenis-id 1116.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="77ade-172">The Windows event log will also show [Windows Defender client event ID 1116](troubleshoot-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="77ade-173">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="77ade-173">Related articles</span></span>

- [<span data-ttu-id="77ade-174">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="77ade-174">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="77ade-175">Cloudbeveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="77ade-175">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="77ade-176">Opdrachtregelargumenten</span><span class="sxs-lookup"><span data-stu-id="77ade-176">Command line arguments</span></span>](command-line-arguments-microsoft-defender-antivirus.md)

- [<span data-ttu-id="77ade-177">Belangrijke wijzigingen in het eindpunt van Microsoft Active Protection Services</span><span class="sxs-lookup"><span data-stu-id="77ade-177">Important changes to Microsoft Active Protection Services endpoint</span></span>](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)
