---
title: Aan de slag met bewaarbeleid en retentielabels
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Bent u klaar voor het implementeren van bewaarbeleid en bewaarlabels om de gegevens van uw organisatie te bepalen, maar weet u niet zeker waar u moet beginnen? Lees wat praktische tips om aan de slag te gaan.
ms.openlocfilehash: bd3ed5e354ee80831cb1af073b6da6f277418b51
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689035"
---
# <a name="get-started-with-retention-policies-and-retention-labels"></a>Aan de slag met bewaarbeleid en retentielabels

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Bent u klaar om de gegevens van uw organisatie te gaan beheren door de inhoud die u nodig hebt te behouden en de inhoud die u niet hebt te verwijderen? Gebruik de volgende tips om aan de slag te gaan:

1. **Lees hoe bewaarbeleid** in Microsoft 365 werkt en bepaal vervolgens of u gebruik moet maken van bewaarbeleid of bewaarlabels, of een combinatie: [Meer informatie over bewaren](retention.md)

2. **Bepaal welke bewaarinstellingen en -acties** zijn vereist door de beleidsregels van uw organisatie of branchevoorschriften.
    
    Als onderdeel van deze evaluatie kunt u bepalen of u het [beheer van records](records-management.md) gebruiken.

3. **Maak bewaarbeleid en labels voor bewaren**, op basis van de instellingen en acties die u hebt geïdentificeerd.
    
    Voor labels voor bewaren is het misschien handig om een [bestandsplan](file-plan-manager.md) te definiëeren om uw bewaarlabels in een werkblad te definiëren en verfijnen. Importeer vervolgens het spreadsheet om uw labels te maken.
    
