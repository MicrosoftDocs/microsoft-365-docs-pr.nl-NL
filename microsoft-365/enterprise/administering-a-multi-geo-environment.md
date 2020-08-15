---
title: Een omgeving met meerdere geografische gebieden beheren
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Beheerders kunnen leren hoe u SharePoint-en OneDrive-Services beheert in een omgeving met meerdere geografische omgevingen.
ms.openlocfilehash: 1b6d2cb1cb9511677f717f0e58553abc4473e1ad
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688946"
---
# <a name="administering-a-multi-geo-environment"></a>Een omgeving met meerdere geografische gebieden beheren

Hier ziet u een overzicht van de manier waarop Microsoft 365-Services in een omgeving met meerdere geografische omgevingen werken.

## <a name="audit-log-search"></a>Zoeken in audit logboek

Er is een uniform [audit logboek](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c) voor al uw satelliet locaties beschikbaar op de pagina microsoft 365 audit log Search. U kunt alle controlelogboekvermeldingen van de geografische locaties weergeven, & zoals naam van gebruikers van de gebruikers in de weergave van de organisatie, en vervolgens kunt u bestaande filters toepassen om specifieke activiteiten van gebruikers te bekijken.

## <a name="bcs-secure-store-apps"></a>BCS, Secure Store, apps

BCS, Secure Store en apps hebben allemaal afzonderlijke exemplaren in elke locatie van de satelliet, zodat de beheerder van SharePoint Online deze services afzonderlijk kan beheren en configureren vanuit elke locatie van satellieten.

## <a name="ediscovery"></a>eDiscovery 

Standaard kan een eDiscovery-beheerder of beheerder van een meervoudige geo-Tenant alleen eDiscovery uitvoeren op de centrale locatie van de Tenant. De globale beheerder van Office 365 moet de machtigingen van een eDiscovery-beheerder toewijzen om de gebruikers de mogelijkheid te bieden eDiscovery uit te voeren en een ' regio '-parameter toe te wijzen aan het toepasselijke beveiligings filter voor de vestiging, anders wordt er geen eDiscovery-actie uitgevoerd voor de locatie van de satelliet. Als u het beveiligings filter voor naleving voor een regio wilt configureren, raadpleegt u [Office 365 multi-geo eDiscovery configureren](multi-geo-ediscovery-configuration.md).

## <a name="exchange-mailboxes"></a>Exchange-postvakken

De Exchange-postvakken van gebruikers worden automatisch verplaatst als hun PDL wordt gewijzigd. Wanneer een nieuw postvak wordt gemaakt, wordt dit geconfigureerd voor de PDL van de gebruiker of voor de centrale locatie als er geen waarde voor de PDL van de gebruiker is ingesteld.

## <a name="information-protection-ip-data-loss-prevention-dlp-policy"></a>Beleidsregels voor informatiebescherming (DLP) voor preventie van gegevensverlies (DLP)

U kunt de DLP-beleidsregels voor OneDrive voor bedrijven, SharePoint en Exchange instellen in het beveiligings-en compliance-centrum, de bereikregels naar wens voor de volledige Tenant of voor de desbetreffende gebruikers opgeven. Bijvoorbeeld: als u een beleid voor een gebruiker op een locatie wilt selecteren, selecteert u om het beleid toe te passen op een specifieke OneDrive en de OneDrive-URL van de gebruiker in te voeren. Zie [overzicht van beleidsregels voor preventie van gegevensverlies](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) voor algemene richtlijnen voor het maken van DLP-beleidsregels.

De DLP-beleidsregels worden automatisch gesynchroniseerd op basis van de toepassing van de toepassing op elke geografische locatie.

Beleidsregels voor preventie van gegevensbeveiliging en preventie van gegevensverlies voor alle gebruikers op een geo-locatie is geen optie beschikbaar in de GEBRUIKERSINTERFACE, in plaats daarvan dient u de betreffende accounts voor het beleid te selecteren of het beleid globaal toe te passen op alle accounts.

## <a name="microsoft-flow"></a>Microsoft Flow

Doorstromen die zijn gemaakt voor de satelliet locatie, wordt het eindpunt gebruikt dat zich in de standaard geografische locatie van de Tenant bevindt.  Microsoft flow is geen meervoudige geo-service. 

## <a name="microsoft-powerapps"></a>Microsoft PowerApps

Met PowerApps gemaakt voor de satelliet locatie wordt het eindpunt van de centrale locatie voor de Tenant gebruikt. Microsoft PowerApps is geen meervoudige geo-service. 

## <a name="onedrive-administrator-experience"></a>Beheer ervaring van OneDrive

