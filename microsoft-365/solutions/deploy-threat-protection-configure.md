---
title: Stappen voor het configureren van mogelijkheden voor risicobeveiliging in Microsoft 365
description: Informatie over het implementeren van services en mogelijkheden voor bedreigingsbeveiliging in Microsoft 365 E5.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 492db78c9aea881ae05dbc66f5e84ad98629b923
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931984"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>Mogelijkheden voor bedreigingsbeveiliging configureren in Microsoft 365

Volg deze stappen om bedreigingsbeveiliging te configureren in Microsoft 365.


## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>Stap 1: Meervoudige verificatie en beleidsregels voor voorwaardelijke toegang instellen

[Bij meervoudige verificatie](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) moeten gebruikers hun identiteit verifiëren met een telefoonoproep- of verificatie-app. [Beleidsregels voor voorwaardelijke](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) toegang definiëren bepaalde vereisten die moeten worden voldaan om ervoor te zorgen dat gebruikers toegang hebben tot apps en gegevens in Microsoft 365. MFA en beleidsregels voor voorwaardelijke toegang werken samen om uw organisatie te beschermen. Als iemand zich bijvoorbeeld probeert aan te melden vanaf een mobiel apparaat met een account dat niet is ingeschakeld voor MFA en voor een beleid voor voorwaardelijke toegang is vereist dat MFA van kracht is, kan die gebruiker zich niet aanmelden.  

Microsoft heeft een specifieke set voorwaardelijke toegang en verwante beleidsregels getest en aanbevolen voor de beveiliging van de toegang tot al uw SaaS-toepassingen, met name Microsoft 365. Beleid wordt aanbevolen voor basislijnbeveiliging, gevoelige en sterk reguleerde beveiliging. Implementeert eerst het beleid voor basislijnbeveiliging. 


