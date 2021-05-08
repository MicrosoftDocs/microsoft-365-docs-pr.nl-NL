---
title: Netwerkverbindingen van Microsoft Defender Antivirus configureren en valideren
description: Configureer en test uw verbinding met de cloudbeveiligingsservice van Microsoft Defender Antivirus.
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
ms.date: 12/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c049a7301cc651dbf2621d0baa398117856b925
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274638"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a><span data-ttu-id="d41c5-104">Netwerkverbindingen van Microsoft Defender Antivirus configureren en valideren</span><span class="sxs-lookup"><span data-stu-id="d41c5-104">Configure and validate Microsoft Defender Antivirus network connections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d41c5-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d41c5-105">**Applies to:**</span></span>

- [<span data-ttu-id="d41c5-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="d41c5-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d41c5-107">Als u ervoor wilt zorgen dat de beveiliging van Microsoft Defender Antivirus in de cloud correct werkt, moet u uw netwerk zo configureren dat verbindingen tussen uw eindpunten en bepaalde Microsoft-servers worden toegestaan.</span><span class="sxs-lookup"><span data-stu-id="d41c5-107">To ensure Microsoft Defender Antivirus cloud-delivered protection works properly, you need to configure your network to allow connections between your endpoints and certain Microsoft servers.</span></span>

<span data-ttu-id="d41c5-108">In dit artikel worden de verbindingen vermeld die moeten worden toegestaan, bijvoorbeeld met behulp van firewallregels, en worden instructies gegeven voor het valideren van uw verbinding.</span><span class="sxs-lookup"><span data-stu-id="d41c5-108">This article lists the connections that must be allowed, such as by using firewall rules, and provides instructions for validating your connection.</span></span> <span data-ttu-id="d41c5-109">Als u uw beveiliging correct configureert, kunt u ervoor zorgen dat u de beste waarde ontvangt van uw beveiligingsservices die in de cloud worden geleverd.</span><span class="sxs-lookup"><span data-stu-id="d41c5-109">Configuring your protection properly helps ensure that you receive the best value from your cloud-delivered protection services.</span></span>

<span data-ttu-id="d41c5-110">Zie het blogbericht [Belangrijke wijzigingen in het eindpunt van Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) voor meer informatie over netwerkconnectiviteit.</span><span class="sxs-lookup"><span data-stu-id="d41c5-110">See the blog post [Important changes to Microsoft Active Protection Services endpoint](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) for some details about network connectivity.</span></span>

>[!TIP]
><span data-ttu-id="d41c5-111">U kunt ook naar de demowebsite [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) van Microsoft Defender voor Eindpunt demo.wd.microsoft.com om te bevestigen dat de volgende functies werken:</span><span class="sxs-lookup"><span data-stu-id="d41c5-111">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
>
>- <span data-ttu-id="d41c5-112">Cloudbeveiliging</span><span class="sxs-lookup"><span data-stu-id="d41c5-112">Cloud-delivered protection</span></span>
>- <span data-ttu-id="d41c5-113">Snel leren (inclusief blok op het eerste gezicht)</span><span class="sxs-lookup"><span data-stu-id="d41c5-113">Fast learning (including block at first sight)</span></span>
>- <span data-ttu-id="d41c5-114">Mogelijk ongewenste blokkering van toepassingen</span><span class="sxs-lookup"><span data-stu-id="d41c5-114">Potentially unwanted application blocking</span></span>

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a><span data-ttu-id="d41c5-115">Verbindingen met de Microsoft Defender Antivirus-cloudservice toestaan</span><span class="sxs-lookup"><span data-stu-id="d41c5-115">Allow connections to the Microsoft Defender Antivirus cloud service</span></span>

<span data-ttu-id="d41c5-116">De Microsoft Defender Antivirus-cloudservice biedt snelle, krachtige beveiliging voor uw eindpunten.</span><span class="sxs-lookup"><span data-stu-id="d41c5-116">The Microsoft Defender Antivirus cloud service provides fast, strong protection for your endpoints.</span></span> <span data-ttu-id="d41c5-117">Het inschakelen van de door de cloud geleverde beveiligingsservice is optioneel, maar het wordt ten zeerste aanbevolen omdat deze belangrijke bescherming biedt tegen malware op uw eindpunten en in uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="d41c5-117">Enabling the cloud-delivered protection service is optional, however it's highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

>[!NOTE]
><span data-ttu-id="d41c5-118">De Microsoft Defender Antivirus-cloudservice is een mechanisme voor het leveren van bijgewerkte beveiliging aan uw netwerk en eindpunten.</span><span class="sxs-lookup"><span data-stu-id="d41c5-118">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="d41c5-119">Hoewel het een cloudservice wordt genoemd, is het niet alleen beveiliging voor bestanden die zijn opgeslagen in de cloud, maar wordt gebruikgemaakt van gedistribueerde resources en machine learning om uw eindpunten te beschermen tegen een snelheid die veel sneller is dan traditionele beveiligingsinformatie-updates.</span><span class="sxs-lookup"><span data-stu-id="d41c5-119">Although it's called a cloud service, it's not simply protection for files stored in the cloud, rather it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="d41c5-120">Zie Beveiliging in de cloud inschakelen voor meer informatie over het inschakelen van de service met Intune, Microsoft Endpoint Configuration Manager, Groepsbeleid, PowerShell-cmdlets of op afzonderlijke clients in de Windows [Security-app.](enable-cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d41c5-120">See [Enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) for details on enabling the service with Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, or on individual clients in the Windows Security app.</span></span> 

<span data-ttu-id="d41c5-121">Nadat u de service hebt ingeschakeld, moet u mogelijk uw netwerk of firewall configureren om verbindingen tussen de service en uw eindpunten toe te staan.</span><span class="sxs-lookup"><span data-stu-id="d41c5-121">After you've enabled the service, you may need to configure your network or firewall to allow connections between it and your endpoints.</span></span>

<span data-ttu-id="d41c5-122">Omdat uw beveiliging een cloudservice is, moeten computers toegang hebben tot internet en de Machine Learning-services van Microsoft Defender voor Office 365 bereiken.</span><span class="sxs-lookup"><span data-stu-id="d41c5-122">Because your protection is a cloud service, computers must have access to the internet and reach the Microsoft Defender for Office 365 machine learning services.</span></span> <span data-ttu-id="d41c5-123">Sluit de URL niet uit `*.blob.core.windows.net` van een netwerkcontrole.</span><span class="sxs-lookup"><span data-stu-id="d41c5-123">Don't exclude the URL `*.blob.core.windows.net` from any kind of network inspection.</span></span> 

<span data-ttu-id="d41c5-124">De onderstaande tabel bevat de services en bijbehorende URL's.</span><span class="sxs-lookup"><span data-stu-id="d41c5-124">The table below lists the services and their associated URLs.</span></span> <span data-ttu-id="d41c5-125">Zorg ervoor dat er geen firewall- of netwerkfilterregels zijn die toegang tot deze URL's weigeren, of u moet mogelijk een regel voor toestaan speciaal voor hen maken (met uitzondering van de `*.blob.core.windows.net` URL).</span><span class="sxs-lookup"><span data-stu-id="d41c5-125">Make sure that there are no firewall or network filtering rules denying access to these URLs, or you may need to create an allow rule specifically for them (excluding the URL `*.blob.core.windows.net`).</span></span> <span data-ttu-id="d41c5-126">Hieronder vermelden URL's gebruiken poort 443 voor communicatie.</span><span class="sxs-lookup"><span data-stu-id="d41c5-126">Below mention URLs are using port 443 for communication.</span></span>


| <span data-ttu-id="d41c5-127">**Service**</span><span class="sxs-lookup"><span data-stu-id="d41c5-127">**Service**</span></span>| <span data-ttu-id="d41c5-128">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="d41c5-128">**Description**</span></span> |<span data-ttu-id="d41c5-129">**URL**</span><span class="sxs-lookup"><span data-stu-id="d41c5-129">**URL**</span></span> |
| :--: | :-- | :-- |
| <span data-ttu-id="d41c5-130">Microsoft Defender Antivirus-beveiligingsservice in de cloud, ook wel Microsoft Active Protection Service (MAPS) genoemd</span><span class="sxs-lookup"><span data-stu-id="d41c5-130">Microsoft Defender Antivirus cloud-delivered protection service, also referred to as Microsoft Active Protection Service (MAPS)</span></span>|<span data-ttu-id="d41c5-131">Gebruikt door Microsoft Defender Antivirus om beveiliging in de cloud te bieden</span><span class="sxs-lookup"><span data-stu-id="d41c5-131">Used by Microsoft Defender Antivirus to provide cloud-delivered protection</span></span>|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| <span data-ttu-id="d41c5-132">Microsoft Update Service (MU)</span><span class="sxs-lookup"><span data-stu-id="d41c5-132">Microsoft Update Service (MU)</span></span> <br/> <span data-ttu-id="d41c5-133">Windows Update Service (WU)</span><span class="sxs-lookup"><span data-stu-id="d41c5-133">Windows Update Service (WU)</span></span>|  <span data-ttu-id="d41c5-134">Beveiligingsinformatie en productupdates</span><span class="sxs-lookup"><span data-stu-id="d41c5-134">Security intelligence and product updates</span></span>   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> <span data-ttu-id="d41c5-135">Zie Verbindings [eindpunten voor Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update) voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="d41c5-135">For details see [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span></span>|
|<span data-ttu-id="d41c5-136">Beveiligingsinformatieupdates Alternatieve downloadlocatie (ADL)</span><span class="sxs-lookup"><span data-stu-id="d41c5-136">Security intelligence updates Alternate Download Location (ADL)</span></span>|   <span data-ttu-id="d41c5-137">Alternatieve locatie voor updates van Microsoft Defender Antivirus Security Intelligence als de geïnstalleerde beveiligingsintelligentie verouderd is (7 of meer dagen achter)</span><span class="sxs-lookup"><span data-stu-id="d41c5-137">Alternate location for Microsoft Defender Antivirus Security intelligence updates if the installed Security intelligence is out of date (7 or more days behind)</span></span>|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| <span data-ttu-id="d41c5-138">Opslag voor malware indienen</span><span class="sxs-lookup"><span data-stu-id="d41c5-138">Malware submission storage</span></span>|<span data-ttu-id="d41c5-139">Locatie uploaden voor bestanden die naar Microsoft zijn verzonden via het formulier Voorzending of automatische voorbeeldinzending</span><span class="sxs-lookup"><span data-stu-id="d41c5-139">Upload location for files submitted to Microsoft via the Submission form or automatic sample submission</span></span>    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| <span data-ttu-id="d41c5-140">Intrekkingslijst voor certificaten (CRL)</span><span class="sxs-lookup"><span data-stu-id="d41c5-140">Certificate Revocation List (CRL)</span></span>|<span data-ttu-id="d41c5-141">Gebruikt door Windows bij het maken van de SSL-verbinding met KAARTEN voor het bijwerken van de CRL</span><span class="sxs-lookup"><span data-stu-id="d41c5-141">Used by Windows when creating the SSL connection to MAPS for updating the CRL</span></span>   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| <span data-ttu-id="d41c5-142">Symbol Store</span><span class="sxs-lookup"><span data-stu-id="d41c5-142">Symbol Store</span></span>|<span data-ttu-id="d41c5-143">Gebruikt door Microsoft Defender Antivirus om bepaalde kritieke bestanden te herstellen tijdens herstelstromen</span><span class="sxs-lookup"><span data-stu-id="d41c5-143">Used by Microsoft Defender Antivirus to restore certain critical files during remediation flows</span></span>  | `https://msdl.microsoft.com/download/symbols` |
| <span data-ttu-id="d41c5-144">Universele telemetrieclient</span><span class="sxs-lookup"><span data-stu-id="d41c5-144">Universal Telemetry Client</span></span>| <span data-ttu-id="d41c5-145">Wordt door Windows gebruikt om diagnostische gegevens van de client te verzenden; Microsoft Defender Antivirus gebruikt telemetrie voor kwaliteitsbewakingsdoeleinden</span><span class="sxs-lookup"><span data-stu-id="d41c5-145">Used by Windows to send client diagnostic data; Microsoft Defender Antivirus uses telemetry for product quality monitoring purposes</span></span>   | <span data-ttu-id="d41c5-146">De update gebruikt SSL (TCP-poort 443) om manifesten te downloaden en diagnostische gegevens te uploaden naar Microsoft met de volgende DNS-eindpunten:   `vortex-win.data.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="d41c5-146">The update uses SSL (TCP Port 443) to download manifests and upload diagnostic data to Microsoft that uses the following DNS endpoints:   `vortex-win.data.microsoft.com`</span></span> <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a><span data-ttu-id="d41c5-147">Verbindingen tussen uw netwerk en de cloud valideren</span><span class="sxs-lookup"><span data-stu-id="d41c5-147">Validate connections between your network and the cloud</span></span>

<span data-ttu-id="d41c5-148">Nadat u de hierboven genoemde URL's hebt toestaan, kunt u testen of u verbinding hebt met de Microsoft Defender Antivirus-cloudservice en correct gegevens rapporteert en ontvangt om ervoor te zorgen dat u volledig bent beveiligd.</span><span class="sxs-lookup"><span data-stu-id="d41c5-148">After allowing the URLs listed above, you can test if you're connected to the Microsoft Defender Antivirus cloud service and are correctly reporting and receiving information to ensure you're fully protected.</span></span>

<span data-ttu-id="d41c5-149">**Gebruik het cmdline-hulpprogramma om beveiliging in de cloud te valideren:**</span><span class="sxs-lookup"><span data-stu-id="d41c5-149">**Use the cmdline tool to validate cloud-delivered protection:**</span></span>

<span data-ttu-id="d41c5-150">Gebruik het volgende argument met de microsoft Defender Antivirus command-line utility () om te controleren of uw netwerk kan communiceren met de `mpcmdrun.exe` Microsoft Defender Antivirus-cloudservice:</span><span class="sxs-lookup"><span data-stu-id="d41c5-150">Use the following argument with the Microsoft Defender Antivirus command-line utility (`mpcmdrun.exe`) to verify that your network can communicate with the Microsoft Defender Antivirus cloud service:</span></span>

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> <span data-ttu-id="d41c5-151">U moet een versie op beheerdersniveau van de opdrachtprompt openen.</span><span class="sxs-lookup"><span data-stu-id="d41c5-151">You need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="d41c5-152">Klik met de rechtermuisknop op het item in het menu Start, klik op **Uitvoeren als beheerder** en klik op **Ja** bij de machtigingenprompt.</span><span class="sxs-lookup"><span data-stu-id="d41c5-152">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span> <span data-ttu-id="d41c5-153">Deze opdracht werkt alleen in Windows 10, versie 1703 of hoger.</span><span class="sxs-lookup"><span data-stu-id="d41c5-153">This command will only work on Windows 10, version 1703 or higher.</span></span>

<span data-ttu-id="d41c5-154">Zie Microsoft Defender Antivirus beheren met het mpcmdrun.exe [commandline-hulpprogramma voor meer informatie.](command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d41c5-154">For more information, see [Manage Microsoft Defender Antivirus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="d41c5-155">**Probeer een nep-malwarebestand van Microsoft te downloaden:**</span><span class="sxs-lookup"><span data-stu-id="d41c5-155">**Attempt to download a fake malware file from Microsoft:**</span></span>

<span data-ttu-id="d41c5-156">U kunt een voorbeeldbestand downloaden dat door Microsoft Defender Antivirus wordt gedetecteerd en geblokkeerd als u goed verbonden bent met de cloud.</span><span class="sxs-lookup"><span data-stu-id="d41c5-156">You can download a sample file that Microsoft Defender Antivirus will detect and block if you're properly connected to the cloud.</span></span>

<span data-ttu-id="d41c5-157">Download het bestand door naar [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .</span><span class="sxs-lookup"><span data-stu-id="d41c5-157">Download the file by visiting [https://aka.ms/ioavtest](https://aka.ms/ioavtest).</span></span>

>[!NOTE]
><span data-ttu-id="d41c5-158">Dit bestand is geen echt stukje malware.</span><span class="sxs-lookup"><span data-stu-id="d41c5-158">This file is not an actual piece of malware.</span></span> <span data-ttu-id="d41c5-159">Het is een nepbestand dat is ontworpen om te testen of u goed verbonden bent met de cloud.</span><span class="sxs-lookup"><span data-stu-id="d41c5-159">It's a fake file that is designed to test if you're properly connected to the cloud.</span></span>

<span data-ttu-id="d41c5-160">Als u goed bent verbonden, ziet u een waarschuwingsmelding voor Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="d41c5-160">If you're properly connected, you'll see a warning Microsoft Defender Antivirus notification.</span></span>

<span data-ttu-id="d41c5-161">Als u Microsoft Edge gebruikt, ziet u ook een meldingsbericht:</span><span class="sxs-lookup"><span data-stu-id="d41c5-161">If you're using Microsoft Edge, you'll also see a notification message:</span></span>

![Microsoft Edge die de gebruiker informeert dat malware is gevonden](images/defender/wdav-bafs-edge.png)

<span data-ttu-id="d41c5-163">Een soortgelijk bericht treedt op als u Internet Explorer gebruikt:</span><span class="sxs-lookup"><span data-stu-id="d41c5-163">A similar message occurs if you're using Internet Explorer:</span></span>

![Microsoft Defender Antivirusmelding die de gebruiker informeert dat malware is gevonden](images/defender/wdav-bafs-ie.png)

<span data-ttu-id="d41c5-165">U ziet ook een detectie onder In **quarantaine** geplaatste bedreigingen in de sectie **Scangeschiedenis** in de Windows Security-app:</span><span class="sxs-lookup"><span data-stu-id="d41c5-165">You'll also see a detection under **Quarantined threats** in the **Scan history** section in the Windows Security app:</span></span>

1. <span data-ttu-id="d41c5-166">Open de Windows Security-app door op het schildpictogram op de taakbalk te klikken of door te zoeken in het startmenu voor **Defender.**</span><span class="sxs-lookup"><span data-stu-id="d41c5-166">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="d41c5-167">Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk) en vervolgens het label **Scangeschiedenis:**</span><span class="sxs-lookup"><span data-stu-id="d41c5-167">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Scan history** label:</span></span>

    ![Schermafbeelding van het label Scangeschiedenis in de Windows Security-app](images/defender/wdav-history-wdsc.png)

3. <span data-ttu-id="d41c5-169">Selecteer onder **de sectie In quarantaine geplaatste** bedreigingen de optie Volledige geschiedenis **bekijken** om de gedetecteerde nep-malware te zien.</span><span class="sxs-lookup"><span data-stu-id="d41c5-169">Under the **Quarantined threats** section, select **See full history** to see the detected fake malware.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d41c5-170">Versies van Windows 10 vóór versie 1703 hebben een andere gebruikersinterface.</span><span class="sxs-lookup"><span data-stu-id="d41c5-170">Versions of Windows 10 before version 1703 have a different user interface.</span></span> <span data-ttu-id="d41c5-171">Zie [Microsoft Defender Antivirus in de Windows Security-app](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="d41c5-171">See [Microsoft Defender Antivirus in the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

   <span data-ttu-id="d41c5-172">In het Windows-gebeurtenislogboek wordt ook [Windows Defender-clientgebeurtenis-id 1116 voor client.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d41c5-172">The Windows event log will also show [Windows Defender client event ID 1116](troubleshoot-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="d41c5-173">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="d41c5-173">Related articles</span></span>

- [<span data-ttu-id="d41c5-174">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="d41c5-174">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="d41c5-175">Beveiliging via de cloud inschakelen</span><span class="sxs-lookup"><span data-stu-id="d41c5-175">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="d41c5-176">Opdrachtregelargumenten</span><span class="sxs-lookup"><span data-stu-id="d41c5-176">Command line arguments</span></span>](command-line-arguments-microsoft-defender-antivirus.md)

- [<span data-ttu-id="d41c5-177">Belangrijke wijzigingen in het eindpunt van Microsoft Active Protection Services</span><span class="sxs-lookup"><span data-stu-id="d41c5-177">Important changes to Microsoft Active Protection Services endpoint</span></span>](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)