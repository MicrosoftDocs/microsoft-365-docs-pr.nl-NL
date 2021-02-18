---
title: Beleid tegen phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer informatie krijgen over het anti-phishingbeleid dat beschikbaar is in Exchange Online Protection (EOP) en Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 083fd4ae7e5564f2affeca73dd3d78a52657c5a7
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287315"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Anti-phishingbeleid in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Beleid voor het configureren van anti-phishingbeveiligingsinstellingen is beschikbaar in Microsoft 365-organisaties met Exchange Online-postvakken, zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken en Microsoft Defender voor Office 365-organisaties.

Anti-phishingbeleid in Microsoft Defender voor Office 365 is alleen beschikbaar in organisaties met Defender voor Office 365. Bijvoorbeeld:

- Microsoft 365 Enterprise E5, Microsoft 365 Education A5, enzovoort
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Microsoft Defender voor Office 365 als een invoegverklaring](https://products.office.com/exchange/advance-threat-protection)

De grote verschillen tussen anti-phishingbeleid in EOP en anti-phishingbeleid in Microsoft Defender voor Office 365 worden in de volgende tabel beschreven:

****

|Functie|Anti-phishingbeleid in EOP|Anti-phishingbeleid in Microsoft Defender voor Office 365|
|---|:---:|:---:|
|Automatisch standaardbeleid gemaakt|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|
|Aangepaste beleidsregels maken|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|
|Beleidsinstellingen<sup>\*</sup>|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|
|Imitatie-instellingen||![Vinkje](../../media/checkmark.png)|
|Instellingen voor adresvervalsing|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|
|Geavanceerde drempelwaarden voor phishing||![Vinkje](../../media/checkmark.png)|
|

<sup>\*</sup> In het standaardbeleid zijn de beleidsnaam en beschrijving alleen-lezen (de beschrijving is leeg) en kunt u niet opgeven op wie het beleid van toepassing is (het standaardbeleid geldt voor alle geadresseerden).

Zie de volgende artikelen om anti-phishingbeleid te configureren:

- [Antiphishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md)

- [Anti-phishingbeleid configureren in Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md)

In de rest van dit artikel worden de instellingen beschreven die beschikbaar zijn in anti-phishingbeleid in EOP en Defender voor Office 365.

## <a name="policy-settings"></a>Beleidsinstellingen

De volgende beleidsinstellingen zijn beschikbaar in anti-phishingbeleid in EOP en Microsoft Defender voor Office 365:

- **Naam:** U kunt de naam van het standaard anti-phishingbeleid niet wijzigen, maar u kunt wel aangepaste beleidsregels die u maakt een naam geven en de naam wijzigen.

- **Beschrijving** U kunt geen beschrijving toevoegen aan het standaard anti-phishingbeleid, maar u kunt wel de beschrijving toevoegen en wijzigen voor aangepaste beleidsregels die u maakt.

- **Toegepast op:** identificeert interne geadresseerden op wie het anti-phishingbeleid van toepassing is. Deze waarde is vereist in aangepast beleid en is niet beschikbaar in het standaardbeleid (het standaardbeleid is van toepassing op alle geadresseerden).

  U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

  - **De ontvanger is:** een of meer postvakken, e-mailgebruikers of e-mailcontactcontacten in uw organisatie.
  - **De ontvanger is lid van:** een of meer groepen in uw organisatie.
  - **Het domein van de** ontvanger is: een of meer van de geconfigureerde geaccepteerde domeinen in Microsoft 365.

  - **Behalve wanneer:** uitzonderingen voor de regel. De instellingen en het gedrag zijn precies hetzelfde als de voorwaarden:

    - **Ontvanger is**
    - **De ontvanger is lid van**
    - **Het domein van de ontvanger is**

  > [!NOTE]
  > De **instelling Toegepast op** is vereist in aangepaste  anti-phishing-beleidsregels om te bepalen voor welke geadresseerden van het bericht het beleid van <u>toepassing is.</u> Anti-phishingbeleid in Microsoft Defender voor Office [](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 365 heeft ook imitatie-instellingen waar u <u></u> e-mailadressen van afzonderlijke afzenders of afzenderdomeinen kunt opgeven die imitatiebeveiliging krijgen, zoals verder in dit artikel wordt beschreven.

## <a name="spoof-settings"></a>Instellingen voor adresvervalsing

Spoofing is wanneer het Van-adres in een e-mailbericht (het afzenderadres dat wordt weergegeven in e-mail clients) niet overeen komt met het domein van de e-mailbron. Zie Beveiliging tegen spoofing [in Microsoft 365](anti-spoofing-protection.md)voor meer informatie over spoofing.

De volgende spoof-instellingen zijn beschikbaar in anti-phishingbeleid in EOP en Microsoft Defender voor Office 365:

- **Bescherming tegen spoofing:** hiermee schakelt u beveiliging tegen spoofing in of uit. Het is raadzaam om deze ingeschakeld te laten. U gebruikt het **spoof intelligence-beleid om** specifieke vervalste interne en externe afzenders toe te staan of te blokkeren. Zie [spoof-intelligentie configureren in Microsoft 365](learn-about-spoof-intelligence.md) voor meer informatie.

  > [!NOTE]
  >
  > - Beveiliging tegen spoofing is standaard ingeschakeld in het standaardbeleid tegen phishing en in elk nieuw aangepast anti-phishingbeleid dat u maakt.
  >
  > - U hoeft beveiliging tegen adresvervalsing niet uit te schakelen als uw MX-record niet naar Microsoft 365 betekent. hebt u in plaats daarvan Enhanced Filtering for Connectors ingeschakeld. Zie [Enhanced Filtering for Connectors in Exchange Online voor instructies.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)
  >
  > - Als u de beveiliging tegen adresvervalsing uit schakelen, worden impliciete spoofing-beveiliging alleen uitgeschakeld tegen [samengestelde verificatiecontroles.](email-validation-and-authentication.md#composite-authentication) Als de afzender niet expliciet [DMARC controleert](use-dmarc-to-validate-email.md) waar het beleid is ingesteld op quarantaine of weigeren, wordt het bericht nog steeds in quarantaine geplaatst of geweigerd.

  Voor berichten van geblokkeerde afzenders met adresvervalsing kunt u ook aangeven welke actie er moet worden ondernomen op de berichten:

  - **Bericht verplaatsen naar map Ongewenste e-mail:** dit is de standaardwaarde. Het bericht wordt bezorgd in het postvak en verplaatst naar de map Ongewenste e-mail. In Exchange Online wordt het bericht verplaatst naar de map Ongewenste e-mail als de regel voor ongewenste e-mail is ingeschakeld in het postvak (dit is standaard ingeschakeld). Zie Instellingen voor ongewenste [e-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie.

  - **Het bericht in quarantaine** plaatsen: hiermee wordt het bericht in quarantaine geplaatst in plaats van de geadresseerden. Zie de volgende artikelen voor informatie over quarantaine:

    - [Quarantaine in Microsoft 365](quarantine-email-messages.md)
    - [Berichten en bestanden in quarantaine beheren als beheerder in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Berichten in quarantaine als gebruiker zoeken en vrijgeven in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

- **Niet-geauteerde afzender:** zie de informatie in de volgende sectie.

### <a name="unauthenticated-sender"></a>Niet-geauteerde afzender

Identificatie van niet-geauteerde afzender maakt deel uit van de [spoof-instellingen](#spoof-settings) die beschikbaar zijn in anti-phishingbeleid in EOP en Microsoft Defender voor Office 365, zoals beschreven in de vorige sectie.

Met **de instelling Niet-geauteerde** afzender kunt u de identificatie van niet-geauteerde afzender in Outlook in- of uitschakelen. Met name:

- Er wordt een vraagteken (?) toegevoegd aan de foto van de afzender als  het bericht niet door SPF- of DKIM-controles wordt gecontroleerd en het bericht niet door DMARC- of samengestelde verificatie [komt.](email-validation-and-authentication.md#composite-authentication) Als u de identificatie van niet-geauteerde afzender uit te stellen, voorkomt u dat het vraagteken wordt toegevoegd aan de foto van de afzender.

- De via-code (chris@contoso.com <u>via</u> fabrikam.com) wordt toegevoegd als het domein in het Van-adres (de afzender van het bericht dat wordt weergegeven in e-mail clients) verschilt van het domein in de DKIM-handtekening of het **MAIL FROM-adres.** Zie een overzicht van de standaarden voor [e-mailberichten voor meer](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)informatie over deze adressen.

  Het uitschakelen van de identificatie van niet-geauteerde afzenders voorkomt niet dat de via-code wordt toegevoegd als het domein in het Van-adres verschilt van het domein in de DKIM-handtekening of het MAIL FROM-adres.

Als u wilt voorkomen dat het vraagteken of via een tag wordt toegevoegd aan berichten van specifieke afzenders, hebt u de volgende opties:

- Sta de afzender toe spoofing in het spoof intelligence-beleid te gebruiken. Met deze actie wordt voorkomen dat de via-code wordt weergegeven in berichten van de afzender wanneer de identificatie van niet-geauteerde afzender is uitgeschakeld. Zie Spoof [Intelligence configureren in Microsoft 365](learn-about-spoof-intelligence.md)voor instructies.

- [Configureer e-mailverificatie](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) voor het domein van de afzender.
  - Voor het vraagteken op de foto van de afzender zijn SPF of DKIM de belangrijkste.
  - Bevestig voor de via-code dat het domein in de DKIM-handtekening of het **MAIL FROM-adres** overeenkomt (of is een subdomein van) het domein in het Van-adres.

Zie Verdachte berichten identificeren in Outlook.com [en de webversie van Outlook voor meer informatie.](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Exclusieve instellingen in anti-phishingbeleid in Microsoft Defender voor Office 365

In deze sectie worden de beleidsinstellingen beschreven die alleen beschikbaar zijn in anti-phishingbeleid in Microsoft Defender voor Office 365.

> [!NOTE]
> Het standaardbeleid tegen phishing in Microsoft Defender voor Office 365 biedt [spoof-beveiliging](set-up-anti-phishing-policies.md#spoof-settings) en postvakinformatie voor alle geadresseerden. De andere beschikbare functies voor [](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) [imitatiebeveiliging](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) en geavanceerde instellingen worden echter niet geconfigureerd of ingeschakeld in het standaardbeleid. Als u alle beveiligingsfuncties wilt inschakelen, wijzigt u het standaardbeleid tegen phishing of maakt u aanvullende anti-phishingbeleidsregels.

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Imitatie-instellingen in anti-phishingbeleid in Microsoft Defender voor Office 365

Imitatie is waar de afzender of het e-maildomein van de afzender in een bericht eruitziet als een echte afzender of domein:

- Een voorbeeld van een imitatie van het domein contoso.com wordt ćóntoso.com.
- Een voorbeeld van een imitatie van de michelle@contoso.com gebruiker wordt michele@contoso.com.

Een gemitmiteerd domein wordt anders als legitiem beschouwd (geregistreerd domein, geconfigureerde e-mailverificatierecords, enzovoort), behalve dat het de bedoeling is geadresseerden te verleiden.

De volgende imitatie-instellingen zijn alleen beschikbaar in anti-phishingbeleid in Microsoft Defender voor Office 365:

- **Ter bescherming van gebruikers:** voorkomt dat de opgegeven interne of externe e-mailadressen worden gemitmiteerd **als afzenders** van berichten. U ontvangt bijvoorbeeld een e-mailbericht van de adjunct-directeur van uw bedrijf waarin u wordt gevraagd haar interne bedrijfsgegevens te sturen. Zou u dit doen? Veel mensen verzenden het antwoord zonder te denken.

  U kunt beveiligde gebruikers gebruiken om e-mailadressen van interne en externe afzenders toe te voegen om te beschermen tegen imitatie. Deze lijst met **afzenders** die zijn beveiligd tegen gebruikers imitatie, verschilt van de lijst met geadresseerden die het beleid van  toepassing is [](#policy-settings) (alle geadresseerden voor het standaardbeleid; specifieke geadresseerden die zijn geconfigureerd in de instelling Toegepast op in de sectie Beleidsinstellingen). 

  > [!NOTE]
  >
  > - In elk anti-phishingbeleid kunt u maximaal 60 beveiligde gebruikers (e-mailadressen van afzenders) opgeven. U kunt dezelfde beveiligde gebruiker niet opgeven in meerdere beleidsregels. Ongeacht hoeveel beleidsregels van toepassing zijn op een geadresseerde, is het maximum aantal beveiligde gebruikers (e-mailadressen van afzenders) voor elke afzonderlijke geadresseerde dus 60. Zie Volgorde en prioriteit van e-mailbeveiliging voor meer informatie over de beleidsprioriteit en hoe de verwerking van beleid stopt nadat het eerste beleid [is toegepast.](how-policies-and-protections-are-combined.md)
  >
  > - Beveiliging tegen gebruikers imitatie werkt niet als de afzender en de ontvanger eerder via e-mail hebben gecommuniceerd. Als de afzender en geadresseerde nooit per e-mail hebben gecommuniceerd, wordt het bericht geïdentificeerd als een imitatiepoging.

  Standaard worden er geen e-mailadressen van afzenders geconfigureerd voor imitatiebeveiliging in **Gebruikers om te beveiligen.** Daarom worden er standaard geen e-mailadressen van afzenders gedekt door imitatiebeveiliging in het standaardbeleid of in aangepaste beleidsregels.

  Wanneer u interne of externe e-mailadressen toevoegt aan de gebruikers om de lijst te beveiligen, worden berichten van die **afzenders** gecontroleerd op imitatiebeveiliging.  Het bericht is ingeschakeld voor imitatie **als**  het bericht wordt verzonden naar een geadresseerde op wie het beleid van toepassing is (alle geadresseerden voor het standaardbeleid; **Toegepast op** geadresseerden in aangepaste beleidsregels). Als er imitatie wordt gedetecteerd in het e-mailadres van de afzender, worden de imitatiebeveiligingsacties voor gebruikers toegepast op het bericht (wat moet ik doen met het bericht, of er veiligheidstips voor gebruikers worden weergegeven, enzovoort).

- **Te beveiligen domeinen:** voorkomt dat de opgegeven domeinen worden gemitmiteerd in het domein van de **afzender van het bericht.** Bijvoorbeeld alle domeinen die in uw bezit zijn[(geaccepteerde](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)domeinen) of specifieke domeinen (domeinen die u bezit of partnerdomeinen). Deze lijst met afzenderdomeinen die zijn beveiligd tegen  imitatie, verschilt van de lijst met geadresseerden waar het beleid op  van toepassing is [](#policy-settings) (alle geadresseerden voor het standaardbeleid; specifieke geadresseerden die zijn geconfigureerd in de instelling Toegepast op in de sectie Beleidsinstellingen). 

  > [!NOTE]
  > Het maximum aantal beveiligde domeinen dat u kunt definiëren in alle anti-phishingbeleidsregels is 50.

  Standaard zijn er geen afzenderdomeinen geconfigureerd voor imitatiebeveiliging in **domeinen om te beveiligen.** Daarom worden er standaard geen afzenderdomeinen gedekt door imitatiebeveiliging in het standaardbeleid of in aangepaste beleidsregels.

  Wanneer u domeinen toevoegt aan de domeinen om de lijst te beveiligen, worden berichten van **afzenders in** die domeinen gecontroleerd op imitatiebeveiliging.  Het bericht is ingeschakeld voor imitatie **als**  het bericht wordt verzonden naar een geadresseerde op wie het beleid van toepassing is (alle geadresseerden voor het standaardbeleid; **Toegepast op** geadresseerden in aangepaste beleidsregels). Als er imitatie wordt gedetecteerd in het domein van de afzender, worden de imitatiebeveiligingsacties voor domeinen toegepast op het bericht (wat moet u doen met het bericht, of er veiligheidstips voor gebruikers worden weergegeven, enzovoort).

- **Acties voor beveiligde gebruikers of** domeinen: kies de actie die u wilt uitvoeren op inkomende berichten die imitatiepogingen bevatten tegen de beveiligde gebruikers en beveiligde domeinen in het beleid. U kunt verschillende acties opgeven voor imitatie van beveiligde gebruikers versus imitatie van beveiligde domeinen:

  - **Geen actie toepassen**

  - **Bericht omleiden naar andere e-mailadressen:** hiermee wordt het bericht verzonden naar de opgegeven geadresseerden in plaats van naar de geadresseerden.

  - **Bericht verplaatsen naar map Ongewenste** e-mail: het bericht wordt bezorgd in het postvak en verplaatst naar de map Ongewenste e-mail. In Exchange Online wordt het bericht verplaatst naar de map Ongewenste e-mail als de regel voor ongewenste e-mail is ingeschakeld in het postvak (dit is standaard ingeschakeld). Zie Instellingen voor ongewenste [e-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie.

    - **Het bericht in quarantaine** plaatsen: hiermee wordt het bericht in quarantaine geplaatst in plaats van de geadresseerden. Zie de volgende artikelen voor informatie over quarantaine:

    - [Quarantaine in Microsoft 365](quarantine-email-messages.md)
    - [Berichten en bestanden in quarantaine beheren als beheerder in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Berichten in quarantaine als gebruiker zoeken en vrijgeven in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

  - **Bezorg het bericht en voeg** andere adressen toe aan de BCC-regel: Bezorg het bericht bij de beoogde geadresseerden en bezorg het bericht op de gewenste locatie.

  - **Verwijder het bericht voordat het wordt** bezorgd: op de silently verwijdert u het hele bericht, inclusief alle bijlagen.

- **Veiligheidstips:** hiermee schakelt u de volgende veiligheidstips voor imitatie in of uit. Er worden berichten weergegeven die geen imitatiecontroles uitvoeren:

  - **Gemitmiteerde gebruikers:** het Van-adres bevat een beveiligde gebruiker.
  - **Gemitmiteerde domeinen:** het Van-adres bevat een beveiligd domein.
  - **Ongebruikelijke tekens:** het Van-adres bevat ongebruikelijke tekensets (bijvoorbeeld wiskundige symbolen en tekst of een combinatie van hoofdletters en kleine letters) in een beveiligde afzender of domein.


  > [!IMPORTANT]
  >
  > Aanbeveling voor het inschakelen van een veiligheidstip die wordt weergegeven tijdens de eerste keer dat een contactpersoon tussen de afzender en de **ontvanger(s)** wordt weergegeven: zelfs als de veiligheidstips voor imitatie zijn uitgeschakeld,  raden **we** u aan een e-mailstroomregel (ook wel transportregel genoemd) te gebruiken om een berichtkop met de naam **X-MS-Exchange-EnableFirstContactSafetyTip** met waarde voor berichten toe te voegen. Met een veiligheidstip worden geadresseerden op de hoogte gebracht wanneer ze de eerste keer een bericht van de afzender ontvangen of als ze niet vaak berichten van de afzender ontvangen. Deze mogelijkheid voegt een extra beveiligingslaag toe tegen potentiële imitatieaanvallen. 
  > :::image type="content" source="../../media/safety-tip-first-contact-multiple-recipients.png" alt-text="De tekst van de veiligheidstip voor imitatiebeveiliging met meerdere geadresseerden.":::

- **Postvakinformatie:** schakelt kunstmatige intelligentie (AI) in of uit die e-mailpatronen van gebruikers met veelgebruikte contactpersonen bepaalt. Deze instelling helpt de AI onderscheid te maken tussen legitieme en vervalste e-mails van die contactpersonen. Postvakinformatie is alleen beschikbaar voor Exchange Online-postvakken.

- Beveiliging tegen imitatie op basis van **postvakinformatie:** schakelt uitgebreide imitatieresultaten in of uit op basis van de afzonderlijke afzenderkaart van elke gebruiker. Met deze intelligence kan Microsoft 365 detectie van gebruikers imitatie aanpassen en fout-positieven beter verwerken. Wanneer er gebruikers imitatie wordt gedetecteerd, kunt u een specifieke actie definiëren die moet worden ondernomen op het bericht:

  - **Geen actie toepassen**
  - **Bericht omleiden naar andere e-mailadressen**
  - **Bericht verplaatsen naar map Ongewenste e-mail**
  - **Het bericht in quarantaine plaatsen**
  - **Bezorg het bericht en voeg andere adressen toe aan de BCC-regel**
  - **Het bericht verwijderen voordat het wordt bezorgd**

- **Vertrouwde afzenders en domeinen:** uitzonderingen op de instellingen voor imitatiebeveiliging. Berichten van de opgegeven afzenders en afzenderdomeinen worden nooit door het beleid geclassificeerd als imitatieaanvallen. Met andere woorden, de actie voor beveiligde afzenders, beveiligde domeinen of postvakinformatiebeveiliging wordt niet toegepast op deze vertrouwde afzenders of afzenderdomeinen. De maximumlimiet voor deze lijsten is ongeveer 1000 vermeldingen.

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Geavanceerde drempelwaarden voor phishing in anti-phishingbeleid in Microsoft Defender voor Office 365

De volgende geavanceerde drempelwaarden voor phishing zijn alleen beschikbaar in anti-phishingbeleid in Microsoft Defender voor Office 365. Met deze drempels wordt de gevoeligheid bepaald voor het toepassen van machine learning-modellen op berichten om een phishing-phishingbericht te bepalen:

- **1 - Standaard:** dit is de standaardwaarde. De ernst van de actie die wordt ondernomen op het bericht, hangt af van de mate van vertrouwen dat het bericht phishing is (laag, gemiddeld, hoog of zeer vertrouwelijk). Voor berichten die worden geïdentificeerd als phishing en die zeer vertrouwelijk zijn, worden de meest ernstige acties toegepast, terwijl op berichten die zijn geïdentificeerd als phishing en die weinig vertrouwen hebben, minder ernstige acties zijn toegepast.

- **2 -** Aggressive: berichten die worden geïdentificeerd als phishing met een hoge mate van betrouwbaarheid, worden behandeld alsof ze met een zeer hoge betrouwbaarheid zijn geïdentificeerd.

- **3 - Meer** agressief: berichten die worden geïdentificeerd als phishing met een gemiddelde of hoge mate van betrouwbaarheid, worden behandeld alsof ze met een zeer hoge betrouwbaarheid zijn geïdentificeerd.

- **4 - Meest** agressief: berichten die worden geïdentificeerd als phishing met een lage, gemiddelde of hoge betrouwbaarheid, worden behandeld alsof ze zijn geïdentificeerd met een zeer hoge betrouwbaarheid.

De kans op fout-positieven (goede berichten gemarkeerd als slecht) neemt toe naarmate u deze instelling verhoogt. Zie het [anti-phishingbeleid in de instellingen van Microsoft Defender voor Office 365](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)voor meer informatie over de aanbevolen instellingen.
