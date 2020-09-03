---
title: Stappen voor het configureren van functies voor beveiliging tegen bedreigingen in Microsoft 365
description: Meer informatie over het implementeren van Threat Protection-Services en-functies in Microsoft 365 E5.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: a5f3f93ad70210143cbe774c2a4e96542b1cfd34
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332674"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>Functies voor bedreigingsbeveiliging configureren in Microsoft 365

Ga als volgt te werk om de beveiliging van bedreigingen te configureren in Microsoft 365.


## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>Stap 1: multi-factor Authentication en regels voor voorwaardelijke toegang instellen

Voor [multi-factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) moeten gebruikers hun identiteit verifiëren met een telefoongesprek of Authenticator-app. [Regels voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) definiëren bepaalde vereisten waaraan moet worden voldaan om gebruikers toegang te bieden tot apps en gegevens in microsoft 365. MFA en regels voor voorwaardelijke toegang samenwerken om uw organisatie te beveiligen. Als iemand bijvoorbeeld probeert zich aan te melden vanaf een mobiel apparaat met een account dat niet is ingeschakeld voor MFA, en als voor een voorwaardelijk toegangsbeleid een MFA moet worden gebruikt, is het mogelijk dat de gebruiker zich niet kan aanmelden.  

Microsoft heeft een specifieke set voorwaardelijke toegang en gerelateerde beleidsregels getest voor de bescherming van de toegang tot alle SaaS-toepassingen, met name Microsoft 365. Beleidsregels worden aanbevolen voor basislijn-, gevoelige en sterk gereguleerde bescherming. Begin met het implementeren van de beleidsregels voor basisbescherming. 


