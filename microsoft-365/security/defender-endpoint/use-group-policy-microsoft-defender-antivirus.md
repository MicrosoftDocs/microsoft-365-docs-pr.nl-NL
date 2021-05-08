---
title: Microsoft Defender Antivirus configureren met groepsbeleid
description: Lees hoe u een groepsbeleid kunt gebruiken om uw Microsoft Defender Antivirus te configureren en te beheren in Microsoft Defender voor eindpunten.
keywords: groepsbeleid, GPO, configuratie, instellingen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 04/13/2021
ms.reviewer: ksarens, jtoole, pahuijbr
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 8db14b016491ac10872f29f04b8166e548d6c63b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275334"
---
# <a name="use-group-policy-settings-to-configure-and-manage-microsoft-defender-antivirus"></a>Groepsbeleidsinstellingen gebruiken voor het configureren en beheren van Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

U kunt [Groepsbeleid gebruiken om](/windows/win32/srvnodes/group-policy) uw Microsoft Defender Antivirus te configureren en te beheren.

In het algemeen kunt u de volgende procedure gebruiken voor het configureren of wijzigen van Microsoft Defender Antivirus groepsbeleidsinstellingen:

1. Open op uw groepsbeleidsbeheercomputer de console Groepsbeleidsbeheer [,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

2. Ga met **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**

3. Klik **op Beheersjablonen.**

4. Vouw de boom uit Windows **onderdelen**  >  **Microsoft Defender Antivirus.**

5. Vouw de sectie uit (ook wel locatie **genoemd** in de tabel in dit onderwerp) met de instelling die u wilt configureren, dubbelklik op de instelling om deze te openen en wijzig de configuratie.

6. [Implementeer het bijgewerkte GPO zoals u dat normaal doet.](/windows/win32/srvnodes/group-policy) 

De volgende tabel in dit onderwerp bevat de groepsbeleidsinstellingen die beschikbaar zijn in Windows 10, versie 1703, en bevat koppelingen naar het juiste onderwerp in deze documentatiebibliotheek (indien van toepassing).

| Locatie | Instelling | Artikel |
|:---|:---|:---|
| Clientinterface | Gebruikersinterface zonder hoofd inschakelen | [Voorkomen dat gebruikers de gebruikersinterface van de Microsoft Defender Antivirus zien of gebruiken](prevent-end-user-interaction-microsoft-defender-antivirus.md) |
| Clientinterface | Extra tekst weergeven aan clients wanneer ze een actie moeten uitvoeren | [De meldingen configureren die op eindpunten worden weergegeven](configure-notifications-microsoft-defender-antivirus.md) |
| Clientinterface | Alle meldingen onderdrukken | [De meldingen configureren die op eindpunten worden weergegeven](configure-notifications-microsoft-defender-antivirus.md) |
| Clientinterface | Herstartmeldingen onderdrukken | [De meldingen configureren die op eindpunten worden weergegeven](configure-notifications-microsoft-defender-antivirus.md) |
| Uitsluitingen | Uitbreidingsuitsluitingen | [Uitsluitingen configureren en valideren in Microsoft Defender Antivirus scans](configure-exclusions-microsoft-defender-antivirus.md) |
| Uitsluitingen | Paduitsluitingen | [Uitsluitingen configureren en valideren in Microsoft Defender Antivirus scans](configure-exclusions-microsoft-defender-antivirus.md) |
| Uitsluitingen | Uitsluitingen verwerken | [Uitsluitingen configureren en valideren in Microsoft Defender Antivirus scans](configure-exclusions-microsoft-defender-antivirus.md) | 
| Uitsluitingen | Automatische uitsluitingen uitschakelen | [Uitsluitingen configureren en valideren in Microsoft Defender Antivirus scans](configure-exclusions-microsoft-defender-antivirus.md) |
| KAARTEN | De functie 'Block at First Sight' configureren | [Blok op het eerste gezicht inschakelen](configure-block-at-first-sight-microsoft-defender-antivirus.md) |
| KAARTEN | Deelnemen aan Microsoft MAPS | [Beveiliging via de cloud inschakelen](enable-cloud-protection-microsoft-defender-antivirus.md) |
| KAARTEN | Bestandsvoorbeelden verzenden wanneer verdere analyse is vereist | [Beveiliging via de cloud inschakelen](enable-cloud-protection-microsoft-defender-antivirus.md) |
| KAARTEN | Lokale instelling overschrijven voor rapportage naar Microsoft MAPS configureren | [Voorkomen of toestaan dat gebruikers beleidsinstellingen lokaal wijzigen](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| MpEngine | Uitgebreide cloudcontrole configureren | [De time-outperiode voor cloudblokkering configureren](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) |
| MpEngine | Beveiligingsniveau voor de cloud selecteren | [Niveau voor door cloud geleverde beveiliging opgeven](specify-cloud-protection-level-microsoft-defender-antivirus.md) |
| Netwerkcontrolesysteem | Aanvullende definitiesets opgeven voor netwerkverkeersinspectie | Niet meer relevant |
| Netwerkcontrolesysteem | Definitie-uittreding in-/uit- | Niet meer relevant |
| Netwerkcontrolesysteem | Protocolherkenning in- en uit- | Niet meer relevant |
| Quarantaine | Lokale instelling overschrijven configureren voor het verwijderen van items uit de map Quarantaine | [Voorkomen of toestaan dat gebruikers beleidsinstellingen lokaal wijzigen](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Quarantaine | Het verwijderen van items configureren uit de map Quarantaine | [Herstel configureren voor Microsoft Defender Antivirus scans](configure-remediation-microsoft-defender-antivirus.md) |
| Realtime beveiliging | Lokale instelling overschrijven configureren voor het controleren van bestands- en programmaactiviteit op uw computer | [Voorkomen of toestaan dat gebruikers beleidsinstellingen lokaal wijzigen](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Realtime beveiliging | Lokale instelling overschrijven configureren voor het controleren op activiteiten inkomende en uitgaande bestanden | [Voorkomen of toestaan dat gebruikers beleidsinstellingen lokaal wijzigen](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Realtime beveiliging | Lokale instelling overschrijven configureren voor het scannen van alle gedownloade bestanden en bijlagen | [Voorkomen of toestaan dat gebruikers beleidsinstellingen lokaal wijzigen](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Realtime beveiliging | Lokale instelling overschrijven configureren om gedragscontrole in te stellen | [Voorkomen of toestaan dat gebruikers beleidsinstellingen lokaal wijzigen](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Realtime beveiliging | Lokale instelling overschrijven configureren om realtimebeveiliging in te stellen | [Voorkomen of toestaan dat gebruikers beleidsinstellingen lokaal wijzigen](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Realtime beveiliging | De maximale grootte definiëren van gedownloade bestanden en bijlagen die moeten worden gescand | [Beveiliging en Microsoft Defender Antivirus altijd ingeschakeld inschakelen en configureren](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Realtime beveiliging | Bestands- en programmaactiviteit op uw computer controleren | [Beveiliging en Microsoft Defender Antivirus altijd ingeschakeld inschakelen en configureren](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Realtime beveiliging | Alle gedownloade bestanden en bijlagen scannen | [Beveiliging en Microsoft Defender Antivirus altijd ingeschakeld inschakelen en configureren](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Realtime beveiliging | Realtime beveiliging uitschakelen | [Beveiliging en Microsoft Defender Antivirus altijd ingeschakeld inschakelen en configureren](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Realtime beveiliging | Gedragscontrole in- en uit- | [Beveiliging en Microsoft Defender Antivirus altijd ingeschakeld inschakelen en configureren](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Realtime beveiliging | Processcans inschakelen wanneer realtimebeveiliging is ingeschakeld | [Beveiliging en Microsoft Defender Antivirus altijd ingeschakeld inschakelen en configureren](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Realtime beveiliging | Onbewerkte schrijfmeldingen voor volume in- en uit- | [Beveiliging en Microsoft Defender Antivirus altijd ingeschakeld inschakelen en configureren](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Realtime beveiliging | Monitoring configureren voor inkomende en uitgaande bestands- en programmaactiviteit | [Beveiliging en Microsoft Defender Antivirus altijd ingeschakeld inschakelen en configureren](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Herstellen | Lokale instelling overschrijven voor het tijdstip van de dag configureren om een geplande volledige scan uit te voeren om herstel te voltooien | [Voorkomen of toestaan dat gebruikers beleidsinstellingen lokaal wijzigen](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Herstellen | Geef de dag van de week op om een geplande volledige scan uit te voeren om herstel te voltooien | [Geplande scans Microsoft Defender Antivirus configureren](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Herstellen | Geef de tijd van de dag op om een geplande volledige scan uit te voeren om de hersteltijd te voltooien | [Geplande scans Microsoft Defender Antivirus configureren](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Rapportage | Verbeterde meldingen uitschakelen | [De meldingen configureren die op eindpunten worden weergegeven](configure-notifications-microsoft-defender-antivirus.md)
| Hoofdmap | Schakel de Microsoft Defender Antivirus | Niet gebruikt (Deze instelling moet zijn ingesteld op Niet **geconfigureerd** om ervoor te zorgen dat geïnstalleerde antivirus-apps van derden correct werken)
| Hoofdmap | Adressen definiëren om proxyserver te omzeilen | Niet gebruikt |
| Hoofdmap | Proxy autoconfig (.pac) definiëren voor verbinding maken met het netwerk | Niet gebruikt |
| Hoofdmap | Proxyserver definiëren voor verbinding maken met het netwerk | Niet gebruikt |
| Hoofdmap | Het samenvoeggedrag van lokale beheerders configureren voor lijsten | [Voorkomen of toestaan dat gebruikers beleidsinstellingen lokaal wijzigen](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Hoofdmap | Antimalware-service met normale prioriteit laten starten | [Herstel configureren voor Microsoft Defender Antivirus scans](configure-remediation-microsoft-defender-antivirus.md) |
| Hoofdmap | Toestaan dat antimalwareservice altijd actief blijft | [Herstel configureren voor Microsoft Defender Antivirus scans](configure-remediation-microsoft-defender-antivirus.md) |
| Hoofdmap | Routine-herstel uitschakelen | [Herstel configureren voor Microsoft Defender Antivirus scans](configure-remediation-microsoft-defender-antivirus.md) |
| Hoofdmap | Geplande taaktijden willekeurig maken | [Geplande scans configureren voor Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Scannen | Toestaan dat gebruikers de scan onderbreken | [Voorkomen dat gebruikers de](prevent-end-user-interaction-microsoft-defender-antivirus.md) gebruikersinterface van de Microsoft Defender Antivirus zien of gebruiken (niet ondersteund op Windows 10) |
| Scannen | Controleer op de meest recente virus- en spywaredefinities voordat u een geplande scan gaat uitvoeren | [Op basis van gebeurtenissen afgedwongen updates beheren](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Scannen | Het aantal dagen definiëren waarop een inhaalscan wordt gedwongen | [Updates beheren voor eindpunten die verouderd zijn](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Scannen | Volledige scan inhalen in- en uithalen | [Updates beheren voor eindpunten die verouderd zijn](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Scannen | Quick Scan inhalen in-/uit- | [Updates beheren voor eindpunten die verouderd zijn](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Scannen | Lokale instelling overschrijven configureren voor maximumpercentage cpu-gebruik | [Voorkomen of toestaan dat gebruikers beleidsinstellingen lokaal wijzigen](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Scannen | Lokale instelling overschrijven voor planningsscandag configureren | [Voorkomen of toestaan dat gebruikers beleidsinstellingen lokaal wijzigen](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Scannen | Lokale instelling overschrijven configureren voor geplande snelle scantijd | [Voorkomen of toestaan dat gebruikers beleidsinstellingen lokaal wijzigen](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Scannen | Lokale instelling overschrijven configureren voor geplande scantijd | [Voorkomen of toestaan dat gebruikers beleidsinstellingen lokaal wijzigen](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Scannen | Lokale instelling overschrijven configureren voor het scantype dat wordt gebruikt voor een geplande scan | [Voorkomen of toestaan dat gebruikers beleidsinstellingen lokaal wijzigen](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Scannen | Een systeemherstelpunt maken | [Herstel configureren voor Microsoft Defender Antivirus scans](configure-remediation-microsoft-defender-antivirus.md) |
| Scannen | Het verwijderen van items uit de map scangeschiedenis in- | [Herstel configureren voor Microsoft Defender Antivirus scans](configure-remediation-microsoft-defender-antivirus.md) |
| Scannen | Heuristiek in- en uit- | [Beveiliging en Microsoft Defender Antivirus altijd ingeschakeld inschakelen en configureren](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Scannen | E-mail scannen in-/uit- | [Scanopties configureren in Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Scannen | Reparse point scanning in- | [Scanopties configureren in Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Scannen | Volledige scan uitvoeren op netwerkstations met kaart | [Scanopties configureren in Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Scannen | Archiefbestanden scannen | [Scanopties configureren in Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Scannen | Netwerkbestanden scannen | [Scanopties configureren in Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Scannen | Scanpakket uitvoerbare bestanden | [Scanopties configureren in Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Scannen | Verwisselbare stations scannen | [Scanopties configureren in Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Scannen | De maximale diepte opgeven voor het scannen van archiefbestanden | [Scanopties configureren in Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Scannen | Het maximale percentage cpu-gebruik opgeven tijdens een scan | [Scanopties configureren in Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Scannen | De maximale grootte opgeven van archiefbestanden die moeten worden gescand | [Scanopties configureren in Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Scannen | De dag van de week opgeven om een geplande scan uit te voeren | [Geplande scans configureren voor Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Scannen | Geef het interval op om snelle scans per dag uit te voeren | [Geplande scans configureren voor Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Scannen | Het scantype opgeven dat moet worden gebruikt voor een geplande scan | [Geplande scans configureren voor Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Scannen | De tijd voor een dagelijkse snelle scan opgeven | [Geplande scans configureren voor Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Scannen | De tijd van de dag opgeven om een geplande scan uit te voeren | [Geplande scans configureren voor Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Scannen | De geplande scan alleen starten wanneer de computer is aan, maar niet in gebruik is | [Geplande scans configureren voor Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Beveiligingsintelligentie-updates | Beveiligingsinformatie-updates van Microsoft Update toestaan | [Updates beheren voor mobiele apparaten en virtuele machines (VM's)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| Beveiligingsintelligentie-updates | Beveiligingsintelligentie-updates toestaan wanneer u op de batterij werkt | [Updates beheren voor mobiele apparaten en virtuele machines (VM's)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| Beveiligingsintelligentie-updates | Meldingen toestaan om rapporten op basis van definities uit te schakelen naar Microsoft MAPS | [Op basis van gebeurtenissen afgedwongen updates beheren](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Beveiligingsintelligentie-updates | Realtime beveiligingsintelligentie-updates toestaan op basis van rapporten voor Microsoft MAPS | [Op basis van gebeurtenissen afgedwongen updates beheren](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Beveiligingsintelligentie-updates | Controleren op de meest recente definities van virussen en spyware bij het opstarten | [Op basis van gebeurtenissen afgedwongen updates beheren](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Beveiligingsintelligentie-updates | Bestandsaandelen definiëren voor het downloaden van beveiligingsinformatie-updates | [Beveiligings- Microsoft Defender Antivirus beveiligings- en beveiligingsinformatie-updates beheren](manage-protection-updates-microsoft-defender-antivirus.md) |
| Beveiligingsintelligentie-updates | Het aantal dagen definiëren waarna een update voor beveiligingsinformatie vereist is | [Updates beheren voor eindpunten die verouderd zijn](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Beveiligingsintelligentie-updates | Het aantal dagen definiëren voordat spywaredefinities als verouderd worden beschouwd | [Updates beheren voor eindpunten die verouderd zijn](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Beveiligingsintelligentie-updates | Het aantal dagen definiëren voordat virusdefinities als verouderd worden beschouwd | [Updates beheren voor eindpunten die verouderd zijn](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Beveiligingsintelligentie-updates | De volgorde van bronnen definiëren voor het downloaden van beveiligingsinformatie-updates | [Beveiligings- Microsoft Defender Antivirus beveiligings- en beveiligingsinformatie-updates beheren](manage-protection-updates-microsoft-defender-antivirus.md) |
| Beveiligingsintelligentie-updates | Beveiligingsintelligentie-update starten bij opstarten | [Op basis van gebeurtenissen afgedwongen updates beheren](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Beveiligingsintelligentie-updates | Geef de dag van de week op om te controleren op beveiligingsinformatie-updates | [Beheren wanneer beveiligingsupdates moeten worden gedownload en toegepast](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Beveiligingsintelligentie-updates | Geef het interval op om te controleren op beveiligingsinformatie-updates | [Beheren wanneer beveiligingsupdates moeten worden gedownload en toegepast](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Beveiligingsintelligentie-updates | Geef de tijd op om te controleren op beveiligingsinformatie-updates | [Beheren wanneer beveiligingsupdates moeten worden gedownload en toegepast](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Beveiligingsintelligentie-updates | Scannen in-/uit-/uit-2014 in- en | [Geplande scans configureren voor Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Bedreigingen | Waarschuwingsniveaus opgeven waarop standaardactie niet moet worden ondernomen wanneer deze wordt gedetecteerd | [Herstel configureren voor Microsoft Defender Antivirus scans](configure-remediation-microsoft-defender-antivirus.md) |
| Bedreigingen | Geef bedreigingen op waarop standaardactie niet moet worden ondernomen wanneer deze worden gedetecteerd | [Herstel configureren voor Microsoft Defender Antivirus scans](configure-remediation-microsoft-defender-antivirus.md) |


## <a name="related-articles"></a>Verwante artikelen

- [Referentieonderwerpen voor beheer- en configuratiehulpmiddelen](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
