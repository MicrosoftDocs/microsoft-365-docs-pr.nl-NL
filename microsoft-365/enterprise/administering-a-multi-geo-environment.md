---
title: Een multi-geo-omgeving beheren
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
description: Beheerders kunnen meer informatie krijgen over het beheren SharePoint en OneDrive services in een multi-geoomgeving.
ms.openlocfilehash: 9ef22a34881ef5c9c2ed72835bc88c1dbfe835b5
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363941"
---
# <a name="administering-a-multi-geo-environment"></a>Een multi-geo-omgeving beheren

Hier ziet u hoe Microsoft 365 services werken in een multi-geoomgeving.

## <a name="administrator-experience"></a>Beheerderservaring

Het [SharePoint beheercentrum](https://admin.microsoft.com/sharepoint) heeft een tabblad **Geolocaties** in de linkernavigatie met een kaart met geografische locaties waar u uw geografische locaties kunt bekijken en beheren. Gebruik deze pagina om geografische locaties voor uw tenant toe te voegen of te verwijderen.

## <a name="audit-log-search"></a>Zoeken in het Auditlogboek

Een geïntegreerd [auditlogboek](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c) voor al uw satellietlocaties is beschikbaar op de zoekpagina Microsoft 365 auditlogboek. U kunt alle auditlogboekgegevens van verschillende geografische locaties zien, bijvoorbeeld dat de activiteiten van NAM & EUR-gebruikers in één organisatieweergave worden weergeven en u vervolgens bestaande filters kunt toepassen om de activiteiten van specifieke gebruikers te bekijken.

## <a name="bcs-secure-store-apps"></a>BCS, Secure Store, Apps

BCS, Secure Store en Apps hebben allemaal afzonderlijke exemplaren op elke satellietlocatie. Daarom moet de beheerder van SharePoint Online deze services afzonderlijk van elke satellietlocatie beheren en configureren.

## <a name="compliance-admin-center"></a>Compliance-beheercentrum

Er is één centraal compliancecentrum voor een multi-geo tenant: [Microsoft 365 Compliance-beheercentrum.](https://compliance.microsoft.com/)

## <a name="ediscovery"></a>eDiscovery

Standaard kan een eDiscovery-manager of beheerder van een multi-geo tenant eDiscovery alleen uitvoeren op de centrale locatie van die tenant. De globale Office 365-beheerder moet eDiscovery Manager-machtigingen toewijzen om anderen toe te staan eDiscovery uit te voeren en een 'Regio'-parameter toe te wijzen in hun toepasselijke compliancebeveiligingsfilter om de regio voor het uitvoeren van eDiscovery op te geven als satellietlocatie, anders wordt er geen eDiscovery uitgevoerd voor de satellietlocatie. Zie Configure [Office 365 Multi-Geo eDiscovery (Multi-Geo eDiscovery) als](multi-geo-ediscovery-configuration.md)u het compliancebeveiligingsfilter voor een regio wilt configureren.

## <a name="exchange-mailboxes"></a>Exchange postvakken

De postvakken Exchange gebruikers worden automatisch verplaatst als hun PDL wordt gewijzigd. Wanneer een nieuw postvak wordt gemaakt, wordt dit ingericht op de PDL van de gebruiker of op de centrale locatie als er geen waarde is ingesteld voor de PDL van de gebruiker.

## <a name="information-protection-ip-data-loss-prevention-dlp-policy"></a>Beleid voor gegevensbescherming (IP) preventie van gegevensverlies (DLP)

U kunt uw IP-DLP-beleid instellen voor OneDrive voor Bedrijven, SharePoint en Exchange in het Beveiligings- en compliancecentrum, het beleid zo nodig voor de hele tenant of voor de betreffende gebruikers. Bijvoorbeeld: Als u een beleid wilt selecteren voor een gebruiker op een satellietlocatie, selecteert u om het beleid toe te passen op een specifieke OneDrive en voert u de url van de gebruiker OneDrive in. Zie [Overzicht van beleid voor preventie van gegevensverlies](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) voor algemene richtlijnen bij het maken van DLP-beleid.

Het DLP-beleid wordt automatisch gesynchroniseerd op basis van de toepassing ervan op elke geografische locatie.

Het implementeren van het preventiebeleid voor gegevensbescherming en gegevensverlies voor alle gebruikers op een geografische locatie is geen optie die beschikbaar is in de gebruikersinterface. In plaats daarvan moet u de toepasselijke accounts voor het beleid selecteren of het beleid globaal toepassen op alle accounts.

## <a name="microsoft-powerapps"></a>Microsoft PowerApps

PowerApps die zijn gemaakt voor de satellietlocatie, gebruiken het eindpunt op de centrale locatie voor de tenant. Microsoft PowerApps is geen Multi-Geo-service. 

## <a name="power-automate"></a>Power Automate

Stromen die zijn gemaakt voor de satellietlocatie, gebruiken het eindpunt op de standaardlocatie voor de tenant.  Power Automate is geen Multi-Geo-service. 

## <a name="sharepoint-storage-quota"></a>SharePoint opslagquotum

Standaard delen alle geografische locaties van een multi-geo-omgeving het beschikbare opslagquotum voor tenants.  U kunt het opslagquotum ook beheren door een specifiek quotum toe tewijsen voor een bepaalde geografische locatie. Zie voor meer informatie SharePoint [opslagquota's in multi-geo-omgevingen.](sharepoint-multi-geo-storage-quota.md)

## <a name="sharing"></a>Delen

Beheerders kunnen beleid voor delen instellen en beheren voor elk van hun locaties. De OneDrive en SharePoint sites op elke geografische locatie worden alleen aan de bijbehorende geospecifieke instellingen voor delen aangepast. (U kunt bijvoorbeeld extern delen [toestaan](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85) voor uw centrale locatie, maar niet voor uw satellietlocatie of omgekeerd.) De instellingen voor delen staan het configureren van beperkingen voor delen tussen geografische locaties niet toe.

## <a name="stream"></a>Stream

Video's die zijn geüpload naar Stream in een 1:1-chat, worden opgeslagen in de OneDrive van de persoon die uploadt. Opnamen van vergaderingen worden opgeslagen in de OneDrive van elke deelnemer die de vergadering registreert.

## <a name="taxonomy"></a>Taxonomie

We ondersteunen een geïntegreerde [taxonomie](/sharepoint/managed-metadata) voor door ondernemingen beheerde metagegevens op verschillende geografische locaties, met het hoofd dat wordt gehost op de centrale locatie voor uw bedrijf. U wordt aangeraden uw globale taxonomie vanaf de centrale locatie te beheren en alleen locatiespecifieke termen toe te voegen aan de Taxonomie van de satellietlocatie. Globale taxonomievoorwaarden worden gesynchroniseerd met de satellietlocaties.

Zie [Metagegevens beheren in een multi-geo tenant](/sharepoint/dev/solution-guidance/multigeo-managedmetadata) voor meer informatie en voor richtlijnen voor ontwikkelaars.

## <a name="user-profile-application"></a>Gebruikersprofieltoepassing

Er is een [gebruikersprofieltoepassing](/sharepoint/manage-user-profiles) op elke geografische locatie. De profielgegevens van elke gebruiker worden gehost op hun geografische locatie en zijn beschikbaar voor de beheerder voor die geografische locatie.

Als u aangepaste profieleigenschappen hebt, raden we u aan hetzelfde profielschema in verschillende geografische gebieden te gebruiken en uw aangepaste profieleigenschappen in te vullen op alle geografische locaties of waar nodig. Raadpleeg de Bulk User Profile Update API voor informatie over het programmatisch in vullen van [gebruikersprofielgegevens.](/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online)

Zie [Werken met gebruikersprofielen in een multi-geo tenant](/sharepoint/dev/solution-guidance/multigeo-userprofileexperience) voor meer informatie en voor richtlijnen voor ontwikkelaars.

## <a name="yammer"></a>Yammer

Yammer is geen multi-geobelasting. Yammer threads die zijn opgeslagen in Yammer worden op de centrale locatie van de tenant geplaatst. Yammer wordt een wijziging in de bestandsopslag uitgerold waarmee Yammer bestanden binnen de SharePoint. Yammer bestanden die zijn opgeslagen in SharePoint, wordt de SharePoint site geplaatst die is gekoppeld aan de Yammer groep. SharePoint groepssites zijn gebaseerd op PDL-logica, zoals beschreven in [SharePoint Sites en Groepen.](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups)
