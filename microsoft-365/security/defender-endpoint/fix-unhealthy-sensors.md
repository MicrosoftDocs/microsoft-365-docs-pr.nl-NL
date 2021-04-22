---
title: Ongezonde sensoren in Microsoft Defender voor eindpunt oplossen
description: Fix device sensors that are reporting as misconfigured or inactive so that the service receives data from the device.
keywords: verkeerd geconfigureerd, inactief, fix sensor, sensor health, no sensor data, sensor data, sensor data, impaired communications, communication
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
ms.date: 11/06/2020
ms.technology: mde
ms.openlocfilehash: c4cdc80170b49a111f476d2d17222c41e2b5c55f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935363"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a>Ongezonde sensoren in Microsoft Defender voor eindpunt oplossen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-fixsensor-abovefoldlink)

Apparaten die zijn gecategoriseerd als onjuist geconfigureerd of inactief, kunnen worden gemarkeerd vanwege verschillende oorzaken. In deze sectie worden enkele uitleg gegeven over de oorzaak van de mogelijke inactiviteit of onjuiste configuratie van een apparaat.

## <a name="inactive-devices"></a>Inactieve apparaten

Een inactief apparaat wordt niet per se gemarkeerd vanwege een probleem. De volgende acties op een apparaat kunnen ertoe leiden dat een apparaat wordt gecategoriseerd als inactief:

### <a name="device-is-not-in-use"></a>Apparaat is niet in gebruik

Als het apparaat om welke reden dan ook niet langer dan zeven dagen is gebruikt, blijft het in de portal de status 'Inactief'.

### <a name="device-was-reinstalled-or-renamed"></a>Apparaat is opnieuw geïnstalleerd of hernoemd
Een opnieuw geïnstalleerd of hernoemd apparaat genereert een nieuwe apparaatentiteit in het Microsoft Defender-beveiligingscentrum. De vorige apparaatentiteit blijft behouden met de status 'Inactief' in de portal. Als u een apparaat opnieuw hebt geïnstalleerd en het Defender for Endpoint-pakket hebt geïmplementeerd, zoekt u naar de naam van het nieuwe apparaat om te controleren of het apparaat normaal rapporteert.

### <a name="device-was-offboarded"></a>Apparaat is offboarded
Als het apparaat buiten het bord is geplaatst, wordt het nog steeds weergegeven in de lijst met apparaten. Na zeven dagen moet de status van het apparaat worden gewijzigd in inactief.

### <a name="device-is-not-sending-signals"></a>Apparaat verstuurt geen signalen
Als het apparaat om welke reden dan ook geen signalen meer dan zeven dagen naar een van de Kanalen van Microsoft Defender voor Eindpunt verstuurt, inclusief voorwaarden die onder verkeerd geconfigureerde apparatenclassificatie vallen, kan een apparaat als inactief worden beschouwd. 

Verwacht u dat een apparaat de status 'Actief' heeft? [Open een ondersteuningsticket](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).

## <a name="misconfigured-devices"></a>Onjuist geconfigureerde apparaten
Verkeerd geconfigureerde apparaten kunnen verder worden geclassificeerd als:
- Communicatie met verminderde werking
- Geen sensorgegevens

### <a name="impaired-communications"></a>Communicatie met verminderde werking
Deze status geeft aan dat er beperkte communicatie is tussen het apparaat en de service.

De volgende voorgestelde acties kunnen helpen bij het oplossen van problemen met een verkeerd geconfigureerd apparaat met communicatieproblemen:

- [Controleer of het apparaat een internetverbinding heeft](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  Voor de Microsoft Defender voor eindpunten-sensor moet Microsoft Windows HTTP (WinHTTP) sensorgegevens rapporteren en communiceren met de Microsoft Defender voor Eindpunt-service.

- [Clientconnectiviteit verifiëren met URL's van Microsoft Defender voor endpoint-service](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  Controleer of de proxyconfiguratie is voltooid, of WinHTTP kan ontdekken en communiceren via de proxyserver in uw omgeving, en of de proxyserver verkeer toestaat naar de URL's van de Microsoft Defender-service voor eindpunten.

Als u corrigerende acties hebt ondernomen en de apparaatstatus nog steeds niet is geconfigureerd, [opent u een ondersteuningsticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).

### <a name="no-sensor-data"></a>Geen sensorgegevens
Een verkeerd geconfigureerd apparaat met de status 'Geen sensorgegevens' heeft communicatie met de service, maar kan slechts gedeeltelijke sensorgegevens rapporteren.
Volg theses actions to correct known issues related to a misconfigured device with status 'No sensor data':

- [Controleer of het apparaat een internetverbinding heeft](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  Voor de Microsoft Defender voor eindpunten-sensor moet Microsoft Windows HTTP (WinHTTP) sensorgegevens rapporteren en communiceren met de Microsoft Defender voor Eindpunt-service.

- [Clientconnectiviteit verifiëren met URL's van Microsoft Defender voor endpoint-service](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  Controleer of de proxyconfiguratie is voltooid, of WinHTTP kan ontdekken en communiceren via de proxyserver in uw omgeving, en of de proxyserver verkeer toestaat naar de URL's van de Microsoft Defender-service voor eindpunten.

- [Controleren of de diagnostische gegevensservice is ingeschakeld](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
Als de apparaten niet correct rapporteren, moet u mogelijk controleren of de diagnostische gegevensservice van Windows 10 is ingesteld op automatisch starten en wordt uitgevoerd op het eindpunt.

- [Ervoor zorgen dat Microsoft Defender Antivirus niet is uitgeschakeld door beleid](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
Als op uw apparaten een antimalwareclient van derden wordt uitgevoerd, moet het ELAM-stuurprogramma (Antimalware) van Microsoft Defender Antivirus Early Launch (ELAM) worden ingeschakeld.

Als u corrigerende acties hebt ondernomen en de apparaatstatus nog steeds niet is geconfigureerd, [opent u een ondersteuningsticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).

## <a name="see-also"></a>Zie ook
- [Status van sensor controleren in Microsoft Defender voor eindpunt](check-sensor-status.md)
