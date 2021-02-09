---
title: Beveiligingsbeleid vooraf instellen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie krijgen over het toepassen van standaard- en strikte beleidsinstellingen voor de beveiligingsfuncties van Exchange Online Protection (EOP) en Microsoft Defender voor Office 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f57b388716eca02741ba48b3e6b47b7cf9f28884
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150077"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>Vooraf ingestelde beveiligingsbeleidsregels in EOP en Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender voor Office 365-abonnement 1 en abonnement 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Vooraf ingestelde beveiligingsbeleid biedt een centrale locatie voor het tegelijk toepassen van alle aanbevolen spam-, malware- en phishingbeleidsregels op gebruikers. De beleidsinstellingen kunnen niet worden geconfigureerd. In plaats daarvan worden ze door ons ingesteld en zijn ze gebaseerd op onze waarnemingen en ervaringen in de datacenters voor een balans tussen het weghouden van schadelijke inhoud voor gebruikers zonder hun werk te verstoren.

In de rest van dit onderwerp worden vooraf ingestelde beveiligingsbeleidsregels beschreven en hoe u deze kunt configureren.

## <a name="what-preset-security-policies-are-made-of"></a>De vooraf ingestelde beveiligingsbeleidsregels

Vooraf ingestelde beveiligingsbeleidsregels bestaan uit de volgende elementen:

- Profielen
- Beleidsregels
- Beleidsinstellingen

Bovendien is de volgorde van prioriteit belangrijk als meerdere vooraf ingestelde beveiligingsbeleidsregels en andere beleidsregels op dezelfde persoon van toepassing zijn.

### <a name="profiles-in-preset-security-policies"></a>Profielen in vooraf ingesteld beveiligingsbeleid

Een profiel bepaalt het beschermingsniveau. De volgende profielen zijn beschikbaar:

- **Standaardbeveiliging:** een basislijnbeveiligingsprofiel dat geschikt is voor de meeste gebruikers.
- **Strikte beveiliging:** een strikter beveiligingsprofiel voor geselecteerde gebruikers (doelen voor hoge waarden of gebruikers met een hoge prioriteit).

U gebruikt regels met voorwaarden en uitzonderingen die bepalen op wie de profielen zijn of niet worden toegepast.

U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

De beschikbare voorwaarden en uitzonderingen zijn:

- **De geadresseerden zijn:** postvakken, e-mailgebruikers of e-mailcontactcontacten in uw organisatie.
- **De geadresseerden zijn leden van:** Groepen in uw organisatie.
- **De domeinen van de ontvanger zijn:** Geaccepteerde domeinen die zijn geconfigureerd in Microsoft 365.

### <a name="policies-in-preset-security-policies"></a>Beleid in vooraf ingesteld beveiligingsbeleid

Vooraf ingestelde beveiligingsbeleidsregels maken gebruik van de bijbehorende beleidsregels van de verschillende beveiligingsfuncties in EOP en Microsoft Defender voor Office 365. Dit beleid wordt gemaakt _nadat u_ het vooraf **ingestelde** beveiligingsbeleid Voor standaardbeveiliging of **Strikte beveiliging** hebt toegewezen aan gebruikers. U kunt dit beleid niet wijzigen.

