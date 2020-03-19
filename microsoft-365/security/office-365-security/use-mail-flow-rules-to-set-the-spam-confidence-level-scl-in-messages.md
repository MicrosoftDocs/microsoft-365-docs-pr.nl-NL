---
title: Regels voor e-mailstroom gebruiken om het spamvertrouwensniveau (SCL) in berichten in te stellen
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe u de SCL van berichten instellen in Exchange Online Protection.
ms.openlocfilehash: 10440d5ac8cd57388f4550f21ca72ce7aa1a2745
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808451"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a>Regels voor e-mailstroom gebruiken om het spamvertrouwensniveau (SCL) in berichten in te stellen

U een e-mailstroomregel maken (ook wel een transportregel genoemd) waarmee het spamvertrouwen (SCL) van een e-mailbericht wordt ingesteld. De SCL is een maat voor hoe waarschijnlijk een bericht is om spam te zijn. Spam is ongevraagde (en meestal ongewenste) e-mailberichten. De service onderneemt verschillende actie op een bericht, afhankelijk van de SCL-beoordeling. U bijvoorbeeld spaminhoud omzeilen die wordt gefilterd op berichten die worden verzonden van mensen binnen uw organisatie, omdat u erop vertrouwt dat een bericht dat intern van een collega wordt verzonden, geen spam is. Het gebruik van regels voor de stroom van e-mail om de SCL-waarde van een bericht in te stellen, geeft u meer controle bij het verwerken van spam.

 **Wat moet je weten voordat je begint?**

- Geschatte tijd om deze procedure te voltooien: 10 minuten.

- U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Zie de vermelding 'Regels voor de stroomstroom' in [Functiemachtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) of [Functiemachtigingen in EOP](feature-permissions-in-eop.md)om te zien welke machtigingen u nodig hebt.

- Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.

### <a name="to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Een e-mailstroomregel maken waarmee de SCL van een bericht wordt ingesteld

1. Kies in het Exchange-beheercentrum (EAC) de optie \> **Regels** **voor de stroom van e-mail** .

2. Kies Pictogram](../../media/ITPro-EAC-AddIcon.gif) **Nieuw**![toevoegen en selecteer Vervolgens Een nieuwe regel **maken**.

3. Geef een naam voor de regel op.

4. Kies **Meer opties**en geef vervolgens onder Deze regel toepassen **als**u een voorwaarde opgeeft die de actie activeert die u voor deze regel instelt (namelijk het instellen van de SCL-waarde).

   U bijvoorbeeld de **afzender** \> **intern/extern**instellen en vervolgens in het dialoogvenster **Afzenderlocatie selecteren** binnen de **organisatie**selecteren en **ok**kiezen.<br/>
   ![Afzenderlocatie selecteren](../../media/EOP-ETR-SetSCL-1.jpg)

5. Selecteer onder **Ga als volgt**de optie De \> eigenschappen van het bericht **wijzigen** **en stel het betrouwbaarheidsniveau voor spam (SCL)** in .

6. Selecteer in het vak **SCL opgeven** een van de volgende waarden en kies **OK:**

   - **Bypass spam filtering**: Hiermee wordt de SCL ingesteld op -1, wat betekent dat contentfiltering niet wordt uitgevoerd.

   - **0-4**: Het bericht wordt doorgegeven aan het inhoudsfilter voor extra verwerking.

   - **5-6**: De actie die voor **spam** is opgegeven in het toepasselijke beleid voor inhoudsfilter wordt toegepast. Standaard is de actie om het bericht naar de map Ongewenste e-mail van de ontvanger te verzenden.

   - **7-9**: De actie die is opgegeven voor **spam met een hoog vertrouwen** in het toepasselijke beleid voor inhoudsfilter, wordt toegepast. Standaard is de actie om het bericht naar de map Ongewenste e-mail van de ontvanger te verzenden.

   Zie Uw beleid voor spamfilters configureren voor meer informatie over het configureren van uw beleid voor [inhoudsfilters.](configure-your-spam-filter-policies.md) Zie [Vertrouwensniveaus](spam-confidence-levels.md)voor spam voor meer informatie over SCL-waarden in de service.

7. Geef extra eigenschappen voor de regel op en kies **opslaan**.

   > [!TIP]
   > Zie De EAC gebruiken om regels voor [e-mailstroom te maken voor](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules)meer informatie over de extra eigenschappen die u voor deze regel selecteren of opgeven.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of deze procedure correct werkt, stuurt u een e-mailbericht naar iemand binnen uw organisatie en controleert u of de actie die op het bericht is uitgevoerd, zoals verwacht. Als u bijvoorbeeld **het spamvertrouwensniveau (SCL) instelt op** **spamfiltering omzeilen,** moet het bericht naar het postvak in van de opgegeven ontvanger worden verzonden. Als u echter **het spamvertrouwensniveau (SCL) instelt op** **9**, en de **spamactie met veel vertrouwen** voor uw toepasselijke beleid voor inhoudsfilter is om het bericht naar de map Ongewenste e-mail te verplaatsen, moet het bericht worden verzonden naar de map Ongewenste e-mail van de opgegeven ontvanger.
