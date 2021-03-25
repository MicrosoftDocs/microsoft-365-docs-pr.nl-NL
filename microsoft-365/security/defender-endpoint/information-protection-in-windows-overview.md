---
title: Informatiebeveiliging in Windows-overzicht
ms.reviewer: ''
description: Meer informatie over hoe informatiebeveiliging in Windows werkt om gevoelige informatie te identificeren en te beveiligen
keywords: informatie, beveiliging, dlp, gegevens, verlies, preventie, bescherming
search.product: eADQiWindows 10XVcnh
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 733f86ed48b9cc7a68fb0cd346c7b15fdcc3ce65
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187503"
---
# <a name="information-protection-in-windows-overview"></a>Informatiebeveiliging in Windows-overzicht

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Prerelease information](../../includes/prerelease.md)]

Informatiebeveiliging is een integraal onderdeel van de Microsoft 365 Enterprise-suite en biedt intelligente beveiliging om gevoelige gegevens veilig te houden en productiviteit op de werkplek in te stellen.


>[!TIP]
> Lees ons blogbericht over de integratie van Microsoft Defender ATP met Microsoft Information Protection om gevoelige gegevens op [Windows-apparaten te ontdekken,](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/)te beveiligen en te bewaken.

Defender voor Eindpunt past de volgende methoden toe om gegevens te ontdekken, te classificeren en te beveiligen:

- **Gegevensdetectie** : gevoelige gegevens identificeren op Windows-apparaten die risico lopen
- **Gegevensclassificatie:** gegevens automatisch classificeren op basis van gemeenschappelijk MIP-beleid (Microsoft Information Protection) dat wordt beheerd in office 365-beveiligings- & Compliancecentrum. Met automatische classificatie kunt u gevoelige gegevens beveiligen, zelfs als de eindgebruiker deze niet handmatig heeft geclassificeerd.


## <a name="data-discovery-and-data-classification"></a>Gegevensdetectie en gegevensclassificatie

In Defender voor Eindpunt worden automatisch bestanden met gevoeligheidslabels en bestanden met gevoelige informatietypen ontdekt.

Gevoeligheidslabels classificeren en helpen gevoelige inhoud te beveiligen.

Gevoelige informatietypen in de implementatie van Office 365 data loss prevention (DLP) vallen onder twee categorieën:

- Standaard
- Aangepast

Standaardgevoelige informatietypen bevatten gegevens zoals bankrekeningnummers, socialezekerheidsnummers of nationale persoonsgegevens. Zie Waar het type gevoelige informatie naar op [zoek is voor meer informatie.](https://docs.microsoft.com/office365/securitycompliance/what-the-sensitive-information-types-look-for)

Aangepaste typen zijn typen die u definieert en die zijn ontworpen om een ander type gevoelige informatie te beveiligen (bijvoorbeeld werknemers-1D's of projectnummers). Zie Een aangepast type gevoelige informatie maken voor [meer informatie.](https://docs.microsoft.com/office365/securitycompliance/create-a-custom-sensitive-information-type)

Wanneer een bestand wordt gemaakt of bewerkt op een Windows-apparaat, scant Defender voor Eindpunt de inhoud om te evalueren of het gevoelige informatie bevat.

Schakel de Azure Information Protection-integratie in, zodat wanneer een bestand met gevoelige informatie wordt gevonden door Defender voor Eindpunt, hoewel etiketten of informatietypen, het automatisch wordt doorgestuurd naar Azure Information Protection vanaf het apparaat.

![Afbeelding van instellingenpagina met Azure Information Protection](images/atp-settings-aip.png)

De gerapporteerde signalen kunnen worden bekeken op het dashboard Azure Information Protection – Data Discovery.

## <a name="azure-information-protection---data-discovery-dashboard"></a>Azure Information Protection - Dashboard gegevensdetectie

Dit dashboard bevat een overzicht van de detectiegegevens die zijn ontdekt door zowel Defender voor Eindpunt als Azure Information Protection. Gegevens van Defender voor Eindpunt zijn gemarkeerd met Locatietype - Eindpunt.

![Afbeelding van Azure Information Protection - Gegevensdetectie](images/azure-data-discovery.png)

Let op de kolom Apparaatrisico aan de rechterkant, dit apparaatrisico wordt rechtstreeks afgeleid van Defender voor Eindpunt, waarmee het risiconiveau wordt aangegeven van het beveiligingsapparaat waar het bestand is gevonden, op basis van de actieve beveiligingsrisico's die door Defender voor Eindpunt zijn gedetecteerd.

Klik op een apparaat om een lijst met bestanden te bekijken die op dit apparaat zijn waargenomen, met de gevoeligheidslabels en informatietypen.

>[!NOTE]
>Sta ongeveer 15-20 minuten toe dat de Detectie van het Azure Information Protection Dashboard de gevonden bestanden wedt.

## <a name="log-analytics"></a>Logboekanalyse

Gegevensdetectie op basis van Defender voor Eindpunt is ook beschikbaar in [Azure Log Analytics,](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)waar u complexe query's kunt uitvoeren op de onbewerkte gegevens.

Zie Centrale rapportage voor Azure Information Protection voor meer informatie over Azure Information Protection [Analytics.](https://docs.microsoft.com/azure/information-protection/reports-aip)

Open Azure Log Analytics in Azure Portal en open een opbouwfunctie voor query's (standaard of klassiek).

Als u Defender voor eindpuntgegevens wilt weergeven, voert u een query uit die het volgende bevat:

```
InformationProtectionLogs_CL
| where Workload_s == "Windows Defender"
```

**Vereisten:**

- Klanten moeten een abonnement hebben voor Azure Information Protection.
- Integratie van Azure Information Protection inschakelen in het Microsoft Defender-beveiligingscentrum:
    - Ga naar **Instellingen** in het Microsoft Defender-beveiligingscentrum en klik op **Geavanceerde instellingen** onder **Algemeen.**



