---
title: Het verschil tussen documentbegripmodellen en formulierverwerkingsmodellen
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Uitleg over het verschil tussen documentbegripmodellen en formulierverwerkingsmodellen
ms.openlocfilehash: e847ed9b7a00e0ff0542ad3b9ba35c314070837d
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087629"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>Het verschil tussen documentbegripmodellen en formulierverwerkingsmodellen 


Met documentbegrip in Microsoft SharePoint Syntex kunt u documenten identificeren en classificeren die worden geüpload naar SharePoint-documentbibliotheken en kunt u relevante informatie uit de bestanden halen.  Als bestanden bijvoorbeeld worden geüpload naar een SharePoint-documentbibliotheek, worden alle bestanden die worden geïdentificeerd als *inkooporders* als zodanig geclassificeerd en vervolgens weergegeven in een aangepaste weergave van een documentbibliotheek. Bovendien kunt u specifieke informatie uit elk bestand halen (zoals *PO-nummer* en *Totaal*) en die weergeven als een kolom in de documentbibliotheekweergave. 

Met inhoudsbegrip kunt u *modellen* maken om de informatie die u nodig hebt te identificeren en extraheren. Met modellen kunnen helpen op allerlei zakelijke gebieden, zoals zoekopdrachten, bedrijfsprocessen, compliance en vele andere.

Er zijn twee modeltypen die u kunt gebruiken:

- [Documentbegripmodellen](document-understanding-overview.md)
- [Formulierverwerkingsmodellen](form-processing-overview.md)

Beide modellen worden in het algemeen gebruikt voor dezelfde doeleinden, maar de hieronder vermelde verschillen bepalen welke je kunt gebruiken.

> [!NOTE]
> Zie [Ingebruikname van SharePoint Syntex: introductiehandleiding](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) voor meer informatie over formulierverwerking scenariovoorbeelden voor documentbegrip.


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Gestructureerde versus niet-gestructureerde en gedeeltelijk gestructureerde inhoud

Gebruik documentbegripmodellen om gegevens te identificeren en extraheren uit niet-gestructureerde documenten, zoals brieven of contracten, waarin de tekstentiteiten die u wilt extraheren zich in zinnen of specifieke delen van het document bevinden. Een niet-gestructureerd document kan bijvoorbeeld een brief zijn voor het verlengen van een contract, die op verschillende manieren kan zijn geschreven. Maar bepaalde informatie bevindt zich altijd in de hoofdtekst van een contractverlengingsdocument, zoals de tekenreeks *Begindatum van de service* gevolgd door een werkelijke datum.   

Gebruik formulierverwerkingsmodellen om bestanden te identificeren en gegevens te extraheren uit gestructureerde of half-gestructureerde documenten, zoals formulieren of facturen. Formulierverwerkingsmodellen worden met voorbeelddocumenten getraind om de indeling van uw formulieren te begrijpen, en om te zoeken naar de gegevens die u wilt ophalen van soortgelijke locaties, aangezien formulieren een meer gestructureerde indeling hebben en entiteiten zich op dezelfde locatie bevinden (zoals een BSN-nummer in een belastingformulier). 

> [!NOTE]
> U moet toegang hebben tot een inhoudscentrumsite om een documentbegripmodel te maken of toe te passen op een SharePoint-documentbibliotheek. 


## <a name="where-they-are-created"></a>Waar worden ze gemaakt

Documentbegripmodellen worden gemaakt en beheerd in een SharePoint-inhoudscentrumsite. 

> [!NOTE]
> Zie voor meer informatie over invoerdocumenten [Vereisten voor en beperkingen van formulierverwerkingsmodellen](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

Formulierverwerkingsmodellen worden gemaakt in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), maar het maken van de modellen wordt rechtstreeks vanuit een SharePoint-documentbibliotheek gestart. Het maken van formulierverwerkingsmodellen moet worden ingeschakeld in uw documentbibliotheek om het gebruikers mogelijk te maken een formulierverwerkingsmodel te maken. Een beheerder kan dit doen in de beheerdersinstellingen voor inhoudsbegrip. Formulierverwerkingsmodellen gebruiken Power Automate-stromen om bestanden te verwerken wanneer die worden geüpload naar de documentbibliotheek.

Wanneer u een documentbegripmodel maakt, maakt u een nieuw [SharePoint-inhoudstype](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) dat wordt opgeslagen in de SharePoint-inhoudstypengalerie. U kunt ook bestaande inhoudstypen gebruiken om het model te definiëren.

Formulierverwerkingsmodellen maken ook nieuwe [SharePoint-inhoudstypen](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)en worden ook opgeslagen in de SharePoint-inhoudstypegalerie.

## <a name="where-they-can-be-applied"></a>Waar kunnen ze worden toegepast

U kunt documentbegripmodellen toepassen op SharePoint-documentbibliotheken waartoe u toegang hebt. Gebruik het inhoudscentrum om een documentbegripmodel te maken en toe te passen op verschillende documentbibliotheken. Het inhoudscentrum biedt u een centrale manier om te beheren hoe documenten worden gebruikt en waar ze worden toegepast. Houd er rekening mee dat deze informatie moet ook worden doorgegeven naar een inhoudscentrum.

Formulierverwerkingsmodellen kunnen momenteel alleen worden toegepast op de SharePoint-documentbibliotheek waarin u ze hebt gemaakt. Hierdoor krijgen gebruikers met een licentie toegang tot de site om een formulierverwerkingsmodel te maken. De beheerder moet de formulierverwerking inschakelen voor een SharePoint-documentbibliotheek, zodat deze functie beschikbaar is voor gebruikers met een licentie.

 ## <a name="see-also"></a>Zie ook
[Training: zakelijke prestaties verbeteren met AI-Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)



[Overzicht van documentbegrip](document-understanding-overview.md)

[Overzicht formulierverwerking](form-processing-overview.md)

[Kennismaken met SharePoint Syntex](index.md)
