---
title: Tenant isolatie in Microsoft 365 zoeken
ms.author: robmazz
author: robmazz
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
description: In dit artikel vindt u een beschrijving van de manier waarop Tenant isolatie werkt om Tenant gegevens te scheiden in Microsoft 365 Search.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3416afdeceaa7000b516ec89b4a2a1e59d8708d0
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332398"
---
# <a name="tenant-isolation-in-microsoft-365-search"></a>Tenant isolatie in Microsoft 365 zoeken

Voor zoekopdrachten in SharePoint Online wordt gebruikgemaakt van een Tenant scheidings model waarmee de efficiëntie van gedeelde gegevensstructuren met beveiliging wordt vergeleken met informatie die tussen tenants is lekt. Met dit model kunnen de zoekfuncties niet:

- Queryresultaten met documenten uit andere tenants retourneren
- Voldoende informatie in queryresultaten weergeven die een ervaren gebruiker informatie over andere tenants kan afleiden
- Het schema of de instellingen van een andere Tenant weergeven
- De verwerking van analysegegevens van een mengsel tussen tenants of Store-resultaten in de verkeerde Tenant
- Woordenboek vermeldingen uit een andere Tenant gebruiken

Voor elk type Tenant gegevens gebruikt u een of meer beveiligingslagen in de code om te voorkomen dat gegevens worden gelekt. De meest kritieke gegevens zijn de meeste beveiligingslagen waarmee u ervoor kunt zorgen dat één gebrek opgaat met werkelijke of vertraagde gegevens lekkage.

## <a name="tenant-separation-for-the-search-index"></a>Tenant scheiding voor de zoek index

De zoekindex wordt opgeslagen op de schijf op de servers die de indexonderdelen en de tenants hosten, delen de indexbestanden. De geïndexeerde documenten van een Tenant zijn alleen zichtbaar voor query's voor die Tenant. Drie onafhankelijke mechanismen voorkomen informatie lekkage:

- Tenant-ID filteren
- Voorvoegsel van de Tenant-ID voor de periode
- ACL-controles

Het is niet mogelijk om documenten terug te vinden in de verkeerde Tenant.

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>Tenant-ID filteren en voorvoegsels van de Tenant-ID

Met deze functie wordt elke term met de Tenant-ID die is geïndexeerd in de index met volledige tekst, opgelost. Wanneer de term '*Foo*' bijvoorbeeld wordt geïndexeerd voor een Tenant met de ID '*123*', is de vermelding in de index met volledige tekst '*123foo '.*

Elke query wordt geconverteerd, waarbij de Tenant-ID wordt gebruikt met een proces genaamd Tenant-ID filteren. De query '*Foo*' wordt bijvoorbeeld geconverteerd naar ' <*GUID*>. *Foo* EN *tenantID*: <*GUID*>, waarbij de <*GUID*> de Tenant vertegenwoordigt die de query uitvoert. Deze query wordt geconverteerd binnen elk indexknooppunt en de query kan niet worden gewijzigd. Aangezien de Tenant-ID aan elke query wordt toegevoegd, kan de frequentie van een term in andere tenants niet worden afgeleid door te kijken naar de rangschikking van de beste treffer in één Tenant.

Voorvoegsel van de voornaam van de Tenant-ID vindt u alleen in de index met volledige tekst. Met geplaatste zoekopdrachten, zoals '*Titel: Foo*', gaat u naar een synthetische zoekindex waarbij de termen niet worden hersteld via een Tenant-id. In plaats daarvan worden met veldnamen een tijdelijke oplossing uitgevoerd. De query '*Titel: Foo*' wordt bijvoorbeeld geconverteerd naar '*velden. title: foo en Fields. tenantID*: <*GUID*> '. Aangezien de frequentie van een term geen invloed heeft op de classificatie van treffers in de synthetische zoekindex, is er geen Tenant scheidingsteken voor het voorvoegsel van de term. Voor een zoekopdracht via een veld zoals*Titel: Foo*, is het niet mogelijk Tenant-inhouds scheidings functie te filteren op Tenant-id.

## <a name="document-access-control-list-checks"></a>Controles van de toegangsbeheerlijst voor documenten

Met de zoekfunctie beheert u de toegang tot documenten via Acl's die zijn opgeslagen in de zoekindex. Elk item wordt geïndexeerd met een set termen in een speciaal ACL-veld. Het veld ACL bevat één term per groep of gebruiker waarin het document kan worden weergegeven. Elke query wordt uitgebreid met een lijst met ACE-vermeldingen (toegangscontrolevermeldingen), één voor elke groep waarvan de geverifieerde gebruiker lid is.

Bijvoorbeeld een query zoals " *guid*> <. *foo en tenantID*: <*GUID*> "wordt:" <*GUID*>. *foo en tenantID*: <*GUID* >  *en* (*docACL:* < *ace1* >  *of docACL*: <*ACE2* >  *of docACL*: <*ace3* >  *...*)

Aangezien gebruikers-en groeps-id's en daarom unieke Ace's zijn, biedt dit een extra beveiligingsniveau tussen tenants voor documenten die alleen zichtbaar zijn voor sommige gebruikers. Hetzelfde is het geval voor de ACE voor speciale gebruikers, met uitzondering van externe gebruikers, die toegang biedt tot normale gebruikers in de Tenant. Aangezien Ace's voor ' iedereen ' hetzelfde zijn voor alle tenants, is de scheiding van de Tenant voor openbare documenten afhankelijk van het filteren van Tenant-id's. Deny-Ace's worden ook ondersteund. Met behulp van de query-uitbreiding voegt u een component toe waarmee een document wordt verwijderd uit het resultaat wanneer er een overeenkomst is met een Deny-ACE.

In de zoekfunctie van Exchange Online is de index gepartitioneerd op Postvak-ID voor de postvakken van de afzonderlijke gebruikers in plaats van Tenant-ID (abonnements-ID), zoals in SharePoint Online. Het partitionatie mechanisme is hetzelfde als SharePoint Online, maar er is geen ACL-filter.
