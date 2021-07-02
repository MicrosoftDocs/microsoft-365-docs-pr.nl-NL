---
title: Indicatoren voor bestanden maken
ms.reviewer: ''
description: Maak indicatoren voor een bestandshash die de detectie, preventie en uitsluiting van entiteiten definieert.
keywords: bestand, hash, beheren, toegestaan, geblokkeerd, blokkeren, schoon, schadelijk, bestandshash, ip-adres, url's, domein
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
ms.openlocfilehash: b56a18e1b35b65629318ab29f2189ef1f73373f5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256913"
---
# <a name="create-indicators-for-files"></a>Indicatoren voor bestanden maken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Voorkom verdere verspreiding van een aanval in uw organisatie door potentieel schadelijke bestanden of vermoedelijke malware te verbieden. Als u een potentieel schadelijk bestand voor draagbaar uitvoerbaar (PE) kent, kunt u dit blokkeren. Deze bewerking voorkomt dat deze wordt gelezen, geschreven of uitgevoerd op apparaten in uw organisatie.

U kunt op drie manieren indicatoren voor bestanden maken:

- Door een indicator te maken via de pagina Instellingen
- Door een contextuele indicator te maken met behulp van de knop Indicator toevoegen op de pagina met bestandsgegevens
- Door een indicator te maken via de [Indicator-API](ti-indicator.md)

## <a name="before-you-begin"></a>Voordat u begint

Het is belangrijk om de volgende vereisten te begrijpen voordat u indicatoren voor bestanden maakt:

- Deze functie is beschikbaar als uw organisatie gebruikmaakt **van Microsoft Defender Antivirus (in** actieve modus) en **cloudbeveiliging is ingeschakeld.** Zie Beveiliging in de [cloud beheren voor meer informatie.](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)

- De versie van de Antimalware-client moet 4.18.1901.x of hoger zijn. Zie [Maandelijkse platform- en engineversies](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

- Ondersteund op apparaten met Windows 10, versie 1703 of hoger, Windows Server 2016 en 2019.

- Als u bestanden wilt blokkeren, moet u eerst de functie 'blokkeren of [toestaan'](advanced-features.md) in Instellingen.

Deze functie is ontworpen om te voorkomen dat verdachte malware (of mogelijk schadelijke bestanden) van internet wordt gedownload. Het ondersteunt momenteel draagbare uitvoerbare (PE)-bestanden, .exe en .dll bestanden. De dekking wordt in de tijd uitgebreid.

## <a name="create-an-indicator-for-files-from-the-settings-page"></a>Een indicator voor bestanden maken op de pagina Instellingen

1. Selecteer in het navigatiedeelvenster **Instellingen > Indicatoren.**

2. Selecteer het **tabblad Bestandshash.**  

3. Selecteer **Indicator toevoegen.**

4. Geef de volgende details op:
    - Indicator: geef de details van de entiteit op en definieer de afloop van de indicator.
    - Actie: geef de actie op die moet worden ondernomen en geef een beschrijving op.
    - Bereik: definieer het bereik van de apparaatgroep.

5. Bekijk de details op het tabblad Overzicht en selecteer **Opslaan.**

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a>Een contextuele indicator maken op de pagina met bestandsgegevens

Een van de opties bij het [uitvoeren van antwoordacties in een bestand](respond-file-alerts.md)is het toevoegen van een indicator voor het   bestand. Wanneer u een indicatorhash voor een bestand toevoegt, kunt u ervoor kiezen om een waarschuwing te verhogen en het bestand te blokkeren wanneer een apparaat in uw organisatie dit probeert uit te voeren.

Bestanden die automatisch worden geblokkeerd door een indicator, worden niet weergegeven in het actiecentrum van het bestand, maar de waarschuwingen blijven wel zichtbaar in de wachtrij Waarschuwingen.