- **Beleidsregels voor Exchange Online Protection (EOP:** Dit geldt ook voor Microsoft 365-organisaties met Exchange Online-postvakken en zelfstandige EOP-organisaties zonder Exchange Online-postvakken:

  - [Antispambeleid met de naam](configure-your-spam-filter-policies.md) **Standaard vooraf ingestelde beveiligingsbeleid en** Strikt vooraf ingestelde **beveiligingsbeleid.**
  - [Anti-malwarebeleid genaamd](configure-anti-malware-policies.md) **Standaard vooraf ingestelde beveiligingsbeleid en** Strikt vooraf ingestelde **beveiligingsbeleid.**
  - [EOP Anti-phishingbeleid met de](set-up-anti-phishing-policies.md#spoof-settings) naam **Standaard vooraf ingestelde beveiligingsbeleid en** Strikt vooraf ingestelde **beveiligingsbeleid** (spoof-instellingen).

- Beleid van Microsoft Defender voor **Office 365:** dit geldt ook voor organisaties met Microsoft 365 E5- of Defender voor Office 365-abonnementen met invoegabonnementen:

  - Anti-phishingbeleid in Microsoft Defender voor Office  365, met de namen Standaard vooraf ingestelde beveiligingsbeleid en Strikt vooraf ingestelde beveiligingsbeleid, waaronder:

    - Dezelfde [spoof-instellingen](set-up-anti-phishing-policies.md#spoof-settings) die beschikbaar zijn in het anti-phishingbeleid van EOP.
    - [Imitatie-instellingen](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Geavanceerde drempelwaarden voor phishing](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Beleid voor veilige koppelingen met](set-up-atp-safe-links-policies.md) de naam **Standaardbeveiligingsbeleid en** Strikt vooraf ingesteld **beveiligingsbeleid.**

  - [Beleid voor veilige bijlagen met de](set-up-atp-safe-attachments-policies.md) naam **Standaardbeveiligingsbeleid en** Strikt vooraf ingesteld **beveiligingsbeleid.**

U kunt EOP-beveiliging toepassen op andere gebruikers dan Microsoft Defender voor Office 365-beveiliging.

### <a name="policy-settings-in-preset-security-policies"></a>Beleidsinstellingen in vooraf ingestelde beveiligingsbeleidsregels

U kunt de beleidsinstellingen in de beveiligingsprofielen niet wijzigen. De **waarden voor** de beleidsinstelling Standaard en Strikt worden beschreven in aanbevolen instellingen voor de beveiliging van EOP en Microsoft Defender voor Office  [365.](recommended-settings-for-eop-and-office365-atp.md)

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Volgorde van prioriteit voor vooraf ingesteld beveiligingsbeleid en ander beleid

Wanneer meerdere beleidsregels worden toegepast op een gebruiker, wordt de volgende volgorde toegepast van hoogste naar laagste prioriteit:

1. **Strikt beveiligingsbeleid**
2. **Standaardbeveiliging vooraf** ingestelde beveiligingsbeleid
3. Aangepast beveiligingsbeleid
4. Standaardbeveiligingsbeleid

Met andere woorden, de  instellingen van het beleid voor  strikte beveiliging overschrijven de instellingen van het standaardbeveiligingsbeleid, waardoor de instellingen van een aangepast beleid worden overschrijven, waardoor de instellingen van het standaardbeleid worden overschrijven.

## <a name="assign-preset-security-policies-to-users"></a>Vooraf ingestelde beveiligingsbeleidsregels toewijzen aan gebruikers

### <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina Vooraf **ingesteld beveiligingsbeleid wilt** gaan, gebruikt u <https://protection.office.com/presetSecurityPolicies> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.

- Je moet beschikken over toegewezen machtigingen voor het uitvoeren van de procedures in dit onderwerp:
  - Als u vooraf ingesteld beveiligingsbeleid wilt configureren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
  - Voor alleen-lezen toegang tot vooraf ingesteld beveiligingsbeleid moet u lid zijn van de rollengroep **Globale** lezer.

  Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

  **Opmerking:** als u gebruikers toevoegt aan de bijbehorende Azure Active Directory-rol in het Microsoft 365-beheercentrum, krijgen gebruikers de vereiste machtigingen in het beveiligings- & compliancecentrum en machtigingen voor andere functies in Microsoft 365.  Raadpleeg [Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>Het beveiligings- & gebruiken om vooraf ingestelde beveiligingsbeleidsregels aan gebruikers toe te wijzen

1. Ga in het & compliancecentrum naar  Vooraf ingestelde beveiligingsbeleidsregels voor \>  \> **risicobeheerbeleid.**

2. Klik **onder Standaardbeveiliging** **of Strikte beveiliging** op **Bewerken.**

3. De **wizard Standaardbeveiliging toepassen** of Strikte beveiliging **toepassen** wordt gestart. Zoek in **de EOP-beveiligingen** die van toepassing zijn op stap de interne geadresseerden op wie de [EOP-beveiligingen](#policies-in-preset-security-policies) van toepassing zijn:

   1. Klik **op Voorwaarde toevoegen.** Selecteer in de vervolgkeuzepkeuze die wordt weergegeven een voorwaarde onder **Toegepast als:**

      - **De geadresseerden zijn**
      - **De geadresseerden zijn lid van**
      - **De domeinen van de ontvanger zijn**

      U kunt een voorwaarde slechts eenmaal gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde. Meerdere waarden van dezelfde voorwaarde gebruiken OF-logica (bijvoorbeeld _\<recipient1\>_ of _\<recipient2\>_ ).

   2. De geselecteerde voorwaarde wordt weergegeven in een gearceerde sectie. Klik in deze sectie in het **vak Een van deze.** Als u even wacht, wordt er een lijst weergegeven zodat u een waarde kunt selecteren. U kunt ook een waarde typen om de lijst te filteren en een waarde selecteren. Herhaal deze stap zo vaak als nodig is. Als u een afzonderlijke waarde wilt verwijderen, klikt **u op het** pictogram Verwijderen van de ![ ](../../media/scc-remove-icon.png) waarde. Als u de gehele voorwaarde wilt verwijderen, klikt **u op het** pictogram Verwijderen van de ![ ](../../media/scc-remove-icon.png) voorwaarde.

   3. Als u nog een voorwaarde wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u een van de overige voorwaarden. Voor verschillende voorwaarden wordt EN-logica gebruikt _\<recipient1\>_ (bijvoorbeeld, en _\<member of group 1\>_ ).

      Herhaal de vorige stap om waarden toe te voegen aan de voorwaarde en herhaal deze stap zo vaak als nodig is of totdat de voorwaarden op zijn.

   4. Als u een uitzondering wilt toevoegen, klikt **u op Voorwaarde toevoegen.** Selecteer een voorwaarde onder Behalve wanneer in de **vervolgkeuzepkeuze die wordt weergegeven.** De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.

   Klik op Volgende wanneer u klaar **bent.**

4. Als uw organisatie gebruik maakt van Microsoft Defender voor Office 365, gaat u naar de beveiliging van **ATP** om vast te stellen op welke interne geadresseerden de beveiliging van Microsoft Defender voor [Office 365](#policies-in-preset-security-policies) van toepassing is.

   De instellingen en het gedrag zijn precies hetzelfde als de **EOP-beveiligingen die worden toegepast op stap.**

   Klik op Volgende wanneer u klaar **bent.**

5. Controleer **uw** selecties in de stap Bevestigen en klik op **Bevestigen.**

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>Het beveiligings- & compliancecentrum gebruiken om de toewijzingen van vooraf ingestelde beveiligingsbeleidsregels te wijzigen

De stappen voor het  wijzigen van  de toewijzing van het beveiligingsbeleid standaard of strikt beveiligingsbeleid zijn hetzelfde als wanneer u het vooraf ingestelde beveiligingsbeleid in eerste instantie aan [gebruikers hebt toegewezen.](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)

Als u het **beveiligingsbeleid standaard of** **Strikt** beveiligingsbeleid wilt uitschakelen terwijl de bestaande voorwaarden en uitzonderingen behouden blijven, schuift u de schakelaar naar **Uitgeschakeld.** Als u het beleid wilt inschakelen, schuift u de schakelaar naar **Ingeschakeld.**

### <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Als u wilt controleren of  het beveiligingsbeleid standaard- of strikt beveiligingsbeleid aan een gebruiker is toegewezen, gebruikt u een  beveiligingsinstelling waarbij de standaardwaarde verschilt van de instelling Standaardbeveiliging. Dit is anders dan de instelling Strikte beveiliging.  

Controleer bijvoorbeeld bij e-mail die is gedetecteerd als spam (geen spam met hoge betrouwbaarheid) of het bericht wordt bezorgd in de map Ongewenste e-mail voor Standaardbeveiligingsgebruikers en of het in quarantaine is geplaatst voor gebruikers van strikte **beveiliging.** 

Of controleer bij [bulkmail](bulk-complaint-level-values.md)of het bericht met BCL-waarde 6 of  hoger in de map Ongewenste e-mail voor standaardbeveiligingsgebruikers wordt geplaatst en of het bericht in quarantaine wordt geplaatst met de waarde 4 of hoger voor gebruikers met strikte beveiliging. 
