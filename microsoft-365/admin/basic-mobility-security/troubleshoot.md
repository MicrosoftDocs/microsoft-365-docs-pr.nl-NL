---
title: Problemen oplossen met eenvoudige mobiliteit en beveiliging
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
description: Voer de volgende stappen uit om eenvoudige problemen met mobiliteit en beveiliging op te sporen
ms.openlocfilehash: 43e7533e598f769dd5f2bcae28c4252f96a9be76
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430131"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>Problemen oplossen met eenvoudige mobiliteit en beveiliging

Als u problemen ondervindt wanneer u een apparaat wilt registreren bij basis mobiliteit en beveiliging, voert u deze stappen uit om het probleem op te lossen. Als het probleem niet is verholpen door de algemene stappen, raadpleegt u een van de volgende gedeelten met specifieke stappen voor uw apparaattype.

## <a name="steps-to-try-first"></a>Stappen om eerst te proberen

Controleer eerst het volgende:

- Controleer of het apparaat niet al is geregistreerd bij een andere provider voor mobiel Apparaatbeheer, zoals intune.
    
- Controleer of het apparaat is ingesteld op de juiste datum en tijd.
    
- Overschakelen naar een ander WIFI-of mobiel netwerk op het apparaat.
    
- Voor Android-of iOS-apparaten verwijdert u de app intune Company portal van het apparaat en installeert u deze opnieuw. 

## <a name="ios-phone-or-tablet"></a>iOS-telefoon of-Tablet

- Zorg ervoor dat u een APNs-certificaat hebt ingesteld. Zie [een APNs-certificaat voor IOS-apparaten maken](create-an-apns-certificate-for-ios-devices.md)voor meer informatie.
    
-  **Settings**   > Zorg dat in het algemeen profiel van de instelling **Algemeen**   >  **(of Apparaatbeheer)** een management profiel nog niet is geïnstalleerd. Als dat het geval is, verwijdert u het bestand.
    
- Als u het foutbericht "apparaat niet geregistreerd" ziet, meldt u zich aan bij Microsoft 365 en controleert u of een licentie voor Exchange Online is toegewezen aan de gebruiker die zich bij het apparaat heeft aangemeld.
    
- Als het volgende foutbericht wordt weergegeven: "profiel kan niet worden geïnstalleerd", kunt u een van de volgende oplossingen proberen:
    
    - Zorg ervoor dat Safari de standaardbrowser is op het apparaat en dat cookies niet zijn uitgeschakeld.
    
    - Start het apparaat opnieuw op en ga naar portal.manage.microsoft.com. Meld u aan met uw gebruikers-ID en wachtwoord voor Microsoft 365 en installeer het profiel handmatig.    

## <a name="windows-rt"></a>Windows RT

- Zorg ervoor dat uw domein is ingesteld in Microsoft 365, zodat dit werkt met basis mobiliteit en beveiliging. Zie [eenvoudige mobiliteit en beveiliging instellen](set-up.md)voor meer informatie.
    
- Zorg ervoor dat de gebruiker inschakelen kiest **Turn On**   in plaats van deel te **nemen**.    

## <a name="windows-10-pc"></a>PC met Windows 10

- Zorg ervoor dat uw domein is ingesteld in Microsoft 365, zodat dit werkt met basis mobiliteit en beveiliging. Zie [eenvoudige mobiliteit en beveiliging instellen](set-up.md)voor meer informatie.
    
- Tenzij u Azure Active Directory Premium hebt, moet u ervoor zorgen dat de gebruiker **alleen registreren in Apparaatbeheer**kiest in   plaats van **verbinding maken**te kiezen.

## <a name="android-phone-or-tablet"></a>Android-telefoon of-Tablet

- Controleer of op het apparaat Android 4,4 of hoger wordt uitgevoerd.
    
- Zorg dat chroom up-to-date is en is ingesteld als de standaardbrowser.
    
- Als u het foutbericht "dit apparaat kan niet worden geregistreerd" ziet, meldt u zich aan bij Microsoft 365 en controleert u of een licentie voor Exchange Online is toegewezen aan de gebruiker die zich bij het apparaat heeft aangemeld.
    
- Controleer het systeemvak op het apparaat om te zien of de vereiste taken voor eindgebruikers in behandeling zijn en of ze de acties kunnen voltooien.