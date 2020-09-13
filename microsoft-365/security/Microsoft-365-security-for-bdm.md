---
title: Microsoft 365 Security for Business Decisioners (BDMs)
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: de meest voorkomende scenario's voor de bedreiging en aanval die momenteel door organisaties worden geconfronteerd voor hun Microsoft 365-omgevingen, en aanbevolen acties om deze Risico's te beperken.
ms.openlocfilehash: 2f7de328edbd0220e5627612430fca24641ace11
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547996"
---
# <a name="microsoft-365-security-for-business-decision-makers-bdms"></a>Microsoft 365 Security for Business Decisioners (BDMs)

In dit artikel worden enkele van de meest voorkomende scenario's voor bedreiging en aanval besproken die momenteel door organisaties worden geconfronteerd voor hun Microsoft 365-omgevingen, en aanbevolen acties om deze Risico's te beperken. Hoewel Microsoft 365 deel uitmaakt van een ruime configuratie van vooraf geconfigureerde beveiligingsfuncties, dient u ook de klant te verantwoordelijk stellen om uw eigen identiteiten, data en apparatuur te beschermen voor toegang tot cloudservices. Deze richtlijnen zijn ontwikkeld door Kozeta straal (Microsoft Cloud Security architect) en Thiagaraj Sundararajan (Microsoft Senior consultant).

Dit artikel is ingedeeld op prioriteit van werk, te beginnen met de bescherming van de accounts die worden gebruikt voor het beheren van de meest kritieke services en assets, zoals uw Tenant, e-mail en SharePoint. Deze functie biedt een methode voor de aanpak van de beveiliging en werkt samen met de volgende spreadsheet, zodat u de voortgang kunt bijhouden met belanghebbenden en teams in uw organisatie: [Microsoft 365 beveiliging voor BDMs-spreadsheet](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx). 

[![Afbeelding van miniatuur Microsoft 365 BDM beveiligingsaanbevelingen](../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)

Microsoft biedt u het hulpmiddel voor veilig scoren in uw Tenant voor het automatisch analyseren van uw beveiligings Posture op basis van uw normale activiteiten, het toewijzen van een score en het verschaffen van aanbevelingen voor beveiligingsverbeteringen. Voordat u de acties in dit artikel uitvoert, moet u rekening houden met uw huidige score en aanbevelingen. Met de acties die in dit artikel worden aanbevolen, wordt uw score hoger weergegeven. Het doel is niet de maximum score te bereiken, maar wel op een manier om uw omgeving te beschermen op een wijze die niet negatief van invloed is op de productiviteit van uw gebruikers. Zie [Microsoft Secure Score](mtp/microsoft-secure-score.md).

Nog een ding voordat we aan de slag gaan. . . Zorg ervoor dat u [het auditlogboek inschakelt](../compliance/search-the-audit-log-in-security-and-compliance.md). U hebt deze gegevens later nodig, in het geval dat u een incident of een schending moet onderzoeken. 

## <a name="protect-privileged-accounts"></a>Geprivilegieerde accounts beveiligen

In de eerste stap is het raadzaam om kritieke accounts in de omgeving te zorgen voor een extra beveiligingslaag omdat deze accounts toegang hebben tot en wijziging van kritieke services en bronnen die van invloed kunnen zijn op de gehele organisatie, als deze zijn opgetast. Het beveiligen van geprivilegieerde accounts is een van de beste manieren om te beschermen tegen een kwaadwillende persoon die de machtigingen van een gemanipuleerd account mag verhogen. 

|Aanbeveling  |E3 |E5  |
|---------|---------|---------|
|Meerdere MFA-verificatie (MFA) afdwingen voor alle beheeraccounts.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)| 
|Azure Active Directory (Azure AD) met geprivilegieerde identiteitsbeheer (PIM) implementeren, zodat u toegang hebt tot Azure AD en Azure-bronnen. U kunt ook ontdekken wie toegang heeft en toegang tot bevoegdheden controleren.|         | ![groen vinkje](../media/green-check-mark.png)|
|Geprivilegieerde toegangsbeheer implementeren voor het beheren van granulair toegangsbeheer voor taken met beheerdersmachtigingen in Office 365. |         | ![groen vinkje](../media/green-check-mark.png)|
|Geprivilegieerde toegangs werkstations configureren en gebruiken (PAW) voor het beheren van services. Gebruik niet dezelfde werkstations om te surfen op internet en om e-mail te controleren die niet is gerelateerd aan uw beheerdersaccount.|  ![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png) | 

