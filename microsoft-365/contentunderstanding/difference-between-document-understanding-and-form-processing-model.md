---
title: Verschil tussen documentbegrip en formulierverwerkingsmodellen (Voorbeeld)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Beschrijft het belangrijkste verschil tussen documentbegrip en formulierverwerkingsmodellen.
ms.openlocfilehash: bceeb4b2f52ecf95aa0a23bf8970d1427088d877
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537150"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a>Verschil tussen documentbegrip en formulierverwerkingsmodellen (Voorbeeld)

> [!Note] 
> De inhoud in dit artikel is voor Project Cortex Private Preview. [Lees meer over Project Cortex](https://aka.ms/projectcortex).

Met inhoudsbegrip in Project Cortex u documenten identificeren en classificeren die naar SharePoint-documentbibliotheken worden geüpload en relevante informatie uit elk bestand extraheren.  Als bestanden bijvoorbeeld worden geüpload naar een SharePoint-documentbibliotheek, worden alle bestanden die als *inkooporders* zijn geïdentificeerd, als zodanig geclassificeerd en weergegeven in een aangepaste documentbibliotheekweergave waarin ze worden weergegeven. Daarnaast u specifieke informatie uit elk bestand ophalen (bijvoorbeeld *PO-nummer* en *Totaal)* en deze weergeven in een kolom in de documentbibliotheekweergave. 


Met het begrijpen van inhoud u *modellen* maken om de informatie die u nodig hebt te identificeren en te extraheren.  Er zijn twee soorten modellen die kunnen worden gebruikt:

- [Modellen voor documentinzicht](document-understanding-overview.md)
- [Formulierverwerkingsmodellen](form-processing-overview.md)

Hoewel beide modellen worden gebruikt voor over het algemeen hetzelfde doel, zijn er belangrijke verschillen die van invloed zijn op welke modellen u kiezen om te gebruiken.


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Gestructureerd versus ongestructureerde en semi-gestructureerde inhoud

Gebruik modellen voor documentbegrip om gegevens uit ongestructureerde documenten, zoals brieven of contracten, te identificeren en te extraheren, waarbij de tekstentiteiten die u wilt extraheren zich in zinnen of specifieke gebieden van het document bevinden. Een ongestructureerd document kan bijvoorbeeld een brief voor contractverlenging zijn die op verschillende manieren kan worden geschreven. Er is echter informatie die consistent in de hoofdtekst van elk contractverlengingsdocument zit, zoals de tekstreeks 'Begindatum van de service' gevolgd door een werkelijke datum.   

Gebruik formulierverwerkingsmodellen om bestanden te identificeren en gegevens uit gestructureerde of semi-gestructureerde documenten te extraheren, zoals formulieren of facturen, waarbij u duidelijke sleutelwaardeparen hebt (bijvoorbeeld *Datum: 10/1/2020*)* of tabelgegevens. Een goede kandidaat voor formulierverwerking zou bijvoorbeeld het aanvraagformulier van een bedrijf zijn waarin klanten hun informatie moeten verstrekken voor specifieke velden die zich in hetzelfde gebied van de documentindeling bevinden, zoals *Naam,* *Telefoonnummer,* *Totale kosten,* enz.  Een belastingformulier is een goed voorbeeld van een gestructureerd document. 

## <a name="where-they-are-created"></a>Waar ze worden gemaakt

Document understanding modellen worden gemaakt en beheerd in een SharePoint content center site. U moet toegang hebben tot een inhoudscentrumsite om een documentbegripmodel te maken of om een model toe te passen op een SharePoint-documentbibliotheek. 

Wanneer u een documentbegripmodel maakt, maakt u een nieuw [SharePoint-inhoudstype](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) dat is opgeslagen in de galerie SharePoint-inhoudstypen. U optioneel bestaande inhoudstypen gebruiken om uw model zo nodig te definiëren.

Formulierverwerkingsmodellen worden gemaakt in PowerApps [AI Builder,](https://docs.microsoft.com/ai-builder/overview)maar de creatie wordt rechtstreeks gestart vanuit een SharePoint-documentbibliotheek. Het maken van formulierverwerkingsmodellen moet worden ingeschakeld in uw documentbibliotheek, zodat een gebruiker er een formulierverwerkingsmodel voor kan maken, en een beheerder kan dit doen in de beheerdersinstellingen voor inhoudsbegrip. Formulierverwerkingsmodellen gebruiken PowerAutomate-stromen om bestanden te verwerken wanneer ze worden geüpload naar de documentbibliotheek.

Formulierverwerkingsmodellen maken ook nieuwe [SharePoint-inhoudstypen,](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)die ook worden opgeslagen in de galerie SharePoint-inhoudstypen.

## <a name="where-they-can-be-applied"></a>Waar ze kunnen worden toegepast

Modellen voor documentbegrip kunnen worden toegepast op verschillende SharePoint-documentbibliotheken waar toe u toegang hebt. U het inhoudscentrum gebruiken om niet alleen een documentbegripmodel te maken, maar ook om het toe te passen op verschillende documentbibliotheken. Het inhoudscentrum geeft een meer centrale controle over hoe documentbegripmodellen worden gebruikt en waar ze worden toegepast, omdat deze informatie moet worden uitgerold naar een inhoudscentrum.

Formulierverwerkingsmodellen kunnen momenteel alleen worden toegepast op de SharePoint-documentbibliotheek waaruit ze zijn gemaakt. Hierdoor kan elke gelicentieerde gebruiker die toegang heeft tot de site een formulierverwerkingsmodel maken.




 ## <a name="see-also"></a>Zie ook
[Training: Verbeter de bedrijfsprestaties met AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[Een classificatie maken](create-a-classifier.md)</br>
[Een afzuiger maken](create-an-extractor.md)</br>
[Een documentbegripmodel toepassen](apply-a-model.md)</br>
[Een formulierverwerkingsmodel maken](create-a-form-processing-model.md)</br>



  
  



