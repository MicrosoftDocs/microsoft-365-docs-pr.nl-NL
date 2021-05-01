---
title: Voorbeeld van een phishing-e-mail aanval
description: Stap door een voorbeeldanalyse van een phishing-aanval.
keywords: incidenten, waarschuwingen, onderzoeken, correlatie, aanval, machines, apparaten, gebruikers, identiteiten, identiteit, postvak, e-mail, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fb3656a9d3f67d979c012d9cc316a10e65a72042
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114644"
---
# <a name="example-of-a-phishing-email-attack"></a>Voorbeeld van een phishing-e-mail aanval

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

Microsoft 365 Defender kan helpen bij het opsporen van schadelijke bijlagen die via e-mail worden bezorgd. Aangezien [Office 365 beveiligings-](https://protection.office.com/) en compliancecentrum is geïntegreerd met Microsoft 365 Defender, kunnen beveiligingsanalisten inzicht hebben in bedreigingen die afkomstig zijn van Office 365, bijvoorbeeld via e-mailbijlagen.

Aan een analist is bijvoorbeeld een incident met meerdere fases toegewezen.
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="Voorbeeld van een incident met meerdere fases"::: 

Op het **tabblad Waarschuwingen** van het incident worden waarschuwingen van Defender voor Office 365 en Microsoft Cloud App Security weergegeven. De analist kan inzoomen op de Defender voor Office 365 waarschuwingen door de waarschuwingen voor e-mailberichten te selecteren. De details van de waarschuwing worden weergegeven in het zijvenster.

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="Voorbeeld van een e-mailwaarschuwing":::
 
Als u verder omlaag schuift, wordt er meer informatie weergegeven, met de schadelijke bestanden en gebruikers die zijn beïnvloed.

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="Voorbeeld van de invloed van een e-mailwaarschuwing op de gebruiker en het bestand":::
  
Als **u De waarschuwingspagina openen** selecteert, gaat u naar de specifieke waarschuwing, waar u verschillende informatie gedetailleerder kunt bekijken door de koppeling te selecteren. Het werkelijke e-mailbericht kan worden weergegeven door Berichten **weergeven in Explorer** onder aan het deelvenster te selecteren.
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="Voorbeeld van de details van een waarschuwing"::: 

Hiermee gaat de analist naar de pagina Bedreigingsbeheer, waar het onderwerp, de geadresseerde, de afzender en andere informatie worden weergegeven. **ZAP** onder **Speciale acties** vertelt de analist dat de functie voor automatisch reinigen van nul uur is geïmplementeerd. ZAP detecteert en verwijdert automatisch schadelijke en spamberichten uit postvakken in de hele organisatie. Zie Voor meer informatie [Zero-hour Auto Purge (ZAP) in Exchange Online.](../office-365-security/zero-hour-auto-purge.md)

Andere acties kunnen worden ondernomen op specifieke berichten door Acties **te selecteren.** 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="Voorbeeld van de andere acties voor e-mailberichten"::: 

## <a name="next-step"></a>Volgende stap

Bekijk het [op identiteit gebaseerde onderzoekspad](first-incident-path-identity.md) voor aanvallen.

## <a name="see-also"></a>Zie ook

- [Overzicht van incidenten](incidents-overview.md)
- [Incidenten analyseren](investigate-incidents.md)
- [Incidenten beheren](manage-incidents.md)
