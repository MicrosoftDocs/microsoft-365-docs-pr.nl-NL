---
title: Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management
description: Gebruik hulpprogramma's voor mobiel apparaatbeheer om het configuratiepakket op apparaten te implementeren, zodat ze zijn aan boord van de service.
keywords: onboard devices using mdm, device management, onboard Windows ATP devices, onboard Microsoft Defender for Endpoint devices, mdm
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f3042ef9ced11ebc5439308d2781528d5267975f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893611"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="5120f-104">Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="5120f-104">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5120f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="5120f-105">**Applies to:**</span></span>
- [<span data-ttu-id="5120f-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="5120f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5120f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5120f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="5120f-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="5120f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5120f-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="5120f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

<span data-ttu-id="5120f-110">U kunt MDM-oplossingen (Mobile Device Management) gebruiken om apparaten te configureren.</span><span class="sxs-lookup"><span data-stu-id="5120f-110">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="5120f-111">Defender voor Eindpunt ondersteunt MDM's door OMA-URIs om beleid te maken voor het beheren van apparaten.</span><span class="sxs-lookup"><span data-stu-id="5120f-111">Defender for Endpoint supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>

<span data-ttu-id="5120f-112">Zie [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection CSP and WindowsAdvancedThreatProtection DDF file (WindowsAdvancedThreatProtection DDF-bestand)](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)voor meer informatie over het gebruik van Defender voor Endpoint CSP.</span><span class="sxs-lookup"><span data-stu-id="5120f-112">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5120f-113">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="5120f-113">Before you begin</span></span>
<span data-ttu-id="5120f-114">Als u Microsoft Intune gebruikt, moet het apparaat MDM zijn geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="5120f-114">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="5120f-115">Anders worden de instellingen niet toegepast.</span><span class="sxs-lookup"><span data-stu-id="5120f-115">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="5120f-116">Zie [Apparaatinschrijving (Microsoft Intune) voor](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)meer informatie over het inschakelen van MDM met Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="5120f-116">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="5120f-117">Onboard-apparaten met Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5120f-117">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="5120f-118">[![Afbeelding van het PDF-bestand met onboarding-apparaten voor Defender voor Eindpunt met Microsoft Intune ](images/onboard-intune.png)](images/onboard-intune-big.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5120f-118">[![Image of the PDF showing onboarding devices to Defender for Endpoint using Microsoft Intune](images/onboard-intune.png) ](images/onboard-intune-big.png#lightbox)</span></span>

<span data-ttu-id="5120f-119">Bekijk het [PDF-bestand](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  of  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) om de verschillende paden te bekijken bij de implementatie van Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="5120f-119">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 

<span data-ttu-id="5120f-120">Volg de instructies van [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="5120f-120">Follow the instructions from [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

<span data-ttu-id="5120f-121">Zie [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection CSP and WindowsAdvancedThreatProtection DDF file (WindowsAdvancedThreatProtection DDF-bestand)](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)voor meer informatie over het gebruik van Defender voor Endpoint CSP.</span><span class="sxs-lookup"><span data-stu-id="5120f-121">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>


> [!NOTE]
> - <span data-ttu-id="5120f-122">Het **beleid Statusstatus voor onboarded-apparaten** gebruikt alleen-lezen eigenschappen en kan niet worden gesaneerd.</span><span class="sxs-lookup"><span data-stu-id="5120f-122">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>
> - <span data-ttu-id="5120f-123">Configuratie van de rapportagefrequentie voor diagnostische gegevens is alleen beschikbaar voor apparaten in Windows 10, versie 1703.</span><span class="sxs-lookup"><span data-stu-id="5120f-123">Configuration of diagnostic data reporting frequency is only available for devices on Windows 10, version 1703.</span></span>


>[!TIP]
> <span data-ttu-id="5120f-124">Nadat u het apparaat hebt onboarding, kunt u ervoor kiezen om een detectietest uit te voeren om te controleren of een apparaat correct is aan boord van de service.</span><span class="sxs-lookup"><span data-stu-id="5120f-124">After onboarding the device, you can choose to run a detection test to verify that a device is properly onboarded to the service.</span></span> <span data-ttu-id="5120f-125">Zie Een detectietest uitvoeren op een nieuw ingebouwde [Microsoft Defender voor eindpuntapparaat](run-detection-test.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5120f-125">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span>


<span data-ttu-id="5120f-126">Bekijk het [PDF-bestand](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  of  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) om de verschillende paden te bekijken bij de implementatie van Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="5120f-126">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Microsoft Defender for Endpoint.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="5120f-127">Apparaten offboarden en bewaken met behulp van hulpprogramma's voor mobiel apparaatbeheer</span><span class="sxs-lookup"><span data-stu-id="5120f-127">Offboard and monitor devices using Mobile Device Management tools</span></span>
<span data-ttu-id="5120f-128">Om veiligheidsredenen verloopt het pakket dat wordt gebruikt voor Offboard-apparaten 30 dagen na de datum waarop het is gedownload.</span><span class="sxs-lookup"><span data-stu-id="5120f-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="5120f-129">Verlopen offboarding-pakketten die naar een apparaat zijn verzonden, worden geweigerd.</span><span class="sxs-lookup"><span data-stu-id="5120f-129">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="5120f-130">Wanneer u een offboarding-pakket downloadt, wordt u op de hoogte gesteld van de vervaldatum van de pakketten en wordt het ook opgenomen in de pakketnaam.</span><span class="sxs-lookup"><span data-stu-id="5120f-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="5120f-131">Onboarding- en offboarding-beleid mag niet tegelijkertijd op hetzelfde apparaat worden geïmplementeerd, anders veroorzaakt dit onvoorspelbare botsingen.</span><span class="sxs-lookup"><span data-stu-id="5120f-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="5120f-132">Ontvang het offboarding-pakket van [het Microsoft Defender-beveiligingscentrum:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="5120f-132">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

   1. <span data-ttu-id="5120f-133">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Offboarding**.</span><span class="sxs-lookup"><span data-stu-id="5120f-133">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

   1. <span data-ttu-id="5120f-134">Selecteer Windows 10 als het besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="5120f-134">Select Windows 10 as the operating system.</span></span>

   1. <span data-ttu-id="5120f-135">Selecteer in **het veld** Implementatiemethode de optie Mobile Device Management / **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="5120f-135">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
   1. <span data-ttu-id="5120f-136">Klik **op Pakket downloaden** en sla het ZIP-bestand op.</span><span class="sxs-lookup"><span data-stu-id="5120f-136">Click **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="5120f-137">Haal de inhoud van het ZIP-bestand op naar een gedeelde, alleen-lezen locatie die kan worden gebruikt door de netwerkbeheerders die het pakket zullen implementeren.</span><span class="sxs-lookup"><span data-stu-id="5120f-137">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="5120f-138">U moet een bestand met de *naam WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding hebben.*</span><span class="sxs-lookup"><span data-stu-id="5120f-138">You should have a file named *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding*.</span></span>

3. <span data-ttu-id="5120f-139">Gebruik het aangepaste configuratiebeleid van Microsoft Intune om de volgende ondersteunde OMA-URI-instellingen te implementeren.</span><span class="sxs-lookup"><span data-stu-id="5120f-139">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="5120f-140">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="5120f-140">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span><br/>
      <span data-ttu-id="5120f-141">Datumtype: tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5120f-141">Date type: String</span></span><br/>
      <span data-ttu-id="5120f-142">Waarde: [De waarde kopiëren en plakken uit de inhoud van het WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding-bestand]</span><span class="sxs-lookup"><span data-stu-id="5120f-142">Value: [Copy and paste the value from the content of the WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="5120f-143">Zie Windows [10-beleidsinstellingen in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)voor meer informatie over beleidsinstellingen van Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="5120f-143">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>


> [!NOTE]
> <span data-ttu-id="5120f-144">In **het beleid Statusstatus voor niet-geboarde apparaten** worden alleen-lezen eigenschappen gebruikt en deze kunnen niet worden gesaneerd.</span><span class="sxs-lookup"><span data-stu-id="5120f-144">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5120f-145">Offboarding zorgt ervoor dat het apparaat stopt met het verzenden van sensorgegevens naar de portal, maar gegevens van het apparaat, inclusief verwijzingen naar eventuele waarschuwingen die het heeft ontvangen, blijven maximaal 6 maanden bewaard.</span><span class="sxs-lookup"><span data-stu-id="5120f-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5120f-146">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="5120f-146">Related topics</span></span>
- [<span data-ttu-id="5120f-147">Onboard Windows 10-apparaten met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="5120f-147">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="5120f-148">Onboard Windows 10-apparaten met Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5120f-148">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="5120f-149">Onboarden Windows 10-apparaten met een lokaal script</span><span class="sxs-lookup"><span data-stu-id="5120f-149">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="5120f-150">Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten</span><span class="sxs-lookup"><span data-stu-id="5120f-150">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="5120f-151">Een detectietest uitvoeren op een nieuw ingebouwde Microsoft Defender voor eindpuntapparaat</span><span class="sxs-lookup"><span data-stu-id="5120f-151">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="5120f-152">Problemen met de onboarding van Microsoft Defender voor eindpunten oplossen</span><span class="sxs-lookup"><span data-stu-id="5120f-152">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
