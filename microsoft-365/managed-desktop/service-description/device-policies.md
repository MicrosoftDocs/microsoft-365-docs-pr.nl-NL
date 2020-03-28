---
title: Apparaatconfiguratie
description: Meer informatie over het standaardbeleid dat wordt toegepast op Microsoft Managed Desktop-apparaten.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 35c24153bdacbdc0d07d65b508e66878bd0045e4
ms.sourcegitcommit: ce6121a8e3ca7438071d73b0c76e2b6f33ac1cf7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/27/2020
ms.locfileid: "43029826"
---
# <a name="device-configuration"></a>Apparaatconfiguratie


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Wanneer een nieuw Microsoft Managed Desktop-apparaat wordt ingesteld, zorgen we ervoor dat het de juiste configuratie heeft die is geoptimaliseerd voor Microsoft Managed Desktop. Dit omvat een set standaardbeleidsregels die zijn ingesteld als onderdeel van het onboarding-proces. Dit beleid wordt waar mogelijk geleverd met Mobile Device Management (MDM). Zie [Mobile Device Management](https://docs.microsoft.com/windows/client-management/mdm/)voor meer informatie. 

>[!NOTE]
>Om conflicten te voorkomen, wijzigt u dit beleid niet.

Apparaten komen met een handtekeningafbeelding en sluiten vervolgens aan bij het Azure Active Directory-domein wanneer de eerste gebruiker zich aanmeldt. Het apparaat installeert automatisch het vereiste beleid en de vereiste toepassingen zonder tussenkomst van uw IT-personeel.

## <a name="default-policies"></a>Standaardbeleid

In deze tabel wordt het standaardbeleid weergegeven dat wordt toegepast op alle Microsoft Managed Desktop-apparaten tijdens het inrichten van apparaten. Alle gedetecteerde wijzigingen die niet zijn goedgekeurd door Microsoft Managed Desktop Operations Team voor objecten die door Microsoft Managed Desktop worden beheerd, worden teruggezet.

Beleid | Beschrijving
--- | ---
Basislijn voor beveiliging | [Microsoft-beveiligingsbasislijn](https://docs.microsoft.com/windows/device-security/windows-security-baselines) voor MDM is geconfigureerd voor alle Microsoft Managed Desktop-apparaten. Deze basislijn is de industriestandaardconfiguratie. Het is openbaar vrijgegeven, goed getest, en is beoordeeld door Microsoft security experts om Microsoft Managed Desktop apparaten en apps veilig te houden in de moderne werkplek. <br><br>Om bedreigingen in het voortdurend evoluerende beveiligingsrisicolandschap te beperken, wordt de microsoft-beveiligingsbasislijn bijgewerkt en geïmplementeerd op Microsoft Managed Desktop-apparaten met elke Windows 10-functie-update.<br><br>Zie [Basislijn beveiliging voor Windows 10 voor](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/)meer informatie.
Aanbevolen beveiligingssjabloon voor Microsoft Managed Desktop | Een reeks aanbevolen wijzigingen in de beveiligingsbasislijn die de gebruikerservaring optimaliseren.  Deze wijzigingen zijn gedocumenteerd in [het beveiligingsaddendum](#security-addendum). Updates van het beleidsaddendum vinden naar behoefte plaats.  
Implementatie bijwerken | Gebruik Windows Update voor Bedrijven om de geleidelijke implementatie van software-updates uit te voeren. IT-beheerders kunnen de instellingen voor het beleid voor implementatiegroepen niet wijzigen. Zie Hoe updates worden verwerkt [in Microsoft Managed Desktop](updates.md)voor meer informatie over groepsimplementatie.
Verbindingen met datalimiet | Updates via verbindingen met datalimiet (zoals LTE-netwerken) zijn standaard uitgeschakeld, maar elke gebruiker kan deze functie onafhankelijk inschakelen in **Instellingen > Updates > Geavanceerde opties.** Als u alle gebruikers wilt toestaan updates in te schakelen via verbindingen met datalimiet, [dient u een wijzigingsverzoek](../working-with-managed-desktop/admin-support.md)in, waarin deze instelling voor alle apparaten wordt ingeschakeld.
| Naleving van het apparaat | Deze beleidsregels zijn geconfigureerd voor alle Microsoft Managed Desktop-apparaten. Een apparaat wordt gerapporteerd als niet-compatibel wanneer het afdrijft van onze vereiste beveiligingsconfiguratie.

## <a name="diagnostic-data"></a>Diagnostische gegevens

 Apparaten worden ingesteld om verbeterde diagnostische gegevens aan Microsoft te verstrekken onder een bekende commerciële id. Als onderdeel van Microsoft Managed Desktop kunnen IT-beheerders deze instellingen niet wijzigen. Voor klanten in de algemene verordening gegevensbescherming (GDPR) regio's, kunnen eindgebruikers het niveau van diagnostische gegevens die wordt verstrekt verminderen, maar er zal een vermindering van de service. Microsoft Managed Desktop kan bijvoorbeeld niet de gegevens verzamelen die nodig zijn om instellingen en beleidsregels te herhalen om zo goed mogelijk te voldoen aan de prestatie- en beveiligingsbehoeften. Zie Diagnostische gegevens van Windows configureren in uw organisatie voor meer [informatie.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>Beveiligingsaddendum

 In deze sectie worden de beleidsregels beschreven die worden geïmplementeerd naast het standaardbeleid voor Microsoft Managed Desktop dat wordt weergegeven in [standaardbeleid](#default-policies). Deze configuratie is ontworpen met financiële diensten en sterk gereguleerde industrieën in het achterhoofd, optimaliseren voor de hoogste beveiliging met behoud van de productiviteit van de gebruiker.

 ### <a name="additional-security-policies"></a>Aanvullend beveiligingsbeleid

 Dit beleid wordt toegevoegd om de veiligheid voor sterk gereguleerde industrieën te verhogen. 
 - **Beveiligingscontrole:** Microsoft controleert apparaten met [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Als er een bedreiging wordt gedetecteerd, zal Microsoft de klant hiervan op de hoogte stellen, het apparaat isoleren en het probleem op afstand verhelpen. 
 - **PowerShell V2 uitschakelen**: Microsoft heeft PowerShell V2 in augustus 2017 verwijderd. Deze functie is uitgeschakeld op alle Microsoft Managed Desktop-apparaten. Zie [Windows PowerShell 2.0 Deprecation voor](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)meer informatie over deze wijziging.
