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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: Meer informatie over het aanpassen van rapporten in de browser en Power BI Desktop.
ms.openlocfilehash: 4f0c85802ecb5db9c57add2fa6dd561827e8fa22
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140707"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a><span data-ttu-id="7d0bd-103">Rapporten in Microsoft 365 Gebruiksanalyse naar voorkeur aanpassen</span><span class="sxs-lookup"><span data-stu-id="7d0bd-103">Customize the reports in Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="7d0bd-104">Het beheercentrum verandert.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-104">The admin center is changing.</span></span> <span data-ttu-id="7d0bd-105">Als uw ervaring niet overeenkomt met de hier gepresenteerde details, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="7d0bd-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="7d0bd-106">Microsoft 365-gebruiksanalyse biedt een dashboard in Power BI dat inzicht biedt in de manier waarop gebruikers Microsoft 365 gebruiken en gebruiken.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-106">Microsoft 365 usage analytics provides a dashboard in Power BI that offers insights into how users adopt and use Microsoft 365.</span></span> <span data-ttu-id="7d0bd-107">Het dashboard is alleen een beginpunt voor interactie met de gebruiksgegevens.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-107">The dashboard is just a starting point to interact with the usage data.</span></span> <span data-ttu-id="7d0bd-108">De rapporten kunnen worden aangepast voor meer persoonlijke inzichten.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-108">The reports can be customized for more personalized insights.</span></span>
  
<span data-ttu-id="7d0bd-109">U kunt ook Power BI Desktop gebruiken om uw rapporten verder aan te passen, door verbinding te maken met andere gegevensbronnen voor nog uitgebreidere inzichten in uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-109">You can also use the Power BI desktop to further customize your reports by connecting them to other data sources to gain richer insights about your business.</span></span>
  
## <a name="customizing-reports-in-the-browser"></a><span data-ttu-id="7d0bd-110">Rapporten aanpassen in de browser</span><span class="sxs-lookup"><span data-stu-id="7d0bd-110">Customizing reports in the browser</span></span>

<span data-ttu-id="7d0bd-111">In de volgende twee voorbeelden ziet u hoe u een bestaand visueel element kunt aanpassen en een nieuw visueel element kunt maken.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-111">The following two examples show how to modify an existing visual and how to create a new visual.</span></span>
  
### <a name="modify-an-existing-visual"></a><span data-ttu-id="7d0bd-112">Een bestaand visueel element wijzigen</span><span class="sxs-lookup"><span data-stu-id="7d0bd-112">Modify an existing visual</span></span>

<span data-ttu-id="7d0bd-113">In dit voorbeeld ziet u hoe u het tabblad **Activering wijzigt** in het rapport **Activering/licentieverlening.**</span><span class="sxs-lookup"><span data-stu-id="7d0bd-113">This example shows how to modify the **Activation** tab within the **Activation/Licensing** report.</span></span> 
  
1. <span data-ttu-id="7d0bd-114">Klik in het rapport **Activering/licentieverlening** op het tabblad **Activering.**</span><span class="sxs-lookup"><span data-stu-id="7d0bd-114">Within the **Activation/Licensing** report, click on the **Activation** tab.</span></span>
    
2. <span data-ttu-id="7d0bd-115">Voer de bewerkingsmodus in **Edit** door bovenaan op de ![knop Bewerken te klikken](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) via de knop Meer pagina in de knop Power BI.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-115">Enter the edit mode by clicking the **Edit** button on the top through the ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) button.</span></span> 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. <span data-ttu-id="7d0bd-117">Klik rechtsboven op **Deze pagina dupliceren**.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-117">On the top right, click **Duplicate this page**.</span></span>
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. <span data-ttu-id="7d0bd-119">Klik rechtsonder op een van de staafdiagrammen met het aantal gebruikers dat activeert op basis van het besturingssysteem, zoals Android, iOS, Mac, enz.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-119">In the bottom right, click on any of the bar charts showing the count of users activating based on the OS such as Android, iOS, Mac, etc.</span></span>
    
