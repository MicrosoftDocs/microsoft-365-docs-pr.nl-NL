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
ms.openlocfilehash: d62db9206a98078ae5adaad220a7c9b53ff116cd
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561693"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Beveiligingsschema-de belangrijkste punten voor de eerste 30 dagen, 90 dagen en langer

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


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
|30 dagen|Snelle configuratie: <ul><li>Basis beheerders beveiliging.</li><li>Logboekregistratie en analyses.</li><li>Basis identiteits bescherming.</li></ul> <p> Tenant configuratie. <p> Belanghebbenden voorbereiden.|
|90 dagen|Geavanceerde bescherming: <ul><li>Beheerdersaccounts.</li><li>Data en gebruikersaccounts.</li></ul> <p> Inzicht in compliance, Threat en gebruikersbehoeften. <p> Pas standaardbeleid en beveiliging aan en implementeer deze.|
|Verdergaan|Pas de sleutel beleidsregels en besturingselementen aan en verfijnen. <p> Breid de bescherming van on-premises afhankelijkheden uit. <p> Integratie met bedrijfs-en beveiligings processen (wettelijk, Insider-bedreiging, enzovoort).|
|

## <a name="30-days--powerful-quick-wins"></a>30 dagen — krachtige snelle WINS
<a name="Thirdaydays"> </a>

U kunt deze taken snel afhandelen en hebben minder invloed op de gebruikers.

****

