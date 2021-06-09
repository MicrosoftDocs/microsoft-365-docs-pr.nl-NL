---
title: Problemen met basismobiliteit en beveiliging oplossen
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Probeer deze stappen om problemen met basismobiliteit en beveiliging op te sporen
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876850"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>Problemen met basismobiliteit en beveiliging oplossen

Als u problemen hebt wanneer u probeert een apparaat in te schrijven in Basismobiliteit en Beveiliging, probeert u de stappen hier om het probleem op te sporen. Als het probleem niet wordt opgelost met de algemene stappen, bekijkt u een van de latere secties met specifieke stappen voor uw apparaattype.

## <a name="steps-to-try-first"></a>Stappen om het eerst te proberen

Ga als volgt te werk om te beginnen:

- Zorg ervoor dat het apparaat nog niet is geregistreerd bij een andere provider voor mobiel apparaatbeheer, zoals Intune.

- Zorg ervoor dat het apparaat is ingesteld op de juiste datum en tijd.

- Schakel over naar een ander WIFI- of mobiel netwerk op het apparaat.

- Voor Android- of iOS-apparaten verwijdert en installeert u de Intune-bedrijfsportal app op het apparaat. 

## <a name="ios-phone-or-tablet"></a>iOS-telefoon of -tablet

- Zorg ervoor dat u een APN-certificaat hebt ingesteld. Zie Een APN-certificaat maken voor [iOS-apparaten](create-an-apns-certificate-for-ios-devices.md)voor meer informatie.

- In **Instellingen**   >  **Algemeen**   >  **profiel (of Apparaatbeheer)** moet u ervoor zorgen dat een beheerprofiel nog niet is geïnstalleerd. Als dit het is, verwijdert u het.

- Als u het foutbericht 'Apparaat kan zich niet registreren' ziet, meld u zich aan bij Microsoft 365 en zorg er dan voor dat er een licentie met Exchange Online is toegewezen aan de gebruiker die is aangemeld bij het apparaat.

- Als u het foutbericht 'Profiel is niet geïnstalleerd' ziet, probeert u een van de volgende opties:

    - Zorg ervoor dat Safari de standaardbrowser op het apparaat is en dat cookies niet zijn uitgeschakeld.

    - Start het apparaat opnieuw op en navigeer naar portal.manage.microsoft.com. Meld u aan met uw Microsoft 365 en wachtwoord en probeer het profiel handmatig te installeren.

## <a name="windows-rt"></a>Windows RT

- Zorg ervoor dat uw domein is ingesteld in Microsoft 365 om te werken met Basismobiliteit en Beveiliging. Zie Basismobiliteit en beveiliging instellen voor [meer informatie.](set-up.md)
    
- Zorg ervoor dat de gebruiker **In-aan** kiest   in plaats van **Deelnemen.**

## <a name="windows-10-pc"></a>Windows 10 Pc

- Zorg ervoor dat uw domein is ingesteld in Microsoft 365 om te werken met Basismobiliteit en Beveiliging. Zie Basismobiliteit en beveiliging instellen voor [meer informatie.](set-up.md)
    
- Tenzij u Azure Active Directory Premium hebt, moet u ervoor zorgen dat de gebruiker Alleen registreren **voor Apparaatbeheer** kiest in plaats van dat   u Verbinding maken. ****

## <a name="android-phone-or-tablet"></a>Android-telefoon of -tablet

- Zorg ervoor dat het apparaat Android 4.4 of hoger gebruikt.

- Zorg ervoor dat Chrome up-to-date is en is ingesteld als de standaardbrowser.

- Als u het foutbericht 'We kunnen dit apparaat niet registreren' ziet, meld u dan aan bij Microsoft 365 en zorg ervoor dat er een licentie met Exchange Online is toegewezen aan de gebruiker die is aangemeld bij het apparaat.

- Controleer het systeemsysteemgebied op het apparaat om te zien of er vereiste acties van eindgebruikers in behandeling zijn en als dat het geval is, voltooit u de acties.