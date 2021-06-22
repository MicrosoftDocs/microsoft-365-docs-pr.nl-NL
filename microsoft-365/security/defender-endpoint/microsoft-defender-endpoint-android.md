---
title: Microsoft Defender voor Eindpunt op Android
ms.reviewer: ''
description: Beschrijft hoe u Microsoft Defender voor Eindpunt op Android installeert en gebruikt
keywords: microsoft, defender, Microsoft Defender for Endpoint, android, installation, deploy, uninstallation, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ceccd9e3c8a8137f672e7be519675034a84c7881
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055111"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="b3100-104">Microsoft Defender voor Eindpunt op Android</span><span class="sxs-lookup"><span data-stu-id="b3100-104">Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b3100-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b3100-105">**Applies to:**</span></span>
- [<span data-ttu-id="b3100-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b3100-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b3100-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3100-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b3100-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="b3100-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b3100-109">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="b3100-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="b3100-110">In dit onderwerp wordt beschreven hoe u Defender voor Eindpunt op Android kunt installeren, configureren, bijwerken en gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b3100-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="b3100-111">Het uitvoeren van andere endpointbeveiligingsproducten van derden naast Defender voor Eindpunt op Android kan waarschijnlijk prestatieproblemen en onvoorspelbare systeemfouten veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="b3100-111">Running other third-party endpoint protection products alongside Defender for Endpoint on Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="b3100-112">Microsoft Defender voor Eindpunt installeren op Android</span><span class="sxs-lookup"><span data-stu-id="b3100-112">How to install Microsoft Defender for Endpoint on Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="b3100-113">Vereisten</span><span class="sxs-lookup"><span data-stu-id="b3100-113">Prerequisites</span></span>

-   <span data-ttu-id="b3100-114">**Voor eindgebruikers**</span><span class="sxs-lookup"><span data-stu-id="b3100-114">**For end users**</span></span>

    -   <span data-ttu-id="b3100-115">Microsoft Defender for Endpoint-licentie die is toegewezen aan de eindgebruiker(s) van de app.</span><span class="sxs-lookup"><span data-stu-id="b3100-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="b3100-116">Zie [Microsoft Defender voor endpoint-licentievereisten](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="b3100-116">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="b3100-117">Intune-bedrijfsportal app kan worden gedownload van [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) en is beschikbaar op het Android-apparaat.</span><span class="sxs-lookup"><span data-stu-id="b3100-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="b3100-118">Bovendien kunnen apparaat(en) worden geregistreerd [via](/mem/intune/user-help/enroll-device-android-company-portal) de app Intune-bedrijfsportal om intune-beleid voor apparaat compliance af te dwingen.</span><span class="sxs-lookup"><span data-stu-id="b3100-118">Additionally, device(s) can be [enrolled](/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="b3100-119">Hiervoor moet aan de eindgebruiker een licentie Microsoft Intune toegewezen.</span><span class="sxs-lookup"><span data-stu-id="b3100-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="b3100-120">Zie Licenties toewijzen aan gebruikers voor meer informatie over het toewijzen van [licenties.](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="b3100-120">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="b3100-121">**Voor beheerders**</span><span class="sxs-lookup"><span data-stu-id="b3100-121">**For Administrators**</span></span>

    -   <span data-ttu-id="b3100-122">Toegang tot de Microsoft Defender-beveiligingscentrum portal.</span><span class="sxs-lookup"><span data-stu-id="b3100-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="b3100-123">Microsoft Intune is de enige ondersteunde MDM-oplossing (Mobile Device Management) voor de implementatie van Microsoft Defender voor Eindpunt op Android.</span><span class="sxs-lookup"><span data-stu-id="b3100-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on Android.</span></span> <span data-ttu-id="b3100-124">Momenteel worden alleen geregistreerde apparaten ondersteund voor het afdwingen van Defender voor Eindpunt op android-gerelateerde apparaat compliancebeleid in Intune.</span><span class="sxs-lookup"><span data-stu-id="b3100-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint on Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="b3100-125">Access [Microsoft Endpoint Manager beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431), om de app te implementeren voor geregistreerde gebruikersgroepen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b3100-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>
        
### <a name="network-requirements"></a><span data-ttu-id="b3100-126">Netwerkvereisten</span><span class="sxs-lookup"><span data-stu-id="b3100-126">Network Requirements</span></span>

- <span data-ttu-id="b3100-127">Als Microsoft Defender voor Eindpunt op Android werkt wanneer deze is verbonden met een netwerk, moet de firewall/proxy worden geconfigureerd om toegang tot URL's van [de Microsoft Defender-service](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)voor eindpunten in te stellen.</span><span class="sxs-lookup"><span data-stu-id="b3100-127">For Microsoft Defender for Endpoint on Android to function when connected to a network the firewall/proxy will need to be configured to [enable access to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="b3100-128">Systeemvereisten</span><span class="sxs-lookup"><span data-stu-id="b3100-128">System Requirements</span></span>

-   <span data-ttu-id="b3100-129">Mobiele telefoons met Android 6.0 en hoger.</span><span class="sxs-lookup"><span data-stu-id="b3100-129">Mobile phones running Android 6.0 and above.</span></span> <span data-ttu-id="b3100-130">**Tablets en andere mobiele apparaten met Android worden momenteel niet ondersteund.**</span><span class="sxs-lookup"><span data-stu-id="b3100-130">**Tablets and other mobile devices running Android are not currently supported.**</span></span> 

-   <span data-ttu-id="b3100-131">Intune-bedrijfsportal app wordt gedownload van [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) en geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="b3100-131">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="b3100-132">Apparaatinschrijving is vereist om intune-beleid voor apparaat compliance af te dwingen.</span><span class="sxs-lookup"><span data-stu-id="b3100-132">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="b3100-133">Installatie-instructies</span><span class="sxs-lookup"><span data-stu-id="b3100-133">Installation instructions</span></span>

<span data-ttu-id="b3100-134">Microsoft Defender voor Eindpunt op Android ondersteunt installatie op beide modi van geregistreerde apparaten, de oudere apparaatbeheerder en Android Enterprise-modi.</span><span class="sxs-lookup"><span data-stu-id="b3100-134">Microsoft Defender for Endpoint on Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="b3100-135">**Op dit moment worden apparaten met een persoonlijk eigendom met werkprofiel en volledig beheerde gebruikersapparaatinschrijvingen van bedrijven ondersteund in Android Enterprise. Ondersteuning voor andere Android Enterprise-modi wordt aangekondigd wanneer u klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="b3100-135">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrollments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="b3100-136">De implementatie van Microsoft Defender voor Eindpunt op Android is via Microsoft Intune (MDM).</span><span class="sxs-lookup"><span data-stu-id="b3100-136">Deployment of Microsoft Defender for Endpoint on Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="b3100-137">Zie Microsoft Defender voor Eindpunt implementeren op Android met Microsoft Intune voor [meer Microsoft Intune.](android-intune.md)</span><span class="sxs-lookup"><span data-stu-id="b3100-137">For more information, see [Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="b3100-138">**Microsoft Defender voor Eindpunt voor Android is nu beschikbaar op [Google Play.](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span><span class="sxs-lookup"><span data-stu-id="b3100-138">**Microsoft Defender for Endpoint on Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="b3100-139">U kunt verbinding maken met Google Play vanuit Intune om microsoft Defender voor eindpunt-app te implementeren, in de verschillende registratiemodi voor Apparaatbeheerder en Android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b3100-139">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="b3100-140">Microsoft Defender configureren voor Eindpunt op Android</span><span class="sxs-lookup"><span data-stu-id="b3100-140">How to Configure Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="b3100-141">Richtlijnen voor het configureren van Microsoft Defender voor Endpoint voor Android-functies zijn beschikbaar in Microsoft Defender voor eindpunt [configureren op Android-functies.](android-configure.md)</span><span class="sxs-lookup"><span data-stu-id="b3100-141">Guidance on how to configure Microsoft Defender for Endpoint on Android features is available in [Configure Microsoft Defender for Endpoint on Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="b3100-142">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b3100-142">Related topics</span></span>
- [<span data-ttu-id="b3100-143">Microsoft Defender voor Eindpunt op Android implementeren via Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b3100-143">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="b3100-144">Microsoft Defender voor Eindpunt in Android-functies configureren</span><span class="sxs-lookup"><span data-stu-id="b3100-144">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)

