---
title: Microsoft Defender voor Eindpunt op iOS
ms.reviewer: ''
description: Beschrijft hoe u Microsoft Defender voor Eindpunt in iOS installeert en gebruikt
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, overview, installation, deploy, uninstallation, intune
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4a051742775c3d4e8b36bf0ba7a4fd2502763014
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694459"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="9c0e3-104">Microsoft Defender voor Eindpunt op iOS</span><span class="sxs-lookup"><span data-stu-id="9c0e3-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9c0e3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="9c0e3-105">**Applies to:**</span></span>
- [<span data-ttu-id="9c0e3-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="9c0e3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9c0e3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9c0e3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9c0e3-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="9c0e3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9c0e3-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="9c0e3-110">**Microsoft Defender voor Eindpunt op iOS** biedt bescherming tegen phishing en onveilige netwerkverbindingen van websites, e-mailberichten en apps.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-110">**Microsoft Defender for Endpoint on iOS** will offer protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="9c0e3-111">Alle waarschuwingen zijn beschikbaar via één deelvenster glas in de Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="9c0e3-112">De portal biedt beveiligingsteams een gecentraliseerde weergave van bedreigingen op iOS-apparaten, samen met andere platforms.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="9c0e3-113">Het uitvoeren van andere endpointbeveiligingsproducten van derden naast Defender voor Eindpunt in iOS kan waarschijnlijk prestatieproblemen en onvoorspelbare systeemfouten veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="9c0e3-114">Vereisten</span><span class="sxs-lookup"><span data-stu-id="9c0e3-114">Pre-requisites</span></span>

<span data-ttu-id="9c0e3-115">**Voor eindgebruikers**</span><span class="sxs-lookup"><span data-stu-id="9c0e3-115">**For End Users**</span></span>

- <span data-ttu-id="9c0e3-116">Microsoft Defender for Endpoint-licentie die is toegewezen aan de eindgebruiker(s) van de app.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="9c0e3-117">Zie [Microsoft Defender voor endpoint-licentievereisten](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="9c0e3-117">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="9c0e3-118">Apparaat(en) zijn [geregistreerd via de](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) Intune-bedrijfsportal app om intune-beleid voor apparaat compliance af te dwingen.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-118">Device(s) are [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="9c0e3-119">Hiervoor moet aan de eindgebruiker een licentie Microsoft Intune toegewezen.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="9c0e3-120">Intune-bedrijfsportal app kan worden gedownload vanuit de [Apple App Store.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="9c0e3-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="9c0e3-121">Apple staat niet toe dat gebruikers worden omgeleid om andere apps te downloaden uit de App Store en daarom moet deze stap worden uitgevoerd door de gebruiker voordat deze wordt onboarding naar de Microsoft Defender voor Endpoint-app.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="9c0e3-122">Zie Licenties toewijzen aan gebruikers voor meer informatie over het toewijzen van [licenties.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="9c0e3-122">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="9c0e3-123">**Voor beheerders**</span><span class="sxs-lookup"><span data-stu-id="9c0e3-123">**For Administrators**</span></span>

- <span data-ttu-id="9c0e3-124">Toegang tot de Microsoft Defender-beveiligingscentrum portal.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-124">Access to the Microsoft Defender Security Center portal.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9c0e3-125">Microsoft Intune is de enige ondersteunde MDM-oplossing (Mobile Device Management) voor de implementatie van Microsoft Defender voor Eindpunt in iOS.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-125">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on iOS.</span></span> <span data-ttu-id="9c0e3-126">Momenteel worden alleen geregistreerde apparaten ondersteund voor het afdwingen van Defender voor Eindpunt op iOS-beleid voor apparaat compliance in Intune.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-126">Currently only enrolled devices are supported for enforcing Defender for Endpoint on iOS related device compliance policies in Intune.</span></span>

- <span data-ttu-id="9c0e3-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

<span data-ttu-id="9c0e3-128">**Systeemvereisten**</span><span class="sxs-lookup"><span data-stu-id="9c0e3-128">**System Requirements**</span></span>

- <span data-ttu-id="9c0e3-129">iOS-apparaten met iOS 11.0 en hoger.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-129">iOS devices running iOS 11.0 and above.</span></span> <span data-ttu-id="9c0e3-130">iPad apparaten worden officieel ondersteund vanaf versie 1.1.15010101.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-130">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="9c0e3-131">Apparaat is geregistreerd met de [Intune-bedrijfsportal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span><span class="sxs-lookup"><span data-stu-id="9c0e3-131">Device is enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>

> [!NOTE]
> <span data-ttu-id="9c0e3-132">**Microsoft Defender voor Eindpunt voor iOS is beschikbaar in [de Apple App Store.](https://aka.ms/mdatpiosappstore)**</span><span class="sxs-lookup"><span data-stu-id="9c0e3-132">**Microsoft Defender for Endpoint on iOS is available on [Apple App Store](https://aka.ms/mdatpiosappstore).**</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="9c0e3-133">Installatie-instructies</span><span class="sxs-lookup"><span data-stu-id="9c0e3-133">Installation instructions</span></span>

<span data-ttu-id="9c0e3-134">De implementatie van Microsoft Defender voor Eindpunt in iOS is via Microsoft Intune (MDM) en zowel gecontroleerde als niet-bewaakte apparaten worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="9c0e3-134">Deployment of Microsoft Defender for Endpoint on iOS is via Microsoft Intune (MDM) and both supervised and unsupervised devices are supported.</span></span>
<span data-ttu-id="9c0e3-135">Zie Microsoft Defender voor eindpunten implementeren in [iOS voor meer informatie.](ios-install.md)</span><span class="sxs-lookup"><span data-stu-id="9c0e3-135">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="9c0e3-136">Resources</span><span class="sxs-lookup"><span data-stu-id="9c0e3-136">Resources</span></span>

- <span data-ttu-id="9c0e3-137">Blijf op de hoogte van aanstaande releases door naar Nieuw in Microsoft Defender voor Eindpunt op [iOS](ios-whatsnew.md) of onze blog te [gaan.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)</span><span class="sxs-lookup"><span data-stu-id="9c0e3-137">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="9c0e3-138">Feedback geven via een in-app feedbacksysteem of via [de SecOps-portal](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="9c0e3-138">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="9c0e3-139">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="9c0e3-139">Next steps</span></span>

- [<span data-ttu-id="9c0e3-140">Microsoft Defender voor eindpunt implementeren in iOS</span><span class="sxs-lookup"><span data-stu-id="9c0e3-140">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="9c0e3-141">Microsoft Defender voor eindpunt configureren voor iOS-functies</span><span class="sxs-lookup"><span data-stu-id="9c0e3-141">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
