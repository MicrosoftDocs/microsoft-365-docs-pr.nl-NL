---
title: EOP-functies
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: De volgende tabel bevat een overzicht van de functies die beschikbaar zijn in de Exchange Online Protection (EOP) hosting email filtering service.
ms.openlocfilehash: 58893cd4a4d6c90c8d19de5a6b2f0d108ee797e0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202925"
---
# <a name="eop-features"></a>EOP-functies

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


De volgende tabel bevat een overzicht van de functies die beschikbaar zijn in de Exchange Online Protection (EOP) hosting email filtering service.

> [!TIP]
> De [routekaart voor Microsoft 365 voor bedrijven](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) is een goede bron voor het vinden van informatie over aanstaande nieuwe functies. Zie beschrijving van de [Exchange Online Protection Service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)voor een bredere weergave van de functies die beschikbaar zijn voor de verschillende EOP-abonnementen.

****

|Functie|Beschrijving|
|---|---|
|**Beveiliging tegen ongewenste e-mail**||
|Detectie van inkomende spam|Zie [bescherming tegen spam in Microsoft 365](anti-spam-protection.md)voor meer informatie. <br/><br/> In standalone EOP-omgevingen waar EOP on-premises Exchange-postvakken beschermt, moet u regels voor e-mailstroom (ook wel transportregels genoemd) configureren in on-premises Exchange om de EOP-spamfilterbeoordeling te vertalen, zodat de regel voor ongewenste e-mail het bericht kan verplaatsen naar de map Ongewenste e-mail. Zie voor meer informatie [STANDALONE EOP voor het bezorgen van spam op de map Ongewenste e-mail in hybride omgevingen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)|
|Uitgaande spam detectie|Beveiliging tegen ongewenste e-mail wordt altijd ingeschakeld als u de service gebruikt voor het verzenden van uitgaande e-mail. Zie [uitgaande spam bescherming](outbound-spam-controls.md)voor meer informatie.|
|Backscatter-bescherming|Zie [Backscatter en EOP](backscatter-messages-and-eop.md)voor meer informatie.|
|Filters voor bulk mail filteren|EOP gebruikt de drempelwaarde voor bulk klachten (BCL) om bulk-e-mailberichten als spam te markeren. Zie de volgende onderwerpen voor meer informatie: <br/><br/> [Wat is het verschil tussen ongewenste e-mail en bulkmail?](what-s-the-difference-between-junk-email-and-bulk-email.md) <br/> [Bulk klachten niveau (BCL) in EOP](bulk-complaint-level-values.md) <br/> [Beleid tegen ongewenste e-mail configureren](configure-your-spam-filter-policies.md)|
|Lijst met schadelijke URL-blok lijsten|EOP gebruikt verschillende URL-blok lijsten waarmee bekende kwaadaardige koppelingen binnen berichten kunnen worden gedetecteerd.|
|Bescherming tegen phishing|EOP bevat 750.000-domeinen met bekende spammers.|
|Beveiliging tegen adresvervalsing|Zie [bescherming tegen spoofing](anti-spoofing-protection.md)voor meer informatie.|
|**Spam beheer**||
|Veilige afzenders en geblokkeerde afzenders configureren|Zie [lijsten met veilige afzenders maken](create-safe-sender-lists-in-office-365.md) en [lijsten met geblokkeerde afzenders](create-block-sender-lists-in-office-365.md)maken voor meer informatie.|
|Aangepast Antispambeleid maken|Voor een betere granulatie kunt u een aangepast Antispambeleid maken en deze toepassen op opgegeven gebruikers, groepen of domeinen in uw organisatie. Aangepaste beleidsregels hebben altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (dat wil zeggen, de actieve order) van uw aangepaste beleid wijzigen. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|De acties voor spam gefilterde berichten configureren|U kunt bijvoorbeeld door inhoud gefilterde berichten verwijderen of ze verzenden naar de map Ongewenste E-mail of de quarantaine. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|Internationale spamfilters|U kunt antispam filters configureren om berichten te filteren die in bepaalde talen zijn geschreven of die zijn verzonden vanuit bepaalde landen of regio's. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.|
|Spam beheren via Outlook of de webversie van Outlook (voorheen Outlook Web app)|Beheerders en eindgebruikers kunnen lijsten met veilige afzenders en geblokkeerde afzenders maken. Zie voor meer informatie [over instellingen voor ongewenste e-mail in Outlook](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook). <br/><br/> Als u gebruikmaakt van EOP om on-premises postvakken te beschermen, moet u eerst adreslijstsynchronisatie gebruiken om ervoor te zorgen dat deze instellingen worden gesynchroniseerd met de service. Zie voor meer informatie over het instellen van adreslijstsynchronisatie ' adreslijstsynchronisatie gebruiken voor het beheren van e-mail gebruikers ' in [e-mail gebruikers beheren in EOP](manage-mail-users-in-eop.md).|
|Meld onjuiste positieve en onjuiste negatieven aan Microsoft.|Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).|
|Meldingen van de Quarantine voor spam van eindgebruikers|Voor meer informatie raadpleegt u [spam meldingen voor eindgebruikers](use-spam-notifications-to-release-and-report-quarantined-messages.md) en [configureert u spam meldingen voor eindgebruikers](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications).|
|Berichten in de quarantaine portal weergeven, zoeken en beheren.|Zie voor meer informatie geplaatste [berichten en bestanden beheren als beheerder in EOP](manage-quarantined-messages-and-files.md) of geplaatste [berichten in quarantaine plaatsen en vrijgeven als gebruiker](find-and-release-quarantined-messages-as-a-user.md).|
|Berichtkoppen in de quarantaine|Nadat u de kop van het bericht in de quarantaine hebt weergegeven, kunt u de koptekst ook kopiëren en plakken in de kop-en [voet](https://mha.azurewebsites.net/) tekst van het bericht om erachter te komen wat er is gebeurd met het bericht.|
|**Beveiliging tegen malware**||
|Beveiliging van meerdere engines tegen malware|Meerdere anti malware-engines helpen onze klanten altijd automatisch te beschermen.|
|De mogelijkheid om het filteren van schadelijke software uit te schakelen|U kunt het filteren van schadelijke software niet uitschakelen. We geloven dat het voor de bescherming van uw e-mailberichten omgeving een cruciale en strikte beschermingsniveau biedt voor al onze klanten een belangrijk onderdeel van de inuitgebreide strategie. Daarom wordt het filteren van malware automatisch ingeschakeld voor alle klanten.|
|Malwarecontrole van de berichttekst en bijlagen|Met de service wordt de actieve nettolading gecontroleerd in de hoofdtekst van het bericht en alle berichtbijlagen voor malware.|
|Standaard-of aangepaste meldingen voor schadelijke software|U kunt een waarschuwingsbericht verzenden naar afzenders of beheerders. Zie voor meer informatie [het artikel anti malware-beleidsregels configureren](configure-anti-malware-policies.md).|
|Meldingen van ontvangers|U kunt het bericht op de Stille quarantaine plaatsen of in quarantaine plaatsen en ook alle bijlagen afleveren met alle bijlagen die zijn vervangen door één tekstbestand met standaardtekst of aangepaste tekst. Zie voor meer informatie [het artikel anti malware-beleidsregels configureren](configure-anti-malware-policies.md).|
|Veelgebruikte bijlagen filteren|U kunt een lijst met bestandstypen inschakelen en aanpassen die altijd malware zijn. Zie [bescherming tegen malware in EOP](anti-malware-protection.md)voor meer informatie.|
|Bescherming tegen spyware|Beveiliging tegen malware omvat anti-virusbescherming en bescherming tegen spyware.|
|Aangepaste beleidsregels voor malware filters maken|Voor een betere granulatie kunt u aangepaste beleidsregels voor malware filters maken en deze toepassen op opgegeven gebruikers, groepen of domeinen in uw organisatie. Aangepaste beleidsregels hebben altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (dat wil zeggen, de actieve order) van uw aangepaste beleid wijzigen. Zie voor meer informatie [het artikel anti malware-beleidsregels configureren](configure-anti-malware-policies.md).|
|**E-mail Routering en connectors**||
|Voorwaardelijke e-mail routering|Zie [scenario: voorwaardelijke e-mail routering in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing)voor meer informatie.|
|Opportunistisch of geforceerd TLS|Opportunistisch of afgedwongen TLS is beschikbaar met connectors. Met opportunistisch TLS wordt een TLS-verbinding geprobeerd, maar wordt een SMTP-verbinding gebruikt als de TLS-verbinding mislukt. TLS dwingen TLS-verbindingen af te dwingen, wat betekent dat het bericht wordt afgewezen als de TLS-verbinding mislukt. Voor meer informatie over TLS, beveiliging en connectors raadpleegt [u connectors instellen voor de beveiligde e-mail stroom met een partnerorganisatie](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner).|
|Regionale routering (de beperking van de e-mail stroom naar een specifieke regio)|Zie voor meer informatie de sectie ' EOP datacenters ' in het [overzicht van Exchange Online Protection](exchange-online-protection-overview.md).|
|Het hulpprogramma SMTP-verbindings controle|Voor meer informatie over het gebruik van dit hulpprogramma voor het testen van uw e-mail stroom raadpleegt u [e-mail stroom testen door uw Microsoft 365-connectors te valideren](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).|
|Subdomeinen afstemmen|Zie [e-mail stroom in EOP](mail-flow-in-eop.md)voor meer informatie over het inschakelen van e-mail stromen naar en van subdomeinen van uw geaccepteerde domeinen.|
|**Regels voor e-mail stroom**||
|Op beleids basis filteren en acties|Aangepaste beleidsregels zijn gebaseerd op Exchange-e-mail stroom regels (ook wel een zogenaamde transportregels genoemd). U kunt filteren op domein, trefwoord, bestandsnaam, bestandstype, onderwerpregel, berichttekst, afzender, geadresseerde, koptekst en IP-adres. Zie voor meer informatie [e-mail stroom regels (transportregels) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md).|
|Filteren op tekstpatronen|Voor e-mail stroom regels kunnen met een matrix of reguliere expressies tekst worden vergeleken. U kunt ook één tekenreeks of een matrix met tekenreeksen gebruiken die overeenkomen met de verschillende berichteigenschappen, zoals het adres, het onderwerp, de hoofdtekst of de naam van de bijlage. Zie voor meer informatie [e-mail stroom regels (transportregels) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md)|
|Aangepaste woordenlijsten|De regels voor e-mail stroom kunnen lange lijsten met tekst en trefwoorden bevatten, die dezelfde functionaliteit bieden als een aangepaste woordenlijst.|
|Beleidsregels per domein|Het bereik van een e-mail stroom regel kan worden aangepast aan de naam van de afzender of het domein van de geadresseerde, IP-adresbereiken, adres trefwoorden of patronen, groepslidmaatschappen en andere voorwaarden.|
|Bijlage Scanning|U kunt regels maken voor het scannen van de bestandsnaam, de extensie en de inhoud van de bijlage.|
|Meldingen voor beleidsregels verzenden naar de afzender|U kunt berichten afkeuren en een rapport over niet-uitgevoerde bezorging (ook wel een NDR genoemd of bericht met **de status** van een bericht) verzenden naar de afzender via het **bericht afwijzen met** de uitgebreide actiecode. Zie [acties voor e-mail stroom regels in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)voor meer informatie.|
|Berichten doorsturen of kopiëren|Voor e-mail stroom regels kunt u omleiden, geadresseerden toevoegen met CC of BCC, simpelweg geadresseerden toevoegen en andere opties. Zie [acties voor e-mail stroom regels in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)voor meer informatie.|
|De prioriteit van regels in meerdere regels aanpassen|Via het Exchange-Beheercentrum kunt u de volgorde wijzigen waarin regels worden verwerkt.|
|Berichten filteren en de routering of kenmerken van een bericht wijzigen|U kunt berichten filteren op basis van diverse voorwaarden en vervolgens een reeks acties toepassen op elk bericht. Zie voor meer informatie [e-mail stroom regels (transportregels) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md).|
|Het betrouwbaarheidsniveau voor ongewenste e-mail (SCL) van een bericht per regel wijzigen.|U kunt een in-transit bericht controleren en een betrouwbaarheidsniveau voor ongewenste e-mail toewijzen op basis van criteria die u kiest. Zie voor meer informatie [de regels voor e-mail stroom gebruiken voor het instellen van het spam betrouwbaarheidsniveau (SCL) in berichten](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).|
|Bijlagen in berichten controleren|U kunt de inhoud van een bijlage of de kenmerken van een bijgevoegd bestand bekijken en een actie definiëren die u kunt uitvoeren op basis van wat er wordt gevonden. Zie voor meer informatie [e-mail stroom regels gebruiken om berichten bijlagen te controleren in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments).|
|**Beheer**||
|Web-based beheer|Beheerders kunnen de service beheren in het Exchange Admin Center (SBV), dat wordt ondersteund in talen van 60. Zie [Exchange-Beheercentrum in zelfstandige EOP](exchange-admin-center-in-exchange-online-protection-eop.md)voor meer informatie.|
|Adreslijstsynchronisatie|Adreslijstsynchronisatie is beschikbaar via het Azure Active Directory-synchronisatieprogramma. Zie voor meer informatie de sectie ' adreslijstsynchronisatie gebruiken voor het beheren van e-mail gebruikers ' in [e-mail gebruikers beheren in EOP](manage-mail-users-in-eop.md).|
|Op mappen gebaseerde rand blokkeren (DBEB)|Met de functie DBEB kunt u berichten voor ongeldige geadresseerden op de netwerk perimeter van de service weigeren. Met DBEB kunnen beheerders e-mail geadresseerden toevoegen aan Microsoft 365 en alle berichten die zijn verzonden naar e-mailadressen die niet beschikbaar zijn in Microsoft 365 blokkeren. Voor meer informatie over het configureren van DBEB raadpleegt u [op mappen gebaseerde rand blokkeren om berichten die naar ongeldige geadresseerden zijn verzonden, af te](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)wijzen.|
|PowerShell|De volledige functionaliteit van EOP is beschikbaar in standalone EOP PowerShell. Zie [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell)voor meer informatie.|
|**Rapporten en logboekregistratie**||
|Bericht traceren|Beheerders kunnen e-mailberichten volgen wanneer ze de service passeren. U kunt bepalen of een specifiek e-mailbericht is ontvangen, afgewezen, uitgesteld of geleverd door de service. Hiermee kunt u de vragen van gebruikers op een efficiënte manier beantwoorden, problemen met de e-mail stroom oplossen, beleidswijzigingen valideren en contact opnemen met de technische ondersteuning. Voor meer informatie raadpleegt u [bericht tracering in het beveiligings & nalevings centrum](message-trace-scc.md).|
|Webgebaseerde rapporten|De e-mail beveiligingsrapporten in het compliance-& Beveiligingscentrum zorgen voor berichten gegevens. U kunt bijvoorbeeld controleren hoeveel spam en malware wordt gedetecteerd, of hoe vaak de regels voor de e-mail stroom worden vergeleken. Met deze interactieve rapporten kunt u snel een visueel rapport met overzichtsgegevens weergeven en meer details over afzonderlijke berichten weergeven, met een afstand van 90 dagen. Zie voor meer informatie [rapporten over e-mail beveiliging gebruiken om gegevens over malware, spam en regel detectie te bekijken](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports).|
|Controlelogboekregistratie|Het rapport rollen groep van beheerder en het controlelogboek van de beheerder zijn beschikbaar voor EOP-beheerders. Zie [rapporten controleren in EOP](auditing-reports-in-eop.md)voor meer informatie.|
|**Serviceniveau overeenkomsten (Service overeenkomst) en support**||
|SLA effectiviteit van de spam|\> 99%|
|SLA met positieve verhouding|\< 1:250000|
|Virus detectie en de blokkering van SLA|100% van bekende virussen|
|SLA de maandelijkse uptime|99,999%|
|Technische ondersteuning van telefoon en Web, 24 uur per dag, zeven dagen per week|Zie [Help en ondersteuning voor EOP](help-and-support-for-eop.md)voor meer informatie over de EOP-Help en ondersteuningsopties.|
|**Andere functies**||
|Een geografisch redundant globaal netwerk van servers|EOP wordt uitgevoerd in een wereldwijd netwerk van datacenters die zijn ontworpen om de beste beschikbaarheid te bieden. Zie voor meer informatie de sectie ' EOP datacenters ' in het [overzicht van Exchange Online Protection](exchange-online-protection-overview.md).|
|Message Queuing wanneer de on-premises server geen e-mail kan accepteren|Berichten in deze vertraagde blijven in onze wachtrijen voor één dag bestaan. De nieuwe pogingen voor het bericht worden weergegeven op basis van de fout die het e-mailsysteem van de ontvanger van de geadresseerde ontvangt. Gemiddeld worden berichten elke 5 minuten opnieuw geprobeerd. Zie voor meer informatie de [Veelgestelde vragen over EOP in de wachtrij geplaatst, uitgesteld en ingedrukte berichten](eop-queued-deferred-and-bounced-messages-faq.md).|
|Office 365-bericht versleuteling beschikbaar als service voor een invoegtoepassing|Zie voor meer informatie [versleutelen in Office 365](../../compliance/encryption.md).|
|
