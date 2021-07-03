---
title: Microsoft 365 Gebruiksanalyse inschakelen
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Meer informatie over het verzamelen van gegevens voor uw tenant met de Microsoft 365 de sjabloon-app Gebruiksanalyse in Power BI.
ms.openlocfilehash: 4a3110ead76621e93e646577189b7b03d65caf1d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286067"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="fb43b-103">Microsoft 365 Gebruiksanalyse inschakelen</span><span class="sxs-lookup"><span data-stu-id="fb43b-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="fb43b-104">Microsoft 365 gebruiksanalyse is nog niet beschikbaar voor Microsoft 365 Amerikaanse overheidsgemeenschap.</span><span class="sxs-lookup"><span data-stu-id="fb43b-104">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fb43b-105">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="fb43b-105">Before you begin</span></span>

<span data-ttu-id="fb43b-106">Als u wilt beginnen met Microsoft 365 gebruiksanalyse, moet u eerst de gegevens beschikbaar maken in de Microsoft 365-beheercentrum en vervolgens de sjabloon-app starten in Power BI.</span><span class="sxs-lookup"><span data-stu-id="fb43b-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>

## <a name="get-power-bi"></a><span data-ttu-id="fb43b-107">Power BI downloaden</span><span class="sxs-lookup"><span data-stu-id="fb43b-107">Get Power BI</span></span>

