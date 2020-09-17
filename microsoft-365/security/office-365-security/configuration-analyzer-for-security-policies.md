---
title: Configuratie analyse voor beveiligingsbeleid
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe u met de wizard Configuratie analyse beveiligingsbeleid onder de standaardbeveiliging en strikte beveiligings beleidsregels voor beveiliging kunt vinden en oplossen.
ms.openlocfilehash: 022f11013ef49c65b1f94fea7a3872233ff1ab14
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949476"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a>Configuratie analyse voor beveiligingsbeleid in EOP en Office 365 ATP

> [!NOTE]
> De functies die in dit onderwerp worden beschreven, zijn in voorbeeld, zijn niet beschikbaar in alle organisaties en zijn onderhevig aan wijzigingen. Voor informatie over de release planning raadpleegt u het [Microsoft 365-wegwijzer](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).

Configuratie-analyse in het compliance van beveiligings & biedt een centrale locatie voor het zoeken naar en herstellen van beveiligingsbeleid waarbij de instellingen onder de standaardbeveiliging en strikte bescherming van profielinstellingen in [vooraf ingesteld beveiligingsbeleid](preset-security-policies.md).

De volgende typen beleidsregels worden geanalyseerd door de Configuration Analyzer:

- **Beleid voor Exchange Online Protection (EOP)**: Dit omvat microsoft 365-organisaties met Exchange Online-postvakken en zelfstandige EOP-organisaties zonder postvakken van Exchange Online:
  
  - [Anti spam beleid](configure-your-spam-filter-policies.md).
  - [Beleid voor malware van malware](configure-anti-malware-policies.md).
  - [EOP anti phishings beleid](set-up-anti-phishing-policies.md#spoof-settings).

- **Office 365 Advanced Threat Protection (ATP)-beleidsregels**: Dit omvat organisaties met microsoft 365 E5 of Office 365 ATP-uitbreidings abonnementen:

  - ATP anti-phishing-beleid, waaronder:

    - De [instellingen voor spoofing](set-up-anti-phishing-policies.md#spoof-settings) die beschikbaar zijn in het anti-phishings beleid van EOP.
    - [Imitatie-instellingen](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [Geavanceerde phishingberichten](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - [Beleidsregels voor veilige koppelingen](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).

  - [Beleidsregels voor veilige bijlagen](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).

De **standaard** waarden en **strikte** beleidsinstelling waarden die worden gebruikt als basislijnen, worden beschreven in [Aanbevolen instellingen voor EOP en Office 365 ATP-beveiliging](recommended-settings-for-eop-and-office365-atp.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u direct naar de pagina **Configuration Analyzer** wilt gaan, gebruikt u <https://protection.office.com/configurationAnalyzer> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

- U moet machtigingen zijn toegewezen voordat u de procedures in dit artikel kunt uitvoeren:

  - Als u de Configuration Analyzer wilt gebruiken **en** beveiligingsbeleidsregels wilt bijwerken, moet u lid zijn van een van de volgende groepen rollen:

    - **Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
    - **Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Voor alleen-lezen toegang tot de configuratie analyse, moet u lid zijn van een van de volgende groepen rollen:

    - **Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
    - **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>Werken met de functie Configuration Analyzer in het compliance van beveiligings &

Ga in het beveiligings & compliance naar **Threat management** \> **Policy** \> **configuratie analyse**beleid voor Threat Management.

![De widget configuratie analyse op de pagina beleid voor risicobeheer \>](../../media/configuration-analyzer-widget.png)

De configuratie analyse bestaat uit twee hoofdtabbladen:

- **Instellingen en aanbevelingen**: u kunt standaard of strict selecteren en deze instellingen vergelijken met uw bestaande beveiligingsbeleidsregels. In de resultaten kunt u de waarden van uw instellingen aanpassen, zodat ze op hetzelfde niveau als standaard of strikt worden weergegeven.

- Configuratie van de overstappen **en geschiedenis**van de configuratie van de overstappen, zodat u de beleidswijzigingen in de tijd kunt bijhouden.

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>Tabblad instelling en aanbevelingen in de configuratie-analyse

Standaard wordt het tabblad op de vergelijking met het standaardbeveiligingsprofiel geopend. U kunt overstappen op de vergelijking van het strikte beveiligingsprofiel door op **strikte aanbevelingen weergeven**te klikken. Als u wilt terugkeren, selecteert u **standaard aanbevelingen weergeven**.

![De weergave van instellingen en aanbevelingen in de configuratie-analyse](../../media/configuration-analyzer-settings-and-recommendations-view.png)

De kolom **Beleidsgroep/naam van instelling** bevat standaard een samengevouwen weergave van de verschillende typen beveiligingsbeleidsregels en het aantal instellingen dat moet worden verbeterd (indien van toepassing). De typen beleidsregels zijn:

- **Anti spam**
- **Anti phishing**
- **Anti malware**
- **Veilige bijlage van ATP** (als uw abonnement de ATP omvat)
- **Veilige koppelingen voor ATP** (als uw abonnement de ATP omvat)

In de standaardweergave is alles samengevouwen. Naast elk beleid bevindt zich een samenvatting van vergelijkingsresultaten van uw beleid (die u kunt wijzigen) en de instellingen in het bijbehorende beleid voor de standaard-of strikte beveiligingsprofielen (die u niet kunt wijzigen). U ziet de volgende informatie voor het beveiligingsprofiel waarmee u een vergelijking maakt:

- **Groen**: alle instellingen in alle bestaande beleidsregels zijn ten minste veilig als het beveiligingsprofiel.
- **Geel**: een klein aantal instellingen in het bestaande beleid is niet veilig als het beveiligingsprofiel.
- **Rood**: een groot aantal instellingen in het bestaande beleid is niet veilig als het beveiligingsprofiel. Dit kan een paar instellingen zijn voor veel beleidsregels of veel instellingen in één beleid.

Voor gunstige vergelijkingen ziet u de tekst: bij **alle instellingen volgen** de \<**Standard** or **Strict**\> **aanbevelingen**. Anders ziet u het aantal aanbevolen instellingen dat u wilt wijzigen.

Als u **Beleidsgroep/naam**van de instelling uitvouwt, worden alle beleidsregels en de bijbehorende instellingen in elk specifiek beleid weergegeven dat aandacht moet richten. U kunt ook een specifiek type beleid uitvouwen (bijvoorbeeld **anti spam**), zodat alleen de instellingen worden weergegeven van de typen beleidsregels die uw aandacht vereisen.

Als de vergelijking geen aanbevelingen oplevert voor verbetering (groen), onthult het beleid niets. Als er sprake is van een aantal aanbevelingen voor verbetering (geel of rood), worden de instellingen die aandacht vereisen weergegeven en wordt de bijbehorende informatie getoond in de volgende kolommen:

- De naam van de instelling die uw aandacht vereist. In de vorige schermafbeelding ziet u bijvoorbeeld de limiet voor **bulk mail** in een antispambeleid.

- **Beleid**: de naam van het betreffende beleid dat de instelling bevat.

- **Toepassen op**: het aantal gebruikers waarop het desbetreffende beleid wordt toegepast.

- **Huidige configuratie**: de huidige waarde van de instelling.

- **Laatst gewijzigd**: de datum waarop het beleid het laatst is gewijzigd.

- **Aanbevelingen**: de waarde van de instelling in het standaard-of strikte beveiligingsprofiel. Als u de waarde van de instelling in het beleid wilt wijzigen zodat deze overeenkomt met de aanbevolen waarde in het beveiligingsprofiel, klikt u op **aannemen**. Als de wijziging slaagt, ziet u het volgende bericht: **aanbevelingen zijn besloten**. Klik op **vernieuwen** om het minder aantal aanbevelingen te zien en het verwijderen van de specifieke rij voor beleidsregels/beleid van de resultaten.

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>Configuratie van configuratie van drijfman en historie van configuratie-analyse

Op dit tabblad kunt u de wijzigingen bijhouden die u in uw aangepaste beveiligingsbeleid hebt aangebracht. Standaard wordt de volgende informatie weergegeven:

- **Laatst gewijzigd**
- **Gewijzigd door**
- **Naam van instelling**
- **Beleid**
- **Type**

Klik op **Filter** om de resultaten te filteren. In de **gefilterde** flyout die wordt weergegeven, kunt u kiezen uit de volgende filters:

- **Begintijd** en **Eindtijd** (datum)
- **Standaard bescherming** of **strikte bescherming**

Als u de resultaten naar een CSV-bestand wilt exporteren, klikt u op **exporteren**.

![Configuratie-analyse-en historie weergave](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
