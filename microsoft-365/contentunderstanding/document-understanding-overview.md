---
title: Overzicht van documentbegrip
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Bekijk een overzicht van documentbegrip in Microsoft SharePoint Syntex.
ms.openlocfilehash: 3f2c463d3713048ffff7c20f2fcf6220d55d6a32
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321771"
---
# <a name="document-understanding-overview"></a>Overzicht van documentbegrip


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

Bij documentbegrip wordt gebruikgemaakt van modellen voor kunstmatige intelligentie (AI) om de classificatie van bestanden en extractie van informatie te automatiseren. Dit werkt het beste met ongestructureerde documenten zoals brieven of contracten. Deze documenten moeten tekst bevatten die kan worden geïdentificeerd op basis van frasen of patronen. De geïdentificeerde tekst duidt aan wat het bestandstype is (de classificatie) en wat u eruit wilt halen (de extractoren).

Documentbegripmodellen worden gemaakt en beheerd in een type SharePoint-site, genaamd een *inhoudscentrum*. Wanneer het model wordt toegepast op een SharePoint-documentbibliotheek, wordt het gekoppeld aan een inhoudstype dat kolommen bevat waarin de geëxtraheerde informatie wordt opgeslagen. De inhoud die u maakt, wordt opgeslagen in de SharePoint-inhoudstypegalerie. U kunt er ook voor kiezen om het schema van bestaande inhoudstypen te gebruiken.

U kunt *classificaties* en *extractoren* toevoegen aan uw documentbegripmodellen om het volgende te doen: 

- Classificaties worden gebruikt om documenten die worden geüpload naar de documentbibliotheek te identificeren en classificeren. Een classificatie kan bijvoorbeeld worden ‘getraind’ om alle documenten met *contractverlengingen* te identificeren die naar de bibliotheek worden geüpload. Het inhoudstype contractverlenging wordt door u gedefinieerd wanneer u de classificatie maakt.

- Extractoren halen informatie uit deze documenten. Bijvoorbeeld: voor alle contractverlengingsdocumenten die in uw documentbibliotheek zijn geïdentificeerd, worden in uw weergave kolommen getoond met de *Servicestartdatum* en *Klant* voor elk contractverlengingsdocument. 

U kunt voorbeeldbestanden gebruiken om de classificaties en extractoren in uw model te trainen en te testen. Voorbeeldbestanden voorzien uw model van voorbeelden van waar ze naar moeten zoeken bij het identificeren en extraheren van gegevens uit bestanden. U kunt bijvoorbeeld uw contractverlengingsclassificaties en -extractoren trainen met voorbeelden van contractverlengingsdocumenten waar uw bedrijf mee werkt. U kunt voorbeeldbestanden ook gebruiken om de effectiviteit van uw model te testen.

Nadat u uw model hebt gepubliceerd, gebruikt u het inhoudscentrum om het toe te passen op een SharePoint-documentbibliotheek waartoe u toegang hebt.  



## <a name="see-also"></a>Zie ook
[Een classificatie maken](create-a-classifier.md)

[Een extractor maken](create-an-extractor.md)

[Een inhoudscentrum maken](create-a-content-center.md)

[Een formulierverwerkingsmodel maken](create-a-form-processing-model.md)

[Een model toepassen](apply-a-model.md)   

[Het verschil tussen een documentbegripmodel en een formulierverwerkingsmodel](difference-between-document-understanding-and-form-processing-model.md)
  
[Overzicht formulierverwerking](form-processing-overview.md)
