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
ms.openlocfilehash: c153b94b450b834687e83f39fc7179e0dda1a21f
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943565"
---
# <a name="microsoft-365-security-for-business-decision-makers-bdms"></a>Microsoft 365 Security for Business Decision Makers (BDM's)

In dit artikel worden enkele van de meest voorkomende bedreigings- en aanvalsscenario's besproken waarmee organisaties momenteel worden geconfronteerd voor hun Microsoft 365-omgevingen en worden aanbevolen acties om deze risico's te beperken. Hoewel Microsoft 365 wordt geleverd met een breed scala aan vooraf geconfigureerde beveiligingsfuncties, vereist het ook dat u als klant de verantwoordelijkheid neemt om uw eigen identiteit, gegevens en apparaten te beveiligen die worden gebruikt om toegang te krijgen tot cloudservices. Deze begeleiding is ontwikkeld door Kozeta Beam (Microsoft Cloud Security Architect) en Thiagaraj Sundararajan (Microsoft Senior Consultant).

Dit artikel is georganiseerd op basis van prioriteit van het werk, te beginnen met het beschermen van de accounts die worden gebruikt om de meest kritieke services en -assets te beheren, zoals uw tenant, e-mail en SharePoint. Het biedt een methodische manier om de beveiliging te benaderen en werkt samen met de volgende spreadsheet, zodat u uw voortgang bijhouden met belanghebbenden en teams in uw organisatie: [Microsoft 365-beveiliging voor BDMs-spreadsheet.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx) 

[![Duimafbeelding Microsoft 365 BDM-beveiligingsaanbevelingen spreadsheet](../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)

Microsoft biedt u de Secure Score-tool in uw tenant om uw beveiligingshouding automatisch te analyseren op basis van uw reguliere activiteiten, een score toe te wijzen en aanbevelingen voor beveiligingsverbetering te geven. Neem de in dit artikel aanbevolen acties op, voordat u rekening houdt met uw huidige score en aanbevelingen. De acties die in dit artikel worden aanbevolen, verhogen uw score. Het doel is niet om de maximale score te bereiken, maar om je bewust te zijn van mogelijkheden om uw omgeving te beschermen op een manier die de productiviteit voor uw gebruikers niet negatief beïnvloedt. Zie [Microsoft Secure Score](mtp/microsoft-secure-score.md).

Nog één ding voordat we beginnen. . . zorg ervoor dat [u het controlelogboek inschakelt.](../compliance/search-the-audit-log-in-security-and-compliance.md) U hebt deze gegevens later nodig, in het geval u een incident of een inbreuk moet onderzoeken. 

## <a name="protect-privileged-accounts"></a>Bevoorrechte accounts beveiligen

Als eerste stap raden we aan ervoor te zorgen dat kritieke accounts in de omgeving een extra beveiligingslaag krijgen, omdat deze accounts toegang en machtigingen hebben voor het beheren en wijzigen van kritieke services en resources die een negatieve invloed kunnen hebben op de hele organisatie, als ze worden gecompromitteerd. Het beveiligen van bevoegde accounts is een van de meest effectieve manieren om te beschermen tegen een aanvaller die de machtigingen van een gecompromitteerd account wil verhogen naar een administratief account. 

|Aanbeveling  |E3 |E5  |
|---------|---------|---------|
|Multi-factor authentication (MFA) afdwingen voor alle beheerdersaccounts.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)| 
|Implementeer Azure Active Directory (Azure AD) Privileged Identity Management (PIM) om just-in-time bevoorrechte toegang toe te passen tot Azure AD- en Azure-bronnen. U ook ontdekken wie toegang heeft tot bevoegde toegang en deze bekijken.|         | ![groen vinkje](../media/green-check-mark.png)|
|Implementeer privileged access management om gedetailleerde toegangsbeheer te beheren over bevoegde beheertaken in Office 365. |         | ![groen vinkje](../media/green-check-mark.png)|
|Configureer en gebruik Paws (Privileged Access Workstations) om services te beheren. Gebruik niet dezelfde werkstations voor het surfen op het internet en het controleren van e-mail die niet gerelateerd is aan uw beheerdersaccount.|  ![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png) | 

