---
title: Rapporten in Microsoft 365 Gebruiksanalyse naar voorkeur aanpassen
f1.keywords:
- NOCSH
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
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: Leer hoe u rapporten aanpast in de browser en de bureaubladversie van Power BI.
ms.openlocfilehash: 8baeb1a9f48d8f1ccdb591a60fefe863502344b6
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841421"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a><span data-ttu-id="37f32-103">Rapporten in Microsoft 365 Gebruiksanalyse naar voorkeur aanpassen</span><span class="sxs-lookup"><span data-stu-id="37f32-103">Customize the reports in Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="37f32-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="37f32-104">The admin center is changing.</span></span> <span data-ttu-id="37f32-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="37f32-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="37f32-106">Microsoft 365 gebruiksanalyse biedt een dashboard in Power BI waarmee u inzicht krijgt in de manier waarop gebruikers Microsoft 365 aannemen en gebruiken.</span><span class="sxs-lookup"><span data-stu-id="37f32-106">Microsoft 365 usage analytics provides a dashboard in Power BI that offers insights into how users adopt and use Microsoft 365.</span></span> <span data-ttu-id="37f32-107">Het dashboard is alleen een beginpunt voor interactie met de gebruiksgegevens.</span><span class="sxs-lookup"><span data-stu-id="37f32-107">The dashboard is just a starting point to interact with the usage data.</span></span> <span data-ttu-id="37f32-108">De rapporten kunnen worden aangepast voor meer persoonlijke inzichten.</span><span class="sxs-lookup"><span data-stu-id="37f32-108">The reports can be customized for more personalized insights.</span></span>
  
<span data-ttu-id="37f32-109">U kunt ook Power BI Desktop gebruiken om uw rapporten verder aan te passen, door verbinding te maken met andere gegevensbronnen voor nog uitgebreidere inzichten in uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="37f32-109">You can also use the Power BI desktop to further customize your reports by connecting them to other data sources to gain richer insights about your business.</span></span>
  
## <a name="customizing-reports-in-the-browser"></a><span data-ttu-id="37f32-110">Rapporten aanpassen in de browser</span><span class="sxs-lookup"><span data-stu-id="37f32-110">Customizing reports in the browser</span></span>

<span data-ttu-id="37f32-111">In de volgende twee voorbeelden ziet u hoe u een bestaand visueel element kunt aanpassen en een nieuw visueel element kunt maken.</span><span class="sxs-lookup"><span data-stu-id="37f32-111">The following two examples show how to modify an existing visual and how to create a new visual.</span></span>
  
### <a name="modify-an-existing-visual"></a><span data-ttu-id="37f32-112">Een bestaand visueel element wijzigen</span><span class="sxs-lookup"><span data-stu-id="37f32-112">Modify an existing visual</span></span>

<span data-ttu-id="37f32-113">In dit voorbeeld ziet u hoe u het tabblad **Activering** kunt wijzigen in het rapport **Activering/licentieverlening** .</span><span class="sxs-lookup"><span data-stu-id="37f32-113">This example shows how to modify the **Activation** tab within the **Activation/Licensing** report.</span></span> 
  
1. <span data-ttu-id="37f32-114">Selecteer in het rapport **Activering/licentieverlening** het tabblad **Activering** .</span><span class="sxs-lookup"><span data-stu-id="37f32-114">Within the **Activation/Licensing** report, select the **Activation** tab.</span></span>
    
2. <span data-ttu-id="37f32-115">Voer de bewerkingsmodus in door op de knop **bewerken** te klikken op de bovenkant via de knop ![ meer pagina op de Power bi- ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) knop.</span><span class="sxs-lookup"><span data-stu-id="37f32-115">Enter the edit mode by choosing the **Edit** button on the top through the ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) button.</span></span> 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. <span data-ttu-id="37f32-117">Kies in de rechterbovenhoek de optie **Deze pagina dupliceren** .</span><span class="sxs-lookup"><span data-stu-id="37f32-117">On the top right, choose **Duplicate this page** .</span></span>
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. <span data-ttu-id="37f32-119">Kies in de rechterbenedenhoek een van de staaf-grafieken met het aantal gebruikers dat is geactiveerd op basis van het besturingssysteem, zoals Android, iOS, Mac, etc.</span><span class="sxs-lookup"><span data-stu-id="37f32-119">In the bottom right, choose any of the bar-charts showing the count of users activating based on the OS such as Android, iOS, Mac, etc.</span></span>
    
