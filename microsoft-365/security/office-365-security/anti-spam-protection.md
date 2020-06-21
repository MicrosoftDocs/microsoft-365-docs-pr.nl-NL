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
description: Beheerders kunnen meer te weten komen over de antispaminstellingen en -filters die spam helpen voorkomen in Exchange Online Protection (EOP).
ms.openlocfilehash: ce673a4bee64dfbc84f870f9cf4871e9ac32a71c
ms.sourcegitcommit: 89636f35b0194986f156302fc1bb96af25d4805b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/18/2020
ms.locfileid: "44800105"
---
# <a name="anti-spam-protection-in-eop"></a>Antispambeveiliging in EOP

> [!NOTE]
> Dit onderwerp is bedoeld voor beheerders. Zie [Overzicht van het filter ongewenste e-mail](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) en meer informatie over ongewenste [e-mail en phishing voor](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31)onderwerpen van eindgebruikers.

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken worden e-mailberichten automatisch beveiligd tegen spam (ongewenste e-mail) door EOP.

De e-mailveiligheidsroadmap van Microsoft omvat een ongeëvenaarde cross-productbenadering. EOP anti-spam en anti-phishing technologie wordt toegepast op onze e-mailplatforms om gebruikers te voorzien van de nieuwste anti-spam en anti-phishing tools en innovaties in het hele netwerk. Het doel van EOP is om een uitgebreide en bruikbare e-mailservice aan te bieden die gebruikers helpt bij het detecteren en beschermen van ongewenste e-mail, frauduleuze e-mailbedreigingen (phishing) en malware.

Als e-mail gebruik is gegroeid, zo heeft e-mail misbruik. Ongecontroleerde ongewenste e-mail kan inboxen en netwerken verstoppen, de tevredenheid van gebruikers beïnvloeden en de effectiviteit van legitieme e-mailcommunicatie belemmeren. Daarom blijft Microsoft investeren in antispamtechnologieën. Simpel gezegd, het begint met het bevatten en filteren van ongewenste e-mail.

## <a name="anti-spam-technologies-in-eop"></a>Anti-spam technologieën in EOP

Om ongewenste e-mail te verminderen, bevat EOP bescherming tegen ongewenste e-mail die gebruik maakt van gepatenteerde technologieën voor het filteren van spam om ongewenste e-mail te identificeren en te scheiden van legitieme e-mail. EOP spam filtering leert van bekende spam en phishing bedreigingen en feedback van gebruikers van ons consumentenplatform, Outlook.com. Voortdurende feedback van EOP-gebruikers in het classificatieprogramma voor ongewenste e-mail helpt ervoor te zorgen dat de EOP-technologieën voortdurend worden getraind en verbeterd.

De anti-spam instellingen in EOP zijn gemaakt van de volgende technologieën:

- **Verbindingsfiltering**: Identificeert goede en slechte e-mailbronservers in het begin van de binnenkomende e-mailverbinding via de IP Allow List, IP-blokkerlijst en de *veilige lijst* (een dynamische maar niet-bewerkbare lijst met vertrouwde afzenders die door Microsoft worden onderhouden). U configureert deze instellingen in het verbindingsfilterbeleid. Meer informatie bij [Verbindingsfiltering configureren.](configure-the-connection-filter-policy.md)

  > [!NOTE]
  > Spoofintelligentie maakt gebruik van verbindingsfiltering om lijsten van afzenders die uw e-maildomein spoofen, te maken en te blokkeren. Zie Meer informatie [over spoofinformatie in Microsoft 365](learn-about-spoof-intelligence.md)voor meer informatie.

- **Spam filteren (content filtering)**: EOP maakt gebruik van de spam filteren vonnissen **Spam**, **High confidence spam**, Bulk **e-mail,** **Phishing e-mail** en **High confidence phishing e-mail** om berichten te classificeren. U de acties configureren die u moet uitvoeren op basis van deze vonnissen en u de meldingsopties voor eindgebruikers configureren voor berichten die in quarantaine zijn geplaatst in plaats van geleverd. Zie [Antispambeleid configureren in Microsoft 365](configure-your-spam-filter-policies.md)voor meer informatie.

  > [!NOTE]
  > Spamfilters zijn standaard geconfigureerd om berichten die zijn gemarkeerd als spam naar de map Ongewenste e-mail van de ontvanger te verzenden. In hybride omgevingen waarin EOP on-premises Exchange-postvakken beschermt, moet u echter twee regels voor e-mailstroom (ook wel transportregels genoemd) configureren in uw on-premises Exchange-organisatie om de EOP-spamkoppen te herkennen die aan berichten zijn toegevoegd. Zie [Standalone EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) voor meer informatie. 

