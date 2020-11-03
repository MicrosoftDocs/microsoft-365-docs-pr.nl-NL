---
title: Veilige koppelingen
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.article: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
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
description: In dit artikel kunnen beheerders informatie bieden over beveiliging van veilige koppelingen in Defender voor Office 365 om hun organisatie tegen phishing en andere aanvallen met schadelijke Url's te beschermen.
ms.openlocfilehash: 869cb2f330b81481a2a0a013564853274654d0ef
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846054"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>Veilige koppelingen in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten met [Microsoft Defender voor Office 365](office-365-atp.md). Als u gebruikmaakt van Outlook.com, Microsoft 365 Family of Microsoft 365 Personal en u zoekt naar informatie over Safelinks in Outlook, raadpleegt u [geavanceerde beveiliging van Outlook.com](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Veilige koppelingen is een functie in [Defender voor Office 365](office-365-atp.md) waarmee u de inkomende e-mailberichten in de e-mail stroom kunt scannen en opnieuw kunt schrijven, en de gewenste verificatie van url's en koppelingen in e-mailberichten en andere locaties. Het scannen van veilige koppelingen vindt u naast de regelmatige [antispam en anti-malware bescherming](anti-spam-and-anti-malware-protection.md) in inkomende e-mailberichten in Exchange Online Protection (EOP). Met behulp van veilige koppelingen scannen kunt u uw organisatie beschermen tegen kwaadaardige koppelingen die worden gebruikt in phishing en andere aanvallen.

Beveiliging van veilige koppelingen is beschikbaar op de volgende locaties:

- **E-mailberichten** : beveiliging van veilige koppelingen voor koppelingen in e-mailberichten wordt bepaald door beleid voor veilige koppelingen. Er is geen standaardbeleid voor veilige koppelingen, **dus als u de beveiliging van veilige koppelingen in een e-mailbericht wilt ontvangen, moet u een of meer beleidsregels voor veilige koppelingen maken**. Zie [beleid voor veilige koppelingen instellen in Microsoft Defender voor Office 365](set-up-atp-safe-links-policies.md)voor instructies.

  Zie de [instellingen voor veilige koppelingen voor e-mailberichten](#safe-links-settings-for-email-messages) verderop in dit artikel voor meer informatie over de bescherming van veilige koppelingen voor e-mailberichten.

- **Microsoft teams** (momenteel in de preview-versie van het lint): beveiliging van veilige koppelingen voor koppelingen in teams-gesprekken, groepsgesprekken of van kanalen wordt ook bestuurd door beleidsregels voor veilige koppelingen. Er is geen standaardbeleid voor veilige koppelingen, **dus als u de beveiliging van veilige koppelingen in teams wilt instellen, moet u een of meer beleidsregels voor veilige koppelingen maken**.

  Zie de sectie [instellingen voor veilige koppelingen voor Microsoft teams](#safe-links-settings-for-microsoft-teams) verderop in dit onderwerp voor meer informatie over beveiliging van veilige koppelingen in teams.

- **Apps van office 365** : beveiliging van veilige koppelingen voor Office 365-apps is beschikbaar in de ondersteunde Desktop-, Mobile-en Web-APS. U **configureert** de bescherming voor veilige koppelingen voor Office 365-apps in de globale instelling **buiten** het beleid voor veilige koppelingen. Zie [algemene instellingen configureren voorinstellingen voor veilige koppelingen in Microsoft Defender voor Office 365](configure-global-settings-for-safe-links.md)voor instructies.

  Maar de bescherming van veilige koppelingen voor Office 365-apps is alleen van **toepassing** op gebruikers die deel uitmaken van de beleidsregels voor Active Safe koppelingen. Als een gebruiker niet is opgenomen in een actief beleid voor veilige koppelingen, wordt de beveiliging van veilige koppelingen niet ondersteund in ondersteunde Office 365-apps.

  Zie de sectie [instellingen voor veilige koppelingen voor office 365](#safe-links-settings-for-office-365-apps) -apps verderop in dit artikel voor meer informatie over beveiliging van veilige koppelingen in Office 365-apps.

Dit artikel bevat uitgebreide beschrijvingen van de volgende typen instellingen voor veilige koppelingen:

- **Instellingen voor beleidsregels voor veilige koppelingen** : deze instellingen zijn alleen van toepassing op de gebruikers die in de specifieke beleidsregels zijn opgenomen, en de instellingen kunnen afwijken van het beleid. De volgende instellingen zijn beschikbaar:

  - [Instellingen voor veilige koppelingen voor e-mailberichten](#safe-links-settings-for-email-messages)
  - [Instellingen voor veilige koppelingen voor Microsoft teams](#safe-links-settings-for-microsoft-teams)
  - [De lijsten ' de volgende Url's niet herschrijven ' in het beleid voor veilige koppelingen](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **Algemene instellingen voor veilige koppelingen** : deze instellingen zijn globaal geconfigureerd, niet in het beleid voor veilige koppelingen. De instellingen zijn alleen van toepassing op gebruikers die deel uitmaken van een actief beleid voor veilige koppelingen. De volgende instellingen zijn beschikbaar:

  - [Instellingen voor veilige koppelingen voor Office 365-apps](#safe-links-settings-for-office-365-apps)
  - [De lijst volgende Url's blokkeren voor veilige koppelingen](#block-the-following-urls-list-for-safe-links)

In de volgende tabel wordt beschreven hoe u veilige koppelingen in Microsoft 365 en Office 365-organisaties die de oplossing van Defender voor Office 365 bevatten (met andere woorden, onvoldoende licentieverlening in de voorbeelden).

****

|Voorbeeld|Resultaat|
|---|---|
|Jean maakt deel uit van de marketingafdeling. Beveiliging van veilige koppelingen voor Office 365-apps is ingeschakeld in de algemene instellingen voor veilige koppelingen en een beleid voor veilige koppelingen dat van toepassing is op leden van de marketingafdeling. Jean opent een PowerPoint-presentatie in een e-mailbericht en klikt op een URL in de presentatie.|Jean is beveiligd met behulp van veilige koppelingen. <br/><br/> Jean maakt deel uit van een beleid voor veilige koppelingen, en beveiliging van beveiligde koppelingen voor Office 365-apps is ingeschakeld. <br/><br/> Zie de sectie [instellingen voor veilige koppelingen voor office 365](#safe-links-settings-for-office-365-apps) -apps verderop in dit artikel voor meer informatie over de vereisten voor de bescherming van veilige koppelingen in Office 365-apps.|
|De organisatie van Chris Microsoft 365 E5 heeft geen beleid voor veilige koppelingen geconfigureerd. Chris ontvangt een e-mailbericht van een externe afzender die een URL bevat naar een schadelijke website waarop hij uiteindelijk klikt.|Chris is niet beveiligd via veilige koppelingen. <br/><br/> Een beheerder moet ten minste één beleid voor veilige koppelingen maken voor iedereen om veilige koppelingen te beschermen in inkomende e-mailberichten. Chris moet zijn opgenomen in de voorwaarden van het beleid om de bescherming van veilige koppelingen te voorkomen.|
|In de organisatie van de Pat hebben beheerders geen beleid voor veilige koppelingen gemaakt, maar beveiliging van Office 365-apps is ingeschakeld. Pat opent een Word-document en klikt op een URL in het bestand.|Pat is niet beveiligd door veilige koppelingen. <br/><br/> Hoewel de bescherming van veilige koppelingen voor Office 365-apps algemeen is ingeschakeld, is Pat niet opgenomen in actieve beleidsregels voor veilige koppelingen, zodat de beveiliging niet kan worden toegepast.|
|De organisatie van Lee `https://tailspintoys.com` is geconfigureerd in de lijst **de volgende Url's blokkeren** in de algemene instellingen voor veilige koppelingen. Er bestaat al een beleid voor veilige koppelingen met de optie Lee. Lee ontvangt een e-mailbericht met de URL `https://tailspintoys.com/aboutus/trythispage` . Lee: klikken op de URL.|De URL wordt mogelijk automatisch geblokkeerd voor Lee. Dit hangt af van de URL-vermelding in de lijst en de e-mailclient Lee die wordt gebruikt. Zie voor meer informatie de sectie [' de volgende Url's blokkeren voor veilige koppelingen '](#block-the-following-urls-list-for-safe-links) verderop in dit onderwerp.|
|Jan en Julia beide werken voor contoso.com. Lang geleden, beheerders die het beleid voor veilige koppelingen voor beheerders hebben geconfigureerd, gelden voor zowel Janny als Julia. Jan verzendt een e-mailbericht naar Julia, en weet niet dat het e-mailbericht een schadelijke URL bevat.|Julia is beveiligd met behulp van veilige koppelingen **als** het beleid voor veilige koppelingen dat van toepassing is, is geconfigureerd voor het toepassen van berichten tussen interne geadresseerden. Zie voor meer informatie de sectie [instellingen voor veilige koppelingen voor e-mailberichten](#safe-links-settings-for-email-messages) verderop in dit onderwerp.|

## <a name="safe-links-settings-for-email-messages"></a>Instellingen voor veilige koppelingen voor e-mailberichten

Veilige koppelingen Hiermee wordt binnenkomende e-mail van bekende, schadelijke hyperlinks gescand. Gescande Url's worden herschreven met het Microsoft-standaard URL-voorvoegsel: `https://nam01.safelinks.protection.outlook.com` . Wanneer de koppeling is herschreven, wordt deze geanalyseerd voor mogelijk schadelijke inhoud.

Nadat u met veilige koppelingen een URL hebt geschreven, wordt de URL opnieuw weggeschreven, zelfs als het bericht wordt doorgestuurd of beantwoord. Aanvullende koppelingen die zijn toegevoegd aan het bericht doorgestuurd of beantwoord, worden niet herschreven.

In de volgende lijst vindt u een beschrijving van de instellingen voor beleidsregels voor veilige koppelingen die van toepassing zijn op e-mailberichten:

- **Selecteer de actie voor onbekende mogelijk schadelijke url's in berichten** : schakelt veilige koppelingen in e-mailberichten in of uit. De aanbevolen waarde is **ingeschakeld**. U schakelt deze instelling in door de volgende acties uit te voeren.

  - Het scannen van veilige koppelingen is ingeschakeld in Outlook (C2R) voor Windows.
  - Url's worden herschreven en gebruikers gerouteerd via de bescherming van veilige koppelingen wanneer ze op Url's in berichten klikken.
  - Wanneer erop wordt geklikt, worden Url's gecontroleerd tegen een lijst met bekende schadelijke Url's en de [lijst ' de volgende Url's blokkeren '](#block-the-following-urls-list-for-safe-links).
  - Url's zonder een geldige reputatie worden asynchroon op de achtergrond.

- Het **scannen van realtime-Url's toepassen op verdachte koppelingen en koppelingen die verwijzen naar bestanden** : Hiermee kunt u koppelingen in realtime scannen, waaronder koppelingen in e-mailberichten die naar downloadbare inhoud verwijzen. De aanbevolen waarde is ingeschakeld.

  - **Wacht totdat URL-Scan is voltooid voordat u het bericht aflevert** :

    - Ingeschakeld: berichten die Url's bevatten, worden bewaard totdat de scan is voltooid. Berichten worden pas bezorgd nadat de Url's zijn bevestigd dat deze veilig zijn. Dit is de aanbevolen waarde.
    - Uitgeschakeld: als het scannen van URL'S niet kan worden voltooid, moet u het bericht toch afleveren.

- **Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie worden verzonden** : schakelt veilige koppelingen voor het scannen van berichten tussen interne afzenders en interne geadresseerden binnen dezelfde Exchange Online-organisatie in of uit. De aanbevolen waarde is ingeschakeld.

- **Gebruikers klikken niet bijhouden** : Hiermee schakelt u de optie voor het opslaan van veilige koppelingen in of uit op de url's die in e-mailberichten zijn geselecteerd. De aangeraden waarde is om deze instelling uit te sluiten (om de gebruikers klikken te volgen).

  URL klik op controleren voor koppelingen in e-mailberichten die worden verzonden tussen interne afzenders en interne geadresseerden worden momenteel niet ondersteund.

- **Gebruikers kunnen niet naar de oorspronkelijke URL klikken** : gebruikers kunnen door de [waarschuwingspagina](#warning-pages-from-safe-links) op de oorspronkelijke URL klikken. De aangeraden waarde is ingeschakeld.

- **Herschrijf de volgende url's niet** en laat de url's doorlopen. Hiermee wordt een aangepaste lijst bijgehouden met veilige Url's die u niet nodig hebt om te scannen. De lijst is uniek voor elk beleid voor veilige koppelingen. Zie voor meer informatie over de lijst de volgende url's **niet opnieuw schrijven** de sectie [' de volgende url's niet herschrijven ' in het gedeelte beleidsregels voor veilige koppelingen](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) verderop in dit artikel.

Zie [beleidsinstellingen voor veilige koppelingen](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)voor meer informatie over de aanbevolen waarden voor standaard-en strikte beleidsinstellingen voor beleidsregels voor veilige koppelingen.

- **Filters voor geadresseerden** : u moet de voorwaarden en uitzonderingen opgeven voor de ontvanger van het beleid. U kunt deze eigenschappen gebruiken voor voorwaarden en uitzonderingen:

  - **De ontvanger is**
  - **Het domein van de ontvanger is**
  - **De ontvanger is lid van**

  U kunt slechts één voorwaarde of een uitzondering gebruiken, maar de voorwaarde of uitzondering kan meerdere waarden bevatten. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_ ). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_ ).

- **Prioriteit** : als u meerdere beleidsregels maakt, kunt u de volgorde opgeven waarin ze worden toegepast. Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

  Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).

### <a name="how-safe-links-works-in-email-messages"></a>De werking van veilige koppelingen in e-mailberichten

Met een hoog niveau gaat u als volgt te werk om de beveiliging van veilige koppelingen te gebruiken voor Url's in e-mailberichten:

1. Alle e-mailberichten lopen via EOP, waarbij IP-en envelop filters, op handtekening gebaseerde beveiliging, antispam en anti-malware filters voordat het bericht in het postvak van de geadresseerde wordt bezorgd.

2. De gebruiker opent het bericht in het postvak en klikt op een URL in het bericht.

3. Veilige koppelingen controleren onmiddellijk de URL voordat ze de website openen:

   - Als de URL is opgenomen in de lijst **de volgende Url's blokkeren** , wordt een [geblokkeerde URL-waarschuwing](#blocked-url-warning) geopend.

   - Als de URL verwijst naar een website die is ingesteld als schadelijk, wordt de pagina met een [kwaadaardige website](#malicious-website-warning) (of een andere waarschuwingspagina) geopend.

   - Als de URL verwijst naar een bestand dat u wilt downloaden en de instelling **realtime van de URL gebruiken voor verdachte koppelingen en koppelingen die naar bestanden verwijzen** , is ingeschakeld in het beleid dat van toepassing is op de gebruiker, is het downloadbare bestand geselecteerd.

   - Als u zeker weet dat de URL veilig is, wordt de website geopend.

## <a name="safe-links-settings-for-microsoft-teams"></a>Instellingen voor veilige koppelingen voor Microsoft teams

> [!IMPORTANT]
> Met ingang van maart 2020 is deze functie in de preview-versie en is deze alleen beschikbaar voor leden van het Microsoft teams-programma voor de acceptatie van Microsoft teams. Voor informatie over de release planning raadpleegt u het [Microsoft 365-wegwijzer](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams).

U kunt de bescherming van veilige koppelingen voor Microsoft teams in-of uitschakelen in het beleid voor veilige koppelingen. Met name gebruikt u de instelling **de actie een actie voor onbekende of mogelijk schadelijke url's binnen Microsoft teams** . De aanbevolen waarde is **ingeschakeld**.

De volgende instellingen in beleid voor veilige koppelingen die gelden voor koppelingen in e-mailberichten, gelden ook voor koppelingen in teams:

- **Het scannen van realtime-URL'S toepassen op verdachte koppelingen en koppelingen die verwijzen naar bestanden**
- **Geclickte gebruikers niet bijhouden**
- **Gebruikers kunnen niet naar de oorspronkelijke URL klikken**

Deze instellingen worden beschreven in de sectie vorige [instellingen voor veilige koppelingen voor e-mailberichten](#safe-links-settings-for-email-messages) .

Nadat u de bescherming van veilige koppelingen voor Microsoft teams hebt ingeschakeld, worden Url's in teams gecontroleerd aan de hand van een lijst met bekende kwaadaardige koppelingen wanneer de beveiligde gebruiker op de koppeling klikt (time-to-klik-bescherming). Url's worden niet herschreven. Als een koppeling schadelijk moet zijn, kunnen gebruikers de volgende functies volgen:

- Als u op de koppeling hebt geklikt in een team gesprek, groepsgesprek of kanalen, wordt de waarschuwingspagina, zoals weergegeven in de onderstaande schermafbeelding, weergegeven in de standaardbrowser.
- Als u op de koppeling hebt geklikt van het tabblad vastgemaakt, wordt de pagina waarschuwing weergegeven in de teaminterface op dat tabblad. De optie om de koppeling in een webbrowser te openen, is vanwege beveiligingsredenen uitgeschakeld.
- Afhankelijk van hoe de instelling **gebruikers niet toestaan om te klikken op de oorspronkelijke URL** -instelling in het beleid is geconfigureerd, wordt de gebruiker of kan er niet doorgaan naar de oorspronkelijke URL (wordt **niet aanbevolen)** op de schermafbeelding). U wordt aangeraden de optie **niet toestaan dat gebruikers op de oorspronkelijke URL** -instelling klikken, zodat gebruikers niet kunnen klikken op de oorspronkelijke URL.

Als de gebruiker die de koppeling heeft verzonden, geen deel uitmaakt van een beleid voor veilige koppelingen waar de bescherming van teams is ingeschakeld, kan de gebruiker klikken op de oorspronkelijke URL op hun computer of apparaat.

![Een pagina met veilige koppelingen voor teams die een kwaadaardige koppeling melden.](../../media/tp-safe-links-for-teams-malicious.png)

Als u op de knop **terug** op de waarschuwingspagina klikt, krijgt de gebruiker de oorspronkelijke context of URL-locatie. Als u echter op de oorspronkelijke koppeling klikt, wordt de URL opnieuw gecontroleerd, zodat de pagina wordt weergegeven.

### <a name="how-safe-links-works-in-teams"></a>De werking van veilige koppelingen in teams

Met een hoog niveau gaat u als volgt te werk om de beveiliging van veilige koppelingen voor Url's in Microsoft teams te gebruiken:

1. Een gebruiker begint de teams-app.

2. Microsoft 365 verifieert dat de organisatie van de gebruiker Microsoft Defender for Office 365 bevat en dat de gebruiker is opgenomen in een actief beleid voor veilige koppelingen waarbij beveiliging voor Microsoft teams is ingeschakeld.

3. Url's worden gevalideerd wanneer u op het moment van klikken voor de gebruiker in chats, groepsgesprekken, kanalen en tabbladen.

## <a name="safe-links-settings-for-office-365-apps"></a>Instellingen voor veilige koppelingen voor Office 365-apps

Met de bescherming van veilige koppelingen voor Office 365-apps worden koppelingen in Office-documenten gecontroleerd, niet koppelingen in e-mailberichten (maar kunnen ze koppelingen in gekoppelde Office-documenten controleren in e-mailberichten nadat het document is geopend).

Beveiliging van veilige koppelingen voor Office 365-apps heeft de volgende clientvereisten:

- Microsoft 365-apps of Microsoft 365 Business Premium.
  - Actuele versies van Word, Excel en PowerPoint voor Windows, Mac of in een webbrowser.
  - Office-apps op iOS-of Android-apparaten.
  - Visio voor Windows.
  - OneNote in een webbrowser.

- Apps van Office 365 zijn geconfigureerd voor het gebruik van moderne verificatie. Zie de werking [van moderne verificatie voor office 2013-, office 2016-en office 2019-clienttoepassingen](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)voor meer informatie.

- Gebruikers zijn aangemeld met hun werk-of schoolaccount. Zie [Aanmelden bij Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)voor meer informatie.

U configureert de bescherming voor veilige koppelingen voor Office 365-apps in de algemene instellingen voor veilige koppelingen, niet in het beleid voor veilige koppelingen. Als u de beveiliging van Office 365-Apps wilt toepassen, moet de gebruiker die het Office-document opent, klikken op de koppeling en vervolgens op de koppeling klikken en op de koppeling klikken.

De volgende instellingen voor veilige koppelingen zijn beschikbaar voor Office 365-apps:

- **Office 365-toepassingen** : Hiermee wordt de scan van veilige koppelingen in ondersteunde Office 365-apps in-of uitgeschakeld. De standaard en aanbevolen waarde is **ingeschakeld**.

- **Niet bijhouden wanneer gebruikers op veilige koppelingen klikken** : de optie voor het opslaan van veilige koppelingen op de bureaublad versies van Word, Excel, PowerPoint en Visio wordt uitgeschakeld. De aanbevolen waarde is **uitgeschakeld** , wat betekent dat de gebruiker klikt op bijgehouden.

- **Laat gebruikers niet via veilige koppelingen naar de oorspronkelijke URL klikken** : Hiermee kunt u gebruikers niet via de [waarschuwingspagina](#warning-pages-from-safe-links) doorlopen in de bureaubladversie van Word, Excel, PowerPoint en Visio. De standaard en aanbevolen waarde is **ingeschakeld**.

Zie [beveiliging van veilige koppelingen voor office 365-apps configureren](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)als u de instellingen voor veilige koppelingen voor Office 365-Apps wilt configureren.

Zie [algemene instellingen voor veilige koppelingen](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links)voor meer informatie over de aanbevolen waarden voor de standaard-en strikte beleidsinstellingen.

### <a name="how-safe-links-works-in-office-365-apps"></a>De werking van veilige koppelingen in Office 365-apps

Met een hoog niveau gaat u als volgt te werk om de beveiliging van veilige koppelingen te gebruiken voor Url's in Office 365-apps. De ondersteunde Office 365-apps worden beschreven in de vorige sectie.

1. Een gebruiker meldt zich aan met een werk-of schoolaccount in een organisatie die Microsoft 365-apps of Microsoft 365 Business Premium omvat.

2. De gebruiker wordt geopend en u klikt op een koppeling naar een Office-document in een ondersteunde Office-app.

3. Veilige koppelingen controleren onmiddellijk de URL voordat ze de doelwebsite openen:

   - Als de URL is opgenomen in de lijst die de functie voor het scannen van veilige koppelingen overlaat, wordt er een **pagina met** [geblokkeerde URL-waarschuwingen](#blocked-url-warning) weergegeven.

   - Als de URL verwijst naar een website die is ingesteld als schadelijk, wordt de pagina met een [kwaadaardige website](#malicious-website-warning) (of een andere waarschuwingspagina) geopend.

   - Als de URL verwijst naar een downloadbaar bestand en het beleid voor veilige koppelingen dat van toepassing is op de gebruiker, is geconfigureerd voor het scannen van koppelingen naar downloadbare inhoud ( **toepassen op de realtime-URL scannen voor verdachte koppelingen en koppelingen naar bestanden** ), is het downloadbare bestand geselecteerd.

   - Als de URL als veilig wordt beschouwd, wordt de gebruiker gekeken naar de website.

   - Als de scanfunctie voor veilige koppelingen niet kan worden voltooid, wordt de bescherming van veilige koppelingen niet geactiveerd. In Office-bureaubladclient wordt de gebruiker gewaarschuwd voordat ze verder gaan met de doelwebsite.

> [!NOTE]
> Het kan een paar minuten duren voordat een sessie wordt uitgevoerd om te controleren of de gebruiker veilige koppelingen voor Office heeft ingeschakeld.

## <a name="block-the-following-urls-list-for-safe-links"></a>De lijst volgende Url's blokkeren voor veilige koppelingen

De lijst **de volgende Url's blokkeren** definieert de koppelingen die altijd worden geblokkeerd door veilige koppelingen op de volgende locaties:

- E-mailberichten.
- Documenten in Office 365-apps in Windows en Mac.
- Documenten in Office voor iOS en Android.

Wanneer een gebruiker in een actief beleid voor veilige koppelingen op een geblokkeerde koppeling in een ondersteunde app klikt, worden deze naar de pagina met [geblokkeerde URL-waarschuwingen](#blocked-url-warning) verwezen.

U configureert de lijst met Url's in de algemene instellingen voor veilige koppelingen. Zie [de lijst ' de volgende Url's blokkeren ' configureren](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)voor instructies.

**Opmerkingen** :

- Zie [Url's beheren in de lijst Tenant toestaan/blokkeren](tenant-allow-block-list.md)voor een daadwerkelijk universele lijst met url's die overal worden geblokkeerd.

- Gelden
  - Het maximale aantal vermeldingen is 500.
  - De maximumlengte van een vermelding is 128 tekens.
  - Alle items kunnen niet langer zijn dan 10.000 tekens.

- Neem geen voorwaartse schuine streep ( `/` ) aan het einde van de URL. Bijvoorbeeld gebruiken `https://www.contoso.com` `https://www.contoso.com/` .

- Een alleen domein-URL (bijvoorbeeld `contoso.com` of `tailspintoys.com` ) blokkeert alle url's die het domein bevatten.

- U kunt een subdomein blokkeren zonder het hele domein te blokkeren. Met `toys.contoso.com*` een willekeurige URL die het subdomein bevat, kunt u bijvoorbeeld alle url's blokkeren die het volledige domein bevatten `contoso.com` .

- U kunt maximaal drie jokertekens ( `*` ) per URL-vermelding opnemen.

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>De syntaxis van de invoer voor de lijst ' de volgende Url's blokkeren '

Zie de volgende tabel voor voorbeelden van de waarden die u kunt invoeren en de resultaten hiervan.

****

|Waarde|Resultaat|
|---|---|
|`contoso.com` <br/> of <br/> `*contoso.com*`|Blokkeert het domein, subdomeinen en paden. Bijvoorbeeld,, `https://www.contoso.com` `https://sub.contoso.com` en `https://contoso.com/abc` worden geblokkeerd.|
|`https://contoso.com/a`|Blokkeert `https://contoso.com/a` maar geen extra subpad, zoals `https://contoso.com/a/b` .|
|`https://contoso.com/a*`|Blokken `https://contoso.com/a` en extra subpad, zoals `https://contoso.com/a/b` .|
|`https://toys.contoso.com*`|Een subdomein blok `toys` keren (in dit voorbeeld), maar klikken op andere domein-url's (zoals `https://contoso.com` of `https://home.contoso.com` ).|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>De lijsten ' de volgende Url's niet herschrijven ' in het beleid voor veilige koppelingen

> [!NOTE]
> Als uw organisatie gebruikmaakt van beleidsregels voor veilige koppelingen, is de naam van **de volgende url's niet opnieuw schrijven** de enige ondersteunde methode voor phishing-tests van derden.

Elk beleid voor veilige koppelingen bevat een lijst met **de volgende url's niet herschrijven** , die u kunt gebruiken om url's op te geven die niet worden herschreven door veilige koppelingen te scannen. Met andere woorden: de lijst Hiermee kunnen gebruikers die in het beleid zijn opgenomen, toegang krijgen tot de opgegeven Url's die anders worden geblokkeerd door veilige koppelingen. U kunt verschillende lijsten configureren in verschillende beleidsregels voor veilige koppelingen. Beleidsverwerking stopt na het eerste beleid (waarschijnlijk met het hoogste prioriteit) dat wordt toegepast op de gebruiker. Daarom wordt slechts één lijst met **url's niet herschreven** met een gebruiker die is opgenomen in meerdere actieve beleidsregels voor veilige koppelingen.

Zie [beleidsregels voor veilige koppelingen maken](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) of [beleidsregels voor veilige koppelingen wijzigen](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)voor informatie over het toevoegen van vermeldingen aan de lijst in nieuwe of bestaande beleidsregels voor veilige koppelingen.

**Opmerkingen** :

- De volgende clients herkennen de **volgende url's niet** opnieuw te schrijven in het beleid voor veilige koppelingen. Gebruikers die deel uitmaken van de policies, kunnen de Url's blokkeren op basis van de resultaten van het scannen van veilige koppelingen in deze clients:

  - Microsoft Teams
  - Office Web apps

  Zie [Url's beheren in de lijst Tenant toestaan/blokkeren](tenant-allow-block-list.md)voor een daadwerkelijk universele lijst met url's die overal toegestaan zijn.

- Overweeg veelgebruikte interne Url's toe te voegen aan de lijst om de gebruikerservaring te verbeteren. Als u bijvoorbeeld on-premises Services hebt, zoals Skype voor bedrijven of SharePoint, kunt u deze Url's toevoegen om ze niet te scannen.

- Als u **de volgende url's nog niet** opnieuw moet schrijven in uw beleidsregels voor veilige koppelingen, controleert u de lijsten en voegt u jokertekens toe. Uw lijst heeft bijvoorbeeld een item zoals `https://contoso.com/a` en u kunt later ook subpaden opnemen als `https://contoso.com/a/b` . In plaats van een nieuwe vermelding toe te voegen, voegt u een jokerteken toe aan de bestaande vermelding, zodat deze wordt weergegeven `https://contoso.com/a/*` .

- U kunt maximaal drie jokertekens ( `*` ) per URL-vermelding opnemen. Jokertekens zijn expliciet voorvoegsels of subdomeinen. U kunt bijvoorbeeld niet gelijk zijn aan de invoer `contoso.com` `*.contoso.com/*` omdat `*.contoso.com/*` gebruikers subdomeinen en paden kunnen vinden in het opgegeven domein.

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>De syntaxis van de invoer voor de lijst "de volgende Url's niet herschrijven"

Zie de volgende tabel voor voorbeelden van de waarden die u kunt invoeren en de resultaten hiervan.

****

|Waarde|Resultaat|
|---|---|
|`contoso.com`|Toegang tot `https://contoso.com` subdomeinen of paden is toegestaan.|
|`*.contoso.com/*`|Hiermee kunt u toegang krijgen tot een domein, subdomeinen en paden (bijvoorbeeld,,, `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` of `https://www.contoso.com/a` ). <br/><br/> Deze vermelding is inherent `*contoso.com*` aan het feit omdat het niet mogelijk is frauduleuze websites, zoals `https://www.falsecontoso.com` of `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Toegang tot `https://contoso.com/a` , maar geen subpaden zoals `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Toegang tot `https://contoso.com/a` en subpad zoals `https://contoso.com/a/b`|
|

## <a name="warning-pages-from-safe-links"></a>Waarschuwings pagina's van veilige koppelingen

Dit gedeelte bevat voorbeelden van de verschillende waarschuwings pagina's die worden geactiveerd door de bescherming van veilige koppelingen wanneer u op een URL klikt.

Houd er rekening mee dat er meerdere waarschuwings pagina's zijn bijgewerkt. Als u de bijgewerkte pagina's nog niet ziet, dan gaat u binnenkort. De bijgewerkte pagina's bevatten een nieuw kleurenschema en meer details, en de mogelijkheid om naar een site te gaan ondanks de gegeven waarschuwings en aanbevelingen.

### <a name="scan-in-progress-notification"></a>Melding voor een actieve viruscontrole

De door u gekozen URL wordt gescand met behulp van veilige koppelingen. Misschien moet u even wachten voordat u de link opnieuw probeert.

![Melding ' de koppeling wordt gescand '](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

De oorspronkelijke meldings pagina ziet er als volgt uit:

![Origineel: de koppeling wordt gescand](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a>Waarschuwing voor verdachte berichten

De geklikt URL stond in een e-mailbericht dat lijkt op andere verdachte berichten. We raden u aan het e-mailbericht te controleren voordat u verder gaat met de site.

![' Er is een koppeling op basis van een verdacht bericht ' weergegeven](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a>Waarschuwing voor phishing-poging

De doorgegeven URL werd opgenomen in een e-mailbericht dat is herkend als een malafide aanval. Daarom worden alle Url's in het e-mailbericht geblokkeerd. We raden u aan om verder te gaan met de site.

![Waarschuwing ' de koppeling is op basis van een malafide bericht geklikt '](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a>Waarschuwing voor schadelijke website

De klik-URL verwijst naar een site die is geïdentificeerd als schadelijk. We raden u aan om verder te gaan met de site.

![Waarschuwing ' deze website is geclassificeerd als schadelijk '](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

De oorspronkelijke waarschuwingspagina ziet er als volgt uit:

![Oorspronkelijk is geclassificeerd als schadelijk voor deze website](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a>Waarschuwing voor geblokkeerde URL

De aangeklikte URL is handmatig geblokkeerd door een beheerder in de organisatie (de **volgende Url's blokkeren** in de algemene instellingen voor veilige koppelingen). De koppeling is niet gescand door veilige koppelingen omdat de koppeling handmatig is geblokkeerd.

Er zijn verschillende redenen waarom een beheerder handmatig bepaalde Url's blokkeert. Neem contact op met uw beheerder als u denkt dat de site niet wordt geblokkeerd.

![Waarschuwing ' deze website is geblokkeerd door de beheerder '](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

De oorspronkelijke waarschuwingspagina ziet er als volgt uit:

![Oorspronkelijk ' deze website is geblokkeerd per URL-beleid van uw organisatie ' waarschuwing](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a>Foutmelding

Er is een fout opgetreden en de URL kan niet worden geopend.

![Waarschuwing ' de pagina die u wilt openen, kan niet worden geladen '](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

De oorspronkelijke waarschuwingspagina ziet er als volgt uit:

![De waarschuwing ' deze webpagina kan niet worden geladen '](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
