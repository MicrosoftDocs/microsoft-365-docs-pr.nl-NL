---
title: Overzicht van beheer en API's
ms.reviewer: ''
description: Meer informatie over de beheerhulpmiddelen en API-categorieën in Microsoft Defender voor Eindpunt
keywords: onboarding, api, siem, rbac, access, portal, integratie, onderzoek, antwoord, entiteiten, entiteit, gebruikerscontext, toepassingscontext, streaming
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a57cebd2cb7d35f968ed9ddfa4d9215eac2182d6
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934451"
---
# <a name="overview-of-management-and-apis"></a><span data-ttu-id="27ec6-104">Overzicht van beheer en API's</span><span class="sxs-lookup"><span data-stu-id="27ec6-104">Overview of management and APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="27ec6-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="27ec6-105">**Applies to:**</span></span>
- [<span data-ttu-id="27ec6-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="27ec6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="27ec6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27ec6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="27ec6-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="27ec6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="27ec6-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="27ec6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mgt-apis-abovefoldlink)


<span data-ttu-id="27ec6-110">Defender voor Eindpunt ondersteunt een groot aantal opties om ervoor te zorgen dat klanten het platform eenvoudig kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="27ec6-110">Defender for Endpoint supports a wide variety of options to ensure that customers can easily adopt the platform.</span></span> 

<span data-ttu-id="27ec6-111">Als u erkent dat klantomgevingen en -structuren kunnen variëren, is Defender for Endpoint gemaakt met flexibiliteit en gedetailleerde controle om aan verschillende klantvereisten te voldoen.</span><span class="sxs-lookup"><span data-stu-id="27ec6-111">Acknowledging that customer environments and structures can vary, Defender for Endpoint was created with flexibility and granular control to fit varying customer requirements.</span></span> 

## <a name="endpoint-onboarding-and-portal-access"></a><span data-ttu-id="27ec6-112">Onboarding van eindpunten en portaltoegang</span><span class="sxs-lookup"><span data-stu-id="27ec6-112">Endpoint onboarding and portal access</span></span> 

<span data-ttu-id="27ec6-113">Apparaat onboarding is volledig geïntegreerd in Microsoft Endpoint Manager en Microsoft Intune voor clientapparaten en Azure Defender voor serverapparaten, wat volledige end-to-end ervaring biedt met configuratie, implementatie en monitoring.</span><span class="sxs-lookup"><span data-stu-id="27ec6-113">Device onboarding is fully integrated into Microsoft Endpoint Manager and Microsoft Intune for client devices and Azure Defender for server devices, providing complete end-to-end experience of configuration, deployment, and monitoring.</span></span> <span data-ttu-id="27ec6-114">Daarnaast ondersteunt Microsoft Defender voor Eindpunt groepsbeleid en andere hulpprogramma's van derden die worden gebruikt voor apparatenbeheer.</span><span class="sxs-lookup"><span data-stu-id="27ec6-114">In addition, Microsoft Defender for Endpoint supports Group Policy and other third-party tools used for devices management.</span></span>

<span data-ttu-id="27ec6-115">Defender voor Eindpunt biedt een fijnkorrelige controle over wat gebruikers met toegang tot de portal kunnen zien en doen via de flexibiliteit van op rollen gebaseerde toegangsbeheer (RBAC).</span><span class="sxs-lookup"><span data-stu-id="27ec6-115">Defender for Endpoint provides fine-grained control over what users with access to the portal can see and do through the flexibility of role-based access control (RBAC).</span></span> <span data-ttu-id="27ec6-116">Het RBAC-model ondersteunt alle smaken van de structuur van beveiligingsteams:</span><span class="sxs-lookup"><span data-stu-id="27ec6-116">The RBAC model supports all flavors of security teams structure:</span></span>
- <span data-ttu-id="27ec6-117">Wereldwijd verspreide organisaties en beveiligingsteams</span><span class="sxs-lookup"><span data-stu-id="27ec6-117">Globally distributed organizations and security teams</span></span>
- <span data-ttu-id="27ec6-118">Teams voor beveiligingsbewerkingen met laagge lagenmodel</span><span class="sxs-lookup"><span data-stu-id="27ec6-118">Tiered model security operations teams</span></span>
- <span data-ttu-id="27ec6-119">Volledig gescheiden afdelingen met één gecentraliseerde teams voor globale beveiligingsbewerkingen</span><span class="sxs-lookup"><span data-stu-id="27ec6-119">Fully segregated divisions with single centralized global security operations teams</span></span> 

## <a name="available-apis"></a><span data-ttu-id="27ec6-120">Beschikbare API's</span><span class="sxs-lookup"><span data-stu-id="27ec6-120">Available APIs</span></span>
<span data-ttu-id="27ec6-121">De Microsoft Defender voor Eindpunt-oplossing is gebouwd op een platform dat klaar is voor integratie.</span><span class="sxs-lookup"><span data-stu-id="27ec6-121">The Microsoft Defender for Endpoint solution is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="27ec6-122">In Defender voor Eindpunt worden veel van de gegevens en acties via een set programmatische API's beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="27ec6-122">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="27ec6-123">Met deze API's kunt u werkstromen automatiseren en innoveren op basis van De mogelijkheden van Defender voor eindpunten.</span><span class="sxs-lookup"><span data-stu-id="27ec6-123">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span>

![Afbeelding van de beschikbare API en integratie in Microsoft Defender voor Eindpunt](images/mdatp-apis.png)  

<span data-ttu-id="27ec6-125">De API's van Defender voor eindpunten kunnen worden gegroepeerd in drie:</span><span class="sxs-lookup"><span data-stu-id="27ec6-125">The Defender for Endpoint APIs can be grouped into three:</span></span>
- <span data-ttu-id="27ec6-126">Microsoft Defender voor eindpunt-API's</span><span class="sxs-lookup"><span data-stu-id="27ec6-126">Microsoft Defender for Endpoint APIs</span></span> 
- <span data-ttu-id="27ec6-127">API voor onbewerkte voor gegevensstreaming</span><span class="sxs-lookup"><span data-stu-id="27ec6-127">Raw data streaming API</span></span>
- <span data-ttu-id="27ec6-128">SIEM-integratie</span><span class="sxs-lookup"><span data-stu-id="27ec6-128">SIEM integration</span></span>

## <a name="microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="27ec6-129">Microsoft Defender voor eindpunt-API's</span><span class="sxs-lookup"><span data-stu-id="27ec6-129">Microsoft Defender for Endpoint APIs</span></span>

<span data-ttu-id="27ec6-130">Defender voor Eindpunt biedt een gelaagd API-model met gegevens en mogelijkheden in een gestructureerd, duidelijk en eenvoudig te gebruiken model, dat wordt belicht via een standaard azure AD-verificatie- en autorisatiemodel dat toegang biedt in context van gebruikers of SaaS-toepassingen.</span><span class="sxs-lookup"><span data-stu-id="27ec6-130">Defender for Endpoint offers a layered API model exposing data and capabilities in a structured, clear, and easy to use model, exposed through a standard Azure  AD-based authentication and authorization model allowing access in context of users or SaaS applications.</span></span> <span data-ttu-id="27ec6-131">Het API-model is ontworpen om entiteiten en mogelijkheden in een consistente vorm weer te geven.</span><span class="sxs-lookup"><span data-stu-id="27ec6-131">The API model was designed to expose entities and capabilities in a consistent form.</span></span> 

<span data-ttu-id="27ec6-132">Bekijk deze video voor een kort overzicht van de API's van Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="27ec6-132">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="27ec6-133">Met de **Onderzoeks-API** wordt de rijkdom van Defender voor Eindpunt beschreven, waarbij berekende of 'geprofileerde' entiteiten (bijvoorbeeld apparaat, gebruiker en bestand) en discrete gebeurtenissen (bijvoorbeeld procescreatie en bestandscreatie) worden beschreven, waarbij doorgaans een gedrag wordt beschreven dat betrekking heeft op een entiteit, waardoor toegang tot gegevens wordt mogelijk gemaakt via onderzoeksinterfaces die een querytoegang tot gegevens mogelijk maken.</span><span class="sxs-lookup"><span data-stu-id="27ec6-133">The **Investigation API** exposes the richness of Defender for Endpoint - exposing calculated or 'profiled' entities (for example, device, user, and file) and discrete events (for example, process creation and file creation) which typically describes a behavior related to an entity, enabling access to data via investigation interfaces allowing a query-based access to data.</span></span> <span data-ttu-id="27ec6-134">Zie Ondersteunde [API's voor meer informatie.](exposed-apis-list.md)</span><span class="sxs-lookup"><span data-stu-id="27ec6-134">For more information, see [Supported APIs](exposed-apis-list.md).</span></span>

