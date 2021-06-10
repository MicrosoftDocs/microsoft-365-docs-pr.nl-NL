---
title: SIEM-integratie inschakelen in Microsoft Defender voor Eindpunt
description: Schakel SIEM-integratie in om detecties te ontvangen in uw siem-oplossing (Security Information and Event Management).
keywords: siem connector, siem, connector, beveiligingsgegevens en gebeurtenissen inschakelen
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 87078bb7bfc6b38788fea2a6a4c3c9108be1d5b4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842960"
---
# <a name="enable-siem-integration-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="8d45c-104">SIEM-integratie inschakelen in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="8d45c-104">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8d45c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8d45c-105">**Applies to:**</span></span>
- [<span data-ttu-id="8d45c-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="8d45c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


><span data-ttu-id="8d45c-107">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="8d45c-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8d45c-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="8d45c-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink) 

<span data-ttu-id="8d45c-109">Schakel de siem-integratie (Security Information and Event Management) in, zodat u detecties van Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="8d45c-109">Enable security information and event management (SIEM) integration so you can pull detections from Microsoft Defender Security Center.</span></span> <span data-ttu-id="8d45c-110">Detecties trekken met uw SIEM-oplossing of door rechtstreeks verbinding te maken met de REST-API voor detecties.</span><span class="sxs-lookup"><span data-stu-id="8d45c-110">Pull detections using your SIEM solution or by connecting directly to the detections REST API.</span></span>

