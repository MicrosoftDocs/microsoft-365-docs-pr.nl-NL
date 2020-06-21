---
title: Microsoft 365 security roadmap - Topprioriteiten
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: 'De belangrijkste aanbevelingen van het cyberbeveiligingsteam van Microsoft voor het implementeren van beveiligingsmogelijkheden om uw Microsoft 365-omgeving te beschermen. '
ms.openlocfilehash: 968d2c5a2e8954df97fb884da6fab967b7cc806b
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726464"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Beveiligingsroadmap - Topprioriteiten voor de eerste 30 dagen, 90 dagen en daarna

Dit artikel bevat de belangrijkste aanbevelingen van het cyberbeveiligingsteam van Microsoft voor het implementeren van beveiligingsmogelijkheden om uw Microsoft 365-omgeving te beschermen. Dit artikel is aangepast van een Microsoft Ignite sessie - [Secure Microsoft 365 als een cybersecurity pro: Topprioriteiten voor de eerste 30 dagen, 90 dagen, en daarna](https://www.youtube.com/watch?v=luignzNyR-o). Deze sessie werd ontwikkeld en gepresenteerd door Mark Simos en Matt Kemelhar, Enterprise Cybersecurity Architects.

In dit artikel:

- [Routekaartresultaten](security-roadmap.md#Roadmap)

- [30 dagen — krachtige snelle overwinningen](security-roadmap.md#Thirdaydays)

- [90 dagen — betere beveiligingen](security-roadmap.md#Ninetydays)

- [Buiten](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Routekaartresultaten
<a name="Roadmap"> </a>

Deze roadmap aanbevelingen worden gefaseerd in drie fasen in een logische volgorde met de volgende doelen.

|||
|:-----|:-----|
| |Resultaten
|30 dagen|Snelle configuratie:  <br/> * Basisbeheerbeveiligingen  <br/> * Logging en analytics  <br/> * Basisidentiteitsbescherming  <br/> Tenantconfiguratie  <br/>  Belanghebbenden voorbereiden|
|90 dagen|Geavanceerde beveiligingen:  <br/> * Admin accounts  <br/>  * &amp; Gebruikersaccounts voor gegevens  <br/>  Inzicht in de behoeften van compliance, bedreigingen en gebruikers  <br/>  Standaardbeleid en -beveiligingen aanpassen en implementeren|
|Buiten|Belangrijke beleidsregels en besturingselementen aanpassen en verfijnen  <br/> Beschermingen uitbreiden tot on-premises afhankelijkheden  <br/> Integreren met zakelijke en beveiligingsprocessen (juridische, insider threat, etc.)|



## <a name="30-days--powerful-quick-wins"></a>30 dagen — krachtige snelle overwinningen
<a name="Thirdaydays"> </a>

Deze taken kunnen snel worden uitgevoerd en hebben een lage impact voor gebruikers.

|||
|:-----|:-----|
|Gebied|Taken|
|Beveiligingsbeheer|* Controleer Secure Score en let op uw huidige score ( [https://securescore.office.com](https://securescore.office.com) ).  <br/>  * Schakel controlelogboekregistratie in voor Office 365. Zie [Zoeken in het controlelogboek](../../compliance/search-the-audit-log-in-security-and-compliance.md).  <br/> * [Microsoft 365 configureren voor meer beveiliging](tenant-wide-setup-for-increased-security.md) .  <br/>  * Controleer regelmatig dashboards en rapporten in het Microsoft 365-beveiligingscentrum en Cloud App Security.|
|Bedreigingsbeveiliging|[Verbind Microsoft 365 met Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) om te beginnen met het controleren met behulp van het standaardbeleid voor bedreigingsdetectie voor afwijkend gedrag. Het duurt zeven dagen om een basislijn voor anomaliedetectie te bouwen.  <br><br/>  Implementeer de beveiliging voor beheerdersaccounts:  <br/> * Gebruik speciale beheerdersaccounts voor beheerdersactiviteit.  <br/>  * Afdwingen multi-factor authenticatie (MFA) voor admin accounts.  <br/>  * Gebruik een [zeer beveiligd Windows 10-apparaat](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) voor beheerdersactiviteit.|
|Identiteits- en toegangsbeheer|* [Azure Active Directory-identiteitsbeveiliging inschakelen.](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)  <br/> * Voor federatieve identiteitsomgevingen u de beveiliging van uw account afdwingen (wachtwoordlengte, leeftijd, complexiteit, enz.).|
|Informatiebescherming| Bekijk voorbeelden aanbevelingen voor informatiebescherming. Informatiebescherming vereist coördinatie in uw organisatie. Aan de slag met de volgende informatiebronnen:  <br/> * [Office 365-informatiebescherming voor GDPR](https://aka.ms/o365gdpr) <br/> * [Teams configureren met drie beschermingsniveaus](../../solutions/configure-teams-three-tiers-protection.md) (waaronder delen, classificatie, preventie van gegevensverlies en Azure-informatiebeveiliging)|

## <a name="90-days--enhanced-protections"></a>90 dagen — betere beveiligingen
<a name="Ninetydays"> </a>

Deze taken nemen een beetje meer tijd om te plannen en uit te voeren, maar sterk verhogen van uw veiligheid houding.

|||
|:-----|:-----|
|Gebied|Taak|
|Beveiligingsbeheer|* Controleer Secure Score voor aanbevolen acties voor uw omgeving ( [https://securescore.office.com](https://securescore.office.com) ).  <br/>  * Blijf regelmatig dashboards en rapporten bekijken in het Microsoft 365-beveiligingscentrum, Cloud App Security en SIEM-hulpprogramma's. <br/> * Zoek naar en implementeer software-updates. <br/> * Voer aanval simulaties voor spear-phishing, wachtwoord-spray, en brute-force wachtwoord aanvallen met behulp van [Attack Simulator](attack-simulator.md) (inbegrepen bij [Office 365 Threat Intelligence](office-365-ti.md)).  <br/> * Zoek naar risico's voor delen door de ingebouwde rapporten in Cloud App Security te bekijken (op het tabblad Onderzoeken). <br/> * Controleer [de nalevingsscore](https://docs.microsoft.com/microsoft-365/compliance/compliance-score) om de status te controleren op regelgeving die van toepassing is op uw organisatie (zoals GDPR, NIST 800-171).|
|Bedreigingsbeveiliging| Implementeer verbeterde beveiligingen voor beheerdersaccounts: <br/> * [Configureer Privileged Access Workstations (PAWs)](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) voor beheerdersactiviteit. <br/> * Azure [AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)configureren . <br/> * Configureer een SIEM-hulpprogramma (Security Information and Event Management) om logboekgegevens te verzamelen van Office 365, Cloud App Security en andere services, waaronder AD FS. Het controlelogboek slaat gegevens slechts 90 dagen op. Door deze gegevens vast te leggen in siem-tool u gegevens voor een langere periode opslaan.|
|Identiteits- en toegangsbeheer|* MFA inschakelen en afdwingen voor alle gebruikers. <br/> * Implementeer een reeks [voorwaardelijke toegang en gerelateerd beleid](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations). |
|Informatiebescherming| Het beleid inzake informatiebescherming aanpassen en implementeren. Deze bronnen bevatten voorbeelden: <br/> * [Office 365-informatiebescherming voor GDPR](https://aka.ms/o365gdpr) <br/> * [Teams configureren met drie beschermingsniveaus](../../solutions/configure-teams-three-tiers-protection.md) <br/> <br> Gebruik beleid voor het voorkomen van gegevensverlies en monitoringtools in Microsoft 365 voor gegevens die zijn opgeslagen in Microsoft 365 (in plaats van cloud-appbeveiliging). <br><br>Gebruik Cloud App Security met Microsoft 365 voor geavanceerde waarschuwingsfuncties (met uitzondering van preventie van gegevensverlies).|

## <a name="beyond"></a>Buiten
<a name="Beyond"> </a>

Dit zijn belangrijke beveiligingsmaatregelen die voortbouwen op eerdere werkzaamheden.

|||
|:-----|:-----|
|Gebied|Taak|
|Beveiligingsbeheer|* Doorgaan met het plannen van volgende acties met behulp van Secure Score ( [https://securescore.office.com](https://securescore.office.com) ). <br/> * Blijf regelmatig dashboards en rapporten bekijken in het Microsoft 365-beveiligingscentrum, Cloud App Security en SIEM-hulpprogramma's. <br/> * Blijven zoeken naar en implementeren van software-updates. <br/> * Integreer eDiscovery in uw juridische en bedreigingsresponsprocessen.|
|Bedreigingsbeveiliging|* Implementeer [Secure Privileged Access](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) voor identiteitscomponenten on premises (AD, AD FS). <br/> * Gebruik Cloud App Security om te controleren op insider bedreigingen. <br/> * Ontdek schaduw IT SaaS-gebruik met behulp van Cloud App Security.|
|Identiteits- en toegangsbeheer|* Verfijn beleid en operationele processen. <br/> * Gebruik Azure AD Identity Protection om insiderbedreigingen te identificeren.|
|Informatiebescherming| Het beleid voor informatiebescherming verfijnen: <br/> * Microsoft 365- en Office 365-gevoeligheidslabels en gegevensverliespreventie (DLP) of Azure Information Protection. <br/> * Cloud App Beveiligingsbeleid en waarschuwingen.|

Zie ook: [Hoe snelle cyberaanvallen zoals Petya en WannaCrypt te verzachten.](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)
