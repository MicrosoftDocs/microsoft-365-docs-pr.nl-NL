---
title: Het hulpprogramma Paginadiagnose gebruiken voor SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/03/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPO160
- MOE150
- BSA160
f1.keywords:
- NOCSH
description: Gebruik het hulpprogramma Paginadiagnose voor SharePoint om SharePoint moderne portal en klassieke publicatiepagina's van Online te analyseren op basis van een vooraf gedefinieerde set prestatiecriteria.
ms.openlocfilehash: b55e5c04f56bac4e6313284de60753d1beaaaed1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921628"
---
# <a name="use-the-page-diagnostics-for-sharepoint-tool"></a>Het hulpprogramma Paginadiagnose SharePoint gebruiken

In dit artikel wordt beschreven hoe u het hulpprogramma **Paginadiagnose** voor SharePoint kunt gebruiken om moderne en klassieke sitepagina's van SharePoint Online te analyseren op basis van een vooraf gedefinieerde set prestatiecriteria.

Het hulpprogramma Paginadiagnose voor SharePoint kan worden geïnstalleerd voor:

- **Microsoft Edge** [(Edge-extensie)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji)
- **Chrome** [(Chrome-extensie)](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi)

>[!TIP]
>Versie **2.0.0** en hoger bevat ondersteuning voor moderne pagina's naast klassieke sitepagina's. Als u niet zeker weet welke versie van het hulpprogramma u gebruikt, kunt u de **koppeling** Over of de drie puntjes (...) selecteren om uw versie te verifiëren. **Werk altijd bij naar de nieuwste versie wanneer** u het hulpprogramma gebruikt.

