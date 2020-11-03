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
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a>Rapporten in Microsoft 365 Gebruiksanalyse naar voorkeur aanpassen

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Microsoft 365 gebruiksanalyse biedt een dashboard in Power BI waarmee u inzicht krijgt in de manier waarop gebruikers Microsoft 365 aannemen en gebruiken. Het dashboard is alleen een beginpunt voor interactie met de gebruiksgegevens. De rapporten kunnen worden aangepast voor meer persoonlijke inzichten.
  
U kunt ook Power BI Desktop gebruiken om uw rapporten verder aan te passen, door verbinding te maken met andere gegevensbronnen voor nog uitgebreidere inzichten in uw bedrijf.
  
## <a name="customizing-reports-in-the-browser"></a>Rapporten aanpassen in de browser

In de volgende twee voorbeelden ziet u hoe u een bestaand visueel element kunt aanpassen en een nieuw visueel element kunt maken.
  
### <a name="modify-an-existing-visual"></a>Een bestaand visueel element wijzigen

In dit voorbeeld ziet u hoe u het tabblad **Activering** kunt wijzigen in het rapport **Activering/licentieverlening** . 
  
1. Selecteer in het rapport **Activering/licentieverlening** het tabblad **Activering** .
    
2. Voer de bewerkingsmodus in door op de knop **bewerken** te klikken op de bovenkant via de knop ![ meer pagina op de Power bi- ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) knop. 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. Kies in de rechterbovenhoek de optie **Deze pagina dupliceren** .
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. Kies in de rechterbenedenhoek een van de staaf-grafieken met het aantal gebruikers dat is geactiveerd op basis van het besturingssysteem, zoals Android, iOS, Mac, etc.
    