<span data-ttu-id="27ec6-135">De **Response API** biedt de mogelijkheid om acties uit te voeren in de service en op apparaten, zodat klanten indicatoren kunnen opnemen, instellingen kunnen beheren, de status van een waarschuwing kunnen beheren en reactieacties kunnen uitvoeren op apparaten die programmatisch zijn, zoals apparaten isoleren van het netwerk, quarantainebestanden en andere apparaten.</span><span class="sxs-lookup"><span data-stu-id="27ec6-135">The **Response API** exposes the ability to take actions in the service and on devices, enabling customers to ingest indicators, manage settings, alert status, as well as take response actions on devices programmatically such as isolate devices from the network, quarantine files, and others.</span></span> 

## <a name="raw-data-streaming-api"></a><span data-ttu-id="27ec6-136">API voor onbewerkte voor gegevensstreaming</span><span class="sxs-lookup"><span data-stu-id="27ec6-136">Raw data streaming API</span></span> 
<span data-ttu-id="27ec6-137">Defender for Endpoint Raw Data Streaming API biedt klanten de mogelijkheid om realtime gebeurtenissen en waarschuwingen van hun exemplaren te verzenden terwijl ze binnen één gegevensstroom voorkomen, wat zorgt voor een lage latentie en een mechanisme voor hoge doorvoerbezorging.</span><span class="sxs-lookup"><span data-stu-id="27ec6-137">Defender for Endpoint raw data streaming API provides the ability for customers to ship real-time events and alerts from their instances as they occur within a single data stream, providing a low latency, high throughput delivery mechanism.</span></span>

