---
title: Host firewall reporting in Microsoft Defender for Endpoint
description: Firewallrapportage hosten en weergeven in Microsoft 365 beveiligingscentrum.
keywords: Windows Defender, firewall
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 0289d6f920fd6ff35fd446f9c2b8c5516883a4d2
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809253"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="d6721-104">Host firewall reporting in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d6721-104">Host firewall reporting in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d6721-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d6721-105">**Applies to:**</span></span>
- [<span data-ttu-id="d6721-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="d6721-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d6721-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d6721-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="d6721-108">Als u een beheerder bent, kunt u nu firewallrapportage hosten [Microsoft 365 beveiligingscentrum.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="d6721-108">If you are an admin, you can now host firewall reporting to [Microsoft 365 security center](https://security.microsoft.com).</span></span> <span data-ttu-id="d6721-109">Met deze functie kunt u de Windows 10 en Windows Server 2019-firewallrapportage bekijken vanaf een gecentraliseerde locatie.</span><span class="sxs-lookup"><span data-stu-id="d6721-109">This feature enables you to view Windows 10 and Windows Server 2019 firewall reporting from a centralized location.</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d6721-110">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="d6721-110">What do you need to know before you begin?</span></span> 

- <span data-ttu-id="d6721-111">U moet server 2019 Windows 10 of Windows uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="d6721-111">You must be running Windows 10 or Windows Server 2019.</span></span>
- <span data-ttu-id="d6721-112">Als u apparaten wilt onboarden bij de Microsoft Defender for Endpoint-service, zie [hier](onboard-configure.md).</span><span class="sxs-lookup"><span data-stu-id="d6721-112">To onboard devices to the Microsoft Defender for Endpoint service, see [here](onboard-configure.md).</span></span> 
- <span data-ttu-id="d6721-113">Als Microsoft 365 beveiligingscentrum de gegevens wilt ontvangen, moet u **Auditgebeurtenissen** inschakelen Windows Defender Firewall geavanceerde beveiliging:</span><span class="sxs-lookup"><span data-stu-id="d6721-113">For Microsoft 365 security center to start receiving the data, you must enable **Audit Events** for Windows Defender Firewall with Advanced Security:</span></span> 
    - [<span data-ttu-id="d6721-114">Controlefilterplatformpakket neerzetten</span><span class="sxs-lookup"><span data-stu-id="d6721-114">Audit Filtering Platform Packet Drop</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
    - [<span data-ttu-id="d6721-115">Audit Filtering Platform Connection</span><span class="sxs-lookup"><span data-stu-id="d6721-115">Audit Filtering Platform Connection</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-connection) 
- <span data-ttu-id="d6721-116">Schakel deze gebeurtenissen in met groepsbeleidsobjecteditor, lokaal beveiligingsbeleid of de auditpol.exe opdrachten.</span><span class="sxs-lookup"><span data-stu-id="d6721-116">Enable these events by using Group Policy Object Editor, Local Security Policy, or the auditpol.exe commands.</span></span> <span data-ttu-id="d6721-117">Zie hier voor meer [informatie.](/windows/win32/fwp/auditing-and-logging)</span><span class="sxs-lookup"><span data-stu-id="d6721-117">For more information, see [here](/windows/win32/fwp/auditing-and-logging).</span></span> 
    - <span data-ttu-id="d6721-118">De twee PowerShell-opdrachten zijn:</span><span class="sxs-lookup"><span data-stu-id="d6721-118">The two PowerShell commands are:</span></span>
        - <span data-ttu-id="d6721-119">**auditpol /set /subcategorie:"Filtering Platform Packet Drop" /failure:enable**</span><span class="sxs-lookup"><span data-stu-id="d6721-119">**auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**</span></span> 
        - <span data-ttu-id="d6721-120">**auditpol /set /subcategorie:"Filterplatformverbinding" /failure:enable**</span><span class="sxs-lookup"><span data-stu-id="d6721-120">**auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**</span></span> 

## <a name="the-process"></a><span data-ttu-id="d6721-121">Het proces</span><span class="sxs-lookup"><span data-stu-id="d6721-121">The process</span></span>
> [!NOTE]
> <span data-ttu-id="d6721-122">Zorg ervoor dat u de instructies uit de bovenstaande sectie volgt en uw apparaten correct configureert voor de eerste preview-deelname.</span><span class="sxs-lookup"><span data-stu-id="d6721-122">Make sure to follow the instructions from the section above and properly configure your devices for the early preview participation.</span></span>

- <span data-ttu-id="d6721-123">Nadat u de gebeurtenissen inschakelen, Microsoft 365 beveiligingscentrum de gegevens controleren.</span><span class="sxs-lookup"><span data-stu-id="d6721-123">After enabling the events, Microsoft 365 security center will start to monitor the data.</span></span>
    - <span data-ttu-id="d6721-124">Externe IP, Externe poort, Lokale poort, Lokale IP, Computernaam, Proces tussen binnenkomende en uitgaande verbindingen.</span><span class="sxs-lookup"><span data-stu-id="d6721-124">Remote IP, Remote Port, Local Port, Local IP, Computer Name, Process across inbound and outbound connections.</span></span>
- <span data-ttu-id="d6721-125">Beheerders kunnen nu hier Windows hostfirewallactiviteit [zien.](https://security.microsoft.com/firewall)</span><span class="sxs-lookup"><span data-stu-id="d6721-125">Admins can now see Windows host firewall activity [here](https://security.microsoft.com/firewall).</span></span>
    - <span data-ttu-id="d6721-126">Aanvullende rapportage kan worden vergemakkelijkt door het script Aangepaste rapportage te [downloaden](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) om de Windows Defender Firewall activiteiten met behulp van Power BI.</span><span class="sxs-lookup"><span data-stu-id="d6721-126">Additional reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 
    - <span data-ttu-id="d6721-127">Het kan tot 12 uur duren voordat de gegevens worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d6721-127">It can take up to 12 hours before the data is reflected.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="d6721-128">Ondersteunde scenario's</span><span class="sxs-lookup"><span data-stu-id="d6721-128">Supported scenarios</span></span>
<span data-ttu-id="d6721-129">De volgende scenario's worden ondersteund tijdens Ring0 Preview.</span><span class="sxs-lookup"><span data-stu-id="d6721-129">The following scenarios are supported during Ring0 Preview.</span></span> 

### <a name="firewall-reporting-in-security-center"></a><span data-ttu-id="d6721-130">Firewallrapportage in beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="d6721-130">Firewall reporting in security center</span></span>

<span data-ttu-id="d6721-131">Hier zijn een paar voorbeelden van de firewallrapportpagina's.</span><span class="sxs-lookup"><span data-stu-id="d6721-131">Here is a couple of examples of the firewall report pages.</span></span> <span data-ttu-id="d6721-132">Hier vindt u een overzicht van de inkomende, uitgaande en toepassingsactiviteit.</span><span class="sxs-lookup"><span data-stu-id="d6721-132">Here you will find a summary of inbound, outbound, and application activity.</span></span> <span data-ttu-id="d6721-133">U kunt deze pagina rechtstreeks openen door naar https://security.microsoft.com/firewall .</span><span class="sxs-lookup"><span data-stu-id="d6721-133">You can access this page directly by going to https://security.microsoft.com/firewall.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d6721-134">![Rapportpagina hostfirewall](\images\host-firewall-reporting-page.png)</span><span class="sxs-lookup"><span data-stu-id="d6721-134">![Host firewall reporting page](\images\host-firewall-reporting-page.png)</span></span>

<span data-ttu-id="d6721-135">U kunt deze rapporten ook openen door naar **Rapporten**  >  **Beveiligingsrapportapparaten**  >   (sectie) te gaan onder aan de **kaart Geblokkeerde** binnenkomende verbindingen van firewall.</span><span class="sxs-lookup"><span data-stu-id="d6721-135">These reports can also be accessed by going to **Reports** > **Security Report** > **Devices** (section) located at the bottom of the **Firewall Blocked Inbound Connections** card.</span></span>

### <a name="from-computers-with-a-blocked-connection-to-device"></a><span data-ttu-id="d6721-136">Van 'Computers met een geblokkeerde verbinding' naar apparaat</span><span class="sxs-lookup"><span data-stu-id="d6721-136">From "Computers with a blocked connection" to device</span></span>

<span data-ttu-id="d6721-137">Kaarten ondersteunen interactieve objecten.</span><span class="sxs-lookup"><span data-stu-id="d6721-137">Cards support interactive objects.</span></span> <span data-ttu-id="d6721-138">U kunt inzoomen op de activiteit van een apparaat door op de naam van het apparaat te klikken, die wordt weergegeven op een nieuw tabblad, en u rechtstreeks naar het tabblad https://securitycenter.microsoft.com **Apparaattijdlijn te** gaan.</span><span class="sxs-lookup"><span data-stu-id="d6721-138">You can drill into the activity of a device by clicking on the device name, which will launch https://securitycenter.microsoft.com in a new tab, and take you directly to the **Device Timeline** tab.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d6721-139">![Computers met een geblokkeerde verbinding](\images\firewall-reporting-blocked-connection.png)</span><span class="sxs-lookup"><span data-stu-id="d6721-139">![Computers with a blocked connection](\images\firewall-reporting-blocked-connection.png)</span></span>

<span data-ttu-id="d6721-140">U kunt nu het tabblad **Tijdlijn** selecteren, waarmee u een lijst krijgt met gebeurtenissen die aan dat apparaat zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="d6721-140">You can now select the **Timeline** tab, which will give you a list of events associated with that device.</span></span> 

<span data-ttu-id="d6721-141">Nadat u op de knop **Filters** in de rechterbovenhoek van het weergavevenster hebt geklikt, selecteert u het type gebeurtenis dat u wilt.</span><span class="sxs-lookup"><span data-stu-id="d6721-141">After clicking on the **Filters** button on the upper right-hand corner of the viewing pane, select the type of event you want.</span></span> <span data-ttu-id="d6721-142">Selecteer in dit geval **Firewallgebeurtenissen** en het deelvenster wordt gefilterd op firewallgebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="d6721-142">In this case, select **Firewall events** and the pane will be filtered to Firewall events.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d6721-143">![Knop Filters](\images\firewall-reporting-filters-button.png)</span><span class="sxs-lookup"><span data-stu-id="d6721-143">![Filters button](\images\firewall-reporting-filters-button.png)</span></span>

### <a name="drill-into-advanced-hunting-preview-refresh"></a><span data-ttu-id="d6721-144">Inzoomen op geavanceerd zoeken (preview vernieuwen)</span><span class="sxs-lookup"><span data-stu-id="d6721-144">Drill into advanced hunting (preview refresh)</span></span>

<span data-ttu-id="d6721-145">Firewallrapporten ondersteunen het boren van de kaart rechtstreeks naar **Geavanceerd zoeken** door op de knop Geavanceerd zoeken **openen te** klikken.</span><span class="sxs-lookup"><span data-stu-id="d6721-145">Firewall reports support drilling from the card directly into **Advanced Hunting** by clicking the **Open Advanced hunting** button.</span></span> <span data-ttu-id="d6721-146">De query wordt vooraf ingevuld.</span><span class="sxs-lookup"><span data-stu-id="d6721-146">The query will be pre-populated.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d6721-147">![Knop Geavanceerd zoeken openen](\images\firewall-reporting-advanced-hunting.png)</span><span class="sxs-lookup"><span data-stu-id="d6721-147">![Open Advanced hunting button](\images\firewall-reporting-advanced-hunting.png)</span></span>

<span data-ttu-id="d6721-148">De query kan nu worden uitgevoerd en alle gerelateerde firewallgebeurtenissen van de afgelopen 30 dagen kunnen worden verkend.</span><span class="sxs-lookup"><span data-stu-id="d6721-148">The query can now be executed, and all related Firewall events from the last 30 days can be explored.</span></span> 

<span data-ttu-id="d6721-149">Voor extra rapportages of aangepaste wijzigingen kan de query worden geëxporteerd naar Power BI voor verdere analyse.</span><span class="sxs-lookup"><span data-stu-id="d6721-149">For additional reporting, or custom changes, the query can be exported into Power BI for further analysis.</span></span> <span data-ttu-id="d6721-150">Aangepaste rapportage kan worden vergemakkelijkt door het script Aangepaste rapportage te [downloaden](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) om de Windows Defender Firewall activiteiten met behulp van Power BI.</span><span class="sxs-lookup"><span data-stu-id="d6721-150">Custom reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 

 