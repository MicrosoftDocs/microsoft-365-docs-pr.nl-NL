---
title: Meer informatie over spoofinformatie
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/22/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
description: Gebruik spoofinformatie in &amp; het Security Compliance Center op de pagina Anti-spam-instellingen om alle afzenders te controleren die domeinen spoofen die deel uitmaken van uw organisatie of externe domeinen spoofen. Spoofinformatie is beschikbaar als onderdeel van Office 365 Enterprise E5 of afzonderlijk als onderdeel van Advanced Threat Protection en Exchange Online Protection.
ms.openlocfilehash: a58f98852f321791615c5f0064b69e8510aadbe5
ms.sourcegitcommit: a7b2cd892cb65a61ee246268e1af2f8b9e526f6b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2020
ms.locfileid: "43081458"
---
# <a name="learn-more-about-spoof-intelligence"></a>Meer informatie over spoofinformatie

Gebruik spoofinformatie in &amp; het Security Compliance Center op de **pagina Anti-spam-instellingen** om alle afzenders te controleren die domeinen spoofen die deel uitmaken van uw organisatie of externe domeinen spoofen. Spoofinformatie is beschikbaar als onderdeel van Office 365 Enterprise E5 of afzonderlijk als onderdeel van Advanced Threat Protection (ATP) en vanaf oktober 2018 Exchange Online Protection (EOP).

## <a name="what-types-of-email-spoofing-can-i-review-and-which-should-i-protect-against-with-spoof-intelligence"></a>Tegen welke soorten e-mailspoofing kan ik bekijken en tegen welke moet ik me beschermen met spoofinformatie?

Voor domeinen die u bezit, u afzenders bekijken die uw domein spoofen en vervolgens ervoor kiezen om de afzender door te laten gaan of de afzender te blokkeren. Voor externe domeinen u het afzenderdomein toestaan in combinatie met de verzendinfrastructuur, hoewel het geen individueel verzendend e-mailadres is.

Wanneer een afzender een e-mailadres vervalst, lijkt deze e-mail te verzenden namens een of meer gebruikersaccounts binnen een van de domeinen van uw organisatie of een extern domein dat naar uw organisatie wordt verzonden. Verrassend, er zijn een aantal legitieme zakelijke redenen voor spoofing. In deze gevallen zou u bijvoorbeeld de afzender niet blokkeren om uw domein te spoofen:

- U hebt afzenders van derden die uw domein gebruiken om bulkmail naar uw eigen werknemers te verzenden voor bedrijfspeilingen.

- U hebt een extern bedrijf ingehuurd om namens u reclame- of productupdates te genereren en uit te sturen.

- Een assistent die regelmatig e-mail moet sturen voor een andere persoon binnen uw organisatie.

- Een toepassing die is geconfigureerd om de eigen organisatie te spoofen om interne meldingen per e-mail te verzenden.

Externe domeinen sturen vaak vervalste e-mail, en veel van deze redenen zijn legitiem. Hier zijn bijvoorbeeld enkele legitieme gevallen waarin externe afzenders vervalste e-mail verzenden:

- De afzender staat op een discussiemailinglijst en de mailinglijst stuurt de e-mail van de oorspronkelijke afzender door naar alle deelnemers op de mailinglijst.

- Een extern bedrijf stuurt e-mail namens een ander bedrijf (bijvoorbeeld een geautomatiseerd rapport of een software-as-a-service bedrijf).

U hebt een manier nodig om ervoor te zorgen dat de e-mail die door legitieme spoofers wordt verzonden, niet verstrikt raakt in spamfilters in Office 365 of externe e-mailsystemen. Normaal gesproken behandelt Office 365 deze e-mailberichten als spam. Als Office 365-beheerder u dit voorkomen door spooffilters &amp; in te stellen in het Security Compliance Center. Als u eigenaar bent van het domein, u SPF, DKIM en DMARC zo configureren dat deze afzenders mogelijk zijn.

Aan de andere kant moeten kwaadwillende spoofers, afzenders die uw domein spoofen of externe domeinen, spam of phishing-e-mail verzenden, worden geblokkeerd. Spoofing is ook een veel voorkomende manier voor phishers om gebruikersreferenties te krijgen. Office 365 heeft ingebouwde spoofbeveiliging om uw organisatie te beschermen tegen afzenders van deze schadelijke e-mails. Spoofbeveiliging voor de domeinen van uw organisatie is altijd ingeschakeld voor alle Office 365-klanten en externe domeinspoofbeveiliging is standaard ingeschakeld voor klanten met geavanceerde bedreigingsbeveiliging en vanaf oktober 2018 ook EOP-klanten. Om deze bescherming verder te versterken, u ons vertellen welke afzenders gemachtigd zijn om de domeinen van uw organisatie te spoofen en namens u e-mail te verzenden en of externe domeinen mogen spoofen. Elke e-mail die wordt verzonden van een afzender die u niet autoert, wordt door Office 365 behandeld als spam of spoofing. Houd de afzenders in de gaten die uw domein spoofen en help ons spoofinformatie te verbeteren met behulp van het Security &amp; Compliance Center.

