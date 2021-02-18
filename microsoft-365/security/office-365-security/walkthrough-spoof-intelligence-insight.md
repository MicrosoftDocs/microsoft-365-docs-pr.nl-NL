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
description: Beheerders kunnen informatie krijgen over de manier waarop intelligence-inzicht in spoofing werkt. Ze kunnen snel bepalen welke afzenders e-mail legitiem naar hun organisatie verzenden vanuit domeinen die niet aan e-mailverificatiecontroles (SPF, DKIM of DMARC) kunnen deelnemen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 91cd26498b2a14166f1be10921b9d5b2ea8d583c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287969"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-organisaties met Defender voor Office 365 kunt u het inzicht in adresvervalsingsinformatie gebruiken om snel te kunnen bepalen welke externe afzenders u legitiem e-mail met een niet-geauteerde afzender sturen (berichten van domeinen die niet door SPF-, DKIM- of DMARC-controles komen).

Door bekende externe afzenders mogelijk te maken vervalste berichten te verzenden vanaf bekende locaties, kunt u fout-positieven (goede e-mail die als slecht is gemarkeerd) verminderen. Door de toegestane vervalste afzenders te controleren, biedt u een extra beveiligingslaag om te voorkomen dat onveilige berichten binnenkomt in uw organisatie.

Zie Rapporten en inzichten in het beveiligings- en compliancecentrum voor meer informatie [& inzichten.](reports-and-insights-in-security-and-compliance.md)

