---
title: Een risicovolle leveringsgroep voor uitgaande berichten
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/24/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Wanneer het e-mailsysteem van een klant is gecompromitteerd door malware of een kwaadaardige spamaanval en het uitgaande spam verzendt via de gehoste filterservice, kan dit ertoe leiden dat de IP-adressen van de Office 365-datacenterservers worden vermeld op blok van derden Lijsten.
ms.openlocfilehash: 19987ae74b9c78a796ddb5f13cf8291a5ed269ad
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42805479"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a>Een risicovolle leveringsgroep voor uitgaande berichten

Wanneer het e-mailsysteem van een klant is gecompromitteerd door malware of een kwaadaardige spamaanval en het uitgaande spam verzendt via de gehoste filterservice, kan dit ertoe leiden dat de IP-adressen van de Office 365-datacenterservers worden vermeld op blok van derden Lijsten. Doelservers die de gehoste filterservice niet gebruiken, maar deze bloklijsten wel gebruiken, weigeren alle e-mail die is verzonden vanaf een van de gehoste filterIP-adressen die aan die lijsten zijn toegevoegd. Om dit te voorkomen, worden alle uitgaande berichten die de spamdrempel overschrijden, verzonden via een groep met een hoog risico.To prevent this, all outbound messages that exceed the spam threshold are sent through a high-risk delivery pool. Deze secundaire uitgaande e-mailgroep wordt alleen gebruikt om berichten te verzenden die van lage kwaliteit kunnen zijn. Dit helpt om de rest van het netwerk te beschermen tegen het verzenden van berichten die waarschijnlijk ertoe leiden dat het verzenden van IP-adres wordt geblokkeerd.
  
Het gebruik van een speciale groep met een hoog risico zorgt ervoor dat de normale uitgaande pool alleen berichten verzendt waarvan bekend is dat ze van hoge kwaliteit zijn. Het gebruik van deze secundaire IP-pool helpt om de kans te verkleinen dat de normale uitgaande IP-groep wordt toegevoegd aan een geblokkeerde lijst. De mogelijkheid dat de risicovolle bezorgpool op een geblokkeerde lijst wordt geplaatst, blijft een risico. Dit is normaal.
  
Berichten waarin het verzendende domein geen adresrecord (A-record) heeft, waardoor u het IP-adres van het domein krijgt en geen MX-record, waarmee direct mail wordt verzonden naar de servers die de e-mail moeten ontvangen voor een bepaald domein in de DNS, worden altijd door de een risicovolle bezorgpool, ongeacht hun spampositie.
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a>DSN-berichten (Delivery Status Notification) begrijpen

De uitgaande groep met een hoog risico beheert de levering voor alle "bounced" of "failed" (DSN) berichten.
  
Mogelijke oorzaken voor een piek in DSN-berichten zijn de volgende:
  
- Een spoofing-campagne die van invloed is op een van de klanten die de service gebruiken
    
- Een directory oogst aanval
    
- Een spamaanval
    
- Een malafide SMTP-server
    
Al deze problemen kunnen leiden tot een plotselinge toename van het aantal DSN-berichten dat door de service wordt verwerkt. Vaak lijken deze DSN-berichten spam te zijn voor andere e-mailservers en -services.
  
## <a name="for-more-information"></a>Voor meer informatie

[Het uitgaande spambeleid configureren](configure-the-outbound-spam-policy.md)
  
[Veelgestelde vragen over antispambescherming](anti-spam-protection-faq.md)
  

