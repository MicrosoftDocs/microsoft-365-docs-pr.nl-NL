---
title: Apps beheren in Microsoft Managed Desktop
description: Informatie over het bijwerken van line-of-business-apps die zijn geïmplementeerd op Microsoft Managed Desktop apparaten
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: b016d8458b4b4cc9f6b684d3b8a3c0a1e1322fef
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925405"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Line-Of-Business-apps beheren in Microsoft Managed Desktop

<!--Application management -->

Er zijn een aantal manieren om app-updates te beheren voor apps die u hebt ge onboarded voor Microsoft Managed Desktop en geïmplementeerd op uw Microsoft Managed Desktop apparaten. U kunt app-updates maken in Microsoft Managed Desktop portal of Intune. 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>Line-of-business-apps bijwerken in Microsoft Managed Desktop

**Uw line-of-business-apps bijwerken in Microsoft Managed Desktop portal**
1. Meld u aan [bij Microsoft Managed Desktop beheerportal.](https://aka.ms/mmdportal)
2. Selecteer **onder Inventaris** de optie **Apps.**  
3. Selecteer de app die u wilt updaten en selecteer vervolgens **Bewerken.**
4. Selecteer **onder** Beheren de optie **Eigenschappen.** 
5. Klik **op App-pakketbestand** en blader naar een nieuw app-pakketbestand.
6. Selecteer **App-pakketbestand**.
7. Selecteer het mappictogram en blader naar de locatie van het bijgewerkte app-bestand. Selecteer **Openen**. De app-informatie wordt bijgewerkt met de pakketgegevens.
8. Controleer of **de app-versie** het bijgewerkte app-pakket weerspiegelt. 

De bijgewerkte app wordt geïmplementeerd op de apparaten van uw gebruiker.

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Line-of-Business-apps bijwerken in Intune

**Uw line-of-business-apps bijwerken in Intune**
1. Meld u aan bij [azure portal.](https://portal.azure.com)
2. Selecteer **Alle Services**  >  **Intune**. Intune staat in de sectie **Monitoring + Management.**
3. Selecteer **Client-apps > Apps.**
4. Zoek en selecteer uw app in de lijst met apps.
5. Selecteer eigenschappen **in het** blad **Overzicht.**
6. Selecteer **App-pakketbestand**.
7. Selecteer het mappictogram en blader naar de locatie van het bijgewerkte app-bestand. Selecteer **Openen**. De app-informatie wordt bijgewerkt met de pakketgegevens.
8. Controleer of **de app-versie** het bijgewerkte app-pakket weerspiegelt.

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>Een app terugdraaien naar een vorige versie

Als er een fout is gevonden wanneer een nieuwe versie van een app wordt geïmplementeerd, kunt u terugdraaien naar een vorige versie. Het proces dat hier wordt beschreven, is voor apps waarbij type wordt weergegeven **als Windows MSI line-of-business** app of **Windows-app (Win 32) - preview**

**Een line-of-business-app terugdraaien naar een vorige versie**

1. Meld u aan [bij Microsoft Managed Desktop beheerportal.](https://aka.ms/mmdportal)
2. Selecteer **onder Inventaris** de optie **Apps.**  
3. Selecteer de app die u wilt terugdraaien en selecteer vervolgens **Bewerken.**
4. Selecteer **onder** Beheren de optie **Eigenschappen.** 
    - Als **Windows app-apps voor een MSI-lijn** wilt gebruiken, selecteert u **App-informatie** en selecteert u vervolgens onder App-versie negeren **de** optie **Ja.**
    - Voor **Windows app (Win 32) -** preview-apps, selecteer **App-informatie,** selecteer **Detectieregels** en selecteer vervolgens **Toevoegen.** 
    Als er een MSI-regel is, controleert u of de controle van **de MSI-productversie** is ingesteld op **Nee**.
5. [Upload een vorige versie van het app-bronbestand naar](../get-started/deploy-apps.md) Microsoft Managed Desktop beheerportal.  