Het volgende diagram illustreert deze mogelijkheden.
![Aanbevolen mogelijkheden voor het beveiligen van bevoegde accounts](../media/m365-security-bdm-illustrations-privileged-accounts.png)

Aanvullende aanbevelingen:
- Zorg ervoor dat accounts die zijn gesynchroniseerd vanuit on-premises, geen beheerdersrollen toegewezen krijgen voor cloudservices. Dit helpt voorkomen dat een aanvaller gebruik maakt van on-premises accounts om administratieve toegang te krijgen tot cloudservices. 
- Zorg ervoor dat serviceaccounts geen beheerdersrollen toegewezen krijgen. Deze accounts worden vaak niet gecontroleerd en ingesteld met wachtwoorden die niet verlopen. Begin met ervoor te zorgen dat de AADConnect- en ADFS-servicesaccounts standaard geen globale beheerders zijn.
- Licenties verwijderen uit beheerdersaccounts. Tenzij er een specifieke gebruiksaanvraag is om licenties toe te wijzen aan specifieke beheerdersaccounts, verwijdert u licenties uit deze accounts. 

## <a name="reduce-the-surface-of-attack"></a>Verminder het oppervlak van de aanval

Het volgende aandachtsgebied is het verminderen van het oppervlak van de aanval. Dit kan worden bereikt met minimale inspanning en impact op uw gebruikers en diensten. Door het oppervlak van de aanval te verkleinen, hebben aanvallers minder manieren om een aanval op uw organisatie uit te voeren.

Dit zijn enkele voorbeelden:
- Schakel POP3-, IMAP- en SMTP-protocollen uit. De meeste moderne organisaties gebruiken deze oudere protocollen niet meer. U deze veilig uitschakelen en uitzonderingen alleen toestaan als dat nodig is. 
- Verminder en houd het aantal globale beheerders in de tenant tot het absolute minimum dat vereist is. Dit vermindert direct het oppervlak van de aanval voor alle Cloud-toepassingen. 
- Servers en toepassingen die niet meer in uw omgeving worden gebruikt, in trekken. 
- Implementeer een proces voor het uitschakelen en verwijderen van accounts die niet meer worden gebruikt. 

## <a name="protect-against-known-threats"></a>Beschermen tegen bekende bedreigingen

Bekende bedreigingen zijn malware, gecompromitteerde accounts en phishing. Sommige beveiligingen tegen deze bedreigingen kunnen snel worden geïmplementeerd zonder directe gevolgen voor uw gebruikers, terwijl andere meer planning en gebruikerstraining vereisen. 

|Aanbeveling  |E3  |E5  |
|---------|---------|---------|
|**Stel multi-factor authenticatie in en gebruik aanbevolen beleid voor voorwaardelijke toegang, inclusief aanmeldingsrisicobeleid**. Microsoft raadt en heeft een reeks beleidsregels getest die samenwerken om alle cloud-apps, waaronder Office 365- en Microsoft 365-services, te beschermen. Zie [Configuraties voor identiteits- en apparaattoegangs .](../enterprise/microsoft-365-policies-configurations.md) | |![groen vinkje](../media/green-check-mark.png)|
|**Multifactorauthenticatie vereisen voor alle gebruikers.** Als u niet beschikt over de licenties die nodig zijn om het aanbevolen beleid voor voorwaardelijke toegang te implementeren, moet u minimaal multifactorauthenticatie vereisen voor alle gebruikers.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Verhoog het niveau van bescherming tegen malware in e-mail.** Uw Office 365- of Microsoft 365-omgeving bevat bescherming tegen malware, maar u deze bescherming verhogen door bijlagen te blokkeren met bestandstypen die vaak worden gebruikt voor malware.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Bescherm uw e-mail tegen gerichte phishing-aanvallen.** Als u een of meer aangepaste domeinen hebt geconfigureerd voor uw Office 365- of Microsoft 365-omgeving, u gerichte antiphishingbeveiliging configureren. ATP-bescherming tegen phishing, onderdeel van Office 365 Advanced Threat Protection, kan uw organisatie beschermen tegen schadelijke phishing-aanvallen en andere phishing-aanvallen. Als u geen aangepast domein hebt geconfigureerd, hoeft u dit niet te doen.| |![groen vinkje](../media/green-check-mark.png)|
|**Beschermen tegen ransomware aanvallen in e-mail.** Ransomware neemt toegang tot uw gegevens weg door bestanden te versleutelen of computerschermen te vergrendelen. Het probeert vervolgens om geld af te persen van slachtoffers door te vragen om "losgeld", meestal in de vorm van cryptocurrencies zoals Bitcoin, in ruil voor het retourneren van toegang tot uw gegevens. U helpen beschermen tegen ransomware door het creëren van een of meer mail flow regels om bestandsextensies die vaak worden gebruikt voor ransomware te blokkeren, of om gebruikers die deze bijlagen ontvangen in e-mail te waarschuwen.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Blokkeer verbindingen uit landen waar u geen zaken mee doet.** Maak een azure AD-beleid voor voorwaardelijke toegang om verbindingen uit deze landen te blokkeren en effectief een geofirewall rond uw tenant te maken.| |![groen vinkje](../media/green-check-mark.png)|

