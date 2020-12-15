---
title: Onderwerp Ervaar beveiliging en privacy
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over het plannen van onderwerpen over beveiliging en privacy in Microsoft 365
ms.openlocfilehash: 7b88e5bbc8158ebd7dea65b2ecbf77085651b439
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668164"
---
# <a name="topic-experiences-security-and-privacy"></a>Onderwerp Ervaar beveiliging en privacy

In dit onderwerp worden bestaande beveiligingsfuncties voor inhoud in Microsoft 365 gebruikt, samen met de besturingselementen van het kennis netwerk, om te bepalen welke AI-gegenereerde inhoud wordt getoond aan gebruikers in uw organisatie. Dit is de combinatie van beveiligingsinstellingen van Microsoft 365 (machtigingen voor sites, bestanden en mappen) en onderwerp met Beheerdersinstellingen die bepalen wat een bepaalde gebruiker kan zien in onderwerpen.

Het instellen van het kennis netwerk heeft geen invloed op bestaande toegangsbeheerfuncties voor inhoud in uw organisatie. Gebruikers kunnen alleen zien waartoe ze al toegang hebben.

In dit artikel wordt beschreven hoe u onderwerp kunt gebruiken in een beveiligings perspectief en de opties die de kennis beheerders en kennis beheerders hebben om de zichtbaarheid van het onderwerp te bepalen. Lees dit artikel als onderdeel van uw [planning voor topic Experience](plan-topic-experiences.md).

U moet bekend zijn met de [functies](knowledge-management-overview.md)van het onderwerp, het [onderwerp centrum](topic-center-overview.md)en [werken met onderwerpen in het onderwerp centrum](work-with-topics.md) voordat u dit artikel leest.

## <a name="what-users-can-see-in-topics"></a>Wat gebruikers in de onderwerpen kunnen zien

Een gebruiker moet het volgende doen om onderwerpen weer te geven:

- Met een onderwerp een licentie
- U bent een [onderwerp-Viewer](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization), [Inzender of kennis Manager](topic-experiences-user-permissions.md)

Met deze twee zaken kunnen gebruikers toegang geven tot het onderwerp centrum en kunnen ze hooglichten en onderwerpgebieden zien.

