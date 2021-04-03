---
title: Rapporten in Microsoft 365 Gebruiksanalyse naar voorkeur aanpassen
f1.keywords:
- NOCSH
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
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: Informatie over het aanpassen van rapporten in de browser en Power BI Desktop.
ms.openlocfilehash: 0ef2364c82318dfea93e8df4e64d53a66caa8d74
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580772"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a><span data-ttu-id="976ee-103">Rapporten in Microsoft 365 Gebruiksanalyse naar voorkeur aanpassen</span><span class="sxs-lookup"><span data-stu-id="976ee-103">Customize the reports in Microsoft 365 usage analytics</span></span>

<span data-ttu-id="976ee-104">Gebruiksanalyse van Microsoft 365 biedt een dashboard in Power BI dat inzicht biedt in de manier waarop gebruikers Microsoft 365 gebruiken en gebruiken.</span><span class="sxs-lookup"><span data-stu-id="976ee-104">Microsoft 365 usage analytics provides a dashboard in Power BI that offers insights into how users adopt and use Microsoft 365.</span></span> <span data-ttu-id="976ee-105">Het dashboard is alleen een beginpunt voor interactie met de gebruiksgegevens.</span><span class="sxs-lookup"><span data-stu-id="976ee-105">The dashboard is just a starting point to interact with the usage data.</span></span> <span data-ttu-id="976ee-106">De rapporten kunnen worden aangepast voor meer persoonlijke inzichten.</span><span class="sxs-lookup"><span data-stu-id="976ee-106">The reports can be customized for more personalized insights.</span></span>
  
<span data-ttu-id="976ee-107">U kunt ook Power BI Desktop gebruiken om uw rapporten verder aan te passen, door verbinding te maken met andere gegevensbronnen voor nog uitgebreidere inzichten in uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="976ee-107">You can also use the Power BI desktop to further customize your reports by connecting them to other data sources to gain richer insights about your business.</span></span>
  
## <a name="customizing-reports-in-the-browser"></a><span data-ttu-id="976ee-108">Rapporten aanpassen in de browser</span><span class="sxs-lookup"><span data-stu-id="976ee-108">Customizing reports in the browser</span></span>

<span data-ttu-id="976ee-109">In de volgende twee voorbeelden ziet u hoe u een bestaand visueel element kunt aanpassen en een nieuw visueel element kunt maken.</span><span class="sxs-lookup"><span data-stu-id="976ee-109">The following two examples show how to modify an existing visual and how to create a new visual.</span></span>
  
### <a name="modify-an-existing-visual"></a><span data-ttu-id="976ee-110">Een bestaand visueel element wijzigen</span><span class="sxs-lookup"><span data-stu-id="976ee-110">Modify an existing visual</span></span>

<span data-ttu-id="976ee-111">In dit voorbeeld ziet u hoe u het tabblad **Activering** wijzigt in **het rapport Activering/licentie.**</span><span class="sxs-lookup"><span data-stu-id="976ee-111">This example shows how to modify the **Activation** tab within the **Activation/Licensing** report.</span></span> 
  
1. <span data-ttu-id="976ee-112">Selecteer in **het rapport Activering/licentie** het **tabblad** Activering.</span><span class="sxs-lookup"><span data-stu-id="976ee-112">Within the **Activation/Licensing** report, select the **Activation** tab.</span></span>
    
2. <span data-ttu-id="976ee-113">Voer de bewerkingsmodus in door **de** knop Bewerken bovenaan te kiezen via de knop Meer pagina in ![ Power ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) BI.</span><span class="sxs-lookup"><span data-stu-id="976ee-113">Enter the edit mode by choosing the **Edit** button on the top through the ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) button.</span></span> 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. <span data-ttu-id="976ee-115">Kies rechtsboven de optie **Deze pagina dupliceren.**</span><span class="sxs-lookup"><span data-stu-id="976ee-115">On the top right, choose **Duplicate this page**.</span></span>
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. <span data-ttu-id="976ee-117">Kies rechtsonder een van de staafdiagrammen met het aantal gebruikers dat activeert op basis van het besturingssysteem, zoals Android, iOS, Mac, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="976ee-117">In the bottom right, choose any of the bar-charts showing the count of users activating based on the OS such as Android, iOS, Mac, etc.</span></span>
    