>[!IMPORTANT]
>- Meestal worden bestandsblokken binnen een paar minuten afgedwongen en verwijderd, maar dit kan meer dan 30 minuten duren.
> 
>- Als er conflicterende bestands-IoC-beleidsregels zijn met hetzelfde afdwingingstype en hetzelfde doel, wordt het beleid van de veiligere hash toegepast. Een sha-256-bestandshash-IoC-beleid zal een SHA-1-bestandshash-IoC-beleid overnemen, dat een MD5-bestandshash-IoC-beleid overwint als de hashtypen hetzelfde bestand definiëren. Dit geldt altijd, ongeacht de apparaatgroep. 
>   Als in alle andere gevallen conflicterende bestand-IoC-beleidsregels met hetzelfde afdwingingsdoel worden toegepast op alle apparaten en op de groep van het apparaat, wordt voor een apparaat het beleid in de apparaatgroep gewonnen. 
>   
>- Als het groepsbeleid EnableFileHashComputation is uitgeschakeld, wordt de blokkeringsnauwkeurigheid van de bestands-IoC verminderd. Het inschakelen kan `EnableFileHashComputation` echter van invloed zijn op de prestaties van het apparaat. Het kopiëren van grote bestanden van een netwerk delen naar uw lokale apparaat, met name via een VPN-verbinding, kan bijvoorbeeld van invloed zijn op de prestaties van het apparaat.
>
>   Zie [Defender CSP](/windows/client-management/mdm/defender-csp) voor meer informatie over het groepsbeleid enableFileHashComputation

## <a name="policy-conflict-handling"></a>Beleidsconflictafhandeling  

Cert- en bestands-IoC-beleidsafhandelingsconflicten volgen de volgende volgorde:

- Als het bestand niet is toegestaan Windows Defender toepassingsbeheer en AppLocker-modusbeleid/-beleid afdwingen, **blokkeert** u

- Anders als het bestand is toegestaan door de Microsoft Defender Antivirus uitsluiting, dan **toestaan**

- Anders als het bestand is geblokkeerd of gewaarschuwd door een blok- of waarschuwingsbestand-IoC, vervolgens **blokkeren/waarschuwen**

- Anders als het bestand is toegestaan door een IoC-beleid voor bestand toestaan, wordt **het bestand vervolgens toegestaan**

- Anders als het bestand is geblokkeerd door ASR-regels, CFA, AV, SmartScreen en **vervolgens Blokkeren**  

- Else Allow (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it) Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)

Als er conflicterende bestands-IoC-beleidsregels zijn met hetzelfde afdwingingstype en hetzelfde doel, wordt het beleid van de veiligere hash (wat langer betekent) toegepast. Een sha-256-bestandshash-IoC-beleid zal bijvoorbeeld een IoC-beleid voor MD5-bestandshash winnen als beide hashtypen hetzelfde bestand definiëren.

De functies voor vulnerability management en blokkering van kwetsbare toepassingen maken gebruik van de bestands-Ioc's voor handhaving en volgen de bovenstaande conflictafhandelingsvolgorde.

### <a name="examples"></a>Voorbeelden

|Onderdeel |Component afdwingen |Actie bestandsindicator |Resultaat
|--|--|--|--|
|Uitsluiting van het surface reduction-bestandspad voor aanvallen |Toestaan |Blokkeren |Blokkeren
|Surface Reduction-regel voor aanvallen |Blokkeren |Toestaan |Toestaan
|Windows Defender-toepassingsbeheer |Toestaan |Blokkeren |Toestaan |
|Windows Defender-toepassingsbeheer |Blokkeren |Toestaan |Blokkeren
|Microsoft Defender Antivirus uitsluiting |Toestaan |Blokkeren |Toestaan

## <a name="see-also"></a>Zie ook

- [Indicatoren maken](manage-indicators.md)
- [Indicatoren maken voor IP's en URL's/domeinen](indicator-ip-domain.md)
- [Indicatoren maken op basis van certificaten](indicator-certificates.md)
- [Indicatoren beheren](indicator-manage.md)
