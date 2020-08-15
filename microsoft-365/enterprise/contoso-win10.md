---
title: Windows 10 Enterprise-implementatie voor Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Ontdek hoe Contoso Microsoft Endpoint Configuration Manager gebruikte om in-place upgrades voor Windows 10 Enterprise te implementeren.
ms.openlocfilehash: a100eb07408053fd270c26f388265696549fff9f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686416"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="1c9dc-103">Windows 10 Enterprise-implementatie voor Contoso</span><span class="sxs-lookup"><span data-stu-id="1c9dc-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="1c9dc-104">Voor de grote implementatie van Microsoft 365 for Enterprise hadden contoso Windows-compatibele Pc's en apparaten met een menging van Windows 7 (10%), Windows 8,1 (65%) en Windows 10 (25%).</span><span class="sxs-lookup"><span data-stu-id="1c9dc-104">Prior to the wide rollout of Microsoft 365 for enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%).</span></span> <span data-ttu-id="1c9dc-105">Contoso wilde haar pc’s upgraden, omdat Windows 10 Enterprise gebruikmaakt van geavanceerde beveiliging en IT-overhead vermindert door automatische implementatie van updates.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-105">Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of advanced security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="1c9dc-106">Na het evalueren van hun infrastructuur en bedrijfsbehoeften identificeerde Contoso deze belangrijke vereisten voor de implementatie:</span><span class="sxs-lookup"><span data-stu-id="1c9dc-106">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="1c9dc-107">Zoveel mogelijk pc’s en apparaten moeten Windows 10 Enterprise uitvoeren</span><span class="sxs-lookup"><span data-stu-id="1c9dc-107">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="1c9dc-108">De implementatie van de in-place upgrades gebruikt de bestaande Configuration Manager-infrastructuur</span><span class="sxs-lookup"><span data-stu-id="1c9dc-108">Rollout of the in-place upgrades leverages existing Configuration Manager infrastructure</span></span>
- <span data-ttu-id="1c9dc-109">De controle over welke versie van Windows 10 Enterprise moet worden geïmplementeerd en updates moeten plaatsvinden middels ringen.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-109">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="1c9dc-110">Pc’s en apparaten moeten up-to-date blijven met minimale administratieve IT-kosten en minimale overlast voor eindgebruikers</span><span class="sxs-lookup"><span data-stu-id="1c9dc-110">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="1c9dc-111">Up-to-date wordt gedefinieerd als de ondersteunde versie van Windows 10 Enterprise die voldoet aan de bedrijfsbehoeften van Contoso. Dit hoeft niet te betekenen dat alle Windows-compatibele pc’s de nieuwste versie van Windows 10 Enterprise uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-111">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="1c9dc-112">Implementatiehulpmiddelen</span><span class="sxs-lookup"><span data-stu-id="1c9dc-112">Deployment tools</span></span>

<span data-ttu-id="1c9dc-113">Voorafgaand en tijdens de in-place upgrades van Windows 10 Enterprise gebruikte Contoso de volgende oplossingen van Windows Analytics:</span><span class="sxs-lookup"><span data-stu-id="1c9dc-113">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="1c9dc-114">Gereedheidscontroles voor upgrades</span><span class="sxs-lookup"><span data-stu-id="1c9dc-114">Upgrade Readiness</span></span>  

  <span data-ttu-id="1c9dc-115">Hiermee worden systeem-, toepassings- en stuurprogrammagagevens verzameld voor analyses en vervolgens compatibiliteitsproblemen die een upgrade kunnen blokkeren en voorgestelde oplossingen van bij Microsoft bekende problemen geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-115">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="1c9dc-116">Naleving van updates</span><span class="sxs-lookup"><span data-stu-id="1c9dc-116">Update Compliance</span></span>  

  <span data-ttu-id="1c9dc-117">Geeft de status van uw apparaten weer inzake de Windows-updates, zodat u er zeker van kunt zijn dat ze de meest recente updates hebben.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-117">Shows you the state of your devices with respect to the Windows updates so that you can ensure that they are on the most current updates as appropriate.</span></span>