Het [OneDrive-Beheercentrum](https://admin.onedrive.com) heeft een tabblad **geo-locaties** in het linker navigatiegebied, wat een geo-locaties plattegrond bevat, waar u uw geografische locaties kunt weergeven en beheren. Gebruik deze pagina om geografische locaties voor uw Tenant toe te voegen of te verwijderen.

## <a name="security-and-compliance-admin-center"></a>Beheercentrum voor beveiliging en compliance

Er is één centraal compliance-centrum voor een multigeo-Tenant: [Microsoft 365 Security & compliance Center](https://protection.office.com/?rfr=AdminCenter\#/homepage).

## <a name="sharepoint-storage-quota"></a>SharePoint-opslagquotum

Standaard delen alle geografische locaties van een multi-geografische omgeving het beschikbare opslagquotum voor de Tenant.  U kunt de opslagquota ook beheren door een specifiek quotum voor een bepaalde geografische locatie toe te wijzen. Voor meer informatie raadpleegt u [opslagquota voor SharePoint in meerdere geo-omgevingen](sharepoint-multi-geo-storage-quota.md).

## <a name="sharing"></a>Delen

Beheerders kunnen de beleidsregels voordelen voor elk van hun locaties instellen en beheren. Op de OneDrive-en SharePoint-sites op elke geografische locatie wordt alleen de bijbehorende geo-specifieke instellingen voordelen geaccepteerd. (U kunt bijvoorbeeld [extern delen](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85) voor uw centrale locatie toestaan, maar niet voor uw satelliet locatie of vice versa). Houd er rekening mee dat de instellingen voordelen geen ondersteuning bieden voor het configureren van beperkingen voordelen tussen geo-locaties.

## <a name="taxonomy"></a>Taxonomie

We bieden ondersteuning voor een uniforme [taxonomie](https://docs.microsoft.com/sharepoint/managed-metadata) voor de beheerde metagegevens van een onderneming op geografische locaties, waarbij het model wordt gehost op de centrale locatie voor uw bedrijf. U wordt aangeraden uw globale taxonomie vanaf de centrale locatie te beheren en alleen locatiespecifieke voorwaarden toe te voegen aan de taxonomie van de satelliet locatie. Globale taxonomie voorwaarden worden gesynchroniseerd met de satelliet locaties.

Zie [metagegevens van een meervoudige geo-Tenant beheren](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-managedmetadata) voor meer informatie en voor de instructies voor ontwikkelaars.

## <a name="user-profile-application"></a>Gebruikersprofieltoepassing

Er staat een [gebruikersprofieltoepassing](https://docs.microsoft.com/sharepoint/manage-user-profiles) op elke geografische locatie. De profielgegevens van elke gebruiker worden gehost op de geografische locatie en beschikbaar voor de beheerder voor die geografische locatie.

Als u aangepaste profieleigenschappen hebt, raden we u aan om hetzelfde profielschema te gebruiken voor geografi en de aangepaste profieleigenschappen in te vullen op alle geografische locaties of waar nodig. Raadpleeg voor meer informatie over het gebruik van gebruikersprofielgegevens via programmacode de [Update-API voor bulk gebruikersprofielen](https://docs.microsoft.com/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online).

Zie [werken met gebruikersprofielen in een Tenant van meerdere geo](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-userprofileexperience) voor aanvullende informatie en instructies voor ontwikkelaars.

## <a name="video-portal"></a>Video portal

In een Tenant met meerdere geo-films wordt de O365 video-portal alleen vanaf standaard geo bediend en worden alle gebruikers omgeleid naar de URL van de centrale Portal. Daarom wordt de Remote Media service (RMS) voor die regio gebruikt, op basis van uw centrale locatie.

Stream is momenteel beschikbaar in de volgende regio's:

- Noord-Amerika, gehost in de Verenigde Staten 
- Europa
- Azië en Stille Oceaan

Stream is nog niet beschikbaar in de volgende regio's die momenteel worden ondersteund voor Microsoft 365-Video's, dus voor deze lokale exemplaren, dan gebruiken we de RMS in het dichtstbijzijnde ondersteunde gebied.

- Australië
- Canada
- India
- Verenigd Koninkrijk

## <a name="yammer"></a>Yammer

Yammer is geen werkbelasting in meerdere geo. Yammer-threads die zijn opgeslagen in Yammer, worden op de centrale locatie van de Tenant geplaatst. Yammer maakt een wijziging in de opslagruimte voor bestanden waarmee u Yammer-bestanden in SharePoint kunt opslaan. Yammer-bestanden die zijn opgeslagen in SharePoint, worden toegevoegd aan de SharePoint-site die is gekoppeld aan de Yammer-groep. SharePoint-groeps sites zijn gebaseerd op PDL-logica zoals deze in [SharePoint-sites en-groepen](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups)worden beschreven.
