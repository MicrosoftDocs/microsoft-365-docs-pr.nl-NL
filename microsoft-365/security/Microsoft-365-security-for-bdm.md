---
title: Microsoft 365 Security for Business Decision Makers (BDMs)
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
description: de meest voorkomende bedreigings- en aanvalsscenario's waarmee organisaties momenteel worden geconfronteerd voor hun Microsoft 365-omgevingen en aanbevolen acties om deze risico's te beperken.
ms.openlocfilehash: d03593059d473e96768e6dc3b2246fcda2ebc999
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809531"
---
# <a name="microsoft-365-security-for-business-decision-makers-bdms"></a>Microsoft 365 Security for Business Decision Makers (BDMs)

In dit artikel worden enkele van de meest voorkomende bedreigings- en aanvalsscenario's besproken waarmee organisaties momenteel worden geconfronteerd voor hun Microsoft 365-omgevingen en worden aanbevolen acties voor het beperken van deze risico's. Hoewel Microsoft 365 wordt geleverd met een breed scala aan vooraf geconfigureerde beveiligingsfuncties, vereist het ook dat u als klant verantwoordelijkheid neemt om uw eigen identiteit, gegevens en apparaten te beveiligen die worden gebruikt om toegang te krijgen tot cloudservices. Deze begeleiding is ontwikkeld door Kozeta Beam (Microsoft Cloud Security Architect) en Thiagaraj Sundararajan (Microsoft Senior Consultant).

Dit artikel wordt georganiseerd op basis van prioriteit van het werk, te beginnen met het beschermen van de accounts die worden gebruikt om de meest kritieke services en assets te beheren, zoals uw tenant, e-mail en SharePoint. Het biedt een methodische manier voor het benaderen van beveiliging en werkt samen met de volgende spreadsheet, zodat u uw voortgang bijhouden met belanghebbenden en teams in uw hele organisatie: [Microsoft 365-beveiliging voor BDMs-spreadsheet.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx) 

[![Spreadsheet duimafbeelding Microsoft 365 BDM-beveiligingsaanbevelingen](../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)

Microsoft biedt u het hulpprogramma Secure Score in uw tenant om uw beveiligingshouding automatisch te analyseren op basis van uw reguliere activiteiten, een score toe te wijzen en aanbevelingen voor beveiligingsverbetering te geven. Voordat u de in dit artikel aanbevolen acties onderneemt, neemt u nota van uw huidige score en aanbevelingen. De acties aanbevolen in dit artikel zal uw score te verhogen. Het doel is niet om de maximale score te bereiken, maar om bewust te zijn van mogelijkheden om uw omgeving te beschermen op een manier die de productiviteit voor uw gebruikers niet negatief beïnvloedt. Zie [Microsoft Secure Score](mtp/microsoft-secure-score.md).

Nog één ding voordat we beginnen. . . zorg ervoor dat u [het controlelogboek van Office 365 inschakelt](../compliance/search-the-audit-log-in-security-and-compliance.md). U hebt deze gegevens later nodig, in het geval dat u een incident of een inbreuk moet onderzoeken. 

## <a name="protect-privileged-accounts"></a>Bevoorrechte accounts beveiligen

Als eerste stap raden we aan ervoor te zorgen dat kritieke accounts in de omgeving een extra beschermingslaag krijgen, omdat deze accounts toegang en machtigingen hebben om kritieke services en resources te beheren en te wijzigen die een negatieve invloed kunnen hebben op de hele organisatie, indien gecompromitteerd. Het beschermen van geprivilegieerde accounts is een van de meest effectieve manieren om te beschermen tegen een aanvaller die de machtigingen van een gecompromitteerde account wil verhogen tot een administratief account. 

|Aanbeveling  |E3 |E5 E5  |
|---------|---------|---------|
|Afdwingen multi-factor authenticatie (MFA) voor alle administratieve accounts.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)| 
|Implementeer Azure Active Directory (Azure AD) Privileged Identity Management (PIM) om just-in-time bevoorrechte toegang toe te passen op Azure AD- en Azure-bronnen. U ook ontdekken wie toegang heeft tot bevoorrechte toegang en deze heeft beoordeeld.|         | ![groen vinkje](../media/green-check-mark.png)|
|Implementeer beheer met beheer voor privileged access in Office 365 om gedetailleerde toegangsbeheer over bevoorrechte beheertaken in Office 365 te beheren. |         | ![groen vinkje](../media/green-check-mark.png)|
|Configureer en gebruik Privileged Access Workstations (PAW) om services te beheren. Gebruik niet dezelfde werkstations voor het surfen op het internet en het controleren van e-mail die niet gerelateerd is aan uw administratieve account.|  ![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png) | 