<span data-ttu-id="fb43b-108">Als u nog geen Power BI hebt, kunt u [zich registreren voor Power BI Pro.](https://go.microsoft.com/fwlink/p/?linkid=845347)</span><span class="sxs-lookup"><span data-stu-id="fb43b-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="fb43b-109">Selecteer **Gratis proberen** om u aan te melden voor een proefabonnement of Nu kopen **om** uw Power BI Pro.</span><span class="sxs-lookup"><span data-stu-id="fb43b-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>


<span data-ttu-id="fb43b-110">U kunt ook **Products** uitvouwen om een versie van Power BI te kopen.</span><span class="sxs-lookup"><span data-stu-id="fb43b-110">You can also expand **Products** to buy a version of Power BI.</span></span>

> [!NOTE]
> <span data-ttu-id="fb43b-111">U hebt een Power BI Pro nodig om een sjabloon-app te installeren, aan te passen en te distribueren.</span><span class="sxs-lookup"><span data-stu-id="fb43b-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="fb43b-112">Zie Vereisten voor [meer informatie.](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="fb43b-112">For more information, please see [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="fb43b-113">Als u uw gegevens wilt delen, hebben zowel u als de personen met wie u de gegevens deelt, een Power BI Pro-licentie nodig of moet de inhoud zich in een werkruimte in een [Power BI premium-service.](/power-bi/service-premium-what-is)</span><span class="sxs-lookup"><span data-stu-id="fb43b-113">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](/power-bi/service-premium-what-is).</span></span>

## <a name="enable-the-template-app"></a><span data-ttu-id="fb43b-114">De sjabloon-app inschakelen</span><span class="sxs-lookup"><span data-stu-id="fb43b-114">Enable the template app</span></span>

<span data-ttu-id="fb43b-115">Als u de sjabloon-app wilt inschakelen, moet u een globale **beheerder zijn.**</span><span class="sxs-lookup"><span data-stu-id="fb43b-115">To enable the template app, you have to be a **Global administrator**.</span></span>

<span data-ttu-id="fb43b-116">Zie [beheerdersrollen voor](../add-users/about-admin-roles.md) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="fb43b-116">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span>

1. <span data-ttu-id="fb43b-117">Ga in het beheercentrum naar het **tabblad Instellingen** \> **instellingen** \> **services.**</span><span class="sxs-lookup"><span data-stu-id="fb43b-117">In the admin center, go to the **Settings** \> **Org settings** \> **Services** tab.</span></span>

2. <span data-ttu-id="fb43b-118">Selecteer op **het tabblad** Services de optie  **Rapporten**.</span><span class="sxs-lookup"><span data-stu-id="fb43b-118">On the **Services** tab, select  **Reports**.</span></span>

3. <span data-ttu-id="fb43b-119">Stel in het deelvenster Rapporten dat wordt geopend rapportgegevens beschikbaar maken voor **Microsoft 365 gebruiksanalyse** voor Power BI op **Opslaan** \> .</span><span class="sxs-lookup"><span data-stu-id="fb43b-119">On the Reports panel that opens, set **Make report data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span>

<span data-ttu-id="fb43b-120">Het proces voor het verzamelen van gegevens wordt in twee tot 48 uur voltooid, afhankelijk van de grootte van uw tenant.</span><span class="sxs-lookup"><span data-stu-id="fb43b-120">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="fb43b-121">De knop **Ga naar Power BI** zal ingeschakeld zijn (niet langer grijs) als het verzamelen van gegevens is voltooid.</span><span class="sxs-lookup"><span data-stu-id="fb43b-121">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span>

## <a name="start-the-template-app"></a><span data-ttu-id="fb43b-122">De sjabloon-app starten</span><span class="sxs-lookup"><span data-stu-id="fb43b-122">Start the template app</span></span>

<span data-ttu-id="fb43b-123">Als u de sjabloon-app wilt starten, moet u een globale **beheerder,** **rapportlezer,** Exchange **beheerder,** Skype voor Bedrijven **beheerder** of SharePoint beheerder **zijn.**</span><span class="sxs-lookup"><span data-stu-id="fb43b-123">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span>

1. <span data-ttu-id="fb43b-124">Kopieer de tenant-id en selecteer **Ga naar Power BI.**</span><span class="sxs-lookup"><span data-stu-id="fb43b-124">Copy the tenant ID and select **Go to Power BI**.</span></span>

2. <span data-ttu-id="fb43b-125">Meld u aan wanneer u in Power BI komt.</span><span class="sxs-lookup"><span data-stu-id="fb43b-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="fb43b-126">Selecteer **vervolgens Apps** Downloaden van -> **apps** in het navigatiemenu.</span><span class="sxs-lookup"><span data-stu-id="fb43b-126">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>

3. <span data-ttu-id="fb43b-127">In het tabblad **Apps** typt u Microsoft 365 in het zoekvak en selecteer vervolgens **Microsoft 365 Gebruiksanalyse** \> **Koop het vandaag nog**.</span><span class="sxs-lookup"><span data-stu-id="fb43b-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="fb43b-128">[![Selecteer Nu krijgen](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="fb43b-128">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>

4. <span data-ttu-id="fb43b-129">Zodra de app is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="fb43b-129">Once the app is installed.</span></span> <span data-ttu-id="fb43b-130">Selecteer de tegel om deze te openen.</span><span class="sxs-lookup"><span data-stu-id="fb43b-130">Select the tile to open it.</span></span>

5. <span data-ttu-id="fb43b-131">Selecteer **Verken de app** om de app te bekijken met voorbeeldgegevens.</span><span class="sxs-lookup"><span data-stu-id="fb43b-131">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="fb43b-132">Kies **Verbinding maken** om de app te verbinden met de gegevens van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="fb43b-132">Choose **Connect** to connect the app to your organization’s data.</span></span>

6. <span data-ttu-id="fb43b-133">Kies **Verbinding maken**, op het **scherm Verbinding maken** voor Microsoft 365 gebruiksanalyse, typ vervolgens de tenant-id (zonder streepjes) die u hebt gekopieerd in stap (1) en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="fb43b-133">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>

7. <span data-ttu-id="fb43b-134">Selecteer in het volgende scherm **OAuth2** als **verificatiemethode** \> **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="fb43b-134">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="fb43b-135">Als u een andere verificatiemethode kiest, mislukt de verbinding met de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="fb43b-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>

    ![Microsoft-account kiezen als verificatiemethode](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)

8. <span data-ttu-id="fb43b-137">Nadat de sjabloon-app is instantiated, is Microsoft 365 dashboard voor gebruiksanalyse beschikbaar in Power BI op internet.</span><span class="sxs-lookup"><span data-stu-id="fb43b-137">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="fb43b-138">Het eerste laden van het dashboard duurt 2 tot 30 minuten.</span><span class="sxs-lookup"><span data-stu-id="fb43b-138">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>

<span data-ttu-id="fb43b-139">Aggregaten op tenantniveau zijn beschikbaar in alle rapporten nadat u zich heeft geaggregeerd.</span><span class="sxs-lookup"><span data-stu-id="fb43b-139">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="fb43b-140">**Details op gebruikersniveau zijn pas beschikbaar rond de 5e van de volgende kalendermaand na** het kiezen van de .</span><span class="sxs-lookup"><span data-stu-id="fb43b-140">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="fb43b-141">Dit is van invloed op alle rapporten onder Gebruikersactiviteit (Zie Navigeren en gebruik de rapporten in Microsoft 365 [gebruiksanalyse](navigate-and-utilize-reports.md) voor tips over het weergeven en gebruiken van deze rapporten).</span><span class="sxs-lookup"><span data-stu-id="fb43b-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>

## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="fb43b-142">Verzamelde gegevens anoniem maken</span><span class="sxs-lookup"><span data-stu-id="fb43b-142">Make the collected data anonymous</span></span>

<span data-ttu-id="fb43b-143">Alleen hoofdbeheerders kunnen de gegevens die worden verzameld voor alle rapporten anoniem maken.</span><span class="sxs-lookup"><span data-stu-id="fb43b-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="fb43b-144">Hiermee worden identificeerbare gegevens zoals gebruikers-, groeps- en sitenamen in rapporten en in de sjabloon-app verborgen.</span><span class="sxs-lookup"><span data-stu-id="fb43b-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>

1. <span data-ttu-id="fb43b-145">Ga in het beheercentrum naar de **Instellingen** Organisatie Instellingen en kies onder het \> tabblad **Services** de optie **Rapporten.**</span><span class="sxs-lookup"><span data-stu-id="fb43b-145">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>

2. <span data-ttu-id="fb43b-146">Selecteer **Rapporten** en kies vervolgens **Anonieme id's weergeven.**</span><span class="sxs-lookup"><span data-stu-id="fb43b-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="fb43b-147">Deze instelling wordt toegepast op zowel de gebruiksrapporten als op de sjabloon-app.</span><span class="sxs-lookup"><span data-stu-id="fb43b-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>

3. <span data-ttu-id="fb43b-148">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fb43b-148">Select **Save changes**.</span></span>

## <a name="related-content"></a><span data-ttu-id="fb43b-149">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="fb43b-149">Related content</span></span>

<span data-ttu-id="fb43b-150">[Over gebruiksanalyse](usage-analytics.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="fb43b-150">[About usage analytics](usage-analytics.md) (article)</span></span>\
<span data-ttu-id="fb43b-151">[De nieuwste versie van gebruiksanalyse](get-the-latest-version-of-usage-analytics.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="fb43b-151">[Get the latest version of usage analytics](get-the-latest-version-of-usage-analytics.md) (article)</span></span>\
<span data-ttu-id="fb43b-152">[Navigeren en de rapporten gebruiken in Microsoft 365 gebruiksanalyse](navigate-and-utilize-reports.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="fb43b-152">[Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) (article)</span></span>