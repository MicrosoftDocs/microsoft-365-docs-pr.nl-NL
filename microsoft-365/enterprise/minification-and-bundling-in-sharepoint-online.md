---
title: Minification en bundeling in SharePoint Online
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
description: Meer informatie over het gebruik van minification en bundel technieken met Web Essentials voor minder HTTP-aanvragen en de manier waarop u pagina's laadt in SharePoint Online.
ms.openlocfilehash: 2e2ff7b9d36a6c28ca3840304d896782e1096e85
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688987"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a>Minification en bundeling in SharePoint Online

In dit artikel wordt uitgelegd hoe u minification en bundel technieken met Web Essentials gebruikt om het aantal HTTP-aanvragen te verminderen en de tijd te besparen voor het laden van pagina's in SharePoint Online.
  
Wanneer u uw website aanpast, kunt u het toevoegen van een groot aantal extra bestanden op de server beëindigen om de aanpassing te ondersteunen. Door extra JavaScript, CSS en afbeeldingen toe te voegen, wordt het aantal HTTP-aanvragen voor de server verhoogd waarmee de tijd die het duurt voor het weergeven van een webpagina groter wordt. Als u meerdere bestanden van hetzelfde type hebt, kunt u deze bestanden bundelen om sneller het downloaden van deze bestanden uit te voeren.
  
Voor JavaScript-en CSS-bestanden kunt u ook gebruikmaken van een methode met de naam minification, waarbij u de totale grootte van bestanden beperkt door witruimte en andere tekens die niet nodig zijn te verwijderen.
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a>Minification en bundeling van JavaScript en CSS-bestanden met Web Essentials

U kunt software van derden gebruiken, zoals web Essentials, om CSS-en JavaScript-bestanden te bundelen.
  
> [!IMPORTANT]
> Web Essentials is een derde, openende bron-, op Community gebaseerd project. De software is een uitbreiding op Visual Studio 2012 en Visual Studio 2013 en wordt niet ondersteund door Microsoft. Bezoek de website op de website van uw voor het downloaden van web Essentials [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) . 
  
Web Essentials biedt twee soorten bundeling:
  
- . bundel: voor CSS-en JavaScript-bestanden
    
- . Sprite: voor afbeeldingen (alleen beschikbaar in Visual Studio 2013)
    
U kunt web Essentials gebruiken als u een bestaande functie hebt voor bepaalde huisstijl elementen waarnaar wordt verwezen in een aangepaste basispagina, zoals:
  
![Schermafbeelding van het merk element in de aangepaste basispagina](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 **Een TE000127218 en CSS-bundel maken in Web Essentials**
  
1. Selecteer in Visual Studio in Solution Explorer de bestanden die u wilt opnemen in de bundel.
    
2. Klik met de rechtermuisknop op de geselecteerde bestanden en selecteer vervolgens **Web Essentials** - \> **bundelbestand maken** in het contextmenu. Bijvoorbeeld: 
    
    ![Schermafbeelding van de menu opties voor het werken met Web Essentials](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a>De resultaten van het bundelen van JavaScript-en CSS-bestanden bekijken

Wanneer u een JavaScript-en CSS-bundel maakt, wordt met Web Essentials een XML-bestand gemaakt, een recept bestand met de naam van de JavaScript-en CSS-bestanden en andere configuratiegegevens: 
  
![Schermafbeelding van recept-bestand voor JavaScript en CSS](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
Als de vlag Minify is ingesteld op waar in het bundelen van het recept, worden de bestanden kleiner en gegroepeerd. Dit betekent dat er nieuwe, minified-versies van de JavaScript-bestanden zijn gemaakt waarnaar u op de basispagina kunt verwijzen.
  
![Schermafbeelding van de vlag Minify ingesteld op waar](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
Wanneer u een pagina van uw website laadt, kunt u de hulpmiddelen voor ontwikkelaars in uw webbrowser gebruiken, zoals Internet Explorer 11, om het aantal aanvragen te zien dat naar de server is verzonden en hoelang elk bestand moet worden geladen.
  
De volgende afbeelding is het resultaat van het laden van de JavaScript-en CSS-bestanden voor minification.
  
![Schermafbeelding met het downloaden van 80-items](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
Na het bundelen van de CSS-en JavaScript-bestanden, is het aantal aanvragen gedaald tot 74 en duurde het slechts iets langer om elk bestand te downloaden dan de oorspronkelijke bestanden:
  
![Schermafbeelding met het downloaden van 74-items](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
Na het bundelen is het JavaScript-bundelbestand aanzienlijk verkleind van 815KB in 365KB:
  
![Schermafbeelding met gereduceerde downloadgrootte](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a>Afbeeldingen bundelen door een afbeeldings sprite te maken

Net als in de manier waarop u JavaScript-en CSS-bestanden bundelt, kunt u een groot aantal kleine pictogrammen en andere gemeenschappelijke afbeeldingen combineren in een groter etiketvel en de afzonderlijke afbeeldingen met CSS weergeven. In plaats van elke afzonderlijke afbeelding te downloaden, downloadt de webbrowser van de gebruiker de sprite-blad eenmaal en slaat u het vervolgens op in de lokale computer. Hierdoor wordt de prestaties van de pagina geladen en worden de pagina's gepaard met het aantal downloads.
  
 **Een afbeeldings sprite maken in Web Essentials**
  
1. Selecteer in Visual Studio in Solution Explorer de bestanden die u wilt opnemen in de bundel.
    
2. Klik met de rechtermuisknop op de geselecteerde bestanden en selecteer vervolgens **Web Essentials** , \> **Maak afbeelding sprite** in het contextmenu. Bijvoorbeeld: 
    
    ![Schermafbeelding waarin wordt getoond hoe u een afbeeldings sprite maakt](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. Kies een locatie om het bestand sprite op te slaan. Het bestand. Sprite is een XML-bestand waarin de instellingen en bestanden van de sprite worden beschreven. In de volgende afbeelding ziet u een voorbeeld van een sprite PNG-bestand en het bijbehorende XML-bestand. sprite.
    
    ![Schermafbeelding van een sprite-bestand](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![Schermafbeelding van Sprite-XML-bestand](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

