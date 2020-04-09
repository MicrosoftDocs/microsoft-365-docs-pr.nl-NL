---
title: Sites en bestanden van SharePoint Online beveiligen
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: ''
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
- SPO_Content
ms.custom:
- Ent_Architecture
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
description: 'Samenvatting: Configuratieaanbevelingen voor het beveiligen van bestanden in SharePoint Online en Office 365.'
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 542cf1c899b0eee21b458cd8e9dd5fb8363cf1e9
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809858"
---
# <a name="secure-sharepoint-online-sites-and-files"></a>Sites en bestanden van SharePoint Online beveiligen

Dit artikel bevat aanbevelingen voor het configureren van teamsites in SharePoint Online en voor bestandsbeveiliging waarbij beveiliging en gemak van samenwerking hand in hand gaan. In dit artikel worden vier verschillende configuraties gedefinieerd, te beginnen met een openbare site in uw organisatie met het meest liberale beleid voor het delen van bestanden. Elke extra configuratie vertegenwoordigt een zinvolle stap in de bescherming, maar de mogelijkheid om bronnen te openen en eraan samen te werken, is beperkt tot de desbetreffende groep gebruikers. Gebruik deze aanbevelingen als uitgangspunt en pas de configuraties aan om aan de behoeften van uw organisatie te kunnen voldoen.

De configuraties in dit artikel zijn in overeenstemming met de aanbevelingen van Microsoft voor de drie beveiligingslagen voor gegevens, identiteiten en apparaten:

- Basisbescherming

- Bescherming van gevoelige gegevens

- Bescherming van zeer vertrouwelijke gegevens

Zie de volgende bronnen voor meer informatie over deze lagen en functionaliteiten voor elke laag.

