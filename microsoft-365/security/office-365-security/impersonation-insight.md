---
title: Inzicht in imitatie
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe het nabootsingsinzicht werkt. Ze kunnen snel bepalen welke afzenders e-mail naar hun organisatie verzenden vanuit domeinen die niet worden gecontroleerd op e-mailverificatie (SPF, DKIM of DMARC).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e1b99590d7ae96ad8371eb2a2fab5fb7e8f94d07
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879034"
---
# <a name="impersonation-insight-in-defender-for-office-365"></a>Inzicht in imitatie in Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> De functies die in dit artikel worden beschreven, zijn in Preview, kunnen worden gewijzigd en zijn niet beschikbaar in alle organisaties.

Imitatie is de plaats waar de afzender van een e-mailbericht lijkt op een e-mailadres van een echte of verwachte afzender. Aanvallers hebben vaak e-mailadressen van afzenders nagebootst in phishing of andere soorten aanvallen om het vertrouwen van de ontvanger te winnen. Er zijn in feite twee typen imitatie:

- **Domein imitatie:** In plaats van lila@contoso.com, wordt het e-mailadres van de nagebootsde afzender lila@ćóntoso.com.
- **Gebruikers imitatie:** In plaats van michelle@contoso.com, wordt het e-mailadres van de nagebootsde afzender rnichell@contoso.com.

Domain impersonation is different from [domain spoofing](anti-spoofing-protection.md), because the impersonated domain is typically a real, registered domain. Berichten van afzenders in het nagebootst domein kunnen regelmatig e-mailverificatiecontroles uitvoeren die anders spoofingpogingen (SPF, DKIM en DMARC) zouden identificeren.

Imitatiebeveiliging maakt deel uit van de instellingen voor anti-phishingbeleid die exclusief zijn voor Microsoft Defender voor Office 365. Zie Instellingen voor imitatie in [anti-phishingbeleid in Microsoft Defender](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)voor Office 365.

U kunt het inzicht in imitatie gebruiken in de Microsoft 365 Defender-portal om snel berichten te identificeren van nagebootsde afzenders of afzenderdomeinen die u hebt geconfigureerd voor imitatiebeveiliging.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent de Microsoft 365 Defender-portal op <https://security.microsoft.com> . Als u rechtstreeks naar het inzicht voor imitatie op de **pagina Anti-phishing** wilt gaan, gebruikt u <https://security.microsoft.com/antiphishing> . Als u rechtstreeks naar de **pagina Imitatieinzicht wilt** gaan, gebruikt u <https://security.microsoft.com/impersonationinsight> .

- U moet machtigingen krijgen toegewezen in de Microsoft 365 Defender-portal voordat u de procedures in dit artikel kunt uitvoeren:
  - **Organisatiebeheer**
  - **Beveiligingsbeheerder**
  - **Beveiligingslezer**
  - **Globale lezer**

  Zie Machtigingen [in de portal Microsoft 365 Defender voor meer informatie.](permissions-in-the-security-and-compliance-center.md)

  **Opmerking:** Gebruikers toevoegen aan de bijbehorende Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de vereiste  machtigingen in de Microsoft 365 Defender-portal en machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.

- U kunt imitatiebeveiliging inschakelen en configureren in anti-phishingbeleid in Microsoft Defender voor Office 365. Imitatiebeveiliging is standaard niet ingeschakeld. Zie [Anti-phishingbeleid configureren in Microsoft Defender](configure-atp-anti-phishing-policies.md)voor Office 365.

## <a name="open-the-impersonation-insight-in-the-microsoft-365-defender-portal"></a>Het inzicht in imitatie openen in de Microsoft 365 Defender-portal

1. Ga in Microsoft 365 Defender-portal naar **E-mail & Samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsregels \>  \>  \>  \> **Anti-phishing**.

2. Op de **pagina Anti-phishing** ziet het nabootsingsinzicht er als volgende uit:

   ![Imitatieinzicht en spoofintelligentie op de pagina Anti-phishingbeleid](../../media/m365-sc-impersonation-and-spoof-intelligence-insight.png)

   Het inzicht heeft twee modi:

    - **Insight-modus:** Als imitatiebeveiliging is ingeschakeld en geconfigureerd in een anti-phishingbeleid, wordt in het inzicht het aantal gedetecteerde berichten van nagebootsde domeinen en nagebootsde gebruikers (afzenders) in de afgelopen zeven dagen in beeld gegeven. Dit is het totaal van alle gedetecteerde, nagebootsde afzenders van alle anti-phishingbeleidsregels.
    - Wat als de modus **:** Als imitatiebeveiliging niet is ingeschakeld en geconfigureerd in een actief  anti-phishingbeleid, wordt in het inzicht duidelijk hoeveel berichten de afgelopen zeven dagen door onze mogelijkheden voor imitatiebeveiliging zijn gedetecteerd.

