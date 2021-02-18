---
title: Routekaart voor beveiliging van Microsoft 365 - Topprioriteiten
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
description: De belangrijkste aanbevelingen van het microsoft-team voor het implementeren van beveiligingsfuncties ter bescherming van uw Microsoft 365-omgeving.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a7d376eb7266975dc7582b83bfd4fa5e930ccea4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288167"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Roadmap voor beveiliging: topprioriteiten voor de eerste 30 dagen, 90 dagen en daarna

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Dit artikel bevat de belangrijkste aanbevelingen van het Microsoft-team voor het implementeren van beveiligingsfuncties om uw Microsoft 365-omgeving te beschermen. Dit artikel is overgenomen uit een Microsoft Ignite-sessie: Beveilig Microsoft 365 als een pro: Topprioriteiten voor de eerste [30, 90 dagen en daarna.](https://www.youtube.com/watch?v=luignzNyR-o) Deze sessie is ontwikkeld en gepresenteerd door Mark Simos en Matt Kemelhar, Enterprise Architects Architects.

In dit artikel:

- [Resultaten van roadmap](security-roadmap.md#Roadmap)
- [30 dagen — krachtige snelle winst](security-roadmap.md#Thirdaydays)
- [90 dagen — verbeterde beveiliging](security-roadmap.md#Ninetydays)
- [Meer](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Resultaten van roadmap
<a name="Roadmap"> </a>

Deze aanbevelingen voor roadmaps zijn in drie fasen in een logische volgorde gefaseerd met de volgende doelen.

****

|Tijdsbestek|Resultaten|
|---|---|
|30 dagen|Snelle configuratie: <ul><li>Basisbeheerdersbescherming.</li><li>Logboekregistratie en analyse.</li><li>Basisidentiteitsbescherming.</li></ul> <p> Tenantconfiguratie. <p> Bereid belanghebbenden voor.|
|90 dagen|Geavanceerde beveiliging: <ul><li>Beheerdersaccounts.</li><li>Gegevens- en gebruikersaccounts.</li></ul> <p> Inzicht in nalevings-, bedreigings- en gebruikersbehoeften. <p> Pas standaardbeleid en -beveiliging aan en implementeert deze.|
|Meer|Pas belangrijke beleidsregels en besturingselementen aan en verfijn deze. <p> Beveiliging uitbreiden naar on-premises afhankelijkheden. <p> Integreer met bedrijfsprocessen en beveiligingsprocessen (juridische processen, bedreigingen voor insiders, enzovoort).|
|

## <a name="30-days--powerful-quick-wins"></a>30 dagen — krachtige snelle winst
<a name="Thirdaydays"> </a>

Deze taken kunnen snel worden uitgevoerd en hebben weinig gevolgen voor gebruikers.

****

|Gebied|Taken|
|---|---|
|Beveiligingsbeheer|<ul><li>Controleer Secure Score en noteer uw huidige score ( <https://securescore.office.com> ).</li><li>Schakel auditlogregistratie in voor Office 365. Zie [Zoeken in het auditlogboek.](../../compliance/search-the-audit-log-in-security-and-compliance.md)</li><li>[Configureer Microsoft 365 voor betere beveiliging.](tenant-wide-setup-for-increased-security.md)</li><li>Controleer regelmatig dashboards en rapporten in het Microsoft 365-beveiligingscentrum en cloud-app-beveiliging.</li></ul>|
|Bedreigingsbeveiliging|[Verbind Microsoft 365 met Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) om te beginnen met controleren met behulp van het standaardbeleid voor bedreigingsdetectie voor afwijkende gedrag. Het duurt zeven dagen om een basislijn te maken voor een afwijkingsdetectie. <p>  Beveiliging implementeren voor beheerdersaccounts:<ul><li>Speciale beheerdersaccounts gebruiken voor beheeractiviteiten.</li><li>Dwing meervoudige verificatie (MFA) af voor beheerdersaccounts.</li><li>Gebruik een [sterk beveiligd Windows 10-apparaat voor](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) beheeractiviteiten.</li></ul>|
|Identiteits- en toegangsbeheer|<ul><li>[Schakel Azure Active Directory Identity Protection in.](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)</li><li>Voor federatief identiteitsomgevingen moet u accountbeveiliging afdwingen (wachtwoordlengte, leeftijd, complexiteit, enzovoort).</li></ul>|
|Gegevensbescherming|Bekijk voorbeeldaanbevelingen voor gegevensbescherming. Informatiebescherming vereist coördinatie binnen uw organisatie. Aan de slag met de volgende informatiebronnen:<ul><li>[Office 365 Information Protection voor de AVG](https://aka.ms/o365gdpr)</li><li>[Teams configureren met drie beschermingsniveaus](../../solutions/configure-teams-three-tiers-protection.md) (waaronder delen, classificatie, preventie van gegevensverlies en Azure-gegevensbescherming)</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 dagen — verbeterde beveiliging
<a name="Ninetydays"> </a>

Het duurt wat langer om deze taken te plannen en te implementeren, maar de beveiligingsrisico's nemen sterk toe.

****

|Gebied|Taak|
|---|---|
|Beveiligingsbeheer|<ul><li>Controleer Secure Score voor aanbevolen acties voor uw omgeving ( <https://securescore.office.com> ).</li><li>Blijf regelmatig dashboards en rapporten controleren in het Microsoft 365-beveiligingscentrum, cloud-app-beveiliging en SIEM-hulpprogramma's.</li><li>Zoek naar software-updates en implementeert deze.</li><li>Onder leiding van een aanvalsslopers voor phishing- en [](attack-simulator.md) wachtwoordaanvallen met het wachtwoord van het handje (inbegrepen in [Office 365 Threat Intelligence).](office-365-ti.md)</li><li>Bekijk de ingebouwde rapporten in cloud-app-beveiliging (op het tabblad Onderzoeken) voor het delen van risico's.</li><li>Raadpleeg [Compliancebeheer](../../compliance/compliance-manager.md) om de status te controleren van regelgeving die van toepassing is op uw organisatie (zoals AVG, NIST 800-171).</li></ul>|
|Bedreigingsbeveiliging|Verbeterde beveiliging voor beheerdersaccounts implementeren: <ul><li>[Bevoorrechte toegangswerkstations](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) configureren voor beheeractiviteiten.</li><li>Azure [AD Privileged Identity Management configureren.](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)</li><li>Configureer een hulpprogramma voor beveiligingsinformatie- en gebeurtenisbeheer (SIEM) voor het verzamelen van logboekgegevens van Office 365, Cloud App-beveiliging en andere services, waaronder AD FS. In het auditlogboek worden gegevens niet meer dan 90 dagen op dezelfde manier op te halen. Door deze gegevens vast te leggen in het SIEM-hulpprogramma kunt u gegevens voor een langere periode opslaan.</li></ul>|
|Identiteits- en toegangsbeheer|<ul><li>Schakel MFA in en dwing deze af voor alle gebruikers.</li><li>Een set voorwaardelijke [toegang en verwante beleidsregels implementeren.](microsoft-365-policies-configurations.md)</li></ul>|
|Gegevensbescherming| Pas beleidsregels voor gegevensbeveiliging aan en implementeert ze. Deze bronnen bevatten voorbeelden: <ul><li>[Office 365 Information Protection voor de AVG](https://aka.ms/o365gdpr)</li><li>[Teams met drie beschermingsniveaus configureren](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Gebruik beleid voor preventie van gegevensverlies en controlehulpprogramma's in Microsoft 365 voor gegevens die zijn opgeslagen in Microsoft 365 (in plaats van cloud-app-beveiliging). <p> Gebruik Cloud-app-beveiliging met Microsoft 365 voor geavanceerde functies voor waarschuwingen (met andere opties dan preventie van gegevensverlies).|
|

## <a name="beyond"></a>Meer
<a name="Beyond"> </a>

Dit zijn belangrijke beveiligingsmaatregelen die voortbouwen op eerder werk.

****

|Gebied|Taak|
|---|---|
|Beveiligingsbeheer|<ul><li>Ga verder met het plannen van volgende acties met behulp van Secure Score <https://securescore.office.com> ().</li><li>Blijf regelmatig dashboards en rapporten controleren in het Microsoft 365-beveiligingscentrum, cloud-app-beveiliging en SIEM-hulpprogramma's.</li><li>Blijf zoeken naar software-updates en deze implementeren.</li><li>Integreer eDiscovery in uw juridische en bedreigingsreactieprocessen.</li></ul>|
|Bedreigingsbeveiliging|<ul><li>Implementeert [Secure Privileged Access](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) voor identiteitsonderdelen on-premises (AD, AD FS).</li><li>Gebruik Cloud-app-beveiliging om te controleren op insider-bedreigingen.</li><li>Ontdek het gebruik van Shadow IT SaaS met behulp van Cloud App Security.</li></ul>|
|Identiteits- en toegangsbeheer|<ul><li>Beleid en operationele processen verfijnen.</li><li>Gebruik Azure AD Identity Protection om insider-bedreigingen te identificeren.</li></ul>|
|Gegevensbescherming|Beleid voor informatiebeveiliging verfijnen: <ul><li>Gevoeligheidslabels en preventie van gegevensverlies (DLP) voor Microsoft 365 en Office 365, of Azure Information Protection.</li><li>Beveiligingsbeleid en waarschuwingen voor cloud-apps.</li></ul>|
|

Zie ook: Hoe u snelle cyberaanvallen zoals Petya en [WannaCrypt kunt beperken.](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)
