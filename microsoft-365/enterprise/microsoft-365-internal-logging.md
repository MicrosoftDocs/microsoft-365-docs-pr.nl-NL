---
title: Microsoft 365 interne logboekregistratie voor Microsoft 365 engineering
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
description: In dit artikel vindt u een beschrijving van de manier waarop interne logboekregistratie voor Microsoft 365 engineering teams werkt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b4c4b1db876a6b68ec852adbbd51afe7386a1855
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695747"
---
# <a name="internal-logging-for-microsoft-365-engineering"></a>Interne logboekregistratie voor Microsoft 365 engineering

Naast de gebeurtenissen en logboekgegevens die voor klanten beschikbaar zijn, is er ook een intern logboek met gegevensverzameling voor de beheerder dat beschikbaar is voor Microsoft 365-technici bij Microsoft. Veel verschillende typen logboekgegevens worden geüpload van Microsoft 365-servers naar een interne, grote data-service service genaamd Cosmos. Elk service team uploadt auditlogboeken van de betreffende servers in de Cosmos-database voor aggregatie en analyse. Deze gegevensoverdracht vindt plaats via een door FIPS 140-2 gevalideerde TLS-verbinding op specifiek goedgekeurde poorten en protocollen met een eigen automatiserings programma genaamd Office Data loader (ODL). De hulpmiddelen in Microsoft 365 voor het verzamelen en verwerken van controlerecords zijn niet toegestaan permanente of onherstelbare wijzigingen in de oorspronkelijke audit record-inhoud of de tijd volgorde.

Service teams gebruiken Cosmos als centrale opslagruimte voor het uitvoeren van toepassingen, voor het meten van de systeemprestaties en de operationele prestaties, en het zoeken naar abnormale en patronen die problemen kunnen voordoen. Elk service team uploadt de basislijn van Logboeken in Cosmos, afhankelijk van wat ze willen analyseren, wat vaak omvat:

- Gebeurtenislogboeken
- AppLocker-logboeken
- Prestatiegegevens
- System Center Data
- Details van oproep detailrecords
- Ervaring met gegevenskwaliteit
- Logboeken van IIS Web Server
- SQL Server-logboeken
- Syslog-gegevens
- Beveiligingscontrole logboeken

Voordat u gegevens uploadt naar Cosmos, wordt in de ODL-toepassing een reinigings service gebruikt voor het weergeven van velden die klantgegevens bevatten, zoals Tenant informatie en identificatiegegevens van eindgebruikers, en vervangt u deze velden door een hashwaarde. De logboeken geanonimiseerde en hash worden herschreven en vervolgens geüpload naar Cosmos. Service teams voeren query's met een bereik op basis van hun gegevens in Cosmos voor correlatie, waarschuwingen en rapportage. De periode voor het bewaren van controlelogboekgegevens in Cosmos wordt bepaald door de service teams. de meeste gegevens van het auditlogboek worden gedurende 90 dagen of langer bewaard voor de ondersteuning van beveiligingsincidenten en om te voldoen aan de nalevingsvereisten.

Toegang tot Microsoft 365-gegevens die zijn opgeslagen in Cosmos, is beperkt tot geautoriseerd personeel. Microsoft beperkt het beheer van controlefuncties voor de beperkte subset van service teamleden die verantwoordelijk zijn voor de controle functionaliteit. Deze teamleden hebben geen mogelijkheid om gegevens te wijzigen of te verwijderen uit Cosmos, en alle wijzigingen aan logboek mechanismen voor Cosmos worden opgenomen en gecontroleerd.

Elk service team opent de logboekgegevens voor analyse door bepaalde toepassingen te machtigen voor het uitvoeren van specifieke analyses. Het Microsoft 365-beveiligingsteam gebruikt bijvoorbeeld gegevens van Cosmos via een ingebouwde parser van een gebeurtenislogboek waarmee u op de Microsoft 365-productieomgeving informatie over mogelijke verdachte activiteiten kunt afstemmen, waarschuwen en rapporten kunt genereren. De rapporten van deze gegevens worden gebruikt om beveiligingsproblemen op te lossen en om de algehele prestaties van de service te verbeteren. Als een specifieke waarschuwing of een bepaald rapport verder moet worden onderzocht, kan service personeel de gegevens opnieuw importeren in de Microsoft 365-service. Aangezien het specifieke logboek dat wordt geïmporteerd uit Cosmos, in versleuteld-en service personeel geen toegang heeft tot versleutelingssleutels, wordt het doellogboek via programmacode door een ontsleutelings Service doorgestuurd die de resultaten van het bereik levert aan het geautoriseerde service personeel. Eventuele problemen die zijn gevonden in deze oefening worden gerapporteerd en doorgestuurd met behulp van de standaard beveiligingsincidenten van het Microsoft-beheerkanaal.
