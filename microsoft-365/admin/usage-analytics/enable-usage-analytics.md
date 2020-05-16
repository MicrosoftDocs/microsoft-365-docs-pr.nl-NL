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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Meer informatie over het verzamelen van gegevens voor uw tenant met de sjabloon-app Microsoft 365 Usage Analytics in Power BI.
ms.openlocfilehash: 3c5e1a35b93b755b92710f0499599d849a6c251c
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262533"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="ce234-103">Microsoft 365 Gebruiksanalyse inschakelen</span><span class="sxs-lookup"><span data-stu-id="ce234-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="ce234-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="ce234-104">The admin center is changing.</span></span> <span data-ttu-id="ce234-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="ce234-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="ce234-106">Microsoft 365-gebruiksanalyses zijn ook beschikbaar voor de Microsoft 365-overheidsgemeenschap van de Amerikaanse overheid.</span><span class="sxs-lookup"><span data-stu-id="ce234-106">Microsoft 365 usage analytics is also available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="ce234-107">Stappen voor het inschakelen van Microsoft 365 Gebruiksanalyse</span><span class="sxs-lookup"><span data-stu-id="ce234-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="ce234-108">Om aan de slag te gaan met Microsoft 365-gebruiksanalyses moet u de gegevens eerst beschikbaar maken in het Microsoft 365-beheercentrum en vervolgens de sjabloon-app starten in Power BI.</span><span class="sxs-lookup"><span data-stu-id="ce234-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="ce234-109">Power BI downloaden</span><span class="sxs-lookup"><span data-stu-id="ce234-109">Get Power BI</span></span>

