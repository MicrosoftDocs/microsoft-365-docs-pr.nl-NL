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
description: Meer informatie over het verzamelen van gegevens voor uw tenant met de sjabloon-app Microsoft 365 Usage Analytics in Power BI.
ms.openlocfilehash: b5cb8df7fbe8ce1844d2af3ecaf62c7903d4e98b
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527373"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="c1726-103">Microsoft 365 Gebruiksanalyse inschakelen</span><span class="sxs-lookup"><span data-stu-id="c1726-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c1726-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="c1726-104">The admin center is changing.</span></span> <span data-ttu-id="c1726-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="c1726-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="c1726-106">Microsoft 365-gebruiksanalyses zijn nog niet beschikbaar voor microsoft 365-overheidscommunity van de Amerikaanse overheid.</span><span class="sxs-lookup"><span data-stu-id="c1726-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="c1726-107">Stappen voor het inschakelen van Microsoft 365 Gebruiksanalyse</span><span class="sxs-lookup"><span data-stu-id="c1726-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="c1726-108">Als u aan de slag wilt met Microsoft 365-gebruiksanalyses, moet u eerst de gegevens beschikbaar stellen in het Microsoft 365-beheercentrum en vervolgens de sjabloon-app in Power BI starten.</span><span class="sxs-lookup"><span data-stu-id="c1726-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="c1726-109">Power BI downloaden</span><span class="sxs-lookup"><span data-stu-id="c1726-109">Get Power BI</span></span>

