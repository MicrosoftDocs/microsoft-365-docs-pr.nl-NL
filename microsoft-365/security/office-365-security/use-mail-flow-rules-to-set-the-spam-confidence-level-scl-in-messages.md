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
ms.openlocfilehash: 67a4c25a1006e9b1554cf8ffbc2d5e29b4063752
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827371"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>De regels voor de e-mail stroom gebruiken voor het instellen van het betrouwbaarheidsniveau voor ongewenste e-mail (SCL) in berichten in EOP

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP-organisaties zonder Exchange Online-postvakken), EOP maakt gebruik van Antispambeleid (ook wel spamfilter beleid of inhouds filter beleid) om inkomende berichten voor spam te scannen. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

Als u bepaalde berichten wilt markeren als spam voordat ze worden gescand via spam filteren of berichten markeren zodat ze spam filteren, kunt u een e-mail stroom regels (ook wel de zogenaamde transportregels) maken om de berichten te identificeren en het betrouwbaarheidsniveau voor ongewenste e-mail (SCL) in te stellen. Zie voor meer informatie over het SCL [spam niveau (SCL) in EOP](spam-confidence-levels.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet machtigingen toegewezen hebben in Exchange Online voordat u deze procedures kunt uitvoeren. Specifiek moet u de rol van **transport regels** toewijzen, die aan de rollen voor **Organisatiebeheer**, **Compliance Management**, en het **beheer van recordbeheer** standaard is toegewezen. Zie [rollen groepen beheren in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)voor meer informatie.

- Zie [Exchange-Beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center)om het SBV te openen in Exchange Online.

- Zie voor meer informatie over regels voor de e-mail stroom in Exchange Online, [regels voor e-mail stroom (transportregels) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Het Exchange-Beheercentrum gebruiken om een e-mail stroom regel te maken waarmee de SCL van een bericht wordt ingesteld

1. Ga in het Exchange-Beheercentrum naar de regels voor de **e-mail stroom** \> **Rules**.

2. Klik **op** ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) en selecteer vervolgens **een nieuwe regel maken**.

3. Configureer de volgende instellingen op de pagina **nieuwe regel** die wordt geopend:

   - **Naam**: Typ een unieke, beschrijvende naam voor de regel.

   - Klik op **meer opties**.

   - **Deze regel toepassen als**: Selecteer een of meer voorwaarden voor het identificeren van berichten. Zie voor meer informatie de [voorwaarden voor de e-mail stroom regels en uitzonderingen (predikaten) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

   - **Ga als volgt**te werk: opties voor het wijzigen van het **bericht** is \> **het betrouwbaarheidsniveau van spam (SCL)**. In het dialoogvenster **SCL opgeven** dat wordt weergegeven, configureert u een van de volgende waarden:

   - **Spam filteren negeren**: de berichten worden in spam filteren overgeslagen.

     > [!CAUTION]
     > Wees zeer voorzichtig met het toestaan van berichten om spam te filteren. Kwaadwillenden kunnen dit beveiligingslek gebruiken om phishingberichten en andere schadelijke berichten te verzenden naar uw organisatie. Voor de regels voor de e-mail stroom zijn er meer dan alleen het e-mailadres of domein van de afzender vereist. Zie voor meer informatie [lijsten met veilige afzenders maken in EOP](create-safe-sender-lists-in-office-365.md).

   - **0 t**/m 4: het bericht wordt via spam filteren verzonden voor verdere verwerking.

   - **5 of 6**: het bericht is gemarkeerd als **spam**. De actie die u hebt geconfigureerd voor het filteren van **ongewenste e-mail** Verdicts in uw Antispambeleid op het bericht (de standaardwaarde is **bericht verplaatsen naar map Ongewenste e-mail**).

   - **7 en 9**: het bericht is gemarkeerd als **spam van hoge betrouwbaarheid**. De actie die u hebt geconfigureerd voor het filteren van **ongewenste e-mail** in Verdicts in uw antispambeleid wordt toegepast op het bericht (de standaardwaarde is **bericht verplaatsen naar map Ongewenste e-mail**).

4. Geef de gewenste extra eigenschappen voor de regel op. Klik op **Opslaan** wanneer u gereed bent.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Ga als volgt te werk om te controleren of deze procedure goed werkt: een e-mailbericht naar iemand binnen uw organisatie verzenden en controleren of de actie die op het bericht is uitgevoerd, is zoals verwacht. Als u bijvoorbeeld **het spam niveau (SCL) instelt** om **spam te filteren**, moet het bericht naar het postvak in van de opgegeven ontvanger worden verzonden. Als u echter **het betrouwbaarheidsniveau voor ongewenste e-mail (SCL) instelt** op **9**en de actie **spam hoge betrouwbaarheid** voor uw toepasselijke Antispambeleid is het verplaatsen van het bericht naar de map Ongewenste e-mail, dan moet het bericht worden verzonden naar de map Ongewenste e-mail van de opgegeven geadresseerde.
