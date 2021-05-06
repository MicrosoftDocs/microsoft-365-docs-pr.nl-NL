---
title: Een classificatie opnieuw trainen voor de inhoudsverkenner
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Meer informatie over het geven van feedback aan een trainbare classificatie in Inhoudsverkenner.
ms.openlocfilehash: d61437634dcad7f01a6737947b0f32f42de2818e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161914"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a>Een classificatie opnieuw trainen voor de inhoudsverkenner

Een Microsoft 365 trainable classifier is een hulpmiddel dat u kunt trainen om verschillende soorten inhoud te herkennen door deze voorbeelden te geven om naar te kijken. Nadat u bent opgeleid, kunt u het gebruiken om het item te identificeren voor de toepassing van Office gevoeligheidslabels, compliancebeleid voor communicatie en bewaarlabelbeleid.

In dit artikel wordt beschreven hoe u de prestaties van aangepaste, trainbare classificaties en sommige vooraf getrainde classificaties kunt verbeteren door hen extra feedback te geven.

Zie Meer informatie over leerbare classificaties voor meer informatie over de verschillende typen [classificaties.](classifier-learn-about.md)

Bekijk deze video voor een beknopt overzicht van het afstemmen en omscholingsproces. U moet dit volledige artikel nog steeds lezen voor meer informatie.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGMs]


## <a name="permissions"></a>Machtigingen

Toegang tot classificaties in het Microsoft 365 compliancecentrum:

- de rol van compliancebeheerder of compliancegegevensbeheerder is vereist om een classificatie te trainen

U hebt accounts met deze machtigingen nodig om classificaties in deze scenario's te kunnen gebruiken:

- Scenario bewaarlabelbeleid: rollen recordbeheer en bewaarbeheer 

## <a name="overall-workflow"></a>Algemene werkstroom

> [!IMPORTANT]
> U geeft feedback in inhoudsverkenner voor het automatisch toepassen van bewaarlabelbeleid op Exchange items en gebruikt de classificatie als voorwaarde. **Als u geen bewaarbeleid hebt dat automatisch een bewaarlabel op items Exchange en een classificatie als voorwaarde gebruikt, stopt u hier.**

Als u uw classificaties gebruikt, kunt u de nauwkeurigheid van de classificaties die ze maken, vergroten. U doet dit door de kwaliteit te evalueren van de classificaties die zijn gemaakt voor items die zijn geïdentificeerd als een overeenkomst of geen overeenkomst. Nadat u 30 evaluaties voor een classificatie hebt gemaakt, is die feedback nodig en wordt deze automatisch opnieuw opgeleid.

