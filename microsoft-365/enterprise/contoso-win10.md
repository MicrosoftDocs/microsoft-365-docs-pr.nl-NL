---
title: Windows 10 Enterprise-implementatie voor Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Ontdek hoe Contoso Microsoft Endpoint Configuration Manager gebruikte om in-place upgrades voor Windows 10 Enterprise te implementeren.
ms.openlocfilehash: 0543f24665048d0679bc1b099fdd0a2d431c1e54
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754245"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="7b9ac-103">Windows 10 Enterprise-implementatie voor Contoso</span><span class="sxs-lookup"><span data-stu-id="7b9ac-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="7b9ac-104">Voor de grote implementatie van Microsoft 365 for Enterprise hadden contoso Windows-compatibele Pc's en apparaten met een menging van Windows 7 (10%), Windows 8,1 (65%) en Windows 10 (25%).</span><span class="sxs-lookup"><span data-stu-id="7b9ac-104">Prior to the wide rollout of Microsoft 365 for enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%).</span></span> <span data-ttu-id="7b9ac-105">Contoso wilde haar pc’s upgraden, omdat Windows 10 Enterprise gebruikmaakt van geavanceerde beveiliging en IT-overhead vermindert door automatische implementatie van updates.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-105">Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of advanced security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="7b9ac-106">Na het evalueren van hun infrastructuur en bedrijfsbehoeften identificeerde Contoso deze belangrijke vereisten voor de implementatie:</span><span class="sxs-lookup"><span data-stu-id="7b9ac-106">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="7b9ac-107">Zoveel mogelijk pc’s en apparaten moeten Windows 10 Enterprise uitvoeren</span><span class="sxs-lookup"><span data-stu-id="7b9ac-107">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="7b9ac-108">De implementatie van de in-place upgrades gebruikt de bestaande Configuration Manager-infrastructuur</span><span class="sxs-lookup"><span data-stu-id="7b9ac-108">Rollout of the in-place upgrades leverages existing Configuration Manager infrastructure</span></span>
- <span data-ttu-id="7b9ac-109">De controle over welke versie van Windows 10 Enterprise moet worden geïmplementeerd en updates moeten plaatsvinden middels ringen.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-109">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="7b9ac-110">Pc’s en apparaten moeten up-to-date blijven met minimale administratieve IT-kosten en minimale overlast voor eindgebruikers</span><span class="sxs-lookup"><span data-stu-id="7b9ac-110">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="7b9ac-111">Up-to-date wordt gedefinieerd als de ondersteunde versie van Windows 10 Enterprise die voldoet aan de bedrijfsbehoeften van Contoso. Dit hoeft niet te betekenen dat alle Windows-compatibele pc’s de nieuwste versie van Windows 10 Enterprise uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-111">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="7b9ac-112">Implementatiehulpmiddelen</span><span class="sxs-lookup"><span data-stu-id="7b9ac-112">Deployment tools</span></span>

<span data-ttu-id="7b9ac-113">Voorafgaand en tijdens de in-place upgrades van Windows 10 Enterprise gebruikte Contoso de volgende oplossingen van Windows Analytics:</span><span class="sxs-lookup"><span data-stu-id="7b9ac-113">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="7b9ac-114">Gereedheidscontroles voor upgrades</span><span class="sxs-lookup"><span data-stu-id="7b9ac-114">Upgrade Readiness</span></span>  

  <span data-ttu-id="7b9ac-115">Hiermee worden systeem-, toepassings- en stuurprogrammagagevens verzameld voor analyses en vervolgens compatibiliteitsproblemen die een upgrade kunnen blokkeren en voorgestelde oplossingen van bij Microsoft bekende problemen geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-115">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="7b9ac-116">Naleving van updates</span><span class="sxs-lookup"><span data-stu-id="7b9ac-116">Update Compliance</span></span>  

  <span data-ttu-id="7b9ac-117">Geeft de status van uw apparaten weer inzake de Windows-updates, zodat u er zeker van kunt zijn dat ze de meest recente updates hebben.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-117">Shows you the state of your devices with respect to the Windows updates so that you can ensure that they are on the most current updates as appropriate.</span></span>

- <span data-ttu-id="7b9ac-118">Apparaatstatus</span><span class="sxs-lookup"><span data-stu-id="7b9ac-118">Device Health</span></span>  

  <span data-ttu-id="7b9ac-119">Hiermee worden apparaten geïdentificeerd die regelmatig vastlopen en die daarom mogelijk opnieuw moeten worden opgebouwd of vervangen en stuurprogramma’s die de oorzaak zijn van het vastlopen, met suggesties van alternatieve versies van die stuurprogramma’s, waardoor apparaten minder vaak vastlopen.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-119">Identifies devices that crash frequently, and therefore might need to be rebuilt or replaced and device drivers that are causing device crashes, with suggestions of alternative versions of those drivers that might reduce the number of crashes.</span></span> <span data-ttu-id="7b9ac-120">Hiermee worden meldingen weergegeven over onjuiste configuraties van Windows-gegevensbescherming en aanwijzingen naar de eindgebruikers verzonden.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-120">Provides notification of Windows Information Protection misconfigurations that send prompts to end users.</span></span>
 
