---
title: Minificatie en bundeling in SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/1/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
ms.assetid: 87a52468-994e-43a2-b155-7229ed659291
description: Meer informatie over het gebruik van minificatie- en bundelingstechnieken met Web Essentials om HTTP-aanvragen te beperken en de tijd die nodig is om pagina's te laden in SharePoint Online.
ms.openlocfilehash: 2e2ff7b9d36a6c28ca3840304d896782e1096e85
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688987"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a>Minificatie en bundeling in SharePoint Online

In dit artikel wordt beschreven hoe u minificatie- en bundelingstechnieken gebruikt met Web Essentials om het aantal HTTP-aanvragen te verminderen en de tijd te beperken die nodig is om pagina's in SharePoint Online te laden.
  
Wanneer u uw website aanpast, kunt u uiteindelijk een groot aantal extra bestanden toevoegen aan de server ter ondersteuning van de aanpassing. Als u extra JavaScript, CSS en afbeeldingen toevoegt, neemt het aantal HTTP-aanvragen toe aan de server, waardoor de weergave van een webpagina langer duurt. Als u meerdere bestanden van hetzelfde type hebt, kunt u deze bestanden bundelen, zodat u deze bestanden sneller kunt downloaden.
  
Voor JavaScript- en CSS-bestanden kunt u ook een methode genaamd minification gebruiken, waarbij u de totale grootte van bestanden verkleint door whitespace en andere tekens te verwijderen die niet nodig zijn.
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a>JavaScript- en CSS-bestanden minification en bundelen met Web Essentials

U kunt software van derden, zoals Web Essentials, gebruiken om CSS- en JavaScript-bestanden te bundelen.
  
> [!IMPORTANT]
> Web Essentials is een project van derden, open-source, community-based. De software is een uitbreiding naar Visual Studio 2012 en Visual Studio 2013 en wordt niet ondersteund door Microsoft. Als u Web Essentials wilt downloaden, gaat u naar de website op [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) . 
  
Web Essentials biedt twee vormen van bundeling:
  
- .bundle: voor CSS- en JavaScript-bestanden
    
- .sprite: voor afbeeldingen (alleen beschikbaar in Visual Studio 2013)
    
U kunt Web Essentials gebruiken als u een bestaande functie hebt met enkele huisstijlelementen waarnaar wordt verwezen op een aangepaste basispagina, zoals:
  
![Schermafbeelding van merkelement op aangepaste basispagina](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 **Een TE000127218- en CSS-bundel maken in Web Essentials**
  
1. Selecteer Visual Studio in Solution Explorer de bestanden die u in de bundel wilt opnemen.
    
2. Klik met de rechtermuisknop op de geselecteerde bestanden en selecteer **vervolgens Web Essentials** \> **JavaScript-bundelbestand maken** in het contextmenu. Bijvoorbeeld: 
    
    ![Schermafbeelding met menuopties voor Web Essentials](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a>De resultaten van het bundelen van JavaScript- en CSS-bestanden weergeven

Wanneer u een JavaScript- en CSS-bundel maakt, wordt in Web Essentials een XML-bestand gemaakt dat een receptbestand wordt genoemd waarin de JavaScript- en CSS-bestanden worden geïdentificeerd, evenals enkele andere configuratiegegevens: 
  
![Schermafbeelding van het JavaScript- en CSS-receptbestand](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
Als de minify-vlag is ingesteld op waar in het bundelingsrecept, worden de bestanden bovendien verkleind en gebundeld. Dit betekent dat er nieuwe, minified versies van de JavaScript-bestanden zijn gemaakt waarnaar u op de basispagina kunt verwijzen.
  
![Schermafbeelding van de minify-vlag die is ingesteld op waar](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
Wanneer u een pagina laadt vanaf uw website, kunt u de hulpprogramma's voor ontwikkelaars vanuit uw webbrowser, zoals Internet Explorer 11, gebruiken om het aantal aanvragen te bekijken dat naar de server is verzonden en hoe lang het laden van elk bestand duurde.
  
De volgende afbeelding is het resultaat van het laden van de JavaScript- en CSS-bestanden vóór minificatie.
  
![Schermafbeelding van 80 items die worden gedownload](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
Na het bundelen van de CSS- en JavaScript-bestanden is het aantal aanvragen gedaald tot 74 en duurde het downloaden van elk bestand iets langer dan de oorspronkelijke bestanden afzonderlijk:
  
![Schermafbeelding van 74 items die worden gedownload](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
Na bundeling wordt het JavaScript-bundelbestand aanzienlijk teruggebracht van 815 KB naar 365 KB:
  
![Schermafbeelding met een kleinere downloadgrootte](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a>Afbeeldingen bundelen door een afbeeldingsspite te maken

Net zoals u JavaScript- en CSS-bestanden bundelt, kunt u veel kleine pictogrammen en andere veelgebruikte afbeeldingen combineren tot een groter spriteblad en vervolgens CSS gebruiken om de afzonderlijke afbeeldingen weer te geven. In plaats van elke afzonderlijke afbeelding te downloaden, downloadt de webbrowser van de gebruiker het spriteblad eenmaal en cachet deze vervolgens op de lokale computer. Dit verbetert de laadprestaties van pagina's door het aantal downloads en retouren naar de webserver te beperken.
  
 **Een afbeeldingsspite maken in Web Essentials**
  
1. Selecteer Visual Studio in Solution Explorer de bestanden die u in de bundel wilt opnemen.
    
2. Klik met de rechtermuisknop op de geselecteerde bestanden en selecteer **vervolgens Web Essentials** \> **Afbeelding maken sprite** in het contextmenu. Bijvoorbeeld: 
    
    ![Schermafbeelding van het maken van een afbeeldingsspite](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. Kies een locatie om het sprite-bestand op te slaan. Het SPRITE-bestand is een XML-bestand waarin de instellingen en bestanden in de sprite worden beschreven. In de volgende cijfers wordt een voorbeeld van een sprite PNG-bestand en het bijbehorende .sprite XML-bestand ervan becijferd.
    
    ![Schermafbeelding van een spritebestand](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![Schermafbeelding van sprite XML-bestand](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