Het volgende diagram illustreert deze mogelijkheden.
![Aanbevolen mogelijkheden om te beschermen tegen bekende bedreigingen](../media/m365-security-bdm-illustrations-known-threats.png)

## <a name="protect-against-unknown-threats"></a>Beschermen tegen onbekende bedreigingen

Nadat u extra beveiligingen aan uw bevoegde accounts hebt toegevoegd en bescherming hebt tegen bekende aanvallen, u uw aandacht verleggen naar bescherming tegen onbekende bedreigingen. De meer vastberaden en gevorderde tegenstanders gebruiken innovatieve en nieuwe, onbekende methoden om organisaties aan te vallen. Met de enorme telemetrie van gegevens van Microsoft die zijn verzameld over miljarden apparaten, toepassingen en services, kunnen we Geavanceerde bedreigingsbeveiliging uitvoeren op Windows, Office 365 en Azure om zero day-aanvallen te voorkomen, gebruik te maken van zandboxomgevingen en de geldigheid te controleren voordat u toegang tot uw inhoud toestaat. 


|Aanbeveling  |E3  |E5  |
|---------|---------|---------|
|**Office 365 Advanced Threat Protection (ATP) configureren:**<br>* ATP veilige bijlagen<br>* ATP Veilige Links<br>* ATP voor SharePoint, OneDrive en Microsoft Teams<br>* ATP anti-phishing bescherming|         |![groen vinkje](../media/green-check-mark.png) |
|**Microsoft Defender Geavanceerde bedreigingsbeveiliging-mogelijkheden configureren:**<br>* Windows Defender Antivirus <br>* Bescherming tegen gebruik <br> * Aanval oppervlaktereductie <br> * Hardwarematige isolatie <br>* Gecontroleerde toegang tot mappen     |         |![groen vinkje](../media/green-check-mark.png) |
|**Gebruik Microsoft Cloud App Security** om SaaS-apps te ontdekken en gedragsanalyses en anomaliedetectie te gebruiken. |         |![groen vinkje](../media/green-check-mark.png) |

Het volgende diagram illustreert deze mogelijkheden.
![Aanbevolen mogelijkheden om te beschermen tegen onbekende bedreigingen](../media/m365-security-bdm-illustrations-unknown-threats.png)

