---
title: Walkthrough - Inzicht in informatie spoofen
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
description: Beheerders kunnen leren hoe de spoof intelligentie inzicht werkt, met inbegrip van hoe snel te bepalen welke afzenders zijn rechtmatig sturen u niet-geverifieerde e-mail.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1f04baca3761e44acfd26c09cdc0d5283db13697
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726514"
---
# <a name="walkthrough---atp-spoof-intelligence-insight-in-microsoft-365"></a>Walkthrough - ATP Spoof intelligentie inzicht in Microsoft 365

In Microsoft 365-organisaties met Advanced Threat Protection (ATP) u de inzicht in spoofinformatie gebruiken om snel te bepalen welke afzenders u ongeoorloofde e-mail sturen. Door hen toe te staan om vervalste berichten te verzenden, u het risico van valse positieven die naar uw gebruikers gaan verminderen. U het inzicht in spoofinformatie ook gebruiken om toegestane domeinparen te bewaken en te beheren om een extra beveiligingslaag te bieden en te voorkomen dat onveilige berichten in uw organisatie binnenkomen.

Als u nieuw bent [bij rapporten en inzichten in het Security & Compliance Center,](reports-and-insights-in-security-and-compliance.md)kan het helpen om te zien hoe u eenvoudig van een dashboard naar inzicht en aanbevolen acties navigeren.

Deze walkthrough is een van de vele voor het Security & Compliance Center. Zie de walkthroughs in de sectie Gerelateerde onderwerpen voor het navigeren door rapporten en inzichten.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de **dashboardpagina Beveiliging** wilt gaan, gebruikt u <https://protection.office.com/searchandinvestigation/dashboard> .

  U het inzicht in spoofinformatie bekijken vanuit meer dan één dashboard in het Security & Compliance Center. Welk dashboard u ook bekijkt, het inzicht biedt dezelfde details en stelt u in staat om snel dezelfde taken uit te voeren.

