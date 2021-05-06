---
title: Geavanceerde indexering van beheerdersgegevens
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
description: Wanneer een bewaarder wordt toegevoegd aan een Advanced eDiscovery geval, wordt inhoud die als gedeeltelijk geïndexeerd is beschouwd, opnieuw verwerkt om deze volledig doorzoekbaar te maken.
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161892"
---
# <a name="advanced-indexing-of-custodian-data"></a>Geavanceerde indexering van beheerdersgegevens

Wanneer een bewaarder wordt toegevoegd aan een Advanced eDiscovery geval, wordt inhoud die als gedeeltelijk geïndexeerd is beschouwd, opnieuw verwerkt om deze volledig doorzoekbaar te maken.  Dit proces wordt Geavanceerde *indexering genoemd.* Inhoud kan gedeeltelijk worden geïndexeerd om een aantal redenen, zoals het bestaan van afbeeldingen, niet-ondersteunde bestandstypen of wanneer limieten voor bestandsgrootte indexeren worden aangetroffen.

Zie voor meer informatie over het verwerken van ondersteuning en gedeeltelijk geïndexeerde items:

- [Ondersteunde bestandstypen in Advanced eDiscovery](supported-filetypes-ediscovery20.md)

- [Gedeeltelijk geïndexeerde items in Inhoud zoeken in Office 365](partially-indexed-items-in-content-search.md)

- [Bestandsindelingen geïndexeerd door Exchange Zoeken](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Standaard verkende bestandsnaamextensies en geparseerde bestandstypen in SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Geavanceerde indexeringsresultaten weergeven

Nadat het proces voor geavanceerde indexering is voltooid, kunt u inzicht krijgen in de effectiviteit van de opwerking.  In de weergave Geavanceerde indexeringsresultaten op **het** tabblad Verwerking voor een zaak bevat de grafiek het aantal items dat aan de *hybride index is toegevoegd.*  De hybride index is de Advanced eDiscovery inhoud op te slaat.

Deze weergave bevat ook het aantal items waarvoor herstel nodig is en een andere grafiek met fouten per bestandstype. Zie voor meer informatie:

- [Foutherstel bij het verwerken van gegevens](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [Foutherstel voor één item](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>De geavanceerde index voor beheerders bijwerken

Wanneer een bewaarder wordt toegevoegd aan een Advanced eDiscovery, worden alle gedeeltelijk geïndexeerde items opnieuw verwerkt. Naarmate de tijd verstrijkt, kunnen echter meer gedeeltelijk geïndexeerde items worden toegevoegd aan het postvak of het OneDrive account van een gebruiker.  Indien nodig kunt u de index bijwerken voor specifieke bewaarders. Zie Beheerders beheren in een Advanced eDiscovery [voor meer informatie.](manage-new-custodians.md#re-index-custodian-data) U kunt ook de index voor alle beheerders in een zaak bijwerken door op de **index Bijwerken** op het tabblad **Verwerking te** klikken.

> [!NOTE]
> Het bijwerken van beheerdersindexen is een langlopende procedure. U wordt aangeraden indexen niet meer dan één keer per dag bij te werken in een zaak.