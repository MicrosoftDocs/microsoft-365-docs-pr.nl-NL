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
description: Beheerders kunnen inzicht krijgen in de werking van de spoof Intelligence-informatie, waaronder hoe u snel kunt bepalen welke afzenders u niet-geverifieerde e-mail hebt verzonden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5995095e442bbcd07ddf4538b67be6e1b14fd8f1
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844210"
---
# <a name="walkthrough---defender-for-office-365-spoof-intelligence-insight-in-microsoft-365"></a>Procedure-Defender voor Office 365 spoof Intelligence inzicht in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-organisaties met Defender for Office 365 kunt u met behulp van de spoof Intelligence-informatie snel bepalen welke afzenders op de legitiem manier u niet-geverifieerde e-mail verzenden. Als u wilt dat ze vervalste berichten kunnen verzenden, kunt u het risico van onbepaalde valse berichten verminderen. U kunt ook gebruikmaken van de informatie over het gebruik van spoof Intelligence voor het bewaken en beheren van toegestane domein paren, zodat er een extra beveiligingslaag wordt geboden en onveilige berichten in uw organisatie kunnen worden binnengekomen.

Als u geen ervaring hebt met [rapporten en inzichten in het beveiligings & compliance](reports-and-insights-in-security-and-compliance.md), kan het handig zijn om te zien hoe u eenvoudig kunt navigeren van een dashboard naar een insightle en aanbevolen actie.

Dit scenario is een van de verschillende voor het beveiligings & nalevings centrum. Zie de procedures in de sectie Verwante onderwerpen voor meer informatie over het navigeren in rapporten en inzichten.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina **beveiligings dashboard** wilt gaan, gebruikt u <https://protection.office.com/searchandinvestigation/dashboard> .

  U kunt de spoof Intelligence-informatie van meer dan één dashboard bekijken in de beveiligings & compliance Center. Ongeacht het dashboard dat u zoekt, biedt het inzicht dezelfde Details, zodat u snel dezelfde taken kunt uitvoeren.

- U moet machtigingen zijn toegewezen voordat u de procedures in dit onderwerp kunt uitvoeren. Als u de spoof Intelligence-inzichten wilt gebruiken, moet u lid zijn van een van de volgende rollen groepen:

  - **Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
  - **Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).
  - **Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
  - **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- U schakelt spoof informatie in en uit in anti-phishing-beleid in Microsoft Defender voor Office 365. Zie [anti phishing-beleid in Microsoft Defender voor Office 365 in Microsoft 365 configureren](configure-atp-anti-phishing-policies.md)voor meer informatie.

- In Microsoft 365-organisaties met postvakken van Exchange Online en in standalone Exchange Online Protection (EOP) zonder postvakken van Exchange Online, kunt u gebruikmaken van spoof Intelligence om afzenders te volgen en te beheren waarnaar u niet-geverifieerde berichten verzendt. Zie [spoof-intelligentie configureren in Microsoft 365](learn-about-spoof-intelligence.md) voor meer informatie.

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Open de informatie over spoof informatie in het beveiligings & nalevings centrum

1. Ga in het beveiligings & nalevings centrum naar het dashboard **Threat Management** \> **.**

2. Ga naar de rij **inzichten** en zoek een van de volgende items:

   - **Spoof Intelligence is ingeschakeld** : het inzicht is **in vervals bare domeinen die de authenticatie van de afgelopen 30 dagen mislukt**. Dit is de standaardinstelling.

   - **Spoof-informatie is uitgeschakeld** : de inzichten van de naam **spoofing inschakelen** en op de optie om spoof Intelligence in te schakelen.

