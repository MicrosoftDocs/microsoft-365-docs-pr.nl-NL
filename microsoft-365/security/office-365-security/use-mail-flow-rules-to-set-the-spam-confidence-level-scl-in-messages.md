---
title: Regels voor de e-mailstroom gebruiken in de SCL in berichten
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
description: Informatie over het maken van regels voor de e-mailstroom (transportregels) om berichten te identificeren en het spamver vertrouwelijkheidsniveau van berichten in te stellen in Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: aa2893214543f77114d517dc38f874d6172a920a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287555"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>Regels voor de e-mailstroom gebruiken om het betrouwbaarheidsniveau voor ongewenste e-mail in te stellen in berichten in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken gebruikt EOP antispambeleidsregels (ook wel spamfilterbeleid of inhoudsfilterbeleid genoemd) om inkomende berichten op spam te scannen. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

Als u specifieke berichten wilt markeren als spam voordat ze zelfs worden gescand op spamfilters, of als u berichten wilt markeren zodat ze geen spamfilters meer gebruiken, kunt u regels voor de e-mailstroom (ook wel transportregels genoemd) maken om de berichten te identificeren en het betrouwbaarheidsniveau voor spam in te stellen. Zie het betrouwbaarheidsniveau voor ongewenste e-mail in EOP voor meer informatie over de [SCL.](spam-confidence-levels.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet machtigingen toegewezen krijgen in Exchange Online of Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren. U hebt met name de rol **Transportregels** nodig, die standaard is toegewezen aan de rollengroepen **Organisatiebeheer,** **Compliancebeheer** (globale beheerders) en **Recordbeheer.**

  Zie de volgende onderwerpen voor meer informatie:

  - [Machtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [Machtigingen in standalone EOP](feature-permissions-in-eop.md)
  - [De lijst met leden in rollengroepen wijzigen met het EAC](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Als u het Exchange-beheercentrum wilt openen in Exchange Online, gaat u naar [het Exchange-beheercentrum in Exchange Online.](https://docs.microsoft.com/Exchange/exchange-admin-center) Zie het Exchange-beheercentrum in de zelfstandige EOP om het Exchange-beheercentrum [te openen in de zelfstandige EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Zie E-mailstroomregels [(transportregels) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) voor meer informatie over regels voor de e-mailstroom in Exchange Online en Exchange Online Protection.

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Het EAC gebruiken om een regel voor de e-mailstroom te maken die de SCL van een bericht in stelt

1. Ga in het EAC naar **Regels voor e-mailstroom.** \> 

2. Klik **op het** pictogram Toevoegen en selecteer vervolgens Een nieuwe regel ![ ](../../media/ITPro-EAC-AddIcon.png) **maken.**

3. Configureer **de volgende instellingen** op de pagina Nieuwe regel die wordt geopend:

   - **Naam:** voer een unieke, beschrijvende naam voor de regel in.

   - Klik **op Meer opties.**

   - **Pas deze regel toe als:** selecteer een of meer voorwaarden voor het identificeren van berichten. Zie voorwaarden en uitzonderingen [(predicaten)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)voor de e-mailstroomregel in Exchange Online voor meer informatie.

   - **Ga als volgt te** werk: selecteer **Wijzigen van de berichteigenschappen** \> **om het betrouwbaarheidsniveau voor ongewenste e-mail in te stellen.** Configureer een van de volgende waarden in het dialoogvenster **SCL** opgeven dat wordt weergegeven:

   - **Spamfilters omzeilen:** de berichten worden overgeslagen naar spamfilters.

     > [!CAUTION]
     > Wees voorzichtig met het toestaan dat berichten spamfilters overslaan. Aanvallers kunnen dit beveiligingsprobleem gebruiken om phishing en andere schadelijke berichten naar uw organisatie te verzenden. Voor de regels voor de e-mailstroom is meer nodig dan alleen het e-mailadres of domein van de afzender. Zie Lijsten met veilige afzenders maken in EOP voor [meer informatie.](create-safe-sender-lists-in-office-365.md)

   - **0 tot 4:** Het bericht wordt verzonden via spamfilters voor aanvullende verwerking.

   - **5 of 6:** Het bericht wordt gemarkeerd als **Spam.** De actie die u hebt  geconfigureerd voor spamfilters in uw antispambeleid wordt toegepast op het bericht (de standaardwaarde is Bericht verplaatsen naar map Ongewenste **e-mail).**

   - **7 tot 9:** Het bericht wordt gemarkeerd als zeer **vertrouwelijk spam.** De actie die u hebt  geconfigureerd voor een spamfilter met hoge betrouwbaarheid in uw antispambeleid wordt toegepast op het bericht (de standaardwaarde is Bericht verplaatsen naar map Ongewenste **e-mail).**

4. Geef eventuele extra eigenschappen op die u voor de regel wilt hebben. Klik op **Opslaan** wanneer u gereed bent.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of deze procedure correct werkt, verzendt u een e-mailbericht naar iemand binnen uw organisatie en controleert u of de actie die voor het bericht wordt uitgevoerd, is zoals verwacht. Als u bijvoorbeeld het betrouwbaarheidsniveau voor ongewenste e-mail **hebt** ingesteld op Het omzeilen van **spamfilters,** moet het bericht worden verzonden naar het Postvak IN van de opgegeven geadresseerde. Als u echter het betrouwbaarheidsniveau voor **ongewenste** e-mail  in stelt op **9** en u het bericht in hoge mate wilt verplaatsen naar de map Ongewenste e-mail, moet het bericht naar de map Ongewenste e-mail van de opgegeven geadresseerde worden verplaatst.
