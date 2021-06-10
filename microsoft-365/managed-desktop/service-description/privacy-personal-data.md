---
title: Privacy en persoonlijke gegevens
description: Details van de gegevens die door de service zijn verzameld, opgeslagen en gebruikt
keywords: AVG, bewaring, verwijdering, opslag, bewaring, verwerking, beveiliging, controle
ms.service: m365-md
ms.sitesec: library
author: jaimeo
manager: laurawi
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
audience: Admin, ITPro
ms.localizationpriority: normal
ms.openlocfilehash: 3de39e8d10f949856862095ebd204fac1a4d694e
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861681"
---
# <a name="privacy-and-personal-data"></a>Privacy en persoonlijke gegevens

Gebruikers kunnen gegevens ontvangen, verzenden en opslaan op apparaten die worden beheerd door Microsoft Managed Desktop. Ze vertrouwen erop dat de privacy van de gegevens wordt beschermd en alleen wordt gebruikt op een manier die in overeenstemming is met hun verwachtingen. In dit artikel wordt uitgelegd hoe Microsoft Managed Desktop persoonlijke gegevens verzamelt, op slaat, bewaart, verwerkt, beveiligt, deelt, controleert en exporteert. U leert ook hoe een beheerder persoonlijke gegevens kan bekijken, corrigeren en verwijderen.

Microsoft Managed Desktop gebruikt geen persoonlijke gegevens die worden verzameld als onderdeel van het leveren van de service voor profilerings-, reclame- of marketingdoeleinden.

## <a name="data-collection-of-microsoft-managed-desktop"></a>Gegevensverzameling van Microsoft Managed Desktop

Wanneer gebruikers zakelijke apparaten registreren voor Microsoft Managed Desktop, wordt gegevensverzameling op de technische laag verwerkt met behulp van Windows en Microsoft Intune. Deze bronnen verzamelen persoonlijke gegevens over apparaten van gebruikers, zoals apparaatnamen voor Microsoft Managed Desktop om het apparaat te kunnen identificeren dat moet worden beheerd en met de Microsoft Managed Desktop worden geleverd.

