---
title: Vooraf ingestelde beveiligingsbeleid
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze standaard- en strikte beleidsinstellingen kunnen toepassen op de beveiligingsfuncties van Exchange Online Protection (EOP) en Office 365 Advanced Threat Protection (ATP)
ms.openlocfilehash: 34445c617d2dda59a65b197db2f42324d0085ab3
ms.sourcegitcommit: 688d62a8c52e4fb0feb721bb92b535effc278f54
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/23/2020
ms.locfileid: "45389870"
---
# <a name="preset-security-policies-in-eop-and-office-365-atp"></a>Vooraf ingesteld beveiligingsbeleid in EOP en Office 365 ATP

Vooraf ingestelde beveiligingsbeleid biedt een gecentraliseerde locatie voor het toepassen van alle aanbevolen spam-, malware- en phishingbeleid op gebruikers tegelijk. De beleidsinstellingen zijn niet configureerbaar. In plaats daarvan worden ze door ons ingesteld en zijn ze gebaseerd op onze observaties en ervaringen in de datacenters voor een evenwicht tussen het weghouden van schadelijke inhoud van gebruikers zonder hun werk te verstoren.

In de rest van dit onderwerp wordt het vooraf ingestelde beveiligingsbeleid beschreven en hoe u deze configureren.

## <a name="what-preset-security-policies-are-made-of"></a>Van vooraf ingestelde beveiligingsbeleid wordt gemaakt

Vooraf ingestelde beveiligingsbeleid bestaat uit de volgende elementen:

- Profielen
- Beleid
- Beleidsinstellingen

Bovendien is de rangorde belangrijk als meerdere vooraf ingestelde beveiligingsbeleid en ander beleid van toepassing zijn op dezelfde persoon.

### <a name="profiles-in-preset-security-policies"></a>Profielen in vooraf ingesteld beveiligingsbeleid

Een profiel bepaalt het beschermingsniveau. De volgende profielen zijn beschikbaar:

- **Standaardbescherming**: een basislijnbeveiligingsprofiel dat geschikt is voor de meeste gebruikers.
- **Strikte bescherming**: Een agressiever beveiligingsprofiel voor geselecteerde gebruikers (high value targets of priority users).

U gebruikt regels met voorwaarden en uitzonderingen die bepalen op wie de profielen wel of niet worden toegepast.

U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

De beschikbare voorwaarden en uitzonderingen zijn:

- **De ontvangers zijn**: Postvakken, e-mailgebruikers of e-mailcontactpersonen in uw organisatie.
- **De ontvangers zijn lid van**: Groepen in uw organisatie.
- **De geadresseerde domeinen zijn:** Geaccepteerde domeinen die zijn geconfigureerd in Microsoft 365.

### <a name="policies-in-preset-security-policies"></a>Beleid in vooraf ingesteld beveiligingsbeleid

Beveiligingsbeleid voor vooraf ingestelde instellingen gebruikt het bijbehorende beleid van de verschillende beveiligingsfuncties in EOP en Office 365 ATP. Dit beleid wordt gemaakt _nadat_ u het vooraf ingestelde beveiligingsbeleid **voor standaardbescherming** of **strikte beveiliging** hebt toegewezen aan gebruikers. U dit beleid niet wijzigen.

