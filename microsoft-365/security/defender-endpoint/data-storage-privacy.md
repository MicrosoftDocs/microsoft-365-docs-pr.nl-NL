---
title: Microsoft Defender voor opslag en privacy van eindpuntgegevens
description: Meer informatie over hoe Microsoft Defender voor Eindpunt omgaat met privacy en gegevens die worden verzameld.
keywords: Microsoft Defender for Endpoint, Microsoft Defender ATP, data storage and privacy, storage, privacy, licensing, geocation, data retention, data
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 228a8813bcfff052c7f861dcd2962a94cb58c0fb
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165965"
---
# <a name="microsoft-defender-for-endpoint-data-storage-and-privacy"></a>Microsoft Defender voor opslag en privacy van eindpuntgegevens

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

In deze sectie worden enkele van de meest gestelde vragen over privacy en gegevensafhandeling voor Defender voor Eindpunt bestrijkt.
> [!NOTE]
> In dit document worden de gegevensopslag- en privacygegevens met betrekking tot Defender voor Eindpunt uitgelegd. Zie Microsoft [Privacyverklaring](https://go.microsoft.com/fwlink/?linkid=827576)voor meer informatie over Defender voor Eindpunt en andere producten en services, zoals Microsoft Defender Antivirus en Windows 10. Zie ook [veelgestelde vragen over privacy van Windows 10](https://go.microsoft.com/fwlink/?linkid=827577) voor meer informatie.


## <a name="what-data-does-microsoft-defender-for-endpoint-collect"></a>Welke gegevens worden door Microsoft Defender voor Eindpunt verzameld?

In Microsoft Defender voor Eindpunt worden gegevens van uw geconfigureerde apparaten verzameld en opgeslagen in een klantspecifieke en gescheiden tenant die specifiek is voor de service voor beheer- en tracerings- en rapportagedoeleinden. 

Verzamelde gegevens omvatten bestandsgegevens (zoals bestandsnamen, groottes en hashes), procesgegevens (lopende processen, hashes), registergegevens, netwerkverbindingsgegevens (host-IPs en poorten) en apparaatgegevens (zoals apparaataanduidingen, namen en de versie van het besturingssysteem).

Microsoft slaat deze gegevens veilig op in Microsoft Azure en onderhoudt deze in overeenstemming met microsoft-privacypraktijken en [microsoft-vertrouwenscentrumbeleid.](https://go.microsoft.com/fwlink/?linkid=827578)

Met deze gegevens kan Defender voor Eindpunt het volgende doen:
- Indicatoren voor aanvallen (IOA's) in uw organisatie proactief identificeren
- Waarschuwingen genereren als er een mogelijke aanval is gedetecteerd
- Geef uw beveiligingsbewerkingen inzicht in apparaten, bestanden en URL's die betrekking hebben op bedreigingssignalen van uw netwerk, zodat u de aanwezigheid van beveiligingsrisico's in het netwerk kunt onderzoeken en verkennen.

Microsoft gebruikt uw gegevens niet voor reclame.

## <a name="data-protection-and-encryption"></a>Gegevensbeveiliging en versleuteling
De Defender for Endpoint-service maakt gebruik van geavanceerde gegevensbeschermingstechnologieën die zijn gebaseerd op de Microsoft Azure-infrastructuur. 

Er zijn verschillende aspecten die relevant zijn voor gegevensbescherming die door onze service worden verzorgd. Versleuteling is een van de meest kritieke en bevat gegevensversleuteling in rust, versleuteling tijdens de vlucht en sleutelbeheer met Key Vault. Zie Overzicht van [Azure-versleuteling](https://docs.microsoft.com/azure/security/security-azure-encryption-overview)voor meer informatie over andere technologieën die worden gebruikt door de Defender for Endpoint-service. 

In alle scenario's worden gegevens minimaal versleuteld met 256 bits [AES-versleuteling.](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard)


## <a name="data-storage-location"></a>Locatie voor gegevensopslag

Defender for Endpoint is actief in de Microsoft Azure-datacenters in de Europese Unie, het Verenigd Koninkrijk of in de Verenigde Staten. Klantgegevens die door de service worden verzameld, kunnen worden opgeslagen in: (a) de geografische locatie van de tenant die is geïdentificeerd tijdens de inrichting of (b) als Defender voor Eindpunt een andere onlineservice van Microsoft gebruikt om dergelijke gegevens te verwerken, de geolocatie zoals gedefinieerd door de regels voor gegevensopslag van die andere onlineservice.

Klantgegevens in gepseudonimiseerde vorm kunnen ook worden opgeslagen in de centrale opslag- en verwerkingssystemen in de Verenigde Staten.

Nadat de gegevens zijn geconfigureerd, kunt u de locatie waarop uw gegevens zijn opgeslagen niet wijzigen. Dit biedt een handige manier om compliancerisico's te minimaliseren door actief de geografische locaties te selecteren waar uw gegevens zich bevinden. 

## <a name="is-my-data-isolated-from-other-customer-data"></a>Zijn mijn gegevens geïsoleerd van andere klantgegevens?
Ja, uw gegevens worden geïsoleerd door toegangsverificatie en logische scheiding op basis van klant-id. Elke klant heeft alleen toegang tot gegevens die zijn verzameld vanuit de eigen organisatie en algemene gegevens die Microsoft levert.

## <a name="how-does-microsoft-prevent-malicious-insider-activities-and-abuse-of-high-privilege-roles"></a>Hoe voorkomt Microsoft schadelijke insideractiviteiten en misbruik van hoge bevoegdhedenrollen?

Microsoft-ontwikkelaars en -beheerders hebben per ontwerp voldoende bevoegdheden gekregen om hun toegewezen taken uit te voeren voor het uitvoeren en ontwikkelen van de service. Microsoft implementeert combinaties van preventieve, reactieve en reactieve besturingselementen, waaronder de volgende mechanismen om te beschermen tegen onbevoegde ontwikkelaars en/of administratieve activiteiten:

- Besturingselement voor toegang tot gevoelige gegevens
- Combinaties van besturingselementen die de onafhankelijke detectie van schadelijke activiteiten sterk verbeteren
- Meerdere niveaus voor monitoring, logboekregistratie en rapportage

Daarnaast voert Microsoft achtergrondverificatiecontroles uit van bepaalde personeelsleden en beperkt de toegang tot toepassingen, systemen en netwerkinfrastructuur in verhouding tot het niveau van achtergrondverificatie. Operationeel personeel volgt een formeel proces wanneer ze bij de uitvoering van hun taken toegang moeten krijgen tot het account of de gerelateerde informatie van een klant.

Toegang tot gegevens voor services die zijn geïmplementeerd in microsoft Azure Government-datacenters wordt alleen verleend aan besturingssystemen die zijn gescreend en goedgekeurd voor het verwerken van gegevens die onderhevig zijn aan bepaalde overheidsvoorschriften en -vereisten, zoals FedRAMP, NIST 800.171 (DIB), ITAR, IRS 1075, DoD L4 en CJIS.


## <a name="is-data-shared-with-other-customers"></a>Worden gegevens gedeeld met andere klanten?
Nee. Klantgegevens worden geïsoleerd van andere klanten en worden niet gedeeld. Inzichten over de gegevens die het gevolg zijn van microsoft-verwerking en die geen klantspecifieke gegevens bevatten, kunnen echter worden gedeeld met andere klanten. Elke klant heeft alleen toegang tot gegevens die zijn verzameld vanuit de eigen organisatie en algemene gegevens die Microsoft levert.

## <a name="how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy"></a>Hoe lang worden mijn gegevens door Microsoft opgeslagen? Wat is het gegevensretentiebeleid van Microsoft?
**Bij service onboarding**<br>
U kunt het bewaarbeleid voor uw gegevens kiezen. Hiermee wordt bepaald hoelang Uw gegevens worden opgeslagen in Window Defender voor Endpoint. U kunt flexibel kiezen tussen één maand en zes maanden om te voldoen aan de vereisten voor naleving van de regelgeving van uw bedrijf.

**Bij contractbeëindiging of vervaldatum**<br>
Uw gegevens worden bewaard en zijn beschikbaar voor u terwijl de licentie onder respijtperiode of opgeschorte modus valt. Aan het einde van deze periode worden deze gegevens uit de systemen van Microsoft gewist om deze niet meer te kunnen terugverbinden, niet later dan 180 dagen na beëindiging of vervaldatum van het contract.


## <a name="can-microsoft-help-us-maintain-regulatory-compliance"></a>Kan Microsoft ons helpen de naleving van de regelgeving te handhaven?

Microsoft biedt klanten gedetailleerde informatie over de beveiligings- en complianceprogramma's van Microsoft, waaronder auditrapporten en compliancepakketten, om klanten te helpen Defender voor Endpoint-services te beoordelen op basis van hun eigen wettelijke en wettelijke vereisten. Defender for Endpoint heeft een aantal certificeringen behaald, waaronder ISO, SOC, FedRAMP High en PCI, en blijft aanvullende nationale, regionale en branchespecifieke certificeringen volgen.

Door klanten te voorzien van compatibele, onafhankelijk gecontroleerde services, maakt Microsoft het voor klanten gemakkelijker om naleving te bereiken voor de infrastructuur en toepassingen die ze uitvoeren.

Zie [Microsoft Trust Center](https://servicetrust.microsoft.com/)voor meer informatie over de certificeringsrapporten van Defender voor Eindpunt. 

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-datastorage-belowfoldlink) 