Aanvullende aanbevelingen:
- Beveiligde communicatie via partnerkanalen, zoals e-mails met TLS.
- Open Teams Federation alleen voor partners waarmee u communiceert.
- Plaats afzenderdomeinen, individuele afzenders of bron-IP's niet op de witte lijst, omdat deze hiermee spam- en malwarecontroles kunnen omzeilen - Een gangbare praktijk met klanten is het whitelisten van hun eigen geaccepteerde domeinen of een aantal andere domeinen waar problemen met de e-mailstroom mogelijk zijn gemeld. Voeg geen domeinen toe in de lijst met spam- en verbindingsfilters, omdat hiermee mogelijk alle spamcontroles worden omzeild. 
- Uitgaande spammeldingen inschakelen : Schakel uitgaande spammeldingen intern in een distributielijst in bij de Helpdesk of het IT-beheerteam om te melden of een van de interne gebruikers spam-e-mails extern verzendt. Dit kan een indicator zijn dat de rekening is gecompromitteerd.
- Remote PowerShell uitschakelen voor alle gebruikers — Remote PowerShell wordt voornamelijk gebruikt door beheerders om toegang te krijgen tot services voor administratieve doeleinden of programmatische API-toegang. We raden aan deze optie uit te schakelen voor niet-beheerders om verkenning te voorkomen, tenzij ze een zakelijke vereiste hebben om toegang te krijgen. 
- Blokkeer de toegang tot de Microsoft Azure Management-portal voor alle niet-beheerders. U dit bereiken door een regel voor voorwaardelijke toegang te maken om alle gebruikers te blokkeren, met uitzondering van beheerders. 


## <a name="assume-breach"></a>Veronderstel schending

Hoewel Microsoft alle mogelijke maatregelen neemt om bedreigingen en aanvallen te voorkomen, raden we u aan altijd te werken onder de "Assume Breach"-mentaliteit. Zelfs als een aanvaller erin is geslaagd om de omgeving te binnendringen, moeten we ervoor zorgen dat ze gegevens of identiteitsgegevens uit de omgeving niet kunnen exfiltreren. Daarom raden we aan bescherming mogelijk te maken tegen gevoelige gegevenslekken zoals burgerservicenummers, creditcardnummers, aanvullende persoonlijke informatie en andere vertrouwelijke informatie op organisatieniveau. 

De "Assume Breach" mentaliteit vereist de uitvoering van een zero trust netwerk strategie, wat betekent dat gebruikers niet volledig vertrouwd zijn alleen maar omdat ze intern zijn in het netwerk. In plaats daarvan, als onderdeel van de autorisatie van wat gebruikers kunnen doen, worden sets van voorwaarden gespecificeerd, en wanneer aan dergelijke voorwaarden is voldaan, worden bepaalde controles afgedwongen. Voorwaarden kunnen bestaan uit de status van het apparaat, toegang tot de toepassing, bewerkingen die worden uitgevoerd en gebruikersrisico.Conditions may include device health status, application being accessed, operations being performed and user risk. Een actie voor apparaatinschrijving moet bijvoorbeeld altijd MFA-verificatie activeren om ervoor te zorgen dat er geen rouge-apparaten aan uw omgeving worden toegevoegd. 

Een zero trust netwerkstrategie vereist ook dat u weet waar uw gegevens worden opgeslagen en de juiste besturingselementen toepassen voor classificatie, bescherming en retentie. Om uw meest kritieke en gevoelige assets effectief te beschermen, moet u eerst identificeren waar deze zich bevinden en inventariseren, wat een uitdaging kan zijn. Werk vervolgens samen met uw organisatie om een governancestrategie te definiëren. Het definiëren van een classificatieschema voor een organisatie en het configureren van beleid, labels en voorwaarden vereist een zorgvuldige planning en voorbereiding. Het is belangrijk om te beseffen dat dit geen IT-gestuurd proces is. Zorg ervoor dat u samenwerkt met uw juridische en complianceteam om een passend classificatie- en labelschema voor de gegevens van uw organisatie te ontwikkelen.

Microsoft 365-mogelijkheden voor informatiebescherming kunnen u helpen te ontdekken welke informatie u hebt, waar deze is opgeslagen en welke informatie extra bescherming vereist. Informatiebeveiliging is een continu proces en Microsoft 365-mogelijkheden bieden u inzicht in hoe gebruikers gevoelige informatie gebruiken en distribueren, waar uw gegevens momenteel worden opgeslagen en waar deze worden opgeslagen. U ook zien hoe gebruikers omgaan met informatie die is gereguleerd om er zeker van te zijn dat de juiste labels en beveiligingen worden toegepast.


