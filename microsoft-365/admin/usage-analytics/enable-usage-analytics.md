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
description: Informatie over hoe u begint met het verzamelen van gegevens voor uw tenant met behulp van de sjabloon-app Microsoft 365 Gebruiksanalyse in Power BI.
ms.openlocfilehash: 98ae107b6777ac97d0be3b37847117c6e20be63d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114235"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="586e4-103">Microsoft 365 Gebruiksanalyse inschakelen</span><span class="sxs-lookup"><span data-stu-id="586e4-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="586e4-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="586e4-104">The admin center is changing.</span></span> <span data-ttu-id="586e4-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="586e4-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="586e4-106">Microsoft 365 Gebruiksanalyse is nog niet beschikbaar voor de Microsoft 365 US Government Community.</span><span class="sxs-lookup"><span data-stu-id="586e4-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="586e4-107">Stappen voor het inschakelen van Microsoft 365 Gebruiksanalyse</span><span class="sxs-lookup"><span data-stu-id="586e4-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="586e4-108">Als u aan de slag wilt met Microsoft 365 Gebruiksanalyse, moet u eerst de gegevens beschikbaar maken in het Microsoft 365-beheercentrum en vervolgens de sjabloon-app starten in Power BI.</span><span class="sxs-lookup"><span data-stu-id="586e4-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="586e4-109">Power BI downloaden</span><span class="sxs-lookup"><span data-stu-id="586e4-109">Get Power BI</span></span>

