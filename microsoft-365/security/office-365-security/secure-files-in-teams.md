---
title: Bestanden beveiligen in Microsoft Teams
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom:
- Ent_Architecture
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
description: 'Overzicht: configuratieaanbevelingen voor het beveiligen van bestanden in Microsoft Teams.'
ms.openlocfilehash: 82c55affc8384c04e0595f82d21c7e3532b5cb0e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805912"
---
# <a name="secure-files-in-microsoft-teams"></a>Bestanden beveiligen in Microsoft Teams

Dit artikel bevat aanbevelingen voor het configureren van teams in Microsoft Teams en de onderliggende SharePoint-sites voor bestandsbeveiliging waardoor beveiliging en gemak van samenwerking hand in hand gaan. In dit artikel worden vier verschillende configuraties gedefinieerd, te beginnen met een openbare site in uw organisatie met het meest liberale beleid voor het delen van bestanden. Elke extra configuratie vertegenwoordigt een zinvolle stap in de bescherming, maar de mogelijkheid om bestanden die in Teams zijn opgeslagen, te openen en eraan samen te werken, is beperkt tot de desbetreffende groep teamleden. Gebruik deze aanbevelingen als uitgangspunt en pas de configuraties aan om aan de behoeften van uw organisatie te kunnen voldoen.

De configuraties in dit artikel zijn in overeenstemming met de aanbevelingen van Microsoft voor de drie beveiligingslagen voor gegevens, identiteiten en apparaten:

- Basisbescherming

- Bescherming van gevoelige gegevens

- Bescherming van zeer vertrouwelijke gegevens

Zie de volgende bronnen voor meer informatie over deze lagen en functionaliteiten voor elke laag.

