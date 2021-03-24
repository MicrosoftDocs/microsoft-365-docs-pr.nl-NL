---
title: Uploads van automatiseringsbestand beheren
description: Inhoudsanalyse inschakelen en de bestandsextensies en e-mailbijlageextensies configureren die voor analyse worden ingediend
keywords: automatisering, bestand, uploads, inhoud, analyse, bestand, extensie, e-mail, bijlage
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 72405ad7500bf5d672f66ea64634e60c29ad1704
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060698"
---
# <a name="manage-automation-file-uploads"></a>Uploads van automatiseringsbestand beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

Schakel de mogelijkheid voor inhoudsanalyse in, zodat bepaalde bestanden en e-mailbijlagen automatisch naar de cloud kunnen worden geüpload voor aanvullende controle in Geautomatiseerd onderzoek.

Identificeer de bestanden en e-mailbijlagen door de namen van de bestandsextensie en de extensienamen voor e-mailbijlagen op te geven. 

Als u bijvoorbeeld *exe* en *bat* toevoegt als bestands- of bijlageextensienamen, worden alle bestanden of bijlagen met deze extensies automatisch naar de cloud verzonden voor aanvullende controle tijdens geautomatiseerd onderzoek. 

## <a name="add-file-extension-names-and-attachment-extension-names"></a>Bestandsextensienamen en naam van bijlageextensie toevoegen.

1. Selecteer in het navigatiedeelvenster **Instellingen**  >  **Automatiseringsbestand uploaden**. 

2. Schakel de instelling voor inhoudsanalyse in **tussen Aan** en **Uit.**

3. Configureer de volgende extensienamen en scheid extensienamen met een komma:
   - **Bestandsextensienamen:** verdachte bestanden, behalve e-mailbijlagen, worden ter aanvullende controle ingediend
  

## <a name="related-topics"></a>Verwante onderwerpen
- [Uitsluitingen van automatiseringsmappen beheren](manage-automation-folder-exclusions.md)
