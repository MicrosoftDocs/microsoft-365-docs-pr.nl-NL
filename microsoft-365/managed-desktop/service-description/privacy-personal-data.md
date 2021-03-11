---
title: Privacy en persoonlijke gegevens
description: Details van de gegevens die door de service worden verzameld, opgeslagen en gebruikt
keywords: AVG, bewaar,verwijdering, opslag, bewaar, verwerking, beveiliging, controle
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
ms.openlocfilehash: e98d42e79ac270e6ccce46e88e3b8ff00f8bfc0a
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712304"
---
# <a name="privacy-and-personal-data"></a>Privacy en persoonlijke gegevens

Gebruikers kunnen gegevens ontvangen, verzenden en opslaan op apparaten die worden beheerd door het beheerde bureaublad van Microsoft. Ze vertrouwen erop dat de privacy van de gegevens wordt beschermd en alleen wordt gebruikt op een manier die aan de verwachtingen is voldaan. In dit artikel wordt uitgelegd hoe microsoft Managed Desktop persoonlijke gegevens verzamelt, bewaart, behoudt, processen, beveiligt, deelt, audits en exporteert. U leert ook hoe een beheerder persoonlijke gegevens kan bekijken, corrigeren en verwijderen.

Microsoft Managed Desktop gebruikt geen persoonsgegevens die worden verzameld als onderdeel van de service voorprofilering, advertenties of marketingdoeleinden.

## <a name="data-collection-of-microsoft-managed-desktop"></a>Gegevensverzameling van Microsoft Managed Desktop

Wanneer gebruikers bedrijfsapparaten registreren bij Microsoft Managed Desktop, wordt het verzamelen van gegevens (op de technische laag) uitgevoerd met behulp van Windows en Microsoft Intune. Deze bronnen verzamelen persoonlijke gegevens over apparaten van gebruikers, zoals apparaatnamen voor Het beheerde bureaublad van Microsoft, om het apparaat te identificeren dat moet worden beheerd en geleverd met de beheerde bureaublad-ervaringen van Microsoft.

