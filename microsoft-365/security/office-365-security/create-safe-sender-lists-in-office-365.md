---
title: Lijsten met veilige afzenders maken in Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 4/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: Als u er zeker van wilt zijn dat u e-mail van een bepaalde afzender ontvangt, omdat u hen en hun berichten vertrouwt, u uw lijst met toestaan aanpassen in een beleid voor spamfilters.
ms.openlocfilehash: 727c0eec837627bdf7da05411f619f7705425fe7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42810943"
---
# <a name="create-safe-sender-lists-in-office-365"></a>Lijsten met veilige afzenders maken in Office 365

Als u ervoor wilt zorgen dat gebruikers e-mails ontvangen van een bepaalde afzender of afzender omdat u hen en hun berichten vertrouwt, zijn er meerdere methoden beschikbaar waaruit u kiezen. Deze opties omvatten Exchange mail flow regels (ook wel bekend als transport regels), Outlook Safe Senders, IP Allow Lists, Anti-spam Sender/Domain Allow Lists.

> [!IMPORTANT]
> Hoewel lijstmetjes van de organisatie kunnen worden gebruikt om fout-positieven aan te pakken, moet dit worden beschouwd als een tijdelijke oplossing en indien mogelijk worden vermeden. Het beheren van false positives met behulp van toegestane lijsten wordt niet aanbevolen omdat het per ongeluk uw organisatie kan openen voor spoofing, imitatie en andere aanvallen. Als u een lijst met toegestane doeleinden gebruikt, moet u waakzaam zijn en het artikel bewaren voor [het indienen van spam-, niet-spam- en phishingmails bij Microsoft voor analyse,](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)klaar.

De aanbevolen methode om een lijst met veilige afzenders te configureren, is om regels voor e-mailstromen te gebruiken, omdat dit de meeste flexibiliteit biedt om ervoor te zorgen dat alleen de juiste berichten worden toegestaan. *E-mailadressen van antispambeleid* en *op domeingebaseerde toegestane lijsten* zijn niet zo veilig als op *IP-adres gebaseerde lijsten,* omdat domeinen gemakkelijk kunnen worden vervalst. Maar anti-spam beleid IP gebaseerde staan lijsten ook risico's als ze zullen toestaan dat alle domeinen verzonden via dat IP om spam filtering te omzeilen. Wees voorzichtig en controleer *eventuele* gemaakte uitzonderingen, zorgvuldig.

> [!IMPORTANT]
> • Informatie over het maken van een **lijst met geblokkeerde afzenders** vindt [u hier.](create-block-sender-lists-in-office-365.md) <br/><br/> • Als u een afzenderdomein toestaat niet-geverifieerde e-mail te verzenden (anti-spoofingbescherming omzeilt), maar antispam- en anti-malwarecontroles niet omzeilt, u deze toevoegen aan de [lijst met veilige afzenders allowedTospoof.](walkthrough-spoof-intelligence-insight.md)

## <a name="options-from-most-to-least-recommended"></a>Opties van de meeste tot minst aanbevolen

U moet altijd uw Lijst toestaan beperken omdat ze veel beveiligingsmaatregelen omzeilen. U moet alle stalijsten opnieuw controleren als onderdeel van uw standaardonderhoud, zodat u op de hoogte bent van wie u mag omzeilen. De aanbeveling is om waar mogelijk restrictieve regels voor e-mailstroom te gebruiken.

- Regels voor de e-mailstroom van Exchange
- Outlook-veilige afzenders
- Antispambeleid: IP-lijsttoestaan
- Antispambeleid: lijsten voor afzenders/domeinsta-opties

## <a name="using-exchange-mail-flow-rules-to-allow-specific-senders-recommended"></a>Exchange-e-mailstroomregels gebruiken om specifieke afzenders toe te staan (Aanbevolen)

Om ervoor te zorgen dat alleen legitieme berichten zijn toegestaan in uw organisatie, moet de voorwaarde een van de volgende:

- Gebruik de verificatiestatus van afzenders van het verzendende domein. Dit wordt gedaan door de header Verificatie-resultaten te controleren om ervoor te zorgen dat deze "dmarc=pass" of "dmarc=bestguesspass" bevat. Dit zorgt ervoor dat het verzendende domein is geverifieerd en niet wordt vervalst. Klik voor meer informatie over [SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)en [DMARC](use-dmarc-to-validate-email.md) e-mailverificatie.

- Of als het verzendende domein geen verificatie heeft, gebruikt u het verzenddomein *plus* een verzendend IP-adres (of IP-bereik). Zorg ervoor dat u *zo beperkend mogelijk*bent, met als doel dat u dit zo veilig mogelijk doet. Een IP-bereik groter dan /24 wordt *niet* aanbevolen. Voeg geen IP-adresbereiken toe die behoren tot consumentenservices of gedeelde infrastructuren.

> [!IMPORTANT]
> Als u een IP-adres toestaat dat natted is, moet u de machines kennen die betrokken zijn bij die NAT-groep om het bereik van uw toestaan te kennen. Houd er rekening mee dat IP-adressen kunnen veranderen en nat-deelnemers dat ook. U moet alle lijst met toegestane lijsten opnieuw controleren, inclusief IP-verlenging als onderdeel van uw standaardonderhoud.

- *Voeg eventueel*een voorwaarde toe dat het bericht afkomstig is van buiten de organisatie (dit is impliciet, maar het is prima om het toe te voegen als voorwaarde om rekening te houden met on-premises servers die mogelijk niet correct zijn geconfigureerd).

- *Optioneel*u unieke zoekwoorden of woordgroepen in de e-mail Onderwerp of Body identificeren, als aanvullende voorwaarde om de e-mailberichten die zijn toegestaan door de e-mailstroomregel verder te beperken.

De actie op de regel moet dit patroon volgen:

1. Stel het spamvertrouwensniveau (SCL) in op -1 (bypass spamfiltering).

2. Voeg een X-Header toe om te zeggen wat de regel doet. In het onderstaande voorbeeld `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`u een eenvoudige koptekst toevoegen. Als u meer dan één domein in deze regel hebt, u de koptekst naar gelang van het geval wijzigen. **Wanneer een bericht filtering overslaat als gevolg van een e-mailstroomregel, stempelt het SFV:SKN in de x-Forefront-Antispam-Report-header** **(als het op een IP-lijst toestaan staat, stempelt het ook IPV:CAL**). Dit zal helpen bij het oplossen van problemen.

![GUI voor het omzeilen van spamfiltering.](../../media/1-AllowList-SkipFilteringFromContoso.png)

> [!CAUTION]
> Configureer de regels voor e-mailstroom niet met alleen *het afzenderdomein* als voorwaarde om spamfilters over te slaan. Deze methode verhoogt het risico dat spammers het verzendende domein kunnen spoofen (of zich voordoen als het volledige e-mailadres) om alle spamfilters, verificatiecontroles voor afzenders over te slaan en het bericht komt in het postvak IN van een persoon.

![Hoe stel je de SCL in op min-één.](../../media/2-AllowList-SetsSCLMinus1.png)

Voeg geen domeinen toe die u bezit of `microsoft.com`populaire domeinen (bijvoorbeeld ) aan de regel voor e-mailstroom als voorwaarde. Dit wordt beschouwd als een hoog risico, omdat het kansen creëert voor slechte acteurs om u e-mail te sturen die anders zou worden uitgefilterd.

Zie [Regels voor e-mailstromen gebruiken om de SCL in berichten in te stellen](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)voor meer informatie.

## <a name="use-outlook-safe-senders-end-user-managed"></a>Outlook Safe Senders gebruiken (beheerde eindgebruiker)

