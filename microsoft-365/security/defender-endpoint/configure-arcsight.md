---
title: MicroFocus ArcSight configureren om Microsoft Defender voor eindpuntdetecties op te halen
description: MicroFocus ArcSight configureren voor het ontvangen en trekken van detecties van Microsoft Defender-beveiligingscentrum
keywords: MicroFocus ArcSight, beveiligingsinformatie- en evenementenbeheerhulpmiddelen configureren, boogsight
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
ms.openlocfilehash: a52f810647c387c5a5726b9d31998c34add4092e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166183"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a><span data-ttu-id="e8bcc-104">MicroFocus ArcSight configureren om Defender voor eindpuntdetecties op te halen</span><span class="sxs-lookup"><span data-stu-id="e8bcc-104">Configure Micro Focus ArcSight to pull Defender for Endpoint detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e8bcc-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e8bcc-105">**Applies to:**</span></span>
- [<span data-ttu-id="e8bcc-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="e8bcc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e8bcc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e8bcc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="e8bcc-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="e8bcc-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e8bcc-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configurearcsight-abovefoldlink) 

<span data-ttu-id="e8bcc-110">U moet sommige bestanden en hulpprogramma's installeren en configureren om Micro Focus ArcSight te gebruiken, zodat defender voor eindpuntdetecties kan worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-110">You'll need to install and configure some files and tools to use Micro Focus ArcSight so that it can pull Defender for Endpoint detections.</span></span>

>[!Note]
>- <span data-ttu-id="e8bcc-111">[Defender for Endpoint Alert](alerts.md) is samengesteld uit een of meer detecties</span><span class="sxs-lookup"><span data-stu-id="e8bcc-111">[Defender for Endpoint Alert](alerts.md) is composed from one or more detections</span></span>
>- <span data-ttu-id="e8bcc-112">[Defender for Endpoint Detection](api-portal-mapping.md) is samengesteld uit de verdachte gebeurtenis die zich heeft voorgedaan op het apparaat en de bijbehorende waarschuwingsgegevens.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-112">[Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e8bcc-113">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="e8bcc-113">Before you begin</span></span>

<span data-ttu-id="e8bcc-114">Voor het configureren van het hulpprogramma Micro Focus ArcSight Connector zijn verschillende configuratiebestanden nodig om detecties uit uw Azure Active Directory (AAD)-toepassing te halen en te parseren.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-114">Configuring the Micro Focus ArcSight Connector tool requires several configuration files for it to pull and parse detections from your Azure Active Directory (AAD) application.</span></span>

<span data-ttu-id="e8bcc-115">In deze sectie wordt u begeleid bij het verkrijgen van de benodigde informatie om de vereiste configuratiebestanden correct in te stellen en te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-115">This section guides you in getting the necessary information to set and use the required configuration files correctly.</span></span>