In het volgende diagram ziet u deze mogelijkheden.
![Aanbevolen functies voor het beschermen van geprivilegieerde accounts](../media/m365-security-bdm-illustrations-privileged-accounts.png)

Aanvullende aanbevelingen:
- Zorg ervoor dat accounts die worden gesynchroniseerd van on-premises, geen beheerdersrollen voor cloudservices krijgen. Dit helpt voorkomen dat een aanvaller on-premises accounts kan gebruiken om toegang te krijgen tot cloudservices. 
- Zorg ervoor dat aan serviceaccounts geen beheerdersrollen zijn toegewezen. Deze accounts worden vaak niet gecontroleerd en worden ingesteld met wachtwoorden die niet verlopen. Zorg er eerst voor dat de accounts AADConnect en ADFS Services niet standaard worden gebruikt voor globale beheerders.
- Licenties verwijderen uit beheerdersaccounts. Tenzij er een specifieke use case is voor het toewijzen van licenties aan specifieke beheerdersaccounts, moet u licenties uit deze accounts verwijderen. 

## <a name="reduce-the-surface-of-attack"></a>Verminder het oppervlak van een aanval

Het volgende focus gebied verkleint het oppervlak van de aanval. Dit kan met minimale inspanning en gevolgen voor uw gebruikers en services. Door de oppervlakte van een aanval te verminderen, kunnen hackers op minder manieren een aanval starten tegen uw organisatie.

Dit zijn enkele voorbeelden:
- Schakel POP3-, IMAP-en SMTP-protocollen uit. De meeste moderne organisaties gebruiken deze oudere protocollen niet meer. U kunt deze en uitzonderingen alleen veilig uitschakelen. 
- Verminder het aantal globale beheerders in de Tenant en zorg dat het absoluut minimaal vereist. Hierdoor wordt het oppervlakte van de aanval voor alle Cloud toepassingen direct verlaagd. 
- Servers en toepassingen buiten gebruik stellen die niet meer worden gebruikt in uw omgeving. 
- Implementeer een proces voor het uitschakelen en verwijderen van accounts die niet meer worden gebruikt. 

## <a name="protect-against-known-threats"></a>Beveilig tegen bekende bedreigingen

Bekende bedreigingen zijn onder meer malware, gemanipuleerde accounts en phishing. Sommige bescherming tegen deze bedreigingen kunnen snel worden geïmplementeerd met geen directe impact voor uw gebruikers, terwijl anderen meer planning en gebruikers training vereisen. 

|Aanbeveling  |E3  |E5  |
|---------|---------|---------|
|**Meervoudige verificatie instellen en aanbevolen beleidsregels voor voorwaardelijke toegang gebruiken, met inbegrip van aanmeldings risico beleid**. Microsoft adviseert en heeft een reeks beleidsregels getest die samenwerken om alle Cloud-apps te beschermen, waaronder Office 365 en Microsoft 365-Services. Zie [configuraties voor identiteit en Apparaattoegang](../enterprise/microsoft-365-policies-configurations.md). | |![groen vinkje](../media/green-check-mark.png)|
|**Meerdere factor verificatie vereisen voor alle gebruikers**. Als u niet over de vereiste licentie beschikt om het aanbevolen beleid voor voorwaardelijke toegang te implementeren, moet u voor alle gebruikers minimaal meervoudige verificatie vereisen.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Het beschermingsniveau voor malware in E-mail verhogen**. Uw Office 365-of Microsoft 365-omgeving bevat bescherming tegen malware, maar u kunt deze beveiliging vergroten door bijlagen te blokkeren met bestandstypen die meestal voor malware worden gebruikt.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Beveilig uw e-mail tegen gerichte phishing-aanvallen**. Als u een of meer aangepaste domeinen hebt geconfigureerd voor uw Office 365-of Microsoft 365-omgeving, kunt u de gerichte bescherming tegen phishing instellen. Met een anti-virusbeveiliging van ATP, een onderdeel van Office 365 Advanced Threat Protection, kunt u uw organisatie beschermen tegen kwaadaardige aanvallen op basis van kwaadaardige aanvallen en andere phishing-aanvallen. U hoeft dit niet te doen als u geen aangepast domein hebt geconfigureerd.| |![groen vinkje](../media/green-check-mark.png)|
|**Beveilig het e-mailadres tegen Ransomware via e-mail**. Ransomware zorgt ervoor dat uw gegevens niet toegankelijk zijn voor het versleutelen van bestanden of het vergrendelen van computerschermen. Vervolgens probeert extort u geld van slachtoffers te door te vragen voor ' Ransom ', meestal in de vorm van cryptocurrencies zoals Bitcoin, in Exchange voor het terughalen van de toegang tot uw gegevens. U kunt ervoor zorgen dat u zich voor Ransomware beveiligt door een of meer e-mail stroom regels te maken om bestandsextensies te blokkeren die vaak voor Ransomware worden gebruikt, of om gebruikers te waarschuwen die deze bijlagen in een e-mail ontvangen.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Blokkeer verbindingen uit landen waarmee u geen zaken doet**. Maak een beleid voor voorwaardelijke toegang van Azure AD voor het blokkeren van verbindingen uit deze landen en maak een geo-firewall rondom uw Tenant.| |![groen vinkje](../media/green-check-mark.png)|