<span data-ttu-id="27ec6-138">De gebeurtenisgegevens van Defender voor Eindpunt worden rechtstreeks naar Azure-opslag voor gegevensopslag op lange termijn of naar Azure Event Hubs voor gebruik door visualisatieservices of extra gegevensverwerkingsmotoren.</span><span class="sxs-lookup"><span data-stu-id="27ec6-138">The Defender for Endpoint event information is pushed directly to Azure storage for long-term data retention, or to Azure Event Hubs for consumption by visualization services or additional data processing engines.</span></span> 

<span data-ttu-id="27ec6-139">Zie Raw data streaming API voor meer [informatie.](raw-data-export.md)</span><span class="sxs-lookup"><span data-stu-id="27ec6-139">For more information, see [Raw data streaming API](raw-data-export.md).</span></span>


## <a name="siem-api"></a><span data-ttu-id="27ec6-140">SIEM-API</span><span class="sxs-lookup"><span data-stu-id="27ec6-140">SIEM API</span></span>
<span data-ttu-id="27ec6-141">Wanneer u beveiligingsgegevens en SIEM-integratie (Event Management) inschakelen, kunt u hiermee detecties uit het Microsoft Defender-beveiligingscentrum halen met behulp van uw SIEM-oplossing of door rechtstreeks verbinding te maken met de REST-API voor detecties.</span><span class="sxs-lookup"><span data-stu-id="27ec6-141">When you enable security information and event management (SIEM) integration, it allows you to pull detections from Microsoft Defender Security Center using your SIEM solution or by connecting directly to the detections REST API.</span></span> <span data-ttu-id="27ec6-142">Hiermee activeert u de sectie toegangsgegevens van de SIEM-verbindingslijn met vooraf ingevulde waarden en wordt er een toepassing gemaakt onder uw Azure Active Directory -tenant (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="27ec6-142">This activates the SIEM connector access details section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span> <span data-ttu-id="27ec6-143">Zie [SIEM-integratie voor meer informatie.](enable-siem-integration.md)</span><span class="sxs-lookup"><span data-stu-id="27ec6-143">For more information, see [SIEM integration](enable-siem-integration.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="27ec6-144">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="27ec6-144">Related topics</span></span>
- [<span data-ttu-id="27ec6-145">Toegang tot de API's van Microsoft Defender voor eindpunten </span><span class="sxs-lookup"><span data-stu-id="27ec6-145">Access the Microsoft Defender for Endpoint APIs </span></span>](apis-intro.md)
- [<span data-ttu-id="27ec6-146">Ondersteunde API's</span><span class="sxs-lookup"><span data-stu-id="27ec6-146">Supported APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="27ec6-147">Mogelijkheden voor technische partners</span><span class="sxs-lookup"><span data-stu-id="27ec6-147">Technical partner opportunities</span></span>](partner-integration.md)

