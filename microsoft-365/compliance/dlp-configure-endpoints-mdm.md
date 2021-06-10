---
title: Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Gebruik hulpprogramma's voor mobiel apparaatbeheer om het configuratiepakket op apparaten te implementeren, zodat ze zijn aan boord van de service.
ms.openlocfilehash: 1ad1115308257fa3ce63f10edebb9129638fd52f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161911"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="2dc1e-103">Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="2dc1e-103">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

<span data-ttu-id="2dc1e-104">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2dc1e-104">**Applies to:**</span></span>

- [<span data-ttu-id="2dc1e-105">Microsoft 365 Preventie van gegevensverlies in eindpunten (DLP)</span><span class="sxs-lookup"><span data-stu-id="2dc1e-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="2dc1e-106">U kunt MDM-oplossingen (Mobile Device Management) gebruiken om apparaten te configureren.</span><span class="sxs-lookup"><span data-stu-id="2dc1e-106">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="2dc1e-107">Microsoft 365 Preventie van gegevensverlies in eindpunten ondersteunt MDM's door OMA-URIs om beleid te maken voor het beheren van apparaten.</span><span class="sxs-lookup"><span data-stu-id="2dc1e-107">Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="2dc1e-108">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="2dc1e-108">Before you begin</span></span>
<span data-ttu-id="2dc1e-109">Als u een Microsoft Intune gebruikt, moet u het apparaat MDM-inschrijving hebben.</span><span class="sxs-lookup"><span data-stu-id="2dc1e-109">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="2dc1e-110">Anders worden de instellingen niet toegepast.</span><span class="sxs-lookup"><span data-stu-id="2dc1e-110">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="2dc1e-111">Zie [Apparaatinschrijving (Microsoft Intune)](/mem/intune/enrollment/device-enrollment)voor meer informatie over het inschakelen van MDM met Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="2dc1e-111">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="2dc1e-112">Onboard-apparaten met Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2dc1e-112">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="2dc1e-113">Volg de instructies van [Intune](/intune/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="2dc1e-113">Follow the instructions from [Intune](/intune/advanced-threat-protection).</span></span>

> [!NOTE]
> - <span data-ttu-id="2dc1e-114">Het **beleid Statusstatus voor onboarded-apparaten** gebruikt alleen-lezen eigenschappen en kan niet worden gesaneerd.</span><span class="sxs-lookup"><span data-stu-id="2dc1e-114">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="2dc1e-115">Apparaten offboarden en bewaken met behulp van hulpprogramma's voor mobiel apparaatbeheer</span><span class="sxs-lookup"><span data-stu-id="2dc1e-115">Offboard and monitor devices using Mobile Device Management tools</span></span>

<span data-ttu-id="2dc1e-116">Om veiligheidsredenen verloopt het pakket dat wordt gebruikt voor Offboard-apparaten 30 dagen na de datum waarop het is gedownload.</span><span class="sxs-lookup"><span data-stu-id="2dc1e-116">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="2dc1e-117">Verlopen offboarding-pakketten die naar een apparaat zijn verzonden, worden geweigerd.</span><span class="sxs-lookup"><span data-stu-id="2dc1e-117">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="2dc1e-118">Wanneer u een offboarding-pakket downloadt, wordt u op de hoogte gesteld van de vervaldatum van de pakketten en wordt het ook opgenomen in de pakketnaam.</span><span class="sxs-lookup"><span data-stu-id="2dc1e-118">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="2dc1e-119">Onboarding- en offboarding-beleid mag niet tegelijkertijd op hetzelfde apparaat worden geïmplementeerd, anders veroorzaakt dit onvoorspelbare botsingen.</span><span class="sxs-lookup"><span data-stu-id="2dc1e-119">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="2dc1e-120">Haal het offboarding-pakket op in [het Microsoft Compliance Center.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="2dc1e-120">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="2dc1e-121">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Onboarding**  >  **offboarding** voor apparaten.</span><span class="sxs-lookup"><span data-stu-id="2dc1e-121">In the navigation pane, select **Settings** > **Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="2dc1e-122">Selecteer in **het veld** Implementatiemethode de optie Mobile Device **Management /Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="2dc1e-122">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
4. <span data-ttu-id="2dc1e-123">Klik **op Pakket downloaden** en sla het .zip op.</span><span class="sxs-lookup"><span data-stu-id="2dc1e-123">Click **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="2dc1e-124">Haal de inhoud van het .zip bestand op naar een gedeelde, alleen-lezen locatie die kan worden gebruikt door de netwerkbeheerders die het pakket zullen implementeren.</span><span class="sxs-lookup"><span data-stu-id="2dc1e-124">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="2dc1e-125">U moet een bestand met de naam *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding hebben.*</span><span class="sxs-lookup"><span data-stu-id="2dc1e-125">You should have a file named *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.</span></span>

6. <span data-ttu-id="2dc1e-126">Gebruik het Microsoft Intune aangepast configuratiebeleid om de volgende ondersteunde OMA-URI-instellingen te implementeren.</span><span class="sxs-lookup"><span data-stu-id="2dc1e-126">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="2dc1e-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="2dc1e-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span>      
      <span data-ttu-id="2dc1e-128">Datumtype: tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2dc1e-128">Date type: String</span></span>      
      <span data-ttu-id="2dc1e-129">Waarde: [De waarde kopiëren en plakken uit de inhoud van het DeviceCompliance_valid_until_YYYY-MM-DD.offboarding-bestand]</span><span class="sxs-lookup"><span data-stu-id="2dc1e-129">Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="2dc1e-130">Zie voor meer informatie over Microsoft Intune beleidsinstellingen [Windows 10 beleidsinstellingen in Microsoft Intune.](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="2dc1e-130">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>

> [!NOTE]
> <span data-ttu-id="2dc1e-131">In **het beleid Statusstatus voor niet-geboarde apparaten** worden alleen-lezen eigenschappen gebruikt en deze kunnen niet worden gesaneerd.</span><span class="sxs-lookup"><span data-stu-id="2dc1e-131">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2dc1e-132">Offboarding zorgt ervoor dat het apparaat stopt met het verzenden van sensorgegevens naar de portal, maar gegevens van het apparaat, inclusief verwijzingen naar eventuele waarschuwingen die het heeft ontvangen, blijven maximaal 6 maanden bewaard.</span><span class="sxs-lookup"><span data-stu-id="2dc1e-132">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2dc1e-133">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="2dc1e-133">Related topics</span></span>
- [<span data-ttu-id="2dc1e-134">Onboard Windows 10 apparaten met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="2dc1e-134">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="2dc1e-135">Onboard Windows 10 apparaten met Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2dc1e-135">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="2dc1e-136">Onboarden Windows 10-apparaten met een lokaal script</span><span class="sxs-lookup"><span data-stu-id="2dc1e-136">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="2dc1e-137">Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten</span><span class="sxs-lookup"><span data-stu-id="2dc1e-137">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="2dc1e-138">Problemen met Microsoft Defender Advanced Threat Protection onboarding oplossen</span><span class="sxs-lookup"><span data-stu-id="2dc1e-138">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)