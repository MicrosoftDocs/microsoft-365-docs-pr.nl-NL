---
title: Door de cloud geleverde beveiliging en Microsoft Defender Antivirus
description: Meer informatie over beveiliging en beveiliging in de Microsoft Defender Antivirus
keywords: Microsoft Defender Antivirus, volgende generatie technologieën, av van de volgende generatie, machine learning, antimalware, beveiliging, defender, cloud, beveiliging in de cloud
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: shwjha
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 06/03/2021
ms.openlocfilehash: ce54f8205e62b953022fd2518caac058f4f9bab2
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788797"
---
# <a name="cloud-delivered-protection-and-microsoft-defender-antivirus"></a>Door de cloud geleverde beveiliging en Microsoft Defender Antivirus

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender Antivirus

Technologieën van de volgende generatie in Microsoft Defender Antivirus bieden onmiddellijke, geautomatiseerde bescherming tegen nieuwe en nieuwe bedreigingen. Om nieuwe bedreigingen dynamisch te identificeren, werken technologieën van de volgende generatie met grote sets onderling verbonden gegevens in de Microsoft Intelligent Security Graph en krachtige AI-systemen (Artificial Intelligence) op basis van geavanceerde machine learning-modellen. Microsoft Defender Antivirus maakt gebruik van meerdere detectie- en preventietechnologieën om nauwkeurige, realtime en intelligente beveiliging te bieden. 

> [!TIP]
> Wilt u meer informatie? Zie het blogbericht, Maak gebruik van de geavanceerde technologieën in de [kern van Microsoft Defender voor endpoint next-generation protection.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

Microsoft Defender Antivirus werkt naadloos samen met Microsoft-cloudservices. Deze cloudbeveiligingsservices, ook wel Microsoft Advanced Protection Service (MAPS) genoemd, verbeteren de standaardbeveiliging in realtime, waardoor de beveiliging van antivirusprogramma's waarschijnlijk het beste is. 

> [!NOTE]
> De Microsoft Defender Antivirus cloudservice is een mechanisme voor het leveren van bijgewerkte beveiliging voor uw netwerk en eindpunten. Als cloudservice is het niet alleen beveiliging voor bestanden die zijn opgeslagen in de cloud. In plaats daarvan gebruikt de cloudservice gedistribueerde resources en machine learning om uw eindpunten te beschermen tegen een snelheid die veel sneller is dan traditionele beveiligingsinformatie-updates.

Met cloudbeveiliging bieden technologieën van de volgende generatie snelle identificatie van nieuwe bedreigingen, soms zelfs voordat één computer is geïnfecteerd. In de volgende blogberichten ziet u hoe beveiliging in de cloud werkt:

- [Waarom Microsoft Defender Antivirus de meest geïmplementeerde in de onderneming is](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 
- [Gedragscontrole in combinatie met machine learning bederft een enorme campagne voor het delven van munten](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)
- [Hoe kunstmatige intelligentie een emotet-uitbraak heeft gestopt](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)
- [Een slecht konijn detoneren: Microsoft Defender Antivirus en gelaagde machine learning-verdediging](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)
- [Microsoft Defender Antivirus cloudbeveiligingsservice: geavanceerde realtime verdediging tegen nooit eerder geziene malware](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 
 
## <a name="how-to-get-cloud-delivered-protection"></a>Beveiliging in de cloud 

Beveiliging in de cloud is standaard ingeschakeld. Mogelijk moet u het echter opnieuw inschakelen als deze is uitgeschakeld als onderdeel van eerder organisatiebeleid. Zie Beveiliging in de cloud in- en [uitleveren voor meer informatie.](enable-cloud-protection-microsoft-defender-antivirus.md)

Organisaties met Windows 10 E5 kunnen ook profiteren van dynamische intelligence-updates voor noodgevallen, die in de buurt van realtime bescherming bieden tegen nieuwe bedreigingen. Wanneer u beveiliging in de cloud inlevert, kunnen oplossingen voor malwareproblemen binnen enkele minuten via de cloud worden geleverd, in plaats van te wachten op de volgende update. [Configureer Microsoft Defender Antivirus om automatisch nieuwe beveiligingsupdates te ontvangen op basis van rapporten van onze cloudservice.](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates)

> [!TIP]
> Ga naar Windows Defender website van Testground op [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) om te bevestigen dat de functie werkt en te zien hoe deze werkt.

## <a name="next-steps"></a>Volgende stappen

1. [Beveiliging via de cloud inschakelen.](enable-cloud-protection-microsoft-defender-antivirus.md) U kunt cloudbeveiliging inschakelen met Microsoft Endpoint Manager (die nu Microsoft Endpoint Configuration Manager en Microsoft Intune), Groepsbeleid of PowerShell-cmdlets.

2. [Geef het door de cloud geleverde beveiligingsniveau op.](specify-cloud-protection-level-microsoft-defender-antivirus.md) U kunt het beveiligingsniveau opgeven dat door de cloud wordt geboden met Microsoft Endpoint Manager of Groepsbeleid. Het beveiligingsniveau is van invloed op de hoeveelheid gegevens die met de cloud wordt gedeeld en hoe agressief nieuwe bestanden worden geblokkeerd.

3. [Netwerkverbindingen configureren en valideren voor Microsoft Defender Antivirus.](configure-network-connections-microsoft-defender-antivirus.md) Er zijn bepaalde MICROSOFT-URL's waar uw netwerk en eindpunten verbinding mee moeten kunnen maken om effectief te kunnen werken met beveiliging in de cloud. In dit artikel worden de URL's vermeld die moeten worden toegestaan via firewall- of netwerkfilterregels en worden instructies voor het bevestigen van uw netwerk correct geregistreerd voor beveiliging in de cloud.

4. [Configureer de functie 'blok op het eerste gezicht'.](configure-block-at-first-sight-microsoft-defender-antivirus.md) De functie 'blok op het eerste gezicht' kan nieuwe malware binnen enkele seconden blokkeren, zonder uren te moeten wachten op traditionele beveiligingsinformatie. U kunt het inschakelen en configureren met Microsoft Endpoint Manager of Groepsbeleid.

5. [Configureer de time-outperiode voor cloudblokkering.](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) Microsoft Defender Antivirus kan blokkeren dat verdachte bestanden worden uitgevoerd terwijl er een query wordt uitgevoerd op onze beveiligingsservice in de cloud. U kunt de hoeveelheid tijd configureren dat het bestand niet kan worden uitgevoerd met Microsoft Endpoint Manager of groepsbeleid.