Dit overzicht is een van de verschillende scenario's voor het beveiligings- & compliancecentrum. Zie de scenario's in de sectie Verwante onderwerpen voor informatie over het navigeren in rapporten [en](#related-topics) inzichten.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina **beveiligingsdashboard** wilt gaan, gebruikt u <https://protection.office.com/searchandinvestigation/dashboard> .

  U kunt de informatie over spoof intelligence op meer dan één dashboard bekijken in het & compliancecentrum. Ongeacht het dashboard waarmee u te maken hebt, biedt het inzicht dezelfde details en kunt u snel dezelfde taken uitvoeren.

- Je moet beschikken over toegewezen machtigingen voor het uitvoeren van de procedures in dit onderwerp:
  - **Organisatiebeheer**
  - **Beveiligingsbeheerder**
  - **Beveiligingslezer**
  - **Globale lezer**

  Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

  **Opmerking:** als u gebruikers toevoegt aan de bijbehorende Azure Active Directory-rol in het Microsoft 365-beheercentrum, krijgen gebruikers de vereiste machtigingen in het beveiligings- & compliancecentrum en machtigingen voor andere functies in Microsoft 365.  Raadpleeg [Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.

- U schakelt spoof intelligence in en uit in anti-phishingbeleid in Microsoft Defender voor Office 365. Intelligence over adresvervalsing is standaard ingeschakeld. Zie [Anti-phishingbeleid configureren in Microsoft Defender voor Office 365 voor meer informatie.](configure-atp-anti-phishing-policies.md)

- Zie Spoof Intelligence configureren [in Microsoft 365](learn-about-spoof-intelligence.md)als u spoof intelligence wilt gebruiken om afzenders te controleren en te beheren die u niet-geauteerde berichten sturen.

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Informatie over spoof intelligence openen in het & compliancecentrum

1. Ga in het & Compliancecentrum naar dashboard **Bedreigingsbeheer.** \> 

2. Zoek in **de rij Inzichten** naar een van de volgende items:

   - **Waarschijnlijk is in de** afgelopen zeven dagen vervalste domeinen gebruikt: dit inzicht geeft aan dat intelligence voor adresvervalsing is ingeschakeld (dit is standaard ingeschakeld).
   - **Spoof Protection inschakelen:** dit inzicht geeft aan dat spoof intelligence is uitgeschakeld en als u op het inzicht klikt, kunt u spoof intelligence inschakelen.

3. Het inzicht in het dashboard geeft de volgende informatie weer:

   ![Schermafbeelding van inzicht in adresvervalsingsinformatie](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Dit inzicht heeft twee modi:

   - **Inzichtmodus:** als spoof intelligence is ingeschakeld, kunt u zien hoeveel berichten in de afgelopen zeven dagen zijn beïnvloed door onze mogelijkheden voor spoof intelligence.
   - **Wat als de modus**: als spoof intelligence is  uitgeschakeld, laat het inzicht zien hoeveel berichten in de afgelopen zeven dagen zouden zijn beïnvloed door onze spoof intelligence-mogelijkheden.

   In beide categorieën zijn de in het inzicht weergegeven vervalste domeinen onderverdeeld in twee **categorieën:** Verdachte domeinen en **niet-verdachte domeinen.**

   - **Verdachte domeinen zijn:**

     - Adresvervalsing met hoge betrouwbaarheid: Op basis van de historische verzendende patronen en de reputatiescore van de domeinen, hebben we er veel vertrouwen in dat de domeinen spoofing gebruiken en dat berichten van deze domeinen waarschijnlijk schadelijk zijn.

     - Gemiddelde betrouwbaarheidsvervalsing: Op basis van historische verzendende patronen en de reputatiescore van de domeinen zijn we er met enige vertrouwen in dat de domeinen vervalst zijn en dat berichten die vanuit deze domeinen worden verzonden, legitiem zijn. Fout-positieven zijn in deze categorie waarschijnlijker dan adresvervalsing met hoge betrouwbaarheid.

   **Niet-verdachte domeinen:** met de expliciete e-mailverificatie voor het domein is [mislukt, worden SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)en [DMARC gecontroleerd.](use-dmarc-to-validate-email.md) Het domein is echter geslaagd voor onze impliciete e-mailverificatiecontroles[(samengestelde verificatie).](email-validation-and-authentication.md#composite-authentication) Er is dus geen actie ondernomen tegen spoofing op het bericht.

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>Gedetailleerde informatie over verdachte domeinen weergeven vanuit het inzicht in spoof intelligence

1. Klik op Inzicht in spoof intelligence op **Verdachte** domeinen of **Niet-verdachte** domeinen om naar de **pagina Spoof Intelligence Insight te** gaan. De **pagina Spoof Intelligence insight** bevat de volgende informatie:

   - **Vervalst domein:** het domein van de vervalste gebruiker die wordt weergegeven in het vak **Van** in e-mail clients. Dit adres wordt ook wel het adres `5322.From` genoemd.
   - **Infrastructuur:** ook wel de _verzendende infrastructuur genoemd._ Het domein dat is gevonden in een omgekeerde DNS-zoekactie (PTR-record) van het IP-adres van de bron-e-mailserver. Als het bron-IP-adres geen PTR-record heeft, wordt de verzendende infrastructuur geïdentificeerd als \<source IP\> /24 (bijvoorbeeld 192.168.100.100/24).
   - **Aantal berichten:** het aantal berichten van de verzendende infrastructuur naar uw organisatie waarin het opgegeven vervalste domein is opgeslagen in de afgelopen zeven dagen.
   - **Laatst gezien:** de laatste datum waarop een bericht is ontvangen van de verzendende infrastructuur die het vervalste domein bevat.
   - **Type adresvervalsing:** deze waarde is **Extern.**
   - **Mag worden vervalst?** De waarden die u hier ziet, zijn:
     - **Ja:** berichten van de combinatie van vervalste gebruikersdomein en verzendende infrastructuur zijn toegestaan en worden niet behandeld als vervalste e-mail.
     - **Nee:** berichten van de combinatie van vervalste gebruikersdomein en verzendende infrastructuur worden gemarkeerd als vervalst. De actie wordt bepaald door het standaard anti-phishingbeleid of aangepaste anti-phishingbeleidsregels (de standaardwaarde is Bericht verplaatsen naar map **Ongewenste e-mail).**

     Zie [Anti-phishingbeleid configureren in Microsoft Defender voor Office 365 voor meer informatie.](configure-atp-anti-phishing-policies.md)

2. Selecteer een item in de lijst om de details van het domein/verzendende infrastructuurpaar in een flyout te bekijken. Deze informatie omvat:
   - Waarom hebben we dit te weten pakken.
   - Wat u moet doen.
   - Een domeinsamenvatting.
   - WhoIs data about the sender.
   - Vergelijkbare berichten die we in uw tenant van dezelfde afzender hebben gezien.

   Hier kunt u er ook voor kiezen om het domein/verzendende infrastructuurpaar toe te voegen aan of te verwijderen uit de lijst Met toegestane **afzenders** voor adresvervalsing. Stel de schakelknop dienovereenkomstig in.

   ![Schermafbeelding van een domein in het detailvenster met informatie over adresvervalsing](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>Een domein toevoegen aan de lijst met toegestane adresvervalsingen

Als u een domein toevoegt aan de lijst met toegestane adresvervalsingen vanuit het inzicht in adresvervalsingsinformatie, wordt alleen de combinatie van het vervalste domein en *de* verzendende infrastructuur toegestaan. E-mail van het vervalste domein is niet toegestaan vanaf een bron en staat geen e-mail van de verzendende infrastructuur toe voor een domein.

U staat bijvoorbeeld het volgende domein toe aan de lijst met toegestane adresvervalsings:

- **Domein:** gmail.com
- **Infrastructuur:** tms.mx.com

Alleen e-mail van dat domein/verzendende infrastructuurpaar is toegestaan om te spoofen. Andere afzenders die e-gmail.com zijn niet toegestaan. Berichten in andere domeinen van tms.mx.com zijn gecontroleerd op spoof intelligence.

## <a name="related-topics"></a>Verwante onderwerpen

[Bescherming tegen spoofing in Microsoft 365](anti-spoofing-protection.md)