>[!NOTE]
>- <span data-ttu-id="8d45c-111">[Microsoft Defender for Endpoint Alert](alerts.md) is samengesteld uit een of meer detecties.</span><span class="sxs-lookup"><span data-stu-id="8d45c-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="8d45c-112">[Microsoft Defender voor eindpuntdetectie](api-portal-mapping.md) is samengesteld uit de verdachte gebeurtenis op het apparaat en de bijbehorende waarschuwingsgegevens.</span><span class="sxs-lookup"><span data-stu-id="8d45c-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
>- <span data-ttu-id="8d45c-113">De Microsoft Defender for Endpoint Alert API is de nieuwste API voor waarschuwingsverbruik en bevat een gedetailleerde lijst met verwante gegevens voor elke waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="8d45c-113">The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="8d45c-114">Zie Waarschuwingsmethoden en [-eigenschappen](alerts.md) en [Lijstwaarschuwingen](get-alerts.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8d45c-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8d45c-115">Vereisten</span><span class="sxs-lookup"><span data-stu-id="8d45c-115">Prerequisites</span></span>

- <span data-ttu-id="8d45c-116">De gebruiker die de instelling activeert, moet machtigingen hebben om een app te maken in Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="8d45c-116">The user who activates the setting must have permissions to create an app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="8d45c-117">Dit is iemand met de volgende rollen:</span><span class="sxs-lookup"><span data-stu-id="8d45c-117">This is someone with the following roles:</span></span> 

  - <span data-ttu-id="8d45c-118">Beveiligingsbeheerder en globale beheerder</span><span class="sxs-lookup"><span data-stu-id="8d45c-118">Security Administrator and either Global Administrator</span></span>
  - <span data-ttu-id="8d45c-119">Cloudtoepassingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="8d45c-119">Cloud Application Administrator</span></span>
  - <span data-ttu-id="8d45c-120">Toepassingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="8d45c-120">Application Administrator</span></span>
  - <span data-ttu-id="8d45c-121">Eigenaar van de service-principal</span><span class="sxs-lookup"><span data-stu-id="8d45c-121">Owner of the service principal</span></span>

- <span data-ttu-id="8d45c-122">Tijdens de eerste activering wordt een pop-upscherm weergegeven waarin referenties moeten worden ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="8d45c-122">During the initial activation, a pop-up screen is displayed for credentials to be entered.</span></span> <span data-ttu-id="8d45c-123">Zorg ervoor dat u pop-ups voor deze site toestaat.</span><span class="sxs-lookup"><span data-stu-id="8d45c-123">Make sure that you allow pop-ups for this site.</span></span>

## <a name="enabling-siem-integration"></a><span data-ttu-id="8d45c-124">SIEM-integratie inschakelen</span><span class="sxs-lookup"><span data-stu-id="8d45c-124">Enabling SIEM integration</span></span> 
1. <span data-ttu-id="8d45c-125">Selecteer in het navigatiedeelvenster **Instellingen**  >  **SIEM**.</span><span class="sxs-lookup"><span data-stu-id="8d45c-125">In the navigation pane, select **Settings** > **SIEM**.</span></span>

    ![Afbeelding van SIEM-integratie uit Instellingen menu1](images/enable_siem.png)

    >[!TIP]
    ><span data-ttu-id="8d45c-127">Als er een fout is opgetreden bij het inschakelen van de SIEM-verbindingstoepassing, controleert u de pop-upblokkeringsinstellingen van uw browser.</span><span class="sxs-lookup"><span data-stu-id="8d45c-127">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="8d45c-128">Mogelijk wordt het nieuwe venster geblokkeerd wanneer u de functie inschakelen.</span><span class="sxs-lookup"><span data-stu-id="8d45c-128">It might be blocking the new window being opened when you enable the capability.</span></span> 

2. <span data-ttu-id="8d45c-129">Selecteer **SIEM-integratie inschakelen.**</span><span class="sxs-lookup"><span data-stu-id="8d45c-129">Select **Enable SIEM integration**.</span></span> <span data-ttu-id="8d45c-130">Hiermee activeert u de sectie toegangsdetails van de **SIEM-connector** met vooraf ingevulde waarden en wordt er een toepassing gemaakt onder uw Azure Active Directory (Azure AD)-tenant.</span><span class="sxs-lookup"><span data-stu-id="8d45c-130">This activates the **SIEM connector access details** section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span>

    > [!WARNING]
    ><span data-ttu-id="8d45c-131">Het clientgeheim wordt slechts eenmaal weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8d45c-131">The client secret is only displayed once.</span></span> <span data-ttu-id="8d45c-132">Zorg ervoor dat u een kopie ervan op een veilige plaats houdt.</span><span class="sxs-lookup"><span data-stu-id="8d45c-132">Make sure you keep a copy of it in a safe place.</span></span><br>
     

    ![Afbeelding van SIEM-integratie uit Instellingen menu2](images/siem_details.png)

3. <span data-ttu-id="8d45c-134">Kies het SIEM-type dat u in uw organisatie gebruikt.</span><span class="sxs-lookup"><span data-stu-id="8d45c-134">Choose the SIEM type you use in your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8d45c-135">Als u HP ArcSight selecteert, moet u deze twee configuratiebestanden opslaan:</span><span class="sxs-lookup"><span data-stu-id="8d45c-135">If you select HP ArcSight, you'll need to save these two configuration files:</span></span><br>
   > - <span data-ttu-id="8d45c-136">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="8d45c-136">WDATP-connector.jsonparser.properties</span></span>
   > - <span data-ttu-id="8d45c-137">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="8d45c-137">WDATP-connector.properties</span></span> <br>

   <span data-ttu-id="8d45c-138">Als u rechtstreeks verbinding wilt maken met de DETECTIES REST API via programmatische toegang, kiest u **Generic API.**</span><span class="sxs-lookup"><span data-stu-id="8d45c-138">If you want to connect directly to the detections REST API through programmatic access, choose **Generic API**.</span></span>

4. <span data-ttu-id="8d45c-139">Kopieer de afzonderlijke waarden of selecteer **Details opslaan in bestand om** een bestand te downloaden dat alle waarden bevat.</span><span class="sxs-lookup"><span data-stu-id="8d45c-139">Copy the individual values or select **Save details to file** to download a file that contains all the values.</span></span>

5. <span data-ttu-id="8d45c-140">Selecteer **Tokens genereren** om toegang te krijgen en token te vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="8d45c-140">Select **Generate tokens** to get an access and refresh token.</span></span>
  
   > [!NOTE]
   > <span data-ttu-id="8d45c-141">U moet elke 90 dagen een nieuw vernieuwingsken genereren.</span><span class="sxs-lookup"><span data-stu-id="8d45c-141">You'll need to generate a new Refresh token every 90 days.</span></span> 

6. <span data-ttu-id="8d45c-142">Volg de instructies voor het [maken van een Azure AD-app-registratie](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) voor Microsoft Defender voor Eindpunt en wijs de juiste machtigingen toe om waarschuwingen te lezen.</span><span class="sxs-lookup"><span data-stu-id="8d45c-142">Follow the instructions for [creating an Azure AD app registration for Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) and assign the correct permissions to it to read alerts.</span></span>

<span data-ttu-id="8d45c-143">U kunt nu doorgaan met het configureren van uw SIEM-oplossing of verbinding maken met de DETECTIES REST API via programmatische toegang.</span><span class="sxs-lookup"><span data-stu-id="8d45c-143">You can now proceed with configuring your SIEM solution or connecting to the detections REST API through programmatic access.</span></span> <span data-ttu-id="8d45c-144">U moet de tokens gebruiken bij het configureren van uw SIEM-oplossing, zodat deze detecties kan ontvangen van Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="8d45c-144">You'll need to use the tokens when configuring your SIEM solution to allow it to receive detections from Microsoft Defender Security Center.</span></span>

## <a name="integrate-microsoft-defender-for-endpoint-with-ibm-qradar"></a><span data-ttu-id="8d45c-145">Microsoft Defender voor eindpunt integreren met IBM QRadar</span><span class="sxs-lookup"><span data-stu-id="8d45c-145">Integrate Microsoft Defender for Endpoint with IBM QRadar</span></span> 
<span data-ttu-id="8d45c-146">U kunt IBM QRadar zo configureren dat detecties worden verzameld van Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="8d45c-146">You can configure IBM QRadar to collect detections from Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="8d45c-147">Zie IBM Knowledge Center voor [meer informatie.](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)</span><span class="sxs-lookup"><span data-stu-id="8d45c-147">For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

## <a name="see-also"></a><span data-ttu-id="8d45c-148">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8d45c-148">See also</span></span>
- [<span data-ttu-id="8d45c-149">HP ArcSight configureren om Microsoft Defender te gebruiken voor eindpuntdetecties</span><span class="sxs-lookup"><span data-stu-id="8d45c-149">Configure HP ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="8d45c-150">Microsoft Defender voor eindpuntdetectievelden</span><span class="sxs-lookup"><span data-stu-id="8d45c-150">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="8d45c-151">Microsoft Defender voor eindpuntdetecties trekken met REST API</span><span class="sxs-lookup"><span data-stu-id="8d45c-151">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="8d45c-152">Problemen met de integratie van SIEM-hulpprogramma's oplossen</span><span class="sxs-lookup"><span data-stu-id="8d45c-152">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
