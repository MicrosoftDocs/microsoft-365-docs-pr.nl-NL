---
title: Microsoft Defender voor Eindpunt op Android - Privacyinformatie
description: Privacybesturingselementen, het configureren van beleidsinstellingen die van invloed zijn op privacy en informatie over de diagnostische gegevens die worden verzameld in Microsoft Defender voor Eindpunt op Android.
keywords: microsoft, defender, Microsoft Defender for Endpoint, android, privacy, diagnostic
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 415a1f555e1a33c103894221086b783aa754cf32
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930135"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a><span data-ttu-id="13bfa-104">Microsoft Defender voor Eindpunt op Android - Privacyinformatie</span><span class="sxs-lookup"><span data-stu-id="13bfa-104">Microsoft Defender for Endpoint on Android - Privacy information</span></span>

<span data-ttu-id="13bfa-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="13bfa-105">**Applies to:**</span></span>
- [<span data-ttu-id="13bfa-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="13bfa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="13bfa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="13bfa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="13bfa-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="13bfa-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="13bfa-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="13bfa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="13bfa-110">Defender voor Eindpunt op Android verzamelt gegevens van uw geconfigureerde Android-apparaten en slaat deze op in dezelfde tenant waar u Defender voor Eindpunt hebt.</span><span class="sxs-lookup"><span data-stu-id="13bfa-110">Defender for Endpoint on Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span> <span data-ttu-id="13bfa-111">De gegevens worden verzameld om Defender voor Eindpunt voor Android veilig, up-to-date te houden, te presteren zoals verwacht en om de service te ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="13bfa-111">The information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected, and to support the service.</span></span>

<span data-ttu-id="13bfa-112">Zie Microsoft Defender for [Endpoint data storage and privacy (Microsoft Defender for Endpoint data storage and privacy) voor meer informatie over gegevensopslag.](data-storage-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="13bfa-112">For more information about data storage, see [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span></span>

<span data-ttu-id="13bfa-113">Er worden gegevens verzameld om Defender voor Eindpunt voor Android veilig, up-to-date te houden, te presteren zoals verwacht en om de service te ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="13bfa-113">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

## <a name="required-data"></a><span data-ttu-id="13bfa-114">Vereiste gegevens</span><span class="sxs-lookup"><span data-stu-id="13bfa-114">Required Data</span></span> 

<span data-ttu-id="13bfa-115">Vereiste gegevens bestaan uit gegevens die nodig zijn om Defender voor Eindpunt voor Android te laten werken zoals verwacht.</span><span class="sxs-lookup"><span data-stu-id="13bfa-115">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="13bfa-116">Deze gegevens zijn essentieel voor de werking van de service en kunnen gegevens bevatten die betrekking hebben op de eindgebruiker, de organisatie, het apparaat en apps.</span><span class="sxs-lookup"><span data-stu-id="13bfa-116">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="13bfa-117">Hier is een lijst met de typen gegevens die worden verzameld:</span><span class="sxs-lookup"><span data-stu-id="13bfa-117">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="13bfa-118">App-informatie</span><span class="sxs-lookup"><span data-stu-id="13bfa-118">App information</span></span>

<span data-ttu-id="13bfa-119">Informatie over **kwaadaardige** Android-toepassingspakketten (APK's) op het apparaat, waaronder</span><span class="sxs-lookup"><span data-stu-id="13bfa-119">Information about **malicious** Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="13bfa-120">Installatiebron</span><span class="sxs-lookup"><span data-stu-id="13bfa-120">Install source</span></span>
-  <span data-ttu-id="13bfa-121">Opslaglocatie (bestandspad) van de APK</span><span class="sxs-lookup"><span data-stu-id="13bfa-121">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="13bfa-122">Tijd van installatie, grootte van APK en machtigingen</span><span class="sxs-lookup"><span data-stu-id="13bfa-122">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="13bfa-123">Webpagina/netwerkgegevens</span><span class="sxs-lookup"><span data-stu-id="13bfa-123">Web page / Network information</span></span>

- <span data-ttu-id="13bfa-124">Volledige URL van de website alleen wanneer een schadelijke verbinding of webpagina wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="13bfa-124">Full URL of the website only when a malicious connection or web page is detected.</span></span>
- <span data-ttu-id="13bfa-125">Verbindingsgegevens</span><span class="sxs-lookup"><span data-stu-id="13bfa-125">Connection information</span></span>
- <span data-ttu-id="13bfa-126">Protocoltype (zoals HTTP, HTTPS, enzovoort)</span><span class="sxs-lookup"><span data-stu-id="13bfa-126">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="13bfa-127">Apparaat- en accountgegevens</span><span class="sxs-lookup"><span data-stu-id="13bfa-127">Device and account information</span></span>

- <span data-ttu-id="13bfa-128">Apparaatgegevens, zoals datum &, Android-versie, OEM-model, CPU-informatie en apparaataanduiding</span><span class="sxs-lookup"><span data-stu-id="13bfa-128">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="13bfa-129">Apparaataanduiding is een van de volgende:</span><span class="sxs-lookup"><span data-stu-id="13bfa-129">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="13bfa-130">Wi-Fi mac-adres van adapter</span><span class="sxs-lookup"><span data-stu-id="13bfa-130">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="13bfa-131">[Android-id](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (zoals gegenereerd door Android op het moment van de eerste keer opstarten van het apparaat)</span><span class="sxs-lookup"><span data-stu-id="13bfa-131">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="13bfa-132">Willekeurig gegenereerde, wereldwijd unieke id (GUID)</span><span class="sxs-lookup"><span data-stu-id="13bfa-132">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="13bfa-133">Tenant-, apparaat- en gebruikersgegevens</span><span class="sxs-lookup"><span data-stu-id="13bfa-133">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="13bfa-134">Azure Active Directory (AD) Device ID en Azure User ID: Uniek identificeert het apparaat, gebruiker respectievelijk bij Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="13bfa-134">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="13bfa-135">Azure tenant-id - GUID die uw organisatie identificeert in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="13bfa-135">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="13bfa-136">Microsoft Defender ATP-organisatie-id : unieke id die is gekoppeld aan de onderneming waar het apparaat deel van uitmaken.</span><span class="sxs-lookup"><span data-stu-id="13bfa-136">Microsoft Defender ATP org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="13bfa-137">Hiermee kan Microsoft bepalen of problemen van invloed zijn op een selecte set ondernemingen en hoeveel ondernemingen van invloed zijn</span><span class="sxs-lookup"><span data-stu-id="13bfa-137">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="13bfa-138">Gebruikersnaam : e-mail-id van de gebruiker</span><span class="sxs-lookup"><span data-stu-id="13bfa-138">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="13bfa-139">Gegevens over product- en servicegebruik</span><span class="sxs-lookup"><span data-stu-id="13bfa-139">Product and service usage data</span></span>

<span data-ttu-id="13bfa-140">De volgende gegevens worden alleen verzameld voor de Microsoft Defender for Endpoint-app die op het apparaat is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="13bfa-140">The following information is collected only for Microsoft Defender for Endpoint app installed on the device.</span></span> 

-   <span data-ttu-id="13bfa-141">App-pakketgegevens, waaronder de status van de naam, versie en app-upgrade</span><span class="sxs-lookup"><span data-stu-id="13bfa-141">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="13bfa-142">Acties uitgevoerd in de app</span><span class="sxs-lookup"><span data-stu-id="13bfa-142">Actions performed in the app</span></span>

-   <span data-ttu-id="13bfa-143">Informatie over bedreigingsdetectie, zoals bedreigingsnaam, categorie, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="13bfa-143">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="13bfa-144">Crashrapportlogboeken die zijn gegenereerd door Android</span><span class="sxs-lookup"><span data-stu-id="13bfa-144">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="13bfa-145">Optionele gegevens</span><span class="sxs-lookup"><span data-stu-id="13bfa-145">Optional Data</span></span>

<span data-ttu-id="13bfa-146">Optionele gegevens omvatten diagnostische gegevens en feedbackgegevens.</span><span class="sxs-lookup"><span data-stu-id="13bfa-146">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="13bfa-147">Optionele diagnostische gegevens: aanvullende gegevens voor het maken van productverbeteringen en het verstrekken van uitgebreide informatie voor het detecteren, diagnosticeren en oplossen van problemen.</span><span class="sxs-lookup"><span data-stu-id="13bfa-147">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="13bfa-148">Optionele diagnostische gegevens omvatten:</span><span class="sxs-lookup"><span data-stu-id="13bfa-148">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="13bfa-149">App-, CPU- en netwerkgebruik</span><span class="sxs-lookup"><span data-stu-id="13bfa-149">App, CPU, and network usage</span></span>

-   <span data-ttu-id="13bfa-150">Status van het apparaat vanuit het app-perspectief, inclusief scanstatus, tijdsinstellingen scannen, app-machtigingen verleend en upgradestatus</span><span class="sxs-lookup"><span data-stu-id="13bfa-150">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="13bfa-151">Functies die zijn geconfigureerd door de beheerder</span><span class="sxs-lookup"><span data-stu-id="13bfa-151">Features configured by the admin</span></span>

-   <span data-ttu-id="13bfa-152">Basisinformatie over de browsers op het apparaat</span><span class="sxs-lookup"><span data-stu-id="13bfa-152">Basic information about the browsers on the device</span></span>

<span data-ttu-id="13bfa-153">**Feedbackgegevens** worden verzameld via in-app feedback van de gebruiker</span><span class="sxs-lookup"><span data-stu-id="13bfa-153">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="13bfa-154">Het e-mailadres van de gebruiker als hij of zij ervoor kiest om het op te geven</span><span class="sxs-lookup"><span data-stu-id="13bfa-154">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="13bfa-155">Feedbacktype (glimlach, frons, idee) en eventuele feedback van de gebruiker</span><span class="sxs-lookup"><span data-stu-id="13bfa-155">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
