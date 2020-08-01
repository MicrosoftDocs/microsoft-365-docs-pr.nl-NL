---
title: Configuratieanalyzer voor beveiligingsbeleid
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze de configuratieanalyzer kunnen gebruiken om beveiligingsbeleid te vinden en vast te stellen dat instellingen bevat die lager zijn dan het beveiligingsbeleid voor standaardbescherming en strikte beveiliging.
ms.openlocfilehash: 259d498646ecf893a57a608a37e3b771083716cc
ms.sourcegitcommit: fab425ea4580d1924fb421e6db233d135f5b7d19
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533968"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a>Configuratieanalyzer voor beveiligingsbeleid in EOP en Office 365 ATP

> [!NOTE]
> De functies die in dit onderwerp worden beschreven, staan in Voorbeeld, zijn niet beschikbaar in alle organisaties en kunnen worden gewijzigd.

Configuratieanalyzer in het Security & Compliance center biedt een centrale locatie voor het vinden en repareren van een van uw beveiligingsbeleid dat instellingen bevat die lager zijn dan de instellingen voor standaardbeveiliging en strikt beveiligingsprofiel in [vooraf ingestelde beveiligingsbeleid.](preset-security-policies.md)

De volgende typen beleidsregels worden geanalyseerd door de configuratieanalyzer:

- **EOP-beleid (Exchange Online Protection):** Dit omvat Microsoft 365-organisaties met Exchange Online-postvakken en zelfstandige EOP-organisaties zonder Exchange Online-postvakken:
  
  - [Anti-spam beleid](configure-your-spam-filter-policies.md).
  - [Anti-malware beleid](configure-anti-malware-policies.md).
  - [EOP Anti-phishing beleid](set-up-anti-phishing-policies.md#spoof-settings).

- **Atp-beleid (Advanced Threat Protection) van Office 365:** dit geldt ook voor organisaties met Microsoft 365 E5- of Office 365 ATP-invoegabonnementen:

  - ATP anti-phishing beleid, waaronder:

    - Dezelfde [spoofinstellingen](set-up-anti-phishing-policies.md#spoof-settings) die beschikbaar zijn in het EOP-anti-phishingbeleid.
    - [Imitatie-instellingen](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [Geavanceerde phishingdrempels](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - [Beleid voor veilige links](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).

  - [Beleid voor veilige bijlagen](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).

De **standaard-** en **strikte** beleidsinstellingswaarden die worden gebruikt als basislijnen, worden beschreven in [aanbevolen instellingen voor EOP- en Office 365 ATP-beveiliging](recommended-settings-for-eop-and-office365-atp.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina **Configuratieanalyse wilt** gaan, gebruikt u <https://protection.office.com/configurationAnalyzer> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

- U moet beschikken over bepaalde machtigingen om de procedures in dit onderwerp te kunnen uitvoeren:

  - Als u de configuratieanalyzer wilt gebruiken **en** het beveiligingsbeleid wilt bijsy-updaten, moet u lid zijn van een van de volgende rolgroepen:

    - **Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
    - **Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Voor alleen-lezen toegang tot de configuratieanalyzer moet u lid zijn van een van de volgende rolgroepen:

    - **Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
    - **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>De configuratieanalyzer gebruiken in het Security & Compliance Center

Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Configuration analyzer**.

![Widget Configuratieanalyzer op de \> pagina Bedreigingsbeheerbeleid](../../media/configuration-analyzer-widget.png)

De configuratieanalyzer heeft twee hoofdtabbladen:

- **Instellingen en aanbevelingen**: u kiest Standaard of Streng en vergelijkt deze instellingen met uw bestaande beveiligingsbeleid. In de resultaten u de waarden van uw instellingen aanpassen om ze op hetzelfde niveau te brengen als Standaard of Streng.

- **Analyse en geschiedenis van configuratiedrift:** met deze weergave u de wijzigingen bijhouden die u in uw beleid hebt aangebracht op basis van de resultaten van de configuratieanalyzer in de loop van de tijd.

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>Tabblad Instelling en aanbevelingen in de configuratieanalyzer

Standaard wordt het tabblad geopend op de vergelijking met het standaardbeveiligingsprofiel. U overschakelen naar de vergelijking van het strikt beschermingsprofiel door op **Strikte aanbevelingen weergeven**te klikken. Als u terug wilt schakelen, selecteert u **Standaardaanbevelingen weergeven**.

![Weergave Instellingen en aanbevelingen in de configuratieanalyseree](../../media/configuration-analyzer-settings-and-recommendations-view.png)

Standaard bevat de **kolom Beleidsgroep/instellingsnaam** een samengevouwen weergave van de verschillende typen beveiligingspolitie en het aantal instellingen in het beleid dat moet worden verbeterd (indien van toepassing). De soorten beleid zijn:

- **Anti-spam**
- **Anti-phishing**
- **Anti-malware**
- **ATP Safe Attachments** (als uw abonnement ATP bevat)
- **ATP Safe Links** (als uw abonnement ATP bevat)

In de standaardweergave is alles samengevouwen. Naast elk beleid worden een overzicht weergegeven van de vergelijkingsresultaten van uw beleid (die u wijzigen) en de instellingen in het bijbehorende beleid voor de standaard- of strikte beveiligingsprofielen (die u niet wijzigen). U ziet de volgende informatie:

- **Groen:** Alle instellingen in alle bestaande beleidsregels zijn minstens zo veilig als het beveiligingsprofiel waarmee u het vergelijkt.
- **Amber:** Een klein aantal instellingen in het bestaande beleid zijn niet zo veilig als het beveiligingsprofiel waarmee u zich ver vergeleek.
- **Rood:** Een aanzienlijk aantal instellingen in het bestaande beleid is niet zo veilig als het beveiligingsprofiel waarmee u zich ver vergeleek. Dit kunnen een paar instellingen in veel beleidsregels of veel instellingen in een beleid.

Voor gunstige vergelijkingen ziet u de tekst: **Alle instellingen volgen** \<**Standard** or **Strict**\> **aanbevelingen.** Anders ziet u het aantal aanbevolen instellingen dat moet worden gewijzigd.

Als u **de naam van de beleidsgroep/-instelling uitbreidt,** worden alle beleidsregels en de bijbehorende instellingen in elk specifiek beleid die aandacht vereisen, weergegeven. U ook een specifiek type beleid (bijvoorbeeld **antispam)** uitbreiden om alleen die instellingen te zien in dat soort beleidsregels waarvoor uw aandacht vereist is.

Als de vergelijking geen aanbevelingen voor verbetering (groen) heeft, onthult het uitbreiden van het beleid niets. Als er een aantal aanbevelingen voor verbetering (amber of rood), de instellingen die aandacht vereisen worden onthuld, en de bijbehorende informatie wordt onthuld in de volgende kolommen:

- De naam van de instelling die uw aandacht vereist. In de vorige schermafbeelding is het bijvoorbeeld de **drempel voor bulke-mail** in een antispambeleid.

- **Beleid**: de naam van het betreffende beleid dat de instelling bevat.

- **Toegepast op**: Het aantal gebruikers waarop het betreffende beleid wordt toegepast.

- **Huidige configuratie**: de huidige waarde van de instelling.

- **Laatst gewijzigd**: De datum waarop het beleid voor het laatst is gewijzigd.

- **Aanbevelingen**: De waarde van de instelling in het standaard- of strikt beschermingsprofiel. Als u de waarde van de instelling in uw beleid wilt wijzigen die overeenkomt met de aanbevolen waarde in het beveiligingsprofiel, klikt u op **Adopteren**. Als de wijziging is geslaagd, ziet u het bericht: **Aanbevelingen die zijn aangenomen.** Klik **op Vernieuwen** om het verminderde aantal aanbevelingen en het verwijderen van de specifieke instellings-/beleidsrij uit de resultaten te bekijken.

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>Tabblad Configuratiedriftanalyse en geschiedenis in de configuratieanalyzer

Met dit tabblad u de wijzigingen bijhouden die u hebt aangebracht in uw aangepaste beveiligingsbeleid op basis van de informatie in de beveiligingsanalyseer. Standaard worden de volgende gegevens weergegeven:

- **Laatst gewijzigd**
- **Gewijzigd door**
- **Naam instellen**
- **Beleid**
- **Type**

Klik op **Filter** om de resultaten te filteren. In de flyout **Filters** die wordt weergegeven, u kiezen uit de volgende filters:

- **Begintijd** en **eindtijd** (datum)
- **Standaardbescherming** of **strikte bescherming**

Als u de resultaten wilt exporteren naar een CSV-bestand, klikt u op **Exporteren**.

![Configuratiedriftanalyse en geschiedenisweergave in de configuratieanalyzer](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
