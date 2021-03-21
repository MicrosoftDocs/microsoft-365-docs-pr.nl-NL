---
title: Windows 10-locatieservice
description: Windows-locatieservices hebben ingeschakeld voor uw apparaten
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 210356dd21b36efbb27d8faa4f8616145584159c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929476"
---
# <a name="windows-10-location-service"></a><span data-ttu-id="90da0-104">Windows 10-locatieservice</span><span class="sxs-lookup"><span data-stu-id="90da0-104">Windows 10 location service</span></span>

<span data-ttu-id="90da0-105">Apparaten in Microsoft Managed Desktop worden geregistreerd met Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="90da0-105">Devices in Microsoft Managed Desktop are registered by using Windows Autopilot.</span></span> <span data-ttu-id="90da0-106">Met dit proces kunnen we ze beheren met Azure Active Directory en Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="90da0-106">This process lets us manage them with Azure Active Directory and Microsoft Intune.</span></span> <span data-ttu-id="90da0-107">De Windows 10-locatieservice is standaard uitgeschakeld wanneer een apparaat voor het eerst is ingeschakeld, tenzij deze functie is ingeschakeld in de Privacy-instellingen tijdens de 'out-of-box-ervaring'.</span><span class="sxs-lookup"><span data-stu-id="90da0-107">By default, the Windows 10 location service is disabled when a device is turned on for the first time unless this feature is enabled in the Privacy settings during the "out of box experience."</span></span> <span data-ttu-id="90da0-108">Deze instellingen zijn verborgen tijdens de Autopilot-inschrijving in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="90da0-108">These settings are hidden during Autopilot enrollment in Microsoft Managed Desktop.</span></span> <span data-ttu-id="90da0-109">Zie [First-run experience with Autopilot and the Enrollment Status Page](esp-first-run.md)voor meer informatie over hoe Autopilot is ingesteld.</span><span class="sxs-lookup"><span data-stu-id="90da0-109">For more information about how Autopilot is set up, see [First-run experience with Autopilot and the Enrollment Status Page](esp-first-run.md).</span></span>

<span data-ttu-id="90da0-110">Daarom kunnen Microsoft Managed Desktop-apparaten hun apparaatlocatie niet verkrijgen, waardoor de functionaliteit van verschillende Windows-functies, zoals tijdzones, wordt beperkt.</span><span class="sxs-lookup"><span data-stu-id="90da0-110">For this reason, Microsoft Managed Desktop devices can't obtain their device location, which limits the functionality of several Windows features, such as time zones.</span></span> <span data-ttu-id="90da0-111">Zie Windows 10-locatieservice en privacy voor meer informatie over de [Windows 10-locatieservice.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)</span><span class="sxs-lookup"><span data-stu-id="90da0-111">For more information about the Windows 10 location service, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="90da0-112">U hoeft de locatieservice niet te gebruiken om deel te nemen aan Microsoft Managed Desktop, maar de gebruikerservaring wordt beperkt.</span><span class="sxs-lookup"><span data-stu-id="90da0-112">You don't have to use the location service in order to participate in Microsoft Managed Desktop, but the user experience will be restricted.</span></span> <span data-ttu-id="90da0-113">Apparaten kunnen bijvoorbeeld niet automatisch bepalen in welke tijdzone ze zich bevindt wanneer uw gebruikers in een andere tijdzone werken.</span><span class="sxs-lookup"><span data-stu-id="90da0-113">For example, devices won't be able to automatically determine the time zone they're in when your users work in a different time zone.</span></span>

## <a name="enable-the-location-service"></a><span data-ttu-id="90da0-114">De locatieservice inschakelen</span><span class="sxs-lookup"><span data-stu-id="90da0-114">Enable the location service</span></span>

<span data-ttu-id="90da0-115">U kunt zich aanmelden voor het gebruik van de locatieservice wanneer u apparaten inschrijft bij de Microsoft Managed Desktop-service of u kunt de service in- of uitschakelen na de inschrijving.</span><span class="sxs-lookup"><span data-stu-id="90da0-115">You can either opt in to using the location service when you enroll devices into the Microsoft Managed Desktop service or you can turn the service on or off after enrollment.</span></span>

