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
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie krijgen over de antispam instellingen en filters waarmee u spam in Exchange Online Protection (EOP) kunt voorkomen.
ms.openlocfilehash: 7456ef4de9f887a1782df714f6e454efa213ddec
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445745"
---
# <a name="anti-spam-protection-in-eop"></a>Bescherming tegen ongewenste e-mail in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Dit onderwerp is bedoeld voor beheerders. Zie [overzicht van het filter voor ongewenste e-mail](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) en [Lees meer over ongewenste e-mail en phishing](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31)voor de functies voor eindgebruikers.

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder postvakken van Exchange Online worden e-mailberichten automatisch beveiligd tegen ongewenste e-mail (ongewenste e-mail) door EOP.

Het Microsoft-e-mail schema voor e-mail beveiliging omvat een niet-gerelateerde aanpak van cross-product. EOP anti-spam en tegen phishing-technologie wordt in onze e-mail platforms toegepast om gebruikers de nieuwste anti-spam en anti-spamprogramma's en innovaties in het netwerk te verschaffen. Het doel voor EOP is een uitgebreide en nuttige e-mail service die helpt bij het detecteren en beschermen van gebruikers tegen ongewenste e-mail, frauduleuze e-mail bedreigingen en malware.

Omdat e-mail gebruik is geteeld, heeft dit tot e-mail misbruik. Ongemonitorde ongewenste e-mail kan dicht slibbene postvakken en netwerken, impact gebruikers tevredenheid en de effectiviteit van legitieme e-mail communicatie belemmeren. Daarom gaat Microsoft verder met investeringen in antispam technologieën. U hoeft niets te doen om ongewenste e-mail te bevatten en te filteren.

