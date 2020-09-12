---
title: Privacy en persoonlijke gegevens
description: Details de verzamelde, opgeslagen en gebruikte gegevens van de service
keywords: AVG, bewaren, verwijdering, opslag, bewaren, verwerking, beveiliging, controle
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: e7eb3eaa6961993f8c77645c8d6760e6701817e2
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547936"
---
# <a name="privacy-and-personal-data"></a>Privacy en persoonlijke gegevens

Gebruikers kunnen gegevens ontvangen, verzenden en bewaren op apparaten die worden beheerd via Microsoft Managed Desktop. Ze vertrouwen dat de privacy van de gegevens is beveiligd en uitsluitend op een wijze wordt gebruikt die consistent is met de verwachtingen. In dit artikel wordt uitgelegd hoe u Microsoft Managed Desktop verzamelt, opslaat, onderhoudt, verwerkt, beheert, beveiligt, deelt, controleert en exporteert. U leert ook hoe een beheerder persoonlijke gegevens kan weergeven, corrigeren en verwijderen.

Microsoft Managed Desktop maakt geen gebruik van persoonlijke gegevens die zijn verzameld als onderdeel van de service voor profileering, advertenties of marketingdoeleinden.

## <a name="data-collection-of-microsoft-managed-desktop"></a>Gegevensverzameling van Microsoft Managed Desktop

Wanneer gebruikers de bedrijfsapparatuur registreren in Microsoft Managed Desktop, wordt het verzamelen van gegevens verwerkt op de technische laag, met behulp van Windows en Microsoft intune. Deze bronnen verzamelen persoonlijke gegevens over de apparaten van gebruikers, zoals de apparaatnaam voor Microsoft Managed Desktop, zodat het apparaat kan worden beheerd en geleverd wordt met de Microsoft beheerde bureaubladervaring.