### <a name="opt-in-during-enrollment"></a><span data-ttu-id="90da0-116">Aanmelden tijdens inschrijving</span><span class="sxs-lookup"><span data-stu-id="90da0-116">Opt in during enrollment</span></span>

<span data-ttu-id="90da0-117">U kunt de locatieservice laten inschakelen met de Microsoft Managed Desktop-service.</span><span class="sxs-lookup"><span data-stu-id="90da0-117">You can have the Microsoft Managed Desktop service enable the location service.</span></span> <span data-ttu-id="90da0-118">Tijdens de inschrijvingsreeks wordt u gevraagd te selecteren of u wilt toestaan dat de Windows 10-locatieservice is ingeschakeld op apparaten.</span><span class="sxs-lookup"><span data-stu-id="90da0-118">During the enrollment sequence, you'll be asked to select whether you want to allow the Windows 10 location service to be enabled on devices.</span></span>

### <a name="control-the-location-service-after-enrollment"></a><span data-ttu-id="90da0-119">De locatieservice na inschrijving bepalen</span><span class="sxs-lookup"><span data-stu-id="90da0-119">Control the location service after enrollment</span></span>

<span data-ttu-id="90da0-120">U kunt de locatieservice op elk moment in- of uitschakelen door een [ondersteuningsaanvraag](../working-with-managed-desktop/admin-support.md) in te dienen via de [beheerportal.](access-admin-portal.md)</span><span class="sxs-lookup"><span data-stu-id="90da0-120">You can have the location service turned on (or off) at any time by submitting a [support request](../working-with-managed-desktop/admin-support.md) through the [Admin portal](access-admin-portal.md).</span></span>

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a><span data-ttu-id="90da0-121">Hoe Microsoft Managed Desktop de Windows 10-locatieservice configureert</span><span class="sxs-lookup"><span data-stu-id="90da0-121">How Microsoft Managed Desktop configures the Windows 10 location service</span></span>

<span data-ttu-id="90da0-122">Als u ervoor kiest om de locatieservice te gebruiken, gebruiken we de minimale instellingen die nodig zijn zonder dat dit van invloed is op de privacy van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="90da0-122">If you opt in to using the location service, we use the minimum settings necessary without affecting users' privacy.</span></span> <span data-ttu-id="90da0-123">Zie Locatieservice en [privacy van Windows 10 voor meer informatie.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)</span><span class="sxs-lookup"><span data-stu-id="90da0-123">For more information, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="90da0-124">Microsoft Managed Desktop schakelt de **privacy-instelling Locatie** in **Windows-instellingen** in om **toegang tot locatie op dit apparaat toe te staan.**</span><span class="sxs-lookup"><span data-stu-id="90da0-124">Microsoft Managed Desktop enables the **Location privacy** setting in **Windows settings** to **Allow access to location on this device**.</span></span> <span data-ttu-id="90da0-125">De gebruikersinterface ziet er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="90da0-125">The user interface looks like this:</span></span>

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Locatie-instellingen in Windows-instellingen":::

> [!NOTE]
> <span data-ttu-id="90da0-127">Als u ervoor kiest om de locatieservice te gebruiken, geldt dit alleen voor het Windows-besturingssysteem zelf.</span><span class="sxs-lookup"><span data-stu-id="90da0-127">If you opt in to using the location service, this applies only to the Windows operating system itself.</span></span> <span data-ttu-id="90da0-128">Apps zijn niet toegestaan om locatieservices te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="90da0-128">Apps are not allowed to use location services.</span></span> <span data-ttu-id="90da0-129">Elke gebruiker kan kiezen of apps toegang mogen krijgen tot hun locatie.</span><span class="sxs-lookup"><span data-stu-id="90da0-129">Each user can choose whether to allow apps to access their location.</span></span>