In plaats van een adres, een domein of een IP-adres wereldwijd toe te staan, kunnen eindgebruikers ook het verzenden van adressen toestaan via Outlook Safe Senders. De stappen om dit in te stellen verschillen tussen [de webversie van Outlook](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46) en de [Outlook-client](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). **Wanneer berichten met succes zijn geautoriseerd vanwege veilige afzenders, ziet u SFV:SFE in het X-Forefront-Antispam-Report,** dat aangeeft dat spam/spoof/Phish-filtering wordt omzeild.

## <a name="use-anti-spam-policy-ip-allow-lists"></a>Lijst met IP-stalijsten voor antispambeleid gebruiken

Wanneer het niet mogelijk is om e-mailstroomregels te gebruiken om een specifieke afzender wereldwijd toe te staan terwijl u afzenderverificatie valideert, of door een domein en IP aan elkaar te koppelen, is de volgende beste optie om de afzender toe te voegen aan de *lijst Ip-toestaan voor antispambeleid.* U vindt de gedetailleerde stappen in [Het beleid voor verbindingsfilter configureren.](configure-the-connection-filter-policy.md) Het is belangrijk om het aantal toegestane IP-adressen tot een minimum te beperken, dus vermijd het gebruik van volledige IP-adresbereiken. U moet ook geen IP-adresbereiken toevoegen die behoren tot consumentenservices of gedeelde infrastructuren, en er ook *voor zorgen* dat u de lijst met toegestane IP-adressen regelmatig bekijkt en de adressen verwijdert die niet langer nodig zijn.

> [!CAUTION]
> Als u antispam-politie's configureert die alleen op basis van een IP-adres van de afzender zijn toegestaan, wordt spamfilters voor alle berichten van dat IP-adres in de regel toestaan overgeslagen. Dit creëert een hoog risico van slechte acteurs sturen u e-mail die anders zou worden gefilterd. Deze methode slaat ook alle spamfiltering, verificatiecontroles voor afzenders en het bericht wordt in het postvak IN van een gebruiker verzonden, waardoor het risico toeneemt.

## <a name="use-anti-spam-policy-senderdomain-allow-lists"></a>Lijsten met afzender-/domeinstatus van antispambeleid gebruiken

De minst wenselijke optie is om te autoriseren per afzender/domein. Deze optie moet worden vermeden *indien mogelijk* als het omzeilt Spam / Spoof / Phish bescherming volledig en niet evalueren afzender authenticatie. Deze methode verhoogt uw risico op het ontvangen van e-mail van slechte acteurs en wordt het best aanbevolen tijdelijk en alleen bij het testen. De gedetailleerde stappen zijn te vinden in [Het beleidsonderwerp Voor spamfilters configureren.](configure-your-spam-filter-policies.md)

De maximumlimiet voor deze lijsten is ongeveer 1000 vermeldingen; hoewel, u zult slechts 30 ingangen in de portaal kunnen ingaan. U moet PowerShell gebruiken om meer dan 30 vermeldingen toe te voegen.

> [!IMPORTANT]
> • Het configureren van antispam-polities om *afzender/toestaan-domein toe* te staan, zal resulteren in berichten die spamfilters overslaan voor a) berichten van afzenders in de lijst toestaan, of b) afzenders uit een toegestaan domein. Deze methode verhoogt het risico dat spammers het verzendende domein kunnen spoofen (of zich voordoen als het volledige e-mailadres) dat alle spamfilters, verificatiecontroles voor afzenders overslaat en het bericht rechtstreeks naar het postvak van een persoon verzendt. <br/><br/>• Voeg geen domeinen toe die u bezit `microsoft.com`of populaire domeinen (bijvoorbeeld ) aan de regel voor e-mailstroom als voorwaarde. Deze methode wordt beschouwd als een hoog risico, omdat het kansen creëert voor slechte acteurs om u e-mail te sturen die anders zou worden uitgefilterd, waardoor het risico toeneemt. <br/><br/>• Informatie over het maken van een **lijst met geblokkeerde afzenders** vindt [u hier.](create-block-sender-lists-in-office-365.md)