5. <span data-ttu-id="976ee-118">Selecteer in **het gebied Visualisaties** aan de rechterkant de **X** er naast om Het aantal **Mac's** uit het visuele gedeelte te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="976ee-118">In the **Visualizations** area to the right, in order to remove **Mac Count** from the visual, select the **X** next to it.</span></span>

    ![Aantal Mac's verwijderen](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a><span data-ttu-id="976ee-120">Een nieuw visueel element maken</span><span class="sxs-lookup"><span data-stu-id="976ee-120">Create a new visual</span></span>

<span data-ttu-id="976ee-121">In het volgende voorbeeld ziet u hoe u een nieuw visueel element maakt voor het bijhouden van nieuwe Yammer-gebruikers op maandbasis.</span><span class="sxs-lookup"><span data-stu-id="976ee-121">The following example shows how to create a new visual to track new Yammer users on monthly basis.</span></span>
  
1. <span data-ttu-id="976ee-122">Ga met de linkernavigatie naar het **rapport Productgebruik** en selecteer het **tabblad Yammer.**</span><span class="sxs-lookup"><span data-stu-id="976ee-122">Go to the **Product Usage** report using the left nav and select the **Yammer** tab.</span></span>
    
2. <span data-ttu-id="976ee-123">Schakel over naar de bewerkingsmodus door ![ De knop Meer pagina in Power BI en Bewerken te ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) **kiezen.**</span><span class="sxs-lookup"><span data-stu-id="976ee-123">Switch to edit mode by choosing ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) and **Edit**.</span></span> 
    
3. <span data-ttu-id="976ee-124">Selecteer onder aan de pagina de optie</span><span class="sxs-lookup"><span data-stu-id="976ee-124">At the bottom of the page, select the</span></span> ![De knop Pagina toevoegen in Power BI](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) <span data-ttu-id="976ee-126">om een nieuwe pagina te maken.</span><span class="sxs-lookup"><span data-stu-id="976ee-126">to create a new page.</span></span>
  
