---
title: Microsoft 365 omgaan met gegevensbeschadiging
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: In dit artikel worden de beschadigde gegevens in Microsoft 365 besproken en de inspanningen van Microsoft getroffen om gegevens te voorkomen en te herstellen.
ms.openlocfilehash: fabecf8e368813e2f895669edc19c3f74e305c35
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689137"
---
# <a name="dealing-with-data-corruption-in-microsoft-365"></a>Omgaan met gegevensbeschadiging in Microsoft 365

Een van de problematische aspecten van het uitvoeren van een grootschalige cloudservice is het afhandelen van beschadigde gegevens, gelet op het grote volume van gegevens en onafhankelijke systemen. Beschadigde gegevens kunnen worden veroorzaakt door:

- Bugs van toepassingen of infrastructuur, waarbij sommige of alle toepassingsstatus beschadigd raken
- Hardwareproblemen die tot gegevensverlies leiden of een onvermogen om gegevens te lezen
- Menselijke operationele fouten
- Kwaadwillende hackers en disgruntled-medewerkers
- Incidenten in externe services die tot enig verlies van gegevens leiden

Aangezien een hogere tolerantie voor de integriteit van gegevens minder gegevens veroorzaakt, heeft Microsoft ingebouwde beveiligingsmechanismen voor Microsoft 365 om te voorkomen dat een bestand wordt beschadigd, en systemen en processen waarmee wij gegevens kunnen herstellen. Er bestaan controles en processen binnen de verschillende fasen van het updateproces voor de ontwikkeling van de productiviteit tegen beschadiging van gegevens, waaronder:

- Systeemontwerp
- Code organisatie en structuur
- Code beoordeling
- Unit tests, integratie tests en systeemtests
- Tests/poorten voor reis draden

In Microsoft 365-productieomgevingen zorgt peer replicatie tussen datacenters ervoor dat er altijd meerdere Live kopieën van gegevens zijn. Standaardafbeeldingen en scripts worden gebruikt om verloren servers te herstellen, en gerepliceerde gegevens worden gebruikt om klantgegevens te herstellen. Vanwege de ingebouwde gegevens tolerantie controles en-processen worden in Microsoft reservekopieën van Microsoft 365 Information System Documentation (waaronder documentatie voor beveiliging) bijgehouden, met behulp van de ingebouwde replicatie in SharePoint Online en ons programma voor interne code-opslag, bron depot. Systeemdocumentatie wordt opgeslagen in SharePoint Online en bron depot bevat systeem-en toepassings afbeeldingen. Zowel SharePoint Online als bron-depot gebruiken versiebeheer en worden in de nabije werkelijke termijn gerepliceerd.
