---
title: Wat is &apos; het verschil tussen ongewenste e-mail en bulk-e-mail?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie vinden over de verschillen tussen ongewenste e-mail (spam) en bulk-e-mail (grijze e-mail) in Exchange Online Protection (EOP).
ms.openlocfilehash: 17e6223175013678f389c0d7624cc4e4f4476f98
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826727"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>Wat is het verschil tussen ongewenste e-mail en bulk-e-mail in EOP?

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken kunnen klanten soms het volgende vragen: ' wat is het verschil tussen ongewenste e-mail en bulk-e-mail? '. In dit onderwerp wordt het verschil uitgelegd en worden de beschikbare besturingselementen beschreven in EOP.

- **Ongewenste e-mail** is spam, ongevraagd en universeel ongewenst berichten (bij een juiste identificatie). In de EOP worden de spam standaard genegeerd op basis van de reputatie van de bron-e-mailserver. Als het bericht wordt gecontroleerd via bron-IP-inspectie, wordt het verzonden naar spam filteren. Als het bericht is geclassificeerd als spam via spamfilters, wordt het bericht (standaard) bezorgd bij de geadresseerden en verplaatst naar de map Ongewenste E-mail.

  - U kunt de acties configureren die u moet uitvoeren om spam te filteren Verdicts. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)voor instructies.

  - Als u niet akkoord gaat met de spamfilter Verdict, kunt u op verschillende manieren berichten rapporteren die u beschouwt als spam of niet-spam voor Microsoft, zoals beschreven in [berichten en bestanden aan Microsoft rapporteren](report-junk-email-messages-to-microsoft.md).

- **Bulk-e-mail** (ook wel _grijze e-mail_genoemd), is moeilijker te classificeren. Aangezien spam een voortdurende bedreiging vormt, is bulksgewijs e-mailberichten vaak eenmalige advertenties of marketingberichten. Sommige gebruikers willen bulksgewijs e-mailberichten (en in werkelijkheid hebben ze aangemeld om ze te ontvangen), terwijl andere gebruikers op de hoogte zijn van ongewenste e-mail. Sommige gebruikers willen bijvoorbeeld advertenties van de Contoso Corporation of uitnodigingen ontvangen voor een toekomstige conferentie over de Cyber-veiligheid, terwijl andere gebruikers deze berichten als spam beschouwen.

  Zie voor meer informatie over de manier waarop bulk-e-mail wordt geïdentificeerd de [bulk klachten niveau (BCL) in EOP](bulk-complaint-level-values.md).

## <a name="how-to-manage-bulk-email"></a>Bulk-e-mail beheren

Aangezien de gemengde reacties op bulk e-mail niet, is er geen universele richtlijnen die van toepassing zijn op elke organisatie.

Anti spam policies hebben een standaard BCL-drempel die wordt gebruikt voor het identificeren van bulk e-mail als spam. Beheerders kunnen de drempelwaarden vergroten of verkleinen. Zie de volgende onderwerpen voor meer informatie:

- [Antispambeleid te configureren in EOP](configure-your-spam-filter-policies.md).

- [EOP antispam beleidsinstellingen](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

Een andere optie die gemakkelijk te laat overlopen: als een gebruiker een bericht geeft over het ontvangen van bulk-e-mail, maar de berichten afkomstig zijn van goede afzenders die het filteren op ongewenste e-mail doorgeven in EOP, kunt u de gebruiker controleren op een optie voor het afmelden van het e-mailbericht.
