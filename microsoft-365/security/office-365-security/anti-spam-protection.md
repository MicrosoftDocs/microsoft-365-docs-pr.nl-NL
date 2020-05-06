---
title: Beveiliging tegen ongewenste e-mail
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over de antispam-instellingen en -filters waarmee u spam voorkomen in Exchange Online en Microsoft 365.
ms.openlocfilehash: 96132bf66438861eb117aedd841f7912de1258cc
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034056"
---
# <a name="anti-spam-protection-in-microsoft-365"></a>Bescherming tegen spam in Microsoft 365

> [!NOTE]
> Dit onderwerp is bedoeld voor Microsoft 365-beheerders. Zie [Overzicht van het filter ongewenste e-mail](https://support.Microsoft.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) en ongewenste [e-mail en phishing](https://support.Microsoft.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31)voor onderwerpen van eindgebruikers.

Als u een Microsoft 365-klant bent met postvakken in Exchange Online of een zelfstandige Exchange Online Protection (EOP)-klant zonder Exchange Online-postvakken, worden uw e-mailberichten automatisch beschermd tegen spam (ongewenste e-mail) door EOP.

Microsoft's e-mail veiligheid roadmap omvat een ongeëvenaarde cross-product aanpak. EOP anti-spam en anti-phishing technologie wordt toegepast op onze e-mailplatforms om gebruikers te voorzien van de nieuwste anti-spam en anti-phishing tools en innovaties in het hele netwerk. Het doel voor EOP is om een uitgebreide en bruikbare e-mailservice aan te bieden die gebruikers helpt detecteren en beschermen tegen ongewenste e-mail, frauduleuze e-mailbedreigingen (phishing) en malware.

Aangezien e-mail gebruik is gegroeid, zo heeft e-mail misbruik. Niet-bewaakte ongewenste e-mail kan inboxen en netwerken verstoppen, de tevredenheid van gebruikers beïnvloeden en de effectiviteit van legitieme e-mailcommunicatie belemmeren. Daarom blijft Microsoft investeren in antispamtechnologieën. Simpel gezegd, het begint met het bevatten en filteren van ongewenste e-mail.

## <a name="anti-spam-technologies-in-eop"></a>Antispamtechnologieën in EOP

Om ongewenste e-mail te helpen verminderen, bevat EOP bescherming tegen ongewenste e-mail die gebruikmaakt van gepatenteerde spamfiltertechnologieën om ongewenste e-mail te identificeren en te scheiden van legitieme e-mail. EOP spam filtering leert van bekende spam en phishing bedreigingen en feedback van gebruikers van onze consument platform, Outlook.com. Voortdurende feedback van EOP-gebruikers in het classificatieprogramma voor ongewenste e-mail helpt ervoor te zorgen dat de EOP-technologieën voortdurend worden getraind en verbeterd.

De anti-spam instellingen in EOP zijn gemaakt van de volgende technologieën:

- **Verbindingsfiltering:** identificeert goede en slechte e-mailbronservers in het begin van de binnenkomende e-mailverbinding via de IP-lijst met toegestane gegevens, IP-bloklijst en de *veilige lijst* (een dynamische maar niet-bewerkbare lijst met vertrouwde afzenders die door Microsoft worden onderhouden). U configureert deze instellingen in het verbindingsfilterbeleid. Meer informatie bij [Verbindingsfiltering configureren in Microsoft 365](configure-the-connection-filter-policy.md).

  > [!NOTE]
  > Spoofintelligentie maakt gebruik van verbindingsfiltering om lijsten te maken en te blokkeren van afzenders die uw e-maildomein spoofen. Zie [Meer informatie over spoofinformatie in Microsoft 365](learn-about-spoof-intelligence.md)voor meer informatie.

- **Spam filtering (content filtering)**: EOP maakt gebruik van de spam filteren vonnissen **Spam,** **Hoog vertrouwen spam,** **Bulk e-mail,** **Phishing e-mail** en **Hoog vertrouwen phishing e-mail** om berichten te classificeren. U de acties die u moet uitvoeren configureren op basis van deze uitspraken en u de systeemopties voor meldingen configureren voor berichten die in quarantaine zijn geplaatst in plaats van geleverd. Zie [Beleid voor antispam configureren in Microsoft 365](configure-your-spam-filter-policies.md)voor meer informatie.

  > [!NOTE]
  > Standaard is spamfiltering geconfigureerd om berichten die als spam zijn gemarkeerd, naar de map Ongewenste e-mail van de ontvanger te verzenden. In hybride omgevingen waar EOP on-premises Exchange-postvakken beschermt, moet u echter twee regels voor e-mailstroom (ook wel transportregels genoemd) configureren in uw on-premises Exchange-organisatie om de EOP-spamkoppen te herkennen die aan berichten worden toegevoegd. Zie [Standalone EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) voor meer informatie. 

- **Uitgaande spamfiltering:** EOP controleert ook of uw gebruikers geen spam verzenden, hetzij in uitgaande berichtinhoud, hetzij door de grenzen van uitgaande berichten te overschrijden. Zie [Uitgaand spamfilteren configureren in Microsoft 365](configure-the-outbound-spam-policy.md)voor meer informatie.

- **Spoofinformatie:** zie Meer [informatie over spoofinformatie in Microsoft 365](learn-about-spoof-intelligence.md)voor meer informatie.

## <a name="manage-errors-in-spam-filtering"></a>Fouten in spamfiltering beheren

Het is mogelijk dat goede berichten kunnen worden geïdentificeerd als spam (ook bekend als false positives), of dat spam kan worden geleverd aan de Inbox. U de suggesties in de volgende secties gebruiken om erachter te komen wat er is gebeurd en om te voorkomen dat dit in de toekomst gebeurt.

Hier volgen enkele aanbevolen procedures die van toepassing zijn op beide scenario's:

- Verzend altijd verkeerd geclassificeerde berichten bij Microsoft. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

- **De antispamberichtenkoppen onderzoeken:** deze waarden vertellen u waarom een bericht is gemarkeerd als spam of waarom het spamfilter heeft overgeslagen. Zie [Kopteksten voor antispamberichten](anti-spam-message-headers.md)voor meer informatie.

- **Richt uw MX-record op Microsoft 365:** Om ervoor te zorgen dat EOP de beste bescherming biedt, raden we u altijd aan om eerst e-mail aan Microsoft 365 te laten bezorgen. Zie [DNS-records maken bij elke DNS-hostingprovider voor Microsoft 365 voor](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)instructies.

  Als de MX-record naar een andere locatie verwijst (bijvoorbeeld een antispamoplossing of toestel van derden), is het voor EOP moeilijk om nauwkeurige spamfilters te bieden. In dit scenario moet u Uitgebreide filtering configureren voor connectors (ook wel _aanbieding overslaan genoemd)._ Zie Uitgebreide [filtering voor connectors in Exchange Online voor](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)instructies .

- **E-mailverificatie gebruiken:** als u eigenaar bent van een e-maildomein, u DNS gebruiken om te verzekeren dat berichten van afzenders in dat domein legitiem zijn. Gebruik alle volgende e-mailverificatiemethoden om spam en ongewenste spoofing in EOP te voorkomen:

  - **SPF**: Sender Policy Framework verifieert het bron-IP-adres van het bericht tegen de eigenaar van het verzendende domein. Zie [SPF instellen om spoofing te voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md)voor een snelle introductie tot SPF en om deze snel te configureren. Voor een beter begrip van hoe Microsoft 365 gebruikmaakt van SPF of voor het oplossen van problemen of niet-standaardimplementaties zoals hybride implementaties, begint u met [Hoe Microsoft 365 gebruikmaakt van SPF (Sender Policy Framework) om spoofing te voorkomen](how-office-365-uses-spf-to-prevent-spoofing.md).

  - **DKIM**: DomainKeys Identified Mail voegt een digitale handtekening toe aan de berichtheader van berichten die vanuit uw domein worden verzonden. Zie [DKIM gebruiken om uitgaande e-mail die vanuit uw aangepaste domein in Microsoft 365 is verzonden, te valideren.](use-dkim-to-validate-outbound-email.md)

  - **DMARC**: Met domeinverificatie, rapportage en conformiteit kunnen e-mailsystemen bepalen wat ze moeten doen met berichten die niet slagen op SPF- of DKIM-controles en biedt een ander niveau van vertrouwen voor uw e-mailpartners. Zie [DMARC gebruiken om e-mail in Microsoft 365 te valideren](use-dmarc-to-validate-email.md)voor meer informatie.

- **Controleer uw bulke-mailinstellingen:** de BCL-drempelwaarde (Bulk compliant level) die u configureert in antispambeleid, bepaalt of bulke-mail (ook wel _grijze e-mail_genoemd) is gemarkeerd als spam. De PowerShell-instelling _MarkAsSpamBulkMail_ die standaard is ingeschakeld, draagt ook bij aan de resultaten. Zie [Beleid voor antispam configureren in Microsoft 365](configure-your-spam-filter-policies.md)voor meer informatie.

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Voorkomen dat spam naar het Postvak IN wordt gebracht

- **Uw organisatie-instellingen verifiëren:** Kijk uit voor instellingen waarmee berichten spamfilters kunnen overslaan (bijvoorbeeld als u uw eigen domein toevoegt aan de lijst met toegestane domeinen in antispambeleid). Zie [Aanbevolen instellingen voor EOP- en Microsoft 365 ATP-beveiliging en](recommended-settings-for-eop-and-office365-atp.md) Lijsten met veilige [afzenders voor](create-safe-sender-lists-in-office-365.md)onze aanbevolen instellingen.

- **Controleer of de regel voor ongewenste e-mail is ingeschakeld in het postvak van de gebruiker:** deze is standaard ingeschakeld, maar als deze is uitgeschakeld, kunnen berichten die als ongewenste e-mail zijn gemarkeerd, niet naar de map Ongewenste e-mail worden verplaatst. Zie [Instellingen voor ongewenste e-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie.

- **De lijsten met beschikbare geblokkeerde afzenders gebruiken:** zie [Lijsten met geblokkeerde afzenderen maken](create-block-sender-lists-in-office-365.md)voor informatie .

- **Afmelden voor bulke-mail** Als het bericht iets was waarvoor de gebruiker zich heeft aangemeld (nieuwsbrieven, productaankondigingen, enz.) en een afmeldlink van een gerenommeerde bron bevat, u overwegen deze te vragen zich gewoon af te melden.

- **Standalone EOP: maak e-mailstroomregels in on-premises Exchange voor EOP-spamfilteringsvonnissen:** In zelfstandige EOP-omgevingen waar EOP on-premises Exchange-postvakken beschermt, moet u de regels voor e-mailstromen (ook wel transportregels genoemd) configureren in on-premises Exchange om het EOP-spamfiltervonnis te vertalen, zodat de ongewenste e-mailregel het bericht naar de map Ongewenste e-mail kan verplaatsen. Zie [Standalone EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) voor meer informatie. 

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Voorkomen dat goede e-mail wordt geïdentificeerd als spam

Hier volgen enkele stappen die u nemen om valse positieven te voorkomen:

- **Controleer de instellingen van het filterfilter voor ongewenste e-mail van de gebruiker:**

  - **Controleer of het filter voor ongewenste e-mail van Outlook is uitgeschakeld:** wanneer het filter voor ongewenste e-mail van Outlook is ingesteld op de standaardwaarde **Geen automatische filtering,** probeert Outlook massages niet als spam te classificeren.  Wanneer het is ingesteld op **Laag** of **Hoog,** gebruikt het Outlook Junk Email-filter zijn eigen SmartScreen-filtertechnologie om spam te identificeren en naar de map Ongewenste e-mail te verplaatsen, zodat u valse positieven krijgen. Houd er rekening mee dat Microsoft in november 2016 is gestopt met het produceren van spamdefinitie-updates voor de SmartScreen-filters in Exchange en Outlook. De bestaande SmartScreen spam definities werden overgelaten op zijn plaats, maar hun effectiviteit zal waarschijnlijk degraderen na verloop van tijd.

  - **Controleer of de instelling 'Alleen veilige lijsten' van Outlook is uitgeschakeld:** wanneer deze instelling is ingeschakeld, worden alleen berichten van afzenders in de lijst Met veilige afzenders van de gebruiker of de lijst Met veilige geadresseerden naar het Postvak IN bezorgd. e-mail van iedereen wordt automatisch verplaatst naar de map Ongewenste e-mail.

  Zie Instellingen voor ongewenste [e-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie over deze instellingen.

- **De lijsten met beschikbare veilige afzenders gebruiken:** Zie voor informatie [Lijsten met veilige afzenders maken](lijsten met veilige afzenders maken-in-office-365.md.

- **Controleer of gebruikers zich binnen de verzend- en ontvangstlimieten bevinden,** zoals beschreven in [Het ontvangen en verzenden van limieten](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) in de beschrijving van de Exchange Online-service.

- **Standalone EOP: gebruik adreslijstsynchronisatie:** als u standalone EOP gebruikt om uw on-premises Exchange-organisatie te beschermen, moet u gebruikersinstellingen synchroniseren met de service met behulp van adreslijstsynchronisatie. Dit zorgt ervoor dat de lijsten met veilige afzenders van uw gebruikers worden gerespecteerd door EOP. Zie [Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren voor](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users)meer informatie.

## <a name="anti-spam-legislation"></a>Antispamwetgeving

Bij Microsoft zijn we van mening dat de ontwikkeling van nieuwe technologieën en zelfregulering de ondersteuning vereist van effectief overheidsbeleid en juridische kaders. De wereldwijde spam proliferatie heeft aangespoord tal van wetgevende instanties om commerciële e-mail te reguleren. Veel landen hebben nu spam-fighting wetten op zijn plaats. De Verenigde Staten heeft zowel federale en staatswetten voor spam, en deze complementaire aanpak helpt om spam te beperken, terwijl het mogelijk maken van legitieme e-commerce te bloeien. De CAN-SPAM Act breidt de tools die beschikbaar zijn voor het beteugelen van frauduleuze en misleidende e-mailberichten.