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
description: Beheerders kunnen meer informatie krijgen over de antispaminstellingen en -filters die spam helpen voorkomen in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ae2c4f42d42c37f5b7a7df2b6c8306fd390b0af
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175857"
---
# <a name="anti-spam-protection-in-eop"></a>Bescherming tegen ongewenste e-mail in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!NOTE]
> Dit onderwerp is bedoeld voor beheerders. Zie Overview of the [Junk Email Filter and](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) Learn about junk email and phishing (Overzicht van het filter voor ongewenste e-mail en over ongewenste e-mail en phishing) voor onderwerpen voor [eindgebruikers.](https://support.microsoft.com/office/86c1d76f-4d5a-4967-9647-35665dc17c31)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken worden e-mailberichten automatisch beveiligd tegen spam (ongewenste e-mail) door EOP.

De routekaart voor e-mailveiligheid van Microsoft omvat een niet-overeenkomende benadering voor productoverschrijdende producten. EOP antispam- en anti-phishingtechnologie wordt toegepast op onze e-mailplatforms om gebruikers de nieuwste antispam- en anti-phishinghulpprogramma's en innovaties in het hele netwerk te bieden. EOP heeft als doel een uitgebreide en gebruiksbare e-mailservice aan te bieden waarmee gebruikers worden gedetecteerd en beschermd tegen ongewenste e-mail, frauduleuze e-mailbedreigingen (phishing) en malware.

Naarmate het gebruik van e-mail groter wordt, wordt ook misbruik van e-mail voorkomen. Ongemonitorde ongewenste e-mail kan postvak IN en netwerken in de gaten houden, tevredenheid van gebruikers beïnvloeden en de effectiviteit van legitieme communicatie via e-mail beperken. Daarom blijft Microsoft investeren in antispamtechnologieën. Eenvoudig gezegd begint het met het in- en filteren van ongewenste e-mail.

> [!TIP]
> De volgende antispamtechnologieën zijn nuttig wanneer u berichten wilt toestaan of blokkeren op basis van de berichtenvelop (bijvoorbeeld het domein van de afzender of het BRON-IP-adres van het bericht). Als u berichten wilt toestaan of blokkeren op basis van nettolading (bijvoorbeeld URL's in het bericht of bijgevoegde bestanden), gebruikt u de portal Tenant [toestaan/Lijst blokkeren.](tenant-allow-block-list.md)

## <a name="anti-spam-technologies-in-eop"></a>Antispamtechnologieën in EOP

Om ongewenste e-mail te beperken, bevat EOP bescherming tegen ongewenste e-mail die gebruikmaakt van eigen spamfiltertechnologieën om ongewenste e-mail te identificeren en te scheiden van legitieme e-mail. EOP-spamfilters leren van bekende spam- en phishingbedreigingen en feedback van gebruikers van ons consumentenplatform, Outlook.com. Door continue feedback van EOP-gebruikers in het classificatieprogramma voor ongewenste e-mail zorgt u ervoor dat de EOP-technologieën voortdurend worden opgeleid en verbeterd.

De antispaminstellingen in EOP zijn gemaakt van de volgende technologieën:

- Verbindingsfiltering: identificeert begin van de binnenkomende e-mailverbinding goede en slechte e-mailbronservers via de lijst met toegestane IP-adressen, de lijst met IP-blokkeringen en de veilige lijst *(een* dynamische, maar niet-bewerkbare lijst met vertrouwde afzenders die door Microsoft worden onderhouden). U configureert deze instellingen in het verbindingsfilterbeleid. Meer informatie op [Verbindingsfilter configureren.](configure-the-connection-filter-policy.md)

  > [!NOTE]
  > Spoof intelligence maakt gebruik van verbindingsfilters om lijsten met toegestane en geblokkeerde afzenders te maken die uw e-maildomein vervalsen. Zie meer informatie over intelligence [voor adresvervalsing in Microsoft 365](learn-about-spoof-intelligence.md)voor meer informatie.

- **Spamfilters (inhoudsfilters)**: EOP gebruikt de spamfilters op **Spam,** Zeer vertrouwelijk **spam, bulk-e-mail,** Phishing-e-mail en zeer **betrouwbaarheidsmail voor phishing** om berichten te classificeren.  U kunt de acties configureren die moeten worden ondernomen op basis van deze instellingen en u kunt de meldingsopties voor eindgebruikers configureren voor berichten die in quarantaine zijn geplaatst in plaats van zijn bezorgd. Zie Antispambeleid configureren [in Microsoft 365](configure-your-spam-filter-policies.md)voor meer informatie.

  > [!NOTE]
  > Het spamfilter is standaard zo geconfigureerd dat berichten die zijn gemarkeerd als spam, worden verzonden naar de map Ongewenste e-mail van de geadresseerde. In hybride omgevingen waarin EOP on-premises Exchange-postvakken beschermt, moet u echter twee regels voor de e-mailstroom (ook wel transportregels genoemd) configureren in uw on-premises Exchange-organisatie om de EOP-spamkoppen te herkennen die aan berichten zijn toegevoegd. Zie [Standalone EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) voor meer informatie. 

- **Filteren van uitgaande spam:** EOP controleert ook of uw gebruikers geen spam verzenden, hetzij in uitgaande berichtinhoud ofwel door de limieten voor uitgaande berichten te overschrijden. Zie Uitgaande spamfilters configureren [in Microsoft 365](configure-the-outbound-spam-policy.md)voor meer informatie.

- **Spoof intelligence:** Zie meer informatie over intelligence voor [adresvervalsing in Microsoft 365 voor meer informatie.](learn-about-spoof-intelligence.md)

## <a name="manage-errors-in-spam-filtering"></a>Fouten in spamfilters beheren

Het is mogelijk dat goede berichten kunnen worden geïdentificeerd als spam (ook wel fout-positieven genoemd) of dat spam in het Postvak IN kan worden bezorgd. U kunt de suggesties in de volgende secties gebruiken om erachter te komen wat er is gebeurd en om te voorkomen dat dit in de toekomst gebeurt.

Hier volgen enkele best practices die van toepassing zijn op beide scenario's:

- Verzend altijd verkeerd geclassificeerde berichten naar Microsoft. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

- **Bekijk de berichtkoppen tegen ongewenste e-mail:** deze waarden geven aan waarom een bericht is gemarkeerd als spam of waarom het spamfilter is overgeslagen. Zie berichtkoppen tegen [ongewenste e-mail voor meer informatie.](anti-spam-message-headers.md)

- **Wijs uw MX-record op Microsoft 365:** om EOP de beste bescherming te bieden, wordt u altijd aangeraden eerst e-mail bij Microsoft 365 te laten bezorgen. Zie [DNS-records maken bij een DNS-hostingprovider voor Microsoft 365 voor instructies.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)

  Als de MX-record naar een andere locatie wijst (bijvoorbeeld een oplossing tegen ongewenste e-mail van derden of een apparaat), is het moeilijk voor EOP om nauwkeurige spamfilters te bieden. In dit scenario moet u Enhanced Filtering for connectors (ook wel _vermelding overslaan genoemd) configureren._ Zie [Enhanced Filtering for Connectors in Exchange Online voor instructies.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- **E-mailverificatie** gebruiken: als u de eigenaar bent van een e-maildomein, kunt u DNS gebruiken om ervoor te zorgen dat berichten van afzenders in dat domein legitiem zijn. Gebruik de volgende methoden voor e-mailverificatie om spam en ongewenste spoofing in EOP te voorkomen:

  - **SPF:** Sender Policy Framework verifieert het BRON-IP-adres van het bericht aan de eigenaar van het verzendende domein. Zie SPF instellen om spoofing te helpen voorkomen, voor een korte inleiding tot SPF en om het snel te [configureren.](set-up-spf-in-office-365-to-help-prevent-spoofing.md) Voor een beter begrip van hoe Microsoft 365 gebruikmaakt van SPF of voor het oplossen van problemen of niet-standaardimplementaties zoals hybride implementaties, begint u met [Hoe Microsoft 365 gebruikmaakt van SPF (Sender Policy Framework) om spoofing te voorkomen](how-office-365-uses-spf-to-prevent-spoofing.md).

  - **DKIM:** DomainKeys Identified Mail voegt een digitale handtekening toe aan de berichtkop van berichten die vanaf uw domein worden verzonden. Zie DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanaf uw [aangepaste domein in Microsoft 365.](use-dkim-to-validate-outbound-email.md)

  - **DMARC:** Met domeingebaseerde berichtverificatie, rapportage en conformance kunnen doel-e-mailsystemen bepalen wat er moet doen met berichten die niet voldoen aan SPF- of DKIM-controles en biedt u een ander vertrouwensniveau voor uw e-mailpartners. Zie DMARC gebruiken om e-mail te valideren [in Microsoft 365](use-dmarc-to-validate-email.md)voor meer informatie.

- **Controleer uw instellingen** voor bulk-e-mail: de drempelwaarde voor bulksgewijs compatibele e-mail (BCL) die u configureert in antispambeleid, bepaalt of bulk-e-mail (ook wel grijze _e-mail_ genoemd) wordt gemarkeerd als spam. De instelling _MarkAsSpamBulkMail_ die standaard is ingeschakeld, draagt ook bij aan de resultaten. Zie Antispambeleid configureren [in Microsoft 365](configure-your-spam-filter-policies.md)voor meer informatie.

### <a name="prevent-the-delivery-of-spam-to-the-inbox"></a>Voorkomen dat spam in het Postvak IN wordt bezorgd

- **Controleer de instellingen van** uw organisatie: Let op de instellingen waarmee berichten geen spamfilters kunnen overslaan (bijvoorbeeld als u uw eigen domein toevoegt aan de lijst met toegestane domeinen in antispambeleid). Zie Aanbevolen instellingen voor de beveiliging van EOP en Microsoft Defender voor [Office 365](recommended-settings-for-eop-and-office365-atp.md) en Lijsten met veilige afzenders maken voor [onze aanbevolen instellingen.](create-safe-sender-lists-in-office-365.md)

- **Controleer** of de regel voor ongewenste e-mail is ingeschakeld in het postvak van de gebruiker. Deze is standaard ingeschakeld, maar als deze is uitgeschakeld, kunnen berichten die als ongewenste e-mail zijn gemarkeerd, niet worden verplaatst naar de map Ongewenste e-mail. Zie Instellingen voor ongewenste [e-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie.

- **Gebruik de beschikbare lijsten met geblokkeerde afzenders:** zie Lijsten met geblokkeerde afzenders maken [voor meer informatie.](create-block-sender-lists-in-office-365.md)

- **Afmelden voor bulkmail** Als het bericht iets was waar de gebruiker zich voor heeft aangemeld (nieuwsbrieven, productaankondigingen, enzovoort) en een koppeling voor het afmelden van een betrouwbare bron bevat, kunt u de gebruiker vragen zich af te melden.

- Zelfstandig EOP: maak regels voor de **e-mailstroom in on-premises Exchange voor EOP-spamfilters:** In zelfstandige EOP-omgevingen waarin EOP on-premises Exchange-postvakken beschermt, moet u regels voor de e-mailstroom (ook wel transportregels genoemd) configureren in on-premises Exchange om de spamfilters van EOP te vertalen zodat de regel voor ongewenste e-mail het bericht kan verplaatsen naar de map Ongewenste e-mail. Zie [Standalone EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) voor meer informatie. 

### <a name="prevent-good-email-from-being-identified-as-spam"></a>Voorkomen dat goede e-mail wordt geïdentificeerd als spam

Hier volgen enkele stappen die u kunt ondernemen om fout-positieven te voorkomen:

- **Controleer de instellingen van het Outlook-filter voor ongewenste e-mail:**

  - **Controleer** of het Filter voor ongewenste e-mail van Outlook is uitgeschakeld: wanneer het Outlook-filter voor ongewenste e-mail is ingesteld op de standaardwaarde Geen automatisch **filter,** probeert Outlook geen berichten als spam te classificeren.  Wanneer het is  ingesteld op Laag of **Hoog,** gebruikt het Outlook-filter voor ongewenste e-mail zijn eigen SmartScreen-filtertechnologie om spam te identificeren en naar de map Ongewenste e-mail te verplaatsen, zodat u fout-positieven kunt krijgen. Houd er rekening mee dat Microsoft in november 2016 is gestopt met het produceren van spamdefinitie-updates voor de SmartScreen-filters in Exchange en Outlook. De bestaande SmartScreen-spamdefinities blijven bestaan, maar de effectiviteit zal na verloop van tijd waarschijnlijk slechter zijn.

  - **Controleer** of alleen veilige lijsten van Outlook is uitgeschakeld: wanneer deze instelling is ingeschakeld, worden alleen berichten van afzenders in de lijst met veilige afzenders of veilige geadresseerden van de gebruiker bezorgd in het Postvak IN. E-mail van alle anderen wordt automatisch verplaatst naar de map Ongewenste e-mail.

  Zie Instellingen voor ongewenste e-mail configureren in Exchange Online-postvakken [in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie over deze instellingen.

- **Gebruik de beschikbare lijsten met veilige afzenders:** zie Lijsten met veilige afzenders maken [voor meer informatie.](create-safe-sender-lists-in-office-365.md)

- **Controleer of gebruikers zich binnen de limieten** voor verzenden en ontvangen houden, zoals beschreven [in](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) de limieten voor ontvangen en verzenden in de beschrijving van de Exchange Online-service.

- **Zelfstandig EOP:** gebruik adreslijstsynchronisatie: als u zelfstandige EOP gebruikt ter bescherming van uw on-premises Exchange-organisatie, moet u gebruikersinstellingen synchroniseren met de service via adreslijstsynchronisatie. Op deze manier zorgt u ervoor dat de lijsten met veilige afzenders van uw gebruikers in EOP worden nageleefd. Zie Adreslijstsynchronisatie gebruiken [om e-mailgebruikers te beheren voor meer informatie.](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users)

## <a name="anti-spam-legislation"></a>Antispamwetgeving

Bij Microsoft zijn wij van mening dat voor de ontwikkeling van nieuwe technologieën en zelfvoorschriften de ondersteuning van effectief overheidsbeleid en wettelijke kaders vereist is. De wereldwijde spamgroei heeft talloze overheden verspreid om commerciële e-mail te reguleren. In veel landen is nu wetgeving tegen ongewenste e-mail van spam. De Verenigde Staten heeft zowel federale als staatswetten voor spam. Deze complementaire aanpak helpt spam te beperken en tegelijkertijd legitieme e-commerce mogelijk te maken. Met de CAN-SPAM Act worden de beschikbare hulpmiddelen voor het beteugelen van frauduleuze en misleidende e-mailberichten uitgebreid.