- **Uitgaande spamfiltering**: EOP controleert ook of uw gebruikers geen spam verzenden, hetzij in uitgaande berichtinhoud, hetzij door de limieten voor uitgaande berichten te overschrijden. Zie [Uitgaande spamfiltering configureren in Microsoft 365](configure-the-outbound-spam-policy.md)voor meer informatie.

- **Spoofinformatie**: Zie [Meer informatie over spoofinformatie in Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="manage-errors-in-spam-filtering"></a>Fouten in spamfiltering beheren

Het is mogelijk dat goede berichten kunnen worden geïdentificeerd als spam (ook wel false positives genoemd), of dat spam kan worden bezorgd in de Postvak IN. U de suggesties in de volgende secties gebruiken om erachter te komen wat er is gebeurd en te helpen voorkomen dat dit in de toekomst gebeurt.

Hier volgen enkele aanbevolen procedures die van toepassing zijn op beide scenario's:

- Verzend altijd verkeerd geclassificeerde berichten bij Microsoft. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

- **Onderzoek de anti-spam bericht headers**: Deze waarden vertellen u waarom een bericht is gemarkeerd als spam, of waarom het spam filtering overgeslagen. Zie [Antispamberichtenkoppen](anti-spam-message-headers.md)voor meer informatie.

- **Richt uw MX-record aan Microsoft 365**: Om eOP de beste bescherming te bieden, raden we u altijd aan om eerst e-mail aan Microsoft 365 te laten bezorgen. Zie [DNS-records maken bij een DNS-hostingprovider voor Microsoft 365 voor](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)instructies.

  Als de MX-record naar een andere locatie verwijst (bijvoorbeeld een antispamoplossing of toestel van derden), is het voor EOP moeilijk om nauwkeurige spamfiltering te bieden. In dit scenario moet u Uitgebreide filtering configureren voor connectoren (ook wel _aanbieding overslaan_genoemd). Zie Uitgebreide [filtering voor connectoren in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)voor instructies.

- **E-mailverificatie gebruiken:** als u eigenaar bent van een e-maildomein, u DNS gebruiken om ervoor te zorgen dat berichten van afzenders in dat domein legitiem zijn. Gebruik alle volgende e-mailverificatiemethoden om spam en ongewenste spoofing in EOP te voorkomen:

  - **SPF**: Sender Policy Framework verifieert het bron-IP-adres van het bericht aan de eigenaar van het verzendende domein. Zie SPF instellen om [spoofing te voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md)voor een snelle introductie tot SPF en om deze snel te configureren. Voor een beter begrip van hoe Microsoft 365 gebruikmaakt van SPF of voor het oplossen van problemen of niet-standaardimplementaties zoals hybride implementaties, begint u met [Hoe Microsoft 365 gebruikmaakt van SPF (Sender Policy Framework) om spoofing te voorkomen](how-office-365-uses-spf-to-prevent-spoofing.md).

  - **DKIM**: DomainKeys Identified Mail voegt een digitale handtekening toe aan de berichtkop van berichten die vanuit uw domein worden verzonden. Zie [DKIM gebruiken om uitgaande e-mail die vanuit uw aangepaste domein in Microsoft 365 is verzonden, te valideren](use-dkim-to-validate-outbound-email.md)voor informatie.

  - **DMARC:** op domein gebaseerde berichtverificatie, rapportage en conformiteit helpt doele-mailsystemen te bepalen wat te doen met berichten die niet voldoen aan SPF- of DKIM-controles en biedt een ander niveau van vertrouwen voor uw e-mailpartners. Zie [DMARC gebruiken om e-mail te valideren in Microsoft 365 voor](use-dmarc-to-validate-email.md)meer informatie.

- **Uw bulke-mailinstellingen verifiëren:** De bcl-drempel (bulk compliant level) die u configureert in antispambeleid, bepaalt of bulke-mail (ook wel _grijze e-mail_genoemd) is gemarkeerd als spam. De PowerShell-instelling _MarkAsSpamBulkMail_ die standaard is ingeschakeld, draagt ook bij aan de resultaten. Zie [Antispambeleid configureren in Microsoft 365](configure-your-spam-filter-policies.md)voor meer informatie.

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Voorkom de levering van spam in het Postvak IN

- **Uw organisatie-instellingen verifiëren:** Let op instellingen waarmee berichten spamfilters kunnen overslaan (bijvoorbeeld als u uw eigen domein toevoegt aan de lijst met toegestane domeinen in antispambeleid). Zie [Aanbevolen instellingen voor EOP- en Office 365 ATP-beveiliging en](recommended-settings-for-eop-and-office365-atp.md) Veilige afzenderlijsten maken voor aanbevolen [instellingen.](create-safe-sender-lists-in-office-365.md)

- **Controleer of de regel voor ongewenste e-mail is ingeschakeld in het postvak van de gebruiker:** deze is standaard ingeschakeld, maar als deze is uitgeschakeld, kunnen berichten die als ongewenste e-mail zijn gemarkeerd, niet worden verplaatst naar de map Ongewenste e-mail. Zie [Instellingen voor ongewenste e-mail configureren in Exchange Online-postvakken configureren in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie.

- **Gebruik de beschikbare lijsten met geblokkeerde afzenders**: Zie [Lijsten met geblokkeerde afzenders maken](create-block-sender-lists-in-office-365.md)voor informatie.

- **Afmelden voor bulke-mail** Als het bericht iets was waarvoor de gebruiker zich heeft aangemeld (nieuwsbrieven, productaankondigingen, enz.) en een afmeldlink bevat van een betrouwbare bron, u vragen om zich gewoon af te melden.

- **Standalone EOP: maak regels voor e-mailstroom in on-premises Exchange for EOP-spamfiltervonnten:** In standalone EOP-omgevingen waar EOP on-premises Exchange-postvakken beschermt, moet u regels voor e-mailstroom (ook wel transportregels genoemd) configureren in on-premises Exchange om het EOP-spamfilteringsoordeel te vertalen, zodat de regel voor ongewenste e-mail het bericht naar de map Ongewenste e-mail kan verplaatsen. Zie [Standalone EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) voor meer informatie. 

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Voorkomen dat goede e-mail wordt geïdentificeerd als spam

Hier volgen enkele stappen die u nemen om fout-positieven te voorkomen:

- **Controleer de instellingen van het Outlook-filter voor ongewenste e-mail van de gebruiker:**

  - **Controleer of het filter voor ongewenste e-mail van Outlook is uitgeschakeld:** Wanneer het filter voor ongewenste e-mail van Outlook is ingesteld op de standaardwaarde **Geen automatische filtering,** probeert Outlook massages niet als spam te classificeren.  Wanneer het is ingesteld **op Laag** of **Hoog,** gebruikt het Filter voor ongewenste e-mail van Outlook zijn eigen SmartScreen-filtertechnologie om spam te identificeren en te verplaatsen naar de map Ongewenste e-mail, zodat u fout-positieven krijgen. Houd er rekening mee dat Microsoft in november 2016 is gestopt met het produceren van spamdefinitie-updates voor de SmartScreen-filters in Exchange en Outlook. De bestaande SmartScreen spam definities werden achtergelaten op zijn plaats, maar hun effectiviteit zal waarschijnlijk degraderen na verloop van tijd.

  - **Controleer of de instelling 'Alleen veilige lijsten' van Outlook is uitgeschakeld:** Wanneer deze instelling is ingeschakeld, worden alleen berichten van afzenders in de lijst Veilige afzenders of Veilige geadresseerden naar het Postvak IN bezorgd. e-mail van alle anderen wordt automatisch verplaatst naar de map Ongewenste e-mail.

  Zie Instellingen voor ongewenste [e-mail configureren in Exchange Online-postvakken configureren in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie over deze instellingen.

- **Gebruik de beschikbare lijsten met veilige afzenders**: Zie [Veilige afzenderlijsten maken](create-safe-sender-lists-in-office-365.md)voor informatie.

- **Controleer of gebruikers zich binnen de verzend- en ontvangstlimieten bevinden** zoals beschreven in [Het ontvangen en verzenden van limieten](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) in de beschrijving van de Exchange Online-service.

- **Standalone EOP: gebruik directorysynchronisatie**: Als u standalone EOP gebruikt om uw on-premises Exchange-organisatie te beschermen, moet u gebruikersinstellingen synchroniseren met de service met behulp van adreslijstsynchronisatie. Dit zorgt ervoor dat de Safe Senders-lijsten van uw gebruikers worden gerespecteerd door EOP. Zie [Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren voor](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users)meer informatie.

## <a name="anti-spam-legislation"></a>Antispamwetgeving

Bij Microsoft zijn we van mening dat de ontwikkeling van nieuwe technologieën en zelfregulering de ondersteuning vereist van effectief overheidsbeleid en juridische kaders. De wereldwijde verspreiding van spam heeft talrijke wetgevende instanties aangespoord om commerciële e-mail te reguleren. Veel landen hebben nu spam-gevechten wetten in de plaats. De Verenigde Staten heeft zowel federale als staatswetten die spam regelen, en deze aanvullende aanpak helpt om spam te beperken terwijl het mogelijk maken van legitieme e-commerce om te gedijen. De CAN-SPAM Act breidt de beschikbare tools uit voor het beteugelen van frauduleuze en misleidende e-mailberichten.
