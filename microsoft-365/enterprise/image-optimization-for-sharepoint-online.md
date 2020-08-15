---
title: Afbeeldingen optimaliseren voor klassieke publicerende SharePoint Online-sites
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/18/2019
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
ms.assetid: c7edb02a-fdab-4f91-9a20-cba01dad28ef
description: Meer informatie over het gebruik van weergaven en sprites om de prestaties van afbeeldingen op uw klassieke SharePoint Online-publicerende sites te verbeteren.
ms.openlocfilehash: 47d0f085c13c192417842fcef88c695fe875124c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689189"
---
# <a name="image-optimization-for-sharepoint-online-classic-publishing-sites"></a>Afbeeldingen optimaliseren voor klassieke publicerende SharePoint Online-sites

De snelheid waarmee een webpagina wordt geladen, is afhankelijk van de gecombineerde grootte van alle benodigde onderdelen voor het weergeven van de pagina, waaronder afbeeldingen, HTML, JavaScript en CSS. Afbeeldingen vormen een prima manier om uw site aantrekkelijker te maken, maar de grootte kan van invloed zijn op de prestaties. Als u uw afbeeldingen optimaliseert met compressie en het formaat wijzigen en sprites gebruikt, kunt u de effecten van zeer grote afbeeldingen verschuiven. Met SharePoint-afbeeldingsweergaven kunt u één grote afbeelding uploaden en secties van de afbeelding weergeven, zodat de afbeelding opnieuw kan worden gebruikt in plaats van opnieuw te laden.

