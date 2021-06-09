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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer informatie krijgen over de antispaminstellingen en -filters die spam in Exchange Online Protection (EOP) helpen voorkomen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 52e891a86e75309dadd445736738a3f25584823e
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624859"
---
# <a name="anti-spam-protection-in-eop"></a>Bescherming tegen spam in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)

> [!NOTE]
> Dit onderwerp is bedoeld voor beheerders. Zie Overzicht van het filter voor [ongewenste](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) e-mail en Meer informatie over ongewenste [e-mail en phishing](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31)voor onderwerpen van eindgebruikers.

In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP) organisaties zonder Exchange Online-postvakken, worden e-mailberichten automatisch beveiligd tegen spam (ongewenste e-mail) door EOP.

De routekaart voor e-mailveiligheid van Microsoft omvat een niet-overeenkomende benadering voor cross-product. EOP-antispam- en anti-phishingtechnologie wordt toegepast op onze e-mailplatforms om gebruikers te voorzien van de nieuwste antispam- en anti-phishinghulpmiddelen en -innovaties in het hele netwerk. Het doel van EOP is om een uitgebreide en bruikbaar e-mailservice aan te bieden waarmee gebruikers kunnen worden gedetecteerd en beschermd tegen ongewenste e-mail, frauduleuze e-maildreigingen (phishing) en malware.

Naarmate het gebruik van e-mail is toegenomen, is het misbruik van e-mail ook toegenomen. Ongemonitorde ongewenste e-mail kan postvak IN en netwerken in de weg staan, de tevredenheid van gebruikers beïnvloeden en de effectiviteit van legitieme e-mailcommunicatie belemmeren. Daarom blijft Microsoft investeren in antispamtechnologieën. Eenvoudig gezegd, het begint met het bevatten en filteren van ongewenste e-mail.

