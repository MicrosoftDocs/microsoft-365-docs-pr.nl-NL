---
title: Beleid tegen phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
description: Meer informatie over het basisbeleid voor phishing in Exchange Online Protection (EOP) en het geavanceerde ATP-antiphishingbeleid in Office 365 Advanced Threat Protection.
ms.openlocfilehash: 32214d24c7ed030b3bc7aad36bf3ac99f68a17fb
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2020
ms.locfileid: "43949379"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Anti-phishingbeleid in Microsoft 365

Beleidsregels voor het configureren van instellingen voor bescherming tegen phishing zijn beschikbaar in Microsoft 365-organisaties met Exchange Online-postvakken, zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken en ATP-organisaties (Office 365 Advanced Threat Protection).

ATP-antiphishingbeleid is alleen beschikbaar in organisaties met Office 365 ATP. Bijvoorbeeld:

- Microsoft 365 Enterprise E5, Microsoft 365 Education A5, enz.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Office 365 ATP als invoegtoepassing](https://products.office.com/exchange/advance-threat-protection)

Alle andere organisaties hebben anti-phishing beleid.

De verschillen op hoog niveau tussen antiphishingbeleid en ATP-antiphishingbeleid worden beschreven in de volgende tabel:

||||
|---|:---:|:---:|
|**Functie**|**Beleid tegen phishing**|**ATP anti-phishing beleid**|
|Automatisch gemaakt standaardbeleid|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Aangepaste beleidsregels maken|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Beleidsinstellingen<sup>\*</sup>|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Imitatie-instellingen||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Spoofinstellingen|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Geavanceerde phishingdrempels||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<sup>\*</sup>In het standaardbeleid zijn de beleidsnaam en -beschrijving alleen-lezen (de beschrijving is leeg) en u niet opgeven op wie het beleid van toepassing is (het standaardbeleid is van toepassing op alle ontvangers).

Zie de volgende onderwerpen om antiphishingbeleid te configureren:

- [Anti-phishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md)

- [ATP-beleid voor phishing configureren in Microsoft 365](configure-atp-anti-phishing-policies.md)

De rest van dit onderwerp beschrijft de instellingen die beschikbaar zijn in anti-phishing beleid en ATP anti-phishing beleid.

## <a name="spoof-settings"></a>Spoofinstellingen

Spoofing is wanneer het Van-adres in een e-mailbericht (het afzenderadres dat wordt weergegeven in e-mailclients) niet overeenkomt met het domein van de e-mailbron. Zie [Anti-spoofing beveiliging in Microsoft 365](anti-spoofing-protection.md)voor meer informatie over spoofing.

De volgende spoofinstellingen zijn beschikbaar in antiphishingbeleid en ATP-antiphishingbeleid:

- **Anti-spoofing bescherming:** Schakelt anti-spoofing bescherming in of uit. We raden u aan het ingeschakeld te laten. U gebruikt het **spoof-intelligentiebeleid** om specifieke vervalste interne en externe afzenders toe te staan of te blokkeren. Zie [spoof-intelligentie configureren in Microsoft 365](learn-about-spoof-intelligence.md) voor meer informatie.

  > [!NOTE]
  > Spoofinstellingen zijn standaard ingeschakeld in het standaard antiphishingbeleid in EOP, het standaard ATP-antiphishingbeleid en in nieuwe aangepaste antiphishingbeleidsregels of ATP-antiphishingbeleid dat u maakt. <br/><br/> U hoeft anti-spoofingbescherming niet uit te schakelen als uw MX-record niet naar Microsoft 365 wijst; u schakelt in plaats daarvan Uitgebreide filtering voor connectors in. Zie Uitgebreide [filtering voor connectors in Exchange Online voor](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)instructies .

  Voor berichten van geblokkeerde vervalste afzenders u ook de actie opgeven die u op de berichten moet uitvoeren:

  - **Bericht verplaatsen naar map Ongewenste e-mail:** dit is de standaardwaarde. Het bericht wordt in het postvak bezorgd en naar de map Ongewenste e-mail verplaatst. In Exchange Online wordt het bericht verplaatst naar de map Ongewenste e-mail als de regel voor ongewenste e-mail is ingeschakeld in het postvak (het is standaard ingeschakeld). Zie [Instellingen voor ongewenste e-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie.

  - **Quarantaine het bericht:** Stuurt het bericht naar quarantaine in plaats van de beoogde ontvangers. Zie de volgende artikelen voor meer informatie over quarantaine:

    - [Quarantaine in Microsoft 365](quarantine-email-messages.md)
    - [In quarantaine geplaatste berichten en bestanden beheren als beheerder in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [In quarantaine geplaatste berichten zoeken en vrijgeven als gebruiker in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

- **Niet-geverifieerde afzender:** hiermee schakelt of wordt de identificatie van niet-geïdentificeerde afzenders in Outlook in- of uitgeschakeld. Specifiek:

  - Er wordt een vraagteken (?) toegevoegd aan de foto van de afzender als het bericht niet door de SPF- of DKIM-controles komt **en** het bericht niet door DMARC of [samengestelde verificatie](email-validation-and-authentication.md#composite-authentication)voldoet.

  - De via-tag (chris@contoso.com <u>via</u> michelle@fabrikam.com) wordt toegevoegd als het domein in het Adres Van (de afzender van het bericht dat wordt weergegeven in e-mailclients) verschilt van het domein in de DKIM-handtekening of het **E-mailadres.** Zie [Een overzicht van de normen voor e-mailberichten](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards) voor meer informatie over deze adressen

  Om te voorkomen dat deze id's worden toegevoegd aan berichten van specifieke afzenders, hebt u de volgende opties:

  - Laat de afzender spoofen in het spoof-informatiebeleid. Zie [Spoofinformatie configureren in Microsoft 365](learn-about-spoof-intelligence.md)voor instructies.

  - [E-mailverificatie configureren](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) voor het afzenderdomein.
  
    - Voor het vraagteken op de foto van de afzender zijn SPF of DKIM het belangrijkst.
    - Bevestig voor de via-tag het domein in de DKIM-handtekening of het **E-mailadres dat** overeenkomt (of is een subdomein van) het domein in het Adres van.

  Zie [Verdachte berichten in Outlook.com en de webversie van Outlook identificeren](https://support.office.com/article/3d44102b-6ce3-4f7c-a359-b623bec82206) voor meer informatie

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a>Exclusieve instellingen in atp-antiphishingbeleid

In dit gedeelte worden de beleidsinstellingen beschreven die alleen beschikbaar zijn in het ANTI-phishingbeleid van ATP.

> [!NOTE]
> Standaard zijn de exclusieve ATP-instellingen niet geconfigureerd of ingeschakeld, zelfs niet in het standaardbeleid. Als u van deze functies wilt profiteren, moet u deze inschakelen en configureren in het standaard ATP-antiphishingbeleid, of aangepaste ATP-antiphishingbeleidsregels maken en configureren.

### <a name="policy-settings-in-atp-anti-phishing-policies"></a>Beleidsinstellingen in ATP-antiphishingbeleid

De volgende beleidsinstellingen zijn alleen beschikbaar in het ANTI-phishingbeleid van ATP:

- **Naam:** U de naam van het standaard antiphishingbeleid niet wijzigen, maar u wel de naam van het aangepaste beleid dat u maakt, een naam geven en een andere naam geven.

- **Beschrijving** U geen beschrijving toevoegen aan het standaard antiphishingbeleid, maar u de beschrijving voor het aangepaste beleid dat u maakt toevoegen en wijzigen.

- **Toegepast op**: Identificeert interne ontvangers waarop het ATP-antiphishingbeleid van toepassing is. Deze waarde is vereist in aangepast beleid en is niet beschikbaar in het standaardbeleid (het standaardbeleid is van toepassing op alle ontvangers).

    U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden van dezelfde voorwaarde of uitzondering gebruiken OF-logica (bijv.: _\<afzender1\>_ of _\<afzender2\>_). Verschillende voorwaarden of uitzonderingen gebruiken EN-logica (bijv.: _\<geadresseerde1\>_ en _\<lid van groep 1\>_).

  - **Ontvanger is:** een of meer postvakken, e-mailgebruikers of e-mailcontactpersonen in uw organisatie.
  - **Ontvanger is lid van**: Een of meer groepen in uw organisatie.
  - Het domein van de **geadresseerde is:** Een of meer van de geconfigureerde geaccepteerde domeinen in Microsoft 365.

  - **Behalve wanneer**: Uitzonderingen voor de regel. De instellingen en het gedrag zijn precies zoals de voorwaarden:

    - **Ontvanger is**
    - **Ontvanger is lid van**
    - **Het domein van de ontvanger is**

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>Imitatie-instellingen in het ANTI-phishingbeleid van ATP

Imitatie is waar de afzender of het e-maildomein van de afzender in een bericht erg lijkt op een echte afzender of domein:

- Een voorbeeld van imitatie van het domein contoso.com is ćóntoso.com.

- Een voorbeeld imitatie van de gebruiker michelle@contoso.com is michele@contoso.com.

Een geïmiteerd domein kan anders als legitiem worden beschouwd (geregistreerd domein, geconfigureerde e-mailverificatierecords, enz.), behalve dat het de bedoeling is om ontvangers te misleiden.

De volgende imitatie-instellingen zijn alleen beschikbaar in het ANTI-phishingbeleid van ATP:

- **Gebruikers om te beschermen:** voorkomt dat de opgegeven interne of externe gebruikers worden nagebootst. Bijvoorbeeld leidinggevenden (intern) en bestuursleden (extern). U maximaal 60 interne en externe adressen toevoegen. Deze lijst met beveiligde gebruikers verschilt van de lijst met ontvangers waarop het beleid van toepassing is in de **instelling Toegepast.**

  U geeft felipe Apodaca (felipea@contoso.com) bijvoorbeeld op als een beveiligde gebruiker in een beleid dat van toepassing is op de groep met de naam Leidinggevenden. Binnenkomende berichten die worden verzonden naar leden van de groep Leidinggevenden waar de plaats waar Felipe Apodaca wordt nagebootst, wordt uitgevoerd door het beleid (de actie die u configureert voor geïmiteerde gebruikers).

- **Domeinen om te beschermen:** voorkom dat de opgegeven domeinen worden nagebootst. Bijvoorbeeld alle domeinen waarvan u eigenaar bent[(geaccepteerde domeinen)](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)of specifieke domeinen (domeinen waarvan u eigenaar bent of partnerdomeinen). Deze lijst met beveiligde domeinen verschilt van de lijst met domeinen waarop het beleid van toepassing is in de **instelling Toegepast.**

  U geeft bijvoorbeeld tailspintoys.com op als een beveiligd domein in een beleid dat van toepassing is op leden van de groep met de naam Leidinggevenden. Binnenkomende berichten die worden verzonden naar leden van de groep Leidinggevenden waar de plaats waar de tailspintoys.com wordt nagebootst, worden uitgevoerd door het beleid (de actie die u configureert voor nagebootste domeinen).

- **Acties voor beveiligde gebruikers of domeinen:** kies de actie die u wilt uitvoeren met binnenkomende berichten die imitatiepogingen bevatten tegen de beveiligde gebruikers en beveiligde domeinen in het beleid. U verschillende acties opgeven voor imitatie van beschermde gebruikers versus imitatie van beveiligde domeinen:

  - **Geen actie toepassen**

  - **Bericht doorverwijzen naar andere e-mailadressen:** Stuurt het bericht naar de opgegeven ontvangers in plaats van naar de beoogde ontvangers.

  - **Bericht verplaatsen naar map Ongewenste e-mail:** het bericht wordt naar het postvak bezorgd en naar de map Ongewenste e-mail verplaatst. In Exchange Online wordt het bericht verplaatst naar de map Ongewenste e-mail als de regel voor ongewenste e-mail is ingeschakeld in het postvak (het is standaard ingeschakeld). Zie [Instellingen voor ongewenste e-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie.

    - **Quarantaine het bericht:** Stuurt het bericht naar quarantaine in plaats van de beoogde ontvangers. Zie de volgende artikelen voor meer informatie over quarantaine:

    - [Quarantaine in Microsoft 365](quarantine-email-messages.md)
    - [In quarantaine geplaatste berichten en bestanden beheren als beheerder in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [In quarantaine geplaatste berichten zoeken en vrijgeven als gebruiker in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

  - **Breng het bericht af en voeg andere adressen toe aan de BCC-regel:** Breng het bericht aan de beoogde ontvangers en lever het bericht in stilte af aan de opgegeven ontvangers.

  - **Verwijder het bericht voordat het wordt bezorgd:** verwijdert in stilte het hele bericht, inclusief alle bijlagen.

- **Veiligheidstips:** Hiermee worden de volgende imitatieveiligheidstips in- of uitgeschakeld die berichten worden weergegeven die geen imitatiecontroles uitvoeren:

  - **Nagebootste gebruikers**: Het adres van het adres bevat een beveiligde gebruiker.
  - **Nagebootste domeinen**: Het adres van het adres bevat een beveiligd domein.
  - **Ongebruikelijke tekens**: Het adres van Het Adres bevat ongebruikelijke tekenreeksen (bijvoorbeeld wiskundige symbolen en tekst of een mix van hoofdletters en kleine letters) in een beveiligde afzender of domein.

- **Postvakintelligentie**: Hiermee schakelt of schakelt kunstmatige intelligentie (AI) uit die e-mailpatronen van gebruikers bepaalt met hun frequente contactpersonen. Met deze instelling maakt de AI onderscheid tussen legitieme en vervalste e-mail van die contactpersonen. Postvakinformatie is alleen beschikbaar voor Exchange Online-postvakken.

- Bescherming op basis van imitatie van **postvakinformatie:** hiermee worden verbeterde imitatieresultaten ingeschakeld of uitgeschakeld op basis van de afzonderlijke afzenderkaart van elke gebruiker. Met deze intelligentie kan Microsoft 365 de detectie van gebruikersimitatie aanpassen en fout-positieven beter verwerken. Wanneer imitatie van gebruikers wordt gedetecteerd, u een specifieke actie definiëren die u op het bericht moet uitvoeren:

  - **Geen actie toepassen**
  - **Bericht doorverwijzen naar andere e-mailadressen**
  - **Bericht verplaatsen naar map Ongewenste e-mail**
  - **Het bericht in quarantaine plaatsen**
  - **Het bericht afgeven en andere adressen toevoegen aan de BCC-regel**
  - **Het bericht verwijderen voordat het wordt bezorgd**

- **Vertrouwde afzenders en domeinen:** uitzonderingen op de instellingen voor imitatiebeveiliging. Berichten van de opgegeven afzenders en afzenderdomeinen worden nooit geclassificeerd als aanvallen op basis van imitaties door het beleid. Met andere woorden, de actie voor beveiligde afzenders, beveiligde domeinen of beveiliging van postvakinformatie wordt niet toegepast op deze vertrouwde afzenders of afzenderdomeinen. De maximumlimiet voor deze lijsten is ongeveer 1000 vermeldingen.

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a>Geavanceerde phishingdrempels in ATP-antiphishingbeleid

De volgende geavanceerde phishing-drempels zijn alleen beschikbaar in het ATP-antiphishingbeleid om aan te geven hoe gedetecteerde phishingberichten moeten worden behandeld:

- **1 - Standaard:** Dit is de standaardwaarde. De ernst van de actie die wordt uitgevoerd op het bericht is afhankelijk van de mate van vertrouwen dat het bericht is phishing (laag, gemiddeld, hoog, of zeer hoog vertrouwen). Bijvoorbeeld, berichten die worden geïdentificeerd als phishing met een zeer hoge mate van vertrouwen hebben de meest ernstige acties toegepast, terwijl berichten die worden geïdentificeerd als phishing met een lage mate van vertrouwen hebben minder ernstige acties toegepast.

- **2 - Agressief**: Berichten die worden geïdentificeerd als phishing met een hoge mate van vertrouwen worden behandeld alsof ze werden geïdentificeerd met een zeer hoge mate van vertrouwen.

- **3 - Agressiever**: Berichten die worden geïdentificeerd als phishing met een gemiddelde of hoge mate van vertrouwen worden behandeld alsof ze werden geïdentificeerd met een zeer hoge mate van vertrouwen.

- **4 - Meest agressieve**: Berichten die worden geïdentificeerd als phishing met een lage, gemiddelde of hoge mate van vertrouwen worden behandeld alsof ze werden geïdentificeerd met een zeer hoge mate van vertrouwen.

De kans op false positives (goede berichten gemarkeerd als slecht) neemt toe naarmate u deze instelling verhoogt. Zie [Beleidsinstellingen voor antiphishing](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)in Office ATP voor informatie over de aanbevolen instellingen.