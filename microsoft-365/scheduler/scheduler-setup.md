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
ms.openlocfilehash: 924b25e3d921f402c97632f7475ed5beea98d5c7
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362544"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Planner instellen voor Microsoft 365


Als u de Scheduler voor Microsoft 365 wilt instellen, volgt u de volgende vereisten:

| Wat heb ik nodig? | Omschrijving |
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
> Volg deze stappen om uw organisatie te verbinden met PowerShell als u dit nog niet eerder hebt gedaan: Verbinding maken Microsoft 365 [powershell.](../enterprise/connect-to-microsoft-365-powershell.md)

Als u wilt weten welk postvak in uw organisatie momenteel is ingesteld als de Cortana planningsassistent, kunt u de functie Get uitvoeren:

```powershell
Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> Het kan maximaal twee uur duren voordat het Postvak Scheduler volledig is ingericht om de schedulerAssistant-functie in te stellen.

## <a name="exchange-online-mailbox"></a>Exchange Online postvak
Een Scheduler-licentie is een invoeging voor Microsoft 365 waarmee de organisator van de vergadering zijn taken voor het plannen van vergaderingen kan delegeren aan zijn planningsassistent. Voor het werken van de Scheduler, meestal via Microsoft 365 licentie, hebben organisatoren van de vergadering de volgende onderdelen nodig:

- Een postvak dat is aangewezen als postvak van de assistent scheduler
- Scheduler-licentie
- Exchange Online postvak en agenda

De deelnemers aan de vergadering hebben geen scheduler of Microsoft 365 nodig.

## <a name="scheduler-end-user-license-requirements"></a>Licentievereisten voor scheduler voor eindgebruikers

Voor een Scheduler-licentie is een van de volgende licenties vereist:

- Microsoft 365 E3, A3, E5, A5
- Business Basic, Business, Business Standard, Premium
- Office 365 E1, A1, E3, A3, E5, A5
- Business Essentials, Business Premium
- Exchange Online Abonnement 1- of Abonnement 2-licentie. 

> [!Note]

> Scheduler voor Microsoft 365 is alleen beschikbaar in wereldwijde omgevingen met meerdere tenants in het Engels. **Scheduler voor Microsoft 365** is niet beschikbaar voor gebruikers van:

- Microsoft 365 beheerd door 21Vianet in China
- Microsoft 365 duitse cloud die gebruikmaakt van de Data Trustee German Telekom
- Government cloud inclusief GCC, Consumer, GCC High of DoD

Scheduler ondersteunt gebruikers in Duitsland waarvan de gegevenslocatie zich niet in het Duitse datacenter bevindt.