> [!TIP]
> De volgende antispamtechnologieën zijn handig als u berichten wilt toestaan of blokkeren op basis van de envelop met berichten (bijvoorbeeld het domein van de afzender of het bron-IP-adres van het bericht). Als u berichten wilt toestaan of blokkeren op basis van laadvermogen (bijvoorbeeld URL's in het bericht of bijgevoegde bestanden), moet u de [portal Tenant allow/Block List gebruiken.](tenant-allow-block-list.md)

## <a name="anti-spam-technologies-in-eop"></a>Antispamtechnologieën in EOP

EOP bevat bescherming tegen ongewenste e-mail die gebruikmaakt van eigen spamfiltertechnologieën om ongewenste e-mail te identificeren en te scheiden van legitieme e-mail. EOP-spamfilters leren van bekende spam- en phishingrisico's en feedback van gebruikers van ons consumentenplatform, Outlook.com. Permanente feedback van EOP-gebruikers in het classificatieprogramma voor ongewenste e-mail helpt ervoor te zorgen dat de EOP-technologieën voortdurend worden opgeleid en verbeterd.

De antispaminstellingen in EOP zijn gemaakt van de volgende technologieën:

- Verbindingsfilters: identificeert goede en slechte e-mailbronservers in het begin van de inkomende e-mailverbinding via de IP-lijst toestaan, ip-blokkeringslijst en de veilige lijst *(een* dynamische, maar niet-bewerkbare lijst met vertrouwde afzenders die door Microsoft worden onderhouden). U configureert deze instellingen in het verbindingsfilterbeleid. Meer informatie bij [Verbindingsfilters configureren.](configure-the-connection-filter-policy.md)

- **Spamfilters (inhoudsfiltering)**: EOP gebruikt de spamfilters **Spam,**  Spam met hoog **vertrouwen,** Bulk-e-mail, Phishing-e-mail en phishing-e-mail met veel vertrouwen om berichten te classificeren.  U kunt de acties configureren die u wilt uitvoeren op basis van deze uitspraken en u kunt de meldingsopties voor eindgebruikers configureren voor berichten die in quarantaine zijn geplaatst in plaats van bezorgd. Zie [Antispambeleid configureren in](configure-your-spam-filter-policies.md)Microsoft 365.

  > [!NOTE]
  > Spamfilters zijn standaard zo geconfigureerd dat berichten die als spam zijn gemarkeerd, worden verzonden naar de map Ongewenste e-mail van de geadresseerde. In hybride omgevingen waarin EOP on-premises Exchange-postvakken beschermt, moet u echter twee regels voor de e-mailstroom configureren (ook wel transportregels genoemd) in uw on-premises Exchange-organisatie om de EOP-spamkoppen te herkennen die aan berichten worden toegevoegd. Zie [EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](/exchange/standalone-eop/configure-eop-spam-protection-hybrid) voor meer informatie. 

- **Uitgaande spamfilters:** EOP controleert ook of uw gebruikers geen spam verzenden, in uitgaande berichtinhoud of door de limieten voor uitgaande berichten te overschrijden. Zie Uitgaande [spamfilters](configure-the-outbound-spam-policy.md)configureren in Microsoft 365.

- **Spoof intelligence**: Zie Bescherming tegen [spoofing in EOP](anti-spoofing-protection.md)voor meer informatie.

## <a name="manage-errors-in-spam-filtering"></a>Fouten in spamfilters beheren

Het is mogelijk dat goede berichten kunnen worden geïdentificeerd als spam (ook wel false positives genoemd) of dat spam kan worden bezorgd in het Postvak IN. U kunt de suggesties in de volgende secties gebruiken om erachter te komen wat er is gebeurd en om te voorkomen dat dit in de toekomst gebeurt.

Hier volgen enkele best practices die van toepassing zijn op beide scenario's:

- Verzend altijd verkeerd geclassificeerde berichten naar Microsoft. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

- **Bekijk de kopteksten van** het antispambericht: deze waarden geven aan waarom een bericht is gemarkeerd als spam of waarom spamfilters zijn overgeslagen. Zie Kopteksten [van antispamberichten voor meer informatie.](anti-spam-message-headers.md)

- **Wijs uw MX-record** aan Microsoft 365: om ervoor te zorgen dat EOP de beste beveiliging biedt, wordt u altijd aangeraden om eerst e-mail aan uw Microsoft 365 leveren. Zie [DNS-records maken bij een DNS-hostingprovider](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)voor meer Microsoft 365.

  Als de MX-record naar een andere locatie wijst (bijvoorbeeld een antispamoplossing of -apparaat van derden), is het moeilijk voor EOP om nauwkeurige spamfilters te bieden. In dit scenario moet u Enhanced Filtering configureren voor verbindingslijnen (ook wel _skip listing genoemd)._ Zie [Enhanced Filtering for Connectors in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- **E-mailverificatie** gebruiken: als u eigenaar bent van een e-maildomein, kunt u DNS gebruiken om ervoor te zorgen dat berichten van afzenders in dat domein legitiem zijn. Gebruik alle volgende methoden voor e-mailverificatie om spam en ongewenste spoofing in EOP te voorkomen:

  - **SPF:** Sender Policy Framework verifieert het bron-IP-adres van het bericht tegen de eigenaar van het verzendende domein. Zie SPF instellen om spoofing te voorkomen voor een snelle inleiding tot SPF en om deze snel te [configureren.](set-up-spf-in-office-365-to-help-prevent-spoofing.md) Voor een beter begrip van hoe Microsoft 365 gebruikmaakt van SPF of voor het oplossen van problemen of niet-standaardimplementaties zoals hybride implementaties, begint u met [Hoe Microsoft 365 gebruikmaakt van SPF (Sender Policy Framework) om spoofing te voorkomen](how-office-365-uses-spf-to-prevent-spoofing.md).

  - **DKIM:** DomainKeys Identified Mail voegt een digitale handtekening toe aan de berichtkop van berichten die vanuit uw domein zijn verzonden. Zie [DKIM gebruiken om uitgaande](use-dkim-to-validate-outbound-email.md)e-mail te valideren die is verzonden vanuit uw aangepaste domein in Microsoft 365.

  - **DMARC:** Op domein gebaseerde berichtverificatie, rapportage en conformatie helpt doel-e-mailsystemen te bepalen wat te doen met berichten die niet worden gecontroleerd door SPF of DKIM en biedt een ander niveau van vertrouwen voor uw e-mailpartners. Zie [DMARC gebruiken om e-mail te valideren in](use-dmarc-to-validate-email.md)Microsoft 365.

- **Controleer de instellingen voor** bulksgewijs e-mail: de drempelwaarde voor bulkklachten (BCL) die u configureert in antispambeleid, bepaalt of bulk-e-mail (ook wel grijze e-mail _genoemd)_ is gemarkeerd als spam. De instelling Alleen-PowerShell _MarkAsSpamBulkMail_ die standaard is ingeschakeld, draagt ook bij aan de resultaten. Zie [Antispambeleid configureren in](configure-your-spam-filter-policies.md)Microsoft 365.

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Voorkomen dat spam wordt bezorgd in het Postvak IN

- **Uw organisatie-instellingen** controleren: Let op instellingen waarmee berichten spamfilters kunnen overslaan (bijvoorbeeld als u uw eigen domein toevoegt aan de lijst met toegestane domeinen in antispambeleid). Zie Aanbevolen instellingen voor [EOP](recommended-settings-for-eop-and-office365.md) en Microsoft Defender voor Office 365 beveiliging en Lijsten met veilige [afzenders maken](create-safe-sender-lists-in-office-365.md)voor onze aanbevolen instellingen.

- **Controleer** of de regel voor ongewenste e-mail is ingeschakeld in het postvak van de gebruiker: Deze is standaard ingeschakeld, maar als deze is uitgeschakeld, kunnen berichten die als ongewenste e-mail zijn gemarkeerd, niet worden verplaatst naar de map Ongewenste e-mail. Zie Instellingen voor ongewenste e-mail configureren op [Exchange Online postvakken in](configure-junk-email-settings-on-exo-mailboxes.md)Microsoft 365.

- **Gebruik de beschikbare lijsten met geblokkeerde afzenders**: Zie Lijsten met geblokkeerde afzenders maken voor [meer informatie.](create-block-sender-lists-in-office-365.md)

- **Afmelden voor bulk-e-mail** Als het bericht iets is waar de gebruiker zich voor heeft aangemeld (nieuwsbrieven, productaankondigingen, enzovoort) en een afmeldkoppeling van een betrouwbare bron bevat, kunt u hen vragen zich gewoon af te melden.

- Zelfstandige EOP: maak regels voor **e-mailstroom in on-premises Exchange voor EOP-spamfilters:** In EOP-omgevingen waarin EOP on-premises Exchange-postvakken beschermt, moet u regels voor e-mailstroom (ook wel transportregels genoemd) configureren in on-premises Exchange om de EOP-spamfilteringsregel te vertalen, zodat de regel voor ongewenste e-mail het bericht naar de map Ongewenste e-mail kan verplaatsen. Zie [EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](/exchange/standalone-eop/configure-eop-spam-protection-hybrid) voor meer informatie. 

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Voorkomen dat goede e-mail wordt geïdentificeerd als spam

Hier volgen enkele stappen die u kunt nemen om fout-positieven te voorkomen:

- **Controleer de instellingen van Outlook filter voor ongewenste e-mail:**

  - Controleer of **het Outlook** filter voor ongewenste e-mail is uitgeschakeld: Wanneer het Outlook Filter voor ongewenste e-mail is ingesteld op de standaardwaarde Geen automatische **filtering,** probeert Outlook geen masseers te classificeren als spam.  Wanneer het filter is ingesteld op **Laag** of **Hoog,** gebruikt het Outlook Filter voor ongewenste e-mail zijn eigen SmartScreen-filtertechnologie om spam te identificeren en te verplaatsen naar de map Ongewenste e-mail, zodat u onwaar positieven kunt krijgen. Houd er rekening mee dat Microsoft in november 2016 is gestopt met het produceren van spamdefinitie-updates voor de SmartScreen-filters in Exchange en Outlook in november 2016. De bestaande SmartScreen-spamdefinities zijn op hun plaats gebleven, maar de effectiviteit ervan zal waarschijnlijk na verloop van tijd verslechteren.

  - Controleer of **de instelling Outlook 'alleen Safe Lijsten' is** uitgeschakeld: wanneer deze instelling is ingeschakeld, worden alleen berichten van afzenders in de lijst met Safe afzenders of Safe Geadresseerden van de gebruiker bezorgd in het Postvak IN. e-mail van alle anderen wordt automatisch verplaatst naar de map Ongewenste e-mail.

  Zie Instellingen voor ongewenste e-mail configureren op Exchange Online [postvakken in](configure-junk-email-settings-on-exo-mailboxes.md)Microsoft 365.

- **Gebruik de beschikbare lijsten met veilige afzenders**: Zie Lijsten met veilige afzenders maken voor [meer informatie.](create-safe-sender-lists-in-office-365.md)

- **Controleer of gebruikers zich binnen de limieten** voor verzenden en ontvangen houden, zoals beschreven in [Ontvangst-](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) en Exchange Online servicebeschrijving.

- **Zelfstandige EOP:** gebruik adreslijstsynchronisatie: als u zelfstandige EOP gebruikt om uw on-premises Exchange-organisatie te beschermen, moet u gebruikersinstellingen synchroniseren met de service met behulp van adreslijstsynchronisatie. Als u dit doet, worden de lijsten Safe afzenders van uw gebruikers door EOP gerespecteerd. Zie Adreslijstsynchronisatie gebruiken om [e-mailgebruikers te beheren voor meer informatie.](/exchange/standalone-eop/manage-mail-users-in-eop#synchronize-directories-with-azure-active-directory-connect-aad-connect)

## <a name="anti-spam-legislation"></a>Antispamwetgeving

Bij Microsoft zijn we van mening dat voor de ontwikkeling van nieuwe technologieën en zelfregulering effectieve overheidsbeleid en juridische kaders moeten worden ondersteund. De wereldwijde verspreiding van spam heeft tal van wetgevingsinstanties aangespoord om commerciële e-mail te reguleren. Veel landen hebben nu wetten voor spambestrijding. De Verenigde Staten hebben zowel federale als staatswetten die betrekking hebben op spam. Deze complementaire benadering helpt spam te beperken en tegelijkertijd legitieme e-commerce te laten slagen. De CAN-SPAM Act breidt de beschikbare hulpmiddelen uit voor het tegen gaan van frauduleuze en misleidende e-mailberichten.