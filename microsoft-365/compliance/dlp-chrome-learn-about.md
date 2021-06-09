---
title: Meer informatie over Microsoft compliance-extensie
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: De Microsoft-compliance-extensie is een uitbreiding van de controle en het beheer van bestandsactiviteiten en beschermende maatregelen, voor de Google Chrome-browser
ms.openlocfilehash: cf7a3cd2e26f2e7d7a116e4a609f98aeea78be19
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843804"
---
# <a name="learn-about-the-microsoft-compliance-extension"></a>Meer informatie over Microsoft compliance-extensie

[Eindpunt-DLP (preventie van gegevensverlies)](endpoint-dlp-learn-about.md) is een uitbreiding voor de activiteitencontrole en beveiligingsmogelijkheden van [Microsoft 365 DLP (preventie van gegevensverlies)](dlp-learn-about-dlp.md) voor gevoelige items op Windows 10-apparaten. Zodra apparaten zijn geregistreerd bij de Microsoft 365-complianceoplossingen, wordt de informatie over wat gebruikers met gevoelige items doen, zichtbaar in [Activiteitenverkenner](data-classification-activity-explorer.md) en kunt u beschermende maatregelen voor deze items afdwingen via [DLP-beleid](create-test-tune-dlp-policy.md).

Zodra de Microsoft-compliance-extensie is geïnstalleerd op een Windows 10-apparaat, kunnen organisaties controleren wanneer een gebruiker een gevoelig item probeert te openen of te uploaden naar een cloudservice met behulp van Google Chrome. Vervolgens kunnen beschermende maatregelen worden afgedwongen via DLP.  

## <a name="activities-you-can-monitor-and-take-action-on"></a>Activiteiten die u kunt controleren en waarvoor u maatregelen kunt nemen

Met de Microsoft-compliance-extensie kunt u de typen activiteiten die gebruikers uitvoeren op gevoelige items, controleren en beheren op apparaten met Windows 10.

activiteit |beschrijving  | ondersteunde beleidsacties|
|---------|---------|---------|
|bestand is gekopieerd naar de cloud  | Hiermee wordt gedetecteerd wanneer een gebruiker probeert om een gevoelig item te uploaden naar een beperkt servicedomein via de Chrome-browser |controleren, blokkeren|
|bestand is afgedrukt  |Hiermee wordt gedetecteerd wanneer een gebruiker een gevoelig item dat is geopend in de Chrome-browser, probeert af te drukken op een lokale printer of een netwerkprinter |controleren, blokkeren met overschrijven, blokkeren|
|bestand is gekopieerd naar het klembord |Hiermee wordt gedetecteerd wanneer een gebruiker informatie uit een gevoelig item dat wordt weergegeven in de Chrome-browser, probeert te kopiëren en vervolgens te plakken in een andere app, of in een ander proces of item. |controleren, blokkeren met overschrijven, blokkeren|
|bestand is gekopieerd naar verwisselbare opslag    | Hiermee wordt gedetecteerd wanneer een gebruiker een gevoelig item, of gevoelige informatie uit een gevoelig item dat is geopend in de Chrome-browser, probeert te kopiëren naar een verwisselbaar medium of USB-apparaat |controleren, blokkeren met overschrijven, blokkeren|
|bestand is gekopieerd naar netwerkshare  |Hiermee wordt gedetecteerd wanneer een gebruiker een gevoelig item, of gevoelige informatie uit een gevoelig item dat is geopend in de Chrome-browser, probeert te kopiëren naar een netwerkshare of een toegewezen netwerkstation.|controleren, blokkeren met overschrijven, blokkeren |

## <a name="deployment-process"></a>Implementatieproces
1. [Aan de slag met Eindpunt-DLP](endpoint-dlp-getting-started.md)
2. [Hulpprogramma’s en methoden voor onboarding voor Windows 10-apparaten](dlp-configure-endpoints.md)
3. [Installeer de extensie op uw Windows 10-apparaten](dlp-chrome-get-started.md)
4. [Maak en bewerk DLP-beleidsregels](create-test-tune-dlp-policy.md) die uploaden naar een cloudservice en het verkrijgen van toegang via niet-toegestane browseracties beperken, en pas deze regels toe op uw Windows 10-apparaten

## <a name="next-steps"></a>Volgende stappen

Raadpleeg [Aan de slag met de Microsoft-compliance-extensie](dlp-chrome-get-started.md) voor de volledige procedures en scenario's voor de implementatie.

## <a name="see-also"></a>Zie ook

- [Aan de slag met de Microsoft compliance-extensie](dlp-chrome-get-started.md)
- [Meer informatie over Microsoft 365 Eindpunt-DLP](endpoint-dlp-learn-about.md)
- [Aan de slag met Microsoft Eindpunt-DLP](endpoint-dlp-getting-started.md)
- [Eindpunt-DLP gebruiken](endpoint-dlp-using.md)
- [Meer informatie over preventie van gegevensverlies](dlp-learn-about-dlp.md)
- [Een DLP-beleid maken, testen en afstemmen](create-test-tune-dlp-policy.md)
- [Aan de slag met Activity Explorer](data-classification-activity-explorer.md)
- [Microsoft Defender voor Eindpunt](/windows/security/threat-protection/)
- [Insider Risk-beheer](insider-risk-management.md)
