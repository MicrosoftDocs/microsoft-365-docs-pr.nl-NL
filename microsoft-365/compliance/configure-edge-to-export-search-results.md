---
title: Het eDiscovery-exporthulpmiddel gebruiken in Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: U moet ondersteuning ClickOnce om de nieuwste versie van Microsoft Edge te kunnen gebruiken om zoekresultaten te downloaden van Inhoud zoeken en eDiscovery in het beveiligings- en compliancecentrum.
ms.openlocfilehash: 60f42d2884c56aaff40bc0a6a979e99698a3cd2e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2020
ms.locfileid: "52161519"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a>Het eDiscovery-exporthulpmiddel gebruiken in Microsoft Edge

Als gevolg van recente wijzigingen in de nieuwste versie van Microsoft Edge is ClickOnce standaard niet meer ingeschakeld. Als u het hulpprogramma voor eDiscovery-export wilt blijven gebruiken om zoekresultaten voor Inhoud zoeken of eDiscovery te downloaden, moet u [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) gebruiken of ClickOnce-ondersteuning inschakelen in de nieuwste versie van Microsoft Edge.

## <a name="enable-clickonce-support-in-microsoft-edge"></a>Ondersteuning ClickOnce inschakelen in Microsoft Edge

1. Ga Microsoft Edge naar **edge://flags/#edge-click-once.**

2. Als de bestaande waarde is ingesteld op **Standaard of** **Uitgeschakeld** in de vervolgkeuzelijst, wijzigt u deze in **Ingeschakeld.**

   ![Selecteer Ingeschakeld in vervolgkeuzelijst](../media/ClickOnceimage1.png)

3. Schuif omlaag naar de onderkant van het browservenster en klik op Opnieuw starten **om** Edge opnieuw te starten.

   ![Klik op Opnieuw starten](../media/ClickOnceimage2.png)

**Opmerking:** Organisaties kunnen groepsbeleid gebruiken om de ondersteuning ClickOnce uitschakelen. Als u wilt controleren of er een organisatiebeleid is voor ClickOnce ondersteuning, gaat u naar **edge://policy.** In de volgende schermafbeelding ziet u ClickOnce is ingeschakeld in de hele organisatie. Als deze beleidswaarde is ingesteld op **onwaar,** moet u contact opnemen met een beheerder in uw organisatie.

![Lijst met edge-organisatiebeleid](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a>Het hulpprogramma voor eDiscovery-export installeren en uitvoeren

1. Klik **op Resultaten downloaden** op de flyoutpagina van een export in Inhoud zoeken of een eDiscovery-zaak.

   ![Klik op Resultaten downloaden op de flyoutpagina om zoekresultaten te downloaden](../media/ClickOnceExport1.png)

2. U wordt gevraagd of u het hulpprogramma wilt starten, klik op **Openen.**

   ![Klik op Openen om het eDiscovery-exporthulpmiddel te starten](../media/ClickOnceimage4.png)

   Als het eDiscovery-exportprogramma niet is geïnstalleerd, wordt u gevraagd om een beveiligingswaarschuwing, 

   ![Klik op Installeren om het hulpprogramma voor eDiscovery-export te installeren](../media/ClickOnceimage5.png)

3. Klik op **Installeren**. Nadat het hulpprogramma is geïnstalleerd, wordt het exportprogramma automatisch uitgevoerd.

Zie de volgende onderwerpen voor meer informatie:

- [Inhoudszoekresultaten exporteren](export-search-results.md)

- [Experimentvlaggen inschakelen in Microsoft Edge](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
