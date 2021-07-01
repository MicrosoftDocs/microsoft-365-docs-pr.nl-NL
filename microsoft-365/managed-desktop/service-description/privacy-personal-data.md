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
ms.openlocfilehash: 0ee214cf7ff5d5998a7fa35688574a23f8b082f0
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229597"
---
# <a name="overview"></a>Overzicht

Microsoft Managed Desktop is een IT-as-a-Service -service (ITaaS) voor zakelijke cloudklanten die zijn ontworpen om de apparaten van werknemers Windows geïmplementeerd en bijgewerkt te houden. Het biedt ook IT-servicebeheer en -bewerkingen, bewaakt de beveiligings- en incidentrespons en biedt gebruikersondersteuning. Deze documentatie bevat aanvullende informatie over gegevensplatform en privacy compliance voor Microsoft Managed Desktop.

## <a name="microsoft-managed-desktop-data-sources-and-purpose"></a>Microsoft Managed Desktop gegevensbronnen en doel

Microsoft Managed Desktop biedt zijn service aan zakelijke klanten en beheert de geregistreerde apparaten van klanten op de juiste manier met behulp van gegevens uit verschillende bronnen. Deze bronnen, waaronder Azure Active Directory, Microsoft Intune, Microsoft Windows 10 en Microsoft Defender voor Eindpunt, bieden een uitgebreide weergave van de apparaten die Microsoft Managed Desktop beheert. De service gebruikt ook deze Microsoft-services om Microsoft Managed Desktop ITaaS-mogelijkheden te bieden:

- [Microsoft Windows 10 Enterprise](/windows/windows-10/) - voor het beheer van apparaatconfiguratie, het beheren van verbindingen met andere services en operationele ondersteuning voor IT-professionals.
- [Windows Update voor Bedrijven](/windows/deployment/update/waas-manage-updates-wufb) : gebruikt Windows 10 Enterprise diagnostische gegevens om aanvullende informatie over de update Windows 10 geven. 
- [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) - voor apparaatbeheer en om uw gegevens veilig te houden.
  - [Microsoft Azure Active Directory](/azure/active-directory/) - voor verificatie en identificatie van alle gebruikersaccounts. 
  - [Microsoft Intune](/mem/intune/) : voor het distribueren van apparaatconfiguraties, apparaatbeheer en toepassingsbeheer.
  - [Endpoint Analytics:](/mem/analytics/overview) voor analytische inzichten over apparaat- en app-gebruik.
  - [Windows Autopilot:](/microsoft-365/windows/windows-autopilot) voor inrichting en implementatie van apparaten.
  - [Microsoft Defender voor Eindpunt: biedt](/microsoft-365/security/defender-endpoint/) beveiligingsservices, zoals apparaatbeveiligingscontrole en gegevens over beveiligingsinformatie.
