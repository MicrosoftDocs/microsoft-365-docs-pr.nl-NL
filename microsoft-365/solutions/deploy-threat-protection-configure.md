---
title: Stappen voor het configureren van mogelijkheden voor bedreigingsbeveiliging in Microsoft 365
description: Gebruik dit artikel als handleiding voor het implementeren van uw oplossing voor bedreigingsbeveiliging. Beveiligingsservices en -mogelijkheden voor bedreigingen implementeren in Microsoft 365 E5.
keywords: beveiligingsoplossing, installatie, configuratie, Microsoft 365 E5, geavanceerde bedreigingsbeveiliging, defender
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
audience: Admin
ms.topic: how-to
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: a0c728e5f273752792f851c72df2dfe243116221
ms.sourcegitcommit: a46532bb422ee51331f478ff50cc5444586bf6a9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2021
ms.locfileid: "51650216"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>Mogelijkheden voor bedreigingsbeveiliging configureren in Microsoft 365

Volg deze stappen om bedreigingsbeveiliging in Microsoft 365 te configureren.

## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>Stap 1: Meervoudige verificatie en beleid voor voorwaardelijke toegang instellen

[Voor meervoudige verificatie](/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) moeten gebruikers hun identiteit verifiëren met een telefoongesprek of een authenticator-app. [Beleid voor voorwaardelijke](/azure/active-directory/conditional-access/overview) toegang definieert bepaalde vereisten die moeten worden voldaan om gebruikers toegang te geven tot apps en gegevens in Microsoft 365. MFA- en Conditional Access-beleid werken samen om uw organisatie te beschermen. Als iemand zich bijvoorbeeld probeert aan te melden vanaf een mobiel apparaat met een account dat niet is ingeschakeld voor MFA en een beleid voor Voorwaardelijke toegang vereist dat MFA van kracht is, kan deze gebruiker zich niet aanmelden.  

Microsoft heeft een specifieke set voorwaardelijke toegang en verwante beleidsregels getest en aanbevolen voor het beschermen van de toegang tot al uw SaaS-toepassingen, met name Microsoft 365. Beleid wordt aanbevolen voor basislijnbeveiliging, gevoelige en sterk gereguleerde beveiliging. Begin met het implementeren van het beleid voor basislijnbeveiliging. 


