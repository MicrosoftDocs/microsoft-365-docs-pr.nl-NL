---
title: Wat is er nieuw in Microsoft 365-compliance
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Of het nu gaat om het toevoegen van nieuwe oplossingen aan het compliancecentrum, het bijwerken van bestaande functies op basis van uw feedback of het implementeren van nieuwe en bijgewerkte documentatie, met Microsoft 365 kunt u het steeds veranderende compliancelandschap in de hand houden. Ontdek wat we deze maand hebben gedaan.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1884989abba56a7da68a2a1372132015a81f5e03
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985010"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Wat is er nieuw in Microsoft 365-compliance

Of het nu gaat om het toevoegen van nieuwe oplossingen aan de [Microsoft 365-compliancecentrum,](microsoft-365-compliance-center.md)het bijwerken van bestaande functies op basis van uw feedback of het implementeren van nieuwe en bijgewerkte documentatie, met Microsoft 365 kunt u op de hoogte blijven van het steeds veranderende compliancelandschap. Bekijk hieronder wat er nieuw is in Microsoft 365 compliance.

> [!NOTE]
> Sommige compliancefuncties worden met verschillende snelheden uitgerold voor onze klanten. Als u nog geen functie ziet, kunt u proberen om uzelf toe te voegen aan [een gerichte release.](/office365/admin/manage/release-options-in-office-365)

