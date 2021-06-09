---
title: Prestatieproblemen diagnosticeren met SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/9/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 3c364f9e-b9f6-4da4-a792-c8e8c8cd2e86
description: In dit artikel wordt beschreven hoe u veelvoorkomende problemen met uw SharePoint onlinesite kunt opsporen met behulp van hulpprogramma's voor ontwikkelaars van Internet Explorer.
ms.openlocfilehash: 6a29b8b2df54d74d8237418828a7aa89efdbcfaf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927610"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a>Prestatieproblemen diagnosticeren met SharePoint Online

In dit artikel wordt beschreven hoe u veelvoorkomende problemen met uw SharePoint onlinesite kunt opsporen met behulp van hulpprogramma's voor ontwikkelaars van Internet Explorer.
  
Er zijn drie verschillende manieren waarop u kunt vaststellen dat een pagina op een SharePoint Online-site een prestatieprobleem heeft met de aanpassingen.
  
- De netwerkmonitor van de F12-werkbalk

- Vergelijking met een niet-aangepaste basislijn

- SharePoint Metrische onlinereactiekoppen

In dit onderwerp wordt beschreven hoe u elk van deze methoden kunt gebruiken om prestatieproblemen te diagnosticeren. Nadat u de oorzaak van het probleem hebt gevonden, kunt u naar een oplossing werken met behulp van de artikelen over het verbeteren van SharePoint prestaties die u kunt vinden op https://aka.ms/tune .
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a>De werkbalk F12 gebruiken om de prestaties te diagnosticeren in SharePoint Online
<a name="F12ToolInfo"> </a>

In dit artikel gebruiken we Internet Explorer 11. Versies van de hulpprogramma's voor F12-ontwikkelaars in andere browsers hebben vergelijkbare functies, hoewel ze er mogelijk iets anders uitzien. Zie de volgende informatie over de hulpprogramma's voor F12-ontwikkelaars:
  
- [Nieuwe functies in F12-hulpprogramma's](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))

- [De hulpprogramma's voor F12-ontwikkelaars gebruiken](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))

Druk op **F12** om de hulpprogramma's voor ontwikkelaars weer te geven en klik vervolgens op Wi-Fi pictogram:
  
![Schermafbeelding van het wifi-pictogram hulpprogramma's voor F12-ontwikkelaars](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
Druk op **het** tabblad Netwerk op de groene knop Afspelen om een pagina te laden. Het hulpprogramma retourneert alle bestanden die door de browser worden opgevraagd om de pagina te krijgen waar u om hebt gevraagd. In de volgende schermafbeelding ziet u een dergelijke lijst.
  
![Schermafbeelding van de lijst met bestanden die zijn geretourneerd met een paginaaanvraag.](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
U kunt ook de downloadtijden van de bestanden aan de rechterkant zien, zoals wordt weergegeven in deze schermafbeelding.
  
![Diagram met de tijd die nodig is voor het laden van de aangevraagde pagina's SharePoint](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
Dit geeft een visuele weergave van hoe lang het bestand heeft moeten worden geladen. De groene lijn geeft aan wanneer de pagina klaar is om door de browser te worden weergegeven. Hierdoor hebt u snel een overzicht van de verschillende bestanden die mogelijk leiden tot trage paginabelastingen op uw site.
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a>Een niet-aangepaste basislijn instellen voor SharePoint Online
<a name="F12ToolInfo"> </a>

De beste manier om de zwakke punten van de prestaties van uw site te bepalen, is door een volledig kant-en-klaar siteverzameling in te stellen in SharePoint Online. Op deze manier kunt u alle verschillende aspecten van uw site vergelijken met wat u zou krijgen zonder aanpassing op de pagina. De OneDrive voor Bedrijven startpagina is een goed voorbeeld van een afzonderlijke siteverzameling die waarschijnlijk geen aanpassingen bevat.
  
## <a name="viewing-sharepoint-response-header-information"></a>Informatie SharePoint antwoordkop weergeven
<a name="F12ToolInfo"> </a>

In SharePoint Online hebt u toegang tot de gegevens die worden teruggestuurd naar de browser in de antwoordkop voor elk bestand. De meest nuttige waarde voor het diagnosticeren van prestatieproblemen is **SPRequestDuration,** waarmee de hoeveelheid tijd wordt weergegeven die de aanvraag op de server heeft genomen om te worden verwerkt. Dit kan helpen bepalen of de aanvraag erg zwaar en resourceintensief is. Dit is het beste inzicht dat u hebt in hoeveel werk de server doet om de pagina te bedienen.

### <a name="to-view-sharepoint-response-header-information"></a>Informatie over SharePoint koptekst weergeven
  
1. Controleer of de F12-hulpprogramma's zijn geïnstalleerd. Zie Nieuwe functies [in F12-hulpprogramma's](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))voor meer informatie over het downloaden en installeren van deze hulpprogramma's.

2. Druk in de F12-hulpmiddelen op het tabblad **Netwerk** op de groene knop Afspelen om een pagina te laden.

3. Klik op een van de .aspx-bestanden die door het hulpprogramma worden geretourneerd en klik vervolgens op **DETAILS.**

    ![Toont details van de antwoordkop](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. Klik **op Antwoordkoppen**.

    ![Diagram met de URL van de antwoordkoptekst](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a>Wat veroorzaakt prestatieproblemen in SharePoint Online?
<a name="F12ToolInfo"> </a>

In het artikel Navigatieopties voor [SharePoint Online](navigation-options-for-sharepoint-online.md) wordt een voorbeeld weergegeven van het gebruik van de waarde SPRequestDuration om te bepalen dat de ingewikkelde structurele navigatie ervoor zorgde dat de pagina lang op de server werd verwerkt. Door een waarde te nemen voor een basislijnsite (zonder aanpassing), is het mogelijk om te bepalen of het laden van een bepaald bestand lang duurt. Het voorbeeld dat wordt gebruikt in [navigatieopties voor SharePoint Online](navigation-options-for-sharepoint-online.md) is het hoofdbestand .aspx. Dat bestand bevat de meeste ASP.NET code die wordt uitgevoerd voor het laden van de pagina. Afhankelijk van de sitesjabloon die u gebruikt, kan dit start.aspx, home.aspx, default.aspx of een andere naam zijn als u de startpagina aan te passen. Als dit getal aanzienlijk hoger is dan uw basislijnsite, is dit een goede indicatie dat er iets complexs aan de hand is op uw pagina dat prestatieproblemen veroorzaakt.
  
Nadat u hebt vastgesteld dat er een specifiek probleem is voor uw site, kunt u de beste manier vinden om erachter te komen wat de slechte prestaties veroorzaakt door alle mogelijke oorzaken te verwijderen, zoals paginaaanpassingen, en deze vervolgens een voor een toe te voegen aan de site. Nadat u voldoende aanpassingen hebt verwijderd dat de pagina goed presteert, kunt u vervolgens specifieke aanpassingen een voor een toevoegen.
  
Als u bijvoorbeeld een zeer complexe navigatie hebt, kunt u de navigatie wijzigen om geen subsites weer te geven. Controleer vervolgens de hulpprogramma's voor ontwikkelaars om te zien of dit een verschil maakt. Of als u een grote hoeveelheid inhouds roll-ups hebt, probeert u deze van uw pagina te verwijderen en te kijken of dit de zaken verbetert. Als u alle mogelijke oorzaken wegwerkt en deze in één voor één toevoegt, kunt u eenvoudig bepalen welke functies het grootste probleem zijn en vervolgens naar een oplossing werken.