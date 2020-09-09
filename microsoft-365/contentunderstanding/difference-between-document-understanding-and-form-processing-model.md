---
title: Verschil tussen document begrijpt en formulier verwerkings modellen (preview)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: In dit artikel wordt het verschil beschreven tussen document begrijpt en formulier verwerkings modellen.
ms.openlocfilehash: 972fa9e8446a44f6220baa7cde3f484172c50da6
ms.sourcegitcommit: 57b37a3ce40f205c7320d5be1a0d906dd492b863
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405615"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a>Verschil tussen document begrijpt en formulier verwerkings modellen (preview)

> [!Note] 
> De inhoud in dit artikel is bedoeld voor project cortex private preview. [Lees meer over project cortex](https://aka.ms/projectcortex).

Met inhoud begrijpen in Project cortex kunt u documenten identificeren en classificeren die worden geüpload naar SharePoint-documentbibliotheken, en relevante informatie uit elk bestand ophalen.  Wanneer bestanden worden geüpload naar een SharePoint-documentbibliotheek, worden alle bestanden die zijn geïdentificeerd als *aankoop orders* , geclassificeerd en weergegeven in de aangepaste weergave van een documentbibliotheek waarin ze worden weergegeven. Daarnaast kunt u specifieke informatie uit elk bestand (bijvoorbeeld *ko-nummer* en *totaal*) optrekken en dit weergeven in een kolom in de weergave van de documentbibliotheek. 


Met inhoud kunt u *modellen* maken waarmee de benodigde gegevens worden geïdentificeerd en uitgepakt.  Er zijn twee soorten modellen die kunnen worden gebruikt:

- [Documenten begrijpen met modellen](document-understanding-overview.md)
- [Formulier verwerkings modellen](form-processing-overview.md)

Hoewel beide modellen voor algemeen dezelfde doeleinden worden gebruikt, is er sprake van belangrijke verschillen die van invloed zijn op de manier waarop u kunt kiezen.


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Gestructureerd versus niet-gestructureerd en gedeeltelijk gestructureerde inhoud

U kunt documenten gebruiken om gegevens te identificeren en te extraheren uit niet-gestructureerde documenten, zoals brieven of contracten, waarbij de tekst entiteiten die u wilt extraheren, zich bevinden in zinnen of bepaalde gebieden van het document. Een niet-gestructureerd document kan bijvoorbeeld een brief voor het verlengen van een contract zijn dat op verschillende manieren kan worden geschreven. Er is echter informatie die consistent is in de hoofdtekst van het document voor het verlengen van contracten, zoals de tekenreeks ' service begindatum ', gevolgd door een werkelijke datum.   

Gebruik formulier verwerkings modellen om bestanden te identificeren en gegevens te extraheren uit gestructureerd of gedeeltelijk gestructureerde documenten, zoals formulieren of facturen, waar u paren met sleutelwaarden hebt uitgeschakeld (bijvoorbeeld *datum: 10/1/2020*) * of tabelgegevens. Voorbeeld: een goede kandidaat voor het verwerken van een formulier is een aanvraagformulier voor de order van een bedrijf waarin clients hun gegevens moeten verschaffen voor specifieke velden die zich in hetzelfde gebied van de documentindeling bevinden, zoals *naam*, *telefoonnummer*, *totale kosten*, etc.  Een belasting formulier is een goed voorbeeld van een gestructureerd document. 

## <a name="where-they-are-created"></a>Waar ze worden gemaakt

Document leren hoe modellen worden gemaakt en beheerd op een SharePoint-inhouds centrum site. U moet toegang hebben tot een inhouds centrum site om een document te leren maken met model of om een document toe te passen op een SharePoint-documentbibliotheek. 

Wanneer u een document maakt wat het model is, maakt u een nieuw [SharePoint-inhoudstype](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) dat is opgeslagen in de galerie met SharePoint-inhoudstypen. U kunt eventueel bestaande inhoudstypen gebruiken om zo nodig uw model te definiëren.

Formulier verwerkings modellen worden gemaakt in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), maar het maken van een SharePoint-documentbibliotheek wordt direct geïnitieerd. Het maken van een model voor formulierverwerking moet zijn ingeschakeld in de documentbibliotheek om een gebruiker hiervoor een formulier verwerkings model te kunnen maken, en een beheerder kan dit doen met de inhoud van de beheerdersinstellingen. Formulier verwerkings modellen gebruiken PowerAutomate-stromen om bestanden te verwerken wanneer ze worden geüpload naar de documentbibliotheek.

Voor formulier verwerkings modellen worden ook nieuwe [SharePoint-inhoudstypen](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)gemaakt, die ook zijn opgeslagen in de galerie met SharePoint-inhoudstypen.

## <a name="where-they-can-be-applied"></a>Waar ze kunnen worden toegepast

Document wat betekent dat modellen kunnen worden toegepast op verschillende SharePoint-documentbibliotheken waartoe u toegang hebt. U kunt het inhouds centrum gebruiken om niet alleen een document te leren maken dat niet wordt gebruikt, maar ook om dit toe te passen op verschillende documentbibliotheken. Het inhouds centrum biedt een meer centrale controle over hoe documenten worden gebruikt en waar ze worden toegepast, aangezien deze informatie moet worden opgedeeld in een inhouds centrum.

Formulier verwerkings modellen kunnen op dit moment alleen worden toegepast op de SharePoint-documentbibliotheek van waaraf ze zijn gemaakt. Hiermee kan een gelicentieerde gebruiker die toegang heeft tot de site, een formulier verwerkings model maken.




 ## <a name="see-also"></a>Zie ook
[Training: bedrijfsprestaties verbeteren met AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[Een classificatie maken](create-a-classifier.md)</br>
[Een extractor maken](create-an-extractor.md)</br>
[Een document met inzicht toepassen](apply-a-model.md)</br>
[Een formulier verwerkings model maken](create-a-form-processing-model.md)</br>



  
  