>[!NOTE]
>Dit onderwerp is van toepassing op klassieke publicatie sites van SharePoint Online, niet moderne portal-sites. Zie voor meer informatie over het optimaliseren van afbeeldingen in moderne portal-sites in SharePoint Online [afbeeldingen in SharePoint Online-pagina's met moderne Portal optimaliseren](modern-image-optimization.md).
  
## <a name="using-sprites-to-speed-up-image-loading"></a>Sprites gebruiken om afbeeldingen sneller te laden

|||
|:-----|:-----|
| Een afbeelding sprite bevat veel kleinere afbeeldingen. Met CSS selecteert u een deel van de samengestelde afbeelding dat moet worden weergegeven op een bepaald deel van de pagina met absolute plaatsing. In principe plaatst u één afbeelding rondom de pagina in plaats van meerdere afbeeldingen te laden, en maakt u een klein deel van de afbeelding zichtbaar via een klein venster waarbij het vereiste deel van de sprite-afbeelding wordt getoond aan de eindgebruiker. In SharePoint Online worden sprites gebruikt om de verschillende pictogrammen weer te geven in de sprite-spcommon.png.  <br/>  Wat hier wordt besproken:  <br/>  Afbeeldingscompressie  <br/>  Afbeeldingen optimaliseren  <br/>  SharePoint-afbeeldingsweergaven  <br/> |![Schermafbeelding van spcommon](../media/cc5cdee1-8e54-4537-9a8a-8854f4ee849f.png)|
   
Dit kan leiden tot betere prestaties omdat u slechts één afbeelding in plaats van meerdere afbeeldingen kunt downloaden en de afbeelding vervolgens kunt opslaan en opnieuw kunt gebruiken. Zelfs als de afbeelding niet meer in de cache is opgeslagen en u een afbeelding in plaats van meerdere afbeeldingen gebruikt, wordt met deze methode het totale aantal HTTP-aanvragen naar de server verminderd waarmee de laadtijd van pagina's wordt beperkt. Dit is echt een vorm van een bundeling van afbeeldingen. Dit is een zeer handige functie als de afbeeldingen niet vaak veranderen, zoals pictogrammen, zoals weergegeven in het voorbeeld hierboven van SharePoint. U kunt [Web Essentials](https://vswebessentials.com/), een derde, openbare versie van een community gebruiken om dit eenvoudig te verwezenlijken in Microsoft Visual Studio. Zie [Minification en bundeling in SharePoint Online](https://go.microsoft.com/fwlink/?LinkId=708698)voor meer informatie.
  
## <a name="using-image-compression-and-optimization-to-speed-up-page-loading"></a>Afbeeldingen comprimeren en optimaliseren om pagina's sneller te laden

Afbeeldingscompressie en-optimalisering maakt het verkleinen van de bestandsgrootte van de afbeeldingen die u op uw site gebruikt. Vaak kunt u de grootte van een afbeelding verkleinen door de grootte van de afbeelding te wijzigen in de maximale afmetingen die de afbeelding op de site wordt weergegeven. Er is geen zin om een afbeelding groter te maken dan de afbeelding ooit wordt weergegeven. Zorg ervoor dat de afbeeldingen van de juiste afmetingen met behulp van een afbeeldingseditor snel en gemakkelijk te gebruiken zijn om de grootte van de pagina te verkleinen.
  
Wanneer afbeeldingen de juiste grootte hebben, is de volgende stap het optimaliseren van de compressie van deze afbeeldingen. Er zijn verschillende hulpprogramma's beschikbaar voor compressie en optimalisering, waaronder Fotogalerie en hulpmiddelen van derden. De sleutel voor compressie is het verkleinen van de bestandsgrootte zo veel mogelijk, zonder dat de kwaliteit van de eindgebruikers verloren gaat. Zorg ervoor dat u de gecomprimeerde bestanden op een high-definition scherm test om er zeker van te zijn dat deze er nog goed uitzien.
  
## <a name="speed-up-page-downloads-by-using-sharepoint-image-renditions"></a>Downloads van pagina's versnellen met behulp van SharePoint-afbeeldingsweergaven

Afbeeldingsweergaven zijn een functie in SharePoint Online waarmee u verschillende versies van afbeeldingen kunt gebruiken op basis van vooraf gedefinieerde afmetingen van afbeeldingen. Dit is met name belangrijk wanneer de inhoud van de afbeelding door de gebruiker is gegenereerd of als de afmetingen van de afbeelding worden verholpen door de CSS op de site. Zelfs als een afbeelding is verholpen door CSS, wordt de afbeelding met volledige resolutie nog steeds geladen. In dit geval kunt u de bestandsgrootte reduceren met afbeeldingsweergaven.
  
> [!NOTE]
> Weergaven zijn alleen beschikbaar voor SharePoint wanneer publicatie is ingeschakeld. U kunt de publicatie inschakelen onder instellingen \> site \> -instellingen Siteonderdelen van \> SharePoint Server-publicatie beheren. De optie wordt niet anders weergegeven.
  
Met de grootte van de afbeeldingsweergave kunt u de kleinst mogelijke afmetingen voor breedte of hoogte gebruiken en de grootte van de afbeelding aanpassen, zodat de andere afmetingen automatisch worden aangepast op basis van de vergrendelde hoogte-breedteverhouding. Standaard wordt de afbeelding in het midden bijgesneden met de resterende afmetingen. Als u bijvoorbeeld een voorbeeld van een weergave van 100px breed en vervaging 50 px hoog en de oorspronkelijke afbeelding van 1000px breed en 800px hoog maakt, wordt de grootte van de dimensie gewijzigd zodat de dimensie 800px nu vervaging 50 px en de 1000px Dimension (nu 62.5 px) wordt bijgesneden van het midden van de afbeelding.
  
De stappen zijn tamelijk simpel maar voor afbeeldingen die de weergaven gebruiken, moeten de weergaven op de SharePoint-site staan voordat u de afbeeldingen toevoegt. Daarnaast moet u ook de functies voor publicatie-infrastructuur van SharePoint Server (siteverzamelingsniveau) en SharePoint Server-publicatie (siteniveau) inschakelen.
  
### <a name="add-an-image-rendition-to-speed-up-page-loading"></a>Een Afbeeldingsweergave toevoegen om pagina's sneller te laden
  
1. Controleer of het gebruikersaccount waarmee deze procedure wordt uitgevoerd, ten minste ontwerpmachtigingen heeft voor de site op het hoogste niveau van de siteverzameling en dat de site wordt gepubliceerd op een webpagina.

2. Ga in een webbrowser naar de site op het hoogste niveau van de verzameling publicerende sites.

3. Kies het pictogram **instellingen** .

4. Op de pagina **site-instellingen** in de sectie **uiterlijk** ziet u de ingebouwde afbeeldingsweergaven.

    U kunt de kant-en-klare weergaven gebruiken of **afbeeldingsweergaven** kiezen om een nieuwe weergave te maken.

    ![Schermafbeelding van Afbeeldingsweergave](../media/eaae0d53-657d-47ef-b687-65c5167eae4d.PNG)
  
5. Kies **Nieuw item toevoegen**op de pagina **afbeeldingsweergaven** .

    ![Schermafbeelding van nieuw item toevoegen](../media/8cede22e-52bf-4d9d-99cb-162f2f6ce92b.PNG)
  
6. Voer in het vak **naam** op de pagina **nieuwe Afbeeldingsweergave** een naam in voor de weergave.

7. Voer in de tekstvakken **breedte** en **hoogte** de breedte en hoogte van de weergave in pixels in en kies vervolgens **Opslaan**.

    ![Schermafbeelding van de naam van de afbeeldingsweergave](../media/5a6119ed-c163-40df-a4db-ec629d15607d.PNG)
  
## <a name="custom-cropping-with-image-renditions"></a>Aangepast bijsnijden met afbeeldingsweergaven

Een Afbeeldingsweergave wordt standaard van het midden van de afbeelding gegenereerd. U kunt de vertoning van de afbeelding aanpassen voor afzonderlijke afbeeldingen door het gedeelte van de afbeelding dat u wilt gebruiken, bij te snijden. U kunt de afbeeldingen afzonderlijk bijsnijden, op basis van één voorvertoning. Wanneer u de afbeeldingen bijsnijdt, wordt de pagina sneller geladen met behulp van de blobcache van SharePoint voor het maken van een versie van de afbeelding voor elke weergave. Op deze manier wordt de server werklast verkleind omdat de afbeelding slechts één keer groter wordt en vervolgens klaar is om eindgebruikers meerdere keren te gebruiken. Zie [een Afbeeldingsweergave](https://go.microsoft.com/fwlink/p/?LinkId=525626)bijsnijden voor meer informatie over het bijsnijden van een Afbeeldingsweergave.
  