In het volgende diagram ziet u deze mogelijkheden.
![Aanbevolen mogelijkheden om te beschermen tegen bekende bedreigingen](../media/m365-security-bdm-illustrations-known-threats.png)

## <a name="protect-against-unknown-threats"></a>Bescherming tegen onbekende bedreigingen

Na het toevoegen van extra bescherming aan uw geprivilegieerde accounts en het beschermen tegen bekende aanvallen, moet u uw aandacht verschuiven om tegen onbekende bedreigingen te beschermen. Hoe meer bepaald en Geavanceerd adversaries gebruikmaken van innovatieve en nieuwe, onbekende methoden voor aanvallen van organisaties. Met de vergrote telemetriegegevens van Microsoft kunnen gegevens worden verzameld via een groot aantal apparaten, toepassingen en services van Microsoft, zodat u kunt voorkomen dat u een aanval moet voeren tegen zero day-aanvallen, het gebruik 365 van zand box-omgevingen en de geldigheid controleert voordat u toegang krijgt tot uw inhoud. 


|Aanbeveling  |E3  |E5  |
|---------|---------|---------|
|**Office 365 Advanced Threat Protection (ATP) configureren**:<br>* Veilige bijlagen met ATP<br>* Veilige koppelingen met ATP<br>* ATP voor SharePoint, OneDrive en Microsoft teams<br>* Anti-virusbeveiliging van ATP|         |![groen vinkje](../media/green-check-mark.png) |
|**Functies voor geavanceerde bedreigingsbeveiliging voor Microsoft Defender configureren**:<br>* Windows Defender antivirus <br>* Preventie beveiliging <br> * Oppervlakte vermindering van aanval <br> * Geïsoleerd op basis van hardware <br>* Controlled map Access     |         |![groen vinkje](../media/green-check-mark.png) |
|**Gebruik Microsoft Cloud app Security** om SaaS-apps te ontdekken en te beginnen met het detecteren van gedrags analyses en anomaliedetectie. |         |![groen vinkje](../media/green-check-mark.png) |

In het volgende diagram ziet u deze mogelijkheden.
![Aanbevolen functies voor het beschermen tegen onbekende bedreigingen](../media/m365-security-bdm-illustrations-unknown-threats.png)

