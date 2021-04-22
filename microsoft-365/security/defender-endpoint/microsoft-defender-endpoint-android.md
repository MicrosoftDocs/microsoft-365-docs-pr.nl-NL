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
ms.openlocfilehash: 35a43aa7bfcd9ed8c83d10c2ec44a974b03bca72
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935567"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="2a7d6-104">Microsoft Defender voor Eindpunt op Android</span><span class="sxs-lookup"><span data-stu-id="2a7d6-104">Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2a7d6-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2a7d6-105">**Applies to:**</span></span>
- [<span data-ttu-id="2a7d6-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="2a7d6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2a7d6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a7d6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2a7d6-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="2a7d6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2a7d6-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="2a7d6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="2a7d6-110">In dit onderwerp wordt beschreven hoe u Defender voor Eindpunt op Android kunt installeren, configureren, bijwerken en gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2a7d6-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="2a7d6-111">Het uitvoeren van andere endpointbeveiligingsproducten van derden naast Defender voor Eindpunt op Android kan waarschijnlijk prestatieproblemen en onvoorspelbare systeemfouten veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="2a7d6-111">Running other third-party endpoint protection products alongside Defender for Endpoint on Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="2a7d6-112">Microsoft Defender voor Eindpunt installeren op Android</span><span class="sxs-lookup"><span data-stu-id="2a7d6-112">How to install Microsoft Defender for Endpoint on Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="2a7d6-113">Vereisten</span><span class="sxs-lookup"><span data-stu-id="2a7d6-113">Prerequisites</span></span>

-   <span data-ttu-id="2a7d6-114">**Voor eindgebruikers**</span><span class="sxs-lookup"><span data-stu-id="2a7d6-114">**For end users**</span></span>

    -   <span data-ttu-id="2a7d6-115">Microsoft Defender for Endpoint-licentie die is toegewezen aan de eindgebruiker(s) van de app.</span><span class="sxs-lookup"><span data-stu-id="2a7d6-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="2a7d6-116">Zie [Microsoft Defender voor endpoint-licentievereisten](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="2a7d6-116">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="2a7d6-117">De Intune Company Portal-app kan worden gedownload van [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) en is beschikbaar op het Android-apparaat.</span><span class="sxs-lookup"><span data-stu-id="2a7d6-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="2a7d6-118">Bovendien kunnen apparaat(en) worden geregistreerd [via](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) de Intune Company Portal-app om intune-beleid voor apparaat compliance af te dwingen.</span><span class="sxs-lookup"><span data-stu-id="2a7d6-118">Additionally, device(s) can be [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="2a7d6-119">Hiervoor moet aan de eindgebruiker een Microsoft Intune-licentie worden toegewezen.</span><span class="sxs-lookup"><span data-stu-id="2a7d6-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="2a7d6-120">Zie Licenties toewijzen aan gebruikers voor meer informatie over het toewijzen van [licenties.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="2a7d6-120">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="2a7d6-121">**Voor beheerders**</span><span class="sxs-lookup"><span data-stu-id="2a7d6-121">**For Administrators**</span></span>

    -   <span data-ttu-id="2a7d6-122">Toegang tot de microsoft Defender-beveiligingscentrumportal.</span><span class="sxs-lookup"><span data-stu-id="2a7d6-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="2a7d6-123">Microsoft Intune is de enige ondersteunde MDM-oplossing (Mobile Device Management) voor het implementeren van Microsoft Defender voor Eindpunt op Android.</span><span class="sxs-lookup"><span data-stu-id="2a7d6-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on Android.</span></span> <span data-ttu-id="2a7d6-124">Momenteel worden alleen geregistreerde apparaten ondersteund voor het afdwingen van Defender voor Eindpunt op android-gerelateerde apparaat compliancebeleid in Intune.</span><span class="sxs-lookup"><span data-stu-id="2a7d6-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint on Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="2a7d6-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span><span class="sxs-lookup"><span data-stu-id="2a7d6-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

### <a name="system-requirements"></a><span data-ttu-id="2a7d6-126">Systeemvereisten</span><span class="sxs-lookup"><span data-stu-id="2a7d6-126">System Requirements</span></span>

-   <span data-ttu-id="2a7d6-127">Android-apparaten met Android 6.0 en hoger.</span><span class="sxs-lookup"><span data-stu-id="2a7d6-127">Android devices running Android 6.0 and above.</span></span>
-   <span data-ttu-id="2a7d6-128">De Intune Company Portal-app wordt gedownload van [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) en geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="2a7d6-128">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="2a7d6-129">Apparaatinschrijving is vereist om intune-beleid voor apparaat compliance af te dwingen.</span><span class="sxs-lookup"><span data-stu-id="2a7d6-129">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="2a7d6-130">Installatie-instructies</span><span class="sxs-lookup"><span data-stu-id="2a7d6-130">Installation instructions</span></span>

<span data-ttu-id="2a7d6-131">Microsoft Defender voor Eindpunt op Android ondersteunt installatie op beide modi van geregistreerde apparaten, de oudere apparaatbeheerder en Android Enterprise-modi.</span><span class="sxs-lookup"><span data-stu-id="2a7d6-131">Microsoft Defender for Endpoint on Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="2a7d6-132">**Op dit moment worden apparaten met een persoonlijk eigendom met werkprofiel en volledig beheerde gebruikersapparaatinschrijvingen van bedrijven ondersteund in Android Enterprise. Ondersteuning voor andere Android Enterprise-modi wordt aangekondigd wanneer u klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="2a7d6-132">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrollments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="2a7d6-133">De implementatie van Microsoft Defender voor Eindpunt op Android is via Microsoft Intune (MDM).</span><span class="sxs-lookup"><span data-stu-id="2a7d6-133">Deployment of Microsoft Defender for Endpoint on Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="2a7d6-134">Zie Microsoft Defender voor Eindpunt implementeren op [Android met Microsoft Intune](android-intune.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2a7d6-134">For more information, see [Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="2a7d6-135">**Microsoft Defender voor Eindpunt voor Android is nu beschikbaar op [Google Play.](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span><span class="sxs-lookup"><span data-stu-id="2a7d6-135">**Microsoft Defender for Endpoint on Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="2a7d6-136">U kunt verbinding maken met Google Play vanuit Intune om microsoft Defender voor eindpunt-app te implementeren, in de verschillende registratiemodi voor Apparaatbeheerder en Android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2a7d6-136">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="2a7d6-137">Microsoft Defender configureren voor Eindpunt op Android</span><span class="sxs-lookup"><span data-stu-id="2a7d6-137">How to Configure Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="2a7d6-138">Richtlijnen voor het configureren van Microsoft Defender voor Endpoint voor Android-functies zijn beschikbaar in Microsoft Defender voor eindpunt [configureren op Android-functies.](android-configure.md)</span><span class="sxs-lookup"><span data-stu-id="2a7d6-138">Guidance on how to configure Microsoft Defender for Endpoint on Android features is available in [Configure Microsoft Defender for Endpoint on Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="2a7d6-139">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="2a7d6-139">Related topics</span></span>
- [<span data-ttu-id="2a7d6-140">Microsoft Defender voor Eindpunt op Android implementeren via Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2a7d6-140">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="2a7d6-141">Microsoft Defender voor Eindpunt in Android-functies configureren</span><span class="sxs-lookup"><span data-stu-id="2a7d6-141">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)

