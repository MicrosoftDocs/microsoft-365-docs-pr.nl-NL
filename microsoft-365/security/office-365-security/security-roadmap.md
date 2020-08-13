---
title: Microsoft 365-beveiligingsschema-belangrijkste prioriteiten
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
description: 'De beste aanbevelingen van het Microsoft-Cyber Security team voor het implementeren van beveiligingsfuncties voor het beschermen van uw Microsoft 365-omgeving. '
ms.openlocfilehash: 089e63ad9c83aac0bc5e88da8a24184eb8bdee6e
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656955"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Beveiligingsschema-de belangrijkste punten voor de eerste 30 dagen, 90 dagen en langer

Dit artikel bevat belangrijke aanbevelingen van het Microsoft-Cyber Security team voor de implementatie van beveiligingsfuncties om uw Microsoft 365-omgeving te beschermen. Dit artikel is aangepast via een Microsoft Ignite-sessie — [Beveilig Microsoft 365 zoals een Cyber Security Pro: belangrijkste prioriteiten voor de eerste 30 dagen, 90 dagen](https://www.youtube.com/watch?v=luignzNyR-o)en meer. Deze sessie is ontwikkeld en gepresenteerd door Mark Simos en Matt Kemelhar, Enterprise Cyber Security architecten.

In dit artikel:

- [Resultaten van routekaart](security-roadmap.md#Roadmap)

- [30 dagen — krachtige snelle WINS](security-roadmap.md#Thirdaydays)

- [90 dagen — uitgebreide bescherming](security-roadmap.md#Ninetydays)

- [Verdergaan](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Resultaten van routekaart
<a name="Roadmap"> </a>

De aanbevelingen van deze procedure worden gedurende drie fasen klaargezet met de volgende doelstellingen.

****

|Tijdsbestek|Resultaten|
|---|---|
|30 dagen|Snelle configuratie:  <br/> * Basis beheerders beveiliging  <br/> * Logboekregistratie en analyse  <br/> * Basisbescherming van identiteiten  <br/> Tenant configuratie  <br/>  Belanghebbenden voorbereiden|
|90 dagen|Geavanceerde bescherming:  <br/> * Beheerdersaccounts  <br/>  * Gegevens &amp; gebruikersaccounts  <br/>  Inzicht in compliance, Threat en gebruikersbehoeften  <br/>  Standaardbeleid en beveiliging aanpassen en implementeren|
|Verdergaan|Belangrijke beleidsregels en besturingselementen aanpassen en verfijnen  <br/> Beveiliging van de on-premises afhankelijkheden verlengen  <br/> Integratie met zakelijke en beveiligings processen (wettelijk, Insider-bedreiging, etc.)|
|

## <a name="30-days--powerful-quick-wins"></a>30 dagen — krachtige snelle WINS
<a name="Thirdaydays"> </a>

U kunt deze taken snel afhandelen en hebben minder invloed op de gebruikers.

****

|Ziet|Taken|
|---|---|
|Beveiligingsbeheer|* Controleer de Secure Score en neem uw huidige Score ( <https://securescore.office.com> ).  <br/>  * Schakel de controlelogboekregistratie voor Office 365 in. Zie [Zoeken in het auditlogboek](../../compliance/search-the-audit-log-in-security-and-compliance.md).  <br/> * [Configureer Microsoft 365 voor een betere beveiliging](tenant-wide-setup-for-increased-security.md).  <br/>  * Dashboards en rapporten regelmatig controleren in het Microsoft 365 Beveiligingscentrum en de beveiliging van Cloud apps.|
|Bedreigingsbeveiliging|[Microsoft 365 verbinden met de beveiliging van de Microsoft Cloud-app](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) om te beginnen met het standaardbeleid voor bedreiging voor detectie van anomalie gedrag. Voor het maken van anomaliedetectie duurt het zeven dagen om een basislijn te maken.  <br><br/>  Beveiligingsimplementatie voor beheerdersaccounts:  <br/> * Gebruik speciale beheerdersaccounts voor beheeractiviteiten.  <br/>  * Multi-factor Authentication (MFA) afdwingen voor beheerdersaccounts.  <br/>  * Gebruik een [zeer veilig Windows 10-apparaat](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) voor beheeractiviteiten.|
|Identiteits- en toegangsbeheer|* [Azure Active Directory-identiteits bescherming inschakelen](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).  <br/> * Voor federatieve identiteits omgevingen: beveiliging van accounts afdwingen (wachtwoordlengte, ouderdom, complexiteit, enzovoort).|
|Informatiebescherming|Bekijk voorbeelden van aanbevelingen voor informatiebeveiliging. Voor de informatiebescherming moet de coördinatie binnen uw organisatie worden gecoördineerd. Aan de slag met de volgende informatiebronnen:  <br/> * [Office 365 Information Protection voor AVG](https://aka.ms/o365gdpr) <br/> * [Teams configureren met drie niveaus van bescherming](../../solutions/configure-teams-three-tiers-protection.md) (waaronder delen, classificatie, preventie van gegevensverlies en Azure Information Protection)|
|

## <a name="90-days--enhanced-protections"></a>90 dagen — uitgebreide bescherming
<a name="Ninetydays"> </a>

Deze taken doen wat meer tijd voor het plannen en implementeren van uw beveiligings posture.

****

|Ziet|Taak|
|---|---|
|Beveiligingsbeheer|* Bekijk de beveiligde score voor aanbevolen acties voor uw omgeving ( [https://securescore.office.com](https://securescore.office.com) ).  <br/>  * Blijf dashboards en rapporten regelmatig controleren in het Microsoft 365-Beveiligingscentrum, de functies van de Cloud app en SIEM. <br/> * Zoek en implementeer software-updates. <br/> * Aanvals simulaties voor woord vermoeden, wachtwoord spuiten en aanval met brute kracht met [aanval Simulator](attack-simulator.md) (inbegrepen in [Office 365 Threat Intelligence](office-365-ti.md)).  <br/> * Ga naar risico voordelen door de ingebouwde rapporten in de Cloud-app-beveiliging te controleren (op het tabblad onderzoek). <br/> * Controleer de [compliantie Score](https://docs.microsoft.com/microsoft-365/compliance/compliance-score) om de status te controleren van de voorschriften die van toepassing zijn op uw organisatie (zoals AVG, NIST 800-171).|
|Bedreigingsbeveiliging| Uitgebreide beveiliging voor beheerdersaccounts implementeren: <br/> * [Geprivilegieerde toegangs werkstations](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) configureren voor beheeractiviteiten. <br/> * Configureer [Azure AD-beheer met bevoegdheden](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure). <br/> * U kunt een SIEM-hulpprogramma (Security Information and Event Management) configureren om logboekregistratie gegevens te verzamelen uit Office 365, de beveiliging van Cloud apps en andere services, waaronder AD FS. Het auditlogboek bevat gegevens voor slechts 90 dagen. Door deze gegevens te vastleggen in het hulpmiddel SIEM kunt u gegevens bewaren voor een langere periode.|
|Identiteits- en toegangsbeheer|* MFA in-en uitdwingen voor alle gebruikers. <br/> * Implementeer een set [voorwaardelijke toegang en gerelateerde beleidsregels](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations). |
|Informatiebescherming| Beleidsregels voor informatiebescherming aanpassen en implementeren. Dit zijn voorbeelden van deze informatiebronnen: <br/> * [Office 365 Information Protection voor AVG](https://aka.ms/o365gdpr) <br/> * [Teams met drie niveaus van bescherming configureren](../../solutions/configure-teams-three-tiers-protection.md) <br/> <br> Gebruik beleidsregels voor preventie van gegevensverlies en controlefuncties in Microsoft 365 voor gegevens die zijn opgeslagen in Microsoft 365 (in plaats van de beveiliging van de Cloud app). <br><br>Gebruik Cloud app-beveiliging met Microsoft 365 voor geavanceerde waarschuwingsfuncties (buiten de preventie van gegevensverlies).|
|

## <a name="beyond"></a>Verdergaan
<a name="Beyond"> </a>

Dit zijn belangrijke beveiligingsmaatregelen die voorgaande werkzaamheden worden gemaakt.

****

|Ziet|Taak|
|---|---|
|Beveiligingsbeheer|* Ga verder met het plannen van volgende acties met behulp van Secure Score ( [https://securescore.office.com](https://securescore.office.com) ). <br/> * Blijf dashboards en rapporten regelmatig controleren in het Microsoft 365-Beveiligingscentrum, de functies van de Cloud app en SIEM. <br/> * Ga naar software-updates zoeken en implementeren. <br/> * Integreer eDiscovery in uw juridische en bedreigings respons processen.|
|Bedreigingsbeveiliging|* Implementeer [beveiligingsbevoegdheden](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) voor het uitvoeren van beveiligingsbevoegdheden (Spa) voor Identity-onderdelen (AD, AD FS). <br/> * Beveiliging van Cloud apps gebruiken om te controleren op Insider-bedreigingen. <br/> * Ontdek de schaduw met behulp van de Cloud-app-beveiliging.|
|Identiteits- en toegangsbeheer|* Beleidsregels en operationele processen verfijnen. <br/> * Gebruik Azure AD-identiteitsbeveiliging om Insider-bedreigingen te identificeren.|
|Informatiebescherming|Beleidsregels voor informatiebescherming verfijnen: <br/> * Microsoft 365 en Office 365-labels en preventie van gegevensverlies (DLP) of Azure Information Protection. <br/> * Beveiligingsbeleid en waarschuwingen voor Cloud apps.|
|

Zie ook: de [beperking voor snelle cyberattacks, zoals Petya en WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/).