<span data-ttu-id="c1726-110">Als u nog geen Power BI hebt, u [zich aanmelden voor Power BI Pro.](https://go.microsoft.com/fwlink/p/?linkid=845347)</span><span class="sxs-lookup"><span data-stu-id="c1726-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="c1726-111">Selecteer **Probeer je gratis** aan te melden voor een proefversie of Koop **nu** om Power BI Pro te krijgen.</span><span class="sxs-lookup"><span data-stu-id="c1726-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="c1726-112">U kunt ook **Products** uitvouwen om een versie van Power BI te kopen.</span><span class="sxs-lookup"><span data-stu-id="c1726-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="c1726-113">U hebt een Power BI Pro-licentie nodig om een sjabloon-app te installeren, aan te passen en te distribueren.</span><span class="sxs-lookup"><span data-stu-id="c1726-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="c1726-114">Zie [Voorwaarden](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c1726-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="c1726-115">U hebt een Power BI Pro-licentie nodig om uw inhoud te delen, en de mensen met wie u deze deelt, doen dat ook, of de inhoud moet zich in een werkruimte bevinden in een [Premium-capaciteit.](https://docs.microsoft.com/power-bi/service-premium-what-is)</span><span class="sxs-lookup"><span data-stu-id="c1726-115">You need a Power BI Pro license to share your content, and the people you share it with do too, or the content needs to be in a workspace in a [Premium capacity](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="c1726-116">De sjabloon-app inschakelen</span><span class="sxs-lookup"><span data-stu-id="c1726-116">Enable the template app</span></span>

<span data-ttu-id="c1726-117">Als u de sjabloon-app wilt inschakelen, moet u een **globale beheerder**, **rapportlezer**, **Exchange-beheerder,** **Skype voor Bedrijven-beheerder**of **SharePoint-beheerder**zijn.</span><span class="sxs-lookup"><span data-stu-id="c1726-117">To enable the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
<span data-ttu-id="c1726-118">Zie [Over beheerdersrollen](../add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c1726-118">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="c1726-119">Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.</span><span class="sxs-lookup"><span data-stu-id="c1726-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="c1726-120">Zoek op de pagina **Gebruik** de **Microsoft 365-gebruiksanalysekaart** en selecteer **Aan de slag**.</span><span class="sxs-lookup"><span data-stu-id="c1726-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="c1726-121">Stel in het deelvenster Rapporten dat wordt geopend, de gegevens beschikbaar maken **voor Microsoft 365-gebruiksanalyses voor Power BI** in **Opslaan.** \> **Save**</span><span class="sxs-lookup"><span data-stu-id="c1726-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="c1726-p104">Hiermee wordt het gegevensverzamelingsproces gestart, en dit zal voltooid worden in 2 tot 48 uur, afhankelijk van de grootte van uw tenant. De knop **Ga naar Power BI** zal ingeschakeld zijn (niet langer grijs) als het verzamelen van gegevens is voltooid.</span><span class="sxs-lookup"><span data-stu-id="c1726-p104">This initiates the data collection process and will complete in 2 to 48 hours depending on the size of your tenant. The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="initiate-the-template-app"></a><span data-ttu-id="c1726-124">De sjabloon-app starten</span><span class="sxs-lookup"><span data-stu-id="c1726-124">Initiate the template app</span></span>

<span data-ttu-id="c1726-125">Als u de sjabloon-app wilt starten, moet u een **globale beheerder**, **rapportlezer**, **Exchange-beheerder,** **Skype voor Bedrijven-beheerder**of **SharePoint-beheerder**zijn.</span><span class="sxs-lookup"><span data-stu-id="c1726-125">To initiate the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="c1726-126">Kopieer de tenant-id en selecteer **Ga naar Power BI**.</span><span class="sxs-lookup"><span data-stu-id="c1726-126">Copy the tenant Id and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="c1726-127">Meld u aan wanneer u in Power BI komt.</span><span class="sxs-lookup"><span data-stu-id="c1726-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="c1726-128">Selecteer Apps->Apps ophalen in het navigatiemenu.</span><span class="sxs-lookup"><span data-stu-id="c1726-128">Select Apps->Get apps from the navigation menu.</span></span>    
  
3. <span data-ttu-id="c1726-129">In het tabblad **Apps** typt u Microsoft 365 in het zoekvak en selecteer vervolgens **Microsoft 365 Gebruiksanalyse** \> **Koop het vandaag nog**.</span><span class="sxs-lookup"><span data-stu-id="c1726-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="c1726-130">[![Selecteer Nu ophalen](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="c1726-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="c1726-131">Zodra de app is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="c1726-131">Once the app is installed.</span></span> <span data-ttu-id="c1726-132">Klik op de tegel om deze te openen.</span><span class="sxs-lookup"><span data-stu-id="c1726-132">Click on the tile to open it.</span></span>

5.  <span data-ttu-id="c1726-133">Klik **op De app verkennen** om de app met voorbeeldgegevens weer te geven.</span><span class="sxs-lookup"><span data-stu-id="c1726-133">Click **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="c1726-134">Klik **op Verbinding** maken om de app te koppelen aan de gegevens van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c1726-134">Click **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="c1726-135">Nadat u **op Verbinding**hebt geklikt , typt u in het scherm Verbinding maken met Microsoft **365-gebruiksanalyse** de tenant-id (zonder streepjes) die u in stap hebt gekopieerd (1) en selecteert u **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c1726-135">After clicking **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, type in the tenant Id (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="c1726-136">Selecteer in het volgende scherm **Microsoft-account** als **verificatiemethode** \> **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="c1726-136">On the next screen, select **Microsoft account** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="c1726-137">Als u een andere verificatiemethode kiest, mislukt de verbinding met de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="c1726-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Microsoft-account kiezen als verificatiemethode](../../media/ab6f0463-c3f7-4088-a605-67c699fa86ad.png)
  
8. <span data-ttu-id="c1726-139">Zodra de sjabloon-app is gehe momentediated, is het Microsoft 365 usage analytics-dashboard beschikbaar in Power BI op het web.</span><span class="sxs-lookup"><span data-stu-id="c1726-139">Once the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="c1726-140">Het eerste laden van het dashboard duurt 2 tot 30 minuten.</span><span class="sxs-lookup"><span data-stu-id="c1726-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="c1726-141">Samengevoegde gegevens op tenantniveau zijn beschikbaar in alle rapporten.</span><span class="sxs-lookup"><span data-stu-id="c1726-141">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="c1726-142">**Gegevens op gebruikersniveau zijn pas beschikbaar na de 1e of 15e dag van de kalendermaand na aanmelding**.</span><span class="sxs-lookup"><span data-stu-id="c1726-142">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in**.</span></span> <span data-ttu-id="c1726-143">Dit heeft gevolgen voor alle rapporten onder Gebruikersactiviteit (Zie [Navigeren en gebruik de rapporten in Microsoft 365-gebruiksanalyses](navigate-and-utilize-reports.md) voor tips over het bekijken en gebruiken van deze rapporten).</span><span class="sxs-lookup"><span data-stu-id="c1726-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="c1726-144">Verzamelde gegevens anoniem maken</span><span class="sxs-lookup"><span data-stu-id="c1726-144">Make the collected data anonymous</span></span>

<span data-ttu-id="c1726-145">Alleen hoofdbeheerders kunnen de gegevens die worden verzameld voor alle rapporten anoniem maken.</span><span class="sxs-lookup"><span data-stu-id="c1726-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="c1726-146">Hiermee worden identificeerbare informatie zoals gebruikers-, groeps- en sitenamen verborgen in rapporten en in de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="c1726-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="c1726-147">Ga in het beheercentrum naar **de** \> **instellingeninstellingen van organisatie**en kies onder tabblad **Services** De optie **Rapporten**.</span><span class="sxs-lookup"><span data-stu-id="c1726-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="c1726-148">Selecteer **Rapporten**en kies vervolgens voor **Anonieme id's weergeven**.</span><span class="sxs-lookup"><span data-stu-id="c1726-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="c1726-149">Deze instelling wordt zowel toegepast op de gebruiksrapporten als op de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="c1726-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="c1726-150">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c1726-150">Select **Save changes**.</span></span>
