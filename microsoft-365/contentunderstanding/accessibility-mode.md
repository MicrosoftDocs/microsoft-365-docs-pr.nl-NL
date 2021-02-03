---
title: 'Toegankelijkheidsmodus in SharePoint Syntex '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: Informatie over het gebruik van de toegankelijkheidsmodus bij het trainen van een model in SharePoint Syntex.
ms.openlocfilehash: 32e5bd132a7a0145f03e4620545d65d1d92ff223
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080999"
---
# <a name="sharepoint-syntex-accessibility-mode"></a>Toegankelijkheidsmodus in SharePoint Syntex

In [SharePoint Syntex](index.md)kunnen gebruikers tijdens het werken met voorbeelddocumenten de toegankelijkheidsmodus inschakelen in alle fases van modeltraining (label, training, test). Als u de toegankelijkheidsmodus gebruikt, kunnen gebruikers die slechtziend zijn gemakkelijker toetsenbordtoegankelijkheid bieden tijdens het navigeren door items en items labelen in de documentviewer.

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
- Pijl naar voren: Hiermee gaat u naar voren door afzonderlijke tekens in een geselecteerd woord.
- Pijl-terug: Hiermee gaat u achteruit door afzonderlijke tekens in een geselecteerd woord.

> [!NOTE]
> Als u meerdere woorden labelt voor één etiket, moet u elk woord van een label voorzien.


## <a name="narration"></a>Gesproken tekst

Voor verteller-gebruikers die de toegankelijkheidsmodus gebruiken, gebruikt u dezelfde toetsenbordnavigatie die voor toetsenbordgebruikers is beschreven om het voorbeelddocument in de viewer te bekijken.

Terwijl u door de voorbeelddocumenten en labelreekswaarden navigeert, geeft Verteller de gebruiker de volgende audioprompts:

- Wanneer u het toetsenbord gebruikt om door de documentviewer te navigeren, wordt de geselecteerde tekenreeks voor het geluid van Verteller opgezocht.
- Binnen een geselecteerde tekenreeks geeft Verteller-audio elk teken in de tekenreeks op terwijl u deze selecteert met behulp van de pijl vooruit of achteruit.
- Als u een gelabelde tekenreeks selecteert, wordt de waarde door Verteller vermeld en vervolgens 'gelabeld'.  Als de labelwaarde bijvoorbeeld 'Contoso' is, wordt 'Costoso gelabeld' als resultaat geven. 
- Als u op het tabblad Training een tekenreeks selecteert in de documentviewer die alleen is voorspeld, wordt de waarde voor het geluid van Verteller weergegeven en vervolgens 'voorspeld'. Deze fout treedt op wanneer met de training een waarde in het bestand wordt voorspeld die niet overeen komt met wat door de gebruiker is gelabeld.
- Als u op het tabblad Training een tekenreeks selecteert in de documentviewer die is gelabeld en voorspeld, wordt de waarde voor het geluid van Verteller weergegeven en vervolgens 'gelabeld en voorspeld'. Dit gebeurt wanneer de training is geslaagd en er een overeenkomst is tussen een voorspelde waarde en het gebruikerslabel.



Nadat een tekenreeks is gelabeld of er een label is verwijderd in de viewer, wordt u gewaarschuwd door Verteller-audio om uw wijzigingen op te slaan voordat u deze sluit.

## <a name="see-also"></a>Zie ook

[Een extractor maken](create-an-extractor.md)</br>

[Een classificatie maken](create-a-classifier.md)</br>










 


  
  



