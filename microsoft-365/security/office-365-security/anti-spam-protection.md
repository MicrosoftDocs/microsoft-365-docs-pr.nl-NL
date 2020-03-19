---
title: Office 365 email anti-spam protection
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: dansimp
ms.date: 6/29/2018
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
description: Meer informatie over de antispam-instellingen en filters waarmee u spam voorkomen in Exchange Online en Office 365. Krijg je te veel spam in Office 365? U uw spamfilters en antispambeleidsinstellingen aanpassen.
ms.openlocfilehash: b7ffb29d09a357cc0a2e407d1a66f29273fc950f
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806313"
---
# <a name="office-365-email-anti-spam-protection"></a>Office 365 email anti-spam protection

Bent u bezorgd over te veel spam in Office 365? We hebben meerdere spamfilters ingebouwd in uw Office 365- of Exchange Online Protection (EOP-service), zodat uw e-mail wordt beveiligd vanaf het moment dat u uw eerste bericht ontvangt. Om spam in Office 365 te voorkomen, u een beveiligingsinstelling wijzigen om een specifiek probleem in uw organisatie aan te pakken, bijvoorbeeld dat u veel spam ontvangt van een bepaalde afzender, of om uw instellingen eenvoudig af te stemmen zodat deze afgestemd op de behoeften van uw organisatie. U hiervoor antispaminstellingen wijzigen in het Office &amp; 365 Security Compliance Center.

Dit artikel is bedoeld voor Office 365-beheerders. Als u geen beheerder bent, maar wel een Office 365-gebruiker bent en u wilt leren hoe u omgaan met spam die u ontvangt, is dit niet het artikel dat u zoekt. Als u in plaats daarvan Outlook voor pc of Outlook voor Mac gebruikt, begint u met [overzicht van het filter ongewenste e-mail](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). Als u Outlook op internet gebruikt, begint u met [Meer informatie over ongewenste e-mail en phishing](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31).

## <a name="these-options-help-you-prevent-spam-in-office-365"></a>Met deze opties u spam in Office 365 voorkomen

 **Verbindingsfiltering:** Wanneer u verbindingsfiltering gebruikt, controleert Office 365 de reputatie van de afzender voordat een bericht wordt doorgegeven. U een lijst met toegestane of veilige afzenders maken om ervoor te zorgen dat u elk bericht ontvangt dat naar u wordt verzonden vanaf een specifiek IP-adres of IP-adresbereik. U ook een lijst maken met IP-adressen van waaruit u berichten blokkeren, een bloklijst genaamd. Zie [Het beleid voor verbindingsfilter configureren](configure-the-connection-filter-policy.md)voor meer informatie. Als u zich zorgen maakt over spam in Office 365, gebruikt u verbindingsfiltering om spam te voorkomen.

Voor klanten die Office 365 Enterprise E5 hebben of ATP-licenties (Advanced Threat Protection) hebben gekocht, wordt verbindingsfiltering gebruikt door spoofinformatie om lijsten met afzenders die uw domein spoofen te maken en te blokkeren. Zie [Meer informatie over spoofintelligentie](learn-about-spoof-intelligence.md)voor meer informatie.

 **Spamfiltering**: Office 365 controleert op berichtkenmerken die consistent zijn met spam met behulp van spamfiltering. U wijzigen welke acties u wilt uitvoeren op berichten die als spam zijn geïdentificeerd en kiezen of u berichten wilt filteren die in specifieke talen zijn geschreven of die vanuit specifieke landen of regio's worden verzonden. U ook geavanceerde opties voor spamfiltering inschakelen als u een agressieve benadering van spamfiltering wilt nastreven. Bovendien u spammeldingen van eindgebruikers configureren om gebruikers te informeren wanneer berichten die voor hen zijn bedoeld, in plaats daarvan naar de quarantaine zijn verzonden. (Het verzenden van berichten naar de quarantaine is een van de configureerbare acties.) Uit deze meldingen kunnen eindgebruikers fout-positieven vrijgeven en deze melden aan Microsoft voor analyse. Zie [Uw spamfilterbeleid configureren](configure-your-spam-filter-policies.md)voor meer informatie. Gebruik verbindingsfiltering als u zich zorgen maakt over te veel spam in Office 365 om spam in Office 365 te voorkomen.

> [!NOTE]
> Voor zelfstandige eop-klanten: standaard sturen de EOP-spamfilters door spam gedetecteerde berichten naar de map Ongewenste e-mail van elke ontvanger. Om er echter voor te zorgen dat de **mapactie Berichten verplaatsen naar ongewenste e-mail** werkt met on-premises postvakken, moet u twee Exchange-regels voor e-mailstromen (ook wel transportregels genoemd) configureren op uw on-premises servers om spamkoppen van EOP te detecteren. Zie Zorgen [dat spam wordt doorgestuurd naar de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)van elke gebruiker.

## <a name="extra-information-if-you-receive-too-much-spam-in-office-365"></a>Extra informatie als u te veel spam ontvangt in Office 365

De volgende video geeft een overzicht van het configureren van spamfiltering in EOP.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/608be94c-d763-4c47-af94-99e7cb277713?autoplay=false]