[ ![ Algemeen beleid voor het configureren van identiteits-](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)en apparaattoegang 
 [Zie een grotere versie van deze afbeelding](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>Basislijnbeveiliging voor Microsoft 365 implementeren

![Proces voor het implementeren van basislijnbeveiliging](../media/deploy-threat-protection/deploy-threat-protection-identity-access-steps.png) 

1. [Vereisten configureren, waaronder Azure AD Identity Protection](../security/office-365-security/identity-access-prerequisites.md).
2. [Algemene beleidsregels voor identiteits- en apparaattoegang configureren](../security/office-365-security/identity-access-policies.md) voor basislijnbeveiliging.
3. Beleid configureren [voor gastgebruikers,](../security/office-365-security/identity-access-policies-guest-access.md) [Microsoft Teams,](../security/office-365-security/teams-access-policies.md) [Exchange Online](../security/office-365-security/secure-email-recommended-policies.md)en [SharePoint Online en OneDrive.](../security/office-365-security/sharepoint-file-access-policies.md)

### <a name="more-information-about-protecting-identities"></a>Meer informatie over het beveiligen van identiteiten

- [Configuratie van identiteiten en apparaattoegang](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Beveiligingsadvies voor Azure MFA](/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-microsoft-defender-for-identity"></a>Stap 2: Microsoft Defender configureren voor identiteit

[Microsoft Defender voor](/defender-for-identity/what-is) identiteit is een cloudgebaseerde beveiligingsoplossing die werkt met uw on-premises Ad DS-signalen (Active Directory Domain Services) om geavanceerde bedreigingen, gecompromitteerde identiteiten en kwaadaardige insideracties die zijn gericht op uw organisatie te identificeren, te detecteren en te onderzoeken.

Met Microsoft Defender voor identiteit kunnen beveiligingsbewerkingen (SecOps)-analisten en beveiligingsprofessionals die problemen hebben met het opsporen van geavanceerde aanvallen in hybride omgevingen, het volgende doen:
- Controleer gebruikers, gedrag van entiteiten en activiteiten met op leer gebaseerde analyses.
- Gebruikersidentiteiten en -referenties beveiligen die zijn opgeslagen in Active Directory.
- Verdachte gebruikersactiviteiten en geavanceerde aanvallen in de hele kill chain identificeren en onderzoeken.
- Heldere incidentinformatie verstrekken op een eenvoudige tijdlijn voor snelle sortering.

### <a name="to-set-up-microsoft-defender-for-identity"></a>Microsoft Defender voor identiteit instellen

![Proces voor het implementeren van Microsoft Defender voor identiteit](../media/deploy-threat-protection/deploy-azure-atp-steps.png) 

1. [Microsoft Defender voor identiteit instellen om](/azure-advanced-threat-protection/install-atp-step1) uw primaire omgevingen te beschermen.
2. Bescherm al uw [domeincontrollers](/azure-advanced-threat-protection/atp-sensor-monitoring) en [-bossen.](/azure-advanced-threat-protection/atp-multi-forest)
3. Microsoft [Defender voor identiteitswaarschuwingen integreren](/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) in uw beveiligingsbewerkingen (SecOps)-werkstroom.

### <a name="more-information-about-microsoft-defender-for-identity"></a>Meer informatie over Microsoft Defender voor identiteit

- [Wat is Microsoft Defender for Identity?](/azure-advanced-threat-protection/what-is-atp)
- [Video: Inleiding tot Microsoft Defender voor identiteit](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Microsoft Defender voor identiteitsimplementatie](/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a>Stap 3: Microsoft 365 Defender in-

[Microsoft 365 Defender](../security/defender/microsoft-365-defender.md) combineert signalen en orden mogelijkheden tot één oplossing. Met de geïntegreerde Microsoft 365 Defender-oplossing kunnen beveiligingsprofessionals de bedreigingssignalen die elk van deze producten ontvangen, samenbrengen en het volledige bereik en de impact van de bedreiging bepalen. de manier waarop de omgeving is ingevoerd, wat de gevolgen zijn en wat de invloed ervan is op de organisatie. Microsoft 365 Defender voert automatisch actie om de aanval te voorkomen of te stoppen en getroffen postvakken, eindpunten en gebruikersidentiteiten te voorkomen of te herstellen.

Microsoft 365 Defender maakt waarschuwingen, incidenten, geautomatiseerd onderzoek en antwoord en geavanceerde zoekwerkbelastingen (Microsoft Defender voor identiteit, Microsoft Defender voor Office 365, Microsoft Defender voor Eindpunt en Microsoft Cloud App-beveiliging) in één deelvenster met glaservaring. Nieuwe functies worden voortdurend toegevoegd aan Microsoft 365 Defender; overwegen om in te kiezen om preview-functies te ontvangen.

### <a name="to-set-up-microsoft-365-defender"></a>Microsoft 365 Defender instellen

![Proces voor de implementatie van Microsoft 365 Defender](../media/deploy-threat-protection/deploy-mtp-steps.png) 

1. [Controleer de vereisten.](../security/defender/prerequisites.md)
2. [Schakel Microsoft 365 Defender in.](../security/defender/m365d-enable.md)
3. [Kies voor preview-functies.](../security/defender/preview.md)

### <a name="more-information-about-microsoft-365-defender"></a>Meer informatie over Microsoft 365 Defender

- [Wat is Microsoft 365 Defender?](../security/defender/microsoft-365-defender.md)
- [Wat is er nieuw in Microsoft 365 Defender](../security/defender/whats-new.md)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a>Stap 4: Microsoft Defender configureren voor Office 365

[Microsoft Defender voor Office 365](../security/office-365-security/defender-for-office-365.md) beschermt uw organisatie tegen schadelijke bedreigingen in e-mailberichten (bijlagen en URL's), Office-documenten en samenwerkingshulpmiddelen. In de volgende tabel vindt u de functies en mogelijkheden van Microsoft Defender voor Office 365 die zijn opgenomen in Microsoft 365 E5:

|Configuratie-, beveiligings- en detectiemogelijkheden|Automatiserings-, onderzoeks-, herstel- en onderwijsmogelijkheden|
|:---|:---|
|[Veilige bijlagen](../security/office-365-security/safe-attachments.md)<br/>[Veilige koppelingen](../security/office-365-security/safe-links.md)<br/>[Veilige documenten](../security/office-365-security/safe-docs.md)<br/>[ATP voor SharePoint, OneDrive en Microsoft Teams](../security/office-365-security/mdo-for-spo-odb-and-teams.md)<br/> [Anti-phishingbeveiliging in Microsoft 365](../security/office-365-security/anti-phishing-protection.md)|[Bedreigingsoverzichten](../security/office-365-security/threat-trackers.md)<br/>[Bedreigingsverkenner](../security/office-365-security/threat-explorer.md)<br/>[Geautomatiseerd onderzoek en reactie](../security/office-365-security/office-365-air.md)<br/>[Aanvalssimulator](../security/office-365-security/attack-simulator.md)|
|

Met Microsoft Defender voor Office 365 kunnen personen in uw organisatie veiliger communiceren en samenwerken, met bescherming tegen bedreigingen voor hun e-mailinhoud en Office-documenten.

### <a name="to-set-up-microsoft-defender-for-office-365"></a>Microsoft Defender voor Office 365 instellen

![Proces voor de implementatie van Microsoft Defender voor Office 365](../media/deploy-threat-protection/deploy-office365-atp-steps.png) 

1. [Uw Microsoft Defender voor Office 365-beleid instellen en configureren.](../security/office-365-security/protect-against-threats.md)
2. [Bekijk en gebruik uw Microsoft Defender voor Office 365-rapporten.](../security/office-365-security/view-reports-for-mdo.md)
3. [Gebruik mogelijkheden voor bedreigingsonderzoek en -reactie.](../security/office-365-security/office-365-ti.md)

### <a name="more-information-about-microsoft-defender-for-office-365"></a>Meer informatie over Microsoft Defender voor Office 365

- [Overzicht van Microsoft Defender voor Office 365](../security/office-365-security/defender-for-office-365.md)
- [Nieuwe functies in Microsoft Defender voor Office 365](../security/office-365-security/whats-new-in-defender-for-office-365.md)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a>Stap 5: Microsoft Defender configureren voor eindpunt

[Microsoft Defender voor Eindpunt](/windows/security/threat-protection) beschermt uw apparaten (ook wel eindpunten genoemd) tegen cyberaanvallen, geavanceerde aanvallen en datalekken. Beveiligingsteams kunnen efficiënter zijn in het beheren van de beveiliging van hun eindpunten. Krachtige hulpprogramma's helpen organisaties om op de hoogte te blijven van ongepatchte systemen met behulp van detectie van kwetsbaarheid [met bedreigings- en beveiligingsprobleembeheer.](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Geautomatiseerde detectie- en herstelmogelijkheden, zoals de beperking van het oppervlak [van](/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)de [](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) [aanval,](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)beveiliging van de volgende [generatie,](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)eindpuntdetectie en -reactie, en geautomatiseerde onderzoek- en herstelmogelijkheden helpen uw apparaten te beschermen tegen malware. Naast deze mogelijkheden kunnen klanten proactieve meldingen ontvangen en op aanvraag contact opnemen met Microsoft Threat Experts, als onderdeel van de opt-in managed hunting service. 


### <a name="set-up-microsoft-defender-for-endpoint"></a>Microsoft Defender voor Eindpunt instellen

![Proces voor de implementatie van Microsoft Defender voor Eindpunt](../media/deploy-threat-protection/deploy-mdatp-steps.png) 

1. [Bereid uw omgeving voor op Microsoft Defender voor Eindpunt.](../security/defender-endpoint/deployment-phases.md)
2. [Microsoft Defender voor eindpunt implementeren.](../security/defender-endpoint/production-deployment.md)
3. [Onboard to the Microsoft Defender for Endpoint service](../security/defender-endpoint/onboarding.md).
4. [Voltooi uw belangrijkste beveiligingstaken.](../security/defender-endpoint/tvm-security-recommendation.md)

### <a name="more-information-about-microsoft-defender-for-endpoint"></a>Meer informatie over Microsoft Defender voor Eindpunt

- [Meer informatie over Microsoft Defender voor Eindpunt](../security/defender-endpoint/microsoft-defender-endpoint.md).
- [Probeer het evaluatielaboratorium van Microsoft Defender voor eindpunten.](../security/defender-endpoint/evaluation-lab.md)

## <a name="step-6-configure-microsoft-cloud-app-security"></a>Stap 6: Beveiliging van Microsoft Cloud App configureren

[Microsoft Cloud App Security](/cloud-app-security) is een Cloud Access Security Broker die ondersteuning biedt voor het verzamelen van logboeken, API-connectors en reverse proxy. Microsoft Cloud App Security biedt uitgebreide zichtbaarheid, controle over het reizen van gegevens en geavanceerde analyses om cyberaanvallen in al uw cloudservices te identificeren en te bestrijden. Met Microsoft Cloud App Security kunnen uw beveiligingsbewerkingen de gevoelige informatie van uw organisatie beschermen, beschermen tegen cyberaanvallen en afwijkingen, apps ontdekken en controleren die toegang hebben tot de gegevens van uw organisatie en ervoor zorgen dat de cloud-apps van uw organisatie voldoen aan de nalevingsvereisten.

### <a name="set-up-microsoft-cloud-app-security"></a>Microsoft Cloud App-beveiliging instellen

![Proces voor het implementeren van Microsoft Cloud App Security](../media/deploy-threat-protection/deploy-mcas-steps.png) 

1. [Stel de portal en andere basisvereisten in.](/cloud-app-security/general-setup)
2. [Clouddetectie instellen en](/cloud-app-security/set-up-cloud-discovery) [apps verbinden.](/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)
3. [Voorwaardelijke toegang app-beheer implementeren voor aanbevolen apps](/cloud-app-security/proxy-deployment-aad).
4. [Gebruik de onderzoekshulpmiddelen en dashboards.](/cloud-app-security/investigate)

### <a name="more-information-about-microsoft-cloud-app-security"></a>Meer informatie over Microsoft Cloud App Security

- [Bekijk nieuwe functies en mogelijkheden.](/cloud-app-security/release-notes)
- [Meer informatie over Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security).

## <a name="step-7-monitor-status-and-take-actions"></a>Stap 7: Status controleren en acties uitvoeren

Nadat u uw services en mogelijkheden voor bedreigingsbeveiliging hebt ingesteld en geïmplementeerd, is het de volgende stap om de detectie van bedreigingen te controleren en de juiste acties uit te voeren. Het beste uitgangspunt is het Microsoft 365-beveiligingscentrum (), waar u de beveiliging in uw [https://security.microsoft.com](https://security.microsoft.com) Microsoft-identiteiten, gegevens, apparaten, apps en infrastructuur kunt bewaken en beheren. 

![Microsoft 365-beveiligingscentrum](../media/solutions-architecture-center/m365-security-center.png)

Het Microsoft 365-beveiligingscentrum is bedoeld voor beveiligingsbeheerders en beveiligingsbewerkingsteams. In het Microsoft 365-beveiligingscentrum kunt u het volgende doen:
- Bekijk de algehele beveiligingstoestand van uw organisatie met [Secure Score.](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-secure-score)
- [Controleer en bekijk rapporten](../security/defender-endpoint/threat-protection-reports.md) over de status van uw identiteiten, gegevens, apparaten, apps en infrastructuur.
- Verbind de puntjes op waarschuwingen via [incidenten.](https://docs.microsoft.com/microsoft-365/security/defender/incident-queue)
- Gebruik [automatisch onderzoek en herstel om bedreigingen](../security/defender/m365d-autoir.md) aan te pakken.
- [Ga proactief op zoek naar](https://docs.microsoft.com/microsoft-365/security/defender/advanced-hunting-overview)bedreigingen, zoals inbraakpogingen of inbreukactiviteiten die van invloed zijn op uw e-mail, gegevens, apparaten en identiteiten.
- [De nieuwste aanvalscampagnes en](https://docs.microsoft.com/microsoft-365/security/defender/latest-attack-campaigns) -technieken begrijpen met bedreigingsanalyses.
- ... en meer!

### <a name="more-information-about-the-microsoft-365-security-center"></a>Meer informatie over het Microsoft 365-beveiligingscentrum

- [Aan de slag met het Microsoft 365-beveiligingscentrum.](../security/defender/overview-security-center.md)
- [Rapporten bewaken en weergeven.](../security/defender/overview-security-center.md)
- [Zie de beveiligingsportalen in Microsoft 365](../security/defender/portals.md).

## <a name="step-8-train-users"></a>Stap 8: Gebruikers trainen

Trainingsgebruikers kunnen uw gebruikers en beveiligingsbewerkingen veel tijd en frustratie besparen. Slimme gebruikers openen minder snel bijlagen of klikken op koppelingen in twijfelachtige e-mailberichten en voorkomen eerder verdachte websites. 

Het Handboek [cyberbeveiligingscampagne](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) van de Harvard Kennedy School biedt uitstekende richtlijnen voor het tot stand brengen van een sterke cultuur van beveiligingsbewustzijn binnen uw organisatie, inclusief het trainen van gebruikers om phishingaanvallen te identificeren. 

Microsoft 365 bevat de volgende bronnen om gebruikers in uw organisatie te informeren:

|Concept  |Resources  |
|---------|---------|
|Microsoft 365     |[Aanpasbare leerpaden](/office365/customlearning/) <p>Deze bronnen kunnen u helpen bij het maken van trainingen voor eindgebruikers in uw organisatie        |
|Microsoft 365-beveiliging |[Leermodule: Uw organisatie beveiligen met ingebouwde, intelligente beveiliging van Microsoft 365](/learn/modules/security-with-microsoft-365) <p>Met deze module kunt u beschrijven hoe beveiligingsfuncties van Microsoft 365 samenwerken en de voordelen van deze beveiligingsfuncties duidelijk maken. |
|Meervoudige verificatie     | [Verificatie in twee stappen: Wat is de extra verificatiepagina?](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>In dit artikel kunnen eindgebruikers begrijpen wat meervoudige verificatie is en waarom het wordt gebruikt in uw organisatie.    |

Naast deze richtlijnen raadt Microsoft aan dat uw gebruikers de acties uitvoeren die in dit artikel worden beschreven: Bescherm uw account en [apparaten tegen hackers en malware.](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx) Deze acties omvatten:
- Sterke wachtwoorden gebruiken
- Apparaten beveiligen 
- Beveiligingsfuncties inschakelen op Windows 10- en Mac-pc's (voor niet-verantwoordelijke apparaten)
    
Microsoft raadt gebruikers ook aan hun persoonlijke e-mailaccounts te beschermen door de acties uit te voeren die in de volgende artikelen worden aanbevolen:
- [Uw e-mailaccount Outlook.com beschermen](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [Uw Gmail-account beveiligen met verificatie in twee stappen](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