Het volgende diagram illustreert deze mogelijkheden.
![Aanbevolen mogelijkheden voor het beschermen van bevoorrechte accounts](../media/m365-security-bdm-illustrations-privileged-accounts.png)

Aanvullende aanbevelingen:
- Zorg ervoor dat accounts die zijn gesynchroniseerd vanuit on-premises geen beheerdersrollen voor cloudservices toegewezen hebben. Dit helpt voorkomen dat een aanvaller on-premises accounts maakt om beheerderstoegang tot cloudservices te krijgen. 
- Zorg ervoor dat serviceaccounts geen beheerdersrollen toegewezen hebben. Deze accounts worden vaak niet gecontroleerd en ingesteld met wachtwoorden die niet verlopen. Zorg er eerst voor dat de AADConnect- en ADFS-servicesaccounts standaard geen globale beheerders zijn.
- Licenties verwijderen uit beheerdersaccounts. Tenzij er een specifieke use case is om licenties toe te wijzen aan specifieke beheerdersaccounts, verwijdert u licenties uit deze accounts. 

## <a name="reduce-the-surface-of-attack"></a>Het aanvalsoppervlak verminderen

De volgende focus gebied is het verminderen van het oppervlak van de aanval. Dit kan worden bereikt met minimale inspanning en impact op uw gebruikers en diensten. Door het oppervlak van de aanval te verminderen, hebben aanvallers minder manieren om een aanval op uw organisatie uit te voeren.

Dit zijn enkele voorbeelden:
- Schakel POP3-, IMAP- en SMTP-protocollen uit. De meeste moderne organisaties gebruiken deze oudere protocollen niet meer. U deze veilig uitschakelen en uitzonderingen alleen toestaan als dat nodig is. 
- Verminder en houd het aantal globale beheerders in de tenant tot het absolute minimum dat nodig is. Dit vermindert direct het oppervlak van de aanval voor alle Cloud-toepassingen. 
- Beheer servers en toepassingen die niet meer in uw omgeving worden gebruikt. 
- Implementeer een proces voor het uitschakelen en verwijderen van accounts die niet meer worden gebruikt. 

## <a name="protect-against-known-threats"></a>Beschermen tegen bekende bedreigingen

Bekende bedreigingen zijn malware, gecompromitteerde accounts en phishing. Sommige beveiligingen tegen deze bedreigingen kunnen snel worden geïmplementeerd zonder directe gevolgen voor uw gebruikers, terwijl andere meer planning en gebruikerstraining vereisen. 

