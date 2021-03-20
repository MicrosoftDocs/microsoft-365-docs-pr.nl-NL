---
title: Microsoft Viva-onderwerpen beveiliging en privacy
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Meer informatie over het plannen van microsoft Viva-onderwerpen voor beveiliging en privacy
ms.openlocfilehash: 9ac7ea085be115ef06244422713099c01ec50a36
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917342"
---
# <a name="microsoft-viva-topics-security-and-privacy"></a>Microsoft Viva-onderwerpen beveiliging en privacy

Onderwerpen maken gebruik van bestaande functies voor inhoudsbeveiliging in Microsoft 365, samen met beheerbesturingselementen, om te bepalen welke ai-gegenereerde inhoud wordt weergegeven aan gebruikers in uw organisatie. Het is de combinatie van beveiligingsinstellingen van Microsoft 365 (machtigingen voor sites, bestanden en mappen) en instellingen voor onderwerpenbeheerder die bepalen wat een bepaalde gebruiker kan zien in onderwerpen.

Het instellen van Onderwerpen wijzigt geen bestaande toegangsbesturingselementen voor inhoud in uw organisatie. Gebruikers zien alleen waar ze al toegang toe hebben.

In dit artikel wordt beschreven hoe Onderwerpen werken vanuit een beveiligingsperspectief en de opties die kennisbeheerders en kennisbeheerders hebben om de zichtbaarheid van het onderwerp te bepalen. Lees dit artikel als onderdeel van uw [planning voor Onderwerpen.](plan-topic-experiences.md)

U moet bekend zijn met [wat Onderwerpen is,](topic-experiences-overview.md)het [onderwerpcentrum,](topic-center-overview.md)en hoe u met onderwerpen in het [onderwerpcentrum](manage-topics.md) kunt werken voordat u dit artikel leest.

## <a name="what-users-can-see-in-topics"></a>Wat gebruikers kunnen zien in onderwerpen

Als u onderwerpen wilt zien, moet een gebruiker:

- Een licentie voor Viva-onderwerpen hebben
- Een [onderwerpviewer,](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization) [inzender of kennismanager zijn](topic-experiences-user-permissions.md)

Deze twee dingen geven gebruikers toegang tot het onderwerpcentrum en geven hen de mogelijkheid om highlights en onderwerpkaarten te zien.

Onderwerpcontribuanten hebben bovendien [machtigingen voor](topic-experiences-user-permissions.md) het maken en bewerken van onderwerpen, en kennisbeheerders kunnen onderwerpen bevestigen of verwijderen.

Wanneer een onderwerp voor het eerst wordt ontdekt, kunnen kennismanagers het zien in het onderwerpcentrum. Afhankelijk van de volledigheid en relevantie van het onderwerp kunnen onderwerpkijkers het onderwerp al dan niet zien in onderwerpkaarten.

Onderwerpen kunnen informatie bevatten die wordt gegenereerd door AI en informatie die is toegevoegd of bewerkt door onderwerpcontribuanten of kennisbeheerders.

- Informatie in een onderwerp dat door AI is toegevoegd, is alleen zichtbaar voor personen die toegang hebben tot de broninhoud.
- Tekst die handmatig is toegevoegd of bewerkt door een inzender van het onderwerp of knowledge manager, is zichtbaar voor iedereen die het onderwerp kan zien.

Onderwerpkijkers en inzenders kunnen de lijst met bevestigd en gepubliceerde onderwerpen in het onderwerpcentrum zien, maar de onderwerpdetails die een bepaalde persoon kan zien, zijn afhankelijk van de machtigingen die ze hebben voor het bronmateriaal en van de vraag of het onderwerp handmatig is bewerkt.

In de volgende tabel wordt beschreven wat gebruikers - kijkers van onderwerpen, medewerkers en kennisbeheerders - kunnen zien in een bepaald onderwerp op basis van hun machtigingen.