Als u informatie over de imitatiedetecties wilt weergeven, klikt u op **Imitaties** weergeven in het imitatie-inzicht.

   > [!NOTE]
   > Zie Inzicht in spoof intelligence in EOP voor informatie over het inzicht in [spoof intelligence.](learn-about-spoof-intelligence.md)

## <a name="view-information-about-messages-from-senders-in-impersonated-domains"></a>Informatie weergeven over berichten van afzenders in nagebootsde domeinen

Controleer op **de pagina Imitatieinzicht** die wordt weergegeven nadat u op  Imitaties **weergeven** in het imitatie-inzicht hebt geklikt, of het tabblad Domeinen is geselecteerd. Het **tabblad Domeinen** bevat de volgende informatie:

- **Afzenderdomein:** het imitatiedomein, dat het domein is dat is gebruikt om het e-mailbericht te verzenden.
- **Aantal berichten:** het aantal berichten dat afkomstig is van een afzenderdomein in de afgelopen 7 dagen.
- **Type imitatie:** deze waarde toont de gedetecteerde locatie van de imitatie (bijvoorbeeld **Domein in adres).**
- **Imiteerde domein(s)**: het nagebootsde domein, dat lijkt op het domein dat is geconfigureerd voor imitatiebeveiliging in het anti-phishingbeleid.
- **Domeintype:** Deze waarde is **bedrijfsdomein** voor interne domeinen of **Aangepast domein** voor aangepaste domeinen.
- **Beleid:** het anti-phishingbeleid dat het nagebootsde domein heeft gedetecteerd.
- **Mag zich voordoen als**: Een van de volgende waarden:
  - **Ja:** Het domein is geconfigureerd als vertrouwd domein (een uitzondering voor imitatiebeveiliging) in het anti-phishingbeleid. Berichten van afzenders in het nagebootsde domein zijn gedetecteerd, maar zijn toegestaan.
  - **Nee:** Het domein is geconfigureerd voor imitatiebeveiliging in het anti-phishingbeleid. Berichten van afzenders in het nagebootsde domein zijn gedetecteerd en geacteerd op basis van de actie voor nagebootsde domeinen in het anti-phishingbeleid.

U kunt op geselecteerde kolomkoppen klikken om de resultaten te sorteren.

