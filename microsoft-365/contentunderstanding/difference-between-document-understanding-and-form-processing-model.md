---
title: Het verschil tussen documentbegripmodellen en formulierverwerkingsmodellen
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Uitleg over het verschil tussen documentbegripmodellen en formulierverwerkingsmodellen
ms.openlocfilehash: 9640b028e4b5a9cbd914b183e61de9b8a7ba00bc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905788"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>Het verschil tussen documentbegripmodellen en formulierverwerkingsmodellen 


Met documentbegrip in Microsoft SharePoint Syntex kunt u documenten identificeren en classificeren die worden geüpload naar SharePoint-documentbibliotheken en kunt u relevante informatie uit de bestanden halen.  Als bestanden bijvoorbeeld worden geüpload naar een SharePoint-documentbibliotheek, worden alle bestanden die worden geïdentificeerd als *inkooporders* als zodanig geclassificeerd en vervolgens weergegeven in een aangepaste weergave van een documentbibliotheek. Bovendien kunt u specifieke informatie uit elk bestand halen (zoals *PO-nummer* en *Totaal*) en die weergeven als een kolom in de documentbibliotheekweergave. 

Met inhoudsbegrip kunt u *modellen* maken om de informatie die u nodig hebt te identificeren en extraheren. Met modellen kunnen helpen op allerlei zakelijke gebieden, zoals zoekopdrachten, bedrijfsprocessen, compliance en vele andere.

Er zijn twee modeltypen die u kunt gebruiken:

- [Documentbegripmodellen](document-understanding-overview.md)
- [Formulierverwerkingsmodellen](form-processing-overview.md)

Beide modellen worden in het algemeen gebruikt voor dezelfde doeleinden, maar de hieronder vermelde verschillen bepalen welke je kunt gebruiken.

