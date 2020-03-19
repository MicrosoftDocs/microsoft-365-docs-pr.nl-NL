---
title: Spam-, spam- en phishing-scamberichten verzenden naar Microsoft voor analyse
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'U en uw gebruikers kunnen valse negatieve en fout-positieve spamberichten naar Microsoft sturen voor analyse. '
ms.openlocfilehash: 7b53f74be78bc1203189815c6a7adf3337decd21
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2020
ms.locfileid: "42856867"
---
# <a name="submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis"></a>Spam-, spam- en phishing-scamberichten verzenden naar Microsoft voor analyse

Het kan frustrerend zijn wanneer gebruikers in uw organisatie ongewenste berichten (spam) of phishing-scamberichten ontvangen in hun Postvak IN, of als ze geen legitiem e-mailbericht ontvangen omdat het is gemarkeerd als ongewenste e-mailberichten. We verfijnen onze spamfilters voortdurend om nauwkeuriger te zijn. U en uw gebruikers kunnen dit proces helpen door valse negatieve en fout-positieve spamberichten bij Microsoft in te dienen voor analyse. Een "vals negatief" is een spambericht dat had moeten zijn, maar niet werd geïdentificeerd als spam. Een "vals positief" is een legitiem e-mailbericht dat ten onrechte is geïdentificeerd als spam.

> [!NOTE]
> Vanwege het grote aantal inzendingen dat we ontvangen, kunnen we mogelijk niet alle verzoeken om analyse beantwoorden.

Beheerders kunnen e-mail, url en bijlagen ter controle naar Microsoft verzenden. Zie [Beheerdersinzendingen in Office 365 ATP](admin-submission.md).

## <a name="submit-junk-or-phishing-messages-that-passed-through-the-spam-filters"></a>Ongewenste of phishingberichten verzenden die door de spamfilters zijn verzonden

Als u een bericht ontvangt dat door de spamfilters is verzonden en moet worden geclassificeerd als ongewenste of phishing-scam, u het bericht 'vals negatief' indienen bij de microsoft spamanalyse- en Microsoft Phishing-analyseteams, indien van toepassing. De analisten zullen het bericht bekijken en toevoegen aan de servicebrede filters als het voldoet aan de classificatiecriteria.

Zie [E-mailspam blokkeren met het spamfilter van Office 365 om valse negatieve problemen te voorkomen voor](reduce-spam-email.md)meer spaminstellingen die van toepassing zijn op de hele organisatie. Dit artikel bevat tips om valse negatieven te voorkomen.

U ongewenste e-mailberichten op de volgende manieren verzenden:

- Voor webgebruikers outlook en Outlook voor de webgebruikers gebruikt u de invoegtoepassing Berichtrapport voor Microsoft Outlook. Zie [Invoegtoepassing Rapportbericht inschakelen](enable-the-report-message-add-in.md)voor informatie over het installeren en gebruiken van deze tool.

- U ook e-mail gebruiken om berichten aan Microsoft in te dienen die moeten worden geclassificeerd als ongewenste of phishing-scams, zoals beschreven in de volgende procedure.

### <a name="use-email-to-submit-junk-spam-or-phishing-scam-messages-to-microsoft"></a>E-mail gebruiken om ongewenste (spam) of phishing-scamberichten naar Microsoft te verzenden

Ga als lid van microsoft over een scambericht voor ongewenste e-mail of phishing:

1. Maak een leeg e-mailbericht.

2. Adres het bericht aan het Microsoft-team dat berichten als volgt beoordeelt:

   - Voor ongewenste berichten: junk@office365.microsoft.com

   - Voor phishing scam berichten: phish@office365.microsoft.com

3. Kopieer en plak de junk of phishing scam bericht in het nieuwe bericht als een bijlage.

   > [!NOTE]
   > • U meerdere berichten toevoegen in het nieuwe bericht. Zorg ervoor dat alle berichten hetzelfde type zijn: phishing-scamberichten of ongewenste e-mailberichten. <br/><br/>• Laat het lichaam van het nieuwe bericht leeg. <br/><br/>• Gebruik .msg (standaard Outlook-indeling) of .eml (standaard Outlook op de webindeling) voor de bijgevoegde berichten.

4. Klik op **Verzenden**.

## <a name="submit-messages-that-were-tagged-as-junk-but-should-have-been-allowed-through"></a>Berichten verzenden die als ongewenste e-mail zijn getagd, maar die via

Als een bericht ten onrechte is geïdentificeerd als ongewenste e-mail, u het bericht 'fout-positief' indienen bij het Microsoft Spam Analysis Team. De analisten zullen de boodschap evalueren en analyseren. Afhankelijk van de resultaten van de analyse kunnen de filterregels voor spaminhoud voor de hele service worden aangepast om het bericht door te laten gaan.
  
Beheerders kunnen meer informatie over het instellen van spam controleren die van toepassing is op een hele organisatie. Zie [Hoe u ervoor zorgen dat een bericht niet is gemarkeerd als spam.](prevent-email-from-being-marked-as-spam.md) Deze informatie is handig als u controle hebt op administratorniveau en u fout-positieven wilt voorkomen.
  
U op de volgende manieren niet-spamberichten verzenden:

- Als u de map **Bericht verplaatsen naar ongewenste e-mail** gebruikt wanneer u uw inhoudsfilters configureert (dit is de standaardactie), kunnen gebruikers fout-positieve berichten vrijgeven in de map Ongewenste e-mail in Outlook of Outlook (voorheen bekend als de map Ongewenste e-mail van Outlook).

  - Outlook-gebruikers kunnen fout-positieve berichten vrijgeven met de menuoptie **Niet ongewenste** berichten met de rechtermuisknop. Ze moeten het bericht echter via e-mail aan Microsoft voorleggen, zoals blijkt uit de procedure in dit artikel.

  - Webgebruikers van Outlook kunnen fout-positieve berichten vrijgeven en deze naar Microsoft verzenden voor analyse met behulp van de **merkactie als geen ongewenste** actie. Zie [Ongewenste e-mail en phishing melden in de webversie van Outlook voor ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)meer informatie over hoe u dit doen.

- Als u de actie **Bericht quarantaine** gebruikt in plaats van de actie Bericht verplaatsen naar **ongewenste e-mail** wanneer u de inhoudsfilters configureert:

  - Beheerders kunnen in quarantaine geplaatste berichten vrijgeven en deze rapporteren als false positives vanuit het Exchange-beheercentrum. Zie [In quarantaine geplaatste berichten en bestanden beheren als beheerder in Office 365](manage-quarantined-messages-and-files.md)voor meer informatie.

  - Gebruikers kunnen hun eigen spam-quarantaine berichten vrijgeven en ze rapporteren als valse positieven via de volgende kanalen:

  - De gebruikersinterface van het Exchange-beheercentrum (EAC). Zie [In quarantaine geplaatste berichten (eindgebruikers) zoeken en vrijgeven](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie.

  - Spammeldingen van eindgebruikers (als deze zijn ingeschakeld door uw beheerder).

- U e-mail ook gebruiken om berichten aan Microsoft in te dienen die niet als spam moeten worden geclassificeerd. Wanneer u dit doet, moet u ervoor zorgen dat u de stappen in de volgende procedure gebruikt.

### <a name="use-email-to-submit-false-positive-messages"></a>E-mail gebruiken om fout-positieve berichten in te dienen

Gebruik dezelfde procedure als beschreven in de [e-mail gebruiken om ongewenste (spam) of phishing-scamberichten naar de](#use-email-to-submit-junk-spam-or-phishing-scam-messages-to-microsoft) sectie Microsoft te verzenden, maar stuur het bericht naar not_junk@office365.microsoft.com.

## <a name="spam-evaluation-and-rules-deployment"></a>Spamevaluatie en implementatie van regels

Het spamanalyseteam onderzoekt berichten die u indient en past de spamfilters aan om toekomstige ongewenste e-mail te voorkomen. Als gevolg hiervan worden de spamfilters van Office 365 voortdurend verfijnd. Alle ingediende items worden geëvalueerd op netwerkbreed niveau. Fout-positieve inzendingen worden onderzocht en beoordeeld op mogelijke regelaanpassing om toekomstige berichten via de spamfilters toe te staan. Daarom is het melden van de service van false positives en ook valse negatieven (ongefilterde spam) voordelig voor u en alle klanten die gebruik maken van het wereldwijde netwerk. Het spamteam onderzoekt indicatoren binnen elk verzonden bericht, zoals:

- Vanaf adres

- IP-adres verzenden

- Zoekwoorden

- Zinnen

- Frequentie van de transmissie

- Andere trends en patronen

Nadat ze deze informatie hebben bekeken, kan het spamteam wijzigingen aanbrengen in de spamfilterlagen van de service. Voor meer informatie over het spamteam u de volgende video met alleen Engels bekijken:

[Microsoft Exchange Spam-teamvideo](https://youtu.be/-TpX_-GMC7o?hd=1)

Spamevaluatie is een doorlopend proces dat van toepassing is ongeacht de taal of tekenset die van oorsprong is. Omdat een spambericht vaag kan zijn of zelfs tekst in de onderwerp- of berichtentekst kan missen, vertrouwt het spamteam op andere berichtkenmerken om filtering uit te voeren. Dit betekent dat nadat het spamteam een bepaald bericht als spam heeft gevlagd en de nodige wijzigingen in de regelbasis heeft aangebracht, dat bericht in de toekomst wordt geblokkeerd totdat de kenmerken ervan voldoende zijn gewijzigd om onze filters te vermijden. Nieuwe spamregels worden continu geïmplementeerd. De termijnen voor regels voor afzonderlijke inzendingen variëren afhankelijk van de hoeveelheid en de kwaliteit van de inzendingen. Omdat er wereldwijd nieuwe spamregels worden ingesteld voor alle klanten, zullen niet alle afzonderlijke spam-inzendingen resulteren in een nieuwe spamregel.

## <a name="for-more-information"></a>Voor meer informatie

[Bescherming tegen ongewenste e-mail en malware](anti-spam-and-anti-malware-protection.md)
  
[Hoe ervoor te zorgen dat een bericht niet is gemarkeerd als spam](prevent-email-from-being-marked-as-spam.md)
  
[Block email spam with the Office 365 spam filter to prevent false negative issues](reduce-spam-email.md)
  

[Block email spam with the Office 365 spam filter to prevent false negative issues](reduce-spam-email.md)
