---
title: Mogelijkheden voor bedreigingsbescherming implementeren in Microsoft 365
description: Meer informatie over het implementeren van services en mogelijkheden voor bedreigingsbescherming in Microsoft 365 E5.
ms.author: bcarter
author: brendacarter
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365solutions
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: ee3acf0729920f1ab4fdaa3fb79b2b541a7a608b
ms.sourcegitcommit: a3ec91423c352cd5fbf79b46ccd9c169455a03ba
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44664596"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>Mogelijkheden voor bedreigingsbescherming implementeren in Microsoft 365

[Malware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware), en geavanceerde cyberaanvallen, zoals [fileless bedreigingen](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats), komen vaak voor. Bedrijven moeten zichzelf en hun klanten beschermen. Dergelijke aanvallen kunnen grote problemen veroorzaken voor uw organisatie, variërend van verlies van vertrouwen tot financiële ellende, bedrijfsbedreigende downtime en meer. Bescherming tegen bedreigingen is belangrijk, maar het kan een uitdaging zijn om te bepalen waar u de tijd, moeite en middelen van uw organisatie richten. 

Microsoft-beveiligingsoplossingen zijn ingebouwd in onze producten en services. Automatiserings- en machine learning-mogelijkheden verminderen de belasting van uw beveiligingsteams om ervoor te zorgen dat de juiste items worden aangepakt. En de kracht van Microsoft-beveiligingsoplossingen is gebaseerd op triljoenen signalen die we dagelijks verwerken in onze [Intelligent Security Graph.](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph) Microsoft 365-beveiligingsoplossingen omvatten [Microsoft Threat Protection,](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)een oplossing die signalen over uw e-mail, gegevens, apparaten en identiteiten samenbrengt om een beeld te schetsen van geavanceerde bedreigingen tegen uw organisatie.

Bekijk deze video voor een overzicht van het implementatieproces.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

Gebruik dit artikel als een handleiding voor het implementeren van uw oplossing voor bedreigingsbescherming.

## <a name="threat-protection-in-microsoft-365-e5"></a>Bescherming tegen bedreigingen in Microsoft 365 E5

[Met Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) u uw organisatie beschermen met adaptieve, ingebouwde intelligentie. Met de functies voor bedreigingsbescherming in Microsoft 365 E5 u geavanceerde bedreigingen, gecompromitteerde identiteiten en schadelijke acties in uw on-premises en cloudomgevingen detecteren en onderzoeken.

In Microsoft 365 E5 zijn de mogelijkheden voor bedreigingsbescherming standaard geïntegreerd. Signalen van elke mogelijkheid voegen kracht toe aan het algemene vermogen om bedreigingen te detecteren en erop te reageren. De gecombineerde reeks mogelijkheden biedt de beste bescherming voor organisaties, met name multinationale organisaties, in vergelijking met het uitvoeren van niet-Microsoft-producten. De volgende afbeelding toont de bedreigingenbeschermingsservices en -mogelijkheden in Microsoft 365 E5 die in dit artikel worden beschreven.