- **EOP-beleid (Exchange Online Protection):** Dit omvat Microsoft 365-organisaties met Exchange Online-postvakken en zelfstandige EOP-organisaties zonder Exchange Online-postvakken:
  
  - [Antispambeleid](configure-your-spam-filter-policies.md) met de naam **Standaard vooraf ingestelde beveiligingsbeleid** en **strikt beveiligingsbeleid voor vooraf ingestelde.**
  - [Anti-malware beleid](configure-anti-malware-policies.md) genaamd **Standard Preset Security Policy** en Strikte Preset Security **Policy**.
  - [EOP Anti-phishing beleid](set-up-anti-phishing-policies.md#spoof-settings) genaamd **Standard Preset Security Policy** en Strikte Preset Security **Policy** (spoof instellingen).

- **Atp-beleid (Advanced Threat Protection) van Office 365:** dit geldt ook voor organisaties met Microsoft 365 E5- of Office 365 ATP-invoegabonnementen:

  - ATP-antiphishingbeleid met de naam **Standard Preset Security Policy** en Strikt Vooraf ingesteld **beveiligingsbeleid,** waaronder:

    - Dezelfde [spoofinstellingen](set-up-anti-phishing-policies.md#spoof-settings) die beschikbaar zijn in het EOP-anti-phishingbeleid.
    - [Imitatie-instellingen](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [Geavanceerde phishingdrempels](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - [Safe Links-beleid](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users) met de naam **Standaard vooraf ingestelde beveiligingsbeleid** en **strikt vooraf ingesteld beveiligingsbeleid**.

  - [Beleid voor veilige bijlagen](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users) met de naam **Standaard vooraf ingesteld beveiligingsbeleid** en **strikt vooraf ingesteld beveiligingsbeleid**.

Houd er rekening mee dat u EOP-beveiligingen toepassen op verschillende gebruikers dan ATP-beveiligingen.

### <a name="policy-settings-in-preset-security-policies"></a>Beleidsinstellingen in vooraf ingesteld beveiligingsbeleid

U de beleidsinstellingen in de beveiligingsprofielen niet wijzigen. De **waarden voor standaard** en **strikte** beleidsinstellingen worden beschreven in aanbevolen instellingen [voor EOP- en Office 365 ATP-beveiliging](recommended-settings-for-eop-and-office365-atp.md).

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Rangorde voor vooraf ingestelde beveiligingsbeleid en ander beleid

Wanneer meerdere beleidsregels op een gebruiker worden toegepast, wordt de volgende volgorde toegepast van hoogste prioriteit naar laagste prioriteit:

1. **Beveiligingsbeleid** voor strikte beveiliging vooraf ingesteld
2. **Beveiligingsbeleid** voor standaardbeveiliging vooraf ingesteld
3. Alle andere gerelateerde beleidsregels.

Met andere woorden, de instellingen van het **strikte beveiligingsbeleid** overschrijven de instellingen van het **standaardbeveiligingsbeleid,** waardoor de instellingen worden overschrijft van andere gerelateerde beleidsregels.

## <a name="assign-preset-security-policies-to-users"></a>Vooraf ingestelde beveiligingsbeleid toewijzen aan gebruikers

### <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina **Vooraf ingesteld beveiligingsbeleid** wilt gaan, gebruikt u <https://protection.office.com/presetSecurityPolicies> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

- U moet beschikken over bepaalde machtigingen om de procedures in dit onderwerp te kunnen uitvoeren:

  - Als u vooraf ingestelde beveiligingsbeleid wilt configureren, moet u lid zijn van een van de volgende rolgroepen:

    - **Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
    - **Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Voor alleen-lezen toegang tot vooraf ingestelde beveiligingsbeleid moet u lid zijn van een van de volgende rolgroepen:

    - **Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
    - **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>Gebruik het Security & Compliance Center om vooraf ingestelde beveiligingsbeleid toe te wijzen aan gebruikers

1. Ga in het Security & Compliance Center naar **het** \> vooraf ingestelde beveiligingsbeleid voor **bedreigingsbeheerbeleid** \> **Preset security policies**.

2. Klik **onder Standaardbescherming** of **Strikte bescherming**op **Bewerken**.

3. De wizard **Standaardbeveiliging toepassen** of **Strikte bescherming toepassen,** wordt gestart. Op de **EOP-beveiligingen die van toepassing zijn** op stap, moet u de interne ontvangers identificeren waarop de [EOP-beveiligingen](#policies-in-preset-security-policies) van toepassing zijn:

   1. Klik **op Een voorwaarde toevoegen**. Selecteer in de vervolgkeuzelijst die wordt weergegeven een voorwaarde onder **Toegepast als**:

      - **De ontvangers zijn**
      - **De ontvangers zijn lid van**
      - **De geadresseerde domeinen zijn**

      U een voorwaarde slechts één keer gebruiken, maar u meerdere waarden opgeven voor de voorwaarde. Meerdere waarden van dezelfde voorwaarde gebruiken OF-logica _\<recipient1\>_ (bijvoorbeeld, of _\<recipient2\>_ ).

   2. De voorwaarde die u hebt geselecteerd, wordt weergegeven in een gearceerde sectie. Klik in die sectie in **het vak Een van deze.** Als u even wacht, verschijnt er een lijst zodat u een waarde selecteren. U ook beginnen met het typen van een waarde om de lijst te filteren en een waarde te selecteren. Herhaal deze stap zo vaak als nodig is. Als u een afzonderlijke waarde wilt verwijderen, **klikt** u ![ op pictogram Verwijderen verwijderen op de ](../../media/scc-remove-icon.png) waarde. Als u de volledige **Remove** voorwaarde wilt verwijderen, klikt u ![ op pictogram Verwijderen op de ](../../media/scc-remove-icon.png) voorwaarde verwijderen.

   3. Als u een andere voorwaarde wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u in de resterende voorwaarden. Verschillende voorwaarden gebruiken EN logica _\<recipient1\>_ (bijvoorbeeld, en _\<member of group 1\>_ ).

      Herhaal de vorige stap om waarden toe te voegen aan de voorwaarde en herhaal deze stap zo vaak als nodig is of totdat u geen voorwaarden meer hebt.

   4. Als u een uitzondering wilt toevoegen, klikt u op **Een voorwaarde toevoegen**. Selecteer in de vervolgkeuzelijst die wordt weergegeven een voorwaarde onder **Behalve wanneer**. De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.

   Klik op **Volgende**als u klaar bent.

4. Als uw organisatie Office 365 ATP heeft, wordt u naar de **ATP-beveiligingen** geleid om de interne ontvangers te identificeren waarop de [ATP-beveiligingen van Office 365](#policies-in-preset-security-policies) van toepassing zijn.

   De instellingen en het gedrag zijn precies zoals de **EOP-beveiligingen van toepassing zijn op** stap.

   Klik op **Volgende**als u klaar bent.

5. Controleer in de stap **Bevestigen** uw selecties en klik vervolgens op **Bevestigen**.

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>Gebruik het Security & Compliance Center om de toewijzingen van vooraf ingestelde beveiligingsbeleid te wijzigen

De stappen om de toewijzing van het beveiligingsbeleid **voor standaardbeveiliging** of **strikte beveiliging** te wijzigen, zijn dezelfde als wanneer u het [vooraf ingestelde beveiligingsbeleid](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)in eerste instantie aan gebruikers hebt toegewezen.

Als u het beveiligingsbeleid **voor standaardbeveiliging** of **strikte beveiliging** wilt uitschakelen terwijl de bestaande voorwaarden en uitzonderingen behouden blijven, schuift u de schakelaar naar **Uitgeschakeld.** Als u het beleid wilt inschakelen, schuift u de schakelaar naar **Ingeschakeld**.

### <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Als u wilt controleren of u het beveiligingsbeleid **voor standaardbeveiliging** of **strikte beveiliging** aan een gebruiker hebt toegewezen, gebruikt u een beveiligingsinstelling waarbij de standaardwaarde anders is dan de **standaardbeveiligingsinstelling,** wat anders is dan de instelling **Strikte beveiliging.**

Bijvoorbeeld, voor e-mail die wordt gedetecteerd als spam (niet hoog vertrouwen spam) controleren of het bericht wordt geleverd aan de map Ongewenste e-mail voor **standaard beveiligingsgebruikers,** en in quarantaine geplaatst voor **gebruikers van strikte bescherming.**

Of controleer voor [bulke-mail](bulk-complaint-level-values.md)of de BCL-waarde 6 of hoger het bericht aflevert in de map Ongewenste e-mail voor gebruikers **van standaardbeveiliging** en de BCL-waarde 4 of hoger het bericht voor **gebruikers van strikte bescherming** in quarantaine.
