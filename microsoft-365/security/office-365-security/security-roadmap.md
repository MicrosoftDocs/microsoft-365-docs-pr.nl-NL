---
title: Beveiligingsroadmap - Topprioriteiten voor de eerste 30 dagen, 90 dagen en daarna
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
ms.openlocfilehash: f00cf7c63e84f19ac2cae080adb87209b32d3012
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633723"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Beveiligingsroadmap - Topprioriteiten voor de eerste 30 dagen, 90 dagen en daarna

Dit artikel bevat de belangrijkste aanbevelingen van het cyberbeveiligingsteam van Microsoft voor het implementeren van beveiligingsmogelijkheden om uw Microsoft 365-omgeving te beschermen. Dit artikel is aangepast van een Microsoft Ignite-sessie - [Beveilig Microsoft 365 als een cyberbeveiligingspro: topprioriteiten voor de eerste 30 dagen, 90 dagen en daarna.](https://www.youtube.com/watch?v=luignzNyR-o) Deze sessie werd ontwikkeld en gepresenteerd door Mark Simos en Matt Kemelhar, Enterprise Cybersecurity Architects.

In dit artikel:

- [Resultaten van routekaarten](security-roadmap.md#Roadmap)

- [30 dagen - krachtige quick wins](security-roadmap.md#Thirdaydays)

- [90 dagen — verbeterde beveiligingen](security-roadmap.md#Ninetydays)

- [Buiten](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Resultaten van routekaarten
<a name="Roadmap"> </a>

Deze roadmap aanbevelingen worden gefaseerd in drie fasen in een logische volgorde met de volgende doelstellingen.

|||
|:-----|:-----|
| |Resultaten
|30 dagen|Snelle configuratie:  <br/> * Basisbeheerdersbeveiligingen  <br/> * Logging en analytics  <br/> * Basisidentiteitsbescherming  <br/> Tenantconfiguratie  <br/>  Belanghebbenden voorbereiden|
|90 dagen|Geavanceerde beveiligingen:  <br/> * Admin-accounts  <br/>  * &amp; Gegevens gebruikersaccounts  <br/>  Inzicht in compliance, bedreiging en gebruikersbehoeften  <br/>  Standaardbeleid en -beveiligingen aanpassen en implementeren|
|Buiten|Belangrijke beleidsregels en besturingselementen aanpassen en verfijnen  <br/> Beveiligingen uitbreiden naar on-premises afhankelijkheden  <br/> Integreren met bedrijfs- en beveiligingsprocessen (juridische, insiderthreat, enz.)|



## <a name="30-days--powerful-quick-wins"></a>30 dagen - krachtige quick wins
<a name="Thirdaydays"> </a>

Deze taken kunnen snel worden uitgevoerd en hebben een lage impact op gebruikers.

|||
|:-----|:-----|
|Gebied|Taken|
|Beveiligingsbeheer|* Check Secure Score en kennis[https://securescore.office.com](https://securescore.office.com)te nemen van uw huidige score ( ).  <br/>  * Schakel controlelogboekregistratie in voor Office 365. Zie [Het controlelogboek doorzoeken](../../compliance/search-the-audit-log-in-security-and-compliance.md).  <br/> * [Microsoft 365 configureren voor meer beveiliging.](tenant-wide-setup-for-increased-security.md)  <br/>  * Bekijk regelmatig dashboards en rapporten in het Microsoft 365-beveiligingscentrum en cloud-appbeveiliging.|
|Bedreigingsbeveiliging|[Verbind Microsoft 365 met Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) om te beginnen met het controleren met behulp van het standaardbeleid voor bedreigingsdetectie voor afwijkend gedrag. Het duurt zeven dagen om een basislijn voor anomaliedetectie te bouwen.  <br><br/>  Implementeer beveiliging voor beheerdersaccounts:  <br/> * Gebruik speciale beheerdersaccounts voor beheerdersactiviteiten.  <br/>  * Multi-factor authenticatie (MFA) afdwingen voor beheerdersaccounts.  <br/>  * Gebruik een [zeer veilig Windows 10-apparaat](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) voor beheerdersactiviteiten.|
|Identiteits- en toegangsbeheer|* [Azure Active Directory Identity Protection inschakelen](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).  <br/> * Voor federatieve identiteitsomgevingen u accountbeveiliging afdwingen (wachtwoordlengte, leeftijd, complexiteit, enz.).|
|Gegevensbescherming| Bekijk voorbeeld aanbevelingen voor informatiebescherming. Informatiebescherming vereist coördinatie binnen uw organisatie. Aan de slag met de volgende informatiebronnen:  <br/> * [Informatiebeveiliging van Office 365 voor GDPR](https://aka.ms/o365gdpr) <br/> * [Beveiligde SharePoint Online-sites en -bestanden](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) (inclusief delen, classificatie, preventie van gegevensverlies en Azure Information Protection)|

## <a name="90-days--enhanced-protections"></a>90 dagen — verbeterde beveiligingen
<a name="Ninetydays"> </a>

Deze taken nemen een beetje meer tijd om te plannen en uit te voeren, maar sterk verhogen van uw veiligheid houding.

|||
|:-----|:-----|
|Gebied|Taak|
|Beveiligingsbeheer|* Controleer Secure Score voor aanbevolen[https://securescore.office.com](https://securescore.office.com)acties voor uw omgeving ( ).  <br/>  * Blijf regelmatig dashboards en rapporten bekijken in het Microsoft 365-beveiligingscentrum, cloud-appbeveiliging en SIEM-hulpprogramma's. <br/> * Zoek naar en implementeer software-updates. <br/> * Voer aanvalssimulaties uit voor spear-phishing, wachtwoordspray en brute-force wachtwoordaanvallen met [Attack Simulator](attack-simulator.md) (inbegrepen bij [Office 365 Threat Intelligence).](office-365-ti.md)  <br/> * Zoek naar risico's voor delen door de ingebouwde rapporten in Cloud App Security te bekijken (op het tabblad Onderzoeken). <br/> * Controleer [de nalevingsscore](https://docs.microsoft.com/microsoft-365/compliance/compliance-score) om de status te controleren op regelgeving die van toepassing is op uw organisatie (zoals GDPR, NIST 800-171).|
|Bedreigingsbeveiliging| Implementeer verbeterde beveiligingen voor beheerdersaccounts: <br/> * [Configureer Privileged Access Workstations](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) voor beheerdersactiviteiten. <br/> * Configureer [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure). <br/> * Configureer een SIEM-tool (Security Information and Event Management) om logboekgegevens te verzamelen van Office 365, Cloud App Security en andere services, waaronder AD FS. Het controlelogboek slaat gegevens op voor slechts 90 dagen. Als u deze gegevens vastlegt in siem-tool, u gegevens voor een langere periode opslaan.|
|Identiteits- en toegangsbeheer|* MFA inschakelen en afdwingen voor alle gebruikers. <br/> * Implementeren van een set van [voorwaardelijke toegang en aanverwante beleid](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations). |
|Gegevensbescherming| Het beleid inzake informatiebescherming aanpassen en implementeren. Deze bronnen bevatten voorbeelden: <br/> * [Informatiebeveiliging van Office 365 voor GDPR](https://aka.ms/o365gdpr) <br/> * [SharePoint Online-sites en -bestanden beveiligen](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) <br/> <br> Gebruik beleid voor het voorkomen van gegevensverlies en bewakingstools in Microsoft 365 voor gegevens die zijn opgeslagen in Microsoft 365 (in plaats van cloud-appbeveiliging). <br><br>Gebruik Cloud App Security met Microsoft 365 voor geavanceerde waarschuwingsfuncties (andere dan preventie van gegevensverlies).|

## <a name="beyond"></a>Buiten
<a name="Beyond"> </a>

Dit zijn belangrijke beveiligingsmaatregelen die voortbouwen op eerder werk.

|||
|:-----|:-----|
|Gebied|Taak|
|Beveiligingsbeheer|* Doorgaan met het plannen [https://securescore.office.com](https://securescore.office.com)van volgende acties met behulp van Secure Score ( ). <br/> * Blijf regelmatig dashboards en rapporten bekijken in het Microsoft 365-beveiligingscentrum, cloud-appbeveiliging en SIEM-hulpprogramma's. <br/> * Blijven zoeken naar en implementeren van software-updates. <br/> * Integreer eDiscovery in uw juridische en dreigingsresponsprocessen.|
|Bedreigingsbeveiliging|* Implementeer [Secure Privileged Access](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) voor identiteitsonderdelen op locatie (AD, AD FS). <br/> * Gebruik Cloud App Security om te controleren op insider bedreigingen. <br/> * Ontdek schaduw IT SaaS gebruik met behulp van Cloud App Security.|
|Identiteits- en toegangsbeheer|* Verfijn beleid en operationele processen. <br/> * Gebruik Azure AD Identity Protection om bedreigingen van insiders te identificeren.|
|Gegevensbescherming| Beleid voor informatiebescherming verfijnen: <br/> * Microsoft 365- en Office 365-gevoeligheidslabels en preventie van gegevensverlies (DLP) of Azure Information Protection. <br/> * Cloud App Beveiligingsbeleid en waarschuwingen.|

Zie ook: [Hoe snelle cyberaanvallen zoals Petya en WannaCrypt te verzachten.](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)
