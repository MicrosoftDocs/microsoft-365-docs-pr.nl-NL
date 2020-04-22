---
title: Windows 10 Enterprise-infrastructuur voor Microsoft 365 Enterprise
description: Biedt een advies op hoog niveau over de stappen die u nodig hebt om Windows 10 Enterprise op pc's te implementeren als onderdeel van Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-documentatie, Windows 10 Enterprise, implementatie
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/28/2019
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: 53c38ba2e915cd439c8d7629bc7f9cd56ebc8647
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636673"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="69a85-104">Fase 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="69a85-104">Phase 3: Windows 10 Enterprise</span></span>

![Fase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="69a85-106">Microsoft 365 Enterprise bevat Windows 10 Enterprise, waarmee u de tools hebt om meer te doen en veilig te blijven.</span><span class="sxs-lookup"><span data-stu-id="69a85-106">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure.</span></span> <span data-ttu-id="69a85-107">Windows 10 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="69a85-107">Windows 10 Enterprise:</span></span>

- <span data-ttu-id="69a85-108">**Is geïntegreerd voor eenvoud** - Benut de kracht van de cloud om de complexiteit van het beheer van de moderne IT-apparaatomgeving te verminderen, ongeacht de grootte.</span><span class="sxs-lookup"><span data-stu-id="69a85-108">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="69a85-109">**Heeft intelligente beveiliging** - Het is de veiligste release van Windows ooit, met intelligente beveiligingsmogelijkheden die zijn ontworpen om samen te werken om uw organisatie beter te beschermen.</span><span class="sxs-lookup"><span data-stu-id="69a85-109">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="69a85-110">**Maakt creativiteit en teamwork mogelijk** - ontgrendelt creativiteit en teamwork om de meest productieve ervaring te bieden waar zowel gebruikers als IT dol op zullen zijn.</span><span class="sxs-lookup"><span data-stu-id="69a85-110">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="69a85-111">U moet inzicht krijgen in de verschillende manieren waarop u het Windows 10-besturingssysteem implementeren en de juiste optie voor uw organisatie kiezen.</span><span class="sxs-lookup"><span data-stu-id="69a85-111">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization.</span></span> <span data-ttu-id="69a85-112">Afhankelijk van uw Microsoft 365 Enterprise-abonnement zijn er ook Windows 10-services en beveiligingsfuncties die u moet configureren om het meeste uit Windows 10 te halen.</span><span class="sxs-lookup"><span data-stu-id="69a85-112">Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

>[!Note]
><span data-ttu-id="69a85-113">Zie het [Modern Desktop Deployment Center](https://aka.ms/howtoshift)om zowel Windows 10 Enterprise- als Microsoft 365-apps voor bedrijven samen te implementeren en over te schakelen naar een moderne [desktop.](https://www.microsoft.com/microsoft-365/modern-desktop)</span><span class="sxs-lookup"><span data-stu-id="69a85-113">To deploy both Windows 10 Enterprise and Microsoft 365 Apps for enterprise together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](https://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="69a85-114">Windows 10-implementatie</span><span class="sxs-lookup"><span data-stu-id="69a85-114">Windows 10 deployment</span></span>

<span data-ttu-id="69a85-115">Er zijn meerdere manieren waarop u Windows 10 Enterprise voor uw organisatie implementeren.</span><span class="sxs-lookup"><span data-stu-id="69a85-115">There are multiple ways you can deploy Windows 10 Enterprise for your organization.</span></span> <span data-ttu-id="69a85-116">Hier richten we ons op hoe u een Windows 10 Enterprise-afbeelding configureren en implementeren via deze moderne implementatiescenario's.</span><span class="sxs-lookup"><span data-stu-id="69a85-116">Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="69a85-117">Implementatiescenario</span><span class="sxs-lookup"><span data-stu-id="69a85-117">Deployment scenario</span></span> | <span data-ttu-id="69a85-118">Wanneer te gebruiken</span><span class="sxs-lookup"><span data-stu-id="69a85-118">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="69a85-119">Microsoft Endpoint Configuration Manager gebruiken als een in-place upgrade</span><span class="sxs-lookup"><span data-stu-id="69a85-119">Using Microsoft Endpoint Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="69a85-120">Selecteer deze optie als u Windows 7- of Windows 8.1-computers moet upgraden naar de <a href="https://aka.ms/windows-10-release-information" target="_blank">huidige versie</a> van Windows 10 Enterprise en uw computers momenteel worden beheerd met Configuration <a href="https://docs.microsoft.com/configmgr/core/understand/introduction" target="_blank">Manager (Huidige branch).</a></span><span class="sxs-lookup"><span data-stu-id="69a85-120">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://docs.microsoft.com/configmgr/core/understand/introduction" target="_blank">Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="69a85-121">Windows Autopilot gebruiken</span><span class="sxs-lookup"><span data-stu-id="69a85-121">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="69a85-122">Selecteer deze optie als u nieuwe Windows-computers instelt waarop Windows 10 Enterprise, versie 1703 of hoger is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="69a85-122">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed.</span></span> <span data-ttu-id="69a85-123">Eindgebruikers starten de installatie met de gewenste configuratie door hun rechten van het werk- of schoolaccount in te voeren.</span><span class="sxs-lookup"><span data-stu-id="69a85-123">End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="69a85-124">Als deze implementatiescenario's niet voldoen aan de behoeften van uw organisatie, u meer te weten komen over andere scenario's en inzicht krijgen in de mogelijkheden en beperkingen van elk van deze [scenario's in Windows 10-implementatiescenario's.](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)</span><span class="sxs-lookup"><span data-stu-id="69a85-124">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="69a85-125">U kunt ook zelf <a href="https://aka.ms/planforwin10deployment" target="_blank">de implementatie van Windows 10 plannen</a>.</span><span class="sxs-lookup"><span data-stu-id="69a85-125">You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="69a85-126">U meer informatie over Windows 10 lezen met deze artikelen:</span><span class="sxs-lookup"><span data-stu-id="69a85-126">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="69a85-127">Microsoft 365 Enterprise-productpagina</span><span class="sxs-lookup"><span data-stu-id="69a85-127">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="69a85-128">Windows 10</span><span class="sxs-lookup"><span data-stu-id="69a85-128">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="69a85-129">Windows 10 implementeren en bijwerken</span><span class="sxs-lookup"><span data-stu-id="69a85-129">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="69a85-130">Aanvullende services en functies</span><span class="sxs-lookup"><span data-stu-id="69a85-130">Additional services and features</span></span>
<span data-ttu-id="69a85-131">Als onderdeel van uw implementatie van Windows 10 Enterprise u deze extra services en functies toevoegen.</span><span class="sxs-lookup"><span data-stu-id="69a85-131">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="windows-analytics"></a><span data-ttu-id="69a85-132">Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="69a85-132">Windows Analytics</span></span>

<span data-ttu-id="69a85-133">Windows gebruikt diagnostische gegevens om uitgebreide, bruikbare informatie te bieden om u te helpen diepgaande inzichten te krijgen in de operationele efficiëntie en de status van Windows 10-apparaten in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="69a85-133">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="69a85-134">Gereedheid voor upgrade - Met de gereedheid voor upgrade u overstappen naar Windows 10 en op de hoogte blijven van nieuwe Windows 10-functie-updates.</span><span class="sxs-lookup"><span data-stu-id="69a85-134">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="69a85-135">Compliance bijwerken - Update Compliance is gericht op de IT-beheerder die een holistisch beeld wil krijgen van al hun Windows 10-apparaten, zonder extra infrastructuurvereisten.</span><span class="sxs-lookup"><span data-stu-id="69a85-135">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="69a85-136">Apparaatstatus - U apparaatstatus gebruiken om problemen met problemen met de gevolgen van eindgebruikers proactief op te sporen en op te lossen.</span><span class="sxs-lookup"><span data-stu-id="69a85-136">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="69a85-137">Zie [Overzicht van Windows Analytics](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="69a85-137">See [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="69a85-138">Windows-beveiliging</span><span class="sxs-lookup"><span data-stu-id="69a85-138">Windows security</span></span>

<span data-ttu-id="69a85-139">Windows 10 biedt functies om u te beschermen tegen bedreigingen, u te helpen uw apparaten te beveiligen en te helpen bij toegangscontrole.</span><span class="sxs-lookup"><span data-stu-id="69a85-139">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control.</span></span> <span data-ttu-id="69a85-140">Met Windows 10 krijgt u kritieke beveiligingsfuncties die uw apparaat vanaf het begin beschermen.</span><span class="sxs-lookup"><span data-stu-id="69a85-140">With Windows 10, you get critical security features that protect your device right from the start.</span></span> <span data-ttu-id="69a85-141">Microsoft 365 E3 voegt beveiligingsfuncties toe, zoals Windows Hello for Business, Windows Defender Application Control en Windows Information Protection.</span><span class="sxs-lookup"><span data-stu-id="69a85-141">Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection.</span></span> <span data-ttu-id="69a85-142">Met Microsoft 365 E5 krijgt u alle bescherming van Microsoft 365 E3-beveiliging plus cloudgebaseerde beveiligingsfuncties en Microsoft Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="69a85-142">With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Microsoft Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="69a85-143">Zie [Stap 5: Windows 10 Enterprise-beveiligingsfuncties implementeren](windows10-enable-security-features.md)voor meer informatie over de beveiligingsfuncties die u met Windows 10 Enterprise krijgt en voor meer informatie over de beveiligingsfuncties die u met Windows 10 Enterprise implementeren, beheren, configureren en oplossen.</span><span class="sxs-lookup"><span data-stu-id="69a85-143">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key security features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="69a85-144">Hoe Microsoft omgaat met Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="69a85-144">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="69a85-145">Neem een kijkje in Microsoft en ontdek hoe het bedrijf [Windows 10 Enterprise heeft geïmplementeerd en sterke verificatie, Intune en Microsoft Defender ATP gebruikt.](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6)</span><span class="sxs-lookup"><span data-stu-id="69a85-145">Peek inside Microsoft and learn how the company [deployed Windows 10 Enterprise and is using strong authentication, Intune, and Microsoft Defender ATP](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="69a85-146">Hoe Contoso Microsoft 365 Enterprise gebruikt</span><span class="sxs-lookup"><span data-stu-id="69a85-146">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="69a85-147">Bekijk hoe de Contoso Corporation, een fictief maar representatief multinationaal bedrijf, [Windows 10 Enterprise heeft geïmplementeerd.](contoso-win10.md)</span><span class="sxs-lookup"><span data-stu-id="69a85-147">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="69a85-149">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="69a85-149">Next step</span></span>

|||
|:-------|:-----|
|![Stap 1](../media/stepnumbers/Step1.png)| [<span data-ttu-id="69a85-151">Uw organisatie voorbereiden op Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="69a85-151">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
