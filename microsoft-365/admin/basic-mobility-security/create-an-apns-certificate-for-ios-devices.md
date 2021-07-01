---
title: Een APNs-certificaat voor iOS-apparaten maken
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
description: IOS-apparaten beheren in Basismobiliteit en Beveiliging.
ms.openlocfilehash: 84f3589593ef26325397f5b6e90d5b21662d2352
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228241"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>Een APNs-certificaat voor iOS-apparaten maken

Als u iOS-apparaten, zoals iPads en iPhones in Basismobiliteit en Beveiliging, wilt beheren, maakt u een APN-certificaat.

1. Meld u aan bij Microsoft 365 met uw globale beheerdersaccount.

2. Typ in uw browser  <https://protection.office.com/> .

3. Selecteer  **Preventie van gegevensverlies**   >  **Apparaatbeheer** en kies **APN's-certificaat voor iOS-apparaten.**

4. Kies op de pagina Apple Push Notification Certificate Instellingen de optie **Volgende**.

5. Selecteer Uw MVO-bestand downloaden en sla het certificaat ondertekeningsverzoek op ergens op uw computer op dat u zich zult herinneren. Selecteer  **Volgende**.

6. Op de pagina Een APN-certificaat maken:

    1. Selecteer Apple APNS Portal om de Apple Push Certificates Portal te openen.

    2. Meld u aan met een Apple ID.

       > [!IMPORTANT]
       > Gebruik een Apple-id van het bedrijf die is gekoppeld aan een e-mailaccount dat bij uw organisatie blijft, zelfs als de gebruiker die het account beheert, weggaat. Sla deze id op omdat u dezelfde id moet gebruiken wanneer het tijd is om het certificaat te verlengen.

    3. Selecteer  **Een certificaat maken** en accepteer de   gebruiksvoorwaarden.

    4. Blader naar het certificaat ondertekeningsverzoek dat u hebt gedownload naar uw computer Microsoft 365 en selecteer **Upload.**

       Download het APN-certificaat dat is gemaakt door de Apple Push Certificate Portal naar uw computer.

       > [!TIP]
       > Als u problemen hebt met het downloaden van het certificaat, vernieuwt u de browser.

7. Ga terug naar Microsoft 365 en selecteer **Volgende** om naar de pagina Upload     **APNS-certificaat te**   gaan.

8. Blader naar het APN-certificaat dat u hebt gedownload van de Apple Push Certificates Portal.

9. Selecteer  **Voltooien**.

Als u de installatie wilt voltooien, gaat u terug naar het Beveiligings- & compliancecentrum > **Beveiligingsbeleid** Instellingen voor   >  ****   >  **apparaatbeheer beheren.**