|Onderwerpitem|Wat gebruikers kunnen zien|
|:---------|:------------------|
|Onderwerpnaam|Gebruikers kunnen de onderwerpnaam van alle onderwerpen in het onderwerpcentrum zien. Sommige onderwerpen zijn mogelijk niet zichtbaar als ze een lage relevantie hebben voor de gebruiker.|
|Beschrijving van onderwerp|Door AI gegenereerde beschrijvingen zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud. Handmatig ingevoerde of bewerkte beschrijvingen zijn zichtbaar voor alle gebruikers.|
|Personen|Vastgemaakte personen zijn zichtbaar voor alle gebruikers. Voorgestelde personen zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.|
|Bestanden|Bestanden zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.|
|Pagina's|Pagina's zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.|
|Sites|Sites zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.|

## <a name="best-practices"></a>Aanbevolen procedures

Onderwerpen bevatten informatie voor gebruikers op basis van hun bestaande machtigingen voor inhoud. Microsoft 365 biedt verschillende manieren om ervoor te zorgen dat gevoelige inhoud is beperkt tot de juiste gebruikers. Naast standaardmachtigingen voor teams [](../compliance/sensitivity-labels.md) of site's, kunt u gevoeligheidslabels of preventie van gegevensverlies gebruiken om de toegang tot inhoud te beperken en beoordelingen te openen om de toegang van gebruikers tot gevoelige informatie regelmatig te controleren. [](../compliance/data-loss-prevention-policies.md) [](/azure/active-directory/governance/access-reviews-overview)

U wordt aangeraden deze hulpprogramma's te gebruiken om ervoor te zorgen dat uw inhoudsmachtigingen op de juiste manier zijn ingesteld binnen uw organisatie. Onderwerpervaringen kunnen uw gebruikers dan nuttige en juiste informatie bieden.

Als er onderwerpen zijn die u volledig wilt uitsluiten van onderwerpervaringen, kunt u ook:

- [Sluit gevoelige SharePoint-sites uit van onderwerpdetectie.](topic-experiences-discovery.md#select-sharepoint-topic-sources) Inhoud op deze sites wordt niet weergegeven in onderwerpervaringen.

- [Sluit onderwerpen op naam uit.](topic-experiences-discovery.md#exclude-topics-by-name) Onderwerpen die expliciet zijn uitgesloten, worden niet weergegeven in onderwerpervaringen.

- Laten kennisbeheerders onderwerpen verwijderen in het onderwerpcentrum.

Daarnaast raden we u deze aanbevolen procedures aan:

- Recruit knowledge managers from different areas of your organization. Met kennisbeheerders met een verscheidenheid aan expertise en toegang tot de onderliggende inhoud die door AI wordt gebruikt, kunt u de meest nuttige kennis voor uw gebruikers verzamelen en gevoelige informatie verwijderen als deze wordt gevonden.

- Een werkstroom instellen voor het aanvragen van wijzigingen. Kennisbeheerders of team- of site-eigenaren moeten een proces hebben waarmee ze uitsluiting van onderwerpen of sites kunnen aanvragen wanneer nieuwe projecten binnen uw organisatie worden gestart of als ze inhoud vinden met instellingen voor ongepaste machtigingen.

- Let op het publiek en de gevoeligheid van informatie bij het maken van onderwerpbeschrijvingen. Deze beschrijvingen zijn mogelijk zichtbaar voor gebruikers die geen machtigingen hebben voor de broninhoud voor het onderwerp.

Hoewel u de machtigingen voor afzonderlijke onderwerppagina's kunt wijzigen om de toegang tot een bepaalde groep gebruikers te beperken, raden we deze benadering af vanwege de hoge mate van administratieve inspanning die vereist is.

## <a name="see-also"></a>Zie ook

[Teams met drie beschermingsniveaus configureren](../solutions/configure-teams-three-tiers-protection.md)

[Onderwerpservaringen plannen](plan-topic-experiences.md)

[Onderwerpservaringen instellen](set-up-topic-experiences.md)