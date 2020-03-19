---
title: Regels voor de stroom van e-mail (transportregels) in Exchange Online Protection
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9c2cf227-eff7-48ef-87fb-487186e47363
description: U regels voor e-mailstroom (transportregels) gebruiken om berichten te identificeren en actie te ondernemen die door uw Office 365-organisatie stromen.
ms.openlocfilehash: 42b55893a9884b547a0d2d36e901169153d290d7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42808448"
---
# <a name="mail-flow-rules-transport-rules-in-exchange-online-protection"></a>Regels voor de stroom van e-mail (transportregels) in Exchange Online Protection

U regels voor e-mailstromen (ook wel transportregels genoemd) gebruiken om berichten te identificeren en actie te ondernemen die door uw Office 365-organisatie stromen. Regels voor de mailstroom zijn vergelijkbaar met de Inbox-regels die beschikbaar zijn in De outlook en de webversie van Outlook. Het belangrijkste verschil is dat regels voor e-mailstromen actie ondernemen op berichten terwijl ze onderweg zijn en niet nadat het bericht in het postvak is bezorgd. Regels voor e-mailstromen bevatten een rijkere set voorwaarden, uitzonderingen en acties, waardoor u de flexibiliteit hebt om vele soorten berichtenbeleid te implementeren.

In dit artikel worden de onderdelen van de regels voor de e-mailstroom uitgelegd en hoe ze werken.

Zie Regels voor [e-mailstromen beheren in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)voor stappen om regels voor e-mailstromen te maken, te kopiëren en te beheren. Voor elke regel hebt u de mogelijkheid om deze af te dwingen, te testen of te testen en de afzender op de hoogte te stellen. Zie Regels voor [de stroomstroom](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/test-mail-flow-rules) testen [in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/policy-tips)voor meer informatie over de testopties.

Zie [E-mailbeveiligingsrapporten gebruiken in Office 365 voor](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports)overzichts- en detailrapporten over berichten die overeenkwamen met de regels voor e-mailstromen.

Zie de volgende onderwerpen om specifiek berichtenbeleid te implementeren met behulp van regels voor e-mailstromen:

