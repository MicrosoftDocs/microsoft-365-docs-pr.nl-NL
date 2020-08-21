---
title: Uitgaande bezorgingspools
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Meer informatie over hoe de leverings groepen worden gebruikt om de reputatie van e-mailservers in de Microsoft 365-datacenters te beschermen.
ms.openlocfilehash: 83ea21a9230240f1339513efc75587f3d84733cb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827735"
---
# <a name="outbound-delivery-pools"></a>Uitgaande bezorgingspools

E-mailservers in de Microsoft 365-datacenters zijn mogelijk tijdelijk van spam verzonden. Een malware of kwaadaardige spam aanval in een on-premises e-mail organisatie waarmee uitgaande e-mail wordt verzonden via Microsoft 365 of in gemanipuleerde Microsoft 365-accounts. Hackers proberen ook detectie berichten te voorkomen door berichten via Microsoft 365 door te sturen.

Deze scenario's kunnen leiden tot het IP-adres van de desbetreffende Microsoft 365-datacenter servers in blok lijsten van derden. De doel-e-mail organisaties die gebruikmaken van deze blok lijsten, negeren e-mail van die berichten bronnen.

## <a name="high-risk-delivery-pool"></a>Groep voor hoog risico voor levering
Om dit te voorkomen, worden alle uitgaande berichten van Microsoft 365-datacenter servers die zijn afgeleid van spam of de verzending van [de service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) of het [uitgaande spam beleid](configure-the-outbound-spam-policy.md) , verzonden via de _groep voor hoog risico_.

De groep hoog risico voor bezorgings berichten is een afzonderlijke IP-adresgroep voor uitgaande e-mail die alleen wordt gebruikt voor het verzenden van berichten met lage kwaliteit (bijvoorbeeld spam en [Backscatter](backscatter-messages-and-eop.md)). Met de bezorgings groep voor hoog risico kan de normale IP-adresgroep voor uitgaande e-mail niet worden verzonden. De normale IP-adresgroep voor uitgaande e-mail onderhoudt de reputatie berichten ' hoge kwaliteit ' verzenden, waardoor de kans kleiner is dat dit IP-adres wordt weergegeven op de IP-blok lijsten.

De zeer reële mogelijkheid die IP-adressen in de bezorgings pool voor hoog risico op de IP-blok lijsten plaatst, blijft bestaan, maar dit is een ontwerp. Levering aan de bedoelde geadresseerden is niet gegarandeerd, omdat veel e-mail bedrijven geen berichten van de groep hoog risico leveren.

Zie [uitgaande spam beheren](outbound-spam-controls.md)voor meer informatie.

> [!NOTE]
> Berichten waarbij het bron-e-mail domein geen record heeft en de MX-record die is gedefinieerd in openbare DNS, wordt altijd doorgestuurd via de bezorgings pool voor hoog risico, ongeacht hun spam of verzend beperkingen.

### <a name="bounce-messages"></a>Berichten stuiteren

De uitgaande groep met een hoog risico beheert de bezorging van alle rapporten over niet-uitgevoerde bezorging (ook wel Ndr's genoemd, berichten verzenden, melding van afleverings status of Dsn's).

Mogelijke oorzaken voor een piek in Ndr's zijn:

- Een vervalsings campagne die van invloed is op een van de klanten die de service gebruiken.
- Een aanval in de Directory oogst.
- Een spam aanval.
- Een Rogue-e-mailserver.

Al deze problemen kunnen leiden tot een plotselingere toename van het aantal Ndr's dat wordt verwerkt door de service. Deze Ndr's lijken vaak spam te zijn voor andere e-mailservers en-services (ook wel bekend als _[Backscatter](backscatter-messages-and-eop.md)_).

## <a name="relay-pool"></a>Relais groep

Berichten die worden doorgestuurd of doorgestuurd van Microsoft 365, worden verzonden met behulp van een speciale doorstuur groep, aangezien de uiteindelijke bestemming Microsoft 365 niet als de werkelijke afzender moet beschouwen. Het is ook belangrijk om dit verkeer te isoleren, omdat er legitieme en ongeldige scenario's zijn voor het doorsturen of doorsturen van e-mail van Microsoft 365. Vergelijkbaar met de bezorgings pool voor hoog risico, wordt een afzonderlijke IP-adresgroep gebruikt voor het doorsturen van e-mail. Deze adresgroep wordt niet gepubliceerd, omdat deze vaak kan wijzigen.

Microsoft 365 moet controleren of de oorspronkelijke afzender legitiem is, zodat we het doorgestuurde bericht kunnen bezorgen. Om die te doen moet de e-mail verificatie (SPF, DKIM en DMARC) worden overlopen wanneer het bericht naar ons wordt verzonden. Wanneer we de afzender kunnen verifiëren, gebruiken we Herschrijf de afzender om de ontvanger te helpen weten dat het doorgestuurde bericht afkomstig is van een vertrouwde bron. U kunt meer lezen over wat u kunt doen en wat u kunt doen om ervoor te zorgen dat het verzendende domein authenticatie in de vorm van een [Overschrijf schema (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)moet passeren.
