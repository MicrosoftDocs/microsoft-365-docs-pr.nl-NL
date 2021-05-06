---
title: Bewaringsmeldingen beheren
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Gebruik de communicatiewerkstroom in Advanced eDiscovery om de status van uw meldingen over wettelijke wachtposities bij te houden en deze zo nodig bij te werken en opnieuw te sturen.
ms.openlocfilehash: 8852bfd1651e1855d276b60ba6fac35c378d4631
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/26/2020
ms.locfileid: "52161443"
---
# <a name="manage-hold-notifications"></a>Bewaringsmeldingen beheren

Nadat u de meldingswerkstroom voor wettelijke wachtpositie hebt gestart, kunt u de communicatiewerkstroom in Advanced eDiscovery gebruiken om de status van uw communicatie bij te houden. Het tabblad Communicatie bevat een lijst met alle meldingen in uw Advanced eDiscovery geval. U kunt details zien, zoals het aantal bewaarders dat is toegewezen of dat de kennisgeving heeft bevestigd.

## <a name="monitor-acknowledgments"></a>Bevestigingen controleren

Nadat u een communicatie hebt geselecteerd op het tabblad **Communicatie,** kunt u een lijst bekijken met bewaarders die een kennisgeving hebben bevestigd. 

1. Ga in het compliancecentrum naar **eDiscovery > Advanced eDiscovery.**

2. Selecteer een zaak en klik vervolgens op **het tabblad** Communicatie.

3. Selecteer een communicatie om de **flyoutpagina voor communicatie van beheerders** weer te geven.

Een lijst met beheerders die aan de geselecteerde communicatie zijn gekoppeld, wordt weergegeven op de pagina communicatie flyout. Op deze pagina ziet u ook inzichten en over het aantal ontvangstbevestigingen en het aantal openstaande ontvangsten. Op de pagina ziet u ook welke bewaarders een bevestiging hebben verzonden dat ze de bewaarmelding hebben ontvangen.

## <a name="re-send-a-hold-notice"></a>Een wachtbericht opnieuw verzenden

Soms raken beheerders e-mailberichten kwijt in hun dagelijkse werk. Of voor een langlopende rechtszaken kan een bewaarder contact opnemen met u of anderen en verzoeken u een kennisgeving opnieuw te verzenden. Als u de communicatiewerkstroom voor kennisgevingen voor juridische ingebruikgevingen beheert, moet u mogelijk een bericht opnieuw verzenden om deze terug te brengen naar de 'bovenkant van het postvak van een gebruiker'.

Een bewaartermijn opnieuw verzenden naar een bewaarder:

1. Selecteer Advanced eDiscovery geval en klik vervolgens op **het tabblad** Communicatie.

2. Selecteer een communicatie om de **flyoutpagina voor communicatie van beheerders** weer te geven.

3. Klik **op Meer > Bericht over het opnieuw verzenden van de wacht.**

4. Selecteer op **de flyoutpagina** Bericht over wacht houden opnieuw verzenden de bewaarders die u wilt verzenden en typ een optionele reden.

5. Klik **op Opnieuw verzenden om** de melding naar de geselecteerde bewaarders te verzenden.

Als een bewaarder de melding voor het in de wacht houden niet heeft bevestigd, worden de herinnerings- en escalatiewerkstroom opnieuw gestart. Als een bewaarder de bewaartermijn heeft bevestigd, ontvangt de bewaarder een kopie van de oorspronkelijke bewaartermijn.

> [!NOTE]
> U kunt alleen een melding over een wettelijke bewaarplicht opnieuw sturen aan bewaarders die aan de communicatie zijn toegewezen. 

## <a name="update-preservation-requirements"></a>Bewaarvereisten bijwerken
  
Naarmate het geval vordert, moeten bewaarders mogelijk aanvullende of minder gegevens bewaren dan eerder is geïnstrueerd. In eDiscovery-termen moet u de wachttermijn opnieuw uitgeven met bijgewerkte inhoud.

De inhoud van de eerste aanzegtermijn bijwerken:

1. Selecteer Advanced eDiscovery geval en klik vervolgens op **het tabblad** Communicatie.

2. Selecteer de wachtbezorging die u wilt bijwerken en klik **op Bewerken** op de **flyoutpagina van de** bewaarder.

3. Klik in de wizard **Communicatie** bewerken op **Portalinhoud** definiëren in het linkerdeelvenster van de wizard en werk de inhoud van de melding bij.

4. Klik op **Opslaan**.

De heruitgiftemelding wordt verzonden naar alle bewaarders die zijn toegewezen aan de melding van de wettelijke bewaartermijn. Als de melding Herinnering of Escalatie is ingeschakeld, worden de werkstromen voor deze typen kennisgevingen bovendien opnieuw gestart.

## <a name="update-legal-hold-notifications-and-settings"></a>Meldingen en instellingen voor juridische wacht houden bijwerken

Wanneer u de inhoud of instellingen van de melding Uitgifte, Release, Heruitgave, Herinnering of Escalatie bijwerkt, zijn deze wijzigingen van toepassing op alle toekomstige communicatie die door de werkstroom wordt gegenereerd.

## <a name="more-information"></a>Meer informatie

- [Beheerders toevoegen aan een case](add-custodians-to-case.md)

- [Een kennisgeving voor een wettelijke wachttermijn maken](create-hold-notification.md)

- [Een bewaringsmelding bevestigen](acknowledge-hold-notification.md)