> [!NOTE]
> Zie [Ingebruikname van SharePoint Syntex: introductiehandleiding](./adoption-getstarted.md#form-processing-scenario-example) voor meer informatie over formulierverwerking scenariovoorbeelden voor documentbegrip.


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Gestructureerde versus niet-gestructureerde en gedeeltelijk gestructureerde inhoud

Gebruik documentbegripmodellen om gegevens te identificeren en extraheren uit niet-gestructureerde documenten, zoals brieven of contracten, waarin de tekstentiteiten die u wilt extraheren zich in zinnen of specifieke delen van het document bevinden. Een niet-gestructureerd document kan bijvoorbeeld een brief zijn voor het verlengen van een contract, die op verschillende manieren kan zijn geschreven. Maar bepaalde informatie bevindt zich altijd in de hoofdtekst van een contractverlengingsdocument, zoals de tekenreeks *Begindatum van de service* gevolgd door een werkelijke datum.

Gebruik formulierverwerkingsmodellen om bestanden te identificeren en gegevens te extraheren uit gestructureerde of half-gestructureerde documenten, zoals formulieren of facturen. Formulierverwerkingsmodellen worden met voorbeelddocumenten getraind om de indeling van uw formulieren te begrijpen, en om te zoeken naar de gegevens die u wilt ophalen van soortgelijke locaties. Formulieren hebben meestal een meer gestructureerde indeling waarbij entiteiten zich op dezelfde locatie bevinden (bijvoorbeeld een bsn-nummer in een belastingformulier).

> [!NOTE]
> U moet toegang hebben tot een inhoudscentrumsite om een documentbegripmodel te maken of toe te passen op een SharePoint-documentbibliotheek. 


## <a name="where-models-are-created"></a>Waar modellen worden gemaakt

Documentbegripmodellen worden gemaakt en beheerd in een SharePoint-inhoudscentrumsite. 

> [!NOTE]
> Zie voor meer informatie over invoerdocumenten [Vereisten voor en beperkingen van formulierverwerkingsmodellen](/ai-builder/form-processing-model-requirements). 

Formulierverwerkingsmodellen worden gemaakt in PowerApps [AI Builder](/ai-builder/overview), maar het maken van de modellen wordt rechtstreeks vanuit een SharePoint-documentbibliotheek gestart. Voor een documentbibliotheek moet het maken van formulierverwerkingsmodellen zijn ingeschakeld om te zorgen dat gebruikers er een formulierverwerkingsmodel voor kunnen maken. Beheerders kunnen het maken van een formulierverwerkingsmodel inschakelen in de beheerinstellingen voor inhoudsbegrip. Formulierverwerkingsmodellen gebruiken Power Automate-stromen om bestanden te verwerken wanneer die worden geüpload naar de documentbibliotheek.

Wanneer u een documentbegripmodel maakt, maakt u een nieuw [SharePoint-inhoudstype](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) dat wordt opgeslagen in de SharePoint-inhoudstypengalerie. U kunt ook bestaande inhoudstypen gebruiken om het model te definiëren.

Formulierverwerkingsmodellen maken ook nieuwe [SharePoint-inhoudstypen](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)en worden ook opgeslagen in de SharePoint-inhoudstypegalerie.

## <a name="where-they-can-be-applied"></a>Waar kunnen ze worden toegepast

U kunt documentbegripmodellen toepassen op SharePoint-documentbibliotheken waartoe u toegang hebt. Gebruik het inhoudscentrum om een documentbegripmodel te maken en toe te passen op verschillende documentbibliotheken. Het inhoudscentrum biedt u een centrale manier om te beheren hoe documenten worden gebruikt en waar ze worden toegepast. Houd er rekening mee dat deze informatie moet ook worden doorgegeven naar een inhoudscentrum.

Formulierverwerkingsmodellen kunnen momenteel alleen worden toegepast op de SharePoint-documentbibliotheek waarin u ze hebt gemaakt. Hierdoor krijgen gebruikers met een licentie toegang tot de site om een formulierverwerkingsmodel te maken. De beheerder moet de formulierverwerking inschakelen voor een SharePoint-documentbibliotheek, zodat deze functie beschikbaar is voor gebruikers met een licentie.

## <a name="comparison-of-forms-processing-and-document-understanding"></a>Vergelijking van formulierverwerking en documentbegrip

Gebruik de volgende tabel als u wilt weten wanneer u formulierverwerking moet gebruiken en wanneer u documentbegrip moet gebruiken:

| Functie | Formulierverwerking | Documentbegrip |
| ------- | ------- | ------- |
| Modeltype: wanneer gebruikt u welk type | Wordt gebruikt voor niet-gestructureerde bestandsindelingen, zoals pdf-bestanden voor formulierinhoud, zoals facturen of inkooporders met een vergelijkbare indeling en opmaak.  | Wordt gebruikt voor gedeeltelijk gestructureerde bestandsindelingen, bijvoorbeeld Office-documenten met verschillen in de indeling, maar waaruit nog steeds vergelijkbare informatie moet worden geëxtraheerd. |
| Het maken van het model | Het model wordt in AI Builder gemaakt met naadloze toegang vanuit de SharePoint-documentbibliotheek.| Model is gemaakt in SharePoint op een nieuwe site, het inhoudscentrum. |
| Classificatietype| Instelbare classificatie wordt gebruikt om het systeem aanwijzingen te geven over welke gegevens er moeten worden geëxtraheerd.| Te trainen classificatie met optionele extractoren die machinaal leren gebruiken om de documentlocatie toe te wijzen over te extraheren gegevens.|
| Locaties | Getraind voor één documentbibliotheek.| Kan worden toegepast op meerdere bibliotheken.|
| Ondersteunde bestandstypen| Trainen op pdf-, JPG-, PNG-indeling, totaal 50 MB en 500 pagina's.| Trainen op 5 tot 10 pdf-, Office- of e-mailbestanden, inclusief negatieve voorbeelden.<br>Office-bestanden worden afgekapt bij 64.000 tekens. Gescande OCR-bestanden zijn beperkt tot 20 pagina's.|
| Integreren met beheerde metagegevens | Nee | Ja, door de entiteitsextractor te trainen om te verwijzen naar een geconfigureerd veld met beheerde metagegevens.|
| Integratie van compliancefunctie wanneer Microsoft-gegevensbescherming is ingeschakeld | Gepubliceerde labels voor retentie instellen.<br>Gevoeligheidslabels instellen komt nog. | Gepubliceerde labels voor retentie instellen.<br>Gevoeligheidslabels instellen komt nog. |
| Ondersteunde regio's| Formulierverwerking is afhankelijk van Power Platform. Raadpleeg voor meer informatie over wereldwijde beschikbaarheid van Power Platform en AI Builder [Beschikbaarheid van Power Platform](https://dynamics.microsoft.com/geographic-availability/). | Beschikbaar in alle regio's.|
| Transactiekosten | Maakt gebruik van AI Builder-credits.<br>Tegoeden zijn te koop in partijen van 1 miljoen.<br>1 miljoen credits zijn inbegrepen wanneer u meer dan 300 SharePoint Syntex-licenties aanschaft.<br>Met 1 miljoen credits kunnen 2.000 bestandspagina's worden verwerkt.<br>| N.v.t. |
| Capaciteit | Gebruikt de standaard omgeving van Power-platform (aangepaste omgevingen waarin de Dataverse database wordt ondersteund). | Heeft geen capaciteitsbeperkingen.|
| Ondersteunde talen| Engels <br>Later beschikbaar in 2021: Talen met Latijns alfabet | Modellen werken met alle talen met het Latijnse alfabet. Behalve Engels: Duits, Zweeds, Frans, Spaans, Italiaans en Portugees.|

## <a name="see-also"></a>Zie ook
[Training: zakelijke prestaties verbeteren met AI-Builder](/learn/paths/improve-business-performance-ai-builder/?source=learn)



[Overzicht van documentbegrip](document-understanding-overview.md)

[Overzicht formulierverwerking](form-processing-overview.md)

[Kennismaken met SharePoint Syntex](index.md)