|Ziet|Taken|
|---|---|
|Beveiligingsbeheer|<ul><li>Controleer de beveiligde Score en neem uw huidige Score ( <https://securescore.office.com> ).</li><li>Schakel controlelogboekregistratie voor Office 365 in. Zie [Zoeken in het auditlogboek](../../compliance/search-the-audit-log-in-security-and-compliance.md).</li><li>[Configureer Microsoft 365 voor een betere beveiliging](tenant-wide-setup-for-increased-security.md).</li><li>Controleer regelmatig dashboards en rapporten in het Microsoft 365 Beveiligingscentrum en de beveiliging van Cloud apps.</li></ul>|
|Bedreigingsbeveiliging|[Microsoft 365 verbinden met de beveiliging van de Microsoft Cloud-app](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) om te beginnen met het standaardbeleid voor bedreiging voor detectie van anomalie gedrag. Voor het maken van anomaliedetectie duurt het zeven dagen om een basislijn te maken. <p>  Beveiligingsimplementatie voor beheerdersaccounts:<ul><li>Exclusieve beheerdersaccounts gebruiken voor beheeractiviteiten.</li><li>Meervoudige verificatie (MFA) afdwingen voor beheerdersaccounts.</li><li>Gebruik een [zeer veilig Windows 10-apparaat](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) voor beheeractiviteiten.</li></ul>|
|Identiteits- en toegangsbeheer|<ul><li>[Azure Active Directory-identiteits bescherming inschakelen](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</li><li>Voor federatieve identiteits omgevingen: beveiliging van accounts afdwingen (wachtwoordlengte, ouderdom, complexiteit, enzovoort).</li></ul>|
|Gegevensbescherming|Bekijk voorbeelden van aanbevelingen voor informatiebeveiliging. Voor de informatiebescherming moet de coördinatie binnen uw organisatie worden gecoördineerd. Aan de slag met de volgende informatiebronnen:<ul><li>[Office 365 Information Protection voor de AVG](https://aka.ms/o365gdpr)</li><li>[Teams configureren met drie niveaus van bescherming](../../solutions/configure-teams-three-tiers-protection.md) (waaronder delen, classificatie, preventie van gegevensverlies en Azure Information Protection)</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 dagen — uitgebreide bescherming
<a name="Ninetydays"> </a>

Deze taken doen wat meer tijd voor het plannen en implementeren van uw beveiligings posture.

****

|Ziet|Taak|
|---|---|
|Beveiligingsbeheer|<ul><li>Controleer de beveiligde score voor aanbevolen acties voor uw omgeving ( [https://securescore.office.com](https://securescore.office.com) ).</li><li>Blijf regelmatig dashboards en rapporten in het Microsoft 365 Beveiligingscentrum, de Cloud app Security en de hulpprogramma's voor SIEM bekijken.</li><li>Zoek en implementeer software-updates.</li><li>Simuleer beveiligings simulaties voor een Spear, wachtwoord en een aanval met een grove aanval met behulp van [aanvals Simulator](attack-simulator.md) (inbegrepen in [Office 365 Threat Intelligence](office-365-ti.md)).</li><li>Let op delen van risico door de ingebouwde rapporten in de Cloud-app-beveiliging te controleren (op het tabblad onderzoek).</li><li>Controleer [Compliance Manager](https://docs.microsoft.com/microsoft-365/compliance/compliance-manager) om de status te controleren van de voorschriften die van toepassing zijn op uw organisatie (zoals AVG, NIST 800-171).</li></ul>|
|Bedreigingsbeveiliging|Uitgebreide beveiliging voor beheerdersaccounts implementeren: <ul><li>[Geprivilegieerde toegangs werkstations](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) configureren voor beheeractiviteiten.</li><li>Configureer [Azure AD-beheer](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)van de identiteit.</li><li>Configureer een beveiligings-en SIEM-hulpmiddel voor het verzamelen van logboekgegevens uit Office 365, de beveiliging van Cloud apps en andere services, waaronder AD FS. Het auditlogboek bevat gegevens voor slechts 90 dagen. Door deze gegevens te vastleggen in het hulpmiddel SIEM kunt u gegevens bewaren voor een langere periode.</li></ul>|
|Identiteits- en toegangsbeheer|<ul><li>MFA inschakelen en afdwingen voor alle gebruikers.</li><li>Implementeer een set [voorwaardelijke toegang en gerelateerde beleidsregels](microsoft-365-policies-configurations.md).</li></ul>|
|Gegevensbescherming| Beleidsregels voor informatiebescherming aanpassen en implementeren. Dit zijn voorbeelden van deze informatiebronnen: <ul><li>[Office 365 Information Protection voor de AVG](https://aka.ms/o365gdpr)</li><li>[Teams met drie beschermingsniveaus configureren](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Gebruik beleidsregels voor preventie van gegevensverlies en controlefuncties in Microsoft 365 voor gegevens die zijn opgeslagen in Microsoft 365 (in plaats van de beveiliging van de Cloud app). <p> Gebruik Cloud app-beveiliging met Microsoft 365 voor geavanceerde waarschuwingsfuncties (buiten de preventie van gegevensverlies).|
|

## <a name="beyond"></a>Verdergaan
<a name="Beyond"> </a>

Dit zijn belangrijke beveiligingsmaatregelen die voorgaande werkzaamheden worden gemaakt.

****

|Ziet|Taak|
|---|---|
|Beveiligingsbeheer|<ul><li>Ga verder met het plannen van volgende acties met behulp van Secure Score ( <https://securescore.office.com> ).</li><li>Blijf regelmatig dashboards en rapporten in het Microsoft 365 Beveiligingscentrum, de Cloud app Security en de hulpprogramma's voor SIEM bekijken.</li><li>Ga naar software-updates zoeken en implementeren.</li><li>Integreer eDiscovery in uw juridische en bedreigings antwoord processen.</li></ul>|
|Bedreigingsbeveiliging|<ul><li>Implementeer [beveiligingsbevoegdheden](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) voor het uitvoeren van beveiligingsbevoegdheden (Spa) voor Identity-onderdelen (AD, AD FS).</li><li>Gebruik Cloud app-beveiliging om te controleren op Insider-bedreigingen.</li><li>Ontdek de schaduw IT SaaS-gebruik door de Cloud beveiliging van de cloud te gebruiken.</li></ul>|
|Identiteits- en toegangsbeheer|<ul><li>Verfijnen beleidsregels en operationele processen.</li><li>Insider-bedreigingen met Azure Active Directory-beveiliging identificeren.</li></ul>|
|Gegevensbescherming|Beleidsregels voor informatiebescherming verfijnen: <ul><li>Microsoft 365 en Office 365 voor de vertrouwelijkheid van labels en preventie van gegevensverlies (DLP) of Azure Information Protection.</li><li>Beveiligingsbeleid en waarschuwingen voor Cloud apps.</li></ul>|
|

Zie ook: de [beperking voor snelle cyberattacks, zoals Petya en WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/).
