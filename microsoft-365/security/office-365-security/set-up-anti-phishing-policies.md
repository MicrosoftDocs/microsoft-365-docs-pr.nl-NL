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
ms.openlocfilehash: 9e5cd60915699cd2adb42e575c25912f5f164a5b
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055131"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Anti-phishingbeleid in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Beleidsregels voor het configureren van anti-phishingbeveiligingsinstellingen zijn beschikbaar in Microsoft 365-organisaties met Exchange Online-postvakken, zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken en Microsoft Defender voor Office 365-organisaties.

Voorbeelden van Microsoft Defender voor Office 365 organisaties zijn:

- Microsoft 365 Enterprise E5, Microsoft 365 Education A5, enzovoort.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Microsoft Defender voor Office 365 als een invoegvoegvoeging](https://products.office.com/exchange/advance-threat-protection)

De verschillen op hoog niveau tussen anti-phishingbeleid in EOP en anti-phishingbeleid in Defender voor Office 365 worden in de volgende tabel beschreven:

<br>

****

|Functie|Anti-phishingbeleid in EOP|Anti-phishingbeleid in Defender voor Office 365|
|---|:---:|:---:|
|Automatisch standaardbeleid gemaakt|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|
|Aangepast beleid maken|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|
|Algemene beleidsinstellingen<sup>\*</sup>|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|
|Spoofinstellingen|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|
|Eerste contact veiligheidstip|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|
|Instellingen voor imitatie||![Vinkje](../../media/checkmark.png)|
|Geavanceerde phishingdrempels||![Vinkje](../../media/checkmark.png)|
|

<sup>\*</sup> In het standaardbeleid zijn de naam van het beleid en de beschrijving alleen-lezen (de beschrijving is leeg) en kunt u niet opgeven op wie het beleid van toepassing is (het standaardbeleid is van toepassing op alle geadresseerden).

Zie de volgende artikelen om anti-phishingbeleid te configureren:

- [Antiphishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md)
- [Anti-phishingbeleid configureren in Microsoft Defender voor Office 365](configure-mdo-anti-phishing-policies.md)

In de rest van dit artikel worden de instellingen beschreven die beschikbaar zijn in anti-phishingbeleid in EOP en Defender voor Office 365.

## <a name="common-policy-settings"></a>Algemene beleidsinstellingen

De volgende beleidsinstellingen zijn beschikbaar in anti-phishingbeleid in EOP en Defender voor Office 365:

- **Naam:** U kunt de naam van het standaard anti-phishingbeleid niet wijzigen. Nadat u een aangepast anti-phishingbeleid hebt gemaakt, kunt u de naam van het beleid niet wijzigen in de Microsoft 365 Defender portal.

- **Beschrijving** U kunt geen beschrijving toevoegen aan het standaard anti-phishingbeleid, maar u kunt wel de beschrijving toevoegen en wijzigen voor aangepaste beleidsregels die u maakt.

- **Gebruikers, groepen en domeinen:** identificeert interne geadresseerden op wie het anti-phishingbeleid van toepassing is. Deze waarde is vereist in aangepast beleid en is niet beschikbaar in het standaardbeleid (het standaardbeleid is van toepassing op alle geadresseerden).

  U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

  - **Gebruikers:** Een of meer postvakken, e-mailgebruikers of e-mailcontactcontacten in uw organisatie.
  - **Groepen:** Een of meer groepen in uw organisatie.
  - **Domeinen:** Een of meer van de geconfigureerde [geaccepteerde](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) domeinen in Microsoft 365.

  - **Sluit deze gebruikers, groepen en domeinen uit:** Uitzonderingen voor het beleid. De instellingen en het gedrag zijn precies hetzelfde als de voorwaarden:
    - **Gebruikers**
    - **Groepen**
    - **Domeinen**

  > [!NOTE]
  > Ten minste één selectie in de instellingen **Gebruikers,** groepen en domeinen is vereist  in aangepaste anti-phishingbeleidsregels om de geadresseerden van het bericht te identificeren op wie het beleid van toepassing <u>is.</u> Anti-phishingbeleid in Defender voor Office 365 [](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) bevat ook imitatie-instellingen waarin u e-mailadressen <u></u> van afzonderlijke afzenders of afzenderdomeinen kunt opgeven die imitatiebeveiliging ontvangen, zoals verder in dit artikel wordt beschreven.

## <a name="spoof-settings"></a>Spoofinstellingen

Spoofing is wanneer het Van-adres in een e-mailbericht (het afzenderadres dat wordt weergegeven in e-mail clients) niet overeenkomen met het domein van de e-mailbron. Zie Bescherming tegen spoofing in Microsoft 365 voor [meer informatie over spoofing.](anti-spoofing-protection.md)

De volgende spoofinstellingen zijn beschikbaar in anti-phishingbeleid in EOP en Defender voor Office 365:

- **Spoof intelligence inschakelen:** Schakel spoof intelligence in of uit. U wordt aangeraden deze ingeschakeld te laten.

  Wanneer spoof intelligence is  ingeschakeld, worden vervalste afzenders die automatisch zijn gedetecteerd en door spoof intelligence zijn toegestaan of geblokkeerd, in het inzicht van de spoof intelligence bekent. U kunt handmatig de spoof intelligence-uitspraak overschrijven om de gedetecteerde vervalste afzenders binnen het inzicht toe te staan of te blokkeren. Maar wanneer u dit doet, verdwijnt de vervalste afzender uit het inzicht in spoof intelligence en is deze nu alleen zichtbaar op het tabblad **Spoof** in de lijst Tenant toestaan/blokkeren. U kunt ook handmatig vermeldingen voor vervalste afzenders maken of blokkeren in de lijst Tenant toestaan/blokkeren. Zie de volgende artikelen voor meer informatie:

  - [Inzicht in spoof intelligence in EOP](learn-about-spoof-intelligence.md)
  - [De lijst Tenant toestaan/blokkeren beheren in EOP](tenant-allow-block-list.md)

  > [!NOTE]
  >
  > - Anti-spoofingbeveiliging is standaard ingeschakeld in het standaard anti-phishingbeleid en in nieuwe aangepaste anti-phishingbeleidsregels die u maakt.
  > - U hoeft de bescherming tegen spoofing niet uit te schakelen als uw MX-record niet naar de Microsoft 365; u in plaats daarvan Verbeterde filtering voor verbindingslijnen inschakelen. Zie [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).
  > - Als u bescherming tegen spoofing  uit schakelt, wordt impliciete spoofing-beveiliging alleen uitgeschakeld tegen [samengestelde verificatiecontroles.](email-validation-and-authentication.md#composite-authentication) Als de afzender _niet_ [expliciete DMARC](use-dmarc-to-validate-email.md) controleert waar het beleid is ingesteld op quarantaine of weigeren, wordt het bericht nog steeds in quarantaine geplaatst of geweigerd.

- **Meldingen van niet-nautische afzenders:** deze meldingen zijn alleen beschikbaar wanneer spoof intelligence is ingeschakeld. Zie de informatie in de volgende sectie.
- **Acties:** Voor berichten van geblokkeerde vervalste afzenders (automatisch geblokkeerd door spoof intelligence of handmatig geblokkeerd in de lijst Tenant Allow/Block), kunt u ook de actie opgeven voor de berichten:
  - **Berichten verplaatsen naar de mappen ongewenste e-mail** van de geadresseerden: dit is de standaardwaarde. Het bericht wordt bezorgd in het postvak en verplaatst naar de map Ongewenste e-mail. In Exchange Online wordt het bericht verplaatst naar de map Ongewenste e-mail als de regel ongewenste e-mail is ingeschakeld in het postvak (het is standaard ingeschakeld). Zie Instellingen voor ongewenste e-mail configureren op [Exchange Online postvakken in](configure-junk-email-settings-on-exo-mailboxes.md)Microsoft 365.
  - **Het bericht in quarantaine plaatsen:** hiermee wordt het bericht in quarantaine geplaatst in plaats van de beoogde geadresseerden. Zie de volgende artikelen voor informatie over quarantaine:
    - [Quarantaine in Microsoft 365](quarantine-email-messages.md)
    - [In quarantaine geplaatste berichten en bestanden beheren als beheerder in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Berichten in quarantaine zoeken en vrijgeven als gebruiker in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

### <a name="unauthenticated-sender"></a>Niet-genauteerde afzender

De niet-genauteerde afzendermeldingen maken deel uit van de [spoofinstellingen](#spoof-settings) die beschikbaar zijn in anti-phishingbeleid in EOP en Defender voor Office 365 zoals beschreven in de vorige sectie. De volgende instellingen zijn alleen beschikbaar wanneer spoof intelligence is ingeschakeld:

- **Weergeven (?)** voor niet-nautische afzenders voor spoof: met deze melding wordt een vraagteken toegevoegd aan de foto van de  afzender in het vak Van als het bericht niet door SPF- of DKIM-controles wordt gecontroleerd en het bericht niet door DMARC of samengestelde verificatie [komt.](email-validation-and-authentication.md#composite-authentication) Wanneer deze instelling is uitgeschakeld, wordt het vraagteken niet toegevoegd aan de foto van de afzender.

- **'via' tag weergeven?**: met deze melding wordt de via-tag (chris@contoso.com <u>via</u> fabrikam.com) toegevoegd aan het vak Van als het domein in het Van-adres (de afzender van het bericht die wordt weergegeven in e-mail clients) verschilt van het domein in de DKIM-handtekening of het **MAIL FROM-adres.** Zie Een overzicht van de standaarden voor [e-mailberichten](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)voor meer informatie over deze adressen.

Als u wilt voorkomen dat het vraagteken of via een tag wordt toegevoegd aan berichten van specifieke afzenders, hebt u de volgende opties:

- Sta de vervalste afzender toe in het inzicht van [de spoof intelligence](learn-about-spoof-intelligence.md) of handmatig in de Tenant [Allow/Block List](tenant-allow-block-list.md). Als u de vervalste afzender toestaat, wordt de tag via niet weergegeven in berichten van de afzender wanneer de identificatie van niet-nautische afzenders is uitgeschakeld.
- [E-mailverificatie configureren](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) voor het afzenderdomein.
  - Voor het vraagteken op de foto van de afzender zijn SPF of DKIM het belangrijkste.
  - Bevestig voor de via-tag het domein in de DKIM-handtekening of het **MAIL FROM-adres** komt overeen (of is een subdomein van) het domein in het Van-adres.

Zie Verdachte berichten identificeren [in Outlook.com en webversie van Outlook](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="first-contact-safety-tip"></a>Eerste contact veiligheidstip

De instellingen voor eerste **contact veiligheidstip** is beschikbaar in EOP en Defender voor Office 365 organisaties en is niet afhankelijk van spoof intelligence- of imitatiebeveiligingsinstellingen. De veiligheidstip wordt weergegeven aan geadresseerden in de volgende scenario's:

- De eerste keer dat ze een bericht van een afzender ontvangen
- Als ze niet vaak berichten van de afzender ontvangen.

![De tekst van het veiligheidstip voor imitatiebeveiliging bij meerdere geadresseerden.](../../media/safety-tip-first-contact-multiple-recipients.png)

Deze mogelijkheid voegt een extra beveiligingslaag toe tegen mogelijke imitatieaanvallen, dus raden we u aan deze in te zetten.

De eerste contactpersoon veiligheidstip vervangt ook de noodzaak om regels voor e-mailstroom (ook wel transportregels genoemd) te maken die de **koptekst X-MS-Exchange-EnableFirstContactSafetyTip** toevoegen met de waarde **Inschakelen** voor berichten (hoewel deze mogelijkheid nog steeds beschikbaar is).

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Exclusieve instellingen in anti-phishingbeleid in Microsoft Defender voor Office 365

In deze sectie worden de beleidsinstellingen beschreven die alleen beschikbaar zijn in anti-phishingbeleid in Defender voor Office 365.

> [!NOTE]
> Het standaard anti-phishingbeleid in Defender voor Office 365 biedt [spoofbeveiliging](set-up-anti-phishing-policies.md#spoof-settings) en postvakinformatie voor alle geadresseerden. De andere beschikbare functies voor [imitatiebeveiliging](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) en geavanceerde instellingen [zijn](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) echter niet geconfigureerd of ingeschakeld in het standaardbeleid. Als u alle beveiligingsfuncties wilt inschakelen, wijzigt u het standaardbeleid voor phishing of maakt u extra anti-phishingbeleid.

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Imitatie-instellingen in anti-phishingbeleid in Microsoft Defender voor Office 365

Imitatie is de plaats waar de afzender of het e-maildomein van de afzender in een bericht lijkt op een echte afzender of domein:

- Een voorbeeld van imitatie van het domein contoso.com is ćóntoso.com.
- Een voorbeeld van imitatie van de gebruiker michelle@contoso.com is michele@contoso.com.

Een nabootsend domein kan anders als legitiem worden beschouwd (geregistreerd domein, geconfigureerde e-mailverificatierecords, enzovoort), behalve dat het de bedoeling is geadresseerden te misleiden.

De volgende imitatie-instellingen zijn alleen beschikbaar in anti-phishingbeleid in Defender voor Office 365:

- **Gebruikers inschakelen om te beveiligen:** voorkomt dat de opgegeven interne of externe e-mailadressen worden weergegeven **als afzenders van berichten.** U ontvangt bijvoorbeeld een e-mailbericht van de vice-president van uw bedrijf waarin u wordt gevraagd haar interne bedrijfsgegevens te sturen. Zou u het doen? Veel mensen sturen het antwoord zonder na te denken.

  U kunt beveiligde gebruikers gebruiken om e-mailadressen van interne en externe afzenders toe te voegen om te beschermen tegen imitatie. Deze lijst met **afzenders** die zijn beveiligd tegen gebruikersremitatie verschilt van de lijst met geadresseerden waar het beleid op van toepassing is (alle [](#common-policy-settings) geadresseerden voor het standaardbeleid; specifieke geadresseerden zoals geconfigureerd in de instelling **Gebruikers,** groepen en domeinen in de sectie Gemeenschappelijke beleidsinstellingen). 

  > [!NOTE]
  >
  > - In elk anti-phishingbeleid kunt u maximaal 60 beveiligde gebruikers opgeven (e-mailadressen van afzenders). U kunt niet dezelfde beveiligde gebruiker opgeven in meerdere beleidsregels. Ongeacht het aantal beleidsregels dat van toepassing is op een geadresseerde, is het maximum aantal beveiligde gebruikers (e-mailadressen van afzenders) voor elke afzonderlijke geadresseerde dus 60. Zie Volgorde en prioriteit van e-mailbeveiliging voor meer informatie over beleidsprioriteit en hoe de beleidsverwerking stopt nadat het eerste beleid is [toegepast.](how-policies-and-protections-are-combined.md)
  > - Gebruikersbeveiliging werkt niet als de afzender en geadresseerde eerder via e-mail hebben gecommuniceerd. Als de afzender en geadresseerde nooit via e-mail hebben gecommuniceerd, wordt het bericht geïdentificeerd als een imitatiepoging.

  Standaard worden geen e-mailadressen van afzenders geconfigureerd voor imitatiebeveiliging in **Gebruikers om te beveiligen.** Daarom worden standaard geen e-mailadressen van afzenders gedekt door imitatiebeveiliging, hetzij in het standaardbeleid of in aangepast beleid.

  Wanneer u interne of externe e-mailadressen toevoegt aan de lijst Gebruikers om de lijst te beveiligen, worden berichten van die **afzenders** onderworpen aan imitatiebeveiligingscontroles.  Het bericht wordt gecontroleerd op imitatie als  **het** bericht wordt verzonden naar een geadresseerde op wie het beleid van toepassing is (alle geadresseerden voor het standaardbeleid; **Gebruikers, groepen en geadresseerden van** domeinen in aangepast beleid). Als imitatie wordt gedetecteerd in het e-mailadres van de afzender, worden de acties voor imitatiebeveiliging voor gebruikers toegepast op het bericht (wat moet ik doen met het bericht, of er veiligheidstips voor nagebootsde gebruikers moeten worden weergegeven, enzovoort).

- **Domeinen beveiligen:** voorkomt dat de opgegeven domeinen worden nagebootsd in het domein van de afzender **van het bericht.** Bijvoorbeeld alle domeinen die u bezit[(geaccepteerde](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)domeinen) of specifieke aangepaste domeinen (domeinen die u bezit of partnerdomeinen). Deze lijst  met afzenderdomeinen die zijn beveiligd tegen imitatie verschilt van de lijst met geadresseerden waar het beleid op van toepassing is (alle geadresseerden [](#common-policy-settings) voor het standaardbeleid; specifieke geadresseerden zoals geconfigureerd in de instelling **Gebruikers,** groepen en domeinen in de sectie Gemeenschappelijke beleidsinstellingen). 

  > [!NOTE]
  > Het maximum aantal beveiligde domeinen dat u in alle anti-phishingbeleidsregels kunt definiëren, is 50.

  Standaard zijn er geen afzenderdomeinen geconfigureerd voor imitatiebeveiliging in **Domeinen beveiligen.** Daarom worden standaard geen afzenderdomeinen gedekt door imitatiebeveiliging, in het standaardbeleid of in aangepast beleid.

  Wanneer u domeinen toevoegt aan de lijst **Domeinen** inschakelen om te beveiligen, worden berichten van **afzenders in** die domeinen onderworpen aan imitatiebeveiligingscontroles. Het bericht wordt gecontroleerd op imitatie als  **het** bericht wordt verzonden naar een geadresseerde op wie het beleid van toepassing is (alle geadresseerden voor het standaardbeleid; **Gebruikers, groepen en geadresseerden van** domeinen in aangepast beleid). Als imitatie wordt gedetecteerd in het domein van de afzender, worden de imitatiebeveiligingsacties voor domeinen toegepast op het bericht (wat moet u doen met het bericht, of er veiligheidstips voor nagebootsde gebruikers worden weergegeven, enzovoort).

- **Acties:** Kies de actie die u wilt uitvoeren op inkomende berichten die imitatiepogingen bevatten tegen de beveiligde gebruikers en beveiligde domeinen in het beleid. U kunt verschillende acties opgeven voor imitatie van beveiligde gebruikers versus imitatie van beveiligde domeinen:
  - **Geen actie toepassen**
  - **Bericht omleiden naar andere e-mailadressen:** hiermee wordt het bericht verzonden naar de opgegeven geadresseerden in plaats van naar de beoogde geadresseerden.
  - **Berichten verplaatsen naar de mappen ongewenste** e-mail van de geadresseerden: het bericht wordt bezorgd in het postvak en verplaatst naar de map Ongewenste e-mail. In Exchange Online wordt het bericht verplaatst naar de map Ongewenste e-mail als de regel ongewenste e-mail is ingeschakeld in het postvak (het is standaard ingeschakeld). Zie Instellingen voor ongewenste e-mail configureren op [Exchange Online postvakken in](configure-junk-email-settings-on-exo-mailboxes.md)Microsoft 365.
  - **Het bericht in quarantaine plaatsen:** hiermee wordt het bericht in quarantaine geplaatst in plaats van de beoogde geadresseerden. Zie de volgende artikelen voor informatie over quarantaine:
    - [Quarantaine in Microsoft 365](quarantine-email-messages.md)
    - [In quarantaine geplaatste berichten en bestanden beheren als beheerder in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Berichten in quarantaine zoeken en vrijgeven als gebruiker in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)
  - **Bezorg het bericht en voeg andere** adressen toe aan de BCC-regel: Bezorg het bericht bij de beoogde geadresseerden en bezorg het bericht in stilte bij de opgegeven geadresseerden.
  - **Verwijder het bericht voordat het wordt bezorgd:** het hele bericht wordt geruisloos verwijderd, inclusief alle bijlagen.

- **Veiligheidstips voor** imitaties: Schakel de volgende veiligheidstips voor imitaties in of uit die berichten worden weergegeven die niet worden gecontroleerd op imitatie:
  - **Tip voor nagebootste gebruikers tonen:** het Van-adres bevat gebruikers **inschakelen om de gebruiker te** beveiligen. Alleen beschikbaar als **Gebruikers beveiligen** inschakelen is ingeschakeld en geconfigureerd.
  - **Tip voor nagebootste domeinen tonen:** het Van-adres bevat een **domein inschakelen om domein te** beveiligen. Alleen beschikbaar als **Domeinen beveiligen** inschakelen is ingeschakeld en geconfigureerd.
  - **Tip** voor ongebruikelijke tekens tonen: Het Van-adres bevat ongebruikelijke tekensets (bijvoorbeeld wiskundige symbolen en tekst  of een combinatie van hoofdletters en kleine letters) in een Enable users to protect sender or an **Enable domains** to protect sender domain.  Alleen beschikbaar als **Gebruikers inschakelen om**  domeinen **te** beveiligen of inschakelen is ingeschakeld en geconfigureerd.

- **Postvakintelligentie** inschakelen: kunstmatige intelligentie (AI) in- of uitschakelen die e-mailpatronen van gebruikers bepaalt met hun frequente contactpersonen. Deze instelling helpt de AI om onderscheid te maken tussen berichten van legitieme en nagebootsde afzenders.

  Zo is Gabriela Laureano (glaureano@contoso.com) de CEO van uw bedrijf, dus voegt u  haar toe als een beveiligde afzender in de instellingen van het beleid inschakelen voor gebruikers. Sommige geadresseerden die het beleid van toepassing is, communiceren echter regelmatig met een leverancier die ook Gabriela Laureano (glaureano@fabrikam.com). Omdat deze geadresseerden een communicatiegeschiedenis hebben met glaureano@fabrikam.com, worden berichten van glaureano@fabrikam.com niet door postvakinformatie als een imitatiepoging van glaureano@contoso.com voor deze geadresseerden.

  Als u veelgebruikte contactpersonen wilt gebruiken die zijn geleerd door postvakintelligentie  (en het ontbreken daarvan) om gebruikers te beschermen tegen imitatieaanvallen, kunt u Beveiliging voor het imiteren van intelligentie inschakelen inschakelen nadat u Postvakintelligentie inschakelen hebt **ingeschakeld.**

- **Beveiliging van imiteren van** intelligentie inschakelen: Schakel deze instelling in om de actie op te geven die moet worden ondernomen voor het opsporen van imitaties van postvakinformatieresultaten:
  - **Geen actie toepassen:** houd er rekening mee dat deze waarde hetzelfde resultaat heeft als het inschakelen van Postvakintelligentie,  maar het uitschakelen van beveiliging tegen het **imiteren van intelligentie inschakelen.**
  - **Bericht omleiden naar andere e-mailadressen**
  - **Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**
  - **Het bericht in quarantaine plaatsen**
  - **Het bericht bezorgen en andere adressen toevoegen aan de BCC-regel**
  - **Het bericht verwijderen voordat het wordt bezorgd**

- **Vertrouwde afzenders en domeinen toevoegen:** Uitzonderingen op de instellingen voor imitatiebeveiliging. Berichten van de opgegeven afzenders en afzenderdomeinen worden nooit door het beleid geclassificeerd als op imitatie gebaseerde aanvallen. Met andere woorden, de actie voor beveiligde afzenders, beveiligde domeinen of postvakinformatiebeveiliging wordt niet toegepast op deze vertrouwde afzenders of afzenderdomeinen. De maximumlimiet voor deze lijsten is ongeveer 1000 vermeldingen.

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Geavanceerde phishingdrempels in anti-phishingbeleid in Microsoft Defender voor Office 365

De volgende geavanceerde phishingdrempels zijn alleen beschikbaar in anti-phishingbeleid in Defender voor Office 365. Deze drempelwaarden bepalen de gevoeligheid voor het toepassen van machine learning-modellen op berichten om een phishing-uitspraak te bepalen:

- **1 - Standaard:** dit is de standaardwaarde. De ernst van de actie die wordt ondernomen op het bericht, is afhankelijk van de mate van vertrouwen dat het bericht phishing is (laag, gemiddeld, hoog of zeer hoog vertrouwen). Berichten die worden geïdentificeerd als phishing met een zeer hoge mate van vertrouwen, hebben bijvoorbeeld de meest ernstige acties toegepast, terwijl berichten die worden geïdentificeerd als phishing met een lage mate van vertrouwen, minder ernstige acties hebben toegepast.
- **2 - Agressief:** berichten die met een hoge mate van vertrouwen als phishing worden geïdentificeerd, worden behandeld alsof ze met een zeer hoge mate van vertrouwen zijn geïdentificeerd.
- **3 - Agressiever:** Berichten die worden geïdentificeerd als phishing met een gemiddelde of hoge mate van vertrouwen, worden behandeld alsof ze met een zeer hoge mate van vertrouwen zijn geïdentificeerd.
- **4 - Meest agressief:** Berichten die worden geïdentificeerd als phishing met een lage, gemiddelde of hoge mate van vertrouwen, worden behandeld alsof ze met een zeer hoge mate van vertrouwen zijn geïdentificeerd.

De kans op onwaar positieven (goede berichten die als slecht zijn gemarkeerd) neemt toe naarmate u deze instelling verhoogt. Zie [anti-phishingbeleid in Microsoft Defender](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)voor meer Office 365 informatie over de aanbevolen instellingen.
