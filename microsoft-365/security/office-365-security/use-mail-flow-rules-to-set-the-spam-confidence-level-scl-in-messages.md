---
title: E-mailstroomregels gebruiken voor de SCL in berichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Meer informatie over het maken van regels voor e-mailstromen (transportregels) om berichten te identificeren en het spamvertrouwensniveau (SCL) van berichten in Exchange Online Protection in te stellen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 223e676579c99eca7db641146d3a1b6bd22f9ca2
ms.sourcegitcommit: 1f3101326e8a54b9bda4ba0324eae00fafcf5e7b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44405117"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>Gebruik regels voor e-mailstroom om het spamvertrouwensniveau (SCL) in te stellen in berichten in EOP

In Microsoft 365-organisaties met postvakken in Exchange Online- of zelfstandige Exchange Online Protection-organisaties (EOP)-organisaties zonder Exchange Online-postvakken gebruikt EOP antispambeleid (ook wel spamfilterbeleid of inhoudsfilterbeleid genoemd) om binnenkomende berichten te scannen op spam. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

Als u specifieke berichten als spam wilt markeren voordat ze worden gescand door spamfiltering, of berichten markeren zodat ze spamfilters overslaan, u regels voor e-mailstroom (ook wel transportregels genoemd) maken om de berichten te identificeren en het spamvertrouwensniveau (SCL) in te stellen. Zie [Spam vertrouwensniveau (SCL) in EOP voor](spam-confidence-levels.md)meer informatie over de SCL.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet machtigingen in Exchange Online krijgen toegewezen voordat u deze procedures uitvoeren. U moet in het bijzonder de rol **Transportregels** toegewezen krijgen, die standaard is toegewezen aan de rollen **Organisatiebeheer,** **Compliancebeheer**en **Records Management.** Zie [Rolgroepen beheren in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)voor meer informatie .

- Zie [Exchange-beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center)als u de EAC in Exchange Online wilt openen.

- Zie [Regels voor e-mailstroom (transportregels) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) voor meer informatie over regels voor e-mailstromen in Exchange Online

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>De EAC gebruiken om een e-mailstroomregel te maken die de SCL van een bericht instelt

1. Ga in de EAC naar **Mail flow** \> **Rules**.

2. Klik **op** ![ Pictogram Toevoegen toevoegen en selecteer vervolgens Een nieuwe ](../../media/ITPro-EAC-AddIcon.png) regel **maken**.

3. Configureer op de pagina **Nieuwe regel** die wordt geopend de volgende instellingen:

   - **Naam:** Voer een unieke, beschrijvende naam voor de regel in.

   - Klik **op Meer opties**.

   - **Pas deze regel toe als**: Selecteer een of meer voorwaarden om berichten te identificeren. Zie [Voorwaarden en uitzonderingen (predicaten) e-mailstroomregel in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)voor meer informatie.

   - **Ga als volgt**te werk: Selecteer **De eigenschappen van het bericht wijzigen** stel het \> **spamvertrouwensniveau (SCL) in.** Configureer in het dialoogvenster **SCL opgeven** dat wordt weergegeven een van de volgende waarden:

   - **Spamfiltering omzeilen:** de berichten slaan spamfiltering over.

     > [!CAUTION]
     > Wees zeer voorzichtig met het toestaan van berichten om spam filtering overslaan. Aanvallers kunnen dit beveiligingslek gebruiken om phishing en andere schadelijke berichten naar uw organisatie te verzenden. De regels voor e-mailstroom vereisen meer dan alleen het e-mailadres of domein van de afzender. Zie [Lijsten met veilige afzenders maken in EOP](create-safe-sender-lists-in-office-365.md)voor meer informatie.

   - **0 tot 4**: Het bericht wordt verzonden via spamfiltering voor extra verwerking.

   - **5 of 6**: Het bericht is gemarkeerd als **Spam**. De actie die u hebt **Spam** ingesteld voor spamfiltervonnissen in uw antispambeleid, wordt toegepast op het bericht (de standaardwaarde is **Bericht verplaatsen naar map Ongewenste e-mail).**

   - **7 tot 9**: Het bericht is gemarkeerd als **High confidence spam**. De actie die u hebt geconfigureerd voor spamfiltervonnissen met **een hoog vertrouwen** in uw antispambeleid, wordt toegepast op het bericht (de standaardwaarde is Bericht verplaatsen naar map Ongewenste **e-mail).**

4. Geef eventuele extra eigenschappen op die u voor de regel wilt hebben. Klik op **Opslaan** wanneer u gereed bent.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of deze procedure correct werkt, stuurt u een e-mailbericht naar iemand binnen uw organisatie en controleert u of de actie die op het bericht is uitgevoerd, zoals verwacht. Als u bijvoorbeeld **het spamvertrouwensniveau (SCL) instelt** op **Het filteren van spam omzeilen,** moet het bericht naar het postvak IN van de opgegeven ontvanger worden verzonden. Als u **echter het spamvertrouwensniveau (SCL) instelt** op **9**en de **spamactie met veel vertrouwen** voor uw toepasselijke antispambeleid is om het bericht naar de map Ongewenste e-mail te verplaatsen, moet het bericht naar de map Ongewenste e-mail van de opgegeven ontvanger worden verzonden.