Microsoft Managed Desktop verzamelt geen gegevens op zichzelf om de service te leveren (met uitzondering van [contactgegevens van IT-beheerder.](#it-admin-contact-information) In plaats Microsoft Managed Desktop gegevens die andere bronnen, zoals Windows en Microsoft Intune, al hebben verzameld. Microsoft Managed Desktop gebruikt gegevens die deze services verzamelen van geregistreerde apparaten:

- Windows diagnostische gegevens van apparaten die door Microsoft Managed Desktop worden verzonden naar de Windows van Microsoft.
- Microsoft Managed Desktop gebruikt [modern beheer voor](/learn/modules/introduction-to-modern-management-in-microsoft-365/) het beheren van de geregistreerde apparaten. Als onderdeel van 'modern beheer' moeten de apparaten zijn geregistreerd in het Azure Active Directory.
- Voor het distribueren van de sterk geoptimaliseerde en veilige configuratie naar geregistreerde apparaten, Microsoft Managed Desktop gebruikt Microsoft Intune.
- Microsoft Managed Desktop gebruikt beveiligingsinformatiegegevens van Microsoft Defender Advanced Thread Protection voor klanten die die service gebruiken.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Gegevensopslag en bronnen in Microsoft Managed Desktop

Nadat Microsoft Managed Desktop de gegevens heeft verzameld, moet deze de service, opslag en verwerking van die gegevens als volgt leveren:

### <a name="storing-data-storage-location-and-data-retention"></a>Gegevens, opslaglocatie en gegevensretentie opslaan

Microsoft Managed Desktop slaat de gegevens op in een of meer van de volgende Microsoft-opslagservices:

- Azure SQL
- Azure-opslag
- Dynamics 365

Microsoft Managed Desktop slaat de gegevens op in de Verenigde Staten. Persoonlijke gegevens worden door de Microsoft Managed Desktop maximaal 30 dagen bewaard, met uitzondering van waarschuwingsgegevens voor Microsoft Managed Desktop apparaten die door Microsoft Defender voor Eindpunt zijn verzameld. De werkelijke waarschuwingsgegevens (waaronder persoonlijke gegevens) worden 180 dagen opgeslagen. Waarschuwingsgegevens met verwijderde persoonlijke gegevens worden maximaal twee jaar opgeslagen. In overeenstemming met de Algemene verordening gegevensbescherming (AVG) en de California Consumer Privacy Act (CTPA) respecteert Microsoft Managed Desktop de rechten van de gegevenspersoon voor alle persoonsgegevens die zijn opgeslagen in waarschuwingsgegevens.

### <a name="staff-location"></a>Personeelslocatie

De Microsoft Managed Desktop Operations and Security Operations teams bevinden zich in de Verenigde Staten en India.

## <a name="data-usage-of-microsoft-managed-desktop"></a>Gegevensgebruik van Microsoft Managed Desktop

Microsoft Managed Desktop gebruikt deze gegevens:


| Gegevensbronnen |Gebruiken met Microsoft Managed Desktop  |
|---------|---------|
|Azure Active Directory gegevens     | Gebruikt in rapporten die zijn gemaakt voor tenantbeheerders, die beschikbaar zijn in de Microsoft Managed Desktop Beheerportal.        |
|Intune-gegevens     | Gebruikt in rapporten die zijn gemaakt voor tenantbeheerders, die beschikbaar zijn in de Microsoft Managed Desktop Beheerportal.        |
|Microsoft Defender voor Eindpunt     |  Wordt gebruikt voor het aanpakken van beveiligingsrisico's die zijn gedetecteerd op geregistreerde apparaten door Microsoft Managed Desktop beveiligingscentrum (SOC).  |
|Windows diagnostische gegevens     |Wordt gebruikt om de updatestatus van beheerde apparaten te bepalen en om het IT-as-a-Service-aanbod (ITaaS) van Microsoft Managed Desktop te bieden en te verbeteren.         |
|Contactgegevens van beheerder     | Gebruikt door Microsoft Managed Desktop om te communiceren met tenantbeheerders.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Entiteiten die zijn verwerkt door Microsoft Managed Desktop

Microsoft Managed Desktop deze entiteiten verwerkt om de service te leveren:

- Apparaatgegevens
- Apparaatbeveiligingsinstellingen
- Apparaatbesturingssysteem en -hardware
- Samengevoegde informatie over de status van apparaten
- Diagnostische gegevens van apparaten
- Tenantgegevens
- Azure Active Directory resources
- Beleids- en configuratiegegevens
- Microsoft Defender voor metagegevens van eindpunten en waarschuwingsgegevens
- Windows diagnostische gegevens
- Gegevens over product- en servicegebruik

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Identiteitsgegevens die door Microsoft Managed Desktop worden gebruikt, worden door Azure Active Directory opgeslagen op een geografische locatie op basis van het adres dat door de organisatie wordt opgegeven bij het abonneren op een Online Service van Microsoft, zoals Office 365 of Azure. Zie [Microsoft Azure: Waar zijn mijn klantgegevens?](http://azuredatacentermap.azurewebsites.net/) voor een kaart met de datacenters voor Azure Active Directory.

Zie voor meer informatie over de regio's die Azure [gebruikt voor gegevensopslag Azure Active Directory-Waar bevinden zich uw gegevens.](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

### <a name="microsoft-intune"></a>Microsoft Intune

Intune-gegevens kunnen worden opgeslagen in een aantal verschillende regio's, zoals Europa Noord (Ierland) en Europa-West (Nederland). Uw IT-beheerder maakt een tenantaccount en kiest het land waar gegevens worden opgeslagen wanneer ze zich aanvankelijk registreren voor Intune-services. Zie voor een lijst met datacenterlocaties die door Intune worden gebruikt [Microsoft Intune:Waar zijn mijn klantgegevens?](http://intunedatacentermap.azurewebsites.net/). Zie [Gegevensverzameling in Intune](/intune/privacy-data-collect)voor meer informatie over gegevensopslag en gebruik door Intune.

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender voor Eindpunt

Gegevens van Microsoft Defender voor eindpunten kunnen in een aantal verschillende regio's worden opgeslagen. Om deze reden is Defender for Endpoint actief in de Microsoft Azure-datacenters in de Europese Unie, het Verenigd Koninkrijk en de Verenigde Staten, zoals is aangegeven bij [Microsoft Defender voor Eindpunt:](http://intunedatacentermap.azurewebsites.net/)Locaties voor gegevensopslag . Zie Welke gegevens worden door Microsoft Defender voor Eindpunt verzameld voor meer informatie over gegevensopslag en gebruik door Defender voor [Eindpunt?](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Zoals wordt vermeld in de [Privacyverklaring](https://privacy.microsoft.com/privacystatement)van Microsoft , kunnen persoonlijke gegevens die door Microsoft worden verzameld, worden opgeslagen en verwerkt in uw regio, in de Verenigde Staten en in een ander land waar Microsoft of haar gelieerde ondernemingen, dochterondernemingen of serviceproviders vestigingen hebben. [...] Meestal bevindt de primaire opslaglocatie zich in de regio van de klant of in de Verenigde Staten, vaak met een back-up naar een datacenter in een andere regio. De opslaglocatie(en) worden gekozen om efficiënt te kunnen werken, om de prestaties te verbeteren en om redundanties te maken om de gegevens te beschermen als er een uitval of een ander probleem is. We nemen stappen om ervoor te zorgen dat de gegevens die we onder deze privacyverklaring verzamelen, worden verwerkt op basis van de bepalingen van deze verklaring en de vereisten van toepasselijk recht, waar de gegevens zich ook bevinden."

Zie de sectie 'Waar [we](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) persoonlijke gegevens opslaan en verwerken' van de Privacyverklaring van Microsoft voor meer informatie over het verzamelen van diagnostische gegevens van Windows 10 gegevens.

## <a name="data-access-protection"></a>Gegevenstoegangsbeveiliging

Directe toegang tot Microsoft Managed Desktop interne gegevensopslag is op verschillende manieren beperkt:

- Hiervoor is goedkeuring van het technische niveau voor lood vereist.
- Het is tijdgebonden en gecontroleerd.
- Alle gegevens worden versleuteld terwijl deze worden opgeslagen.
- Voor toegang Microsoft Managed Desktop interne beheerportal van uw bedrijf is een sterk beveiligd en beperkt werkstation vereist.

## <a name="processing-personal-data-in-a-compliant-manner"></a>Persoonsgegevens op een compatibele manier verwerken
Microsoft Managed Desktop verwerkt persoonsgegevens met ISO-gecertificeerde systemen. Zie Compliance voor [meer informatie.](../intro/compliance.md)

## <a name="profiling-and-marketing"></a>Profilering en marketing

Microsoft Managed Desktop gebruikt geen persoonlijke gegevens die worden verzameld als onderdeel van het leveren van de service voor profilerings-, reclame- of marketingdoeleinden.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Verzoeken om gegevensonderwerpen voor de AVG en CTPA

De Algemene verordening gegevensbescherming van de Europese Unie [(AVG)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) geeft personen (in de verordening bekend als gegevensonderwerpen) het recht om de persoonlijke gegevens te beheren die zijn verzameld door een werkgever of ander type instantie of organisatie (bekend als de gegevenscontroller of alleen controller). Persoonsgegevens worden onder de AVG in grote lijnen gedefinieerd als gegevens die betrekking hebben op een geïdentificeerde of identificeerbare natuurlijke persoon. De AVG geeft gegevensonderwerpen specifieke rechten op hun persoonlijke gegevens. Deze rechten omvatten het verkrijgen van kopieën van persoonlijke gegevens, het aanvragen van correcties, het beperken van de verwerking ervan, het verwijderen ervan of het ontvangen ervan in een elektronische indeling, zodat deze naar een andere controller kan worden verplaatst. Een formeel verzoek van een gegevenspersoon aan een controller om actie te ondernemen op zijn of haar persoonlijke gegevens, wordt een verzoek om gegevensonderwerp of DSR genoemd.

Op dezelfde manier biedt de CTPA privacyrechten en -verplichtingen aan Californische consumenten, met inbegrip van rechten die vergelijkbaar zijn met de avg-rechten voor gegevensonderwerpen, zoals het recht om hun persoonlijke gegevens te verwijderen, te openen en te ontvangen (overdraagbaarheid). De CTPA voorziet ook in bepaalde openbaarmakingen, bescherming tegen discriminatie bij het kiezen van oefenrechten en 'opt-out/opt-in'-vereisten voor bepaalde gegevensoverdrachten die als 'verkoop' zijn geclassificeerd. Verkoop wordt breed gedefinieerd om het delen van gegevens op te nemen voor een waardevolle overweging. Zie de California Consumer Privacy [Act](/compliance/regulatory/offering-ccpa?view=o365-worldwide) en de Veelgestelde vragen over de California Consumer Privacy Act voor meer informatie over de CTPA. [](/compliance/regulatory/ccpa-faq?view=o365-worldwide)

In de volgende sectie wordt bespraken hoe Microsoft Managed Desktop helpt bij het vinden, openen en handelen van persoonlijke gegevens of persoonlijke gegevens die door Microsoft Managed Desktop.

> [!NOTE]
> Als u op zoek bent naar algemene informatie over de AVG, bekijkt u de [sectie AVG](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) van de Service Trust Portal.

### <a name="it-admin-contact-information"></a>Contactgegevens van IT-beheerder

Een tenantbeheerder kan zijn of haar eigen persoonlijke gegevens (zoals hun eigen contactgegevens) rechtstreeks weergeven, corrigeren en verwijderen in de sectie Beheerdercontactcontact van de Microsoft Managed Desktop Portal.

## <a name="microsoft-defender-for-endpoint-alert-data"></a>Waarschuwingsgegevens van Microsoft Defender voor eindpunt

Beveiligingsbeheerders kunnen een extractie of verwijdering van persoonlijke gegevens met betrekking tot Microsoft Defender voor eindpuntwaarschuwingen aanvragen op een Microsoft Managed Desktop beheerd apparaat in hun omgeving. De beveiligingsbeheerder moet zich aanmelden bij de Microsoft Managed Desktop [admin portal](https://aka.ms/memadmin) en een ondersteuningsaanvraag indienen. Selecteer **Ondersteuningsaanvraagtype** Wijzigingsaanvraag, Categorie van beveiliging **en** **Subcategorie** van Overige **en** geef vervolgens de relevante apparaatnamen in de beschrijving op, samen met uw verzoek om gegevens te extrar of te verwijderen.  

### <a name="user-related-personal-data"></a>Gebruikersgerelateerde persoonlijke gegevens

Daarnaast worden er Microsoft Managed Desktop persoonlijke gegevens niet alleen verzameld. In plaats daarvan wordt gebruikgemaakt van persoonlijke gegevens die andere Microsoft Enterprise Online Services hebben verzameld. IT-beheerders die willen reageren op hun gebruikersverzoeken om hun persoonlijke gegevens te bekijken, te corrigeren en te verwijderen, kunnen gebruikmaken van de desbetreffende functionaliteit van de onderliggende services Microsoft Managed Desktop afhankelijk is. Als u geïnteresseerd bent in het weergeven of verwijderen van persoonlijke gegevens die door deze services worden gebruikt, bekijkt u eerst het artikel Azure Data Subject Requests for [the GDPR.](/compliance/regulatory/gdpr-dsr-Azure)

Gebruik bovendien de volgende richtlijnen om DSR's uit te oefenen voor de services Microsoft Managed Desktop afhankelijk is van voor het verzamelen van persoonlijke gegevens:

- [Microsoft Azure Active Directory](/compliance/regulatory/gdpr-dsr-Azure?view=o365-worldwide)
- [Microsoft Intune](/compliance/regulatory/gdpr-dsr-Intune?view=o365-worldwide)
- [Microsoft Defender voor Eindpunt](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](/windows/privacy/windows-10-and-privacy-compliance)