> [!TIP]
> Bent u geïnteresseerd in wat er gebeurt in andere beheercentra? Bekijk deze artikelen:<br>[Nieuwe functies in de Microsoft 365-beheercentrum](/office365/admin/whats-new-in-preview)<br>[Nieuwe functies in het SharePoint beheercentrum](/sharepoint/what-s-new-in-admin-center)<br>[Wat is er nieuw in Microsoft 365 Defender](../security/defender/whats-new.md)<br><br>
En ga naar [Microsoft 365 routekaart](https://www.microsoft.com/microsoft-365/roadmap) voor meer Microsoft 365 functies die zijn gestart, worden uitgerold, in ontwikkeling zijn, zijn geannuleerd of eerder zijn uitgebracht.

## <a name="may-2021"></a>Mei 2021

### <a name="data-loss-prevention"></a>Preventie van gegevensverlies

- Nieuwe richtlijnen voor [het plannen van uw strategie voor preventie van gegevensverlies.](dlp-overview-plan-for-dlp.md)

### <a name="retention-and-records-management"></a>Bewaar- en recordbeheer

- Als u een bewaarbeleid los laat van een SharePoint-site of OneDrive-account, hoeft u niet langer te wachten op de respijtperiode van 30 dagen voordat u de site of het account kunt verwijderen. Een populair verzoek van klanten, deze wijziging is nu voltooid voor alle tenants.
- In preview, **multi-stage disposition review:** Een beheerder kan nu maximaal vijf opeenvolgende stadia van [disposition review](disposition.md) voor een bewaarlabel toevoegen en revisoren kunnen andere gebruikers toevoegen aan hun beoordelingsfase. U kunt ook de e-mailmeldingen en herinneringen aanpassen.

### <a name="sensitive-information-types"></a>Gevoelige informatietypen

- Nieuwe informatie toegevoegd om u te helpen [een woordenlijst met trefwoorden te wijzigen.](sit-modify-keyword-dictionary.md)

### <a name="sensitivity-labels"></a>Vertrouwelijkheidslabels

- In preview is er nu een nieuwe instelling voor **verificatiecontext** beschikbaar wanneer u een [gevoeligheidslabel]( sensitivity-labels-teams-groups-sites.md)configureert voor groepen en sites. Deze optie werkt in combinatie met beleidsregels voor Azure AD Conditional Access om strengere voorwaarden af te dwingen wanneer gebruikers toegang krijgen tot SharePoint sites waarop het label is toegepast. Zorg ervoor dat u de [afhankelijkheden en beperkingen leest](sensitivity-labels-teams-groups-sites.md#more-information-about-the-dependencies-for-the-authentication-context-option) voordat u deze instelling configureert.
- [Beleidsregels voor](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) automatisch labelen die alleen zijn geconfigureerd voor Exchange ondersteunen nu **gevoeligheidslabels** die versleuteling toepassen met Gebruikers machtigingen laten toewijzen voor de opties Niet doorsturen of Encrypt-Only toewijzen.
- [Verplichte labeling](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) is nu algemeen beschikbaar voor alle Office apps, op alle platforms.

## <a name="april-2021"></a>April 2021

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- [Limieten in Advanced eDiscovery](/microsoft-365/compliance/limits-ediscovery20#export-limits---final-export-out-of-review-set). Organisaties kunnen nu maximaal 5 miljoen items of 500 MB exporteren, wat kleiner is, in één export van items uit een revisieset.

### <a name="data-classification"></a>Gegevensclassificatie

- [Labeling-activiteiten die beschikbaar zijn in Activiteitenverkenner](/microsoft-365/compliance/data-classification-activity-explorer-available-events)

### <a name="data-connectors"></a>Gegevensconnectors

- [Een connector instellen voor het archiveren van Cisco Jabber op Oracle-gegevens](/microsoft-365/compliance/archive-ciscojabberonoracle-data)
- [Een connector instellen voor het archiveren van Cisco Jabber op PostgreSQL-gegevens](/microsoft-365/compliance/archive-ciscojabberonpostgresql-data)

### <a name="data-loss-prevention"></a>Preventie van gegevensverlies

- Nieuw onderwerp voor [tips voor preventie van gegevensverlies.](/microsoft-365/compliance/dlp-policy-tips-reference)
- Nieuw onderwerp voor [Meer informatie over preventie van gegevensverlies.](/microsoft-365/compliance/dlp-learn-about-dlp)
- Nieuw onderwerp voor [Aan de slag met het waarschuwingsdashboard voor preventie van gegevensverlies.](/microsoft-365/compliance/dlp-alerts-dashboard-get-started)

### <a name="retention-policies-and-retention-label-policies"></a>Bewaarbeleid en bewaarlabelbeleid

- De Microsoft 365 Groups-locatie ondersteunt nu het toepassen van de bewaarinstellingen op alleen Microsoft 365-postvakken SharePoint alleen de verbonden SharePoint-sites met behulp van de [PowerShell-cmdlet Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) met de parameter *Applications.*

### <a name="sensitivity-labels"></a>Vertrouwelijkheidslabels

Outlook releases en updates:
- [Verschillende instellingen voor het standaardlabel en verplichte labeling](sensitivity-labels-office-apps.md#outlook-specific-options-for-default-label-and-mandatory-labeling) worden nu ondersteund voor ingebouwde labeling. Voorheen werden deze instellingen alleen ondersteund door de geïntegreerde AIP-labelingclient.
- [Encrypt-Only](encryption-sensitivity-labels.md#let-users-assign-permissions) wordt nu ondersteund door macOS, iOS en Android.
- [Verplichte labeling](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) wordt uitgerold naar de overige platforms.
- [Dynamische markeringen met alle variabelen worden](sensitivity-labels-office-apps.md#dynamic-markings-with-variables) ondersteund in alle Outlook clients.

## <a name="march-2021"></a>Maart 2021

Hier zijn een paar van de wijzigingen in Microsoft 365 complianceoplossingen en -inhoud voor de maand maart.

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- **Advanced eDiscovery verzamelingen** ondersteunt nu het [nieuwe hulpprogramma voor verzamelingen en werkstroom.](/microsoft-365/compliance/collections-overview) Andere nieuwe onderwerpen zijn [het maken van een conceptverzameling,](/microsoft-365/compliance/create-draft-collection)het maken van een conceptverzameling aan een [revisieset](/microsoft-365/compliance/commit-draft-collection)en [verzamelingsstatistieken en -rapporten.](/microsoft-365/compliance/collection-statistics-reports)
- **Documenten in** een revisieset exporteren naar een [Azure Storage](/microsoft-365/compliance/download-export-jobs) account.
- **Module voor voorspellende codering voor Advanced eDiscovery.** Bekijk eerst de nieuwe [functie voor voorspellende codering](/microsoft-365/compliance/predictive-coding-overview) die de niet-bestaande relevantiemodule vervangt.

### <a name="data-classification"></a>Gegevensclassificatie

- **Gegevensclassificatieverkenner**. [Aan de slag](/microsoft-365/compliance/data-classification-activity-explorer) met gegevensclassificatieverkenner.

### <a name="data-connectors"></a>Gegevensconnectors

- **Privésleutels.** Ondersteuning voor privésleutels is toegevoegd aan gegevens van [Het bericht van Bloomberg,](/microsoft-365/compliance/archive-bloomberg-message-data#set-up-a-connector-using-public-keys) [ICE Chat-gegevens](/microsoft-365/compliance/archive-icechat-data#set-up-a-connector-using-public-keys) en [Instant Bloomberg-gegevensconnectoren.](/microsoft-365/compliance/archive-instant-bloomberg-data#set-up-a-connector-using-public-keys)

### <a name="data-loss-prevention"></a>Preventie van gegevensverlies

- **Microsoft Teams ondersteuning**. Ondersteuning voor preventie van gegevensverlies uitgebreid tot [Microsoft Teams.](/microsoft-365/compliance/dlp-teams-default-policy)
- **Microsoft Compliance-extensie**. Aan de slag met de [Microsoft Compliance-extensie](/microsoft-365/compliance/dlp-chrome-get-started).

### <a name="encryption"></a>Versleuteling

- **Klantcode voor Microsoft 365.** [Overzicht van de klantsleutel](/microsoft-365/compliance/customer-key-tenant-level) voor Microsoft 365 op tenantniveau (openbare preview).
- **Dubbele-sleutelversleuteling**. Meer informatie over het [inschakelen van ondersteuning voor gelabelde en](/microsoft-365/compliance/double-key-encryption) beveiligde documenten in SharePoint en OneDrive voor Bedrijven.

### <a name="insider-risk-management"></a>Intern risicobeheer

De volgende insider-functies voor risicobeheer zijn in maart uitgebracht voor een openbare preview:

- Nieuwe analysefunctie voor het identificeren van risico's voordat u beleidsregels voor insiderrisico's maakt
- Ondersteuning en beheer van nieuwe risicoactiviteitsreeksdetectie
- Ondersteuning voor nieuwe cumulatieve exfiltratiedetectie
- Nieuwe in-app beleidsrapportage en ondersteuning voor aanbevelingen
- Nieuwe controlelogboekfunctie en -rapportage
- Verbeteringen aan de wizard Beleid maken
- Updates voor Inhoudsverkenner
- Nieuw gebruikersbeheerproces/-ondersteuning (gebruikers toevoegen/verwijderen uit beleid)
- Nieuwe ondersteuning voor AAD-integratie (ondersteuning voor gebruikersbeleid)
- Bijgewerkte domeinondersteuning in beleidsregels (REGEX)
- Verbeteringen en verbeteringen van beleidssjabloon

De volgende onderwerpen zijn bijgewerkt of toegevoegd ter ondersteuning van deze nieuwe functies:

- [Meer informatie over intern risicobeheer](/microsoft-365/compliance/insider-risk-management)
- [Intern risicobeheer plannen](/microsoft-365/compliance/insider-risk-management-plan)
- [Aan de slag met instellingen voor insider-risicobeheer](/microsoft-365/compliance/insider-risk-management-settings)
- [Aan de slag met insider-risicobeheer](/microsoft-365/compliance/insider-risk-management-configure)
- [Intern risicobeleid maken en beheren](/microsoft-365/compliance/insider-risk-management-policies)
- [Waarschuwingen voor insider-risico onderzoeken](/microsoft-365/compliance/insider-risk-management-alerts)
- [Actie ondernemen in het geval van insider-risico](/microsoft-365/compliance/insider-risk-management-cases)
- [Activiteiten controleren met insider-risico auditlogboek.](/microsoft-365/compliance/insider-risk-management-audit-log)
- [Gegevens controleren met de Verkenner voor inhoud met insider-risico](/microsoft-365/compliance/insider-risk-management-content-explorer)
- [De werkstroom beheren met het gebruikersdashboard](/microsoft-365/compliance/insider-risk-management-users)

### <a name="records-management"></a>Records Management

- **Verbeteringen in bestandsplan.** Met een update [voor het bestandsplan](file-plan-manager.md) worden de vorige lengtebeperkingen voor importeren verwijderd of verbeterd.
- **Bewaarlabels voor records verwijderen.** Een preview-release ondersteunt de mogelijkheid om [bewaarlabels te verwijderen die](create-apply-retention-labels.md#deleting-retention-labels) items markeren als records.

### <a name="sensitive-information-types"></a>Gevoelige informatietypen

Inhoud is toegevoegd of bijgewerkt in de volgende onderwerpen:

- [Aan de slag met aangepast type gevoelige informatie](/microsoft-365/compliance/create-a-custom-sensitive-information-type)
- [Meer informatie over typen gevoelige informatie](/microsoft-365/compliance/sensitive-information-type-learn-about)
- [Aangepaste gevoelige informatietypen maken met een classificatie op basis van Exacte gegevensmatch](/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [Meldingen maken voor exacte gegevensmatchactiviteiten](/microsoft-365/compliance/sit-edm-notifications-activities)
- [Entiteitsdefinities van het type gevoelige informatie](/microsoft-365/compliance/sensitive-information-type-entity-definitions)
- [Een aangepast type gevoelige informatie maken met PowerShell](/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [Een woordenlijst met trefwoorden maken](/microsoft-365/compliance/create-a-keyword-dictionary)

### <a name="sensitivity-labels"></a>Vertrouwelijkheidslabels

- **DoD-ondersteuning**. Ondersteuning voor Amerikaanse overheidsten tenants met DoD-omgevingen.
- **Alleen-versleutelen voor Outlook**. Versleutelingsopties voor Outlook bevatten nu Encrypt-Only wanneer u Gebruikers machtigingen laten [toewijzen selecteert.](encryption-sensitivity-labels.md#let-users-assign-permissions)
- **Ingebouwde labels afdwingen in Office-apps.** Bijgewerkte [richtlijnen](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client) voor het afdwingen van ingebouwde labels in Office-apps wanneer u de geïntegreerde labelingclient van Azure Information Protection hebt geïnstalleerd.

## <a name="february-2021"></a>Februari 2021

Hier zijn enkele wijzigingen in microsoft 365-complianceoplossingen en -inhoud voor de maand februari.

### <a name="auditing"></a>Controleren

- **Bewaarbeleid voor auditlogboek beheren.** Meer informatie over het nieuwe [dashboard Controle bewaarbeleid](/microsoft-365/compliance/audit-log-retention-policies#manage-audit-log-retention-policies-1).
- **Zoek in het auditlogboek**. [PowerShell-script gebruiken om het auditlogboek te doorzoeken.](/microsoft-365/compliance/audit-log-search-script)

### <a name="data-classification-content-explorer"></a>Inhoudsverkenner voor gegevensclassificatie

Inhoud is toegevoegd of bijgewerkt in de volgende onderwerpen:

- [Aan de slag met de inhoudsverkenner](/microsoft-365/compliance/data-classification-content-explorer)
- [Opmerkingen bij de release van gegevensclassificatie](/microsoft-365/compliance/data-classification-pub-preview-relnotes)

### <a name="data-loss-prevention"></a>Preventie van gegevensverlies

Inhoud is toegevoegd of bijgewerkt in de volgende onderwerpen:

- [Meer informatie over Endpoint DLP](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Send email notifications and show policy tips for DLP policies](/microsoft-365/compliance/use-notifications-and-policy-tips) (E-mailmeldingen verzenden en beleidstips tonen voor DLP-beleid)
- [Meer informatie over de on-premises scanner voor preventie van gegevensverlies van Microsoft 365](/microsoft-365/compliance/dlp-on-premises-scanner-learn)
- [Aan de slag met de on-premises scanner voor preventie van gegevensverlies](/microsoft-365/compliance/dlp-on-premises-scanner-get-started)
- [Een DLP-beleid maken om documenten te beveiligen met FCI of andere eigenschappen](/microsoft-365/compliance/protect-documents-that-have-fci-or-other-properties)
- [Preventie van gegevensverlies van eindpunten gebruiken](/microsoft-365/compliance/endpoint-dlp-using)
- [Aan de slag met Eindpunt-DLP (gegevensverlies voor eindpunten)](/microsoft-365/compliance/endpoint-dlp-getting-started)

### <a name="ediscovery"></a>eDiscovery

Inhoud is toegevoegd of bijgewerkt in de volgende onderwerpen:

- [Ontsleuteling in microsoft 365 eDiscovery-hulpprogramma's](/microsoft-365/compliance/ediscovery-decryption)
- [Trefwoordquery's en zoekvoorwaarden](/microsoft-365/compliance/keyword-queries-and-search-conditions#limitations-for-searching-sensitive-data-types)
- [Uittreding van de relevantiemodule in Advanced eDiscovery](/microsoft-365/compliance/relevance-module-retirement)
- [Een script gebruiken om gebruikers toe te voegen aan een wacht in een Hoofd-eDiscovery-zaak](/microsoft-365/compliance/use-a-script-to-add-users-to-a-hold-in-ediscovery)

### <a name="encryption"></a>Versleuteling

Inhoud is toegevoegd of bijgewerkt in de volgende onderwerpen:

#### <a name="azure-rights-management-service-rms"></a>Azure Rights Management Service (RMS)

- [Door de klant beheerde versleutelingsfuncties](/microsoft-365/compliance/office-365-customer-managed-encryption-features)
- [Exchange Online-e-mailversleuteling met AD RMS](/microsoft-365/compliance/information-rights-management-in-exchange-online). Ondersteuning voor deze service is afgeschaft. U kunt AD RMS niet meer gebruiken in een hybride Exchange-omgeving. In plaats daarvan migreert u naar Azure RMS.

#### <a name="customer-key"></a>Klantsleutel

- [Klantcode voor Microsoft 365 op tenantniveau](/microsoft-365/compliance/customer-key-tenant-level)
- [Overzicht van beveiliging en naleving](/microsoftteams/security-compliance-overview)

#### <a name="information-rights-management-irm"></a>Information Rights Management (IRM)

- [IRM (Information Rights Management) toepassen op een lijst of bibliotheek.](/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server) Deze nationale wolken ondersteunen deze instelling niet:
    - Microsoft Cloud voor amerikaanse overheid
    - Microsoft Cloud Germany
    - Azure en Microsoft 365 beheerd door 21Vianet in China)
- [Configureer IRM om een on-premises AD RMS-server te gebruiken.](/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server) Ondersteuning voor deze service in een hybride Exchange-omgeving is afgeschaft.

### <a name="sensitive-information-types"></a>Gevoelige informatietypen

Inhoud is toegevoegd of bijgewerkt in de volgende onderwerpen:

- [Meer informatie over typen gevoelige informatie](/microsoft-365/compliance/sensitive-information-type-learn-about)
- [Een aangepast type voor vertrouwelijke gegevens maken met PowerShell](/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [Een aangepaste gevoelige informatietypen maken met een classificatie op basis van Exacte gegevensmatch](/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [Definities van entiteiten van het type vertrouwelijke gegevens](/microsoft-365/compliance/sensitive-information-type-entity-definitions)


### <a name="sensitivity-labels"></a>Vertrouwelijkheidslabels

Inhoud is toegevoegd of bijgewerkt in de volgende onderwerpen:

- **Extern delen in SharePoint**. Voor [containerlabels](sensitivity-labels-teams-groups-sites.md) wordt de optie voor extern delen van SharePoint-sites nu uitgebracht als algemeen beschikbaar. Daarnaast ondersteunen het Microsoft 365-beheercentrum en Planner nu het toepassen van deze gevoeligheidslabels. 
- **Coauteuring en Automatisch opslaan**. Ondersteuning voor [coauteuring en Automatisch opslaan](sensitivity-labels-coauthoring.md) voor versleutelde bestanden wordt uitgebracht als voorbeeld voor het testen in niet-productieten tenants.

## <a name="january-2021"></a>Januari 2021

### <a name="support-for-card-content-in-teams"></a>Ondersteuning voor kaartinhoud in Teams

De volgende microsoft 365-complianceoplossingen ondersteunen nu de detectie van [kaartinhoud](/microsoftteams/platform/task-modules-and-cards/what-are-cards) die wordt gegenereerd via apps in Teams-berichten:

- **Core en Advanced eDiscovery**. Kaartinhoud kan nu in [de wacht worden geplaatst](create-ediscovery-holds.md#preserve-card-content) of worden opgenomen in [zoekopdrachten](/microsoftteams/ediscovery-investigation#search-for-card-content) (ook van toepassing op zoeken naar inhoud).
- **Audit**. Kaartactiviteit wordt nu [opgenomen in het auditlogboek](/microsoftteams/audit-log-events#teams-activities).
- **Bewaarbeleid**. Kan nu bewaarbeleid gebruiken om [kaartinhoud te behouden en te verwijderen.](retention-policies-teams.md#whats-included-for-retention-and-deletion)

### <a name="information-governance-and-records-management"></a>Informatiebeheer en recordbeheer

[Nieuwe beoordeling voor](retention-regulatory-requirements.md#new-zealand-public-records-act) het gebruik van informatiebeheer en recordbeheer om te voldoen aan nalevingsverplichtingen voor de New Zealand Public Records Act.

### <a name="sensitivity-labels"></a>Vertrouwelijkheidslabels

- Gevoeligheidslabels worden nu ondersteund voor tenants van de Amerikaanse overheid (GCC en GCC-H).
- Nieuwe [ondersteuning voor automatische labeling](sensitivity-labels-office-apps.md) voor macOS.

## <a name="december-2020"></a>December 2020

### <a name="spotlight-new-content-for-insider-risk-solutions"></a>Spotlight: Nieuwe inhoud voor oplossingen voor insiderrisico's

Het microsoft 365 compliance-inhoudsteam is hard bezig met het maken van documenten met 'inhoudsoplossing' om te bevorderen hoe compliancemogelijkheden samen kunnen worden gebruikt om uw nalevingsdoelstellingen te bereiken.

Ten eerste is inhoud die onze insiderrisicooplossingen met elkaar verbindt: communicatie compliance, insider risk management, informatiebarrières en privileged access management. Hier ziet u wat u kunt vinden:

- [Nieuwe landingspagina voor insiderrisicooplossingen.](insider-risk-solution-overview.md) Bevat details over de risico's die de oplossingen kunnen helpen beperken, licentievereisten, implementatiereeks, architectuurillustraties, trainingsbronnen en meer.
- Nieuwe overzichtsartikelen voor elke insider-risicooplossing. Richtlijnen en koppelingen naar artikelen die u helpen bij het plannen, implementeren en beheren van elke oplossing:
  - [Communicatiecompliance](communication-compliance-solution-overview.md)
  - [Intern risicobeheer](insider-risk-management-solution-overview.md)
  - [Informatiebelemmeringen](information-barriers-solution-overview.md)
  - [Privileged Access Management](privileged-access-management-solution-overview.md)
  
Er komen binnenkort meer inhoudsoplossings docs!

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

Verbeterde werkstroom en functionaliteit voor het toevoegen van [bewaarders](add-custodians-to-case.md) en [niet-bewaardergegevensbronnen](non-custodial-data-sources.md) aan een Advanced eDiscovery zaak.

### <a name="data-connectors"></a>Gegevensconnectors

[Er zijn vier nieuwe Veritas-connectors](archiving-third-party-data.md#third-party-data-connectors)uitgebracht: Redtail Speak, Salesforce Chatter, ServiceNow en Yieldbroker.

### <a name="encryption"></a>Versleuteling

Maak kennis [met klantsleutel voor Microsoft 365 op tenantniveau.](customer-key-tenant-level.md) Met behulp van de door u op te geven sleutels kunt u een dep (Data Encryption Policy) maken en deze toewijzen aan de tenant. De DEP versleutelt gegevens in de tenant voor deze werkbelastingen:

- Teams chatberichten (1:1 chats, groepschats, vergaderingschats en kanaalgesprekken)
- Teams mediaberichten (afbeeldingen, codefragmenten, video's, wikiafbeeldingen)
- Teams gespreks- en vergaderingsopnamen die zijn opgeslagen in Teams opslag
- Teams chatmeldingen
- Teams chatsuggesties per Cortana
- Teams statusberichten
- Gebruikers- en signaalgegevens voor Exchange Online

### <a name="records-management"></a>Records Management

De [rollengroep Records management verleent](get-started-with-records-management.md#permissions-required-for-records-management) nu machtigingen voor alle functies voor recordbeheer, inclusief beoordeling van de beschikking.

### <a name="sensitivity-labels"></a>Vertrouwelijkheidslabels

- [Gegevens automatisch labelen in Azure Purview (voorbeeld)](/azure/purview/create-sensitivity-label). U kunt nu gevoeligheidslabels maken en automatisch toepassen op activa in Azure Purview, zoals bestanden in Azure Blob-opslag en databasekolommen in SQL Server.
- [Gebruikers moeten een label toepassen op items.](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) Deze nieuwe optie wordt ook wel 'verplichte labeling' genoemd en vereist dat gebruikers een gevoeligheidslabel kiezen en toepassen onder de specifieke scenario's.