<span data-ttu-id="7b9ac-121">Contoso heeft een bestaande Configuration Manager-infrastructuur (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="7b9ac-121">Contoso has an existing Configuration Manager (Current Branch) infrastructure.</span></span> <span data-ttu-id="7b9ac-122">Configuration Manager is schaalbaar voor grote omgevingen en biedt uitgebreide controle over installatie, updates en instellingen.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-122">Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings.</span></span> <span data-ttu-id="7b9ac-123">Er zijn ook ingebouwde functies waarmee het eenvoudiger en efficiënter wordt om Windows 10 Enterprise te implementeren en te beheren.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-123">It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="7b9ac-124">Planningsproces</span><span class="sxs-lookup"><span data-stu-id="7b9ac-124">Planning process</span></span>

<span data-ttu-id="7b9ac-125">Contoso heeft de upgrade gereedheids gebruikt in Windows Analytics om te bepalen welke set geïnstalleerde apps en de compatibiliteit met Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-125">Contoso used the Upgrade Readiness in Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="7b9ac-126">Implementatieproces</span><span class="sxs-lookup"><span data-stu-id="7b9ac-126">Deployment process</span></span>

<span data-ttu-id="7b9ac-127">Contoso implementeerde het volgende proces, met de aanbevelingen van Microsoft voor aanbevolen procedures om de implementatie van de in-place upgrade van Windows 10 Enterprise te voltooien:</span><span class="sxs-lookup"><span data-stu-id="7b9ac-127">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="7b9ac-128">Peer-cache voor Configuration Manager werd ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-128">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="7b9ac-129">Aangepaste Windows-pakketten werden gemaakt op basis van images van het Servicecentrum voor volumelicenties.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-129">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="7b9ac-130">Gebruik Configuration Manager om de Windows-pakketten te implementeren op distributiepunten voor distributiepunten in hun netwerk en geïmplementeerde versies van de drie groepen voor het testen van validatie en implementatie.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-130">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging groups.</span></span>
4. <span data-ttu-id="7b9ac-131">Evaluatie werd uitgevoerd voor het slagen van de implementatie op pc’s en apparaten in de drie ringen voor validatie- en implementatiefasen met de Windows Analytics-oplossingen Apparaatstatus en Naleving van updates.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-131">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="7b9ac-132">Op basis van de informatie over Windows Analytics heeft Contoso de versie van Windows 10 Enterprise vastgesteld voor de implementatie van de overkoepelende implementatiegroep.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-132">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment group.</span></span>
6. <span data-ttu-id="7b9ac-133">De stappen voor de implementatie van Configuration Manager uitvoeren om het geselecteerde Windows-pakket te implementeren voor de overkoepelende implementatiegroep.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-133">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment group.</span></span>
7. <span data-ttu-id="7b9ac-134">Gecontroleerde Pc's en apparaten in de uitgebreide implementatiegroep, met behulp van de apparaatcompatibiliteit en update de compliance-oplossingen om problemen op te lossen.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-134">Monitored PCs and devices in the broad deployment group using the Device Health and Update Compliance solutions to address issues.</span></span>

<span data-ttu-id="7b9ac-135">Dit is de implementatie-architectuur van in-place upgrades en doorlopende updates van Contoso.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-135">Here is Contoso’s in-place upgrade and ongoing updates deployment architecture.</span></span>

![Implementatie-architectuur van Windows 10 Enterprise van Contoso](../media/contoso-win10/contoso-win10-fig1.png)

<span data-ttu-id="7b9ac-137">Deze infrastructuur bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="7b9ac-137">This infrastructure consists of:</span></span>

- <span data-ttu-id="7b9ac-138">Configuration Manager, die:</span><span class="sxs-lookup"><span data-stu-id="7b9ac-138">Configuration Manager, which:</span></span>
  - <span data-ttu-id="7b9ac-139">images ophaalt voor Windows 10 Enterprise-pakketten van het Microsoft Servicecentrum voor volumelicenties in het Microsoft-netwerk.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-139">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="7b9ac-140">het centrale beheerpunt is voor implementatiepakketten.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-140">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="7b9ac-141">Regionale distributiepunten die zich normaliter in de regionale hub-kantoren van Contoso bevinden.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-141">Regional distribution points that are typically located in Contoso’s regional hub offices.</span></span>
- <span data-ttu-id="7b9ac-142">Windows-Pc's en-apparaten op diverse locaties waarop de implementatiepakketten worden ontvangen en geïnstalleerd voor de interne upgrade of voortdurende updates op basis van groepslidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="7b9ac-142">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on group membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="7b9ac-143">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="7b9ac-143">Next step</span></span>

<span data-ttu-id="7b9ac-144">Meer informatie over hoe Contoso de configuratie van een Configuration Manager-infrastructuur maakt om [actuele Microsoft 365-apps voor Enterprise binnen de organisatie te implementeren en te behouden](contoso-o365pp.md) .</span><span class="sxs-lookup"><span data-stu-id="7b9ac-144">Learn how Contoso is leveraging its Configuration Manager infrastructure to [deploy and keep current Microsoft 365 Apps for enterprise](contoso-o365pp.md) across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="7b9ac-145">Zie ook</span><span class="sxs-lookup"><span data-stu-id="7b9ac-145">See also</span></span>

[<span data-ttu-id="7b9ac-146">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7b9ac-146">Windows 10 Enterprise</span></span>](https://docs.microsoft.com/windows/deployment/)

[<span data-ttu-id="7b9ac-147">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="7b9ac-147">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7b9ac-148">Testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="7b9ac-148">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
