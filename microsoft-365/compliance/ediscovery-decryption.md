---
title: Ontsleuteling in eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over hoe Microsoft 365 eDiscovery-hulpprogramma's versleutelde documenten verwerken die zijn gekoppeld aan e-mailberichten en zijn opgeslagen in SharePoint Online en OneDrive voor Bedrijven.
ms.openlocfilehash: b87d87b7b0e870d6f396d87dc693fb8f41d5826b
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "52162582"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Ontsleuteling in Microsoft 365 eDiscovery-hulpprogramma's

Versleuteling is een belangrijk onderdeel van uw strategie voor bestandsbeveiliging en informatiebeveiliging. Organisaties van alle typen gebruiken versleutelingstechnologie om gevoelige inhoud binnen hun organisatie te beschermen en ervoor te zorgen dat alleen de juiste personen toegang hebben tot die inhoud.

Als u algemene eDiscovery-taken voor versleutelde inhoud wilt uitvoeren, moesten eDiscovery-managers inhoud van e-mailberichten ontsleutelen terwijl deze werd geëxporteerd vanuit inhoudszoekopdrachten, Core eDiscovery-gevallen en Advanced eDiscovery gevallen. Inhoud die is versleuteld met Microsoft-versleutelingstechnologieën, kan pas worden beoordeeld nadat deze is geëxporteerd.

Om het gemakkelijker te maken om versleutelde inhoud te beheren in de eDiscovery-werkstroom, bevatten Microsoft 365 de hulpprogramma's van eDiscovery nu de ontsleuteling van versleutelde bestanden die zijn gekoppeld aan e-mailberichten en worden verzonden in Exchange Online. <sup>1</sup> Bovendien worden versleutelde documenten die zijn opgeslagen in SharePoint Online en OneDrive voor Bedrijven in een Advanced eDiscovery.

Vóór deze nieuwe mogelijkheid is alleen de inhoud van een e-mailbericht dat is beveiligd door rights management (en niet bijgevoegde bestanden) ontsleuteld. Versleutelde documenten in SharePoint en OneDrive kunnen niet worden ontsleuteld tijdens de eDiscovery-werkstroom. Bestanden die zijn versleuteld met een Microsoft-versleutelingstechnologie bevinden zich nu op een SharePoint- of OneDrive-account, kunnen worden doorzocht en ontsleuteld wanneer de zoekresultaten worden voorbereid voor een voorbeeld, worden toegevoegd aan een revisieset in Advanced eDiscovery en worden geëxporteerd. Bovendien kunnen versleutelde documenten in SharePoint en OneDrive die zijn gekoppeld aan een e-mailbericht, worden doorzocht. Met deze ontsleutelingsfunctie kunnen eDiscovery-managers de inhoud van versleutelde e-mailbijlagen en sitedocumenten bekijken bij het bekijken van zoekresultaten en deze bekijken nadat ze zijn toegevoegd aan een revisieset in Advanced eDiscovery.

## <a name="supported-encryption-technologies"></a>Ondersteunde versleutelingstechnologieën

Microsoft eDiscovery-hulpprogramma's ondersteunen items die zijn versleuteld met Microsoft-versleutelingstechnologieën. Deze technologieën zijn Azure Rights Management en Microsoft Information Protection (specifiek gevoeligheidslabels). Zie Versleuteling voor meer [](encryption.md)informatie over Microsoft-versleutelingstechnologieën. Inhoud die is versleuteld door versleutelingstechnologieën van derden, wordt niet ondersteund. Het bekijken of exporteren van inhoud die is versleuteld met niet-Microsoft-technologieën, wordt bijvoorbeeld niet ondersteund.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>eDiscovery-activiteiten die versleutelde items ondersteunen

In de volgende tabel worden de ondersteunde taken geïdentificeerd die kunnen worden uitgevoerd in Microsoft 365 eDiscovery-hulpprogramma's voor versleutelde bestanden die zijn gekoppeld aan e-mailberichten en versleutelde documenten in SharePoint en OneDrive. Deze ondersteunde taken kunnen worden uitgevoerd op versleutelde bestanden die voldoen aan de criteria van een zoekopdracht. Een waarde van `N/A` geeft aan dat de functionaliteit niet beschikbaar is in het bijbehorende hulpprogramma eDiscovery.

