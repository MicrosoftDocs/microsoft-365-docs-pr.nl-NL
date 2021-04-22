---
title: Tijdzone-instellingen voor microsoft Defender Security Center
description: Gebruik de informatie hier om de tijdzone-instellingen van het Microsoft Defender-beveiligingscentrum te configureren en licentiegegevens weer te geven.
keywords: instellingen, Microsoft Defender, cyberbeveiligingsbedreigingsinformatie, Microsoft Defender voor eindpunt, tijdzone, utc, lokale tijd, licentie
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
ms.openlocfilehash: df55a1b0e92c24b5f52032330ef95bf19aeb8cb3
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932629"
---
# <a name="microsoft-defender-security-center-time-zone-settings"></a>Tijdzone-instellingen voor microsoft Defender Security Center

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-settings-abovefoldlink)

Gebruik het **pictogram Tijdzone-instellingen** in het menu ![ Tijdzone1 om de tijdzone te ](images/atp-time-zone.png) configureren en licentiegegevens weer te geven.

## <a name="time-zone-settings"></a>Tijdzone-instellingen
Het tijdsaspect is belangrijk bij het beoordelen en analyseren van waargenomen en werkelijke cyberaanvallen.

Cyberforensische onderzoeken zijn vaak afhankelijk van tijdstempels om de volgorde van gebeurtenissen samen te brengen. Het is belangrijk dat uw systeem de juiste tijdzone-instellingen weerspiegelt.

Microsoft Defender voor Eindpunt kan Coordinated Universal Time (UTC) of lokale tijd weergeven.

De huidige tijdzone-instelling wordt weergegeven in het menu Microsoft Defender voor eindpunt. U kunt de weergegeven tijdzone wijzigen in het **menu Tijdzone.**

![Pictogram Tijdzone-instellingen2](images/atp-time-zone-menu.png).

### <a name="utc-time-zone"></a>UTC-tijdzone
Microsoft Defender voor Eindpunt gebruikt standaard UTC-tijd.

Als u de tijdzone van Microsoft Defender voor eindpunt instelt op UTC, worden alle systeemtijdstempels (waarschuwingen, gebeurtenissen en andere) weergegeven in UTC voor alle gebruikers. Dit kan beveiligingsanalisten die op verschillende locaties over de hele wereld werken helpen om dezelfde tijdstempels te gebruiken tijdens het onderzoeken van gebeurtenissen.

### <a name="local-time-zone"></a>Lokale tijdzone
U kunt ervoor kiezen om voor Microsoft Defender voor Eindpunt lokale tijdzone-instellingen te laten gebruiken. Alle waarschuwingen en gebeurtenissen worden weergegeven met uw lokale tijdzone.

De lokale tijdzone wordt overgenomen uit de regionale instellingen van uw apparaat. Als u uw regionale instellingen wijzigt, wordt ook de tijdzone van Microsoft Defender voor eindpunt gewijzigd. Als u deze instelling kiest, worden de tijdstempels die worden weergegeven in Microsoft Defender voor Eindpunt, uitgelijnd op lokale tijd voor alle Gebruikers van Microsoft Defender voor Eindpunten. Analisten die zich op verschillende globale locaties bevinden, zien nu de waarschuwingen van Microsoft Defender voor eindpunten op basis van hun landinstellingen.

Het gebruik van lokale tijd kan handig zijn als de analisten zich op één locatie bevinden. In dit geval is het mogelijk gemakkelijker om gebeurtenissen te correleren met lokale tijd, bijvoorbeeld wanneer een lokale gebruiker op een verdachte e-mailkoppeling heeft geklikt.

### <a name="set-the-time-zone"></a>De tijdzone instellen
De tijdzone van Microsoft Defender voor eindpunt is standaard ingesteld op UTC.
Als u de tijdzone instelt, worden ook de tijden voor alle Weergaven van Microsoft Defender voor eindpunten gewijzigd.
De tijdzone instellen:

1. Klik op **het pictogram Tijdzonemenu** ![ Tijdzone-instellingen3 ](images/atp-time-zone.png) .
2. Selecteer de **timezone UTC-indicator.**
3. Selecteer **Timezone UTC** of uw lokale tijdzone, bijvoorbeeld -7:00.

### <a name="regional-settings"></a>Regionale instellingen
Als u verschillende datumindelingen wilt toepassen voor Microsoft Defender voor Eindpunt, gebruikt u landinstellingen voor Internet Explorer (IE) en Microsoft Edge (Edge). Als u een andere browser gebruikt, zoals Google Chrome, volgt u de vereiste stappen om de tijd- en datuminstellingen voor die browser te wijzigen. 


**Internet Explorer (IE) en Microsoft Edge**

IE en Microsoft Edge gebruiken de **regio-instellingen** die zijn geconfigureerd in de optie **Klokken, Taal** en Regio in het Configuratiescherm. 


#### <a name="known-issues-with-regional-formats"></a>Bekende problemen met regionale indelingen

**Datum- en tijdnotaties**<br>
Er zijn enkele bekende problemen met de tijd- en datumnotatie. Als u uw regionale instellingen configureert op iets anders dan de ondersteunde indelingen, is het mogelijk dat de portal uw instellingen niet correct wedt.

De volgende datum- en tijdnotaties worden ondersteund:
- Datumnotatie MM/dd/yyyy
- Datumnotatie dd/MM/yyyy
- Tijdnotatie hh:mm:ss (12 uursnotatie)

De volgende datum- en tijdindelingen worden momenteel niet ondersteund:
- Datumnotatie yyyy-MM-dd
- Datumnotatie dd-MMM-yy
- Datumnotatie dd/MM/yy
- Datumnotatie MM/dd/yy
- Datumnotatie met yy. Toont alleen yyyy.
- Tijdnotatie HH:mm:ss (24 uursnotatie)

**Decimaal symbool dat wordt gebruikt in getallen**<br>
Het gebruikte decimale symbool is altijd een punt,  zelfs als een komma is geselecteerd in de instellingen voor de notatie Getallen in **regio-instellingen.** 15,5K wordt bijvoorbeeld weergegeven als 15,5K.


