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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie krijgen over het anti-phishings beleid dat beschikbaar is in Exchange Online Protection (EOP) en Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: a68baf8f2598b8ca0cd13e45d18919ecfdccdacc
ms.sourcegitcommit: 294a51ef0ff48dddb659c602e047d7fd98f91172
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/08/2020
ms.locfileid: "47407926"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Anti malafide beleid in Microsoft 365

Beleidsregels voor het configureren van anti-phishing-instellingen zijn beschikbaar in Microsoft 365-organisaties met postvakken van Exchange Online, standalone Exchange Online Protection-organisaties (EOP) zonder postvak van Exchange Online en Office 365 Advanced Threat Protection (Office 365 ATP).

ATP anti-phishing is alleen beschikbaar in organisaties die Office 365 ATP hebben. Bijvoorbeeld:

- Microsoft 365 Enterprise E5, Microsoft 365 education A5, etc.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Office 365 ATP als een invoegtoepassing](https://products.office.com/exchange/advance-threat-protection)

Alle andere organisaties hebben een anti-phishing beleid.

Het hoge niveau van de verschillen tussen anti-phishingfilter en ATP anti-phishingfilter worden beschreven in de volgende tabel:

****

|Functie|Beleid tegen phishing|ATP anti-phishings beleid|
|---|:---:|:---:|
|Standaardbeleid automatisch gemaakt|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Aangepaste beleidsregels maken|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Beleidsinstellingen<sup>\*</sup>|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Imitatie-instellingen||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Spoof-instellingen|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Geavanceerde phishingberichten||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<sup>\*</sup> In het standaardbeleid zijn de Beleidsnaam en-beschrijving alleen-lezen (de beschrijving is leeg) en kunt u niet opgeven wie het beleid van toepassing is op het standaardbeleid voor alle geadresseerden.

Zie de volgende artikelen voor meer informatie over het configureren van een anti phishing-beleid:

- [Anti-phishings beleid configureren in EOP](configure-anti-phishing-policies-eop.md)

- [ATP anti-phishing configureren in Microsoft 365](configure-atp-anti-phishing-policies.md)

In de rest van dit artikel worden de instellingen beschreven die beschikbaar zijn in anti-phishings beleid en het anti-phishingfilter van ATP.

## <a name="policy-settings"></a>Beleidsinstellingen

De volgende beleidsinstellingen zijn beschikbaar in anti phishingfilter en op een anti-phishingfilter-beleid:

- **Naam**: u kunt de naam van het standaard anti-Phishingfilter niet wijzigen, maar u kunt wel een naam geven en aangepaste beleidsregels maken die u zelf maakt.

- Een **Beschrijving** van U kunt geen beschrijving toevoegen aan het standaard anti-phishingfilter, maar u kunt wel een beschrijving toevoegen en wijzigen voor aangepaste beleidsregels die u maakt.

- **Toegepast op**: identificeert interne geadresseerden waarop het anti-phishingfilter-beleid van toepassing is. Deze waarde is vereist in aangepaste beleidsregels en niet beschikbaar in het standaardbeleid (het standaardbeleid is van toepassing op alle geadresseerden).

  U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

  - De **ontvanger is**: een of meer postvakken, e-mail gebruikers of contactpersonen in uw organisatie.
  - **De ontvanger is lid van**: een of meer groepen in uw organisatie.
  - **Het domein van de ontvanger is**: een of meer van de geconfigureerde domeinen in microsoft 365.

  - **Behalve wanneer**: uitzonderingen voor de regel. De instellingen en het gedrag zijn exact hetzelfde als de voorwaarden:

    - **Geadresseerde is**
    - **De ontvanger is lid van**
    - **Het domein van de ontvanger is**

  > [!NOTE]
  > De instelling **voor toepassen op** is vereist in een aangepast anti-phishingfilter om te identificeren <u>of het beleid van toepassing is op de</u> **ontvanger** . Een anti-phishing-beleid voor vrije gebruikers hebben ook [imitatie-instellingen](#impersonation-settings-in-atp-anti-phishing-policies) waar u <u>de</u> e-mailadressen of e-mailadressen van afzonderlijke e-mailadressen van de afzender kunt opgeven, zoals verderop in dit onderwerp wordt beschreven.

## <a name="spoof-settings"></a>Spoof-instellingen

Spoofing is wanneer het van-adres in een e-mailbericht (het adres van de afzender dat wordt weergegeven in e-mail cliënten) niet overeenkomen met het domein van de e-mail bron. Zie voor meer informatie over spoofing [bescherming tegen spoofing in Microsoft 365](anti-spoofing-protection.md).

De volgende spoof-instellingen zijn beschikbaar in anti-phishingfilter en op een ATP anti-phishings beleid:

- **Anti-spoofing beveiliging**: schakelt anti-spoofing beveiliging in of uit. U wordt aangeraden om de optie ingeschakeld te laten. U gebruikt het **beleid voor spoof Intelligence** om specifieke vervalste interne en externe afzenders toe te staan of te blokkeren. Zie [spoof-intelligentie configureren in Microsoft 365](learn-about-spoof-intelligence.md) voor meer informatie.

  > [!NOTE]
  > De instellingen voor spoofing zijn standaard ingeschakeld in het standaard anti-phishings beleid in EOP, het standaard-Phishingfilter anti-phishingfilter en een nieuw aangepast anti-phishingfilter-beleid of een vrij-Phishingfilter-beleid dat u maakt. <br/><br/> U hoeft geen anti-spoofing-beveiliging uit te schakelen als uw MX-record niet verwijst naar Microsoft 365. u kunt in plaats hiervan uitgebreid filteren op connectors. Zie voor meer informatie het artikel [uitgebreid filteren op connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

  Voor berichten van geblokkeerde vervalste afzenders kunt u ook opgeven welke actie u wilt uitvoeren op de berichten:

  - **Bericht verplaatsen naar map Ongewenste e-mail**: dit is de standaardwaarde. Het bericht wordt bezorgd in het postvak en wordt verplaatst naar de map Ongewenste E-mail. Het bericht wordt verplaatst naar de map Ongewenste e-mail in Exchange Online als de regel voor ongewenste e-mail is ingeschakeld voor het postvak (deze optie is standaard ingeschakeld). Zie voor meer informatie [instellingen voor ongewenste E-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

  - **Quarantine het bericht**: verzendt het bericht naar Quarantine in plaats van de bedoelde geadresseerden. Zie de volgende artikelen voor informatie over quarantaine:

    - [Quarantaine in Microsoft 365](quarantine-email-messages.md)
    - [Geplaatste berichten en bestanden beheren als beheerder in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Geplaatste berichten zoeken en vrijgeven als een gebruiker in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

- **Niet-geverifieerde afzender**: Zie de informatie in het volgende gedeelte.

### <a name="unauthenticated-sender"></a>Niet-geverifieerde afzender

Niet-geverifieerde afzender-identificatie maakt deel uit van de [spoof-instellingen](#spoof-settings) die beschikbaar zijn in anti-phishingfilter en op een anti-PHISHINGFILTER van ATP zoals beschreven in de vorige sectie.

Met de instelling niet- **geverifieerde afzender** schakelt u de identificatie van niet-geverifieerde afzender in Outlook in of uit. Precies

- U kunt een vraagteken (?) toevoegen aan de foto van de afzender als het bericht SPF-of DKIM-controles niet doorschakelt **en** het bericht geen DMARC of [samengestelde verificatie](email-validation-and-authentication.md#composite-authentication)passeert. Als u niet-geverifieerde afzender uitschakelt, wordt het vraagteken niet toegevoegd aan de foto van de afzender.

- Met de tag via (chris@contoso.com <u>via</u> Michelle@fabrikam.com) wordt de toevoeging van het domein in het van-adres (de afzender van het bericht dat wordt weergegeven in e-mail cliënten) anders dan het domein in de-handtekening of het **e-mail** adres. Zie [een overzicht van de standaarden voor e-mailberichten](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)voor meer informatie over deze adressen.

  Niet-geverifieerde afzender-id wordt niet voorkomen dat de via-code kan worden toegevoegd als het domein in het van-adres afwijkt van het domein in de DKIM-handtekening of het e-MAIL adres.

U hebt de volgende opties om te voorkomen dat het vraagteken of via tag wordt toegevoegd aan berichten van specifieke afzenders:

- Laat de afzender spoofen in het beleid voor spoof Intelligence. Met deze actie wordt voorkomen dat de via-code in berichten van de afzender wordt weergegeven als de id van de niet-geverifieerde afzender is uitgeschakeld. Zie voor instructies voor instructies het artikel [spoof Intelligence configureren in Microsoft 365](learn-about-spoof-intelligence.md).

- [Configureer e-mail verificatie](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) voor het domein van de afzender.
  
  - Voor het vraagteken in de foto van de afzender, SPF of DKIM zijn de belangrijkste punten.
  - Voor de via-tag bevestigt u het domein in de DKIM-handtekening of het e-mail adres dat overeenkomt met het **e-mail** adres of het subdomein van het domein in het van-adres.

Zie voor meer informatie [verdachte berichten identificeren in Outlook.com en de webversie van Outlook](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a>Exclusieve instellingen in ATP anti-phishings beleid

In dit gedeelte worden de beleidsinstellingen beschreven die alleen beschikbaar zijn in de ATP anti-phishingfilter-beleidsregels.

> [!NOTE]
> Standaard zijn de instellingen voor exclusief ATP niet geconfigureerd of ingeschakeld, zelfs in het standaardbeleid. Als u deze functies wilt gebruiken, moet u deze functie in-of uitschakelen in het standaard-anti-phishingfilter van ATP, of aangepaste ATP anti phishingfilter-beleidsregels maken en configureren.

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>Imitatie-instellingen in ATP anti-phishingfilter

Met imitatie wordt het e-mail domein van de afzender of het e-mail domein van de afzender in een bericht vergelijkbaar met een echte afzender of een domein:

- Een voorbeeld van imitatie van de domein contoso.com is ćóntoso.com.
- Een voorbeeld van imitatie van de User michelle@contoso.com is michele@contoso.com.

Mogelijk wordt een geïmiteerd domein ook als legitiem beschouwd (geregistreerd domein, geconfigureerde e-mail verificatie records, etc.), behalve dat de intentie van de geadresseerden de geadresseerden moet opzeggen.

De volgende imitatie-instellingen zijn alleen beschikbaar in het ATP anti-phishings beleid:

- **Te beschermen gebruikers**: voorkomt dat de opgegeven interne of externe e-mailadressen worden geïmiteerd **als afzenders van berichten**. Bijvoorbeeld leidinggevenden (interne afzenders) en bord leden (externe afzenders). U kunt maximaal 60 interne en externe afzender e-mailadressen toevoegen om te beschermen tegen imitatie. Deze lijst met **afzenders** die zijn beveiligd tegen imitatie, verschilt van de lijst met **geadresseerden** waarop het beleid van toepassing is.

  Het standaardbeleid is van toepassing op berichten die naar alle geadresseerden worden verzonden, terwijl aangepaste beleidsregels alleen van toepassing zijn op berichten die zijn **verzonden naar de** geadresseerden die u definieert in de sectie [beleidsinstellingen](#policy-settings) .

  Standaard worden er geen e-mailadressen van de afzender geconfigureerd voor imitatie bescherming in **gebruikers**. Daarom zijn de e-mailadressen van de afzender standaard niet onder de bescherming van de imitatie, hetzij in het standaardbeleid of in aangepaste beleidsregels.

  Wanneer u interne of externe e-mailadressen toevoegt aan de **gebruikers die** de lijst beveiligen, zijn berichten van deze **afzenders** onderworpen aan controles van de bescherming van de imitatie. Het bericht wordt gecontroleerd op imitatie **als** het bericht wordt verzonden naar een **geadresseerde** waarop het beleid van toepassing is (alle geadresseerden voor het standaardbeleid; Dit **geldt voor** geadresseerden in een aangepast beleid. Als er in het e-mailadres van de afzender in het e-mailadres van de afzender gebruik wordt gemaakt van imitatie, worden de acties voor imitatie bescherming voor gebruikers toegepast op het bericht (de actie voor het bericht, de melding voor geïmiteerde gebruikers, enzovoort).

- **Te beschermen domeinen**: voorkomt dat de opgegeven domeinen worden geïmiteerd **in het domein van de afzender van het bericht**. Voorbeelden van alle domeinen die u eigenaar bent ([geaccepteerde domeinen](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) of specifieke domeinen (domeinen die u bezit of een partnerdomein). In de lijst met geadresseerden waarvoor het beleid van toepassing is, is de **lijst met de** **geadresseerden** waarvoor het beleid van toepassing is, anders.

  Het standaardbeleid is van toepassing op berichten die naar alle geadresseerden worden verzonden, terwijl aangepaste beleidsregels alleen van toepassing zijn op berichten die zijn **verzonden naar de** geadresseerden die u definieert in de sectie [beleidsinstellingen](#policy-settings) .

  Standaard worden er geen verzender domeinen geconfigureerd voor de bescherming van imitatie in **domeinen**. Daarom worden niet-gegroepeerde domeinnamen bedoeld met de bescherming van de imitatie, hetzij in het standaardbeleid of aangepaste beleidsregels.

  Wanneer u domeinen toevoegt aan de **domeinen die u wilt beveiligen** , zijn berichten van **afzenders in die domeinen** onderhevig aan imitatie beschermings controles. Het bericht wordt gecontroleerd op imitatie **als** het bericht wordt verzonden naar een **geadresseerde** waarop het beleid van toepassing is (alle geadresseerden voor het standaardbeleid; Dit **geldt voor** geadresseerden in een aangepast beleid. Als er in het domein van de afzender een imitatie wordt gedetecteerd, worden de acties voor de bescherming van de bescherming voor domeinen toegepast op het bericht (de actie in het bericht, de beveiligings Tip van het domein, enzovoort).

- **Acties voor beveiligde gebruikers of domeinen**: Kies de actie die u wilt uitvoeren op inkomende berichten met de gewenste beschermings pogingen voor de beveiligde gebruikers en beveiligde domeinen in het beleid. U kunt verschillende acties opgeven voor imitatie van beveiligde gebruikers versus imitatie van beveiligde domeinen:

  - **Geen actie toepassen**

  - **Bericht omleiden naar andere e-mailadressen**: Hiermee wordt het bericht naar de opgegeven geadresseerden verzonden in plaats van de bedoelde geadresseerden.

  - **Bericht verplaatsen naar map Ongewenste**E-mail: het bericht wordt bezorgd in het postvak en verplaatst naar de map Ongewenste e-mail. Het bericht wordt verplaatst naar de map Ongewenste e-mail in Exchange Online als de regel voor ongewenste e-mail is ingeschakeld voor het postvak (deze optie is standaard ingeschakeld). Zie voor meer informatie [instellingen voor ongewenste E-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

    - **Quarantine het bericht**: verzendt het bericht naar Quarantine in plaats van de bedoelde geadresseerden. Zie de volgende artikelen voor informatie over quarantaine:

    - [Quarantaine in Microsoft 365](quarantine-email-messages.md)
    - [Geplaatste berichten en bestanden beheren als beheerder in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Geplaatste berichten zoeken en vrijgeven als een gebruiker in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

  - **Zorg dat u het bericht bezorgt en andere adressen aan de BCC-regel toevoegt**: Bezorg het bericht voor de geadresseerden en laat het bericht op de opgegeven geadresseerden staan.

  - **Het bericht verwijderen voordat het wordt bezorgd**: Hiermee wordt het volledige bericht, inclusief alle bijlagen, op de achtergrond verwijderd.

- **Veiligheidstips**: schakelt de volgende imitatie tips voor de bescherming van de persoon in of uit, die berichten weergeven die niet door de gebruiker worden gecontroleerd:

  - **Geïmiteerde gebruikers**: het van-adres bevat een beveiligde gebruiker.
  - **Geïmiteerde domeinen**: het van-adres bevat een beveiligd domein.
  - **Ongebruikelijk tekens**: het van-adres bevat ongebruikelijke tekensets (bijvoorbeeld wiskundige symbolen en tekst of een combinatie van hoofdletters en kleine letters) in een beveiligde afzender of domein.

- **Postvak intelligentie**: Hiermee wordt gecommuniceerd met de optie veelgebruikte contactpersonen (AI) in-of uitgeschakeld. Met deze instelling zorgt u ervoor dat de AI onderscheidt tussen legitieme en vervalste e-mail van deze contactpersonen. Postvak intelligentie is alleen beschikbaar voor postvakken van Exchange Online.

- **Op basis van de bescherming op basis**van de toegang tot de Cloud: schakelt uitgebreide imitatie resultaten in of uit op basis van de afzonderlijke toewijzingen van de afzonderlijke verzenders van elke gebruiker. Deze Intelligence zorgt ervoor dat Microsoft 365 de detectie van gebruikers imitatie aanpast en betere fout-positieven verduidelijkt. Wanneer gebruikers imitatie wordt gedetecteerd, kunt u opgeven welke actie u wilt uitvoeren op het bericht:

  - **Geen actie toepassen**
  - **Bericht omleiden naar andere e-mailadressen**
  - **Bericht verplaatsen naar map Ongewenste e-mail**
  - **Het bericht Quarantine**
  - **Het bericht bezorgen en andere adressen toevoegen aan de regel BCC**
  - **Het bericht verwijderen voordat het wordt bezorgd**

- **Vertrouwde afzenders en domeinen**: uitzonderingen op de instellingen voor imitatie bescherming. Berichten van de opgegeven domeinen van afzenders en afzender worden nooit als onbedoelde aanval geclassificeerd op basis van de beleidsregels voor imitatie. Met andere woorden: de actie voor beveiligde afzenders, beveiligde domeinen en e-mail beveiliging worden niet toegepast op de domeinen van de vertrouwde afzenders of van de afzender. De maximumlimiet voor deze lijsten is ongeveer 1000 vermeldingen.

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a>Geavanceerde phishing-drempels in een anti-phishingfilter-beleid

De volgende geavanceerde vergelijkings drempels zijn alleen beschikbaar in het ATP anti-phishings beleid voor het bepalen van de gevoeligheid voor het toepassen van machine learning modellen op berichten voor het bepalen van een malafide verdict:

- **1-standaard**: dit is de standaardwaarde. De ernst van de actie die in het bericht wordt gegeven, is afhankelijk van het vertrouwensniveau dat het bericht phishing is (slecht, gemiddeld, hoog of zeer hoog vertrouwen). Berichten die door een zeer hoge mate van phishing worden geïdentificeerd, zijn bijvoorbeeld met de meest ernstige vertrouwens kracht, terwijl berichten die als phishing met een laag vertrouwen worden geïdentificeerd, minder nadelig worden toegepast.

- **2-agressief**: berichten die zijn geïdentificeerd als phishing, zijn een hoge mate van vertrouwen, worden behandeld alsof ze zijn geïdentificeerd met een zeer hoge mate van betrouwbaarheid.

- **3-meer agressief**: berichten die zijn geïdentificeerd als phishing met een gemiddelde of een hoge mate van vertrouwen, worden behandeld alsof ze een zeer hoge mate van vertrouwen hebben.

- **4-de meeste agressieve**berichten die worden geïdentificeerd als phishing met een slecht, gemiddeld of hoog vertrouwensniveau, worden behandeld alsof ze worden vastgesteld met een zeer hoge mate van betrouwbaarheid.

De kans op fout-positieven (goede berichten gemarkeerd als beschadigd) neemt toe naarmate u deze instelling groter maakt. Zie voor meer informatie over de aanbevolen instellingen [Office-instellingen voor het anti-phishingfilter van Office](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).
