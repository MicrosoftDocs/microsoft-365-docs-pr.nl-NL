---
title: Scenario-spoof Intelligence Insight
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Beheerders kunnen inzicht krijgen in de werking van de spoof Intelligence-informatie. De persoon kan snel bepalen welke afzenders legitiem e-mail naar hun organisatie verzenden vanuit domeinen die geen e-mail verificatiecontroles doorgeven (SPF, DKIM of DMARC).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 89a31c6df7c9b6e02f52ea414ceb6334427feab1
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920476"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Scenario-spoof informatie inzicht in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-organisaties met Defender for Office 365 kunt u met behulp van de spoof Intelligence-informatie snel bepalen welke afzenders op de legitiem manier u niet-geverifieerde e-mailberichten (berichten van domeinen die geen SPF-, DKIM-of DMARC-controles doorgeven).

Door bekende afzenders toe te staan vervalste berichten van bekende locaties te verzenden, kunt u foutberichten verminderen (goede e-mailberichten die als slecht zijn gemarkeerd). Door de toegestane vervalste afzenders te bewaken, geeft u een extra beveiligingslaag aan om te voorkomen dat onveilige berichten in uw organisatie arriveren.

Zie [rapporten en inzichten in het beveiligings & nalevings centrum](reports-and-insights-in-security-and-compliance.md)voor meer informatie over rapporten en inzichten.

Dit scenario is een van de verschillende voor het beveiligings & nalevings centrum. Zie de procedures in de sectie [Verwante onderwerpen](#related-topics) voor meer informatie over het navigeren in rapporten en inzichten.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina **beveiligings dashboard** wilt gaan, gebruikt u <https://protection.office.com/searchandinvestigation/dashboard> .

  U kunt de spoof Intelligence-informatie van meer dan één dashboard bekijken in de beveiligings & compliance Center. Ongeacht het dashboard dat u zoekt, biedt het inzicht dezelfde Details, zodat u snel dezelfde taken kunt uitvoeren.

- U moet machtigingen zijn toegewezen voordat u de procedures in dit onderwerp kunt uitvoeren. Als u de spoof Intelligence-inzichten wilt gebruiken, moet u lid zijn van een van de volgende rollen groepen:

  - **Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
  - **Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).
  - **Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
  - **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- U schakelt spoof informatie in en uit in anti-phishing-beleid in Microsoft Defender voor Office 365. Zie [anti phishingberichten configureren in Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md)voor meer informatie.

- Zie [spoof informatie configureren in Microsoft 365](learn-about-spoof-intelligence.md)als u wilt weten hoe u via spoof Intelligence afzenders kunt volgen en beheren die u niet-geverifieerde berichten verzendt.

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Open de informatie over spoof informatie in het beveiligings & nalevings centrum

1. Ga in het beveiligings & nalevings centrum naar het dashboard **Threat Management** \> **.**

2. Ga naar de rij **inzichten** en zoek een van de volgende items:

   - **Spoof Intelligence is ingeschakeld** : het inzicht is **in vervals bare domeinen die de authenticatie van de afgelopen 30 dagen mislukt**. Dit is de standaardinstelling.
   - **Spoof-informatie is uitgeschakeld** : de inzichten van de naam **spoofing inschakelen** en op de optie om spoof Intelligence in te schakelen.

