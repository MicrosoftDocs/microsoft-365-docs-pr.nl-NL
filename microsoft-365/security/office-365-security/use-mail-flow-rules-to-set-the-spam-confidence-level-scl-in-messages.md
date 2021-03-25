---
title: E-mailstroomregels gebruiken voor de SCL in berichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Informatie over het maken van regels voor e-mailstroom (transportregels) om berichten te identificeren en het betrouwbaarheidsniveau voor spam (SCL) van berichten in Exchange Online Protection in te stellen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 795347046342ea17870e7758a6327facf51315a4
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204452"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>Regels voor e-mailstroom gebruiken om het betrouwbaarheidsniveau voor spam (SCL) in te stellen in berichten in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, gebruikt EOP antispambeleid (ook wel spamfilterbeleid of inhoudsfilterbeleid genoemd) om binnenkomende berichten te scannen op spam. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

Als u specifieke berichten wilt markeren als spam voordat ze zelfs worden gescand door spamfilters, of berichten markeren zodat ze spamfilters overslaan, kunt u regels voor e-mailstroom (ook wel transportregels genoemd) maken om de berichten te identificeren en het betrouwbaarheidsniveau voor spam (SCL) in te stellen. Zie Betrouwbaarheidsniveau spam [(SCL) in EOP voor meer informatie over de SCL.](spam-confidence-levels.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet machtigingen krijgen toegewezen in Exchange Online of Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren. U hebt met name de rol **Transportregels** nodig, die standaard is toegewezen aan de rollengroepen **Organisatiebeheer,** **Compliancebeheer** (globale beheerders) en **Recordsbeheer.**

  Zie de volgende onderwerpen voor meer informatie:

  - [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo)
  - [Machtigingen in standalone EOP](feature-permissions-in-eop.md)
  - [De lijst met leden in rollengroepen wijzigen met het EAC](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Zie [Exchange-beheercentrum in Exchange Online](/Exchange/exchange-admin-center)om het EAC in Exchange Online te openen. Zie [Exchange-beheercentrum in](exchange-admin-center-in-exchange-online-protection-eop.md)zelfstandige EOP om de EAC in zelfstandige EOP te openen.

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Zie Regels voor e-mailstroom [(transportregels) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) voor meer informatie over e-mailstroomregels in Exchange Online en Exchange Online Protection.

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>De EAC gebruiken om een e-mailstroomregel te maken die de SCL van een bericht in stelt

1. Ga in het EAC naar **E-mailstroomregels.** \> 

2. Klik **op Pictogram** Toevoegen toevoegen en selecteer vervolgens Een nieuwe regel ![ ](../../media/ITPro-EAC-AddIcon.png) **maken.**

3. Configureer **de volgende instellingen** op de pagina Nieuwe regel die wordt geopend:

   - **Naam:** Voer een unieke, beschrijvende naam in voor de regel.

   - Klik **op Meer opties.**

   - **Pas deze regel toe als**: Selecteer een of meer voorwaarden om berichten te identificeren. Zie Voorwaarden en uitzonderingen voor [e-mailstroomregelen (predicaten) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)voor meer informatie.

   - **Ga als volgt te** werk: Selecteer **De eigenschappen van het bericht wijzigen** om \> **het betrouwbaarheidsniveau voor spam (SCL) in te stellen.** Configureer een van de volgende waarden in het dialoogvenster **SCL** opgeven dat wordt weergegeven:

   - **Spamfilters overslaan:** de berichten worden overgeslagen op spamfilters.

     > [!CAUTION]
     > Wees erg voorzichtig met het toestaan dat berichten spamfilters overslaan. Aanvallers kunnen dit beveiligingsprobleem gebruiken om phishing en andere schadelijke berichten naar uw organisatie te verzenden. Voor de regels voor de e-mailstroom is meer nodig dan alleen het e-mailadres of domein van de afzender. Zie Lijsten met veilige afzenders maken in EOP voor [meer informatie.](create-safe-sender-lists-in-office-365.md)

   - **0 tot en met 4**: Het bericht wordt verzonden via spamfilters voor aanvullende verwerking.

   - **5 of 6**: Het bericht is gemarkeerd als **Spam.** De actie die u hebt  geconfigureerd voor spamfilters in uw antispambeleid, wordt toegepast op het bericht (de standaardwaarde is Bericht verplaatsen naar map **Ongewenste e-mail).**

   - **7 tot en met 9**: Het bericht is gemarkeerd als **Spam met hoog vertrouwen.** De actie die u hebt  geconfigureerd voor het filteren van spam met hoge betrouwbaarheid in uw antispambeleid, wordt toegepast op het bericht (de standaardwaarde is Bericht verplaatsen naar map Ongewenste **e-mail).**

4. Geef eventuele extra eigenschappen op die u voor de regel wilt hebben. Klik op **Opslaan** wanneer u gereed bent.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of deze procedure correct werkt, verzendt u een e-mailbericht naar iemand binnen uw organisatie en controleert u of de actie die op het bericht is uitgevoerd, is zoals verwacht. Als u bijvoorbeeld het **betrouwbaarheidsniveau voor spam (SCL)** in stelt op **Spamfilters** omzeilen, moet het bericht worden verzonden naar het Postvak IN van de opgegeven geadresseerde. Als u echter het betrouwbaarheidsniveau voor ongewenste e-mail  **(SCL)** in stelt op **9** en u het bericht wilt verplaatsen naar de map Ongewenste e-mail, wordt het bericht naar de map Ongewenste e-mail verzonden naar de map Ongewenste e-mail van de opgegeven geadresseerde.