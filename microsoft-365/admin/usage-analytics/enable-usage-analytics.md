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
ms.openlocfilehash: 734712994d47fcb234ba988bb4d185d09f3267d0
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471055"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="bff1e-103">Microsoft 365 Gebruiksanalyse inschakelen</span><span class="sxs-lookup"><span data-stu-id="bff1e-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="bff1e-104">Microsoft 365 gebruiksanalyse is nog niet beschikbaar voor de Amerikaanse overheid van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bff1e-104">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="bff1e-105">Stappen voor het inschakelen van Microsoft 365 Gebruiksanalyse</span><span class="sxs-lookup"><span data-stu-id="bff1e-105">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="bff1e-106">Als u wilt beginnen met gebruiksanalyses van Microsoft 365, moet u eerst de gegevens beschikbaar stellen in het Microsoft 365-beheercentrum en vervolgens de sjabloon-app starten in Power BI.</span><span class="sxs-lookup"><span data-stu-id="bff1e-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="bff1e-107">Power BI downloaden</span><span class="sxs-lookup"><span data-stu-id="bff1e-107">Get Power BI</span></span>

<span data-ttu-id="bff1e-108">Als u Power BI nog niet hebt, kunt u [zich registreren voor Power BI Pro.](https://go.microsoft.com/fwlink/p/?linkid=845347)</span><span class="sxs-lookup"><span data-stu-id="bff1e-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="bff1e-109">Selecteer **Gratis proberen** om u aan te melden voor een proefabonnement of Nu kopen **om** Power BI Pro te downloaden.</span><span class="sxs-lookup"><span data-stu-id="bff1e-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="bff1e-110">U kunt ook **Products** uitvouwen om een versie van Power BI te kopen.</span><span class="sxs-lookup"><span data-stu-id="bff1e-110">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="bff1e-111">U hebt een Power BI Pro-licentie nodig om een sjabloon-app te installeren, aan te passen en te distribueren.</span><span class="sxs-lookup"><span data-stu-id="bff1e-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="bff1e-112">Zie Vereisten voor [meer informatie.](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="bff1e-112">For more information, please see [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="bff1e-113">Als u uw gegevens wilt delen, hebben u en de personen met wie u de gegevens deelt, een Power BI Pro-licentie nodig of moet de inhoud zich in een werkruimte in een [Power BI Premium-service hebben.](/power-bi/service-premium-what-is)</span><span class="sxs-lookup"><span data-stu-id="bff1e-113">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="bff1e-114">De sjabloon-app inschakelen</span><span class="sxs-lookup"><span data-stu-id="bff1e-114">Enable the template app</span></span>

<span data-ttu-id="bff1e-115">Als u de sjabloon-app wilt inschakelen, moet u een globale **beheerder zijn.**</span><span class="sxs-lookup"><span data-stu-id="bff1e-115">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="bff1e-116">Zie [beheerdersrollen voor](../add-users/about-admin-roles.md) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bff1e-116">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="bff1e-117">Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.</span><span class="sxs-lookup"><span data-stu-id="bff1e-117">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="bff1e-118">Zoek op **de** pagina Gebruik de **microsoft 365-gebruiksanalysekaart** en selecteer **Aan de slag.**</span><span class="sxs-lookup"><span data-stu-id="bff1e-118">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="bff1e-119">Stel gegevens beschikbaar maken voor **Microsoft 365** gebruiksanalyse voor Power BI in op Opslaan in het deelvenster Rapporten **dat wordt** \> **geopend.**</span><span class="sxs-lookup"><span data-stu-id="bff1e-119">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="bff1e-120">Het proces voor het verzamelen van gegevens wordt in twee tot 48 uur voltooid, afhankelijk van de grootte van uw tenant.</span><span class="sxs-lookup"><span data-stu-id="bff1e-120">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="bff1e-121">De knop **Ga naar Power BI** zal ingeschakeld zijn (niet langer grijs) als het verzamelen van gegevens is voltooid.</span><span class="sxs-lookup"><span data-stu-id="bff1e-121">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="bff1e-122">De sjabloon-app starten</span><span class="sxs-lookup"><span data-stu-id="bff1e-122">Start the template app</span></span>

<span data-ttu-id="bff1e-123">Als u de sjabloon-app wilt starten, moet u een globale **beheerder,** **rapportlezer,** **Exchange-beheerder,** **Skype voor Bedrijven-beheerder** of **SharePoint-beheerder zijn.**</span><span class="sxs-lookup"><span data-stu-id="bff1e-123">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="bff1e-124">Kopieer de tenant-id en selecteer **Ga naar Power BI.**</span><span class="sxs-lookup"><span data-stu-id="bff1e-124">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="bff1e-125">Meld u aan wanneer u in Power BI komt.</span><span class="sxs-lookup"><span data-stu-id="bff1e-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="bff1e-126">Selecteer **vervolgens Apps** Downloaden van -> **apps** in het navigatiemenu.</span><span class="sxs-lookup"><span data-stu-id="bff1e-126">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="bff1e-127">In het tabblad **Apps** typt u Microsoft 365 in het zoekvak en selecteer vervolgens **Microsoft 365 Gebruiksanalyse** \> **Koop het vandaag nog**.</span><span class="sxs-lookup"><span data-stu-id="bff1e-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="bff1e-128">[![Selecteer Nu krijgen](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="bff1e-128">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="bff1e-129">Zodra de app is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="bff1e-129">Once the app is installed.</span></span> <span data-ttu-id="bff1e-130">Selecteer de tegel om deze te openen.</span><span class="sxs-lookup"><span data-stu-id="bff1e-130">Select the tile to open it.</span></span>

5.  <span data-ttu-id="bff1e-131">Selecteer **Verken de app** om de app te bekijken met voorbeeldgegevens.</span><span class="sxs-lookup"><span data-stu-id="bff1e-131">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="bff1e-132">Kies **Verbinding** maken om de app te verbinden met de gegevens van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="bff1e-132">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="bff1e-133">Kies **Verbinding** maken in het scherm Verbinding maken met **Microsoft 365** gebruiksanalyse en typ vervolgens de tenant-id (zonder streepjes) die u hebt gekopieerd in stap (1) en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="bff1e-133">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="bff1e-134">Selecteer in het volgende scherm **OAuth2** als **verificatiemethode** \> **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="bff1e-134">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="bff1e-135">Als u een andere verificatiemethode kiest, mislukt de verbinding met de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="bff1e-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Microsoft-account kiezen als verificatiemethode](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="bff1e-137">Nadat de sjabloon-app is instantiated, is het Microsoft 365-dashboard voor gebruiksanalyse beschikbaar in de webwinkel van Power BI.</span><span class="sxs-lookup"><span data-stu-id="bff1e-137">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="bff1e-138">Het eerste laden van het dashboard duurt 2 tot 30 minuten.</span><span class="sxs-lookup"><span data-stu-id="bff1e-138">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="bff1e-139">Aggregaten op tenantniveau zijn beschikbaar in alle rapporten nadat u zich heeft geaggregeerd.</span><span class="sxs-lookup"><span data-stu-id="bff1e-139">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="bff1e-140">**Details op gebruikersniveau zijn pas beschikbaar rond de 5e van de volgende kalendermaand na** het kiezen van de .</span><span class="sxs-lookup"><span data-stu-id="bff1e-140">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="bff1e-141">Dit is van invloed op alle rapporten onder Gebruikersactiviteit (Zie Navigeren en gebruik de rapporten in Gebruiksanalyse van [Microsoft 365](navigate-and-utilize-reports.md) voor tips over het weergeven en gebruiken van deze rapporten).</span><span class="sxs-lookup"><span data-stu-id="bff1e-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="bff1e-142">Verzamelde gegevens anoniem maken</span><span class="sxs-lookup"><span data-stu-id="bff1e-142">Make the collected data anonymous</span></span>

<span data-ttu-id="bff1e-143">Alleen hoofdbeheerders kunnen de gegevens die worden verzameld voor alle rapporten anoniem maken.</span><span class="sxs-lookup"><span data-stu-id="bff1e-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="bff1e-144">Hiermee worden identificeerbare gegevens zoals gebruikers-, groeps- en sitenamen in rapporten en in de sjabloon-app verborgen.</span><span class="sxs-lookup"><span data-stu-id="bff1e-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="bff1e-145">Ga in het beheercentrum naar **instellingen** \> **voor organisatie-instellingen** en kies onder **het tabblad Services** de optie **Rapporten.**</span><span class="sxs-lookup"><span data-stu-id="bff1e-145">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="bff1e-146">Selecteer **Rapporten** en kies vervolgens **Anonieme id's weergeven.**</span><span class="sxs-lookup"><span data-stu-id="bff1e-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="bff1e-147">Deze instelling wordt toegepast op zowel de gebruiksrapporten als op de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="bff1e-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="bff1e-148">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="bff1e-148">Select **Save changes**.</span></span>