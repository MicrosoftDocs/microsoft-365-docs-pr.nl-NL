---
title: Microsoft 365 Security for Business Decision Makers (BDM's)
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: o365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: de meest voorkomende bedreigings- en aanvalsscenario's waarmee organisaties momenteel worden geconfronteerd voor hun Microsoft 365-omgevingen en aanbevolen acties om deze risico's te beperken.
ms.openlocfilehash: 894486951deac7e9c157409af8da5e813b53343b
ms.sourcegitcommit: 9ea67fd2e02af760d4fb62e3d09c93b446173f9d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/15/2020
ms.locfileid: "44739233"
---
# <a name="microsoft-365-security-for-business-decision-makers-bdms"></a>Microsoft 365 Security for Business Decision Makers (BDM's)

In dit artikel worden enkele van de meest voorkomende bedreigings- en aanvalsscenario's besproken waarmee organisaties momenteel worden geconfronteerd voor hun Microsoft 365-omgevingen en worden aanbevolen acties om deze risico's te beperken. Hoewel Microsoft 365 wordt geleverd met een breed scala aan vooraf geconfigureerde beveiligingsfuncties, vereist het ook dat u als klant verantwoordelijkheid neemt om uw eigen identiteit, gegevens en apparaten te beveiligen die worden gebruikt om toegang te krijgen tot cloudservices. Deze begeleiding is ontwikkeld door Kozeta Beam (Microsoft Cloud Security Architect) en Thiagaraj Sundararajan (Microsoft Senior Consultant).

Dit artikel is georganiseerd op prioriteit van het werk, te beginnen met het beveiligen van de accounts die worden gebruikt om de meest kritieke services en activa te beheren, zoals uw tenant, e-mail en SharePoint. Het biedt een methodische manier om beveiliging te benaderen en werkt samen met de volgende spreadsheet, zodat u uw voortgang bijhouden met belanghebbenden en teams in uw organisatie: [Microsoft 365-beveiliging voor BDM-spreadsheet.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx) 

[![Duimafbeelding Microsoft 365 BDM-beveiligingsaanbevelingen spreadsheet](../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)

Microsoft biedt u de Secure Score-tool binnen uw tenant om uw beveiligingshouding automatisch te analyseren op basis van uw reguliere activiteiten, een score toe te wijzen en aanbevelingen voor beveiligingsverbetering te doen. Voordat u de acties uitvoert die in dit artikel worden aanbevolen, moet u nota nemen van uw huidige score en aanbevelingen. De acties die in dit artikel worden aanbevolen, verhogen uw score. Het doel is niet om de maximale score te bereiken, maar om bewust te zijn van mogelijkheden om uw omgeving te beschermen op een manier die de productiviteit voor uw gebruikers niet negatief beïnvloedt. Zie [Microsoft Secure Score](mtp/microsoft-secure-score.md).

Nog één ding voordat we beginnen. . . zorg ervoor dat [u het controlelogboek inschakelt.](../compliance/search-the-audit-log-in-security-and-compliance.md) Je hebt deze gegevens later nodig, in het geval dat je een incident of een inbreuk moet onderzoeken. 

## <a name="protect-privileged-accounts"></a>Bevoorrechte accounts beveiligen

Als eerste stap raden we u aan ervoor te zorgen dat kritieke accounts in de omgeving een extra beveiligingslaag krijgen, omdat deze accounts toegang hebben en machtigingen hebben om kritieke services en resources te beheren en te wijzigen die een negatieve invloed kunnen hebben op de hele organisatie, als ze gecompromitteerd zijn. Het beschermen van bevoorrechte accounts is een van de meest effectieve manieren om te beschermen tegen een aanvaller die de machtigingen van een gecompromitteerd account wil verheffen tot een administratief account. 

|Aanbeveling  |E3 E3 |E5 E5  |
|---------|---------|---------|
|Multi-factor authentication (MFA) afdwingen voor alle administratieve accounts.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)| 
|Implementeer Azure Active Directory (Azure AD) Privileged Identity Management (PIM) om just-in-time privileged access toe te passen op Azure AD- en Azure-bronnen. U ook ontdekken wie toegang heeft en bevoorrechte toegang bekijken.|         | ![groen vinkje](../media/green-check-mark.png)|
|Implementeer privileged access management om gedetailleerde toegangscontrole te beheren over bevoorrechte beheerderstaken in Office 365. |         | ![groen vinkje](../media/green-check-mark.png)|
|Privileged Access Workstations (PAW) configureren en gebruiken om services te beheren. Gebruik niet dezelfde werkstations voor het surfen op internet en het controleren van e-mail die niet gerelateerd is aan uw administratieve account.|  ![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png) | 

In het volgende diagram worden deze mogelijkheden uitgelegd.
![Aanbevolen mogelijkheden voor het beveiligen van bevoorrechte accounts](../media/m365-security-bdm-illustrations-privileged-accounts.png)

Aanvullende aanbevelingen:
- Zorg ervoor dat accounts die vanaf on-premises worden gesynchroniseerd, geen beheerdersrollen voor cloudservices worden toegewezen. Dit voorkomt dat een aanvaller on-premises accounts kan gebruiken om toegang te krijgen tot cloudservices. 
- Zorg ervoor dat serviceaccounts geen beheerdersrollen worden toegewezen. Deze accounts worden vaak niet gecontroleerd en ingesteld met wachtwoorden die niet verlopen. Begin met ervoor te zorgen dat de AADConnect- en ADFS-servicesaccounts standaard geen globale beheerders zijn.
- Licenties verwijderen uit beheerdersaccounts. Tenzij er een specifieke use case is om licenties toe te wijzen aan specifieke beheerdersaccounts, verwijdert u licenties uit deze accounts. 

## <a name="reduce-the-surface-of-attack"></a>Verminder het oppervlak van de aanval

Het volgende focusgebied is het verminderen van het oppervlak van de aanval. Dit kan worden bereikt met minimale inspanning en impact voor uw gebruikers en services. Door het verminderen van het oppervlak van de aanval, aanvallers hebben minder manieren om een aanval tegen uw organisatie te lanceren.

Dit zijn enkele voorbeelden:
- Pop3-, IMAP- en SMTP-protocollen uitschakelen. De meeste moderne organisaties gebruiken deze oudere protocollen niet meer. U deze veilig uitschakelen en uitzonderingen alleen toestaan als dat nodig is. 
- Verminder en houd het aantal globale beheerders in de tenant tot het absolute minimum dat vereist is. Dit vermindert direct het oppervlak van de aanval voor alle Cloud-toepassingen. 
- Met pensioen gaan van servers en toepassingen die niet meer worden gebruikt in uw omgeving. 
- Implementeer een proces voor het uitschakelen en verwijderen van accounts die niet meer worden gebruikt. 

## <a name="protect-against-known-threats"></a>Beschermen tegen bekende bedreigingen

Bekende bedreigingen zijn malware, gecompromitteerde accounts en phishing. Sommige beveiligingen tegen deze bedreigingen kunnen snel worden geïmplementeerd zonder directe gevolgen voor uw gebruikers, terwijl andere meer planning en gebruikerstraining vereisen. 

|Aanbeveling  |E3 E3  |E5 E5  |
|---------|---------|---------|
|**Stel meerstapverificatie in en gebruik aanbevolen beleid voor voorwaardelijke toegang, inclusief aanmeldingsrisicobeleid.** Microsoft raadt aan en heeft een reeks beleidsregels getest die samenwerken om alle cloud-apps te beschermen, waaronder Office 365- en Microsoft 365-services. Zie [Configuraties voor identiteits- en apparaattoegang .](../enterprise/microsoft-365-policies-configurations.md) | |![groen vinkje](../media/green-check-mark.png)|
|**Vereisen multi-factor authenticatie voor alle gebruikers**. Als u niet over de licenties beschikt die nodig zijn om het aanbevolen beleid voor voorwaardelijke toegang te implementeren, moet minimaal meervoudige verificatie voor alle gebruikers worden vereist.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Verhoog het niveau van bescherming tegen malware in e-mail.** Uw Office 365- of Microsoft 365-omgeving biedt bescherming tegen malware, maar u deze bescherming verhogen door bijlagen te blokkeren met bestandstypen die vaak worden gebruikt voor malware.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Bescherm uw e-mail tegen gerichte phishing-aanvallen.** Als u een of meer aangepaste domeinen hebt geconfigureerd voor uw Office 365- of Microsoft 365-omgeving, u gerichte bescherming tegen phishing configureren. ATP-bescherming tegen phishing, onderdeel van Office 365 Advanced Threat Protection, kan uw organisatie beschermen tegen schadelijke imitatiegebaseerde phishing-aanvallen en andere phishing-aanvallen. Als u een aangepast domein nog niet hebt geconfigureerd, hoeft u dit niet te doen.| |![groen vinkje](../media/green-check-mark.png)|
|**Bescherm tegen ransomware aanvallen in e-mail**. Ransomware neemt de toegang tot uw gegevens weg door bestanden te versleutelen of computerschermen te vergrendelen. Het probeert vervolgens om geld af te persen van slachtoffers door te vragen om "losgeld", meestal in de vorm van cryptocurrencies zoals Bitcoin, in ruil voor terugkerende toegang tot uw gegevens. U helpen verdedigen tegen ransomware door het creëren van een of meer mail flow regels om bestandsextensies die vaak worden gebruikt voor ransomware te blokkeren, of om gebruikers die deze bijlagen ontvangen in e-mail te waarschuwen.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Blokkeer verbindingen uit landen waar u geen zaken mee doet.** Maak een Azure AD-beleid voor voorwaardelijke toegang om verbindingen uit deze landen te blokkeren en effectief een geofirewall rond uw tenant te maken.| |![groen vinkje](../media/green-check-mark.png)|

In het volgende diagram worden deze mogelijkheden uitgelegd.
![Aanbevolen mogelijkheden om te beschermen tegen bekende bedreigingen](../media/m365-security-bdm-illustrations-known-threats.png)

## <a name="protect-against-unknown-threats"></a>Beschermen tegen onbekende bedreigingen

Nadat u extra beveiligingen hebt toegevoegd aan uw bevoorrechte accounts en hebt beschermd tegen bekende aanvallen, verlegt u uw aandacht naar bescherming tegen onbekende bedreigingen. De meer vastberaden en gevorderde tegenstanders gebruiken innovatieve en nieuwe, onbekende methoden om organisaties aan te vallen. Met de enorme telemetrie van gegevens van Microsoft die over miljarden apparaten, toepassingen en services zijn verzameld, zijn we in staat om Geavanceerde bedreigingsbescherming uit te voeren op Windows, Office 365 en Azure om aanvallen op Zero Day te voorkomen, gebruik te maken van zandboxomgevingen en de geldigheid te controleren voordat we toegang tot uw inhoud toestaan. 


|Aanbeveling  |E3 E3  |E5 E5  |
|---------|---------|---------|
|**Office 365 Advanced Threat Protection (ATP) configureren:**<br>* ATP veilige bijlagen<br>* ATP Veilige Links<br>* ATP voor SharePoint, OneDrive en Microsoft Teams<br>* ATP anti-phishing bescherming|         |![groen vinkje](../media/green-check-mark.png) |
|**Geavanceerde beveiligingsmogelijkheden voor bedreigingen configureren:**<br>* Windows Defender Antivirus <br>* Exploit bescherming <br> * Aanval oppervlaktereductie <br> * Hardware-gebaseerde isolatie <br>* Gecontroleerde toegang tot mappen     |         |![groen vinkje](../media/green-check-mark.png) |
|**Gebruik Microsoft Cloud App Security** om SaaS-apps te ontdekken en gedragsanalyses en anomaliedetectie te gebruiken. |         |![groen vinkje](../media/green-check-mark.png) |

In het volgende diagram worden deze mogelijkheden uitgelegd.
![Aanbevolen mogelijkheden om te beschermen tegen onbekende bedreigingen](../media/m365-security-bdm-illustrations-unknown-threats.png)

Aanvullende aanbevelingen:
- Beveiligde communicatie via partnerkanaals, zoals e-mails met TLS.
- Open Teams Federatie alleen voor partners waarmee u communiceert.
- Voeg geen afzenderdomeinen, individuele afzenders of bron-IP's toe aan uw lijst met toestaan, omdat deze hiermee spam- en malwarecontroles kunnen omzeilen - Een gangbare praktijk bij klanten is het toevoegen van hun eigen geaccepteerde domeinen of een aantal andere domeinen waar problemen met de e-mailstroom mogelijk zijn gemeld aan de lijst met toestaan. Voeg geen domeinen toe in de lijst Spam- en Verbindingsfilters, omdat dit mogelijk alle spamcontroles omzeilt. 
- Uitgaande spammeldingen inschakelen : schakel uitgaande spammeldingen intern in een distributielijst in bij de Helpdesk of het IT-beheerdersteam om te melden of een van de interne gebruikers spam-e-mails extern verzendt. Dit kan een indicator zijn dat de rekening is gecompromitteerd.
- Externe PowerShell uitschakelen voor alle gebruikers - Remote PowerShell wordt voornamelijk gebruikt door beheerders om toegang te krijgen tot services voor administratieve doeleinden of programmatische API-toegang. We raden u aan deze optie uit te schakelen voor niet-beheerders om verkenning te voorkomen, tenzij ze een zakelijke vereiste hebben om toegang te krijgen tot deze optie. 
- De toegang tot de Microsoft Azure Management-portal blokkeren voor alle niet-beheerders. U dit bereiken door een regel voor voorwaardelijke toegang te maken om alle gebruikers te blokkeren, met uitzondering van beheerders. 


## <a name="assume-breach"></a>Ga uit van schending

Hoewel Microsoft alle mogelijke maatregelen neemt om bedreigingen en aanvallen te voorkomen, raden we u aan altijd te werken onder de "Assume Breach"-mentaliteit. Zelfs als een aanvaller erin is geslaagd om binnen te dringen in de omgeving, moeten we ervoor zorgen dat ze niet in staat zijn om gegevens of identiteitsgegevens uit de omgeving te exfiltreren. Daarom raden we u aan bescherming te bieden tegen gevoelige gegevenslekken zoals burgerservicenummers, creditcardnummers, aanvullende persoonlijke informatie en andere vertrouwelijke informatie op organisatieniveau. 

De "Assume Breach" mentaliteit vereist het implementeren van een zero trust netwerk strategie, wat betekent dat gebruikers niet volledig vertrouwd alleen maar omdat ze intern zijn om het netwerk. In plaats daarvan worden, als onderdeel van de autorisatie van wat gebruikers kunnen doen, sets van voorwaarden opgegeven en wanneer aan dergelijke voorwaarden wordt voldaan, worden bepaalde besturingselementen afgedwongen. Voorwaarden kunnen zijn apparaatstatus, toepassing die wordt geopend, bewerkingen worden uitgevoerd en risico van de gebruiker. Een apparaatinschrijvingsactie moet bijvoorbeeld altijd MFA-verificatie activeren om ervoor te zorgen dat er geen rouge-apparaten aan uw omgeving worden toegevoegd. 

Een zero trust-netwerkstrategie vereist ook dat u weet waar uw gegevens worden opgeslagen en dat u de juiste besturingselementen toepast voor classificatie, bescherming en retentie. Om uw meest kritieke en gevoelige activa effectief te beschermen, moet u eerst identificeren waar deze zich bevinden en inventariseren, wat een uitdaging kan zijn. Werk vervolgens samen met uw organisatie om een governancestrategie te definiëren. Het definiëren van een classificatieschema voor een organisatie en het configureren van beleid, labels en voorwaarden vereist een zorgvuldige planning en voorbereiding. Het is belangrijk om te beseffen dat dit geen IT-gedreven proces is. Zorg ervoor dat u samenwerkt met uw juridische en compliance-team om een geschikt classificatie- en etiketteringsschema voor de gegevens van uw organisatie te ontwikkelen.

Microsoft 365-mogelijkheden voor informatiebescherming kunnen u helpen te ontdekken welke informatie u hebt, waar deze wordt opgeslagen en welke informatie extra bescherming vereist. Informatiebescherming is een continu proces en Microsoft 365-mogelijkheden bieden u inzicht in hoe gebruikers gevoelige informatie gebruiken en distribueren, waar uw informatie momenteel wordt opgeslagen en waar deze zich bevindt. U ook zien hoe gebruikers omgaan met informatie die is gereguleerd om er zeker van te zijn dat de juiste labels en beveiligingen worden toegepast.


|Aanbeveling |E3 E3|E5 E5 |
|---------|---------|---------|
|**Controleer en optimaliseer uw voorwaardelijke toegang en bijbehorend beleid om af te stemmen op uw doelstellingen voor een zero trust-netwerk.** Bescherming tegen bekende bedreigingen omvat het implementeren van een reeks [aanbevolen beleidsregels](../enterprise/microsoft-365-policies-configurations.md). Controleer uw implementatie van dit beleid om ervoor te zorgen dat u uw apps en gegevens beschermt tegen hackers die toegang hebben gekregen tot uw netwerk. Houd er rekening mee dat het aanbevolen beveiligingsbeleid voor Intune-apps voor Windows 10 Windows Information Protection (WIP) mogelijk maakt. WIP beschermt tegen onbedoelde lekken van uw organisatiegegevens via apps en services, zoals e-mail, sociale media en de openbare cloud. |         |![groen vinkje](../media/green-check-mark.png)|
|**Externe e-mail doorsturen uitschakelen**. Hackers die toegang krijgen tot het postvak van een gebruiker kunnen uw e-mail stelen door het postvak in te stellen om automatisch e-mail door te sturen. Dit kan zelfs gebeuren zonder het bewustzijn van de gebruiker. U dit voorkomen door een e-mailstroomregel te configureren.|![groen vinkje](../media/green-check-mark.png) |![groen vinkje](../media/green-check-mark.png)|
|**Anoniem delen van externe agenda's uitschakelen**. Het standaard delen van externe anonieme agenda's is toegestaan. [Schakel het delen van agenda's uit](https://docs.microsoft.com/exchange/sharing/sharing-policies/modify-a-sharing-policy) om mogelijke lekken van gevoelige informatie te verminderen.|![groen vinkje](../media/green-check-mark.png) |![groen vinkje](../media/green-check-mark.png)|
|**Beleid voor het voorkomen van gegevensverlies configureren voor gevoelige gegevens.** Maak een beleid voor het voorkomen van gegevensverlies in het Security &amp; Compliance Center om gevoelige gegevens zoals creditcardnummers, burgerservicenummers en bankrekeningnummers te ontdekken en te beschermen. Microsoft 365 bevat veel vooraf gedefinieerde gevoelige informatietypen die u gebruiken in het beleid voor het voorkomen van gegevensverlies. U ook uw eigen gevoelige informatietypen maken voor gevoelige gegevens die zijn aangepast aan uw omgeving. |![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Implementeer het beleid voor gegevensclassificatie en informatiebescherming**. Implementeer gevoeligheidslabels en gebruik deze om bescherming te classificeren en toe te passen op gevoelige gegevens. U deze labels ook gebruiken in het beleid voor het voorkomen van gegevensverlies. Als u Azure Information Protection-labels gebruikt, raden we u aan geen nieuwe labels in andere beheercentra te maken.|         |![groen vinkje](../media/green-check-mark.png)|
|**Bescherm gegevens in apps en services van derden met behulp van Cloud App Security.** Configureer het beveiligingsbeleid voor Cloud App om gevoelige informatie te beschermen in cloud-apps van derden, zoals Salesforce, Box of Dropbox. U gevoelige informatietypen en de gevoeligheidslabels die u hebt gemaakt in het beveiligingsbeleid voor Cloud App gebruiken en deze toepassen in uw SaaS-apps. <br><br>Met Microsoft Cloud App Security u een breed scala aan geautomatiseerde processen afdwingen. Beleid kan worden ingesteld om continue nalevingsscans, legale eDiscovery-taken, DLP voor gevoelige inhoud die openbaar wordt gedeeld, en meer te bieden. Cloud App Security kan elk bestandstype controleren op basis van meer dan 20 metagegevensfilters (bijvoorbeeld toegangsniveau, bestandstype). |         |![groen vinkje](../media/green-check-mark.png)|
|**Gebruik [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/information-protection-in-windows-overview) om te bepalen of gebruikers gevoelige informatie opslaan op hun Windows-apparaten**. |         |![groen vinkje](../media/green-check-mark.png)|
|**Gebruik [AIP-scanner](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner) om informatie te identificeren en te classificeren tussen servers en bestandsshares.** Gebruik het AIP-rapportageprogramma om de resultaten te bekijken en passende acties te ondernemen.|         |![groen vinkje](../media/green-check-mark.png)|

In het volgende diagram worden deze mogelijkheden uitgelegd.
![Aanbevolen mogelijkheden om te beschermen tegen inbreuken](../media/m365-security-bdm-illustrations-assume-breach.png)

## <a name="continuous-monitoring-and-auditing"></a>Continue monitoring en auditing

Last but not least Continue Monitoring and Auditing of the Microsoft 365 environment along with the Windows and Devices is critical to sure to sure you are able to quickly detect and remediate any intrusions. Tools zoals Secure Score, Security Center en geavanceerde analyses van Microsoft Intelligent Graph bieden waardevolle informatie in uw tenant en koppelen enorme hoeveelheden bedreigingsinformatie en beveiligingsgegevens om u ongeëvenaarde bedreigingsbescherming en detectie te bieden.


|Aanbeveling |E3 E3 |E5 E5 |
|---------|---------|---------|
|Controleer of het **controlelogboek** is ingeschakeld.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Controleer de beveiligde score wekelijks** - Secure score is een centrale locatie om toegang te krijgen tot de beveiligingsstatus van uw bedrijf en acties uit te voeren op basis van aanbevelingen voor de secure score. Het wordt aanbevolen om deze controle wekelijks uit te voeren.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|Gebruik **Office 365** ATP-hulpprogramma's:<br>* Threat investigation en response mogelijkheden<br> * Geautomatiseerd onderzoek en reactie |         |![groen vinkje](../media/green-check-mark.png)|
|Microsoft **Defender ATP gebruiken:**<br> *    [Eindpuntdetectie en -respons](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) <br> * Geautomatiseerd onderzoek en sanering Secure score <br>*    [Geavanceerde jacht](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) <br>|         |![groen vinkje](../media/green-check-mark.png)|
|Gebruik **Microsoft Cloud App Security** om ongebruikelijk gedrag in cloud-apps te detecteren om ransomware, gecompromitteerde gebruikers of malafide toepassingen te identificeren, hoog risicogebruik te analyseren en automatisch te herstellen om het risico voor uw organisatie te beperken.|         |![groen vinkje](../media/green-check-mark.png)|
|Gebruik **Microsoft Azure Sentinel** of uw huidige SIEM-tool om te controleren op bedreigingen in uw omgeving. |         |![groen vinkje](../media/green-check-mark.png)|
|**Implementeer [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) ** om te controleren en te beschermen tegen bedreigingen die zijn gericht op uw on-premises Active Directory-omgeving.   |         |![groen vinkje](../media/green-check-mark.png) |
|Gebruik het **Azure Security Center** om te controleren op bedreigingen voor hybride en cloudworkloads. Azure Security Center bevat een gratis serviceniveau en een standaardniveau voor mogelijkheden waarvoor wordt betaald op basis van resourceuren of transacties.|         |         |

In het volgende diagram worden deze mogelijkheden uitgelegd.
![Aanbevolen mogelijkheden voor continue monitoring en auditing](../media/m365-security-bdm-illustrations-monitoring-auditing.png)

Aanbevolen bestradingsacties:
- **Bekijk microsoft secure score wekelijks** - Secure score is een centrale locatie om toegang te krijgen tot de beveiligingsstatus van uw tenant en om acties te ondernemen op basis van topaanbevelingen. Het wordt aanbevolen om deze controle wekelijks uit te voeren. Secure Score bevat aanbevelingen van in Azure AD, Intune, Cloud App Security en Microsoft Defender Advanced Threat Protection, evenals Office 365. 
- **Bekijk wekelijks riskante aanmeldingen** : gebruik het Azure AD-beheercentrum om wekelijks riskante aanmeldingen te bekijken. De aanbevolen regelset voor identiteits- en apparaattoegang bevat een beleid om wachtwoordwijzigingen af te dwingen bij riskante aanmeldingen.  
- **Bekijk wekelijks top malware en phished gebruikers** - Gebruik Office Advanced Threat Protection Threat Explorer om topgebruikers gericht met malware en phish te beoordelen en om uit te vinden waarom deze gebruikers worden beïnvloed.