[ ![ Veelgebruikte beleidsregels voor het configureren van de identiteit en Apparaattoegang bieden](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [een grotere versie van deze afbeelding weer](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>Basislijn beveiliging voor Microsoft 365 implementeren

![Basisbeginselen voor de implementatie van basislijn beveiliging](../media/solutions-architecture-center/deploy-threat-protection-identity-access-steps.png) 

1. [Vereisten configureren, waaronder Azure identiteits bescherming](../enterprise/identity-access-prerequisites.md).
2. [Veelgebruikte beleidsregels voor identiteit en Apparaattoegang configureren](../enterprise/identity-access-policies.md) voor basisbescherming.
3. Beleidsregels configureren voor [gastgebruikers](../enterprise/identity-access-policies-guest-access.md), [Microsoft teams](../enterprise/teams-access-policies.md), [Exchange Online](../enterprise/secure-email-recommended-policies.md)en [SharePoint Online en OneDrive](../enterprise/sharepoint-file-access-policies.md).

### <a name="more-information-about-protecting-identities"></a>Meer informatie over het beveiligen van identiteiten

- [Configuratie van identiteiten en apparaattoegang](../enterprise/microsoft-365-policies-configurations.md)
- [Beveiligingsrichtlijnen voor Azure MFA](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-azure-advanced-threat-protection"></a>Stap 2: Azure Advanced Threat Protection configureren

[Azure Advanced Threat Protection](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) (Azure ATP) is een op de cloud gebaseerde beveiligingsoplossing die geschikt is voor uw on-premises [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) -signalen voor het identificeren, detecteren en onderzoeken van geavanceerde bedreigingen, compromisloze identiteiten en schadelijke Insider-acties die u in uw organisatie kunt gebruiken.

Azure ATP schakelt beveiligingsactiviteiten (SecOps) analisten en beveiligings professionals struggling uit om geavanceerde aanvallen in hybride omgevingen te detecteren voor:
- Toezicht van gebruikers, entiteits gedrag en activiteiten met analyses op basis van Learning.
- Gebruikersidentiteiten en -referenties beveiligen die zijn opgeslagen in Active Directory.
- Verdachte gebruikersactiviteiten en geavanceerde aanvallen in de hele kill chain identificeren en onderzoeken.
- Heldere incidentinformatie verstrekken op een eenvoudige tijdlijn voor snelle sortering.

### <a name="to-set-up-azure-atp"></a>Azure ATP instellen

![Installatie van Azure ATP voorbereiden](../media/solutions-architecture-center/deploy-azure-atp-steps.png) 

1. [Azure ATP instellen](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) om uw primaire omgeving te beschermen.
2. Beveilig al uw [domeincontrollers](https://docs.microsoft.com/azure-advanced-threat-protection/atp-sensor-monitoring) en [forests](https://docs.microsoft.com/azure-advanced-threat-protection/atp-multi-forest).
3. [Azure ATP-waarschuwingen](https://docs.microsoft.com/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) in uw SecOps-werkstroom (beveiligingsbewerkingen) integreren.

### <a name="more-information-about-azure-atp"></a>Meer informatie over Azure ATP

- [Wat is Azure ATP?](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Video: Inleiding tot Azure ATP](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Azure ATP-implementatie](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-threat-protection"></a>Stap 3: Microsoft Threat Protection inschakelen

[Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) combineert signalen en biedt mogelijkheden in één oplossing. Met de geïntegreerde oplossing voor Microsoft Threat Protection kunnen beveiligings medewerkers de bedreigings signalen samenstellen die elk van deze producten ontvangen en bepalen wat het volledige bereik en de impact van de bedreiging zijn. de werking van de omgeving, wat van invloed is op de omgeving, en de werking van de organisatie. Microsoft Threat Protection beslaat automatische actie om de aanval te voorkomen of te stoppen, en de desbetreffende postvakken, eindpunten en gebruikers-id's.

Microsoft Threat Protection beveiligt waarschuwingen, incidenten, geautomatiseerd onderzoek en antwoord en een geavanceerde jacht van de werkbelasting (Azure ATP, Office 365 ATP, Microsoft Defender ATP en de beveiliging van Microsoft Cloud apps) in één venster van glas. Wanneer u een of meer van uw Advanced Threat Protection-Services hebt geconfigureerd, schakelt u Microsoft Threat Protection in. Nieuwe functies worden continu toegevoegd aan Microsoft Threat Protection. u kunt ook kiezen voor het ontvangen van Voorbeeldfuncties.

### <a name="to-set-up-microsoft-threat-protection"></a>Microsoft Threat Protection instellen

![Installatie van Microsoft Threat Protection](../media/solutions-architecture-center/deploy-mtp-steps.png) 

1. [Controleer de vereisten](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites).
2. [Schakel Microsoft Threat Protection in](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable).
3. Deel de optie [voor Voorbeeldfuncties](https://docs.microsoft.com/microsoft-365/security/mtp/preview).

### <a name="more-information-about-microsoft-threat-protection"></a>Meer informatie over Microsoft Threat Protection

- [Wat is Microsoft Threat Protection?](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [Wat is er nieuw in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)

## <a name="step-4-configure-office-365-advanced-threat-protection"></a>Stap 4: Office 365 Advanced Threat Protection configureren

[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) beschermt uw organisatie tegen kwaadaardige bedreigingen in e-mailberichten (bijlagen en url's), Office-documenten en samenwerkingsprogramma's. De volgende tabel bevat een overzicht van de functies en mogelijkheden van Office 365 ATP die zijn opgenomen in Microsoft 365 E5:

|Functies voor configuratie, beveiliging en detectie|Automatiserings-, onderzoek-, herstel-en onderwijs mogelijkheden|
|---|---|
|[Veilige bijlagen](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br/>[Veilige koppelingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)<br/>[Veilige documenten](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)<br/>[ATP voor SharePoint, OneDrive en Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)<br/>[ATP-bescherming tegen phishing](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#exclusive-settings-in-atp-anti-phishing-policies)|[Bedreigingsoverzichten](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-trackers)<br/>[Bedreigingsverkenner](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)<br/>[Geautomatiseerd onderzoek en reactie](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>[Aanvalssimulator](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)|
|

Met Office 365 ATP kunnen medewerkers in uw organisatie veiliger communiceren en samenwerken met behulp van bedreigingsbeveiliging voor hun e-mail inhoud en Office-documenten.

### <a name="to-set-up-office-365-atp"></a>Office 365 ATP instellen

![Installatie van Office 365 ATP voorbereiden](../media/solutions-architecture-center/deploy-office365-atp-steps.png) 

1. [Stel uw Office 365 ATP-beleid in en configureer](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)dit.
2. [Uw Office 365 ATP-rapporten weergeven en gebruiken](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).
3. [Gebruik functies voor het onderzoek en antwoord van bedreigingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti).

### <a name="more-information-about-office-365-atp"></a>Meer informatie over Office 365 ATP

- [Overzicht van Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Nieuw in Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

## <a name="step-5-configure-microsoft-defender-advanced-threat-protection"></a>Stap 5: Microsoft Defender Advanced Threat Protection configureren

Met [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP) beschermt u uw organisatie apparaten (ook wel eindpunten genoemd) van cyberthreats, geavanceerde aanvallen en schending van gegevens. Beveiligings teams kunnen efficiënter werken met het beheren van de beveiliging van hun eindpunten. Krachtige hulpmiddelen helpt organisaties bij het beschermen van systemen met een beveiligingslek via de detectie van beveiligingsproblemen met het [beheer van bedreiging en](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)risico. Geautomatiseerde detectie-en herstelmogelijkheden, zoals [aanval via een aanval](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction), de detectie van de [volgende generatie](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10), het detecteren van het [eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)en het beantwoorden van het [automatische onderzoek en herstel](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) zorgen ervoor dat uw apparatuur veilig is tegen malware. Met de beste van deze mogelijkheden kunnen klanten proactief meldingen ontvangen en via Microsoft Threat experts raadplegen op aanvraag, als onderdeel van de beheerde service voor het aangaan van een abonnement. 


### <a name="set-up-microsoft-defender-atp"></a>Microsoft Defender ATP instellen

![Installatie van Microsoft Defender ATP voorbereiden](../media/solutions-architecture-center/deploy-mdatp-steps.png) 

1. [Uw Microsoft Defender ATP-implementatie voorbereiden](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases).
2. [Uw implementatie van Microsoft Defender ATP instellen](https://docs.microsoft.com/windows/security/threat-protection/micros.oft-defender-atp/production-deployment)
3. [Onboarding to the Microsoft Defender ATP service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboarding).
4. [Voltooi de belangrijkste beveiligingstaken](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation).

### <a name="more-information-about-microsoft-defender-atp"></a>Meer informatie over Microsoft Defender ATP

- [Meer informatie over Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection).
- [Probeer het Microsoft Defender ATP-evaluatie lab](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluation-lab).

## <a name="step-6-configure-microsoft-cloud-app-security"></a>Stap 6: beveiliging van de Microsoft Cloud app configureren

[Microsoft Cloud-app-beveiliging](https://docs.microsoft.com/cloud-app-security) is een beveiligings Broker voor Cloud toegang die de logboekverzameling, API-connectors en omgekeerde proxy ondersteunt. De beveiliging van de Microsoft Cloud-app biedt uitgebreide zichtbaarheid, controle over gegevens reizen en geavanceerde analyses voor het identificeren en bestrijden van cyberthreats in alle Cloud Services. Met de beveiliging van de Microsoft Cloud-app kunnen uw beveiligingsactiviteiten de gevoelige informatie van uw organisatie beschermen, de bescherming tegen cyberthreats en anomalie afwijkingen, ontdekken en controleren welke apps toegang krijgen tot de gegevens van uw organisatie en ervoor zorgen dat de Cloud-apps van uw organisatie aan nalevingsvereisten voldoen.

### <a name="set-up-microsoft-cloud-app-security"></a>Beveiligingsinstellingen voor Microsoft Cloud-app instellen

![Installatie van de Microsoft Cloud app-beveiliging](../media/solutions-architecture-center/deploy-mcas-steps.png) 

1. [Stel de portal en andere basisvereisten](https://docs.microsoft.com/cloud-app-security/general-setup)in.
2. Apps Discovery en Connect- [apps](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps) [instellen](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery) .
3. [Besturingselement voor voorwaardelijke toegang implementeren voor aanbevolen apps](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad).
4. [Gebruik de hulpmiddelen en dashboards voor onderzoek](https://docs.microsoft.com/cloud-app-security/investigate).

### <a name="more-information-about-microsoft-cloud-app-security"></a>Meer informatie over Microsoft Cloud App Security

- [Bekijk de nieuwe functies en mogelijkheden](https://docs.microsoft.com/cloud-app-security/release-notes).
- Meer [informatie over beveiliging van de Microsoft Cloud-app](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).

## <a name="step-7-monitor-status-and-take-actions"></a>Stap 7: status controleren en acties ondernemen

Nadat u de services en functies van bedreigingsbeveiliging hebt geconfigureerd en geïmplementeerd, is de volgende stap het controleren van bedreigings detectie en het uitvoeren van de juiste acties. Uw beste uitgangspunt is het Microsoft 365-Beveiligingscentrum ( [https://security.microsoft.com](https://security.microsoft.com) ), waarin u de beveiliging kunt controleren en beheren in uw Microsoft-identiteiten, gegevens, apparaten, apps en infrastructuur. 

![Microsoft 365-beveiligingscentrum](../media/solutions-architecture-center/m365-security-center.png)

Het Microsoft 365-Beveiligingscentrum is specifiek bedoeld voor beveiligingsbeheerders en beveiligingsbewerkingen teams. In Microsoft 365 Beveiligingscentrum kunt u het volgende doen:
- Bekijk de algehele beveiligingsstatus van uw organisatie met behulp van [Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).
- [Bewaak rapporten](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting) over de status van uw identiteiten, gegevens, apparaten, apps en infrastructuur.
- Verbind de punten met meldingen via [incidenten](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue).
- Gebruik [automatisch onderzoek en herstel](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir) om bedreigingen te verhelpen.
- U kunt op elk gewenst apparaat [bedreigingen zoeken](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview), zoals aanvallen via een indringer of een overtreding van activiteiten die van invloed zijn op uw e-mailberichten, gegevens, apparaten en identiteiten.
- [Begrijpt de nieuwste aanvals campagnes](https://docs.microsoft.com/microsoft-365/security/mtp/latest-attack-campaigns) en-technieken met Threat Analytics.
- ... en nog veel meer.

### <a name="more-information-about-the-microsoft-365-security-center"></a>Meer informatie over het Microsoft 365-Beveiligingscentrum

- [Ga aan de slag met Microsoft 365 Beveiligingscentrum](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center).
- [Rapporten bijhouden en weergeven](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting).
- [Zie de beveiligings portals in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/portals).

## <a name="step-8-train-users"></a>Stap 8: gebruikers trainen

Gebruikers kunnen gebruikers en beveiligingsactiviteiten team veel tijd en frustraties bewaren. Gebruikers met een betrouwbare gebruikers hebben minder waarschijnlijk bijlagen te openen, of klik op koppelingen in dubieuze e-mailberichten, en het is waarschijnlijk dat ze verdachte websites vermijden. 

The Harvard Kennedy School [Cyber Security Campaign Handbook](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) biedt uitstekende richtlijnen voor het vaststellen van een sterke cultuur voor beveiliging binnen uw organisatie, waaronder gebruikers van de opleiding waarmee u phishing-aanvallen kunt identificeren. 

Microsoft 365 biedt de volgende bronnen om gebruikers in uw organisatie op de hoogte te stellen:

|Definitie  |Resources  |
|---------|---------|
|Microsoft 365     |[Aanpasbare leer paden](https://docs.microsoft.com/office365/customlearning/) <p>Deze informatiebronnen kunnen u helpen bij het samenvoegen van trainingen voor eindgebruikers in uw organisatie.        |
|Microsoft 365-beveiliging |[Leermodule: Beveilig uw organisatie met ingebouwde, intelligente beveiliging van Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>In deze module kunt u beschrijven hoe Microsoft 365 beveiligingsfuncties samenwerken en de voordelen van deze beveiligingsfuncties gelen. |
|Meervoudige verificatie     | [Verificatie in twee stappen: wat is de pagina extra verificatie?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Dit artikel helpt eindgebruikers inzicht te krijgen in een meervoudige verificatie en hoe deze worden gebruikt in uw organisatie.    |

Naast deze richtlijnen wordt door Microsoft aanbevolen dat uw gebruikers de in dit artikel beschreven acties uitvoeren: [uw account en apparaten beschermen tegen hackers en malware](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx). Dit zijn de volgende acties:
- Sterke wachtwoorden gebruiken
- Apparaten beschermen 
- Beveiligingsfuncties inschakelen op computers met Windows 10 en Mac (voor niet-beheerde apparaten)
    
Microsoft adviseert gebruikers hun persoonlijke e-mailaccounts ook te beschermen door de acties uit te voeren die worden aanbevolen in de volgende artikelen:
- [Uw e-mailaccount van Outlook.com helpen beschermen](https://support.microsoft.com/en-us/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [Uw Gmail-account beschermen met verificatie in twee stappen](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
