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
ms.openlocfilehash: b4c2d586cd23a346db1bcebf891689ff648b639b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844704"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="fc8eb-104">Microsoft Defender voor Eindpunt op iOS</span><span class="sxs-lookup"><span data-stu-id="fc8eb-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fc8eb-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="fc8eb-105">**Applies to:**</span></span>
- [<span data-ttu-id="fc8eb-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="fc8eb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fc8eb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc8eb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fc8eb-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="fc8eb-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fc8eb-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="fc8eb-110">**Microsoft Defender voor Eindpunt op iOS** biedt bescherming tegen phishing en onveilige netwerkverbindingen van websites, e-mailberichten en apps.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-110">**Microsoft Defender for Endpoint on iOS** will offer protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="fc8eb-111">Alle waarschuwingen zijn beschikbaar via één deelvenster glas in de Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="fc8eb-112">De portal biedt beveiligingsteams een gecentraliseerde weergave van bedreigingen op iOS-apparaten, samen met andere platforms.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="fc8eb-113">Het uitvoeren van andere endpointbeveiligingsproducten van derden naast Defender voor Eindpunt in iOS kan waarschijnlijk prestatieproblemen en onvoorspelbare systeemfouten veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="fc8eb-114">Vereisten</span><span class="sxs-lookup"><span data-stu-id="fc8eb-114">Pre-requisites</span></span>

<span data-ttu-id="fc8eb-115">**Voor eindgebruikers**</span><span class="sxs-lookup"><span data-stu-id="fc8eb-115">**For End Users**</span></span>

- <span data-ttu-id="fc8eb-116">Microsoft Defender for Endpoint-licentie die is toegewezen aan de eindgebruiker(s) van de app.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="fc8eb-117">Zie [Microsoft Defender voor endpoint-licentievereisten](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="fc8eb-117">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="fc8eb-118">Apparaat(en) zijn [geregistreerd via de](/mem/intune/user-help/enroll-your-device-in-intune-ios) Intune-bedrijfsportal app om intune-beleid voor apparaat compliance af te dwingen.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-118">Device(s) are [enrolled](/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="fc8eb-119">Hiervoor moet aan de eindgebruiker een licentie Microsoft Intune toegewezen.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="fc8eb-120">Intune-bedrijfsportal app kan worden gedownload vanuit de [Apple App Store.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="fc8eb-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="fc8eb-121">Apple staat niet toe dat gebruikers worden omgeleid om andere apps te downloaden uit de App Store en daarom moet deze stap worden uitgevoerd door de gebruiker voordat deze wordt onboarding naar de Microsoft Defender voor Endpoint-app.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="fc8eb-122">Zie Licenties toewijzen aan gebruikers voor meer informatie over het toewijzen van [licenties.](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="fc8eb-122">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="fc8eb-123">**Voor beheerders**</span><span class="sxs-lookup"><span data-stu-id="fc8eb-123">**For Administrators**</span></span>

- <span data-ttu-id="fc8eb-124">Toegang tot de Microsoft Defender-beveiligingscentrum portal.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-124">Access to the Microsoft Defender Security Center portal.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fc8eb-125">Microsoft Intune is de enige ondersteunde UEM-oplossing (Unified Endpoint Management) voor het implementeren van Microsoft Defender voor Eindpunt en het afdwingen van Defender voor endpoint-gerelateerde beleidsregels voor apparaat compliance in Intune.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-125">Microsoft Intune is the only supported Unified Endpoint Management (UEM) solution for deploying Microsoft Defender for Endpoint and enforcing Defender for Endpoint related device compliance policies in Intune.</span></span>

- <span data-ttu-id="fc8eb-126">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-126">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

<span data-ttu-id="fc8eb-127">**Systeemvereisten**</span><span class="sxs-lookup"><span data-stu-id="fc8eb-127">**System Requirements**</span></span>

- <span data-ttu-id="fc8eb-128">iOS-apparaten met iOS 11.0 en hoger.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-128">iOS devices running iOS 11.0 and above.</span></span> <span data-ttu-id="fc8eb-129">iPad apparaten worden officieel ondersteund vanaf versie 1.1.15010101.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-129">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="fc8eb-130">Apparaat is geregistreerd met de [Intune-bedrijfsportal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span><span class="sxs-lookup"><span data-stu-id="fc8eb-130">Device is enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="fc8eb-131">Installatie-instructies</span><span class="sxs-lookup"><span data-stu-id="fc8eb-131">Installation instructions</span></span>

<span data-ttu-id="fc8eb-132">De implementatie van Microsoft Defender voor Eindpunt in iOS is via Microsoft Intune (MDM) en zowel gecontroleerde als niet-bewaakte apparaten worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-132">Deployment of Microsoft Defender for Endpoint on iOS is via Microsoft Intune (MDM) and both supervised and unsupervised devices are supported.</span></span> <span data-ttu-id="fc8eb-133">Eindgebruikers kunnen de app ook rechtstreeks installeren vanuit de [Apple App Store.](https://aka.ms/mdatpiosappstore)</span><span class="sxs-lookup"><span data-stu-id="fc8eb-133">End-users can also directly install the app from the [Apple app store](https://aka.ms/mdatpiosappstore).</span></span>
<span data-ttu-id="fc8eb-134">Zie Microsoft Defender voor eindpunten implementeren in [iOS voor meer informatie.](ios-install.md)</span><span class="sxs-lookup"><span data-stu-id="fc8eb-134">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="fc8eb-135">Resources</span><span class="sxs-lookup"><span data-stu-id="fc8eb-135">Resources</span></span>

- <span data-ttu-id="fc8eb-136">Blijf op de hoogte van aanstaande releases door naar Nieuw in Microsoft Defender voor Eindpunt op [iOS](ios-whatsnew.md) of onze blog te [gaan.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)</span><span class="sxs-lookup"><span data-stu-id="fc8eb-136">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="fc8eb-137">Feedback geven via een in-app feedbacksysteem of via [de SecOps-portal](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="fc8eb-137">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="fc8eb-138">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="fc8eb-138">Next steps</span></span>

- [<span data-ttu-id="fc8eb-139">Microsoft Defender voor eindpunt implementeren in iOS</span><span class="sxs-lookup"><span data-stu-id="fc8eb-139">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="fc8eb-140">Microsoft Defender voor eindpunt configureren voor iOS-functies</span><span class="sxs-lookup"><span data-stu-id="fc8eb-140">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
