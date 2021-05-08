---
title: Beveiligingsfuncties voor Microsoft Defender Antivirus inschakelen en configureren
description: Beveiligingsfuncties in Microsoft Defender Antivirus realtime inschakelen en configureren, zoals gedragscontrole, heuristische functies en machine learning
keywords: antivirus, real-time beveiliging, rtp, machine-learning, gedragscontrole, heuristiek
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 12/16/2019
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 1e39e42b79a2a767473c4473434da249a0d07228
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275130"
---
# <a name="enable-and-configure-microsoft-defender-antivirus-always-on-protection-in-group-policy"></a>Always-on beveiliging van Microsoft Defender Antivirus inschakelen en configureren in Groepsbeleid

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Always-on-beveiliging bestaat uit realtime bescherming, gedragscontrole en heuristische acties om malware te identificeren op basis van bekende verdachte en schadelijke activiteiten.

Deze activiteiten omvatten gebeurtenissen, zoals processen die ongebruikelijke wijzigingen aanbrengen in bestaande bestanden, het wijzigen of maken van automatische opstartregistersleutels en opstartlocaties (ook wel bekend als extensibility-punten voor automatisch starten of ASEPs) en andere wijzigingen in het bestandssysteem of de bestandsstructuur.

## <a name="enable-and-configure-always-on-protection-in-group-policy"></a>Always-on-beveiliging inschakelen en configureren in groepsbeleid

U kunt lokale **groepsbeleidseditor gebruiken om** de Microsoft Defender Antivirus instellingen voor altijd ingeschakelde beveiliging in te stellen en te configureren.

Altijd ingeschakelde beveiliging inschakelen en configureren:

1. Open **Local Group Policy Editor**. Ga als volgende te werk:  

    1. Typ gpedit Windows 10 het zoekvak van de **taakbalk.**
    
    1. Klik **onder Beste overeenkomst** op **Groepsbeleid bewerken om** Lokale groepsbeleidseditor te **starten.**
    
       ![Zoekresultaat gpEdit-taakbalk](images/gpedit-search.png)

2. Vouw in het **linkerdeelvenster** van de Editor voor lokaal groepsbeleid de structuur uit naar **Beheersjablonen** voor computerconfiguratie Windows  >    >  **Onderdelen**  >  **Microsoft Defender Antivirus.** 

3. Configureer de Microsoft Defender Antivirus antimalwareservicebeleidsinstellingen. Ga als volgende te werk:  

    1. Dubbelklik **in Microsoft Defender Antivirus** detailvenster aan de rechterkant op de beleidsinstelling zoals aangegeven in de volgende tabel:

       | Instelling | Beschrijving | Standaardinstelling |
       |-----------------------------|------------------------|-------------------------------|
       | Antimalware-service met normale prioriteit laten opstarten | U kunt de prioriteit van de Microsoft Defender Antivirus verlagen, wat handig kan zijn in lichtgewicht implementaties waarin u een zo laag mogelijk opstartproces wilt hebben. Dit kan van invloed zijn op de beveiliging op het eindpunt. | Ingeschakeld
       | Toestaan dat antimalwareservice altijd actief blijft | Als beveiligingsupdates zijn uitgeschakeld, kunt u instellen dat Microsoft Defender Antivirus nog steeds wordt uitgevoerd. Hierdoor wordt de beveiliging op het eindpunt verlaagd. | Uitgeschakeld |
    
    1. Configureer de instelling zo nodig en klik op **OK.**
    
    1. Herhaal de vorige stappen voor elke instelling in de tabel.