Aanvullende aanbevelingen:
- Beveiligde partner kanaal communicatie, zoals E-mails via TLS.
- Open teams-Federatie alleen voor partners waarmee u communiceert.
- Voeg geen e-mailadressen, afzonderlijke afzenders of bron-Ip's toe aan uw lijst toestaan, zodat deze de controles voor spam en malware overslaan (een veelvoorkomende gewoonte met klanten toevoegen aan hun eigen geaccepteerde domeinen of een ander e-mailbericht) waar de e-mail stroom problemen mogelijk zijn gerapporteerd. Voeg geen domeinen toe aan de lijst voor het filteren van ongewenste E-mail en verbindingen, aangezien dit mogelijk alle spam controles negeert. 
- Uitgaande spam meldingen inschakelen: Schakel uitgaande spam meldingen in voor een distributielijst voor de helpdesk of IT-beheer team om te rapporteren of een van de interne gebruikers spamberichten extern verstuurt. Dit kan een indicator zijn die de account heeft aangetast.
- Externe PowerShell uitschakelen voor alle gebruikers: externe PowerShell wordt hoofdzakelijk door beheerders gebruikt voor toegang tot services voor administratieve doeleinden of via programma-API-toegang. U wordt aangeraden deze optie uit te schakelen voor gebruikers zonder beheerder om Reconnaissance te vermijden, tenzij ze toegang hebben tot de organisatie. 
- Toegang tot de Microsoft Azure-beheerportal blokkeren voor alle niet-beheerders. U kunt dit doen door een regel voor voorwaardelijke toegang te maken waarmee u alle gebruikers kunt blokkeren, met uitzondering van beheerders. 


## <a name="assume-breach"></a>Ervan uitgaan dat schending

Hoewel Microsoft de mogelijkheid draagt om bedreigingen en aanvallen te voorkomen, raden we u aan altijd te werken onder de Mindset ' bij voorbehoud van een schending '. Zelfs als een kwaadwillende persoon het intrude in de omgeving heeft beheerd, moeten we ervoor zorgen dat ze geen gegevens of identiteitsgegevens kunnen exfiltrate van de omgeving. Om die reden is het raadzaam bescherming te bieden tegen gevoelige gegevens lekkage, zoals sofi-nummers, creditcardnummers, extra persoonlijke gegevens en andere vertrouwelijke informatie van organisatieniveau. 

Bij de Mindset ' verzorgt u een schending ' moet u een strategie voor het vertrouwens netwerk van een beheerder instellen, wat betekent dat gebruikers niet volledig worden vertrouwd, zodat ze intern voor het netwerk zijn. Als onderdeel van de autorisatie van de gebruikers die kunnen doen, worden voorwaarden de sets voorwaarden gespecificeerd en wanneer aan deze voorwaarden wordt voldaan, worden bepaalde besturingselementen afgedwongen. Voorwaarden kan de status van het apparaat bevatten, de toepassing wordt geopend en het gebruikers risico wordt uitgevoerd. Met een actie voor het inschrijven van een apparaat wordt bijvoorbeeld MFA-authenticatie altijd geactiveerd, zodat er geen Rouge-apparaten aan uw omgeving worden toegevoegd. 

Bij een strategie met een vertrouwens netwerk moet u ook weten waar uw gegevens zijn opgeslagen en de juiste besturingselementen voor classificatie, bescherming en behoud. Om uw meest kritieke en gevoelige assets efficiënt te beschermen, moet u eerst identificeren waar deze zich bevinden en de voorraad inventariseren, wat ook moeilijk te doen is. Werk vervolgens met uw organisatie om een beheer strategie te definiëren. Voor het definiëren van een classificatieschema voor een organisatie en het configureren van beleid, etiketten en voorwaarden is een zorgvuldige planning en voorbereiding vereist. Het is belangrijk te beseffen dat dit geen IT-proces is. Zorg ervoor dat u met uw juridisch en compliance team een juiste classificatie en etiket schema voor de gegevens van uw organisatie ontwikkelt.

Microsoft 365 mogelijkheden voor informatiebescherming helpt u te ontdekken welke informatie u hebt, waar deze wordt opgeslagen en welke informatie extra bescherming vereist. Information Protection is een doorlopend proces en Microsoft 365-mogelijkheden met inzicht in de manier waarop gebruikers gevoelige informatie gebruiken en distribueren, waar uw gegevens momenteel zijn opgeslagen, en waar ze zich ook bevinden. U kunt ook zien hoe gebruikers informatie behandelen waarop de juiste labels en bescherming worden toegepast.


