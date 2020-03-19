---
title: Office 365-beveiligingsroadmap - Topprioriteiten voor de eerste 30 dagen, 90 dagen en daarna
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
description: 'De beste aanbevelingen van het cyberbeveiligingsteam van Microsoft voor het implementeren van beveiligingsmogelijkheden om uw Office 365-omgeving te beschermen. '
ms.openlocfilehash: c668bb736e6d9f788fe2c54e8a49adbfd4156f43
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42806845"
---
# <a name="office-365-security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Office 365-beveiligingsroadmap - Topprioriteiten voor de eerste 30 dagen, 90 dagen en daarna

Dit artikel bevat de belangrijkste aanbevelingen van het cyberbeveiligingsteam van Microsoft voor het implementeren van beveiligingsmogelijkheden om uw Office 365-omgeving te beschermen. Dit artikel is aangepast van een Microsoft Ignite-sessie - [Secure Office 365 als een cybersecurity-pro: topprioriteiten voor de eerste 30 dagen, 90 dagen en daarna](https://www.youtube.com/watch?v=luignzNyR-o). Deze sessie werd ontwikkeld en gepresenteerd door Mark Simos en Matt Kemelhar, Enterprise Cybersecurity Architects.

In dit artikel:

- [Roadmap resultaten](security-roadmap.md#Roadmap)

- [30 dagen - krachtige quick wins](security-roadmap.md#Thirdaydays)

- [90 dagen — betere bescherming](security-roadmap.md#Ninetydays)

- [Buiten](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Roadmap resultaten
<a name="Roadmap"> </a>

Deze roadmap aanbevelingen worden gefaseerd over drie fasen in een logische volgorde met de volgende doelen.

|||
|:-----|:-----|
| |Resultaten
|30 dagen|Snelle configuratie:  <br/> • Basisbeheerders  <br/> • Logboekregistratie en analyse  <br/> • Basisidentiteitsbescherming  <br/> Tenantconfiguratie  <br/>  Belanghebbenden voorbereiden|
|90 dagen|Geavanceerde beveiligingen:  <br/> • Beheerdersaccounts  <br/>  • &amp; Gegevens gebruikersaccounts  <br/>  Inzicht in compliance, bedreiging en gebruikersbehoeften  <br/>  Standaardbeleid en -beveiliging aanpassen en implementeren|
|Buiten|Het belangrijkste beleid en de besturingselementen aanpassen en verfijnen  <br/> Beveiligingen uitbreiden tot on-premises afhankelijkheden  <br/> Integreren met bedrijfs- en beveiligingsprocessen (juridische, insider threat, enz.)|



## <a name="30-days--powerful-quick-wins"></a>30 dagen - krachtige quick wins
<a name="Thirdaydays"> </a>

Deze taken kunnen snel worden uitgevoerd en hebben een lage impact op gebruikers.

|||
|:-----|:-----|
|Gebied|Taken|
|Beveiligingsbeheer|• Controleer secure score en neem[https://securescore.office.com](https://securescore.office.com)nota van uw huidige score ( ).  <br/>  • Schakel controlelogboekregistratie in voor Office 365. Zie [Het controlelogboek doorzoeken](../../compliance/search-the-audit-log-in-security-and-compliance.md).  <br/> • [Configureer uw Office 365-tenant voor meer beveiliging.](tenant-wide-setup-for-increased-security.md)  <br/>  • Bekijk regelmatig dashboards en rapporten in het Microsoft 365-beveiligingscentrum en Cloud App Security.|
|Bescherming tegen bedreigingen|[Sluit Office 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) aan met Microsoft Cloud App Security om te beginnen met monitoring met behulp van het standaardbeleid voor bedreigingsdetectie voor afwijkend gedrag. Het duurt zeven dagen om een basislijn te bouwen voor anomaliedetectie.  <br><br/>  Beveiliging implementeren voor beheerdersaccounts:  <br/> • Gebruik speciale beheerdersaccounts voor beheeractiviteiten.  <br/>  • Afdwingen multi-factor authenticatie (MFA) voor admin accounts.  <br/>  • Gebruik een [zeer veilig Windows 10-apparaat](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) voor beheerdersactiviteiten.|
|Identiteits- en toegangsbeheer|• [Azure Active Directory-identiteitsbeveiliging inschakelen.](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)  <br/> • Voor federatieve identiteitsomgevingen moet u accountbeveiliging afdwingen (wachtwoordlengte, leeftijd, complexiteit, enz.).|
|Informatiebescherming| Bekijk voorbeeld aanbevelingen voor informatiebescherming. Informatiebescherming vereist coördinatie in uw organisatie. Aan de slag met de volgende informatiebronnen:  <br/> • [Office 365 Informatiebescherming voor GDPR](https://aka.ms/o365gdpr) <br/> • [Beveilig SharePoint Online-sites en -bestanden](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) (inclusief delen, classificatie, preventie van gegevensverlies en Azure Information Protection)|

## <a name="90-days--enhanced-protections"></a>90 dagen — betere bescherming
<a name="Ninetydays"> </a>

Deze taken nemen een beetje meer tijd om te plannen en uit te voeren, maar sterk verhogen van uw beveiligingshouding.

|||
|:-----|:-----|
|Gebied|Taak|
|Beveiligingsbeheer|• Controleer de veilige score voor[https://securescore.office.com](https://securescore.office.com)aanbevolen acties voor uw omgeving ( ).  <br/>  • Blijf regelmatig dashboards en rapporten bekijken in de hulpprogramma's voor Microsoft 365-beveiligingscentrum, Cloud App Security en SIEM. <br/> • Zoek en implementeer software-updates. <br/> • Voer aanvalssimulaties uit voor spear-phishing, wachtwoordspray en brute-force wachtwoordaanvallen met Behulp van [Attack Simulator](attack-simulator.md) (inbegrepen bij [Office 365 Threat Intelligence).](office-365-ti.md)  <br/> • Zoek naar risico's delen door de ingebouwde rapporten in Cloud App Security (op het tabblad Onderzoeken) te bekijken. <br/> • Controleer [de nalevingsscore](https://docs.microsoft.com/microsoft-365/compliance/compliance-score) om de status te controleren op regelgeving die van toepassing is op uw organisatie (zoals GDPR, NIST 800-171).|
|Bescherming tegen bedreigingen| Verbeterde beveiligingen implementeren voor beheerdersaccounts: <br/> • [Configureer Geschikt voor toegang tot standplekken](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PA's) voor beheeractiviteiten. <br/> • [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)configureren. <br/> • Configureer een SIEM-tool (Security Information and Event Management) om logboekgegevens te verzamelen van Office 365, Cloud App Security en andere services, waaronder AD FS. Het controlelogboek van Office 365 slaat gegevens slechts 90 dagen op. Als u deze gegevens vastlegt in siem-tool, u gegevens voor een langere periode opslaan.|
|Identiteits- en toegangsbeheer|• MFA inschakelen en afdwingen voor alle gebruikers. <br/> • Implementeren van een reeks [voorwaardelijke toegang en bijbehorend beleid](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations). |
|Informatiebescherming| Het beleid voor informatiebescherming aanpassen en implementeren. Deze bronnen bevatten voorbeelden: <br/> • [Office 365 Informatiebescherming voor GDPR](https://aka.ms/o365gdpr) <br/> • [Beveilig SharePoint Online-sites en -bestanden](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) <br/> <br> Gebruik beleid voor gegevensverliespreventie en bewakingshulpprogramma's in Office 365 voor gegevens die zijn opgeslagen in Office 365 (in plaats van Cloud App Security). <br><br>Cloud app-beveiliging gebruiken met Office 365 voor geavanceerde waarschuwingsfuncties (anders dan het voorkomen van gegevensverlies).|

## <a name="beyond"></a>Buiten
<a name="Beyond"> </a>

Dit zijn belangrijke veiligheidsmaatregelen die voortbouwen op eerder werk.

|||
|:-----|:-----|
|Gebied|Taak|
|Beveiligingsbeheer|• Doorgaan met het plannen [https://securescore.office.com](https://securescore.office.com)van volgende acties met behulp van Secure Score ( ). <br/> • Blijf regelmatig dashboards en rapporten bekijken in de hulpprogramma's voor Microsoft 365-beveiligingscentrum, Cloud App Security en SIEM. <br/> • Blijf zoeken naar en implementeren van software-updates. <br/> • Integreer eDiscovery in uw juridische en bedreigingsreactieprocessen.|
|Bescherming tegen bedreigingen|• Implementeer [Secure Privileged Access](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) voor identiteitscomponenten op locatie (AD, AD FS). <br/> • Gebruik Cloud App Security om te controleren op bedreigingen met voorkennis. <br/> • Ontdek schaduw IT SaaS-gebruik met behulp van Cloud App Security.|
|Identiteits- en toegangsbeheer|• Verfijn beleid en operationele processen. <br/> • Gebruik Azure AD-identiteitsbeveiliging om insiderbedreigingen te identificeren.|
|Informatiebescherming| Beleid voor informatiebescherming verfijnen: <br/> • Microsoft 365- en Office 365-gevoeligheidslabels en gegevensverliespreventie (DLP) of Azure Information Protection. <br/> • Beveiligingsbeleid en waarschuwingen voor cloud-apps.|

Zie ook: [Hoe snelle cyberaanvallen zoals Petya en WannaCrypt te beperken.](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)
