---
title: Meer informatie over de on-premises scanner voor Microsoft 365 preventie van gegevensverlies (preview)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: De on-premises scanner voor Microsoft 365 preventie van gegevensverlies breidt het toezicht op bestandsactiviteiten en beschermende maatregelen voor die bestanden uit tot on-premises gedeelde bestanden en SharePoint-mappen en documentbibliotheken. Bestanden worden gescand en beveiligd met AIP-scanner (Azure Information Protection)
ms.openlocfilehash: f0a34a13630e42c5dd29734ad708b3c11bb1d587
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162910"
---
# <a name="learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a>Meer informatie over de on-premises scanner voor Microsoft 365 preventie van gegevensverlies (preview)

De on-premises scanner voor Microsoft preventie van gegevensverlies maakt deel uit van het Microsoft 365-programmapakket voor preventie van gegevensverlies (DLP) met functies die u kunt gebruiken voor het detecteren en beveiligen van gevoelige items in Microsoft 365-services. Zie voor meer informatie over alle DLP-aanbiedingen van Microsoft [Meer informatie over preventie van gegevensverlies](dlp-learn-about-dlp.md).

De **DLP-on-premises scanner** verkent on-premises data-at-rest in gedeelde bestanden en in SharePoint-documentbibliotheken en -mappen voor gevoelige items die, als deze worden gelekt, een risico vormen voor uw organisatie of een risico van schending van het compliancebeleid vormen. Dit geeft u de zichtbaarheid en controle die u nodig hebt om ervoor te zorgen dat gevoelige items goed worden gebruikt en beveiligd, en om risicogedrag te voorkomen dat dergelijke gevoelige items in gevaar kan brengen. De on-premises DLP-scanner detecteert gevoelige informatie met behulp van [ingebouwde](sensitive-information-type-entity-definitions.md)of [aangepaste gevoelige informatie](create-a-custom-sensitive-information-type.md) -typen, [gevoeligheidslabels](sensitivity-labels.md) of bestandseigenschappen. De informatie over wat gebruikers met gevoelige items doen, wordt zichtbaar in [Activiteitenverkenner](data-classification-activity-explorer.md) en u kunt acties op deze items afdwingen via [DLP-beleid](create-test-tune-dlp-policy.md).

## <a name="the-dlp-on-premises-scanner-relies-on-azure-information-protection-scanner"></a>De on-premises DLP-scanner is afhankelijk van Azure Information Protection-scanner

De on-premises DLP-scanner is afhankelijk van een volledige implementatie van de Azure Information Protection (AIP)-scanner voor het controleren, labelen en beveiligen van gevoelige items. Als u niet bekend bent met de AIP-scanner, wordt het ten zeerste aangeraden u vertrouwd te maken met de scanner. Zie de volgende artikelen:

- [Wat is Azure Information Protection?](/azure/information-protection/what-is-information-protection)
- [Wat is de geïntegreerde labelscanner van Azure Information Protection?](/azure/information-protection/deploy-aip-scanner)
- [Vereisten voor het installeren en implementeren van de geïntegreerde labelscanner van Azure Information Protection](/azure/information-protection/deploy-aip-scanner-prereqs)
- [Handleiding: Installeren van de geïntegreerde labelscanner van Azure Information Protection (AIP)](/azure/information-protection/tutorial-install-scanner)
- [Configureren en installeren van de geïntegreerde labelscanner van Azure Information Protection](/azure/information-protection/deploy-aip-scanner-configure-install)
- [Geïntegreerde labelclient van Azure Information Protection - Versiegeschiedenis en ondersteuningsbeleid](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)

## <a name="dlp-on-premises-scanner-actions"></a>Acties van on-premises DLP-scanner

Met DLP-on-premises scanner worden bestanden gedetecteerd met een van de volgende vier methoden:

- typen gevoelige informatie
- vertrouwelijkheidslabels
- bestandsextensie
- aangepaste documenteigenschappen alleen voor Office-bestanden 

Wanneer een gedetecteerd bestand een potentieel risico vormt bij lekken of een schending van het compliancebeleid, kan de on-premises DLP-scanner een van deze vier acties uitvoeren.

