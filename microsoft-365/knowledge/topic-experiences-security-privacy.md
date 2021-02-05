---
title: Beveiliging en privacy van Microsoft Viva-onderwerpen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Informatie over het plannen van de beveiliging en privacy van Microsoft Viva-onderwerpen
ms.openlocfilehash: be5be01bce117a80bd95ee268c193889eccea67f
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107790"
---
# <a name="microsoft-viva-topics-security-and-privacy"></a>Beveiliging en privacy van Microsoft Viva-onderwerpen

Onderwerpen maken gebruik van bestaande functies voor inhoudsbeveiliging in Microsoft 365, samen met administratieve controle, om te bepalen welke ai-gegenereerde inhoud wordt weergegeven aan gebruikers in uw organisatie. Het is een combinatie van beveiligingsinstellingen van Microsoft 365 (machtigingen voor sites, bestanden en mappen) en instellingen voor onderwerpen die bepalen wat een bepaalde gebruiker in onderwerpen kan zien.

Het instellen van Onderwerpen wijzigt geen bestaande toegangsbesturingselementen voor inhoud in uw organisatie. Gebruikers zien alleen de informatie waar ze al toegang tot hebben.

In dit artikel wordt beschreven hoe onderwerpen werken vanuit een beveiligings perspectief en de opties die kennisbeheerders en kennisbeheerders hebben om de zichtbaarheid van het onderwerp te bepalen. Lees dit artikel als onderdeel van uw [planning voor Onderwerpen.](plan-topic-experiences.md)

Voordat u dit artikel leest, [](topic-center-overview.md)moet u weten wat Onderwerpen [is,](topic-experiences-overview.md)het onderwerpcentrum en hoe u met onderwerpen kunt werken [in](manage-topics.md) het onderwerpcentrum.

## <a name="what-users-can-see-in-topics"></a>Wat gebruikers kunnen zien in onderwerpen

Als u onderwerpen wilt bekijken, moet een gebruiker:

- Een licentie voor Viva-onderwerpen hebben
- Een [onderwerpviewer,](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization) [bijdrager of Knowledge Manager zijn](topic-experiences-user-permissions.md)

Met deze twee dingen hebben gebruikers toegang tot het onderwerpcentrum en kunnen ze highlights en onderwerpkaarten zien.

Onderwerpbijdragers hebben ook [machtigingen voor](topic-experiences-user-permissions.md) het maken en bewerken van onderwerpen, en kennisbeheerders kunnen onderwerpen bevestigen of verwijderen.

Wanneer een onderwerp voor het eerst wordt ontdekt, kunnen kennisbeheerders dit zien in het onderwerpcentrum. Afhankelijk van de volledigheid en relevantie van het onderwerp, kunnen kijkers van het onderwerp het onderwerp al dan niet zien dat wordt gepresenteerd in onderwerpkaarten.

Onderwerpen kunnen informatie bevatten die wordt gegenereerd door AI en informatie die is toegevoegd of bewerkt door onderwerpbijdragers of knowledge managers.

- De informatie in een onderwerp dat door AI is toegevoegd, is alleen zichtbaar voor personen die toegang hebben tot de broninhoud.
- Tekst die handmatig is toegevoegd of bewerkt door een onderwerp-medewerker of Knowledge Manager is zichtbaar voor iedereen die het onderwerp kan zien.

Onderwerpbekijkers en inzenders kunnen de lijst met bevestigd en gepubliceerde onderwerpen in het onderwerpcentrum zien, maar de onderwerpdetails die een bepaalde persoon kan zien, zijn afhankelijk van de machtigingen die ze hebben voor het bronmateriaal en van de vraag of het onderwerp handmatig is bewerkt.

In de volgende tabel wordt beschreven wat gebruikers , onderwerpbekijkers, medewerkers en kennismanagers, in een bepaald onderwerp kunnen zien op basis van hun machtigingen.

