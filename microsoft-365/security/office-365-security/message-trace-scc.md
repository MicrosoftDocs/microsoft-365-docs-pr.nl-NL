---
title: Bericht traceren in de Microsoft 365 Defender portal
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen de koppeling Bericht traceren gebruiken in de Microsoft 365 Defender portal om erachter te komen wat er met berichten is gebeurd.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7b6f7b12086e46c6ad93b60e8c510ea533815a1
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108125"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a>Bericht traceren in de Microsoft 365 Defender portal

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Berichtspoor in de Microsoft 365 Defender portal volgt e-mailberichten terwijl ze door uw Exchange Online reizen. U kunt bepalen of een bericht is ontvangen, geweigerd, uitgesteld of bezorgd door de service. Ook wordt weergegeven welke acties zijn uitgevoerd op het bericht voordat het de uiteindelijke status heeft bereikt.

U kunt de informatie uit bericht traceren gebruiken om gebruikersvragen efficiënt te beantwoorden over wat er met berichten is gebeurd, problemen met de e-mailstroom op te lossen en beleidswijzigingen te valideren.

> [!NOTE]
> Berichtspoor in de Microsoft 365 Defender portal is slechts een doorspoort naar Bericht traceren in het Exchange beheercentrum. Zie Bericht traceren in het moderne Exchange [beheercentrum voor meer informatie.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet lid zijn van de rollengroepen **Organisatiebeheer,** **Compliancebeheer** of **Helpdesk** **in** Exchange Online om bericht traceren te gebruiken. Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.

  **Opmerkingen:** Lidmaatschap van de bijbehorende Azure Active Directory rol in de Microsoft 365-beheercentrum geeft  gebruikers de vereiste machtigingen en machtigingen voor andere functies in Microsoft 365. Raadpleeg [Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.

- Het maximum aantal berichten dat wordt weergegeven in de resultaten van een berichtspoor, is afhankelijk van het rapporttype dat u hebt geselecteerd (zie de sectie [Rapporttype](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) kiezen voor meer informatie). De [cmdlet Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) in Exchange Online PowerShell of zelfstandige EOP PowerShell retourneert alle berichten in de resultaten.

## <a name="open-message-trace"></a>Bericht traceren openen

Ga in Microsoft 365 Defender portal ( ) naar <https://security.microsoft.com> **E-mail & samenwerking** \> **Exchange bericht traceren.** Of als u rechtstreeks naar de pagina bericht traceren wilt gaan, gebruikt <https://admin.exchange.microsoft.com/#/messagetrace> u .

Op dit moment wordt berichtspoor in het EAC geopend. Zie Bericht traceren in het moderne Exchange [beheercentrum voor meer informatie.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)