|Actie |Omschrijving  |
|---------|---------|
|**Blokkeren dat deze personen toegang hebben tot bestanden die zijn opgeslagen in on-premises scanner - Iedereen** | Als dit wordt afgedwongen, blokkeert deze actie de toegang tot alle accounts, met uitzondering van de eigenaar van de inhoud, het laatste account dat het item heeft gewijzigd en de beheerder. Dit wordt gedaan door alle accounts te verwijderen van NTFS-/SharePoint-machtigingen op bestandsniveau, behalve de eigenaar van het bestand, de eigenaar van de opslagplaats (ingesteld in de [Eigenaar opslagplaats instellen](/azure/information-protection/deploy-aip-scanner-configure-install#use-a-data-loss-prevention-dlp-policy-public-preview) instelling in de inhoudsscantaak),laatste modificator (kan alleen worden geïdentificeerd in SharePoint) en beheerder. Aan het scanneraccount worden ook FC-rechten toegekend voor het bestand.|
|**Blokkeren dat deze personen toegang hebben tot bestanden die zijn opgeslagen in on-premises scanner - toegang blokkeren voor de hele organisatie (openbaar)**    |Als deze actie wordt afgedwongen, worden de **_Everyone_*_, _*_NT AUTHORITY\authenticated users_*_, en _*_Domain Users_** SID's uit de ACL (controlelijst voor bestandstoegang) verwijderd. Alleen gebruikers en groepen die expliciet rechten hebben op het bestand of de bovenliggende map, hebben toegang tot het bestand.|
|**Machtigingen voor het bestand instellen**|Als dit wordt afgedwongen, wordt het bestand gedwongen de machtigingen van de bovenliggende map over te nemen. Standaard wordt deze actie alleen afgedwongen als de machtigingen voor de bovenliggende map meer beperkingen hebben dan de machtigingen die al voor het bestand staan. Als de ACL voor het bestand bijvoorbeeld is ingesteld op alleen **_specifieke gebruikers_*_ toestaan en de bovenliggende map zo is geconfigureerd om _*_Domain Users_*_ groep toe te staan, worden de machtigingen voor bovenliggende mappen niet overgenomen door het bestand. U kunt dit gedrag overschrijven door de optie _* Overnemen zelfs als bovenliggende machtigingen minder beperkend zijn,** te selecteren.|
|**Het bestand verwijderen van een onjuiste locatie**|Als dit wordt afgedwongen, vervangt deze actie het oorspronkelijke bestand door een stubbestand met de extensie .txt en wordt een kopie van het oorspronkelijke bestand in een quarantainemap geplaatst. 

## <a name="whats-different-in-the-on-premises-scanner"></a>Wat is er anders in de on-premises scanner?

Er zijn enkele extra concepten waar u rekening mee moet houden voordat u de on-premises scanner gaat in gebruik nemen.

### <a name="aip-repositories-and-content-scan-jobs"></a>AIP-opslagplaatsen en inhoudsscantaken

U moet een AIP-inhoudsscantaak maken en de opslagplaatsen identificeren die als host dienen voor de bestanden die door de DLP-engine moeten worden geëvalueerd. Zorg ervoor dat u DLP-regels inschakelt in de gemaakte AIP-inhoudsscantaak.

### <a name="policy-tips"></a>Beleidstips

[Beleidstips](use-notifications-and-policy-tips.md) zijn niet beschikbaar in on-premises scanner.


### <a name="viewing-dlp-on-premises-scanner-events"></a>Gebeurtenissen van DLP on-premises scanner weergeven

U bekijkt DLP-gegevens van de on-premises scanner in de [activiteitenverkenner](data-classification-activity-explorer.md) van het M365-compliancecentrum. 

## <a name="next-steps"></a>Volgende stappen

Nu u meer weet over de on-premises DLP-scanner, gaat u als volgt te werk:

1. [Aan de slag met DLP-on-premises scanner](dlp-on-premises-scanner-get-started.md)
2. [Gebruik van de DLP on-premises scanner](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a>Zie ook

- [Aan de slag met de on-premises scanner voor Microsoft 365 preventie van gegevensverlies](dlp-on-premises-scanner-get-started.md)
- [Gebruik de on-premises scanner voor Microsoft preventie van gegevensverlies](dlp-on-premises-scanner-use.md)
- [Meer informatie over preventie van gegevensverlies](dlp-learn-about-dlp.md)
- [Een DLP-beleid maken, testen en afstemmen](create-test-tune-dlp-policy.md)
- [Aan de slag met de activiteitenverkenner](data-classification-activity-explorer.md)