## <a name="managing-spoof-intelligence-in-the-security-amp-compliance-center"></a>Spoofinformatie beheren in &amp; het Security Compliance Center
<a name="Managespooflist"> </a>

Het spoof-intelligentiebeleid dat u hebt ingesteld, wordt altijd afgedwongen door Office 365. U het niet uitschakelen, maar u wel kiezen hoeveel u het actief wilt beheren.

U de afzenders bekijken die uw domein of externe domeinen spoofen en vervolgens beslissen of &amp; elke afzender dit moet kunnen doen met behulp van het Security Compliance Center. Voor elk vervalst gebruikersaccount dat een afzender spooft vanuit uw domein of een extern domein, u de informatie in de volgende tabel bekijken.

|**Parameter**|**Beschrijving**|
|:-----|:-----|
|Afzender  <br/> |Ook wel de ware afzender genoemd. Dit is meestal het domein waaruit de spoof e-mail afkomstig is. Office 365 bepaalt het domein van de DNS-record (pointer) van het verzendende IP-adres dat uw organisatie spooft. Als er geen domein wordt gevonden, wordt in het rapport het IP-adres van de afzender weergegeven.  <br/> |
|Vervalste gebruiker  <br/> |Het gebruikersaccount dat wordt vervalst door de afzender.  <br/> **Alleen intern** tabblad. Dit veld bevat één e-mailadres of als de afzender meerdere gebruikersaccounts vervalst, bevat het **meer dan één**.  <br/> **Alleen** extern tabblad. Externe domeinen bevatten alleen een verzendend domein en bevatten geen volledig e-mailadres.  <br/> **Tip! Voor gevorderde beheerders.** De vervalste gebruiker is het From (5322.From) adres dat ook het adres is dat wordt weergegeven als het Van-adres van de e-mailclient. Dit wordt ook wel de header.van adres genoemd. De geldigheid van dit adres wordt niet gecontroleerd door SPF.           |
|Aantal berichten  <br/> |Het aantal e-mailberichten dat de afzender namens de geïdentificeerde vervalste afzender of afzenders in de afgelopen 30 dagen naar uw organisatie heeft verzonden.  <br/> |
|Aantal klachten van gebruikers  <br/> |Klachten die door gebruikers zijn ingediend tegen deze afzender door uw gebruikers in de afgelopen 30 dagen. Klachten zijn meestal in de vorm van ongewenste inzendingen bij Microsoft.  <br/> |
|Verificatieresultaat  <br/> |Deze waarde wordt **doorgegeven** als de afzender doordeed aan verificatiecontroles voor Afzenders van Exchange Online Protection (EOP), zoals SPF of DKIM, **Mislukt** als de afzender verificatiecontroles voor EOP-afzenders heeft mislukt of **onbekend** is als het resultaat van deze controles niet bekend is.  <br/> |
|Besluit vastgesteld door  <br/> |Hiermee wordt weergegeven of de Office 365-beheerder of het spoof-informatiebeleid heeft bepaald of de afzender de gebruiker mag spoofen.  <br/> |
|Laatst gezien  <br/> |De laatste datum waarop deze afzender namens deze vervalste gebruiker een bericht heeft ontvangen.  <br/> |
|Mag je spoofen?  <br/> | Geeft aan of deze afzender e-mail mag verzenden namens de vervalste gebruiker. Mogelijke waarden zijn:  <br/> **Ja.** Alle vervalste adressen van deze afzender van spoofing mogen uw organisatie spoofen.  <br/> **Nee.** Vervalste adressen van deze afzender van spoofing mogen uw organisatie niet spoofen. In plaats daarvan worden berichten van deze afzender gemarkeerd als spam door Office 365.  <br/> **Sommige gebruikers** Als een afzender meerdere gebruikers spooft, mogen sommige vervalste adressen van deze afzender uw organisatie spoofen, de rest wordt gemarkeerd als spam. Gebruik het tabblad **Gedetailleerd** om de specifieke adressen te bekijken.  <br/> |
|Spooftype  <br/> |Deze waarde is **Intern** als het domein een van de ingerichte domeinen van uw organisatie is, anders is de waarde **Extern**.  <br/> |

 **Afzenders beheren die uw domein spoofen &amp; met het Security Compliance Center**

