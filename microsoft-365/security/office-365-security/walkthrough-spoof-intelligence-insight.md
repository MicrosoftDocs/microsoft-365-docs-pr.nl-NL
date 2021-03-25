---
title: Stapsgewijze instructies voor inzicht in adresvervalsingsanalyses
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
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe het inzicht in spoofinformatie werkt. Ze kunnen snel bepalen welke afzenders e-mail naar hun organisatie verzenden vanuit domeinen die niet worden gecontroleerd op e-mailverificatie (SPF, DKIM of DMARC).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d2b48b8540fb71404a0636120a5884d381b08cd1
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204817"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Walkthrough - Inzicht in spoofinformatie in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-organisaties met Defender voor Office 365 kunt u het inzicht in spoofinformatie gebruiken om snel te bepalen welke externe afzenders u legitiem niet-verwerkte e-mail verzenden (berichten van domeinen die niet door SPF-, DKIM- of DMARC-controles worden verzonden).

Door bekende externe afzenders toe te staan vervalste berichten te verzenden vanaf bekende locaties, kunt u fout-positieven verminderen (goede e-mail die als slecht is gemarkeerd). Door de toegestane vervalste afzenders te controleren, biedt u een extra beveiligingslaag om te voorkomen dat onveilige berichten in uw organisatie aankomen.

Zie Rapporten en inzichten in het Beveiligings- en compliancecentrum & voor meer informatie over rapporten [en inzichten.](reports-and-insights-in-security-and-compliance.md)

Deze walkthrough is een van de verschillende scenario's voor & compliancecentrum. Zie de overzichten in de sectie Gerelateerde [onderwerpen](#related-topics) voor informatie over het navigeren in rapporten en inzichten.

> [!NOTE]
> Het inzicht in spoof intelligence toont gegevens uit de afgelopen 7 dagen. Het [spoof intelligence-beleid](learn-about-spoof-intelligence.md) en de bijbehorende [Get-PhishFilterPolicy-cmdlet](/powershell/module/exchange/get-phishfilterpolicy) in Exchange Online PowerShell bevatten gegevens van de afgelopen 30 dagen. Het [Get-SpoofMailReport bevat](/powershell/module/exchange/get-spoofmailreport) gegevens die maximaal 90 dagen duren.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina **Beveiligingsdashboard wilt** gaan, gebruikt <https://protection.office.com/searchandinvestigation/dashboard> u .

  U kunt het inzicht in spoofinformatie bekijken vanuit meer dan één dashboard in het beveiligings- & Compliancecentrum. Ongeacht het dashboard dat u ziet, biedt het inzicht dezelfde details en kunt u snel dezelfde taken uitvoeren.

- Je moet beschikken over toegewezen machtigingen voor het uitvoeren van de procedures in dit onderwerp:
  - **Organisatiebeheer**
  - **Beveiligingsbeheerder**
  - **Beveiligingslezer**
  - **Algemene lezer**

  Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

  **Opmerking:** Gebruikers toevoegen aan de bijbehorende Azure Active Directory-rol in het Microsoft 365-beheercentrum biedt gebruikers de vereiste machtigingen in het Beveiligings- & _Compliancecentrum_ en machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.

- U schakelt spoofinformatie in en uit in anti-phishingbeleid in Microsoft Defender voor Office 365. Spoofinformatie is standaard ingeschakeld. Zie [Anti-phishingbeleid configureren in Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md)voor meer informatie.

- Zie Spoof intelligence configureren [in Microsoft 365](learn-about-spoof-intelligence.md)als u spoof intelligence wilt gebruiken voor het bewaken en beheren van afzenders die u niet-verwerkte berichten sturen.

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Het inzicht in spoof intelligence openen in het beveiligings- & compliancecentrum

1. Ga in het & Compliancecentrum naar **Threat Management** \> **Dashboard.**

2. Zoek in **de rij** Inzichten naar een van de volgende items:

   - **Waarschijnlijk vervalste domeinen in** de afgelopen zeven dagen: Dit inzicht geeft aan dat spoof intelligence is ingeschakeld (deze is standaard ingeschakeld).
   - **Spoofbeveiliging inschakelen:** dit inzicht geeft aan dat spoofinformatie is uitgeschakeld en als u op het inzicht klikt, kunt u spoofinformatie inschakelen.