5. <span data-ttu-id="7d0bd-120">Klik in het gebied **Visualisaties** aan de rechterkant om **Mac Count** uit de visual te verwijderen op de **X** ernaast.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-120">In the **Visualizations** area to the right, in order to remove **Mac Count** from the visual, click on the **X** next to it.</span></span>

    ![Mac-aantal verwijderen](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a><span data-ttu-id="7d0bd-122">Een nieuw visueel element maken</span><span class="sxs-lookup"><span data-stu-id="7d0bd-122">Create a new visual</span></span>

<span data-ttu-id="7d0bd-123">In het volgende voorbeeld ziet u hoe u een nieuw visueel element maakt voor het bijhouden van nieuwe Yammer-gebruikers op maandbasis.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-123">The following example shows how to create a new visual to track new Yammer users on monthly basis.</span></span>
  
1. <span data-ttu-id="7d0bd-124">Ga naar het rapport **Productgebruik** met de linkernavigatie en klik op het tabblad **Yammer.**</span><span class="sxs-lookup"><span data-stu-id="7d0bd-124">Go to the **Product Usage** report using the left nav and click on **Yammer** tab.</span></span>
    
2. <span data-ttu-id="7d0bd-125">Schakel over naar de bewerkingsmodus door te klikken op ![De knop Meer pagina in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) en **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-125">Switch to edit mode by clicking on ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) and **Edit**.</span></span> 
    
3. <span data-ttu-id="7d0bd-126">Klik onderaan de pagina op</span><span class="sxs-lookup"><span data-stu-id="7d0bd-126">At the bottom of the page, click on</span></span> ![De knop Pagina toevoegen in Power BI](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) <span data-ttu-id="7d0bd-128">om een nieuwe pagina te maken.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-128">to create a new page.</span></span>
  
4. <span data-ttu-id="7d0bd-129">Klik in het gebied **Visualisaties** rechts op het **gestapelde staafdiagram** (bovenste rij, eerste van links).</span><span class="sxs-lookup"><span data-stu-id="7d0bd-129">In the **Visualizations** area to the right, click the **Stacked bar chart** (top row, first from left).</span></span>

    ![Staafdiagram selecteren](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. <span data-ttu-id="7d0bd-131">Klik op de rechtersbenedenhoek van de visualisatie en sleep om die groter te maken.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-131">Click the bottom right of that visualization and drag to make it larger.</span></span>

6. <span data-ttu-id="7d0bd-132">Vouw in het gebied **Velden** aan de rechterkant de tabel **Agenda** uit.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-132">In the **Fields** area to the right, expand the **Calendar** table.</span></span>

7. <span data-ttu-id="7d0bd-133">Sleep **MonthName** naar het gedeelte met velden, direct onder de koptekst **As** in het gedeelte **Visualisaties**.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-133">Drag **MonthName** to the fields area, directly below the **Axis** heading in the **Visualizations** area.</span></span>
 
    ![Maandnaam slepen](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. <span data-ttu-id="7d0bd-135">Vouw in het gedeelte **Velden** aan de rechterkant de tabel **TenantProductUsage** uit.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-135">In the **Fields** area to the right, expand the **TenantProductUsage** table.</span></span>

9. <span data-ttu-id="7d0bd-136">Sleep **FirstTimeUsers** naar het gedeelte met velden, direct onder de koptekst **Waarde**.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-136">Drag **FirstTimeUsers** to the fields area, directly below the **Value** heading.</span></span>

10. <span data-ttu-id="7d0bd-137">Sleep **Product** naar het gedeelte **Filters**, direct onder de koptekst **Filters op niveau van visuele elementen**.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-137">Drag **Product** to the **Filters** area, directly below the **Visual level filters** heading.</span></span>

11. <span data-ttu-id="7d0bd-138">Selecteer in het gedeelte **Filtertype** dat wordt weergegeven het selectievakje **Yammer**.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-138">In the **Filter Type** area that appears, select the **Yammer** check box.</span></span>

    ![Het selectievakje Yammer inschakelen](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. <span data-ttu-id="7d0bd-140">Klik net onder de lijst met ![visualisaties op het pictogram](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) **Opmaak** in Power BI Visualizaions .</span><span class="sxs-lookup"><span data-stu-id="7d0bd-140">Just below the list of visualizations, click the **Format** icon ![Format icon in Power BI Visualizaions](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).</span></span>

13. <span data-ttu-id="7d0bd-141">Vouw Titel uit en wijzig de waarde **Titel** in **Nieuwe gebruikers van Yammer per maand**.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-141">Expand Title and change the **Title Text** value to **First-Time Yammer Users by Month**.</span></span>
    
14. <span data-ttu-id="7d0bd-142">Wijzig de **Tekengrootte** in **12**.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-142">Change the **Text Size** value to **12**.</span></span>
    
15. <span data-ttu-id="7d0bd-143">Wijzig de titel van de nieuwe pagina door de naam van de pagina rechtsonder te bewerken.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-143">Change the title of the new page by editing the name of the page on bottom right.</span></span>

16.  <span data-ttu-id="7d0bd-144">Sla het rapport op door bovenaan op **leesweergave** te klikken en vervolgens **op te slaan**.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-144">Save out the report by Clicking on **Reading View** on top and then **Save**.</span></span>
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a><span data-ttu-id="7d0bd-145">De rapporten in Power BI Desktop aanpassen</span><span class="sxs-lookup"><span data-stu-id="7d0bd-145">Customizing the reports in Power BI Desktop</span></span>

<span data-ttu-id="7d0bd-p103">Voor de meeste klanten is het aanpassen van de rapporten en visuele elementen van grafieken op de Power BI-website voldoende. Sommige klanten willen deze gegevens echter misschien koppelen aan andere gegevensbronnen voor uitgebreidere inzichten in de context van hun eigen bedrijf. In dat geval kunnen ze rapporten aanpassen en aanvullende rapporten maken met Power BI Desktop. U kunt [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) gratis downloaden.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-p103">For most customers modifying the reports and chart visuals in Power BI web will be sufficient. For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop. You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free.</span></span> 
  
### <a name="use-the-reporting-apis"></a><span data-ttu-id="7d0bd-149">De rapportage-API's gebruiken</span><span class="sxs-lookup"><span data-stu-id="7d0bd-149">Use the reporting APIs</span></span>

<span data-ttu-id="7d0bd-150">U beginnen door rechtstreeks verbinding te maken met de ODATA-rapportage-API's van Microsoft 365 die deze rapporten van stroom voorstaan.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-150">You can start by connecting directly to the ODATA reporting APIs from Microsoft 365 that power these reports.</span></span>
  
1. <span data-ttu-id="7d0bd-151">Ga naar **Gegevens ophalen** \> **Overige** \> **ODATA-feed** \> **Verbinding maken**.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-151">Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect**.</span></span>
    
2. <span data-ttu-id="7d0bd-152">Voer in het URL-venster 'https://<i></i>reports.office.com/pbi/v1.0/\<tenantid\>in'</span><span class="sxs-lookup"><span data-stu-id="7d0bd-152">In the URL window enter "https://<i></i>reports.office.com/pbi/v1.0/\<tenantid\>"</span></span>
    
    <span data-ttu-id="7d0bd-153">**LET OP:** De rapportage-API's zijn in preview en kunnen worden gewijzigd totdat ze in productie gaan.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-153">**NOTE:** The reporting APIs are in preview and are subject to change until they go into production.</span></span> 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. <span data-ttu-id="7d0bd-155">Voer uw Microsoft 365-beheerdersreferenties (organisatie of school) in om deze te verifiëren bij Microsoft 365 wanneer daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-155">Enter your Microsoft 365 (organization or school) admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
    <span data-ttu-id="7d0bd-156">Zie de [veelgestelde vragen](usage-analytics.md#faq) voor meer informatie over wie toegang heeft tot de rapporten van de Microsoft 365-sjabloonvoor adoptie.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-156">See the [FAQ](usage-analytics.md#faq) for more information about who is allowed to access the Microsoft 365 Adoption template app reports.</span></span> 
    
4. <span data-ttu-id="7d0bd-157">Zodra de verbinding is geautoriseerd, wordt het Navigator-venster weergegeven met de gegevenssets waarmee u verbinding kunt maken.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-157">Once the connection is authorized, you will see the Navigator window that shows the datasets available to connect to.</span></span>
    
    <span data-ttu-id="7d0bd-158">Selecteer alles en klik op **Laden**.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-158">Select all and click on **Load**.</span></span>
    
    <span data-ttu-id="7d0bd-p104">Hiermee downloadt u de gegevens naar Power BI Desktop. Sla het bestand op. U kunt beginnen met het maken van de gewenste rapporten.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-p104">This will download the data into your Power BI Desktop. Save this file and then you can start creating the reports you need.</span></span>
    
    ![ODATA-waarden beschikbaar in de rapportage-API](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a><span data-ttu-id="7d0bd-162">Het Microsoft 365 Gebruiksanalyse sjabloon gebruiken</span><span class="sxs-lookup"><span data-stu-id="7d0bd-162">Use the Microsoft 365 usage analytics template</span></span>

<span data-ttu-id="7d0bd-p105">U kunt ook het Power BI-sjabloonbestand dat hoort bij de rapporten van Microsoft 365 Gebruiksanalyse gebruiken als startpunt voor het maken van verbinding met de gegevens. Het voordeel van het gebruik van het PBIT-bestand is dat de verbindingstekenreeks al is vastgelegd. U kunt ook profiteren van alle aangepaste metingen die zijn gedaan ter aanvulling op de gegevens in het basisschema, en die verder uitbouwen.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-p105">You can also use the Power BI template file that corresponds to the Microsoft 365 usage analytics reports as a starting point to connect to the data. The advantage of using the pbit file is that it has the connection string already established. You can also take advantage of all the custom measures that are created, on top of the data that the base schema returns and build on it further.</span></span>
  
<span data-ttu-id="7d0bd-166">U het Power BI-sjabloonbestand downloaden vanuit het Microsoft-downloadcentrum vanuit het [downloadcentrum.](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)</span><span class="sxs-lookup"><span data-stu-id="7d0bd-166">You can download the Power BI template file from the Microsoft download center from the [Download center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span></span> <span data-ttu-id="7d0bd-167">Nadat u het Power BI-sjabloonbestand hebt gedownload, gaat u als volgt te werk om aan de slag te gaan:</span><span class="sxs-lookup"><span data-stu-id="7d0bd-167">After you have downloaded the Power BI template file follow these steps to get started:</span></span>
  
1. <span data-ttu-id="7d0bd-168">Open het PBIT-bestand.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-168">Open the pbit file.</span></span>
    
2. <span data-ttu-id="7d0bd-169">Geef uw tenant-id op in het dialoogvenster.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-169">Enter your tenant id value in the dialog.</span></span>
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. <span data-ttu-id="7d0bd-171">Voer uw beheerdersreferenties in om te verifiëren bij Microsoft 365 wanneer daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-171">Enter your admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
     <span data-ttu-id="7d0bd-172">voor meer informatie over wie toegang heeft tot de Microsoft 365-rapporten over gebruiksanalyses.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-172">for more information about who is allowed to access the Microsoft 365 usage analytics reports.</span></span> 
    
    <span data-ttu-id="7d0bd-173">Na autorisatie worden de gegevens in het Power BI-bestand vernieuwd.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-173">Once authorized, the data will be refreshed in the Power BI file.</span></span>
    
    <span data-ttu-id="7d0bd-174">Het laden van de gegevens kan enige tijd duren. Wanneer het is voltooid, kunt u het bestand opslaan als een PBIX-bestand en de rapporten verder aanpassen of nog meer gegevensbronnen aan het rapport toevoegen.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-174">Data load may take some time, once complete, you can save the file as a .pbix file and continue to customize the reports or bring an additional data source into this report.</span></span>
    
4. <span data-ttu-id="7d0bd-p107">Volg de documentatie [Aan de slag met Power BI](https://go.microsoft.com/fwlink/?linkid=849802) voor informatie over hoe u rapporten maakt, ze publiceert naar de Power BI-service en ze deelt binnen uw organisatie. Voor het volgen van dit pad voor aanpassen en delen zijn mogelijk extra Power BI-licenties vereist. Zie de [licentierichtlijnen](https://go.microsoft.com/fwlink/p/?linkid=849803) voor Power BI voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7d0bd-p107">Follow [Getting started with Power BI](https://go.microsoft.com/fwlink/?linkid=849802) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization. Following this path for customization and sharing may require additional Power BI licenses. See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details.</span></span> 
    

