---
title: Hoe DLP werkt met & compliancecentrum & Exchange beheercentrum
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/19/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Meer informatie over hoe DLP in & compliancecentrum voor beveiliging werkt met DLP- en e-mailstroomregels (transportregels) in het Exchange beheercentrum.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c5249279e1dd04447235aae813128cf458adde03
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162896"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a>De werking van DLP tussen het Beveiligings- en compliancecentrum en het Exchange-beheercentrum

In Office 365 kunt u een DLP-beleid (Data Loss Prevention) maken in twee verschillende beheercentra:
  
- In het **Beveiligings- & Compliancecentrum** kunt u één DLP-beleid maken om inhoud te beschermen in SharePoint, OneDrive, Exchange en nu Microsoft Teams. Indien mogelijk raden we u aan hier een DLP-beleid te maken. Zie Verwijzing naar preventie van [gegevensverlies voor meer informatie.](data-loss-prevention-policies.md)
    
- In het **Exchange beheercentrum** kunt u een DLP-beleid maken om inhoud alleen in de Exchange. In dit beleid kunnen Exchange regels voor e-mailstroom (ook wel transportregels genoemd) gebruiken, zodat er meer specifieke opties zijn voor het verwerken van e-mail. Zie [DLP in het Exchange beheercentrum voor meer informatie.](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
    
DLP-agenten die in deze beheercentra zijn gemaakt, werken naast elkaar: in dit onderwerp wordt uitgelegd hoe.
  
![DLP-pagina's in het beveiligings- en compliancecentrum en Exchange beheercentrum](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>Hoe DLP in het beveiligings- & compliancecentrum werkt met DLP- en e-mailstroomregels in het Exchange beheercentrum

Nadat u een DLP-beleid hebt opgesteld in het Beveiligings- & Compliancecentrum, wordt het beleid geïmplementeerd op alle locaties die in het beleid zijn opgenomen. Als het beleid Exchange Online, wordt het beleid daar gesynchroniseerd en afgedwongen op precies dezelfde manier als een DLP-beleid dat is gemaakt in het Exchange beheercentrum. 
  
Als u DLP-beleid hebt gemaakt in het Exchange-beheercentrum, blijven deze beleidsregels naast elk beleid voor e-mail werken dat u maakt in het beveiligings- & Compliancecentrum. Houd er echter rekening mee dat regels die zijn gemaakt in het Exchange beheercentrum voorrang hebben. Alle Exchange e-mailstroomregels worden eerst verwerkt en vervolgens worden de DLP-regels van & compliancecentrum verwerkt.
  
Dit betekent dat:
  
- Berichten die worden geblokkeerd door Exchange regels voor e-mailstroom, worden niet gescand door DLP-regels die zijn gemaakt in het beveiligings- & Compliancecentrum.
    
- Als een Exchange-e-mailstroomregel een bericht zodanig wijzigt dat het voldoet aan een DLP-beleid in het beveiligings- &-compliancecentrum , zoals het toevoegen van externe gebruikers, wordt dit gedetecteerd door de DLP-regels en wordt het beleid zo nodig afgedwongen.
    
Houd er ook rekening mee dat Exchange regels voor e-mailstroom die de actie Stoppen met verwerken gebruiken, geen invloed hebben op de verwerking van DLP-regels in het Beveiligings- & Compliancecentrum. Ze worden nog steeds verwerkt.
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>Beleidstips in het beveiligings- & compliancecentrum versus het Exchange beheercentrum

Beleidstips kunnen werken met DLP-beleidsregels en e-mailstroomregels die zijn gemaakt in het Exchange-beheercentrum of met DLP-beleid dat is gemaakt in het Compliancecentrum voor beveiliging &, maar niet beide. Dit komt omdat deze beleidsregels op verschillende locaties worden opgeslagen, maar beleidstips kunnen slechts op één locatie worden gebruikt.
  
Als u beleidstips hebt geconfigureerd in het Exchange-beheercentrum, worden beleidstips die u configureert in het Compliancecentrum voor beveiliging & niet weergegeven voor gebruikers in Outlook op het web en Outlook 2013 en hoger totdat u de tips in het Exchange-beheercentrum uit schakelen. Dit zorgt ervoor dat uw huidige Exchange e-mailstroomregels blijven werken totdat u ervoor kiest om over te schakelen naar het Beveiligings- & Compliancecentrum.
  
Hoewel beleidstips slechts vanaf één locatie kunnen worden gebruikt, worden er altijd e-mailmeldingen verzonden, zelfs als u DLP-beleid gebruikt in zowel het Compliancecentrum voor beveiliging & als het Exchange-beheercentrum.