3. Het inzicht in het Dashboard toont u informatie zoals hier:

   ![Schermafbeelding van spoof Intelligence Insight](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Dit inzicht heeft in twee modi:

   - Berekenings **modus** : als spoof Intelligence is ingeschakeld, ziet u in het voor inzicht hoe veel berichten werden beïnvloed door onze spoofberichten en de afgelopen 30 dagen.

   - **Wat als-modus** : als spoof Intelligence is uitgeschakeld, kunt u in het inzicht zien hoeveel *berichten werden beïnvloed door* onze vervals Intelligence-mogelijkheden in de afgelopen 30 dagen.

   In beide gevallen zijn de spoofende domeinen die worden weergegeven in het inzicht, onderverdeeld in twee categorieën: **verdachte domein paren** en **niet-verdachte domein paren**. Deze categorieën worden verder onderverdeeld in drie verschillende buckets om te worden gecontroleerd.

   Een **domein paar** is een combinatie van het van-adres en de infrastructuur van verzenden:

   - Het adres van de afzender is het e-mailadres dat wordt weergegeven in het vak van in e-mailclients. Dit adres wordt ook wel het `5322.From` adres genoemd.

   - De verzendende infrastructuur, of afzender, is het organisatie domein van de omgekeerde DNS-zoekopdracht (PTR-record) van het verzendende IP-adres. Als het verzendende IP-adres geen PTR-record heeft, wordt de afzender geïdentificeerd door het versturen van IP met het 255.255.255.0-subnetmask in de CIDR-notatie (/24). Als bijvoorbeeld het IP-adres 192.168.100.100 is, is het volledige IP-adres van de afzender 192.168.100.100/24.

   **Verdachte domein paren** zijn:

   - **Spoofing van hoge betrouwbaarheid** : op basis van de historische verplaatsings patronen en de reputatie Score van de domeinen, hebben we nadrukkelijk vertrouwen dat de domeinen wel spoofing zijn en dat berichten van deze domeinen waarschijnlijk schadelijk zijn.

   - **Spoofing van matige betrouwbaarheid** : op basis van de historische Verstuur patronen en de reputatie Score van de domeinen, zijn er zeker van te zijn dat de domeinen spoofing zijn en dat berichten die vanuit deze domeinen worden verzonden, legitiem zijn. In deze categorie zijn er onjuiste positieve en onjuiste vertrouw baarheid van een spoof.

   - **Niet-verdachte domein paren** (waaronder **herstel van spoofing** ): het domein is vanwege expliciete verificatie van e-mail [verificatie gecontroleerd,](how-office-365-uses-spf-to-prevent-spoofing.md) [dkim](use-dkim-to-validate-outbound-email.md)en [DMARC](use-dmarc-to-validate-email.md)). Het domein heeft echter wel verificatie gecontroleerd op impliciete e-mail verificatie ([samengestelde verificatie](email-validation-and-authentication.md#composite-authentication)). Daarom is er geen anti-spoofing-actie uitgevoerd voor het bericht.

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Gedetailleerde informatie weergeven over verdachte domein paren van de spoof Intelligence Insight

1. Klik in het inzicht in de spoof Intelligence-informatie op een van de domein paren (hoog, normaal of hersteld).

   De pagina **spoof Intelligence Insight** wordt weergegeven. Op de pagina ziet u een lijst met afzenders die niet-geverifieerde e-mail naar uw organisatie verzenden.

   Met deze informatie kunt u bepalen of spoofing berichten worden geautoriseerd, of dat u verdere actie moet ondernemen.

   U kunt de gegevens sorteren op aantal berichten, de datum waarop het spoof voor het laatst is gedetecteerd, en nog veel meer.

2. Selecteer een item in de tabel om een detaildeelvenster met uitgebreide informatie over het domein paar te openen. De informatie omvat:
   - Waarom we dit hebben ondervangen.
   - Wat u moet doen.
   - Een domein samenvatting.
   - WhoIs gegevens over de afzender.
   - Vergelijkbare berichten die we hebben weergegeven in uw Tenant van dezelfde afzender.

   U kunt hier ook voor kiezen om het domein paar toe te voegen of te verwijderen uit de lijst met veilige afzenders van **AllowedToSpoof** .

   ![Schermafbeelding van een domein in het detailvenster van de spoof Intelligence Insight](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-list"></a>Een domein toevoegen aan of verwijderen uit de lijst met AllowedToSpoof

U kunt een domein toevoegen aan of verwijderen uit de lijst AllowedToSpoof (lijst met veilige afzenders) in het detailvenster van de spoof Intelligence-inzichten voor het domein paar. Zet de wisselknop dienovereenkomstig.

Als u een domein paar toestaat, is de combinatie van het vervalste domein *en* de verstuurde infrastructuur alleen toegestaan. De e-mail van het vervalste domein van een bron wordt niet toegestaan, noch mag e-mail van de verzendende infrastructuur voor geen domeinen.

U kunt bijvoorbeeld het volgende domein paar vervalste berichten in uw organisatie verzenden:

- *Vervalste domein* : Gmail.com
- *Infrastructuur verzenden* `tms.mx.com` :

Alleen e-mailberichten van dit domein paar kunnen worden vervalst. Andere afzenders proberen te vervalsen gmail.com zijn niet toegestaan. Berichten in andere domeinen van tms.mx.com zijn gecontroleerd via spoof Intelligence.

## <a name="related-topics"></a>Verwante onderwerpen

[Anti-spoofing beveiliging in Microsoft 365](anti-spoofing-protection.md)
