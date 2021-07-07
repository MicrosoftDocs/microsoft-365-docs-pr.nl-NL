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
ms.openlocfilehash: f09d1f51ed8a868712c22fbd7a641b35f5d29073
ms.sourcegitcommit: b6e63febe24ef1f1793dfb3ecc5ed41a4e730578
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/06/2021
ms.locfileid: "53309344"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Planner instellen voor Microsoft 365


Als u de Scheduler voor Microsoft 365 wilt instellen, volgt u de volgende vereisten:

|**Wat heb ik nodig?** |**Beschrijving** |
|-------------------|-------------|
|Cortana postvak |Tenantbeheerders moeten een postvak instellen als het postvak 'Cortana' (dat wil zeggen, cortana@yourdomain.com).         |
|Exchange Online postvak |Gebruikers moeten een e-Exchange Online en agenda hebben         |
|Scheduler-licentie |Zie [Scheduler](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing)voor Microsoft 365.        |

## <a name="create-a-mailbox-for-cortana"></a>Een postvak maken voor Cortana
Een Exchange postvak in uw tenant fungeert als het Cortana voor uw tenant om e-mailberichten te verzenden en te ontvangen van en naar Cortana. Alle e-mailberichten die naar Cortana worden bewaard in het postvak van uw tenant Cortana op basis van uw bewaarbeleid.

- Gebruik de Microsoft 365-beheercentrum om een gebruikerspostvak te maken. Een bewaarbeleid van 30 dagen wordt aanbevolen. 
- Gebruik de naam Cortana in het primaire SMTP-adres van uw postvak. Namen zoals 'Cortana@yourdomain.com', 'CortanaScheduler@contoso.com', of 'Cortana. Scheduler@yourdomain.com' wordt aanbevolen.

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>Het postvak aanwijzen als planningsassistent

Nadat er een uniek postvak Cortana Scheduler is gemaakt, moet u het postvak aanwijzen om formeel Microsoft 365 maken. Nadat u het postvak Cortana scheduler hebt aangewezen, is het beschikbaar om vergaderingen namens uw gebruikers te plannen.

Als u het postvak Cortana scheduler wilt aanwijzen, moet een geautoriseerde beheerder een powershell-opdracht met één regel uitvoeren. 

1. Verbinding maken om Microsoft 365 externe PowerShell-ruimte voor uw organisatie uit te voeren.
2. Voer het volgende PowerShell-script uit om het postvak voor Scheduler aan te wijzen:

```powershell

Set-mailbox cortana@contoso.com -SchedulerAssistant:$true

```

Nadat u deze opdracht 'set' hebt uitgevoerd in het Cortana Scheduler-postvak, wordt er een nieuwe 'PersistedCapability' ingesteld op het postvak om te zien dat dit postvak het 'SchedulerAssistant' is.

> [!NOTE]
> Volg deze stappen om uw organisatie te verbinden met PowerShell als u dit nog niet eerder hebt gedaan: Verbinding maken Microsoft 365 [PowerShell - Microsoft 365 Enterprise | Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)

Als u wilt weten welk postvak in uw organisatie momenteel is ingesteld als de Cortana planningsassistent, kunt u de functie Get uitvoeren:
 
```powershell

Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}

```

> [!IMPORTANT]
> Het kan maximaal twee uur duren voordat het Postvak Scheduler volledig is ingericht om de schedulerAssistant-functie in te stellen.

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
> **Scheduler voor Microsoft 365** is momenteel beschikbaar voor wereldwijde multitenten, alleen in het Engels.</br>
>
>Het is niet beschikbaar voor gebruikers van Office 365 beheerd door 21Vianet in China of gebruikers van Microsoft 365 met de Duitse cloud die gebruikmaakt van de Data Trustee German Telekom. Deze wordt ondersteund voor gebruikers in Duitsland waarvan de gegevenslocatie zich niet in het Duitse datacenter bevindt.
>
>Deze functie wordt ook niet ondersteund voor gebruikers van de Government Cloud, zoals GCC, Consumer, GCC High of DoD.
