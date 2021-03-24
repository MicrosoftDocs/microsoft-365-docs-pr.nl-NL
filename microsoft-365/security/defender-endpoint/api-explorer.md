---
title: API Explorer in Microsoft Defender ATP
ms.reviewer: ''
description: De API Explorer gebruiken voor het maken en uitvoeren van API-query's, testen en verzenden van aanvragen voor een beschikbare API
keywords: api, verkenner, verzenden, aanvragen, ontvangen, posten,
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
ms.openlocfilehash: 0cfe5227d5d1cdb1f1f4eaea2c859937d7e75264
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058793"
---
# <a name="api-explorer"></a><span data-ttu-id="c97b1-104">API Explorer</span><span class="sxs-lookup"><span data-stu-id="c97b1-104">API Explorer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c97b1-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c97b1-105">**Applies to:**</span></span>
- [<span data-ttu-id="c97b1-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="c97b1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


<span data-ttu-id="c97b1-107">De Microsoft Defender voor Endpoint API Explorer is een hulpmiddel waarmee u verschillende API's voor Defender voor eindpunten interactief kunt verkennen.</span><span class="sxs-lookup"><span data-stu-id="c97b1-107">The Microsoft Defender for Endpoint API Explorer is a tool that helps you explore various Defender for Endpoint APIs interactively.</span></span> 

<span data-ttu-id="c97b1-108">Met API Explorer kunt u eenvoudig API-query's maken, testen en verzenden voor alle beschikbare Defender voor Endpoint API-eindpunten.</span><span class="sxs-lookup"><span data-stu-id="c97b1-108">The API Explorer makes it easy to construct and do API queries, test, and send requests for any available Defender for Endpoint API endpoint.</span></span> <span data-ttu-id="c97b1-109">Gebruik de API Explorer om acties uit te voeren of gegevens te vinden die mogelijk nog niet beschikbaar zijn via de gebruikersinterface.</span><span class="sxs-lookup"><span data-stu-id="c97b1-109">Use the API Explorer to take actions or find data that might not yet be available through the user interface.</span></span>

<span data-ttu-id="c97b1-110">Het hulpprogramma is handig tijdens het ontwikkelen van apps.</span><span class="sxs-lookup"><span data-stu-id="c97b1-110">The tool is useful during app development.</span></span> <span data-ttu-id="c97b1-111">Hiermee kunt u API-query's uitvoeren die uw gebruikerstoegangsinstellingen respecteren, waardoor u minder toegangstokens hoeft te genereren.</span><span class="sxs-lookup"><span data-stu-id="c97b1-111">It allows you to perform API queries that respect your user access settings, reducing the need to generate access tokens.</span></span>

<span data-ttu-id="c97b1-112">U kunt het hulpprogramma ook gebruiken om de galerie met voorbeeldquery's te verkennen, resultatencodevoorbeelden te kopiëren en foutopsporingsgegevens te genereren.</span><span class="sxs-lookup"><span data-stu-id="c97b1-112">You can also use the tool to explore the gallery of sample queries, copy result code samples, and generate debug information.</span></span>

<span data-ttu-id="c97b1-113">Met de API Explorer kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="c97b1-113">With the API Explorer, you can:</span></span>

- <span data-ttu-id="c97b1-114">Aanvragen voor een methode uitvoeren en antwoorden in realtime bekijken</span><span class="sxs-lookup"><span data-stu-id="c97b1-114">Run requests for any method and see responses in real-time</span></span>
- <span data-ttu-id="c97b1-115">Blader snel door de API-voorbeelden en ontdek welke parameters ze ondersteunen</span><span class="sxs-lookup"><span data-stu-id="c97b1-115">Quickly browse through the API samples and learn what parameters they support</span></span>
- <span data-ttu-id="c97b1-116">Maak API-oproepen met gemak; u hoeft zich niet te verifiëren buiten de aanmelding van de beheerportal</span><span class="sxs-lookup"><span data-stu-id="c97b1-116">Make API calls with ease; no need to authenticate beyond the management portal sign in</span></span>

## <a name="access-api-explorer"></a><span data-ttu-id="c97b1-117">Access API Explorer</span><span class="sxs-lookup"><span data-stu-id="c97b1-117">Access API Explorer</span></span>

<span data-ttu-id="c97b1-118">Selecteer in het linkernavigatiemenu **Partners &**  >  **API-API Explorer**.</span><span class="sxs-lookup"><span data-stu-id="c97b1-118">From the left navigation menu, select **Partners & APIs** > **API Explorer**.</span></span>

## <a name="supported-apis"></a><span data-ttu-id="c97b1-119">Ondersteunde API's</span><span class="sxs-lookup"><span data-stu-id="c97b1-119">Supported APIs</span></span>

<span data-ttu-id="c97b1-120">API Explorer ondersteunt alle API's die worden aangeboden door Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="c97b1-120">API Explorer supports all the APIs offered by Defender for Endpoint.</span></span>
  
<span data-ttu-id="c97b1-121">De lijst met ondersteunde API's is beschikbaar in de [DOCUMENTATIE van API's.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c97b1-121">The list of supported APIs is available in the [APIs documentation](apis-intro.md).</span></span> 

## <a name="get-started-with-the-api-explorer"></a><span data-ttu-id="c97b1-122">Aan de slag met de API Explorer</span><span class="sxs-lookup"><span data-stu-id="c97b1-122">Get started with the API Explorer</span></span>

1. <span data-ttu-id="c97b1-123">In het linkerdeelvenster ziet u een lijst met voorbeeldaanvragen die u kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c97b1-123">In the left pane, there is a list of sample requests that you can use.</span></span> 
2. <span data-ttu-id="c97b1-124">Volg de koppelingen en klik op **Query uitvoeren.**</span><span class="sxs-lookup"><span data-stu-id="c97b1-124">Follow the links and click **Run query**.</span></span> 

<span data-ttu-id="c97b1-125">Voor sommige voorbeelden moet mogelijk een parameter in de URL worden opgegeven, bijvoorbeeld {machine-ID}.</span><span class="sxs-lookup"><span data-stu-id="c97b1-125">Some of the samples may require specifying a parameter in the URL, for example, {machine- ID}.</span></span>

## <a name="faq"></a><span data-ttu-id="c97b1-126">Veelgestelde vragen</span><span class="sxs-lookup"><span data-stu-id="c97b1-126">FAQ</span></span>

<span data-ttu-id="c97b1-127">**Moet ik een API-token hebben om de API Explorer te kunnen gebruiken?**</span><span class="sxs-lookup"><span data-stu-id="c97b1-127">**Do I need to have an API token to use the API Explorer?**</span></span> <br>
<span data-ttu-id="c97b1-128">Referenties voor toegang tot een API zijn niet nodig.</span><span class="sxs-lookup"><span data-stu-id="c97b1-128">Credentials to access an API aren't needed.</span></span> <span data-ttu-id="c97b1-129">De API Explorer gebruikt het token van de Defender for Endpoint Management Portal wanneer deze een aanvraag indient.</span><span class="sxs-lookup"><span data-stu-id="c97b1-129">The API Explorer uses the Defender for Endpoint management portal token whenever it makes a request.</span></span>

<span data-ttu-id="c97b1-130">De aanmeldingsreferentie voor gebruikersverificatie wordt gebruikt om te controleren of de API Explorer gemachtigd is om namens u toegang te krijgen tot gegevens.</span><span class="sxs-lookup"><span data-stu-id="c97b1-130">The logged-in user authentication credential is used to verify that the API Explorer is authorized to access data on your behalf.</span></span>

<span data-ttu-id="c97b1-131">Specifieke API-aanvragen zijn beperkt op basis van uw RBAC-bevoegdheden.</span><span class="sxs-lookup"><span data-stu-id="c97b1-131">Specific API requests are limited based on your RBAC privileges.</span></span> <span data-ttu-id="c97b1-132">Een aanvraag voor 'Indicator verzenden' is bijvoorbeeld beperkt tot de rol van beveiligingsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="c97b1-132">For example, a request to "Submit indicator" is limited to the security admin role.</span></span> 