|Aanbeveling  |E3  |E5 E5  |
|---------|---------|---------|
|**Multi-factor authenticatie instellen en aanbevolen beleid voor voorwaardelijke toegang gebruiken, inclusief aanmeldingsrisicobeleid.** Microsoft raadt en heeft een reeks beleidsregels getest die samenwerken om alle cloud-apps te beschermen, waaronder Office 365- en Microsoft 365-services. Zie [Identiteits- en apparaattoegangsconfiguraties](../enterprise/microsoft-365-policies-configurations.md). | |![groen vinkje](../media/green-check-mark.png)|
|**Vereisen multi-factor authenticatie voor alle gebruikers.** Als u niet beschikt over de vereiste licenties om het aanbevolen beleid voor voorwaardelijke toegang te implementeren, vereist u minimaal multi-factor authenticatie voor alle gebruikers.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Verhoog het niveau van bescherming tegen malware in e-mail.** Uw Office 365- of Microsoft 365-omgeving bevat bescherming tegen malware, maar u deze bescherming verhogen door bijlagen met bestandstypen te blokkeren die vaak worden gebruikt voor malware.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Bescherm uw e-mail tegen gerichte phishing-aanvallen.** Als u een of meer aangepaste domeinen hebt geconfigureerd voor uw Office 365- of Microsoft 365-omgeving, u gerichte anti-phishingbescherming configureren. ATP-anti-phishingbescherming, onderdeel van Office 365 Advanced Threat Protection, kan uw organisatie helpen beschermen tegen kwaadaardige phishingaanvallen op basis van imitatie en andere phishing-aanvallen. Als u een aangepast domein niet hebt geconfigureerd, hoeft u dit niet te doen.| |![groen vinkje](../media/green-check-mark.png)|
|**Bescherm tegen ransomware aanvallen in e-mail**. Ransomware neemt de toegang tot uw gegevens weg door bestanden te versleutelen of computerschermen te vergrendelen. Het probeert vervolgens om geld af te persen van slachtoffers door te vragen om "losgeld", meestal in de vorm van cryptocurrencies zoals Bitcoin, in ruil voor het retourneren van toegang tot uw gegevens. U helpen te verdedigen tegen ransomware door het creëren van een of meer mail flow regels om bestandsextensies die vaak worden gebruikt voor ransomware te blokkeren, of om gebruikers die deze bijlagen ontvangen in e-mail te waarschuwen.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Blokkeer verbindingen uit landen waarmee u geen zaken doet.** Maak een Azure AD-beleid voor voorwaardelijke toegang om verbindingen uit deze landen te blokkeren en maak effectief een geofirewall rond uw tenant.| |![groen vinkje](../media/green-check-mark.png)|

Het volgende diagram illustreert deze mogelijkheden.
![Aanbevolen mogelijkheden voor bescherming tegen bekende bedreigingen](../media/m365-security-bdm-illustrations-known-threats.png)

## <a name="protect-against-unknown-threats"></a>Beschermen tegen onbekende bedreigingen

Nadat u extra beveiligingen hebt toegevoegd aan uw bevoorrechte accounts en beschermt tegen bekende aanvallen, verschuift u uw aandacht naar bescherming tegen onbekende bedreigingen. De meer vastberaden en geavanceerde tegenstanders gebruiken innovatieve en nieuwe, onbekende methoden om organisaties aan te vallen. Met de enorme telemetrie van microsoft van gegevens die zijn verzameld over miljarden apparaten, toepassingen en services, kunnen we geavanceerde bedreigingsbeveiliging uitvoeren op Windows, Office 365 en Azure om zero day-aanvallen te voorkomen, waarbij gebruik wordt gemaakt van zandboxomgevingen en de geldigheid te controleren voordat u toegang geeft tot uw inhoud. 


|Aanbeveling  |E3  |E5 E5  |
|---------|---------|---------|
|**Office 365 Advanced Threat Protection (ATP) configureren:**<br>• ATP Veilige bijlagen<br>• ATP Veilige links<br>• ATP voor SharePoint, OneDrive en Microsoft Teams<br>• ATP anti-phishing bescherming|         |![groen vinkje](../media/green-check-mark.png) |
|**Configureer geavanceerde bedreigingsbeheermogelijkheden van Microsoft Defender:**<br>• Windows Defender Antivirus <br>• Bescherming benutten <br> • Vermindering van het oppervlak <br> • Op hardware gebaseerde isolatie <br>• Gecontroleerde toegang tot mappen     |         |![groen vinkje](../media/green-check-mark.png) |
|**Gebruik Microsoft Cloud App Security** om SaaS-apps te ontdekken en gedragsanalyses en anomaliedetectie te gebruiken. |         |![groen vinkje](../media/green-check-mark.png) |

Het volgende diagram illustreert deze mogelijkheden.
![Aanbevolen mogelijkheden voor bescherming tegen onbekende bedreigingen](../media/m365-security-bdm-illustrations-unknown-threats.png)

