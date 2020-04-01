---
title: Regels voor e-mailstroom (transportregels) in Exchange Online Protection
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
description: U regels voor e-mailstroom (transportregels) gebruiken om berichten die door uw Office 365-organisatie stromen te identificeren en actie te ondernemen.
ms.openlocfilehash: 4332399ce7b3724a7bd23c761eec4328afe5e2a9
ms.sourcegitcommit: a7b2cd892cb65a61ee246268e1af2f8b9e526f6b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2020
ms.locfileid: "43081422"
---
# <a name="mail-flow-rules-transport-rules-in-exchange-online-protection"></a>Regels voor e-mailstroom (transportregels) in Exchange Online Protection

U regels voor e-mailstromen (ook wel transportregels genoemd) gebruiken om berichten te identificeren en actie te ondernemen die door uw Office 365-organisatie stromen. E-mailstroomregels zijn vergelijkbaar met de Regels voor Postvak IN die beschikbaar zijn in de webversie van Outlook en Outlook. Het belangrijkste verschil is dat de regels voor e-mailstroom actie ondernemen op berichten tijdens het transport en niet nadat het bericht in het postvak is bezorgd. Regels voor e-mailstromen bevatten een uitgebreidere set voorwaarden, uitzonderingen en acties, die u de flexibiliteit bieden om veel soorten berichtenbeleid te implementeren.

In dit artikel worden de onderdelen van de regels voor e-mailstromen en hoe ze werken, uitgelegd.

Zie [Regels voor e-mailstroom beheren in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)voor stappen voor het maken, kopiëren en beheren van regels voor e-mailstromen. Voor elke regel hebt u de mogelijkheid om deze af te dwingen, te testen of te testen en de afzender hiervan op de hoogte te stellen. Zie [Regels voor e-mailstroom](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/test-mail-flow-rules) en [beleidstips testen in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/policy-tips)voor meer informatie over de testopties.

Zie [Rapporten over e-mailbeveiliging gebruiken in Office 365 om gegevens over malware, spam en regeldetecties weer te geven voor](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports)beknopte en gedetailleerde rapporten over berichten die overeenkomen met de regels voor e-mailstromen.

Zie de volgende onderwerpen als u specifiek berichtenbeleid wilt implementeren met behulp van regels voor e-mailstromen:

- [E-mailstroomregels gebruiken om berichtbijlagen in Exchange Online te inspecteren](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

- [Versleuteling instellen in Office 365 Enterprise](../../compliance/set-up-encryption.md)

- [Disclaimers van berichten in de hele organisatie, handtekeningen, voetteksten of kopteksten in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)

- [Regels voor e-mailstroom gebruiken om het spamvertrouwensniveau (SCL) in te stellen in berichten](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- [Lijsten met blokafzenders maken in Office 365](create-block-sender-lists-in-office-365.md)

- [Malwarebedreigingen verminderen door het blokkeren van bestandsbijlagen in Exchange Online Protection](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)

- [Regels definiëren om e-mailberichten in Office 365 te versleutelen of te decoderen](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)

De volgende video geeft een demonstratie van het instellen van regels voor e-mailstroom in Exchange Online Protection.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]

## <a name="mail-flow-rule-components"></a>Onderdelen van de regel van de e-mailstroom

Er wordt een regel voor e-mailstroom gemaakt van voorwaarden, uitzonderingen, acties en eigenschappen:

- **Voorwaarden:** Identificeer de berichten waarop u de acties wilt toepassen. Sommige voorwaarden onderzoeken de koptekstvelden van berichten (bijvoorbeeld de velden Aan, Van of Cc). Andere voorwaarden onderzoeken berichteigenschappen (bijvoorbeeld het berichtonderwerp, de hoofdtekst, bijlagen, de grootte van het bericht of de berichtclassificatie). De meeste voorwaarden vereisen dat u een vergelijkingsoperator opgeeft (bijvoorbeeld gelijk is aan, niet gelijk is of bevat) en een waarde die overeenkomt. Als er geen voorwaarden of uitzonderingen zijn, wordt de regel toegepast op alle berichten.

Zie [Voorwaarden en uitzonderingen (basisregels) voor e-mailstroomregels](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)in Exchange Online Protection.

- **Uitzonderingen**: Identificeer optioneel de berichten waarop de acties niet van toepassing moeten zijn. Dezelfde bericht-id's die beschikbaar zijn in voorwaarden zijn ook beschikbaar in uitzonderingen. Uitzonderingen overschrijven voorwaarden en voorkomen dat de regelacties worden toegepast op een bericht, zelfs als het bericht overeenkomt met alle geconfigureerde voorwaarden.

- **Acties:** Geef op wat u moet doen met berichten die overeenkomen met de voorwaarden in de regel en niet overeenkomen met een van de uitzonderingen. Er zijn veel acties beschikbaar, zoals het weigeren, verwijderen of omleiden van berichten, het toevoegen van extra ontvangers, het toevoegen van voorvoegsels in het berichtonderwerp of het invoegen van disclaimers in de berichttekst.

Zie Acties voor [e-mailstroomregels in Exchange Online-beveiliging voor](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)meer informatie over acties met de regel van de e-mailstroom die beschikbaar zijn in Exchange Online.

- **Eigenschappen:** Geef andere regels op die geen voorwaarden, uitzonderingen of acties zijn. Bijvoorbeeld wanneer de regel moet worden toegepast, of de regel moet worden afgedwongen of getest, en de periode waarin de regel actief is.

  Zie de sectie [Eigenschappen van de regel e-mailstroom](#mail-flow-rule-properties) in dit onderwerp voor meer informatie.

### <a name="multiple-conditions-exceptions-and-actions"></a>Meerdere voorwaarden, uitzonderingen en acties

In de volgende tabel ziet u hoe meerdere voorwaarden, conditiewaarden, uitzonderingen en acties in een regel worden verwerkt.

|**Component**|**Logica**|**Opmerkingen**|
|:-----|:-----|:-----|
|Meerdere voorwaarden|En|Een bericht moet overeenkomen met alle voorwaarden in de regel. Als u een of andere voorwaarde moet overeenkomen, gebruikt u afzonderlijke regels voor elke voorwaarde. Als u bijvoorbeeld dezelfde disclaimer wilt toevoegen aan berichten met bijlagen en berichten die specifieke tekst bevatten, maakt u één regel voor elke voorwaarde. In de EAC u eenvoudig een regel kopiëren.|
|Eén voorwaarde met meerdere waarden|OF|Met sommige voorwaarden u meer dan één waarde opgeven. Het bericht moet overeenkomen met een (niet alle) van de opgegeven waarden. Als een e-mailbericht bijvoorbeeld het onderwerp Voorraadprijsinformatie heeft en het **onderwerp een van deze woorden bevat,** is deze geconfigureerd om overeen te komen met de woorden Contoso of voorraad, wordt aan de voorwaarde voldaan omdat het onderwerp ten minste één van de opgegeven waarden bevat.|
|Meerdere uitzonderingen|OF|Als een bericht overeenkomt met een van de uitzonderingen, worden de acties niet toegepast op het bericht. Het bericht hoeft niet overeen te komen met alle uitzonderingen.|
|Meerdere acties|En|Berichten die overeenkomen met de voorwaarden van een regel, krijgen alle acties die in de regel zijn opgegeven. Als de acties bijvoorbeeld **het onderwerp van het bericht** voorbereiden met en **Geadresseerden toevoegen aan het vak BCC,** worden beide acties op het bericht toegepast. <br/><br/> Houd er rekening mee dat sommige acties, zoals **Het bericht verwijderen zonder iemand op de hoogte te stellen** van actie, voorkomen dat volgende regels worden toegepast op een bericht. Andere acties, zoals **Het bericht doorsturen,** staan geen extra acties toe. <br/><br/> U ook een actie instellen op een regel, zodat wanneer die regel wordt toegepast, latere regels niet worden toegepast op het bericht.|

### <a name="mail-flow-rule-properties"></a>Eigenschappen van e-mailstroomregel

In de volgende tabel worden de regeleigenschappen beschreven die beschikbaar zijn in de regels voor e-mailstromen.

|**Eigendomsnaam in de EAC**|**Parameternaam in PowerShell**|**Beschrijving**|
|:-----|:-----|:-----|
|**Prioriteit**|_Prioriteit_|Geeft de volgorde aan waarin de regels worden toegepast op berichten. De standaardprioriteit is gebaseerd op wanneer de regel wordt gemaakt (oudere regels hebben een hogere prioriteit dan nieuwere regels en regels met een hogere prioriteit worden verwerkt vóór regels met een lagere prioriteit). <br/><br/> U wijzigt de regelprioriteit in de EAC door de regel omhoog of omlaag te verplaatsen in de lijst met regels. In de PowerShell stelt u het prioriteitsnummer in (0 is de hoogste prioriteit). <br/><br/> Als u bijvoorbeeld één regel hebt om berichten met een creditcardnummer af te wijzen en een andere regel die goedkeuring vereist, wilt u dat de afwijsregel eerst plaatsvindt en stopt u met het toepassen van andere regels.  |
|**Modus**|_Modus_|U opgeven of u wilt dat de regel onmiddellijk begint met het verwerken van berichten, of dat u regels wilt testen zonder de weergave van het bericht te beïnvloeden (met of zonder gegevensverliespreventie of DLP-beleidstips). <br/><br/> Beleidstips bevatten een korte notitie in outlook of de webversie van Outlook met informatie over mogelijke beleidsschendingen aan de persoon die het bericht maakt. Zie **Beleidstips**voor meer informatie. <br/><br/> Zie Een regel voor **e-mailstroom testen**voor meer informatie over de modi.|
|**Deze regel activeren op de volgende datum** <br/><br/> **Deze regel op de volgende datum deactiveren**|_Activeringsdatum_ <br/> _Vervaldatum_|Hiermee geeft u het datumbereik op wanneer de regel actief is.|
|**In** selectievakje ingeschakeld of niet geselecteerd|Nieuwe regels: _Ingeschakelde_ parameter op de cmdlet **Nieuw-Transportregel.** <br/><br/> Bestaande regels: Gebruik de cmdlets **Enable-TransportRule** of **Disable-TransportRule.** <br/><br/> De waarde wordt weergegeven in de **eigenschap Staat** van de regel.|U een uitgeschakelde regel maken en deze inschakelen wanneer u klaar bent om deze te testen. U ook een regel uitschakelen zonder deze te verwijderen om de instellingen te behouden.|
|**Het bericht uitstellen als de verwerking van de regel niet is voltooid**|_RegelFoutactie_|U opgeven hoe het bericht moet worden afgehandeld als de regelverwerking niet kan worden voltooid. Standaard wordt de regel genegeerd, maar u ervoor kiezen om het bericht opnieuw in te dienen voor verwerking.|
|**Afzenderadres in bericht overeenkomen**|_SenderAddressLocatie_|Als de regel voorwaarden of uitzonderingen gebruikt die het e-mailadres van de afzender onderzoeken, u zoeken naar de waarde in de berichtkop, de envelop van het bericht of beide.|
|**Meer regels niet meer verwerken**|_SenderAddressLocatie_|Dit is een actie voor de regel, maar het ziet eruit als een eigenschap in de EAC. U ervoor kiezen om geen extra regels meer toe te passen op een bericht nadat een regel een bericht heeft verwerkt.|
|**Opmerkingen**|_Opmerkingen_|U beschrijvende opmerkingen over de regel invoeren.|

## <a name="how-mail-flow-rules-are-applied-to-messages"></a>Hoe regels voor e-mailstromen worden toegepast op berichten

Alle berichten die door uw organisatie stromen, worden geëvalueerd aan de hand van de ingeschakelde regels voor e-mailstromen in uw organisatie. Regels worden verwerkt in de volgorde die wordt vermeld op de pagina **EAC-regels** \> **Rules** of op basis van de overeenkomstige _parameterwaarde prioriteit_ in de PowerShell.

Elke regel biedt ook de mogelijkheid om de verwerking van meer regels te stoppen wanneer de regel wordt geëvenaard. Deze instelling is belangrijk voor berichten die overeenkomen met de voorwaarden in meerdere regels voor e-mailstromen (welke regel wilt u toepassen op het bericht? Alle? Slechts een?).

### <a name="differences-in-processing-based-on-message-type"></a>Verschillen in verwerking op basis van berichttype

Er zijn verschillende soorten berichten die door een organisatie gaan. In de volgende tabel ziet u welke berichtentypen kunnen worden verwerkt door regels voor e-mailstromen.

****

|**Type bericht**|**Kan een regel worden toegepast?**|
|:-----|:-----|
|**Regelmatige berichten:** berichten die één rtf -indeling (rich text) bevatten, HTML of platte teksttekstof een meerdelige of alternatieve set berichtinstanties.|Ja|
|**Office 365-berichtversleuteling:** berichten versleuteld met Office 365-berichtversleuteling in Office 365. Zie [Versleuteling in Office 365](https://docs.microsoft.com/microsoft-365/compliance/encryption)voor meer informatie.|Regels hebben altijd toegang tot envelope headers en verwerken berichten op basis van voorwaarden die deze headers inspecteren. <br/><br/> Als u een regel wilt controleren of wijzigen van de inhoud van een versleuteld bericht, moet u controleren of dedecryptie van het transport is ingeschakeld (Verplicht of optioneel; de standaardinstelling is optioneel). Zie [Regels definiëren voor het versleutelen of decoderen van e-mailberichten in Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)voor meer informatie.|
|**Versleutelde Berichten s/MIME**|Regels hebben alleen toegang tot envelope headers en verwerken berichten op basis van voorwaarden die deze headers inspecteren. <br/><br/> Regels met voorwaarden die inzien van de inhoud van het bericht vereisen, of acties die de inhoud van het bericht wijzigen, kunnen niet worden verwerkt.|
|**RMS-beveiligde berichten:** berichten waarop een AD RMS-beleid (Active Directory Rights Management Services) of Azure Rights Management (RMS) is toegepast.|Regels hebben altijd toegang tot envelope headers en verwerken berichten op basis van voorwaarden die deze headers inspecteren. <br/><br/> Als u een regel wilt controleren of wijzigen van de inhoud van een beveiligd RMS-bericht, moet u controleren of dedecryptie van het transport is ingeschakeld (Verplicht of optioneel; de standaardinstelling is optioneel).|
|**Duidelijke ondertekende berichten:** berichten die zijn ondertekend, maar niet versleuteld.|Ja|
|**UM-berichten**: berichten die zijn gemaakt of verwerkt door de Unified Messaging-service, zoals voicemail, fax, meldingen van gemiste oproepen en berichten die zijn gemaakt of doorgestuurd met Microsoft Outlook Voice Access.|Ja|
|**Anonieme berichten**: Berichten verzonden door anonieme afzenders.|Ja|
|**Rapporten lezen**: Rapporten die worden gegenereerd als reactie op ontvangstverzoeken van afzenders. Leesrapporten hebben een `IPM.Note*.MdnRead` berichtklasse van of `IPM.Note*.MdnNotRead`.|Ja|

## <a name="what-else-should-i-know"></a>Wat moet ik nog meer weten?

- De **eigenschapswaarde Versie** of **Regelversie** voor een regel is niet belangrijk in Exchange Online Protection.

- Nadat u een regel voor e-mailstroom hebt gemaakt of gewijzigd, kan het tot 30 minuten duren voordat de nieuwe of bijgewerkte regel op berichten wordt toegepast.

## <a name="for-more-information"></a>Voor meer informatie

[E-mailstroomregels gebruiken om berichtbijlagen in Exchange Online te inspecteren](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

[E-mailversleuteling in Office 365](../../compliance/email-encryption.md)

[Limieten voor logboek-, transport- en postvak IN](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#journal-transport-and-inbox-rule-limits)
