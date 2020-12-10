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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen de standaard-en strikte beleidsinstellingen toepassen op de beveiligingsfuncties van Exchange Online Protection (EOP) en Microsoft Defender voor Office 365
ms.openlocfilehash: fb613916ec375214b33b8b842c6817561920715d
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616042"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>Vooraf ingesteld beveiligingsbeleid in EOP en Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Vooraf ingesteld beveiligingsbeleid biedt een centrale locatie voor het toepassen van alle aanbevolen spam, malware en Phishingfilter aan gebruikers tegelijk. Het is niet mogelijk om de beleidsinstellingen te configureren. In plaats daarvan worden ze door ons opgezet en zijn ze gebaseerd op onze waarnemingen en ervaringen in de datacenters voor een evenwicht tussen het behoud van schadelijke inhoud van gebruikers zonder dat ze hun werk onderbreken.

In de rest van dit onderwerp wordt vooraf ingesteld beveiligingsbeleid beschreven en wordt uitgelegd hoe u deze kunt configureren.

## <a name="what-preset-security-policies-are-made-of"></a>Welke vooraf ingestelde beveiligingsbeleidsregels worden gemaakt van

Vooraf ingestelde beveiligingsbeleidsregels bestaan uit de volgende elementen:

- Profiel
- Lijnen
- Beleidsinstellingen

Daarnaast is de volgorde van prioriteit belangrijk als er meerdere vooraf ingestelde beveiligingsbeleidsregels en andere beleidsregels van toepassing zijn op dezelfde persoon.

### <a name="profiles-in-preset-security-policies"></a>Profielen in vooraf ingesteld beveiligingsbeleid

Een profiel bepaalt het beschermingsniveau. De volgende profielen zijn beschikbaar:

- **Standaard bescherming**: een profiel voor basisbescherming dat geschikt is voor de meeste gebruikers.
- **Stringente bescherming**: een meer agressief beveiligingsprofiel voor geselecteerde gebruikers (doelgroepen met hoge waarden of gebruikersprioriteit).

U gebruikt regels met voorwaarden en uitzonderingen om te bepalen wie er profielen zijn of waarop niet wordt toegepast.

U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

Dit zijn de beschikbare voorwaarden en uitzonderingen:

- **De geadresseerden zijn**: postvakken, e-mail gebruikers of contactpersonen in uw organisatie.
- **De geadresseerden zijn lid van**: groepen in uw organisatie.
- **De domeinen van de ontvanger zijn**: geaccepteerde domeinen die zijn geconfigureerd in microsoft 365.

### <a name="policies-in-preset-security-policies"></a>Beleidsregels in vooraf ingesteld beveiligingsbeleid

Vooraf ingesteld beveiligingsbeleid gebruikt het bijbehorende beleid van de verschillende beveiligingsfuncties in EOP en Microsoft Defender voor Office 365. Deze beleidsregels worden gemaakt _nadat_ u de vooraf ingestelde beveiligings beleidsregels **Standaardbeveiliging** of **strikte beveiliging** aan gebruikers hebt toegewezen. U kunt deze beleidsregels niet wijzigen.