Aanvullende aanbevelingen:
- Beveiligde communicatie via partnerkanalen zoals e-mails met TLS.
- Open Teams Federation alleen voor partners waarmee u communiceert.
- Zet afzenderdomeinen, afzonderlijke afzenders of bron-IP's niet op de witte lijst, omdat deze hierdoor spam- en malwarecontroles kunnen omzeilen - Een gangbare praktijk met klanten is hun eigen geaccepteerde domeinen of een aantal andere domeinen waarop problemen met de e-mailstroom kunnen zijn Gemeld. Voeg geen domeinen toe in de lijst Spam- en verbindingsfilterfiltering, omdat dit mogelijk alle spamcontroles omzeilt. 
- Schakel uitgaande spammeldingen in : schakel uitgaande spammeldingen in op een distributielijst intern aan de Helpdesk of het IT-beheerdersteam om te rapporteren of een van de interne gebruikers spam-e-mails extern verzendt. Dit kan een indicator zijn dat de rekening is gecompromitteerd.
- Remote PowerShell uitschakelen voor alle gebruikers — Remote PowerShell wordt voornamelijk gebruikt door beheerders om toegang te krijgen tot Office 365-services voor administratieve doeleinden of programmatische API-toegang. We raden u aan deze optie uit te schakelen voor niet-beheerdersgebruikers om verkenning te voorkomen, tenzij ze een zakelijke vereiste hebben om er toegang toe te krijgen. 
- De toegang tot de Microsoft Azure Management-portal blokkeren voor alle niet-beheerders. U dit bereiken door een regel voor voorwaardelijke toegang te maken om alle gebruikers te blokkeren, met uitzondering van beheerders. 


## <a name="assume-breach"></a>Neem inbreuk aan

Hoewel Microsoft alle mogelijke maatregelen neemt om bedreigingen en aanvallen te voorkomen, raden we u aan altijd onder de mindset "Assume Breach" te werken. Zelfs als een aanvaller erin is geslaagd om de omgeving binnen te dringen, moeten we ervoor zorgen dat hij of zij geen gegevens of identiteitsgegevens uit de omgeving kan exfiltreren. Daarom raden we aan om bescherming tegen gevoelige gegevenslekken mogelijk te maken, zoals burgerservicenummers, creditcardnummers, aanvullende persoonlijke informatie en andere vertrouwelijke informatie op organisatieniveau. 

De "Assume Breach" mentaliteit vereist de uitvoering van een zero trust netwerk strategie, wat betekent dat gebruikers niet volledig vertrouwd zijn, alleen maar omdat ze intern zijn voor het netwerk. In plaats daarvan, als onderdeel van de autorisatie van wat gebruikers kunnen doen, worden sets van voorwaarden opgegeven en wanneer aan dergelijke voorwaarden is voldaan, worden bepaalde besturingselementen afgedwongen. Voorwaarden kunnen onder meer de status van apparaatstatus, toegang tot toepassingen, bewerkingen die worden uitgevoerd en gebruikersrisico's omvatten. Een apparaatinschrijvingsactie moet bijvoorbeeld altijd leiden tot MFA-verificatie om ervoor te zorgen dat er geen rouge-apparaten aan uw omgeving worden toegevoegd. 

Een zero trust netwerkstrategie vereist ook dat u weet waar uw gegevens worden opgeslagen en de juiste besturingselementen toepassen voor classificatie, bescherming en retentie. Om uw meest kritieke en gevoelige assets effectief te beschermen, moet u eerst identificeren waar deze zich bevinden en inventariseren, wat een uitdaging kan zijn. Werk vervolgens samen met uw organisatie om een governancestrategie te definiëren. Het definiëren van een classificatieschema voor een organisatie en het configureren van beleid, labels en voorwaarden vereist een zorgvuldige planning en voorbereiding. Het is belangrijk om te beseffen dat dit geen IT-gedreven proces is. Zorg ervoor dat u met uw juridische en complianceteam samenwerkt om een passend classificatie- en etiketteringsschema te ontwikkelen voor de gegevens van uw organisatie.

Microsoft 365-mogelijkheden voor informatiebescherming kunnen u helpen te ontdekken welke informatie u hebt, waar deze wordt opgeslagen en welke informatie extra bescherming vereist. Informatiebescherming is een continu proces en Microsoft 365-mogelijkheden bieden u inzicht in hoe gebruikers gevoelige informatie gebruiken en distribueren, waar uw gegevens momenteel worden opgeslagen en waar deze worden verspreid. U ook zien hoe gebruikers omgaan met informatie die is geregeld om er zeker van te zijn dat de juiste labels en beveiligingen worden toegepast.


