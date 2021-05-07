---
title: TLS 1.0 en 1.1 uitschakelen in Microsoft 365 GCC Hoog en DoD
description: Bespreekt hoe Microsoft ondersteuning voor TLS 1.1 en 1.0 in GCC High- en DoD-omgevingen in Microsoft 365.
author: kccross
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: 16a02985107c5f578d6d6c21bf2efc6e80297951
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161963"
---
# <a name="disabling-tls-10-and-11-in-microsoft-365-gcc-high-and-dod"></a>TLS 1.0 en 1.1 uitschakelen in Microsoft 365 GCC Hoog en DoD

## <a name="summary"></a>Samenvatting

Om te voldoen aan de meest recente nalevingsstandaarden voor het Federal Risk and Authorization Management Program (FedRAMP), worden de TLS-versies (Transport Layer Security) 1.1 en 1.0 in Microsoft 365 voor GCC High- en DoD-omgevingen uitschakelen. Deze wijziging is eerder aangekondigd via Microsoft Ondersteuning bij Het voorbereiden van het verplichte gebruik van [TLS 1.2 in Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)

De beveiliging van uw gegevens is belangrijk en we willen transparantie over wijzigingen die van invloed kunnen zijn op uw gebruik van de service.

Hoewel de [Implementatie van Microsoft TLS 1.0](https://support.microsoft.com/help/3117336) geen bekende beveiligingsproblemen heeft, blijven we ons houden aan de nalevingsstandaarden van FedRAMP. Daarom hebben we TLS 1.1 en 1.0 uitgeschakeld in Microsoft 365 in GCC High- en DoD-omgevingen op 15 januari 2020. Zie de volgende whitepaper voor informatie over het verwijderen van TLS 1.1- en 1.0-afhankelijkheden:

[Het TLS 1.0-probleem oplossen](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a>Meer informatie

Vanaf 15 januari 2020 worden Microsoft 365 TLS 1.1 en 1.0 uitgeschakeld in de GCC High- en DoD-omgevingen.

Op 15 januari 2020 moeten alle combinaties van clientservers en browserservers gebruik maken van TLS-versie 1.2 (of een latere versie) om ervoor te zorgen dat alle verbindingen kunnen worden gemaakt zonder problemen met Microsoft 365. Hiervoor zijn mogelijk updates nodig voor bepaalde combinaties van clientservers en browserservers.

Voor SharePoint en OneDrive moet u .NET bijwerken en configureren om TLS 1.2 te ondersteunen. Zie [TLS 1.2 inschakelen](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)op clients voor meer informatie.

U moet uw clientcomputers bijwerken om ervoor te zorgen dat u ononderbroken toegang hebt tot Office 365 GCC High en DoD.

U moet toepassingen bijwerken die via TLS 1.0 Microsoft 365 TLS 1.1 of TLS 1.1 bellen om TLS 1.2 te gebruiken. .NET 4.5 is standaard ingesteld op TLS 1.1. Zie Transport Layer Security [(TLS) 1.2](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)op clients inschakelen als u uw .NET-configuratie wilt bijwerken. Zie Voorbereiden op het verplichte gebruik van [TLS 1.2 in](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)Office 365.

We weten dat in de volgende clienttoepassingen TLS 1.2 niet kan worden gebruikt:

- Android 4.3 en eerdere versies
- Firefox versie 5.0 en eerdere versies
- Internet Explorer 8–10 op Windows 7 en eerdere versies
- Internet Explorer 10 op Windows Phone 8.0
- Safari 6.0.4/OS X 10.8.4 en eerdere versies

Hoewel uit de huidige analyse van verbindingen met Microsoft Online-services blijkt dat de meeste services en eindpunten zeer weinig TLS 1.1- en 1.0-gebruik zien, geven we deze wijziging door, zodat u alle getroffen clients of servers zo nodig kunt bijwerken voordat de ondersteuning voor TLS 1.1 en 1.0 eindigt. Als u een on-premises infrastructuur gebruikt voor hybride scenario's of Active Directory Federation Services (AD FS), moet u ervoor zorgen dat de infrastructuur zowel binnenkomende als uitgaande verbindingen ondersteunt die gebruikmaken van TLS 1.2 (of een latere versie).

Naast de uitval die u mogelijk ervaart als u de vermelde clients gebruikt die TLS 1.2 niet kunnen gebruiken, voorkomt u dat u het volgende Microsoft-product kunt gebruiken door TLS 1.1 en 1.0 te verwijderen:

- Lync-telefoon

## <a name="references"></a>Verwijzingen

Zie Voorbereiden op het verplichte gebruik van [TLS 1.2 in](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)Office 365 voor richtlijnen en verwijzingen om ervoor te zorgen dat uw klanten TLS 1.2 gebruiken.