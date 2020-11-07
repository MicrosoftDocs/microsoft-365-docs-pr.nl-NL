---
title: Microsoft 365 Gebruiksanalyse inschakelen
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Meer informatie over het verzamelen van gegevens voor uw Tenant met behulp van de app Microsoft 365 Usage Analytics template in Power BI.
ms.openlocfilehash: 347256fa7acaae18cd31f0c8c6b7eca20ad2e9dd
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941329"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="6c52d-103">Microsoft 365 Gebruiksanalyse inschakelen</span><span class="sxs-lookup"><span data-stu-id="6c52d-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="6c52d-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="6c52d-104">The admin center is changing.</span></span> <span data-ttu-id="6c52d-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="6c52d-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="6c52d-106">De gebruiksanalyse voor Microsoft 365 is nog niet beschikbaar voor Microsoft 365 US Government community.</span><span class="sxs-lookup"><span data-stu-id="6c52d-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="6c52d-107">Stappen voor het inschakelen van Microsoft 365 Gebruiksanalyse</span><span class="sxs-lookup"><span data-stu-id="6c52d-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="6c52d-108">Als u aan de slag wilt met Microsoft 365 use Analytics, moet u eerst de gegevens beschikbaar maken in het Microsoft 365-Beheercentrum en vervolgens de sjabloon-app starten in Power BI.</span><span class="sxs-lookup"><span data-stu-id="6c52d-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="6c52d-109">Power BI downloaden</span><span class="sxs-lookup"><span data-stu-id="6c52d-109">Get Power BI</span></span>