5. <span data-ttu-id="37f32-120">Selecteer in het gebied **Visualisaties** aan de rechterkant de **X** ernaast om het **aantal** te verwijderen uit het visuele element.</span><span class="sxs-lookup"><span data-stu-id="37f32-120">In the **Visualizations** area to the right, in order to remove **Mac Count** from the visual, select the **X** next to it.</span></span>

    ![Mac-aantal verwijderen](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a><span data-ttu-id="37f32-122">Een nieuw visueel element maken</span><span class="sxs-lookup"><span data-stu-id="37f32-122">Create a new visual</span></span>

<span data-ttu-id="37f32-123">In het volgende voorbeeld ziet u hoe u een nieuw visueel element maakt voor het bijhouden van nieuwe Yammer-gebruikers op maandbasis.</span><span class="sxs-lookup"><span data-stu-id="37f32-123">The following example shows how to create a new visual to track new Yammer users on monthly basis.</span></span>
  
1. <span data-ttu-id="37f32-124">Ga naar het rapport **product gebruik** met de linkernavigatiebalk en selecteer het tabblad **Yammer** .</span><span class="sxs-lookup"><span data-stu-id="37f32-124">Go to the **Product Usage** report using the left nav and select the **Yammer** tab.</span></span>
    
2. <span data-ttu-id="37f32-125">Ga naar de bewerkingsmodus door te klikken op ![ de knop meer pagina in Power bi ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) en **bewerken** .</span><span class="sxs-lookup"><span data-stu-id="37f32-125">Switch to edit mode by choosing ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) and **Edit** .</span></span> 
    
3. <span data-ttu-id="37f32-126">Selecteer onder aan de pagina de</span><span class="sxs-lookup"><span data-stu-id="37f32-126">At the bottom of the page, select the</span></span> ![De knop pagina toevoegen in Power BI](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) <span data-ttu-id="37f32-128">om een nieuwe pagina te maken.</span><span class="sxs-lookup"><span data-stu-id="37f32-128">to create a new page.</span></span>
  
