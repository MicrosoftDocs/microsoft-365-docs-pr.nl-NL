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
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer te weten komen over het anti-phishingbeleid dat beschikbaar is in Exchange Online Protection (EOP) en Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: a61123e3d90a4125bf5a8303654973e1b478fc4c
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754662"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Anti-phishingbeleid in Microsoft 365

Beleid voor het configureren van instellingen voor bescherming tegen phishing is beschikbaar in Microsoft 365-organisaties met Exchange Online-postvakken, zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken en Office 365 Advanced Threat Protection (Office 365 ATP)-organisaties.

Atp-antiphishingbeleid is alleen beschikbaar in organisaties die Office 365 ATP hebben. Bijvoorbeeld:

- Microsoft 365 Enterprise E5, Microsoft 365 Education A5, enz.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Office 365 ATP als invoegtoepassing](https://products.office.com/exchange/advance-threat-protection)

Alle andere organisaties hebben een anti-phishingbeleid.

De verschillen op hoog niveau tussen anti-phishingbeleid en ATP-antiphishingbeleid worden beschreven in de volgende tabel:

||||
|---|:---:|:---:|
|**Functie**|**Beleid tegen phishing**|**ATP anti-phishing beleid**|
|Automatisch standaardbeleid maken|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Aangepast beleid maken|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Beleidsinstellingen<sup>\*</sup>|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Imitatie-instellingen||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Spoofinstellingen|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Geavanceerde phishingdrempels||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<sup>\*</sup>In het standaardbeleid zijn de beleidsnaam en -beschrijving alleen-lezen (de beschrijving is leeg) en u niet opgeven op wie het beleid van toepassing is (het standaardbeleid is van toepassing op alle ontvangers).

Zie de volgende onderwerpen om antiphishingbeleid te configureren:

- [Anti-phishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md)

- [Atp-beleid voor antiphishing configureren in Microsoft 365](configure-atp-anti-phishing-policies.md)

De rest van dit onderwerp beschrijft de instellingen die beschikbaar zijn in anti-phishing beleid en ATP anti-phishing beleid.

## <a name="spoof-settings"></a>Spoofinstellingen

Spoofing is wanneer het adres Van in een e-mailbericht (het afzenderadres dat wordt weergegeven in e-mailclients) niet overeenkomt met het domein van de e-mailbron. Zie [Anti-spoofing-beveiliging in Microsoft 365](anti-spoofing-protection.md)voor meer informatie over spoofing.

De volgende spoofinstellingen zijn beschikbaar in het anti-phishingbeleid en het ATP-anti-phishingbeleid:

- **Bescherming tegen spoofing:** hiermee u antipoofingbescherming uitschakelen. We raden u aan het ingeschakeld te laten. U gebruikt het **spoofinformatiebeleid** om specifieke vervalste interne en externe afzenders toe te staan of te blokkeren. Zie [spoof-intelligentie configureren in Microsoft 365](learn-about-spoof-intelligence.md) voor meer informatie.

  > [!NOTE]
  > Spoofinstellingen zijn standaard ingeschakeld in het standaard anti-phishingbeleid in EOP, het standaard ATP-antiphishingbeleid en in nieuw aangepast antiphishingbeleid of ATP-antiphishingbeleid dat u maakt. <br/><br/> U hoeft de bescherming tegen spoofing niet uit te schakelen als uw MX-record niet naar Microsoft 365 wijst; u in plaats daarvan Uitgebreide filtering voor connectoren inschakelt. Zie Uitgebreide [filtering voor connectoren in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)voor instructies.

  Voor berichten van geblokkeerde vervalste afzenders u ook de actie opgeven die u op de berichten moet uitvoeren:

  - **Bericht verplaatsen naar map Ongewenste e-mail:** dit is de standaardwaarde. Het bericht wordt bezorgd in het postvak en verplaatst naar de map Ongewenste e-mail. In Exchange Online wordt het bericht verplaatst naar de map Ongewenste e-mail als de regel voor ongewenste e-mail is ingeschakeld in het postvak (het is standaard ingeschakeld). Zie [Instellingen voor ongewenste e-mail configureren in Exchange Online-postvakken configureren in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie.

  - **Quarantaine het bericht**: Stuurt het bericht naar quarantaine in plaats van de beoogde ontvangers. Zie de volgende artikelen voor meer informatie over quarantaine:

    - [Quarantaine in Microsoft 365](quarantine-email-messages.md)
    - [Berichten en bestanden in quarantaine beheren als beheerder in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Berichten in quarantaine zoeken en vrijgeven als gebruiker in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

- **Niet-geverifieerde afzender**: Hiermee schakelt u niet-geïdentificeerde afzenderidentificatie in Outlook in of uit. Specifiek:

  - Er wordt een vraagteken (?) toegevoegd aan de foto van de afzender als het bericht niet door SPF- of DKIM-controles komt **en** het bericht niet door DMARC of [samengestelde verificatie](email-validation-and-authentication.md#composite-authentication)gaat.

  - De via-tag (chris@contoso.com <u>via</u> michelle@fabrikam.com) wordt toegevoegd als het domein in het Van-adres (de afzender van het bericht dat wordt weergegeven in e-mailclients) verschilt van het domein in de DKIM-handtekening of het **E-mailadres.** Zie [Een overzicht van de normen voor e-mailberichten](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards) voor meer informatie over deze adressen

  Om te voorkomen dat deze id's worden toegevoegd aan berichten van specifieke afzenders, hebt u de volgende opties:

  - Laat de afzender spoofen in het spoofinformatiebeleid. Zie [Spoofintelligentie configureren in Microsoft 365](learn-about-spoof-intelligence.md)voor instructies.

  - [E-mailverificatie configureren](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) voor het afzenderdomein.
  
    - Voor het vraagteken in de foto van de afzender zijn SPF of DKIM het belangrijkst.
    - Bevestig voor de via-tag het domein in de DKIM-handtekening of het **E-MAIL FROM-adres** (of is een subdomein van) het domein in het Van-adres.

  Zie [Verdachte berichten identificeren in Outlook.com en de webversie van Outlook voor](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206) meer informatie

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a>Exclusieve instellingen in atp-anti-phishingbeleid

In deze sectie worden de beleidsinstellingen beschreven die alleen beschikbaar zijn in het atp-anti-phishingbeleid.

> [!NOTE]
> Standaard zijn de exclusieve ATP-instellingen niet geconfigureerd of ingeschakeld, zelfs niet in het standaardbeleid. Om van deze functies te profiteren, moet u deze in- en configureren in het standaard ATP-antiphishingbeleid, of aangepast ATP-antiphishingbeleid maken en configureren.

### <a name="policy-settings-in-atp-anti-phishing-policies"></a>Beleidsinstellingen in atp-antiphishingbeleid

De volgende beleidsinstellingen zijn alleen beschikbaar in het ATP-anti-phishingbeleid:

- **Naam**: U de naam van het standaardbeleid voor antiphishing niet wijzigen, maar u wel de naam en de naam wijzigen van aangepaste beleidsregels die u maakt.

- **Beschrijving** U geen beschrijving toevoegen aan het standaardantiphishingbeleid, maar u de beschrijving toevoegen en wijzigen voor aangepaste beleidsregels die u maakt.

- **Toegepast op**: Identificeert interne ontvangers waarop het ATP-anti-phishingbeleid van toepassing is. Deze waarde is vereist in aangepast beleid en niet beschikbaar in het standaardbeleid (het standaardbeleid is van toepassing op alle geadresseerden).

    U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

  - **Ontvanger is:** Een of meer postvakken, e-mailgebruikers of e-mailcontactpersonen in uw organisatie.
  - **De ontvanger is lid van**: Een of meer groepen in uw organisatie.
  - **Het domein**van de ontvanger is : Een of meer van de geconfigureerde geaccepteerde domeinen in Microsoft 365.

  - **Behalve wanneer**: Uitzonderingen voor de regel. De instellingen en het gedrag zijn precies zoals de voorwaarden:

    - **Ontvanger is**
    - **Ontvanger is lid van**
    - **Het domein van de ontvanger is**

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>Imitatie-instellingen in atp-anti-phishingbeleid

Imitatie is de plaats waar de afzender of het e-maildomein van de afzender in een bericht lijkt op een echte afzender of domein:

- Een voorbeeld imitatie van het domein contoso.com is ćóntoso.com.

- Een voorbeeld imitatie van de gebruiker michelle@contoso.com is michele@contoso.com.

Een geïmiteerd domein kan anders als legitiem worden beschouwd (geregistreerd domein, geconfigureerde e-mailverificatierecords, enz.), behalve dat het de bedoeling is om ontvangers te misleiden.

De volgende imitatie-instellingen zijn alleen beschikbaar in atp-anti-phishingbeleid:

- **Gebruikers om te beschermen**: Voorkomt dat de opgegeven interne of externe gebruikers zich voordoen. Bijvoorbeeld leidinggevenden (intern) en bestuursleden (extern). U maximaal 60 interne en externe adressen toevoegen. Deze lijst met beveiligde gebruikers verschilt van de lijst met ontvangers waarop het beleid van toepassing is in de instelling **Toegepast op.**

  U geeft bijvoorbeeld Felipe Apodaca (felipea@contoso.com) op als een beveiligde gebruiker in een beleid dat van toepassing is op de groep met de naam Executives. Binnenkomende berichten die worden verzonden naar leden van de groep Leidinggevenden waar Felipe Apodaca wordt nagebootst, worden uitgevoerd door het beleid (de actie die u configureert voor geïmiteerde gebruikers).

- **Domeinen om te beschermen:** voorkom dat de opgegeven domeinen worden nagebootst. Bijvoorbeeld alle domeinen die u bezit[(geaccepteerde domeinen)](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)of specifieke domeinen (domeinen waarvan u eigenaar bent of partnerdomeinen). Deze lijst met beveiligde domeinen verschilt van de lijst met domeinen waarop het beleid van toepassing is in de instelling **Toegepast op.**

  U geeft bijvoorbeeld tailspintoys.com op als een beveiligd domein in een beleid dat van toepassing is op leden van de groep met de naam Executives. Binnenkomende berichten die worden verzonden naar leden van de groep Leidinggevenden waarbij tailspintoys.com wordt geïmiteerd, worden uitgevoerd door het beleid (de actie die u configureert voor geïmiteerde domeinen).

- **Acties voor beveiligde gebruikers of domeinen:** kies de actie die u wilt uitvoeren op binnenkomende berichten die imitatiepogingen tegen de beveiligde gebruikers en beveiligde domeinen in het beleid bevatten. U verschillende acties opgeven voor imitatie van beveiligde gebruikers versus imitatie van beveiligde domeinen:

  - **Geen actie toepassen**

  - **Bericht omleiden naar andere e-mailadressen**: stuurt het bericht naar de opgegeven ontvangers in plaats van de beoogde ontvangers.

  - **Bericht verplaatsen naar map Ongewenste e-mail:** het bericht wordt naar het postvak bezorgd en verplaatst naar de map Ongewenste e-mail. In Exchange Online wordt het bericht verplaatst naar de map Ongewenste e-mail als de regel voor ongewenste e-mail is ingeschakeld in het postvak (het is standaard ingeschakeld). Zie [Instellingen voor ongewenste e-mail configureren in Exchange Online-postvakken configureren in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie.

    - **Quarantaine het bericht**: Stuurt het bericht naar quarantaine in plaats van de beoogde ontvangers. Zie de volgende artikelen voor meer informatie over quarantaine:

    - [Quarantaine in Microsoft 365](quarantine-email-messages.md)
    - [Berichten en bestanden in quarantaine beheren als beheerder in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Berichten in quarantaine zoeken en vrijgeven als gebruiker in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

  - **Het bericht overbrengen en andere adressen toevoegen aan de BCC-regel:** Breng het bericht naar de beoogde ontvangers en lever het bericht stilletjes af aan de opgegeven ontvangers.

  - **Het bericht verwijderen voordat het wordt bezorgd:** verwijdert in stilte het hele bericht, inclusief alle bijlagen.

- **Veiligheidstips**: Hiermee worden de volgende veiligheidstips voor imitatie in- of uitgeschakeld die berichten weergeven die niet nabootsen:

  - **Geïmiteerde gebruikers**: Het van-adres bevat een beveiligde gebruiker.
  - **Geïmiteerde domeinen**: Het adres Van bevat een beveiligd domein.
  - **Ongebruikelijke tekens**: Het adres Van bevat ongebruikelijke tekensets (bijvoorbeeld wiskundige symbolen en tekst of een mix van hoofdletters en kleine letters) in een beveiligde afzender of domein.

- **Postvakintelligentie**: Hiermee schakelt u kunstmatige intelligentie (AI) in die de e-mailpatronen van gebruikers bepaalt met hun frequente contacten. Met deze instelling maakt de AI onderscheid tussen legitieme en vervalste e-mail van die contactpersonen. Postvakinformatie is alleen beschikbaar voor Exchange Online-postvakken.

- **Op postvakinformatie gebaseerde imitatiebeveiliging**: Hiermee worden verbeterde imitatieresultaten ingeschakeld of uitgeschakeld op basis van de individuele afzenderkaart van elke gebruiker. Met deze intelligentie kan Microsoft 365 de detectie van imitatie van gebruikers aanpassen en valse positieven beter verwerken. Wanneer imitatie van de gebruiker wordt gedetecteerd, u een specifieke actie definiëren die u op het bericht moet uitvoeren:

  - **Geen actie toepassen**
  - **Bericht omleiden naar andere e-mailadressen**
  - **Bericht verplaatsen naar map Ongewenste e-mail**
  - **Quarantaine het bericht**
  - **Het bericht overbrengen en andere adressen toevoegen aan de BCC-regel**
  - **Het bericht verwijderen voordat het wordt bezorgd**

- **Vertrouwde afzenders en domeinen**: uitzonderingen op de instellingen voor imitatiebeveiliging. Berichten van de opgegeven afzender- en afzenderdomeinen worden nooit geclassificeerd als aanvallen op basis van imitatie door het beleid. Met andere woorden, de actie voor beveiligde afzenders, beveiligde domeinen of postvakintelligentiebeveiliging wordt niet toegepast op deze vertrouwde afzenders of afzenderdomeinen. De maximumlimiet voor deze lijsten is ongeveer 1000 vermeldingen.

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a>Geavanceerde phishingdrempels in atp-anti-phishingbeleid

De volgende geavanceerde phishingdrempels zijn alleen beschikbaar in atp-antiphishingbeleid om de gevoeligheid voor het toepassen van machine learning-modellen op berichten voor het bepalen van een phishing-vonnis te controleren:

- **1 - Standaard**: dit is de standaardwaarde. De ernst van de actie die is ondernomen op het bericht hangt af van de mate van vertrouwen dat het bericht is phishing (laag, gemiddeld, hoog, of zeer hoog vertrouwen). Berichten die worden geïdentificeerd als phishing met een zeer hoge mate van vertrouwen, hebben bijvoorbeeld de zwaarste acties toegepast, terwijl berichten die worden geïdentificeerd als phishing met een lage mate van vertrouwen minder ernstige acties hebben toegepast.

- **2 - Agressief**: Berichten die worden geïdentificeerd als phishing met een hoge mate van vertrouwen worden behandeld alsof ze werden geïdentificeerd met een zeer hoge mate van vertrouwen.

- **3 - Agressiever**: Berichten die worden geïdentificeerd als phishing met een gemiddelde of hoge mate van vertrouwen worden behandeld alsof ze met een zeer hoge mate van vertrouwen zijn geïdentificeerd.

- **4 - Meest agressief**: Berichten die worden geïdentificeerd als phishing met een lage, medium, of hoge mate van vertrouwen worden behandeld alsof ze werden geïdentificeerd met een zeer hoge mate van vertrouwen.

De kans op false positives (goede berichten gemarkeerd als slecht) neemt toe naarmate u deze instelling verhoogt. Zie Beleidsinstellingen voor office [ATP-beleid](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)voor phishing voor meer informatie over de aanbevolen instellingen.