- [Identity and Device Protection for Office 365](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#identity-and-device-protection-for-office-365) (Bescherming van identiteiten en apparaten in Office 365)

- [File Protection Solutions in Office 365](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#file-protection-solutions-in-office-365) (Oplossingen voor bestandsbeveiliging in Office 365)

## <a name="capability-overview"></a>Overzicht van functionaliteiten

Aanbevelingen voor teamsites in SharePoint Online zijn gebaseerd op een groot aantal Microsoft 365-functionaliteiten. In de volgende afbeelding ziet u de aanbevolen configuraties voor vier teamsites in SharePoint Online.

![Aanbevolen configuratie voor SharePoint-sites](../../media/SharePoint-site-configurations.png)

Zoals afgebeeld:

- Basisbescherming bevat twee opties voor teamsites in SharePoint Online: een openbare site en een privésite. Openbare sites kunnen door iedereen in de organisatie worden gevonden en geopend. Privésites kunnen alleen door leden van de site worden gevonden en geopend. In beide siteconfiguraties is het delen buiten de groep toegestaan.

- Sites voor gevoelige en zeer vertrouwelijke bescherming zijn privésites waarvan de toegang is beperkt tot alleen de leden van specifieke groepen.

- [Retentielabels](../../compliance/labels.md) bieden een mogelijkheid om bestanden in de sites te classificeren. Elke teamsite in SharePoint Online is geconfigureerd voor het automatisch labelen van bestanden in documentbibliotheken met een standaardretentielabel voor die site. De labels in dit voorbeeld zijn Intern openbaar, Privé, Gevoelig en Zeer vertrouwelijk, in overeenstemming met de vier siteconfiguraties. Gebruikers kunnen de labels wijzigen, maar met deze configuratie krijgen alle bestanden een standaardlabel.

- Beleid voor [preventie van gegevensverlies](../../compliance/data-loss-prevention-policies.md) (DLP) wordt geconfigureerd voor de retentielabels Gevoelig en Zeer vertrouwelijk om gebruikers te waarschuwen als ze deze typen bestanden buiten de organisatie willen verzenden, of om dit te voorkomen.

- Indien nodig kunt u [gevoeligheidslabels](../../compliance/sensitivity-labels.md) gebruiken om zeer vertrouwelijke bestanden met versleuteling en machtigingen te beveiligen. Voor klanten van Azure Information Protection: u kunt uw Azure Information Protection-labels in het Microsoft 365-compliancecentrum gebruiken. Uw labels worden vervolgens gesynchroniseerd met Azure Portal indien u voor aanvullende of geavanceerde configuratie kiest. Azure Information Protection-labels en Office 365-gevoeligheidslabels zijn volledig met elkaar compatibel. Dit betekent dat als u bijvoorbeeld inhoud hebt die is gelabeld door Azure Information Protection, u deze inhoud niet opnieuw hoeft te classificeren of labelen. Niet alle klanten hebben dit beveiligingsniveau nodig.

## <a name="tenant-wide-settings-for-sharepoint-online-and-onedrive-for-business"></a>Tenantbrede instellingen voor SharePoint Online en OneDrive voor Bedrijven

SharePoint Online en OneDrive voor Bedrijven bevatten tenantbrede instellingen die van invloed zijn op alle sites en gebruikers. Sommige van deze instellingen kunnen ook worden aangepast op siteniveau zodat ze meer beperkend zijn (maar niet minder). In deze sectie worden instellingen voor de gehele tenant besproken die van invloed zijn op beveiliging en samenwerking.

### <a name="sharing"></a>Delen

Voor deze oplossing raden we u de volgende tenantbrede instellingen aan:

- Het standaardbeleid voor delen blijven gebruiken voor het delen van alle accounttypen, inclusief anoniem delen.

- Anonieme koppelingen instellen om ze te laten verlopen, indien gewenst.

- Het standaardkoppelingstype voor delen wijzigen naar Intern. Hiermee voorkomt u dat gegevens per ongeluk buiten uw organisatie terechtkomen.

Hoewel het tegenintuïtief lijkt om extern delen toe te staan, biedt deze benadering meer controle over het delen van bestanden ten opzichte van het verzenden van bestanden via e-mail. SharePoint Online en Outlook werken samen om veilige samenwerking aan bestanden mogelijk te maken.

- Standaard wordt in Outlook een koppeling naar een bestand gedeeld in plaats dat het bestand per e-mail wordt verzonden.

- Met SharePoint Online en OneDrive voor Bedrijven kunt u eenvoudig koppelingen naar bestanden delen met medewerkers die zich binnen of buiten uw organisatie bevinden.

Bovendien kunt u het extern delen van bestanden beheren. U kunt bijvoorbeeld:

- Een anonieme gastkoppeling uitschakelen.

- De toegang intrekken die gebruikers tot een site hebben.

- Kijken wie er toegang heeft tot een bepaalde site of een bepaald document.

- Instellen dat koppelingen voor anoniem delen moeten verlopen (tenant-instelling).

- Beperken wie kan delen buiten uw organisatie (tenant-instelling).

### <a name="use-external-sharing-together-with-data-loss-prevention-dlp"></a>Extern delen gebruiken in combinatie met preventie van gegevensverlies (DLP)

Als u extern delen niet toestaat, kunnen gebruikers die dat willen, alternatieve hulpmiddelen en methoden vinden. Microsoft raadt aan extern delen te combineren met DLP-beleid om gevoelige en zeer vertrouwelijke bestanden te beveiligen.

### <a name="device-access-settings"></a>Instellingen voor apparaattoegang

Met instellingen voor apparaattoegang voor SharePoint Online en OneDrive voor Bedrijven kunt u bepalen of toegang beperkt wordt tot alleen browsers (bestanden kunnen dan niet worden gedownload) of dat de hele toegang wordt geblokkeerd. Zie [Control access from unmanaged devices (Toegangsbeheer op niet-beheerde apparaten)](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices) voor meer informatie.

Zie [Beleidsaanbevelingen voor het beveiligen van SharePoint-sites en -bestanden](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies) als u instellingen voor apparaattoegang wilt gebruiken met aanbevolen beleid voor voorwaardelijke toegang in Azure Active Directory.

### <a name="onedrive-for-business"></a>OneDrive voor Bedrijven

Ga naar deze instellingen om te bepalen of u de standaardinstellingen voor OneDrive voor Bedrijven-sites wilt wijzigen. Op dit moment worden de instellingen voor delen en apparaattoegang gedupliceerd vanuit het SharePoint Online Beheercentrum. Deze zijn van toepassing op beide omgevingen.

## <a name="sharepoint-team-site-configuration"></a>Configuratie van een SharePoint-teamsite

In de volgende tabel vindt u een overzicht van de configuratie voor alle teams, zoals eerder beschreven in dit artikel. Gebruik deze configuraties als uitgangspunt en pas de sitetypen en -configuraties aan de behoeften van uw organisatie aan. Niet elke organisatie heeft elk type site nodig. Voor slechts een klein aantal organisaties is zeer vertrouwelijke bescherming vereist.

||||||
|:-----|:-----|:-----|:-----|:-----|
||**Basisbescherming 1**|**Basisbescherming 2**|**Bescherming van gevoelige gegevens**|**Zeer vertrouwelijk**|
|Beschrijving|Vrije detectie en samenwerking binnen de organisatie.|Privésite en groep met delen buiten de groep zijn toegestaan.|Privésite met delen is alleen toegestaan voor leden van de site. DLP waarschuwt gebruikers bij het verzenden van bestanden buiten de organisatie.|Privésite en het versleutelen van bestanden en machtigingen met gevoeligheidslabels. DLP voorkomt dat gebruikers bestanden buiten het bedrijf verzenden.|
|Privé- of openbare team site|Openbaar|Privé|Privé|Privé|
|Wie heeft er toegang?|Iedereen in de organisatie, waaronder B2B- en gastgebruikers.|Alleen leden van de site. Anderen kunnen toegang aanvragen.|Alleen leden van de site. Anderen kunnen toegang aanvragen.|Alleen leden. Anderen kunnen geen toegang aanvragen.|
|Besturingselementen voor delen op siteniveau|Delen met iedereen toegestaan. Standaardinstellingen.|Delen met iedereen toegestaan. Standaardinstellingen.|Leden kunnen toegang tot de site niet delen. <br/> Niet-leden kunnen toegang tot de site aanvragen, maar deze aanvragen moeten door een sitebeheerder worden behandeld.|Leden kunnen toegang tot de site niet delen. <br/> Niet-leden kunnen geen toegang tot de site of de inhoud aanvragen.|
|Besturingselementen voor toegang op siteniveau|Geen extra besturingselementen.|Geen extra besturingselementen.|Voorkomt dat gebruikers bestanden downloaden naar niet-compatibele apparaten of apparaten die geen deel uitmaken van een domein. Hiermee is alleen toegang met de browser toegestaan vanaf alle overige apparaten.|Blokkeert het downloaden van bestanden naar niet-compatibele apparaten of apparaten die geen deel uitmaken van een domein.|
|Retentielabels|Intern openbaar|Privé|Gevoelig|Zeer vertrouwelijk|
|DLP-beleid|||Waarschuwt gebruikers bij het verzenden buiten de organisatie van bestanden die het label Gevoelig dragen. <br/> Voor het blokkeren van extern delen van gevoelige gegevenstypen (bijvoorbeeld creditkaartnummers of andere persoonlijke gegevens), kunt u aanvullend DLP-beleid voor deze gegevenstypen configureren (waaronder aangepaste gegevenstypen die u configureert).|Voorkomt dat gebruikers bestanden met het label Zeer vertrouwelijk buiten de organisatie verzenden. Staat gebruikers toe dit te overschrijven door hiervoor een rechtvaardiging te geven, zoals met wie ze het bestand willen delen.|
|Gevoeligheidslabels||||Gebruik gevoeligheidslabels om bestanden automatisch te versleutelen en machtigingen voor de bestanden te verlenen. Deze bescherming wordt met de bestanden mee verzonden in het geval van een lek. <br/> Office 365 kan bestanden die zijn versleuteld met gevoeligheidslabels niet lezen. Daarnaast kan het DLP-beleid alleen worden gebruikt met de metagegevens (met inbegrip van labels), maar niet met de inhoud van deze bestanden (zoals creditcardnummers in bestanden).|

Zie [Sites in SharePoint Online implementeren voor drie beschermingslagen voor bestanden](../../compliance/deploy-sharepoint-online-sites-for-three-tiers-of-protection.md) voor de stappen voor het implementeren van vier verschillende typen teamsites in SharePoint Online in deze oplossing.

## <a name="office-365-retention-labels"></a>Office 365-retentielabels

Het gebruik van retentielabels wordt aangeraden voor omgevingen met gevoelige of zeer vertrouwelijke gegevens. Ga na het configureren en publiceren van retentielabels als volgt te werk:

- U kunt een standaardlabel toepassen op een documentbibliotheek in een teamsite in SharePoint Online, zodat alle documenten in die bibliotheek het standaardlabel krijgen.

- U kunt automatisch labels op inhoud toepassen als deze aan bepaalde voorwaarden voldoet.

- U kunt DLP-beleid toepassen dat op retentielabels is gebaseerd.

- Personen in uw organisatie kunnen een label handmatig toepassen op inhoud in de webversie van Outlook, Outlook 2010 en hoger, OneDrive voor Bedrijven, SharePoint Online en Office 365-groepen. Gebruikers weten vaak het beste met welk type inhoud ze bezig zijn, zodat ze deze kunnen classificeren en het juiste DLP-beleid erop kunnen toepassen.

![Aanbevolen configuratie voor SharePoint-sites](../../media/7fed0126-ab4a-4480-922c-681970642339.png)

Zoals u ziet, bevat deze oplossing de volgende retentielabels:

- Zeer vertrouwelijk

- Gevoelig

- Privé

- Intern openbaar

Deze labels worden toegewezen aan de aanbevolen sites in de illustraties en grafieken die eerder in dit artikel zijn behandeld. In deze oplossing wordt aanbevolen om DLP-beleid in te stellen om het lekken van bestanden met de labels Gevoelig of Zeer vertrouwelijk te voorkomen.

Zie [Bestanden van SharePoint Online beveiligen met retentielabels en DLP](../../compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp.md) voor de stappen om retentielabels en DLP-beleid in deze oplossing te configureren.

## <a name="sensitivity-labels"></a>Gevoeligheidslabels

Indien gerechtvaardigd voor uw beveiligingsscenario, kunt u gevoeligheidslabels gebruiken om bescherming toe te passen op de bestanden, ongeacht hun locatie. Gevoeligheidslabels in het Microsoft 365-compliancecentrum en Azure Information Protection-labels zijn dezelfde. Voor deze oplossing wordt u aangeraden een gevoeligheidslabel of een sublabel van de Zeer vertrouwelijke gevoeligheidslabel te gebruiken voor het versleutelen en verlenen van machtigingen aan bestanden die moeten worden beschermd met het hoogste beveiligingsniveau.

Als uw organisatie geen [gevoeligheidslabels voor Office-bestanden in SharePoint en OneDrive (openbare preview) heeft ingeschakeld](/microsoft-365/compliance/sensitivity-labels-sharepoint-onedrive-files): Houd er rekening mee dat de service de inhoud van de bestanden niet kan verwerken als het versleutelen met gevoeligheidslabels wordt toegepast op bestanden die zijn opgeslagen in Office 365. Cocreatie, eDiscovery, zoeken, Delve en andere samenwerkingsfuncties werken niet. Het DLP-beleid kan alleen worden gebruikt met de metagegevens (met inbegrip van retentielabels), maar niet met de inhoud van deze bestanden (zoals creditcardnummers in bestanden).

Zie [Overzicht van gevoeligheidslabels](../../compliance/sensitivity-labels.md) voor meer informatie.

### <a name="adding-permissions-for-external-users"></a>Machtigingen voor externe gebruikers toevoegen

Er zijn twee manieren waarop u externe gebruikers toegang kunt verlenen tot bestanden die zijn beveiligd met een gevoeligheidslabel. In beide gevallen moeten externe gebruikers een Microsoft Azure AD-account hebben. Als externe gebruikers geen lid zijn van een organisatie die gebruikmaakt van Microsoft Azure AD, kunnen ze een Microsoft Azure AD-account als individu verkrijgen via deze registratiepagina: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).

- Externe gebruikers toevoegen aan een Microsoft Azure AD-groep die wordt gebruikt om de beveiliging voor een label te configureren

  U moet het account eerst toevoegen als B2B-gebruiker in uw directory. [Groepslidmaatschappen opslaan in de cache van Azure Rights Management](https://docs.microsoft.com/information-protection/plan-design/prepare) kan enkele uren in beslag nemen. Met deze methode worden machtigingen verleend voor alle bestaande bestanden die zijn beveiligd met het label (zelfs bestanden die zijn beveiligd voordat een gebruiker werd toegevoegd aan de Microsoft Azure AD-groep).

- Externe gebruikers rechtstreeks toevoegen aan de labelbeveiliging

  U kunt alle gebruikers van een organisatie (bijvoorbeeld Fabrikam.com), een Microsoft Azure AD-groep (zoals een groep Financiën binnen een organisatie) of een afzonderlijke gebruiker toevoegen. U kunt bijvoorbeeld een extern team met toezichthouders toevoegen aan de beveiliging voor een label. Met deze methode worden machtigingen alleen verleend voor bestanden die zijn beveiligd met het label nadat de externe entiteit is toegevoegd aan de beveiliging.

### <a name="deploying-and-using-a-sensitivity-label"></a>Een gevoeligheidslabel implementeren en gebruiken

Zie [Bestanden van SharePoint Online beveiligen met een gevoeligheidslabel](../../compliance/protect-sharepoint-online-files-with-sensitivity-label.md) voor de stappen voor het configureren van een gevoeligheidslabel in deze oplossing.

## <a name="next-step"></a>Volgende stap

Bouw dit uit tot een haalbaarheidstest met [Beveiligde SharePoint Online-sites in een ontwikkel-/testomgeving](secure-sharepoint-online-sites-in-a-dev-test-environment.md).

## <a name="see-also"></a>Zie ook

[Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) (Beveiligingsrichtlijnen van Microsoft voor politieke campagnes, non-profitorganisaties en andere agile organisaties)

[Cloud adoption and hybrid solutions](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions) (Overstappen op de cloud en hybride oplossingen)
