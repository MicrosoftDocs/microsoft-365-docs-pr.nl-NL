---
title: Apparaten in gebruik nemen bij Microsoft Defender voor Eindpunt
description: Houd onboarding bij van door Intune beheerde apparaten naar Microsoft Defender voor Eindpunt en verhoog de onboardingsnelheid.
keywords: onboard, Intune management, MDATP, WDATP, Microsoft Defender, Windows Defender, advanced threat protection, configuration management
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 09ca9fb466efd7764f7459a4754cfb30c8100bdb
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904138"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="856ac-104">Apparaten in gebruik nemen bij Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="856ac-104">Get devices onboarded to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="856ac-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="856ac-105">**Applies to:**</span></span>
- [<span data-ttu-id="856ac-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="856ac-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="856ac-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="856ac-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="856ac-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="856ac-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="856ac-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="856ac-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="856ac-110">Elk onboarded apparaat voegt een extra EDR-sensor (EndPoint Detection and Response) toe en vergroot de zichtbaarheid van inbreukactiviteiten in uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="856ac-110">Each onboarded device adds an additional endpoint detection and response (EDR) sensor and increases visibility over breach activity in your network.</span></span> <span data-ttu-id="856ac-111">Onboarding zorgt er ook voor dat een apparaat kan worden gecontroleerd op kwetsbare onderdelen, evenals beveiligingsconfiguratieproblemen en kritieke herstelacties kan ontvangen tijdens aanvallen.</span><span class="sxs-lookup"><span data-stu-id="856ac-111">Onboarding also ensures that a device can be checked for vulnerable components as well security configuration issues and can receive critical remediation actions during attacks.</span></span>

<span data-ttu-id="856ac-112">Voordat u onboarding van apparaten kunt bijhouden en beheren:</span><span class="sxs-lookup"><span data-stu-id="856ac-112">Before you can track and manage onboarding of devices:</span></span>
- [<span data-ttu-id="856ac-113">Uw apparaten registreren voor Intune-beheer</span><span class="sxs-lookup"><span data-stu-id="856ac-113">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="856ac-114">Zorg ervoor dat u de benodigde machtigingen hebt</span><span class="sxs-lookup"><span data-stu-id="856ac-114">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="discover-and-track-unprotected-devices"></a><span data-ttu-id="856ac-115">Niet-beveiligde apparaten ontdekken en bijhouden</span><span class="sxs-lookup"><span data-stu-id="856ac-115">Discover and track unprotected devices</span></span>

<span data-ttu-id="856ac-116">De **Onboarding-kaart** biedt een overzicht op hoog niveau van uw onboardingsnelheid door het aantal Windows 10-apparaten dat daadwerkelijk is ge onboarded bij Defender for Endpoint te vergelijken met het totale aantal door Intune beheerde Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="856ac-116">The **Onboarding** card provides a high-level overview of your onboarding rate by comparing the number of Windows 10 devices that have actually onboarded to Defender for Endpoint against the total number of Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="856ac-117">![Onboarding-kaart voor apparaatconfiguratiebeheer](images/secconmgmt_onboarding_card.png)</span><span class="sxs-lookup"><span data-stu-id="856ac-117">![Device configuration management Onboarding card](images/secconmgmt_onboarding_card.png)</span></span><br>
<span data-ttu-id="856ac-118">*Kaart met onboarded-apparaten in vergelijking met het totale aantal door Intune beheerde Windows 10-apparaten*</span><span class="sxs-lookup"><span data-stu-id="856ac-118">*Card showing onboarded devices compared to the total number of Intune-managed Windows 10 device*</span></span>

>[!NOTE]
><span data-ttu-id="856ac-119">Als u Security Center Configuration Manager, het onboarding-script of andere onboarding-methoden hebt gebruikt die geen Intune-profielen gebruiken, kunnen er gegevensverschillen zijn.</span><span class="sxs-lookup"><span data-stu-id="856ac-119">If you used Security Center Configuration Manager, the onboarding script, or other onboarding methods that don’t use Intune profiles, you might encounter data discrepancies.</span></span> <span data-ttu-id="856ac-120">Als u deze verschillen wilt oplossen, maakt u een bijbehorend Intune-configuratieprofiel voor Defender voor endpoint-onboarding en wijst u dat profiel toe aan uw apparaten.</span><span class="sxs-lookup"><span data-stu-id="856ac-120">To resolve these discrepancies, create a corresponding Intune configuration profile for Defender for Endpoint onboarding and assign that profile to your devices.</span></span>

## <a name="onboard-more-devices-with-intune-profiles"></a><span data-ttu-id="856ac-121">Meer apparaten aan boord met Intune-profielen</span><span class="sxs-lookup"><span data-stu-id="856ac-121">Onboard more devices with Intune profiles</span></span>

<span data-ttu-id="856ac-122">Defender voor Eindpunt biedt verschillende handige opties voor [het onboarden van Windows 10-apparaten.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="856ac-122">Defender for Endpoint provides several convenient options for [onboarding Windows 10 devices](onboard-configure.md).</span></span> <span data-ttu-id="856ac-123">Voor door Intune beheerde apparaten kunt u echter Intune-profielen gebruiken om de Defender for Endpoint-sensor eenvoudig te implementeren om apparaten te selecteren, zodat deze apparaten effectief aan de service worden ge onboardd.</span><span class="sxs-lookup"><span data-stu-id="856ac-123">For Intune-managed devices, however, you can leverage Intune profiles to conveniently deploy the Defender for Endpoint sensor to select devices, effectively onboarding these devices to the service.</span></span>

<span data-ttu-id="856ac-124">Selecteer op **de Onboarding-kaart** **Meer apparaten onboarden om** een profiel op Intune te maken en toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="856ac-124">From the **Onboarding** card, select **Onboard more devices** to create and assign a profile on Intune.</span></span> <span data-ttu-id="856ac-125">De koppeling brengt u naar de pagina apparaat compliance op Intune, die een vergelijkbaar overzicht biedt van uw onboarding-status.</span><span class="sxs-lookup"><span data-stu-id="856ac-125">The link takes you to the device compliance page on Intune, which provides a similar overview of your onboarding state.</span></span>

<span data-ttu-id="856ac-126">![Microsoft Defender for Endpoint device compliance page on Intune device management](images/secconmgmt_onboarding_1deviceconfprofile.png)</span><span class="sxs-lookup"><span data-stu-id="856ac-126">![Microsoft Defender for Endpoint device compliance page on Intune device management](images/secconmgmt_onboarding_1deviceconfprofile.png)</span></span><br>
   <span data-ttu-id="856ac-127">*Microsoft Defender for Endpoint device compliance page on Intune device management*</span><span class="sxs-lookup"><span data-stu-id="856ac-127">*Microsoft Defender for Endpoint device compliance page on Intune device management*</span></span>

>[!TIP]
><span data-ttu-id="856ac-128">U kunt ook navigeren naar de compliancepagina van Defender voor eindpunten in de [Microsoft Azure-portal](https://portal.azure.com/) van **Alle services > Intune > Apparaat compliance > Microsoft Defender ATP.**</span><span class="sxs-lookup"><span data-stu-id="856ac-128">Alternatively, you can navigate to the Defender for Endpoint onboarding compliance page in the [Microsoft Azure portal](https://portal.azure.com/) from **All services > Intune > Device compliance > Microsoft Defender ATP**.</span></span>

>[!NOTE]
> <span data-ttu-id="856ac-129">Als u de meest recente apparaatgegevens wilt bekijken, klikt u op Lijst met **apparaten zonder ATP-sensor.**</span><span class="sxs-lookup"><span data-stu-id="856ac-129">If you want to view the most up-to-date device data, click on **List of devices without ATP sensor**.</span></span>

<span data-ttu-id="856ac-130">Maak op de pagina apparaat compliance een configuratieprofiel speciaal voor de implementatie van de Defender for Endpoint-sensor en wijs dat profiel toe aan de apparaten die u wilt onboarden.</span><span class="sxs-lookup"><span data-stu-id="856ac-130">From the device compliance page, create a configuration profile specifically for the deployment of the Defender for Endpoint sensor and assign that profile to the devices you want to onboard.</span></span> <span data-ttu-id="856ac-131">U kunt dit doen door het volgende te doen:</span><span class="sxs-lookup"><span data-stu-id="856ac-131">To do this, you can either:</span></span>

- <span data-ttu-id="856ac-132">Selecteer **Een apparaatconfiguratieprofiel maken om ATP-sensor** te configureren om te beginnen met een vooraf gedefinieerd apparaatconfiguratieprofiel.</span><span class="sxs-lookup"><span data-stu-id="856ac-132">Select **Create a device configuration profile to configure ATP sensor** to start with a predefined device configuration profile.</span></span>
- <span data-ttu-id="856ac-133">Maak het apparaatconfiguratieprofiel vanaf het begin.</span><span class="sxs-lookup"><span data-stu-id="856ac-133">Create the device configuration profile from scratch.</span></span>

<span data-ttu-id="856ac-134">Lees voor meer informatie [over het gebruik van intune-apparaatconfiguratieprofielen voor onboard-apparaten naar Defender voor Eindpunt.](https://docs.microsoft.com/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile)</span><span class="sxs-lookup"><span data-stu-id="856ac-134">For more information, [read about using Intune device configuration profiles to onboard devices to Defender for Endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile).</span></span>

><span data-ttu-id="856ac-135">Wilt u Microsoft Defender ATP ervaren?</span><span class="sxs-lookup"><span data-stu-id="856ac-135">Want to experience Microsoft Defender ATP?</span></span> [<span data-ttu-id="856ac-136">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="856ac-136">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="856ac-137">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="856ac-137">Related topics</span></span>
- [<span data-ttu-id="856ac-138">Controleren of uw apparaten juist zijn geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="856ac-138">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="856ac-139">Naleving van de beveiligingslijn defender voor eindpunt verhogen</span><span class="sxs-lookup"><span data-stu-id="856ac-139">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
- [<span data-ttu-id="856ac-140">Asr-regelimplementatie en -detecties optimaliseren</span><span class="sxs-lookup"><span data-stu-id="856ac-140">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
