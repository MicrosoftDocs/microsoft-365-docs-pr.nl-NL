---
title: Het thema van Office 365 aanpassen voor uw organisatie
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
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
ms.assetid: 8275da91-7a48-4591-94ab-3123a3f79530
description: 'Meer informatie over het wijzigen van het standaardthema van Office 365 en het aanpassen aan uw bedrijfslogo of -kleur. '
ms.openlocfilehash: c553e5254246bd81d435b4ebc2be2e975dd80a9d
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826325"
---
# <a name="customize-the-office-365-theme-for-your-organization"></a>Het thema van Office 365 aanpassen voor uw organisatie

Meer informatie over het aanpassen van uw thema in het Microsoft 365-beheercentrum. Als beheerder van uw Office 365 voor Bedrijven-abonnement kunt u voor iedereen in de organisatie het standaardthema wijzigen dat wordt weergegeven op de bovenste navigatiebalk. U uw bedrijfslogo toevoegen en de kleuren wijzigen om de rest van uw merk te evenaren. U zelfs een bestemmingskoppeling toevoegen waarnaar gebruikers kunnen navigeren wanneer ze uw logo selecteren. U kunt hier het standaardthema en het resultaat van het aangepaste thema in Office 365 zien.
  
![Default Office 365 theme and Custom Office 365 theme](../../media/e2cbc922-b424-4683-8c5c-fdbcbd0ce844.png)
  
## <a name="customize-your-theme-in-the-admin-center"></a>Uw thema aanpassen in het beheercentrum

1. Ga in het beheercentrum **Settings** \> naar de **instellingen**instellingen en kies het tabblad **Profiel organisatie.**

2. Kies op het tabblad **Organisatieprofiel** **aangepaste thema's**.

3. Wijzig in het deelvenster **Douanethema's** de gewenste thema-elementen voor uw organisatie:
    
    - **Een aangepaste logoafbeelding gebruiken:** kies of u een afbeelding van een URL wilt gebruiken of een afbeelding wilt uploaden. Als u een URL gebruikt, moet u ervoor zorgen dat de URL HTTPS gebruikt en 200 x 30 pixels van elke grootte is. U een logo uploaden onder 10 KB dat 200 x 30 pixels is in jpg-, PNG-, GIF- of SVG-indeling.

      > [!NOTE]
      > Gebruik alleen SVG-afbeeldingen als het logo in de mobiele SharePoint-app wordt weergegeven. Afbeeldingen die in een andere indeling worden geüpload, worden niet weergegeven in de app. Logo's zijn niet klikbaar in de SharePoint Mobile-app.

    - **Het logo klikbaar maken:** u uw logo in de navigatiebalk gebruiken als link naar een bedrijfsbron. U hier de URL voor het logo invoeren, te beginnen met http:// of https://. Dit is niet verplicht.

    - **Achtergrondafbeelding selecteren:** Selecteer de afbeelding en upload uw eigen JPG, PNG of GIF met een resolutie van 1366 x 50 pixels, niet groter dan 15 KB. De achtergrondafbeelding wordt weergegeven op de bovenste navigatiebalk op elke pagina.

      > [!NOTE]
      > Afbeeldingen die tekst bevatten, worden mogelijk niet weergegeven zoals verwacht. Ingebouwde elementen die links en rechts op de navigatiebalk worden weergegeven, kunnen variëren per service en de tekst kan door deze elementen worden afgedekt. Vanwege het dynamische karakter van de navigatiebalk kunnen we momenteel geen richtlijnen geven voor opvulling van afbeeldingen om tot een consistente ervaring te komen. 

    - **Kleur navigatiebalk:** selecteer een kleur die u wilt gebruiken voor de achtergrond van de navigatiebalk. De navigatiebalk wordt boven aan elke pagina weergegeven.

    - **Tekst en pictogrammen**: Selecteer een kleur voor de tekst en pictogrammen op de bovenste navigatiebalk.

    - **Accentkleur:** Selecteer een kleur die u wilt gebruiken voor de zwevende kleur en paginaaccenten zoals knoppen en tekst op bepaalde toepassingen.

     - **Voorkom dat gebruikers het thema overschrijven:** Draai deze schakelaar om te voorkomen dat gebruikers hun eigen thema kiezen uit onze themaselectie. Dit weerhoudt gebruikers er niet van een thema met een hoog contrast in te stellen.

    - **De gebruikersnaam weergeven:** kies of u de volledige naam van een gebruiker wilt weergeven op het ingangspunt aan de accountmanager rechtsboven op de pagina wanneer de gebruiker is aangemeld. Standaard zien gebruikers hun foto of hun initialen als een foto niet is geüpload.
    
