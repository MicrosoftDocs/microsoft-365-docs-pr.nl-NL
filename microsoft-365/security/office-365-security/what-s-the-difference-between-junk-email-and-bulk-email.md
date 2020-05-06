---
title: Wat is het verschil tussen ongewenste e-mail en bulkmail?
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
description: Meer informatie over het verschil tussen ongewenste & bulke-mail. Lees ook over verschillende opties die beschikbaar zijn in Exchange Online & Exchange Online Protection (EOP).
ms.openlocfilehash: 5d9d3b513de64d2a150d9e0a1c94bc5ca746b617
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036594"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>Wat is het verschil tussen ongewenste e-mail en bulkmail?

Microsoft 365-klanten met postvakken in Exchange Online- of zelfstandige Exchange Online Protection (EOP)-klanten zonder Exchange Online-postvakken vragen soms: "wat is het verschil tussen ongewenste e-mail en bulke-mail?" In dit onderwerp wordt het verschil uitgelegd en worden de besturingselementen beschreven die beschikbaar zijn in EOP.

- **Ongewenste e-mail** is spam, die ongevraagde en universeel ongewenste berichten (wanneer correct geïdentificeerd). Standaard wijst de EOP spam af op basis van de reputatie van de bron-e-mailserver. Als een bericht de IP-inspectie van de bron doorgeeft, wordt het verzonden naar spamfiltering. Als het bericht wordt geclassificeerd als spam door spamfiltering, wordt het bericht (standaard) geleverd aan de beoogde ontvangers en verplaatst naar de map Ongewenste e-mail.

  - U de acties configureren die u wilt uitvoeren op spamfilteringsvonnissen. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)voor instructies.

  - Als u het niet eens bent met het spamfiltervonnis, u berichten die u als spam of niet-spam beschouwt op verschillende manieren aan Microsoft rapporteren, zoals beschreven in [Berichten en bestanden rapporteren aan Microsoft.](report-junk-email-messages-to-microsoft.md)

- **Bulk e-mail** (ook wel bekend als _grijze e-mail),_ is moeilijker te classificeren. Terwijl spam is een constante bedreiging, bulk e-mail is vaak eenmalige advertenties of marketing berichten. Sommige gebruikers willen bulk e-mailberichten (en in feite, ze hebben bewust aangemeld om ze te ontvangen), terwijl andere gebruikers overwegen bulk e-mail te zijn spam. Sommige gebruikers willen bijvoorbeeld advertentieberichten ontvangen van de Contoso Corporation of uitnodigingen voor een komende conferentie over cyberbeveiliging, terwijl andere gebruikers dezelfde berichten als spam beschouwen.

  Zie [Bulkklachtenniveau (BCL) in Office 365 voor](bulk-complaint-level-values.md)meer informatie over de manier waarop bulke-mail wordt geïdentificeerd.

## <a name="how-to-manage-bulk-email"></a>Bulke-mail beheren

Vanwege de gemengde reactie op bulk e-mail, is er geen universele begeleiding die van toepassing is op elke organisatie.

Anti-spam politie heeft een standaard BCL drempel die wordt gebruikt om bulk e-mail te identificeren als spam. Beheerders kunnen de drempelwaarde verhogen of verlagen. Lees de volgende onderwerpen voor meer informatie:

- [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md).

- [EOP-beleidsinstellingen voor spam](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

Een andere optie die gemakkelijk over het hoofd te zien: als een gebruiker klaagt over het ontvangen van bulk e-mail, maar de berichten zijn van gerenommeerde afzenders die spam filtering passeren in EOP, hebben de gebruiker controleren op een uitschrijven optie in de bulk e-mailbericht.