Microsoft Managed Desktop verzamelt niet zelf gegevens om de service te bieden (met uitzondering van contactgegevens [van IT-beheerder.](#it-admin-contact-information) In plaats daarvan worden gegevens die andere bronnen, zoals Windows en Microsoft Intune, al hebben verzameld, opnieuw gebruikt door Microsoft Managed Desktop. Microsoft Managed Desktop gebruikt gegevens die door deze services worden verzameld van geregistreerde apparaten:

- Diagnostische Windows-gegevens van apparaten die worden beheerd door Microsoft Managed Desktop, worden verzonden naar de diagnostische gegevensopslag van Windows van Microsoft.
- Microsoft Managed Desktop maakt gebruik [van modern beheer](https://docs.microsoft.com/learn/modules/introduction-to-modern-management-in-microsoft-365/) voor het beheren van de geregistreerde apparaten. Als onderdeel van 'modern beheer' moeten de apparaten zijn geregistreerd in Azure Active Directory van de tenant.
- Voor het distribueren van de sterk geoptimaliseerde en veilige configuratie naar geregistreerde apparaten maakt Microsoft Managed Desktop gebruik van Microsoft Intune.
- Microsoft Managed Desktop maakt gebruik van beveiligingsinformatiegegevens van Microsoft Defender Advanced Thread Protection voor klanten die van deze service gebruikmaken.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Gegevensopslag en bronnen in het beheerde bureaublad van Microsoft

Nadat de gegevens door Microsoft Managed Desktop zijn opgeslagen, moet het de service, opslag en verwerking van die gegevens bieden:

### <a name="storing-data-storage-location-and-data-retention"></a>Gegevens, opslaglocatie en gegevensretentie opslaan

De gegevens worden opgeslagen in een of meer van de volgende opslagservices van Microsoft:

- Azure SQL
- Azure-opslag
- Dynamics 365

Microsoft Managed Desktop slaat de gegevens op in de Verenigde Staten. Persoonlijke gegevens worden maximaal 30 dagen bewaard door Beheerd bureaublad van Microsoft, met uitzondering van waarschuwingsgegevens voor door Microsoft Defender voor Eindpunt verzamelde Apparaten voor het beheerde bureaublad van Microsoft. De werkelijke waarschuwingsgegevens (waaronder persoonlijke gegevens) worden 180 dagen bewaard. Waarschuwingsgegevens met persoonlijke gegevens die zijn verwijderd, worden maximaal twee jaar bewaard. In overeenstemming met de Algemene Verordening Gegevensbescherming (AVG) en APK (California Consumer Privacy Act), houdt Microsoft Managed Desktop zich aan de rechten van de onderwerpsgegevens voor alle persoonsgegevens die zijn opgeslagen in waarschuwingsgegevens.

### <a name="staff-location"></a>Personeelslocatie

De teams microsoft Managed Desktop Operations and Security Operations bevinden zich in de Verenigde Staten en India.

## <a name="data-usage-of-microsoft-managed-desktop"></a>Dataverbruik van Microsoft Managed Desktop

Microsoft Managed Desktop gebruikt deze gegevens:


| Gegevensbronnen |Gebruiken met Beheerd bureaublad van Microsoft  |
|---------|---------|
|Azure Active Directory-gegevens     | Wordt gebruikt in rapporten die zijn gemaakt voor tenantbeheerders, die beschikbaar zijn in de beheerportal van Microsoft Managed Desktop.        |
|Intune-gegevens     | Wordt gebruikt in rapporten die zijn gemaakt voor tenantbeheerders, die beschikbaar zijn in de beheerportal van Microsoft Managed Desktop.        |
|Microsoft Defender for Endpoint     |  Wordt gebruikt voor het adressering van beveiligingsrisico's die zijn gedetecteerd op geregistreerde apparaten door het Security Operations Center (SOC) van Microsoft Managed Desktop.  |
|Diagnostische Windows-gegevens     |Wordt gebruikt om de updatestatus van beheerde apparaten te bepalen en om de ITaaS-aanbieding (IT-as-a-Service) van Microsoft Managed Desktop te bieden en te verbeteren.         |
|Contactgegevens beheerder     | Wordt gebruikt door Beheerd bureaublad van Microsoft om te communiceren met tenantbeheerders.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Entiteiten die worden verwerkt door het beheerde bureaublad van Microsoft

Microsoft Managed Desktop verwerkt deze entiteiten om de service te bieden:

- Apparaatgegevens
- Beveiligingsinstellingen voor apparaten
- Besturingssysteem en hardware van apparaat
- Samengevoegde informatie over de status van apparaten
- Diagnostische gegevens van apparaat
- Tenantgegevens
- Azure Active Directory-bronnen
- Gegevens van beleid en configuratie
- Metagegevens en waarschuwingsgegevens van Microsoft Defender voor eindpunt
- Diagnostische Windows-gegevens
- Gebruiksgegevens voor producten en diensten

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Identiteitsgegevens die worden gebruikt door het beheerde bureaublad van Microsoft, worden door Azure Active Directory opgeslagen op een geografische locatie op basis van het adres dat de organisatie heeft opgegeven bij het abonneren op een Microsoft-onlineservice, zoals Office 365 of Azure. Zie [Microsoft Azure: waar zijn mijn klantgegevens?](http://azuredatacentermap.azurewebsites.net/) voor een kaart met de datacenters voor Azure Active Directory.

Zie Azure Active Directory– Waar bevinden zich uw gegevens voor meer informatie over de regio's waar Azure gebruikmaakt van [gegevensopslag.](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

### <a name="microsoft-intune"></a>Microsoft Intune

Intune-gegevens kunnen worden opgeslagen in een paar verschillende regio's, zoals Europa (Noord- (Ierland) en Europa West (Nederland). Uw IT-beheerder maakt een tenantaccount en kiest het land waar de gegevens worden opgeslagen wanneer ze zich in eerste instantie registreren voor Intune-services. Voor een lijst met datacenterlocaties die door Intune worden gebruikt, bekijkt u [Microsoft Intune: waar zijn mijn klantgegevens?](http://intunedatacentermap.azurewebsites.net/) Zie Gegevens verzamelen in Intune voor meer informatie over het opslaan en gebruiken van [gegevens door Intune.](https://docs.microsoft.com/intune/privacy-data-collect)

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint

Gegevens van Microsoft Defender voor eindpunt kunnen in een paar verschillende regio's worden opgeslagen. Om deze reden werkt Defender for Endpoint in de microsoft Azure-datacenters in de Europese Unie, het Verenigd Koninkrijk en in de Verenigde Staten, zoals vermeld bij [Microsoft Defender for Endpoint: gegevensopslaglocaties.](http://intunedatacentermap.azurewebsites.net/) Zie Welke gegevens worden door Microsoft Defender for Endpoint verzameld voor meer informatie over het opslaan en gebruiken van gegevens door Defender [voor eindpunt?](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Zoals wordt vermeld in de privacyverklaring van [Microsoft,](https://privacy.microsoft.com/privacystatement)kunnen door Microsoft verzamelde persoonlijke gegevens worden opgeslagen en verwerkt in uw regio, in de Verenigde Staten en in een ander land waar Microsoft of haar filialen, dochterondernemingen of serviceproviders vestigingen hebben. [...] Meestal bevindt de primaire opslaglocatie zich in de regio van de klant of in de Verenigde Staten, vaak met een back-up naar een datacenter in een andere regio. De opslaglocatie(s) worden gekozen om efficiënt te werken, de prestaties te verbeteren en redundantie te creëren om de gegevens te beschermen bij een storing of een ander probleem. We nemen stappen om ervoor te zorgen dat de gegevens die we onder deze privacyverklaring verzamelen, worden verwerkt op basis van de bepalingen van deze verklaring en de vereisten van de toepasselijke wetgeving, waar de gegevens zich ook bevinden.'

Zie de sectie 'Waar [we](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) persoonlijke gegevens opslaan en verwerken' van de Privacyverklaring van Microsoft voor meer informatie over het verzamelen van diagnostische gegevens van Windows 10.

## <a name="data-access-protection"></a>Gegevenstoegangsbescherming

Directe toegang tot de interne gegevensopslag van Microsoft Managed Desktop is op verschillende manieren beperkt:

- Goedkeuring op engineeringniveau is vereist.
- Er wordt zowel een controle uitgevoerd als de tijd is beperkt.
- Hiervoor is het gebruik van een hoog beveiligd en beperkt werkstation vereist.
- Alle gegevens worden versleuteld terwijl deze worden opgeslagen.
- Er is geen staande toegang.
- Toegang tot de interne beheerportal van Microsoft Managed Desktop vereist een sterk beveiligd en beperkt werkstation.

## <a name="processing-personal-data-in-a-compliant-manner"></a>Persoonlijke gegevens op een compatibele manier verwerken
In Microsoft Managed Desktop worden persoonlijke gegevens verwerkt met ISO-gecertificeerde systemen. Zie Compliance voor meer [informatie.](../intro/compliance.md)

## <a name="profiling-and-marketing"></a>Profileren en marketing

Microsoft Managed Desktop gebruikt geen persoonsgegevens die worden verzameld als onderdeel van de service voorprofilering, advertenties of marketingdoeleinden.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Verzoeken van een gegevensonderwerp voor de AVG en THEE.A.

De Algemene Verordening Gegevensbescherming [(AVG)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) van de Europese Unie geeft personen (in de regelgeving bekend als gegevensonderwerpen) rechten om de persoonsgegevens te beheren die zijn verzameld door een werkgever of ander type instantie of organisatie (de zogenaamde gegevenscontroller of alleen controller). Persoonlijke gegevens worden globaal onder de AVG gedefinieerd als alle gegevens die betrekking hebben op een geïdentificeerde of identificeerbare natuurlijke persoon. De AVG geeft onderwerpen specifieke rechten op hun persoonlijke gegevens; deze rechten omvatten het verkrijgen van kopieën van persoonlijke gegevens, het aanvragen van correcties, het beperken van de verwerking ervan, het verwijderen ervan of het ontvangen ervan in een elektronische indeling, zodat deze naar een andere controller kan worden verplaatst. Een formele aanvraag van een persoon die aan een controller is onderworpen om actie te ondernemen op zijn of haar persoonlijke gegevens, wordt een aanvraag of DSR van een gegevensonderwerp genoemd.

Op dezelfde manier biedt DE AFW.A privacyrechten en verplichtingen aan Consumenten in Californië, met inbegrip van rechten die lijken op de rechten van de avg voor onderwerp van gegevens, zoals het recht om hun persoonlijke gegevens te verwijderen, te openen en te ontvangen (overdraagbaarheid). De VOORWAARDENA biedt ook bepaalde openbaarmakingen, beveiligingen tegen aantrieding bij het kiezen van rechten voor oefeningen en vereisten voor opt-out /opt-in voor bepaalde gegevensoverdracht die als 'verkoop' zijn geclassificeerd. Verkoop wordt ruim gedefinieerd om het delen van gegevens op te nemen, ter overweging. Zie de Veelgestelde vragen van de California [Consumer Privacy Act](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa?view=o365-worldwide) en California Consumer Privacy Act voor meer informatie over DE [AE.A.](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq?view=o365-worldwide)

In de volgende sectie wordt bespreekt hoe met Beheerd bureaublad van Microsoft controllers persoonlijke gegevens of persoonlijke gegevens die door Microsoft Managed Desktop worden gebruikt, kunnen worden gevonden, toegankelijk zijn en waarop deze kunnen worden toegepast.

> [!NOTE]
> Als u op zoek bent naar algemene informatie over de AVG, zie de [avg-sectie](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) van de Service Trust Portal.

### <a name="it-admin-contact-information"></a>Contactgegevens IT-beheerder

Een tenantbeheerder kan zijn of haar eigen persoonlijke gegevens (zoals hun eigen contactgegevens) rechtstreeks bekijken, corrigeren en verwijderen in de sectie Beheerderscontacten van de Microsoft Managed Desktop Portal.

## <a name="microsoft-defender-for-endpoint-alert-data"></a>Waarschuwingsgegevens van Microsoft Defender voor eindpunt

Beveiligingsbeheerders kunnen een extractie of verwijdering van persoonlijke gegevens met betrekking tot Microsoft Defender for Endpoint-waarschuwingen aanvragen op een door Microsoft Beheerd bureaublad beheerd apparaat in hun omgeving. De beveiligingsbeheerder moet zich aanmelden bij de beheerportal van Microsoft Managed [Desktop](https://aka.ms/memadmin) en een ondersteuningsaanvraag indienen. Selecteer het **aanvraagtype Wijzigingsaanvraag,** Categorie van beveiliging en **Subcategorie** Overige en geef de relevante apparaatnamen op in de beschrijving, samen met uw aanvraag voor extractie of verwijdering van gegevens.   

### <a name="user-related-personal-data"></a>Persoonlijke gegevens in verband met gebruikers

Afgezien van dit alles, worden door Microsoft Beheerd bureaublad niet zelf persoonlijke gegevens verzameld. In plaats daarvan worden persoonlijke gegevens gebruikt die door andere Microsoft Enterprise Online Services worden verzameld. IT-beheerders die op hun gebruikersverzoeken willen reageren om hun persoonlijke gegevens te bekijken, te corrigeren en te verwijderen, kunnen gebruikmaken van de functies van de onderliggende services die afhankelijk zijn van het beheerde bureaublad van Microsoft. Als u geïnteresseerd bent in het bekijken of verwijderen van persoonlijke gegevens die door deze services worden gebruikt, bekijkt u eerst de [Azure Data Subject Requests voor](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure) het AVG-artikel.

Gebruik bovendien de volgende richtlijnen om DSR's uit te oefenen voor de services Microsoft Managed Desktop die afhankelijk zijn van het verzamelen van persoonlijke gegevens:

- [Microsoft Azure Active Directory](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-intune?view=o365-worldwide)
- [Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
