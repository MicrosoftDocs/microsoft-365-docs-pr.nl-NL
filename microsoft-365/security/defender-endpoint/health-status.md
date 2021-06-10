---
title: Statusproblemen van agent onderzoeken
description: Meer informatie over de waarden die worden geretourneerd bij het uitvoeren van de opdracht mdatp-status
keywords: mdatp-status, opdracht, status, status, opdracht, onboardingstatus
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
ms.openlocfilehash: acc75a931cb14a7aab729c09a7b835fb9f26d1d1
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281112"
---
# <a name="investigate-agent-health-issues"></a>Statusproblemen van agent onderzoeken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


In de volgende tabel vindt u informatie over de waarden die worden geretourneerd wanneer u de `mdatp health` opdracht en de bijbehorende beschrijvingen uit te voeren.

| Waarde | Beschrijving |
|-|-|
| automatic_definition_update_enabled | Is waar als automatische antivirusdefinitie-updates zijn ingeschakeld, anders onwaar. |
|  cloud_automatic_sample_submission_consent | Huidige voorbeeldinzendingsniveau. Kan een van de volgende waarden zijn:     <br><br>  - **Geen:** Er worden geen verdachte steekproeven ingediend bij Microsoft.  <br> <br>     - **Safe:** Alleen verdachte steekproeven die geen persoonsgegevens bevatten, worden automatisch verzonden. Dit is de standaardwaarde voor deze instelling.    <br> <br>   - **Alle**: Alle verdachte steekproeven worden verzonden naar Microsoft.   |
| cloud_diagnostic_enabled | True als optionele diagnostische gegevensverzameling is ingeschakeld, anders onwaar. Zie Microsoft [Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=827576)voor meer informatie over Defender voor Eindpunt en andere producten en services, zoals Microsoft Defender Antivirus en Windows 10. |
| cloud_enabled | Is waar als beveiliging in de cloud is ingeschakeld, anders onwaar. |
| conflicting_applications | Lijst met toepassingen die mogelijk conflicteren met Microsoft Defender voor Eindpunt. Deze lijst bevat, maar is niet beperkt tot andere beveiligingsproducten en andere toepassingen die compatibiliteitsproblemen veroorzaken. |
| definitions_status | Status van antivirusdefinities. |
| definitions_updated | Datum en tijd van de laatste antivirusdefinitieupdate. |
| definitions_updated_minutes_ago | Aantal minuten sinds de laatste antivirusdefinitieupdate. |
| definitions_version | Antivirusdefinitieversie. |
| edr_client_version | Versie van de EDR client die op het apparaat wordt uitgevoerd. |
| edr_configuration_version | EDR configuratieversie. |
| edr_device_tags | Lijst met tags die aan het apparaat zijn gekoppeld. |
| edr_group_ids | Groeps-id waar het apparaat aan is gekoppeld. |
| edr_machine_id | Apparaataanduiding die wordt gebruikt in Microsoft Defender-beveiligingscentrum. |
| engine_version | Versie van de antivirusprogramma. |
| gezond | Waar als het product gezond is, anders onwaar. |
| gelicentieerd | Waar als het apparaat is aan boord van een tenant, anders onwaar. |
| log_level | Huidig logboekniveau voor het product. |
| machine_guid | Unieke machine-id die door het antivirusonderdeel wordt gebruikt. |
| network_protection_status                 | Status van het netwerkbeveiligingsonderdeel (alleen macOS). Kan een van de volgende waarden zijn:       <br> <br>- **starten** - Netwerkbeveiliging wordt in de startblokken  <br> <br>     - **failed_to_start** - Netwerkbeveiliging kan niet worden gestart vanwege een fout   <br> <br>    - **gestart** - Netwerkbeveiliging wordt momenteel uitgevoerd op het apparaat     <br> <br>  - **opnieuw opstarten** - Netwerkbeveiliging wordt momenteel opnieuw gestart   <br> <br>    - **stoppen** - Netwerkbeveiliging stopt     <br> <br>  - **gestopt** - Netwerkbeveiliging wordt niet uitgevoerd |
| org_id | Organisatie waar het apparaat aan is onboarded. Als het apparaat nog niet is onboarded voor een organisatie, wordt dit niet afgedrukt. Zie Onboard to Microsoft Defender for Endpoint (Onboard [to Microsoft Defender for Endpoint)](onboarding.md)voor meer informatie over onboarding. |
| passive_mode_enabled | Is waar als het antivirusonderdeel is ingesteld op uitvoeren in de passieve modus, anders onwaar. |
| product_expiration | Datum en tijd waarop de huidige productversie het einde van de ondersteuning bereikt. |
| real_time_protection_available | Is waar als het realtimebeveiligingsonderdeel gezond is, anders onwaar. |
| real_time_protection_enabled | Is waar als realtime antivirusbeveiliging is ingeschakeld, anders onwaar. |
| real_time_protection_subsystem | Subsysteem dat wordt gebruikt om realtime-beveiliging te bieden. Als realtimebeveiliging niet werkt zoals verwacht, is dit niet beschikbaar. |
| release_ring | Releasering. Zie Implementatieringen voor [meer informatie.](deployment-rings.md) |