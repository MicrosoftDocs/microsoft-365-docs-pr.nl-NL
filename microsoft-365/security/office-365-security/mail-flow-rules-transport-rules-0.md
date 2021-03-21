---
title: E-mailstroomregels in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 9c2cf227-eff7-48ef-87fb-487186e47363
description: U kunt regels voor e-mailstroom (transportregels) gebruiken om berichten te identificeren en actie te ondernemen die door uw organisatie stromen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7f3edb8b764df0699a9837fc1ce261837c636255
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926842"
---
# <a name="mail-flow-rules-transport-rules-in-standalone-eop"></a>E-mailstroomregels (transportregels) in standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken kunt u regels voor e-mailstroom (ook wel transportregels genoemd) gebruiken om berichten te identificeren en actie te ondernemen die door uw organisatie stromen.

In dit onderwerp worden de onderdelen van de regels voor e-mailstroom uitgelegd en hoe ze werken.

Zie Regels voor e-mailstroom beheren in Exchange Online voor stappen voor het maken, kopiëren en beheren van regels voor [e-mailstroom.](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) Voor elke regel kunt u de regel afdwingen, testen of testen en de afzender op de hoogte stellen. Zie [E-mailstroomregels](/exchange/security-and-compliance/mail-flow-rules/test-mail-flow-rules) en [Beleidstips testen in Exchange Online](/exchange/security-and-compliance/data-loss-prevention/policy-tips)voor meer informatie over de testopties.

Zie E-mailbeveiligingsrapporten gebruiken om gegevens over malware, spam en regeldetectie weer te geven voor overzichts- en detailrapporten over berichten die overeenkomen met [e-mailstroomregels.](/exchange/monitoring/use-mail-protection-reports)

Zie de volgende onderwerpen als u specifiek berichtenbeleid wilt implementeren met behulp van regels voor e-mailstroom:

- [Regels voor e-mailstroom gebruiken om berichtbijlagen in Exchange Online te controleren](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

- [Versleuteling instellen in Office 365 Enterprise](../../compliance/set-up-encryption.md)

- [Bericht disclaimers, handtekeningen, voetteksten of kopteksten voor de hele organisatie in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)

- [Regels voor e-mailstroom gebruiken om het betrouwbaarheidsniveau voor spam (SCL) in berichten in te stellen](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- [Lijsten met blok afzenders maken in EOP](create-block-sender-lists-in-office-365.md)

- [Malwarebedreigingen verminderen door bestandsbijlagen te blokkeren in Exchange Online Protection](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)

- [Regels definiëren voor het versleutelen of ontsleutelen van e-mailberichten in Office 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md)

In de volgende video wordt een demonstratie gegeven van het instellen van e-mailstroomregels in zelfstandige EOP.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]

## <a name="mail-flow-rule-components"></a>Onderdelen van e-mailstroomregel

Een e-mailstroomregel bestaat uit voorwaarden, uitzonderingen, acties en eigenschappen:

- **Voorwaarden:** Identificeer de berichten op wie u de acties wilt toepassen. In sommige voorwaarden worden berichtkopvelden onderzocht (bijvoorbeeld de velden Aan, Van of CC). Andere voorwaarden onderzoeken berichteigenschappen (bijvoorbeeld het berichtonderwerp, de tekst, bijlagen, de berichtgrootte of de berichtclassificatie). Voor de meeste voorwaarden moet u een vergelijkingsoperator opgeven (bijvoorbeeld gelijk aan, is niet gelijk aan of bevat) en een waarde die moet overeenkomen. Als er geen voorwaarden of uitzonderingen zijn, wordt de regel toegepast op alle berichten.

Zie Voorwaarden en uitzonderingen voor e-mailstroomregelen [(predicaten) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)voor meer informatie over de voorwaarden van de e-mailstroomregel in zelfstandige EOP.

- **Uitzonderingen:** Identificeer desgewenst de berichten op wie de acties niet van toepassing moeten zijn. Dezelfde berichtaanduidingen die beschikbaar zijn onder voorwaarden, zijn ook beschikbaar in uitzonderingen. Uitzonderingen overschrijven de voorwaarden en voorkomen dat de regelacties worden toegepast op een bericht, zelfs als het bericht overeenkomt met alle geconfigureerde voorwaarden.

- **Acties:** Geef op wat u moet doen met berichten die voldoen aan de voorwaarden in de regel en die niet overeenkomen met een van de uitzonderingen. Er zijn veel acties beschikbaar, zoals het weigeren, verwijderen of omleiden van berichten, het toevoegen van extra geadresseerden, het toevoegen van voorvoegsels in het berichtonderwerp of het invoegen van vrijwaringen in de berichtbesturen.

Zie [E-mailstroomregelacties in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)voor meer informatie over acties voor e-mailstroomregelacties die beschikbaar zijn in zelfstandige EOP.

- **Eigenschappen:** Geef andere regels op die geen voorwaarden, uitzonderingen of acties zijn. Bijvoorbeeld wanneer de regel moet worden toegepast, of u de regel wilt afdwingen of testen, en de periode waarin de regel actief is.

  Zie de sectie Eigenschappen van de [e-mailstroomregel](#mail-flow-rule-properties) in dit artikel voor meer informatie.

### <a name="multiple-conditions-exceptions-and-actions"></a>Meerdere voorwaarden, uitzonderingen en acties

In de volgende tabel ziet u hoe meerdere voorwaarden, voorwaardewaarden, uitzonderingen en acties in een regel worden verwerkt.

****

|Onderdeel|Logica|Opmerkingen|
|---|---|---|
|Meerdere voorwaarden|EN|Een bericht moet overeenkomen met alle voorwaarden in de regel. Als u een voorwaarde of een andere voorwaarde wilt overeenkomen, gebruikt u afzonderlijke regels voor elke voorwaarde. Als u bijvoorbeeld dezelfde vrijwaring wilt toevoegen aan berichten met bijlagen en berichten die specifieke tekst bevatten, maakt u één regel voor elke voorwaarde. In het EAC kunt u eenvoudig een regel kopiëren.|
|Eén voorwaarde met meerdere waarden|OF|Met sommige voorwaarden kunt u meer dan één waarde opgeven. Het bericht moet overeenkomen met een (niet alle) van de opgegeven waarden. Als een e-mailbericht bijvoorbeeld het onderwerp Aandelenkoersgegevens bevat en het onderwerp een van deze woorden bevat, is geconfigureerd voor de woorden Contoso **of** aandelen, is aan de voorwaarde voldaan omdat het onderwerp ten minste één van de opgegeven waarden bevat.|
|Meerdere uitzonderingen|OF|Als een bericht overeenkomt met een van de uitzonderingen, worden de acties niet toegepast op het bericht. Het bericht hoeft niet op alle uitzonderingen te passen.|
|Meerdere acties|EN|Berichten die overeenkomen met de voorwaarden van een regel, krijgen alle acties die in de regel zijn opgegeven. Als bijvoorbeeld de acties Het onderwerp **van** het bericht voorbereiden met en Geadresseerden toevoegen aan het **vak BCC** zijn geselecteerd, worden beide acties toegepast op het bericht. <p> Houd er rekening mee dat  sommige acties, zoals het bericht verwijderen zonder iemand op de hoogte te stellen, voorkomen dat volgende regels worden toegepast op een bericht. Andere acties, zoals **Het bericht doorsturen,** staan geen extra acties toe. <p> U kunt ook een actie voor een regel instellen, zodat wanneer deze regel wordt toegepast, de volgende regels niet worden toegepast op het bericht.|
|

### <a name="mail-flow-rule-properties"></a>Eigenschappen van e-mailstroomregel

In de volgende tabel worden de regeleigenschappen beschreven die beschikbaar zijn in regels voor e-mailstroom.

****

|Eigenschapsnaam in het EAC|Parameternaam in PowerShell|Beschrijving|
|---|---|---|
|**Prioriteit**|_Prioriteit_|Geeft de volgorde aan dat de regels worden toegepast op berichten. De standaardprioriteit is gebaseerd op het moment waarop de regel wordt gemaakt (oudere regels hebben een hogere prioriteit dan nieuwere regels en regels met een hogere prioriteit worden verwerkt vóór regels met een lagere prioriteit). <p> U wijzigt de regelprioriteit in het OC door de regel omhoog of omlaag te verplaatsen in de lijst met regels. In PowerShell stelt u het prioriteitsnummer in (0 is de hoogste prioriteit). <p> Als u bijvoorbeeld één regel hebt om berichten met een creditcardnummer te weigeren en een andere regel waarvoor goedkeuring is vereist, wilt u dat de afwijzingsregel eerst wordt toegepast en stopt u met het toepassen van andere regels.  |
|**Modus**|_Modus_|U kunt opgeven of u wilt dat de regel berichten direct gaat verwerken of dat u regels wilt testen zonder dat dit van invloed is op de bezorging van het bericht (met of zonder preventie van gegevensverlies of DLP-beleidstips). <p> Beleidstips bevatten een korte notitie in Outlook of de webversie van Outlook met informatie over mogelijke beleidsovertredingen voor de persoon die het bericht maakt. Zie **Beleidstips voor meer informatie.** <p> Zie Een **e-mailstroomregel testen** voor meer informatie over de modi.|
|**Deze regel op de volgende datum activeren** <p> **Deze regel deactiveren op de volgende datum**|_Activeringsdatum_ <p> _Vervaldatum_|Hiermee geeft u het datumbereik op wanneer de regel actief is.|
|**Selectievakje** ingeschakeld of niet geselecteerd|Nieuwe regels: _ingeschakelde_ parameter op de **cmdlet New-TransportRule.** <p> Bestaande regels: Gebruik de **cmdlets Enable-TransportRule** **of Disable-TransportRule.** <p> De waarde wordt weergegeven in de **eigenschap State** van de regel.|U kunt een uitgeschakelde regel maken en deze inschakelen wanneer u klaar bent om deze te testen. U kunt ook een regel uitschakelen zonder deze te verwijderen om de instellingen te behouden.|
|**Het bericht uitstellen als de verwerking van regels niet is voltooid**|_RuleErrorAction_|U kunt opgeven hoe het bericht moet worden verwerkt als de regelverwerking niet kan worden voltooid. Standaard wordt de regel genegeerd, maar u kunt ervoor kiezen om het bericht opnieuw in te sturen voor verwerking.|
|**Adres van afzender in bericht overeenkomen**|_SenderAddressLocation_|Als voor de regel voorwaarden of uitzonderingen worden gebruikt die het e-mailadres van de afzender onderzoeken, kunt u zoeken naar de waarde in de berichtkop, de envelop van het bericht of beide.|
|**Meer regels niet meer verwerken**|_SenderAddressLocation_|Dit is een actie voor de regel, maar het ziet eruit als een eigenschap in het EAC. U kunt ervoor kiezen om geen extra regels meer toe te passen op een bericht nadat een bericht door een regel is verwerkt.|
|**Opmerkingen**|_Opmerkingen_|U kunt beschrijvende opmerkingen over de regel invoeren.|
|

## <a name="how-mail-flow-rules-are-applied-to-messages"></a>Regels voor e-mailstroom toepassen op berichten

Alle berichten die door uw organisatie stromen, worden geëvalueerd op basis van de ingeschakelde regels voor e-mailstroom in uw organisatie. Regels worden verwerkt in de volgorde die wordt weergegeven op de pagina Regels voor **e-mailstroom** in EAC of op basis van de bijbehorende \>  _parameterwaarde Prioriteit_ in PowerShell.

Elke regel biedt ook de optie om het verwerken van meer regels te stoppen wanneer de regel is afgestemd. Deze instelling is belangrijk voor berichten die overeenkomen met de voorwaarden in meerdere regels voor e-mailstroom (welke regel wilt u toepassen op het bericht? Alles? Slechts één?).

### <a name="differences-in-processing-based-on-message-type"></a>Verschillen in verwerking op basis van berichttype

Er zijn verschillende typen berichten die door een organisatie lopen. In de volgende tabel ziet u welke berichtentypen kunnen worden verwerkt met regels voor e-mailstroom.

****

|Type bericht|Kan een regel worden toegepast?|
|---|---|
|**Gewone berichten:** berichten met één RTF-indeling (Rich Text Format), HTML of tekst zonder opmaak of een veelgemaakte of alternatieve set berichtteksten.|Ja|
|**Office 365-berichtversleuteling:** berichten die zijn versleuteld door Office 365-berichtversleuteling in Office 365. Zie Versleuteling [in Office 365](../../compliance/encryption.md)voor meer informatie.|Regels kunnen altijd toegang krijgen tot envelopkoppen en berichten verwerken op basis van voorwaarden die deze kopteksten controleren. <p> Als een regel de inhoud van een versleuteld bericht wilt controleren of wijzigen, moet u controleren of transportdecryptie is ingeschakeld (Verplicht of Optioneel; de standaardwaarde is Optioneel). Zie Regels definiëren voor het versleutelen of [ontsleutelen van e-mailberichten in Office 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md)voor meer informatie.|
|**S/MIME-versleutelde berichten**|Regels kunnen alleen toegang krijgen tot envelopkoppen en berichten verwerken op basis van voorwaarden die deze kopteksten controleren. <p> Regels met voorwaarden waarvoor de inhoud van het bericht moet worden gecontroleerd of acties die de inhoud van het bericht wijzigen, kunnen niet worden verwerkt.|
|**RMS-beveiligde** berichten: berichten met een AD RMS-beleid (Active Directory Rights Management Services) of RMS-beleid (Azure Rights Management).|Regels kunnen altijd toegang krijgen tot envelopkoppen en berichten verwerken op basis van voorwaarden die deze kopteksten controleren. <p> Als een regel de inhoud van een rms-beveiligd bericht wilt controleren of wijzigen, moet u controleren of transportdecryptie is ingeschakeld (Verplicht of Optioneel; de standaardwaarde is Optioneel).|
|**Duidelijk ondertekende berichten:** berichten die zijn ondertekend, maar niet zijn versleuteld.|Ja|
|**UM-berichten:** berichten die worden gemaakt of verwerkt door de Unified Messaging-service, zoals voicemail, fax, meldingen van gemiste oproep en berichten die zijn gemaakt of doorgestuurd met Microsoft Outlook Voice Access.|Ja|
|**Anonieme berichten:** berichten die zijn verzonden door anonieme afzenders.|Ja|
|**Rapporten lezen:** rapporten die worden gegenereerd als antwoord op leesbevestigingsaanvragen van afzenders. Leesrapporten hebben een berichtklasse van of `IPM.Note*.MdnRead` `IPM.Note*.MdnNotRead` .|Ja|
|

## <a name="what-else-should-i-know"></a>Wat moet ik nog meer weten?

- De **eigenschapswaarde** **Versie of RuleVersion** voor een regel is niet belangrijk in Exchange Online Protection.

- Nadat u een regel voor de e-mailstroom hebt aan- of gewijzigd, kan het tot 30 minuten duren voordat de nieuwe of bijgewerkte regel is toegepast op berichten.

## <a name="for-more-information"></a>Voor meer informatie

[Regels voor e-mailstroom gebruiken om berichtbijlagen in Exchange Online te controleren](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

[E-mailversleuteling in Office 365](../../compliance/email-encryption.md)

[Regellimieten voor logboeken, transport en Postvak IN](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#journal-transport-and-inbox-rule-limits)