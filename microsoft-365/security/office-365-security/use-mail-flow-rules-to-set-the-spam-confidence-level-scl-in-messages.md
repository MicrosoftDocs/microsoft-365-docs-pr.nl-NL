---
title: Regels voor e-mail stroom gebruiken voor de SCL in berichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Informatie over het maken van een e-mail stroom regels (transportregels) om berichten te identificeren en het betrouwbaarheidsniveau (spam niveau) van berichten in Exchange Online Protection in te stellen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 447333eb968ba7d91a1673c57b11afdb16b90469
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659835"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>De regels voor de e-mail stroom gebruiken voor het instellen van het betrouwbaarheidsniveau voor ongewenste e-mail (SCL) in berichten in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP-organisaties zonder Exchange Online-postvakken), EOP maakt gebruik van Antispambeleid (ook wel spamfilter beleid of inhouds filter beleid) om inkomende berichten voor spam te scannen. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

Als u bepaalde berichten wilt markeren als spam voordat ze worden gescand via spam filteren of berichten markeren zodat ze spam filteren, kunt u een e-mail stroom regels (ook wel de zogenaamde transportregels) maken om de berichten te identificeren en het betrouwbaarheidsniveau voor ongewenste e-mail (SCL) in te stellen. Zie voor meer informatie over het SCL [spam niveau (SCL) in EOP](spam-confidence-levels.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Voordat u de procedures in dit artikel kunt uitvoeren, moet u beschikken over machtigingen voor Exchange Online of Exchange Online Protection. Specifiek hebt u de rol van **transport regels** nodig, dat is toegewezen aan **Organisatiebeheer**, **nalevings beheer** (globale beheerders) en rollen groepen voor **recordbeheer** .

  Zie de volgende onderwerpen voor meer informatie:

  - [Machtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [Machtigingen in standalone EOP](feature-permissions-in-eop.md)
  - [Werken met de lijst met wijzigingen in de lijst met leden van rollen groepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Zie [Exchange-Beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center)om het SBV te openen in Exchange Online. Als u het Exchange-Beheercentrum in standalone EOP wilt openen, raadpleegt u [Exchange Admin Center in STANDALONE EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Zie voor meer informatie over regels voor e-mail stroom in Exchange Online en Exchange Online Protection Zie [regels voor e-mail stroom (transportregels) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Het Exchange-Beheercentrum gebruiken om een e-mail stroom regel te maken waarmee de SCL van een bericht wordt ingesteld

1. Ga in het Exchange-Beheercentrum naar de regels voor de **e-mail stroom** \> .

2. Klik **op** ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) en selecteer vervolgens **een nieuwe regel maken**.

3. Configureer de volgende instellingen op de pagina **nieuwe regel** die wordt geopend:

   - **Naam**: Typ een unieke, beschrijvende naam voor de regel.

   - Klik op **meer opties**.

   - **Deze regel toepassen als**: Selecteer een of meer voorwaarden voor het identificeren van berichten. Zie voor meer informatie de [voorwaarden voor de e-mail stroom regels en uitzonderingen (predikaten) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

   - **Ga als volgt** te werk: opties voor het wijzigen van het **bericht** is \> **het betrouwbaarheidsniveau van spam (SCL)**. In het dialoogvenster **SCL opgeven** dat wordt weergegeven, configureert u een van de volgende waarden:

   - **Spam filteren negeren**: de berichten worden in spam filteren overgeslagen.

     > [!CAUTION]
     > Wees zeer voorzichtig met het toestaan van berichten om spam te filteren. Kwaadwillenden kunnen dit beveiligingslek gebruiken om phishingberichten en andere schadelijke berichten te verzenden naar uw organisatie. Voor de regels voor de e-mail stroom zijn er meer dan alleen het e-mailadres of domein van de afzender vereist. Zie voor meer informatie [lijsten met veilige afzenders maken in EOP](create-safe-sender-lists-in-office-365.md).

   - **0 t**/m 4: het bericht wordt via spam filteren verzonden voor verdere verwerking.

   - **5 of 6**: het bericht is gemarkeerd als **spam**. De actie die u hebt geconfigureerd voor het filteren van **ongewenste e-mail** Verdicts in uw Antispambeleid op het bericht (de standaardwaarde is **bericht verplaatsen naar map Ongewenste e-mail**).

   - **7 en 9**: het bericht is gemarkeerd als **spam van hoge betrouwbaarheid**. De actie die u hebt geconfigureerd voor het filteren van **ongewenste e-mail** in Verdicts in uw antispambeleid wordt toegepast op het bericht (de standaardwaarde is **bericht verplaatsen naar map Ongewenste e-mail**).

4. Geef de gewenste extra eigenschappen voor de regel op. Klik op **Opslaan** wanneer u gereed bent.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Ga als volgt te werk om te controleren of deze procedure goed werkt: een e-mailbericht naar iemand binnen uw organisatie verzenden en controleren of de actie die op het bericht is uitgevoerd, is zoals verwacht. Als u bijvoorbeeld **het spam niveau (SCL) instelt** om **spam te filteren**, moet het bericht naar het postvak in van de opgegeven ontvanger worden verzonden. Als u echter **het betrouwbaarheidsniveau voor ongewenste e-mail (SCL) instelt** op **9** en de actie **spam hoge betrouwbaarheid** voor uw toepasselijke Antispambeleid is het verplaatsen van het bericht naar de map Ongewenste e-mail, dan moet het bericht worden verzonden naar de map Ongewenste e-mail van de opgegeven geadresseerde.
