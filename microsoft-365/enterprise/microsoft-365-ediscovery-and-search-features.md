---
title: Overzicht van Microsoft 365 eDiscovery en zoekfuncties
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: Een overzicht van de eDiscovery-functie en andere zoekfuncties in Microsoft 365 voor controle gebruik en transparantie.
ms.openlocfilehash: ea7b221ab8fe2ff41d089bb344d2dce58002d0f5
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47331857"
---
# <a name="microsoft-365-ediscovery-and-search-features-overview"></a>Overzicht van Microsoft 365 eDiscovery en zoekfuncties 

## <a name="ediscovery"></a>eDiscovery

De eDiscovery-functie biedt een enkele plaats voor beheerders, compliance officers en andere geautoriseerde gebruikers om een uitgebreid onderzoek te doen naar Microsoft 365-gebruikersactiviteit. Beveiligings ambtenaren met de juiste machtigingen Hiermee voert u zoekopdrachten uit en plaatst u ruimten voor inhoud. De zoekresultaten zijn dezelfde resultaten als het zoeken van inhoud, met uitzondering van eDiscovery-aanvragen voor toegepaste wachtruimten. De resultaten van eDiscovery-zoekopdrachten zijn versleuteld voor beveiliging en u kunt geëxporteerde gegevens analyseren met [Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).

## <a name="content-search"></a>Inhoud zoeken

[Content Search](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a) is een eDiscovery-zoekprogramma dat betere schaal-en prestatiefuncties biedt voor eerdere eDiscovery-zoekprogramma's. U kunt inhoud zoeken gebruiken om te zoeken in postvakken, openbare mappen, SharePoint Online-sites en OneDrive voor bedrijven-locaties. Inhoud zoeken ondersteunt grote zoekopdrachten. Er gelden geen limieten voor het aantal postvakken en sites waarop u kunt zoeken. Er gelden ook geen beperkingen voor het aantal zoekopdrachten dat tegelijkertijd wordt uitgevoerd. Wanneer u een zoekopdracht uitvoert, worden het aantal inhoudsbronnen en een geraamd aantal zoekresultaten weergegeven in het detailvenster op de pagina zoeken. U kunt de resultaten bekijken of exporteren naar een lokale computer. Als uw organisatie een Microsoft 365 E5-abonnement heeft, kunt u [de analyseresultaten voorbereiden](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a#prepare) met behulp van de krachtige analysefuncties van [Microsoft 365 Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).

## <a name="audit-log-search"></a>Zoeken in audit logboek

Naast wijzigingen bijhouden in de Microsoft 365-organisatie, kunt u controlerapporten weergeven en auditlogboeken exporteren. Zodra de controle is ingeschakeld als Microsoft 365-Tenant, worden gebruikers-en beheeractiviteiten vastgelegd in Logboeken en kunnen doorzoekbare activiteiten worden uitgevoerd. U kunt bijvoorbeeld logboekregistratie voor Postvak in gebruiken om acties bij te houden die op een postvak zijn uitgevoerd door andere gebruikers dan de eigenaar van het postvak. Compliance officers kunnen de functies voor zoeken en filteren gebruiken voor specifieke activiteiten van gebruikers. U kunt bijvoorbeeld gebruikers identificeren die een specifiek document bekijken of downloaden, als beheerders gebruikers van gebruikers toegang hebben uitgevoerd, of wijzigingen in de Tenant configuratie bekijken in de afgelopen 90 dagen. Zoekresultaten bevatten waardevolle Forensic informatie over specifieke activiteiten van een gebruiker of beheerder. Zie [Zoeken in het auditlogboek](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) voor een beschrijving van de gebruikers-en beheeractiviteiten die zijn opgeslagen in microsoft 365.