|Aanbeveling |E3|E5 E5 |
|---------|---------|---------|
|**Uw voorwaardelijke toegang en bijbehorende beleid controleren en optimaliseren om af te stemmen op uw doelstellingen voor een netwerk zonder vertrouwen.** Bescherming tegen bekende bedreigingen omvat het implementeren van een reeks [aanbevolen beleidsregels](../enterprise/microsoft-365-policies-configurations.md). Bekijk uw implementatie van dit beleid om ervoor te zorgen dat u uw apps en gegevens beschermt tegen hackers die toegang hebben gekregen tot uw netwerk. Houd er rekening mee dat het aanbevolen beleid voor app-beveiliging van de Intune-app voor Windows 10 Windows Information Protection (WIP) mogelijk maakt. WIP beschermt tegen onbedoelde lekken van uw organisatiegegevens via apps en services, zoals e-mail, sociale media en de openbare cloud. |         |![groen vinkje](../media/green-check-mark.png)|
|**Externe e-maildoorschakelen uitschakelen**. Hackers die toegang krijgen tot het postvak van een gebruiker kunnen uw e-mail stelen door het postvak in te stellen om e-mail automatisch door te sturen. Dit kan zelfs gebeuren zonder het bewustzijn van de gebruiker. U dit voorkomen door een e-mailstroomregel te configureren.|![groen vinkje](../media/green-check-mark.png) |![groen vinkje](../media/green-check-mark.png)|
|**Automatisch extern agendadelen uitschakelen**. Extern anoniem delen van agenda's is standaard toegestaan. Schakel het delen van [agenda's uit](https://docs.microsoft.com/exchange/sharing/sharing-policies/modify-a-sharing-policy) om mogelijke lekken van gevoelige informatie te verminderen.|![groen vinkje](../media/green-check-mark.png) |![groen vinkje](../media/green-check-mark.png)|
|**Preventiebeleid voor gegevensverlies configureren voor gevoelige gegevens**. Maak een beleid voor het voorkomen van gegevensverlies in het Office 365-beveiligings- en nalevingscentrum om gevoelige gegevens zoals creditcardnummers, burgerservicenummers en bankrekeningnummers te ontdekken en te beschermen. Office 365 bevat veel vooraf gedefinieerde gevoelige informatietypen die u gebruiken in het preventiebeleid voor gegevensverlies. U ook uw eigen gevoelige informatietypen maken voor gevoelige gegevens die zijn aangepast aan uw omgeving. |![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Beleid voor gegevensclassificatie en informatiebescherming implementeren**. Implementeer gevoeligheidslabels in Office 365 en gebruik deze om gevoelige gegevens te classificeren en toe te passen. U deze labels ook gebruiken in het preventiebeleid voor gegevensverlies. Als u Azure Information Protection-labels gebruikt, raden we u aan geen nieuwe labels te maken in andere beheercentra.|         |![groen vinkje](../media/green-check-mark.png)|
|**Bescherm gegevens in apps en services van derden met cloudappbeveiliging.** Configureer het beveiligingsbeleid voor cloudapps om gevoelige informatie te beschermen in cloud-apps van derden, zoals Salesforce, Box of Dropbox. U gevoelige informatietypen en de gevoeligheidslabels die u hebt gemaakt in Office 365 gebruiken in het beveiligingsbeleid voor cloudapps en deze toepassen in uw SaaS-apps. <br><br>Met Microsoft Cloud App Security u een breed scala aan geautomatiseerde processen afdwingen. Beleidsregels kunnen worden ingesteld om continue nalevingsscans, wettelijke eDiscovery-taken, DLP voor gevoelige inhoud openbaar te maken en meer. Cloud App Security kan elk bestandstype controleren op basis van meer dan 20 metagegevensfilters (bijvoorbeeld toegangsniveau, bestandstype). |         |![groen vinkje](../media/green-check-mark.png)|
|**Gebruik [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/information-protection-in-windows-overview) om te bepalen of gebruikers gevoelige informatie opslaan op hun Windows-apparaten.** |         |![groen vinkje](../media/green-check-mark.png)|
|**Gebruik [AIP Scanner](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner) om informatie te identificeren en te classificeren op servers en bestandsshares.** Gebruik het AIP-rapportagetool om de resultaten te bekijken en passende maatregelen te nemen.|         |![groen vinkje](../media/green-check-mark.png)|

Het volgende diagram illustreert deze mogelijkheden.
![Aanbevolen mogelijkheden voor bescherming tegen inbreuk](../media/m365-security-bdm-illustrations-assume-breach.png)

## <a name="continuous-monitoring-and-auditing"></a>Continue monitoring en auditing

Last but not least continue monitoring en auditing van de Microsoft 365-omgeving samen met de Windows en Apparaten is van cruciaal belang om ervoor te zorgen dat u in staat bent om snel te detecteren en te herstellen eventuele inbraken. Tools zoals Secure Score, Security Center en geavanceerde analyses van Microsoft Intelligent Graph bieden waardevolle informatie aan uw tenant en koppelen enorme hoeveelheden informatie over bedreigingen en beveiligingsgegevens om u ongeëvenaarde bescherming tegen bedreigingen te bieden en detectie.


|Aanbeveling |E3 |E5 E5 |
|---------|---------|---------|
|Controleer of het **controlelogboek van Office 365** is ingeschakeld.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Wekelijks secure score controleren** - Beveiligde score is een centrale locatie om toegang te krijgen tot de beveiligingsstatus van uw Office 365-tenant en acties uit te voeren op basis van aanbevelingen voor beveiligde score. Het wordt aanbevolen om deze controle wekelijks uit te voeren.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Office 365** ATP-hulpprogramma's gebruiken:<br>• Bedreigingsonderzoeks- en reactiemogelijkheden<br> • Geautomatiseerd onderzoek en respons |         |![groen vinkje](../media/green-check-mark.png)|
|Microsoft **Defender ATP**gebruiken:<br> • [Endpoint detectie en respons](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) <br> • Geautomatiseerd onderzoek en herstel Veilige score <br>• [Geavanceerde jacht](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) <br>|         |![groen vinkje](../media/green-check-mark.png)|
|Gebruik **Microsoft Cloud App Security** om ongewoon gedrag in cloud-apps te detecteren om ransomware, gecompromitteerde gebruikers of malafide toepassingen te identificeren, gebruik met een hoog risico te analyseren en automatisch te herstellen om het risico voor uw organisatie te beperken.|         |![groen vinkje](../media/green-check-mark.png)|
|Gebruik **Microsoft Azure Sentinel** of uw huidige SIEM-tool om te controleren op bedreigingen in uw omgeving. |         |![groen vinkje](../media/green-check-mark.png)|
|**Implementeer [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) ** om bedreigingen te bewaken en te beschermen die zijn gericht op uw on-premises Active Directory-omgeving.   |         |![groen vinkje](../media/green-check-mark.png) |
|Gebruik het **Azure Security Center** om te controleren op bedreigingen voor hybride en cloudworkloads. Azure Security Center bevat een gratis niveau van mogelijkheden en een standaard niveau van mogelijkheden die worden betaald op basis van resourceuren of transacties.|         |         |

Het volgende diagram illustreert deze mogelijkheden.
![Aanbevolen mogelijkheden voor continue bewaking en controle](../media/m365-security-bdm-illustrations-monitoring-auditing.png)

Aanbevolen controleacties:
- **Microsoft Secure Score wekelijks controleren** - Beveiligde score is een centrale locatie om toegang te krijgen tot de beveiligingsstatus van uw Office 365-tenant en om acties uit te voeren op basis van de belangrijkste aanbevelingen. Het wordt aanbevolen om deze controle wekelijks uit te voeren. Secure Score bevat aanbevelingen van in heel Azure AD, Intune, Cloud App Security en Microsoft Defender Advanced Threat Protection, evenals Office 365. 
- **Bekijk wekelijks risicovolle aanmeldingen** : gebruik het Azure AD-beheercentrum om wekelijks risicovolle aanmeldingen te bekijken. De aanbevolen identiteits- en apparaattoegangsregelset bevat een beleid om wachtwoordwijziging af te dwingen op risicovolle aanmeldingen.  
- **Bekijk de beste malware en phished gebruikers wekelijks** - Gebruik Office Advanced Threat Protection Threat Explorer om top gebruikers gericht met malware en phish te herzien en om uit te vinden van de oorzaak van de reden waarom deze gebruikers worden beïnvloed.
