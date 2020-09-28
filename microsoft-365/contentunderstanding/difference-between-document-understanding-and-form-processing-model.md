---
title: Het verschil tussen document begrijpt en formulier verwerkings modellen
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Beschrijving van het verschil tussen document begrijpt en modellen voor formulierverwerking
ms.openlocfilehash: 268a2fa4a0381e5822c17e5df22566c931d37f3c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294746"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>Het verschil tussen document begrijpt en formulier verwerkings modellen 

De inhoud in dit artikel is bedoeld voor de cortex van de private preview van project. [Lees meer over project cortex](https://aka.ms/projectcortex).

Met inhoud begrijpen in Project cortex kunt u documenten identificeren en classificeren die worden geüpload naar SharePoint-documentbibliotheken, en relevante informatie uit elk bestand ophalen.  Wanneer bestanden worden geüpload naar een SharePoint-documentbibliotheek, worden alle bestanden die zijn geïdentificeerd als *aankoop orders* , ingedeeld in een aangepaste weergave van de documentbibliotheek. Daarnaast kunt u specifieke informatie uit elk bestand (bijvoorbeeld *ko-nummer* en *totaal*) optrekken en dit weergeven als een kolom in de weergave van de documentbibliotheek. 

Met inhoud kunt u *modellen* maken waarmee de benodigde gegevens worden geïdentificeerd en uitgepakt. Dit zijn twee modeltypen die u kunt gebruiken:

- [Documenten begrijpen met modellen](document-understanding-overview.md)
- [Formulier verwerkings modellen](form-processing-overview.md)

Hoewel beide modellen meestal voor hetzelfde doel worden gebruikt, zijn de hierboven vermelde belangrijkste verschillen van invloed op welke modellen u kunt gebruiken.

## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Gestructureerd versus niet-gestructureerd en gedeeltelijk gestructureerde inhoud

U kunt documenten gebruiken om gegevens te identificeren en te extraheren uit niet-gestructureerde documenten, zoals brieven of contracten, waarbij de tekst entiteiten die u wilt extraheren, zich bevinden in zinnen of bepaalde gebieden van het document. Een niet-gestructureerd document kan bijvoorbeeld een brief voor het verlengen van een contract zijn dat op verschillende manieren kan worden geschreven. Informatie is echter consistent in de hoofdtekst van het document voor het verlengen van contracten, zoals de tekenreeks ' service StartDate ', gevolgd door een werkelijke datum.   

Gebruik formulier verwerkings modellen om bestanden te identificeren en gegevens te extraheren uit gestructureerde of gedeeltelijk gestructureerde documenten, zoals formulieren of facturen. Deze documenten moeten Clear key-value-paren hebben, zoals *datum: 10/1/2020*) * of tabelgegevens. Voorbeeld: een goede kandidaat voor het verwerken van formulieren is een aanvraagformulier voor de bestellingen van een bedrijf dat clients informatie moeten geven over bepaalde velden in hetzelfde gebied van de documentindeling, zoals de *naam*, het *telefoonnummer*, de *totale kosten*, etc.  Een belasting formulier is een goed voorbeeld van een gestructureerd document. 

## <a name="where-they-are-created"></a>Waar ze worden gemaakt

Document leren hoe modellen worden gemaakt en beheerd op een SharePoint-inhouds centrum site. 

> [!NOTE]
> U moet toegang hebben tot een inhouds centrum site om een document te leren maken met model of om een document toe te passen op een SharePoint-documentbibliotheek. 

Formulier verwerkings modellen worden gemaakt in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), maar het maken van een SharePoint-documentbibliotheek wordt direct geïnitieerd. Het maken van een model voor formulierverwerking moet zijn ingeschakeld in de documentbibliotheek om een gebruiker hiervoor een formulier verwerkings model te kunnen maken, en een beheerder kan dit doen met de inhoud van de beheerdersinstellingen. Formulier verwerkings modellen gebruiken PowerAutomate-stromen om bestanden te verwerken wanneer ze worden geüpload naar de documentbibliotheek.

Wanneer u een document maakt wat het model is, maakt u een nieuw [SharePoint-inhoudstype](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) dat is opgeslagen in de galerie met SharePoint-inhoudstypen. U kunt ook bestaande inhoudstypen gebruiken om uw model te definiëren, indien nodig.

Formulier verwerkings modellen worden gemaakt in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), maar het maken van een SharePoint-document bibliotheek wordt direct geïnitieerd. Het maken van een formulier model moet worden ingeschakeld voor de documentbibliotheek zodat een gebruiker een formulier voor een formulier verwerkings model kan maken. Of een beheerder kan dit doen met de inhoud van de beheerdersinstellingen. Formulier verwerkings modellen gebruiken PowerAutomate-stromen om bestanden te verwerken wanneer ze worden geüpload naar de documentbibliotheek.

Formulier verwerkings modellen maken ook nieuwe [SharePoint-inhoudstypen](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)en worden ook opgeslagen in de galerie met SharePoint-inhoudstypen.

## <a name="where-they-can-be-applied"></a>Waar ze kunnen worden toegepast

U kunt documenten met modellen aan documentbibliotheken van SharePoint gebruiken waartoe u toegang hebt. U kunt het inhouds centrum gebruiken om een document te leren maken en het model toe te passen op verschillende documentbibliotheken. In het inhouds centrum krijgt u een meer centrale controle over hoe documenten worden gebruikt en waar ze worden toegepast. Opmerking Deze informatie moet ook samen met een inhouds centrum worden samengevouwen.

Formulier verwerkings modellen kunnen op dit moment alleen worden toegepast op de SharePoint-documentbibliotheek waaruit u deze hebt gemaakt. Dit betekent dat gebruikers met een licentie toegang hebben tot de site, een formulier verwerkings model kunnen maken.

 ## <a name="see-also"></a>Zie ook
[Training: bedrijfsprestaties verbeteren met AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[Een classificatie maken](create-a-classifier.md)</br>
[Een extractor maken](create-an-extractor.md)</br>
[Een document met inzicht toepassen](apply-a-model.md)</br>
[Een formulier verwerkings model maken](create-a-form-processing-model.md)</br>
