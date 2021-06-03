---
title: Metagegevensvelden in documenten in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In dit artikel worden de metagegevensvelden voor documenten in een revisieset in een zaak in Advanced eDiscovery in Microsoft 365.
ms.openlocfilehash: 7b8628973a8b07a3cd31e2b42df28c181e77e288
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730496"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Metagegevensvelden in documenten in Advanced eDiscovery

De volgende tabel bevat de metagegevensvelden voor documenten in een revisieset in een zaak in Advanced eDiscovery. De tabel bevat de volgende informatie:

- **Veldnaam** en **weergaveveldnaam: de** naam van het metagegevensveld en de naam van het veld dat wordt weergegeven bij het weergeven van de bestandsmetagegevens van een geselecteerd document in een revisieset. Sommige metagegevensvelden worden niet opgenomen bij het weergeven van de bestandsmetagegevens van een document. Deze velden zijn gemarkeerd met een sterretje (*).

- **Doorzoekbare veldnaam:** De naam van de eigenschap die u kunt zoeken bij het uitvoeren van een [revisiesetquery.](review-set-search.md) Een lege cel betekent dat u niet kunt zoeken naar het veld in een revisiesetquery.

- **Naam van geëxporteerd veld:** De naam van het metagegevensveld dat is opgenomen wanneer documenten worden geëxporteerd.  Een lege cel betekent dat het veld niet is opgenomen in de geëxporteerde metagegevens.

- **Beschrijving:** Een beschrijving van het metagegevensveld.

> [!NOTE]
> In **het veld Trefwoorden** in [zoekopdrachtenset wordt](./review-set-search.md) KQL (Keyword Query Language) gebruikt. De velden in  de kolom Zoekbare veldnaam  kunnen worden gebruikt in het veld Trefwoorden in een zoekactie om complexe query's te vormen zonder dat u de opbouwfunctie voor query's moet gebruiken. Zie Verwijzing naar de syntaxis van de [trefwoordquerytaal voor](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)meer informatie over KQL.