Zie het onderwerp [Beleid voor uw spamfilter configureren](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="check-your-outgoing-messages-to-prevent-spam-in-office-365"></a>Controleer uw uitgaande berichten om spam in Office 365 te voorkomen

 **Uitgaande filtering:** Office 365 controleert ook of uw gebruikers geen spam verzenden. Bijvoorbeeld, een gebruiker computer kan besmet raken met malware die ervoor zorgt dat het spam-berichten te sturen, dus bouwen we bescherming tegen die zogenaamde *uitgaande filtering*. U uitgaande filtering niet uitschakelen, maar u wel de instellingen configureren die zijn beschreven in [Het uitgaande spambeleid configureren.](configure-the-outbound-spam-policy.md) Als u zich zorgen maakt over te veel spam in Office 365, gebruikt u uitgaande filtering om spam in Exchange Online te voorkomen.

## <a name="beyond-the-basics-more-ways-to-prevent-spam-in-office-365"></a>Voorbij de basisbeginselen: meer manieren om spam in Office 365 te voorkomen

 **Regels voor e-mailstromen:** als u verder wilt gaan dan het ingebouwde spamfiltering en aangepaste regels wilt maken die zijn gebaseerd op uw bedrijfsbeleid, zijn regels voor _[de mailstroom](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)_ (ook wel _transportregels_genoemd) een ander filter waarmee u spam in Office 365 voorkomen. U bijvoorbeeld regels voor e-mailstroom gebruiken om de SCL-waarde (Spam Confidence Level) in te stellen voor berichten die overeenkomen met specifieke voorwaarden, zoals beschreven in [regels voor de gebruikersstroomstromen gebruiken om het spamvertrouwensniveau (SCL) in berichten in te stellen.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

 **E-mailverificatie**: Technieken die het Domain Name System (DNS) gebruiken om verifieerbare informatie toe te voegen aan e-mailberichten over de afzender van een e-mailbericht worden e-mailverificatie genoemd. Meer geavanceerde Office 365-beheerders kunnen gebruik maken van deze e-mailverificatiemethoden:

- **Sender Policy Framework (SPF)**: SPF valideert de oorsprong van e-mailberichten door het IP-adres van de afzender te verifiëren tegen de vermeende eigenaar van het verzendende domein. Zie [SPF instellen in Office 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md)om spoofing te voorkomen voor een snelle inleiding tot SPF en om deze snel te configureren. Voor een meer diepgaand inzicht in hoe Office 365 SPF gebruikt, of voor het oplossen van problemen of niet-standaardimplementaties zoals hybride implementaties, begint u met [hoe Office 365 Sender Policy Framework (SPF) gebruikt om spoofing te voorkomen.](how-office-365-uses-spf-to-prevent-spoofing.md)

- **DomainKeys Identified Mail (DKIM)**: Met DKIM u een digitale handtekening toevoegen aan e-mailberichten in de berichtkop van e-mails die u verzendt. E-mailsystemen die e-mail ontvangen van uw domein gebruiken deze digitale handtekening om te bepalen of binnenkomende e-mail die ze ontvangen legitiem is. Zie [DKIM gebruiken om uitgaande e-mails te valideren die vanuit uw aangepaste domein zijn verzonden in Office 365.](use-dkim-to-validate-outbound-email.md)

- **Domeingebaseerde message authentication, reporting en conformance (DMARC)**: DMARC helpt bij het ontvangen van e-mailsystemen bepalen wat te doen met berichten die niet voldoen aan De SPF- of DKIM-controles en biedt een ander niveau van vertrouwen voor uw e-mailpartners. Zie [DMARC gebruiken om e-mail te valideren in Office 365](use-dmarc-to-validate-email.md)voor informatie over het instellen van DMARC.

Als u zich zorgen maakt over spam, phishing en spoofing in Office 365, gebruikt u Samen SPF, DKIM en DMARC om spam en ongewenste spoofing te voorkomen.

 Instellingen voor beheerde eindgebruikers: als u op zoek bent naar informatie over hoe eindgebruikers hun eigen spam-instellingen kunnen beheren, bekijk dan het [overzicht van het filter ongewenste e-mail](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) (voor Microsoft **Outlook-gebruikers)** of [Meer informatie over ongewenste e-mail en phishing](https://support.microsoft.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31) (voor Outlook in de webgebruikers). Als u EOP gebruikt om on-premises postvakken te beschermen, moet u directorysynchronisatie gebruiken om ervoor te zorgen dat deze instellingen worden gesynchroniseerd met de service. Zie 'Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren' in [EOP](manage-mail-users-in-eop.md)voor meer informatie over het instellen van adreslijstsynchronisatie.

## <a name="for-more-information"></a>Voor meer informatie

[Blog: Waarom komen spam en phishing via Office 365?](https://blogs.msdn.microsoft.com/tzink/2014/09/12/why-does-spam-and-phishing-get-through-office-365-and-what-can-be-done-about-it/)

[Veelgestelde vragen over antispambescherming](anti-spam-protection-faq.md)

[Valse positieve e-mail voorkomen die is gemarkeerd als spam met een safelist of andere technieken](prevent-email-from-being-marked-as-spam.md)

[Office 365-spamfiltering instellen om ongewenste berichten te blokkeren](reduce-spam-email.md)

[Wat is het verschil tussen ongewenste e-mail en bulke-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md)

[Kopteksten voor spamberichten](anti-spam-message-headers.md)

[Backscatter messages and EOP](backscatter-messages-and-eop.md)(Backscatter-berichten en EOP)

## <a name="more-resources"></a>Meer informatie

[Hulp krijgen van de Office 365-communityforums](https://techcommunity.microsoft.com/t5/Office-365/ct-p/Office365)

[Beheerders: Aanmelden en een serviceaanvraag maken](https://portal.office.com/AdminPortal/Home?ref=support)

[AContact-ondersteuning voor zakelijke producten - Help voor beheerders](https://docs.microsoft.com/Office365/Admin/contact-support-for-business-products)