<span data-ttu-id="586e4-110">Als u nog geen Power BI hebt, kunt u zich [registreren voor Power BI Pro.](https://go.microsoft.com/fwlink/p/?linkid=845347)</span><span class="sxs-lookup"><span data-stu-id="586e4-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="586e4-111">Selecteer **Gratis proberen** om u aan te melden voor een proefversie of Nu kopen **om** Power BI Pro te downloaden.</span><span class="sxs-lookup"><span data-stu-id="586e4-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="586e4-112">U kunt ook **Products** uitvouwen om een versie van Power BI te kopen.</span><span class="sxs-lookup"><span data-stu-id="586e4-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="586e4-113">U hebt een Power BI Pro-licentie nodig om een sjabloon-app te installeren, aan te passen en te distribueren.</span><span class="sxs-lookup"><span data-stu-id="586e4-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="586e4-114">Zie Vereisten voor [meer informatie.](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="586e4-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="586e4-115">Als u uw gegevens wilt delen, hebben zowel u als de personen met wie u de gegevens deelt een Power BI Pro-licentie nodig of moet de inhoud zich in een werkruimte in een [Power BI Premium-service hebben.](https://docs.microsoft.com/power-bi/service-premium-what-is)</span><span class="sxs-lookup"><span data-stu-id="586e4-115">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="586e4-116">De sjabloon-app inschakelen</span><span class="sxs-lookup"><span data-stu-id="586e4-116">Enable the template app</span></span>

<span data-ttu-id="586e4-117">Als u de sjabloon-app wilt inschakelen, moet u een globale **beheerder zijn.**</span><span class="sxs-lookup"><span data-stu-id="586e4-117">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="586e4-118">Meer [informatie over beheerdersrollen.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="586e4-118">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="586e4-119">Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.</span><span class="sxs-lookup"><span data-stu-id="586e4-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="586e4-120">Zoek op **de** pagina Gebruik de **Kaart Microsoft 365 Gebruiksanalyse** en selecteer **Aan de slag.**</span><span class="sxs-lookup"><span data-stu-id="586e4-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="586e4-121">Stel in het deelvenster Rapporten dat wordt geopend, Gegevens beschikbaar maken voor **Microsoft 365** Gebruiksanalyse voor Power BI in **bij** \> **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="586e4-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="586e4-122">Het proces voor het verzamelen van gegevens wordt in twee tot 48 uur voltooid, afhankelijk van de grootte van uw tenant.</span><span class="sxs-lookup"><span data-stu-id="586e4-122">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="586e4-123">De knop **Ga naar Power BI** zal ingeschakeld zijn (niet langer grijs) als het verzamelen van gegevens is voltooid.</span><span class="sxs-lookup"><span data-stu-id="586e4-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="586e4-124">De sjabloon-app starten</span><span class="sxs-lookup"><span data-stu-id="586e4-124">Start the template app</span></span>

<span data-ttu-id="586e4-125">Als u de sjabloon-app wilt starten, moet u een globale **beheerder,** **rapportlezer,** **Exchange-beheerder,** **Skype** voor Bedrijven-beheerder of **SharePoint-beheerder zijn.**</span><span class="sxs-lookup"><span data-stu-id="586e4-125">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="586e4-126">Kopieer de tenant-id en selecteer **Ga naar Power BI.**</span><span class="sxs-lookup"><span data-stu-id="586e4-126">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="586e4-127">Meld u aan wanneer u in Power BI komt.</span><span class="sxs-lookup"><span data-stu-id="586e4-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="586e4-128">Selecteer **vervolgens Apps** downloaden -> **uit** het navigatiemenu.</span><span class="sxs-lookup"><span data-stu-id="586e4-128">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="586e4-129">In het tabblad **Apps** typt u Microsoft 365 in het zoekvak en selecteer vervolgens **Microsoft 365 Gebruiksanalyse** \> **Koop het vandaag nog**.</span><span class="sxs-lookup"><span data-stu-id="586e4-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="586e4-130">[![Selecteer Nu krijgen](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="586e4-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="586e4-131">Nadat de app is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="586e4-131">Once the app is installed.</span></span> <span data-ttu-id="586e4-132">Selecteer de tegel om deze te openen.</span><span class="sxs-lookup"><span data-stu-id="586e4-132">Select the tile to open it.</span></span>

5.  <span data-ttu-id="586e4-133">Selecteer **De app Verkennen** om de app met voorbeeldgegevens weer te geven.</span><span class="sxs-lookup"><span data-stu-id="586e4-133">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="586e4-134">Kies **Verbinding maken** om de app te verbinden met de gegevens van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="586e4-134">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="586e4-135">Kies **Verbinden,** typ in het scherm Verbinding maken met **Microsoft 365** Gebruiksanalyse de tenant-id (zonder streepjes) die u in stap 1 hebt gekopieerd en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="586e4-135">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="586e4-136">Selecteer **OAuth2** in het volgende scherm als de **verificatiemethode** \> **Aanmelden.**</span><span class="sxs-lookup"><span data-stu-id="586e4-136">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="586e4-137">Als u een andere verificatiemethode kiest, mislukt de verbinding met de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="586e4-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Microsoft-account kiezen als verificatiemethode](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="586e4-139">Nadat de sjabloon-app is instantiated, is het dashboard voor Microsoft 365 Gebruiksanalyse beschikbaar in Power BI op het web.</span><span class="sxs-lookup"><span data-stu-id="586e4-139">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="586e4-140">Het eerste laden van het dashboard duurt 2 tot 30 minuten.</span><span class="sxs-lookup"><span data-stu-id="586e4-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="586e4-141">Statistische tenantniveau zijn beschikbaar in alle rapporten nadat u zich heeftmeld.</span><span class="sxs-lookup"><span data-stu-id="586e4-141">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="586e4-142">**Gebruikersdetails zijn pas beschikbaar** rond de vijfde van de volgende kalendermaand nadat u zich heeft gekozen.</span><span class="sxs-lookup"><span data-stu-id="586e4-142">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="586e4-143">Dit is van invloed op alle rapporten onder Gebruikersactiviteit (zie Navigeren en de rapporten [gebruiken in Microsoft 365](navigate-and-utilize-reports.md) Gebruiksanalyse voor tips over het weergeven en gebruiken van deze rapporten).</span><span class="sxs-lookup"><span data-stu-id="586e4-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="586e4-144">Verzamelde gegevens anoniem maken</span><span class="sxs-lookup"><span data-stu-id="586e4-144">Make the collected data anonymous</span></span>

<span data-ttu-id="586e4-145">Alleen hoofdbeheerders kunnen de gegevens die worden verzameld voor alle rapporten anoniem maken.</span><span class="sxs-lookup"><span data-stu-id="586e4-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="586e4-146">Hierdoor worden identificatiegegevens zoals namen van gebruikers, groepen en site's verborgen in rapporten en in de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="586e4-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="586e4-147">Ga in het beheercentrum  naar Instellingen organisatie-instellingen en kies rapporten op het \>  **tabblad Services.** </span><span class="sxs-lookup"><span data-stu-id="586e4-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="586e4-148">Selecteer **Rapporten** en kies voor **Het weergeven van anonieme id's.**</span><span class="sxs-lookup"><span data-stu-id="586e4-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="586e4-149">Deze instelling wordt zowel op de gebruiksrapporten als op de sjabloon-app toegepast.</span><span class="sxs-lookup"><span data-stu-id="586e4-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="586e4-150">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="586e4-150">Select **Save changes**.</span></span>
