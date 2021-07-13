---
title: Microsoft 365 Lighthouse Overzicht van de pagina Apparaat compliance
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Voor MSP's (Managed Service Providers) met Microsoft 365 Lighthouse, meer informatie over de pagina Apparaat compliance.
ms.openlocfilehash: 3568f5b362df86955a1ea6ce15928658c854a584
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395035"
---
# <a name="microsoft-365-lighthouse-device-compliance-page-overview"></a><span data-ttu-id="d5580-103">Microsoft 365 Lighthouse Overzicht van de pagina Apparaat compliance</span><span class="sxs-lookup"><span data-stu-id="d5580-103">Microsoft 365 Lighthouse Device compliance page overview</span></span>

> [!NOTE]
> <span data-ttu-id="d5580-104">De functies die in dit artikel worden beschreven, zijn in Preview, kunnen worden gewijzigd en zijn alleen beschikbaar voor partners die aan de vereisten [voldoen.](m365-lighthouse-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="d5580-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="d5580-105">Als uw organisatie geen Microsoft 365 Lighthouse, zie [Registreren voor Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="d5580-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="d5580-106">Microsoft 365 Lighthouse kunt u inzichten en informatie over intune-apparaat compliance voor al uw tenants bekijken door Apparaten **te** selecteren in het linkernavigatiedeelvenster om de pagina Apparaat compliance te openen.</span><span class="sxs-lookup"><span data-stu-id="d5580-106">Microsoft 365 Lighthouse lets you view insights and information related to Intune device compliance for all your tenants by selecting **Devices** in the left navigation pane to open the Device compliance page.</span></span> <span data-ttu-id="d5580-107">Op deze pagina kunt u een overzicht krijgen van de nalevingsstatus van tenants, een lijst met apparaten voor elke tenant bekijken en statusrapporten over compliancebeleid en -instellingen krijgen.</span><span class="sxs-lookup"><span data-stu-id="d5580-107">From this page, you can get an overview of compliance status across tenants, view a list of devices for each tenant, and get status reports on compliance policies and settings.</span></span>

## <a name="overview-tab"></a><span data-ttu-id="d5580-108">Tabblad Overzicht</span><span class="sxs-lookup"><span data-stu-id="d5580-108">Overview tab</span></span>  
  
<span data-ttu-id="d5580-109">Op het tabblad Overzicht kunt u de nalevingsstatus van apparaten in uw tenants bekijken, trends in de naleving van maandelijkse apparaten bekijken en bijhouden of apparaten compliancebeleid hebben toegewezen.</span><span class="sxs-lookup"><span data-stu-id="d5580-109">On the Overview tab, you can view device compliance status across your tenants, see monthly device compliance trends, and track whether devices have compliance policies assigned to them.</span></span> <span data-ttu-id="d5580-110">U kunt ook informatie weergeven over nalevingsacties en vereisten voor tenantapparaat op basis van beleidsregels voor Voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="d5580-110">You can also view information on tenant device compliance actions and requirements based on Conditional Access policies.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-overview-tab.png" alt-text="Schermafbeelding van het tabblad Overzicht.":::

## <a name="devices-tab"></a><span data-ttu-id="d5580-112">Tabblad Apparaten</span><span class="sxs-lookup"><span data-stu-id="d5580-112">Devices tab</span></span>

<span data-ttu-id="d5580-113">Op het tabblad Apparaten kunt u een lijst met alle tenantapparaten bekijken en de lijst filteren op basis van de volgende nalevingsstatussen: Compliant, Non-compliant, In Respijtperiode en Niet geëvalueerd.</span><span class="sxs-lookup"><span data-stu-id="d5580-113">On the Devices tab, you can view a list of all tenant devices and filter the list based on the following compliance statuses: Compliant, Non-compliant, In Grace period, and Not evaluated.</span></span> <span data-ttu-id="d5580-114">Zie Intune Device compliance policies controleren voor meer informatie over de [verschillende nalevingsstatussen.](/mem/intune/protect/compliance-policy-monitor)</span><span class="sxs-lookup"><span data-stu-id="d5580-114">For more information about the different compliance statuses, see [Monitor Intune Device compliance policies](/mem/intune/protect/compliance-policy-monitor).</span></span>

<span data-ttu-id="d5580-115">Selecteer een apparaat om meer informatie te bekijken over de huidige nalevingstoestand van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="d5580-115">Select any device to view more information on why the device is in its current compliance state.</span></span> <span data-ttu-id="d5580-116">Als u actie moet ondernemen op het apparaat, is er een optie om het apparaat weer te Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="d5580-116">If you need to take action on the device, there's an option to view the device in Microsoft Endpoint Manager.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-device-tab.png" alt-text="Schermafbeelding van het tabblad Apparaten.":::

## <a name="policies-tab"></a><span data-ttu-id="d5580-118">Tabblad Beleid</span><span class="sxs-lookup"><span data-stu-id="d5580-118">Policies tab</span></span>

<span data-ttu-id="d5580-119">Op het tabblad Beleid kunt u compliancebeleid voor uw tenants bekijken en twee of drie beleidsregels van hetzelfde platformtype vergelijken met behulp van de functie Vergelijken op de werkbalk.</span><span class="sxs-lookup"><span data-stu-id="d5580-119">On the Policies tab, you can view compliance policies across your tenants and compare two or three policies of the same platform type by using the Compare feature on the toolbar.</span></span> <span data-ttu-id="d5580-120">U kunt ook elk beleid selecteren om meer informatie weer te geven.</span><span class="sxs-lookup"><span data-stu-id="d5580-120">You can also select any policy to view more information.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-policies-tab.png" alt-text="Schermafbeelding van het tabblad Beleid.":::

## <a name="settings-tab"></a><span data-ttu-id="d5580-122">Instellingen tabblad</span><span class="sxs-lookup"><span data-stu-id="d5580-122">Settings tab</span></span>

<span data-ttu-id="d5580-123">Het tabblad Instellingen bevat een samengevoegd rapport met niet-compatibele instellingen op tenantapparaten.</span><span class="sxs-lookup"><span data-stu-id="d5580-123">The settings tab provides an aggregated report of non-compliant settings across tenant devices.</span></span> <span data-ttu-id="d5580-124">Selecteer een van de rapportrijen om meer informatie weer te geven, inclusief welke tenants de niet-compatibele apparaten behoren.</span><span class="sxs-lookup"><span data-stu-id="d5580-124">Select any of the report rows to view more information, including which tenants the non-compliant devices belong to.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-settings-tab.png" alt-text="Schermafbeelding van het Instellingen tabblad.":::

## <a name="related-content"></a><span data-ttu-id="d5580-126">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="d5580-126">Related content</span></span>

<span data-ttu-id="d5580-127">[Microsoft 365 Lighthouse Paginaoverzicht gebruikers](m365-lighthouse-users-page-overview.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="d5580-127">[Microsoft 365 Lighthouse Users page overview](m365-lighthouse-users-page-overview.md) (article)</span></span>\
<span data-ttu-id="d5580-128">[Microsoft 365 Lighthouse veelgestelde vragen](m365-lighthouse-faq.yml) (artikel)</span><span class="sxs-lookup"><span data-stu-id="d5580-128">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