4. <span data-ttu-id="976ee-127">Kies in **het gebied Visualisaties** aan de rechterkant de optie **Gestapeld staafdiagram** (bovenste rij, eerst van links).</span><span class="sxs-lookup"><span data-stu-id="976ee-127">In the **Visualizations** area to the right, choose the **Stacked bar chart** (top row, first from left).</span></span>

    ![Staafdiagram selecteren](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. <span data-ttu-id="976ee-129">Selecteer de rechteronderzijde van die visualisatie en sleep om deze groter te maken.</span><span class="sxs-lookup"><span data-stu-id="976ee-129">Select the bottom right of that visualization and drag to make it larger.</span></span>

6. <span data-ttu-id="976ee-130">Vouw in **het** gebied Velden aan de rechterkant de tabel **Agenda** uit.</span><span class="sxs-lookup"><span data-stu-id="976ee-130">In the **Fields** area to the right, expand the **Calendar** table.</span></span>

7. <span data-ttu-id="976ee-131">Sleep **MonthName** naar het gedeelte met velden, direct onder de koptekst **As** in het gedeelte **Visualisaties**.</span><span class="sxs-lookup"><span data-stu-id="976ee-131">Drag **MonthName** to the fields area, directly below the **Axis** heading in the **Visualizations** area.</span></span>
 
    ![Maandnaam slepen](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. <span data-ttu-id="976ee-133">Vouw in het gedeelte **Velden** aan de rechterkant de tabel **TenantProductUsage** uit.</span><span class="sxs-lookup"><span data-stu-id="976ee-133">In the **Fields** area to the right, expand the **TenantProductUsage** table.</span></span>

9. <span data-ttu-id="976ee-134">Sleep **FirstTimeUsers** naar het gedeelte met velden, direct onder de koptekst **Waarde**.</span><span class="sxs-lookup"><span data-stu-id="976ee-134">Drag **FirstTimeUsers** to the fields area, directly below the **Value** heading.</span></span>

10. <span data-ttu-id="976ee-135">Sleep **Product** naar het gedeelte **Filters**, direct onder de koptekst **Filters op niveau van visuele elementen**.</span><span class="sxs-lookup"><span data-stu-id="976ee-135">Drag **Product** to the **Filters** area, directly below the **Visual level filters** heading.</span></span>

11. <span data-ttu-id="976ee-136">Selecteer in het gedeelte **Filtertype** dat wordt weergegeven het selectievakje **Yammer**.</span><span class="sxs-lookup"><span data-stu-id="976ee-136">In the **Filter Type** area that appears, select the **Yammer** check box.</span></span>

    ![Selectievakje Yammer selecteren](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. <span data-ttu-id="976ee-138">Kies net onder de lijst met visualisaties het **pictogram** Opmaakpictogram Opmaak in Power ![ BI Visualizaions. ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png)</span><span class="sxs-lookup"><span data-stu-id="976ee-138">Just below the list of visualizations, choose the **Format** icon ![Format icon in Power BI Visualizaions](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).</span></span>

13. <span data-ttu-id="976ee-139">Vouw Titel uit en wijzig de waarde **Titel** in **Nieuwe gebruikers van Yammer per maand**.</span><span class="sxs-lookup"><span data-stu-id="976ee-139">Expand Title and change the **Title Text** value to **First-Time Yammer Users by Month**.</span></span>
    
14. <span data-ttu-id="976ee-140">Wijzig de **Tekengrootte** in **12**.</span><span class="sxs-lookup"><span data-stu-id="976ee-140">Change the **Text Size** value to **12**.</span></span>
    
15. <span data-ttu-id="976ee-141">Wijzig de titel van de nieuwe pagina door de naam van de pagina rechtsonder te bewerken.</span><span class="sxs-lookup"><span data-stu-id="976ee-141">Change the title of the new page by editing the name of the page on bottom right.</span></span>

16.  <span data-ttu-id="976ee-142">Sla het rapport op door te klikken op de **leesweergave** bovenaan en vervolgens **op Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="976ee-142">Save out the report by Clicking on **Reading View** on top and then **Save**.</span></span>
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a><span data-ttu-id="976ee-143">De rapporten in Power BI Desktop aanpassen</span><span class="sxs-lookup"><span data-stu-id="976ee-143">Customizing the reports in Power BI Desktop</span></span>

<span data-ttu-id="976ee-p102">Voor de meeste klanten is het aanpassen van de rapporten en visuele elementen van grafieken op de Power BI-website voldoende. Sommige klanten willen deze gegevens echter misschien koppelen aan andere gegevensbronnen voor uitgebreidere inzichten in de context van hun eigen bedrijf. In dat geval kunnen ze rapporten aanpassen en aanvullende rapporten maken met Power BI Desktop. U kunt [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) gratis downloaden.</span><span class="sxs-lookup"><span data-stu-id="976ee-p102">For most customers modifying the reports and chart visuals in Power BI web will be sufficient. For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop. You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free.</span></span> 
  
### <a name="use-the-reporting-apis"></a><span data-ttu-id="976ee-147">De rapportage-API's gebruiken</span><span class="sxs-lookup"><span data-stu-id="976ee-147">Use the reporting APIs</span></span>

<span data-ttu-id="976ee-148">U kunt beginnen door rechtstreeks verbinding te maken met de ODATA-rapportage-API's van Microsoft 365 die van invloed zijn op deze rapporten.</span><span class="sxs-lookup"><span data-stu-id="976ee-148">You can start by connecting directly to the ODATA reporting APIs from Microsoft 365 that power these reports.</span></span>
  
1. <span data-ttu-id="976ee-149">Ga naar **Gegevens ophalen** \> **Overige** \> **ODATA-feed** \> **Verbinding maken**.</span><span class="sxs-lookup"><span data-stu-id="976ee-149">Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect**.</span></span>
    
2. <span data-ttu-id="976ee-150">Voer in het URL-venster 'https:// <i></i> \<tenantid\> reports.office.com/pbi/v1.0/' in</span><span class="sxs-lookup"><span data-stu-id="976ee-150">In the URL window enter "https://<i></i>reports.office.com/pbi/v1.0/\<tenantid\>"</span></span>
    
    <span data-ttu-id="976ee-151">**OPMERKING:** De rapportage-API's zijn in preview en kunnen worden gewijzigd totdat ze in productie gaan.</span><span class="sxs-lookup"><span data-stu-id="976ee-151">**NOTE:** The reporting APIs are in preview and are subject to change until they go into production.</span></span> 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. <span data-ttu-id="976ee-153">Voer uw Microsoft 365-beheerdersreferenties (organisatie of school) in om te verifiëren bij Microsoft 365 wanneer u daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="976ee-153">Enter your Microsoft 365 (organization or school) admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
    <span data-ttu-id="976ee-154">Zie de [veelgestelde](usage-analytics.md#faq) vragen voor meer informatie over wie toegang heeft tot de microsoft 365-app-app-rapporten met acceptatiesjabloon.</span><span class="sxs-lookup"><span data-stu-id="976ee-154">See the [FAQ](usage-analytics.md#faq) for more information about who is allowed to access the Microsoft 365 Adoption template app reports.</span></span> 
    
4. <span data-ttu-id="976ee-155">Zodra de verbinding is geautoriseerd, wordt het Navigator-venster weergegeven met de gegevenssets waarmee u verbinding kunt maken.</span><span class="sxs-lookup"><span data-stu-id="976ee-155">Once the connection is authorized, you will see the Navigator window that shows the datasets available to connect to.</span></span>
    
    <span data-ttu-id="976ee-156">Selecteer alles en kies **Laden.**</span><span class="sxs-lookup"><span data-stu-id="976ee-156">Select all and choose **Load**.</span></span>
    
    <span data-ttu-id="976ee-157">Hiermee worden de gegevens gedownload naar uw Power BI-bureaublad.</span><span class="sxs-lookup"><span data-stu-id="976ee-157">This will download the data into your Power BI Desktop.</span></span> <span data-ttu-id="976ee-158">Sla dit bestand op en vervolgens kunt u beginnen met het maken van de rapporten die u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="976ee-158">Save this file and then you can start creating the reports you need.</span></span>
    
    ![ODATA-waarden die beschikbaar zijn in de rapportage-API](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a><span data-ttu-id="976ee-160">Het Microsoft 365 Gebruiksanalyse sjabloon gebruiken</span><span class="sxs-lookup"><span data-stu-id="976ee-160">Use the Microsoft 365 usage analytics template</span></span>

<span data-ttu-id="976ee-p104">U kunt ook het Power BI-sjabloonbestand dat hoort bij de rapporten van Microsoft 365 Gebruiksanalyse gebruiken als startpunt voor het maken van verbinding met de gegevens. Het voordeel van het gebruik van het PBIT-bestand is dat de verbindingstekenreeks al is vastgelegd. U kunt ook profiteren van alle aangepaste metingen die zijn gedaan ter aanvulling op de gegevens in het basisschema, en die verder uitbouwen.</span><span class="sxs-lookup"><span data-stu-id="976ee-p104">You can also use the Power BI template file that corresponds to the Microsoft 365 usage analytics reports as a starting point to connect to the data. The advantage of using the pbit file is that it has the connection string already established. You can also take advantage of all the custom measures that are created, on top of the data that the base schema returns and build on it further.</span></span>
  
<span data-ttu-id="976ee-164">U kunt het Power BI-sjabloonbestand downloaden vanuit het [Microsoft Downloadcentrum.](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)</span><span class="sxs-lookup"><span data-stu-id="976ee-164">You can download the Power BI template file from the [Microsoft Download Center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span></span> <span data-ttu-id="976ee-165">Nadat u het Power BI-sjabloonbestand hebt gedownload, volgt u de volgende stappen om aan de slag te gaan:</span><span class="sxs-lookup"><span data-stu-id="976ee-165">After you download the Power BI template file, follow these steps to get started:</span></span>
  
1. <span data-ttu-id="976ee-166">Open het PBIT-bestand.</span><span class="sxs-lookup"><span data-stu-id="976ee-166">Open the pbit file.</span></span>
    
2. <span data-ttu-id="976ee-167">Geef uw tenant-id op in het dialoogvenster.</span><span class="sxs-lookup"><span data-stu-id="976ee-167">Enter your tenant id value in the dialog.</span></span>
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. <span data-ttu-id="976ee-169">Voer uw beheerdersreferenties in om te verifiëren bij Microsoft 365 wanneer u daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="976ee-169">Enter your admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
     <span data-ttu-id="976ee-170">voor meer informatie over wie toegang heeft tot de analyserapporten voor Microsoft 365-gebruik.</span><span class="sxs-lookup"><span data-stu-id="976ee-170">for more information about who is allowed to access the Microsoft 365 usage analytics reports.</span></span> 
    
    <span data-ttu-id="976ee-171">Na autorisatie worden de gegevens in het Power BI-bestand vernieuwd.</span><span class="sxs-lookup"><span data-stu-id="976ee-171">Once authorized, the data will be refreshed in the Power BI file.</span></span>
    
    <span data-ttu-id="976ee-172">Het laden van de gegevens kan enige tijd duren. Wanneer het is voltooid, kunt u het bestand opslaan als een PBIX-bestand en de rapporten verder aanpassen of nog meer gegevensbronnen aan het rapport toevoegen.</span><span class="sxs-lookup"><span data-stu-id="976ee-172">Data load may take some time, once complete, you can save the file as a .pbix file and continue to customize the reports or bring an additional data source into this report.</span></span>
    
4. <span data-ttu-id="976ee-p106">Volg de documentatie [Aan de slag met Power BI](/power-bi/fundamentals/desktop-getting-started) voor informatie over hoe u rapporten maakt, ze publiceert naar de Power BI-service en ze deelt binnen uw organisatie. Voor het volgen van dit pad voor aanpassen en delen zijn mogelijk extra Power BI-licenties vereist. Zie de [licentierichtlijnen](https://go.microsoft.com/fwlink/p/?linkid=849803) voor Power BI voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="976ee-p106">Follow [Getting started with Power BI](/power-bi/fundamentals/desktop-getting-started) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization. Following this path for customization and sharing may require additional Power BI licenses. See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details.</span></span> 