|Aanbeveling |E3|E5 |
|---------|---------|---------|
|**Uw voorwaardelijke toegang en gerelateerde beleidsregels controleren en optimaliseren om af te stemmen op uw doelstellingen voor een vertrouwens netwerk met nul**. Het beschermen tegen bekende bedreigingen omvat een set [Aanbevolen beleidsregels](../enterprise/microsoft-365-policies-configurations.md). Controleer de implementatie van deze beleidsregels om ervoor te zorgen dat u uw apps en gegevens beschermt tegen hackers die toegang hebben verkregen tot uw netwerk. Houd er rekening mee dat in het aanbevolen beleid voor de intune-app voor Windows 10 Windows Information Protection (OHW) is ingeschakeld. OHW beschermt tegen onbedoelde lekkage van uw organisatiegegevens via apps en services, zoals e-mail, sociale media en de openbare wolk. |         |![groen vinkje](../media/green-check-mark.png)|
|**Externe e-mail forwarding uitschakelen**. Hackers die toegang krijgen tot het postvak van een gebruiker kunnen uw e-mail stelen door het postvak in te stellen op het automatisch doorsturen van e-mail. Dit kan zelfs zonder de aandacht van de gebruiker. U kunt dit voorkomen door een e-mail stroom regel te configureren.|![groen vinkje](../media/green-check-mark.png) |![groen vinkje](../media/green-check-mark.png)|
|**Anoniem delen van Agenda's uitschakelen**. Standaard is extern anoniem delen van agenda's toegestaan. Het [delen van Agenda's uitschakelen](https://docs.microsoft.com/exchange/sharing/sharing-policies/modify-a-sharing-policy) om mogelijke lekkages van gevoelige gegevens te beperken.|![groen vinkje](../media/green-check-mark.png) |![groen vinkje](../media/green-check-mark.png)|
|**Beleidsregels voor preventie van gegevensverlies configureren voor gevoelige gegevens**. Maak een beleid voor preventie van gegevensverlies in het beveiligings &amp; centrum voor de detectie en beveiliging van gevoelige gegevens, zoals creditcardnummers, sofi-nummers en bankrekeningnummers. Microsoft 365 bevat veel vooraf gedefinieerde gevoelige informatie typen die u kunt gebruiken in het beleid voor preventie van gegevensverlies. U kunt ook uw eigen gevoelige informatie typen maken voor gevoelige gegevens die in uw omgeving zijn aangepast. |![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Implementeer beleidsregels voor gegevensclassificatie en informatiebescherming**. Implementeer gevoelige labels en gebruik deze om beveiliging te classificeren en ter bescherming van gevoelige gegevens toe te passen. U kunt deze labels ook gebruiken in beleidsregels voor preventie van gegevensverlies. Als u Azure Information Protection-labels gebruikt, raden we u aan om nieuwe labels in andere beheer centra te maken.|         |![groen vinkje](../media/green-check-mark.png)|
|**Beveilig gegevens in apps en services van derden met behulp van de beveiliging van Cloud apps**. Configureer het beveiligingsbeleid van de Cloud app om gevoelige informatie te beschermen voor alle Cloud-apps van derden, zoals Salesforce, box of Dropbox. U kunt gevoelige informatie typen en de gevoeligheids labels die u hebt gemaakt in het beveiligingsbeleid van de Cloud-app gebruiken en ze toepassen in de SaaS-apps. <br><br>Met beveiliging van Microsoft Cloud-apps kunt u een groot aantal geautomatiseerde processen afdwingen. Beleidsregels kunnen worden ingesteld voor voortdurende nalevings scans, juridische eDiscovery-taken, DLP voor gevoelige inhoud, openbaar en meer. Met beveiliging van de Cloud-app kunnen bestandstypen worden gecontroleerd op basis van meer dan 20 filters voor metagegevens, zoals het niveau van toegang, bestandstype. |         |![groen vinkje](../media/green-check-mark.png)|
|**Gebruik [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/information-protection-in-windows-overview) om te bepalen of gebruikers gevoelige informatie op hun Windows-apparaten opslaan**. |         |![groen vinkje](../media/green-check-mark.png)|
|**Gebruik de [beheerders scanner](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner) om gegevens te identificeren en classificeren tussen servers en bestandsshares**. Gebruik het rapportageprogramma van beheerders om de resultaten te bekijken en de juiste acties uit te voeren.|         |![groen vinkje](../media/green-check-mark.png)|

In het volgende diagram ziet u deze mogelijkheden.
![Aanbevolen mogelijkheden om te beschermen tegen schending](../media/m365-security-bdm-illustrations-assume-breach.png)

## <a name="continuous-monitoring-and-auditing"></a>Continue controle en controle

De laatste, maar de laatste voortdurende controle en controle van de Microsoft 365-omgeving met de Vensters en apparaten is essentieel, zodat u zeker weet dat u de indringers snel kunt ontdekken en herstellen. Met hulpprogramma's zoals Secure Score, Security Center en Microsoft intelligent Graph Advanced Analytics levert u ter informatie een zeer waardevolle informatie in uw Tenant op en koppelt u enorme hoeveelheden Threat Intelligence-en beveiligingsgegevens voor een ongeevenwijdige bedreigings bescherming en-detectie.


|Aanbeveling |E3 |E5 |
|---------|---------|---------|
|Zorg ervoor dat het **auditlogboek** is ingeschakeld.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|**Bekijk de veiligste Score** : Secure Score is een centrale locatie voor het openen van de beveiligingsstatus van uw bedrijf en het uitvoeren van acties op basis van aanbevelingen voor de Secure Score. U wordt aangeraden deze controle wekelijks uit te voeren.|![groen vinkje](../media/green-check-mark.png)|![groen vinkje](../media/green-check-mark.png)|
|Gebruik de ATP-hulpprogramma's van **Office 365** :<br>* Mogelijkheden voor het onderzoek en de antwoord mogelijkheden<br> * Automatisch onderzoek en antwoord |         |![groen vinkje](../media/green-check-mark.png)|
|Gebruik **Microsoft Defender ATP**:<br> *    [Detectie van het eindpunt en-antwoord](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) <br> * Automatisch onderzoek en bescherming tegen herstel <br>*    [Geavanceerde jacht](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) <br>|         |![groen vinkje](../media/green-check-mark.png)|
|Gebruik de **beveiliging van Microsoft Cloud-app** om ongebruikelijk gedrag te detecteren in Cloud-apps om Ransomware, gemanipuleerde gebruikers of Rogue-toepassingen te identificeren, analyseren van hoog risico en automatisch herstellen om het risico te beperken voor uw organisatie.|         |![groen vinkje](../media/green-check-mark.png)|
|Gebruik **Microsoft Azure Sentinel** of uw huidige Siem-hulpmiddel om te controleren op bedreigingen in uw omgeving. |         |![groen vinkje](../media/green-check-mark.png)|
|**Implementeer [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) ** om te bewaken en te beschermen tegen bedreigingen die op uw on-premises Active Directory-omgeving van uw organisatie zijn gericht.   |         |![groen vinkje](../media/green-check-mark.png) |
|Gebruik het **Azure-Beveiligingscentrum** om te controleren op bedreigingen voor hybride en Cloud werkbelasting. Azure Security Center bevat een gratis beschikbare functies en een standaardtier van mogelijkheden die zijn betaald op basis van resource uren of transacties.|         |         |

In het volgende diagram ziet u deze mogelijkheden.
![Aanbevolen functies voor voortdurende controle en controle](../media/m365-security-bdm-illustrations-monitoring-auditing.png)

Belangrijkste aanbevolen controleacties:
- Een **wekelijkse controle over de Microsoft-Score** : Secure Score is een centrale locatie voor toegang tot de beveiligingsstatus van de Tenant en om acties te ondernemen op basis van de belangrijkste aanbevelingen. U wordt aangeraden deze controle wekelijks uit te voeren. Secure Score bevat aanbevelingen van in azure AD, intune, Cloud app Security en Microsoft Defender Advanced Threat Protection, en Office 365. 
- **Meld u wekelijkse aanmeldingen als u wekelijkse aanmeldingen** wilt gebruiken, kunt u het Azure AD-Beheercentrum gebruiken om wekelijkse aanmeldpogingen wekelijks te bekijken. De aanbevolen regel-en Apparaattoegang bevat een beleid voor het afdwingen van het wijzigen van het wachtwoord voor risico registratie.  
- De **beste malware en** de geschadelijkte gebruikers bekijken: Gebruik Office Advanced Threat Protection voor de beste gebruikers die met malware en phishing werken, en om de belangrijkste oorzaak van de oorzaak van deze gebruikers te achterhalen.
