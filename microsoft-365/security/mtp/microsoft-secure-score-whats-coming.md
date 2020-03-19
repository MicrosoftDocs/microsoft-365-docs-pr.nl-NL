---
title: Wat komt er in Microsoft Secure Score?
description: Beschrijft Microsoft Secure Score in het Microsoft 365-beveiligingscentrum, hoe details worden berekend en wat beveiligingsbeheerders kunnen verwachten.
keywords: beveiliging, malware, Microsoft 365, M365, beveiligde score, beveiligingscentrum, verbeteracties
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: efb75f26d66258880c9defa94869f27e18685052
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42812884"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Wat komt er in Microsoft Secure Score?

Om van Microsoft Secure Score een betere vertegenwoordiger van uw beveiligingshouding te maken en de bruikbaarheid te verbeteren, voeren we in de nabije toekomst enkele wijzigingen door. Je score en de maximaal mogelijke score zullen veranderen. Dit impliceert echter geen verandering in uw beveiligingshouding.

Zie Nieuwe wijzigingen in Microsoft Secure Score voor meer informatie over recente [wijzigingen?](microsoft-secure-score.md#whats-new)

## <a name="march-16th-2020"></a>16 maart 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Verbeteringsacties verwijderen die niet voldoen aan de verwachtingen voor betrouwbare meting of geen nuttige weergave van beveiligingshouding bieden

Om ervoor te zorgen dat de Microsoft Secure Score zinvol is en dat elke verbeteringsactie meetbaar en betrouwbaar is, verwijderen we de volgende verbeteracties.

- Gebruikersdocumenten opslaan in OneDrive voor Bedrijven
- Office 365 ATP-beleid voor veilige bijlagen instellen
- Veilige koppelingen van Office 365 instellen om URL's te verifiëren
- Postvakdelegatie niet toestaan
- Anonieme koppelingen voor het delen van gasten toestaan voor sites en documenten
- Beveiligingsconsole voor cloudapps inschakelen
- Vervaldatum configureren voor koppelingen voor extern delen

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Ondersteuning voor beveiligingsstandaarden voor Azure AD-verbeteringsacties

Microsoft Secure Score werkt verbeteracties bij ter ondersteuning van [beveiligingsstandaarden in Azure AD,](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)waardoor het eenvoudiger wordt om uw organisatie te beschermen met vooraf geconfigureerde beveiligingsinstellingen voor veelvoorkomende aanvallen.

Het zal van invloed zijn op de volgende verbeteringsacties:

- Ervoor zorgen dat alle gebruikers meervoudige verificatie kunnen voltooien voor veilige toegang
- MFA vereisen voor administratieve rollen
- Beleid inschakelen om verouderde verificatie te blokkeren