- <span data-ttu-id="e8bcc-116">Zorg ervoor dat u de siem-integratiefunctie hebt ingeschakeld in het **Instellingen** menu.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-116">Make sure you have enabled the SIEM integration feature from the **Settings** menu.</span></span> <span data-ttu-id="e8bcc-117">Zie [SiEM-integratie inschakelen in Defender voor eindpunt](enable-siem-integration.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-117">For more information, see [Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="e8bcc-118">Het bestand dat u hebt opgeslagen om de SIEM-integratiefunctie in te stellen, klaar hebben.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-118">Have the file you saved from enabling the SIEM integration feature ready.</span></span> <span data-ttu-id="e8bcc-119">U moet de volgende waarden krijgen:</span><span class="sxs-lookup"><span data-stu-id="e8bcc-119">You'll need to get the following values:</span></span>
  - <span data-ttu-id="e8bcc-120">Url voor vernieuwen van OAuth 2.0 Token</span><span class="sxs-lookup"><span data-stu-id="e8bcc-120">OAuth 2.0 Token refresh URL</span></span>
  - <span data-ttu-id="e8bcc-121">OAuth 2.0 Client-id</span><span class="sxs-lookup"><span data-stu-id="e8bcc-121">OAuth 2.0 Client ID</span></span>
  - <span data-ttu-id="e8bcc-122">OAuth 2.0 Client secret</span><span class="sxs-lookup"><span data-stu-id="e8bcc-122">OAuth 2.0 Client secret</span></span>

- <span data-ttu-id="e8bcc-123">De volgende configuratiebestanden gereed hebben:</span><span class="sxs-lookup"><span data-stu-id="e8bcc-123">Have the following configuration files ready:</span></span>
  - <span data-ttu-id="e8bcc-124">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="e8bcc-124">WDATP-connector.properties</span></span>
  - <span data-ttu-id="e8bcc-125">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="e8bcc-125">WDATP-connector.jsonparser.properties</span></span>

    <span data-ttu-id="e8bcc-126">U zou een .zip bestand met deze twee bestanden hebben opgeslagen wanneer u Micro Focus ArcSight hebt gekozen als het SIEM-type dat u in uw organisatie gebruikt.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-126">You would have saved a .zip file which contains these two files when you chose Micro Focus ArcSight as the SIEM type you use in your organization.</span></span>

- <span data-ttu-id="e8bcc-127">Zorg ervoor dat u de volgende tokens genereert en klaar hebt:</span><span class="sxs-lookup"><span data-stu-id="e8bcc-127">Make sure you generate the following tokens and have them ready:</span></span>
  - <span data-ttu-id="e8bcc-128">Access-token</span><span class="sxs-lookup"><span data-stu-id="e8bcc-128">Access token</span></span>
  - <span data-ttu-id="e8bcc-129">Token vernieuwen</span><span class="sxs-lookup"><span data-stu-id="e8bcc-129">Refresh token</span></span>

  <span data-ttu-id="e8bcc-130">U kunt deze tokens genereren vanuit de **sectie SIEM-integratie-instelling** van de portal.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-130">You can generate these tokens from the **SIEM integration** setup section of the portal.</span></span>

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a><span data-ttu-id="e8bcc-131">MicroFocus ArcSight FlexConnector installeren en configureren</span><span class="sxs-lookup"><span data-stu-id="e8bcc-131">Install and configure Micro Focus ArcSight FlexConnector</span></span>

<span data-ttu-id="e8bcc-132">In de volgende stappen wordt ervan uitgenomen dat u alle vereiste stappen hebt voltooid in [Voordat u begint.](#before-you-begin)</span><span class="sxs-lookup"><span data-stu-id="e8bcc-132">The following steps assume that you have completed all the required steps in [Before you begin](#before-you-begin).</span></span>

1. <span data-ttu-id="e8bcc-133">Installeer de nieuwste 32-bits Windows FlexConnector-installatieprogramma.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-133">Install the latest 32-bit Windows FlexConnector installer.</span></span> <span data-ttu-id="e8bcc-134">U vindt dit in het HPE-softwarecentrum.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-134">You can find this in the HPE Software center.</span></span> <span data-ttu-id="e8bcc-135">Het hulpprogramma wordt meestal geïnstalleerd op de volgende standaardlocatie: `C:\Program Files\ArcSightFlexConnectors\current\bin` .</span><span class="sxs-lookup"><span data-stu-id="e8bcc-135">The tool is typically installed in the following default location: `C:\Program Files\ArcSightFlexConnectors\current\bin`.</span></span></br></br><span data-ttu-id="e8bcc-136">U kunt kiezen waar u het hulpprogramma wilt opslaan, bijvoorbeeld C: \\ *folder_location*\current\bin waar folder_location de installatielocatie vertegenwoordigt. </span><span class="sxs-lookup"><span data-stu-id="e8bcc-136">You can choose where to save the tool, for example C:\\*folder_location*\current\bin where *folder_location* represents the installation location.</span></span>

2. <span data-ttu-id="e8bcc-137">Volg de installatiewizard door de volgende taken:</span><span class="sxs-lookup"><span data-stu-id="e8bcc-137">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="e8bcc-138">Inleiding</span><span class="sxs-lookup"><span data-stu-id="e8bcc-138">Introduction</span></span>
   - <span data-ttu-id="e8bcc-139">Map installeren kiezen</span><span class="sxs-lookup"><span data-stu-id="e8bcc-139">Choose Install Folder</span></span>
   - <span data-ttu-id="e8bcc-140">Installatieset kiezen</span><span class="sxs-lookup"><span data-stu-id="e8bcc-140">Choose Install Set</span></span>
   - <span data-ttu-id="e8bcc-141">Snelkoppelingsmap kiezen</span><span class="sxs-lookup"><span data-stu-id="e8bcc-141">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="e8bcc-142">Overzicht van de installatie vóór de installatie</span><span class="sxs-lookup"><span data-stu-id="e8bcc-142">Pre-Installation Summary</span></span>
   - <span data-ttu-id="e8bcc-143">Installeren...</span><span class="sxs-lookup"><span data-stu-id="e8bcc-143">Installing...</span></span>

   <span data-ttu-id="e8bcc-144">U kunt de standaardwaarden voor elk van deze taken behouden of de selectie aanpassen aan uw vereisten.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-144">You can keep the default values for each of these tasks or modify the selection to suit your requirements.</span></span>

3. <span data-ttu-id="e8bcc-145">Open Verkenner en zoek de twee configuratiebestanden die u hebt opgeslagen toen u de SIEM-integratiefunctie inschakelen.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-145">Open File Explorer and locate the two configuration files you saved when you enabled the SIEM integration feature.</span></span> <span data-ttu-id="e8bcc-146">Zet de twee bestanden op de flexconnector-installatielocatie, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="e8bcc-146">Put the two files in the FlexConnector installation location, for example:</span></span>

   - <span data-ttu-id="e8bcc-147">WDATP-connector.jsonparser.properties: C: \\ *folder_location*\current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="e8bcc-147">WDATP-connector.jsonparser.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   - <span data-ttu-id="e8bcc-148">WDATP-connector.properties: C: \\ *folder_location*\current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="e8bcc-148">WDATP-connector.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   > [!NOTE]
   > 
   > <span data-ttu-id="e8bcc-149">U moet de configuratiebestanden op deze locatie plaatsen, *folder_location* de locatie waar u het hulpprogramma hebt geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-149">You must put the configuration files in this location, where *folder_location* represents the location where you installed the tool.</span></span>

4. <span data-ttu-id="e8bcc-150">Nadat de installatie van de basisconnector is voltooid, wordt het venster Connector-instelling geopend.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-150">After the installation of the core connector completes, the Connector Setup window opens.</span></span> <span data-ttu-id="e8bcc-151">Selecteer in het venster Verbindingslijn instellen **de optie Verbindingslijn toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="e8bcc-151">In the Connector Setup window, select **Add a Connector**.</span></span>

5. <span data-ttu-id="e8bcc-152">Selecteer Type: **ArcSight FlexConnector REST en** klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="e8bcc-152">Select Type: **ArcSight FlexConnector REST** and click **Next**.</span></span>

6. <span data-ttu-id="e8bcc-153">Typ de volgende informatie in het formulier parameterdetails.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-153">Type the following information in the parameter details form.</span></span> <span data-ttu-id="e8bcc-154">Alle andere waarden in het formulier zijn optioneel en kunnen leeg worden gelaten.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-154">All other values in the form are optional and can be left blank.</span></span>

   <table>
    <tbody style="vertical-align:top;">
    <tr>
    <th><span data-ttu-id="e8bcc-155">Veld</span><span class="sxs-lookup"><span data-stu-id="e8bcc-155">Field</span></span></th>
    <th><span data-ttu-id="e8bcc-156">Waarde</span><span class="sxs-lookup"><span data-stu-id="e8bcc-156">Value</span></span></th>
    </tr>
    <tr>
    <td><span data-ttu-id="e8bcc-157">Configuratiebestand</span><span class="sxs-lookup"><span data-stu-id="e8bcc-157">Configuration File</span></span></td>
    <td><span data-ttu-id="e8bcc-158">Typ de naam van het eigenschapsbestand van de client.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-158">Type in the name of the client property file.</span></span> <span data-ttu-id="e8bcc-159">De naam moet overeenkomen met het bestand dat is opgegeven in de .zip die u hebt gedownload.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-159">The name must match the file provided in the .zip that you downloaded.</span></span>
<span data-ttu-id="e8bcc-160">Als het configuratiebestand in de flexagentmap bijvoorbeeld de naam &quot; &quot;WDATP-Connector.js&quot; onparser.properties, moet u &quot; &quot; WDATP-Connector typen als de naam van het &quot; clienteigenschappenbestand.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-160">For example, if the configuration file in &quot;flexagent&quot; directory is named &quot;WDATP-Connector.jsonparser.properties&quot;, you must type &quot;WDATP-Connector&quot; as the name of the client property file.</span></span></td>
    </tr>
    <td><span data-ttu-id="e8bcc-161">GEBEURTENIS-URL</span><span class="sxs-lookup"><span data-stu-id="e8bcc-161">Events URL</span></span></td>
    <td><span data-ttu-id="e8bcc-162">Afhankelijk van de locatie van uw datacenter, selecteert u de URL van de EU of de VS:</span><span class="sxs-lookup"><span data-stu-id="e8bcc-162">Depending on the location of your datacenter, select either the EU or the US URL:</span></span> </br></br> <span data-ttu-id="e8bcc-163"><b>Voor DE EU</b>: https:// <i></i> wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="e8bcc-163"><b>For EU</b>:  https://<i></i>wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br>
   </br><span data-ttu-id="e8bcc-164"><b>Voor vs:</b> https:// <i></i> wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="e8bcc-164"><b>For US:</b> https://<i></i>wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br> <br> <span data-ttu-id="e8bcc-165"><b>Voor het</b>Verenigd Koninkrijk : https:// <i></i> wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="e8bcc-165"><b>For UK</b>:  https://<i></i>wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span></td>
    <tr>
    <td><span data-ttu-id="e8bcc-166">Verificatietype</span><span class="sxs-lookup"><span data-stu-id="e8bcc-166">Authentication Type</span></span></td>
    <td><span data-ttu-id="e8bcc-167">OAuth 2</span><span class="sxs-lookup"><span data-stu-id="e8bcc-167">OAuth 2</span></span></td>
    </tr>
    <td><span data-ttu-id="e8bcc-168">OAuth 2 Clienteigenschappenbestand</span><span class="sxs-lookup"><span data-stu-id="e8bcc-168">OAuth 2 Client Properties file</span></span></td>
    <td><span data-ttu-id="e8bcc-169">Blader naar de locatie van het <em>bestand wdatp-connector.properties.</em></span><span class="sxs-lookup"><span data-stu-id="e8bcc-169">Browse to the location of the <em>wdatp-connector.properties</em> file.</span></span> <span data-ttu-id="e8bcc-170">De naam moet overeenkomen met het bestand dat is opgegeven in de .zip die u hebt gedownload.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-170">The name must match the file provided in the .zip that you downloaded.</span></span></td>
    <tr>
    <td><span data-ttu-id="e8bcc-171">Token vernieuwen</span><span class="sxs-lookup"><span data-stu-id="e8bcc-171">Refresh Token</span></span></td>
    <td><span data-ttu-id="e8bcc-172">U kunt een vernieuwings-token op twee manieren verkrijgen: door een vernieuwings-token te genereren vanaf de <b>pagina SIEM-instellingen</b> of door het hulpprogramma restutil te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-172">You can obtain a refresh token in two ways: by generating a refresh token from the <b>SIEM settings</b> page or using the restutil tool.</span></span> <br><br> <span data-ttu-id="e8bcc-173">Zie <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">SiEM-integratie in defender</a>voor <b></b> eindpunt inschakelen voor meer informatie over het genereren van een vernieuwingsken van de instelling Voorkeuren.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-173">For more information on generating a refresh token from the <b>Preferences setup</b> , see <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Enable SIEM integration in Defender for Endpoint</a>.</span></span> </br> </br><span data-ttu-id="e8bcc-174"><b>Haal uw vernieuwings-token op met behulp van het hulpmiddel Restutil:</b> </span><span class="sxs-lookup"><span data-stu-id="e8bcc-174"><b>Get your refresh token using the restutil tool:</b> </span></span></br> <span data-ttu-id="e8bcc-175">a.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-175">a.</span></span> <span data-ttu-id="e8bcc-176">Een opdrachtprompt openen.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-176">Open a command prompt.</span></span> <span data-ttu-id="e8bcc-177">Ga naar C:\<em>folder_location</em>\current\bin <em>folder_location</em> de locatie waar u het hulpprogramma hebt geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-177">Navigate to C:\<em>folder_location</em>\current\bin where <em>folder_location</em> represents the location where you installed the tool.</span></span> </br></br> <span data-ttu-id="e8bcc-178">b.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-178">b.</span></span> <span data-ttu-id="e8bcc-179">Type: <code>arcsight restutil token -config</code> vanuit de adreslijst van de bin. Bijvoorbeeld: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> Een webbrowservenster wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-179">Type: <code>arcsight restutil token -config</code> from the bin directory.For example: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> A Web browser window will open.</span></span> </br> </br><span data-ttu-id="e8bcc-180">c.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-180">c.</span></span> <span data-ttu-id="e8bcc-181">Typ uw referenties en klik op het wachtwoordveld om de pagina om te leiden.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-181">Type in your credentials then click on the password field to let the page redirect.</span></span> <span data-ttu-id="e8bcc-182">Voer in de aanmeldingsprompt uw referenties in.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-182">In the login prompt, enter your credentials.</span></span> </br> </br><span data-ttu-id="e8bcc-183">d.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-183">d.</span></span> <span data-ttu-id="e8bcc-184">In de opdrachtprompt wordt een vernieuwend token weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-184">A refresh token is shown in the command prompt.</span></span> </br></br> <span data-ttu-id="e8bcc-185">e.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-185">e.</span></span> <span data-ttu-id="e8bcc-186">Kopieer en plak het in het <b>veld Token</b> vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-186">Copy and paste it into the <b>Refresh Token</b> field.</span></span>
    </td>
    </tr>
    </tr>
    </table><br/>
    
7. <span data-ttu-id="e8bcc-187">Er wordt een browservenster geopend door de verbindingslijn.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-187">A browser window is opened by the connector.</span></span> <span data-ttu-id="e8bcc-188">Meld u aan met uw toepassingsreferenties.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-188">Login with your application credentials.</span></span> <span data-ttu-id="e8bcc-189">Nadat u zich hebt aanmelden, wordt u gevraagd toestemming te geven aan uw OAuth2-client.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-189">After you log in, you'll be asked to give permission to your OAuth2 Client.</span></span> <span data-ttu-id="e8bcc-190">U moet toestemming geven aan uw OAuth 2-client, zodat de configuratie van de verbindingslijn kan worden geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-190">You must give permission to your OAuth 2 Client so that the connector configuration can authenticate.</span></span>

   <span data-ttu-id="e8bcc-191">Als het <code>redirect_uri</code> een HTTPS-URL is, wordt u omgeleid naar een URL op de lokale host.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-191">If the <code>redirect_uri</code> is a https URL, you'll be redirected to a URL on the local host.</span></span> <span data-ttu-id="e8bcc-192">U ziet een pagina met het verzoek om het certificaat te vertrouwen dat wordt geleverd door de connector die op de lokale host wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-192">You'll see a page that requests for you to trust the certificate supplied by the connector running on the local host.</span></span> <span data-ttu-id="e8bcc-193">U moet dit certificaat vertrouwen als de redirect_uri https is.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-193">You'll need to trust this certificate if the redirect_uri is a https.</span></span>
   
   <span data-ttu-id="e8bcc-194">Als u echter een http-URL opgeeft voor de redirect_uri, hoeft u geen toestemming te geven voor het vertrouwen van het certificaat.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-194">If however you specify a http URL for the redirect_uri, you do not need to provide consent in trusting the certificate.</span></span>

8. <span data-ttu-id="e8bcc-195">Ga verder met de configuratie van de verbindingslijn door terug te keren naar het venster Micro Focus ArcSight Connector Setup.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-195">Continue with the connector setup by returning to the Micro Focus ArcSight Connector Setup window.</span></span>

9. <span data-ttu-id="e8bcc-196">Selecteer **ArcSight Manager (versleuteld)** als de bestemming en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="e8bcc-196">Select the **ArcSight Manager (encrypted)** as the destination and click **Next**.</span></span>

10. <span data-ttu-id="e8bcc-197">Typ de doel-IP/hostnaam in **Manager Hostname** en uw referenties in het parametersformulier.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-197">Type in the destination IP/hostname in **Manager Hostname** and your credentials in the parameters form.</span></span> <span data-ttu-id="e8bcc-198">Alle andere waarden in het formulier moeten worden behouden met de standaardwaarden.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-198">All other values in the form should be retained with the default values.</span></span> <span data-ttu-id="e8bcc-199">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-199">Click **Next**.</span></span>

11. <span data-ttu-id="e8bcc-200">Typ een naam voor de verbindingslijn in het verbindingslijndetailformulier.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-200">Type in a name for the connector in the connector details form.</span></span> <span data-ttu-id="e8bcc-201">Alle andere waarden in het formulier zijn optioneel en kunnen leeg worden gelaten.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-201">All other values in the form are optional and can be left blank.</span></span> <span data-ttu-id="e8bcc-202">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-202">Click **Next**.</span></span>

12. <span data-ttu-id="e8bcc-203">Het importcertificaatvenster van ESM Manager wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-203">The ESM Manager import certificate window is shown.</span></span> <span data-ttu-id="e8bcc-204">Selecteer **Het certificaat importeren naar verbindingslijn van bestemming** en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="e8bcc-204">Select **Import the certificate to connector from destination** and click **Next**.</span></span> <span data-ttu-id="e8bcc-205">Het **venster Overzicht van verbindingslijn** toevoegen wordt weergegeven en het certificaat wordt geïmporteerd.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-205">The **Add connector Summary** window is displayed and the certificate is imported.</span></span>

13. <span data-ttu-id="e8bcc-206">Controleer of de details in het venster Overzicht van **verbindingslijn** toevoegen juist zijn en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="e8bcc-206">Verify that the details in the **Add connector Summary** window is correct, then click **Next**.</span></span>

14. <span data-ttu-id="e8bcc-207">Selecteer **Installeren als een service** en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="e8bcc-207">Select **Install as a service** and click **Next**.</span></span>

15. <span data-ttu-id="e8bcc-208">Typ een naam in het **veld Interne naam van service.**</span><span class="sxs-lookup"><span data-stu-id="e8bcc-208">Type a name in the **Service Internal Name** field.</span></span> <span data-ttu-id="e8bcc-209">Alle andere waarden in het formulier kunnen behouden blijven met de standaardwaarden of leeg blijven.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-209">All other values in the form can be retained with the default values or left blank .</span></span> <span data-ttu-id="e8bcc-210">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-210">Click **Next**.</span></span>

16. <span data-ttu-id="e8bcc-211">Typ de serviceparameters en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="e8bcc-211">Type in the service parameters and click **Next**.</span></span> <span data-ttu-id="e8bcc-212">Er wordt een venster weergegeven **met het overzicht van de installatieservice.**</span><span class="sxs-lookup"><span data-stu-id="e8bcc-212">A window with the **Install Service Summary** is shown.</span></span> <span data-ttu-id="e8bcc-213">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-213">Click **Next**.</span></span>

17. <span data-ttu-id="e8bcc-214">U kunt de installatie voltooien door **Afsluiten en** Volgende **te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="e8bcc-214">Finish the installation by selecting **Exit** and **Next**.</span></span>

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a><span data-ttu-id="e8bcc-215">De Micro Focus ArcSight-console installeren en configureren</span><span class="sxs-lookup"><span data-stu-id="e8bcc-215">Install and configure the Micro Focus ArcSight console</span></span>

1. <span data-ttu-id="e8bcc-216">Volg de installatiewizard door de volgende taken:</span><span class="sxs-lookup"><span data-stu-id="e8bcc-216">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="e8bcc-217">Inleiding</span><span class="sxs-lookup"><span data-stu-id="e8bcc-217">Introduction</span></span>
   - <span data-ttu-id="e8bcc-218">Licentieovereenkomst</span><span class="sxs-lookup"><span data-stu-id="e8bcc-218">License Agreement</span></span>
   - <span data-ttu-id="e8bcc-219">Speciale mededeling</span><span class="sxs-lookup"><span data-stu-id="e8bcc-219">Special Notice</span></span>
   - <span data-ttu-id="e8bcc-220">ArcSight-installatiemap kiezen</span><span class="sxs-lookup"><span data-stu-id="e8bcc-220">Choose ArcSight installation directory</span></span>
   - <span data-ttu-id="e8bcc-221">Snelkoppelingsmap kiezen</span><span class="sxs-lookup"><span data-stu-id="e8bcc-221">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="e8bcc-222">Overzicht van de installatie vóór de installatie</span><span class="sxs-lookup"><span data-stu-id="e8bcc-222">Pre-Installation Summary</span></span>

2. <span data-ttu-id="e8bcc-223">Klik op **Installeren**.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-223">Click **Install**.</span></span> <span data-ttu-id="e8bcc-224">Nadat de installatie is voltooid, wordt de wizard ArcSight-consoleconfiguratie geopend.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-224">After the installation completes, the ArcSight Console Configuration Wizard opens.</span></span>

3. <span data-ttu-id="e8bcc-225">Typ localhost in **Manager Host Name en** 8443 in Manager **Port** en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="e8bcc-225">Type localhost in **Manager Host Name** and 8443 in **Manager Port** then click **Next**.</span></span>

4. <span data-ttu-id="e8bcc-226">Selecteer **Directe verbinding gebruiken** en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="e8bcc-226">Select **Use direct connection**, then click **Next**.</span></span>

5. <span data-ttu-id="e8bcc-227">Selecteer **Verificatie op basis van wachtwoord** en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="e8bcc-227">Select **Password Based Authentication**, then click **Next**.</span></span>

6. <span data-ttu-id="e8bcc-228">Selecteer **Dit is een installatie van één gebruiker. (Aanbevolen)** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-228">Select **This is a single user installation. (Recommended)**, then click **Next**.</span></span>

7. <span data-ttu-id="e8bcc-229">Klik **op Klaar** om het installatieprogramma te stoppen.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-229">Click **Done** to quit the installer.</span></span>

8. <span data-ttu-id="e8bcc-230">Meld u aan bij de Micro Focus ArcSight-console.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-230">Login to the Micro Focus ArcSight console.</span></span>

9. <span data-ttu-id="e8bcc-231">**Navigeer naar Active channel set** New  >  **Condition**  >  **Device**  >  **Device Product**.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-231">Navigate to **Active channel set** > **New Condition** > **Device** > **Device Product**.</span></span>

10. <span data-ttu-id="e8bcc-232">Apparaatproduct **= Microsoft Defender ATP.**</span><span class="sxs-lookup"><span data-stu-id="e8bcc-232">Set **Device Product = Microsoft Defender ATP**.</span></span> <span data-ttu-id="e8bcc-233">Wanneer u hebt geverifieerd dat gebeurtenissen naar het hulpprogramma lopen, stopt u het proces opnieuw en gaat u naar Windows Services en start u de ArcSight FlexConnector REST.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-233">When you've verified that events are flowing to the tool, stop the process again and go to Windows Services and start the ArcSight FlexConnector REST.</span></span>

<span data-ttu-id="e8bcc-234">U kunt nu query's uitvoeren in de Micro Focus ArcSight-console.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-234">You can now run queries in the Micro Focus ArcSight console.</span></span>

<span data-ttu-id="e8bcc-235">Detecties van Defender voor eindpunten worden weergegeven als afzonderlijke gebeurtenissen, met 'Microsoft' als leverancier en 'Windows Defender ATP' als apparaatnaam.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-235">Defender for Endpoint detections will appear as discrete events, with "Microsoft” as the vendor and “Windows Defender ATP” as the device name.</span></span>


## <a name="troubleshooting-micro-focus-arcsight-connection"></a><span data-ttu-id="e8bcc-236">Problemen met Micro Focus ArcSight-verbinding oplossen</span><span class="sxs-lookup"><span data-stu-id="e8bcc-236">Troubleshooting Micro Focus ArcSight connection</span></span>

<span data-ttu-id="e8bcc-237">**Probleem:** Het token kan niet worden vernieuwd.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-237">**Problem:** Failed to refresh the token.</span></span> <span data-ttu-id="e8bcc-238">U vindt het logboek in C: \\ *folder_location*\current\logs waar folder_location de locatie vertegenwoordigt  waar u het hulpprogramma hebt geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-238">You can find the log located in C:\\*folder_location*\current\logs where *folder_location* represents the location where you installed the tool.</span></span> <span data-ttu-id="e8bcc-239">Open _agent.log en_ zoek naar `ERROR/FATAL/WARN` .</span><span class="sxs-lookup"><span data-stu-id="e8bcc-239">Open _agent.log_ and look for `ERROR/FATAL/WARN`.</span></span>

<span data-ttu-id="e8bcc-240">**Symptoom:** U krijgt het volgende foutbericht:</span><span class="sxs-lookup"><span data-stu-id="e8bcc-240">**Symptom:** You get the following error message:</span></span>

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

<span data-ttu-id="e8bcc-241">**Oplossing:**</span><span class="sxs-lookup"><span data-stu-id="e8bcc-241">**Solution:**</span></span>

1. <span data-ttu-id="e8bcc-242">Stop het proces door in het venster Verbindingslijn op Ctrl +C te klikken.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-242">Stop the process by clicking Ctrl + C on the Connector window.</span></span> <span data-ttu-id="e8bcc-243">Klik **op Y** wanneer u wordt gevraagd 'Batch job Y/N beëindigen?'.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-243">Click **Y** when asked "Terminate batch job Y/N?".</span></span>

2. <span data-ttu-id="e8bcc-244">Ga naar de map waar u het bestand WDATP-connector.properties hebt opgeslagen en bewerk het bestand om de volgende waarde toe te voegen: `reauthenticate=true` .</span><span class="sxs-lookup"><span data-stu-id="e8bcc-244">Navigate to the folder where you stored the WDATP-connector.properties file and edit it to add the following value: `reauthenticate=true`.</span></span>

3. <span data-ttu-id="e8bcc-245">Start de verbindingslijn opnieuw door de volgende opdracht uit te voeren: `arcsight.bat connectors` .</span><span class="sxs-lookup"><span data-stu-id="e8bcc-245">Restart the connector by running the following command: `arcsight.bat connectors`.</span></span>

   <span data-ttu-id="e8bcc-246">Er wordt een browservenster weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-246">A browser window appears.</span></span> <span data-ttu-id="e8bcc-247">Als u de verbindingslijn wilt laten uitvoeren, moet deze verdwijnen en moet de verbindingslijn nu worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-247">Allow it to run, it should disappear, and the connector should now be running.</span></span>

> [!NOTE]
> <span data-ttu-id="e8bcc-248">Controleer of de verbindingslijn wordt uitgevoerd door het proces opnieuw te stoppen.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-248">Verify that the connector is running by stopping the process again.</span></span> <span data-ttu-id="e8bcc-249">Start de verbindingslijn opnieuw en er wordt geen browservenster weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e8bcc-249">Then start the connector again, and no browser window should appear.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e8bcc-250">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="e8bcc-250">Related topics</span></span>
- [<span data-ttu-id="e8bcc-251">SIEM-integratie inschakelen in Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="e8bcc-251">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="e8bcc-252">Detecties naar uw SIEM-hulpprogramma's trekken</span><span class="sxs-lookup"><span data-stu-id="e8bcc-252">Pull detections to your SIEM tools</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [<span data-ttu-id="e8bcc-253">Defender voor eindpuntdetecties trekken met BEHULP van REST API</span><span class="sxs-lookup"><span data-stu-id="e8bcc-253">Pull Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="e8bcc-254">Problemen met de integratie van SIEM-hulpprogramma's oplossen</span><span class="sxs-lookup"><span data-stu-id="e8bcc-254">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
