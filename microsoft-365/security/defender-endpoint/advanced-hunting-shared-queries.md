---
title: Gedeelde query's gebruiken in geavanceerde zoekopdrachten
description: Begin onmiddellijk met het zoeken naar bedreigingen met vooraf gedefinieerde en gedeelde query's. Deel uw query's met het publiek of met uw organisatie.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, custom detections, schema, kusto, github repo, my queries, shared queries
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9788594eaab29aba54c634e79c7aa00d6148aacd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059977"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Gedeelde query's gebruiken in geavanceerde zoekopdrachten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

[Geavanceerde](advanced-hunting-overview.md) zoekquery's kunnen worden gedeeld tussen gebruikers in dezelfde organisatie. U kunt ook query's vinden die openbaar zijn gedeeld op GitHub. Met deze query's kunt u snel specifieke scenario's voor het zoeken naar bedreigingen uitvoeren zonder dat u zelf query's moet schrijven.

![Afbeelding van gedeelde query's](images/atp-advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Een query opslaan, wijzigen en delen
U kunt een nieuwe of bestaande query opslaan, zodat deze alleen toegankelijk is voor u of wordt gedeeld met andere gebruikers in uw organisatie.

1. Typ een nieuwe query of laad een bestaande query onder **Gedeelde query's** of **Mijn query's.**

2. Selecteer **Opslaan** of **Opslaan als** in de opties voor opslaan. Als u wilt voorkomen dat u een bestaande query overschrijft, kiest **u Opslaan als**.

3. Voer een naam in voor de query.

   ![Afbeelding van het opslaan van een query](images/advanced-hunting-save-query.png)

4. Selecteer de map waarin u de query wilt opslaan.
    - **Gedeelde query's:** gedeeld met alle gebruikers in uw organisatie
    - **Mijn query's,** die alleen voor u toegankelijk zijn
    
5. Kies **Opslaan**.

## <a name="delete-or-rename-a-query"></a>Een query verwijderen of de naam wijzigen
1. Klik met de rechtermuisknop op een query die u wilt wijzigen of verwijderen.

    ![Afbeelding van de verwijderquery](images/atp_advanced_hunting_delete_rename.png)

2. Selecteer **Verwijderen** en bevestig verwijdering. Of selecteer **Naam wijzigen** en geef een nieuwe naam op voor de query.

## <a name="create-a-direct-link-to-a-query"></a>Een directe koppeling naar een query maken
Als u een koppeling wilt genereren die uw query rechtstreeks opent in de geavanceerde queryeditor, rondt u de query af en selecteert u **Koppeling delen.**

## <a name="access-queries-in-the-github-repository"></a>Access-query's in de GitHub-opslagplaats  
Microsoft-beveiligingsonderzoekers delen regelmatig geavanceerde zoekquery's in een aangewezen [openbare opslagplaats op GitHub.](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries) Deze opslagplaats staat open voor bijdragen. Als u wilt bijdragen, [kunt u gratis deelnemen aan GitHub.](https://github.com/) 

>[!TIP]
>Beveiligingsonderzoekers van Microsoft bieden ook geavanceerde zoekquery's die u kunt gebruiken om activiteiten en indicatoren te vinden die zijn gekoppeld aan nieuwe bedreigingen. Deze query's worden geleverd als onderdeel van de [bedreigingsanalyserapporten](threat-analytics.md) in het Microsoft Defender-beveiligingscentrum.

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Meer informatie over het schema](advanced-hunting-schema-reference.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van aangepaste detectie](overview-custom-detections.md)
