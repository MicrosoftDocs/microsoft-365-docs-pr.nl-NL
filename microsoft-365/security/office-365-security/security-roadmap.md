---
title: Microsoft 365-beveiligings roadmap - Topprioriteiten
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: De belangrijkste aanbevelingen van het cyberbeveiligingsteam van Microsoft voor het implementeren van beveiligingsmogelijkheden om uw Microsoft 365-omgeving te beschermen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bd86262cd36d9482cd9a54e7fd7c336a6f0700dd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929262"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Routekaart voor beveiliging : topprioriteiten voor de eerste 30 dagen, 90 dagen en daarna

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Dit artikel bevat de belangrijkste aanbevelingen van het cyberbeveiligingsteam van Microsoft voor het implementeren van beveiligingsfuncties om uw Microsoft 365-omgeving te beschermen. Dit artikel is aangepast aan een Microsoft Ignite-sessie: Beveilig Microsoft 365 als een cyberbeveiligingsprof: Topprioriteiten voor de eerste [30 dagen, 90 dagen en daarna.](https://www.youtube.com/watch?v=luignzNyR-o) Deze sessie is ontwikkeld en gepresenteerd door Mark Simos en Matt Kemelhar, Enterprise Cyberbeveiligingsarchitecten.

In dit artikel:

- [Resultaten van routekaart](security-roadmap.md#Roadmap)
- [30 dagen: krachtige snelle overwinningen](security-roadmap.md#Thirdaydays)
- [90 dagen : verbeterde beveiliging](security-roadmap.md#Ninetydays)
- [Voorbij](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Resultaten van routekaart
<a name="Roadmap"> </a>

Deze roadmapaanbevelingen worden gefaseerd in drie fasen in een logische volgorde met de volgende doelen.

****

|Tijdsbestek|Resultaten|
|---|---|
|30 dagen|Snelle configuratie: <ul><li>Basisbeheerdersbescherming.</li><li>Logboekregistratie en analyse.</li><li>Basisidentiteitsbeveiliging.</li></ul> <p> Tenantconfiguratie. <p> Bereid belanghebbenden voor.|
|90 dagen|Geavanceerde beveiligingen: <ul><li>Beheerdersaccounts.</li><li>Gegevens- en gebruikersaccounts.</li></ul> <p> Zichtbaarheid van compliance- en bedreigings- en gebruikersbehoeften. <p> Standaardbeleid en -beveiliging aanpassen en implementeren.|
|Voorbij|Pas belangrijke beleidsregels en besturingselementen aan en verfijn deze. <p> Beveiliging uitbreiden naar on-premises afhankelijkheden. <p> Integreren met bedrijfsprocessen en beveiligingsprocessen (juridische, insider-bedreiging, enzovoort).|
|

## <a name="30-days--powerful-quick-wins"></a>30 dagen: krachtige snelle overwinningen
<a name="Thirdaydays"> </a>

Deze taken kunnen snel worden uitgevoerd en hebben weinig invloed op gebruikers.

****

|Gebied|Taken|
|---|---|
|Beveiligingsbeheer|<ul><li>Controleer Secure Score en noteer uw huidige score <https://securescore.office.com> ().</li><li>Schakel auditlogregistratie voor Office 365 in. Zie [Het auditlogboek doorzoeken.](../../compliance/search-the-audit-log-in-security-and-compliance.md)</li><li>[Configureer Microsoft 365 voor meer beveiliging.](tenant-wide-setup-for-increased-security.md)</li><li>Controleer regelmatig dashboards en rapporten in het Microsoft 365-beveiligingscentrum en Cloud App-beveiliging.</li></ul>|
|Bedreigingsbeveiliging|[Verbind Microsoft 365 met Microsoft Cloud App Security](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) om te gaan controleren met behulp van het standaardbeleid voor bedreigingsdetectie voor afwijkende gedragingen. Het duurt zeven dagen om een basislijn voor afwijkingsdetectie te maken. <p>  Beveiliging implementeren voor beheerdersaccounts:<ul><li>Gebruik speciale beheerdersaccounts voor beheerdersactiviteiten.</li><li>Meervoudige verificatie (MFA) afdwingen voor beheerdersaccounts.</li><li>Gebruik een [zeer veilig Windows 10-apparaat voor](/windows-hardware/design/device-experiences/oem-highly-secure) beheerdersactiviteiten.</li></ul>|
|Identiteits- en toegangsbeheer|<ul><li>[Azure Active Directory Identity Protection inschakelen.](/azure/active-directory/active-directory-identityprotection-enable)</li><li>Voor federatief identiteitsomgevingen kunt u accountbeveiliging afdwingen (wachtwoordlengte, leeftijd, complexiteit, enzovoort).</li></ul>|
|Gegevensbescherming|Bekijk voorbeeldaanbevelingen voor informatiebeveiliging. Informatiebeveiliging vereist coördinatie binnen uw organisatie. Aan de slag met de volgende informatiebronnen:<ul><li>[Office 365 Information Protection voor de AVG](/compliance/regulatory/gdpr)</li><li>[Teams configureren met drie beveiligingslagen](../../solutions/configure-teams-three-tiers-protection.md) (inclusief delen, classificatie, preventie van gegevensverlies en Azure Information Protection)</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 dagen : verbeterde beveiliging
<a name="Ninetydays"> </a>

Het plannen en implementeren van deze taken duurt iets langer, maar verhoogt uw beveiligingspositie sterk.

****

|Gebied|Taak|
|---|---|
|Beveiligingsbeheer|<ul><li>Controleer Secure Score voor aanbevolen acties voor uw omgeving ( <https://securescore.office.com> ).</li><li>Blijf regelmatig dashboards en rapporten bekijken in het Microsoft 365-beveiligingscentrum, cloud-app-beveiliging en SIEM-hulpprogramma's.</li><li>Zoek naar en implementeert software-updates.</li><li>Gebruik Attack [Simulator](attack-simulator.md) (inbegrepen bij [Office 365 Threat Intelligence)](office-365-ti.md)om aanvalssimulaties uit te voeren voor phishing- en wachtwoordintelligentie.</li><li>Zoek naar risico's voor delen door de ingebouwde rapporten in Cloud App Security te bekijken (op het tabblad Onderzoeken).</li><li>Controleer [Compliance manager](../../compliance/compliance-manager.md) om de status te controleren voor regelgeving die van toepassing is op uw organisatie (zoals AVG, NIST 800-171).</li></ul>|
|Bedreigingsbeveiliging|Verbeterde beveiligingen implementeren voor beheerdersaccounts: <ul><li>Configureer [Privileged Access Workstations](/security/compass/privileged-access-devices) (PAWs) voor beheerdersactiviteiten.</li><li>ConfigureEr [Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure).</li><li>Configureer een hulpprogramma voor beveiligingsgegevens en gebeurtenisbeheer (SIEM) om logboekregistratiegegevens te verzamelen van Office 365, Cloud App Security en andere services, waaronder AD FS. Het auditlogboek slaat gegevens slechts 90 dagen op. Door deze gegevens vast te leggen in het SIEM-hulpprogramma kunt u gegevens voor een langere periode opslaan.</li></ul>|
|Identiteits- en toegangsbeheer|<ul><li>MFA in- en afdwingen voor alle gebruikers.</li><li>Een set voorwaardelijke [toegang en verwante beleidsregels implementeren.](microsoft-365-policies-configurations.md)</li></ul>|
|Gegevensbescherming| Beleid voor informatiebeveiliging aanpassen en implementeren. Deze bronnen bevatten voorbeelden: <ul><li>[Office 365 Information Protection voor de AVG](/compliance/regulatory/gdpr)</li><li>[Teams met drie beschermingsniveaus configureren](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Gebruik beleid voor preventie van gegevensverlies en monitoringhulpmiddelen in Microsoft 365 voor gegevens die zijn opgeslagen in Microsoft 365 (in plaats van cloud-appbeveiliging). <p> Gebruik Cloud App Security met Microsoft 365 voor geavanceerde waarschuwingsfuncties (andere dan preventie van gegevensverlies).|
|

## <a name="beyond"></a>Voorbij
<a name="Beyond"> </a>

Dit zijn belangrijke beveiligingsmaatregelen die voortbouwen op eerdere werkzaamheden.

****

|Gebied|Taak|
|---|---|
|Beveiligingsbeheer|<ul><li>Ga door met het plannen van volgende acties met Secure Score <https://securescore.office.com> ().</li><li>Blijf regelmatig dashboards en rapporten bekijken in het Microsoft 365-beveiligingscentrum, cloud-app-beveiliging en SIEM-hulpprogramma's.</li><li>Blijf software-updates zoeken en implementeren.</li><li>Integreer eDiscovery in uw processen voor juridische en bedreigingsreacties.</li></ul>|
|Bedreigingsbeveiliging|<ul><li>Secure [Privileged Access](/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) implementeren voor identiteitsonderdelen on-premises (AD, AD FS).</li><li>Gebruik Cloud App Security om te controleren op insider-bedreigingen.</li><li>Ontdek schaduw-IT SaaS-gebruik met cloud-app-beveiliging.</li></ul>|
|Identiteits- en toegangsbeheer|<ul><li>Beleid en operationele processen verfijnen.</li><li>Gebruik Azure AD Identity Protection om insiderbedreigingen te identificeren.</li></ul>|
|Gegevensbescherming|Beleid voor informatiebeveiliging verfijnen: <ul><li>Gevoeligheidslabels voor Microsoft 365 en Office 365 en preventie van gegevensverlies (DLP) of Azure Information Protection.</li><li>Beveiligingsbeleid en waarschuwingen voor cloud-apps.</li></ul>|
|

Zie ook: [Snelle cyberaanvallen beperken, zoals Petya en WannaCrypt.](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)