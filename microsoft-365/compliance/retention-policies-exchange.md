---
title: Meer informatie over retentie voor Exchange
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Lees hoe retentie werkt voor Exchange.
ms.openlocfilehash: 0763b8bdab75ac76197b8c89f187bb573a3e4bb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162081"
---
# <a name="learn-about-retention-for-exchange"></a>Meer informatie over retentie voor Exchange

De informatie in dit artikel is een aanvulling op [Meer informatie over retentie](retention.md), omdat deze informatie specifiek is voor Exchange.  Zie voor andere workloads:

- [Meer informatie over retentie voor SharePoint en OneDrive](retention-policies-sharepoint.md)
- [Meer informatie over retentie voor Microsoft Teams](retention-policies-teams.md)
- [Meer informatie over retentie voor Yammer](retention-policies-yammer.md)

## <a name="whats-included-for-retention-and-deletion"></a>Wat is inbegrepen voor retentie en verwijdering?

De volgende Exchange-items kunnen worden behouden of verwijderd door het gebruiken van bewaarbeleid en retentielabels: e-mailberichten (inclusief concepten) met eventuele bijlagen, notities en taken als ze een einddatum hebben. 

Agenda-items die een einddatum hebben, worden ondersteund voor bewaarbeleidsregels, maar niet voor retentielabels.

Contacten, en taken en agenda-items die geen einddatum hebben worden niet ondersteund.

Andere items die zijn opgeslagen in een mailbox, zoals Skype- en Teams-berichten, vallen niet binnen het bewaarbeleid of -labels voor Exchange. Voor deze items gelden aparte bewaarbeleidsregels.

## <a name="how-retention-works-for-exchange"></a>Hoe retentie werkt voor Exchange

Zowel postvakken als openbare mappen gebruiken de [map Herstelbare items](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) voor het behouden van items. Alleen mensen met eDiscovery-machtigingen kunnen items in de map Herstelbare items van een andere gebruiker bekijken.
  
Als iemand een bericht verwijdert in een andere map dan de map Verwijderde items, wordt het bericht standaard verplaatst naar de map Verwijderde items. Als iemand een bericht verwijdert in de map Verwijderde items, wordt het bericht standaard verplaatst naar de map Herstelbare items. Een gebruiker kan in iedere map echter een item voorlopig verwijderen (Shift+Delete) waardoor de map Verwijderde items wordt overgeslagen en het item direct naar de map Herstelbare items wordt verplaatst.
  
Als u bewaarinstellingen toepast op Exchange-gegevens, worden de items in de map Herstelbare items regelmatig door een timeropdracht geanalyseerd. Als een item niet overeenkomt met de regels van ten minste één bewaarbeleidsregel of retentielabel, wordt het item permanent verwijderd (definitief verwijderd) uit de map Herstelbare items.

Het uitvoeren van een timeropdracht kan tot zeven dagen duren en de Exchange-locatie moet ten minste 10 MB bevatten.
  
Als een gebruiker probeert de eigenschappen van een postvakitem – zoals het onderwerp, de hoofdtekst, de bijlagen, de afzenders, de geadresseerden, de verzenddatum of de ontvangstdatum te wijzigen, wordt er een kopie van het origineel opgeslagen in de map Herstelbare items voordat de wijziging wordt vastgelegd. Deze actie wordt uitgevoerd bij elke volgende wijziging. Aan het einde van de retentieperiode worden kopieën in de map Herstelbare items permanent verwijderd.

Nadat bewaarinstellingen zijn toegepast op Exchange-inhoud, is de route die de inhoud aflegt afhankelijk van de bewaarinstellingen: bewaren en verwijderen, alleen bewaren of alleen verwijderen.

Als de geselecteerde bewaarinstelling bewaren en verwijderen is:

![Diagram van de retentiestroom in e-mail- en openbare mappen](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. **Als het item is gewijzigd of permanent is verwijderd** door de gebruiker (met SHIFT+DELETE of verwijderd uit de map Verwijderde items) tijdens de retentieperiode: het item wordt verplaatst (of na wijzigen gekopieerd) naar de map Herstelbare items. Daar analyseert en identificeert een timeropdracht regelmatig de items waarvan de retentieperiode is verstreken. Deze items worden permanent verwijderd binnen 14 dagen na het einde van de retentieperiode. Houd er rekening mee dat de instelling standaard 14 dagen is, maar dat deze kan worden verlengd tot 30 dagen.

2. **Als het item niet is gewijzigd of verwijderd** tijdens de retentieperiode: Hetzelfde proces wordt regelmatig toegepast op alle mappen in het postvak waarbij items worden geïndentificeerd waarvan de retentieperiode is verlopen. Deze items worden permanent verwijderd binnen 14 dagen na het einde van de retentieperiode. Houd er rekening mee dat de instelling standaard 14 dagen is, maar dat deze kan worden verlengd tot 30 dagen. 

Als de bewaarinstellingen alleen bewaren of alleen verwijderen zijn, is de route die de inhoud aflegt een variatie van bewaren en verwijderen:

### <a name="content-paths-for-retain-only-retention-settings"></a>Inhoudsroutes voor retentie-instellingen voor alleen bewaren

1. **Als het item is gewijzigd of verwijderd** tijdens de retentieperiode: Er wordt een kopie van het originele item gemaakt in de map Herstelbare items die wordt bewaard tot het einde van de retentieperiode. Daarna wordt het item in de map Herstelbare items binnen 14 dagen na het verlopen ervan definitief verwijderd. 

2. **Als het item niet wordt gewijzigd of verwijderd** tijdens de bewaarperiode: Er gebeurt voor en na de bewaarperiode niets. Het document blijft op de oorspronkelijke locatie staan.

### <a name="content-paths-for-delete-only-retention-settings"></a>Inhoudsroutes voor retentie-instellingen voor alleen verwijderen

1. **Als het item niet is verwijderd** tijdens de geconfigureerde periode: aan het einde van de in het bewaarbeleid geconfigureerde periode wordt het item verplaatst naar de map Herstelbare items. 

2. **Als het item is verwijderd** tijdens de geconfigureerde periode: het item wordt onmiddellijk verplaatst naar de map Herstelbare items. Als een gebruiker het item daar verwijdert of de map Herstelbare items leegmaakt, is het item definitief verwijderd. In alle andere gevallen wordt het item definitief verwijderd nadat het 14 dagen is bewaard in de map Herstelbare items. 

## <a name="when-a-user-leaves-the-organization"></a>Wanneer een gebruiker de organisatie verlaat 

Wanneer een gebruiker uw organisatie verlaat en het postvak van de gebruiker is opgenomen in een bewaarbeleid, wordt het postvak een inactief postvak wanneer het Microsoft 365-account van de gebruiker wordt verwijderd. Een bewaarbeleid dat van toepassing was op een postvak voordat het inactief werd, blijft van toepassing op het inactieve postvak en de inhoud blijft beschikbaar voor een eDiscovery-zoekopdracht. Zie voor meer informatie [Inactive postvakken in Exchange Online](inactive-mailboxes-in-office-365.md).

## <a name="configuration-guidance"></a>Configuratie-richtlijnen

Zie [Aan de slag met bewaarbeleid en retentielabels](get-started-with-retention.md) als het configureren van retentie in Microsoft 365 nieuw voor u is.

Zie de volgende instructies als u een bewaarbeleid of retentielabel wilt configureren voor Exchange:
- [Bewaarbeleid maken en configureren](create-retention-policies.md)
- [Retentielabels maken en deze toepassen in apps](create-apply-retention-labels.md)
- [Een retentielabel automatisch toepassen op inhoud](apply-retention-labels-automatically.md)