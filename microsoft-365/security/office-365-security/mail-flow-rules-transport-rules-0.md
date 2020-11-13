---
title: Regels voor e-mail stroom in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9c2cf227-eff7-48ef-87fb-487186e47363
description: U kunt de e-mail stroom regels (transportregels) gebruiken om berichten te identificeren en te ondernemen die door uw organisatie worden verzonden.
ms.openlocfilehash: 11bf2af56c6e85c868e2e0726736f624e196805c
ms.sourcegitcommit: 9546708a5506fdbadbfe2500cbf1bd1aeaec6fcb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2020
ms.locfileid: "49021047"
---
# <a name="mail-flow-rules-transport-rules-in-standalone-eop"></a>E-mailstroomregels (transportregels) in standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In zelfstandige Exchange Online Protection-organisaties (EOP), kunt u zonder postvakken van Exchange Online een e-mail stroom regels (ook wel transport regels genoemd) gebruiken om berichten te identificeren en te ondernemen die door uw organisatie worden verzonden.

In dit onderwerp worden de onderdelen van de e-mail stroom regels en hoe deze worden gebruikt.

Zie [e-mail stroom regels beheren in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)voor stapsgewijze instructies voor het maken, kopiëren en beheren van e-mail stroom regels. Voor elke regel hebt u de mogelijkheid om het af te dwingen, te testen of te testen en de afzender te informeren. Zie voor meer informatie over de opties voor testen [e-mail stroom regels](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/test-mail-flow-rules) en [beleids tips in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/policy-tips)testen.

Zie [e-mail beveiligingsrapporten gebruiken om gegevens te bekijken over malware, spam en regel detectie](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports)voor samenvattings-en detailrapporten over berichten die overeenkomen met de regels voor de e-mail stroom.

Zie de volgende onderwerpen voor informatie over het implementeren van bepaalde berichten beleidsregels via e-mail stroom regels:

- [De e-mail stroom regels gebruiken om berichten bijlagen te controleren in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

- [Versleuteling instellen in Office 365 Enterprise](../../compliance/set-up-encryption.md)

- [Voor de hele organisatie beweringen, handtekeningen, voetteksten of kopteksten in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)

- [Het betrouwbaarheidsniveau voor ongewenste e-mail (SCL) in berichten instellen met behulp van de regels voor e-mail stroom](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- [Lijsten met geblokkeerde verzenders maken in EOP](create-block-sender-lists-in-office-365.md)

- [Bedreiging van malware beperken via bestandsbijlage blokkering in Exchange Online Protection](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)

- [Regels definiëren voor het versleutelen of versleutelen van e-mailberichten in Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)

In de volgende video ziet u een demonstratie van het instellen van e-mail stroom regels in zelfstandige EOP.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]

## <a name="mail-flow-rule-components"></a>Onderdelen van een e-mail stroom regel

Een e-mail stroom regel bestaat uit voorwaarden, uitzonderingen, acties en eigenschappen:

- **Voorwaarden** : Geef aan met welke berichten u de acties wilt toepassen. In sommige voorwaarden wordt de bericht-header velden onderzocht, bijvoorbeeld de velden aan, van of CC. Overige voorwaarden Bekijk de berichteigenschappen (bijvoorbeeld het onderwerp van het bericht, de hoofdtekst, de bijlagen, de berichtgrootte of de bericht classificatie). Voor de meeste voorwaarden moet u een vergelijkingsoperator opgeven (bijvoorbeeld is gelijk aan, is niet gelijk aan, is niet gelijk aan, is niet gelijk aan, is niet gelijk aan) en een waarde Als er geen voorwaarden of uitzonderingen zijn, wordt de regel toegepast op alle berichten.

Zie voor meer informatie over de voorwaarden voor de e-mail stroom regels in zelfstandige EOP de [voorwaarden voor de e-mail stroom regels en uitzonderingen (predikaten) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

- **Uitzonderingen** : Identificeer ook de berichten waarop de acties niet van toepassing zijn. De in voorwaarden beschikbare bericht aanduidingen zijn ook beschikbaar in uitzonderingen. Uitzonderingen voor voorwaarden negeren en voorkomen dat de regelacties worden toegepast op een bericht, zelfs als het bericht overeenkomt met alle geconfigureerde voorwaarden.

- **Acties** : Geef aan wat er moet gebeuren met berichten die voldoen aan de voorwaarden in de regel en die niet overeenkomen met een van de uitzonderingen. Er zijn veel acties beschikbaar, zoals het afwijzen, verwijderen of omleiden van berichten, het toevoegen van extra geadresseerden, het toevoegen van voorvoegsels in het onderwerp van het bericht of het invoegen van disclaimers in de berichttekst.

Zie [acties voor e-mail stroom regels in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)voor meer informatie over acties voor e-mail stroom regels die beschikbaar zijn in zelfstandige EOP.

- **Eigenschappen** : andere regels opgeven die geen voorwaarden, uitzonderingen of acties opgeven. Wanneer de regel moet worden toegepast, of als u de regel wilt toepassen of testen, en de periode waarin de regel actief is.

  Zie voor meer informatie de sectie [Eigenschappen voor e-mail stroom regels](#mail-flow-rule-properties) in dit onderwerp.

### <a name="multiple-conditions-exceptions-and-actions"></a>Meerdere voorwaarden, uitzonderingen en acties

In de volgende tabel ziet u hoe meerdere voorwaarden, waarden voor voorwaarden, uitzonderingen en acties in een regel worden afgehandeld.

****

|Invoert|Logische|Ontvangen|
|---|---|---|
|Meerdere voorwaarden|EN|Een bericht moet voldoen aan alle voorwaarden in de regel. Als u een voorwaarde of een andere voorwaarde moet voldoen, gebruikt u voor elke voorwaarde aparte regels. Als u bijvoorbeeld dezelfde Disclaimer wilt toevoegen aan berichten met bijlagen en berichten die specifieke tekst bevatten, maakt u een regel voor elke voorwaarde. In het Exchange-Beheercentrum kunt u eenvoudig een regel kopiëren.|
|Eén voorwaarde met meerdere waarden|OF|Met sommige voorwaarden kunt u meerdere waarden opgeven. Het bericht moet overeenkomen met een (niet alle) van de opgegeven waarden. Als een e-mailbericht bijvoorbeeld de informatie over de aandelenkoers bevat, en het **onderwerp een van deze woord voorwaarden bevat** , is geconfigureerd voor overeenstemming met de woorden Contoso of stock, wordt de voorwaarde vervuld omdat het onderwerp minstens één van de opgegeven waarden bevat.|
|Meerdere uitzonderingen|OF|Als een bericht overeenkomt met een van de uitzonderingen, worden de acties niet op het bericht toegepast. Het bericht hoeft niet te voldoen aan alle uitzonderingen.|
|Meerdere acties|EN|Bij berichten die voldoen aan de voorwaarden van een regel, worden alle acties weergegeven die zijn opgegeven in de regel. Als bijvoorbeeld de actie **door het onderwerp van het bericht met** en **geadresseerden toevoegen aan het vak BCC** is geselecteerd, worden beide acties op het bericht toegepast. <p> Houd er rekening mee dat het niet mogelijk is om te voorkomen dat de volgende regels worden toegepast op een bericht, zoals het **bericht verwijderen** . Andere acties, zoals **het doorsturen van het bericht** , bieden geen extra acties mogelijk. <p> U kunt ook een actie toepassen op een regel, zodat wanneer deze regel wordt toegepast, volgende regels niet worden toegepast op het bericht.|
|

### <a name="mail-flow-rule-properties"></a>Eigenschappen van een e-mail stroom regel

In de volgende tabel worden de regeleigenschappen beschreven die beschikbaar zijn in de e-mail stroom regels.

****

|Naam van eigenschap in het SBV|Parameter naam in PowerShell|Beschrijving|
|---|---|---|
|**Prioriteit**|_Prioriteit_|Hiermee wordt de volgorde aangegeven waarin de regels worden toegepast op berichten. De standaardprioriteit is gebaseerd op het moment dat de regel wordt gemaakt (oudere regels hebben een hogere prioriteit dan nieuwere regels en regels met een hogere prioriteit worden verwerkt). <p> U kunt de prioriteit van de regel in het SBV wijzigen door de regel omhoog of omlaag te verplaatsen in de lijst met regels. In PowerShell stelt u het prioriteitsnummer in (0 is de hoogste prioriteit). <p> Als u bijvoorbeeld een regel hebt om berichten te negeren die een creditcardnummer bevatten en een andere regel die moet worden goedgekeurd, moet u de regel weigeren eerst uitvoeren en andere regels niet meer toepassen.  |
|**Kernelmodusstuurprogramma**|_Kernelmodusstuurprogramma_|U kunt opgeven of u wilt dat de regel direct berichten verwerkt, of dat u regels wilt testen zonder dat dit van invloed is op de bezorging van het bericht (met of zonder preventie van gegevensverlies of tips voor DLP-beleid). <p> Beleids tips geven een korte notitie in Outlook of de webversie van Outlook weer met informatie over mogelijke beleidsschendingen van de persoon die het bericht maakt. Zie **Tips voor beleid** voor meer informatie. <p> Zie voor meer informatie over de modi **een regel voor een e-mail stroom testen**.|
|**Deze regel activeren voor de volgende datum** <p> **Deze regel deactiveren voor de volgende datum**|_ActivationDate_ <p> _ExpiryDate_|Hiermee wordt het datumbereik opgegeven waarmee de regel actief is.|
|**Selectievakje is ingeschakeld of** niet geselecteerd|Nieuwe regels: de parameter _enabled_ voor de **New-TransportRule-** cmdlet. <p> Bestaande regels: gebruik de cmdlets **Enable-TransportRule** of **Disable-TransportRule** . <p> De waarde wordt weergegeven in de eigenschap **status** van de regel.|U kunt een uitgeschakelde regel maken en inschakelen wanneer u de regel gaat testen. U kunt ook een regel uitschakelen zonder deze te verwijderen om de instellingen te behouden.|
|**Bericht uitstellen als de verwerking van de regel niet is voltooid**|_RuleErrorAction_|U kunt opgeven hoe het bericht moet worden afgehandeld als de verwerking van de regel niet kan worden voltooid. De regel wordt standaard genegeerd, maar u kunt er ook voor kiezen om het bericht opnieuw te verzenden voor verwerking.|
|**Adres van afzender in bericht aanpassen**|_SenderAddressLocation_|Als bij de regel voorwaarden of uitzonderingen wordt gezocht die het e-mailadres van de afzender beoordeelt, kunt u zoeken naar de waarde in de kop van het bericht, de envelop van het bericht of beide.|
|**De verwerking van meer regels stoppen**|_SenderAddressLocation_|Dit is een actie voor de regel, maar deze ziet er uit als een eigenschap in het SBV. U kunt ervoor kiezen om meer regels op een bericht toe te voegen na een regel verwerkt een bericht.|
|**Ontvangen**|_Ontvangen_|U kunt beschrijvende opmerkingen opgeven voor de regel.|
|

## <a name="how-mail-flow-rules-are-applied-to-messages"></a>Hoe e-mail stroom regels worden toegepast op berichten

Alle berichten die door uw organisatie worden doorgevoerd, worden geëvalueerd tegen de ingeschakelde regels voor de e-mail stroom in uw organisatie. Regels worden in de weergegeven volgorde verwerkt op de pagina regels voor **e-mail stroom** \> **Rules** in het PowerShell-programma of op basis van de bijbehorende parameterwaarde voor _prioriteit_ in PowerShell.

Elke regel biedt ook de mogelijkheid om de verwerking van meer regels te onderbreken wanneer de regel wordt vergeleken. Deze instelling is belangrijk voor berichten die voldoen aan de voorwaarden in meerdere e-mail stroom regels (welke regel wilt u op het bericht toepassen? Al? Slechts één?).

### <a name="differences-in-processing-based-on-message-type"></a>Verschillen in de verwerking op basis van berichttype

Er zijn verschillende typen berichten die een organisatie passeren. In de volgende tabel ziet u welke berichten typen kunnen worden verwerkt door de e-mail stroom regels.

****

|Type bericht|Kan een regel worden toegepast?|
|---|---|
|**Normale berichten** : berichten met een berichttekst met een enkele tekstindeling (Rich Text Format), HTML of tekst zonder opmaak of een meerdelige of een andere groep berichten.|Ja|
|Berichten **versleutelen in office 365** : berichten versleuteld met bericht versleuteling van Office 365 in Office 365. Zie voor meer informatie [versleutelen in Office 365](https://docs.microsoft.com/microsoft-365/compliance/encryption).|Regels hebben altijd toegang tot envelop koppen en proces berichten op basis van voorwaarden die deze kopteksten controleren. <p> Als u de inhoud van een versleuteld bericht wilt controleren of wijzigen, dient u te controleren of het versleutelen van transport is ingeschakeld (verplicht of optioneel; de standaardinstelling is optioneel). Zie [regels definiëren voor het versleutelen of versleutelen van e-mailberichten in Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)voor meer informatie.|
|**S/MIME versleutelde berichten**|Regels hebben alleen toegang tot envelop koppen en proces berichten op basis van voorwaarden die deze kopteksten controleren. <p> Regels met voorwaarden die inspectie van de inhoud van het bericht vereisen of acties waarmee de inhoud van het bericht wordt gewijzigd, kunnen niet worden verwerkt.|
|**Beveiligde berichten in RMS** : berichten waarop een Active Directory Rights Management Services-of Azure Rights Management (RMS)-beleid is toegepast.|Regels hebben altijd toegang tot envelop koppen en proces berichten op basis van voorwaarden die deze kopteksten controleren. <p> Voor een regel om de inhoud van een beveiligd bericht met RMS te controleren of te wijzigen, controleert u of het versleutelen van transport is ingeschakeld (verplicht of optioneel; de standaardinstelling is optioneel).|
|**Berichten** met een uitgeschakeld bericht: berichten die zijn ondertekend maar niet zijn versleuteld.|Ja|
|**Um-berichten** : berichten die zijn gemaakt of verwerkt door de Unified Messaging-Service, zoals voicemail, Fax, meldingen voor gemiste oproepen en berichten die zijn gemaakt of doorgestuurd met behulp van Microsoft Outlook Voice Access.|Ja|
|**Anonieme berichten** : berichten verzonden door anonieme afzenders.|Ja|
|**Lees rapporten** : rapporten die worden gegenereerd in antwoord om ontvangstbevestiging van afzender verzoeken te lezen. Lees rapporten hebben een berichtklasse van `IPM.Note*.MdnRead` of `IPM.Note*.MdnNotRead` .|Ja|
|

## <a name="what-else-should-i-know"></a>Wat moet ik nog meer weten?

- De waarde van de eigenschap **Version** of **RuleVersion** voor een regel is niet belangrijk in Exchange Online Protection.

- Wanneer u een e-mail stroom regel hebt gemaakt of gewijzigd, kan het tot 30 minuten duren voordat de nieuwe of bijgewerkte regel op berichten is toegepast.

## <a name="for-more-information"></a>Voor meer informatie

[De e-mail stroom regels gebruiken om berichten bijlagen te controleren in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

[E-mail versleuteling in Office 365](../../compliance/email-encryption.md)

[Regel beperkingen voor logboeken, transport en Postvak in](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#journal-transport-and-inbox-rule-limits)
