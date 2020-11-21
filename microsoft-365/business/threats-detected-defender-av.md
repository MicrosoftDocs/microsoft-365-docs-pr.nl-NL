---
title: Bedreigingen gedetecteerd door Microsoft Defender antivirus
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
description: Ontdek hoe Microsoft Defender antivirus uw Windows-apparaten beschermt tegen software bedreigingen, zoals virussen, malware en spyware.
ms.openlocfilehash: e3c8a1071625bba41af5f3cccd50f8484acac18d
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376689"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Bedreigingen gedetecteerd door Microsoft Defender antivirus

Microsoft Defender antivirus beschermt uw Windows-apparaten tegen software bedreigingen, zoals virussen, malware en spyware.

- Virussen worden gewoonlijk verspreid door hun code aan andere bestanden op uw apparaat of netwerk te koppelen en kunnen schadelijke Programma's niet juist werken.
- Malware omvat schadelijke bestanden, toepassingen en code die schade kunnen veroorzaken en de normale toepassing van apparaten kunnen verstoren. Daarnaast kunnen malware toegang krijgen tot onbevoegden, systeembronnen, wachtwoorden en accountgegevens stelen, vergrendelen en vragen voor Ransom en meer.
- Spyware verzamelt gegevens, zoals webbrowse activiteiten, en stuurt de gegevens naar externe servers.
 
Microsoft Defender Antivirus gebruikt diverse methoden om bedreigingsbeveiliging te geven. Deze methoden zijn beschikbaar voor cloudbeveiliging, realtime bescherming en gespecialiseerde beveiligingsupdates.

- Door de Cloud geleverde bescherming biedt u de nabije direct detectie en blokkering van nieuwe en opkomende bedreigingen.
- Bij gebruik van de functie voor het scannen van bestands-en proces gedrag en andere technieken (ook wel *bescherming van realtime* genoemd).
- Gespecialiseerde updates worden bijgewerkt op basis van machines Learning, menselijk en geautomatiseerde analyse van grote gegevens, en uitgebreid onderzoek naar de bedreigings vastheid. 

Zie de volgende artikelen voor meer informatie over malware en Microsoft Defender antivirus: 

- [Meer informatie over malware & andere bedreigingen](/windows/security/threat-protection/intelligence/understanding-malware)
- [Hoe Microsoft Malware en mogelijk ongewenste toepassingen identificeert](/windows/security/threat-protection/intelligence/criteria)
- [Volgende generatie beveiliging in Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>Wat gebeurt er wanneer een niet-Microsoft-antivirusoplossing wordt gebruikt? 

Microsoft Defender antivirus maakt deel uit van het besturingssysteem en is ingeschakeld op apparaten met Windows 10. Als u echter een niet-Microsoft-antivirusoplossing gebruikt en u Microsoft [Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)niet gebruikt, wordt Microsoft Defender antivirus automatisch geactiveerd in de modus uitgeschakeld.  

In de modus uitgeschakeld kunnen gebruikers en klanten nog steeds Microsoft Defender antivirus gebruiken voor geplande of op aanvraag scans om bedreigingen te identificeren; Microsoft Defender antivirus bevat echter niet langer:

- Gebruik de standaard antivirus-app.
- scant niet op bestanden met bedreigingen.
- verholpen, of oplossen, bedreigingen.

Als u de niet-Microsoft antivirusoplossing verwijdert, wordt Microsoft Defender antivirus automatisch geopend in de modus actief om uw Windows-apparaten te beschermen tegen bedreigingen.

> [!TIP]
> - Als u Microsoft 365 gebruikt, kunt u Microsoft Defender antivirus gebruiken als uw belangrijkste antivirus oplossing. Integratie biedt betere bescherming. Zie [beter samen: Microsoft Defender antivirus en Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus).
> - Zorg ervoor dat u Microsoft Defender antivirus up-to-date laat, ook als u een niet-Microsoft-antivirus oplossing gebruikt.

## <a name="what-to-expect-when-threats-are-detected"></a>Wat u kunt verwachten wanneer bedreigingen worden gedetecteerd

Wanneer bedreigingen worden gedetecteerd met Microsoft Defender antivirus, gebeurt het volgende:

- Gebruikers ontvangen [meldingen in Windows](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e). 
- Detecties worden vermeld in de [Windows-beveiligingstoepassing](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) op de pagina **beveiligings geschiedenis** .  
- Als u [uw Windows 10-apparaten hebt beveiligd](secure-win-10-pcs.md) en ze zijn [ingeschreven in intune](/mem/intune/enrollment/windows-enrollment-methods), ziet u de bedreigings detectie en inzichten in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-Beheercentrum</a> op de pagina **actieve bedreigingen** , die u kunt openen vanaf de pagina met **Microsoft Defender antivirus** op de **Start** pagina (of in het navigatiedeelvenster door **gezondheids** bedreigingen te selecteren  >  **& antivirus Programma's**).
    > [!NOTE]
    > De pagina's **Microsoft Defender antivirus** en **Active Threat** worden in fasen uitgerold, zodat u deze mogelijk niet direct kunt openen.

In de meeste gevallen hoeven gebruikers geen verdere actie te ondernemen. Zodra een schadelijk bestand of programma op een apparaat wordt gedetecteerd, blokkeert Microsoft Defender antivirus het zodat het niet kan worden uitgevoerd. Daarnaast worden nieuwe bedreigingen toegevoegd aan de antivirus-en antimalware-engine, zodat andere apparaten en gebruikers ook worden beveiligd.  

Als een gebruiker een actie moet ondernemen, zoals het goedkeuren van de verwijdering van een beschadigd bestand, ziet u dat ze in de melding ontvangen. Als u meer wilt weten over acties die in Microsoft Defender antivirus van gebruikers worden uitgevoerd, of acties die gebruikers kunnen uitvoeren, raadpleegt u de [beveiligings geschiedenis](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708). Als u wilt weten hoe u de detectie van bedreigingen als IT-medewerker en beheerder beheert, raadpleegt u [ontdekte bedreigingen controleren en actie ondernemen](review-threats-take-action.md).

Ga voor meer informatie over verschillende bedreigingen naar de <a href="https://www.microsoft.com/wdsi/threats" target="_blank">website Microsoft Security Intelligence Threats</a>, waar u de volgende acties kunt uitvoeren: 

- Actuele informatie weergeven over de belangrijkste bedreigingen.
- Bekijk de nieuwste bedreigingen voor een bepaalde regio.
- Doorzoek de Threat Encyclopedia voor informatie over een specifieke bedreiging.

## <a name="related-content"></a>Verwante onderwerpen

[Windows 10-apparaten beveiligen](secure-windows-10-devices.md) (artikel) \
[Evalueer Microsoft Defender antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (artikel) \
De [realtime-en cloudbeveiliging van antivirusprogramma's inschakelen](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (artikel) \
[Microsoft Defender antivirus inschakelen en gebruiken vanuit de Windows-beveiligingstoepassing](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (artikel) \
[Microsoft Defender antivirus inschakelen met behulp van Groepsbeleid](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (artikel) \
[Uw antivirusdefinities bijwerken](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (artikel) \
[Malware en niet-malware verzenden naar Microsoft for Analysis](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (artikel)