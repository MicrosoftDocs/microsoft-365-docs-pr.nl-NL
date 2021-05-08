---
title: Scheduler instellen voor Microsoft 365.
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Scheduler instellen voor Microsoft 365.
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286154"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Scheduler instellen voor Microsoft 365

Als u de Scheduler voor Microsoft 365 wilt instellen, volgt u de volgende vereisten:

|**Wat heb ik nodig?** |**Beschrijving** |
|-------------------|-------------|
|Postvak van Cortana |Tenantbeheerders moeten een postvak instellen als het postvak 'Cortana' (dat wil zeggen, cortana@yourdomain.com).         |
|Exchange Online postvak |Gebruikers moeten een e-Exchange Online en agenda hebben         |
|Scheduler-licentie |Zie [Scheduler](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)voor Microsoft 365.        |

## <a name="create-a-mailbox-for-cortana"></a>Een postvak voor Cortana maken
Een Exchange postvak in uw tenant fungeert als het Cortana-postvak voor uw tenant om e-mailberichten te verzenden en te ontvangen van en naar Cortana. Alle e-mailberichten die naar Cortana worden verzonden, worden bewaard in het Cortana-postvak van uw tenant op basis van uw bewaarbeleid.

- Gebruik het Microsoft 365 beheercentrum om een nieuw postvak te maken. Een bewaarbeleid van 30 dagen wordt aanbevolen. Gebruik de naam Cortana in het primaire SMTP-adres van uw postvak. Namen zoals 'Cortana@yourdomain.com', 'CortanaScheduler@contoso.com' of 'Cortana.Scheduler@yourdomain.com' worden aanbevolen.
- Neem contact op met Microsoft (scheduler_m365@microsoft.com) om uw Cortana-postvak in te stellen. 

> [!IMPORTANT]
> Neem contact op met Microsoft om uw Cortana-postvak zo te configureren dat u de Scheduler-service kunt gebruiken door een e-mail scheduler_m365@microsoft.com. Het inschakelen van uw Cortana-postvak kan maximaal twee weken duren.

## <a name="exchange-online-mailbox"></a>Exchange Online postvak
Scheduler is een invoegvoegvoeging voor Microsoft 365. Organisatoren van vergadering moeten een postvak Exchange Online agenda hebben om Scheduler te laten werken.

## <a name="exchange-requirements"></a>Exchange-vereisten

Naast licentieplanning moet u een van de volgende licenties hebben:

- Microsoft 365 E3, A3, E5, A5
- Business Basic, Business, Business Standard, Premium
- Office 365 E1, A1, E3, A3, E5, A5
- Business Essentials, Business Premium
- Exchange Online Abonnement 1- of Abonnement 2-licentie. 

> [!Note]
> **Scheduler voor Microsoft 365** is niet beschikbaar voor gebruikers van Office 365 beheerd door 21Vianet in China. Het is ook niet beschikbaar voor gebruikers van Microsoft 365 met de Duitse cloud die gebruikmaakt van de Data Trustee German Telekom. Deze wordt ondersteund voor gebruikers in Duitsland waarvan de gegevenslocatie zich niet in het Duitse datacenter bevindt.
>
>Deze functie wordt ook niet ondersteund voor gebruikers van de Government Cloud, zoals GCC, Consumer, GCC High of DoD.
