---
title: Problemen met de integratie van SIEM-hulpprogramma's oplossen in Microsoft Defender voor Eindpunt
description: Problemen oplossen die zich kunnen voordoen bij het gebruik van SIEM-hulpprogramma's met Microsoft Defender voor Eindpunt.
keywords: probleemoplossing, siem, clientgeheim, geheim
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 60220d00ca1b612564b72103b9206e3d6d89dc60
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689447"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a><span data-ttu-id="0f98c-104">Problemen met de integratie van SIEM-hulpprogramma's oplossen</span><span class="sxs-lookup"><span data-stu-id="0f98c-104">Troubleshoot SIEM tool integration issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0f98c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="0f98c-105">**Applies to:**</span></span>
- [<span data-ttu-id="0f98c-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="0f98c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0f98c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0f98c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="0f98c-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="0f98c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0f98c-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="0f98c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="0f98c-110">Mogelijk moet u problemen oplossen tijdens het trekken van detecties in uw SIEM-hulpprogramma's.</span><span class="sxs-lookup"><span data-stu-id="0f98c-110">You might need to troubleshoot issues while pulling detections in your SIEM tools.</span></span>

<span data-ttu-id="0f98c-111">Deze pagina bevat gedetailleerde stappen om problemen op te lossen die u mogelijk ondervindt.</span><span class="sxs-lookup"><span data-stu-id="0f98c-111">This page provides detailed steps to troubleshoot issues you might encounter.</span></span>


## <a name="learn-how-to-get-a-new-client-secret"></a><span data-ttu-id="0f98c-112">Meer informatie over het krijgen van een nieuw clientgeheim</span><span class="sxs-lookup"><span data-stu-id="0f98c-112">Learn how to get a new client secret</span></span>
<span data-ttu-id="0f98c-113">Als uw clientgeheim verloopt of als u de verstrekte kopie verkeerd hebt geplaatst wanneer u de siem-hulpprogrammatoepassing inschakelen, moet u een nieuw geheim krijgen.</span><span class="sxs-lookup"><span data-stu-id="0f98c-113">If your client secret expires or if you've misplaced the copy provided when you were enabling the SIEM tool application,  you'll need to get a new secret.</span></span>

1. <span data-ttu-id="0f98c-114">Meld u aan bij [de Azure-beheerportal.](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="0f98c-114">Login to the [Azure management portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="0f98c-115">Selecteer **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0f98c-115">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="0f98c-116">Selecteer uw tenant.</span><span class="sxs-lookup"><span data-stu-id="0f98c-116">Select your tenant.</span></span>

4. <span data-ttu-id="0f98c-117">Klik **op App-registraties.**</span><span class="sxs-lookup"><span data-stu-id="0f98c-117">Click **App registrations**.</span></span> <span data-ttu-id="0f98c-118">Selecteer vervolgens in de lijst met toepassingen de toepassing.</span><span class="sxs-lookup"><span data-stu-id="0f98c-118">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="0f98c-119">Selecteer **de** sectie Sleutels en geef vervolgens een sleutelbeschrijving op en geef de geldigheidsduur van de sleutel op.</span><span class="sxs-lookup"><span data-stu-id="0f98c-119">Select **Keys** section, then provide a key description and specify the key validity duration.</span></span>

6. <span data-ttu-id="0f98c-120">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0f98c-120">Click **Save**.</span></span> <span data-ttu-id="0f98c-121">De sleutelwaarde wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0f98c-121">The key value is displayed.</span></span>

7. <span data-ttu-id="0f98c-122">Kopieer de waarde en sla deze op een veilige plaats op.</span><span class="sxs-lookup"><span data-stu-id="0f98c-122">Copy the value and save it in a safe place.</span></span>


## <a name="error-when-getting-a-refresh-access-token"></a><span data-ttu-id="0f98c-123">Fout bij het verkrijgen van een vernieuwingstoegangs token</span><span class="sxs-lookup"><span data-stu-id="0f98c-123">Error when getting a refresh access token</span></span>
<span data-ttu-id="0f98c-124">Als u een fout ondervindt bij het gebruik van de hulpprogramma's threat intelligence API of SIEM, moet u antwoord-URL toevoegen voor relevante toepassing in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0f98c-124">If you encounter an error when trying to get a refresh token when using the threat intelligence API or SIEM tools, you'll need to add reply URL for relevant application in Azure Active Directory.</span></span>

1. <span data-ttu-id="0f98c-125">Meld u aan bij [de Azure-beheerportal.](https://ms.portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="0f98c-125">Login to the [Azure management portal](https://ms.portal.azure.com).</span></span>

2. <span data-ttu-id="0f98c-126">Selecteer **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0f98c-126">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="0f98c-127">Selecteer uw tenant.</span><span class="sxs-lookup"><span data-stu-id="0f98c-127">Select your tenant.</span></span>

4. <span data-ttu-id="0f98c-128">Klik **op App-registraties.**</span><span class="sxs-lookup"><span data-stu-id="0f98c-128">Click **App Registrations**.</span></span> <span data-ttu-id="0f98c-129">Selecteer vervolgens in de lijst met toepassingen de toepassing.</span><span class="sxs-lookup"><span data-stu-id="0f98c-129">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="0f98c-130">Voeg de volgende URL toe:</span><span class="sxs-lookup"><span data-stu-id="0f98c-130">Add the following URL:</span></span>
   - <span data-ttu-id="0f98c-131">Voor de Europese Unie: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="0f98c-131">For the European Union: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="0f98c-132">Voor het Verenigd Koninkrijk: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="0f98c-132">For the United Kingdom: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="0f98c-133">Voor de Verenigde Staten:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` .</span><span class="sxs-lookup"><span data-stu-id="0f98c-133">For the United States:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback`.</span></span>
 
6. <span data-ttu-id="0f98c-134">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0f98c-134">Click **Save**.</span></span>

## <a name="error-while-enabling-the-siem-connector-application"></a><span data-ttu-id="0f98c-135">Fout bij het inschakelen van de SIEM-verbindingstoepassing</span><span class="sxs-lookup"><span data-stu-id="0f98c-135">Error while enabling the SIEM connector application</span></span>
<span data-ttu-id="0f98c-136">Als er een fout is opgetreden bij het inschakelen van de SIEM-verbindingstoepassing, controleert u de pop-upblokkeringsinstellingen van uw browser.</span><span class="sxs-lookup"><span data-stu-id="0f98c-136">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="0f98c-137">Mogelijk wordt het nieuwe venster geblokkeerd wanneer u de functie inschakelen.</span><span class="sxs-lookup"><span data-stu-id="0f98c-137">It might be blocking the new window being opened when you enable the capability.</span></span>




><span data-ttu-id="0f98c-138">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="0f98c-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0f98c-139">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="0f98c-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a><span data-ttu-id="0f98c-140">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="0f98c-140">Related topics</span></span>
- [<span data-ttu-id="0f98c-141">SIEM-integratie inschakelen in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="0f98c-141">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="0f98c-142">ArcSight configureren om Microsoft Defender te gebruiken voor eindpuntdetecties</span><span class="sxs-lookup"><span data-stu-id="0f98c-142">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="0f98c-143">Detecties naar uw SIEM-hulpprogramma's trekken</span><span class="sxs-lookup"><span data-stu-id="0f98c-143">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="0f98c-144">Microsoft Defender voor eindpuntdetectievelden</span><span class="sxs-lookup"><span data-stu-id="0f98c-144">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="0f98c-145">Microsoft Defender voor eindpuntdetecties trekken met REST API</span><span class="sxs-lookup"><span data-stu-id="0f98c-145">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