3. Het inzicht in het Dashboard toont u informatie zoals hier:

   ![Schermafbeelding van spoof Intelligence Insight](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Dit inzicht heeft in twee modi:

   - **Insight-modus**. Als er sprake is van een spoofings beleid, ziet u in het inzicht hoe vaak e-mailberichten werden beïnvloed door onze spoof Intelligence-mogelijkheden in de afgelopen 30 dagen.

   - **Welke if-modus**. Als u geen spoofbeleid hebt ingeschakeld, kunt u in het inzicht zien hoeveel e-mailberichten  *werden beïnvloed*  door onze spoof Intelligence-mogelijkheden in de afgelopen 30 dagen.

   In beide gevallen zijn de spoofende domeinen die worden weergegeven in het inzicht, onderverdeeld in twee categorieën: **verdachte domein paren** en **niet-verdachte domein paren**. Deze categorieën worden verder onderverdeeld in drie verschillende buckets om te worden gecontroleerd.

   Een **domein paar** is een combinatie van het van-adres en de infrastructuur van verzenden:

   - Het adres van de afzender is het e-mailadres dat wordt weergegeven in de e-mailclients. Dit adres identificeert de auteur van de e-mail. Dat wil zeggen, het postvak van de persoon of het systeem dat verantwoordelijk is voor het schrijven van het bericht. Dit adres wordt ook wel het `5322.From` adres genoemd.

   - De verzendende infrastructuur, of afzender, is het organisatie domein van de omgekeerde DNS-zoekopdracht (PTR-record) van het verzendende IP-adres. Als het verzendende IP-adres geen PTR-record heeft, wordt de afzender geïdentificeerd door het versturen van IP met het 255.255.255.0-subnetmask in de CIDR-notatie (/24). Als bijvoorbeeld het IP-adres 192.168.100.100 is, is het volledige IP-adres van de afzender 192.168.100.100/24.

   **Verdachte domein paren** zijn:

   - **Spoofing met hoge betrouwbaarheid** : microsoft 365 heeft sterke signalen ontvangen waarmee deze domeinen verdacht zijn, op basis van de historische Verstuur patronen en de reputatie Score van de domeinen. Microsoft 365 is zeer geschikt voor spoofing en de berichten die vanuit deze domeinen worden verzonden, zijn minder waarschijnlijk legitiem.

   - **Spoofing van minder betrouwbaarheid** : microsoft 365 heeft geregelde signalen ontvangen dat deze domeinen verdacht zijn, op basis van historische Verstuur patronen en de reputatie Score van de domeinen. Office 365 is traag met een goede vertrouwene zekerheid dat de domeinen spoofing hebben en dat verzonden berichten van deze domeinen legitiem zijn. Deze Bucket heeft een groter risico met fout-positieven (FPs) dan de sterke vertrouw baarheid.

   - **Niet-verdachte domein paren** (waaronder **herstel van spoofing** ): hersteld spoof zijn domeinen die de expliciete verificatiecontrole hebben mislukt [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [dkim](use-dkim-to-validate-outbound-email.md), [DMARC](use-dmarc-to-validate-email.md)), maar het impliciet verifiëren van e-mail verificatie ( [samengestelde verificatie](email-validation-and-authentication.md#composite-authentication)). Daarom heeft Microsoft 365 het e-mailbericht namens u hersteld en wordt er geen anti-spoofing-actie uitgevoerd voor het bericht.

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Gedetailleerde informatie weergeven over verdachte domein paren van de spoof Intelligence Insight

1. Klik in het inzicht in de spoof Intelligence-informatie op een van de domein paren (hoog, normaal of hersteld).

   De pagina **spoof Intelligence Insight** wordt weergegeven met een lijst van afzenders die niet-geverifieerde e-mailberichten in uw organisatie verzenden. Met de informatie op deze pagina kunt u bepalen of vervalste berichten worden geautoriseerd, of dat u verdere actie moet ondernemen. U kunt de gegevens sorteren op aantal berichten, de datum waarop het spoof voor het laatst is gedetecteerd, en nog veel meer. (Klik op kolomkoppen, zoals het **aantal berichten** of voor de **laatste weergegeven**.)

2. Selecteer een item in de tabel om een deelvenster met uitgebreide informatie over het domein paar te openen, waaronder waarom we dit hebben vastgelegd, wat u moet doen, wat u moet doen, een domein samenvatting, WhoIs gegevens over de afzender en soortgelijke e-mailberichten die in uw Tenant van dezelfde afzender zijn weergegeven. U kunt hier ook voor kiezen om het domein paar toe te voegen of te verwijderen uit de lijst met veilige afzenders van **AllowedToSpoof** .

   ![Schermafbeelding van een domein in het detailvenster van de spoof Intelligence Insight](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>Een domein toevoegen aan of verwijderen uit de lijst met veilige afzenders van AllowedToSpoof

U kunt een domein toevoegen aan of verwijderen uit de lijst met veilige afzenders van AllowedToSpoof tijdens het bekijken van het domein paar in het detailvenster van de spoof Intelligence-inzichten. Zet de wisselknop dienovereenkomstig.

Hiermee kunt u de unieke combinatie van domein paar van het vervalste domein en de verzendende infrastructuur wijzigen en krijgt u geen dekking voor het hele domein met spoofing of de verzending van de infrastructuur.

Als u bijvoorbeeld het volgende domein paar toevoegt aan de lijst met toegestane afzenders van de ' AllowedToSpoof-afzender:  *domein met spoofing*  ' Gmail.com ' en het *verzenden van infrastructuur* ' TMS *. MX.com ',* dan wordt alleen e-mail van dit domein paar toegestaan. Andere afzenders proberen een spoof te maken voor ' gmail.com ', en andere domeinen die ' tms.mx.com ' proberen te vervalsen, blijven beveiligd via spoof Intelligence.

## <a name="related-topics"></a>Verwante onderwerpen

[Anti-spoofing beveiliging in Microsoft 365](anti-spoofing-protection.md)
