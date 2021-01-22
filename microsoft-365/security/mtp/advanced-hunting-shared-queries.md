---
title: Gedeelde query's gebruiken in de geavanceerde zoekopdracht van Microsoft 365 Defender
description: Start onmiddellijk risicozoeken met vooraf gedefinieerde en gedeelde query's. Deel uw query's met het publiek of met uw organisatie.
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, custom detections, schema, kusto, github repo, my queries, shared queries
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 7dcf446b5e1014d411fc8af08dd15506a2b04e49
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932188"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Gedeelde query's gebruiken bij geavanceerd zoeken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



[Geavanceerde](advanced-hunting-overview.md) zoekquery's kunnen worden gedeeld tussen gebruikers in dezelfde organisatie. U kunt query's die openbaar zijn gedeeld ook vinden in GitHub. Met deze query's kunt u snel specifieke scenario's voor het zoeken naar bedreigingen uitvoeren zonder dat u zelf query's moet schrijven.

![Afbeelding van gedeelde query's](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Een query opslaan, wijzigen en delen
U kunt een nieuwe of bestaande query opslaan, zodat deze alleen toegankelijk is voor u of wordt gedeeld met andere gebruikers in uw organisatie. 

1. Een query maken of wijzigen. 

2. Klik op **de vervolgkeuzeknop Query** opslaan en selecteer Opslaan **als.**
    
3. Voer een naam in voor de query. 

   ![Afbeelding van het opslaan van een query](../../media/advanced-hunting-save-query.png)

4. Selecteer de map waarin u de query wilt opslaan.
    - **Gedeelde query's:** gedeeld met alle gebruikers in uw organisatie
    - **Mijn query's,** die alleen voor u toegankelijk zijn
    
5. Klik op **Opslaan**. 

## <a name="delete-or-rename-a-query"></a>Een query verwijderen of de naam van een query wijzigen
1. Klik met de rechtermuisknop op een query die u een andere naam wilt geven of die u wilt verwijderen.

    ![Afbeelding van verwijderquery](../../media/advanced_hunting_delete_rename.png)

2. Selecteer **Verwijderen en** bevestig het verwijderen. Of selecteer **Naam wijzigen** en geef een nieuwe naam op voor de query.

## <a name="create-a-direct-link-to-a-query"></a>Een directe koppeling naar een query maken
Als u een koppeling wilt genereren om uw query rechtstreeks in de geavanceerde queryeditor te openen, rondt u de query af en selecteert u **Koppeling delen.**

## <a name="access-queries-in-the-github-repository"></a>Access-query's in de GitHub-opslagplaats  
Beveiligingsonderzoek van Microsoft deelt regelmatig geavanceerde zoekquery's in een aangewezen [openbare opslagplaats op GitHub.](https://aka.ms/hunting-queries) Deze opslagplaats is toegankelijk voor bijdragen. Als u wilt bijdragen, [kunt u gratis deelnemen aan GitHub.](https://github.com/)

>[!tip]
>Microsoft-beveiligingsonderzoek biedt ook geavanceerde zoekquery's die u kunt gebruiken om activiteiten en indicatoren te vinden die zijn gekoppeld aan nieuwe bedreigingen. Deze query's worden geleverd als onderdeel van de [bedreigingsanalyserapporten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) in het Microsoft Defender-beveiligingscentrum.

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