[ ![ Algemene beleidsregels voor het configureren van identiteits- en apparaattoegang Zie](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [een grotere versie van deze afbeelding](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>Basislijnbeveiliging implementeren voor Microsoft 365

![Proces voor het implementeren van basislijnbeveiliging](../media/solutions-architecture-center/deploy-threat-protection-identity-access-steps.png) 

1. [Configureer vereisten, waaronder Azure Identity Protection.](../security/office-365-security/identity-access-prerequisites.md)
2. [Configureer algemene beleidsregels voor identiteits- en apparaattoegang](../security/office-365-security/identity-access-policies.md) voor basislijnbeveiliging.
3. Beleid configureren [voor gastgebruikers,](../security/office-365-security/identity-access-policies-guest-access.md) [Microsoft Teams,](../security/office-365-security/teams-access-policies.md) [Exchange Online,](../security/office-365-security/secure-email-recommended-policies.md) [SharePoint Online en OneDrive.](../security/office-365-security/sharepoint-file-access-policies.md)

### <a name="more-information-about-protecting-identities"></a>Meer informatie over het beveiligen van identiteiten

- [Configuratie van identiteiten en apparaattoegang](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Beveiligings richtlijnen voor Azure MFA](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-microsoft-defender-for-identity"></a>Stap 2: Microsoft Defender configureren voor identiteit

[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) is een cloudgebaseerde beveiligingsoplossing die werkt met uw on-premises [Azure Active Directory-signalen](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) voor het identificeren, detecteren en onderzoeken van geavanceerde bedreigingen, gekromde identiteiten en kwaadaardige insideracties die zijn gericht op uw organisatie.

Met Microsoft Defender for Identity kunnen beveiligingsbewerkingen (SecOps) analisten en beveiligingsprofessionals moeite hebben om geavanceerde aanvallen in hybride omgevingen te detecteren. Om:
- Houd gebruikers, gedrag van entiteiten en activiteiten in de gaten met op leer gebaseerde analyse.
- Gebruikersidentiteiten en -referenties beveiligen die zijn opgeslagen in Active Directory.
- Verdachte gebruikersactiviteiten en geavanceerde aanvallen in de hele kill chain identificeren en onderzoeken.
- Heldere incidentinformatie verstrekken op een eenvoudige tijdlijn voor snelle sortering.

### <a name="to-set-up-microsoft-defender-for-identity"></a>Microsoft Defender instellen voor identiteit

![Proces voor het implementeren van Microsoft Defender voor identiteit](../media/solutions-architecture-center/deploy-azure-atp-steps.png) 

1. [Stel Microsoft Defender voor identiteit in om](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) uw primaire omgevingen te beveiligen.
2. Bescherm al uw [domeincontrollers](https://docs.microsoft.com/azure-advanced-threat-protection/atp-sensor-monitoring) en [-forests.](https://docs.microsoft.com/azure-advanced-threat-protection/atp-multi-forest)
3. Integreer [microsoft Defender voor identiteitswaarschuwingen](https://docs.microsoft.com/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) in uw werkstroom voor beveiligingsbewerkingen (SecOps).

### <a name="more-information-about-microsoft-defender-for-identity"></a>Meer informatie over Microsoft Defender voor identiteit

- [Wat is Microsoft Defender for Identity?](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Video: Inleiding tot Microsoft Defender voor identiteit](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Microsoft Defender voor identiteitsimplementatie](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a>Stap 3: Microsoft 365 Defender in te zetten

[Microsoft 365 Defender combineert](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) signalen en mogelijkheden om zo één oplossing te maken. Met de geïntegreerde Microsoft 365 Defender-oplossing kunnen beveiligingsprofessionals samenwerken aan de bedreigingssignalen dat elk van deze producten het volledige bereik en de impact van de bedreiging ontvangt en bepaalt. hoe de omgeving is ingevoerd, wat de gevolgen zijn en hoe deze op dit moment van invloed is op de organisatie. Microsoft 365 Defender onderneemt automatische acties om de aanval en postvakken, eindpunten en gebruikersidentiteiten te voorkomen of te stoppen.

Microsoft 365 Defender defificeert waarschuwingen, incidenten, geautomatiseerd onderzoek en reactie, en geavanceerd zoeken naar werkbelastingen (Microsoft Defender for Identity, Microsoft Defender voor Office 365, Microsoft Defender voor Eindpunt en Microsoft Cloud App-beveiliging) in één deelvenster met een uitgebreide ervaring. Nadat u een of meer van uw Defender voor Office 365-services hebt geconfigureerd, kunt u Microsoft 365 Defender in bedrijf zetten. Nieuwe functies worden voortdurend toegevoegd aan Microsoft 365 Defender. overweeg om preview-functies te ontvangen.

### <a name="to-set-up-microsoft-365-defender"></a>Microsoft 365 Defender instellen

![Proces voor de implementatie van Microsoft 365 Defender](../media/solutions-architecture-center/deploy-mtp-steps.png) 

1. [Controleer de vereisten.](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)
2. [Schakel Microsoft 365 Defender in.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)
3. [Kies voor voorbeeldfuncties.](https://docs.microsoft.com/microsoft-365/security/mtp/preview)

### <a name="more-information-about-microsoft-365-defender"></a>Meer informatie over Microsoft 365 Defender

- [Wat is Microsoft 365 Defender?](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [Wat is er nieuw in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a>Stap 4: Microsoft Defender voor Office 365 configureren

[Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) beschermt uw organisatie tegen schadelijke bedreigingen in e-mailberichten (bijlagen en URL's), Office-documenten en samenwerkingshulpmiddelen. De volgende tabel bevat de functies en mogelijkheden van Microsoft Defender voor Office 365 die deel uit maken van Microsoft 365 E5:

|Mogelijkheden voor configuratie, beveiliging en detectie|Automatiserings-, onderzoeks-, herstel- en onderwijsmogelijkheden|
|---|---|
|[Veilige bijlagen](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br/>[Veilige koppelingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)<br/>[Veilige documenten](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)<br/>[ATP voor SharePoint, OneDrive en Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)<br/>[Bescherming tegen phishing in Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#exclusive-settings-in-atp-anti-phishing-policies)|[Bedreigingsoverzichten](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-trackers)<br/>[Bedreigingsverkenner](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)<br/>[Geautomatiseerd onderzoek en reactie](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>[Aanvalssimulator](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)|
|

Met Microsoft Defender voor Office 365 kunnen personen in uw organisatie veiliger communiceren en samenwerken, met bedreigingsbeveiliging voor hun e-mailinhoud en Office-documenten.

### <a name="to-set-up-microsoft-defender-for-office-365"></a>Microsoft Defender instellen voor Office 365

![Proces voor de implementatie van Microsoft Defender voor Office 365](../media/solutions-architecture-center/deploy-office365-atp-steps.png) 

1. [Stel uw beleidsregels van Microsoft Defender voor Office 365 in en configureer ze.](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)
2. [Bekijk en gebruik uw Microsoft Defender voor Office 365-rapporten.](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)
3. [Gebruik bedreigingsonderzoek en reactiemogelijkheden.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)

### <a name="more-information-about-microsoft-defender-for-office-365"></a>Meer informatie over Microsoft Defender voor Office 365

- [Overzicht van Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Nieuw in Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a>Stap 5: Microsoft Defender configureren voor het eindpunt

[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) beschermt de apparaten van uw organisatie (ook wel eindpunten genoemd) tegen cyberaanvallen, geavanceerde aanvallen en gegevensinbreuken. Beveiligingsteams kunnen efficiënter werken met het beheren van de beveiliging van hun eindpunten. Krachtige hulpprogramma's helpen organisaties op de hoogte te blijven van ongepatchte systemen met behulp van beveiligingsdetectie met het beheer van [bedreigingen en kwetsbaarheid.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Geautomatiseerde detectie- en herstelmogelijkheden, zoals het verminderen van het aanvallenoppervlak, volgende [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) [generatie-beveiliging,](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) [eindpuntdetectie](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)en -reactie, en geautomatiseerd onderzoek en herstel helpen uw apparaten te beschermen tegen malware. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction) Klanten kunnen bovendien proactieve meldingen ontvangen en contact opnemen met Microsoft Threat Experts op aanvraag, als onderdeel van de opt-in beheerde zoekservice. 


### <a name="set-up-microsoft-defender-for-endpoint"></a>Microsoft Defender voor eindpunt instellen

![Proces voor de implementatie van Microsoft Defender voor eindpunt](../media/solutions-architecture-center/deploy-mdatp-steps.png) 

1. [Bereid uw implementatie van Microsoft Defender voor eindpunt voor.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases)
2. [Uw implementatie van Microsoft Defender voor eindpunt instellen](https://docs.microsoft.com/windows/security/threat-protection/micros.oft-defender-atp/production-deployment)
3. [Werk in bij de Microsoft Defender for Endpoint-service.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboarding)
4. [Voltooi uw belangrijkste beveiligingstaken.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)

### <a name="more-information-about-microsoft-defender-for-endpoint"></a>Meer informatie over Microsoft Defender voor eindpunt

- [Meer informatie over Microsoft Defender voor eindpunt.](https://docs.microsoft.com/windows/security/threat-protection)
- [Probeer de evaluatietest lab van Microsoft Defender for Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluation-lab)

## <a name="step-6-configure-microsoft-cloud-app-security"></a>Stap 6: Beveiliging van Microsoft Cloud-apps configureren

[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) is een beveiligingsadviseur voor Cloud Access die ondersteuning biedt voor logboekverzameling, API-connectors en reverse-proxy. Microsoft Cloud App Security biedt uitgebreide zichtbaarheid, controle over gegevensreizen en geavanceerde analyses om cyberaanvallen in al uw cloudservices te identificeren en te bestrijden. Met Microsoft Cloud App Security kunnen uw beveiligingsbewerkingen de gevoelige informatie van uw organisatie beschermen, beschermen tegen cyberaanvallen en -anales, apps vinden en bewaken die toegang krijgen tot de gegevens van uw organisatie en ervoor zorgen dat de cloud-apps van uw organisatie voldoen aan nalevingsvereisten.

### <a name="set-up-microsoft-cloud-app-security"></a>Beveiliging van Microsoft Cloud-apps instellen

![Proces voor de implementatie van Microsoft Cloud App-beveiliging](../media/solutions-architecture-center/deploy-mcas-steps.png) 

1. [Stel de portal en andere basisvereisten in.](https://docs.microsoft.com/cloud-app-security/general-setup)
2. [Clouddetectie instellen en](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery) [apps verbinden.](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)
3. [Voorwaardelijke toegang tot app-besturingselementen implementeren voor aanbevolen apps.](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad)
4. [Gebruik de onderzoekshulpprogramma's en dashboards.](https://docs.microsoft.com/cloud-app-security/investigate)

### <a name="more-information-about-microsoft-cloud-app-security"></a>Meer informatie over Microsoft Cloud App Security

- [Bekijk de nieuwe functies en mogelijkheden.](https://docs.microsoft.com/cloud-app-security/release-notes)
- [Meer informatie over Microsoft Cloud App Security.](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

## <a name="step-7-monitor-status-and-take-actions"></a>Stap 7: Status controleren en acties uitvoeren

Nadat u de services en mogelijkheden voor bedreigingsbeveiliging hebt ingesteld en geïmplementeerd, is de volgende stap het controleren van bedreigingsdetectie en het uitvoeren van de juiste acties. Het beste uitgangspunt is het Microsoft 365-beveiligingscentrum, waar u de beveiliging in al uw [https://security.microsoft.com](https://security.microsoft.com) Microsoft-identiteiten, gegevens, apparaten, apps en infrastructuur kunt bewaken en beheren. 

![Microsoft 365-beveiligingscentrum](../media/solutions-architecture-center/m365-security-center.png)

Het Microsoft 365-beveiligingscentrum is speciaal bedoeld voor beveiligingsbeheerders en teams met beveiligingsbewerkingen. In het Microsoft 365-beveiligingscentrum kunt u:
- Bekijk de algehele beveiligingstoestand van uw organisatie met [Secure Score.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)
- [U kunt rapporten controleren](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting) en weergeven over de status van uw identiteiten, gegevens, apparaten, apps en infrastructuur.
- Verbind de puntjes op waarschuwingen via [incidenten.](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- Gebruik [geautomatiseerd onderzoek en herstel om bedreigingen](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir) aan te pakken.
- [U kunt proactief zoeken naar bedreigingen,](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview)zoals inbreukpogingen of inbreuken op uw e-mail, gegevens, apparaten en identiteiten.
- [Meer informatie over de nieuwste aanvalscampagnes](https://docs.microsoft.com/microsoft-365/security/mtp/latest-attack-campaigns) en -technieken met bedreigingsanalyse.
- ... en meer!

### <a name="more-information-about-the-microsoft-365-security-center"></a>Meer informatie over het Microsoft 365-beveiligingscentrum

- [Aan de slag met het Microsoft 365-beveiligingscentrum.](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)
- [Rapporten bewaken en weergeven.](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting)
- [Zie de beveiligingsportals in Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/mtp/portals)

## <a name="step-8-train-users"></a>Stap 8: Gebruikers trainen

Trainingsgebruikers kunnen uw gebruikers en beveiligingsbewerkingsteam veel tijd en frustratie besparen. Slimme gebruikers openen minder snel bijlagen of klikken op koppelingen in twijfelachtige e-mailberichten en ze vermijden dan waarschijnlijk verdachte websites. 

Het handboek [Marketingcampagne](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) van De Harvard School biedt uitstekende richtlijnen voor het creëren van een sterke cultuur van bekendheid met beveiliging binnen uw organisatie, waaronder training voor het identificeren van phishing-aanvallen. 

Microsoft 365 biedt de volgende informatiebronnen om gebruikers in uw organisatie op de hoogte te stellen:

|Concept  |Resources  |
|---------|---------|
|Microsoft 365     |[Aanpasbare leerroutes](https://docs.microsoft.com/office365/customlearning/) <p>Deze bronnen kunnen u helpen bij het organiseren van trainingen voor eindgebruikers in uw organisatie        |
|Microsoft 365-beveiliging |[Leermodule: Uw organisatie beveiligen met ingebouwde, intelligente beveiliging van Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>Met deze module kunt u beschrijven hoe Microsoft 365-beveiligingsfuncties samenwerken en de voordelen van deze beveiligingsfuncties duidelijk maken. |
|Meervoudige verificatie     | [Verificatie in twee stappen: Wat is de extra verificatiepagina?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Dit artikel helpt eindgebruikers te begrijpen wat meervoudige verificatie is en waarom deze in uw organisatie wordt gebruikt.    |

Naast deze richtlijnen raadt Microsoft uw gebruikers aan de acties uit te voeren die in dit artikel worden beschreven: Bescherm uw account en apparaten [tegen hackers en malware.](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx) Dit zijn onder andere de volgende acties:
- Sterke wachtwoorden gebruiken
- Apparaten beveiligen 
- Beveiligingsfuncties inschakelen op Windows 10- en Mac-pc's (voor niet-beherende apparaten)
    
Microsoft raadt gebruikers ook aan hun persoonlijke e-mailaccounts te beveiligen door de acties uit te voeren die worden aanbevolen in de volgende artikelen:
- [Uw e-mailaccount Outlook.com beveiligen](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [Uw Gmail-account beveiligen met verificatie in twee stappen](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
