---
title: Walkthrough - Spoof intelligentie inzicht
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
description: Bekijk hoe het inzicht in spoofintelligentie werkt in Office 365 Advanced Threat Protection.
ms.openlocfilehash: 4ad3de8812e09b73018c02232e3e66e4bec9d041
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630927"
---
# <a name="walkthrough---atp-spoof-intelligence-insight-in-microsoft-365"></a>Walkthrough - ATP Spoof intelligence insight in Microsoft 365

In Microsoft 365-organisaties met Advanced Threat Protection (ATP) u het inzicht in spoofinformatie gebruiken om snel te bepalen welke afzenders u correct e-mail verzenden. Door hen toe te staan vervalste berichten te verzenden, u het risico verminderen dat er valse positieven naar uw gebruikers gaan. U het inzicht in spoofintelligentie ook gebruiken om toegestane domeinparen te controleren en te beheren om een extra beveiligingslaag te bieden en te voorkomen dat onveilige berichten in uw organisatie binnenkomen.

Als u nieuw bent [in rapporten en inzichten in het Security & Compliance Center,](reports-and-insights-in-security-and-compliance.md)kan dit helpen om te zien hoe u eenvoudig navigeren van een dashboard naar een inzicht en aanbevolen acties.

Deze walkthrough is een van de vele voor het Security & Compliance Center. Zie de walkthroughs in de sectie Gerelateerde onderwerpen voor het navigeren door rapporten en inzichten.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de <https://protection.office.com/searchandinvestigation/dashboard>pagina **Beveiligingsdashboard** wilt gaan, gebruikt u .

  U het inzicht in spoofinformatie bekijken vanuit meer dan één dashboard in het Security & Compliance Center. Ongeacht naar welk dashboard u nu kijkt, het inzicht biedt dezelfde details en stelt u in staat om snel dezelfde taken uit te voeren.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. Als u het inzicht in spoofintelligentie wilt gebruiken, moet u lid zijn van de rolgroepen **Organisatiebeheer,** **Beveiligingsbeheerder**of **Beveiligingslezer.** Zie Machtigingen in het Security & Compliance [Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over rolgroepen in het Security & Compliance Center.

- U schakelt spoofinformatie in en uit in het ATP-antiphishingbeleid. Zie [ATP-antiphishingbeleid configureren in Microsoft 365](configure-atp-anti-phishing-policies.md)voor meer informatie.

- In Microsoft 365-organisaties met Exchange Online-postvakken en in zelfstandige Exchange Online Protection (EOP) zonder Exchange Online-postvakken u spoofinformatie gebruiken om afzenders te controleren en te beheren die u niet-geverifieerde berichten verzendt. Zie [Spoofinformatie configureren in Microsoft 365](learn-about-spoof-intelligence.md)voor meer informatie.

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Open het inzicht in spoofintelligentie in het Security & Compliance Center

1. Ga in het Security & Compliance Center naar **Threat Management** \> **Dashboard.**

2. Zoek in de rij **Inzichten** naar een van de volgende items:

   - **Spoofintelligentie is ingeschakeld:** het inzicht wordt vervalste domeinen genoemd **die de verificatie van de afgelopen 30 dagen hebben mislukt.** Dit is de standaardinstelling.

   - **Spoofintelligentie is uitgeschakeld:** het inzicht in de naam **Spoofbeveiliging inschakelen**en als u erop klikt, u spoofinformatie inschakelen.

3. Het inzicht op het dashboard toont u informatie als volgt:

   ![Schermafbeelding van inzicht in spoofintelligentie](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Dit inzicht heeft twee modi:

   - **Insight-modus**. Als je een spoofbeleid hebt ingeschakeld, laat het inzicht zien hoeveel e-mails de afgelopen 30 dagen zijn beïnvloed door onze spoofintelligentiemogelijkheden.

   - **Wat als modus**. Als u geen spoofbeleid hebt ingeschakeld, toont het inzicht u hoeveel e-mails de afgelopen 30 dagen *zouden* zijn beïnvloed door onze spoofintelligentiemogelijkheden.

   Hoe dan ook, de vervalste domeinen die in het inzicht worden weergegeven, worden onderverdeeld in twee categorieën: **verdachte domeinparen** en **niet-verdachte domeinparen.** Deze categorieën zijn verder onderverdeeld in drie verschillende buckets voor u om te beoordelen.

   Een **domeinpaar** is een combinatie van het Adres Van en de verzendende infrastructuur:

   - Het Van-adres is het e-mailadres van de afzender dat wordt weergegeven in e-mailclients. Dit adres identificeert de auteur van de e-mail. Dat wil zeggen, het postvak van de persoon of het systeem dat verantwoordelijk is voor het schrijven van het bericht. Dit adres wordt ook `5322.From` wel het adres genoemd.

   - De verzendende infrastructuur, of afzender, is het organisatiedomein van de reverse DNS lookup (PTR-record) van het verzendende IP-adres. Als het verzendende IP-adres geen PTR-record heeft, wordt de afzender geïdentificeerd door het verzendende IP met het subnetmasker 255.255.0 in CIDR-notatie (/24). Als het IP-adres bijvoorbeeld 192.168.100.100 is, is het volledige IP-adres van de afzender 192.168.100.100/24.

   **Verdachte domeinparen** zijn:

   - **High-confidence spoof**: Microsoft 365 ontving sterke signalen dat deze domeinen verdacht zijn, gebaseerd op de historische verzendpatronen en de reputatiescore van de domeinen. Microsoft 365 is ervan overtuigd dat de domeinen zijn spoofing en dat berichten verzonden vanuit deze domeinen zijn minder waarschijnlijk legitiem.

   - **Matig vertrouwen spoof**: Microsoft 365 ontvangen matige signalen dat deze domeinen verdacht zijn, gebaseerd op historische verzendpatronen en de reputatiescore van de domeinen. Office 365 heeft er matig van overtuigd dat de domeinen worden vervalst en dat berichten die vanuit deze domeinen worden verzonden legitiem zijn. Deze emmer heeft een grotere kans op het bevatten van valse positieven (FPs) dan de hoog-vertrouwen spoof emmer.

   - **Niet-verdachte domeinparen** (inclusief **geredde spoof):** Geredde spoof zijn domeinen die de expliciete verificatiecontroles [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), [DMARC)](use-dmarc-to-validate-email.md)hebben uitgevoerd, maar onze impliciete e-mailverificatiecontroles hebben doorstaan[(samengestelde verificatie).](email-validation-and-authentication.md#composite-authentication) Als gevolg hiervan heeft Microsoft 365 de e-mail namens u gered en is er geen anti-spoofing actie ondernomen op het bericht.

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Bekijk gedetailleerde informatie over verdachte domeinparen vanuit het spoof-inzicht in intelligentie

1. Klik op het inzicht in de spoofintelligentie op een van de domeinparen (hoog, matig of gered).

   Op de pagina **Inzicht in spoofinformatie** wordt een lijst weergegeven met afzenders die niet-geverifieerde e-mail naar uw organisatie verzenden. Met de informatie op deze pagina u bepalen of vervalste berichten zijn geautoriseerd of dat u verdere actie moet ondernemen. U de informatie sorteren op aantal berichten, de datum waarop de spoof voor het laatst is gedetecteerd en meer. (Klik bijvoorbeeld op kolomkoppen, zoals **aantal berichten** of **Laatst gezien.)**

2. Selecteer een item in de tabel om een detailvenster te openen met uitgebreide informatie over het domeinpaar, waaronder waarom we dit hebben opgevangen, wat u moet doen, een domeinoverzicht, WhoIs-gegevens over de afzender en vergelijkbare e-mails die we in uw tenant van dezelfde afzender hebben gezien. Vanaf hier u er ook voor kiezen om het domeinpaar toe te voegen of te verwijderen uit de lijst met veilige afzenders **allowedTospoof.**

   ![Schermafbeelding van een domein in het detailvenster informatie over spoofintelligentie](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>Een domein toevoegen aan of verwijderen uit de lijst met veilige afzenders allowedTospoof

U voegt een domein toe of verwijdert deze uit de lijst met veilige afzenders van AllowedToSpoof terwijl u het domeinpaar bekijkt in het detailvenster van het inzicht in spoofintelligentie. Stel de schakelaar dienovereenkomstig in.

Dit wijzigt de unieke combinatie van het domeinpaar van het vervalste domein en de verzendende infrastructuur en biedt geen dekking voor het gehele vervalste domein of de verzendende infrastructuur in isolatie.

Als u bijvoorbeeld het volgende domeinpaar toevoegt aan de lijst 'AllowedToSpoof'-afzender: *Spoofed Domain* "gmail.com" en *Infrastructure* "tms *.mx.com",* dan mag alleen e-mail van dat domeinpaar spoofen. Andere afzenders die proberen "gmail.com" te spoofen, en andere domeinen die "tms.mx.com" proberen te spoofen, blijven worden beschermd door spoofinformatie.

## <a name="related-topics"></a>Verwante onderwerpen

[Anti-spoofing bescherming in Microsoft 365](anti-spoofing-protection.md)

[Stapsgewijze instructies - Van een dashboard tot een inzicht](from-a-dashboard-to-an-insight.md)

[Stapsgewijze instructies - Van een gedetailleerd rapport tot een inzicht](from-a-detailed-report-to-an-insight.md)

[Stapsgewijze instructies - Van een inzicht tot een gedetailleerd rapport](from-an-insight-to-a-detailed-report.md)