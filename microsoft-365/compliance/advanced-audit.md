---
title: Geavanceerde audit in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-audit
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Geavanceerde audit in Microsoft 365 biedt nieuwe auditmogelijkheden waarmee uw organisatie forensisch en complianceonderzoek kan uitvoeren.
ms.openlocfilehash: 3c91a388bc01a5531309b556a5a8532cb2efbaa6
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311734"
---
# <a name="advanced-audit-in-microsoft-365"></a>Geavanceerde audit in Microsoft 365

De [geïntegreerde auditfunctionaliteit](search-the-audit-log-in-security-and-compliance.md) in Microsoft 365 biedt organisaties inzicht in vele soorten gecontroleerde activiteiten voor veel verschillende services in Microsoft 365. Met Geavanceerde audit kunnen organisaties forensisch en complianceonderzoek uitvoeren door de auditlogboekretentie te verhogen die nodig is voor het uitvoeren van een onderzoek. Hiermee heb je toegang tot belangrijke gebeurtenissen waarmee de omvang van de inbreuk kan worden bepaald en je sneller toegang hebt tot de Office 365 Management Activity-API.

> [!NOTE]
> Geavanceerde audit is beschikbaar voor organisaties met een Office 365 E5/A5/G5- of Microsoft 365 Enterprise E5/A5/G5-abonnement. Daarnaast kan een Microsoft 365 E5/A5/G5 Compliance- of E5/A5/G5 eDiscovery and Audit-add-on-licentie worden toegewezen aan gebruikers wanneer een licentie per gebruiker vereist is voor Geavanceerde audit-functies, zoals langetermijnretentie van auditlogboeken en toegang tot belangrijke gebeurtenissen voor onderzoeken. Zie voor meer informatie over licenties:<br/>- [Licentievereisten voor Geavanceerde audit](auditing-solutions-overview.md#licensing-requirements)<br/>- [Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit).

In dit artikel vind je een overzicht van de Geavanceerde audit-mogelijkheden en wordt beschreven hoe je gebruikers kunt instellen voor Geavanceerde audit.

## <a name="long-term-retention-of-audit-logs"></a>Langetermijnretentie van auditlogboeken

Met Geavanceerde audit blijven alle Exchange-, SharePoint- en Azure Active Directory-auditrecords één jaar bewaard. Dit gebeurt via een standaardbewaarbeleid voor auditlogboeken waarin auditrecords gedurende één jaar worden bewaard die de waarde van **Exchange**, **SharePoint** of **AzureActiveDirectory** bevatten voor de eigenschap **Workload** (waarmee de service wordt aangegeven waarin de activiteit heeft plaatsgevonden). Als auditrecords langer worden bewaard, kan dit handig zijn voor doorlopend forensisch en complianceonderzoek. Zie de sectie 'Standaardbewaarbeleid voor auditlogboeken' in [Bewaarbeleid voor auditlogboek beheren](audit-log-retention-policies.md#default-audit-log-retention-policy).

Binnenkort is er ook een optie beschikbaar om auditlogboeken tien jaar te bewaren. Dit is handig bij langetermijnonderzoeken en u kunt zo snel voldoen aan wettelijke en interne verplichtingen.

> [!NOTE]
> Als u auditlogboeken tien jaar wilt bewaren, hebt u een extra licentie voor de invoegtoepassing nodig. Zie de [veelgestelde vragen over Geavanceerde audit](#faqs-for-advanced-audit) in dit artikel voor meer informatie.

### <a name="audit-log-retention-policies"></a>Bewaarbeleid voor auditlogboeken beheren

Alle auditrecords die worden gegenereerd in andere services die niet vallen onder het standaardbewaarbeleid voor auditlogboeken (beschreven in de vorige sectie), worden 90 dagen bewaard. Maar u kunt aangepast bewaarbeleid voor auditlogboeken maken om andere auditrecords gedurende langere perioden tot tien jaar te bewaren. U kunt een beleid maken om auditrecords te bewaren op basis van een of meer van de volgende criteria:

- De Microsoft 365-service waar de gecontroleerde activiteiten plaatsvinden.

- Specifieke gecontroleerde activiteiten.

- De gebruiker die een gecontroleerde activiteit uitvoert.

U kunt ook opgeven hoelang u auditrecords die overeenkomen met het beleid en een prioriteitsniveau, wilt bewaren, zodat specifiek beleid prioriteit krijgt boven ander beleid. Elk aangepast bewaarbeleid voor auditlogboeken heeft voorrang op het standaardbewaarbeleid voor auditlogboeken als u Exchange-, SharePoint- of Azure Active Directory-auditrecords minder dan een jaar (of gedurende tien jaar) wilt bewaren voor bepaalde of alle gebruikers in uw organisatie. Zie [Bewaarbeleid voor auditlogboeken beheren](audit-log-retention-policies.md) voor meer informatie.

## <a name="access-to-crucial-events-for-investigations"></a>Toegang tot belangrijke gebeurtenissen voor onderzoeken

Met Geavanceerde audit kunnen organisaties forensisch en complianceonderzoek uitvoeren door toegang te bieden tot belangrijke gebeurtenissen, zoals wanneer e-mailitems zijn geopend, beantwoord en doorgestuurd, en wanneer en wat een gebruiker heeft gezocht in Exchange Online en SharePoint Online. Aan de hand van deze belangrijke gebeurtenissen kunt u mogelijke schendingen onderzoeken en de omvang van de inbreuk bepalen.  Geavanceerde audit bevat de volgende belangrijke gebeurtenissen:

- [MailItemsAccessed](#mailitemsaccessed)

- [Send](#send)

- [SearchQueryInitiatedExchange](#searchqueryinitiatedexchange)<sup>*</sup>

- [SearchQueryInitiatedSharePoint](#searchqueryinitiatedsharepoint)<sup>*</sup>

> [!NOTE]
> <sup>*</sup> Op dit moment is deze gebeurtenis niet beschikbaar in Office 365- en Microsoft 365 Government-omgevingen. Dit geldt ook voor GCC-, GCC High- en DoD-omgevingen.

### <a name="mailitemsaccessed"></a>MailItemsAccessed

De gebeurtenis MailItemsAccessed is een auditactie voor postvakken en wordt geactiveerd wanneer e-mailgegevens worden gebruikt door e-mailprotocollen en e-mailclients. Met behulp van de actie MailItemsAccessed kunnen onderzoekers gegevenslekken identificeren en de omvang bepalen van berichten die mogelijk zijn gecompromitteerd. Als een kwaadwillende gebruiker toegang heeft gekregen tot e-mailberichten, wordt de actie MailItemsAccessed geactiveerd, ook als er geen expliciet signaal is dat berichten daadwerkelijk zijn gelezen (met andere woorden het type toegang zoals een binding of synchronisatie wordt vastgelegd in de auditrecord).

De postvakactie MailItemsAccessed vervangt MessageBind in de logboekregistratie voor postvakcontrole in Exchange Online en is op de volgende punten verbeterd:

- MessageBind kon alleen worden geconfigureerd voor het aanmeldingstype van de AuditAdmin-gebruiker en was niet van toepassing op acties van gedelegeerden of eigenaren. MailItemsAccessed is van toepassing op alle aanmeldingstypen.

- MessageBind kon alleen worden gebruikt door een e-mailclient. De actie was niet van toepassing op synchronisatieactiviteiten. MailItemsAccessed-gebeurtenissen worden geactiveerd door de toegangstypen binding en synchronisatie.

- Door MessageBind-acties werden er meerdere auditrecords gemaakt wanneer hetzelfde e-mailbericht werd geopend, waardoor de audit onsamenhangend werd. MailItemsAccessed-gebeurtenissen worden echter samengevoegd in minder auditrecords.

Zie [Geavanceerde audit gebruiken om gecompromitteerde accounts te onderzoeken](mailitemsaccessed-forensics-investigations.md) voor informatie over auditrecords voor MailItemsAccessed-activiteiten.

Als u MailItemsAccessed-auditrecords wilt zoeken, kunt u zoeken naar de activiteit **Geopende postvakitems** in de vervolgkeuzelijst **Activiteiten in Exchange-postvak** in het [hulpprogramma Zoeken in auditlogboek](search-the-audit-log-in-security-and-compliance.md) in het Microsoft 365-compliancecentrum.

![Zoeken naar MailItemsAccessed-acties in het hulpprogramma Zoeken in auditlogboek](../media/AdvAudit_MailItemsAccessed.png)

U kunt ook de opdracht [Search-UnifiedAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-unifiedauditlog) of [Search-MailboxAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-mailboxauditlog) uitvoeren in Exchange Online PowerShell.

### <a name="send"></a>Send

De gebeurtenis Send is ook een auditactie voor postvakken en wordt geactiveerd wanneer een gebruiker een van de volgende acties uitvoert:

- Een e-mailbericht verzendt

- Een e-mailbericht beantwoordt

- Een e-mailbericht doorstuurt

Onderzoekers kunnen met behulp van de gebeurtenis Send e-mail identificeren die is verzonden vanaf een gecompromitteerd account. De auditrecord voor een Send-gebeurtenis bevat informatie over het bericht, zoals wanneer het bericht is verzonden, de InternetMessage-id, de onderwerpregel en of het bericht bijlagen bevat. Met deze auditgegevens kunnen onderzoekers informatie identificeren over e-mailberichten die zijn verzonden vanaf een gecompromitteerd account of door kwaadwillende gebruikers. Bovendien kunnen onderzoekers een Microsoft 365 eDiscovery-hulpprogramma gebruiken om te zoeken naar het bericht (met behulp van de onderwerpregel of bericht-id) om de geadresseerden te identificeren naar wie het bericht is verzonden en de werkelijke inhoud van het verzonden bericht.

Als u verzonden auditrecords wilt zoeken, kunt u zoeken naar de activiteit **Verzonden bericht** in de vervolgkeuzelijst **Activiteiten in Exchange-postvak** in het [hulpprogramma Zoeken in auditlogboek](search-the-audit-log-in-security-and-compliance.md) in het Microsoft 365-compliancecentrum.

![Zoeken naar Verzonden bericht-acties in het hulpprogramma Zoeken in auditlogboek](../media/AdvAudit_SentMessage.png)

U kunt ook de opdracht [Search-UnifiedAuditLog -Operations Send](/powershell/module/exchange/search-unifiedauditlog) of [Search-MailboxAuditLog -Operations Send](/powershell/module/exchange/search-mailboxauditlog) uitvoeren in Exchange Online PowerShell.

### <a name="searchqueryinitiatedexchange"></a>SearchQueryInitiatedExchange

De gebeurtenis SearchQueryInitiatedExchange wordt geactiveerd wanneer een persoon Outlook gebruikt om te zoeken naar items in een postvak. Gebeurtenissen worden geactiveerd wanneer zoekopdrachten worden uitgevoerd in de volgende Outlook-omgevingen:

- Outlook (desktopclient)

- De webversie van Outlook

- Outlook voor iOS

- Outlook voor Android

- Mail-app voor Windows 10

Onderzoekers kunnen via de gebeurtenis SearchQueryInitiatedExchange nagaan of een kwaadwillende gebruiker die mogelijk een account heeft gecompromitteerd, in het postvak heeft gezocht naar of geprobeerd toegang te krijgen tot gevoelige informatie. De auditrecord voor een gebeurtenis SearchQueryInitiatedExchange bevat informatie zoals de werkelijke tekst van de zoekquery. De auditrecord geeft ook aan in welke Outlook-omgeving de zoekopdracht is uitgevoerd. Door de zoekquery's te analyseren die een kwaadwillende gebruiker mogelijk heeft uitgevoerd, kan een onderzoeker beter begrijpen waarom er naar bepaalde e-mailgegevens zijn gezocht.

Als u SearchQueryInitiatedExchange-auditrecords wilt zoeken, kunt u zoeken naar de activiteit **Uitgevoerde zoekopdracht in e-mail** in de vervolgkeuzelijst **Activiteiten zoeken** in het [hulpprogramma Zoeken in auditlogboek](search-the-audit-log-in-security-and-compliance.md) in het compliancecentrum.

![Zoeken naar Uitgevoerde zoekopdracht in e-mail-acties in het hulpprogramma Zoeken in auditlogboek](../media/AdvAudit_SearchExchange.png)

Je kunt ook de opdracht [Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](/powershell/module/exchange/search-unifiedauditlog) uitvoeren in Exchange Online PowerShell.

> [!NOTE]
> Je moet logboekregistratie inschakelen voor SearchQueryInitiatedExchange, zodat je deze gebeurtenis kunt zoeken in het auditlogboek. Zie [Geavanceerde audit instellen](set-up-advanced-audit.md#step-2-enable-crucial-events) voor instructies.

### <a name="searchqueryinitiatedsharepoint"></a>SearchQueryInitiatedSharePoint

Net als bij het zoeken naar postvakitems wordt de gebeurtenis SearchQueryInitiatedSharePoint geactiveerd wanneer een persoon naar items zoekt in SharePoint. Gebeurtenissen worden geactiveerd wanneer zoekopdrachten worden uitgevoerd in de volgende typen SharePoint-sites:

- Startsites

- Communicatiesites

- Hubsites

- Sites die zijn gekoppeld aan Microsoft Teams

Onderzoekers kunnen met behulp van de gebeurtenis SearchQueryInitiatedSharePoint nagaan of een kwaadwillende gebruiker naar gevoelige informatie heeft gezocht (en mogelijk hier toegang toe heeft gekregen) in SharePoint. De auditrecord voor een gebeurtenis SearchQueryInitiatedSharePoint bevat ook informatie zoals de werkelijke tekst van de zoekquery. De auditrecord geeft ook aan welk type SharePoint-site is doorzocht. Door de zoekquery's te analyseren die een kwaadwillende gebruiker mogelijk heeft uitgevoerd, kan een onderzoeker beter begrijpen waarom en in welke mate er naar bepaalde bestandsgegevens zijn gezocht.

Als u SearchQueryInitiatedSharePoint-auditrecords wilt zoeken, kunt u zoeken naar de activiteit **Uitgevoerde zoekopdracht in SharePoint** in de vervolgkeuzelijst **Activiteiten zoeken** in het [hulpprogramma Zoeken in auditlogboek](search-the-audit-log-in-security-and-compliance.md) in het compliancecentrum.

![Zoeken naar Uitgevoerde zoekopdracht in SharePoint-acties in het hulpprogramma Zoeken in auditlogboek](../media/AdvAudit_SearchSharePoint.png)

Je kunt ook de opdracht [Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](/powershell/module/exchange/search-unifiedauditlog) uitvoeren in Exchange Online PowerShell.

> [!NOTE]
> Je moet logboekregistratie inschakelen voor SearchQueryInitiatedSharePoint, zodat je deze gebeurtenis kunt zoeken in het auditlogboek. Zie [Geavanceerde audit instellen](set-up-advanced-audit.md#step-2-enable-crucial-events) voor instructies.

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>Toegang met hoge bandbreedte tot de Office 365 Management Activity-API

Organisaties met toegang tot auditlogboeken via de Office 365 Management Activity-API hadden te maken met beperkingslimieten op uitgeversniveau. Dit betekent dat voor een uitgever die gegevens ophaalt namens meerdere klanten, de limiet werd gedeeld door al die klanten.

Met de release van Geavanceerde audit gaan we over van een limiet op uitgeversniveau naar een limiet op tenantniveau. Hierdoor krijgt elke organisatie een eigen, volledig toegewezen bandbreedtequotum voor toegang tot de auditgegevens. De bandbreedte is geen statische, vooraf gedefinieerde limiet, maar is gebaseerd op een combinatie van factoren, waaronder het aantal seats in de organisatie en dat E5/A5/G5-organisaties meer bandbreedte krijgen dan niet-E5/A5/G5-organisaties.

Aan alle organisaties wordt in eerste instantie een basislijn van 2000 aanvragen per minuut toegewezen. Deze limiet wordt dynamisch verhoogd, afhankelijk van het aantal seats en het licentieabonnement van een organisatie. E5/A5/G5-organisaties krijgen ongeveer twee keer zoveel bandbreedte als niet-E5/A5/G5-organisaties. Er is ook een limiet voor de maximale bandbreedte om de status van de service te beschermen.

Zie de sectie over API-beperking in de Engelstalige [Office 365 Management Activity-API-handleiding](/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling) voor meer informatie.

## <a name="faqs-for-advanced-audit"></a>Veelgestelde vragen over Geavanceerde audit

**Heeft elke gebruiker een E5/A5/G5-licentie nodig om gebruik te kunnen maken van Geavanceerde audit?**

Om gebruik te kunnen maken van Geavanceerde audit-mogelijkheden op gebruikersniveau, moet aan een gebruiker een E5/A5/G5-licentie zijn toegewezen. Er zijn bepaalde mogelijkheden waarmee kan worden gecontroleerd op de juiste licentie om de functie beschikbaar te maken voor de gebruiker. Als je bijvoorbeeld de auditrecords wilt bewaren voor een gebruiker aan wie langer dan 90 dagen niet de juiste licentie is toegewezen, wordt er een foutbericht weergegeven.

**Mijn organisatie heeft een E5/A5/G5-abonnement. Moet ik iets doen om toegang te krijgen tot auditrecords voor belangrijke gebeurtenissen?**

Voor in aanmerking komende klanten en gebruikers aan wie de juiste licentie is toegewezen, is er geen actie om toegang te krijgen tot belangrijke auditgebeurtenissen.

**Wat gebeurt er met de auditlogboekgegevens van mijn organisatie als ik een bewaarbeleid voor het auditlogboek van tien jaar heb gemaakt toen de functie algemeen beschikbaar werd, maar voordat de vereiste licentie voor de invoegtoepassing beschikbaar werd?**

Alle auditlogboekgegevens die vallen onder een bewaarbeleid voor auditlogboeken van tien jaar dat u hebt gemaakt nadat de functie in het laatste kwartaal van 2020 algemeen beschikbaar werd, blijven tien jaar bewaard. Dit geldt ook voor bewaarbeleid voor auditlogboeken gedurende 10 jaar dat is gemaakt voordat de vereiste licentie voor de invoegtoepassing werd uitgebracht voor aankoop. Aangezien de licentie voor het bewaren van het auditlogboek gedurende tien jaar nu beschikbaar is, moet u deze invoeglicenties kopen en toewijzen aan alle gebruikers van wie de auditgegevens worden vallen onder een bewaarbeleid voor auditlogboeken van tien jaar.

**Zijn de nieuwe gebeurtenissen in Geavanceerde audit beschikbaar in de Office 365 Management Activity-API?**

Ja. Zolang auditrecords worden gegenereerd voor gebruikers met de juiste licentie, hebt u toegang tot deze records via de Office 365 Management Activity-API.

**Betekent hogere bandbreedte betere latentie of hogere SLA?**

Op dit moment biedt hoge bandbreedte een betere pijplijn, met name voor organisaties met een grote hoeveelheid controlesignalen en significante verbruikspatronen. Meer bandbreedte kan leiden tot betere latentie. Maar er is geen SLA gekoppeld aan hoge bandbreedte. Standaardlatentie wordt beschreven en deze latentie verandert niet met de release van Geavanceerde audit.
