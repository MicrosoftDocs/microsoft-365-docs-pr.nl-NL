---
title: Taxonomieën voor het maken van een extractie met een termenarchief
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: De taxonomie termenarchief maken bij het maken van een extractor in uw document met een model in Microsoft SharePoint Syntex.
ms.openlocfilehash: 94f7a0389d2f06e0f8c1a60a341a02e43dfb2071
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295862"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a>Taxonomieën voor het maken van een extractie met een termenarchief


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Wanneer u in uw document een Extractor maakt die het model van SharePoint Syntex, kunt u profiteren van de beheerde termenarchief met [metagegevens Services](https://docs.microsoft.com/sharepoint/managed-metadata#terms) om de voorwaarden weer te geven voor gegevens die u extra uitpakt.  

In het model worden alle **contract** documenten die worden geüpload naar de documentbibliotheek herkend en geclassificeerd.  Daarnaast wordt in het model ook een service waarde voor de **contracten** van elk contract opgehaald en wordt deze weergegeven in een kolom in de weergave van de bibliotheek. Onder de verschillende contract service waarden in de contracten zijn er verschillende oudere waarden die uw bedrijf niet langer gebruikt en waarvan de naam is gewijzigd. Alle verwijzingen naar het *ontwerp*, de *grafische*of de *topografieal* contractservice van de voorwaarden, worden voortaan *creatief*genoemd. Wanneer uw model een van de verouderde voorwaarden uit een contract document ophaalt, zoekt u in uw bibliotheek weergave de actuele term: advertentie. In het onderstaande voorbeeld ziet u in het model training het model dat één voorbeelddocument de verouderde term *ontwerpt*.

   ![Termenarchief](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a>Synoniemen voor termensets 

Termensets worden geconfigureerd in het termenarchief beheerde metagegevens Services in het SharePoint-Beheercentrum. In het onderstaande voorbeeld is de [termenset](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) *contract service* geconfigureerd met een aantal voorwaarden, waaronder *advertenties*.  De gegevens in het voorbeeld laten zien dat de term drie synoniemen (*ontwerp*, *grafisch*en *topografie*) bevat en dat de synoniemen moeten worden omgezet in *creatief*.

   ![Termenset](../media/content-understanding/term-store.png)</br>

<Mike, dit is waar ik niet weet hoe dit moet worden beschreven.  Met welke actie wordt het model aangegeven dat wanneer ik een Extractor maak voor het extraheren en weergeven van een kolom voor contract services, wat betekent dat de kolom ' gemarkeerd ' voor het gebruik van de termenset beheerde metagegevens voor Creative Services? >

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a>De kolom met de documentbibliotheek site configureren voor een beheerd metagegevensveld


   ![Beheerde metagegevens maken](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a>Zie ook
[Inleiding in beheerde metagegevens](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[Een extractor maken](create-an-extractor.md)</br>
[Een kolom met beheerde metagegevens maken](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





