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
description: Beheerders kunnen leren hoe ze standaard- en striktbeleidsinstellingen kunnen toepassen op de beveiligingsfuncties van Exchange Online Protection (EOP) en Microsoft Defender voor Office 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e41edb6c2d77a69ee3d4fa28ff86e0e77410caa5
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108293"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>Vooraf ingestelde beveiligingsbeleidsregels in EOP en Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Vooraf ingestelde beveiligingsbeleidsregels bieden een gecentraliseerde locatie voor het toepassen van alle aanbevolen spam-, malware- en phishingbeleid voor gebruikers in één keer. De beleidsinstellingen zijn niet configureerbaar. In plaats daarvan worden ze door ons ingesteld en zijn ze gebaseerd op onze waarnemingen en ervaringen in de datacenters voor een evenwicht tussen het weghouden van schadelijke inhoud van gebruikers en het voorkomen van onnodige verstoringen.

In de rest van dit artikel worden vooraf ingestelde beveiligingsbeleidsregels beschreven en hoe u deze configureert.

## <a name="what-preset-security-policies-are-made-of"></a>Uit welke vooraf ingestelde beveiligingsbeleidsregels wordt gemaakt

Vooraf ingestelde beveiligingsbeleidsregels bestaan uit de volgende elementen:

- Profielen
- Beleid
- Beleidsinstellingen

Bovendien is de volgorde van prioriteit belangrijk als meerdere vooraf ingestelde beveiligingsbeleidsregels en ander beleid van toepassing zijn op dezelfde persoon.

### <a name="profiles-in-preset-security-policies"></a>Profielen in vooraf ingesteld beveiligingsbeleid

Een profiel bepaalt het beschermingsniveau. De volgende profielen zijn beschikbaar:

- **Standaardbeveiliging:** een basislijnbeveiligingsprofiel dat geschikt is voor de meeste gebruikers.
- **Strikte beveiliging:** een agressiever beveiligingsprofiel voor geselecteerde gebruikers (hoge waarden of prioriteitsgebruikers).

U gebruikt regels met voorwaarden en uitzonderingen die bepalen wie de profielen zijn of niet worden toegepast.

De beschikbare voorwaarden en uitzonderingen zijn:

- **Gebruikers**: de opgegeven postvakken, e-mailgebruikers or e-mailcontactpersonen binnen uw organisatie.
- **Groepen**: de opgegeven distributiegroepen, beveiligingsgroepen met e-mail of Microsoft 365-groepen binnen uw organisatie.
- **Domeinen**: alle geadresseerden in de opgegeven [geaccepteerde domeinen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) binnen uw organisatie.

U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

### <a name="policies-in-preset-security-policies"></a>Beleidsregels in vooraf ingesteld beveiligingsbeleid

Vooraf ingestelde beveiligingsbeleidsregels gebruiken het bijbehorende beleid van de verschillende beveiligingsfuncties in EOP en Microsoft Defender voor Office 365. Dit beleid wordt gemaakt  _nadat u_ het vooraf ingestelde beveiligingsbeleid standaardbeveiliging of **Strikt beveiligingsbeleid** hebt toegewezen aan gebruikers. U kunt deze beleidsregels niet wijzigen.

