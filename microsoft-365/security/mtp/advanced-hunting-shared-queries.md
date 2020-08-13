---
title: Gedeelde query's gebruiken in Microsoft Threat Protection Advanced jacht
description: Start de bedreigings jacht direct met vooraf gedefinieerde en gedeelde query's. Uw query's delen met het publiek of uw organisatie.
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, telemetrie, aangepaste detectie, schema, kusto, github repo, mijn query's, gedeelde query's
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
ms.openlocfilehash: d9dcd07a4fc63130d015bf31270d1de9212f9a53
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649185"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Gedeelde query's gebruiken in geavanceerde jacht

**Van toepassing op:**
- Microsoft Threat Protection



U kunt [Geavanceerde](advanced-hunting-overview.md) zoekopdrachten delen tussen gebruikers in dezelfde organisatie. U kunt ook zoeken naar query's die openbaar zijn gemaakt op GitHub. Met deze query's kunt u snel specifieke scenario's van de Threat-jacht maken zonder dat u query's helemaal hoeft te schrijven.

![Afbeelding van gedeelde query's](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Een query opslaan, wijzigen en delen
U kunt een nieuwe of bestaande query opslaan, zodat deze alleen toegankelijk is voor u of wordt gedeeld met andere gebruikers in uw organisatie. 

1. Maak of wijzig een query. 

2. Klik op de vervolgkeuzeknop **query opslaan** en selecteer **Opslaan als**.
    
3. Voer een naam in voor de query. 

   ![Afbeelding van het opslaan van een query](../../media/advanced-hunting-save-query.png)

4. Selecteer de map waarin u de query wilt opslaan.
    - **Gedeelde query's** , gedeeld met alle gebruikers van uw organisatie
    - **Mijn query's** : alleen toegankelijk voor u
    
5. Kies **Opslaan**. 

## <a name="delete-or-rename-a-query"></a>Een query verwijderen of de naam ervan wijzigen
1. Klik met de rechtermuisknop op de query waarvan u de naam wilt wijzigen of die u wilt verwijderen.

    ![Afbeelding van verwijderquery](../../media/advanced_hunting_delete_rename.png)

2. Selecteer **verwijderen** en bevestig de verwijdering. Of selecteer **naam wijzigen** en geef een nieuwe naam voor de query op.

## <a name="create-a-direct-link-to-a-query"></a>Een directe koppeling maken naar een query
Als u een koppeling wilt maken waarmee de query rechtstreeks wordt geopend in de geavanceerde jacht query editor, maakt u de query af en selecteert u **koppeling delen**.

## <a name="access-queries-in-the-github-repository"></a>Access-query's in de GitHub-bibliotheek  
Microsoft-beveiligingsonderzoekers delen regelmatig geavanceerde jacht-query's in een [aangewezen openbare opslagplaats op github](https://aka.ms/hunting-queries). Deze bibliotheek is geopend met bijdragen. Als u een bijdrage wilt leveren, kunt u [gratis deelnemen aan github](https://github.com/).

>[!tip]
>Microsoft-beveiligingsonderzoekers leveren ook geavanceerde jacht-query's die u kunt gebruiken om te zoeken naar activiteiten en indicatoren die zijn gekoppeld aan de opkomende bedreigingen. Deze query's worden opgenomen als onderdeel van de [Threat Analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) -rapporten in het Microsoft Defender-Beveiligingscentrum.

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Jacht op apparaten, e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
