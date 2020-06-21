---
title: Apparaatconfiguratie
description: Meer informatie over het standaardbeleid dat is toegepast op Microsoft Managed Desktop-apparaten.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e0e5c003ed78b78c5f259eae7e08478d523b5b12
ms.sourcegitcommit: 51e47ca4b355436a2ad3deb154060eb1927428e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44773785"
---
# <a name="device-configuration"></a>Apparaatconfiguratie


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Wanneer een nieuw Microsoft Managed Desktop-apparaat wordt ingesteld, zorgen we ervoor dat de juiste configuratie is geoptimaliseerd voor Microsoft Managed Desktop. Dit omvat een set standaardbeleidsregels die zijn ingesteld als onderdeel van het onboardingproces. Deze beleidsregels worden waar mogelijk geleverd met Behulp van Mobile Device Management (MDM). Zie [Beheer van mobiele apparaten](https://docs.microsoft.com/windows/client-management/mdm/)voor meer informatie. 

>[!NOTE]
>Om conflicten te voorkomen, wijzig dit beleid niet.

Apparaten komen met een handtekeningafbeelding en worden lid van het Azure Active Directory-domein wanneer de eerste gebruiker zich aanmeldt. Het apparaat installeert automatisch het vereiste beleid en de vereiste toepassingen zonder tussenkomst van uw IT-personeel.

## <a name="default-policies"></a>Standaardbeleid

In deze tabel wordt het standaardbeleid weergegeven dat tijdens het inrichten van apparaten op alle Microsoft Managed Desktop-apparaten wordt toegepast. Alle gedetecteerde wijzigingen die niet zijn goedgekeurd door Microsoft Managed Desktop Operations Team in objecten die worden beheerd door Microsoft Managed Desktop, worden teruggezet.

Beleid | Beschrijving
--- | ---
Basislijn voor beveiliging | [Microsoft-beveiligingsbasislijn](https://docs.microsoft.com/windows/device-security/windows-security-baselines) voor MDM is geconfigureerd voor alle Microsoft Managed Desktop-apparaten. Deze basislijn is de industriestandaardconfiguratie. Het is openbaar vrijgegeven, goed getest, en is beoordeeld door Microsoft security experts om Microsoft Managed Desktop apparaten en apps veilig te houden in de moderne werkplek. <br><br>Om bedreigingen in het voortdurend evoluerende beveiligingsrisicolandschap te beperken, wordt de beveiligingsbasislijn van Microsoft bijgewerkt en geïmplementeerd voor Microsoft Managed Desktop-apparaten met elke Windows 10-functie-update.<br><br>Zie [De beveiligingsbasislijnen van Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)voor meer informatie .
Aanbevolen beveiligingssjabloon voor Microsoft Managed Desktop | Een reeks aanbevolen wijzigingen in de beveiligingsbasislijn die de gebruikerservaring optimaliseren.  Deze wijzigingen worden gedocumenteerd in [het beveiligingsvoegser](#security-addendum). Updates van het beleidsvoegsingsdum vinden plaats op basis van de gewenste gegevens.  
Implementatie bijwerken | Gebruik Windows Update voor Bedrijven om de geleidelijke implementatie van software-updates uit te voeren. IT-beheerders kunnen de instellingen voor het beleid van de implementatiegroep niet wijzigen. Zie Hoe updates worden verwerkt [in Microsoft Managed Desktop](updates.md)voor meer informatie over groepsimplementatie.
Verbindingen met datalimiet | Updates via verbindingen met datalimiet (zoals LTE-netwerken) zijn standaard uitgeschakeld, hoewel elke gebruiker deze functie onafhankelijk kan inschakelen in **Instellingen > Updates > Geavanceerde opties**. Als u alle gebruikers wilt toestaan updates in te schakelen via verbindingen met datalimiet, [dient u een wijzigingsverzoek](../working-with-managed-desktop/admin-support.md)in, waarmee deze instelling voor alle apparaten wordt ingeschakeld.
| Naleving van het apparaat | Dit beleid is geconfigureerd voor alle Microsoft Managed Desktop-apparaten. Een apparaat wordt gerapporteerd als niet-compatibel wanneer het afdrijft van onze vereiste beveiligingsconfiguratie.

## <a name="diagnostic-data"></a>Diagnostische gegevens

 Apparaten worden ingesteld om verbeterde diagnostische gegevens te verstrekken aan Microsoft onder een bekende commerciële id. Als onderdeel van Microsoft Managed Desktop kunnen IT-beheerders deze instellingen niet wijzigen. Voor klanten in de algemene verordening gegevensbescherming (AVG) kunnen eindgebruikers het niveau van diagnostische gegevens dat wordt verstrekt verminderen, maar er zal een vermindering van de service zijn. Microsoft Managed Desktop kan bijvoorbeeld niet de gegevens verzamelen die nodig zijn om te herhalen over instellingen en beleidsregels om zo goed mogelijk aan de prestaties en beveiligingsbehoeften te voldoen. Zie Diagnostische gegevens van Windows configureren in uw organisatie voor meer [informatie.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>Beveiligingsvoegseda

 In deze sectie wordt het beleid beschreven dat wordt geïmplementeerd naast het standaardbeleid voor Microsoft Managed Desktop dat wordt vermeld in [standaardbeleid](#default-policies). Deze configuratie is ontworpen met financiële services en sterk gereguleerde industrieën in het achterhoofd, optimaliseren voor de hoogste beveiliging met behoud van de productiviteit van de gebruiker.

 ### <a name="additional-security-policies"></a>Aanvullend beveiligingsbeleid

 Dit beleid wordt toegevoegd om de veiligheid voor sterk gereguleerde industrieën te verhogen. 
 - **Beveiligingscontrole**: Microsoft controleert apparaten met Behulp van [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Als een bedreiging wordt gedetecteerd, zal Microsoft de klant hiervan op de hoogte stellen, het apparaat isoleren en het probleem op afstand verhelpen. 
 - **PowerShell V2 uitschakelen**: Microsoft heeft PowerShell V2 in augustus 2017 verwijderd. Deze functie is uitgeschakeld op alle Microsoft Managed Desktop-apparaten. Zie [Windows PowerShell 2.0 Deprecation](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)voor meer informatie over deze wijziging.
