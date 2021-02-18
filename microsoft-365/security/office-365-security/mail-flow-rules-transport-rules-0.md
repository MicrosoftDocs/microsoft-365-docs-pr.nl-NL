---
title: Regels voor e-mailstroom in EOP
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
description: U kunt regels voor de e-mailstroom (transportregels) gebruiken om berichten te identificeren en actie te ondernemen die door uw organisatie stromen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d189a9f4b21828fa4e23f7d5a325b4e9c56259bc
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289935"
---
# <a name="mail-flow-rules-transport-rules-in-standalone-eop"></a>E-mailstroomregels (transportregels) in standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken kunt u regels voor de e-mailstroom (ook wel transportregels genoemd) gebruiken om berichten te identificeren en actie te ondernemen die door uw organisatie stromen.

In dit onderwerp worden de onderdelen van regels voor de e-mailstroom en de manier waarop deze werken, uitgelegd.

Zie Regels voor de e-mailstroom beheren in Exchange Online voor stappen voor het maken, kopiëren en beheren van regels voor de [e-mailstroom.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) Voor elke regel kunt u de regel afdwingen, testen of testen en de afzender op de hoogte stellen. Zie Regels voor [e-mailstroomtests](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/test-mail-flow-rules) en beleidstips in Exchange Online voor meer informatie over de [testopties.](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/policy-tips)

Zie Rapporten over e-mailbeveiliging gebruiken om gegevens over malware, spam en regeldetectie weer te geven voor overzichtsrapporten en detailrapporten over berichten die voldoen aan de regels voor de [e-mailstroom.](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports)

Zie de volgende onderwerpen als u specifiek berichtbeleid wilt implementeren met behulp van regels voor de e-mailstroom:

- [Regels voor de e-mailstroom gebruiken om berichtbijlagen in Exchange Online te controleren](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

- [Versleuteling instellen in Office 365 Enterprise](../../compliance/set-up-encryption.md)

- [Vrijwaringen, handtekeningen, voetteksten of kopteksten voor berichten in de hele organisatie in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)

- [Regels voor de e-mailstroom gebruiken om het betrouwbaarheidsniveau voor spam in berichten in te stellen](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- [Lijsten met geblokkeerde afzenders maken in EOP](create-block-sender-lists-in-office-365.md)

- [Malwarerisico's verminderen door blokkering van bestandsbijlagen in Exchange Online Protection](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)

- [Regels definiëren voor het versleutelen of ontsleutelen van e-mailberichten in Office 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md)

In de volgende video wordt een demonstratie gegeven van het instellen van regels voor de e-mailstroom in zelfstandige EOP.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]

## <a name="mail-flow-rule-components"></a>Onderdelen van e-mailstroomregel

Een e-mailstroomregel bestaat uit voorwaarden, uitzonderingen, acties en eigenschappen:

- **Voorwaarden:** Identificeer de berichten op wie u de acties wilt toepassen. Bij sommige voorwaarden worden de berichtkopvelden (bijvoorbeeld de velden Aan, Van of CC) onderzocht. Met andere voorwaarden worden de berichteigenschappen onderzocht (bijvoorbeeld het onderwerp, de berichtbijlage, bijlagen, de grootte van het bericht of de berichtclassificatie). Voor de meeste voorwaarden moet u een vergelijkingsoperator opgeven (bijvoorbeeld is gelijk aan, is niet gelijk aan of bevat) en een waarde die moet worden vergeleken. Als er geen voorwaarden of uitzonderingen zijn, wordt de regel toegepast op alle berichten.

Zie voorwaarden voor E-mailstroomregel en uitzonderingen [(predicaten) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)voor meer informatie over voorwaarden voor e-mailstroomregel in zelfstandige EOP.

- **Uitzonderingen:** identificeer desgewenst de berichten die niet van toepassing mogen zijn op de acties. De berichtaanduidingen die onder voorwaarden beschikbaar zijn, zijn ook beschikbaar in uitzonderingen. Uitzonderingen overschrijven voorwaarden en voorkomen dat de regelacties worden toegepast op een bericht, zelfs als het bericht overeenkomt met alle geconfigureerde voorwaarden.

- **Acties:** geef op wat er moet worden gebeurd met berichten die voldoen aan de voorwaarden in de regel en komen niet overeen met een van de uitzonderingen. Er zijn veel acties beschikbaar, zoals het weigeren, verwijderen of omleiden van berichten, het toevoegen van extra geadresseerden, het toevoegen van voorvoegsels aan het onderwerp van het bericht of het invoegen van vrijwaringen in de bericht zelf.

Zie E-mailstroomregelacties in Exchange Online voor meer informatie over acties voor [e-mailstroomregelacties die](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)beschikbaar zijn in de zelfstandige EOP.

- **Eigenschappen:** geef andere regels op die geen voorwaarden, uitzonderingen of acties zijn. Wanneer de regel bijvoorbeeld moet worden toegepast, of u de regel wilt afdwingen of testen, en de tijdsperiode waarin de regel actief is.

  Zie de sectie eigenschappen van de regel voor de [e-mailstroom](#mail-flow-rule-properties) in dit artikel voor meer informatie.

### <a name="multiple-conditions-exceptions-and-actions"></a>Meerdere voorwaarden, uitzonderingen en acties

In de volgende tabel ziet u hoe meerdere voorwaarden, voorwaardenwaarden, uitzonderingen en acties in een regel worden verwerkt.

****

|Onderdeel|Logica|Opmerkingen|
|---|---|---|
|Meerdere voorwaarden|AND|Een bericht moet voldoen aan alle voorwaarden in de regel. Als u moet voldoen aan een of meer voorwaarden, gebruikt u afzonderlijke regels voor elke voorwaarde. Als u bijvoorbeeld dezelfde vrijwaring wilt toevoegen aan berichten met bijlagen en berichten die specifieke tekst bevatten, maakt u voor elke voorwaarde één regel. In het EAC kunt u eenvoudig een regel kopiëren.|
|Eén voorwaarde met meerdere waarden|OF|Bij sommige voorwaarden kunt u meer dan één waarde opgeven. Het bericht moet overeenkomen met een of meer van de opgegeven waarden. Als een e-mailbericht bijvoorbeeld het onderwerp Aandelenkoersinformatie bevat en het onderwerp een van deze woorden bevat, is geconfigureerd voor een overeenkomst met de woorden Contoso **of** aandelen, is aan de voorwaarde voldaan omdat het onderwerp ten minste één van de opgegeven waarden bevat.|
|Meerdere uitzonderingen|OF|Als een bericht overeenkomt met een van de uitzonderingen, worden de acties niet toegepast op het bericht. Het bericht hoeft niet overeen te komen met alle uitzonderingen.|
|Meerdere acties|AND|Berichten die voldoen aan de voorwaarden van een regel, krijgen alle acties die in de regel zijn opgegeven. Als bijvoorbeeld de acties **Voorbereiden op** het onderwerp van het bericht en Geadresseerden toevoegen aan het **vak BCC** zijn geselecteerd, worden beide acties op het bericht toegepast. <p> Houd er rekening mee dat  sommige acties, zoals Het bericht verwijderen zonder dat iemand op de hoogte wordt gehouden, voorkomen dat latere regels worden toegepast op een bericht. Andere acties, zoals Het **bericht doorsturen,** staan geen aanvullende acties toe. <p> U kunt ook een actie voor een regel instellen, zodat de volgende regels niet worden toegepast op het bericht wanneer deze regel wordt toegepast.|
|

### <a name="mail-flow-rule-properties"></a>Eigenschappen van e-mailstroomregel

In de volgende tabel worden de regeleigenschappen beschreven die beschikbaar zijn in regels voor de e-mailstroom.

****

|Naam van eigenschap in het EAC|Parameternaam in PowerShell|Beschrijving|
|---|---|---|
|**Prioriteit**|_Prioriteit_|Geeft de volgorde aan dat de regels worden toegepast op berichten. De standaardprioriteit is gebaseerd op het moment dat de regel wordt gemaakt (oudere regels hebben een hogere prioriteit dan nieuwere regels en regels met een hogere prioriteit worden verwerkt vóór regels met een lagere prioriteit). <p> U wijzigt de regelprioriteit in het EAC door de regel omhoog of omlaag te verplaatsen in de lijst met regels. In PowerShell stelt u het prioriteitsnummer in (0 is de hoogste prioriteit). <p> Als u bijvoorbeeld een regel hebt om berichten te weigeren die een creditcardnummer bevatten en een andere regel waarvoor goedkeuring is vereist, moet u eerst de regel voor weigeren toepassen en stoppen met het toepassen van andere regels.  |
|**Modus**|_Modus_|U kunt opgeven of de regel onmiddellijk moet beginnen met de verwerking van berichten of dat u regels wilt testen zonder dat dit van invloed is op de bezorging van het bericht (met of zonder tips voor preventie van gegevensverlies of DLP-beleidstips). <p> Beleidstips bevatten een korte notitie in Outlook of de webversie van Outlook met informatie over mogelijke beleidsovertredingen voor de persoon die het bericht maakt. Zie **beleidstips voor meer informatie.** <p> Zie Een regel voor de e-mailstroom testen voor meer informatie over **de modi.**|
|**Deze regel activeren op de volgende datum** <p> **Deze regel deactiveren op de volgende datum**|_ActivationDate_ <p> _ExpiryDate_|Hiermee geeft u het datumbereik op wanneer de regel actief is.|
|**Ingeschakeld** of niet ingeschakeld selectievakje|Nieuwe regels: _de ingeschakelde_ parameter op de cmdlet **New-TransportRule.** <p> Bestaande regels: gebruik de cmdlets **Enable-TransportRule** **of Disable-TransportRule.** <p> De waarde wordt weergegeven in de **eigenschap State** van de regel.|U kunt een uitgeschakelde regel maken en deze inschakelen wanneer u deze wilt testen. U kunt een regel ook uitschakelen zonder deze te verwijderen om de instellingen te behouden.|
|**Het bericht uitstellen als de verwerking van de regel niet is voltooid**|_RuleErrorAction_|U kunt opgeven hoe het bericht moet worden verwerkt als de verwerking van de regel niet kan worden voltooid. De regel wordt standaard genegeerd, maar u kunt het bericht opnieuw verzenden voor verwerking.|
|**Adres van afzender in bericht overeenkomen**|_SenderAddressLocation_|Als voor de regel voorwaarden of uitzonderingen worden gebruikt die het e-mailadres van de afzender onderzoeken, kunt u zoeken naar de waarde in de berichtkop, de berichtenvelop of beide.|
|**De verwerking van meer regels stoppen**|_SenderAddressLocation_|Dit is een actie voor de regel, maar deze ziet eruit als een eigenschap in het EAC. U kunt ervoor kiezen om te stoppen met het toepassen van extra regels op een bericht nadat een bericht is verwerkt door een regel.|
|**Opmerkingen**|_Opmerkingen_|U kunt beschrijvende opmerkingen over de regel invoeren.|
|

## <a name="how-mail-flow-rules-are-applied-to-messages"></a>E-mailstroomregels toepassen op berichten

Alle berichten die door uw organisatie stromen, worden geëvalueerd aan de hand van de ingeschakelde regels voor de e-mailstroom in uw organisatie. Regels worden verwerkt in de volgorde die wordt weergegeven op de pagina Regels voor **e-mailstroom** in het EAC of op basis van de bijbehorende waarde voor de \>  _prioriteitsparameter_ in PowerShell.

Elke regel biedt ook de mogelijkheid om de verwerking van meer regels te stoppen wanneer de regel wordt aaneenge passen. Deze instelling is belangrijk voor berichten die voldoen aan de voorwaarden van meerdere regels voor de e-mailstroom (welke regel wilt u op het bericht toepassen? Alles? Slechts één?).

### <a name="differences-in-processing-based-on-message-type"></a>Verschillen in verwerking op basis van berichttype

Er zijn verschillende soorten berichten die door een organisatie worden verzonden. In de volgende tabel ziet u welke berichtentypen kunnen worden verwerkt met regels voor de e-mailstroom.

****

|Type bericht|Kan een regel worden toegepast?|
|---|---|
|**Normale berichten:** berichten met één tekst met opmaak (RTF), HTML of berichttekst zonder opmaak, of een verzameling berichtteksten met meerdere onderdelen of alternatieve berichtteksten.|Ja|
|**Office 365-berichtversleuteling:** berichten die zijn versleuteld met Office 365-berichtversleuteling in Office 365. Zie Versleuteling [in Office 365 voor meer informatie.](../../compliance/encryption.md)|Regels hebben altijd toegang tot envelopkoppen en verwerken berichten op basis van voorwaarden die deze kopteksten controleren. <p> Als u wilt dat een regel de inhoud van een versleuteld bericht controleert of wijzigt, moet u controleren of ontsleuteling van het transport is ingeschakeld (verplicht of optioneel; de standaardwaarde is optioneel). Zie Regels definiëren voor het [versleutelen of ontsleutelen van e-mailberichten in Office 365 voor meer informatie.](../../compliance/define-mail-flow-rules-to-encrypt-email.md)|
|**Versleutelde S/MIME-berichten**|Regels hebben alleen toegang tot envelopkoppen en verwerken berichten op basis van voorwaarden die deze kopteksten controleren. <p> Regels met voorwaarden die controle van de inhoud van het bericht vereisen, of acties die de inhoud van het bericht wijzigen, kunnen niet worden verwerkt.|
|**Met RMS beveiligde berichten:** berichten met een AD RMS-beleid (Active Directory Rights Management Services) of RMS-beleid (Azure Rights Management).|Regels hebben altijd toegang tot envelopkoppen en verwerken berichten op basis van voorwaarden die deze kopteksten controleren. <p> Als u wilt dat een regel de inhoud van een met RMS beveiligd bericht controleert of wijzigt, moet u controleren of ontsleuteling van het transport is ingeschakeld (verplicht of optioneel; de standaardwaarde is optioneel).|
|**Niet-ondertekende berichten:** berichten die zijn ondertekend, maar niet zijn versleuteld.|Ja|
|**UM-berichten:** berichten die zijn gemaakt of verwerkt door de Unified Messaging-service, zoals voicemail, faxberichten, meldingen voor gemiste oproep en berichten die zijn gemaakt of doorgestuurd met Microsoft Outlook Voice Access.|Ja|
|**Anonieme berichten:** berichten die zijn verzonden door anonieme afzenders.|Ja|
|**Rapporten lezen:** rapporten die worden gegenereerd als reactie op leesbevestigingsaanvragen door afzenders. Rapporten lezen hebben een berichtklasse van of `IPM.Note*.MdnRead` `IPM.Note*.MdnNotRead` .|Ja|
|

## <a name="what-else-should-i-know"></a>Wat moet ik nog meer weten?

- De **eigenschapswaarde Versie** of RuleVersion voor een regel is niet belangrijk in Exchange Online Protection. 

- Nadat u een regel voor de e-mailstroom hebt maken of wijzigen, kan het 30 minuten duren voordat de nieuwe of bijgewerkte regel wordt toegepast op berichten.

## <a name="for-more-information"></a>Voor meer informatie

[Regels voor de e-mailstroom gebruiken om berichtbijlagen in Exchange Online te controleren](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

[E-mailversleuteling in Office 365](../../compliance/email-encryption.md)

[Limieten voor logboek-, transport- en Postvak IN-regels](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#journal-transport-and-inbox-rule-limits)
