---
title: Overzicht documentbegrip (voorbeeld)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Krijg een overzicht van het documentbegrip in Project Cortex.
ms.openlocfilehash: 13b0aa3742c6cf1c0c1123996c683d13c6577876
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537133"
---
# <a name="document-understanding-overview-preview"></a>Overzicht documentbegrip (voorbeeld)
> [!Note] 
> Project Cortex is momenteel in Preview. [Lees meer over Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

Document understanding maakt gebruik van AI-modellen om de classificatie van bestanden en het verwijderen van informatie te automatiseren. Het werkt het beste met ongestructureerde documenten, zoals brieven of contracten. De documenten moeten tekst hebben die kan worden geïdentificeerd op basis van zinnen of patronen. De geïdentificeerde tekst kan zowel het type bestand aanwijzen (de classificatie ervan) als wat u wilt extraheren (de uittreksels).

Document understanding modellen worden gemaakt en beheerd in een type SharePoint-site genaamd een inhoudscentrum. Wanneer het model wordt toegepast op een SharePoint-documentbibliotheek, is het gekoppeld aan een inhoudstype met kolommen om de uitgepakte informatie op te slaan. Het inhoudstype dat u maakt, wordt opgeslagen in de galerie met SharePoint-inhoudstype. U er ook voor kiezen om bestaande inhoudstypen te gebruiken om hun schema te gebruiken.

U *classificaties* en *uittreksels* toevoegen aan de modellen voor het begrijpen van documenten om het volgende te doen: 

- Classificaties worden gebruikt om documenten te identificeren en te classificeren die naar de documentbibliotheek zijn geüpload. Een classificatie kan bijvoorbeeld worden 'getraind' om alle *contractverlengingsdocumenten* te identificeren die naar de bibliotheek zijn geüpload. Het inhoudstype contractverlenging wordt door u gedefinieerd wanneer u uw classificatie maakt.

- Extractors halen informatie uit deze documenten. Voor alle contractverlengingsdocumenten die in uw documentbibliotheek zijn geïdentificeerd, worden kolommen bijvoorbeeld weergegeven in uw weergave met de *begindatum* van de service en *de client* voor elk document voor contractverlenging. 

U gebruikt voorbeeldbestanden om uw classificaties en extractors in uw model te trainen en te testen. Voorbeeldbestanden geven uw modelvoorbeelden van waar u op moet letten wanneer u gegevens uit bestanden probeert te identificeren en te extraheren. U traint bijvoorbeeld uw classificeerders en uitsinoordgers voor contractverlenging met voorbeelden van contractverlengingsdocumenten waarmee uw bedrijf werkt. U ook voorbeeldbestanden gebruiken om de effectiviteit van uw model te testen.

Nadat u uw model hebt gepubliceerd, gebruikt u het inhoudscentrum om het toe te passen op elke SharePoint-documentbibliotheek waar u toegang toe hebt.  


## <a name="see-also"></a>Zie ook
[Een classificatie maken](create-a-classifier.md)</br>
[Een afzuiger maken](create-an-extractor.md)</br>
[Een inhoudscentrum maken](create-a-content-center.md) 
 [Een formulierverwerkingsmodel maken](create-a-form-processing-model.md)</br>
[Een model toepassen](apply-a-model.md)   
[Verschil tussen een documentbegrip en een formulierverwerkingsmodel](difference-between-document-understanding-and-form-processing-model.md)  
[Overzicht van formulierverwerking](form-processing-overview.md)




