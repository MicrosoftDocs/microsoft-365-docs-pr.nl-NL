---
title: Microsoft Defender ATP voor Mac
ms.reviewer: ''
description: Meer informatie over het installeren, configureren, bijwerken en gebruiken van Microsoft Defender voor Eindpunt voor Mac.
keywords: microsoft, defender, atp, mac, installatie, implementeren, verwijderen, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3e96cf09fd13a4d99546a1c18f9c61f40c362bf8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057057"
---
# <a name="microsoft-defender-for-endpoint-for-mac"></a>Microsoft Defender voor Eindpunt voor Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

In dit onderwerp wordt beschreven hoe u Defender voor Eindpunt voor Mac kunt installeren, configureren, bijwerken en gebruiken.

> [!CAUTION]
> Het uitvoeren van andere endpointbeveiligingsproducten van derden naast Defender voor Eindpunt voor Mac kan waarschijnlijk leiden tot prestatieproblemen en onvoorspelbare bijwerkingen. Als niet-Microsoft-eindpuntbeveiliging een absolute vereiste is in uw omgeving, kunt u nog steeds veilig profiteren van MDATP voor Mac EDR-functionaliteit na het configureren van de antivirusfunctionaliteit van MDATP voor Mac om in de passieve modus uit te [voeren.](mac-preferences.md#enable--disable-passive-mode)

## <a name="whats-new-in-the-latest-release"></a>Nieuwe functies in de nieuwste release

[Nieuwe functies in Microsoft Defender voor Eindpunt](whats-new-in-microsoft-defender-atp.md)

[Nieuwe functies in Microsoft Defender voor Eindpunt voor Mac](mac-whatsnew.md)

> [!TIP]
> Als u feedback hebt die u wilt delen, verzendt u deze door Microsoft Defender voor Eindpunt voor Mac te openen op uw apparaat en te navigeren naar **Help**  >  **Feedback verzenden.**

Als u de nieuwste functies wilt downloaden, waaronder preview-mogelijkheden (zoals eindpuntdetectie en antwoord voor uw Mac-apparaten), configureert u uw macOS-apparaat met Microsoft Defender voor Eindpunt als een Insider-apparaat.

## <a name="how-to-install-microsoft-defender-for-endpoint-for-mac"></a>Microsoft Defender voor Eindpunt voor Mac installeren

### <a name="prerequisites"></a>Vereisten

- Een Defender for Endpoint-abonnement en toegang tot de microsoft Defender Security Center-portal
- Beginnerservaring in macOS- en BASH-scripting
- Beheerdersbevoegdheden op het apparaat (in geval van handmatige implementatie)

### <a name="installation-instructions"></a>Installatie-instructies

Er zijn verschillende methoden en implementatiehulpmiddelen waarmee u Defender voor Eindpunt voor Mac kunt installeren en configureren.

- Beheerhulpmiddelen van derden:
    - [Microsoft Intune-implementatie](mac-install-with-intune.md)
    - [IMPLEMENTATIE OP BASIS VAN JAMF](mac-install-with-jamf.md)
    - [Andere MDM-producten](mac-install-with-other-mdm.md)

- Opdrachtregelhulpmiddel:
    - [Handmatige implementatie](mac-install-manually.md)

### <a name="system-requirements"></a>Systeemvereisten

De drie meest recente grote versies van macOS worden ondersteund.

> [!IMPORTANT]
> Voor macOS 11 (Big Sur) vereist Microsoft Defender voor Eindpunt extra configuratieprofielen. Als u een bestaande klant bent die upgradet van eerdere versies van macOS, moet u de aanvullende configuratieprofielen implementeren die worden vermeld in Nieuwe configuratieprofielen voor [macOS Catalina](mac-sysext-policies.md)en nieuwere versies van macOS.

> [!IMPORTANT]
> Ondersteuning voor macOS 10.13 (High Sierra) wordt stopgezet op 15 februari 2021.

- 11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave), 10.13 (High Sierra)
- Schijfruimte: 1 GB

Bètaversies van macOS worden niet ondersteund.

Nadat u de service hebt ingeschakeld, moet u mogelijk uw netwerk of firewall configureren om uitgaande verbindingen tussen de service en uw eindpunten toe te staan.

### <a name="licensing-requirements"></a>Licentievereisten

Voor Microsoft Defender voor Endpoint voor Mac is een van de volgende Microsoft Volume Licensing-aanbiedingen vereist:

- Microsoft 365 E5 (M365 E5)
- Microsoft 365 E5-beveiliging
- Microsoft 365 A5 (M365 A5)