|**Veldnaam** en **veldnaam weergeven**|**Doorzoekbare veldnaam**|**Naam van geëxporteerd veld**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|Bijlage-inhouds-id|AttachmentContentId||Bijlageinhoud Id van het item.|
|Score voor clientvoorrechten van advocaten|AttorneyClientPrivilegeScore||Inhoudsscore van het attorney-client privilege-model.|
|Auteur|Auteur|Doc_authors|Auteur van de metagegevens van het document.|
|BCC|BCC|Email_bcc|BCC-veld voor berichttypen. Notatie is **DisplayName. \<SMTPAddress>**|
|CC|CC|Email_cc|CC-veld voor berichttypen. Notatie is **DisplayName. \<SMTPAddress>**|
|Compliancelabels|Compliancelabels|Compliance_labels|[Bewaarlabels](retention.md) die zijn toegepast op inhoud in Office 365.|
|Samengesteld pad|CompoundPath|Compound_path|Human readable path that describes the source of the item.|
|Inhoud*|Content||Geëxtraheerde tekst van het item.|
|Gespreksonderwerp|Gespreksonderwerp||Gespreksonderwerp van het item.|
|Gespreksonderwerp|Gespreksonderwerp||Gespreksonderwerp van het item.|
|Gespreks-id|ConversationId|Conversation_ID|Gespreks-id van het bericht.|
|Gespreksindex||Conversation_index|Gespreksindex uit het bericht.|
|Gespreks pdf-tijd|ConversationPdfTime||Datum waarop de PDF-versie van het gesprek is gemaakt.|
|Gespreksactie Burn Time|ConversationRedactionBurnTime||Datum waarop de PDF-versie van het gesprek is gemaakt voor Chat.|
|||Converted_file_path|Het pad van het geconverteerde exportbestand. Alleen voor intern Microsoft-gebruik.|
|Documentdatum gemaakt|CreatedTime|Doc_date_created|Datum maken op basis van documentmetagegevens.|
|Bewaarder|Bewaarder|Bewaarder|De naam van de bewaarder aan het item is gekoppeld.|
|Datum|Datum|Datum|Datum is een berekend veld dat afhankelijk is van het bestandstype.<br /><br />E-mail: Verzonden datum<br />E-mailbijlagen: Laatst gewijzigde datum van het document; indien niet beschikbaar, de verzonden datum van de bovenliggende<br />Ingesloten documenten: Laatst gewijzigde datum van het document; indien niet beschikbaar, de laatst gewijzigde datum van de ouder<br />SPO-documenten (inclusief moderne bijlagen): SharePoint Laatst gewijzigde datum; indien niet beschikbaar, worden de documenten voor het laatst gewijzigd<br />Niet-Office 365 documenten: Laatst gewijzigde datum<br />Vergaderingen: begindatum van vergadering<br />VoiceMail: Datum verzonden<br />Chatbericht: Verzonden datum|
|Andere paden|Dedupedcompoundpath|Deduped_compound_path|Lijst met samengestelde paden van documenten die exacte duplicaten zijn (e-mail: op basis van inhoud, documenten: op basis van hash).|
|Andere bewaarders|DedupedCustodians|Deduped_custodians|Lijst met bewaarders van documenten die exacte duplicaten zijn (voor e-mail, op basis van inhoud; voor documenten, op basis van hash).|
|Andere bestands-eds|DedupedFileIds|Deduped_file_IDs|Lijst met bestands-eds van documenten die exacte duplicaten zijn (voor e-mail, op basis van inhoud; voor documenten, op basis van hash).|
|Document opmerkingen|DocComments|Doc_comments|Opmerkingen van de metagegevens van het document.|
|Documentbedrijf||Doc_company|Bedrijf van de metagegevens van het document.|
|DocIndex*|||De index in het gezin. **-1** of **0** betekent dat het de hoofdmap is.|
|Documenttrefwoorden||Doc_keywords|Trefwoorden uit de metagegevens van het document.|
|Document gewijzigd door||Doc_modified_by|Laatst gewijzigde datum op basis van documentmetagegevens.|
|Documentherziening|Doc_Version|Doc_Version|Revisie van de metagegevens van het document.|
|Documentonderwerp||Doc_subject|Onderwerp van de metagegevens van het document.|
|Documentsjabloon||Doc_template|Sjabloon van de metagegevens van het document.|
|DocLastSavedBy||Doc_last_saved_by|De naam van de gebruiker die het document het laatst heeft opgeslagen.|
|Dominant thema|DominantTheme|Dominant_theme|Dominant thema zoals berekend voor analyse.|
|Subset dupliceren||Duplicate_subset|Groeps-id voor exacte duplicaten.|
|EmailAction*||Email_action|Waarden zijn **Geen,** **Beantwoorden** of **Doorsturen;** op basis van de onderwerpregel van een bericht.|
|Ontvangstbevestiging per e-mail aangevraagd||Email_delivery_receipt|E-mailadres dat wordt opgegeven in internetkoppen voor ontvangstbevestiging.|
|Belang|EmailImportance|Email_importance|Belang van het bericht: **0** - Laag; **1** - Normaal; **2** - Hoog|
|EmailInternetHeaders|EmailInternetHeaders|Email_internet_headers|De volledige set e-mailkoppen uit het e-mailbericht|
|EmailLevel*||Email_level|Geeft het niveau van een bericht aan in de e-mailthread waarin het hoort; bijlagen nemen de waarde van het bovenliggende bericht over.|
|E-mailbericht-id||Email_message_ID|Internetbericht Id van het bericht.|
|EmailReadReceiptRequested||Email_read_receipt|E-mailadres dat wordt opgegeven in internetkoppen voor leesbevestiging.|
|E-mailbeveiliging|E-mailbeveiliging|Email_security|Beveiligingsinstelling van het bericht: **0** - Geen; **1** - Ondertekend; **2** - Versleuteld; **3** - Versleuteld en ondertekend.|
|E-mailgevoeligheid|EmailSensitivity|email_sensitivity|Gevoeligheidsinstelling van het bericht: **0** - Geen; **1** Persoonlijk; **2** - Privé; **3** - CompanyConfidential.|
|E-mailset|E-mailset|Email_set|Groeps-id voor alle berichten in dezelfde e-mailset.|
|EmailThread*||Email_thread|Positie van het bericht in de e-mailset; bestaat uit knooppunt-ID's van de hoofdmap naar het huidige bericht en worden gescheiden door perioden (.).|
|||Export_native_path|Het pad van het geëxporteerde bestand.|
|Inhoudstype geëxtraheerd||Native_type|Geëxtraheerd inhoudstype, in de vorm van mimetype; bijvoorbeeld **image/jpeg**|
|||Extracted_text_path|Het pad naar het uitgepakte tekstbestand in de export.|
|GeëxtraheerdTextLength*||Extracted_text_length|Het aantal tekens in de uitgepakte tekst.|
|FamilyDuplicateSet*||Family_duplicate_set|Numerieke id voor gezinnen die exacte duplicaten van elkaar zijn (dezelfde inhoud en allemaal dezelfde bijlagen).|
|Gezins-id|FamilyId|Family_ID|Familie-id groeperen alle items; voor e-mail bevat dit het bericht en alle bijlagen; voor documenten omvat dit het document en eventuele ingesloten items.|
|Gezinsgrootte||Family_size|Het aantal documenten in het gezin.|
|Bestandsklasse|FileClass|File_class|Voor inhoud van SharePoint en OneDrive: **Document**; voor inhoud van Exchange: **E-mail** of **Bijlage.**|
|Bestands-id|FileId|File_ID|Documentaanduiding die uniek is in de zaak.|
|Datum van bestandssysteem gemaakt||File_system_date_created|Gemaakt datum uit bestandssysteem (alleen van toepassing op niet-Office 365 gegevens).|
|Datum van bestandssysteem gewijzigd||File_system_date_modified|Gewijzigde datum van bestandssysteem (alleen van toepassing op niet-Office 365 gegevens).|
|Bestandstype|FileType||Bestandstype van het item op basis van bestandsextensie.|
|Groeps-id|GroupID||Groeps-id voor gegroepeerde inhoud.|
|Heeft bijlage|HasAttachment|Email_has_attachment|Hiermee wordt aangegeven of het bericht bijlagen heeft.|
|Heeft een advocaat|HasAttorney||**Waar** wanneer ten minste één van de deelnemers wordt gevonden in de lijst met advocaten; anders is de waarde **Onwaar.**|
|HasText*||Has_text|Hiermee geeft u aan of het item wel of geen tekst bevat. mogelijke waarden zijn **Waar** en **Onwaar.**|
|Onveranderlijke id||Immutable_ID|Deze id wordt gebruikt om een document in een revisieset uniek te identificeren. Dit veld kan niet worden gebruikt in een zoekopdracht in een revisieset en de id kan niet worden gebruikt voor toegang tot een document op de oorspronkelijke locatie.|
|Inclusief type|InclusiveType|Inclusive_type|Inclusief type berekend voor analyse: **0** - niet inclusief; **1** - inclusief; **2** - inclusief min; **3** - inclusief exemplaar.|
|In Antwoord op id||In_reply_to_ID|In antwoord op Id van het bericht.|
|InputFileExtension||Original_file_extension|De oorspronkelijke bestandsextensie van het bestand.|
|InputFileID||Input_file_ID|De bestands-id van het item op het hoogste niveau in de revisieset. Voor een bijlage is deze id de id van de bovenliggende id. Dit kan worden gebruikt om gezinnen samen te groepen.|
|Is moderne bijlage| IsModernAttachment|  |Dit bestand is een moderne bijlage of gekoppeld bestand.|
|Is van documentversie | IsFromDocumentVersion |  |Huidig document is afkomstig uit een andere versie van een ander document.|
|Is e-mailbijlage | IsEmailAttachment|  |Dit item is afkomstig van een e-mailbijlage die wordt weergegeven als een bijgevoegd item aan het bericht.|
|Is inlinebijlage| IsInlineAttachment|  |Dit is inline bijgevoegd en wordt weergegeven in de tekst van het bericht.|
|Is representatief|IsRepresentative|Is_representative|Eén document in elke set exacte duplicaten wordt gemarkeerd als representatief.|
|Itemklasse|Itemclass|Item_class|Itemklasse die wordt geleverd door exchange-server; bijvoorbeeld **IPM. Opmerking**|
|Laatst gewijzigde datum|LastModifiedDate|Doc_date_modified|Laatst gewijzigde datum uit documentmetagegevens.|
|Id laden|LoadId|Load_ID|De id van de laadset waarin het item is toegevoegd aan een revisieset.|
|Locatie|Locatie|Locatie|Tekenreeks die het type locatie aangeeft waaruit documenten zijn afkomstig.<br /><br />**Geïmporteerde** gegevens - Niet-Office 365 gegevens<br />**Teams** - Microsoft Teams<br />**Exchange** - Exchange postvakken<br />**SharePoint** - SharePoint sites<br />**OneDrive** - OneDrive accounts|
|Locatienaam|Locatienaam|Location_name|Tekenreeks die de bron van het item identificeert. Voor exchange is dit het SMTP-adres van het postvak. voor SharePoint en OneDrive, de URL voor de siteverzameling.|
|||Marked_as_pivot|Dit bestand is de draaipunt in een bijna dubbele set.|
|Gemarkeerd als representatief|MarkAsRepresentative||Eén document uit elke set exacte duplicaten wordt gemarkeerd als vertegenwoordigers.|
|Einddatum vergadering|MeetingEndDate|Meeting_end_date|Einddatum van vergadering voor vergaderingen.|
|Begindatum vergadering|MeetingStartDate|Meeting_start_date|Begindatum van vergadering voor vergaderingen.|
|Type bericht|MessageKind|Message_kind|Het type bericht dat u wilt zoeken. Mogelijke waarden: contactpersonen docs email **<br /> <br /> <br /> <br /> <br /> externaldata <br /> faxes <br /> im <br /> journals <br /> meetings <br /> microsoftteams** (returns items from chats, meetings, and calls in Microsoft Teams) **<br /> notes posts <br /> <br /> rssfeeds <br /> tasks <br /> voicemail**| 
|Moderne bovenliggende bijlage-id||ModernAttachment_ParentId|De onveranderlijke id van het bovenliggende document.|
|Native Extension|NativeExtension|Native_extension|Oorspronkelijke uitbreiding van het item.|
|Oorspronkelijke bestandsnaam|NativeFileName|Native_file_name|Oorspronkelijke bestandsnaam van het item.|
|NativeMD5||Native_MD5|MD5-hash (128-bits hashwaarde) van de bestandsstream.|
|NativeSHA256||Native_SHA_256|SHA256-hash (256-bits hashwaarde) van de bestandsstream.|
|ND/ET-sorteer: Bijlagen uitsluiten|NdEtSortExclAttach|ND_ET_sort_excl_attach|Samenvoeging van de ET-set (E-mailthread) en ND-set (Near-Duplicate). Dit veld wordt gebruikt voor efficiënt sorteren tijdens de controle. Een **D** is voorafgevoegd aan ND-sets en een **E** is voorafgevoegd aan ET-sets.|
|ND/ET-sorteer: inclusief bijlagen|NdEtSortInclAttach|ND_ET_sort_incl_attach|Samenvoeging van een ET-set (E-mailthread) en ND-set (Near-Duplicate). Dit veld wordt gebruikt voor efficiënt sorteren tijdens de controle. Een **D** is voorafgevoegd aan ND-sets en een **E** is voorafgevoegd aan ET-sets. Elk e-mailitem in een ET-set wordt gevolgd door de juiste bijlagen.|
|O365-auteurs||O365_authors|Auteur van SharePoint.|
|O365 gemaakt door||O365_created_by|Gemaakt door SharePoint.|
|O365-datum gemaakt||O365_date_created|Datum gemaakt van SharePoint.|
|O365-datum gewijzigd||O365_date_modified|Laatst gewijzigde datum van SharePoint.|
|O365 gewijzigd door||O365_modified_by|Gewijzigd door van SharePoint.|
|Bovenliggende id|ParentId|Parent_ID|Id van het bovenliggende item.|
|ParentNode||Parent_node|Het dichtstbijzijnde voorafgaande e-mailbericht in de e-mailthread.|
|Deelnemersdomeinen|ParticipantDomains|Email_participant_domains|Lijst met alle domeinen van deelnemers aan een bericht.|
|Deelnemers|Deelnemers|Email_participants|Lijst met alle deelnemers van een bericht; bijvoorbeeld Afzender, Aan, CC, BCC.|
|Draaitabel-id|Draaitabel|Pivot_ID|De id van een draaipunt.|
|Potentieel bevoorrecht|PotentieelPrivileged|Potentially_privileged|Waar als het detectiemodel voor advocaten-clientprivilege van mening is dat het document mogelijk is geprivilegieerd|
|Verwerkingsstatus|ProcessingStatus|Error_code|Verwerkingsstatus nadat het item is toegevoegd aan een revisieset.|
|Percentiel lezen|ReadPercentile||Lees percentiel voor het document op basis van Relevantie.|
|Ontvangen|Ontvangen|Email_date_received|De datum en tijd waarop de e-mail is ontvangen in UTC.|
|Aantal geadresseerden||Recipient_count|Het aantal geadresseerden in het bericht.|
|Geadresseerdedomeinen|RecipientDomains|Email_recipient_domains|Lijst met alle domeinen van geadresseerden van een bericht.|
|Geadresseerden|Geadresseerden|Email_recipients|Lijst met alle geadresseerden van een bericht (Aan, CC, BCC).|
|||Redacted_file_path|Het pad van het vervangende bestand in de export.|
|||Redacted_text_path|Het pad van het vervangende tekstbestand in de export. Alleen voor intern Microsoft-gebruik.|
|Relevantielabel Case issue 1||Relevance_tag_case_issue_1|Relevantielabel Case probleem 1 van Relevantie.|
|Relevantiescore|Relevantiescore||Relevantiescore van een document op basis van Relevantie.|
|Relevantietag|Relevantietag||Relevantiescore van een document op basis van Relevantie.|
|Representatieve id|RepresentativeId||Numerieke id van elke set exacte duplicaten.|
|||Row_number|Het rijnummer van het item in het laadbestand.|
|Afzender|Afzender|Email_sender|Het veld Afzender (Van) voor berichttypen. Notatie is **DisplayName. \<SmtpAddress>**|
|Afzender/auteur|SenderAuthor||Berekend veld dat bestaat uit de afzender of auteur van het item.|
|Afzenderdomein|SenderDomain|Email_sender_domain|Domein van de afzender.|
|Verzonden|Verzonden|Email_date_sent|Verzonden datum van het bericht.|
|Volgorde instellen: Eerst inclusief|SetOrderInclusivesFirst|Set_order_inclusives_first|Sorteerveld - e-mail en bijlagen: contrachronologisch; documenten: draai eerst en vervolgens door aflopende gelijkenisscore.|
|SimilarityPercent||Similarity_percent|Geeft aan hoe vergelijkbaar een document is met de draaipunt van de bijna dubbele set.|
|Standaardbestandsgrootte|Grootte|Native_size|Het aantal bytes van het oorspronkelijke item.|
|Onderwerp|Onderwerp|Email_subject|Onderwerp van het bericht.|
|Onderwerp/titel|SubjectTitle||Berekend veld dat bestaat uit het onderwerp of de titel van het item.|
|Tags|Tags|Tags|Tags die zijn toegepast in een revisieset.|
|Lijst met thema's|ThemesList|Themes_list|Lijst met thema's zoals berekend voor analyse.|
|Title|Title|Doc_title|Titel van de metagegevens van het document.|
|Naar|Naar|Email_to|Veld voor berichttypen. Notatie is **DisplayName \<SmtpAddress>**|
|Uniek in e-mailset|UniqueInEmailSet||**Onwaar** als er een duplicaat van de bijlage in de e-mailset staat.|
|Versiegroep-id||Version_Group_Id|Groepeert de verschillende versies van hetzelfde document.|
|Is gesaneerd|WasRemediated|Was_Remediated|**Waar** als het item is gesaneerd, anders **Onwaar.**|
|Aantal woorden|WordCount|Word_count|Het aantal woorden in het item.|
|||||

> [!NOTE]
> Zie Trefwoordenquery's en zoekvoorwaarden voor Inhoud zoeken voor meer informatie over doorzoekbare eigenschappen bij het zoeken naar Office 365 [inhoudslocaties](keyword-queries-and-search-conditions.md)wanneer u gegevens verzamelt voor een Advanced eDiscovery-geval.