<span data-ttu-id="ce234-110">Als u nog geen Power BI hebt, u [zich aanmelden voor Power BI Pro.](https://go.microsoft.com/fwlink/p/?linkid=845347)</span><span class="sxs-lookup"><span data-stu-id="ce234-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="ce234-111">Selecteer **Probeer je gratis** aan te melden voor een proefversie of Koop **nu** om Power BI Pro te krijgen.</span><span class="sxs-lookup"><span data-stu-id="ce234-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="ce234-112">U kunt ook **Products** uitvouwen om een versie van Power BI te kopen.</span><span class="sxs-lookup"><span data-stu-id="ce234-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="ce234-113">U hebt een Power BI Pro-licentie nodig om een sjabloon-app te installeren, aan te passen en te distribueren.</span><span class="sxs-lookup"><span data-stu-id="ce234-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="ce234-114">Zie [Voorwaarden voor](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ce234-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="ce234-115">U hebt een Power BI Pro-licentie nodig om uw inhoud te delen, en de mensen met wie u deze deelt, doen dat ook, of de inhoud moet zich in een werkruimte in een [Premium-capaciteit bevinden.](https://docs.microsoft.com/power-bi/service-premium-what-is)</span><span class="sxs-lookup"><span data-stu-id="ce234-115">You need a Power BI Pro license to share your content, and the people you share it with do too, or the content needs to be in a workspace in a [Premium capacity](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="ce234-116">De sjabloon-app inschakelen</span><span class="sxs-lookup"><span data-stu-id="ce234-116">Enable the template app</span></span>

<span data-ttu-id="ce234-117">Als u de sjabloon-app wilt inschakelen, moet u een **globale beheerder**zijn, **rapportlezer,** **Exchange-beheerder,** **Skype voor Bedrijven-beheerder**of **SharePoint-beheerder**.</span><span class="sxs-lookup"><span data-stu-id="ce234-117">To enable the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
<span data-ttu-id="ce234-118">Zie [Over beheerdersrollen](../add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ce234-118">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="ce234-119">Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.</span><span class="sxs-lookup"><span data-stu-id="ce234-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="ce234-120">Zoek **op** de pagina Gebruik de **Microsoft 365-analysekaart voor gebruik** en selecteer Aan de **slag**.</span><span class="sxs-lookup"><span data-stu-id="ce234-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="ce234-121">Stel gegevens beschikbaar maken **voor Microsoft 365-gebruiksanalyses voor Power BI** **in** het deelvenster Rapporten dat wordt \> **Save**geopend.</span><span class="sxs-lookup"><span data-stu-id="ce234-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="ce234-p104">Hiermee wordt het gegevensverzamelingsproces gestart, en dit zal voltooid worden in 2 tot 48 uur, afhankelijk van de grootte van uw tenant. De knop **Ga naar Power BI** zal ingeschakeld zijn (niet langer grijs) als het verzamelen van gegevens is voltooid.</span><span class="sxs-lookup"><span data-stu-id="ce234-p104">This initiates the data collection process and will complete in 2 to 48 hours depending on the size of your tenant. The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="initiate-the-template-app"></a><span data-ttu-id="ce234-124">De sjabloon-app starten</span><span class="sxs-lookup"><span data-stu-id="ce234-124">Initiate the template app</span></span>

<span data-ttu-id="ce234-125">Als u de sjabloon-app wilt starten, moet u een **globale beheerder**zijn, **rapportlezer,** **Exchange-beheerder,** **Skype voor Bedrijven-beheerder**of **SharePoint-beheerder**.</span><span class="sxs-lookup"><span data-stu-id="ce234-125">To initiate the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="ce234-126">Kopieer de tenant-id en selecteer **Ga naar Power BI**.</span><span class="sxs-lookup"><span data-stu-id="ce234-126">Copy the tenant Id and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="ce234-127">Meld u aan wanneer u in Power BI komt.</span><span class="sxs-lookup"><span data-stu-id="ce234-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="ce234-128">Selecteer Apps->Apps ophalen in het navigatiemenu.</span><span class="sxs-lookup"><span data-stu-id="ce234-128">Select Apps->Get apps from the navigation menu.</span></span>    
  
3. <span data-ttu-id="ce234-129">In het tabblad **Apps** typt u Microsoft 365 in het zoekvak en selecteer vervolgens **Microsoft 365 Gebruiksanalyse** \> **Koop het vandaag nog**.</span><span class="sxs-lookup"><span data-stu-id="ce234-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="ce234-130">[![Selecteer Nu weergeven](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="ce234-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="ce234-131">Zodra de app is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="ce234-131">Once the app is installed.</span></span> <span data-ttu-id="ce234-132">Klik op de tegel om deze te openen.</span><span class="sxs-lookup"><span data-stu-id="ce234-132">Click on the tile to open it.</span></span>

5.  <span data-ttu-id="ce234-133">Klik **op App verkennen** om de app te bekijken met voorbeeldgegevens.</span><span class="sxs-lookup"><span data-stu-id="ce234-133">Click **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="ce234-134">Klik **op Verbinding maken** om de app te verbinden met de gegevens van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ce234-134">Click **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="ce234-135">Nadat u op **Verbinding hebt**geklikt , typt u in het scherm Verbinding maken met **Microsoft 365 gebruiksanalyse** de tenant-id die u in stap (1) Volgende hebt \> **Next**gekopieerd.</span><span class="sxs-lookup"><span data-stu-id="ce234-135">After clicking **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, type in the tenant Id you copied in step (1) \> **Next**.</span></span>
    
7. <span data-ttu-id="ce234-136">Selecteer in het volgende scherm **oAuth2** als **de verificatiemethode** \> **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="ce234-136">On the next screen, select **oAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="ce234-137">Als u een andere verificatiemethode kiest, mislukt de verbinding met de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="ce234-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Choose oAuth2 as authentication method](../../media/ac85a360-c278-4c60-8aa3-68f4828f1d96.png)
  
8. <span data-ttu-id="ce234-139">Zodra de sjabloon-app is geinstantieerd, is het Microsoft 365-dashboard voor gebruiksanalyse beschikbaar in Power BI op internet.</span><span class="sxs-lookup"><span data-stu-id="ce234-139">Once the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="ce234-140">Het eerste laden van het dashboard duurt 2 tot 30 minuten.</span><span class="sxs-lookup"><span data-stu-id="ce234-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="ce234-141">Samengevoegde gegevens op tenantniveau zijn beschikbaar in alle rapporten.</span><span class="sxs-lookup"><span data-stu-id="ce234-141">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="ce234-142">**Gegevens op gebruikersniveau zijn pas beschikbaar na de 1e of 15e dag van de kalendermaand na aanmelding**.</span><span class="sxs-lookup"><span data-stu-id="ce234-142">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in**.</span></span> <span data-ttu-id="ce234-143">Dit heeft gevolgen voor alle rapporten onder Gebruikersactiviteit (Zie [Navigeren en gebruik de rapporten in Microsoft 365-gebruiksanalyses](navigate-and-utilize-reports.md) voor tips over het bekijken en gebruiken van deze rapporten).</span><span class="sxs-lookup"><span data-stu-id="ce234-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="ce234-144">Verzamelde gegevens anoniem maken</span><span class="sxs-lookup"><span data-stu-id="ce234-144">Make the collected data anonymous</span></span>

<span data-ttu-id="ce234-145">Alleen hoofdbeheerders kunnen de gegevens die worden verzameld voor alle rapporten anoniem maken.</span><span class="sxs-lookup"><span data-stu-id="ce234-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="ce234-146">Hiermee worden identificeerbare informatie zoals gebruikers-, groeps- en sitenamen verborgen in rapporten en in de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="ce234-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="ce234-147">Ga in het beheercentrum **Settings** naar de \> **instellingen van de organisatie Instellingen**en kies onder het tabblad **Services** de optie **Rapporten**.</span><span class="sxs-lookup"><span data-stu-id="ce234-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="ce234-148">Selecteer **Rapporten**en kies vervolgens voor **Anonieme id's weergeven**.</span><span class="sxs-lookup"><span data-stu-id="ce234-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="ce234-149">Deze instelling wordt zowel toegepast op de gebruiksrapporten als op de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="ce234-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="ce234-150">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ce234-150">Select **Save changes**.</span></span>