> [!NOTE]
> In aanmerking komende gebruikers met een licentie kunnen Microsoft Defender voor Eindpunt gebruiken op maximaal vijf gelijktijdige apparaten.
> Microsoft Defender voor Eindpunt is ook beschikbaar voor aankoop bij een Cloud Solution Provider (CSP). Bij aankoop via een CSP zijn er geen aanbiedingen voor Microsoft Volume Licensing vereist.

### <a name="network-connections"></a>Netwerkverbindingen

In de volgende downloadbare spreadsheet vindt u de services en bijbehorende URL's waar uw netwerk verbinding mee moet kunnen maken. U moet ervoor zorgen dat er geen firewall- of netwerkfilterregels zijn die de  toegang tot deze URL's weigeren, of u moet mogelijk een regel voor toestaan speciaal voor deze url's maken.



|**Spreadsheet met domeinenlijst**|**Beschrijving**|
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLLs spreadsheet](images/mdatp-urls.png)<br/>  | Spreadsheet met specifieke DNS-records voor servicelocaties, geografische locaties en besturingssysteem. <br><br>Download de spreadsheet hier: [mdatp-urls.xlsx. ](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

Microsoft Defender voor Eindpunt kan een proxyserver vinden met behulp van de volgende detectiemethoden:
- Proxy autoconfig (PAC)
- Web proxy Autodiscovery Protocol (WPAD)
- Handmatige statische proxyconfiguratie

Als een proxy of firewall anoniem verkeer blokkeert, moet u ervoor zorgen dat anoniem verkeer is toegestaan in de eerder genoemde URL's.

> [!WARNING]
> Geverifieerde proxies worden niet ondersteund. Zorg ervoor dat alleen PAC, WPAD of een statische proxy wordt gebruikt.
>
> SSL-inspectie en het onderscheppen van proxies worden ook niet ondersteund om beveiligingsredenen. Configureer een uitzondering voor SSL-inspectie en uw proxyserver om gegevens van Microsoft Defender voor Eindpunt voor Mac rechtstreeks door te geven aan de relevante URL's zonder interceptie. Als u uw interceptiecertificaat toevoegt aan de algemene winkel, is onderschepping niet toegestaan.

Open en in een browser om te testen of een verbinding niet [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) is geblokkeerd.

Als u de voorkeur geeft aan de opdrachtregel, kunt u ook de verbinding controleren door de volgende opdracht uit te voeren in Terminal:

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

De uitvoer van deze opdracht moet ongeveer hetzelfde zijn:

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> We raden u aan [om System Integrity Protection](https://support.apple.com/en-us/HT204899) (SIP) ingeschakeld te houden op clientapparaten. SIP is een ingebouwde beveiligingsfunctie voor macOS die voorkomt dat er op laag niveau wordt geknoeid met het besturingssysteem en standaard is ingeschakeld.

Nadat Microsoft Defender voor Eindpunt is geïnstalleerd, kan de connectiviteit worden gevalideerd door de volgende opdracht uit te voeren in Terminal:
```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-for-mac"></a>Microsoft Defender voor Eindpunt voor Mac bijwerken

Microsoft publiceert regelmatig software-updates om de prestaties, beveiliging en nieuwe functies te verbeteren. Als u Microsoft Defender voor Eindpunt voor Mac wilt bijwerken, wordt een programma met de naam Microsoft AutoUpdate (MAU) gebruikt. Zie Updates implementeren voor Microsoft Defender voor Eindpunt voor Mac voor meer [informatie.](mac-updates.md)

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-mac"></a>Microsoft Defender configureren voor Eindpunt voor Mac

Richtlijnen voor het configureren van het product in bedrijfsomgevingen zijn beschikbaar in Voorkeuren instellen voor [Microsoft Defender voor Eindpunt voor Mac.](mac-preferences.md)

## <a name="macos-kernel-and-system-extensions"></a>macOS-kernel- en systeemextensies

In overeenstemming met de ontwikkeling van macOS bereiden we een Update van Microsoft Defender voor Eindpunt voor Mac voor die gebruik maakt van systeemextensies in plaats van kernelextensies. Zie Nieuw in Microsoft Defender voor Eindpunt voor Mac voor relevante [informatie.](mac-whatsnew.md)

## <a name="resources"></a>Resources

- Zie Resources voor Microsoft Defender voor Eindpunt voor Mac voor meer informatie over logboekregistratie, verwijderen of [andere onderwerpen.](mac-resources.md)

- [Privacy voor Microsoft Defender voor Eindpunt voor Mac](mac-privacy.md).