|Onderwerpitem|Wat gebruikers kunnen zien|
|:---------|:------------------|
|Onderwerpnaam|Gebruikers kunnen de onderwerpnaam van alle onderwerpen in het onderwerpcentrum zien. Sommige onderwerpen zijn mogelijk niet zichtbaar als ze een lage relevantie voor de gebruiker hebben.|
|Onderwerpbeschrijving|Door AI gegenereerde beschrijvingen zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud. Handmatig ingevoerde of bewerkte beschrijvingen zijn zichtbaar voor alle gebruikers.|
|Personen|Vastgemaakte personen zijn zichtbaar voor alle gebruikers. Voorgestelde personen zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.|
|Bestanden|Bestanden zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.|
|Pagina's|Pagina's zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.|
|Sites|Sites zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.|

## <a name="best-practices"></a>Aanbevolen procedures

In onderwerpen wordt informatie aan gebruikers gegeven op basis van hun bestaande machtigingen voor inhoud. Microsoft 365 biedt diverse manieren om ervoor te zorgen dat gevoelige inhoud wordt beperkt tot de juiste gebruikers. U kunt niet alleen standaardmachtigingen voor [](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) teams of site's gebruiken, maar ook gevoeligheidslabels of preventie van gegevensverlies om de toegang tot inhoud en [recensies](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) te beperken om de toegang van gebruikers tot gevoelige informatie periodiek te controleren. [](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)

U wordt aangeraden deze hulpmiddelen te gebruiken om ervoor te zorgen dat uw inhoudsmachtigingen juist worden ingesteld binnen uw organisatie. Onderwerpervaringen kunnen uw gebruikers vervolgens nuttige en relevante informatie geven.

Als er onderwerpen zijn die u volledig van onderwerpervaringen wilt uitsluiten, kunt u ook het volgende doen:

- [Sluit gevoelige SharePoint-sites uit van onderwerpdetectie.](topic-experiences-discovery.md#select-sharepoint-topic-sources) Inhoud op deze sites wordt niet weergegeven in de ervaringen met onderwerpen.

- [Onderwerpen uitsluiten op naam.](topic-experiences-discovery.md#exclude-topics-by-name) Onderwerpen die expliciet zijn uitgesloten, worden niet weergegeven in het werken met onderwerpen.

- Knowledge Managers onderwerpen laten verwijderen in het onderwerpcentrum.

Daarnaast raden we de volgende aanbevolen procedures aan:

- Werv kennisbeheerders uit verschillende gebieden van uw organisatie. Kennisbeheerders met diverse expertise (en toegang tot de onderliggende inhoud die door AI wordt gebruikt) kunnen u helpen om de meest nuttige kennis voor uw gebruikers te verzamelen en gevoelige informatie te verwijderen als deze wordt gevonden.

- Een werkstroom instellen voor het aanvragen van wijzigingen. Kennisbeheerders of team- of site-eigenaren moeten een proces volgen waarmee ze uitsluiting van onderwerpen of sites kunnen aanvragen wanneer nieuwe projecten binnen uw organisatie worden gestart of als ze inhoud met ongepaste machtigingsinstellingen vinden.

- Wees op de hoogte van de doelgroep en de gevoeligheid van informatie bij het maken van onderwerpbeschrijvingen. Deze beschrijvingen zijn mogelijk zichtbaar voor gebruikers die geen machtigingen hebben voor de broninhoud voor het onderwerp.

Hoewel u de machtigingen voor afzonderlijke onderwerppagina's kunt wijzigen om de toegang tot een specifieke groep gebruikers te beperken, wordt deze benadering niet aanbevolen vanwege de hoge mate van administratieve inspanning.

## <a name="see-also"></a>Zie ook

[Teams met drie beschermingsniveaus configureren](../solutions/configure-teams-three-tiers-protection.md)

[Onderwerpservaringen plannen](plan-topic-experiences.md)

[Onderwerpservaringen instellen](set-up-topic-experiences.md)