<span data-ttu-id="6c52d-110">Als u Power BI nog niet hebt, kunt u [zich registreren voor Power bi Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span><span class="sxs-lookup"><span data-stu-id="6c52d-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="6c52d-111">Selecteer **gratis proberen** om u aan te melden voor een proefabonnement of **Nu kopen** voor Power bi Pro.</span><span class="sxs-lookup"><span data-stu-id="6c52d-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="6c52d-112">U kunt ook **Products** uitvouwen om een versie van Power BI te kopen.</span><span class="sxs-lookup"><span data-stu-id="6c52d-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="6c52d-113">U hebt een Power BI Pro-licentie nodig voor het installeren, aanpassen en distribueren van een sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="6c52d-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="6c52d-114">Voor meer informatie raadpleegt u de [vereisten](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="6c52d-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="6c52d-115">Als u uw gegevens wilt delen, moeten zowel u als de personen met wie u de gegevens deelt, een licentie voor Power BI Pro gebruiken, of de inhoud moet zich in een werkruimte in een [Power bi Premium-Service](https://docs.microsoft.com/power-bi/service-premium-what-is)bevinden.</span><span class="sxs-lookup"><span data-stu-id="6c52d-115">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="6c52d-116">De sjabloon-app inschakelen</span><span class="sxs-lookup"><span data-stu-id="6c52d-116">Enable the template app</span></span>

<span data-ttu-id="6c52d-117">Als u de sjabloon-app wilt inschakelen, moet u een **globale beheerder** zijn.</span><span class="sxs-lookup"><span data-stu-id="6c52d-117">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="6c52d-118">Zie [informatie over beheerdersrollen](../add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="6c52d-118">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="6c52d-119">Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.</span><span class="sxs-lookup"><span data-stu-id="6c52d-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="6c52d-120">Zoek op de pagina **gebruik** de kaart **Microsoft 365 Usage Analytics** en selecteer **aan de slag**.</span><span class="sxs-lookup"><span data-stu-id="6c52d-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="6c52d-121">In het deelvenster rapporten dat wordt geopend, stelt u **gegevens beschikbaar maken voor Microsoft 365 gebruiksanalyse voor Power bi** **in bij** \> **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6c52d-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="6c52d-122">Het verzamelen van gegevens wordt in twee tot 48 uur voltooid, afhankelijk van de grootte van de Tenant.</span><span class="sxs-lookup"><span data-stu-id="6c52d-122">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="6c52d-123">De knop **Ga naar Power BI** zal ingeschakeld zijn (niet langer grijs) als het verzamelen van gegevens is voltooid.</span><span class="sxs-lookup"><span data-stu-id="6c52d-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="6c52d-124">De sjabloon-app starten</span><span class="sxs-lookup"><span data-stu-id="6c52d-124">Start the template app</span></span>

<span data-ttu-id="6c52d-125">U moet een hoofd **beheerder** , **rapportlezer** , **Exchange-beheerder** , **Skype voor bedrijven-beheerder** of **SharePoint-beheerder** zijn om de sjabloon-app te starten.</span><span class="sxs-lookup"><span data-stu-id="6c52d-125">To start the template app, you have to be either a **global administrator** , **report reader** , **Exchange administrator** , **Skype for Business administrator** , or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="6c52d-126">Kopieer de Tenant-ID en selecteer **Go to Power bi**.</span><span class="sxs-lookup"><span data-stu-id="6c52d-126">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="6c52d-127">Meld u aan wanneer u in Power BI komt.</span><span class="sxs-lookup"><span data-stu-id="6c52d-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="6c52d-128">**Selecteer vervolgens apps** -> **downloaden** in het navigatiemenu.</span><span class="sxs-lookup"><span data-stu-id="6c52d-128">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="6c52d-129">In het tabblad **Apps** typt u Microsoft 365 in het zoekvak en selecteer vervolgens **Microsoft 365 Gebruiksanalyse** \> **Koop het vandaag nog**.</span><span class="sxs-lookup"><span data-stu-id="6c52d-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="6c52d-130">[![Selecteer nu kopen](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="6c52d-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="6c52d-131">Nadat de app is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="6c52d-131">Once the app is installed.</span></span> <span data-ttu-id="6c52d-132">Selecteer de tegel om deze te openen.</span><span class="sxs-lookup"><span data-stu-id="6c52d-132">Select the tile to open it.</span></span>

5.  <span data-ttu-id="6c52d-133">Selecteer **app verkennen** om de app met voorbeeldgegevens te bekijken.</span><span class="sxs-lookup"><span data-stu-id="6c52d-133">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="6c52d-134">Kies **verbinding maken** om de app te verbinden met de gegevens van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="6c52d-134">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="6c52d-135">Kies **verbinding** , ga naar het scherm **verbinding maken met Microsoft 365 Usage Analytics** en typ de Tenant-id (zonder streepjes) die u in stap 1 hebt gekopieerd, en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="6c52d-135">Choose **Connect** , on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="6c52d-136">Selecteer in het volgende scherm **OAuth2** als **verificatiemethode** \> **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="6c52d-136">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="6c52d-137">Als u een andere verificatiemethode kiest, mislukt de verbinding met de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="6c52d-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Microsoft-account kiezen als verificatiemethode](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="6c52d-139">Nadat de sjabloon-app is geïnstantieerd, is het dashboard Microsoft 365 Usage Analytics beschikbaar in de webversie van Power BI.</span><span class="sxs-lookup"><span data-stu-id="6c52d-139">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="6c52d-140">Het eerste laden van het dashboard duurt 2 tot 30 minuten.</span><span class="sxs-lookup"><span data-stu-id="6c52d-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="6c52d-141">Samengevoegde gegevens op tenantniveau zijn beschikbaar in alle rapporten.</span><span class="sxs-lookup"><span data-stu-id="6c52d-141">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="6c52d-142">**Gegevens op gebruikersniveau zijn pas beschikbaar na de 1e of 15e dag van de kalendermaand na aanmelding**.</span><span class="sxs-lookup"><span data-stu-id="6c52d-142">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in**.</span></span> <span data-ttu-id="6c52d-143">Dit is van invloed op alle rapporten onder gebruikersactiviteit.</span><span class="sxs-lookup"><span data-stu-id="6c52d-143">This will impact all reports under User Activity.</span></span> <span data-ttu-id="6c52d-144">Zie [navigeren en de rapporten gebruiken in Microsoft 365 gebruiksanalyse](navigate-and-utilize-reports.md) voor tips over het weergeven en gebruiken van deze rapporten.</span><span class="sxs-lookup"><span data-stu-id="6c52d-144">See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports.</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="6c52d-145">Verzamelde gegevens anoniem maken</span><span class="sxs-lookup"><span data-stu-id="6c52d-145">Make the collected data anonymous</span></span>

<span data-ttu-id="6c52d-146">Alleen hoofdbeheerders kunnen de gegevens die worden verzameld voor alle rapporten anoniem maken.</span><span class="sxs-lookup"><span data-stu-id="6c52d-146">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="6c52d-147">Hiermee kunt u identificeerbare informatie zoals namen van gebruikers, groepen en sites verbergen in rapporten en in de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="6c52d-147">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="6c52d-148">Ga in het Beheercentrum naar instellingen voor **Settings** \> **organisatie** en kies op het tabblad **Services** de optie **rapporten**.</span><span class="sxs-lookup"><span data-stu-id="6c52d-148">In the admin center, go to the **Settings** \> **Org Settings** , and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="6c52d-149">Selecteer **rapporten** en kies vervolgens deze optie om **anonieme Id's weer te geven**.</span><span class="sxs-lookup"><span data-stu-id="6c52d-149">Select **Reports** , and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="6c52d-150">Deze instelling wordt zowel toegepast op de gebruiksrapporten als voor de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="6c52d-150">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="6c52d-151">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6c52d-151">Select **Save changes**.</span></span>
