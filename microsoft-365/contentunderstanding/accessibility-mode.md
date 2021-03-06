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
description: Informatie over het gebruik van de toegankelijkheidsmodus bij het trainen van een model in SharePoint Syntex.
ms.openlocfilehash: 5f6e9d542f3d41dbddacd54b1b379910dcb0c9dc
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515146"
---
# <a name="sharepoint-syntex-accessibility-mode"></a>SharePoint Syntex toegankelijkheidsmodus

In [SharePoint Syntex](index.md)kunnen gebruikers tijdens het werken met voorbeelddocumenten de toegankelijkheidsmodus inschakelen in alle fasen van modeltraining (label, training, test). Als u de toegankelijkheidsmodus gebruikt, kunnen gebruikers die slechtziend zijn gemakkelijker toetsenbordtoegankelijkheid bieden tijdens het navigeren door items en items labelen in de documentviewer.

Hierdoor kunnen gebruikers hun toetsenbord gebruiken om door tekst in de documentviewer te navigeren en ook gesproken tekst te horen van niet alleen de geselecteerde waarden, maar ook van acties (zoals labelen of verwijderen van labeling uit geselecteerde tekst) of voorspelde labelwaarden terwijl u het model met extra voorbeelddocumenten trainen. 


![Toegankelijkheidsmodus](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a>Vereisten

Als u de audio van de gesproken tekst wilt horen, moet u de [Verteller-app](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in de verteller-instellingen op uw Windows 10-systeem in uitschakelen.

![Verteller in te zetten](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a>Labelen voor toetsenbordgebruikers

Voor toetsenbordgebruikers die de toegankelijkheidsmodus gebruiken, kunt u de volgende toetsen gebruiken als u een label aan tekst in een voorbeelddocument in de viewer wilt toevoegen:

- Tab: Hiermee gaat u naar voren en selecteert u het volgende woord.
- Tab+Shift: hiermee verplaatst u het vorige woord naar achteren en selecteert u het vorige woord.
- Enter: een label toevoegen aan of verwijderen van het geselecteerde woord.
- Pijl-rechts: Hiermee gaat u naar voren door afzonderlijke tekens in een geselecteerd woord.
- Pijl-links: Hiermee gaat u achteruit door afzonderlijke tekens in een geselecteerd woord.

> [!NOTE]
> Als u meerdere woorden labelt voor één etiket, moet u elk woord van een label voorzien.


## <a name="narration"></a>Gesproken tekst

Voor verteller-gebruikers die de toegankelijkheidsmodus gebruiken, gebruikt u dezelfde toetsenbordnavigatie die voor toetsenbordgebruikers is beschreven om het voorbeelddocument in de viewer te bekijken.

Terwijl u door de voorbeelddocumenten en labelreekswaarden navigeert, geeft Verteller de gebruiker de volgende audioprompts:

- Wanneer u het toetsenbord gebruikt om door de documentviewer te navigeren, wordt de geselecteerde tekenreeks voor het geluid van Verteller opgezocht.
- Binnen een geselecteerde tekenreeks geeft Verteller-audio elk teken in de tekenreeks op terwijl u deze selecteert met de pijl-links of pijl-rechts.
- Als u een gelabelde tekenreeks selecteert, wordt in Verteller de waarde vermeld en vervolgens 'gelabeld'.  Als de labelwaarde bijvoorbeeld 'Contoso' is, wordt 'Costoso gelabeld' als resultaat geven. 
- Als u op het tabblad Training een tekenreeks selecteert in de documentviewer die alleen is voorspeld, wordt de waarde voor het geluid van Verteller weergegeven en vervolgens 'voorspeld'. Deze fout treedt op wanneer met de training een waarde in het bestand wordt voorspeld die niet overeen komt met wat door de gebruiker is gelabeld.
- Als u op het tabblad Training een tekenreeks selecteert in de documentviewer die is gelabeld en voorspeld, wordt de waarde door Verteller-audio aangeduid en vervolgens 'gelabeld en voorspeld'. Dit gebeurt wanneer de training is geslaagd en er een overeenkomst is tussen een voorspelde waarde en het gebruikerslabel.



Nadat een tekenreeks is gelabeld of er een label is verwijderd in de viewer, wordt u gewaarschuwd voor het opslaan van de wijzigingen voordat u de tekenreeks sluit.

## <a name="see-also"></a>Zie ook

[Een extractor maken](create-an-extractor.md)</br>

[Een classificatie maken](create-a-classifier.md)</br>










 


  
  



