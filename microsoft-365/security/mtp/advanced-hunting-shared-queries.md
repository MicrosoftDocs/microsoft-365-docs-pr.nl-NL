---
title: Gedeelde query's gebruiken in geavanceerde jacht op Microsoft Threat Protection
description: Start onmiddellijk dreigingsjacht met vooraf gedefinieerde en gedeelde query's. Deel uw vragen met het publiek of uw organisatie.
keywords: geavanceerde jacht, dreigingjacht, cyberdreigingsjacht, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetrie, aangepaste detecties, schema, kusto, github repo, mijn zoekopdrachten, gedeelde query's
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 7ff46226e2535ed9826a61afa857e38b03c06ce1
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807337"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Gedeelde query's gebruiken in geavanceerde jacht

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging



[Geavanceerde](advanced-hunting-overview.md) jachtquery's kunnen worden gedeeld tussen gebruikers in dezelfde organisatie. U ook query's vinden die openbaar worden gedeeld op GitHub. Met deze query's u snel specifieke scenario's voor bedreigingsjacht nastreven zonder dat u query's vanaf nul hoeft te schrijven.

![Afbeelding van gedeelde query's](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Een query opslaan, wijzigen en delen
U een nieuwe of bestaande query opslaan, zodat deze alleen toegankelijk voor u is of wordt gedeeld met andere gebruikers in uw organisatie. 

1. Een query maken of wijzigen. 

2. Klik **op** de vervolgkeuzelijst Query opslaan en selecteer **Opslaan als**.
    
3. Voer een naam in voor de query. 

   ![Afbeelding van het opslaan van een query](../../media/advanced-hunting-save-query.png)

4. Selecteer de map waar u de query wilt opslaan.
    - **Gedeelde query's** — gedeeld met alle gebruikers van uw organisatie
    - **Mijn vragen** — alleen voor u toegankelijk
    
5. Kies **Opslaan**. 

## <a name="delete-or-rename-a-query"></a>Een query verwijderen of de naam wijzigen
1. Klik met de rechtermuisknop op een query die u wilt hernoemen of verwijderen.

    ![Afbeelding van verwijderquery](../../media/advanced_hunting_delete_rename.png)

2. Selecteer **Verwijderen** en verwijdering bevestigen. Of selecteer **Naam wijzigen** en geef een nieuwe naam op voor de query.

## <a name="access-queries-in-the-github-repository"></a>Toegang tot query's in de GitHub-repository  
Microsoft security onderzoekers delen regelmatig geavanceerde jacht query's in een [aangewezen openbare repository op GitHub](https://github.com/microsoft/MTP-AHQ). Deze repository staat open voor bijdragen. Om bij te dragen, [word je gratis lid van GitHub.](https://github.com/)

>[!tip]
>Microsoft security onderzoekers bieden ook geavanceerde jacht query's die u gebruiken om activiteiten en indicatoren in verband met opkomende bedreigingen te lokaliseren. Deze query's worden geleverd als onderdeel van de [rapporten over bedreigingsanalyse](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) in Microsoft Defender Security Center.

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Het schema begrijpen](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
