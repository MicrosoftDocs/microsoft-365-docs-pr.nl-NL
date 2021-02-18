---
title: Veilige koppelingen
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
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
description: In dit artikel kunnen beheerders meer informatie krijgen over de beveiliging van veilige koppelingen in Defender voor Office 365 om hun organisatie te beschermen tegen phishing en andere aanvallen die schadelijke URL's gebruiken.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 15168f2fff5ce1e4afbef5ff71a780de896f0bbf
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288691"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>Veilige koppelingen in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](office-365-atp.md) hebben. Als u Outlook.com, Microsoft 365 Family of Microsoft 365 Personal gebruikt en op zoek bent naar informatie over Safelinks in Outlook, gaat u naar [Advanced Outlook.com security.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Veilige koppelingen is een functie in Defender voor [Office 365](office-365-atp.md) waarmee inkomende e-mailberichten in de e-mailstroom kunnen worden gescand en herschreven met URL's en koppelingen in e-mailberichten en andere locaties via een time-of-click-verificatie. Het scannen van veilige koppelingen vindt plaats naast de reguliere bescherming tegen spam en malware in binnenkomende [e-mailberichten](anti-spam-and-anti-malware-protection.md) in Exchange Online Protection (EOP). Met safe links scannen kunt u uw organisatie beschermen tegen schadelijke koppelingen die worden gebruikt bij phishing en andere aanvallen.

Beveiliging van veilige koppelingen is beschikbaar op de volgende locaties:

- **E-mailberichten:** beveiliging tegen veilige koppelingen voor koppelingen in e-mailberichten wordt bepaald door het beleid voor veilige koppelingen. Er is geen standaardbeleid voor veilige koppelingen. Om de beveiliging van veilige koppelingen in e-mailberichten te krijgen, moet u een of meer beleidsregels voor veilige koppelingen **maken.** Zie Beleidsregels voor veilige [koppelingen instellen in Microsoft Defender voor Office 365](set-up-atp-safe-links-policies.md)voor instructies.

  Zie de sectie Veilige koppelingen voor e-mailberichten verderf in dit artikel voor meer informatie over het beschermen van veilige koppelingen voor e-mailberichten. [](#safe-links-settings-for-email-messages)

- **Microsoft Teams** (momenteel in de preview-versie van TAP): Beveiliging van veilige koppelingen voor koppelingen in Teams-gesprekken, groepschats of van kanalen wordt ook bepaald door beleidsregels voor veilige koppelingen. Er is geen standaardbeleid voor veilige koppelingen. Om de beveiliging van veilige koppelingen in Teams te krijgen, moet u een of meer beleidsregels voor veilige koppelingen **maken.**

  Voor meer informatie over beveiliging tegen veilige koppelingen in Teams, bekijkt u de sectie Met veilige koppelingen voor [Microsoft Teams](#safe-links-settings-for-microsoft-teams) verder op dit artikel.

- **Office 365-apps:** Beveiliging tegen veilige koppelingen voor Office 365-apps is beschikbaar in ondersteunde desktop-, mobiele en web-aps. U **configureert** beveiliging tegen veilige koppelingen voor Office 365-apps in de globale instelling die buiten het beleid voor veilige koppelingen wordt gebruikt.  Zie Algemene instellingen [configureren voor instellingen voor veilige koppelingen in Microsoft Defender voor Office 365](configure-global-settings-for-safe-links.md)voor instructies.

  Beveiliging van veilige koppelingen voor Office 365-apps wordt echter alleen toegepast op gebruikers die zijn opgenomen in het actieve beleid voor veilige koppelingen.  Als een gebruiker niet is opgenomen in een actief beleid voor veilige koppelingen, wordt de gebruiker niet beschermd tegen veilige koppelingen in ondersteunde Office 365-apps.

  Zie de sectie Veilige koppelingen voor Office 365-apps verderf in dit artikel voor meer informatie over het beveiliging van veilige koppelingen in [Office 365-apps.](#safe-links-settings-for-office-365-apps)

Dit artikel bevat gedetailleerde beschrijvingen van de volgende typen instellingen voor veilige koppelingen:

- **Instellingen in beleidsregels voor** veilige koppelingen: deze instellingen zijn alleen van toepassing op de gebruikers die zijn opgenomen in het specifieke beleid en de instellingen kunnen verschillen tussen beleidsregels. Dit zijn onder andere de volgende instellingen:

  - [Instellingen voor veilige koppelingen voor e-mailberichten](#safe-links-settings-for-email-messages)
  - [Instellingen voor veilige koppelingen voor Microsoft Teams](#safe-links-settings-for-microsoft-teams)
  - [Lijsten met 'De volgende URL's niet herschrijven' in beleidsregels voor veilige koppelingen](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **Algemene instellingen voor veilige koppelingen:** deze instellingen worden globaal geconfigureerd, niet in het beleid voor veilige koppelingen. De instellingen zijn echter alleen van toepassing op gebruikers die zijn opgenomen in het actieve beleid voor veilige koppelingen. Dit zijn onder andere de volgende instellingen:

  - [Instellingen voor veilige koppelingen voor Office 365-apps](#safe-links-settings-for-office-365-apps)
  - [Lijst 'De volgende URL's blokkeren' voor Veilige koppelingen](#block-the-following-urls-list-for-safe-links)

In de volgende tabel worden scenario's beschreven voor veilige koppelingen in Microsoft 365- en Office 365-organisaties die Defender voor Office 365 bevatten (met andere woorden, het ontbreken van licenties is nooit een probleem in de voorbeelden).

****

|Scenario|Resultaat|
|---|---|
|John is lid van de marketingafdeling. Beveiliging tegen veilige koppelingen voor Office 365-apps is ingeschakeld in de algemene instellingen voor veilige koppelingen en er is een beleid voor veilige koppelingen van toepassing op leden van de marketingafdeling. In een e-mailbericht opent John een PowerPoint-presentatie en klikt u vervolgens op een URL in de presentatie.|Jean wordt beveiligd door veilige koppelingen. <p> John is opgenomen in een beleid voor veilige koppelingen en beveiliging tegen veilige koppelingen voor Office 365-apps is ingeschakeld. <p> Zie de sectie Met veilige koppelingen voor Office 365-apps verderf in dit artikel voor meer informatie over de vereisten voor beveiliging van veilige koppelingen in Office [365-apps.](#safe-links-settings-for-office-365-apps)|
|Voor chris's Microsoft 365 E5-organisatie is geen beleid voor veilige koppelingen geconfigureerd. Chris ontvangt een e-mailbericht van een externe afzender met een URL naar een schadelijke website die hij uiteindelijk heeft geklikt.|Chris wordt niet beveiligd door veilige koppelingen. <p> Een beheerder moet ten minste één beleid voor veilige koppelingen maken dat iedereen inkomende e-mailberichten met veilige koppelingen kan persoonsgegevens bieden. Chris moet worden opgenomen in de beleidsvoorwaarden om veilige koppelingen te veilig te maken.|
|In de organisatie van Pat hebben geen beheerders beleidsregels voor veilige koppelingen gemaakt, maar beveiliging voor veilige koppelingen voor Office 365-apps is ingeschakeld. Pat opent een Word-document en klikt op een URL in het bestand.|Pat wordt niet beveiligd door veilige koppelingen. <p> Hoewel beveiliging van veilige koppelingen voor Office 365-apps globaal wordt ingeschakeld, is Pat niet opgenomen in actieve beleidsregels voor veilige koppelingen, zodat de beveiliging niet kan worden toegepast.|
|In de organisatie van Luwte is geconfigureerd in de lijst De volgende URL's blokkeren `https://tailspintoys.com` in de algemene instellingen voor veilige koppelingen.  Er bestaat al een beleid voor veilige koppelingen met Lee. Lee ontvangt een e-mailbericht met de `https://tailspintoys.com/aboutus/trythispage` URL. Luwje klikt op de URL.|De URL wordt mogelijk automatisch geblokkeerd voor Lusje; Dit hangt af van de URL-vermelding in de lijst en van de e-mailclient Lee. Zie de lijst 'De volgende [URL's blokkeren'](#block-the-following-urls-list-for-safe-links) voor de sectie Veilige koppelingen verderop in dit artikel.|
|Jamie en Julia werken beide voor contoso.com. Lang geleden hebben beheerders beleidsregels voor veilige koppelingen geconfigureerd die van toepassing zijn op zowel Jamie als Julia. Jamie stuurt een e-mailbericht naar Julia, niet wetende dat het e-mailbericht een schadelijke URL bevat.|Julia wordt beveiligd door veilige koppelingen **als** het beleid voor veilige koppelingen dat op haar van toepassing is, is geconfigureerd voor berichten tussen interne geadresseerden. Zie de sectie Veilige koppelingen [voor](#safe-links-settings-for-email-messages) e-mailberichten verder op dit artikel voor meer informatie.|

## <a name="safe-links-settings-for-email-messages"></a>Instellingen voor veilige koppelingen voor e-mailberichten

Met veilige koppelingen scant u inkomende e-mail op bekende schadelijke hyperlinks. Gescande URL's worden herschreven met het standaard-URL-voorvoegsel van `https://nam01.safelinks.protection.outlook.com` Microsoft: Nadat de koppeling is herschreven, wordt deze geanalyseerd op mogelijk schadelijke inhoud.

Nadat een URL opnieuw is geschreven met Veilige koppelingen,  blijft de URL herschreven, zelfs als het bericht handmatig wordt doorgestuurd of beantwoord (zowel aan interne als externe geadresseerden). Extra koppelingen die aan het doorgestuurde of beantwoorde bericht worden toegevoegd, worden niet herschreven. Bij automatisch doorsturen via regels voor Postvak IN *of* SMTP-doorsturen wordt de URL echter niet herschreven in het bericht dat is bedoeld voor de uiteindelijke geadresseerde, tenzij deze geadresseerde ook wordt beveiligd door veilige koppelingen of als de URL al in een eerdere communicatie is herschreven.  

De instellingen in beleidsregels voor veilige koppelingen die van toepassing zijn op e-mailberichten, worden in de volgende lijst beschreven:

- **Selecteer de actie voor onbekende, mogelijk schadelijke URL's in** berichten: Hiermee schakelt u het scannen van veilige koppelingen in e-mailberichten in of uit. De aanbevolen waarde is **Aan.** Als u deze instelling in uitschakelen, worden de volgende acties ondernomen.

  - Scannen van veilige koppelingen is ingeschakeld in Outlook (C2R) in Windows.
  - URL's worden herschreven en gebruikers worden omgeleid via beveiliging tegen veilige koppelingen wanneer ze op URL's in berichten klikken.
  - Wanneer erop wordt geklikt, worden URL's gecontroleerd op een lijst met bekende schadelijke URL's en de lijst 'De volgende [URL's blokkeren'.](#block-the-following-urls-list-for-safe-links)
  - URL's die geen geldige reputatie hebben, worden asynchroon op de achtergrond gedetoneerd.

- **Gebruik het scannen van realtime-URL's** op verdachte koppelingen en koppelingen die naar bestanden wijzen: hiermee kunt u koppelingen in realtime scannen, inclusief koppelingen in e-mailberichten die naar downloadbare inhoud wijzen. De aanbevolen waarde is ingeschakeld.

  - **Wacht totdat het scannen van de URL is voltooid voordat het bericht wordt weergegeven:**

    - Ingeschakeld: berichten met URL's worden opgeslagen totdat het scannen is voltooid. Berichten worden alleen bezorgd nadat de URL's zijn bevestigd om veilig te zijn. Dit is de aanbevolen waarde.
    - Uitgeschakeld: Als het scannen van URL's niet kan worden voltooid, bezorgt u het bericht toch.

- Veilige koppelingen toepassen op **e-mailberichten** die binnen de organisatie worden verzonden: hiermee schakelt u het scannen van veilige koppelingen in of uit op berichten die worden verzonden tussen interne afzenders en interne geadresseerden binnen dezelfde Exchange Online-organisatie. De aanbevolen waarde is ingeschakeld.

- **Klikken op gebruikers niet bijhouden:** hiermee schakelt u het opslaan van veilige koppelingen in of uit, klik op gegevens voor URL's waarin in e-mailberichten wordt geklikt. Deze instelling wordt aanbevolen niet te worden geselecteerd (om klikken van gebruikers bij te houden).

  Het bijhouden van URL-klikken voor koppelingen in e-mailberichten die worden verzonden tussen interne afzenders en interne geadresseerden, wordt momenteel niet ondersteund.

- **Niet toestaan dat gebruikers doorklikken** naar de oorspronkelijke URL: [](#warning-pages-from-safe-links) hiermee kunnen gebruikers niet door de waarschuwingspagina klikken of naar de oorspronkelijke URL klikken. De aanbevolen waarde is ingeschakeld.

- **Herschrijf de volgende URL's niet** opnieuw: laat DE URL's zo staan. Houdt een aangepaste lijst bij van veilige URL's die u niet hoeft te scannen. De lijst is uniek voor elk beleid voor veilige koppelingen. Zie de lijsten 'De volgende **URL's** niet herschrijven' verder in dit artikel voor meer informatie over het niet herschrijven van de volgende URL's-lijst. [](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

Zie beleidsinstellingen voor veilige koppelingen voor meer informatie over de aanbevolen waarden voor beleidsregels standaard en [strikt voor veilige koppelingen.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)

- **Geadresseerdenfilters:** u moet de voorwaarden van de geadresseerde opgeven en uitzonderingen die bepalen op wie het beleid van toepassing is. U kunt deze eigenschappen gebruiken voor voorwaarden en uitzonderingen:

  - **De ontvanger is**
  - **Het domein van de ontvanger is**
  - **De ontvanger is lid van**

  U kunt een voorwaarde of uitzondering slechts eenmaal gebruiken, maar de voorwaarde of uitzondering kan meerdere waarden bevatten. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

- **Prioriteit:** als u meerdere beleidsregels maakt, kunt u de volgorde opgeven waarin ze worden toegepast. Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

  Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).

### <a name="how-safe-links-works-in-email-messages"></a>De manier waarop veilige koppelingen werken in e-mailberichten

Op hoog niveau werkt beveiliging van veilige koppelingen voor URL's in e-mailberichten als volgende:

1. Alle e-mailberichten worden verzonden via EOP, waar internetprotocolfilters (IP) en envelopfilters, op handtekeningen gebaseerde malwarebeveiliging, antispam- en anti-malwarefilters worden gebruikt voordat het bericht in het postvak van de geadresseerde wordt bezorgd.

2. De gebruiker opent het bericht in het postvak en klikt op een URL in het bericht.

3. Met veilige koppelingen wordt onmiddellijk de URL gecontroleerd voordat u de website opent:

   - Als de URL is opgenomen in de lijst **De volgende URL's** blokkeren, wordt een [waarschuwing voor geblokkeerde URL's](#blocked-url-warning) geopend.

   - Als de URL naar een website wijst die schadelijk is, wordt een waarschuwingspagina voor een schadelijke [website](#malicious-website-warning) (of een andere waarschuwingspagina) geopend.

   - Als de URL naar een downloadbaar bestand wijst en het scannen van **de URL in realtime** op verdachte koppelingen en koppelingen naar bestanden is ingeschakeld in het beleid dat van toepassing is op de gebruiker, wordt het downloadbare bestand gecontroleerd.

   - Als de URL veilig is, wordt de website geopend.

## <a name="safe-links-settings-for-microsoft-teams"></a>Instellingen voor veilige koppelingen voor Microsoft Teams

> [!IMPORTANT]
> Vanaf maart 2020 is deze functie beschikbaar als preview-versie en is alleen beschikbaar voor leden van het Microsoft Teams Technology Adoption Program (TAP). Bekijk de routekaart voor [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)voor informatie over het releaseschema.

U schakelt beveiliging tegen veilige koppelingen voor Microsoft Teams in of uit in beleidsregels voor veilige koppelingen. U gebruikt de actie Selecteren voor onbekende of mogelijk schadelijke **URL's in** de instelling Microsoft Teams. De aanbevolen waarde is **Aan.**

De volgende instellingen in beleidsregels voor veilige koppelingen die van toepassing zijn op koppelingen in e-mailberichten, zijn ook van toepassing op koppelingen in Teams:

- **Real-time URL's scannen op verdachte koppelingen en koppelingen die naar bestanden wijzen**
- **Klikken van gebruikers niet bijhouden**
- **Gebruikers niet toestaan door te klikken naar de oorspronkelijke URL**

Deze instellingen worden uitgelegd in de vorige sectie [met instellingen voor veilige koppelingen voor e-mailberichten.](#safe-links-settings-for-email-messages)

Nadat u Beveiliging voor veilige koppelingen voor Microsoft Teams hebt ingeschakeld, worden URL's in Teams gecontroleerd op een lijst met bekende schadelijke koppelingen wanneer de beveiligde gebruiker op de koppeling klikt (time-of-click-beveiliging). URL's worden niet herschreven. Als een koppeling schadelijk wordt gevonden, hebben gebruikers de volgende ervaringen:

- Als op de koppeling is geklikt in een Teams-gesprek, groepschat of vanuit kanalen, wordt de waarschuwingspagina zoals weergegeven in de onderstaande schermafbeelding weergegeven in de standaardwebbrowser.
- Als u op de koppeling hebt geklikt vanaf een vastgemaakt tabblad, wordt de waarschuwingspagina weergegeven in de Teams-interface op dat tabblad. De optie voor het openen van de koppeling in een webbrowser is om veiligheidsredenen uitgeschakeld.
- Afhankelijk van hoe gebruikers niet mogen doorklikken naar de oorspronkelijke **URL-instelling** in het beleid, kan de gebruiker al dan niet doorklikken naar de oorspronkelijke URL (toch doorgaan **(niet aanbevolen)** in de schermafbeelding). U wordt aangeraden de instelling Niet toestaan dat gebruikers doorklikken naar de oorspronkelijke **URL-instelling** in te stellen, zodat gebruikers niet kunnen doorklikken naar de oorspronkelijke URL.

Als de gebruiker die de koppeling heeft verzonden niet is opgenomen in een beleid voor veilige koppelingen waarin Teams-beveiliging is ingeschakeld, kan de gebruiker op de oorspronkelijke URL op zijn computer of apparaat klikken.

![Een pagina met veilige koppelingen voor Teams met een schadelijke koppeling.](../../media/tp-safe-links-for-teams-malicious.png)

Als u op **de knop Terug** gaan op de waarschuwingspagina klikt, wordt de gebruiker terug geplaatst naar de oorspronkelijke context of URL-locatie. Als u echter nogmaals op de oorspronkelijke koppeling klikt, wordt de URL opnieuw scant door Veilige koppelingen, zodat de waarschuwingspagina opnieuw wordt weergegeven.

### <a name="how-safe-links-works-in-teams"></a>Hoe veilige koppelingen werken in Teams

Op hoog niveau werkt safe links-beveiliging voor URL's in Microsoft Teams als volgende:

1. Een gebruiker start de Teams-app.

2. Microsoft 365 controleert of de organisatie van de gebruiker Microsoft Defender voor Office 365 bevat en dat de gebruiker is opgenomen in een actief beleid voor veilige koppelingen, waarbij beveiliging voor Microsoft Teams is ingeschakeld.

3. URL's worden gevalideerd op het moment dat de gebruiker klikt in chats, groepschats, kanalen en tabbladen.

## <a name="safe-links-settings-for-office-365-apps"></a>Instellingen voor veilige koppelingen voor Office 365-apps

Met de beveiliging van veilige koppelingen voor Office 365-apps worden koppelingen in Office-documenten gecontroleerd, geen koppelingen in e-mailberichten (maar koppelingen in bijgevoegde Office-documenten in e-mailberichten worden gecontroleerd nadat het document is geopend).

Beveiliging tegen veilige koppelingen voor Office 365-apps heeft de volgende clientvereisten:

- Microsoft 365-apps of Microsoft 365 Business Premium.
  - Huidige versies van Word, Excel en PowerPoint op Windows, Mac of in een webbrowser.
  - Office-apps op iOS- of Android-apparaten.
  - Visio voor Windows.
  - OneNote in een webbrowser.

- Office 365-apps zijn geconfigureerd voor gebruik van moderne verificatie. Zie Hoe moderne verificatie werkt voor [Office 2013-, Office 2016- en Office 2019-clientapps](../../enterprise/modern-auth-for-office-2013-and-2016.md)voor meer informatie.

- Gebruikers worden aangemeld met hun werk- of schoolaccount. Zie Aanmelden bij [Office voor meer informatie.](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)

U configureert beveiliging tegen veilige koppelingen voor Office 365-apps in de algemene instellingen voor veilige koppelingen, niet in het beleid voor veilige koppelingen. Maar om Office 365-apps te beschermen tegen veilige koppelingen, moet de gebruiker die het Office-document opent en op de koppeling klikt, worden opgenomen in een actief beleid voor veilige koppelingen.

De volgende instellingen voor veilige koppelingen zijn beschikbaar voor Office 365-apps:

- **Office 365-toepassingen:** Hiermee schakelt u safe links scannen in of uit in ondersteunde Office 365-apps. De standaardwaarde en aanbevolen waarde is **Ingeschakeld.**

- **Houd niet bij** wanneer gebruikers op Veilige koppelingen klikken: Hiermee schakelt u het opslaan van veilige koppelingen in of uit, klik op gegevens voor URL's waarop in de bureaubladversies van Word, Excel, PowerPoint en Visio wordt geklikt. De aanbevolen waarde is **Uit,** wat betekent dat klikken van gebruikers worden bijgesneden.

- Laat gebruikers niet door veilige koppelingen naar de oorspronkelijke **URL** klikken: hiermee kunnen gebruikers niet door de waarschuwingspagina klikken naar de oorspronkelijke URL in de bureaubladversies van Word, Excel, PowerPoint en Visio. [](#warning-pages-from-safe-links) De standaard- en aanbevolen waarde is **Ingeschakeld.**

Zie Beveiliging van veilige koppelingen configureren voor Office 365-apps als u de instellingen voor veilige koppelingen [voor Office 365-apps wilt configureren.](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)

Zie Algemene instellingen voor veilige koppelingen voor meer informatie over de aanbevolen waarden voor standaard- en [strikte beleidsinstellingen.](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links)

### <a name="how-safe-links-works-in-office-365-apps"></a>Hoe veilige koppelingen werken in Office 365-apps

Op hoog niveau kunt u als eerste de beveiliging van veilige koppelingen gebruiken voor URL's in Office 365-apps. De ondersteunde Office 365-apps worden beschreven in het vorige gedeelte.

1. Een gebruiker meldt zich aan met zijn of haar werk- of schoolaccount in een organisatie die Microsoft 365-apps of Microsoft 365 Business Premium bevat.

2. De gebruiker wordt geopend en klikt op een koppeling naar een Office-document in een ondersteunde Office-app.

3. Met veilige koppelingen wordt onmiddellijk de URL gecontroleerd voordat u de doelwebsite opent:

   - Als de URL is opgenomen in de lijst waarin Safe Links niet kan worden gescand (de lijst met de volgende **URL's** blokkeren), wordt een waarschuwingspagina voor geblokkeerde [URL's](#blocked-url-warning) geopend.

   - Als de URL naar een website wijst die schadelijk is, wordt een waarschuwingspagina voor een schadelijke [website](#malicious-website-warning) (of een andere waarschuwingspagina) geopend.

   - Als de URL naar een downloadbaar bestand wijst en het beleid voor Veilige koppelingen dat van toepassing is op de gebruiker zo is geconfigureerd dat koppelingen naar downloadbare inhoud worden gescand (SCAN IN **realtime-URL's** toepassen op verdachte koppelingen en koppelingen naar bestanden), wordt het downloadbare bestand gecontroleerd.

   - Als de URL als veilig wordt beschouwd, wordt de gebruiker naar de website overgebracht.

   - Als scannen van veilige koppelingen niet kan worden voltooid, wordt de beveiliging van veilige koppelingen niet triggers. In Office-desktopcl clients wordt de gebruiker gewaarschuwd voordat deze naar de doelwebsite gaat.

> [!NOTE]
> Het kan enkele seconden aan het begin van elke sessie duren om te controleren of de gebruiker Veilige koppelingen voor Office heeft ingeschakeld.

## <a name="block-the-following-urls-list-for-safe-links"></a>Lijst 'De volgende URL's blokkeren' voor Veilige koppelingen

De **lijst met de volgende URL's** blokkeren definieert de koppelingen die altijd worden geblokkeerd door het scannen van veilige koppelingen op de volgende locaties:

- E-mailberichten.
- Documenten in Office 365-apps in Windows en Mac.
- Documenten in Office voor iOS en Android.

Wanneer een gebruiker in een actief beleid voor veilige koppelingen op een geblokkeerde koppeling in een ondersteunde app klikt, wordt deze naar de waarschuwingspagina voor geblokkeerde [URL's](#blocked-url-warning) overgebracht.

U configureert de lijst met URL's in de algemene instellingen voor veilige koppelingen. Zie De lijst ['De volgende URL's blokkeren' configureren voor instructies.](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)

**Opmerkingen**:

- Zie De lijst met tenants [toestaan/blokkeren](tenant-allow-block-list.md)beheren voor een echt universele lijst met URL's die overal worden geblokkeerd.

- Limieten:
  - Het maximum aantal items is 500.
  - De maximumlengte van een vermelding is 128 tekens.
  - Alle items mogen niet meer dan 10.000 tekens bevatten.

- Voeg geen slash () toe aan `/` het einde van de URL. Gebruik bijvoorbeeld niet `https://www.contoso.com` `https://www.contoso.com/` .

- Met een alleen-url voor een domein (bijvoorbeeld of ) wordt elke `contoso.com` URL geblokkeerd die het domein `tailspintoys.com` bevat.

- U kunt een subdomein blokkeren zonder het volledige domein te blokkeren. De URL die het subdomein bevat, wordt bijvoorbeeld geblokkeerd, maar URL's met het volledige domein `toys.contoso.com*` worden niet `contoso.com` geblokkeerd.

- U kunt maximaal drie jokertekens ( `*` ) per URL-vermelding opnemen.

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>Syntaxis voor de lijst 'De volgende URL's blokkeren'

Voorbeelden van de waarden die u kunt invoeren en de resultaten hiervan worden in de volgende tabel beschreven:

****

|Value|Resultaat|
|---|---|
|`contoso.com` <p> of <p> `*contoso.com*`|Blokkeert het domein, subdomeinen en paden. Deze worden bijvoorbeeld `https://www.contoso.com` `https://sub.contoso.com` `https://contoso.com/abc` geblokkeerd.|
|`https://contoso.com/a`|Blokken, `https://contoso.com/a` maar geen extra subpaths, zoals `https://contoso.com/a/b` .|
|`https://contoso.com/a*`|Blokken `https://contoso.com/a` en extra subpaths, zoals `https://contoso.com/a/b` .|
|`https://toys.contoso.com*`|Hiermee wordt een subdomein (in dit voorbeeld) blokkeert, maar kunt u klikken toestaan naar `toys` andere domein-URL's (zoals `https://contoso.com` `https://home.contoso.com` of).|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>Lijsten met 'De volgende URL's niet herschrijven' in beleidsregels voor veilige koppelingen

> [!NOTE]
> Als in uw organisatie beleid  voor veilige koppelingen wordt gebruikt, zijn de volgende URL's-lijsten niet opnieuw schrijven de enige ondersteunde methode voor phishingtests van derden.

Elk beleid voor veilige koppelingen bevat een lijst met veilige koppelingen die u kunt gebruiken om **URL's** op te geven die niet worden herschreven door scannen met veilige koppelingen. Met andere woorden, de lijst geeft gebruikers die zijn opgenomen in het beleid, toegang tot de opgegeven URL's die anders worden geblokkeerd door veilige koppelingen. U kunt verschillende lijsten configureren in verschillende beleidsregels voor veilige koppelingen. De verwerking van het beleid stopt nadat het eerste beleid (waarschijnlijk de hoogste prioriteit) op de gebruiker is toegepast. De volgende **URL's-lijst** wordt dus slechts één keer opnieuw schrijven toegepast op een gebruiker die is opgenomen in meerdere actieve beleidsregels voor veilige koppelingen.

Zie Beleidsregels voor veilige koppelingen maken of Beleid [](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) voor veilige koppelingen wijzigen als u items aan de lijst wilt toevoegen in nieuwe of bestaande [beleidsregels voor veilige koppelingen.](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)

**Opmerkingen**:

- De volgende clients herkennen  de volgende URL's-lijsten in het beleid voor veilige koppelingen niet opnieuw. Gebruikers die zijn opgenomen in het internet, kunnen worden geblokkeerd voor toegang tot de URL's op basis van de resultaten van het scannen van veilige koppelingen in deze clients:

  - Microsoft Teams
  - Office-web-apps

  Zie De lijst met tenants toestaan/blokkeren beheren voor een echt universele lijst met URL's die overal [zijn toegestaan.](tenant-allow-block-list.md)

- Overweeg om veelgebruikte interne URL's aan de lijst toe te voegen om de gebruikerservaring te verbeteren. Als u bijvoorbeeld on-premises services hebt, zoals Skype voor Bedrijven of SharePoint, kunt u deze URL's toevoegen om scannen uit te sluiten.

- Als u de **volgende** URL's in het beleid voor veilige koppelingen nog niet opnieuw hebt geschreven, controleert u de lijsten en voegt u indien nodig jokertekens toe. De lijst bevat bijvoorbeeld een item zoals dat is `https://contoso.com/a` en u besluit later subpathen zoals `https://contoso.com/a/b` . In plaats van een nieuw item toe te voegen, voegt u een jokerteken toe aan de bestaande vermelding zodat deze `https://contoso.com/a/*` wordt.

- U kunt maximaal drie jokertekens ( `*` ) per URL-vermelding opnemen. Jokertekens bevatten expliciet voorvoegsels of subdomeinen. De vermelding is bijvoorbeeld niet hetzelfde als, omdat personen subdomeinen en paden in het opgegeven `contoso.com` `*.contoso.com/*` domein kunnen `*.contoso.com/*` bezoeken.

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>Syntaxis voor de lijst 'De volgende URL's niet herschrijven'

Voorbeelden van de waarden die u kunt invoeren en de resultaten hiervan worden in de volgende tabel beschreven:

****

|Value|Resultaat|
|---|---|
|`contoso.com`|Hiermee kunt u toegang krijgen `https://contoso.com` tot, maar geen subdomeinen of paden.|
|`*.contoso.com/*`|Hiermee krijgt u toegang tot een domein, subdomeinen en paden `https://www.contoso.com` `https://www.contoso.com` (bijvoorbeeld, of `https://maps.contoso.com` `https://www.contoso.com/a` ). <p> Deze vermelding is inherent beter dan omdat mogelijk frauduleuze `*contoso.com*` sites, zoals of `https://www.falsecontoso.com``https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Hiermee kunt u `https://contoso.com/a` toegang krijgen tot, maar geen subpathen, zoals `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Hiermee kunt u `https://contoso.com/a` toegang krijgen tot en subpathen, zoals `https://contoso.com/a/b`|
|

## <a name="warning-pages-from-safe-links"></a>Waarschuwingspagina's van veilige koppelingen

Deze sectie bevat voorbeelden van de verschillende waarschuwingspagina's die worden geactiveerd door beveiliging tegen veilige koppelingen wanneer u op een URL klikt.

Er zijn verschillende waarschuwingspagina's bijgewerkt. Als u de bijgewerkte pagina's nog niet ziet, gebeurt dit binnenkort. De bijgewerkte pagina's bevatten een nieuw kleurenschema, meer details en de mogelijkheid om naar een site te gaan ondanks de gegeven waarschuwing en aanbevelingen.

### <a name="scan-in-progress-notification"></a>Melding scan wordt uitgevoerd

De geklikte URL wordt gescand op veilige koppelingen. Mogelijk moet u even wachten voordat u de koppeling opnieuw probeert.

![Melding 'De koppeling wordt gescand'](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

De oorspronkelijke meldingspagina ziet er zo uit:

![Oorspronkelijke melding 'De koppeling wordt gescand'](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a>Waarschuwing voor verdacht bericht

De geklikte URL staat in een e-mailbericht dat lijkt op andere verdachte berichten. U wordt aangeraden het e-mailbericht nog eens te controleren voordat u doorgaat naar de site.

![Waarschuwing 'Er is op een koppeling geklikt vanuit een verdacht bericht'](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a>Waarschuwing bij phishingpoging

De geklikte URL staat in een e-mailbericht dat is geïdentificeerd als een phishing-aanval. Hierdoor worden alle URL's in het e-mailbericht geblokkeerd. We raden u aan niet verder te gaan naar de site.

![Waarschuwing 'Er is op de koppeling geklikt vanuit een phishingbericht'](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a>Waarschuwing over schadelijke website

De geklikte URL wijst naar een site die als schadelijk is aangemerkt. U wordt aangeraden niet naar de site te gaan.

![Waarschuwing 'Deze website is geclassificeerd als schadelijk'](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

De oorspronkelijke waarschuwingspagina ziet er zo uit:

![Oorspronkelijke waarschuwing 'Deze website is geclassificeerd als schadelijk'](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a>Waarschuwing over geblokkeerde URL

De geklikte URL is handmatig geblokkeerd door een beheerder in uw organisatie (de lijst met de volgende **URL's** blokkeren in de algemene instellingen voor veilige koppelingen). De koppeling is niet gescand op Veilige koppelingen omdat deze handmatig is geblokkeerd.

Er zijn verschillende redenen waarom een beheerder specifieke URL's handmatig zou blokkeren. Neem contact op met de beheerder als u denkt dat de site niet moet worden geblokkeerd.

![De waarschuwing 'Deze website is geblokkeerd door uw beheerder'](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

De oorspronkelijke waarschuwingspagina ziet er zo uit:

![Oorspronkelijke waarschuwing 'Deze website is geblokkeerd volgens het URL-beleid van uw organisatie'](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a>Foutwaarschuwing

Er is een fout opgetreden en de URL kan niet worden geopend.

![De waarschuwing 'De pagina die u wilt openen, kan niet worden geladen'.](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

De oorspronkelijke waarschuwingspagina ziet er zo uit:

![Oorspronkelijke waarschuwing 'Deze webpagina kan niet worden geladen'](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
