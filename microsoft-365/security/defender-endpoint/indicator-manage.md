---
title: Indicatoren beheren
ms.reviewer: ''
description: Indicatoren beheren voor een bestandshash, IP-adres, URL's of domeinen die de detectie, preventie en uitsluiting van entiteiten definiëren.
keywords: import, indicator, list, ioc, csv, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
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
ms.openlocfilehash: 9fd36f63450335247bf57c4cc1f98d6f0d32a9d5
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185943"
---
# <a name="manage-indicators"></a>Indicatoren beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


1. Selecteer instellingenindicatoren in het  >  **navigatiedeelvenster.**

2. Selecteer het tabblad van het entiteitstype dat u wilt beheren.  

3. Werk de details van de indicator bij en klik op **Opslaan** of klik op de knop **Verwijderen** als u de entiteit uit de lijst wilt verwijderen.

## <a name="import-a-list-of-iocs"></a>Een lijst met IocCs importeren

U kunt er ook voor kiezen om een CSV-bestand te uploaden dat de kenmerken van indicatoren, de actie die moet worden ondernomen en andere details definieert.

Download de voorbeeld-CSV om de ondersteunde kolomkenmerken te kennen.

1. Selecteer instellingenindicatoren in het  >  **navigatiedeelvenster.**

2. Selecteer het tabblad van het entiteitstype waar u indicatoren voor wilt importeren.

3. Selecteer **Bestand importeren**  >  **kiezen.** 

4. Selecteer **Importeren.** Doe dit voor alle bestanden die u wilt importeren. 

5. Selecteer **Gereed**.

In de volgende tabel ziet u de ondersteunde parameters.

Parameter | Type    |   Beschrijving
:---|:---|:---
indicatorType | Enum | Type indicator. Mogelijke waarden zijn: "FileSha1", "FileSha256", "IpAddress", "DomainName" en "Url". **Vereist**
indicatorValue | Tekenreeks | Identiteit van de [entiteit Indicator.](ti-indicator.md) **Vereist**
actie | Enum | De actie die wordt ondernomen als de indicator wordt gevonden in de organisatie. Mogelijke waarden zijn: 'Waarschuwing', 'AlertAndBlock' en 'Toegestaan'. **Vereist**
titel | Tekenreeks | Indicatorwaarschuwingstitel. **Vereist**
beschrijving | Tekenreeks |  Beschrijving van de indicator. **Vereist**
verlooptijd | DateTimeOffset | De verlooptijd van de indicator in de volgende notatie YYYY-MM-DDTHH:MM:SS.0Z. **Optioneel**
ernst | Enum | De ernst van de indicator. Mogelijke waarden zijn: 'Informatief', 'Laag', 'Gemiddeld' en 'Hoog'. **Optioneel**
aanbevolenActie | Tekenreeks | Aanbevolen acties voor ti-indicatorwaarschuwingen. **Optioneel**
rbacGroupNames | Tekenreeks | Door komma's gescheiden lijst met RBAC-groepsnamen waar de indicator op zou worden toegepast. **Optioneel**
categorie | Tekenreeks | Categorie van de waarschuwing. Voorbeelden hiervan zijn: Uitvoering en toegang tot referenties. **Optioneel**
mitretechniques| Tekenreeks | MITRE-technieken code/id (door komma's gescheiden). Zie Ondernemingstactieken [voor meer informatie.](https://attack.mitre.org/tactics/enterprise/) **Optioneel** Het wordt aanbevolen om een waarde toe te voegen aan een categorie wanneer een MITRE-techniek wordt gebruikt.

Zie Waarschuwingscategorieën van Microsoft Defender voor eindpunten zijn nu uitgelijnd met [MITRE ATT-&CK! voor](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748)meer informatie.


## <a name="see-also"></a>Zie ook
- [Indicatoren maken](manage-indicators.md)
- [Indicatoren voor bestanden maken](indicator-file.md)
- [Indicatoren maken voor IPs en URL's/domeinen](indicator-ip-domain.md)
- [Indicatoren maken op basis van certificaten](indicator-certificates.md)
