---
title: API Explorer in Microsoft Defender voor Eindpunt
ms.reviewer: ''
description: De API Explorer gebruiken voor het maken en uitvoeren van API-query's, testen en verzenden van aanvragen voor een beschikbare API
keywords: api, verkenner, verzenden, aanvragen, ontvangen, posten,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: b8d0d991e46464bae3b4d21d6218b9b3b2d2b4cb
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930111"
---
# <a name="api-explorer"></a>API Explorer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)


De Microsoft Defender voor Endpoint API Explorer is een hulpmiddel waarmee u verschillende API's voor Defender voor eindpunten interactief kunt verkennen. 

Met API Explorer kunt u eenvoudig API-query's maken, testen en verzenden voor alle beschikbare Defender voor Endpoint API-eindpunten. Gebruik de API Explorer om acties uit te voeren of gegevens te vinden die mogelijk nog niet beschikbaar zijn via de gebruikersinterface.

Het hulpprogramma is handig tijdens het ontwikkelen van apps. Hiermee kunt u API-query's uitvoeren die uw gebruikerstoegangsinstellingen respecteren, waardoor u minder toegangstokens hoeft te genereren.

U kunt het hulpprogramma ook gebruiken om de galerie met voorbeeldquery's te verkennen, resultatencodevoorbeelden te kopiëren en foutopsporingsgegevens te genereren.

Met de API Explorer kunt u het volgende doen:

- Aanvragen voor een methode uitvoeren en antwoorden in realtime bekijken
- Blader snel door de API-voorbeelden en ontdek welke parameters ze ondersteunen
- Maak API-oproepen met gemak; u hoeft zich niet te verifiëren buiten de aanmelding van de beheerportal

## <a name="access-api-explorer"></a>Access API Explorer

Selecteer in het linkernavigatiemenu **Partners &**  >  **API-API Explorer**.

## <a name="supported-apis"></a>Ondersteunde API's

API Explorer ondersteunt alle API's die worden aangeboden door Defender voor Eindpunt.
  
De lijst met ondersteunde API's is beschikbaar in de [DOCUMENTATIE van API's.](apis-intro.md) 

## <a name="get-started-with-the-api-explorer"></a>Aan de slag met de API Explorer

1. In het linkerdeelvenster ziet u een lijst met voorbeeldaanvragen die u kunt gebruiken. 
2. Volg de koppelingen en klik op **Query uitvoeren.** 

Voor sommige voorbeelden moet mogelijk een parameter in de URL worden opgegeven, bijvoorbeeld {machine-ID}.

## <a name="faq"></a>Veelgestelde vragen

**Moet ik een API-token hebben om de API Explorer te kunnen gebruiken?** <br>
Referenties voor toegang tot een API zijn niet nodig. De API Explorer gebruikt het token van de Defender for Endpoint Management Portal wanneer deze een aanvraag indient.

De aanmeldingsreferentie voor gebruikersverificatie wordt gebruikt om te controleren of de API Explorer gemachtigd is om namens u toegang te krijgen tot gegevens.

Specifieke API-aanvragen zijn beperkt op basis van uw RBAC-bevoegdheden. Een aanvraag voor 'Indicator verzenden' is bijvoorbeeld beperkt tot de rol van beveiligingsbeheerder. 