> [!TIP]
> De volgende antispam technologieën zijn handig wanneer u berichten wilt toestaan of blokkeren op basis van de envelop van het bericht (bijvoorbeeld het domein van de afzender of het bron-IP-adres van het bericht). Als u berichten wilt toestaan of blokkeren op basis van nettolading (bijvoorbeeld Url's in het e-mailbericht of de bijgevoegde bestanden), moet u de portal voor het [weergeven en blokkeren](tenant-allow-block-list.md)van de Tenant gebruiken.

## <a name="anti-spam-technologies-in-eop"></a>Anti spam technologieën in EOP

Om ongewenste e-mail te helpen verminderen, biedt EOP de bescherming tegen ongewenste e-mail die gebruikmaken van technologieën voor het filteren van ongewenste e-mail en ongewenste e-mail van legitieme e-mail identificeren en scheiden. EOP spamfilters leren van bekende spam-en fraude bedreigingen en feedback van gebruikers van ons consumenten platform, Outlook.com. Voortdurende feedback van EOP-gebruikers in het classificatie programma voor ongewenste e-mail helpt ervoor te zorgen dat de EOP Technologies continu wordt opgeleid en verbeterd.

De antispam instellingen in EOP worden gemaakt van de volgende technologieën:

- **Filters voor verbindingen**: identificeert goede en onjuiste e-bronservers in de inkomende e-mail verbinding via de lijst IP toestaan, de lijst met IP-adreslijsten en de *lijst veilig* (een dynamische maar niet-bewerkbare lijst met vertrouwde afzenders die door Microsoft worden beheerd). U configureert deze instellingen in het filter beleid voor verbindingen. Meer informatie vindt [u in het filteren van verbindingen configureren](configure-the-connection-filter-policy.md).

  > [!NOTE]
  > Met behulp van spoof Intelligence wordt gebruikgemaakt van filters om lijsten met afzenders te maken en te blokkeren die uw e-mail domein spoofen. Zie voor meer informatie [meer informatie over spoof Intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

- **Spam filteren (inhoud filteren)**: EOP maakt gebruik van spamfilters Verdicts **spam**, **hoge betrouwbaarheid van spam**, **bulk e-mail**, **phishing-** e-mail en **e-mailen van hoge betrouwbaarheid** voor het classificeren van berichten. U kunt configureren welke acties worden uitgevoerd op basis van deze Verdicts en u kunt de Meldingsopties voor de eindgebruikers configureren voor berichten die zijn gequarantined in plaats van afgeleverd. Zie [Antispambeleid in Microsoft 365 configureren](configure-your-spam-filter-policies.md)voor meer informatie.

  > [!NOTE]
  > Filters voor spam filteren is standaard geconfigureerd voor het verzenden van berichten die als spam zijn gemarkeerd in de map Ongewenste E-mail van de geadresseerde. In hybride omgevingen waarbij EOP on-premises Exchange-postvakken beschermt, moet u twee e-mail stroom regels (ook wel wel transport regels genoemd) configureren in uw on-premises Exchange-organisatie om de EOP spam koppen die aan berichten worden toegevoegd te herkennen. Zie [Standalone EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) voor meer informatie. 

- **Uitgaande spam filteren**: met EOP wordt ook gecontroleerd of uw gebruikers geen spam verzenden, noch bij inhoud van uitgaande berichten of door overschrijden van uitgaande berichten. Zie voor meer informatie [filters voor uitgaande spam filteren in Microsoft 365](configure-the-outbound-spam-policy.md).

- **Spoof informatie**: Zie voor meer informatie meer informatie [over spoof Intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="manage-errors-in-spam-filtering"></a>Fouten in filters voor ongewenste e-mail beheren

U kunt goede berichten ook identificeren als spam (ook wel foutberichten genoemd), of u kunt de spam afleveren in het postvak in. U kunt de suggesties in de volgende secties gebruiken om erachter te komen wat er is gebeurd en om te voorkomen dat dit in de toekomst gebeurt.

Hier volgen enkele aanbevolen procedures die van toepassing zijn op een scenario:

- E-mail altijd verkeerd geclassificeerd indienen bij Microsoft. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

- **De kop-en voettekst van het antispam bericht bekijken**: deze waarden geven aan waarom een bericht is gemarkeerd als spam of waarom het filteren op ongewenste e-mail is genegeerd. Zie [anti spambericht koppen](anti-spam-message-headers.md)voor meer informatie.

- **Schrijf uw MX-record naar Microsoft 365**: om eop de beste beveiliging te bieden, raden we u aan dat u eerst e-mail ontvangt op microsoft 365. Voor instructies raadpleegt u [DNS-records maken bij een DNS-hosting provider voor Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

  Als de MX-record verwijst naar een andere locatie (bijvoorbeeld een oplossing of toestel van een derde antispam), is het moeilijk voor EOP de juiste spamfilters te geven. In dit scenario moet u verbeterde filters configureren voor verbindingslijnen (ook wel vermelding van de _vermelding overslaan_). Zie voor meer informatie het artikel [uitgebreid filteren op connectors in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- **E-mail authenticatie gebruiken**: als u eigenaar bent van een e-mail domein, kunt u DNS gebruiken om te controleren of berichten van afzenders in dat domein geldig zijn. Gebruik alle volgende verificatiemethoden voor e-mail om spam en ongewenste spoofing te helpen voorkomen in EOP:

  - **SPF**: Sender Policy Framework verifieert het bron-IP-adres van het bericht ten opzichte van de eigenaar van het verzendende domein. Zie [SPF instellen om spoofing te helpen voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md)dat u snel aan de slag kunt. Voor een beter begrip van hoe Microsoft 365 gebruikmaakt van SPF of voor het oplossen van problemen of niet-standaardimplementaties zoals hybride implementaties, begint u met [Hoe Microsoft 365 gebruikmaakt van SPF (Sender Policy Framework) om spoofing te voorkomen](how-office-365-uses-spf-to-prevent-spoofing.md).

  - Met **dkim**: DomainKeys geïdentificeerde e-mail wordt een digitale handtekening toegevoegd aan de berichtkop met berichten die vanuit uw domein zijn verzonden. Zie voor meer informatie [dkim gebruiken voor het valideren van uitgaande e-mail verzonden vanaf uw aangepaste domein in Microsoft 365](use-dkim-to-validate-outbound-email.md).

  - **DMARC**: verificatie op domeinbasis, rapportage en conformiteit helpt doele e-mail systemen om te bepalen wat er gebeurt met berichten die niet kunnen worden afgehandeld en niet kunnen worden gecontroleerd en een extra vertrouwensniveau voor uw e-mail partners biedt. Zie voor meer informatie [DMARC gebruiken om e-mail te valideren in Microsoft 365](use-dmarc-to-validate-email.md).

- **Controleer uw instellingen voor bulk-e-mail**: de drempelwaarde voor bulk compliant niveau (BCL) die u configureert in Antispambeleid bepaalt of de bulk-e-mail (ook wel _grijze e-mail_genoemd) is gemarkeerd als spam. De instelling _MarkAsSpamBulkMail_ alleen voor PowerShell-instellingen die standaard is ingeschakeld, draagt ook bij aan de resultaten. Zie [Antispambeleid in Microsoft 365 configureren](configure-your-spam-filter-policies.md)voor meer informatie.

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Voorkomen dat spam wordt bezorgd in het postvak in

- **Controleer uw organisatie-instellingen**: Bekijk de instellingen waarmee berichten worden gefilterd met beondersteuning van spamfilters (als u bijvoorbeeld uw eigen domein toevoegt aan de lijst met toegestane domeinen in Antispambeleid). Zie [Aanbevolen instellingen voor EOP en Office 365 ATP-beveiliging](recommended-settings-for-eop-and-office365-atp.md) voor de aanbevolen instellingen en [Maak lijsten met veilige afzenders](create-safe-sender-lists-in-office-365.md).

- **Controleer of de regel voor ongewenste e-mail is ingeschakeld in het postvak van de gebruiker**: deze functie is standaard ingeschakeld, maar als deze functie is uitgeschakeld, kunnen berichten die als ongewenste e-mail zijn gemarkeerd, niet worden verplaatst naar de map Ongewenste e-mail. Zie voor meer informatie [instellingen voor ongewenste E-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **De lijst beschikbare geblokkeerde afzenders gebruiken**: Zie [lijsten met geblokkeerde afzenders maken](create-block-sender-lists-in-office-365.md)voor informatie.

- **Afmelden voor bulkmail** Als het bericht een bericht bevat dat de gebruiker zich heeft geregistreerd voor nieuwsbrieven, product mededelingen, enzovoort, en een koppeling voor afmelden van een betrouwbare bron bevat, kunt u het beste een abonnement opzeggen.

- **STANDALONE EOP: e-mail stroom regels maken in on-premises Exchange voor EOP spam filteren Verdicts**: in een zelfstandige EOP omgevingen waarbij EOP on-premises Exchange-postvakken wordt beschermd, moet u de e-mail stroom regels (ook wel de waarden voor de transportregels) in on-premises Exchange configureren om het bericht te converteren naar de map Ongewenste e-mail. Zie [Standalone EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) voor meer informatie. 

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Voorkomen dat goede e-mail wordt geïdentificeerd als spam

Hier volgen enkele stappen die u kunt ondernemen om fout-positieven te voorkomen:

- **Controleer de instellingen voor het filter voor ongewenste e-mail van de gebruiker**:

  - **Controleer of het filter voor ongewenste e-mail van Outlook is uitgeschakeld**: wanneer het filter voor ongewenste E-mail van Outlook is ingesteld op de standaardwaarde **geen automatische filtering**, wordt niet geprobeerd massageenen als spam te classificeren.  Wanneer de instelling is ingesteld **op** **hoog of hoog**, gebruikt het filter voor ongewenste e-mail van Outlook de eigen versie van het filter voor ongewenste e-mail om ongewenste e-mail te identificeren en te verplaatsen naar de map Ongewenste e-mail, zodat u foutberichten kunt ontvangen. Houd er rekening mee dat Microsoft de updates voor definities van spam definities voor de SmartScreen-filters in Exchange en Outlook in november 2016 heeft stopgezet. De bestaande definities voor de SmartScreen-spam werden weggegaan, maar de effectiviteit ervan is waarschijnlijk slecht.

  - **Controleer of de instelling alleen veilige lijsten van Outlook is uitgeschakeld**: wanneer deze instelling is ingeschakeld, worden alleen de berichten van afzenders in de lijst met veilige afzenders van de gebruiker of de lijst met veilige geadresseerden bezorgd in het postvak in. e-mail van alle andere personen wordt automatisch verplaatst naar de map Ongewenste E-mail.

  Zie voor meer informatie over deze instellingen de [instellingen voor ongewenste E-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Gebruik de beschikbare lijsten met veilige afzenders**: Zie [lijsten met veilige afzenders maken](create-safe-sender-lists-in-office-365.md)voor meer informatie.

- **Controleer of gebruikers zich bevinden binnen de limieten voor verzenden en ontvangen** , zoals wordt beschreven in [limieten voor het ontvangen en verzenden](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) van de servicebeschrijving van Exchange Online.

- **Zelfstandige EOP: synchronisatie van adreslijsten gebruiken**: als u zelfstandige EOP gebruikt om uw on-premises Exchange-organisatie te beschermen, moet u gebruikersinstellingen synchroniseren met de service via adreslijstsynchronisatie. Dit zorgt ervoor dat de lijsten met veilige afzenders van uw gebruikers worden geëerbiedigd door EOP. Zie voor meer informatie [adreslijstsynchronisatie gebruiken voor het beheren van e-mail gebruikers](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users).

## <a name="anti-spam-legislation"></a>Anti spam wetgeving

Microsoft vermoedt dat het voor de ontwikkeling van nieuwe technologieën en de zelfregulering de ondersteuning van de overheids beleidsregels en juridische kaders moet ondersteunen. De wereldwijde spam proliferatie heeft Spurred talrijke wetgevings organen om commerciële e-mail te reguleren. In veel landen is nu antispam gevechts wetten ter plaatse gehouden. De Verenigde Staten hebben zowel nationale als regionale wetten voor spam, en deze complementaire aanpak helpt bij het aanwijzen van spam bij het inschakelen van legitieme e-commerce voor Prosper. Met de CAN-SPAM Act worden de hulpmiddelen uitgebreid voor het doorvoeren van frauduleuze en misleidende e-mailberichten.
