---
title: Toegang tot de API's voor Microsoft Defender voor Eindpunt
ms.reviewer: ''
description: Meer informatie over hoe u API's kunt gebruiken om workflows te automatiseren en te innoveren op basis van Microsoft Defender for Endpoint-mogelijkheden
keywords: api's, api, wdatp, open api, microsoft defender voor endpoint api, microsoft defender atp, public api, ondersteunde api's, alerts, device, user, domain, ip, file, advanced hunting, query
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a91a401d5d57c7757bc043178c95dc42e7733b41
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571827"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>Toegang tot de API's voor Microsoft Defender voor Eindpunt 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


**Van toepassing op:** 
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Wilt u Microsoft Defender voor Endpoint ervaren? [Meld je aan voor een gratis proefperiode.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



Defender for Endpoint legt veel van zijn gegevens en acties bloot via een set programmatische API's. Met deze API's kunt u workflows automatiseren en innoveren op basis van Defender for Endpoint-mogelijkheden. Voor de API-toegang is OAuth2.0-verificatie vereist. Zie [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)voor meer informatie.

Bekijk deze video voor een snel overzicht van de API's van Defender for Endpoint. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

Over het algemeen moet u de volgende stappen uitvoeren om de API's te gebruiken:
- Een [AAD-toepassing maken](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)
- Een toegangs token ophalen met deze toepassing
- Het token gebruiken om toegang te krijgen tot Defender voor Endpoint API


U hebt toegang tot Defender for Endpoint API met **toepassingscontext** of **gebruikerscontext**.

- **Toepassingscontext: (Aanbevolen)** <br>
    Wordt gebruikt door apps die worden uitgevoerd zonder dat er een aangemelde gebruiker aanwezig is. bijvoorbeeld apps die worden uitgevoerd als achtergrondservices of daemons.

    Stappen die moeten worden uitgevoerd om toegang te krijgen tot Defender for Endpoint API met toepassings context:

  1. Maak een AAD-webtoepassing.
  2. Wijs de gewenste machtiging toe aan de toepassing, bijvoorbeeld 'Lees waarschuwingen', 'Isolate Machines'. 
  3. Maak een sleutel voor deze toepassing.
  4. Token ophalen met behulp van de toepassing met de sleutel.
  5. Het token gebruiken om toegang te krijgen tot de Microsoft Defender for Endpoint API

     Zie [Toegang krijgen met toepassings context voor](exposed-apis-create-app-webapp.md)meer informatie.


- **Gebruikerscontext:** <br>
    Wordt gebruikt om acties uit te voeren in de API namens een gebruiker.

    Stappen die u moet nemen om toegang te krijgen tot Defender for Endpoint API met toepassings context:

  1. Maak een AAD-native toepassing.
  2. Wijs de gewenste toestemming toe aan de applicatie, bijvoorbeeld 'Leeswaarschuwingen', 'Isolate Machines' enz. 
  3. Token ophalen met behulp van de toepassing met gebruikers referenties.
  4. Het token gebruiken om toegang te krijgen tot de Microsoft Defender for Endpoint API

     Zie [Toegang krijgen met gebruikerscontext voor](exposed-apis-create-app-nativeapp.md)meer informatie.


## <a name="related-topics"></a>Verwante onderwerpen
- [Microsoft Defender voor endpoint-API's](exposed-apis-list.md)
- [Toegang tot Microsoft Defender voor eindpunt met toepassingscontext](exposed-apis-create-app-webapp.md)
- [Toegang tot Microsoft Defender voor eindpunt met gebruikerscontext](exposed-apis-create-app-nativeapp.md)
