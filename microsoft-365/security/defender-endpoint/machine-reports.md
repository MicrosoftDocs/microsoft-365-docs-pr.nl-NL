---
title: Rapport over apparaattoestand en naleving in MICROSOFT Defender ATP
description: Detectie van apparaatstatussen, antivirusstatus, besturingssysteemplatform en Windows 10-versies bijhouden met behulp van het rapport Apparaatstatus en naleving
keywords: status, antivirus, besturingssysteemplatform, windows 10-versie, versie, status, naleving, status
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9d41071fc5849f3a11061437af2bb88b117ec4a8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058290"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a>Rapport over apparaattoestand en naleving in Microsoft Defender voor Eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Het statusrapport apparaten bevat informatie op hoog niveau over de apparaten in uw organisatie. Het rapport bevat trending-informatie over de status van de sensorstatus, antivirusstatus, besturingssysteemplatforms en Windows 10-versies.

Het dashboard is gestructureerd in twee secties: ![ Afbeelding van het apparaatrapport](images/device-reports.png)
 
Sectie | Beschrijving
:---|:---
1 | Apparaattrends
2 | Apparaatoverzicht (huidige dag)
 
 
## <a name="device-trends"></a>Apparaattrends 
De apparaattrends geven standaard apparaatgegevens weer uit de periode van 30 dagen die eindigt op de laatste volledige dag. Als u meer inzicht wilt krijgen in trends in uw organisatie, kunt u de rapportageperiode aanpassen door de weergegeven periode aan te passen. Als u de periode wilt aanpassen, selecteert u een tijdsbereik in de vervolgkeuzeopties:
 
- 30 dagen
- 3 maanden
- 6 maanden
- Aangepast

>[!NOTE]
>Deze filters worden alleen toegepast op de sectie Apparaattrends. Dit heeft geen invloed op de sectie Apparaatoverzicht.

## <a name="device-summary"></a>Apparaatoverzicht 
Terwijl de apparatentrends trending apparaatgegevens laten zien, wordt in het apparaatoverzicht de apparaatgegevens tot op de huidige dag gebruikt. 

>[!NOTE]
>De gegevens die in de samenvattingssectie worden weergegeven, hebben een bereik van 180 dagen vóór de huidige datum. Als de datum van vandaag bijvoorbeeld 27 maart 2019 is, worden de gegevens in de samenvattingssectie weergegeven met getallen die beginnen van 28 september 2018 tot en met 27 maart 2019.<br>
> Het filter dat is toegepast op de sectie Trends, wordt niet toegepast op de samenvattingssectie. 
 
In de sectie Apparaattrends kunt u inzoomen op de lijst met apparaten met het bijbehorende filter dat op het apparaat is toegepast. Als u bijvoorbeeld op de inactieve balk in de statuskaart voor sensorstatus klikt, wordt de lijst met apparaten weergegeven met alleen apparaten waarvan de sensorstatus inactief is. 
 
 
 
## <a name="device-attributes"></a>Apparaatkenmerken
Het rapport bestaat uit kaarten met de volgende apparaatkenmerken:
 
- **Gezondheidstoestand:** geeft informatie weer over de sensortoestand op apparaten, met een samengevoegde weergave van apparaten die actief zijn, communicatiesproblemen ondervinden, inactief zijn of waar geen sensorgegevens worden gezien.
  
- **Antivirusstatus voor actieve Windows 10-apparaten:** toont het aantal apparaten en de status van Microsoft Defender Antivirus.
    
- **BESTURINGSSYSTEEM-platforms:** toont de distributie van besturingssysteemplatforms die binnen uw organisatie aanwezig zijn. 
 
- **Windows 10-versies:** toont de distributie van Windows 10-apparaten en hun versies in uw organisatie.
 
 
 
## <a name="filter-data"></a>Gegevens filteren
 
Gebruik de meegeleverde filters om apparaten met bepaalde kenmerken op te nemen of uit te sluiten.

U kunt meerdere filters selecteren die u wilt toepassen op de apparaatkenmerken. 
 
>[!NOTE]
>Deze filters zijn van **toepassing op alle** kaarten in het rapport.
 
Als u bijvoorbeeld gegevens wilt tonen over Windows 10-apparaten met de status actieve sensor:
 
1. Onder **Filters > status van de sensor > Actief**.
2. Selecteer vervolgens **BE-platforms > Windows 10**.
3. Selecteer **Toepassen.**


## <a name="related-topic"></a>Gerelateerd onderwerp
- [Rapport over bedreigingsbeveiliging](threat-protection-reports.md)