|Aanbeveling |E3|E5 |
|---------|---------|---------|
|**Bekijk en optimaliseer uw voorwaardelijke toegang en bijbehorend beleid om af te stemmen op uw doelstellingen voor een netwerk met een vertrouwenswaarde.** Bescherming tegen bekende bedreigingen omvat de uitvoering van een reeks [aanbevolen beleidsregels](../enterprise/microsoft-365-policies-configurations.md). Bekijk uw implementatie van dit beleid om ervoor te zorgen dat u uw apps en gegevens beschermt tegen hackers die toegang hebben gekregen tot uw netwerk. Houd er rekening mee dat het aanbevolen Intune-app-beveiligingsbeleid voor Windows 10 Windows Information Protection (WIP) inschakelt. WIP beschermt tegen onbedoelde lekken van uw organisatiegegevens via apps en services, zoals e-mail, sociale media en de openbare cloud. |         |![groen vinkje](../media/green-check-mark.png)|
|**Extern e-mail doorsturen uitschakelen**. Hackers die toegang krijgen tot het postvak van een gebruiker kunnen uw e-mail stelen door het postvak in te stellen om e-mail automatisch door te sturen. Dit kan zelfs gebeuren zonder het bewustzijn van de gebruiker. U dit voorkomen door een regel voor e-mailstroom te configureren.|![groen vinkje](../media/green-check-mark.png) |![groen vinkje](../media/green-check-mark.png)|
|**Anoniem extern delen van agenda's uitschakelen**. Standaard is extern anoniem agendadelen toegestaan. Het delen van [agenda's uitschakelen](https://docs.microsoft.com/exchange/sharing/sharing-policies/modify-a-sharing-policy) om mogelijke lekken van gevoelige informatie te verminderen.|![groen vinkje](../media/green-check-mark.png) |![groen vinkje](../media/green-check-mark.png)|
|**Het preventiebeleid voor gegevensverlies configureren voor gevoelige gegevens**. Maak een beleid voor gegevensverliespreventie in het Security &amp; Compliance-centrum om gevoelige gegevens zoals creditcardnummers, burgerservicenummers en bankrekeningnummers te ontdekken en te beschermen. Microsoft 365 bevat veel vooraf gedefinieerde gevoelige informatietypen die u gebruiken in het beleid voor het voorkomen van gegevensverlies. U ook uw eigen gevoelige informatietypen maken voor gevoelige gegevens die zijn aangepast aan uw omgeving. |![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Implementeren van beleid voor gegevensclassificatie en informatiebescherming**. Implementeer gevoeligheidslabels en gebruik deze om bescherming op gevoelige gegevens te classificeren en toe te passen. U deze labels ook gebruiken in het beleid ter voorkoming van gegevensverlies. Als u Azure Information Protection-labels gebruikt, raden we u aan geen nieuwe labels te maken in andere beheercentra.|         |![groen vinkje](../media/green-check-mark.png)|
|**Bescherm gegevens in apps en services van derden met cloud-appbeveiliging.** Configureer beveiligingsbeleid voor cloudapps om gevoelige informatie te beschermen in cloud-apps van derden, zoals Salesforce, Box of Dropbox. U gevoelige informatietypen en de gevoeligheidslabels gebruiken die u hebt gemaakt in het beveiligingsbeleid van Cloud App en deze toepassen in uw SaaS-apps. <br><br>Met Microsoft Cloud App Security u een breed scala aan geautomatiseerde processen afdwingen. Beleidsregels kunnen worden ingesteld om continue nalevingsscans, juridische eDiscovery-taken, DLP voor gevoelige inhoud die openbaar wordt gedeeld en meer te bieden. Cloud App Security kan elk bestandstype controleren op basis van meer dan 20 metagegevensfilters (bijvoorbeeld toegangsniveau, bestandstype). |         |![groen vinkje](../media/green-check-mark.png)|
|**Gebruik [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/information-protection-in-windows-overview) om te bepalen of gebruikers gevoelige informatie opslaan op hun Windows-apparaten.** |         |![groen vinkje](../media/green-check-mark.png)|
|**Gebruik [AIP-scanner](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner) om informatie te identificeren en te classificeren tussen servers en bestandsshares.** Gebruik het AIP-rapportageprogramma om de resultaten te bekijken en passende acties te ondernemen.|         |![groen vinkje](../media/green-check-mark.png)|

Het volgende diagram illustreert deze mogelijkheden.
![Aanbevolen mogelijkheden om te beschermen tegen inbreuken](../media/m365-security-bdm-illustrations-assume-breach.png)

## <a name="continuous-monitoring-and-auditing"></a>Continue monitoring en auditing

Last but not least continue monitoring en auditing van de Microsoft 365-omgeving samen met de Windows en Apparaten is van cruciaal belang om ervoor te zorgen dat u instaat bent om snel te detecteren en te herstellen van eventuele indringers. Tools zoals Secure Score, Security Center en de geavanceerde analyses van Microsoft Intelligent Graph bieden waardevolle informatie in uw tenant en koppelen enorme hoeveelheden informatie over bedreiging en beveiligingsgegevens om u ongeëvenaarde bescherming en detectie van bedreigingen te bieden.


|Aanbeveling |E3 |E5 |
|---------|---------|---------|
|Controleer of het **controlelogboek** is ingeschakeld.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Secure Score wekelijks bekijken** : secure score is een centrale locatie om toegang te krijgen tot de beveiligingsstatus van uw bedrijf en acties uit te voeren op basis van aanbevelingen voor een veilige score. Het wordt aanbevolen om deze controle wekelijks uit te voeren.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|Office **365 ATP-hulpprogramma's** gebruiken:<br>* Mogelijkheden voor bedreigingsonderzoek en -respons<br> * Geautomatiseerd onderzoek en reactie |         |![groen vinkje](../media/green-check-mark.png)|
|**Microsoft Defender ATP gebruiken:**<br> *    [Eindpuntdetectie en -respons](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) <br> * Geautomatiseerd onderzoek en herstel Secure score <br>*    [Geavanceerde jacht](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) <br>|         |![groen vinkje](../media/green-check-mark.png)|
|Gebruik **Microsoft Cloud App Security** om ongebruikelijk gedrag in cloud-apps te detecteren om ransomware, gecompromitteerde gebruikers of malafide toepassingen te identificeren, gebruik te maken van risico's en automatisch te herstellen om het risico voor uw organisatie te beperken.|         |![groen vinkje](../media/green-check-mark.png)|
|Gebruik **Microsoft Azure Sentinel** of uw huidige SIEM-tool om te controleren op bedreigingen in uw omgeving. |         |![groen vinkje](../media/green-check-mark.png)|
|**Implementeer [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) ** om te controleren en te beschermen tegen bedreigingen die zijn gericht op uw on-premises Active Directory-omgeving.   |         |![groen vinkje](../media/green-check-mark.png) |
|Gebruik het **Azure Security Center** om te controleren op bedreigingen voor hybride en cloudworkloads. Azure Security Center bevat een gratis niveau van mogelijkheden en een standaardniveau met mogelijkheden waarvoor wordt betaald op basis van resourceuren of transacties.|         |         |

Het volgende diagram illustreert deze mogelijkheden.
![Aanbevolen mogelijkheden voor continue monitoring en auditing](../media/m365-security-bdm-illustrations-monitoring-auditing.png)

De belangrijkste aanbevolen bewakingsacties:
- **Microsoft Secure Score wekelijks controleren** : de beveiligde score is een centrale locatie om toegang te krijgen tot de beveiligingsstatus van uw tenant en om acties uit te voeren op basis van de belangrijkste aanbevelingen. Het wordt aanbevolen om deze controle wekelijks uit te voeren. Secure Score bevat aanbevelingen van in Azure AD, Intune, Cloud App Security en Microsoft Defender Advanced Threat Protection, evenals Office 365. 
- **Wekelijks riskante aanmeldingen bekijken** : gebruik het Azure AD-beheercentrum om wekelijks riskante aanmeldingen te bekijken. De aanbevolen regelset voor identiteits- en apparaattoegang bevat een beleid om wachtwoordwijzigingen af te dwingen bij riskante aanmeldingen.  
- **Bekijk de top malware en phished gebruikers wekelijks** - Gebruik Office Advanced Threat Protection Threat Explorer om top gebruikers gericht met malware en phish te herzien en om uit te vinden van de oorzaak van waarom deze gebruikers worden beïnvloed.
