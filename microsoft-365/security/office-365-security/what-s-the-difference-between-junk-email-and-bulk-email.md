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
description: Beheerders kunnen meer informatie krijgen over de verschillen tussen ongewenste e-mail (spam) en bulk-e-mail (grijze e-mail) in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fc9c94946c3da2f9a14f45070a86c557a5c7dc85
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204937"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>Wat is het verschil tussen ongewenste e-mail en bulk-e-mail in EOP?

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, vragen klanten soms: 'Wat is het verschil tussen ongewenste e-mail en bulk-e-mail?' In dit onderwerp wordt het verschil uitgelegd en worden de besturingselementen beschreven die beschikbaar zijn in EOP.

- **Ongewenste e-mail** is spam, wat ongevraagde en universeel ongewenste berichten zijn (indien correct geïdentificeerd). Standaard wordt spam door de EOP afgewezen op basis van de reputatie van de bron-e-mailserver. Als een bericht de bron-IP-inspectie doorstaat, wordt het verzonden naar spamfilters. Als het bericht is geclassificeerd als spam door spamfilters, wordt het bericht (standaard) bezorgd bij de beoogde geadresseerden en verplaatst naar de map Ongewenste e-mail.

  - U kunt de acties configureren voor het filteren van spam. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)voor instructies.

  - Als u het niet eens bent met de uitspraak over spamfilters, kunt u berichten die u als spam of niet-spam beschouwt op verschillende manieren aan Microsoft rapporteren, zoals beschreven in Berichten en bestanden rapporteren aan [Microsoft.](report-junk-email-messages-to-microsoft.md)

- **Bulk-e-mail** (ook _wel grijze e-mail genoemd)_ is moeilijker te classificeren. Terwijl spam een constante bedreiging is, is bulk-e-mail vaak een een-tijdsadvertenties of marketingberichten. Sommige gebruikers willen bulk-e-mailberichten (en in feite hebben ze zich bewust aangemeld om ze te ontvangen), terwijl andere gebruikers bulk-e-mail beschouwen als spam. Sommige gebruikers willen bijvoorbeeld reclameberichten ontvangen van de Contoso Corporation of uitnodigingen voor een aanstaande conferentie over cyberbeveiliging, terwijl andere gebruikers deze berichten beschouwen als spam.

  Zie Bulk [complaint level (BCL) in EOP voor](bulk-complaint-level-values.md)meer informatie over de manier waarop bulk-e-mail wordt geïdentificeerd.

## <a name="how-to-manage-bulk-email"></a>Bulk-e-mail beheren

Vanwege de gemengde reactie op bulk-e-mail is er geen universele richtlijn die van toepassing is op elke organisatie.

Antispam polices hebben een standaard BCL-drempel die wordt gebruikt om bulk-e-mail te identificeren als spam. Beheerders kunnen de drempel verhogen of verlagen. Zie de volgende onderwerpen voor meer informatie:

- [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md).

- [EOP-antispambeleidsinstellingen](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

Een andere optie die u gemakkelijk kunt over het hoofd zien: als een gebruiker klaagt over het ontvangen van bulk-e-mail, maar de berichten afkomstig zijn van betrouwbare afzenders die spamfilters in EOP doorgeven, laat u de gebruiker controleren op een optie voor afmelden in het bulksgewijs e-mailbericht.