1. Ga naar het [Security &amp; Compliance Center.](https://protection.office.com)

2. Meld u aan bij Office 365 met uw werk- of schoolaccount. Uw account moet beheerdersreferenties hebben in uw Office 365-organisatie.

3. Vouw in &amp; het Security Compliance Center het \> **Policy** \> **antispambeleid voor** **bedreigingen** uit.

    ![Schermafbeelding van toegang tot de antispampagina](../../media/0a098e68-5ecf-40d7-984f-d15fcc1f958d.jpg)

4. Schuif op de pagina **Antispam-instellingen** in het rechterdeelvenster naar beneden en vouw **het informatiebeleid van spoof uit.**

    ![Spoof](https://user-images.githubusercontent.com/41186174/71801032-6228f100-3062-11ea-8461-682b910418c2.png)

5. Als u de lijst met afzenders wilt weergeven die uw domein **spoofen,** kiest u Nieuwe afzenders controleren en selecteert u het tabblad **Uw domeinen.**

    Als je afzenders al hebt beoordeeld en een aantal van je eerdere keuzes wilt wijzigen, kun je **Afzenders weergeven die ik in** plaats daarvan al heb beoordeeld. In beide gevallen wordt het volgende deelvenster weergegeven.

    ![Schermafbeelding van toegang tot het tabblad vervalste afzenders](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

    Elke vervalste gebruiker wordt in een aparte rij weergegeven, zodat u kiezen of u de afzender wilt toestaan of blokkeren om elke gebruiker afzonderlijk te spoofen.

    Als u een afzender wilt toevoegen aan de lijst toestaan voor een gebruiker, selecteert u **Ja** in de kolom **Toegestaan om te spoofen.** Als u een afzender wilt toevoegen aan de bloklijst voor een gebruiker, kiest u **Nee**.

    Als u het beleid wilt instellen voor domeinen waarvan u niet de eigenaar bent, selecteert u het tabblad **Externe domeinen.** Wijzig elke afzender in **Ja** in de kolom **Toegestaan voor spoofen** zodat die afzender niet-geverifieerde e-mail naar uw organisatie kan verzenden. Als u denkt dat Office 365 een fout heeft gemaakt door de afzender toe te staan vervalste e-mail te verzenden, wijzigt u de kolom **Toegestaan om te spoofen** in **Nee**.

    ![Schermafbeelding van de vraag of een afzender mag spoofen](../../media/5dbef9cf-103f-49cd-9638-4b0083d6baa7.jpg)

6. Kies **Opslaan** om eventuele wijzigingen op te slaan.

Als u een Office 365 Enterprise E5-abonnement hebt of Advanced Threat Protection afzonderlijk hebt aangeschaft als add-on, u ook afzenders beheren die uw domein spoofen via het [Spoof Intelligence-inzicht.](walkthrough-spoof-intelligence-insight.md)

## <a name="configuring-the-anti-spoofing-policy"></a>Het anti-spoofingbeleid configureren
<a name="Managespooflist"> </a>

Naast het toestaan of blokkeren van een bepaalde afzender van het verzenden van vervalste e-mail naar uw organisatie, u ook configureren hoe strikt het filter moet zijn en de actie die moet worden ondernomen wanneer een spoofingbericht wordt gevonden.

Anti-spoofing bescherming wordt toegepast op e-mail van afzenders van domeinen die zich buiten uw Office 365-organisatie bevinden. U het beleid toepassen op ontvangers van wie de postvakken een licentie hebben voor Office 365 Enterprise E5, Advanced Threat Protection en vanaf oktober 2018 ook EOP-klanten. U beheert het anti-spoofing beleid samen met de andere anti-phishing-instellingen. Zie [Office 365 ATP antiphishing- en antiphishingbeleid instellen](set-up-anti-phishing-policies.md)voor meer informatie over antiphishing-instellingen.

Office 365 bevat standaard anti-spoofing beveiliging die altijd wordt uitgevoerd. Deze standaardbeveiliging is niet &amp; zichtbaar in het Security Compliance Center of kan niet worden opgehaald via Windows PowerShell-cmdlets. U de standaardanti-spoofingbeveiliging niet wijzigen. In plaats daarvan u configureren hoe strikt Office 365 de anti-spoofingbescherming afdwingt in elk antiphishingbeleid dat u maakt.

Hoewel het anti-spoofingbeleid wordt weergegeven onder het &amp; anti-phishingbeleid in het Security Compliance Center, erft het zijn standaardgedrag niet van de bestaande phishing-instelling onder de antispamconfiguratie. Als u instellingen hebt onder **Anti-spam** \> **Phishing** die u wilt repliceren voor anti-spoofing, moet u een antiphishingbeleid maken en vervolgens het spoofgedeelte van het anti-phishingbeleid bewerken om uw spoofinstellingen weer te geven zoals beschreven in de volgende sectie, in plaats van de standaardinstellingen te accepteren die op de achtergrond worden uitgevoerd.

 **Anti-spoofing bescherming configureren binnen een antiphishingbeleid &amp; met behulp van het Security Compliance Center**

1. Ga naar het [Security &amp; Compliance Center.](https://protection.office.com)

2. Meld u aan bij Office 365 met uw werk- of schoolaccount. Uw account moet beheerdersreferenties hebben in uw Office 365-organisatie.

3. Vouw in &amp; het Security Compliance Center **het beleid voor bedreigingsbeheer** \> **Policy** \> **antiphishing**uit.

4. Selecteer op de **antiphishingpagina** in het rechterdeelvenster het antiphishingbeleid dat u wilt configureren.

5. Kies bewerken op de pagina die wordt weergegeven in de rij **Spoof** **.**

6. Configureer vervolgens de acties die moeten worden uitgevoerd wanneer een bericht wordt gedetecteerd als een fout in meerdere domeinen. Het standaardgedrag is om het bericht te verplaatsen naar de ongewenste e-mailmap van de ontvanger. De andere optie is om het bericht naar de quarantaine te sturen. Zie [E-mailberichten in quarantaine plaatsen in Office 365](quarantine-email-messages.md)voor meer informatie over het beheren van berichten die in quarantaine worden verzonden.

    ![Schermafbeelding van opties voor het bewerken van antispoofing-beleid](../../media/7a868dff-2c4b-46b9-88ca-f2d523ca2307.jpg)

7. Maak uw keuze en kies **Opslaan**.

## <a name="other-ways-to-manage-spoofing-and-phishing-with-office-365"></a>Andere manieren om spoofing en phishing te beheren met Office 365
<a name="Managespooflist"> </a>

Wees ijverig over spoofing en phishing bescherming. Dit zijn gerelateerde manieren om te controleren of afzenders uw domein spoofen en te voorkomen dat ze uw organisatie beschadigen:

- Controleer het spoofmailrapport van Exchange Online Protection als onderdeel van uw routine. U dit rapport vaak gebruiken om vervalste afzenders te bekijken en te beheren. Zie Voor informatie in **Het e-mailrapport spoofen** in [rapporten over e-mailbeveiliging gebruiken in Office 365 om gegevens over malware, spam en regeldetecties weer te geven.](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports)

Voor meer geavanceerde Office 365-beheerders u deze controles ook uitvoeren:

- Bekijk de SPF-configuratie (Sender Policy Framework). Zie [SPF instellen in Office 365 om spoofing te voorkomen voor](set-up-spf-in-office-365-to-help-prevent-spoofing.md)een snelle introductie tot SPF en om deze snel te configureren. Voor een diepgaander inzicht in hoe Office 365 SPF gebruikt, of voor het oplossen van problemen of niet-standaardimplementaties zoals hybride implementaties, begint u met [Hoe Office 365 Het Sender Policy Framework (SPF) gebruikt om spoofing te voorkomen.](how-office-365-uses-spf-to-prevent-spoofing.md)

- Controleer de configuratie van uw DomainKeys Identified Mail (DKIM). U moet DKIM gebruiken naast SPF en DMARC om te voorkomen dat spoofers berichten verzenden die eruit zien alsof ze uit uw domein komen. Met DKIM kunt u een digitale handtekening toevoegen aan e-mailberichten in de berichtkop. Zie [DKIM gebruiken om uitgaande e-mail die vanuit uw aangepaste domein in Office 365 is verzonden, te valideren](use-dkim-to-validate-outbound-email.md)voor informatie.

- Controleer uw domeingebaseerde berichtverificatie- en rapportageconfiguratie (DMARC). De implementatie van DMARC met SPF en DKIM biedt extra bescherming tegen adresvervalsing en phishing-email. DMARC helpt ontvangende e-mailsystemen vast te stellen wat er moet gebeuren met berichten die zijn verzonden vanuit uw domein die niet door de SPF- en DKIM-controles komen. Zie [DMARC gebruiken om e-mail in Office 365 te valideren](use-dmarc-to-validate-email.md)voor meer informatie.

- Gebruik de [cmdlet Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-phishfilterpolicy) in Exchange Online PowerShell of Exchange Online Protection PowerShell om gedetailleerde gegevens over vervalste afzenders te verzamelen, toegestane en bloklijsten te genereren en u te helpen bepalen hoe u uitgebreidere SPF-, DKIM- en DMARC DNS-records genereren zonder dat uw legitieme e-mail wordt betrapt in externe spamfilters. Zie [Hoe antispoofing-beveiliging werkt in Office 365](https://blogs.msdn.microsoft.com/tzink/2016/02/23/how-antispoofing-protection-works-in-office-365/)voor meer informatie.