Het hulpprogramma Paginadiagnose voor SharePoint is een browserextensie voor de nieuwe Microsoft Edge ( en Chrome-browsers die zowel SharePoint Moderne portal online als klassieke https://www.microsoft.com/edge) publicerende sitepagina's analyseren. Dit hulpprogramma werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint systeempagina.

Het hulpprogramma genereert een rapport voor elke geanalyseerde pagina waarin wordt weergegeven hoe de pagina presteert ten opzichte van een vooraf gedefinieerde set regels en gedetailleerde informatie wekt wanneer de resultaten voor een test buiten de basislijnwaarde vallen. SharePoint Onlinebeheerders en ontwerpers kunnen het hulpprogramma gebruiken om prestatieproblemen op te lossen en ervoor te zorgen dat nieuwe pagina's worden geoptimaliseerd voordat ze worden gepubliceerd.

Het hulpprogramma Paginadiagnose is ontworpen om alleen SharePoint sitepagina's te analyseren, niet systeempagina's zoals *allitems.aspx* of *sharepoint.aspx.* Als u het hulpprogramma probeert uit te voeren op een systeempagina of een andere niet-sitepagina, ontvangt u een foutbericht met de melding dat het hulpprogramma niet kan worden uitgevoerd voor dat type pagina.

> [!div class="mx-imgBorder"]
> ![Moet worden uitgevoerd op een SharePoint pagina](../media/page-diagnostics-for-spo/pagediag-Error-StartPage.png)

Dit is geen fout in het hulpprogramma, omdat het beoordelen van bibliotheken of systeempagina's geen waarde heeft. Ga naar een SharePoint sitepagina om het hulpprogramma te gebruiken. Als deze fout optreedt op een SharePoint pagina, controleert u de basispagina om te controleren of de SharePoint niet zijn verwijderd.

Als u feedback wilt geven over het hulpprogramma, selecteert u het beletselteken in de rechterbovenhoek van het hulpprogramma en selecteert u [vervolgens Feedback geven.](https://go.microsoft.com/fwlink/?linkid=874109)

> [!div class="mx-imgBorder"]
> ![Feedback geven](../media/page-diagnostics-for-spo/pagediag-feedback.png)
  
## <a name="install-the-page-diagnostics-for-sharepoint-tool"></a>Het hulpprogramma Paginadiagnose voor SharePoint installeren

De installatieprocedure in deze sectie werkt voor zowel chrome als Microsoft Edge browsers.

> [!IMPORTANT]
> Microsoft leest geen gegevens of pagina-inhoud die wordt geanalyseerd door het hulpprogramma Paginadiagnose voor SharePoint en we leggen geen persoonlijke gegevens, website- of downloadgegevens vast. De enige identificeerbare gegevens die door het hulpprogramma bij Microsoft zijn geregistreerd, zijn de tenantnaam, het aantal regels dat is mislukt en de datum en tijd waarop het hulpprogramma is uitgevoerd. Deze informatie wordt door Microsoft gebruikt om meer inzicht te krijgen in moderne portal- en publicatiesitegebruikstrends en veelvoorkomende prestatieproblemen.

1. Installeer het hulpprogramma Paginadiagnose **SharePoint voor** Microsoft Edge [(edge-extensie)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji) of **Chrome** [(Chrome-extensie)](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi). Bekijk het privacybeleid van de gebruiker op de beschrijvingspagina in de store. Wanneer u het hulpprogramma toevoegt aan uw browser, ziet u de volgende machtigingen.

    > [!div class="mx-imgBorder"]
    > ![Uitbreidingsmachtigingen](../media/page-diagnostics-for-spo/pagediag-add-to-edge.png)

    Deze melding is op zijn plaats omdat een pagina inhoud kan bevatten van locaties buiten SharePoint, afhankelijk van de webonderdelen en aanpassingen op de pagina. Dit betekent dat het hulpprogramma de aanvragen en antwoorden leest wanneer op de startknop wordt geklikt en alleen voor het actieve tabblad SharePoint waarop het hulpprogramma wordt uitgevoerd. Deze gegevens worden lokaal vastgelegd door de webbrowser en zijn beschikbaar via de knop Exporteren  naar **JSON** of Exporteren naar **HAR** op het tabblad Netwerkspoor van het hulpprogramma. De gegevens worden niet verzonden naar of vastgelegd door **Microsoft.** (Het hulpprogramma respecteert het privacybeleid van Microsoft dat hier toegankelijk [is](https://go.microsoft.com/fwlink/p/?linkid=857875).)

    De _machtiging Uw downloads beheren_ heeft betrekking op het gebruik van de functionaliteit Exporteren naar **JSON van het** hulpprogramma. Volg de eigen privacyrichtlijnen van uw bedrijf voordat u het JSON-bestand buiten uw organisatie deelt, omdat de resultaten URL's bevatten en die kunnen worden geclassificeerd als PII (Persoonlijke identificeerbare gegevens).
1. Als u het hulpprogramma wilt gebruiken in de Incognito- of InPrivate-modus, volgt u de procedure voor uw browser:
    1. Ga Microsoft Edge naar **Extensies** of typ edge://extensions _url-balk_ en selecteer **Details** voor de extensie. Schakel in de extensie-instellingen het selectievakje in voor **toestaan in InPrivate.**
    1. Ga in Chrome naar **Extensies** of typ _chrome://extensions_ in de URL-balk en selecteer **Details** voor de extensie. Selecteer in de extensie-instellingen de schuifregelaar voor **toestaan in Incognito.**
1. Ga naar de SharePoint sitepagina op SharePoint Online die u wilt bekijken. We hebben toegestaan dat items op pagina's worden 'vertraagd geladen'. Daarom wordt het hulpprogramma niet automatisch gestopt (dit is een ontwerp voor alle scenario's voor het laden van pagina's). Als u de verzameling wilt stoppen, **selecteert u Stoppen**. Zorg ervoor dat de paginabelasting is voltooid voordat u de gegevensverzameling stopt of dat u slechts een gedeeltelijke trace vasthoudt.
1. Klik op de werkbalkknop van de extensie ![Paginadiagnose voor SharePoint logo](../media/page-diagnostics-for-spo/pagediag-icon32.png) als u het hulpprogramma wilt laden, ziet u het volgende uitbreidingspopupvenster:

    ![Pop-up van het hulpprogramma Paginadiagnose](../media/page-diagnostics-for-spo/pagediag-Landing.png)

Selecteer **Start** om te beginnen met het verzamelen van gegevens voor analyse.

## <a name="what-youll-see-in-the-page-diagnostics-for-sharepoint-tool"></a>Wat u in het hulpprogramma Paginadiagnose voor SharePoint ziet

1. Klik op de drie puntjes (...) in de rechterbovenhoek van het hulpprogramma om de volgende koppelingen te vinden:
   1. De **koppeling Aanvullende bronnen** bevat algemene richtlijnen en details over het hulpprogramma, inclusief een koppeling terug naar dit artikel.
   1. De **koppeling Feedback geven** biedt een koppeling naar de SharePoint sites en de user _voice-site voor_ samenwerking.
   1. De **koppeling** Over bevat de momenteel geïnstalleerde versie van het hulpprogramma en een directe koppeling naar de kennisgeving van derden van het hulpprogramma.  
1. De **correlatie-id, SPRequestDuration, SPIISLatency,** Laadtijd **voor** pagina's en **URL-gegevens** zijn informatief en kunnen voor een paar doeleinden worden gebruikt.

    > [!div class="mx-imgBorder"]
    > ![Details van de diagnostische pagina](../media/page-diagnostics-for-spo/pagediag-details.PNG)

   - **CorrelationID** is een belangrijk element bij het werken met Microsoft Support, omdat ze hierdoor aanvullende diagnostische gegevens voor de specifieke pagina kunnen verzamelen.
   - **SPRequestDuration** is de tijd die nodig is om SharePoint pagina te verwerken. Structurele navigatie, grote afbeeldingen, veel API-oproepen kunnen allemaal bijdragen aan langere duur.
   - **SPIISLatency** is de tijd in milliseconden die is genomen voor SharePoint online de pagina begint te laden. Deze waarde omvat niet de tijd die nodig is om de webtoepassing te laten reageren.
   - **Laadtijd voor pagina's** is de totale tijd die door de pagina is vastgelegd vanaf het moment van de aanvraag tot het moment dat het antwoord is ontvangen en weergegeven in de browser. Deze waarde wordt beïnvloed door verschillende factoren, zoals netwerklatentie, de prestaties van de computer en de tijd die nodig is voor het laden van de pagina door de browser.
   - De **pagina-URL** (Uniform Resource Locator) is het webadres van de huidige pagina.

1. Op [**het tabblad Diagnostische**](#how-to-use-the-diagnostic-tests-tab) tests worden de analyseresultaten weergegeven in drie categorieën. **Geen actie vereist,** **Verbeterkansen en** **Aandacht vereist.** Elk testresultaat wordt weergegeven door een item in een van deze categorieën, zoals beschreven in de volgende tabel:

    |Categorie  |Kleur  |Beschrijving  |
    |---------|---------|---------|
    |**Aandacht vereist** |Rood |Het testresultaat valt buiten de basislijnwaarde en is van invloed op de paginaprestaties. Volg de richtlijnen voor herstel.|
    |**Verbeterkansen** |Geel |Het testresultaat valt buiten de basislijnwaarde en kan bijdragen aan prestatieproblemen. Testspecifieke criteria kunnen van toepassing zijn.|
    |**Geen actie vereist** |Groen |Het testresultaat valt binnen de basislijnwaarde van de test.|

    > [!div class="mx-imgBorder"]
    > ![Paginadiagnose](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

1. Een [**tabblad Netwerk trace**](#how-to-use-the-network-trace-tab-and-how-to-export-a-har-file) bevat details over pagina-buildaanvragen en antwoorden.

## <a name="how-to-use-the-diagnostic-tests-tab"></a>Het tabblad Diagnostische tests gebruiken

Wanneer u een SharePoint moderne portalpagina of klassieke publicatiesitepagina analyseert met het hulpprogramma Paginadiagnose voor SharePoint, worden de resultaten geanalyseerd  met vooraf gedefinieerde regels die resultaten vergelijken met basislijnwaarden en worden weergegeven op het tabblad Diagnostische tests. Regels voor bepaalde tests kunnen verschillende basislijnwaarden gebruiken voor moderne portal- en klassieke publicatiesites, afhankelijk van hoe specifieke prestatiekenmerken tussen de twee verschillen.

Testresultaten die worden  weergegeven  in de categorieën Verbeterkansen of Vereiste aandacht geven gebieden aan die moeten worden beoordeeld op aanbevolen procedures en kunnen worden geselecteerd om aanvullende informatie over het resultaat weer te geven. Details voor elk item bevatten een koppeling _Meer_ informatie, waarmee u rechtstreeks naar de juiste richtlijnen voor de test gaat. Testresultaten die worden weergegeven in de categorie **Geen actie vereist** geven aan dat de relevante regel wordt nageleefd en dat er geen extra details worden weergegeven wanneer deze zijn geselecteerd.

De informatie op het tabblad Diagnostische tests geeft niet aan hoe u pagina's ontwerpt, maar markeert factoren die van invloed kunnen zijn op de prestaties van pagina's. Sommige paginafunctionaliteit en aanpassingen hebben een onvermijdelijke invloed op de paginaprestaties en moeten worden gecontroleerd op mogelijke herstel of weglating van de pagina als de impact aanzienlijk is.

Rode of gele resultaten kunnen ook webonderdelen aangeven die gegevens te vaak vernieuwen. Bedrijfsnieuws wordt bijvoorbeeld niet elke seconde bijgewerkt, maar aangepaste webonderdelen zijn vaak gemaakt om elke seconde het laatste nieuws op te halen in plaats van caching-elementen te implementeren die de algehele gebruikerservaring kunnen verbeteren. Houd er bij het toevoegen van webonderdelen op een pagina rekening mee dat er vaak eenvoudige manieren zijn om de prestaties te beperken door de waarde van elke beschikbare parameter te evalueren om ervoor te zorgen dat deze geschikt is ingesteld voor het beoogde doel.

>[!NOTE]
>Klassieke teamsites die de publicatiefunctie niet hebben ingeschakeld, kunnen geen gebruik maken van CDN's. Wanneer u het hulpprogramma op deze sites uit te voeren, CDN de test mislukt en kan worden genegeerd, maar alle resterende tests zijn van toepassing. De extra functionaliteit van de SharePoint publicatiefunctie kan de laadtijden van pagina's verhogen, zodat deze niet alleen moet worden ingeschakeld om de CDN toestaan.

>[!IMPORTANT]
>Testregels worden regelmatig toegevoegd en bijgewerkt, dus raadpleeg de nieuwste versie van het hulpprogramma voor meer informatie over de huidige regels en specifieke informatie in testresultaten. U kunt de versie verifiëren door uw extensies te beheren en de extensie geeft aan of er een update beschikbaar is.

## <a name="how-to-use-the-network-trace-tab-and-how-to-export-a-har-file"></a>Het tabblad Netwerk traceren gebruiken en een HAR-bestand exporteren

Op **het tabblad Netwerk** trace vindt u gedetailleerde informatie over beide aanvragen voor het maken van de pagina en de antwoorden die zijn ontvangen van SharePoint.

1. **Zoek naar laadtijden van items die als rood zijn gemarkeerd.** Elke aanvraag en elk antwoord wordt met een kleurcode weergegeven om de invloed ervan op de algehele paginaprestaties aan te geven met behulp van de volgende latentiemetrische gegevens:
    - Groen: \< 500 ms
    - Geel: 500-1000 ms
    - Rood: \> 1000 ms

    > [!div class="mx-imgBorder"]
    > ![Netwerk trace](../media/page-diagnostics-for-spo/pagediag-networktrace-red.png)

    In de bovenstaande afbeelding heeft het rode item betrekking op de standaardpagina. Het wordt altijd rood weergegeven, tenzij de pagina wordt geladen in \< 1000 ms (minder dan 1 seconde).

2. **Laadtijden van items testen.** In sommige gevallen is er geen tijd- of kleurindicator omdat de items al in de cache zijn opgeslagen door de browser. Als u dit correct wilt testen, opent u de pagina, leegt u de browsercache en klikt u vervolgens op **Start,** omdat hierdoor een 'koude' pagina wordt geladen en een echte weerspiegeling is van de eerste paginabelasting. Dit moet dan worden vergeleken met de 'warme' paginabelasting, omdat hiermee ook wordt bepaald welke items op de pagina in de cache worden opgeslagen.

3. **Deel relevante details met anderen die kunnen helpen bij het onderzoeken van problemen.** Als u de details of informatie in het hulpprogramma wilt delen met uw ontwikkelaars of een technische ondersteuningspersoon, is het gebruik van de HAR **(Enable exporting to HTTP Archive)** de aanbevolen methode. 

   > [!div class="mx-imgBorder"]
   > ![Exporteren naar HAR inschakelen](../media/page-diagnostics-for-spo/pagediag-submithar.png)

Dit moet zijn ingeschakeld voordat u op Start klikt, zodat de foutopsporingsmodus in uw browser wordt ingeschakeld. Er wordt een HTTP-archiefbestand (HAR) gegenereerd dat vervolgens toegankelijk is via het tabblad Netwerk traceren. Klik op 'Exporteren naar HAR' en download het bestand naar uw computer en u kunt het bestand vervolgens dienovereenkomstig delen. Het bestand kan worden geopend in verschillende hulpprogramma's voor foutopsporing, zoals F12 Developer Tools en Fiddler.

> [!div class="mx-imgBorder"]
> ![Netwerkspoor](../media/page-diagnostics-for-spo/pagediag-networktracehar.png)

> [!IMPORTANT]
> Deze resultaten bevatten URL's en kunnen worden geclassificeerd als PII (Persoonsgegevens). Zorg ervoor dat u de richtlijnen van uw organisatie volgt voordat u deze informatie distribueert.

## <a name="engaging-with-microsoft-support"></a>Interactie met Microsoft-ondersteuning

We hebben een **microsoft-ondersteuningsniveaufunctie opgenomen** die alleen moet worden gebruikt wanneer u rechtstreeks aan een ondersteuningscase werkt. Als u deze functie gebruikt, hebt u geen baat bij gebruik zonder ondersteuning voor teamafspraak en kan de pagina aanzienlijk trager presteren. Er is geen extra informatie bij het gebruik van deze functie in het hulpprogramma, omdat de aanvullende informatie wordt toegevoegd aan de logboekregistratie in de service.

Er is geen wijziging zichtbaar, behalve dat u een melding krijgt dat u deze hebt ingeschakeld en dat de prestaties van uw pagina aanzienlijk worden afgebroken met 2-3 keer tragere prestaties terwijl deze zijn ingeschakeld. Deze is alleen relevant voor de betreffende pagina en die actieve sessie. Daarom moet dit spaarzaam en alleen worden gebruikt wanneer u actief bezig bent met ondersteuning.

### <a name="to-enable-the-microsoft-support-level-feature"></a>De functie Microsoft Support-niveau inschakelen

1. Open het hulpprogramma Paginadiagnose voor SharePoint.
2. Druk op het toetsenbord op **Alt-Shift-L.** Hiermee wordt het selectievakje **Ondersteuningsregistratie inschakelen** weergegeven.
3. Schakel het selectievakje in en klik vervolgens op **Start** om de pagina opnieuw te laden en uitgebreide logboekregistratie te genereren.

   > [!div class="mx-imgBorder"]
   > ![Ondersteuningsoptie ingeschakeld](../media/page-diagnostics-for-spo/pagediag-support.png)
  
    U moet de Correlatie-informatie (boven aan het hulpprogramma) noteren en deze aan uw ondersteuningsvertegenwoordiger verstrekken, zodat deze aanvullende informatie over de diagnostische sessie kan verzamelen.

## <a name="related-topics"></a>Verwante onderwerpen

[Prestaties SharePoint online afstemmen](tune-sharepoint-online-performance.md)

[Prestaties Office 365 afstemmen](tune-microsoft-365-performance.md)

[Prestaties in de moderne SharePoint ervaring](/sharepoint/modern-experience-performance)

[Netwerken voor contentlevering](content-delivery-networks.md)

[De Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)