Microsoft Managed Desktop verzamelt geen gegevens met zichzelf om de service ervan te geven (met uitzondering van [contactgegevens voor IT-beheerders](#it-admin-contact-information). In plaats hiervan worden gegevens die door Microsoft worden beheerd, opnieuw gebruikt met andere bronnen, zoals Vensters en Microsoft intune, al verzameld. Microsoft Managed Desktop gebruikt gegevens die worden verzameld via ingeschreven apparaten:

- Diagnostische gegevens van Windows die worden beheerd door Microsoft Managed Desktop, worden verzonden naar de diagnostische gegevens van Microsoft Windows.
- Microsoft Managed Desktop gebruikt [modern management](https://docs.microsoft.com/learn/modules/introduction-to-modern-management-in-microsoft-365/) voor het beheren van de ingeschreven apparaten. U moet de apparaten als onderdeel registreren in azure Active Directory van de Tenant.
- Microsoft Managed Desktop gebruikt Microsoft intune voor het distribueren van de hoogst geoptimaliseerde en veilige configuratie van geregistreerde apparaten.
- Microsoft Managed Desktop gebruikt beveiligings Intelligence gegevens van Microsoft Defender Advanced thread Protection voor klanten die deze service gebruiken.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Gegevensopslag en bronnen in Microsoft Managed Desktop

Nadat het Microsoft-bureaublad de gegevens heeft opgehaald, moet de service, opslag en verwerking van die gegevens als volgt worden uitgevoerd:

### <a name="storing-data-storage-location-and-data-retention"></a>Gegevens opslaan, opslaglocatie en gegevensretentie

Microsoft Managed Desktop slaat de gegevens op een of meer van de volgende Microsoft Storage services op:

- Azure SQL
- Azure-opslag

Microsoft Managed Desktop slaat de gegevens op in de Verenigde Staten. Persoonlijke gegevens blijven gedurende dertig dagen door Microsoft beheerd bureaublad bewaard.

## <a name="data-usage-of-microsoft-managed-desktop"></a>Data gebruik van Microsoft Managed Desktop

Microsoft Managed Desktop gebruikt deze gegevens:


| Gegevensbronnen |Voor gebruik met Microsoft Managed Desktop  |
|---------|---------|
|Azure Active Directory-gegevens     | Wordt gebruikt in rapporten die zijn gemaakt voor tenantbeheerders, die beschikbaar zijn in de portal van Microsoft Managed Desktop-beheerder.        |
|InTune-gegevens     | Wordt gebruikt in rapporten die zijn gemaakt voor tenantbeheerders, die beschikbaar zijn in de portal van Microsoft Managed Desktop-beheerder.        |
|Microsoft Defender Advanced Threat Protection (ATP)     |  Wordt gebruikt voor het adresseren van beveiligingsbedreigingen op geregistreerde apparaten door Microsoft beheerde bureaublad beveiliging voor processen.  |
|Diagnostische gegevens voor Windows     |Wordt gebruikt om de status van de update van beheerde apparaten te bepalen en de IT-service voor het beheer van de IT-Service (ITaaS) van Microsoft te verbeteren.         |
|Contactgegevens beheerder     | Wordt door Microsoft Managed Desktop gebruikt om te communiceren met tenantbeheerders.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Door Microsoft beheerde desktop verwerkte entiteiten

Beheerde bureaublad processen van Microsoft verwerken deze entiteiten om de service te verlenen:

- Apparaatgegevens
- Beveiligingsinstellingen voor apparaten
- Besturingssysteem en hardware voor apparatuur
- Geaggregeerde informatie over de apparaatstatusverklaring
- Diagnostische gegevens van apparaat
- Tenant gegevens
- Azure Active Directory-bronnen
- Beleids-en configuratiegegevens
- Metagegevens van Microsoft Defender ATP
- Diagnostische gegevens voor Windows
- Gebruiksgegevens van producten en services

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Identiteitsgegevens die door Microsoft worden beheerd bureaublad worden gebruikt, worden opgeslagen door Azure Active Directory op basis van het adres van de organisatie wanneer u zich abonneert op een Microsoft Online-service, zoals Office 365 of Azure. Zie [Microsoft Azure, waar zijn mijn klantgegevens?](http://azuredatacentermap.azurewebsites.net/) voor een kaart met de datacenters voor Azure Active Directory.

Zie [Azure Active Directory – waar bevindt zich uw gegevens](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)voor meer informatie over de regio's die Azure gebruiken voor gegevensopslag.

### <a name="microsoft-intune"></a>Microsoft Intune

InTune-gegevens kunnen worden opgeslagen in een paar verschillende regio's, zoals Europa Noord (Ierland) en Europe West (Nederland). Uw IT-beheerder maakt een Tenant account en kiest het land waar gegevens worden opgeslagen wanneer ze zich aanvankelijk registreren in de intune-Services. Zie [Microsoft intune-waar zijn mijn klantgegevens?](http://intunedatacentermap.azurewebsites.net/)voor een lijst met de datacenter-locaties die worden gebruikt door intune. Zie [gegevens verzamelen in intune](https://docs.microsoft.com/intune/privacy-data-collect)voor meer informatie over het opslaan en gebruiken van gegevens in intune.

### <a name="microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection

Microsoft Defender Advanced Threat Protection (ATP)-gegevens kunnen worden opgeslagen in een paar verschillende regio's. Om die reden werkt Microsoft Defender ATP in de Microsoft Azure-datacenters van de Europese Unie, het Verenigd Koninkrijk, het Verenigd Koninkrijk en in de Verenigde Staten, zoals vermeld op [Microsoft Defender ATP: gegevensopslaglocaties](http://intunedatacentermap.azurewebsites.net/). Zie voor meer informatie over het opslaan en gebruiken van gegevens in Microsoft Defender ATP [welke gegevens worden verzameld in Microsoft Defender ATP?](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Zoals vermeld in de [privacyverklaring van Microsoft](https://privacy.microsoft.com/privacystatement), kunnen persoonlijke gegevens die door Microsoft worden verzameld, worden opgeslagen en verwerkt in uw regio, in de Verenigde Staten en in andere landen waarop Microsoft of zijn gelieerde ondernemingen, dochterondernemingen of service providers hun faciliteiten exploiteren. [...] Meestal is de primaire opslaglocatie in het gebied van de klant of in de Verenigde Staten vaak met een back-up van een datacenter in een andere regio. De opslaglocatie (s) worden gekozen om efficiënt te kunnen werken, om de prestaties te verbeteren en overtolligheden te maken om de gegevens te beschermen als er sprake is van een onderbreking of ander probleem. We nemen de stappen uit om ervoor te zorgen dat de gegevens die u onder deze privacyverklaring ophaalt, wordt verwerkt overeenkomstig de bepalingen van deze verklaring en de vereisten van toepasselijk recht, waar de gegevens zich bevinden.

Zie voor meer informatie over het verzamelen van diagnostische gegevens van Windows 10 de sectie [' waar worden persoonlijke gegevens opgeslagen en verwerkt '](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) van de privacyverklaring van Microsoft.

## <a name="data-access-protection"></a>Gegevens toegangsbeveiliging

U kunt op verschillende manieren directe toegang krijgen tot interne gegevensopslag van Microsoft beheerde bureaubladtoepassingen:

- U moet de functie goedkeuring van engineering-potentiële klanten vereisen.
- Het is zowel gecontroleerd als beperkt.
- Hiervoor is het gebruik van een zeer veilig en beperkt werkstation vereist.
- Alle gegevens worden versleuteld terwijl deze wordt opgeslagen.
- Er is geen permanente toegang.
- Voor toegang tot de interne management portal van Microsoft beheerd bureaublad is een zeer veilig en beperkt werkstation vereist.

## <a name="processing-personal-data-in-a-compliant-manner"></a>Het verwerken van persoonlijke gegevens op een compatibele manier
Microsoft Managed Desktop verwerkt persoonlijke gegevens met ISO-gecertificeerde systemen. Zie [compliance](../intro/compliance.md)voor meer informatie.

## <a name="profiling-and-marketing"></a>Profileering en marketing

Microsoft Managed Desktop maakt geen gebruik van persoonlijke gegevens die zijn verzameld als onderdeel van de service voor profileering, advertenties of marketingdoeleinden.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Aanvragen voor AVG en CCPA

De [algemene verordening gegevensbescherming](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) van de Europese Unie biedt de rechten voor personen (bekend in de voor de regulering als gegevens houders) voor het beheren van de persoonlijke gegevens die zijn verzameld door een werkgever of een ander type agentschap of organisatie (bekend als de gegevenscontroller of een ander type). Persoonlijke gegevens worden zeer algemeen gedefinieerd onder de AVG als gegevens die betrekking hebben op een geïdentificeerde of identificeerbare natuurlijke persoon. Het AVG bevat gegevens die specifiek rechten zijn voor hun persoonlijke gegevens. deze rechten omvatten het verkrijgen van kopieën van persoonlijke gegevens, het aanvragen van correcties aan de persoon, het beperken van de verwerking, het verwijderen van de gegevens of het ontvangen van een elektronische indeling, zodat u deze naar een andere controller kunt verplaatsen. Een formele aanvraag door een verantwoordelijke persoon aan een controller om een actie te ondernemen op hun persoonlijke gegevens wordt een aanvraag voor een subject of DSR genoemd.

Evenzo biedt de privacyverklaring voor consumenten van Californië (CCPA) de bescherming van de privacy en de verplichtingen aan klanten van Californië, waaronder rechten die vergelijkbaar zijn met de rechten van de gebruikersrechten van AVG, zoals het recht op verwijderen, toegang en ontvangst (portabiliteit), hun persoonlijke gegevens. De CCPA levert ook voor bepaalde informatie, bescherming tegen discriminatie wanneer u bevoegdheden voor de uitoefening van de uitoefening kiest, en ' opt-out/opt-in ' voor bepaalde gegevensoverdrachten geclassificeerd als ' verkoop '. Voor de verkoop zijn uitgebreide informatie, zoals het delen van gegevens voor een waardevolle aandacht. Zie voor meer informatie over de CCPA de privacyverklaring van de [consument van Californië](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa?view=o365-worldwide) en de [Veelgestelde vragen over consumenten van Californië](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq?view=o365-worldwide).

In het volgende gedeelte wordt uitgelegd hoe u met Microsoft Managed Desktop om persoonlijke gegevens of persoonlijke gegevens die door Microsoft worden beheerd bureaublad gebruikt, te vinden, te openen en te handelen.

> [!NOTE]
> Als u op zoek bent naar algemene informatie over de AVG, raadpleegt u het [gedeelte AVG](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) van de service Trust Portal.

### <a name="it-admin-contact-information"></a>Contactgegevens voor IT-beheerder

Een tenantbeheerder kan hun persoonlijke gegevens rechtstreeks weergeven, corrigeren en verwijderen in de sectie beheerder contact van de beheerde bureaublad portal van Microsoft.

### <a name="user-related-personal-data"></a>Persoonlijke gegevens die aan de gebruiker zijn gekoppeld

Afgezien van dit houdt Microsoft-bureaublad geen persoonlijke gegevens te verzamelen. In plaats daarvan wordt er gebruikgemaakt van persoonlijke gegevens die worden verzameld door andere online-services van Microsoft Enterprise. IT-beheerders die willen reageren op hun gebruikersverzoeken hun persoonlijke gegevens te bekijken, te corrigeren en verwijderen, kunnen hun persoonlijke gegevens gebruiken, afhankelijk van de functies van de onderliggende services die door Microsoft worden beheerd op het bureaublad. Als u persoonlijke gegevens die door deze services worden gebruikt, wilt weergeven of verwijderen, raadpleegt u eerst de [Azure data subject-aanvragen voor het AVG](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure) -artikel.

Daarnaast moet u de volgende richtlijnen volgen voor het uitvoeren van DSRs voor de services die door Microsoft worden beheerd, afhankelijk van het verzamelen van persoonlijke gegevens:

- [Microsoft Azure Active Directory](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-intune?view=o365-worldwide)
- [Microsoft Defender ATP](https:/docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