Gebeurtenissen van SharePoint Online en OneDrive voor bedrijven worden binnen 30 minuten na de afspraak weergegeven in het logboek. Gebeurtenissen van Exchange Online worden binnen 24 uur na 24 uur weergegeven in de auditlogboeken. Aanmeld gebeurtenissen van Azure AD zijn beschikbaar binnen enkele minuten na een voorval, en andere Directory gebeurtenissen van Azure AD zijn binnen 24 uur na de laatste keer beschikbaar. U kunt ventilatie in de zoekresultaten van het auditlogboek exporteren voor verdere analyse. Maximaal 50.000 vermeldingen uit een zoekopdracht in één auditlogboek worden geëxporteerd. Als u meer items wilt exporteren die deze limiet hebben, moet u het datumbereik verkleinen of meerdere zoekopdrachten in het auditlogboek uitvoeren.

In de volgende tabel vindt u een overzicht van de informatie die wordt weergegeven in activiteitenoverzichten. Zie de [gedetailleerde eigenschappen in het auditlogboek](https://docs.microsoft.com/microsoft-365/compliance/detailed-properties-in-the-office-365-audit-log) voor meer informatie over de eigenschappen die worden verzameld door elke microsoft 365-werkbelasting.

| Eigenschap | Beschrijving |
|----------------|----------------------------------------------------------------------------------------------------------------------|
| Einddatum | Datum en tijd van de gebeurtenis |
| Gebruiker | Gebruiker die de actie heeft uitgevoerd |
| ClientIP | IPv4-of IPv6-adres van het apparaat dat bij het registreren van de activiteit is gebruikt. |
| CreationTime | De datum en tijd in Coordinated Universal Time (UTC) toen de gebruiker de activiteit uitvoerde. |
| Source | Hiermee wordt aangegeven dat er een gebeurtenis heeft plaatsgevonden. Mogelijke waarden zijn SharePoint en ObjectModel. |
| ID | ID van het rapportitem. De ID heeft een unieke aanduiding voor het rapport. |
| Opdracht | Naam van de gebruiker of activiteit, die overeenkomt met de waarde die is geselecteerd in de weergave resultaten van deze gebruikersactiviteit. |
| OrganizationId | GUID voor de Microsoft 365-service van de organisatie waarbij de gebeurtenis plaatsvond. |
| User | Informatie over de browser van de gebruiker, weergegeven in de browser. |
| Schreven | De gebruiker die de actie heeft uitgevoerd (opgegeven in de eigenschap Operation) waardoor de record werd vastgelegd. |
| UserType | Het type gebruiker dat de bewerking heeft uitgevoerd. Met de volgende waarden wordt het gebruikerstype aangegeven. |
|  | 0 een gewone gebruiker aangeeft. |
|  | 2 geeft een beheerder aan in uw Microsoft 365-organisatie. |
|  | 3 geeft een Microsoft datacenter-beheerder of Datacenter-systeemaccount aan. |
| Minder | Microsoft 365-service waarop de activiteit heeft plaatsgevonden. Mogelijke waarden voor deze eigenschap zijn: |
|  | Exchange Online |
|  | SharePoint Online |
|  | OneDrive voor Bedrijven |
|  | Azure Active Directory-rapporten |

Voor uitgebreide stappen voor het zoeken naar Microsoft 365-controlelogboeken raadpleegt u [het auditlogboek doorzoeken in het beveiligings & nalevings centrum](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

## <a name="search-unified-audit-log"></a>Uniform auditlogboek zoeken

Gebruik de zoekfunctie voor audit Logboeken om in het Unified audit logboek te zoeken. Microsoft 365 biedt ook de mogelijkheid om te zoeken in dit logboek met Remote PowerShell. Met de [cmdlet Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/Search-UnifiedAuditLog?view=exchange-ps) in Exchange Online PowerShell wordt het geïntegreerde auditlogboek van gebeurtenissen in verband met gebruikers bewerkingen in Exchange Online, SharePoint Online, OneDrive voor bedrijven en Azure AD gezocht. 

U kunt alle gebeurtenissen in een bepaald datumbereik zoeken, of u kunt de resultaten filteren op basis van bepaalde criteria, zoals een specifieke actie, de gebruiker die de actie heeft uitgevoerd of het doelobject. Beheerders kunnen met maximaal drie tegelijk PowerShell-sessies van Exchange Online gebruiken om grote hoeveelheden zoekopdrachten op te splitsen.