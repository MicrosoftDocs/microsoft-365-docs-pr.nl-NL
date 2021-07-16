---
title: Tenantisolatie in Microsoft 365 Zoeken
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
description: In dit artikel vindt u een uitleg over hoe tenantisolatie werkt om tenantgegevens te scheiden in Microsoft 365 Zoeken.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3416afdeceaa7000b516ec89b4a2a1e59d8708d0
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464068"
---
# <a name="tenant-isolation-in-microsoft-365-search"></a>Tenantisolatie in Microsoft 365 Zoeken

SharePoint Online zoeken maakt gebruik van een tenantscheidingsmodel dat de efficiëntie van gedeelde gegevensstructuren balanceert met beveiliging tegen informatielekken tussen tenants. Met dit model voorkomen we dat de zoekfuncties:

- Queryresultaten met documenten van andere tenants retourneren
- Voldoende informatie in queryresultaten die een ervaren gebruiker kan afleiden uit informatie over andere tenants
- Schema of instellingen van een andere tenant weergeven
- Analyseverwerkingsgegevens tussen tenants combineren of resultaten opslaan in de verkeerde tenant
- Woordenlijstgegevens van een andere tenant gebruiken

Voor elk type tenantgegevens gebruiken we een of meer beveiligingslagen in de code om onbedoelde lekken van informatie te voorkomen. De meest kritieke gegevens hebben de meeste beveiligingslagen om ervoor te zorgen dat één fout niet resulteert in een werkelijke of waargenomen informatielekken.

## <a name="tenant-separation-for-the-search-index"></a>Tenantscheiding voor de zoekindex

De zoekindex wordt opgeslagen op schijf in de servers met de indexonderdelen en de tenants delen de indexbestanden. De geïndexeerde documenten van een tenant zijn alleen zichtbaar voor query's voor die tenant. Drie onafhankelijke mechanismen voorkomen informatielekken:

- Tenant-id-filtering
- Tenant-id-term voorvoegsel
- ACL-controles

Alle drie de mechanismen moeten mislukken voor Zoeken om documenten terug te geven aan de verkeerde tenant.

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>Tenant-id-filtering en tenant-id-term voorvoegsel

Zoek voorvoegsels voor elke term die wordt geïndexeerd in de full-text index met de tenant-id. Als bijvoorbeeld de term "*foo*" wordt geïndexeerd voor een tenant met een id van "*123*", is de vermelding in de full-text index "*123foo.*"

Elke query wordt geconverteerd naar de tenant-id met behulp van een proces dat tenant-id-filtering wordt genoemd. De query '*foo'* wordt bijvoorbeeld geconverteerd naar '<*guid*>. *foo* AND *tenantID*:<*guid*>", waarbij <*guid*> de tenant vertegenwoordigt die de query uitvoert. Deze queryconversie vindt plaats in elk index knooppunt en query' s en inhoudsverwerking kunnen dit niet beïnvloeden. Omdat de tenant-id aan elke query wordt toegevoegd, kan de frequentie van een term in andere tenants niet worden afgeleid door te kijken naar de beste overeenkomstrangschikking in één tenant.

Tenant-id-term voorvoegsel vindt alleen plaats in de index met volledige tekst. Veldzoek zoekopdrachten, zoals "*title:foo*", gaan naar een synthetische zoekindex waarin termen niet zijn voorafgevoegd door tenant-id. In plaats daarvan worden veldzoek zoekopdrachten voorafgevoegd met de veldnaam. De query "*title:foo*" wordt bijvoorbeeld geconverteerd naar "*fields.title:foo AND fields.tenantID*:<*guid*>." Omdat de frequentie van een term geen invloed heeft op het rangschikken van treffers in de index voor synthetische zoekopdrachten, is het niet nodig om tenantscheiding per term voorvoegsel te gebruiken. Voor een veldzoekactie zoals "*title:foo*" is de scheiding van tenantinhoud afhankelijk van het filteren van tenant-id's door queryconversie.

## <a name="document-access-control-list-checks"></a>Document Access Control List Checks

Zoeken besturingselementen voor toegang tot documenten via ACL's die zijn opgeslagen in de zoekindex. Elk item wordt geïndexeerd met een set termen in een speciaal ACL-veld. Het veld ACL bevat één term per groep of gebruiker die het document kan bekijken. Elke query wordt aangevuld met een lijst met ace-termen (Access Control Entry), een voor elke groep waarvan de geverifieerde gebruiker deel uit maakt.

Een query zoals '<*guid>.* *foo AND tenantID*:<*guid*>" wordt: "<*guid*>. *foo AND tenantID*:<*guid* >  *AND* (*docACL:* < *ace1* OR >  *docACL*:<*ace2* >  *OR docACL*:<*ace3* >  *...*)"

Omdat gebruikers- en groepsaanduidingen en dus ACL's uniek zijn, biedt dit een extra beveiligingsniveau tussen tenants voor documenten die alleen zichtbaar zijn voor sommige gebruikers. Hetzelfde geldt voor de speciale ACE 'Iedereen behalve externe gebruikers' die toegang verleent aan gewone gebruikers in de tenant. Maar aangezien AE's voor 'Iedereen' voor alle tenants hetzelfde zijn, is tenantscheiding voor openbare documenten afhankelijk van het filteren van tenant-id's. Weigeren ACL's worden ook ondersteund. Met de queryvergroting wordt een component toegevoegd die een document uit het resultaat verwijdert wanneer er een overeenkomst is met een WEIGEREN-ACE.

In Exchange Online zoeken wordt de index verdeeld over postvak-id voor de postvakken van afzonderlijke gebruikers in plaats van tenant-id (abonnement-id) zoals in SharePoint Online. Het scheidingsmechanisme is hetzelfde als SharePoint Online, maar er is geen ACL-filtering.