- [Identity and Device Protection for Office 365](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#identity-and-device-protection-for-office-365) (Bescherming van identiteiten en apparaten in Office 365)

- [File Protection Solutions in Office 365](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#file-protection-solutions-in-office-365) (Oplossingen voor bestandsbeveiliging in Office 365)

## <a name="capability-overview"></a>Overzicht van functionaliteiten

Aanbevelingen voor beveiligde teams zijn afhankelijk van een groot aantal Microsoft 365-functionaliteiten. In de volgende afbeelding ziet u de aanbevolen configuraties.

![Aanbevolen configuratie voor teams](../../media/secure-team-configurations.png)

Zoals afgebeeld:

- Basisbescherming omvat een openbaar team en een privéteam. Openbare teams kunnen door iedereen in de organisatie worden gedetecteerd en geopend. Privéteams kunnen alleen door leden van het team worden gedetecteerd en geopend. Met beide configuraties kunt u de onderliggende SharePoint-sites delen waarop bestanden van buiten het team zijn opgeslagen.

- Teams voor bescherming van gevoelige en zeer vertrouwelijke gegevens zijn privéteams waarvoor het delen en het aanvragen van toegang tot de onderliggende site beperkt zijn.

- [Retentielabels](../../compliance/labels.md) bieden een mogelijkheid om bestanden in de onderliggende SharePoint-sites te classificeren. Elke onderliggende SharePoint-site is geconfigureerd voor het automatisch labelen van bestanden in documentbibliotheken met een standaardretentielabel. De labels in dit voorbeeld zijn Intern openbaar, Privé, Gevoelig en Zeer vertrouwelijk, in overeenstemming met de vier teamconfiguraties. Gebruikers kunnen de labels voor afzonderlijke bestanden wijzigen, maar met deze configuratie krijgen alle bestanden een standaardlabel.

- Beleid voor [preventie van gegevensverlies](../../compliance/data-loss-prevention-policies.md) (DLP) wordt geconfigureerd voor de retentielabels Gevoelig en Zeer vertrouwelijk om gebruikers te waarschuwen als ze deze typen bestanden buiten de organisatie willen verzenden, of om dit te voorkomen.

- Indien nodig kunt u [gevoeligheidslabels](../../compliance/sensitivity-labels.md) gebruiken om zeer vertrouwelijke bestanden met versleuteling en machtigingen te beveiligen. Voor klanten van Azure Information Protection: u kunt uw Azure Information Protection-labels in het Microsoft 365-compliancecentrum gebruiken. Uw labels worden vervolgens gesynchroniseerd met Azure Portal indien u voor aanvullende of geavanceerde configuratie kiest. Azure Information Protection-labels en Office 365-gevoeligheidslabels zijn volledig met elkaar compatibel. Dit betekent dat als u bijvoorbeeld inhoud hebt die is gelabeld door Azure Information Protection, u deze inhoud niet opnieuw hoeft te classificeren of labelen. Niet alle klanten hebben dit beveiligingsniveau nodig.

## <a name="organization-wide-settings-for-sharepoint-and-onedrive"></a>Instellingen voor de hele organisatie voor SharePoint en OneDrive

SharePoint en OneDrive bevatten instellingen die van invloed zijn op alle sites en gebruikers in de organisatie. Sommige van deze instellingen kunnen ook worden aangepast op siteniveau zodat ze meer beperkend zijn (maar niet minder). In deze sectie worden instellingen voor de gehele tenant besproken die van invloed zijn op beveiliging en samenwerking.

### <a name="sharing"></a>Delen

Voor deze oplossing raden we u de volgende instellingen voor de hele organisatie aan:

- Het standaardbeleid voor delen blijven gebruiken voor het delen van alle accounttypen, inclusief anoniem delen.

- Anonieme koppelingen instellen om ze te laten verlopen, indien gewenst.

- Het standaardkoppelingstype voor delen wijzigen naar Intern. Hiermee voorkomt u dat gegevens per ongeluk buiten uw organisatie terechtkomen.

Hoewel het tegenintuïtief lijkt om extern delen toe te staan, biedt deze benadering meer controle over het delen van bestanden ten opzichte van het verzenden van bestanden via e-mail. SharePoint en Outlook werken samen om veilige samenwerking aan bestanden mogelijk te maken.

- Standaard wordt in Outlook een koppeling naar een bestand gedeeld in plaats dat het bestand per e-mail wordt verzonden.

- Met SharePoint en OneDrive kunt u eenvoudig koppelingen naar bestanden delen met medewerkers die zich binnen of buiten uw organisatie bevinden.

Bovendien kunt u het extern delen van bestanden beheren. U kunt bijvoorbeeld:

- Een anonieme gastkoppeling uitschakelen.

- De toegang intrekken die gebruikers tot een site hebben.

- Kijken wie er toegang heeft tot een bepaalde site of een bepaald document.

- Instellen dat koppelingen voor anoniem delen moeten verlopen (tenant-instelling).

- Beperken wie kan delen buiten uw organisatie (tenant-instelling).

### <a name="use-external-sharing-together-with-data-loss-prevention-dlp"></a>Extern delen gebruiken in combinatie met preventie van gegevensverlies (DLP)

Als u extern delen niet toestaat, kunnen gebruikers die dat willen, alternatieve hulpmiddelen en methoden vinden. Microsoft raadt aan extern delen te combineren met DLP-beleid om gevoelige en zeer vertrouwelijke bestanden te beveiligen.

### <a name="device-access-settings"></a>Instellingen voor apparaattoegang

Met instellingen voor apparaattoegang voor SharePoint en OneDrive kunt u bepalen of toegang beperkt wordt tot alleen browsers (bestanden kunnen dan niet worden gedownload) of dat de hele toegang wordt geblokkeerd. Zie [Control access from unmanaged devices (Toegangsbeheer op niet-beheerde apparaten)](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices) voor meer informatie.

Zie [Beleidsaanbevelingen voor het beveiligen van SharePoint-sites en -bestanden](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies) als u instellingen voor apparaattoegang wilt gebruiken met aanbevolen beleid voor voorwaardelijke toegang in Azure Active Directory.

Ga naar deze instellingen om te bepalen of u de standaardinstellingen voor OneDrive-sites wilt wijzigen. Op dit moment worden de instellingen voor delen en apparaattoegang gedupliceerd vanuit het SharePoint-beheercentrum. Ze zijn van toepassing op beide omgevingen.

## <a name="team-and-sharepoint-site-configuration"></a>Configuratie van Team- en SharePoint-sites

In de volgende tabel vindt u een overzicht van de configuratie voor alle teams en hun onderliggende SharePoint-site, zoals eerder is beschreven in dit artikel. Gebruik deze configuraties als uitgangspunt en pas de sitetypen en -configuraties aan de behoeften van uw organisatie aan. Niet elke organisatie heeft elk type team nodig. Voor slechts een klein aantal organisaties zijn teams met zeer vertrouwelijke bescherming vereist.

||||||
|:-----|:-----|:-----|:-----|:-----|
||**Basisbescherming 1**|**Basisbescherming 2**|**Bescherming van gevoelige gegevens**|**Zeer vertrouwelijk**|
|Beschrijving|Openbaar team met vrije detectie en samenwerking binnen de organisatie.|Privéteam waarbij delen van de onderliggende SharePoint-site is toegestaan buiten de groep.|Privéteam, maar delen van de onderliggende SharePoint-site is alleen toegestaan voor leden van de site. DLP waarschuwt gebruikers bij het verzenden van bestanden buiten de organisatie.|Privéteam met gevoeligheidslabels voor bestandsversleuteling en machtigingen die met het bestand worden verzonden. DLP voorkomt dat gebruikers bestanden buiten het bedrijf verzenden.|
|Privé- of openbare team site|Openbaar|Privé|Privé|Privé|
|Wie heeft er toegang?|Iedereen in de organisatie, waaronder B2B-gebruikers.|Alleen leden van de site. Anderen kunnen toegang aanvragen.|Alleen leden van het team. Anderen kunnen toegang tot de onderliggende site aanvragen, hetgeen wordt goedgekeurd door een teameigenaar.|Alleen leden. Anderen kunnen geen toegang aanvragen tot de onderliggende site.|
|Besturingselementen voor delen op siteniveau|Delen met iedereen toegestaan. Standaardinstellingen.|Delen met iedereen toegestaan. Standaardinstellingen.|Leden kunnen toegang tot de site niet delen. <br/> Niet-leden kunnen toegang tot de site aanvragen, maar deze aanvragen moeten door een groepseigenaar van het team worden behandeld.|Leden kunnen toegang tot de site niet delen. <br/> Niet-leden kunnen geen toegang tot de site of de inhoud ervan aanvragen.|
|Besturingselementen voor toegang op siteniveau|Geen extra besturingselementen.|Geen extra besturingselementen.|Voorkomt dat gebruikers bestanden downloaden naar niet-compatibele apparaten of apparaten die geen deel uitmaken van een domein. Hiermee is alleen toegang met de browser toegestaan vanaf alle overige apparaten.|Blokkeert het downloaden van bestanden naar niet-compatibele apparaten of apparaten die geen deel uitmaken van een domein.|
|Retentielabels|Intern openbaar|Privé|Gevoelig|Zeer vertrouwelijk|
|DLP-beleid|||Waarschuwt gebruikers bij het verzenden buiten de organisatie van bestanden die het label Gevoelig dragen. <br/> Voor het blokkeren van extern delen van gevoelige gegevenstypen (bijvoorbeeld creditkaartnummers of andere persoonlijke gegevens), kunt u aanvullend DLP-beleid voor deze gegevenstypen configureren (waaronder aangepaste gegevenstypen die u configureert).|Voorkomt dat gebruikers bestanden met het label Zeer vertrouwelijk buiten de organisatie verzenden. Staat gebruikers toe dit te overschrijven door hiervoor een rechtvaardiging te geven, zoals met wie ze het bestand willen delen.|
|Gevoeligheidslabels||||Gebruik gevoeligheidslabels om bestanden te versleutelen en er machtigingen voor te verlenen. Deze bescherming wordt met de bestanden mee verzonden voor het geval lekkage van de onderliggende SharePoint-site optreedt.|

Zie [Teams implementeren voor drie beschermingslagen voor bestanden](deploy-teams-three-tiers.md) voor de stappen voor het implementeren van vier verschillende typen teams in deze oplossing.

## <a name="office-365-retention-labels"></a>Office 365-retentielabels

Het gebruik van retentielabels wordt aangeraden voor omgevingen met gevoelige gegevens. Ga na het configureren en publiceren van retentielabels als volgt te werk:

- U kunt een standaardlabel toepassen op een documentbibliotheek in de onderliggende SharePoint-site voor een team, zodat alle documenten in de sectie **Bestanden** van het team het standaardlabel krijgen.

- U kunt automatisch labels op inhoud toepassen als deze aan bepaalde voorwaarden voldoet.

- U kunt DLP-beleid toepassen dat op retentielabels is gebaseerd.

- Personen in uw organisatie kunnen een label handmatig toepassen op inhoud in de webversie van Outlook, Outlook 2010 en hoger, OneDrive, SharePoint en Office 365-groepen. Gebruikers weten vaak het beste met welk type inhoud ze bezig zijn, zodat ze deze kunnen classificeren en het juiste DLP-beleid erop kunnen toepassen.

Zoals u ziet, bevat deze oplossing de volgende retentielabels:

- Zeer vertrouwelijk

- Gevoelig

- Privé

- Intern openbaar

Deze labels worden toegewezen aan de aanbevolen sites in de illustraties en grafieken die eerder in dit artikel zijn behandeld. In deze oplossing wordt aanbevolen om DLP-beleid in te stellen om lekken van bestanden met de labels Gevoelig of Zeer vertrouwelijk te voorkomen.

Zie [Bestanden in teams beveiligen met retentielabels en DLP](deploy-teams-retention-DLP.md) voor de stappen om retentielabels en DLP-beleid in deze oplossing te configureren.

## <a name="sensitivity-labels"></a>Gevoeligheidslabels

Indien gerechtvaardigd voor uw beveiligingsscenario, kunt u gevoeligheidslabels gebruiken om bescherming toe te passen op de bestanden, ongeacht hun locatie. Gevoeligheidslabels in het Microsoft 365-compliancecentrum en Azure Information Protection-labels zijn dezelfde. Voor deze oplossing wordt u aangeraden een gevoeligheidslabel of -sublabel te gebruiken voor het versleutelen en toewijzen van machtigingen aan bestanden die moeten worden beschermd met het hoogste beveiligingsniveau.

Zie [Overzicht van gevoeligheidslabels](../../compliance/sensitivity-labels.md) voor meer informatie.

Zie [Bestanden in teams beveiligen met gevoeligheidslabels](deploy-teams-sensitivity-labels.md) voor de stappen voor het configureren van gevoeligheidlabels in deze oplossing.

## <a name="see-also"></a>Zie ook

[Cloud adoption and hybrid solutions](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions) (Overstappen op de cloud en hybride oplossingen)
