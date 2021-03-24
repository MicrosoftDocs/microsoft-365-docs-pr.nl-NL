---
title: Problemen met microsoft Defender ATP live-antwoord oplossen
description: Problemen oplossen die zich kunnen voordoen bij het gebruik van live-antwoorden in Microsoft Defender ATP
keywords: problemen met livereactie, live, antwoord, vergrendeld, bestand oplossen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 27f2c7eb01a857ec38b11797c0703710c02ac1bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060642"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a><span data-ttu-id="99360-104">Problemen met live-antwoorden op Microsoft Defender voor Eindpunt oplossen</span><span class="sxs-lookup"><span data-stu-id="99360-104">Troubleshoot Microsoft Defender for Endpoint live response issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="99360-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="99360-105">**Applies to:**</span></span>
- [<span data-ttu-id="99360-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="99360-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="99360-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="99360-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="99360-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="99360-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="99360-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="99360-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="99360-110">Op deze pagina vindt u gedetailleerde stappen om problemen met livereacties op te lossen.</span><span class="sxs-lookup"><span data-stu-id="99360-110">This page provides detailed steps to troubleshoot live response issues.</span></span>

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a><span data-ttu-id="99360-111">Bestand kan niet worden gebruikt tijdens livereactiesessies</span><span class="sxs-lookup"><span data-stu-id="99360-111">File cannot be accessed during live response sessions</span></span>
<span data-ttu-id="99360-112">Als u tijdens een livereactiesessie een actie probeert uit te voeren, wordt er een foutbericht weergegeven waarin wordt aangegeven dat het bestand niet kan worden gebruikt, moet u de onderstaande stappen gebruiken om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="99360-112">If while trying to take an action during a live response session, you encounter an error message stating that the file can't be accessed, you'll need to use the steps below to address the issue.</span></span>

1. <span data-ttu-id="99360-113">Kopieer het volgende scriptcodefragment en sla het op als een PS1-bestand:</span><span class="sxs-lookup"><span data-stu-id="99360-113">Copy the following script code snippet and save it as a PS1 file:</span></span>

    ```
    $copied_file_path=$args[0] 
    $action=Copy-Item $copied_file_path -Destination $env:TEMP -PassThru -ErrorAction silentlyContinue
        
    if ($action){
         Write-Host "You copied the file specified in $copied_file_path to $env:TEMP Succesfully"
    }
    
    else{
        Write-Output "Error occoured while trying to copy a file, details:"
        Write-Output  $error[0].exception.message
 
    }
    ```


2. <span data-ttu-id="99360-114">Voeg het script toe aan de live antwoordbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="99360-114">Add the script to the live response library.</span></span>
3. <span data-ttu-id="99360-115">Voer het script uit met één parameter: het bestandspad van het bestand dat moet worden gekopieerd.</span><span class="sxs-lookup"><span data-stu-id="99360-115">Run the script with one parameter: the file path of the file to be copied.</span></span>
4. <span data-ttu-id="99360-116">Ga naar de map TEMP.</span><span class="sxs-lookup"><span data-stu-id="99360-116">Navigate to your TEMP folder.</span></span>
5. <span data-ttu-id="99360-117">Voer de actie uit die u wilt uitvoeren voor het gekopieerde bestand.</span><span class="sxs-lookup"><span data-stu-id="99360-117">Run the action you wanted to take on the copied file.</span></span>

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a><span data-ttu-id="99360-118">Slow live response sessions or delays during initial connections</span><span class="sxs-lookup"><span data-stu-id="99360-118">Slow live response sessions or delays during initial connections</span></span>
<span data-ttu-id="99360-119">Live response maakt gebruik van De registratie van de Defender voor eindpunten-sensor met de WNS-service in Windows.</span><span class="sxs-lookup"><span data-stu-id="99360-119">Live response leverages Defender for Endpoint sensor registration with WNS service in Windows.</span></span> <span data-ttu-id="99360-120">Als u verbindingsproblemen hebt met livereacties, bevestigt u de volgende details:</span><span class="sxs-lookup"><span data-stu-id="99360-120">If you are having connectivity issues with live response, confirm the following details:</span></span>
1. <span data-ttu-id="99360-121">`notify.windows.com` is niet geblokkeerd in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="99360-121">`notify.windows.com` is not blocked in your environment.</span></span> <span data-ttu-id="99360-122">Zie Apparaatproxy- en [internetverbindingsinstellingen configureren](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="99360-122">For more information, see, [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>
2. <span data-ttu-id="99360-123">WpnService (Windows Push Notifications System Service) is niet uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="99360-123">WpnService (Windows Push Notifications System Service) is not disabled.</span></span>

<span data-ttu-id="99360-124">Raadpleeg de onderstaande artikelen om volledig inzicht te krijgen in het gedrag en de vereisten van de WpnService-service:</span><span class="sxs-lookup"><span data-stu-id="99360-124">Refer to the articles below to fully understand the WpnService service behavior and requirements:</span></span>
- [<span data-ttu-id="99360-125">Overzicht van Windows Push Notification Services (WNS)</span><span class="sxs-lookup"><span data-stu-id="99360-125">Windows Push Notification Services (WNS) overview</span></span>](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [<span data-ttu-id="99360-126">Enterprise Firewall en proxyconfiguraties ter ondersteuning van WNS-verkeer</span><span class="sxs-lookup"><span data-stu-id="99360-126">Enterprise Firewall and Proxy Configurations to Support WNS Traffic</span></span>](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [<span data-ttu-id="99360-127">Openbare IP-bereik (Microsoft Push Notifications Service)</span><span class="sxs-lookup"><span data-stu-id="99360-127">Microsoft Push Notifications Service (MPNS) Public IP ranges</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

