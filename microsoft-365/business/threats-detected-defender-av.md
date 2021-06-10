---
title: Bedreigingen gedetecteerd door Microsoft Defender Antivirus
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Lees hoe Microsoft Defender Antivirus uw apparaten Windows tegen softwaredreigingen, zoals virussen, malware en spyware.
ms.openlocfilehash: 7c5d000e2a8c30e17d1f890cef69fe88beed75bb
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198361"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Bedreigingen gedetecteerd door Microsoft Defender Antivirus

Microsoft Defender Antivirus beschermt uw Windows tegen softwaredreigingen, zoals virussen, malware en spyware.

- Virussen worden meestal verspreid door hun code toe te koppelen aan andere bestanden op uw apparaat of netwerk en kunnen ertoe leiden dat geïnfecteerde programma's onjuist werken.
- Malware bevat schadelijke bestanden, toepassingen en code die schade kunnen veroorzaken en het normale gebruik van apparaten kunnen verstoren. Malware kan ook onbevoegde toegang toestaan, systeembronnen gebruiken, wachtwoorden en accountgegevens stelen, u van uw computer vergrendelen en om geld vragen, en meer.
- Spyware verzamelt gegevens, zoals webnavigatieactiviteit, en verzendt de gegevens naar externe servers.
 
Als u bedreigingsbeveiliging wilt bieden, Microsoft Defender Antivirus verschillende methoden gebruikt. Deze methoden omvatten beveiliging in de cloud, realtime beveiliging en speciale beveiligingsupdates.

- Beveiliging die in de cloud wordt geleverd, helpt bij het detecteren en blokkeren van nieuwe en nieuwe bedreigingen.
- Bij altijd scannen worden bestands- en procesgedragscontrole en andere technieken (ook wel *realtimebeveiliging genoemd) gebruikt.*
- Speciale beveiligingsupdates zijn gebaseerd op machine learning, menselijke en geautomatiseerde analyse van big data en uitgebreid onderzoek naar bedreigingsresistentie. 

Zie de volgende artikelen voor meer Microsoft Defender Antivirus en malware: 

- [Inzicht in malware & andere bedreigingen](/windows/security/threat-protection/intelligence/understanding-malware)
- [Hoe Microsoft malware en potentieel ongewenste toepassingen identificeert](/windows/security/threat-protection/intelligence/criteria)
- [Beveiliging van de volgende generatie in Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>Wat gebeurt er wanneer een niet-Microsoft-antivirusoplossing wordt gebruikt? 

Microsoft Defender Antivirus maakt deel uit van het besturingssysteem en is ingeschakeld op apparaten met Windows 10. Als u echter een niet-Microsoft-antivirusoplossing gebruikt en microsoft [Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)voor eindpunt niet gebruikt, wordt Microsoft Defender Antivirus automatisch uitgeschakeld.  

Wanneer de modus is uitgeschakeld, kunnen gebruikers en klanten nog steeds Microsoft Defender Antivirus voor geplande of on-demand scans om bedreigingen te identificeren. De Microsoft Defender Antivirus echter niet meer:

- worden gebruikt als de standaard antivirus-app.
- bestanden actief scannen op bedreigingen.
- om bedreigingen te corrigeren of op te lossen.

Als u de antivirusoplossing van niet-Microsoft verwijdert, Microsoft Defender Antivirus automatisch de actieve modus in om uw apparaten Windows beschermen tegen bedreigingen.

> [!TIP]
> - Als u een Microsoft 365 gebruikt, kunt u deze Microsoft Defender Antivirus als uw primaire antivirusoplossing. Integratie kan betere bescherming bieden. Zie [Beter samen: Microsoft Defender Antivirus en Office 365.](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus)
> - Zorg ervoor dat Microsoft Defender Antivirus up-to-date houdt, zelfs als u een niet-Microsoft-antivirusoplossing gebruikt.

## <a name="what-to-expect-when-threats-are-detected"></a>Wat u kunt verwachten wanneer bedreigingen worden gedetecteerd

Wanneer bedreigingen worden gedetecteerd door Microsoft Defender Antivirus, gebeuren de volgende dingen:

- Gebruikers ontvangen [meldingen in Windows.](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e) 
- Detecties worden weergegeven in de Windows-beveiliging [app](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) op de **pagina Beveiligingsgeschiedenis.**  
- Als u  uw [Windows 10-apparaten hebt](secure-win-10-pcs.md) beveiligd en hebt geregistreerd [in Intune](/mem/intune/enrollment/windows-enrollment-methods)en uw organisatie 800 of minder apparaten heeft geregistreerd, ziet u detecties en inzichten van bedreigingen in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-beheercentrum</a> op de pagina Bedreigingen en **antivirus,** die u kunt openen vanaf de **Microsoft Defender Antivirus-kaart** op de startpagina (of vanuit het navigatiedeelvenster door **Health** Threats & antivirus  >  **te** selecteren).

    Als uw organisatie meer dan 800 apparaten heeft die zijn geregistreerd in Intune, wordt u gevraagd om bedreigingsdetecties en inzichten te bekijken vanuit [Microsoft Endpoint Manager in](/mem/endpoint-manager-overview) plaats van vanaf de pagina Bedreigingen en **antivirus.**
 
    > [!NOTE]
    > De **Microsoft Defender Antivirus** kaart en de pagina Bedreigingen en **antivirus** worden gefaseerd uitgerold, zodat u mogelijk niet direct toegang hebt tot de kaart.

In de meeste gevallen hoeven gebruikers geen verdere actie te ondernemen. Zodra er een schadelijk bestand of programma wordt gedetecteerd op een apparaat, Microsoft Defender Antivirus het bestand en voorkomt u dat het wordt uitgevoerd. Bovendien worden nieuw gedetecteerde bedreigingen toegevoegd aan de antivirus- en antimalware-engine, zodat ook andere apparaten en gebruikers worden beveiligd.  

Als er een actie is die een gebruiker moet ondernemen, zoals het goedkeuren van het verwijderen van een schadelijk bestand, zien ze dat in de melding die ze ontvangen. Zie Beschermingsgeschiedenis voor meer informatie over Microsoft Defender Antivirus acties die namens een gebruiker worden ondernomen of acties die gebruikers mogelijk moeten [uitvoeren.](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708) Zie Gedetecteerde bedreigingen controleren en actie [ondernemen](review-threats-take-action.md)voor informatie over het beheren van bedreigingsdetecties als IT-professional/beheerder.

Voor meer informatie over verschillende bedreigingen gaat <a href="https://www.microsoft.com/wdsi/threats" target="_blank">u naar Microsoft-beveiligingsinformatie site Bedreigingen,</a>waar u de volgende acties kunt uitvoeren: 

- Bekijk de huidige informatie over topbedreigingen.
- Bekijk de meest recente bedreigingen voor een bepaalde regio.
- Zoek in de bedreigingsencyclopedie naar details over een specifieke bedreiging.

## <a name="related-content"></a>Verwante onderwerpen

[Beveiligde Windows 10 apparaten](secure-windows-10-devices.md) (artikel)\
[Evaluatie Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (artikel)\
Realtime en door de cloud geleverde [antivirusbeveiliging in-schakelen](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (artikel)\
[In- en Microsoft Defender Antivirus in](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) Windows-beveiliging app (artikel)\
[Het in- en Microsoft Defender Antivirus met groepsbeleid](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (artikel)\
[Uw antivirusdefinities bijwerken](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (artikel)\
[Malware en niet-malware indienen bij Microsoft voor analyse](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (artikel)