3. In het inzicht op het dashboard ziet u de volgende informatie:

   ![Schermafbeelding van inzicht in spoof intelligence](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Dit inzicht heeft twee modi:

   - **Insight-modus:** als spoof intelligence is ingeschakeld, wordt in het inzicht duidelijk hoeveel berichten de afgelopen zeven dagen zijn beïnvloed door onze mogelijkheden voor spoof intelligence.
   - **Wat als de modus**: Als spoof intelligence is  uitgeschakeld, wordt in het inzicht duidelijk hoeveel berichten de afgelopen zeven dagen zijn beïnvloed door onze mogelijkheden voor spoof intelligence.

   Hoe dan ook, de vervalste domeinen die in het inzicht worden weergegeven, zijn onderverdeeld in twee categorieën: **Verdachte** domeinen en **Niet-verdachte domeinen.**

   - **Verdachte domeinen zijn:**

     - Spoof met veel vertrouwen: op basis van de historische verzendingspatronen en de reputatiescore van de domeinen, zijn we ervan overtuigd dat de domeinen spoofing zijn en dat berichten uit deze domeinen waarschijnlijk schadelijk zijn.

     - Matig vertrouwen spoof: Op basis van historische verzendende patronen en de reputatiescore van de domeinen, zijn we er redelijk zeker van dat de domeinen spoofing zijn en dat berichten die vanuit deze domeinen worden verzonden legitiem zijn. False positives zijn waarschijnlijker in deze categorie dan spoof met veel vertrouwen.

   **Niet-verdachte domeinen:** het domein is mislukt expliciete e-mailverificatie [controleert SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)en [DMARC](use-dmarc-to-validate-email.md)). Het domein is echter geslaagd voor onze impliciete e-mailverificatiecontroles[(samengestelde verificatie).](email-validation-and-authentication.md#composite-authentication) Hierdoor is er geen anti-spoofing actie ondernomen op het bericht.

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>Gedetailleerde informatie over verdachte domeinen weergeven vanuit het inzicht in spoofinformatie

1. Klik op de informatie over spoofinformatie op **Verdachte domeinen** of **Niet-verdachte** domeinen om naar de pagina Inzicht in **spoofinformatie te** gaan. De **pagina Spoof Intelligence Insight** bevat de volgende informatie:

   - **Vervalst domein:** het domein van de vervalste gebruiker die wordt weergegeven in het vak **Van** in e-mail clients. Dit adres wordt ook wel het adres `5322.From` genoemd.
   - **Infrastructuur:** ook wel de _verzendende infrastructuur genoemd._ Het domein dat is gevonden in een REVERSE DNS lookup (PTR-record) van het IP-adres van de bron-e-mailserver. Als het bron-IP-adres geen PTR-record heeft, wordt de verzendende infrastructuur geïdentificeerd als \<source IP\> /24 (bijvoorbeeld 192.168.100.100/24).
   - **Aantal berichten:** het aantal berichten van de verzendende infrastructuur naar uw organisatie dat het opgegeven vervalste domein bevat in de afgelopen 7 dagen.
   - **Laatst gezien:** De laatste datum waarop een bericht is ontvangen van de verzendende infrastructuur met het vervalste domein.
   - **Type spoof:** deze waarde is **Extern**.
   - **Toegestaan om te vervalsen?**: De waarden die u hier ziet, zijn:
     - **Ja:** Berichten uit de combinatie van het domein van de vervalste gebruiker en de verzendende infrastructuur zijn toegestaan en worden niet behandeld als vervalste e-mail.
     - **Nee:** Berichten uit de combinatie van het domein van de vervalste gebruiker en de verzendende infrastructuur worden gemarkeerd als vervalst. De actie wordt bepaald door het standaard anti-phishingbeleid of aangepaste anti-phishingbeleid (de standaardwaarde is Bericht verplaatsen naar map **Ongewenste e-mail**).

     Zie [Anti-phishingbeleid configureren in Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md)voor meer informatie.

2. Selecteer een item in de lijst om details over het domein/verzendende infrastructuurpaar in een flyout weer te geven. De informatie omvat:
   - Waarom we dit hebben gesnapt.
   - Wat u moet doen.
   - Een domeinoverzicht.
   - WhoIs-gegevens over de afzender.
   - Soortgelijke berichten die we hebben gezien in uw tenant van dezelfde afzender.

   Hier kunt u er ook voor kiezen om het domein-/verzendende infrastructuurpaar toe te voegen of te verwijderen uit de **lijst Toegestane** afzender voor spoofing. Stel de schakelaar dienovereenkomstig in.

   ![Schermafbeelding van een domein in het deelvenster Informatie over spoofinformatie](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>Een domein toevoegen aan de lijst Toegestane spoofing

Als u een domein toevoegt aan de lijst Toegestane spoofing vanuit het inzicht in spoof intelligence, kunt u alleen het vervalste *domein* en de verzendende infrastructuur combineren. E-mail van het vervalste domein is niet toegestaan vanuit een bron en ook geen e-mail van de verzendende infrastructuur voor een domein.

U staat bijvoorbeeld het volgende domein toe aan de lijst Toegestane spoofing:

- **Domein:** gmail.com
- **Infrastructuur**: tms.mx.com

Alleen e-mail van dat domein/verzendende infrastructuurpaar mag spoofen. Andere afzenders die proberen te spoofen gmail.com zijn niet toegestaan. Berichten in andere domeinen van tms.mx.com worden gecontroleerd door spoof intelligence.

## <a name="related-topics"></a>Verwante onderwerpen

[Bescherming tegen spoofing in Microsoft 365](anti-spoofing-protection.md)