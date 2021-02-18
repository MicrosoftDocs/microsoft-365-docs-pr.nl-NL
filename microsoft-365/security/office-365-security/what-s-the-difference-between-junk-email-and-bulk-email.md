---
title: Wat &apos; is het verschil tussen ongewenste e-mail en bulk-e-mail?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen de verschillen tussen ongewenste e-mail (spam) en bulkmail (grijze e-mail) in Exchange Online Protection (EOP) leren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c656ed1807b451ae03ecfeb0f220f5d7b902c7ac
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290643"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>Wat is het verschil tussen ongewenste e-mail en bulkmail in EOP?

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken vragen klanten soms: 'Wat is het verschil tussen ongewenste e-mail en bulk-e-mail?' In dit onderwerp wordt het verschil beschreven en worden de besturingselementen beschreven die beschikbaar zijn in EOP.

- **Ongewenste e-mail** is spam, ongevraagde en universeel ongewenste berichten (indien correct geïdentificeerd). Standaard wijst de EOP spam af op basis van de reputatie van de bron-e-mailserver. Als een bericht de bron-IP-controle doorstaat, wordt het verzonden naar spamfilters. Als het bericht door spamfilters als spam wordt geclassificeerd, wordt het bericht (standaard) bezorgd bij de geadresseerden en verplaatst naar de map Ongewenste e-mail.

  - U kunt de acties zodanig configureren dat ze worden genomen op spamfilters. Zie Antispambeleid configureren [in EOP voor instructies.](configure-your-spam-filter-policies.md)

  - Als u het niet eens bent met het spamfilter, kunt u berichten die volgens u spam of niet-spam zijn, op verschillende manieren aan Microsoft rapporteren, zoals wordt beschreven in Berichten en bestanden rapporteren [aan Microsoft.](report-junk-email-messages-to-microsoft.md)

- **Bulk-e-mail** (ook _wel grijze e-mail genoemd)_ is moeilijker te classificeren. Terwijl spam een constante bedreiging is, is bulk-e-mail vaak een eentijdsadvertenties of marketingberichten. Sommige gebruikers willen bulk-e-mailberichten (en in feite hebben ze zich opzettelijk aangemeld om ze te ontvangen), terwijl andere gebruikers van mening zijn dat bulk-e-mail spam is. Sommige gebruikers willen bijvoorbeeld reclameberichten ontvangen van contoso Corporation of uitnodigingen voor een komende conferentie over cyberbeveiliging, terwijl andere gebruikers deze berichten als spam beschouwen.

  Zie Bulk-klachtniveau [(BCL) in EOP voor](bulk-complaint-level-values.md)meer informatie over hoe bulk-e-mail wordt geïdentificeerd.

## <a name="how-to-manage-bulk-email"></a>Bulk-e-mail beheren

Vanwege een gemengde reactie op bulkmail is er geen universele leidraad die van toepassing is op elke organisatie.

Antispam beleid heeft een standaard drempelwaarde voor BCL die wordt gebruikt om bulk-e-mail als spam aan te identificeren. Beheerders kunnen de drempelwaarde verhogen of verlagen. Zie de volgende onderwerpen voor meer informatie:

- [Antispambeleid configureren in EOP.](configure-your-spam-filter-policies.md)

- [Instellingen voor antispambeleid van EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

Een andere optie die u gemakkelijk kunt over het hoofd zien: als een gebruiker over het ontvangen van bulk-e-mail klaagt, maar de berichten afkomstig zijn van betrouwbare afzenders die spamfilters in EOP gebruiken, laat u de gebruiker controleren op een optie voor het afmelden in het bulk-e-mailbericht.