4. Selecteer **Wijzigingen opslaan**.
    
U ziet uw nieuwe thema meteen in het beheercentrum en na een korte vertraging ziet u het in Heel Office 365, inclusief pagina's in Outlook, SharePoint, [mobiele SharePoint-app voor iOS](https://support.office.com/en-us/article/SharePoint-mobile-app-for-iOS-339402ce-16bb-4c97-9475-0c5375ccef7a)en [mobiele SharePoint-app voor Android.](https://support.office.com/en-us/article/SharePoint-mobile-app-for-Android-d875654b-fb0a-4dbe-a17a-a676cf936284) Zie de volgende afbeelding voor een voorbeeld van waar u een thema wijzigt vanuit het beheercentrum.

![m365-admin-tenant-thema-conceptueel](../../media/m365-admin-tenant-theme-conceptual.png)

U kunt op elk gewenst moment het aangepaste pictogram of de aangepaste kleuren verwijderen. Ga gewoon terug naar de themapagina en selecteer **Aangepaste thema's verwijderen**.
  
## <a name="best-practices"></a>Aanbevolen procedures

Bij het kiezen van een **logoafbeelding**raden we aan om waar mogelijk een SVG-bestandstype te gebruiken, zodat uw logo een hoge resolutie heeft op alle schermen en op alle zoomniveaus.

Kies bij het kiezen van aangepaste kleuren een **achtergrondkleur van** de navigatiebalk met een hoge contrastverhouding met de **afbeelding logo** die u hebt gekozen. Kies ook een kleur **Tekst en pictogrammen** met een hoge contrastverhouding ten opzichte van de achtergrondkleur van de **navigatiebalk** om ervoor te zorgen dat alle tekst en pictogrammen gemakkelijk zichtbaar zijn.

Bij het kiezen van aangepaste kleuren, kiest u het best een **Accentkleur** die ook op een witte of lichte achtergrond goed wordt weergegeven. De **Accentkleur** wordt gebruikt om sommige koppelingen en knoppen in te kleuren die worden weergegeven op een witte of lichte achtergrond. De **accentkleur** wordt bijvoorbeeld gebruikt om elementen in het postvak IN van een gebruiker en op de Office.com portalpagina te kleuren. 
  
De aanbevolen contrastverhouding tussen de tekst-, pictogram- of knopkleur en de achtergrondkleur is 4.5:1.

Hier vindt u een eenvoudige stroomdiagram waarmee u snel instellen met een visueel aantrekkelijk aangepast Office 365-thema voor uw organisatie:
  - Ik wil graag een kleurrijke versie van ons logo gebruiken.
    - We raden de volgende instellingen aan:
      - **Logo afbeelding**: Kleurrijke logo van uw organisatie.
      - **Navigatiebalkkleur:** een neutrale kleur. Wij raden #FAF9F7 aan voor een lichte kleur en #252423 voor een donkere kleur.
      - **Tekst- en pictogramkleur:** een kleur die contrast eert met de **kleur navigatiebalk**. Wij raden #FAF9F7 aan voor een lichte kleur en #252423 voor een donkere kleur.
      - **Accentkleur:** Een donkere merkkleur. Bij bepaalde toepassingen moet deze kleur zichtbaar zijn op een lichte achtergrond.
  - Ik wil graag een neutrale versie van ons logo gebruiken en kleur in de navigatiebalk weergeven.
    - We raden de volgende instellingen aan:
      - **Logoafbeelding**: Het neutrale logo van uw organisatie.
      - **Navigatiebalkkleur:** een merkkleur die contrasteert met uw logo.
      - **Tekst- en pictogramkleur:** kies een kleur die contrasteert met de merkkleur die u hebt gekozen voor de **kleur navigatiebalk**. Wij raden #252423 aan voor een donkere kleur en #FAF9F7 voor een lichte kleur.
      - **Accentkleur:** Een donkere merkkleur. Bij bepaalde toepassingen moet deze kleur zichtbaar zijn op een lichte achtergrond.
  
## <a name="related-articles"></a>Verwante artikelen

[Aangepaste tegels toevoegen aan de pagina Mijn apps en het startprogramma voor apps](../manage/customize-the-app-launcher.md)
  
  

