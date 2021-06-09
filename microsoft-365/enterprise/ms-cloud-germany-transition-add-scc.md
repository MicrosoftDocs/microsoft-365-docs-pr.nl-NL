---
title: Informatie over eDiscovery-ervaring tijdens de migratie van Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Overzicht: eDiscovery-migratiestappen voor de migratie van Microsoft Cloud Deutschland.'
ms.openlocfilehash: 0128c8563b2043e4ec41d2c5ab1b208bd3977511
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844248"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a>Informatie over de eDiscovery-ervaring tijdens de migratie van Microsoft Cloud Deutschland
In de volgende secties vindt u aanvullende informatie over de eDiscovery-ervaring bij het over stappen van Microsoft Cloud Germany (Microsoft Cloud Deutschland) naar Office 365 services in de nieuwe Duitse datacenterregio.

## <a name="ediscovery-administration-until-phase-4"></a>eDiscovery-beheer tot fase 4
Tot fase 4 is het Beveiligings- en compliancecentrum volledig beschikbaar. Alle inhoud blijft nog steeds in de Microsoft Cloud Germany staan en kan worden beheert door het Microsoft Cloud Germany Security and Compliance Center ( https://protection.office.de/) .

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a>eDiscovery-ervaring tussen fase 4 tot het einde van fase 9
Vanaf het begin van fase 4 tot fase 9 is voltooid, mislukken eDiscovery-zoekopdrachten of retourneren 0 resultaten voor SharePoint Online OneDrive voor Bedrijven- en Exchange Online-locaties die zijn gemigreerd.

> [!NOTE]
> Tijdens de migratie kunnen klanten zaken blijven maken, in- en uitbaten en exporteren in het [beveiligings- & compliancecentrum,](/microsoft-365/compliance/manage-legal-investigations)inclusief [Inhoud zoeken.](/microsoft-365/compliance/search-for-content) Zoekopdrachten met SharePoint online, OneDrive voor Bedrijven en Exchange Online die zijn gemigreerd, leveren echter 0 resultaten op of leveren een fout op.

Als een zoekopdracht nul resultaten of een fout oplevert tijdens de migratie, moet u de volgende actie ondernemen voor SharePoint Online:

- Download sites rechtstreeks van de SharePoint Online- of OneDrive voor Bedrijven-site door de instructies te volgen in Bestanden en mappen downloaden van OneDrive of [SharePoint.](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) Voor deze methode zijn SharePoint beheerdersmachtigingen of alleen-lezen-machtigingen op de site vereist.
- Als limieten worden overschreden, zoals wordt uitgelegd in Bestanden en mappen downloaden van OneDrive of [SharePoint,](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)kunnen klanten de synchronisatieclient OneDrive voor Bedrijven gebruiken door de richtlijnen in Bestanden synchroniseren SharePoint en [Teams met](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)uw computer te volgen.

- Zie voor meer informatie [In-place eDiscovery in Exchange Server.](/Exchange/policy-and-compliance/ediscovery/ediscovery)


## <a name="ediscovery-administration-after-phase-9"></a>eDiscovery-beheer na fase 9

**Van toepassing op:** Alle klanten die eDiscovery gebruiken

In fase 9 worden de laatste stappen voor het verplaatsen naar het nieuwe Duitse datacenter voltooid. In deze fase worden alle resterende serviceonderdelen gemigreerd.
Na fase 9 wordt het gebruik van het Beveiligings- en compliancecentrum in Microsoft Cloud Germany (protection.office.de) niet meer ondersteund. Gebruik in plaats daarvan [het nieuwe beveiligingscentrum](https://security.microsoft.com/) [of compliancecentrum.](https://compliance.microsoft.com/) Alle gegevens zijn gemigreerd naar de nieuwe beheerportalen.

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
|  Alle SharePoint online, OneDrive voor Bedrijven en Exchange Online zijn samen met het SCC (Security and Compliance Center) gemigreerd. | Alle eDiscovery-activiteiten moeten worden uitgevoerd vanuit de wereldwijde tenant. Zoekopdrachten zijn nu 100% succesvol. Eventuele fouten of fouten moeten de normale ondersteuningskanalen volgen. | Geen |
||||

### <a name="ediscovery-retention-policy"></a>eDiscovery-bewaarbeleid
**Van toepassing op:**  Alle klanten die een bewaarbeleid hebben toegepast als onderdeel van de stappen vóór de migratie

| Stap(en) | Beschrijving | Gevolg |
|:-------|:-------|:-------|
| Bewaarbeleid voor de hele organisatie verwijderen dat is gemaakt tijdens de stappen vóór de migratie | Klanten kunnen het bewaarbeleid voor de hele organisatie verwijderen dat is gemaakt tijdens het werk van de klanten vóór de migratie. | Geen |
||||
