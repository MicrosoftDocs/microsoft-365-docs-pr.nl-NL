---
title: Apps beheren in Microsoft Managed Desktop
description: Informatie over het bijwerken van zakelijke apps die zijn geïmplementeerd op Microsoft Managed Desktop-apparaten
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1a6b91ab5b4523f4b980dab0c25af41a9d614189
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42809136"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Zakelijke line-of-business-apps beheren in Microsoft Managed Desktop

<!--Application management -->

Er zijn een aantal manieren om app-updates te beheren voor apps die u hebt aangesloten op Microsoft Managed Desktop en geïmplementeerd op uw Microsoft Managed Desktop-apparaten. U app-updates uitvoeren in microsoft Managed Desktop-portal of Intune. 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>Line-of-business-apps bijwerken in Microsoft Managed Desktop

**Uw bedrijfsregel-apps bijwerken in microsoft Managed Desktop-portal**
1. Meld u aan bij [microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).
2. Selecteer **Onder Inventaris**de optie **Apps**.  
3. Selecteer de app die u wilt bijwerken en selecteer **Bewerken**.
4. Selecteer **Eigenschappen** **onder Beheren**. 
5. Klik **op App-pakketbestand**en blader vervolgens om een nieuw app-pakketbestand te uploaden.
6. Selecteer **App-pakketbestand**.
7. Selecteer het mappictogram en blader naar de locatie van uw bijgewerkte app-bestand. Selecteer **Openen**. De app-informatie wordt bijgewerkt met de pakketinformatie.
8. Controleer of **de app-versie** het bijgewerkte app-pakket weergeeft. 

De bijgewerkte app wordt geïmplementeerd op de apparaten van uw gebruiker.

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Line-of-business-apps bijwerken in Intune

**Uw line-of-business-apps bijwerken in Intune**
1. Meld u aan bij [Azure portal](https://portal.azure.com).
2. Selecteer **Alle Services** > **Intune**. Intune bevindt zich in de sectie **Monitoring + Management.**
3. Selecteer **Client Apps > Apps**.
4. Zoek en selecteer uw app in de lijst met apps.
5. Selecteer **eigenschappen**in het **blad Overzicht** .
6. Selecteer **App-pakketbestand**.
7. Selecteer het mappictogram en blader naar de locatie van uw bijgewerkte app-bestand. Selecteer **Openen**. De app-informatie wordt bijgewerkt met de pakketinformatie.
8. Controleer of **de app-versie** het bijgewerkte app-pakket weergeeft.

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>Een app terugdraaien naar een vorige versie

Als er een fout wordt gevonden wanneer een nieuwe versie van een app wordt geïmplementeerd, u terugdraaien naar een vorige versie. Het hier beschreven proces is voor apps waarvan het type wordt vermeld als **Windows MSI line-of-business app** of **Windows-app (Win 32) - preview**

**Een bedrijfsregel-app terugdraaien naar een vorige versie**

1. Meld u aan bij [microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).
2. Selecteer **Onder Inventaris**de optie **Apps**.  
3. Selecteer de app die u moet terugdraaien en selecteer **Vervolgens Bewerken**.
4. Selecteer **Eigenschappen** **onder Beheren**. 
    - Selecteer **app-informatie**voor **Windows MSI-apps voor line-of-business** apps en selecteer vervolgens onder **App-versie negeren**de optie **Ja**.
    - Voor **Windows-apps (Win 32) - voorbeeld van** apps, selecteer **App-informatie,** selecteer **Detectieregels**en selecteer vervolgens **Toevoegen**. 
    Als er een MSI-regel is, controleert u of **de controle van de MSI-productversie** is ingesteld op **Nee**.
5. [Upload een vorige versie van het bronbestand van de app](../get-started/deploy-apps.md) naar de Microsoft Managed Desktop Admin-portal.  