- **Exchange Online Protection (EOP)-beleid**: Dit geldt Microsoft 365 organisaties met Exchange Online postvakken en zelfstandige EOP-organisaties zonder Exchange Online postvakken:

  - [Antispambeleid met](configure-your-spam-filter-policies.md) de naam **Standaard vooraf ingestelde beveiligingsbeleid** en strikt vooraf ingestelde **beveiligingsbeleid.**
  - [Anti-malwarebeleid met](configure-anti-malware-policies.md) de naam **Standard Preset Security Policy** and Strict Preset Security **Policy**.
  - [EOP Anti-phishingbeleid met](set-up-anti-phishing-policies.md#spoof-settings) de naam **Standaard vooraf ingestelde beveiligingsbeleid** en **Strikt vooraf ingestelde beveiligingsbeleid** (spoofinstellingen).

- **Microsoft Defender voor Office 365** beleid: Dit geldt ook voor organisaties met Microsoft 365 E5 of Defender voor Office 365-invoegabonnementen:

  - Anti-phishingbeleid in Microsoft Defender voor Office 365 met de naam Standaard vooraf ingestelde **beveiligingsbeleid** en **strikt vooraf** ingestelde beveiligingsbeleid, waaronder:

    - Dezelfde [spoofinstellingen die](set-up-anti-phishing-policies.md#spoof-settings) beschikbaar zijn in het anti-phishingbeleid van EOP.
    - [Instellingen voor imitatie](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Geavanceerde phishingdrempels](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Safe koppelingen met de naam](set-up-safe-links-policies.md) Standaard vooraf ingesteld **beveiligingsbeleid** en **Strikt vooraf ingesteld beveiligingsbeleid.**

  - [Safe bijlagenbeleid met de](set-up-safe-attachments-policies.md) naam **Standaard vooraf ingestelde beveiligingsbeleid** en **Strikt vooraf ingesteld beveiligingsbeleid**.

Houd er rekening mee dat u EOP-beveiligingen kunt toepassen op andere gebruikers dan Microsoft Defender voor Office 365 beveiligingen.

### <a name="policy-settings-in-preset-security-policies"></a>Beleidsinstellingen in vooraf ingesteld beveiligingsbeleid

U kunt de beleidsinstellingen in de beveiligingsprofielen niet wijzigen. De **waarden Standaard** en **Strikt** beleid worden beschreven in aanbevolen instellingen voor EOP en Microsoft Defender voor [Office 365 beveiliging.](recommended-settings-for-eop-and-office365.md)

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Volgorde van prioriteit voor vooraf ingesteld beveiligingsbeleid en ander beleid

Wanneer meerdere beleidsregels worden toegepast op een gebruiker, wordt de volgende volgorde toegepast van hoogste prioriteit naar laagste prioriteit:

1. **Strikt beveiligingsbeleid**
2. **Standaardbeveiligingsinstellingen** voor beveiligingsbeleid
3. Aangepast beveiligingsbeleid
4. Standaardbeveiligingsbeleid

Met andere woorden, de  instellingen van het strikte beveiligingsbeleid overschrijven de instellingen van het standaardbeveiligingsbeleid, waardoor de instellingen worden overgenomen van een aangepast beleid, waardoor de instellingen van het standaardbeleid worden overgenomen. 

## <a name="assign-preset-security-policies-to-users"></a>Vooraf ingestelde beveiligingsbeleidsregels toewijzen aan gebruikers

### <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com>. Als u rechtstreeks naar de pagina Vooraf **ingestelde beveiligingsbeleidsregels wilt** gaan, gebruikt <https://security.microsoft.com/presetSecurityPolicies> u .

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.

- U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u vooraf ingestelde beveiligingsbeleidsregels wilt configureren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
  - Voor alleen-lezen toegang tot vooraf ingestelde beveiligingsbeleidsregels moet u lid zijn van de **rollengroep Globale** lezer.

  Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.

  **Opmerking:** Gebruikers toevoegen aan de bijbehorende Azure Active Directory rol in de Microsoft 365-beheercentrum  geeft gebruikers de vereiste machtigingen en machtigingen voor andere functies in Microsoft 365. Raadpleeg [Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.

### <a name="use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users"></a>De portal Microsoft 365 Defender gebruiken om vooraf ingestelde beveiligingsbeleidsregels toe te wijzen aan gebruikers

1. Ga in Microsoft 365 Defender portal naar **E-mail & Samenwerkingsbeleid** & pagina Regels bedreigingsbeleid sectie Beleidsregels vooraf ingesteld \>  \>  \>  \> **beveiligingsbeleid.**

2. Klik **onder Standaardbeveiliging** **of Strikte beveiliging** op **Bewerken.**

3. De **wizard Standaardbeveiliging toepassen** of Strikte beveiliging **toepassen** wordt gestart. Identificeer op **de pagina EOP-beveiligingen** de interne geadresseerden op wie de [EOP-beveiliging](#policies-in-preset-security-policies) van toepassing is (voorwaarden voor geadresseerden):
   - **Gebruikers**
   - **Groepen**
   - **Domeinen**

   Klik in het juiste vak, begin een waarde te typen en selecteer de gewenste waarde in de resultaten. Herhaal deze stap zo vaak als nodig is. Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) naast de waarde.

   Voor gebruikers of groepen kunt u de meeste id's (naam, weergavenaam, alias, e-mailadres, accountnaam, enzovoort) gebruiken, maar de bijbehorende weergavenaam wordt weergegeven in de resultaten. Voer voor gebruikers een enkel sterretje (\*) in om alle beschikbare waarden weer te geven.

   - **Deze gebruikers, groepen** en domeinen uitsluiten: Als u uitzonderingen wilt toevoegen voor de interne geadresseerden waar het beleid op van toepassing is (uitzonderingen voor geadresseerden), selecteert u deze optie en configureert u de uitzonderingen. De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.

   Wanneer u gereed bent, klikt u op **Volgende**.

4. In Microsoft Defender voor Office 365-organisaties gaat u naar de **Defender** voor Office 365-beveiligingen op de pagina om de interne geadresseerden te identificeren op wie de Microsoft Defender voor [Office 365-beveiliging](#policies-in-preset-security-policies) van toepassing is (voorwaarden voor geadresseerden).

   De instellingen en het gedrag zijn precies zoals de **EOP-beveiligingen van toepassing zijn op de** pagina.

   Wanneer je klaar bent, klik je op **Volgende**.

5. Controleer uw **selecties** op de pagina Controleren en bevestig uw wijzigingen en klik vervolgens op **Bevestigen.**

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-preset-security-policies"></a>Gebruik de Microsoft 365 Defender portal om de toewijzingen van vooraf ingestelde beveiligingsbeleidsregels te wijzigen

De stappen voor het  wijzigen van  de toewijzing van het beveiligingsbeleid Standaardbeveiliging of Strikt beveiligingsbeleid zijn hetzelfde als wanneer u het vooraf ingestelde beveiligingsbeleid in eerste instantie aan [gebruikers hebt toegewezen.](#use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users)

Als u het beveiligingsbeleid **voor** **standaardbeveiliging** of Strikt beveiligingsbeleid wilt uitschakelen met behoud van de bestaande voorwaarden en uitzonderingen, schuift u de schakelknop naar **Uitgeschakeld** ![ In-/uitschakelen. ](../../media/scc-toggle-off.png) Als u het beleid wilt inschakelen, schuift u de schakelknop naar **Ingeschakeld** ![ ](../../media/scc-toggle-on.png) aan.

### <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Als u wilt controleren of u het  beveiligingsbeleid standaardbeveiliging of Strikt beveiligingsbeleid hebt toegewezen aan  een gebruiker, gebruikt u  een beveiligingsinstelling waarbij de standaardwaarde anders is dan de instelling Standaardbeveiliging, wat anders is dan de instelling Strikte beveiliging. 

Voor e-mail die wordt gedetecteerd als spam (geen spam met hoog vertrouwen) controleert  u bijvoorbeeld of het bericht wordt bezorgd in de map Ongewenste e-mail voor standaardbeveiligingsgebruikers en in quarantaine is geplaatst voor gebruikers van strikte **beveiliging.**

Of controleer voor [bulkmail](bulk-complaint-level-values.md)of de BCL-waarde 6 of hoger het  bericht levert aan de map Ongewenste e-mail voor  standaardbeveiligingsgebruikers, en de BCL-waarde 4 of hoger zorgt ervoor dat het bericht in quarantaine wordt geplaatst voor gebruikers met strikte beveiliging.