4. Configureer Microsoft Defender Antivirus realtime beveiligingsbeleidsinstellingen. Ga als volgende te werk:

    1. Dubbelklik **in Microsoft Defender Antivirus** detailvenster op **Realtimebeveiliging.** Of klik in de **Microsoft Defender Antivirus** in het linkerdeelvenster op **Realtimebeveiliging.**
    
    1. Dubbelklik **in het deelvenster Realtimebeveiligingsdetails** aan de rechterkant op de beleidsinstelling zoals aangegeven in de volgende tabel:  

       | Instelling | Beschrijving | Standaardinstelling |
       |-----------------------------|------------------------|-------------------------------|
       | Gedragscontrole in- en uit- | De AV-engine controleert bestandsprocessen, bestands- en registerwijzigingen en andere gebeurtenissen op uw eindpunten op verdachte en bekende schadelijke activiteiten. | Ingeschakeld |
       | Alle gedownloade bestanden en bijlagen scannen | Gedownloade bestanden en bijlagen worden automatisch gescand. Dit werkt in aanvulling op het Windows Defender SmartScreen-filter, waarmee bestanden worden gescand voor en tijdens het downloaden. | Ingeschakeld |
       | Bestands- en programmaactiviteit op uw computer controleren | De Microsoft Defender Antivirus-engine maakt notitie van bestandswijzigingen (bestandswijzigingen, zoals bewegingen, kopieën of wijzigingen) en algemene programmaactiviteit (programma's die worden geopend of uitgevoerd en waardoor andere programma's worden uitgevoerd). | Ingeschakeld |
       | Onbewerkte schrijfmeldingen voor volume in- en uit- | Informatie over onbewerkte volume schrijft wordt geanalyseerd door gedragscontrole. | Ingeschakeld |
       | Processcans inschakelen wanneer realtimebeveiliging is ingeschakeld | U kunt onafhankelijk van elkaar de Microsoft Defender Antivirus om lopende processen te scannen op verdachte wijzigingen of gedragingen. Dit is handig als u de realtimebeveiliging tijdelijk hebt uitgeschakeld en automatisch processen wilt scannen die zijn gestart terwijl deze werd uitgeschakeld. | Ingeschakeld |
       | De maximale grootte definiëren van gedownloade bestanden en bijlagen die moeten worden gescand | U kunt de grootte in kilobytes definiëren. | Ingeschakeld |
       | Lokale instelling overschrijven configureren om gedragscontrole in te stellen | Configureer een lokale override voor de configuratie van gedragscontrole. Deze instelling kan alleen worden ingesteld op groepsbeleid. Als u deze instelling inschakelen, krijgt de lokale voorkeursinstelling prioriteit boven Groepsbeleid. Als u deze instelling uit- of niet configureert, krijgt groepsbeleid voorrang op de lokale voorkeursinstelling.| Ingeschakeld |
       | Lokale instelling overschrijven configureren voor het scannen van alle gedownloade bestanden en bijlagen | Configureer een lokale override voor de configuratie van het scannen van alle gedownloade bestanden en bijlagen. Deze instelling kan alleen worden ingesteld op groepsbeleid. Als u deze instelling inschakelen, krijgt de lokale voorkeursinstelling prioriteit boven Groepsbeleid. Als u deze instelling uit- of niet configureert, krijgt groepsbeleid voorrang op de lokale voorkeursinstelling.| Ingeschakeld |
       | Lokale instelling overschrijven configureren voor het controleren van bestands- en programmaactiviteit op uw computer | Configureer een lokale override voor de configuratie van monitoring voor bestands- en programmaactiviteit op uw computer. Deze instelling kan alleen worden ingesteld op groepsbeleid. Als u deze instelling inschakelen, krijgt de lokale voorkeursinstelling prioriteit boven Groepsbeleid. Als u deze instelling uit- of niet configureert, krijgt groepsbeleid voorrang op de lokale voorkeursinstelling.| Ingeschakeld |
       | Lokale instelling overschrijven configureren om realtimebeveiliging in te stellen | Configureer een lokale override voor de configuratie om realtimebeveiliging in te zetten. Deze instelling kan alleen worden ingesteld op groepsbeleid. Als u deze instelling inschakelen, krijgt de lokale voorkeursinstelling prioriteit boven Groepsbeleid. Als u deze instelling uit- of niet configureert, krijgt groepsbeleid voorrang op de lokale voorkeursinstelling.| Ingeschakeld |
       | Lokale instelling overschrijven configureren voor het controleren op activiteiten inkomende en uitgaande bestanden | Configureer een lokale override voor de configuratie van monitoring voor inkomende en uitgaande bestandsactiviteiten. Deze instelling kan alleen worden ingesteld op groepsbeleid. Als u deze instelling inschakelen, krijgt de lokale voorkeursinstelling prioriteit boven Groepsbeleid. Als u deze instelling uit- of niet configureert, krijgt groepsbeleid voorrang op de lokale voorkeursinstelling. | Ingeschakeld |
       | Monitoring configureren voor inkomende en uitgaande bestands- en programmaactiviteit | Geef op of monitoring moet plaatsvinden bij inkomende, uitgaande, beide of geen richting. Dit is relevant voor Windows serverinstallaties waar u specifieke servers of serverrollen hebt gedefinieerd die grote hoeveelheden bestandswijzigingen in slechts één richting zien en u de netwerkprestaties wilt verbeteren. Volledig bijgewerkte eindpunten (en servers) in een netwerk hebben weinig invloed op de prestaties, ongeacht het aantal of de richting van bestandswijzigingen. | Ingeschakeld (beide richtingen) |

    1. Configureer de instelling zo nodig en klik op **OK.**
    
    1. Herhaal de vorige stappen voor elke instelling in de tabel.

