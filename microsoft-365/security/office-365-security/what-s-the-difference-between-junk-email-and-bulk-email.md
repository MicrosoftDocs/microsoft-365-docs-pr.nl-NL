---
title: Wat &apos; is het verschil tussen ongewenste e-mail en bulk e-mail?
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
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer te weten komen over de verschillen tussen ongewenste e-mail (spam) en bulke-mail (grijze e-mail) in Exchange Online Protection (EOP).
ms.openlocfilehash: c1f5ca724f7a41d9fc11ed0c93f52a79a6ecc8e5
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819434"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>Wat is het verschil tussen ongewenste e-mail en bulke-mail in EOP?

In Microsoft 365-organisaties met mailboxen in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken vragen klanten soms: "wat is het verschil tussen ongewenste e-mail en bulke-mail?" In dit onderwerp wordt het verschil uitgelegd en worden de besturingselementen beschreven die beschikbaar zijn in EOP.

- **Ongewenste e-mail** is spam, die ongevraagde en universeel ongewenste berichten (wanneer correct geïdentificeerd). Standaard weigert de EOP spam op basis van de reputatie van de brone-mailserver. Als een bericht de IP-inspectie van de bron doorgeeft, wordt het verzonden naar spamfiltering. Als het bericht wordt geclassificeerd als spam door spamfiltering, wordt het bericht (standaard) aan de beoogde ontvangers bezorgd en verplaatst naar hun map Ongewenste e-mail.

  - U de acties configureren die moeten worden uitgevoerd op het filteren van spam. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)voor instructies.

  - Als u het niet eens bent met het vonnis voor spamfilters, u berichten die u als spam of niet-spam beschouwt, op verschillende manieren aan Microsoft rapporteren, zoals beschreven in [Berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

- **Bulk e-mail** (ook bekend als _grijze e-mail),_ is moeilijker te classificeren. Terwijl spam is een constante bedreiging, bulk e-mail is vaak eenmalige advertenties of marketing berichten. Sommige gebruikers willen bulk e-mailberichten (en in feite hebben ze zich bewust aangemeld om ze te ontvangen), terwijl andere gebruikers bulk e-mail beschouwen als spam. Sommige gebruikers willen bijvoorbeeld advertentieberichten ontvangen van de Contoso Corporation of uitnodigingen voor een komende conferentie over cyberbeveiliging, terwijl andere gebruikers deze zelfde berichten als spam beschouwen.

  Zie [Bulkklachtenniveau (BCL) in EOP](bulk-complaint-level-values.md)voor meer informatie over de manier waarop bulke-mail wordt geïdentificeerd.

## <a name="how-to-manage-bulk-email"></a>Bulke-mail beheren

Vanwege de gemengde reactie op bulk e-mail, is er geen universele begeleiding die van toepassing is op elke organisatie.

Anti-spam politie heeft een standaard BCL drempel die wordt gebruikt om bulk e-mail te identificeren als spam. Beheerders kunnen de drempelwaarde verhogen of verlagen. Lees de volgende onderwerpen voor meer informatie:

- [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md).

- [Instellingen voor eOP-antispambeleid](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

Een andere optie die gemakkelijk over het hoofd te zien is: als een gebruiker klaagt over het ontvangen van bulke-mail, maar de berichten zijn van gerenommeerde afzenders die spamfiltering doorgeven in EOP, laat de gebruiker controleren op een afmeldoptie in het bulke-mailbericht.