5. Selecteer in het gebied **Visualisaties** aan de rechterkant de **X** ernaast om het **aantal** te verwijderen uit het visuele element.

    ![Mac-aantal verwijderen](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a>Een nieuw visueel element maken

In het volgende voorbeeld ziet u hoe u een nieuw visueel element maakt voor het bijhouden van nieuwe Yammer-gebruikers op maandbasis.
  
1. Ga naar het rapport **product gebruik** met de linkernavigatiebalk en selecteer het tabblad **Yammer** .
    
2. Ga naar de bewerkingsmodus door te klikken op ![ de knop meer pagina in Power bi ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) en **bewerken** . 
    
3. Selecteer onder aan de pagina de ![De knop pagina toevoegen in Power BI](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) om een nieuwe pagina te maken.
  
4. Kies in het gebied **Visualisaties** aan de rechterkant het **gestapeld staafdiagram** (bovenste rij, eerst van links).

    ![Staafdiagram selecteren](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. Selecteer de rechterbenedenhoek van de visualisatie en sleep om deze groter te maken.

6. Vouw in het gedeelte **velden** aan de rechterkant de tabel **agenda** uit.

7. Sleep **MonthName** naar het gedeelte met velden, direct onder de koptekst **As** in het gedeelte **Visualisaties** .
 
    ![Naam van maand slepen](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. Vouw in het gedeelte **Velden** aan de rechterkant de tabel **TenantProductUsage** uit.

9. Sleep **FirstTimeUsers** naar het gedeelte met velden, direct onder de koptekst **Waarde** .

10. Sleep **Product** naar het gedeelte **Filters** , direct onder de koptekst **Filters op niveau van visuele elementen** .

11. Selecteer in het gedeelte **Filtertype** dat wordt weergegeven het selectievakje **Yammer** .

    ![Selectievakje Yammer selecteren](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. Kies net onder de lijst met visualisaties het pictogram opmaak **pictogram opmaak** ![ in Power bi--visualisaties ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) .

13. Vouw Titel uit en wijzig de waarde **Titel** in **Nieuwe gebruikers van Yammer per maand** .
    
14. Wijzig de **Tekengrootte** in **12** .
    
15. Wijzig de titel van de nieuwe pagina door de naam van de pagina aan de rechterkant te bewerken.

16.  Sla het rapport op door op de **leesweergave** op de bovenkant en op **Opslaan** te klikken.
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a>De rapporten in Power BI Desktop aanpassen

Voor de meeste klanten is het aanpassen van de rapporten en visuele elementen van grafieken op de Power BI-website voldoende. Sommige klanten willen deze gegevens echter misschien koppelen aan andere gegevensbronnen voor uitgebreidere inzichten in de context van hun eigen bedrijf. In dat geval kunnen ze rapporten aanpassen en aanvullende rapporten maken met Power BI Desktop. U kunt [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) gratis downloaden. 
  
### <a name="use-the-reporting-apis"></a>De rapportage-API's gebruiken

U kunt beginnen met het maken van een directe verbinding met de ODATA-rapportage-Api's van Microsoft 365, waardoor deze rapporten worden opgenomen.
  
1. Ga naar **Gegevens ophalen** \> **Overige** \> **ODATA-feed** \> **Verbinding maken** .
    
2. Voer in het venster URL het https:// <i></i> Reports.Office.com/pbi/v1.0/ \<tenantid\> in
    
    **Opmerking:** De rapportage-Api's zijn een preview-versie en kunnen worden gewijzigd totdat ze in de productie gaan. 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. Voer uw beheerdersreferenties voor Microsoft 365 (organisatie of school) in om u aan te melden bij Microsoft 365 wanneer hierom wordt gevraagd.
    
    Zie de [Veelgestelde vragen](usage-analytics.md#faq) voor meer informatie over wie er toegang kan krijgen tot de app-rapporten van de microsoft 365-acceptatie sjabloon. 
    
4. Zodra de verbinding is geautoriseerd, wordt het Navigator-venster weergegeven met de gegevenssets waarmee u verbinding kunt maken.
    
    Selecteer alles en klik op **laden** .
    
    Hiermee kunt u de gegevens downloaden naar het Power BI-bureaublad. Sla dit bestand op, zodat u kunt beginnen met het maken van de gewenste rapporten.
    
    ![ODATA-waarden beschikbaar in de rapportage-API](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a>Het Microsoft 365 Gebruiksanalyse sjabloon gebruiken

U kunt ook het Power BI-sjabloonbestand dat hoort bij de rapporten van Microsoft 365 Gebruiksanalyse gebruiken als startpunt voor het maken van verbinding met de gegevens. Het voordeel van het gebruik van het PBIT-bestand is dat de verbindingstekenreeks al is vastgelegd. U kunt ook profiteren van alle aangepaste metingen die zijn gedaan ter aanvulling op de gegevens in het basisschema, en die verder uitbouwen.
  
U kunt het Power BI-sjabloonbestand downloaden van het Microsoft Downloadcentrum vanuit het [Downloadcentrum](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit). Nadat u het Power BI-sjabloonbestand hebt gedownload, gaat u als volgt te werk om aan de slag te gaan:
  
1. Open het PBIT-bestand.
    
2. Geef uw tenant-id op in het dialoogvenster.
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. Voer uw beheerdersreferenties in om u aan te melden bij Microsoft 365 wanneer hierom wordt gevraagd.
    
     meer informatie over wie er toegang kan krijgen tot de rapporten van de Microsoft 365 gebruiksanalyse. 
    
    Na autorisatie worden de gegevens in het Power BI-bestand vernieuwd.
    
    Het laden van de gegevens kan enige tijd duren. Wanneer het is voltooid, kunt u het bestand opslaan als een PBIX-bestand en de rapporten verder aanpassen of nog meer gegevensbronnen aan het rapport toevoegen.
    
4. Volg de documentatie [Aan de slag met Power BI](https://go.microsoft.com/fwlink/?linkid=849802) voor informatie over hoe u rapporten maakt, ze publiceert naar de Power BI-service en ze deelt binnen uw organisatie. Voor het volgen van dit pad voor aanpassen en delen zijn mogelijk extra Power BI-licenties vereist. Zie de [licentierichtlijnen](https://go.microsoft.com/fwlink/p/?linkid=849803) voor Power BI voor meer informatie. 
    