4. <span data-ttu-id="37f32-129">Kies in het gebied **Visualisaties** aan de rechterkant het **gestapeld staafdiagram** (bovenste rij, eerst van links).</span><span class="sxs-lookup"><span data-stu-id="37f32-129">In the **Visualizations** area to the right, choose the **Stacked bar chart** (top row, first from left).</span></span>

    ![Staafdiagram selecteren](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. <span data-ttu-id="37f32-131">Selecteer de rechterbenedenhoek van de visualisatie en sleep om deze groter te maken.</span><span class="sxs-lookup"><span data-stu-id="37f32-131">Select the bottom right of that visualization and drag to make it larger.</span></span>

6. <span data-ttu-id="37f32-132">Vouw in het gedeelte **velden** aan de rechterkant de tabel **agenda** uit.</span><span class="sxs-lookup"><span data-stu-id="37f32-132">In the **Fields** area to the right, expand the **Calendar** table.</span></span>

7. <span data-ttu-id="37f32-133">Sleep **MonthName** naar het gedeelte met velden, direct onder de koptekst **As** in het gedeelte **Visualisaties** .</span><span class="sxs-lookup"><span data-stu-id="37f32-133">Drag **MonthName** to the fields area, directly below the **Axis** heading in the **Visualizations** area.</span></span>
 
    ![Naam van maand slepen](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. <span data-ttu-id="37f32-135">Vouw in het gedeelte **Velden** aan de rechterkant de tabel **TenantProductUsage** uit.</span><span class="sxs-lookup"><span data-stu-id="37f32-135">In the **Fields** area to the right, expand the **TenantProductUsage** table.</span></span>

9. <span data-ttu-id="37f32-136">Sleep **FirstTimeUsers** naar het gedeelte met velden, direct onder de koptekst **Waarde** .</span><span class="sxs-lookup"><span data-stu-id="37f32-136">Drag **FirstTimeUsers** to the fields area, directly below the **Value** heading.</span></span>

10. <span data-ttu-id="37f32-137">Sleep **Product** naar het gedeelte **Filters** , direct onder de koptekst **Filters op niveau van visuele elementen** .</span><span class="sxs-lookup"><span data-stu-id="37f32-137">Drag **Product** to the **Filters** area, directly below the **Visual level filters** heading.</span></span>

11. <span data-ttu-id="37f32-138">Selecteer in het gedeelte **Filtertype** dat wordt weergegeven het selectievakje **Yammer** .</span><span class="sxs-lookup"><span data-stu-id="37f32-138">In the **Filter Type** area that appears, select the **Yammer** check box.</span></span>

    ![Selectievakje Yammer selecteren](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. <span data-ttu-id="37f32-140">Kies net onder de lijst met visualisaties het pictogram opmaak **pictogram opmaak** ![ in Power bi--visualisaties ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) .</span><span class="sxs-lookup"><span data-stu-id="37f32-140">Just below the list of visualizations, choose the **Format** icon ![Format icon in Power BI Visualizaions](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).</span></span>

13. <span data-ttu-id="37f32-141">Vouw Titel uit en wijzig de waarde **Titel** in **Nieuwe gebruikers van Yammer per maand** .</span><span class="sxs-lookup"><span data-stu-id="37f32-141">Expand Title and change the **Title Text** value to **First-Time Yammer Users by Month** .</span></span>
    
14. <span data-ttu-id="37f32-142">Wijzig de **Tekengrootte** in **12** .</span><span class="sxs-lookup"><span data-stu-id="37f32-142">Change the **Text Size** value to **12** .</span></span>
    
15. <span data-ttu-id="37f32-143">Wijzig de titel van de nieuwe pagina door de naam van de pagina aan de rechterkant te bewerken.</span><span class="sxs-lookup"><span data-stu-id="37f32-143">Change the title of the new page by editing the name of the page on bottom right.</span></span>

16.  <span data-ttu-id="37f32-144">Sla het rapport op door op de **leesweergave** op de bovenkant en op **Opslaan** te klikken.</span><span class="sxs-lookup"><span data-stu-id="37f32-144">Save out the report by Clicking on **Reading View** on top and then **Save** .</span></span>
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a><span data-ttu-id="37f32-145">De rapporten in Power BI Desktop aanpassen</span><span class="sxs-lookup"><span data-stu-id="37f32-145">Customizing the reports in Power BI Desktop</span></span>

<span data-ttu-id="37f32-p103">Voor de meeste klanten is het aanpassen van de rapporten en visuele elementen van grafieken op de Power BI-website voldoende. Sommige klanten willen deze gegevens echter misschien koppelen aan andere gegevensbronnen voor uitgebreidere inzichten in de context van hun eigen bedrijf. In dat geval kunnen ze rapporten aanpassen en aanvullende rapporten maken met Power BI Desktop. U kunt [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) gratis downloaden.</span><span class="sxs-lookup"><span data-stu-id="37f32-p103">For most customers modifying the reports and chart visuals in Power BI web will be sufficient. For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop. You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free.</span></span> 
  
### <a name="use-the-reporting-apis"></a><span data-ttu-id="37f32-149">De rapportage-API's gebruiken</span><span class="sxs-lookup"><span data-stu-id="37f32-149">Use the reporting APIs</span></span>

<span data-ttu-id="37f32-150">U kunt beginnen met het maken van een directe verbinding met de ODATA-rapportage-Api's van Microsoft 365, waardoor deze rapporten worden opgenomen.</span><span class="sxs-lookup"><span data-stu-id="37f32-150">You can start by connecting directly to the ODATA reporting APIs from Microsoft 365 that power these reports.</span></span>
  
1. <span data-ttu-id="37f32-151">Ga naar **Gegevens ophalen** \> **Overige** \> **ODATA-feed** \> **Verbinding maken** .</span><span class="sxs-lookup"><span data-stu-id="37f32-151">Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect** .</span></span>
    
2. <span data-ttu-id="37f32-152">Voer in het venster URL het https:// <i></i> Reports.Office.com/pbi/v1.0/ \<tenantid\> in</span><span class="sxs-lookup"><span data-stu-id="37f32-152">In the URL window enter "https://<i></i>reports.office.com/pbi/v1.0/\<tenantid\>"</span></span>
    
    <span data-ttu-id="37f32-153">**Opmerking:** De rapportage-Api's zijn een preview-versie en kunnen worden gewijzigd totdat ze in de productie gaan.</span><span class="sxs-lookup"><span data-stu-id="37f32-153">**NOTE:** The reporting APIs are in preview and are subject to change until they go into production.</span></span> 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. <span data-ttu-id="37f32-155">Voer uw beheerdersreferenties voor Microsoft 365 (organisatie of school) in om u aan te melden bij Microsoft 365 wanneer hierom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="37f32-155">Enter your Microsoft 365 (organization or school) admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
    <span data-ttu-id="37f32-156">Zie de [Veelgestelde vragen](usage-analytics.md#faq) voor meer informatie over wie er toegang kan krijgen tot de app-rapporten van de microsoft 365-acceptatie sjabloon.</span><span class="sxs-lookup"><span data-stu-id="37f32-156">See the [FAQ](usage-analytics.md#faq) for more information about who is allowed to access the Microsoft 365 Adoption template app reports.</span></span> 
    
4. <span data-ttu-id="37f32-157">Zodra de verbinding is geautoriseerd, wordt het Navigator-venster weergegeven met de gegevenssets waarmee u verbinding kunt maken.</span><span class="sxs-lookup"><span data-stu-id="37f32-157">Once the connection is authorized, you will see the Navigator window that shows the datasets available to connect to.</span></span>
    
    <span data-ttu-id="37f32-158">Selecteer alles en klik op **laden** .</span><span class="sxs-lookup"><span data-stu-id="37f32-158">Select all and choose **Load** .</span></span>
    
    <span data-ttu-id="37f32-159">Hiermee kunt u de gegevens downloaden naar het Power BI-bureaublad.</span><span class="sxs-lookup"><span data-stu-id="37f32-159">This will download the data into your Power BI Desktop.</span></span> <span data-ttu-id="37f32-160">Sla dit bestand op, zodat u kunt beginnen met het maken van de gewenste rapporten.</span><span class="sxs-lookup"><span data-stu-id="37f32-160">Save this file and then you can start creating the reports you need.</span></span>
    
    ![ODATA-waarden beschikbaar in de rapportage-API](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a><span data-ttu-id="37f32-162">Het Microsoft 365 Gebruiksanalyse sjabloon gebruiken</span><span class="sxs-lookup"><span data-stu-id="37f32-162">Use the Microsoft 365 usage analytics template</span></span>

<span data-ttu-id="37f32-p105">U kunt ook het Power BI-sjabloonbestand dat hoort bij de rapporten van Microsoft 365 Gebruiksanalyse gebruiken als startpunt voor het maken van verbinding met de gegevens. Het voordeel van het gebruik van het PBIT-bestand is dat de verbindingstekenreeks al is vastgelegd. U kunt ook profiteren van alle aangepaste metingen die zijn gedaan ter aanvulling op de gegevens in het basisschema, en die verder uitbouwen.</span><span class="sxs-lookup"><span data-stu-id="37f32-p105">You can also use the Power BI template file that corresponds to the Microsoft 365 usage analytics reports as a starting point to connect to the data. The advantage of using the pbit file is that it has the connection string already established. You can also take advantage of all the custom measures that are created, on top of the data that the base schema returns and build on it further.</span></span>
  
<span data-ttu-id="37f32-166">U kunt het Power BI-sjabloonbestand downloaden van het Microsoft Downloadcentrum vanuit het [Downloadcentrum](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span><span class="sxs-lookup"><span data-stu-id="37f32-166">You can download the Power BI template file from the Microsoft download center from the [Download center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span></span> <span data-ttu-id="37f32-167">Nadat u het Power BI-sjabloonbestand hebt gedownload, gaat u als volgt te werk om aan de slag te gaan:</span><span class="sxs-lookup"><span data-stu-id="37f32-167">After you have downloaded the Power BI template file follow these steps to get started:</span></span>
  
1. <span data-ttu-id="37f32-168">Open het PBIT-bestand.</span><span class="sxs-lookup"><span data-stu-id="37f32-168">Open the pbit file.</span></span>
    
2. <span data-ttu-id="37f32-169">Geef uw tenant-id op in het dialoogvenster.</span><span class="sxs-lookup"><span data-stu-id="37f32-169">Enter your tenant id value in the dialog.</span></span>
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. <span data-ttu-id="37f32-171">Voer uw beheerdersreferenties in om u aan te melden bij Microsoft 365 wanneer hierom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="37f32-171">Enter your admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
     <span data-ttu-id="37f32-172">meer informatie over wie er toegang kan krijgen tot de rapporten van de Microsoft 365 gebruiksanalyse.</span><span class="sxs-lookup"><span data-stu-id="37f32-172">for more information about who is allowed to access the Microsoft 365 usage analytics reports.</span></span> 
    
    <span data-ttu-id="37f32-173">Na autorisatie worden de gegevens in het Power BI-bestand vernieuwd.</span><span class="sxs-lookup"><span data-stu-id="37f32-173">Once authorized, the data will be refreshed in the Power BI file.</span></span>
    
    <span data-ttu-id="37f32-174">Het laden van de gegevens kan enige tijd duren. Wanneer het is voltooid, kunt u het bestand opslaan als een PBIX-bestand en de rapporten verder aanpassen of nog meer gegevensbronnen aan het rapport toevoegen.</span><span class="sxs-lookup"><span data-stu-id="37f32-174">Data load may take some time, once complete, you can save the file as a .pbix file and continue to customize the reports or bring an additional data source into this report.</span></span>
    
4. <span data-ttu-id="37f32-p107">Volg de documentatie [Aan de slag met Power BI](https://go.microsoft.com/fwlink/?linkid=849802) voor informatie over hoe u rapporten maakt, ze publiceert naar de Power BI-service en ze deelt binnen uw organisatie. Voor het volgen van dit pad voor aanpassen en delen zijn mogelijk extra Power BI-licenties vereist. Zie de [licentierichtlijnen](https://go.microsoft.com/fwlink/p/?linkid=849803) voor Power BI voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="37f32-p107">Follow [Getting started with Power BI](https://go.microsoft.com/fwlink/?linkid=849802) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization. Following this path for customization and sharing may require additional Power BI licenses. See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details.</span></span> 
    