- [Regels voor e-mailstroom gebruiken om berichtbijlagen in Exchange Online te inspecteren](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

- [Versleuteling instellen in Office 365 Enterprise](../../compliance/set-up-encryption.md)

- [Organisatiebrede berichtdisclaimers, handtekeningen, voetteksten of kopteksten in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)

- [Regels voor e-mailstroom gebruiken om het spamvertrouwensniveau (SCL) in berichten in te stellen](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- [Afzenderlijsten voor blokkeren maken in Office 365](create-block-sender-lists-in-office-365.md)

- [Malwarebedreigingen verminderen door het blokkeren van bestandsbijlagen in Exchange Online Protection](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)

- [Regels definiëren voor het versleutelen of decoderen van e-mailberichten in Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)

De volgende video geeft een demonstratie van het instellen van regels voor e-mailstromen in Exchange Online Protection.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]

## <a name="mail-flow-rule-components"></a>Onderdelen van de regel voor e-mailstromen

Er wordt een e-mailstroomregel gemaakt van voorwaarden, uitzonderingen, acties en eigenschappen:

- **Voorwaarden:** Identificeer de berichten waarop u de acties wilt toepassen. In sommige voorwaarden worden kopvelden voor berichten (bijvoorbeeld de velden Aan, Uit of of Cc) onderzocht. Andere voorwaarden onderzoeken berichteigenschappen (bijvoorbeeld het berichtonderwerp, de hoofdtekst, bijlagen, berichtgrootte of berichtclassificatie). De meeste voorwaarden vereisen dat u een vergelijkingsoperator opgeeft (bijvoorbeeld gelijk is aan, niet gelijk is aan of bevat) en een waarde die moet overeenkomen. Als er geen voorwaarden of uitzonderingen zijn, wordt de regel toegepast op alle berichten.

Zie Voorwaarden en uitzonderingen voor de regel van de [mailstroomregel in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)Protection in Exchange Online .

- **Uitzonderingen**: Identificeer optioneel de berichten waarop de acties niet van toepassing mogen zijn. Dezelfde bericht-id's die beschikbaar zijn in voorwaarden zijn ook beschikbaar in uitzonderingen. Uitzonderingen overschrijven voorwaarden en voorkomen dat de regelacties worden toegepast op een bericht, zelfs als het bericht overeenkomt met alle geconfigureerde voorwaarden.

- **Acties:** Geef op wat u moet doen met berichten die overeenkomen met de voorwaarden in de regel en die niet overeenkomen met een van de uitzonderingen. Er zijn veel acties beschikbaar, zoals het weigeren, verwijderen of omleiden van berichten, het toevoegen van extra ontvangers, het toevoegen van voorvoegsels in het berichtonderwerp of het invoegen van disclaimers in de berichttekst.

Zie Acties van de regelvan de [mailstroomregel in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)voor meer informatie over acties van de e-mailstroomregel die beschikbaar zijn in Exchange Online.

- **Eigenschappen:** geef andere regelsinstellingen op die geen voorwaarden, uitzonderingen of acties zijn. Bijvoorbeeld wanneer de regel moet worden toegepast, of de regel moet worden afgedwongen of getest, en de periode waarin de regel actief is.

  Zie de sectie Eigenschappen van de [regel mailstroomin](#mail-flow-rule-properties) dit onderwerp voor meer informatie.

### <a name="multiple-conditions-exceptions-and-actions"></a>Meerdere voorwaarden, uitzonderingen en acties

In de volgende tabel ziet u hoe meerdere voorwaarden, voorwaardenwaarden, uitzonderingen en acties in een regel worden verwerkt.

|**Component**|**Logica**|**Opmerkingen**|
|:-----|:-----|:-----|
|Meerdere voorwaarden|En|Een bericht moet overeenkomen met alle voorwaarden in de regel. Als u een of andere voorwaarde moet matchen, gebruikt u afzonderlijke regels voor elke voorwaarde. Als u bijvoorbeeld dezelfde disclaimer wilt toevoegen aan berichten met bijlagen en berichten die specifieke tekst bevatten, maakt u één regel voor elke voorwaarde. In de EAC u eenvoudig een regel kopiëren.|
|Eén voorwaarde met meerdere waarden|OF|Met sommige voorwaarden u meer dan één waarde opgeven. Het bericht moet overeenkomen met een (niet alle) van de opgegeven waarden. Als een e-mailbericht bijvoorbeeld het onderwerp Voorraadprijsinformatie heeft en het **onderwerp een van deze woorden** bevat, is deze is geconfigureerd om de woorden Contoso of voorraad te evenaren, wordt aan de voorwaarde voldaan omdat het onderwerp ten minste één van de opgegeven waarden bevat.|
|Meerdere uitzonderingen|OF|Als een bericht overeenkomt met een van de uitzonderingen, worden de acties niet toegepast op het bericht. Het bericht hoeft niet overeen te komen met alle uitzonderingen.|
|Meerdere acties|En|Berichten die overeenkomen met de voorwaarden van een regel, krijgen alle acties die in de regel zijn opgegeven. Als de acties bijvoorbeeld **het onderwerp van het bericht** voorbereiden met en ontvangers toevoegen aan het vak **BCC** zijn geselecteerd, worden beide acties op het bericht toegepast. <br/><br/> Houd er rekening mee dat sommige acties, zoals het bericht verwijderen zonder iemand op de hoogte te **stellen,** voorkomen dat latere regels op een bericht worden toegepast. Andere acties zoals **Het bericht doorsturen** staan geen extra acties toe. <br/><br/> U ook een actie instellen op een regel, zodat wanneer die regel wordt toegepast, latere regels niet worden toegepast op het bericht.|

### <a name="mail-flow-rule-properties"></a>Eigenschappen van e-mailstroomregel

In de volgende tabel worden de regeleigenschappen beschreven die beschikbaar zijn in de regels voor e-mailstroom.

|**Naam van de eigenschap in de EAC**|**Parameternaam in PowerShell**|**Beschrijving**|
|:-----|:-----|:-----|
|**Priority**|_Priority_|Geeft de volgorde aan dat de regels worden toegepast op berichten. De standaardprioriteit is gebaseerd op het moment waarop de regel wordt gemaakt (oudere regels hebben een hogere prioriteit dan nieuwere regels en regels met een hogere prioriteit worden verwerkt voordat regels met een lagere prioriteit worden gewijzigd). <br/><br/> U wijzigt de regelprioriteit in de EAC door de regel omhoog of omlaag te verplaatsen in de lijst met regels. In powershell stelt u het prioriteitsnummer in (0 is de hoogste prioriteit). <br/><br/> Als u bijvoorbeeld één regel hebt om berichten met een creditcardnummer af te wijzen en een andere regel waarvoor goedkeuring nodig is, wilt u dat de afwijzingsregel eerst plaatsvindt en stopt met het toepassen van andere regels.  |
|**Modus**|_Modus_|U opgeven of u wilt dat de regel onmiddellijk begint met het verwerken van berichten, of dat u regels wilt testen zonder dat dit gevolgen heeft voor de levering van het bericht (met of zonder gegevensverliespreventie of DLP-beleidstips). <br/><br/> Beleidstips bieden een korte notitie in Outlook of outlook op internet met informatie over mogelijke beleidsschendingen aan de persoon die het bericht maakt. Zie **Beleidstips**voor meer informatie . <br/><br/> Zie Een regel voor **de e-mailstroom testen**voor meer informatie over de modi.|
|**Deze regel activeren op de volgende datum** <br/><br/> **Deze regel deactiveren op de volgende datum**|_Activeringsdatum_ <br/> _Vervaldatum_|Hiermee geeft u het datumbereik op wanneer de regel actief is.|
|**Selectievakje** ingeschakeld of niet geselecteerd|Nieuwe regels: _Parameter Ingeschakeld_ op de **cmdlet New-TransportRule.** <br/><br/> Bestaande regels: Gebruik de **enable-transportrule** of **Disable-TransportRule** cmdlets. <br/><br/> De waarde wordt weergegeven in het eigenschap **State** van de regel.|U een uitgeschakelde regel maken en deze inschakelen wanneer u deze wilt testen. U ook een regel uitschakelen zonder deze te verwijderen om de instellingen te behouden.|
|**Het bericht uitstellen als de regelverwerking niet is voltooid**|_Regelfoutactie_|U opgeven hoe het bericht moet worden verwerkt als de regelverwerking niet kan worden voltooid. Standaard wordt de regel genegeerd, maar u ervoor kiezen om het bericht opnieuw in te dienen voor verwerking.|
|**Afzenderadres overeenkomen in bericht**|_Locatie van afzenderadres_|Als de regel voorwaarden of uitzonderingen gebruikt die het e-mailadres van de afzender onderzoeken, u zoeken naar de waarde in de berichtkop, de berichtenvelop of beide.|
|**Stoppen met het verwerken van meer regels**|_Locatie van afzenderadres_|Dit is een actie voor de regel, maar het ziet eruit als een eigenschap in de EAC. U ervoor kiezen om te stoppen met het toepassen van aanvullende regels op een bericht nadat een regel een bericht heeft verwerkt.|
|**Opmerkingen**|_Opmerkingen_|U beschrijvende opmerkingen over de regel invoeren.|

## <a name="how-mail-flow-rules-are-applied-to-messages"></a>Hoe regels voor e-mailstromen worden toegepast op berichten

Alle berichten die door uw organisatie stromen, worden geëvalueerd aan de hand van de ingeschakelde regels voor e-mailstromen in uw organisatie. Regels worden verwerkt in de volgorde die wordt vermeld op de pagina **Mailflow** \> **Rules** in EAC of op basis van de overeenkomstige _parameterwaarde Prioriteit_ in PowerShell.

Elke regel biedt ook de mogelijkheid om meer regels te stoppen met verwerken wanneer de regel wordt gekoppeld. Deze instelling is belangrijk voor berichten die overeenkomen met de voorwaarden in meerdere regels voor e-mailstroom (welke regel wilt u toepassen op het bericht? Alle? Slechts een?).

### <a name="differences-in-processing-based-on-message-type"></a>Verschillen in verwerking op basis van berichttype

Er zijn verschillende soorten berichten die door een organisatie gaan. In de volgende tabel ziet u welke typen berichten kunnen worden verwerkt op basis van regels voor e-mailstroom.

****

|**Type bericht**|**Kan een regel worden toegepast?**|
|:-----|:-----|
|**Gewone berichten:** Berichten die één uitgebreide tekstindeling (RTF), HTML of platte tekstberichttekstof een meerdelige of alternatieve set berichtinstanties bevatten.|Ja|
|**Office 365-berichtversleuteling**: berichten versleuteld met Office 365-berichtenversleuteling in Office 365. Zie [Versleuteling in Office 365](https://docs.microsoft.com/microsoft-365/compliance/encryption)voor meer informatie.|Regels hebben altijd toegang tot envelopkoppen en verwerken berichten op basis van voorwaarden die deze kopteksten inspecteren. <br/><br/> Als u de inhoud van een versleuteld bericht wilt inspecteren of wijzigen, moet u controleren of de decryptie van het vervoer is ingeschakeld (Verplicht of optioneel; de standaardinstelling is optioneel). Zie Regels definiëren voor het [versleutelen of decoderen van e-mailberichten in Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)voor meer informatie.|
|**S/MIME versleutelde berichten**|Regels hebben alleen toegang tot envelopkoppen en verwerken berichten op basis van voorwaarden die deze kopteksten inspecteren. <br/><br/> Regels met voorwaarden die controle van de inhoud van het bericht vereisen of acties die de inhoud van het bericht wijzigen, kunnen niet worden verwerkt.|
|**MET RMS beveiligde berichten**: Berichten waarop een AD RMS-beleid (Active Directory Rights Management Services) of Azure Rights Management (RMS) is toegepast.|Regels hebben altijd toegang tot envelopkoppen en verwerken berichten op basis van voorwaarden die deze kopteksten inspecteren. <br/><br/> Als u de inhoud van een met RMS beveiligd bericht wilt inspecteren of wijzigen, moet u controleren of de decryptie van het vervoer is ingeschakeld (Verplicht of optioneel; de standaardinstelling is optioneel).|
|**Duidelijke berichten**: berichten die zijn ondertekend, maar niet versleuteld.|Ja|
|**UM-berichten:** berichten die worden gemaakt of verwerkt door de Unified Messaging-service, zoals voicemail, fax, meldingen van gemiste oproepen en berichten die zijn gemaakt of doorgestuurd met Behulp van Microsoft Outlook Voice Access.|Ja|
|**Anonieme berichten**: Berichten verzonden door anonieme afzenders.|Ja|
|**Lees rapporten**: Rapporten die worden gegenereerd als reactie op ontvangstaanvragen van afzenders. Leesrapporten hebben een `IPM.Note*.MdnRead` berichtklasse van of `IPM.Note*.MdnNotRead`.|Ja|

## <a name="what-else-should-i-know"></a>Wat moet ik nog meer weten?

- De **eigenschapswaarde Versie** of **RuleVersion** voor een regel is niet belangrijk in Exchange Online Protection.

- Nadat u een e-mailstroomregel hebt gemaakt of gewijzigd, kan het tot 30 minuten duren voordat de nieuwe of bijgewerkte regel op berichten wordt toegepast.

## <a name="for-more-information"></a>Voor meer informatie

[Regels voor e-mailstroom gebruiken om berichtbijlagen in Exchange Online te inspecteren](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

[E-mailversleuteling in Office 365](https://docs.microsoft.com/office365/securitycompliance/email-encryption)

[Regelslimieten voor dagboek, vervoer en inbox](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#journal-transport-and-inbox-rule-limits)
