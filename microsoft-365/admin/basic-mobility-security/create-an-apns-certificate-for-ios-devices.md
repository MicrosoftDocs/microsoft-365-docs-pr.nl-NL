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
description: IOS-apparaten beheren in eenvoudige mobiliteit en beveiliging.
ms.openlocfilehash: 85baef2defa79255d560f848e57120353fd4fa2e
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877078"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>Een APNs-certificaat voor iOS-apparaten maken

Als u iOS-apparaten zoals iPads en iPhones wilt beheren in basis mobiliteit en beveiliging, maakt u een APNs-certificaat.

1. Meld u aan bij Microsoft 365 met uw globale beheerdersaccount.

2. Typ in uw browser  [https://protection.office.com](https://protection.office.com/) .

3. Selecteer  **preventie van gegevensverlies**   > in  **Apparaatbeheer** en kies **APNs-certificaat voor IOS-apparaten**.

4. Kies **volgende** op de pagina Apple Push Notification Certificate Settings.

5. Selecteer Download Your CSR file en sla de aanvraag voor certificaatondertekening op uw computer op een locatie op die u kunt onthouden. Selecteer  **volgende**.

6. Op de pagina Create a APNs Certificate:  

    1. Selecteer Apple APNS-Portal om de Apple Push Certificate-portal te openen.

    2. Meld u aan met een Apple-ID.

    >[!IMPORTANT]
    >Gebruik een netwerkapple-ID die is gekoppeld aan een e-mailaccount dat bij uw organisatie hoort, zelfs als de gebruiker die het account beheert de account blad houdt. Sla deze ID op omdat u de ID van het certificaat moet verlengen wanneer u dit tijdstip moet gebruiken.

    3. Selecteer  **een certificaat maken**   en accepteer de gebruiksvoorwaarden.

    4. Blader naar de aanvraag voor certificaatondertekening die u naar uw computer hebt gedownload vanuit Microsoft 365 en selecteer **uploaden**.

        Download het APNs-certificaat dat met de Apple Push Certificate-Portal is gemaakt naar uw computer.

       >[!TIP]
       >Als u problemen ondervindt bij het downloaden van het certificaat, vernieuwt u de browser.

7. Ga terug naar Microsoft 365 en selecteer **volgende**   om naar de pagina   **Upload APNS Certificate** te gaan   .

8. Blader naar het APN-certificaat dat u hebt gedownload van de Apple Push Certificate-Portal.

9. Selecteer  **Voltooien**.

Om de installatie te voltooien, gaat u terug naar het beveiligings  ****& compliance >  >  **beleids**   >  **instellingen** voor het beheren van beveiligingsbeleidsregels.