|eDiscovery-taak  |Inhoud zoeken  |Core eDiscovery  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|Zoeken naar inhoud in versleutelde bestanden in e-mail en sites<sup>1</sup>     |Ja      |Ja      |Ja      |
|Voorbeeld van versleutelde bestanden die zijn gekoppeld aan e-mail     |Ja      |Ja     |Ja       |
|Een voorbeeld bekijken van versleutelde documenten in SharePoint en OneDrive|Nee      |Nee    |Ja       |
|Versleutelde bestanden in een revisieset controleren    |N.v.t.      |N.v.t.        | Ja        |
|Versleutelde bestanden exporteren die zijn gekoppeld aan e-mail    |Ja       |Ja  |Ja    |
|Versleutelde documenten exporteren in SharePoint en OneDrive    |Nee       |Nee  |Ja    |
|||||

> [!NOTE]
> <sup>1</sup> Versleutelde bestanden die zich op een lokale computer bevinden (en niet zijn opgeslagen op een SharePoint of OneDrive-site) worden niet geïndexeerd voor eDiscovery. Dit betekent dat als een versleuteld lokaal bestand is gekoppeld aan een e-mailbericht, het bestand niet wordt geretourneerd door een trefwoordzoekquery, zelfs niet als het bestand trefwoorden bevat die overeenkomen met de zoekquery. E-mailberichten met lokaal versleuteld bestand kunnen echter worden geretourneerd door een eDiscovery-zoekopdracht als een e-mailbezit (zoals verzonden datum, afzender, geadresseerde of onderwerp) overeenkomt met de zoekquery.

### <a name="decryption-limitations-with-sensitivity-labels"></a>Ontsleutelingsbeperkingen met gevoeligheidslabels

eDiscovery biedt geen ondersteuning voor versleutelde bestanden in SharePoint en OneDrive wanneer een gevoeligheidslabel waarop de versleuteling is toegepast, is geconfigureerd met een van de volgende instellingen:

- Gebruikers kunnen machtigingen toewijzen wanneer ze het label handmatig toepassen op een document. Dit wordt soms door de gebruiker *gedefinieerde machtigingen genoemd.*

- Gebruikerstoegang tot het document heeft een vervaldatuminstelling die is ingesteld op een andere waarde dan **Nooit.**

Zie de sectie Versleutelingsinstellingen configureren in Toegang tot inhoud beperken met gevoeligheidslabels om versleuteling toe te passen voor meer informatie over [deze instellingen.](encryption-sensitivity-labels.md#configure-encryption-settings)

Documenten die zijn versleuteld met de vorige instellingen, kunnen nog steeds worden geretourneerd door een eDiscovery-zoekopdracht. Dit kan gebeuren wanneer een document (zoals de titel, auteur of gewijzigde datum) aan de zoekcriteria voldoet. Hoewel deze documenten mogelijk worden opgenomen in zoekresultaten, kunnen ze niet worden bekeken of gecontroleerd. Deze documenten blijven ook versleuteld wanneer ze worden geëxporteerd in Advanced eDiscovery.

## <a name="requirements-for-decryption-in-ediscovery"></a>Vereisten voor ontsleuteling in eDiscovery

U moet de rol RMS Decrypt toegewezen krijgen om bestanden te bekijken, te bekijken en te exporteren die zijn versleuteld met Microsoft-versleutelingstechnologieën. U moet deze rol ook krijgen toegewezen om versleutelde bestanden te bekijken en te query's te maken die zijn toegevoegd aan een revisieset in Advanced eDiscovery.

Deze rol wordt standaard toegewezen aan de rollengroep eDiscovery Manager op de pagina Machtigingen in het Office 365 Beveiligings- & Compliancecentrum.  Zie [eDiscovery-machtigingen](assign-ediscovery-permissions.md#rms-decrypt)toewijzen voor meer informatie over de rol RMS-decryptie.
