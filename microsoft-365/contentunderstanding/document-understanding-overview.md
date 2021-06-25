---
title: Overzicht van documentbegrip
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Bekijk een overzicht van documentbegrip in Microsoft SharePoint Syntex.
ms.openlocfilehash: 7e5818a929fa0f4554a7ee4ece460b4fe0d691aa
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683821"
---
# <a name="document-understanding-overview"></a>Overzicht van documentbegrip


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

Bij documentbegrip wordt gebruikgemaakt van modellen voor kunstmatige intelligentie (AI) om de classificatie van bestanden en extractie van informatie te automatiseren. Dit werkt het beste met ongestructureerde documenten zoals brieven of contracten. Deze documenten moeten tekst bevatten die kan worden geïdentificeerd op basis van frasen of patronen. De geïdentificeerde tekst duidt aan wat het bestandstype is (de classificatie) en wat u eruit wilt halen (de extractoren).

> [!NOTE]
> Zie [Ingebruikname van SharePoint Syntex: introductiehandleiding](./adoption-getstarted.md) voor meer informatie over scenariovoorbeelden voor documentbegrip.

Documentbegripmodellen worden gemaakt en beheerd in een type SharePoint-site, genaamd een *inhoudscentrum*. Wanneer het model wordt toegepast op een SharePoint-documentbibliotheek, wordt het gekoppeld aan een inhoudstype dat kolommen bevat waarin de geëxtraheerde informatie wordt opgeslagen. De inhoud die u maakt, wordt opgeslagen in de SharePoint-inhoudstypegalerie. U kunt er ook voor kiezen om het schema van bestaande inhoudstypen te gebruiken.

> [!NOTE]
> Alleen-lezen- of verzegelde inhoudstypen kunnen niet worden bijgewerkt, dus kunnen ze niet worden gebruikt in een model.

U kunt *classificaties* en *extractoren* toevoegen aan uw documentbegripmodellen om het volgende te doen: 

- Classificaties worden gebruikt om documenten die worden geüpload naar de documentbibliotheek te identificeren en classificeren. Een classificatie kan bijvoorbeeld worden ‘getraind’ om alle documenten met *contractverlengingen* te identificeren die naar de bibliotheek worden geüpload. Het inhoudstype contractverlenging wordt door u gedefinieerd wanneer u de classificatie maakt.

- Extractoren halen informatie uit deze documenten. Bijvoorbeeld: voor alle contractverlengingsdocumenten die in uw documentbibliotheek zijn geïdentificeerd, worden in uw weergave kolommen getoond met de *Servicestartdatum* en *Klant* voor elk contractverlengingsdocument. 

U kunt voorbeeldbestanden gebruiken om de classificaties en extractoren in uw model te trainen en te testen. Voorbeeldbestanden voorzien uw model van voorbeelden van waar ze naar moeten zoeken bij het identificeren en extraheren van gegevens uit bestanden. U kunt bijvoorbeeld uw contractverlengingsclassificaties en -extractoren trainen met voorbeelden van contractverlengingsdocumenten waar uw bedrijf mee werkt. U kunt voorbeeldbestanden ook gebruiken om de effectiviteit van uw model te testen.

Nadat u uw model hebt gepubliceerd, gebruikt u het inhoudscentrum om het toe te passen op een SharePoint-documentbibliotheek waartoe u toegang hebt.  

## <a name="file-limitations"></a>Bestandbeperkingen

Documentbegripmodellen gebruiken Optical Character Recognition- (OCR) technologie om pdf-bestanden, afbeeldingen en tiff-bestanden te scannen wanneer je een model traint met voorbeeldbestanden en wanneer je het model uitvoert op bestanden in een documentbibliotheek.

Houd rekening met de volgende verschillen voor tekstgebaseerde Microsoft Office-bestanden en OCR-gescande bestanden (PDF, afbeelding of TIFF):

- Office-bestanden: afgekapt op 64.000 tekens (tijdens training en wanneer uitgevoerd voor bestanden in een documentbibliotheek).

- OCR-gescande bestanden: er geldt een limiet van 20 pagina's.  

### <a name="requirements"></a>Vereisten

OCR-verwerking werkt het beste met documenten die aan de volgende vereisten voldoen:

- JPG-, PNG- of PDF-indeling (tekst of gescand) PDF-bestanden met ingesloten tekst werken beter omdat er geen fouten optreden voor tekenextractie en -locatie.

- Als uw PDF-bestanden met een wachtwoord zijn vergrendeld, moet u de vergrendeling verwijderen voordat u ze indient.

- De gecombineerde bestandsgrootte van de documenten die u gebruikt voor training per collectie, mag niet groter zijn dan 50 MB en PDF-documenten mogen maximaal 500 pagina's bevatten.

- De afmetingen van afbeeldingen moeten tussen 50 x 50 en 10000 x 10000 pixels liggen.
   > [!NOTE]
   > Afbeeldingen die erg breed zijn of bijzondere afmetingen hebben (bijvoorbeeld bouwtekeningen), worden mogelijk afgekapt tijdens het OCR-proces en worden mogelijk minder nauwkeurig.
 
- PDF-bestanden moeten maximaal 17 x 17 inch groot zijn, wat overeenkomt met de papierformaten Legal of A3 en kleiner.

- Scans op basis van papieren documenten moeten afbeeldingen van hoge kwaliteit zijn.

- Het Latijnse alfabet moeten worden gebruikt (Engelse tekens).

> [!NOTE]
> De volgende typen formuliergegevens worden momenteel niet ondersteund in AI Builder:<br>- Selectievakken of keuzerondjes<br>- Handtekeningen<br>- Invulbare PDF-bestanden

### <a name="supported-file-types"></a>Ondersteunde bestandstypen

Documentbegripmodellen ondersteunen de volgende typen:

- doc
- docx
- eml
- heic
- heif
- htm
- html
- jpeg
- jpg
- markdown
- md
- msg
- pdf
- png
- ppt
- pptx
- rtf
- tif
- tiff
- txt
- xls
- xlsx



## <a name="see-also"></a>Zie ook
[Een classificatie maken](create-a-classifier.md)

[Een extractor maken](create-an-extractor.md)

[Een inhoudscentrum maken](create-a-content-center.md)

[Een formulierverwerkingsmodel maken](create-a-form-processing-model.md)

[Een model toepassen](apply-a-model.md)   

[Het verschil tussen een documentbegripmodel en een formulierverwerkingsmodel](difference-between-document-understanding-and-form-processing-model.md)
  
[Overzicht formulierverwerking](form-processing-overview.md)

[SharePoint Syntex toegankheidsmodus](accessibility-mode.md)