Medewerkers van een onderwerp hebben ook machtigingen voor het [maken en bewerken](topic-experiences-user-permissions.md#change-who-has permissions-to-update-topic-details) van onderwerpen, en kennis beheerders kunnen onderwerpen bevestigen of verwijderen.

Wanneer een onderwerp voor het eerst wordt gedetecteerd, kunnen de kennis managers het onderwerp in het onderwerp centrum zien. Afhankelijk van de afronding en relevantie van het onderwerp, kunnen de onderwerpen van het onderwerp of het onderwerp dat wordt weergegeven in de onderwerpgebieden, mogelijk niet worden weergegeven.

De onderwerpen kunnen gegevens bevatten die worden gegenereerd door de AI-en informatie die zijn toegevoegd of bewerkt door medewerkers of kennis beheerders van het onderwerp.

- Informatie in een onderwerp dat door AI is toegevoegd, is alleen zichtbaar voor personen die toegang hebben tot de broninhoud.
- Tekst die handmatig is toegevoegd of bewerkt door een onderwerpassistent of Knowledge Manager, is zichtbaar voor iedereen die het onderwerp kan zien.

Met viewers en medewerkers van een onderwerp kunnen de lijst met bevestigde en gepubliceerde onderwerpen in het onderwerp in het onderwerp worden weergegeven, maar het onderwerp bevat details die een bepaalde persoon kan zien, is afhankelijk van de machtigingen die ze hebben voor het bronmateriaal en of het onderwerp handmatig is bewerkt.

In de volgende tabel wordt beschreven welke gebruikers van een onderwerp, medewerkers en kennis managers van de gebruikers, kunnen zien in een bepaald onderwerp op basis van hun machtigingen.

|Onderwerp|Wat gebruikers kunnen zien|
|:---------|:------------------|
|Naam onderwerp|Gebruikers kunnen de naam van het onderwerp van alle onderwerpen in het onderwerp centrum zien. Sommige onderwerpen zijn mogelijk niet zichtbaar als ze een lage relevantie voor de gebruiker hebben.|
|Beschrijving onderwerp|Met AI gegenereerde beschrijvingen zijn alleen zichtbaar voor gebruikers die zijn gemachtigd voor de broninhoud. Handmatig ingevoerde of bewerkte beschrijvingen zijn zichtbaar voor alle gebruikers.|
|Personen|Vastgemaakte personen zijn zichtbaar voor alle gebruikers. Voorgestelde personen zijn alleen zichtbaar voor gebruikers die zijn gemachtigd voor de broninhoud.|
|Bestanden|Bestanden zijn alleen zichtbaar voor gebruikers die zijn gemachtigd voor de broninhoud.|
|Pagina's|Pagina's zijn alleen zichtbaar voor gebruikers die zijn gemachtigd voor de broninhoud.|
|Sites|Sites zijn alleen zichtbaar voor gebruikers die zijn gemachtigd voor de broninhoud.|

## <a name="best-practices"></a>Aanbevolen procedures

Met een onderwerp worden gegevens voor gebruikers weergegeven op basis van hun bestaande machtigingen voor inhoud. Microsoft 365 biedt verschillende manieren om te voorkomen dat vertrouwelijke inhoud door de juiste gebruikers wordt beperkt. Naast de machtigingen voor het team of de site, kunt u gebruikmaken van [gevoelige labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) of [preventie van gegevensverlies](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) , [zodat u](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) regelmatig de toegang van gebruikers tot gevoelige informatie controleert.

We raden u aan deze hulpmiddelen te gebruiken om ervoor te zorgen dat uw inhouds machtigingen in uw organisatie correct zijn ingesteld. Met behulp van onderwerpen kunnen de gebruikers nuttige en nuttige informatie geven.

Als er onderwerpen zijn die u niet geheel van onderwerpen wilt uitsluiten, kunt u ook het volgende doen:

- [Gevoelige SharePoint-sites uitsluiten van topic Discovery](topic-experiences-discovery.md#select-sharepoint-topic-sources). De inhoud van deze sites wordt niet weergegeven in de onderwerp-ervaringen.

- [Onderwerpen op naam uitsluiten](topic-experiences-discovery.md#exclude-topics-by-name) Onderwerpen die expliciet worden uitgesloten, worden niet weergegeven in de onderwerp-ervaringen.

- Laat kennis beheerders onderwerpen uit het onderwerp centrum verwijderen.

Daarnaast is het raadzaam deze aanbevolen procedures te volgen:

- U werft kennis managers binnen verschillende gebieden van uw organisatie. Met kennis managers met tal van expertise-en toegang tot de onderliggende inhoud die door AI wordt gebruikt, kan u de meest nuttige informatie voor uw gebruikers nakomen en gevoelige informatie verwijderen indien gevonden.

- Een werkstroom voor het aanvragen van wijzigingen instellen. Kennis beheerders of team-of site-eigenaren moeten een proces hebben waarmee ze uitsluiting van onderwerpen of sites kunnen aanvragen wanneer nieuwe projecten in uw organisatie worden gestart of als ze inhoud vinden met onjuiste machtigingsinstellingen.

- Let op het publiek en de vertrouwelijkheid van informatie bij het maken van beschrijvingen van onderwerpen. Deze beschrijvingen zijn mogelijk zichtbaar voor gebruikers die geen machtigingen hebben voor de broninhoud voor het onderwerp.

Hoewel u de machtigingen voor afzonderlijke pagina's van de pagina's kunt wijzigen om toegang te krijgen tot een bepaalde groep gebruikers, wordt deze aanpak niet aangeraden omdat dit een hoge mate van beheer inspanning vereist.

## <a name="see-also"></a>Zie ook

[Teams met drie beschermingsniveaus configureren](../solutions/configure-teams-three-tiers-protection.md)

[Ervaring met onderwerpen plannen](plan-topic-experiences.md)

[Ervaring met het onderwerp instellen](set-up-topic-experiences.md)
