---
title: 'SharePoint Syntex toegankelijkheidsmodus '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: Meer informatie over het gebruik van de toegankelijkheidsmodus tijdens het trainen van een model in SharePoint Syntex.
ms.openlocfilehash: 5f6e9d542f3d41dbddacd54b1b379910dcb0c9dc
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515146"
---
# <a name="sharepoint-syntex-accessibility-mode"></a>SharePoint Syntex toegankelijkheidsmodus

In [SharePoint Syntex](index.md)kunnen gebruikers de toegankelijkheidsmodus inschakelen in alle fasen van modeltraining (label, trein, test) wanneer ze met voorbeelddocumenten werken. Als u de toegankelijkheidsmodus gebruikt, kunnen slechtziende gebruikers gemakkelijker toegankelijkheid van het toetsenbord hebben terwijl ze navigeren en items labelen in de documentviewer.

Hiermee kunnen gebruikers hun toetsenbord gebruiken om door tekst in de documentviewer te navigeren en een gesproken tekst te horen van niet alleen de geselecteerde waarden, maar ook van acties (zoals labeling of het verwijderen van labeling uit geselecteerde tekst) of voorspelde labelwaarden terwijl u het model traint met extra voorbeelddocumenten. 


![Toegankelijkheidsmodus](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a>Vereisten

Als u het geluid van de gesproken tekst wilt horen, moet u de [Verteller-app](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in uw Verteller op uw Windows 10 in.

![De Verteller](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a>Labeling voor toetsenbordgebruikers

Voor toetsenbordgebruikers die de toegankelijkheidsmodus gebruiken, kunt u de volgende toetsen gebruiken als u tekst in een voorbeelddocument in de viewer labelt:

- Tab: Hiermee verplaatst u naar voren en selecteert u het volgende woord.
- Tab + Shift: Hiermee verplaatst u u naar achteren en selecteert u het vorige woord.
- Enter: Een label labelen of verwijderen uit het geselecteerde woord.
- Pijl-rechts: hiermee wordt u door afzonderlijke tekens in een geselecteerd woord verplaatst.
- Pijl-links: hiermee verplaatst u u naar achteren door afzonderlijke tekens in een geselecteerd woord.

> [!NOTE]
> Als u meerdere woorden labelt voor één label, moet u elk woord labelen.


## <a name="narration"></a>Gesproken tekst

Voor Verteller gebruikers die de toegankelijkheidsmodus gebruiken, gebruikt u dezelfde toetsenbordnavigatie die is beschreven voor toetsenbordgebruikers om door het voorbeelddocument in de viewer te gaan.

Terwijl u door de voorbeelddocumenten en labelreekswaarden navigeert, Verteller de gebruiker de volgende audioprompts:

- Wanneer u het toetsenbord gebruikt om door de documentviewer te navigeren, Verteller de geselecteerde tekenreeks.
- In een geselecteerde tekenreeks Verteller elk teken in de tekenreeks als u ze selecteert met behulp van de pijl-links of pijl-rechts.
- Als u een tekenreeks selecteert die is gelabeld, Verteller de waarde en vervolgens 'labeled'.  Als de labelwaarde bijvoorbeeld 'Contoso' is, wordt 'Costoso labeled' vermeld. 
- Als u op het tabblad training een tekenreeks selecteert in de documentviewer die alleen is voorspeld, wordt Verteller de waarde weergegeven en vervolgens 'voorspeld'. Dit gebeurt wanneer de training een waarde in het bestand voorspelt die niet overeenkomen met wat door de gebruiker is gelabeld.
- Als u op het tabblad training een tekenreeks selecteert in de documentviewer die is gelabeld en voorspeld, wordt Verteller audio de waarde weergegeven en vervolgens 'gelabeld en voorspeld'. Dit gebeurt wanneer de training is geslaagd en er een overeenkomst is tussen een voorspelde waarde en het gebruikerslabel.



Nadat een tekenreeks is gelabeld of een label is verwijderd in de viewer, wordt Verteller u gewaarschuwd om uw wijzigingen op te slaan voordat u de video sluit.

## <a name="see-also"></a>Zie ook

[Een extractor maken](create-an-extractor.md)</br>

[Een classificatie maken](create-a-classifier.md)</br>










 


  
  



