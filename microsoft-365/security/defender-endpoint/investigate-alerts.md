---
title: Microsoft Defender onderzoeken voor eindpuntwaarschuwingen
description: Gebruik de onderzoeksopties om details te krijgen over waarschuwingen die van invloed zijn op uw netwerk, wat ze betekenen en hoe u deze kunt oplossen.
keywords: onderzoeken, onderzoeken, apparaten, apparaat, waarschuwingenwachtrij, dashboard, IP-adres, bestand, indienen, inzendingen, diepgaande analyse, tijdlijn, zoeken, domein, URL, IP
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 498f2d83af6e2eb7fc56b232bafd9fc49d9d4fd9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060110"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a>Waarschuwingen onderzoeken in Microsoft Defender voor Eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatealerts-abovefoldlink) 

Onderzoek waarschuwingen die van invloed zijn op uw netwerk, begrijpen wat ze betekenen en hoe u deze kunt oplossen.

Selecteer een waarschuwing in de waarschuwingenwachtrij om naar de waarschuwingspagina te gaan. Deze weergave bevat de waarschuwingstitel, de betreffende assets, het detail zijvenster en het waarschuwingsverhaal.

Start uw onderzoek op de waarschuwingspagina door de betreffende activa of een van de entiteiten te selecteren onder de weergave van de waarschuwingsverhaalstructuur. Het detailvenster wordt automatisch gevuld met meer informatie over wat u hebt geselecteerd. Als u wilt zien wat voor soort informatie u hier kunt bekijken, leest u [Waarschuwingen controleren in Microsoft Defender voor Eindpunt.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/review-alerts)

## <a name="investigate-using-the-alert-story"></a>Onderzoeken met behulp van het waarschuwingsverhaal

Het waarschuwingsverhaal geeft aan waarom de waarschuwing is geactiveerd, gerelateerde gebeurtenissen die vóór en na zijn gebeurd, evenals andere gerelateerde entiteiten.

Entiteiten kunnen worden geklikt en elke entiteit die geen waarschuwing is, kan worden uitvuwbaar met behulp van het uitvuwpictogram aan de rechterkant van de kaart van die entiteit. De entiteit in focus wordt aangegeven met een blauwe streep aan de linkerkant van de kaart van die entiteit, met de waarschuwing in de titel die in eerste instantie de focus heeft.

Vouw entiteiten uit om details in één oogopslag weer te geven. Als u een entiteit selecteert, wordt de context van het detailvenster naar deze entiteit overschakelt en kunt u meer informatie bekijken en deze entiteit beheren. Als *u ...* aan de rechterkant van de entiteitskaart selecteert, worden alle acties die beschikbaar zijn voor die entiteit, aan het licht komen. Dezelfde acties worden weergegeven in het detailvenster wanneer de focus van die entiteit ligt.

> [!NOTE]
> De sectie Waarschuwingsverhaal kan meer dan één waarschuwing bevatten, met aanvullende waarschuwingen die betrekking hebben op dezelfde uitvoeringsstructuur die wordt weergegeven vóór of na de waarschuwing die u hebt geselecteerd.

![Een voorbeeld van een waarschuwingsverhaal met een waarschuwing in focus en enkele uitverbrede kaarten](images/alert-story-tree.png)

## <a name="take-action-from-the-details-pane"></a>Actie ondernemen vanuit het detailvenster

Nadat u een entiteit van belang hebt geselecteerd, wordt het detailvenster gewijzigd om informatie weer te geven  over het geselecteerde entiteitstype, historische informatie wanneer deze beschikbaar is en biedt u besturingselementen om rechtstreeks vanaf de waarschuwingspagina actie te ondernemen op deze entiteit.

Nadat u klaar bent met het onderzoeken, gaat u terug naar  de waarschuwing die u  hebt gestart, markeert u de status van de waarschuwing als Opgelost en classificeert u deze als onwaarmelding of **Waar-waarschuwing.** Als u waarschuwingen classificeert, kunt u deze mogelijkheid afstemmen om meer waargebeurde waarschuwingen en minder onwaar waarschuwingen te geven.

Als u deze als een waar waarschuwing classificeert, kunt u ook een bepaling selecteren, zoals wordt weergegeven in de onderstaande afbeelding.

![Een fragment van het detailvenster met een opgeloste waarschuwing en de vervolgkeuze uitv](images/alert-details-resolved-true.png)

Als u een foutmelding ondervindt met een line-of-business-toepassing, maakt u een onderdrukkingsregel om dit type waarschuwing in de toekomst te voorkomen.

![acties en classificatie in het detailvenster met de onderdrukkingsregel gemarkeerd](images/alert-false-suppression-rule.png)

> [!TIP]
> Als u problemen ondervindt die niet hierboven worden beschreven, gebruikt u de 🙂 knop om feedback te geven of een ondersteuningsticket te openen.


## <a name="related-topics"></a>Verwante onderwerpen
- [De wachtrij waarschuwingen voor Microsoft Defender voor eindpunten weergeven en ordenen](alerts-queue.md)
- [Waarschuwingen voor Microsoft Defender voor eindpunten beheren](manage-alerts.md)
- [Een bestand onderzoeken dat is gekoppeld aan een waarschuwing van Defender voor eindpunt](investigate-files.md)
- [Apparaten onderzoeken in de lijst Defender voor eindpuntapparaten](investigate-machines.md)
- [Een IP-adres onderzoeken dat is gekoppeld aan een waarschuwing van Defender voor eindpunt](investigate-ip.md)
- [Een domein onderzoeken dat is gekoppeld aan een waarschuwing van Defender voor eindpunt](investigate-domain.md)
- [Een gebruikersaccount onderzoeken in Defender voor Eindpunt](investigate-user.md)


