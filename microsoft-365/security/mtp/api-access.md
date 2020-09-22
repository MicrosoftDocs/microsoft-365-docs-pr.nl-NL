---
title: Toegang tot de Microsoft Threat Protection-Api's
description: Lees hoe u toegang krijgt tot de Microsoft Threat Protection-Api's
keywords: Access, api's, toepassingscontext, gebruikerscontext, Aad-toepassing, toegangstoken
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bccf36f46121caceeb6dc6d97c126f48149d9426
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197879"
---
# <a name="access-the-microsoft-threat-protection-apis"></a>Toegang tot de Microsoft Threat Protection-Api's

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.


 Microsoft Threat Protection geeft veel van zijn gegevens en acties getoond via een set programmeer Api's. Met deze Api's kunt u werkstromen en innoveren automatiseren op basis van de mogelijkheden van Microsoft Threat Protection. Voor API-toegang is OAuth 2.0-authenticatie vereist. Voor meer informatie raadpleegt u [OAuth 2,0 Authorization code flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).


In het algemeen dient u de volgende stappen uit te voeren om de Api's te gebruiken:
- Een AAD-toepassing maken
- Een toegangstoken verkrijgen met deze toepassing
- Het token gebruiken om toegang te krijgen tot de Microsoft Threat Protection API


U kunt de Microsoft Threat Protection API met context van de **toepassing** of de **gebruikerscontext**openen.

- **Toepassings context: (aanbevolen)** <br>
    Dit wordt gebruikt door apps die zonder een aangemelde gebruiker worden uitgevoerd. apps die als achtergrondservice of demon worden uitgevoerd, bijvoorbeeld apps.

    Stappen die u moet uitvoeren om de API Microsoft Threat Protection met toepassingscontext te openen:

  1. Maak een AAD-webtoepassing.
  2. Wijs de gewenste machtiging toe aan het applicationFor-voorbeeld, **incident. Read. all**, **AdvancedHunting. Read. all**. 
  3. Maak een sleutel voor deze toepassing.
  4. Token verkrijgen met behulp van de toepassing met de sleutel.
  5. Het token gebruiken om toegang te krijgen tot de Microsoft Threat Protection API

     Zie voor meer informatie [toegang krijgen tot de context](api-create-app-web.md)van de toepassing.


- **Gebruikers context:** <br>
    Wordt gebruikt voor het uitvoeren van acties in de API namens een gebruiker.

    Stappen die u moet uitvoeren om de API Microsoft Threat Protection met toepassingscontext te verkrijgen:
  1. Maak een ingebouwde AAD-toepassing.
  2. Wijs de gewenste machtiging voor de toepassing toe. Bijvoorbeeld **incident. Read**, **AdvancedHunting. Read**.
  3. Token verkrijgen met behulp van de toepassing met gebruikersreferenties.
  4. Het token gebruiken om toegang te krijgen tot de Microsoft Threat Protection API

     Zie [toegang krijgen met gebruikerscontext](api-create-app-user-context.md)voor meer informatie.


## <a name="related-topics"></a>Verwante onderwerpen
- [Api's voor Microsoft Threat Protection](api-supported.md)
- [Toegang tot Microsoft Threat Protection met toepassingscontext](api-create-app-web.md)
- [Microsoft Threat Protection met gebruikerscontext openen](api-create-app-user-context.md)