3. **Uw retentielabels publiceren en toepassen**. Retentiebeleid is ontworpen om in te stellen en te vergeten, maar retentielabels zijn herbruikbare bouwstenen die kunnen worden gebruikt in meerdere beleidsregels en kunnen worden opgenomen in gebruikerswerkstromen. Bekijk de lijst met [veelvoorkomende scenario's](#common-scenarios-for-retention-policies-and-retention-labels) om te bepalen hoe labels voor bewaarbeleid kunnen worden gebruikt. 

## <a name="subscription-and-licensing-requirements-for-retention-policies-and-retention-labels"></a>Abonnements- en licentievereisten voor bewaarbeleid en retentielabels

Een aantal verschillende abonnementen ondersteunen retentiebeleid en -labels en de licentievereisten voor gebruikers zijn afhankelijk van de functies die u gebruikt.

Zie de [Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) om de opties te zien voor de licentieverlening aan uw gebruikers om voordeel te halen uit de functies van Microsoft 365-compliance. Zie voor recordbeheer de sectie [Records Management](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) en een gerelateerde PDF- of Excel-download voor licentievereisten op functieniveau.

## <a name="permissions-required-to-create-and-manage-retention-policies-and-retention-labels"></a>Vereiste machtigingen om bewaarbeleid en bewaarlabels te maken en te beheren

Leden van uw nalevingsteam die bewaarbeleidsregels en bewaarlabels maken en beheren, hebben machtigingen nodig voor het [compliancecentrum van Microsoft 365](https://compliance.microsoft.com/). Standaard heeft de tenantbeheerder (globale beheerder) toegang tot deze locatie en kan deze compliance officers en andere personen toegang verlenen zonder hen alle machtigingen van een tenantbeheerder te geven. Als u machtigingen wilt verlenen voor dit beperkte beheer, raden we u aan gebruikers toe te voegen aan de beheerdersrolgroep **Compliancebeheerder**.

U kunt ook deze standaard rol gebruiken en de rollengroep **Retentiebeheer** aan deze groep toevoegen. Voor een alleen-lezenrol gebruikt u **View-Only Retention Management**. 

Zie [Machtigingen in het Beveiligings- en compliancecentrum](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center) voor meer informatie over rolgroepen en rollen.

Zie [Gebruikers toegang geven tot het Beveiligings- en compliancecentrum](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md) voor instructies om gebruikers aan rolgroepen toe te voegen en rollen toe te wijzen.

Deze machtigingen zijn alleen vereist om retentielabels te maken, te configureren en toe te passen. De persoon die deze beleidsregels labels configureert, heeft geen toegang tot de inhoud nodig.

## <a name="common-scenarios-for-retention-policies-and-retention-labels"></a>Veelvoorkomende scenario's voor bewaarbeleid en retentielabels

Gebruik de volgende tabel om uw zakelijke vereisten toe te passen op retentiescenario's die worden ondersteund door retentiebeheer.

|Ik wil het volgende doen|Documentatie|
|----------------|---------------|
|Efficiënt acties voor behouden en verwijderen instellen door de Microsoft 365-service: <br />- Exchange:  <br />- SharePoint  <br />- OneDrive  <br />Microsoft 365 Groepen <br />Skype voor Bedrijven  <br />Microsoft Teams <br />- Yammer-netwerk |[Bewaarbeleid maken en configureren](create-retention-policies.md)|
|Beheerders en gebruikers handmatig acties voor documenten en e-mailberichten laten toepassen en verwijderen: <br />-  SharePoint <br />- OneDrive <br />- Outlook en Outlook op het web|[Retentielabels maken en deze toepassen in apps](create-apply-retention-labels.md)|
|Sitebeheerders de standaardacties laten instellen voor het bewaren en verwijderen van alle inhoud in een SharePoint-bibliotheek, -map of -documentenset|[Retentielabels maken en deze toepassen in apps](create-apply-retention-labels.md)|
|Gebruikers automatisch acties laten toepassen voor het bewaren en verwijderen op e-mailberichten met behulp van Outlook-regels|[Retentielabels maken en deze toepassen in apps](create-apply-retention-labels.md)|
|Beheerders acties laten toepassen op een model voor documentbegrip en deze verwijderen, zodat deze automatisch worden toegepast op geïdentificeerde documenten in een SharePoint-bibliotheek|[Retentielabels maken en deze toepassen in apps](create-apply-retention-labels.md)|
|Automatisch acties voor bewaren en verwijderen toepassen op documenten en e-mailberichten |[Een retentielabel automatisch toepassen op inhoud](apply-retention-labels-automatically.md)|
|De retentieperiode starten wanneer een gebeurtenis plaatsvindt, zoals:  <br />- Werknemers verlaten de organisatie <br />- Contracten verlopen <br />- Einde productleven| [Retentie starten als zich een gebeurtenis voordoet](event-driven-retention.md)|
|Wijzigingen in beleid beperken om te voldoen aan wettelijke vereisten of beveiliging tegen malafide beheerders| [Behoudvergrendeling gebruiken om wijzigingen in retentiebeleid en retentielabelbeleid te beperken](retention-preservation-lock.md)
|Zorg ervoor dat iemand beoordeelt en goedkeurt voordat inhoud wordt verwijderd aan het einde van de retentieperiode|[Verwijderingsbeoordelingen](disposition.md#disposition-reviews) |
| Controleren hoe en waar instellingen voor behouden en verwijderen op items worden toegepast | [Controleren van retentielabels](retention.md#monitoring-retention-labels) |
|Eén oplossing voor recordbeheer gebruiken voor documenten en e-mailberichten |[Meer informatie over Records Management](records-management.md) |

Als u labels voor bewaarbeleid gebruikt voor recordbeheer, zijn er extra scenario's die uniek zijn voor het bewaren van labels die inhoud markeren als record. Zie [Veelvoorkomende scenario's voor recordbeheer](get-started-with-records-management.md#common-scenarios-for-records-management)

## <a name="end-user-documentation-for-retention"></a>Documentatie voor eindgebruikers voor retentie

De meeste bewaarbeleidsregels werken op de achtergrond zonder tussenkomst van de gebruiker en hebben dus weinig documentatie voor gebruikers nodig. Bewaarbeleid voor Teams informeert gebruikers wanneer hun berichten zijn verwijderd met een koppeling naar [Teams over bewaarbeleidsregels](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).

Aangezien retentielabels een visuele aanwezigheid hebben in uw  Microsoft 365-apps, zorg ervoor dat u richtlijnen biedt voor eindgebruikers en uw helpdesk voordat u retentielabels implementeert in uw productienetwerk. Om gebruikers te helpen bij het toepassen van retentielabels in SharePoint en OneDrive, raadpleeg [Retentielabels toepassen op bestanden in SharePoint of OneDrive](https://support.microsoft.com/office/apply-retention-labels-to-files-in-sharepoint-or-onedrive-11a6835b-ec9f-40db-8aca-6f5ef18132df). 

De meest effectieve documentatie voor eindgebruikers zijn echter aangepaste richtlijnen en instructies die u geeft voor de door u gekozen namen en configuraties van retentielabels. Bekijk de volgende pagina en downloads die u kunt gebruiken voor het trainen van gebruikers: [Eindgebruikerstraining voor Retentielabels](https://microsoft.github.io/ComplianceCxE/enduser/retention/).