![Overzicht van microsoft-bedreigingsbeveiliging](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

Zodra u een van de geavanceerde mogelijkheden voor bedreigingsbescherming implementeert, u Microsoft Threat Protection inschakelen, waardoor de signalen en gegevens op één plaats worden samengebracht. 

![Conceptuele illustratie van het dashboard van Microsoft Threat Protection](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

In de volgende afbeelding wordt een aanbevolen pad weergegeven voor het implementeren van deze afzonderlijke mogelijkheden. 

![M365 bedreigingsbeschermingssignalen](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|Oplossing/mogelijkheden  |Beschrijving  |
|---------|---------|
|Meervoudige verificatie en voorwaardelijke toegang     |Bescherm tegen gecompromitteerde identiteiten en apparaten. Begin met deze bescherming omdat het fundamenteel is. De in deze richtlijnen aanbevolen configuratie bevat Azure AD Identity Protection als voorwaarde.     |
|Azure Advanced Threat Protection     |  Een cloudgebaseerde beveiligingsoplossing die uw on-premises Active Directory-signalen gebruikt om geavanceerde bedreigingen, gecompromitteerde identiteiten en schadelijke insider-acties gericht op uw organisatie te identificeren, te detecteren en te onderzoeken. Focus op deze volgende omdat het beschermt uw on-prem en uw cloud-infrastructuur, heeft geen afhankelijkheden of vereisten, en kan onmiddellijk voordeel bieden.       | 
|Office 365 Advanced Threat Protection     | Beschermt uw organisatie tegen schadelijke bedreigingen van e-mailberichten, koppelingen (URL's) en samenwerkingstools. Beveiligingen voor malware, phishing, spoofing en andere soorten aanvallen. Dit wordt vervolgens aanbevolen omdat het implementeren van het besturingselement wijzigen, migreren van het bestaande systeem en andere overwegingen langer kunnen duren. <br><br>Opmerking: Zorg ervoor dat u ook de mogelijkheden voor bedreigingsbeveiliging configureert die zijn opgenomen in alle Office 365-abonnementen (Exchange Online Protection).       |
|Microsoft Defender Advanced Threat Protection    | Een endpoint protection platform dat helpt bij het voorkomen, detecteren, onderzoeken en reageren op geavanceerde bedreigingen. Dit duurt langer om te implementeren, maar kan parallel met de andere mogelijkheden worden gedaan als andere beheerders verantwoordelijk zijn.   |
|Microsoft Cloud App Security     |   Een cloudtoegangsbeveiligingsmakelaar voor detectie, onderzoek en governance. U dit vroeg mogelijk maken om te beginnen met het verzamelen van gegevens en inzichten. Het implementeren van informatie en andere gerichte beveiliging in uw SaaS-apps houdt planning in en kan meer tijd in beslag nemen.       | 

> [!TIP]
> Organisaties met meerdere beveiligingsteams kunnen deze mogelijkheden parallel implementeren.

## <a name="deploy-your-threat-protection-solution"></a>Uw oplossing voor bedreigingsbescherming implementeren

Om ervoor te zorgen dat uw organisatie over de best mogelijke beveiliging beschikt, stelt u uw beveiligingsoplossing in en implementeer deze om de volgende stappen op te nemen:

1. [Beleid voor meerstapverificatie en beleid voor voorwaardelijke toegang instellen](#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Azure Advanced Threat Protection configureren](#step-2-configure-azure-advanced-threat-protection)
3. [Microsoft Threat Protection inschakelen](#step-3-turn-on-microsoft-threat-protection)
4. [Geavanceerde bedreigingsbeveiliging van Office 365 configureren](#step-4-configure-office-365-advanced-threat-protection)
5. [Geavanceerde bedreigingsbeveiliging van Microsoft Defender configureren](#step-5-configure-microsoft-defender-advanced-threat-protection)
6. [Beveiliging van Microsoft Cloud App configureren](#step-6-configure-microsoft-cloud-app-security)
7. [Status bewaken en acties uitvoeren](#step-7-monitor-status-and-take-actions)
8. [Treingebruikers](#step-8-train-users)

Uw functies voor bedreigingsbeveiliging kunnen parallel worden geconfigureerd, dus als u meerdere beveiligingsteams hebt die verantwoordelijk zijn voor verschillende services, kunnen ze tegelijkertijd de beveiligingsfuncties van uw organisatie configureren. In het volgende diagram wordt het proces op hoog niveau voor het implementeren van mogelijkheden voor bedreigingsbescherming weergedrukt. 

![Proces voor het implementeren van mogelijkheden voor bedreigingsbescherming](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 

## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>Stap 1: Meerstapverificatie en beleid voor voorwaardelijke toegang instellen

[Multi-factor authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) vereist dat gebruikers hun identiteit verifiëren met een telefoongesprek of authenticator-app. [Voorwaardentoegangsbeleid](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) definieert bepaalde vereisten waaraan moet worden voldaan om gebruikers toegang te geven tot apps en gegevens in Microsoft 365. MFA- en beleid voor voorwaardelijke toegang werken samen om uw organisatie te beschermen. Als iemand zich bijvoorbeeld probeert aan te melden vanaf een mobiel apparaat met een account dat niet is ingeschakeld voor MFA en een beleid voor voorwaardelijke toegang vereist dat MFA van kracht is, kan die gebruiker zich niet aanmelden.  

Microsoft heeft een specifieke set voorwaardelijke toegang en bijbehorend beleid getest en aanbevolen om de toegang tot al uw SaaS-toepassingen, met name Microsoft 365, te beschermen. Beleid wordt aanbevolen voor basislijn,gevoelige en sterk gereguleerde bescherming. Begin met het implementeren van het beleid voor basislijnbescherming. 


[ ![ Gemeenschappelijk beleid voor het configureren van identiteit en apparaattoegang](../media/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/Identity_device_access_policies_byplan.png) 
 [Zie een grotere versie van deze afbeelding](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>Basislijnbeveiliging implementeren voor Microsoft 365

![Proces voor het implementeren van mogelijkheden voor bedreigingsbescherming](../media/solutions-architecture-center/deploy-threat-protection-identity-access-steps.png) 

1. [Voorwaarden configureren, waaronder Azure Identity Protection](../enterprise/identity-access-prerequisites.md).
2. [Algemene toegangsbeleid voor identiteits- en apparaattoegang configureren](../enterprise/identity-access-policies.md) voor basislijnbeveiliging.
3. Beleid configureren voor [gastgebruikers](../enterprise/identity-access-policies-guest-access.md), [Microsoft Teams,](../enterprise/teams-access-policies.md) [Exchange Online](../enterprise/secure-email-recommended-policies.md)en [SharePoint Online en OneDrive](../enterprise/sharepoint-file-access-policies.md).

### <a name="more-information-about-protecting-identities"></a>Meer informatie over het beschermen van identiteiten

- [Configuratie van identiteiten en apparaattoegang](../enterprise/microsoft-365-policies-configurations.md)
- [Beveiligingsrichtlijnen voor Azure MFA](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-azure-advanced-threat-protection"></a>Stap 2: Azure Advanced Threat Protection configureren

[Azure Advanced Threat Protection](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) (Azure ATP) is een cloudgebaseerde beveiligingsoplossing die werkt met uw on-premises [Azure Active Directory-signalen](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) om geavanceerde bedreigingen, gecompromitteerde identiteiten en schadelijke insider-acties gericht op uw organisatie te identificeren, te detecteren en te onderzoeken.

Azure ATP stelt analisten en beveiligingsprofessionals (Security Operations) in staat om geavanceerde aanvallen in hybride omgevingen te detecteren om:
- Monitor gebruikers, entiteitsgedrag en activiteiten met op leer gebaseerde analyses.
- Gebruikersidentiteiten en -referenties beveiligen die zijn opgeslagen in Active Directory.
- Verdachte gebruikersactiviteiten en geavanceerde aanvallen in de hele kill chain identificeren en onderzoeken.
- Heldere incidentinformatie verstrekken op een eenvoudige tijdlijn voor snelle sortering.

### <a name="to-set-up-azure-atp"></a>Azure ATP instellen

![Proces voor het implementeren van mogelijkheden voor bedreigingsbescherming](../media/solutions-architecture-center/deploy-azure-atp-steps.png) 

1. [Azure ATP instellen](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) om uw primaire omgevingen te beschermen.
2. Bescherm al uw [domeincontrollers](https://docs.microsoft.com/azure-advanced-threat-protection/atp-sensor-monitoring) en [forests.](https://docs.microsoft.com/azure-advanced-threat-protection/atp-multi-forest)
3. Integreer [Azure ATP-waarschuwingen](https://docs.microsoft.com/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) in uw SecOps-workflow (Security Operations).

### <a name="more-information-about-azure-atp"></a>Meer informatie over Azure ATP

- [Wat is Azure ATP?](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Video: Inleiding tot Azure ATP](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Azure ATP-implementatie](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-threat-protection"></a>Stap 3: Microsoft-bedreigingsbeveiliging inschakelen

[Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) combineert signalen en orkestreert mogelijkheden in één oplossing. Met de geïntegreerde Microsoft Threat Protection-oplossing kunnen beveiligingsprofessionals de dreigingssignalen aan elkaar naaien die elk van deze producten ontvangt en de volledige reikwijdte en impact van de dreiging bepalen; hoe het in de omgeving is terechtgekomen, wat het heeft beïnvloed en hoe het momenteel van invloed is op de organisatie. Microsoft Threat Protection neemt automatisch actie om de aanval te voorkomen of te stoppen en de getroffen mailboxen, eindpunten en gebruikersidentiteiten zelf te genezen.

Microsoft Threat Protection verenigt waarschuwingen, incidenten, geautomatiseerd onderzoek en respons en geavanceerde jacht op workloads (Azure ATP, Office 365 ATP, Microsoft Defender ATP en Microsoft Cloud App Security) tot één glaservaring. Nadat u een of meer geavanceerde services voor bedreigingsbescherming hebt geconfigureerd, schakelt u Microsoft Threat Protection in. Nieuwe functies worden voortdurend toegevoegd aan Microsoft Threat Protection; overwegen om in te gaan op preview-functies te ontvangen.

### <a name="to-set-up-microsoft-threat-protection"></a>Microsoft-bedreigingsbeveiliging instellen

![Proces voor het implementeren van mogelijkheden voor bedreigingsbescherming](../media/solutions-architecture-center/deploy-mtp-steps.png) 

1. [Bekijk de vereisten](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites).
2. [Schakel Microsoft Threat Protection in](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable).
3. [Meld u aan voor voorbeeldfuncties.](https://docs.microsoft.com/microsoft-365/security/mtp/preview)

### <a name="more-information-about-microsoft-threat-protection"></a>Meer informatie over Microsoft Threat Protection

- [Wat is Microsoft Threat Protection?](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [Wat is er nieuw in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)

## <a name="step-4-configure-office-365-advanced-threat-protection"></a>Stap 4: Geavanceerde bedreigingsbeveiliging van Office 365 configureren

[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) beschermt uw organisatie tegen schadelijke bedreigingen in e-mailberichten (bijlagen en URL's), Office-documenten en samenwerkingshulpprogramma's. In de volgende tabel worden Office 365 ATP-functies en -mogelijkheden weergegeven die zijn opgenomen in Microsoft 365 E5:

|||
|---|---|
|Configuratie-, beveiligings- en detectiemogelijkheden|Automatiserings-, onderzoeks-, sanerings- en onderwijsmogelijkheden|
|[Veilige bijlagen](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br/>[Veilige koppelingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)<br/>[Veilige documenten](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)<br/>[ATP voor SharePoint, OneDrive en Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)<br/>[ATP-bescherming tegen phishing](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#exclusive-settings-in-atp-anti-phishing-policies)|[Bedreigingsoverzichten](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-trackers)<br/>[Bedreigingsverkenner](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)<br/>[Geautomatiseerd onderzoek en reactie](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>[Aanvalssimulator](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)|
|

Met Office 365 ATP kunnen mensen in uw organisatie veiliger communiceren en samenwerken, met bescherming tegen bedreigingen voor hun e-mailinhoud en Office-documenten.

### <a name="to-set-up-office-365-atp"></a>Office 365 ATP instellen

![Proces voor het implementeren van mogelijkheden voor bedreigingsbescherming](../media/solutions-architecture-center/deploy-office365-atp-steps.png) 

1. [Uw ATP-beleid voor Office 365 instellen en configureren](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).
2. [Uw ATP-rapporten voor Office 365 weergeven en gebruiken](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).
3. [Gebruik mogelijkheden voor dreigingsonderzoek en -respons](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti).

### <a name="more-information-about-office-365-atp"></a>Meer informatie over Office 365 ATP

- [AtP-overzicht van Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Nieuw in Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

## <a name="step-5-configure-microsoft-defender-advanced-threat-protection"></a>Stap 5: Microsoft Defender Advanced Threat Protection configureren

[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP) beschermt de apparaten van uw organisaties (ook wel endpoints genoemd) tegen cyberbedreigingen, geavanceerde aanvallen en datalekken. Beveiligingsteams kunnen efficiënter de beveiliging van hun eindpunten beheren. Robuuste tools helpen organisaties om ongepatchte systemen bij te houden met behulp van kwetsbaarheidsdetectie met [bedreigings- en kwetsbaarheidsbeheer.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Geautomatiseerde detectie- en herstelmogelijkheden, zoals [vermindering van het aanvalsoppervlak,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction) [bescherming van de volgende generatie,](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) [detectie en respons op eindpunten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)en [geautomatiseerd onderzoek en herstel](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) helpen uw apparaten te beschermen tegen malware. Naast deze mogelijkheden kunnen klanten proactieve meldingen ontvangen en on demand contact opnemen met Microsoft Threat Experts, als onderdeel van de opt-in managed hunting-service. 


### <a name="set-up-microsoft-defender-atp"></a>Atp van Microsoft Defender instellen

![Proces voor het implementeren van mogelijkheden voor bedreigingsbescherming](../media/solutions-architecture-center/deploy-mdatp-steps.png) 

1. [Bereid uw ATP-implementatie van Microsoft Defender voor](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases).
2. [Uw ATP-implementatie van Microsoft Defender instellen](https://docs.microsoft.com/windows/security/threat-protection/micros.oft-defender-atp/production-deployment)
3. [Aan boord van de Microsoft Defender ATP-service.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboarding)
4. [Voltooi uw belangrijkste beveiligingsbeheertaken.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)

### <a name="more-information-about-microsoft-defender-atp"></a>Meer informatie over Microsoft Defender ATP

- [Meer informatie over Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection).
- [Probeer het Microsoft Defender ATP-evaluatielab](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluation-lab).

## <a name="step-6-configure-microsoft-cloud-app-security"></a>Stap 6: Beveiliging van Microsoft Cloud App configureren

[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) is een Cloud Access Security Broker die logboekverzameling, API-connectors en reverse proxy ondersteunt. Microsoft Cloud App Security biedt een rijke zichtbaarheid, controle over gegevensreizen en geavanceerde analyses om cyberbedreigingen in al uw cloudservices te identificeren en te bestrijden. Met Microsoft Cloud App Security kunnen uw beveiligingsactiviteiten de gevoelige informatie van uw organisatie beschermen, beschermen tegen cyberbedreigingen en afwijkingen, apps ontdekken en bewaken die toegang hebben tot de gegevens van uw organisatie en ervoor zorgen dat de cloud-apps van uw organisatie voldoen aan de nalevingsvereisten.

### <a name="set-up-microsoft-cloud-app-security"></a>Beveiliging van Microsoft Cloud App instellen

![Proces voor het implementeren van mogelijkheden voor bedreigingsbescherming](../media/solutions-architecture-center/deploy-mcas-steps.png) 

1. [Stel het portaal en andere basisvereisten in.](https://docs.microsoft.com/cloud-app-security/general-setup)
2. [Clouddetectie instellen](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery) en [apps verbinden](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).
3. [Voorwaardelijke toegangs-app-besturingselement implementeren voor aanbevolen apps](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad).
4. [Gebruik de onderzoekstools en dashboards](https://docs.microsoft.com/cloud-app-security/investigate).

### <a name="more-information-about-microsoft-cloud-app-security"></a>Meer informatie over Microsoft Cloud App Security

- [Bekijk nieuwe functies en mogelijkheden.](https://docs.microsoft.com/cloud-app-security/release-notes)
- [Meer informatie over Beveiliging van Microsoft Cloud App](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).

## <a name="step-7-monitor-status-and-take-actions"></a>Stap 7: Status bewaken en acties uitvoeren

Nadat u uw services en mogelijkheden voor bedreigingsbescherming hebt ingesteld en geïmplementeerd, is uw volgende stap het bewaken van bedreigingsdetecties en het nemen van passende acties. Uw beste startpunt is het Microsoft 365-beveiligingscentrum ( [https://security.microsoft.com](https://security.microsoft.com) ), waar u de beveiliging bewaken en beheren voor uw Microsoft-identiteiten, gegevens, apparaten, apps en infrastructuur. 

:::image type="content" source="../media/solutions-architecture-center/m365-security-center.png" alt-text="Microsoft 365-beveiligingscentrum":::

Het Microsoft 365-beveiligingscentrum is specifiek bedoeld voor beveiligingsbeheerders en beveiligingsteams. In het Microsoft 365-beveiligingscentrum u heten:
- Bekijk de algehele beveiligingsstatus van uw organisatie met [Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).
- [Rapporten controleren en bekijken](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting) over de status van uw identiteit, gegevens, apparaten, apps en infrastructuur.
- Sluit de punten op waarschuwingen door middel van [incidenten](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue).
- Gebruik [geautomatiseerd onderzoek en herstel om](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir) bedreigingen aan te pakken.
- [Ga proactief op zoek naar bedreigingen,](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview)zoals inbraakpogingen of inbreukactiviteiten die uw e-mail, gegevens, apparaten en identiteiten beïnvloeden.
- [Begrijp de nieuwste aanvalscampagnes](https://docs.microsoft.com/microsoft-365/security/mtp/latest-attack-campaigns) en -technieken met threat analytics.
- ... en meer!

### <a name="more-information-about-the-microsoft-365-security-center"></a>Meer informatie over het Microsoft 365-beveiligingscentrum

- [Ga aan de slag met het Microsoft 365-beveiligingscentrum](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center).
- [Rapporten bewaken en bekijken](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting).
- [Bekijk de beveiligingsportalen in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/portals).

## <a name="step-8-train-users"></a>Stap 8: Treingebruikers

Trainingsgebruikers kunnen uw gebruikers en beveiligingsteam veel tijd en frustratie besparen. Savvy gebruikers hebben minder kans om bijlagen te openen of te klikken op links in twijfelachtige e-mailberichten, en ze hebben meer kans om verdachte websites te voorkomen. 

Het Harvard Kennedy School [Cybersecurity Campaign Handbook](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) biedt uitstekende richtlijnen voor het creëren van een sterke cultuur van beveiligingsbewustzijn binnen uw organisatie, inclusief het trainen van gebruikers om phishing-aanvallen te identificeren. 

Microsoft 365 biedt de volgende bronnen om gebruikers in uw organisatie te informeren:

|Concept  |Resources  |
|---------|---------|
|Microsoft 365     |[Aanpasbare leertrajecten](https://docs.microsoft.com/office365/customlearning/) <p>Met deze bronnen u training samenstellen voor eindgebruikers in uw organisatie        |
|Microsoft 365-beveiliging |[Leermodule: beveilig uw organisatie met ingebouwde, intelligente beveiliging van Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>Met deze module u beschrijven hoe Microsoft 365-beveiligingsfuncties samenwerken en de voordelen van deze beveiligingsfuncties verwoorden. |
|Meervoudige verificatie     | [Verificatie in twee stappen: Wat is de extra verificatiepagina?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Dit artikel helpt eindgebruikers te begrijpen wat multi-factor authenticatie is en waarom het wordt gebruikt in uw organisatie.    |

Naast deze richtlijnen raadt Microsoft uw gebruikers aan de in dit artikel beschreven acties uit te voeren: [Bescherm uw account en apparaten tegen hackers en malware.](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx) Deze acties omvatten:
- Sterke wachtwoorden gebruiken
- Apparaten beveiligen 
- Beveiligingsfuncties inschakelen op Windows 10- en Mac-pc's (voor onbeheerde apparaten)
    
Microsoft raadt gebruikers ook aan hun persoonlijke e-mailaccounts te beschermen door de in de volgende artikelen aanbevolen acties uit te voeren:
- [Help uw Outlook.com e-mailaccount te beschermen](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [Bescherm je Gmail-account met verificatie in twee stappen](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
