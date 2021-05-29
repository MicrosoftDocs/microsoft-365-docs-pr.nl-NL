---
title: Veilige koppelingen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: In dit artikel kunnen beheerders meer informatie krijgen over Safe koppelingen in Defender voor Office 365 om hun organisatie te beschermen tegen phishing en andere aanvallen die kwaadaardige URL's gebruiken.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 675de13410ac98e18a8b72125c2226d2c9c62821
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698986"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>Safe Koppelingen in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](defender-for-office-365.md) hebben. Zie Geavanceerde [Outlook.com-beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)als u Outlook.com, Microsoft 365 Family of Microsoft 365 Personal gebruikt en u op zoek bent naar informatie over Safelinks in Outlook.

Safe Koppelingen is een functie in [Defender voor Office 365](defender-for-office-365.md) met URL's voor het scannen en herschrijven van binnenkomende e-mailberichten in de e-mailstroom en tijd-of-clickverificatie van URL's en koppelingen in e-mailberichten en andere locaties. Safe Het scannen van koppelingen vindt plaats naast de reguliere bescherming tegen spam en [anti-malware](anti-spam-and-anti-malware-protection.md) in binnenkomende e-mailberichten in Exchange Online Protection (EOP). Safe Met koppelingen scannen kunt u uw organisatie beschermen tegen schadelijke koppelingen die worden gebruikt bij phishing en andere aanvallen.

Safe Koppelingenbeveiliging is beschikbaar op de volgende locaties:

- **E-mailberichten:** Safe koppelingenbeveiliging voor koppelingen in e-mailberichten wordt bepaald door Safe Koppelingenbeleid. Er is geen standaardbeleid Safe Koppelingen, dus om de beveiliging van Safe Koppelingen in e-mailberichten te krijgen, moet u een of meer Safe **Koppelingenbeleid maken.** Zie Beleidsregels voor [koppelingen instellen Safe Microsoft Defender voor](set-up-safe-links-policies.md)Office 365.

  Zie de sectie Safe Koppelingen voor e-mailberichten verder in dit artikel voor meer [informatie](#safe-links-settings-for-email-messages) over Safe koppelingenbeveiliging voor e-mailberichten.
  
  > [!NOTE]
  > Safe Koppelingen werken niet in openbare mappen met e-mail.

- **Microsoft Teams** (momenteel in TAP Preview): Safe Koppelingenbeveiliging voor koppelingen in Teams-gesprekken, groepschats of vanuit kanalen wordt ook bepaald door Safe Koppelingenbeleid. Er is geen standaardbeleid Safe Koppelingen, dus als u de beveiliging van Safe Koppelingen in Teams wilt krijgen, moet u een of meer Safe **Koppelingenbeleid maken.**

  Zie de instellingen Safe Koppelingen voor Microsoft Teams in dit [](#safe-links-settings-for-microsoft-teams) artikel voor meer informatie over Safe koppelingenbeveiliging in Teams pagina.

- **Office 365 apps:** Safe koppelingenbeveiliging voor Office 365 apps is beschikbaar in ondersteunde bureaublad-, mobiele en web-apps. U **configureert** Safe koppelingenbeveiliging voor Office 365 apps in de algemene instelling die buiten **het** beleid Safe Koppelingen. Zie Algemene instellingen configureren voor Safe [koppelingen in Microsoft Defender voor Office 365.](configure-global-settings-for-safe-links.md)

  Safe Koppelingenbescherming voor Office 365-apps wordt toegepast op alle gebruikers in de organisatie die een licentie hebben voor Defender voor Office 365, ongeacht of de gebruikers zijn opgenomen in het beleid voor actieve Safe Koppelingen of niet.

  Zie de Safe koppelingen voor Office 365 apps verder in dit artikel voor meer informatie over Safe koppelingenbeveiliging in Office 365 [apps.](#safe-links-settings-for-office-365-apps)

Dit artikel bevat gedetailleerde beschrijvingen van de volgende typen Safe Koppelingen:

- **Instellingen in Safe Koppelingenbeleid:** Deze instellingen zijn alleen van toepassing op de gebruikers die zijn opgenomen in het specifieke beleid en de instellingen kunnen verschillen tussen beleidsregels. Deze instellingen omvatten:

  - [Safe Koppelingeninstellingen voor e-mailberichten](#safe-links-settings-for-email-messages)
  - [Safe Koppelingeninstellingen voor Microsoft Teams](#safe-links-settings-for-microsoft-teams)
  - [Lijsten met 'De volgende URL's niet opnieuw schrijven' in Safe koppelingenbeleid](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **Algemene Safe Koppelingen:** deze instellingen zijn globaal geconfigureerd, niet in Safe Koppelingenbeleid. Deze instellingen omvatten:

  - [Safe Koppelingeninstellingen voor Office 365 apps](#safe-links-settings-for-office-365-apps)
  - ['De volgende URL's blokkeren' voor Safe koppelingen](#block-the-following-urls-list-for-safe-links)

In de volgende tabel worden scenario's beschreven voor Safe Koppelingen in Microsoft 365- en Office 365-organisaties met Defender voor Office 365 (met andere woorden: het ontbreken van licenties is nooit een probleem in de voorbeelden).

<br>

****

|Scenario|Resultaat|
|---|---|
|Jean is lid van de marketingafdeling. Safe Koppelingenbeveiliging voor Office 365-apps is ingeschakeld in de algemene instellingen voor Safe Koppelingen en er bestaat een Safe-koppelingenbeleid dat van toepassing is op leden van de marketingafdeling. Jean opent een PowerPoint in een e-mailbericht en klikt vervolgens op een URL in de presentatie.|Jean wordt beveiligd door Safe koppelingen. <p> Jean is opgenomen in een Safe koppelingenbeleid en Safe koppelingenbeveiliging voor Office 365 apps is ingeschakeld. <p> Zie de sectie Safe Koppelingen voor Office 365 apps verder in dit artikel voor meer informatie over de vereisten voor Safe koppelingenbeveiliging in Office 365 [apps.](#safe-links-settings-for-office-365-apps)|
|Chris's Microsoft 365 E5 organisatie heeft geen Safe koppelingen geconfigureerd. Chris ontvangt een e-mail van een externe afzender met een URL naar een schadelijke website waar hij uiteindelijk op klikt.|Chris is niet beveiligd door Safe koppelingen. <p> Een beheerder moet ten minste één Safe koppelingenbeleid maken voor iedereen om de Safe koppelingen te krijgen in binnenkomende e-mailberichten. Chris moet worden opgenomen in de voorwaarden van het beleid om de Safe koppelingen te krijgen.|
|In de organisatie van Pat hebben geen beheerders een Safe Koppelingen gemaakt, maar Safe koppelingenbeveiliging voor Office 365 apps is ingeschakeld. Pat opent een Word-document en klikt op een URL in het bestand.|Pat is niet beveiligd door Safe koppelingen. <p> Hoewel Safe koppelingenbeveiliging voor Office 365-apps globaal is ingeschakeld, is Pat niet opgenomen in een actief Safe-koppelingenbeleid, dus de beveiliging kan niet worden toegepast.|
|In de organisatie van Lee is geconfigureerd in de lijst De volgende URL's blokkeren in de algemene instellingen voor `https://tailspintoys.com` Safe Koppelingen.  Er Safe beleid voor koppelingen met Lee al bestaan. Lee ontvangt een e-mailbericht met de `https://tailspintoys.com/aboutus/trythispage` URL. Lee klikt op de URL.|De URL wordt mogelijk automatisch geblokkeerd voor Lee. dit hangt af van de URL-vermelding in de lijst en de e-mailclient die Lee heeft gebruikt. Zie de lijst ['De](#block-the-following-urls-list-for-safe-links) volgende URL's blokkeren' voor Safe sectie Koppelingen verderop in dit artikel voor meer informatie.|
|Jamie en Julia werken beide voor contoso.com. Lange tijd geleden hebben beheerders het Safe koppelingen ingesteld die van toepassing zijn op zowel Jamie als Julia. Jamie stuurt een e-mail naar Julia, niet wetende dat de e-mail een schadelijke URL bevat.|Julia wordt beveiligd door Safe koppelingen **als** het Safe koppelingenbeleid dat op haar van toepassing is, is geconfigureerd voor berichten tussen interne geadresseerden. Zie de sectie Koppelingen [Safe voor](#safe-links-settings-for-email-messages) e-mailberichten verder in dit artikel voor meer informatie.|
|

## <a name="safe-links-settings-for-email-messages"></a>Safe Koppelingeninstellingen voor e-mailberichten

Safe Koppelingen scant inkomende e-mail op bekende schadelijke hyperlinks. Gescande URL's worden herschreven met het standaard-URL-voorvoegsel van Microsoft: `https://nam01.safelinks.protection.outlook.com` . Nadat de koppeling is herschreven, wordt deze geanalyseerd op potentieel schadelijke inhoud.

Nadat Safe een URL opnieuw hebt geschreven, blijft de URL herschreven, zelfs als het bericht handmatig wordt doorgestuurd of beantwoord (zowel naar interne als externe geadresseerden).  Aanvullende koppelingen die worden toegevoegd aan het doorgestuurde of beantwoorde bericht, worden niet opnieuw geschreven. In het geval  van automatisch doorsturen door Postvak IN-regels of SMTP-doorsturen, wordt de URL  echter niet opnieuw geschreven in het bericht dat is bedoeld voor de uiteindelijke geadresseerde, tenzij deze geadresseerde ook is beveiligd door Safe Koppelingen of de URL al in een eerdere communicatie is herschreven. 

De instellingen in Safe koppelingen die van toepassing zijn op e-mailberichten, worden in de volgende lijst beschreven:

- **Selecteer de actie voor onbekende potentieel schadelijke URL's in berichten:** Hiermee kunt u koppelingen in- Safe in e-mailberichten in- of uitschakelen. De aanbevolen waarde is **Aan**. Als u deze instelling in te stellen, worden de volgende acties als resultaat genomen.

  - Safe Het scannen van koppelingen is ingeschakeld in Outlook (C2R) op Windows.
  - URL's worden herschreven en gebruikers worden omgeleid via Safe koppelingenbeveiliging wanneer ze op URL's in berichten klikken.
  - Wanneer erop wordt geklikt, worden URL's gecontroleerd op een lijst met bekende kwaadaardige URL's en de lijst 'De volgende [URL's blokkeren'.](#block-the-following-urls-list-for-safe-links)
  - URL's die geen geldige reputatie hebben, worden asynchroon op de achtergrond tot ontploffing gebracht.

- **Realtime URL-scan toepassen** op verdachte koppelingen en koppelingen die naar bestanden wijzen: Hiermee kunt u in realtime koppelingen scannen, inclusief koppelingen in e-mailberichten die naar downloadbare inhoud wijzen. De aanbevolen waarde is ingeschakeld.
  - **Wacht totdat URL-scannen is voltooid voordat u het bericht bezorgt:**
    - Ingeschakeld: Berichten die URL's bevatten, worden opgeslagen totdat het scannen is voltooid. Berichten worden alleen bezorgd nadat is bevestigd dat de URL's veilig zijn. Dit is de aanbevolen waarde.
    - Uitgeschakeld: Als URL-scannen niet kan worden voltooid, bezorgt u het bericht toch.

- **Safe** Koppelingen toepassen op e-mailberichten die binnen de organisatie worden verzonden: Hiermee kunt u Safe Koppelingen scannen op berichten die tussen interne afzenders en interne geadresseerden binnen dezelfde organisatie Exchange Online worden verzonden. De aanbevolen waarde is ingeschakeld.

- **Gebruikersklikken niet bijhouden:** Hiermee kunt u het opslaan van koppelingen in- of uitschakelen Safe klikken op gegevens voor URL's die in e-mailberichten zijn geklikt. De aanbevolen waarde is om deze instelling niet geselecteerd te laten (om klikken van gebruikers bij te houden).

  URL-klik op bijhouden voor koppelingen in e-mailberichten die tussen interne afzenders en interne geadresseerden worden verzonden, wordt momenteel niet ondersteund.

- **Gebruikers mogen niet doorklikken** naar de oorspronkelijke URL: Hiermee [](#warning-pages-from-safe-links) kunnen gebruikers niet door de waarschuwingspagina naar de oorspronkelijke URL klikken. De aanbevolen waarde is ingeschakeld.

- **De huisstijl van de organisatie weergeven op meldings-** en waarschuwingspagina's: deze optie toont de huisstijl van uw organisatie op waarschuwingspagina's. Met huisstijl kunnen gebruikers legitieme waarschuwingen identificeren, omdat standaardwaarschuwingspagina's van Microsoft vaak worden gebruikt door aanvallers. Zie Het thema Microsoft 365 uw organisatie aanpassen voor meer informatie over [aangepaste huisstijl.](../../admin/setup/customize-your-organization-theme.md)

- **De volgende URL's niet opnieuw schrijven:** URL's blijven zoals ze zijn. Er wordt een aangepaste lijst met veilige URL's bijhoudt die niet hoeven te worden gescand. De lijst is uniek voor elk Safe koppelingenbeleid. Zie de sectie  'De volgende URL's niet herschrijven' in de sectie Beleidsregels voor [Safe Koppelingen](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) verder in dit artikel voor meer informatie over de lijst Niet opnieuw schrijven van de volgende URL's.

  Zie voor meer informatie over de aanbevolen waarden voor standaard- en strikte beleidsinstellingen voor Safe koppelingenbeleid Safe [Beleidsinstellingen voor koppelingen](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).

- **Filters voor geadresseerden:** u moet de voorwaarden en uitzonderingen voor de geadresseerde opgeven die bepalen op wie het beleid van toepassing is. U kunt deze eigenschappen gebruiken voor voorwaarden en uitzonderingen:
  - **De geadresseerde is**
  - **Het domein van de geadresseerde is**
  - **De geadresseerde is lid van**

  U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar de voorwaarde of uitzondering kan meerdere waarden bevatten. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

- **Prioriteit:** Als u meerdere beleidsregels maakt, kunt u de volgorde opgeven waarin ze worden toegepast. Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

  Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).
  
### <a name="how-safe-links-works-in-email-messages"></a>Hoe Safe koppelingen werkt in e-mailberichten

Op hoog niveau werkt de beveiliging van Safe koppelingen op URL's in e-mailberichten als volgende:

1. Alle e-mail gaat via EOP, waar internetprotocol- en envelopfilters, malwarebeveiliging op basis van handtekeningen, antispam en anti-malwarefilters worden gebruikt voordat het bericht wordt bezorgd in het postvak van de geadresseerde.

2. De gebruiker opent het bericht in zijn postvak en klikt op een URL in het bericht.

3. Safe Koppelingen controleren onmiddellijk de URL voordat u de website opent:

   - Als de URL is opgenomen in de lijst **De volgende URL's** blokkeren, wordt een [geblokkeerde URL-waarschuwing](#blocked-url-warning) geopend.

   - Als de URL naar een website wijst die schadelijk is, wordt er een waarschuwingspagina voor schadelijke [websites](#malicious-website-warning) (of een andere waarschuwingspagina) geopend.

   - Als de URL naar een downloadbaar bestand wijst en het scannen van **url's in realtime** toepassen op verdachte koppelingen en koppelingen naar de instelling voor bestanden is ingeschakeld in het beleid dat van toepassing is op de gebruiker, wordt het downloadbare bestand ingeschakeld.

   - Als de URL veilig is, wordt de website geopend.

## <a name="safe-links-settings-for-microsoft-teams"></a>Safe Koppelingeninstellingen voor Microsoft Teams

> [!IMPORTANT]
> Vanaf maart 2020 is deze functie beschikbaar in Preview en is alleen beschikbaar voor leden van het Microsoft Teams Technology Adoption Program (TAP). Voor meer informatie over de releaseplanning raadpleegt u [de Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams).

U schakelt de beveiliging van Safe koppelingen in of uit voor Microsoft Teams in Safe koppelingenbeleid. In het bijzonder gebruikt u de actie Selecteren voor onbekende of potentieel schadelijke **URL's binnen Microsoft Teams** instelling. De aanbevolen waarde is **Aan**.

De volgende instellingen in Safe Koppelingenbeleid dat van toepassing is op koppelingen in e-mailberichten, zijn ook van toepassing op koppelingen in Teams:

- **Realtime URL-scan toepassen op verdachte koppelingen en koppelingen die naar bestanden wijzen**
- **Gebruikersklikken niet bijhouden**
- **Gebruikers niet toestaan door te klikken naar de oorspronkelijke URL**

Deze instellingen worden eerder uitgelegd in [Safe Instellingen voor koppelingen voor e-mailberichten.](#safe-links-settings-for-email-messages)

Nadat u Safe Koppelingenbeveiliging voor Microsoft Teams hebt ingeschakeld, worden URL's in Teams gecontroleerd op een lijst met bekende schadelijke koppelingen wanneer de beveiligde gebruiker op de koppeling klikt (time-of-click protection). URL's worden niet herschreven. Als een koppeling schadelijk blijkt te zijn, hebben gebruikers de volgende ervaringen:

- Als op de koppeling is geklikt in een Teams gesprek, groepschat of via kanalen, wordt de waarschuwingspagina zoals weergegeven in de onderstaande schermafbeelding weergegeven in de standaardwebbrowser.
- Als op de koppeling is geklikt vanaf een vastgemaakt tabblad, wordt de waarschuwingspagina weergegeven in de Teams interface op dat tabblad. De optie om de koppeling in een webbrowser te openen, is uitgeschakeld om beveiligingsredenen.
- Afhankelijk van de manier waarop gebruikers niet mogen doorklikken naar de oorspronkelijke **URL-instelling** in het beleid, kan de gebruiker wel of niet doorklikken naar de oorspronkelijke URL ( Toch doorgaan **(niet aanbevolen)** in de schermafbeelding). U wordt aangeraden de instelling Gebruikers **niet** toestaan door te klikken naar de oorspronkelijke URL-instelling, zodat gebruikers niet door kunnen klikken naar de oorspronkelijke URL.

Als de gebruiker die de koppeling heeft verzonden, niet is opgenomen in een Safe-koppelingsbeleid waarin Teams-beveiliging is ingeschakeld, kan de gebruiker doorklikken naar de oorspronkelijke URL op zijn of haar computer of apparaat.

![Een Safe Koppelingen voor Teams pagina die een schadelijke koppeling meldt.](../../media/tp-safe-links-for-teams-malicious.png)

Als u op **de knop Teruggaan op** de waarschuwingspagina klikt, wordt de gebruiker terug naar de oorspronkelijke context of URL-locatie. Als u echter nogmaals op de oorspronkelijke koppeling klikt, Safe koppelingen de URL opnieuw scannen, zodat de waarschuwingspagina opnieuw wordt weergegeven.

### <a name="how-safe-links-works-in-teams"></a>Hoe Safe koppelingen werken in Teams

Op een hoog niveau werkt Safe koppelingen voor URL's in Microsoft Teams:

1. Een gebruiker start de Teams app.

2. Microsoft 365 controleert of de organisatie van de gebruiker Microsoft Defender voor Office 365 bevat en dat de gebruiker is opgenomen in een actief Safe-koppelingenbeleid waarin beveiliging voor Microsoft Teams is ingeschakeld.

3. URL's worden gevalideerd op het moment van klikken voor de gebruiker in chats, groepschats, kanalen en tabbladen.

## <a name="safe-links-settings-for-office-365-apps"></a>Safe Koppelingeninstellingen voor Office 365 apps

Safe Koppelingenbeveiliging voor Office 365 apps controleert koppelingen in Office-documenten, niet koppelingen in e-mailberichten (maar het kan koppelingen controleren in bijgevoegde Office documenten in e-mailberichten nadat het document is geopend).

Safe Koppelingenbeveiliging voor Office 365 apps heeft de volgende clientvereisten:

- Microsoft 365-apps of Microsoft 365 Business Premium.
  - Huidige versies van Word, Excel en PowerPoint op Windows, Mac of in een webbrowser.
  - Office apps op iOS- of Android-apparaten.
  - Visio op Windows.
  - OneNote in een webbrowser.

- Office 365 apps zijn geconfigureerd voor moderne verificatie. Zie Hoe moderne verificatie werkt Office [2013, Office 2016 en Office 2019 client-apps](../../enterprise/modern-auth-for-office-2013-and-2016.md)voor meer informatie.

- Gebruikers zijn aangemeld met hun werk- of schoolaccounts. Zie Aanmelden bij [Office.](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)

U configureert Safe koppelingenbeveiliging voor Office 365 apps in de algemene instellingen voor Safe koppelingen, niet in Safe koppelingenbeleid. De beveiliging wordt toegepast op alle gebruikers in de organisatie die een licentie hebben voor Defender voor Office 365, ongeacht of de gebruikers zijn opgenomen in het beleid voor actieve Safe Koppelingen of niet.

De volgende Safe koppelingen zijn beschikbaar voor Office 365 apps:

- **Office 365 toepassingen:** Hiermee schakelt u het scannen Safe koppelingen in ondersteunde Office 365 uit. De standaardwaarde en aanbevolen waarde is **Aan**.

- Niet bijhouden wanneer gebruikers op Safe Koppelingen **klikken:** Het opslaan van Safe Koppelingen wordt in- of uitgeschakeld op gegevens voor URL's waarop in de bureaubladversies word, Excel, PowerPoint en Visio. De aanbevolen waarde is **Uit,** wat betekent dat gebruikersklikken worden bijgespoord.

- **Laat gebruikers niet** door veilige koppelingen naar de oorspronkelijke URL klikken: hiermee kunnen gebruikers niet door de waarschuwingspagina klikken naar de oorspronkelijke URL in de bureaubladversies word, Excel, PowerPoint en Visio. [](#warning-pages-from-safe-links) De standaardwaarde en aanbevolen waarde is **Aan**.

Als u de instellingen voor Safe koppelingen voor Office 365 apps wilt configureren, gaat u naar Beveiliging Safe koppelingen configureren [voor Office 365 apps.](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)

Zie Algemene instellingen voor Safe koppelingen voor meer informatie over de aanbevolen waarden [voor standaard- en strikte beleidsinstellingen.](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links)

### <a name="how-safe-links-works-in-office-365-apps"></a>Hoe Safe koppelingen werken in Office 365 apps

Op hoog niveau werkt Safe koppelingenbeveiliging voor URL's in Office 365 apps. De ondersteunde Office 365 apps worden beschreven in de vorige sectie.

1. Een gebruiker meldt zich aan met zijn of haar werk- of schoolaccount in een organisatie met Microsoft 365-apps of Microsoft 365 Business Premium.

2. De gebruiker wordt geopend en klikt op een koppeling Office document in een ondersteunde Office-app.

3. Safe Koppelingen controleren onmiddellijk de URL voordat u de doelwebsite opent:

   - Als de URL is opgenomen in de lijst die het  scannen van koppelingen Safe (de lijst De volgende URL's blokkeren) wordt een geblokkeerde [URL-waarschuwingspagina](#blocked-url-warning) geopend.

   - Als de URL naar een website wijst die schadelijk is, wordt er een waarschuwingspagina voor schadelijke [websites](#malicious-website-warning) (of een andere waarschuwingspagina) geopend.

   - Als de URL naar een downloadbaar bestand wijst en het beleid voor Safe-koppelingen dat van toepassing is op de gebruiker is geconfigureerd voor het scannen van koppelingen naar downloadbare inhoud ( Realtime **URL-scan** toepassen op verdachte koppelingen en koppelingen die naar bestanden wijzen), wordt het downloadbare bestand ingeschakeld.

   - Als de URL als veilig wordt beschouwd, wordt de gebruiker naar de website overgebracht.

   - Als Safe koppelingen scannen niet kan worden voltooid, wordt Safe koppelingenbeveiliging niet triggert. In Office desktopcl clients wordt de gebruiker gewaarschuwd voordat hij of zij naar de doelwebsite gaat.

> [!NOTE]
> Het kan enkele seconden duren aan het begin van elke sessie om te controleren of de gebruiker koppelingen Safe voor Office ingeschakeld.

## <a name="block-the-following-urls-list-for-safe-links"></a>'De volgende URL's blokkeren' voor Safe koppelingen

In **de lijst De volgende URL's** blokkeren worden de koppelingen definieerd die altijd worden geblokkeerd door Safe Koppelingen scannen op de volgende locaties:

- E-mailberichten.
- Documenten in Office 365 apps in Windows mac.
- Documenten in Office voor iOS en Android.

Wanneer een gebruiker in een actief Safe koppelingenbeleid op een geblokkeerde koppeling in een ondersteunde app klikt, worden deze naar de waarschuwingspagina voor geblokkeerde [URL's](#blocked-url-warning) geplaatst.

U configureert de lijst met URL's in de algemene instellingen voor Safe koppelingen. Zie De lijst ['De volgende URL's blokkeren' configureren](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)voor instructies.

**Opmerkingen**:

- Zie De lijst tenant [toestaan/blokkeren](tenant-allow-block-list.md)beheren voor een werkelijk universele lijst met URL's die overal worden geblokkeerd.
- Limieten voor **de lijst Met de volgende URL's** blokkeren:
  - Het maximum aantal vermeldingen is 500.
  - De maximale lengte van een item is 128 tekens.
  - Alle vermeldingen mogen niet meer dan 10.000 tekens bevatten.
- Voeg geen slash () toe aan het `/` einde van de URL. Gebruik bijvoorbeeld `https://www.contoso.com` , niet `https://www.contoso.com/` .
- Een domein-alleen-URL (bijvoorbeeld `contoso.com` of ) blokkeert elke URL die het domein `tailspintoys.com` bevat.
- U kunt een subdomein blokkeren zonder het volledige domein te blokkeren. Blokkeert bijvoorbeeld een URL die het subdomein bevat, maar geen URL's die het volledige domein `toys.contoso.com*` `contoso.com` bevatten.
- U kunt maximaal drie jokertekens `*` () per URL-vermelding opnemen.

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>Syntaxis van invoer voor de lijst 'De volgende URL's blokkeren'

Voorbeelden van de waarden die u kunt invoeren en de resultaten daarvan worden in de volgende tabel beschreven:

<br>

****

|Waarde|Resultaat|
|---|---|
|`contoso.com` <p> of <p> `*contoso.com*`|Blokkeert het domein, subdomeinen en paden. Bijvoorbeeld, `https://www.contoso.com` en `https://sub.contoso.com` worden `https://contoso.com/abc` geblokkeerd.|
|`https://contoso.com/a`|Blokken, `https://contoso.com/a` maar geen extra subpaden zoals `https://contoso.com/a/b` .|
|`https://contoso.com/a*`|Blokken `https://contoso.com/a` en extra subpaden zoals `https://contoso.com/a/b` .|
|`https://toys.contoso.com*`|Hiermee blokkeert u een subdomein `toys` (in dit voorbeeld), maar kunt u klikken op andere domein-URL's (zoals `https://contoso.com` of `https://home.contoso.com` ).|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>Lijsten met 'De volgende URL's niet opnieuw schrijven' in Safe koppelingenbeleid

> [!NOTE]
> Als uw organisatie gebruik Safe koppelingenbeleid, zijn de volgende **URL'slijsten** niet opnieuw schrijven de enige ondersteunde methode voor phishingtests van derden.

Elk Safe koppelingenbeleid bevat de volgende **URL's** die u kunt gebruiken om URL's op te geven die niet worden herschreven door het scannen Safe koppelingen. Met andere woorden, met de lijst kunnen gebruikers die zijn opgenomen in het beleid, toegang krijgen tot de opgegeven URL's die anders zouden worden geblokkeerd door Safe Koppelingen. U kunt verschillende lijsten configureren in verschillende Safe koppelingenbeleid. De beleidsverwerking stopt nadat het eerste beleid (waarschijnlijk de hoogste prioriteit) is toegepast op de gebruiker. De volgende  URL'slijst niet opnieuw schrijven, wordt dus toegepast op een gebruiker die is opgenomen in meerdere actieve Safe Koppelingenbeleid.

Zie Beleidsregels voor koppelingen maken Safe Koppelingen maken of [](set-up-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) Beleidsregels wijzigen Safe koppelingen als u items wilt toevoegen aan de lijst in nieuwe of bestaande Safe [koppelingenbeleid.](set-up-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)

**Opmerkingen**:

- De volgende clients herkennen de lijst Niet opnieuw schrijven van de volgende **URL's** in Safe Koppelingenbeleid. Gebruikers die zijn opgenomen in de politie kunnen worden geblokkeerd voor toegang tot de URL's op basis van de resultaten van Safe Koppelingen scannen in deze clients:
  - Microsoft Teams
  - Office web-apps

  Zie De lijst tenant toestaan/blokkeren beheren voor een werkelijk universele lijst met URL's die overal [zijn toegestaan.](tenant-allow-block-list.md)

- U kunt veelgebruikte interne URL's toevoegen aan de lijst om de gebruikerservaring te verbeteren. Als u bijvoorbeeld on-premises services hebt, zoals Skype voor Bedrijven of SharePoint, kunt u deze URL's toevoegen om ze uit te sluiten van scannen.
- Als u de volgende **URL's** in uw Safe-koppelingenbeleid niet opnieuw hebt geschreven, controleert u de lijsten en voegt u indien nodig jokertekens toe. Uw lijst heeft bijvoorbeeld een vermelding zoals `https://contoso.com/a` en u besluit later subpathen zoals `https://contoso.com/a/b` . In plaats van een nieuw item toe te voegen, voegt u een jokerteken toe aan de bestaande vermelding, zodat deze wordt `https://contoso.com/a/*` .
- U kunt maximaal drie jokertekens `*` () per URL-vermelding opnemen. Jokertekens bevatten expliciet voorvoegsels of subdomeinen. De vermelding is bijvoorbeeld niet hetzelfde als , omdat personen subdomeinen en paden in het `contoso.com` `*.contoso.com/*` opgegeven domein kunnen `*.contoso.com/*` bezoeken.
- Als voor een URL automatische omleiding voor HTTP naar HTTPS wordt gebruikt (bijvoorbeeld 302 omleiding voor naar) en u probeert zowel HTTP- als HTTPS-vermeldingen in te voeren voor dezelfde URL in de lijst, ziet u mogelijk dat het tweede URL-item de eerste `http://www.contoso.com` `https://www.contoso.com` URL-vermelding vervangt. Dit gedrag treedt niet op als de HTTP- en HTTPS-versies van de URL volledig van elkaar zijn gescheiden.

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>Syntaxis van invoer voor de lijst 'De volgende URL's niet opnieuw schrijven'

Voorbeelden van de waarden die u kunt invoeren en de resultaten daarvan worden in de volgende tabel beschreven:

<br>

****

|Waarde|Resultaat|
|---|---|
|`contoso.com`|Hiermee kunt u toegang `https://contoso.com` krijgen tot subdomeinen of paden, maar niet tot subdomeinen.|
|`*.contoso.com/*`|Hiermee kunt u toegang krijgen tot een domein, subdomeinen en paden (bijvoorbeeld `https://www.contoso.com` , `https://www.contoso.com` of `https://maps.contoso.com` `https://www.contoso.com/a` ). <p> Dit item is inherent beter dan , omdat er geen mogelijk `*contoso.com*` frauduleuze sites, zoals `https://www.falsecontoso.com` of `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Hiermee kunt u `https://contoso.com/a` toegang krijgen tot , maar geen subpaden zoals `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Hiermee kunt u `https://contoso.com/a` toegang krijgen tot en subpathen zoals `https://contoso.com/a/b`|
|

## <a name="warning-pages-from-safe-links"></a>Waarschuwingspagina's van Safe Koppelingen

Deze sectie bevat voorbeelden van de verschillende waarschuwingspagina's die worden geactiveerd door Safe Koppelingenbeveiliging wanneer u op een URL klikt.

Houd er rekening mee dat verschillende waarschuwingspagina's zijn bijgewerkt. Als u de bijgewerkte pagina's nog niet ziet, zult u dit binnenkort doen. De bijgewerkte pagina's bevatten een nieuw kleurenschema, meer details en de mogelijkheid om door te gaan naar een site, ondanks de opgegeven waarschuwing en aanbevelingen.

### <a name="scan-in-progress-notification"></a>Melding scannen in voortgang

De geklikte URL wordt gescand door Safe Koppelingen. Mogelijk moet u even wachten voordat u de koppeling opnieuw probeert.

![Melding 'De koppeling wordt gescand'](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

De oorspronkelijke meldingspagina ziet er als volgende uit:

![Oorspronkelijke melding 'De koppeling wordt gescand'](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a>Waarschuwing voor verdacht bericht

De geklikte URL stond in een e-mailbericht dat lijkt op andere verdachte berichten. U wordt aangeraden het e-mailbericht te controleren voordat u naar de site gaat.

!['Er is op een koppeling geklikt vanuit een verdacht bericht'.](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a>Waarschuwing voor phishingpogingen

De geklikte URL stond in een e-mailbericht dat is geïdentificeerd als een phishing-aanval. Hierdoor worden alle URL's in het e-mailbericht geblokkeerd. U wordt aangeraden niet naar de site te gaan.

!['De koppeling is geklikt vanuit een phishingbericht' waarschuwing](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a>Waarschuwing voor schadelijke website

De geklikte URL wijst naar een site die is geïdentificeerd als schadelijk. U wordt aangeraden niet naar de site te gaan.

!['Deze website is geclassificeerd als schadelijk' waarschuwing](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

De oorspronkelijke waarschuwingspagina ziet er als volgende uit:

![Oorspronkelijke waarschuwing 'Deze website is geclassificeerd als schadelijk'.](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a>Waarschuwing voor geblokkeerde URL

De geklikte URL is handmatig geblokkeerd door een beheerder in uw organisatie (de lijst De volgende **URL's** blokkeren in de algemene instellingen voor Safe Koppelingen). De koppeling is niet gescand door Safe koppelingen omdat deze handmatig is geblokkeerd.

Er zijn verschillende redenen waarom een beheerder handmatig specifieke URL's blokkeert. Als u denkt dat de site niet moet worden geblokkeerd, neem dan contact op met uw beheerder.

![Waarschuwing 'Deze website is geblokkeerd door uw beheerder'.](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

De oorspronkelijke waarschuwingspagina ziet er als volgende uit:

![Oorspronkelijke waarschuwing 'Deze website is geblokkeerd volgens het URL-beleid van uw organisatie'.](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a>Foutwaarschuwing

Er is een fout opgetreden en de URL kan niet worden geopend.

![De waarschuwing 'De pagina die u probeert te openen, kan niet worden geladen'.](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

De oorspronkelijke waarschuwingspagina ziet er als volgende uit:

![Oorspronkelijke waarschuwing 'Deze webpagina kan niet worden geladen'.](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
