---
title: Prestatieproblemen met SharePoint Online vaststellen
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
description: In dit artikel leest u hoe u met de ontwikkelhulpprogramma's van Internet Explorer veelvoorkomende problemen met uw SharePoint Online-site kunt vaststellen.
ms.openlocfilehash: a8a79afd860006a16874370b1124696550dab029
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689178"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a>Prestatieproblemen met SharePoint Online vaststellen

In dit artikel leest u hoe u met de ontwikkelhulpprogramma's van Internet Explorer veelvoorkomende problemen met uw SharePoint Online-site kunt vaststellen.
  
Er zijn drie verschillende manieren waarop u kunt bepalen of een pagina van een SharePoint Online-site een prestatieprobleem heeft vanwege de aanpassingen.
  
- De Netwerkmonitor van F12-werkbalk

- Vergelijking met een niet-aangepaste basislijn

- Metrische gegevens voor SharePoint Online-antwoordheaders

In dit onderwerp wordt beschreven hoe u al deze methoden kunt gebruiken om problemen met de prestaties op te lossen. Als u een probleem hebt met de oorzaak van het probleem, kunt u naar een oplossing werken met behulp van de artikelen over het verbeteren van de prestaties van SharePoint, waarop u kunt zoeken https://aka.ms/tune .
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a>De werkbalk van F12 gebruiken om de prestaties van SharePoint Online te analyseren
<a name="F12ToolInfo"> </a>

In dit artikel wordt beschreven hoe u Internet Explorer 11 gebruikt. Versies van de F12-hulpprogramma's voor ontwikkelaars in andere browsers hebben soortgelijke functies, maar deze kunnen er enigszins anders uitzien. Zie voor meer informatie over de F12-hulpprogramma's voor ontwikkelaars:
  
- [Nieuw in F12-hulpmiddelen](https://go.microsoft.com/fwlink/p/?LinkId=522545)

- [Met de F12-hulpprogramma's voor ontwikkelaars](https://go.microsoft.com/fwlink/p/?LinkId=522546)

Druk op **F12** om de hulpprogramma's voor ontwikkelaars weer te geven en klik op het Wi-Fi-pictogram:
  
![Schermafbeelding van F12-pictogram van hulpmiddelen voor ontwikkelaars](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
Druk op het tabblad **netwerk** op de groene afspeelknop om de pagina te laden. Het hulpmiddel retourneert alle bestanden die in de browser worden aangevraagd om de gewenste pagina te vinden. In de volgende schermafbeelding wordt een lijst weergegeven.
  
![Schermafbeelding van de lijst met bestanden geretourneerd met een pagina-aanvraag.](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
U kunt ook de downloadtijden van de bestanden aan de rechterkant zien, zoals in deze schermafbeelding wordt weergegeven.
  
![Diagram met de tijd die nodig is voor het laden van de gevraagde pagina's van SharePoint](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
Zo krijgt u een visuele weergave van hoe lang het bestand moet worden geladen. Als de pagina klaar is om te worden weergegeven in de browser, wordt de groene lijn aangegeven. U kunt nu een snel overzicht van de verschillende bestanden weergeven die tot gevolg kunnen hebben dat er trage pagina wordt geladen op uw site.
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a>Een niet-aangepaste basislijn instellen voor SharePoint Online
<a name="F12ToolInfo"> </a>

De beste manier om de prestaties van uw site te bepalen, is door een volledig ouder-siteverzameling in SharePoint Online in te stellen. Op deze manier kunt u alle verschillende aspecten van uw site vergelijken en wat u ook verkrijgt zonder dat u op de pagina aan te passen. De startpagina van OneDrive voor bedrijven is een goed voorbeeld van een afzonderlijke siteverzameling die waarschijnlijk geen aanpassingen bevat.
  
## <a name="viewing-sharepoint-response-header-information"></a>Info over informatie in de SharePoint-antwoord weergeven
<a name="F12ToolInfo"> </a>

In SharePoint Online kunt u via de antwoordheader voor elk bestand toegang krijgen tot de informatie die naar de browser wordt verzonden. De meest nuttige waarde voor het vaststellen van prestatieproblemen is **SPRequestDuration**, waarmee de hoeveelheid tijd wordt weergegeven die de aanvraag heeft uitgevoerd op de server. Dit kan u helpen om te bepalen of de aanvraag erg zwaar is en veel bronnen. Dit is het beste inzicht in de manier waarop de server de pagina uitvoert.

### <a name="to-view-sharepoint-response-header-information"></a>Informatie over de koptekst van een SharePoint-antwoord weergeven
  
1. Zorg ervoor dat de F12-hulpprogramma's is geïnstalleerd. Zie [Nieuw in de F12-hulpprogramma's](https://go.microsoft.com/fwlink/p/?LinkId=522545)voor meer informatie over het downloaden en installeren van deze hulpmiddelen.

2. Druk in de F12-hulpprogramma's op het tabblad **netwerk** op de groene afspeelknop om de pagina te laden.

3. Klik op een van de geretourneerde aspx-bestanden en klik vervolgens op **Details**.

    ![Toont details van de antwoordheader](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. Klik op **antwoordheaders**.

    ![Diagram met de URL van de antwoordheader](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a>Wat veroorzaakten prestatieproblemen in SharePoint Online?
<a name="F12ToolInfo"> </a>

In het artikel [Navigatieopties voor SharePoint Online](navigation-options-for-sharepoint-online.md) wordt een voorbeeld van het gebruik van de SPRequestDuration-waarde weergegeven om te bepalen dat de pagina veel tijd in beslag nemen op de server. Door een waarde voor een basislijn site te maken (zonder aanpassing), kunt u bepalen of een bepaald bestand veel tijd in beslag neemt. Het voorbeeld dat in [Navigatieopties voor SharePoint Online](navigation-options-for-sharepoint-online.md) wordt gebruikt, is het belangrijkste aspx-bestand. Dit bestand bevat de meeste ASP.NET-code die wordt uitgevoerd voor het laden van pagina's. Afhankelijk van de sitesjabloon die u gebruikt, is het mogelijk dat u het volgende start. aspx, Home. aspx, default. aspx of een andere naam krijgt als u de startpagina aanpast. Als dit getal aanzienlijk groter is dan de site van de basislijn, is het een goede aanwijzing dat er op de pagina een ingewikkelde uitzondering is op de pagina die prestatieproblemen veroorzaakt.
  
Als u hebt vastgesteld dat een probleem specifiek is voor uw site, kunt u het beste de beste oorzaken van de prestaties van een site verwijderen door de mogelijke oorzaken te elimineren, zoals aanpassingen van pagina's, en ze vervolgens één voor één op de site weer toe te voegen. Wanneer u de aanpassingen van de pagina hebt verwijderd, kunt u deze op een bepaalde manier opnieuw toevoegen.
  
Als u bijvoorbeeld een zeer ingewikkelde navigatie hebt, probeer dan de navigatie te wijzigen, zodat subsites niet worden weergegeven. Of als u een grote hoeveelheid inhouds samenvoeging hebt, verwijdert u deze van uw pagina en kunt u zien of het nu beter is. Als u alle mogelijke oorzaken uitschakelt en ze in één keer toevoegt, kunt u gemakkelijk vaststellen welke functies het grootste probleem zijn en vervolgens naar een oplossing werken.
