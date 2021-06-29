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
ms.openlocfilehash: cbe2fb39221bd9907a3d690503a392edb019d61b
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194851"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="95629-104">Microsoft Defender voor Eindpunt op iOS</span><span class="sxs-lookup"><span data-stu-id="95629-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="95629-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="95629-105">**Applies to:**</span></span>
- [<span data-ttu-id="95629-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="95629-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="95629-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95629-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="95629-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="95629-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="95629-109">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="95629-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="95629-110">**Microsoft Defender voor Eindpunt op iOS** biedt bescherming tegen phishing en onveilige netwerkverbindingen van websites, e-mailberichten en apps.</span><span class="sxs-lookup"><span data-stu-id="95629-110">**Microsoft Defender for Endpoint on iOS** offers protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="95629-111">Alle waarschuwingen zijn beschikbaar via één deelvenster glas in de Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="95629-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="95629-112">De portal biedt beveiligingsteams een gecentraliseerde weergave van bedreigingen op iOS-apparaten, samen met andere platforms.</span><span class="sxs-lookup"><span data-stu-id="95629-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="95629-113">Het uitvoeren van andere endpointbeveiligingsproducten van derden naast Defender voor Eindpunt in iOS kan waarschijnlijk prestatieproblemen en onvoorspelbare systeemfouten veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="95629-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="95629-114">Voorwaarden</span><span class="sxs-lookup"><span data-stu-id="95629-114">Pre-requisites</span></span>

<span data-ttu-id="95629-115">**Voor eindgebruikers**</span><span class="sxs-lookup"><span data-stu-id="95629-115">**For End Users**</span></span>

- <span data-ttu-id="95629-116">Microsoft Defender for Endpoint-licentie die is toegewezen aan de eindgebruiker(s) van de app.</span><span class="sxs-lookup"><span data-stu-id="95629-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="95629-117">Zie [Microsoft Defender voor endpoint-licentievereisten](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="95629-117">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="95629-118">**Voor geregistreerde apparaten:** Apparaten(en) zijn geregistreerd [via](/mem/intune/user-help/enroll-your-device-in-intune-ios) de Intune-bedrijfsportal app om intune-beleid voor apparaat compliance af te dwingen.</span><span class="sxs-lookup"><span data-stu-id="95629-118">**For enrolled devices**: Device(s) are [enrolled](/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="95629-119">Hiervoor moet aan de eindgebruiker een licentie Microsoft Intune toegewezen.</span><span class="sxs-lookup"><span data-stu-id="95629-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="95629-120">Intune-bedrijfsportal app kan worden gedownload vanuit de [Apple App Store.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="95629-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="95629-121">Apple staat niet toe dat gebruikers worden omgeleid om andere apps te downloaden uit de App Store en daarom moet deze stap worden uitgevoerd door de gebruiker voordat deze wordt onboarding naar de Microsoft Defender voor Endpoint-app.</span><span class="sxs-lookup"><span data-stu-id="95629-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="95629-122">**Voor niet-geregistreerde apparaten**: Apparaten(en) zijn geregistreerd bij Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="95629-122">**For unenrolled devices**: Device(s) are registered with Azure Active Directory.</span></span> <span data-ttu-id="95629-123">Hiervoor moet de eindgebruiker zijn aangemeld via de [Microsoft Authenticator app.](https://apps.apple.com/app/microsoft-authenticator/id983156458)</span><span class="sxs-lookup"><span data-stu-id="95629-123">This requires end user to be signed in through [Microsoft Authenticator app](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span></span>

- <span data-ttu-id="95629-124">Zie Licenties toewijzen aan gebruikers voor meer informatie over het toewijzen van [licenties.](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="95629-124">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="95629-125">**Voor beheerders**</span><span class="sxs-lookup"><span data-stu-id="95629-125">**For Administrators**</span></span>

- <span data-ttu-id="95629-126">Toegang tot de Microsoft Defender-beveiligingscentrum portal.</span><span class="sxs-lookup"><span data-stu-id="95629-126">Access to the Microsoft Defender Security Center portal.</span></span>

- <span data-ttu-id="95629-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span><span class="sxs-lookup"><span data-stu-id="95629-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

    > [!NOTE]
    > <span data-ttu-id="95629-128">Microsoft Intune is de enige ondersteunde UEM-oplossing (Unified Endpoint Management) voor het implementeren van Microsoft Defender voor Eindpunt en het afdwingen van Defender voor endpoint-gerelateerde beleidsregels voor apparaat compliance in Intune.</span><span class="sxs-lookup"><span data-stu-id="95629-128">Microsoft Intune is the only supported Unified Endpoint Management (UEM) solution for deploying Microsoft Defender for Endpoint and enforcing Defender for Endpoint related device compliance policies in Intune.</span></span>

<span data-ttu-id="95629-129">**Systeemvereisten**</span><span class="sxs-lookup"><span data-stu-id="95629-129">**System Requirements**</span></span>

- <span data-ttu-id="95629-130">iOS-apparaat met iOS 11.0 en hoger.</span><span class="sxs-lookup"><span data-stu-id="95629-130">iOS device running iOS 11.0 and above.</span></span> <span data-ttu-id="95629-131">iPad apparaten worden officieel ondersteund vanaf versie 1.1.15010101.</span><span class="sxs-lookup"><span data-stu-id="95629-131">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="95629-132">Apparaat is geregistreerd met de Intune-bedrijfsportal [app](https://apps.apple.com/us/app/intune-company-portal/id719171358) of geregistreerd bij Azure Active Directory via [Microsoft Authenticator.](https://apps.apple.com/app/microsoft-authenticator/id983156458)</span><span class="sxs-lookup"><span data-stu-id="95629-132">Device is either enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358) or registered with Azure Active Directory through [Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="95629-133">Installatie-instructies</span><span class="sxs-lookup"><span data-stu-id="95629-133">Installation instructions</span></span>

<span data-ttu-id="95629-134">Implementatie van Microsoft Defender voor Endpoint op iOS kan via Microsoft Endpoint Manager (MEM) en zowel gecontroleerde als niet-bewaakte apparaten worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="95629-134">Deployment of Microsoft Defender for Endpoint on iOS can be done via Microsoft Endpoint Manager (MEM) and both supervised and unsupervised devices are supported.</span></span> <span data-ttu-id="95629-135">Eindgebruikers kunnen de app ook rechtstreeks installeren vanuit de [Apple App Store.](https://aka.ms/mdatpiosappstore)</span><span class="sxs-lookup"><span data-stu-id="95629-135">End-users can also directly install the app from the [Apple app store](https://aka.ms/mdatpiosappstore).</span></span>
<span data-ttu-id="95629-136">Zie Microsoft Defender voor eindpunten implementeren in [iOS voor meer informatie.](ios-install.md)</span><span class="sxs-lookup"><span data-stu-id="95629-136">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="95629-137">Middelen</span><span class="sxs-lookup"><span data-stu-id="95629-137">Resources</span></span>

- <span data-ttu-id="95629-138">Blijf op de hoogte van aanstaande releases door naar Nieuw in Microsoft Defender voor Eindpunt op [iOS](ios-whatsnew.md) of onze blog te [gaan.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)</span><span class="sxs-lookup"><span data-stu-id="95629-138">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="95629-139">Feedback geven via een in-app feedbacksysteem of via [de SecOps-portal](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="95629-139">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="95629-140">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="95629-140">Next steps</span></span>

- [<span data-ttu-id="95629-141">Microsoft Defender voor eindpunt implementeren in iOS</span><span class="sxs-lookup"><span data-stu-id="95629-141">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="95629-142">Microsoft Defender voor eindpunt configureren voor iOS-functies</span><span class="sxs-lookup"><span data-stu-id="95629-142">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