- **Beleid voor Exchange Online Protection (EOP)**: Dit omvat microsoft 365-organisaties met Exchange Online-postvakken en zelfstandige EOP-organisaties zonder postvakken van Exchange Online:

  - [Anti spam beleid](configure-your-spam-filter-policies.md) met de naam **standaard ingestelde beveiligingsbeleid** en **strikte beveiligingsbeleid**.
  - [Beleidsregels voor anti-malware](configure-anti-malware-policies.md) met de naam **standaard ingestelde beveiligingsbeleid** en **strikt vooraf ingesteld beveiligingsbeleid**.
  - [EOP anti-phishingfilter](set-up-anti-phishing-policies.md#spoof-settings) met de naam **standaard ingesteld beveiligingsbeleid** en **strikte beveiligingsbeleid** (spoof instellingen).

- **Beleidsregels voor Microsoft Defender voor Office 365**: Dit omvat organisaties met microsoft 365 E5 of Defender voor Office 365-invoegtoepassingen:

  - Anti phishingfilter in Microsoft Defender voor Office 365 met de naam **standaard vooraf ingestelde beveiligingsbeleid** en **strikte vooraf ingesteld beveiligingsbeleid**, waaronder:

    - De [instellingen voor spoofing](set-up-anti-phishing-policies.md#spoof-settings) die beschikbaar zijn in het anti-phishings beleid van EOP.
    - [Imitatie-instellingen](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Geavanceerde phishingberichten](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Beleidsregels voor veilige koppelingen](set-up-atp-safe-links-policies.md) met de naam **standaard vooraf ingesteld beveiligingsbeleid** en **strikte vooraf ingesteld beveiligingsbeleid**.

  - [Beleidsregels voor veilige bijlagen](set-up-atp-safe-attachments-policies.md) met de naam **standaard ingesteld beveiligingsbeleid** en **strikte beveiligingsbeleid**.

U kunt EOP-bescherming toepassen op verschillende gebruikers dan Microsoft Defender voor Office 365 Protection.

### <a name="policy-settings-in-preset-security-policies"></a>Beleidsinstellingen in vooraf ingesteld beveiligingsbeleid

U kunt de beleidsinstellingen in de beveiligingsprofielen niet wijzigen. De waarden voor **standaard** en **strikte** beleidsinstelling worden beschreven in [Aanbevolen instellingen voor EOP en microsoft Defender voor Office 365-beveiliging](recommended-settings-for-eop-and-office365-atp.md).

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Prioriteit van vooraf ingestelde beveiligingsbeleidsregels en andere beleidsregels

Wanneer meerdere beleidsregels op een gebruiker worden toegepast, wordt de volgende volgorde toegepast op de laagste prioriteit:

1. Vooraf ingesteld beveiligingsbeleid **strikte beveiliging**
2. **Standaardinstelling voor standaardbeveiliging**
3. Aangepast beveiligingsbeleid
4. Standaardbeveiligingsbeleid

Met andere woorden: de instellingen van het **strikte beveiligings** beleid negeren de instellingen van het beleid voor de **Standaardbeveiliging** , waardoor de instellingen van het standaardbeleid worden overschreven.

## <a name="assign-preset-security-policies-to-users"></a>Vooraf ingesteld beveiligingsbeleid toewijzen aan gebruikers

### <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u direct naar de pagina **vooraf ingesteld beveiligingsbeleid** wilt gaan, gebruikt u <https://protection.office.com/presetSecurityPolicies> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

- U moet machtigingen zijn toegewezen voordat u de procedures in dit artikel kunt uitvoeren:

  - Voor het configureren van vooraf ingestelde beveiligingsbeleidsregels moet u lid zijn van de rollen **Organisatiebeheer** of **beveiligingsbeheerder** in het [beveiligings & nalevings centrum](permissions-in-the-security-and-compliance-center.md).

  - Voor alleen-lezen toegang voor vooraf ingestelde beveiligingsbeleidsregels moet u lid zijn van de rollen groep **algemene lezer** in het [beveiligings & nalevings centrum](permissions-in-the-security-and-compliance-center.md).

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>Met behulp van het compliance-beveiligings & u vooraf ingestelde beveiligingsbeleidsregels aan gebruikers toewijzen

1. Ga in het beveiligings & nalevings centrum naar  \>  \> **vooraf gedefinieerde beveiligingsbeleid** van het beleid voor bedreigings beheer.

2. Klik onder **Standaardbeveiliging** of **strikte beveiliging** op **bewerken**.

3. De wizard **Standaardbeveiliging toepassen** of **strikte beveiliging toepassen** . Identificeer op de **EOP-beveiligingstoepassing voor** stap de interne geadresseerden waarop de [EOP-bescherming](#policies-in-preset-security-policies) van toepassing is:

   1. Klik op **een voorwaarde toevoegen**. Selecteer een voorwaarde in de vervolgkeuzelijst die wordt weergegeven **als**:

      - **De geadresseerden zijn**
      - **De geadresseerden zijn lid van**
      - **De domeinen van de ontvanger zijn**

      U kunt slechts één voorwaarde gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde. Meerdere waarden van dezelfde voorwaarde gebruiken of logica (bijvoorbeeld _\<recipient1\>_ of _\<recipient2\>_ ).

   2. De voorwaarde die u hebt geselecteerd, wordt weergegeven in een gearceerde sectie. Klik in de sectie **een van deze** vakken. Als u een ogenblik geduld, verschijnt er een lijst, zodat u een waarde kunt selecteren. U kunt ook een waarde typen om de lijst te filteren en een waarde te selecteren. Herhaal deze stap zo vaak als nodig is. Als u een afzonderlijke waarde **wilt verwijderen, klikt u** op ![ het pictogram verwijderen ](../../media/scc-remove-icon.png) van de waarde. Als u de volledige voorwaarde wilt **verwijderen, klikt u** op ![ pictogram verwijderen ](../../media/scc-remove-icon.png) in de voorwaarde.

   3. Als u nog een voorwaarde wilt toevoegen, klikt u op **een voorwaarde toevoegen** en selecteert u een van de resterende voorwaarden. Voorbeelden van gebruik en logica van verschillende voorwaarden (bijvoorbeeld _\<recipient1\>_ en _\<member of group 1\>_ ).

      Herhaal de vorige stap om waarden toe te voegen aan de voorwaarde en herhaal deze stap zo vaak als nodig is of pas de voorwaarden af.

   4. Als u een uitzondering wilt toevoegen, klikt u op **een voorwaarde toevoegen**. Selecteer een voorwaarde in de vervolgkeuzelijst die wordt weergegeven, **behalve wanneer**. De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.

   Wanneer u klaar bent, klikt u op **volgende**.

4. Als uw organisatie Microsoft Defender voor Office 365 heeft, bent u op de i **ATP-beveiliging van toepassing** op de interne geadresseerden waarop de [Microsoft defender voor Office 365-beveiliging](#policies-in-preset-security-policies) van toepassing is.

   De instellingen en het gedrag lijken exact op de **EOP-bescherming van toepassing op** stap.

   Wanneer u klaar bent, klikt u op **volgende**.

5. Controleer uw selecties in de stap **bevestigen** en klik vervolgens op **bevestigen**.

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>Het nalevings centrum voor beveiliging & gebruiken om de toewijzingen van vooraf ingestelde beveiligingsbeleidsregels te wijzigen

De stappen voor het wijzigen van de toewijzing van het beveiligingsbeleid van de **Standaardbeveiliging** of voor **strikte beveiliging** zijn hetzelfde als wanneer u [de vooraf ingestelde beveiligingsbeleidsregels aan gebruikers hebt toegewezen](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).

Als u de **Standaardbeveiliging** of beveiligings beleidsregels voor **strikte** beveiliging wilt uitschakelen, maar de bestaande voorwaarden en uitzonderingen wel wilt behouden, verschuift u de wisselknop naar **uitgeschakeld**. Als u het beleid wilt inschakelen, verschuift u de wisselknop naar **ingeschakeld**.

### <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Als u wilt controleren of u het beveiligingsbeleid **Standaardbeveiliging** of **strikte** beveiliging aan een gebruiker hebt toegewezen, gebruikt u een beveiligingsinstelling waarbij de standaardwaarde verschilt van de instelling standaard **beveiliging** , wat niet de instelling is van de **strikte beveiliging** .

Voor e-mailberichten die als spam zijn gedetecteerd (niet hoge betrouwbaarheid), controleert u of het bericht wordt bezorgd in de map Ongewenste E-mail voor standaardgebruikers van **beveiliging** en wordt quarantaine voor gebruikers met **strikte beveiliging** .

Voor [bulk-e-mail](bulk-complaint-level-values.md)controleert u of de waarde van de BCL waarde 6 of hoger is voor de map Ongewenste E-mail voor standaardgebruikers van **beveiliging** en de BCL waarde 4 of hoger is het bericht voor **strikte beschermings** gebruikers.