- U moet machtigingen krijgen toegewezen voordat u de procedures in dit onderwerp uitvoeren. Als u het inzicht in spoofinformatie wilt gebruiken, moet u lid zijn van een van de volgende rolgroepen:

  - **Organisatiebeheer** of **beveiligingsbeheerder** in het [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
  - **Organisatiebeheer** of **hygiënebeheer** in [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)
  - **Security Reader** in het [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
  - **Alleen-weergeven organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- U schakelt spoofinformatie in en schakelt deze uit in het ATP-antiphishingbeleid. Zie [ATP-beleid voor antiphishing configureren in Microsoft 365](configure-atp-anti-phishing-policies.md)voor meer informatie.

- In Microsoft 365-organisaties met Exchange Online-postvakken en in zelfstandige Exchange Online Protection (EOP) zonder Exchange Online-postvakken u spoofinformatie gebruiken om afzenders die u u niet-geverifieerde berichten stuurt, te controleren en te beheren. Zie [spoof-intelligentie configureren in Microsoft 365](learn-about-spoof-intelligence.md) voor meer informatie.

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Open het inzicht in spoofinformatie in het Security & Compliance Center

1. Ga in het Security & Compliance Center naar **Threat Management** \> **Dashboard.**

2. Zoek in de rij **Insights** naar een van de volgende items:

   - **Spoofinformatie is ingeschakeld:** het inzicht wordt **spoofed-domeinen genoemd die de verificatie van de afgelopen 30 dagen hebben mislukt.** Dit is de standaardinstelling.

   - **Spoofinformatie is uitgeschakeld:** Het inzicht in de naam **Spoofbeveiliging inschakelen**en erop klikken stelt u in staat om spoofinformatie in te schakelen.

3. Het inzicht op het dashboard toont u informatie als deze:

   ![Schermafbeelding van inzicht in spoofinformatie](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Dit inzicht heeft twee modi:

   - **Insight-modus**. Als u een spoofbeleid hebt ingeschakeld, laat het inzicht zien hoeveel e-mails zijn beïnvloed door onze spoofinformatiemogelijkheden in de afgelopen 30 dagen.

   - **Wat als modus**. Als u geen spoofbeleid hebt ingeschakeld, laat het inzicht zien hoeveel e-mails de afgelopen 30 dagen *zijn* beïnvloed door onze spoofinformatiemogelijkheden.

   Hoe dan ook, de vervalste domeinen die in het inzicht worden weergegeven, worden gescheiden in twee categorieën: **verdachte domeinparen** en **niet-verdachte domeinparen.** Deze categorieën zijn verder onderverdeeld in drie verschillende buckets die u bekijken.

   Een **domeinpaar** is een combinatie van het Adres Van en de verzendende infrastructuur:

   - Het adres Van is het e-mailadres van de afzender dat wordt weergegeven in e-mailclients. Dit adres identificeert de auteur van de e-mail. Dat wil zeggen, het postvak van de persoon of het systeem dat verantwoordelijk is voor het schrijven van het bericht. Dit adres wordt ook wel het `5322.From` adres genoemd.

   - De verzendinfrastructuur of afzender is het organisatiedomein van de reverse DNS lookup (PTR-record) van het verzendende IP-adres. Als het verzendende IP-adres geen PTR-record heeft, wordt de afzender geïdentificeerd door het verzendende IP met het subnetmasker 255.255.0 in CIDR-notatie (/24). Als het IP-adres bijvoorbeeld 192.168.100.100 is, is het volledige IP-adres van de afzender 192.168.100.100/24.

   **Verdachte domeinparen** zijn:

   - **High-confidence spoof**: Microsoft 365 ontvangen sterke signalen dat deze domeinen verdacht zijn, gebaseerd op de historische verzendpatronen en de reputatie score van de domeinen. Microsoft 365 is ervan overtuigd dat de domeinen spoofing zijn en dat berichten die vanuit deze domeinen worden verzonden minder waarschijnlijk legitiem zijn.

   - **Matig vertrouwen spoof**: Microsoft 365 ontvangen matige signalen dat deze domeinen verdacht zijn, op basis van historische verzendpatronen en de reputatie score van de domeinen. Office 365 is er redelijk zeker van dat de domeinen spoofing zijn en dat berichten die vanuit deze domeinen worden verzonden legitiem zijn. Deze emmer heeft een grotere kans op het bevatten van valse positieven (FPs) dan de high-confidence spoof emmer.

   - **Niet-verdachte domeinparen** (inclusief **geredde spoof):** Geredde spoof zijn domeinen die de expliciete verificatiecontroles [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), [DMARC](use-dmarc-to-validate-email.md)) hebben gefaald, maar onze impliciete e-mailverificatiecontroles[(samengestelde verificatie)](email-validation-and-authentication.md#composite-authentication)hebben doorstaan. Als gevolg hiervan heeft Microsoft 365 de e-mail namens u gered en is er geen anti-spoofing-actie ondernomen op het bericht.

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Bekijk gedetailleerde informatie over verdachte domeinparen van de spoofintelligentieinzicht

1. Klik op de spoofintelligentieinzicht op een van de domeinparen (hoog, matig of gered).

   De **pagina Spoof Intelligence insight** toont u een lijst met afzenders die niet-geverifieerde e-mail naar uw organisatie verzenden. Met de informatie op deze pagina u bepalen of vervalste berichten zijn geautoriseerd of dat u verdere actie moet ondernemen. U de informatie sorteren op aantal berichten, de datum waarop de spoof voor het laatst is gedetecteerd en meer. (Klik op kolomkoppen, zoals **het aantal berichten** of Laatst **gezien,** bijvoorbeeld.)

2. Selecteer een item in de tabel om een detailvenster te openen met uitgebreide informatie over het domeinpaar, waaronder waarom we dit hebben opgevangen, wat u moet doen, een domeinoverzicht, WhoIs-gegevens over de afzender en vergelijkbare e-mails die we in uw tenant hebben gezien van dezelfde afzender. Vanaf hier u er ook voor kiezen om het domeinpaar toe te voegen of te verwijderen uit de lijst **Met een** veilige afzender.

   ![Schermafbeelding van een domein in het deelvenster details over inzicht in de informatie over spoofintelligentie](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>Een domein toevoegen of verwijderen uit de lijst Met toegestane afzenders

U voegt of verwijdert een domein uit de lijst Met een veilige afzender toestaan terwijl u het domeinpaar bekijkt in het detailvenster van de informatie-inzicht over spoofinformatie. Stel de toggle dienovereenkomstig in.

Dit wijzigt de unieke domeinpaarcombinatie van het vervalste domein en de verzendende infrastructuur en biedt geen dekking voor het hele vervalste domein of de verzendende infrastructuur afzonderlijk.

Als u bijvoorbeeld het volgende domeinpaar toevoegt aan de lijst met de stuurzender 'AllowedToSpoof': *Spoofed Domain* "gmail.com" en *Send Infrastructure* "tms *.mx.com",* mag alleen e-mail van dat domeinpaar spoofen. Andere afzenders die proberen "gmail.com" te spoofen en andere domeinen die "tms.mx.com" proberen te spoofen, blijven worden beschermd door spoofinformatie.

## <a name="related-topics"></a>Verwante onderwerpen

[Bescherming tegen spoofing in Microsoft 365](anti-spoofing-protection.md)