Zie Processtroom voor het opnieuw bijscholen van een classificatie voor meer informatie over de algehele werkstroom voor het opnieuw bijscholen van een [classificatie.](classifier-learn-about.md#retraining-classifiers)

> [!NOTE]
> Een classificatie moet al zijn gepubliceerd en in gebruik zijn voordat deze opnieuw kan worden opgeleid.

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a>Een classificatie opnieuw trainen voor de inhoudsverkenner

1. Meld u aan bij Microsoft 365 compliancecentrum met roltoegang voor compliancebeheerders of beveiligingsbeheerders en open Microsoft 365 **compliancecentrum**  >  **Gegevensclassificatie**  >  **Inhoudverkenner.** 
2. Vouw **trainbare classificaties** uit onder de lijst Filter op labels, infotypen of **categorieën.**

> [!IMPORTANT]
> Het kan maximaal acht dagen duren voordat samengevoegde items worden weergegeven onder de kop met trainbare classificaties.

3. Kies de trainbare classificatie die u hebt gebruikt in het beleid voor het automatisch toepassen van bewaarlabels. Dit is de trainbare classificatie waar u feedback over geeft.

> [!NOTE]
> Als een item een vermelding heeft in de kolom **Bewaarlabel,** betekent dit dat het item is geclassificeerd als `match` een .  Als een item geen vermelding heeft  in de kolom Bewaarlabel, betekent dit dat het is geclassificeerd als `close match` een . U kunt de precisie van de classificatie het meest verbeteren door feedback te geven over `close match` items. 

4. Kies een item en open het.
 
 > [!TIP]
> U kunt feedback geven over meerdere items tegelijk door ze allemaal te kiezen en vervolgens Classificatie **verbeteren** op de opdrachtbalk te kiezen.

5. Kies **Feedback geven.**
6. Als het **item een echt positief** item is, kiest u in het deelvenster Gedetailleerde feedback de optie **Overeenkomen.**  Als het item een onwaar positief item is, dat wil zeggen dat het ten onrechte is opgenomen in de categorie, kiest u **Geen overeenkomst.**
7. Als er een andere classificatie is die geschikter is voor het item, kunt u dit kiezen in de lijst Andere **trainbare classificaties** voorstellen. Hiermee wordt de andere classifier triggerd om het item te evalueren.
8. Kies **Feedback verzenden** om uw evaluatie van de classificaties te verzenden en andere `match` `not a match` trainbare classificaties voor te stellen. Wanneer u 30 exemplaren van feedback hebt gegeven aan een classificatie, wordt deze automatisch opnieuw opgeleid. Omscholing kan één tot vier uur duren. Classificaties kunnen slechts twee keer per dag opnieuw worden opgeleid.

> [!IMPORTANT]
> Deze informatie gaat naar de classificatie in uw tenant, **deze gaat niet terug naar Microsoft.**

9. Open **Trainable classifiers**.
10. De classificatie die is gebruikt in het compliancebeleid voor communicatie wordt weergegeven onder de **kop Opnieuw trainen.**

![classifier in omscholingsstatus](../media/classifier-retraining.png)

11. Nadat de omscholing is voltooid, kiest u de classificatie om het overzicht van de omscholing te openen.

![Overzicht van omscholingsresultaten van classifier](../media/classifier-retraining-overview.png)

12. Bekijk de aanbevolen actie en de voorspellingsvergelijkingen van de opnieuw getrainde en momenteel gepubliceerde versies van de classificatie.
13. Als u tevreden bent over de resultaten van de omscholing, kiest u **Opnieuw publiceren.**
14. Als u niet tevreden bent over de resultaten van de omscholing, kunt u ervoor kiezen om extra feedback te geven aan de classificatie in de compliance-interface Communicatie en een andere herscholingscyclus te starten of niets te doen in welk geval de momenteel gepubliceerde versie van de classificatie blijft worden gebruikt. 

## <a name="details-on-republishing-recommendations"></a>Details over het opnieuw publiceren van aanbevelingen

Hier vindt u wat informatie over de manier waarop we de aanbeveling formuleren om een omscholingsclassifier opnieuw te publiceren of om verdere omscholing voor te stellen. Dit vereist een beetje meer inzicht in de manier waarop trainbare classificaties werken.

Na een nieuwe training evalueren we de prestaties van de classificatie op zowel de items met feedback als alle items die oorspronkelijk zijn gebruikt om de classificatie te trainen. 

- Voor ingebouwde modellen zijn items die worden gebruikt om de classificatie te trainen de items die door Microsoft worden gebruikt om het model te maken.
- Voor aangepaste modellen zijn items die in de oorspronkelijke training worden gebruikt, afkomstig van de sites die u hebt toegevoegd voor testen en controleren.

We vergelijken de prestatienummers voor beide sets items voor de opnieuw omgeoefde en gepubliceerde classificatie om een aanbeveling te geven over de vraag of er verbetering is in het opnieuw publiceren. 

## <a name="see-also"></a>Zie ook

- [Meer informatie over trainbare classificaties](classifier-learn-about.md)
- [Standaard verkende bestandsnaamextensies en geparseerde bestandstypen in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)