Als u de resultaten wilt filteren, kunt u het vak Zoeken met het pictogram Zoeken gebruiken om een door ![ komma's gescheiden lijst met waarden in te voeren om ](../../media/m365-cc-sc-search-icon.png)  de resultaten te filteren.

### <a name="view-details-about-messages-from-senders-in-impersonated-domains"></a>Details weergeven van berichten van afzenders in nagebootsde domeinen

Selecteer op **het tabblad Domeinen** op de pagina **Imitatieinzicht** een van de beschikbare imitatiedetecties. De details die worden weergegeven, bevatten de volgende informatie en functies:

- **Selectie-imitatiebeleid om te wijzigen:** Selecteer het betreffende anti-phishingbeleid dat u wilt wijzigen. Er zijn alleen agenten beschikbaar waar het nagebootsde domein is gedefinieerd in het beleid. Raadpleeg de vorige pagina om te zien welk beleid daadwerkelijk verantwoordelijk was voor het detecteren van het nagebootst domein (waarschijnlijk op basis van de ontvanger en de prioriteit van het beleid).
- **Toevoegen aan** de lijst met toegestane imitaties: Gebruik deze schakelknop om de afzender toe te voegen of te verwijderen uit de vertrouwde **afzenders** en domeinen (uitzonderingen voor imitatie) voor het anti-phishingbeleid dat u hebt geselecteerd:
  - Als de **waarde Toegestaan voor dit item** nee was, is de schakelknop uitgeschakeld.  Als u alle afzenders in dit domein wilt vrijstellen van evaluatie door imitatiebeveiliging, schuift u de schakelknop in op: ![ Schakel ](../../media/scc-toggle-on.png) in. Het domein wordt toegevoegd aan de **lijst Vertrouwde** domeinen in de instellingen voor imitatiebeveiliging van het anti-phishingbeleid.
  - Als de **waarde Toegestaan voor dit item** ja was, is de schakelknop aan.  Als u alle afzenders in dit domein wilt retourneren naar evaluatie door imitatiebeveiliging, schuift u de schakelknop uit: Schakel de ![ schakelknop ](../../media/scc-toggle-off.png) uit. Het domein wordt verwijderd uit de **lijst Vertrouwde domeinen** in de instellingen voor imitatiebeveiliging van het anti-phishingbeleid.
- Waarom we dit hebben gesnapt.
- Wat u moet doen.
- Een domeinoverzicht met het nagebootsde domein.
- WhoIs-gegevens over de afzender.
- Een koppeling om [Threat Explorer te openen](threat-explorer.md) voor meer informatie over de afzender.
- Soortgelijke berichten van dezelfde afzender die zijn bezorgd bij uw organisatie.

## <a name="view-information-about-messages-from-impersonated-senders"></a>Informatie weergeven over berichten van nagebootsde afzenders

Klik op **de pagina Imitatieinzicht** die wordt weergegeven nadat u op **Imitaties** weergeven in het imitatie-inzicht hebt geklikt op het tabblad **Gebruikers.** Het **tabblad Gebruikers** bevat de volgende informatie:

- **Afzender:** het e-mailadres van de afzender die het e-mailbericht heeft verzonden.
- **Aantal berichten:** het aantal berichten van de afzender die zich voordoet in de afgelopen 7 dagen.
- **Type imitatie:** Deze waarde is **Gebruiker in weergavenaam.**
- **Imiteerde gebruiker(s)**: het e-mailadres van de nagebootsde afzender, dat lijkt op de gebruiker die is geconfigureerd voor imitatiebeveiliging in het anti-phishingbeleid.
- **Gebruikerstype:** deze waarde toont het type beveiliging dat is toegepast (bijvoorbeeld **Beveiligde gebruiker** of **Postvakintelligentie).**
- **Beleid:** het anti-phishingbeleid dat de nagebootsde afzender heeft gedetecteerd.
- **Mag zich voordoen als**: Een van de volgende waarden:
  - **Ja:** De afzender is geconfigureerd als vertrouwde gebruiker (een uitzondering voor imitatiebeveiliging) in het anti-phishingbeleid. Berichten van de nagebootsde afzender zijn gedetecteerd, maar zijn toegestaan.
  - **Nee:** de afzender is geconfigureerd voor imitatiebeveiliging in het anti-phishingbeleid. Berichten van de nagebootsde afzender zijn gedetecteerd en op basis van de actie voor nagebootsde gebruikers in het anti-phishingbeleid.

U kunt op geselecteerde kolomkoppen klikken om de resultaten te sorteren.

Als u de resultaten wilt filteren, kunt u het vak **Filter afzender** gebruiken om een door komma's gescheiden lijst met waarden in te voeren om de resultaten te filteren.

### <a name="view-details-about-messages-from-impersonated-senders"></a>Details weergeven van berichten van nagebootsde afzenders

Selecteer op **het** tabblad Gebruikers op **de pagina Imitatieinzicht** een van de beschikbare imitatiedetecties. De details die worden weergegeven, bevatten de volgende informatie en functies:

- **Selectie-imitatiebeleid om te wijzigen:** Selecteer het betreffende anti-phishingbeleid dat u wilt wijzigen. Er zijn alleen agenten beschikbaar waar de identiteit van de afzender is gedefinieerd in het beleid. Raadpleeg de vorige pagina om te zien welk beleid verantwoordelijk was voor het detecteren van de nagebootste afzender (waarschijnlijk op basis van de ontvanger en de prioriteit van het beleid).
- **Toevoegen aan** de lijst met toegestane imitaties: Gebruik deze schakelknop om de afzender toe te voegen of te verwijderen uit de vertrouwde **afzenders** en domeinen (uitzonderingen voor imitatie) voor het anti-phishingbeleid dat u hebt geselecteerd:
  - Als de **waarde Toegestaan voor dit item** nee was, is de schakelknop uitgeschakeld.  Als u de afzender wilt vrijstellen van evaluatie door imitatiebeveiliging, schuift u de schakelknop in op: Schakel de ![ schakelknop ](../../media/scc-toggle-on.png) in. De afzender wordt toegevoegd aan de **lijst Vertrouwde gebruikers** in de instellingen voor imitatiebeveiliging van het anti-phishingbeleid.
  - Als de **waarde Toegestaan voor dit item** ja was, is de schakelknop aan.  Als u de afzender door imitatiebeveiliging wilt laten evalueren, schuift u de schakelknop uit: Schakel de ![ schakelknop ](../../media/scc-toggle-off.png) uit. De afzender wordt verwijderd uit de **lijst Vertrouwde gebruikers** in de instellingen voor imitatiebeveiliging van het anti-phishingbeleid.
- Waarom we dit hebben gesnapt.
- Wat u moet doen.
- Een afzenderoverzicht met de identiteit van de afzender.
- WhoIs-gegevens over de afzender.
- Een koppeling om [Threat Explorer te openen](threat-explorer.md) voor meer informatie over de afzender.
- Soortgelijke berichten van dezelfde afzender die zijn bezorgd bij uw organisatie.