- [Microsoft Managed Desktop:](https://endpoint.microsoft.com/#home) gegevens die door de klant worden verstrekt of die door de service zijn gegenereerd tijdens het uitvoeren van de service.
- [Microsoft 365 apps voor ondernemingen :](https://www.microsoft.com/en-us/microsoft-365/enterprise/compare-office-365-plans?rtc=1) voor het beheer van Microsoft 365-apps.

## <a name="microsoft-managed-desktop-data-process-and-storage"></a>Microsoft Managed Desktop gegevensproces en -opslag

Microsoft Managed Desktop is afhankelijk van gegevens van meerdere Microsoft-producten en -services om de service aan zakelijke klanten te leveren. Om het doel van het beveiligen en onderhouden van geregistreerde apparaten te bereiken, verwerken en kopiëren we gegevens van deze services naar Microsoft Managed Desktop. Wanneer we gegevens verwerken, volgen we de gedocumenteerde aanwijzingen die u verstrekt, zoals wordt verwezen in de Voorwaarden voor onlineservices en de Privacyverklaring van Microsoft. Wanneer we gegevens verwerken, volgen we de gedocumenteerde aanwijzingen die u verstrekt, zoals wordt verwezen in de [Voorwaarden voor onlineservices](https://www.microsoft.com/licensing/product-licensing/products) en [de Privacyverklaring van Microsoft.](https://privacy.microsoft.com/privacystatement) Microsoft Managed Desktop verwerkertaken omvatten het waarborgen van de juiste vertrouwelijkheid, beveiliging en tolerantie. Microsoft Managed Desktop gebruikt extra privacy- en beveiligingsmaatregelen om ervoor te zorgen dat persoonlijke identificeerbare gegevens op de juiste manier worden gebruikt. 


## <a name="microsoft-managed-desktop-data-storage-and-staff-location"></a>Microsoft Managed Desktop gegevensopslag en personeelslocatie

Microsoft Managed Desktop slaat de gegevens op in de Azure-datacenters in de Verenigde Staten. Persoonsgegevens die zijn verkregen Microsoft Managed Desktop en andere services zijn vereist om de service operationeel te houden. Als een apparaat wordt verwijderd uit Microsoft Managed Desktop, bewaren we persoonlijke gegevens maximaal 30 dagen, behalve voor waarschuwingsgegevens die zijn verzameld door Microsoft Defender voor Eindpunt, die voor beveiligingsdoeleinden 180 dagen worden opgeslagen. Zie Gegevensbewaring, verwijdering en vernietiging van gegevens [in](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)Microsoft 365.

Microsoft Managed Desktop Teams voor technische bewerkingen en beveiligingsbewerkingen bevinden zich in de Verenigde Staten en India. 

## <a name="microsoft-windows-10-diagnostic-data"></a>Microsoft Windows 10 diagnostische gegevens

Microsoft Managed Desktop gebruikt [Windows 10 uitgebreide](/windows/privacy/windows-diagnostic-data) diagnostische gegevens om uw Windows te beveiligen, up-to-date te houden, problemen op te lossen en productverbeteringen aan te brengen. De uitgebreide instelling voor diagnostische gegevens bevat meer gedetailleerde informatie over de apparaten die zijn Microsoft Managed Desktop en hun instellingen, mogelijkheden en apparaattoestand. Wanneer uitgebreide diagnostische gegevens zijn geselecteerd, worden gegevens, inclusief vereiste diagnostische gegevens, verzameld. Zie [Wijzigingen in het Windows diagnostische gegevensverzameling](/windows/privacy/changes-to-windows-diagnostic-data-collection) voor meer informatie over de Windows 10 diagnostische gegevens en het verzamelen van gegevens.

De terminologie voor diagnostische gegevens wordt gewijzigd in toekomstige versies van Windows. Microsoft Managed Desktop is verplicht om alleen de gegevens te verwerken die de service nodig heeft. Hoewel dit betekent dat het diagnostische niveau wordt gewijzigd in Optioneel **,** wordt Microsoft Managed Desktop het beperkte diagnostische beleid geïmplementeerd om de diagnostische gegevensverzameling die nodig is voor de service, aan te passen. Zie Wijzigingen in Windows [diagnostische gegevensverzameling](/windows/privacy/changes-to-windows-diagnostic-data-collection)voor meer informatie.

Microsoft Managed Desktop worden alleen gegevens op systeemniveau verwerkt en op Windows 10 optionele diagnostische gegevens die afkomstig zijn van geregistreerde apparaten, zoals toepassings- en apparaatbetrouwbaarheid en prestatiegegevens. Microsoft Managed Desktop worden geen persoonlijke gegevens van klanten verwerkt en opgeslagen, zoals chat- en browsergeschiedenis, spraak-, tekst- of spraakgegevens. 

Zie de sectie Waar [we](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) persoonlijke gegevens opslaan en verwerken van de Privacyverklaring van Microsoft voor meer informatie over het verzamelen van diagnostische gegevens van Microsoft Windows 10.

## <a name="microsoft-windows-update-for-business"></a>Microsoft Windows Update voor Bedrijven
Microsoft Windows Update voor Bedrijven gebruikt gegevens uit Windows diagnostische gegevens om updatestatus en -fouten te analyseren. Microsoft Managed Desktop maakt gebruik van deze gegevens en gebruikt deze om problemen te beperken en op te lossen om ervoor te zorgen dat alle geregistreerde apparaten up-to-date zijn op basis van een vooraf gedefinieerde updatefrequentie.

## <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory
Het identificeren van gegevens die door Microsoft Managed Desktop worden gebruikt, wordt opgeslagen door Azure Active Directory (Azure AD) op een geografische locatie op basis van de locatie die door de organisatie wordt verstrekt wanneer u zich abonneert op onlineservices van Microsoft, zoals Microsoft Apps voor ondernemingen en Azure. Het identificeren van gegevens die door Microsoft Managed Desktop worden gebruikt, wordt door Azure AD opgeslagen op een geografische locatie op basis van de locatie die door de organisatie wordt verstrekt wanneer u zich abonneert op microsoft-onlineservices, zoals Microsoft Apps voor ondernemingen en Azure. Zie voor meer informatie over waar uw Azure AD-gegevens zich bevinden [Azure Active Directory - Waar bevinden uw gegevens zich?](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

## <a name="microsoft-intune"></a>Microsoft Intune
Microsoft Intune verzamelt, verwerkt en deelt gegevens om Microsoft Managed Desktop bedrijfsactiviteiten en services te ondersteunen. Zie [Gegevensverzameling in Intune voor](/mem/intune/protect/privacy-data-collect) meer informatie over de gegevens die in Intune worden verzameld. 

Zie Waar uw Microsoft 365 klantgegevens worden opgeslagen voor meer Microsoft Intune [gegevenslocaties.](/microsoft-365/enterprise/o365-data-locations) Intune respecteert de opslaglocatieselecties die de beheerder voor klantgegevens heeft gemaakt.

## <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender voor Eindpunt
Microsoft Defender voor Eindpunt verzamelt en slaat gegevens op voor apparaten die zijn Microsoft Managed Desktop voor beheer- en tracerings- en rapportagedoeleinden. Verzamelde gegevens omvatten bestandsgegevens (zoals bestandsnamen, grootte en hashes), procesgegevens (lopende processen, hashes), registergegevens, netwerkverbindingsgegevens en apparaatgegevens (zoals apparaataanduidingen, apparaatnamen en de versie van het besturingssysteem). Zie [Microsoft Defender for Endpoint data storage and privacy for](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect) more information on Microsoft Defender for Endpoint's data collection and storage locations( Microsoft Defender for Endpoint data storage and privacy for more information on Microsoft Defender for Endpoint's data collection and storage locations. 

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365-apps voor ondernemingen 
Microsoft 365-apps voor ondernemingen verzamelt en deelt gegevens met Microsoft Managed Desktop om ervoor te zorgen dat deze apps up-to-date zijn met de nieuwste versie op basis van vooraf gedefinieerde updatekanalen die worden beheerd door Microsoft Managed Desktop. Zie [Microsoft Defender for Endpoint data storage and privacy for](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect) more information on Microsoft 365-apps data collection and storage locations ( Microsoft Defender for Endpoint data storage and privacy for more information on Microsoft 365-apps data collection and storage locations ( Microsoft Defender for Endpoint data storage and privacy for more information on Microsoft 365-apps data collection and storage locations ).

## <a name="major-data-change-notification"></a>Melding over belangrijke gegevenswijziging
Microsoft Managed Desktop volgt een wijzigingsbesturingselementproces zoals beschreven in ons servicecommunicatiekader. We informeren klanten via het Microsoft 365 message center en Microsoft Managed Desktop admin portal van zowel beveiligingsincidenten als belangrijke wijzigingen in de service. Wijzigingen in de typen verzamelde gegevens en de plaats waar deze worden opgeslagen, worden beschouwd als een materiaalwijziging. We bieden minimaal 30 dagen geavanceerde melding van deze wijziging, zoals standaard wordt gebruikt voor Microsoft 365 producten en services. Zie Servicewijzigingen en [communicatie voor meer informatie.](/microsoft-365/managed-desktop/service-description/servicechanges)

## <a name="compliance"></a>Compliance
Microsoft Managed Desktop heeft externe audits uitgevoerd en een uitgebreide reeks nalevingsaanbiedingen verkregen. U vindt meer informatie in Microsoft Managed Desktop [Compliance.](/microsoft-365/managed-desktop/intro/compliance) Auditrapporten zijn beschikbaar om te downloaden op de Microsoft [Service Trust Portal](https://aka.ms/stp), die fungeert als een centrale opslagplaats voor Microsoft Enterprise Online Services. (Microsoft Managed Desktop wordt vermeld in deze documenten onder de categorie 'Monitoring and Management'.) 

## <a name="legal"></a>Juridisch
De privacyverklaring van **Microsoft** aan eindgebruikers van producten die worden geleverd door klanten van de organisatie - De [Privacyverklaring](https://privacy.microsoft.com/privacystatement) van Microsoft meldt eindgebruikers dat wanneer ze zich aanmelden bij Microsoft-producten met een werkaccount, a) hun organisatie hun account kan beheren en beheren (inclusief het beheren van privacy-gerelateerde instellingen) en hun gegevens kan openen en verwerken, en b) Microsoft de gegevens kan verzamelen en verwerken om de service aan de organisatie en eindgebruikers te leveren.