- <span data-ttu-id="1c9dc-118">Apparaatstatus</span><span class="sxs-lookup"><span data-stu-id="1c9dc-118">Device Health</span></span>  

  <span data-ttu-id="1c9dc-119">Hiermee worden apparaten geïdentificeerd die regelmatig vastlopen en die daarom mogelijk opnieuw moeten worden opgebouwd of vervangen en stuurprogramma’s die de oorzaak zijn van het vastlopen, met suggesties van alternatieve versies van die stuurprogramma’s, waardoor apparaten minder vaak vastlopen.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-119">Identifies devices that crash frequently, and therefore might need to be rebuilt or replaced and device drivers that are causing device crashes, with suggestions of alternative versions of those drivers that might reduce the number of crashes.</span></span> <span data-ttu-id="1c9dc-120">Hiermee worden meldingen weergegeven over onjuiste configuraties van Windows-gegevensbescherming en aanwijzingen naar de eindgebruikers verzonden.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-120">Provides notification of Windows Information Protection misconfigurations that send prompts to end users.</span></span>
 
<span data-ttu-id="1c9dc-121">Contoso heeft een bestaande Configuration Manager-infrastructuur (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="1c9dc-121">Contoso has an existing Configuration Manager (Current Branch) infrastructure.</span></span> <span data-ttu-id="1c9dc-122">Configuration Manager is schaalbaar voor grote omgevingen en biedt uitgebreide controle over installatie, updates en instellingen.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-122">Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings.</span></span> <span data-ttu-id="1c9dc-123">Er zijn ook ingebouwde functies waarmee het eenvoudiger en efficiënter wordt om Windows 10 Enterprise te implementeren en te beheren.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-123">It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="1c9dc-124">Planningsproces</span><span class="sxs-lookup"><span data-stu-id="1c9dc-124">Planning process</span></span>

<span data-ttu-id="1c9dc-125">Voorafgaand aan de implementatie definieerde Contoso de volgende ringen:</span><span class="sxs-lookup"><span data-stu-id="1c9dc-125">Prior to deployment, Contoso defined the following rings:</span></span>

- <span data-ttu-id="1c9dc-126">Drie ringen voor validatie- en implementatiefasen</span><span class="sxs-lookup"><span data-stu-id="1c9dc-126">Three rings for validation and deployment staging</span></span> 
  - <span data-ttu-id="1c9dc-127">Eén voor preview-versies</span><span class="sxs-lookup"><span data-stu-id="1c9dc-127">One for preview builds</span></span> 
  - <span data-ttu-id="1c9dc-128">Eén voor nieuwe release-versies</span><span class="sxs-lookup"><span data-stu-id="1c9dc-128">One for new release builds</span></span>
  - <span data-ttu-id="1c9dc-129">Eén voor een eerdere versie</span><span class="sxs-lookup"><span data-stu-id="1c9dc-129">One for a previous build</span></span> 
- <span data-ttu-id="1c9dc-130">Eén ring voor brede implementatie van Windows 10 Enterprise op basis van gegevens van de validatieringen</span><span class="sxs-lookup"><span data-stu-id="1c9dc-130">One ring for broad deployment of Windows 10 Enterprise based on data from the validation rings</span></span>

<span data-ttu-id="1c9dc-131">Contoso gebruikte ook de Windows Analytics-oplossing Gereedheidscontrole voor upgrades om de geïnstalleerde apps en de compatibiliteit met Windows 10 Enterprise vast te stellen.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-131">Contoso also used the Upgrade Readiness solution of Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="1c9dc-132">Implementatieproces</span><span class="sxs-lookup"><span data-stu-id="1c9dc-132">Deployment process</span></span>

<span data-ttu-id="1c9dc-133">Contoso implementeerde het volgende proces, met de aanbevelingen van Microsoft voor aanbevolen procedures om de implementatie van de in-place upgrade van Windows 10 Enterprise te voltooien:</span><span class="sxs-lookup"><span data-stu-id="1c9dc-133">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="1c9dc-134">Peer-cache voor Configuration Manager werd ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-134">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="1c9dc-135">Aangepaste Windows-pakketten werden gemaakt op basis van images van het Servicecentrum voor volumelicenties.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-135">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="1c9dc-136">Configuration Manager werd gebruikt om de Windows-pakketten te implementeren naar distributiepunten in hun netwerk en builds gedistribueerd naar de drie ringen voor validatie- en implementatiefasen.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-136">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging rings.</span></span>
4. <span data-ttu-id="1c9dc-137">Evaluatie werd uitgevoerd voor het slagen van de implementatie op pc’s en apparaten in de drie ringen voor validatie- en implementatiefasen met de Windows Analytics-oplossingen Apparaatstatus en Naleving van updates.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-137">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="1c9dc-138">Op basis van de informatie van Windows Analytics bepaalde Contoso de versie van Windows 10 Enterprise die in de brede implementatiering moest worden geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-138">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment ring.</span></span>
6. <span data-ttu-id="1c9dc-139">De takenreeksen voor implementatie werden uitgevoerd voor het implementeren van de geselecteerde Windows-pakketten in de brede implementatiering.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-139">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment ring.</span></span>
7. <span data-ttu-id="1c9dc-140">Pc’s en apparaten werden bewaakt in de brede implementatiering met de oplossingen Apparaatstatus en Naleving van updates om problemen op te lossen.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-140">Monitored PCs and devices in the broad deployment ring using the Device Health and Update Compliance solutions to address issues.</span></span>

<span data-ttu-id="1c9dc-141">Dit is de implementatie-architectuur van in-place upgrades en doorlopende updates van Contoso.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-141">Here is Contoso’s in-place upgrade and ongoing updates deployment architecture.</span></span>

![Implementatie-architectuur van Windows 10 Enterprise van Contoso](../media/contoso-win10/contoso-win10-fig1.png)

<span data-ttu-id="1c9dc-143">Deze infrastructuur bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="1c9dc-143">This infrastructure consists of:</span></span>

- <span data-ttu-id="1c9dc-144">Configuration Manager, die:</span><span class="sxs-lookup"><span data-stu-id="1c9dc-144">Configuration Manager, which:</span></span>
  - <span data-ttu-id="1c9dc-145">images ophaalt voor Windows 10 Enterprise-pakketten van het Microsoft Servicecentrum voor volumelicenties in het Microsoft-netwerk.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-145">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="1c9dc-146">het centrale beheerpunt is voor implementatiepakketten.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-146">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="1c9dc-147">Regionale distributiepunten die zich normaliter in de regionale hub-kantoren van Contoso bevinden.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-147">Regional distribution points that are typically located in Contoso’s regional hub offices.</span></span>
- <span data-ttu-id="1c9dc-148">Windows-pc’s en -apparaten op verschillende locaties die de implementatiepakketten ontvangen en installeren voor de in-place upgrade of doorlopende updates bij ringleden.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-148">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on ring membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="1c9dc-149">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="1c9dc-149">Next step</span></span>

<span data-ttu-id="1c9dc-150">[Lees](contoso-o365pp.md) hier hoe Contoso zijn infrastructuur voor Configuratiebeheer gebruikt voor het implementeren en onderhouden van Microsoft 365-apps voor ondernemingen in de hele organisatie.</span><span class="sxs-lookup"><span data-stu-id="1c9dc-150">[Learn](contoso-o365pp.md) how Contoso is leveraging its Configuration Manager infrastructure to deploy and keep current Microsoft 365 Apps for enterprise across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="1c9dc-151">Zie ook</span><span class="sxs-lookup"><span data-stu-id="1c9dc-151">See also</span></span>

[<span data-ttu-id="1c9dc-152">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1c9dc-152">Windows 10 Enterprise</span></span>](https://docs.microsoft.com/windows/deployment/)

[<span data-ttu-id="1c9dc-153">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="1c9dc-153">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="1c9dc-154">Testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="1c9dc-154">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
