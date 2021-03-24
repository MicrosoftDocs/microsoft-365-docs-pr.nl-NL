---
title: Technieken in de tijdlijn van het apparaat
description: Informatie over de apparaattijdlijn in Microsoft Defender voor Eindpunt
keywords: apparaattijdlijn, eindpunt, MITRE, MITRE ATT&CK, technieken, tactieken
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d6e2c18bd3710e659b5f9887844bc92528da4607
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057313"
---
# <a name="techniques-in-the-device-timeline"></a>Technieken in de tijdlijn van het apparaat


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)


U kunt meer inzicht krijgen in een onderzoek door de gebeurtenissen op een bepaald apparaat te analyseren. Selecteer eerst het apparaat van belang in de [lijst Apparaten.](machines-view-overview.md) Op de apparaatpagina kunt u het tabblad **Tijdlijn** selecteren om alle gebeurtenissen op het apparaat weer te geven.

## <a name="understand-techniques-in-the-timeline"></a>Technieken in de tijdlijn begrijpen

>[!IMPORTANT]
>Sommige informatie heeft betrekking op een vooraf uitgebrachte productfunctie in een openbare preview die aanzienlijk kan worden gewijzigd voordat deze commercieel wordt uitgebracht. Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.

In Microsoft Defender voor Eindpunt zijn **technieken** een extra gegevenstype in de tijdlijn van de gebeurtenis. Technieken bieden meer inzicht in activiteiten die zijn gekoppeld aan [MITRE ATT-&CK-technieken](https://attack.mitre.org/) of subtechnieken. 

Deze functie vereenvoudigt de onderzoekservaring door analisten te helpen inzicht te krijgen in de activiteiten die op een apparaat zijn waargenomen. Analisten kunnen vervolgens besluiten om het verder te onderzoeken.

Voor een openbaar voorbeeld zijn technieken standaard beschikbaar en worden deze samen met gebeurtenissen weergegeven wanneer de tijdlijn van een apparaat wordt weergegeven. 

![Schermafbeelding van technieken in de tijdlijn van het apparaat](images/device-timeline-2.png)

Technieken zijn gemarkeerd met vetgedrukte tekst en worden weergegeven met een blauw pictogram aan de linkerkant. De bijbehorende MITRE ATT-&CK-id en -techniek worden ook weergegeven als tags onder Aanvullende informatie. 

Zoek- en exportopties zijn ook beschikbaar voor Technieken.

## <a name="investigate-using-the-side-pane"></a>Onderzoeken met behulp van het zijdeelvenster

Selecteer een techniek om het bijbehorende zijvenster te openen. Hier ziet u aanvullende informatie en inzichten, zoals gerelateerde ATT-&CK-technieken, tactieken en beschrijvingen. 

Selecteer de specifieke *aanvalstechniek om* de gerelateerde att-&CK-techniekpagina te openen, waar u meer informatie over kunt vinden.

U kunt de details van een entiteit kopiëren wanneer u een blauw pictogram aan de rechterkant ziet. Als u bijvoorbeeld de SHA1 van een gerelateerd bestand wilt kopiëren, selecteert u het blauwe paginapictogram.

![Entiteitsgegevens kopiëren](images/techniques-side-pane-clickable.png)

U kunt hetzelfde doen voor opdrachtlijnen.

![Opdrachtregel kopiëren](images/techniques-side-pane-command.png)


## <a name="investigate-related-events"></a>Gerelateerde gebeurtenissen onderzoeken

Als u [geavanceerde jacht wilt gebruiken](advanced-hunting-overview.md) om gebeurtenissen te zoeken die betrekking hebben op de geselecteerde techniek, selecteert u **Opzoeken naar gerelateerde gebeurtenissen.** Dit leidt naar de geavanceerde pagina met een query om gebeurtenissen te zoeken die betrekking hebben op de techniek.

![Op zoek gaan naar gerelateerde gebeurtenissen](images/techniques-hunt-for-related-events.png)

>[!NOTE]
>Query's met **behulp** van de knop Zoeken naar gerelateerde gebeurtenissen in een zijvenster Techniek geven alle gebeurtenissen weer die betrekking hebben op de geïdentificeerde techniek, maar bevatten de techniek zelf niet in de queryresultaten.


## <a name="customize-your-device-timeline"></a>De tijdlijn van uw apparaat aanpassen

Rechtsboven in de tijdlijn van het apparaat kunt u een datumbereik kiezen om het aantal gebeurtenissen en technieken in de tijdlijn te beperken. 

U kunt aanpassen welke kolommen u wilt laten zien. U kunt ook filteren op gemarkeerde gebeurtenissen op gegevenstype of op gebeurtenisgroep.

### <a name="choose-columns-to-expose"></a>Kolommen kiezen om weer te geven
U kunt kiezen welke kolommen u wilt weergeven in de tijdlijn door de knop **Kolommen kiezen te** selecteren.

![Kolommen aanpassen](images/filter-customize-columns.png)

Hier kunt u selecteren welke gegevensset u wilt opnemen.

### <a name="filter-to-view-techniques-or-events-only"></a>Filteren om alleen technieken of gebeurtenissen weer te geven

Als u alleen gebeurtenissen of technieken wilt weergeven, **selecteert** u Filters in de apparaattijdlijn en kiest u het gewenste gegevenstype dat u wilt weergeven.

![Schermafbeelding van filters](images/device-timeline-filters.png)



## <a name="see-also"></a>Zie ook
- [De lijst Apparaten weergeven en ordenen](machines-view-overview.md)
- [Gebeurtenisvlaggen van Microsoft Defender voor eindpuntapparaat](device-timeline-event-flag.md) 


 