5. Configureer Microsoft Defender Antivirus scanbeleidsinstelling. Ga als volgende te werk:  

    1. Klik in **Microsoft Defender Antivirus** linkerdeelvenster op **Scannen.**
    
       ![Microsoft Defender Antivirus Scanopties](images/gpedit-windows-defender-antivirus-scan.png)

    1. Dubbelklik in **het** deelvenster Details scannen aan de rechterkant op de beleidsinstelling zoals aangegeven in de volgende tabel:

       | Instelling | Beschrijving | Standaardinstelling |
       |-----------------------------|------------------------|-------------------------------|    
       | Heuristiek in- en uit- | Heuristische beveiliging schakelt verdachte activiteiten uit of blokkeert direct voordat de Microsoft Defender Antivirus wordt gevraagd om de activiteit te detecteren. | Ingeschakeld |

    1. Configureer de instelling zo nodig en klik op **OK.**
    
6. Sluit **Lokale groepsbeleidseditor**.


## <a name="disable-real-time-protection-in-group-policy"></a>Realtimebeveiliging uitschakelen in groepsbeleid

> [!WARNING]
> Het uitschakelen van realtimebeveiliging vermindert de beveiliging op uw eindpunten drastisch en wordt niet aanbevolen.

De belangrijkste realtimebeveiligingsfunctie is standaard ingeschakeld, maar u kunt deze uitschakelen met **lokale groepsbeleidseditor.**

Realtimebeveiliging uitschakelen in groepsbeleid:

1. Open **Local Group Policy Editor**.

   1. Typ gpedit Windows 10 het zoekvak van de **taakbalk.**
   
   1. Klik **onder Beste overeenkomst** op **Groepsbeleid bewerken om** Lokale groepsbeleidseditor te **starten.**

2.  Vouw in het linkerdeelvenster van **de** Editor voor lokaal groepsbeleid de structuur uit naar **Beheersjablonen** voor computerconfiguratie Windows  >    >  **onderdelen**  >  **Microsoft Defender Antivirus**  >  **realtimebeveiliging.**

3. Dubbelklik **in het deelvenster Realtimebeveiligingsgegevens** aan de rechterkant op **Realtimebeveiliging uitschakelen.**

   ![Realtime beveiliging uitschakelen](images/gpedit-turn-off-real-time-protection.png)

4. Stel in **het instellingsvenster Voor realtimebeveiliging** uitschakelen de optie in op **Ingeschakeld.**

   ![Realtimebeveiliging uitschakelen](images/gpedit-turn-off-real-time-protection-enabled.png)
   
5. Klik op **OK**.

6. Sluit **Lokale groepsbeleidseditor**.

## <a name="related-articles"></a>Verwante artikelen

- [Gedrag, heuristiek en realtime bescherming configureren](configure-protection-features-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)