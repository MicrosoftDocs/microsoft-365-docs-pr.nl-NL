---
title: Configuratieanalyse voor beveiligingsbeleid
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie krijgen over het gebruik van de configuratieanalyse om beveiligingsbeleid te zoeken en op te lossen dat zich onder het standaardbeveiligingsbeleid en het vooraf ingestelde beveiligingsbeleid voor strikte beveiliging kunt vinden en oplossen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fd0cf4f3194a7a8eec39f2d0c447dca2dae5948b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537929"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>Configuratieanalyse voor beveiligingsbeleid in EOP en Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Configuratieanalyse in het Beveiligings- & Compliancecentrum biedt een centrale locatie om beveiligingsbeleid te zoeken en op te lossen, waar de instellingen zich onder de instellingen Standaardbeveiligings- en Strikt beveiligingsprofiel bevinden in vooraf ingestelde [beveiligingsbeleidsregels.](preset-security-policies.md)

De volgende typen beleid worden geanalyseerd door de configuratieanalyse:

- **Exchange Online Protection (EOP)-beleid**: Dit geldt Microsoft 365 organisaties met Exchange Online postvakken en zelfstandige EOP-organisaties zonder Exchange Online postvakken:

  - [Antispambeleid.](configure-your-spam-filter-policies.md)
  - [Anti-malwarebeleid.](configure-anti-malware-policies.md)
  - [EOP-anti-phishingbeleid.](set-up-anti-phishing-policies.md#spoof-settings)

- **Microsoft Defender voor Office 365** beleid: Dit geldt ook voor organisaties met Microsoft 365 E5 of Defender voor Office 365-invoegabonnementen:

  - Anti-phishingbeleid in Microsoft Defender voor Office 365, waaronder:

    - Dezelfde [spoofinstellingen die](set-up-anti-phishing-policies.md#spoof-settings) beschikbaar zijn in het anti-phishingbeleid van EOP.
    - [Instellingen voor imitatie](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Geavanceerde phishingdrempels](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Safe koppelingenbeleid](set-up-safe-links-policies.md).

  - [Safe bijlagenbeleid](set-up-safe-attachments-policies.md).

De **waarden standaard** en **strikt** beleid die als basislijnen worden gebruikt, worden beschreven in aanbevolen instellingen voor EOP en Microsoft Defender voor [Office 365 beveiliging.](recommended-settings-for-eop-and-office365.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de **pagina Configuratieanalyse wilt** gaan, gebruikt u <https://protection.office.com/configurationAnalyzer> .

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.

- Je moet beschikken over toegewezen machtigingen voor het uitvoeren van de procedures in dit onderwerp:
  - Als u de configuratieanalyse wilt gebruiken **en** updates voor beveiligingsbeleid wilt uitvoeren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
  - Voor alleen-lezen toegang tot de configuratieanalyse moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**

  Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

  > [!NOTE]
  >  
  > - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  >
  > - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>De configuratieanalyse gebruiken in het beveiligings- & compliancecentrum

Ga in het & compliancecentrum naar **Beleidsanalyse voor bedreigingsbeheer** \>  \> .

![Widget Configuratieanalyse op de pagina Beleid voor \> bedreigingsbeheer](../../media/configuration-analyzer-widget.png)

De configuratieanalyse heeft twee hoofdtabbladen:

- **Instellingen en aanbevelingen:** U kiest Standaard of Strikt en vergelijkt deze instellingen met uw bestaande beveiligingsbeleid. In de resultaten kunt u de waarden van uw instellingen aanpassen om deze op hetzelfde niveau te brengen als Standaard of Strikt.

- **Configuratiedriftanalyse en -geschiedenis:** met deze weergave kunt u beleidswijzigingen in de tijd bijhouden.

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>Tabblad Instellingen en aanbevelingen in de configuratieanalyse

Standaard wordt het tabblad geopend in de vergelijking met het standaardbeveiligingsprofiel. U kunt overschakelen naar de vergelijking van het beveiligingsprofiel Strikt door op Strikte aanbevelingen **weergeven te klikken.** Als u wilt teruggaan, **selecteert u Standaardaanbevelingen weergeven.**

![Instellingen en aanbevelingen weergeven in de configuratieanalyse](../../media/configuration-analyzer-settings-and-recommendations-view.png)

Standaard bevat de kolom **Beleidsgroep/instellingsnaam** een samengevouwen weergave van de verschillende typen beveiligingsbeleid en het aantal instellingen dat moet worden verbeterd (indien van beide). De typen beleidsregels zijn:

- **Antispam**
- **Anti-phishing**
- **Anti-malware**
- **ATP Safe bijlagen** (als uw abonnement Microsoft Defender voor Office 365)
- **ATP Safe Koppelingen** (als uw abonnement Microsoft Defender voor Office 365)

In de standaardweergave wordt alles samengevouwen. Naast elk beleid ziet u een overzicht van de vergelijkingsresultaten van uw beleid (dat u kunt wijzigen) en de instellingen in het bijbehorende beleid voor de standaard- of strikte beveiligingsprofielen (die u niet kunt wijzigen). U ziet de volgende informatie voor het beveiligingsprofiel dat u vergelijkt met:

- **Groen:** Alle instellingen in alle bestaande beleidsregels zijn ten minste even veilig als het beveiligingsprofiel.
- **Oranje:** Een klein aantal instellingen in het bestaande beleid is niet zo veilig als het beveiligingsprofiel.
- **Rood:** Een aanzienlijk aantal instellingen in het bestaande beleid is niet zo veilig als het beveiligingsprofiel. Dit kunnen enkele instellingen zijn in veel beleidsregels of veel instellingen in één beleid.

Voor gunstige vergelijkingen ziet u de tekst: **Alle instellingen volgen** \<**Standard** or **Strict**\> **aanbevelingen.** Anders ziet u het aantal aanbevolen instellingen dat u wilt wijzigen.

Als u de **naam van de groep Beleid/instelling** uitv vouwt, worden alle beleidsregels en de bijbehorende instellingen in elk specifiek beleid die aandacht vereisen, openbaar. U kunt ook een specifiek type beleid (bijvoorbeeld **Antispam)** uitbreiden om alleen die instellingen weer te geven in de beleidtypen die uw aandacht vereisen.

Als de vergelijking geen aanbevelingen voor verbetering (groen) heeft, laat het uitbreiden van het beleid niets zien. Als er een aantal aanbevelingen voor verbetering (oranje of rood) zijn, worden de instellingen die aandacht vereisen, onthuld en worden de bijbehorende informatie in de volgende kolommen aan het licht komen:

- De naam van de instelling die uw aandacht vereist. In de vorige schermafbeelding is het bijvoorbeeld de drempelwaarde Voor bulksgewijs e-mail **in** een antispambeleid.

- **Beleid:** de naam van het betreffende beleid dat de instelling bevat.

- **Toegepast op**: Het aantal gebruikers waar het betreffende beleid op wordt toegepast.

- **Huidige configuratie:** de huidige waarde van de instelling.

- **Laatst gewijzigd:** de datum waarop het beleid voor het laatst is gewijzigd.

- **Aanbevelingen:** De waarde van de instelling in het beveiligingsprofiel Standaard of Strikt. Als u de waarde van de instelling in uw beleid wilt wijzigen op de aanbevolen waarde in het beveiligingsprofiel, klikt u op **Goedkeuren.** Als de wijziging is gelukt, ziet u het bericht: **Aanbevelingen is goedgekeurd.** Klik **op** Vernieuwen om het beperkte aantal aanbevelingen weer te geven en de specifieke rij met instellingen/beleid uit de resultaten te verwijderen.

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>Tabblad Configuratiedriftanalyse en -geschiedenis in de configuratieanalyse

Op dit tabblad kunt u de wijzigingen bijhouden die u hebt aangebracht in uw aangepaste beveiligingsbeleid. Standaard worden de volgende gegevens weergegeven:

- **Laatst gewijzigd**
- **Gewijzigd door**
- **Naam instellen**
- **Beleid**
- **Type**

Klik op **Filter** om de resultaten te filteren. In het **flyout** Filters dat wordt weergegeven, kunt u kiezen uit de volgende filters:

- **Begintijd** **en eindtijd** (datum)
- **Standaardbeveiliging** of **Strikte beveiliging**

Als u de resultaten wilt exporteren naar een .csv bestand, klikt u op **Exporteren.**

![Configuratiedriftanalyse en geschiedenisweergave in configuratieanalyse](../../media/configuration-analyzer-configuration-drift-analysis-view.png)