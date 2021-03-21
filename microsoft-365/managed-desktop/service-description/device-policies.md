---
title: Apparaatconfiguratie
description: Meer informatie over het standaardbeleid dat is toegepast op Beheerde bureaubladapparaten van Microsoft.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e4f07adb051dde24d374055d206955ad61df432a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920490"
---
# <a name="device-configuration"></a>Apparaatconfiguratie


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Wanneer er een nieuw Microsoft Managed Desktop-apparaat wordt ingesteld, zorgen we ervoor dat de juiste configuratie is geoptimaliseerd voor Microsoft Managed Desktop. Deze configuratie bevat een set standaardbeleidsregels die zijn ingesteld als onderdeel van het onboardingproces. Dit beleid wordt zo mogelijk geleverd met MDM (Mobile Device Management). Zie Mobile Device Management voor [meer informatie.](/windows/client-management/mdm/) 

>[!NOTE]
>Als u conflicten wilt voorkomen, wijzigt u dit beleid niet.

Apparaten krijgen een handtekeningafbeelding en worden vervolgens lid van het Azure Active Directory-domein wanneer de eerste gebruiker zich aan meldt. Het apparaat installeert automatisch vereiste beleidsregels en toepassingen zonder tussenkomst van uw IT-personeel.

## <a name="default-policies"></a>Standaardbeleid

In deze tabel worden de standaardbeleidsregels belicht die worden toegepast op alle beheerde bureaubladapparaten van Microsoft tijdens het inrichten van apparaten. Alle gedetecteerde wijzigingen die niet zijn goedgekeurd door het Microsoft Managed Desktop Operations Team voor objecten die worden beheerd door Microsoft Managed Desktop, worden terugverdiend.

Beleid | Beschrijving
--- | ---
Beveiligingslijn | [Microsoft-beveiligingslijn](/windows/device-security/windows-security-baselines) voor MDM is geconfigureerd voor alle beheerde bureaubladapparaten van Microsoft. Deze basislijn is de industriestandaardconfiguratie. De app wordt openbaar uitgebracht, goed getest en is beoordeeld door beveiligingsexperts van Microsoft om Microsoft Managed Desktop-apparaten en -apps veilig te houden op de moderne werkplek. <br><br>Als u bedreigingen wilt beperken in het voortdurend veranderende landschap van beveiligingsrisico's, wordt de Microsoft-beveiligingslijn bijgewerkt en geïmplementeerd op Microsoft Managed Desktop-apparaten met elke Windows 10-functieupdate.<br><br>Zie Windows-beveiligingslijnlijnen voor meer [informatie.](/windows/security/threat-protection/windows-security-baselines)
Aanbevolen beveiligingssjabloon voor Microsoft Managed Desktop | Een reeks aanbevolen wijzigingen in de beveiligingslijn die de gebruikerservaring optimaliseren.  Deze wijzigingen worden gedocumenteerd in [het beveiligings-addendum.](#security-addendum) Updates voor het beleids-addendum vinden zo nodig plaats.  
Implementatie bijwerken | Gebruik Windows Update voor Bedrijven om een geleidelijke implementatie van software-updates uit te voeren. IT-beheerders kunnen de instellingen voor het beleid van de implementatiegroep niet wijzigen. Zie Hoe updates worden verwerkt in Microsoft Managed Desktop voor meer informatie over de implementatie op [basis van groepen.](updates.md)
Verbindingen met een meter | Updates via verbindingen met een datameter (zoals LTE-netwerken) zijn standaard uitgeschakeld, maar elke gebruiker kan deze functie onafhankelijk in schakelen in Instellingen **> Updates > Geavanceerde opties.** Als u wilt toestaan dat alle gebruikers updates [](../working-with-managed-desktop/admin-support.md)kunnen inschakelen via verbindingen met een datameter, dient u een wijzigingsaanvraag in, waarmee deze instelling voor alle apparaten wordt ingeschakeld.
| Apparaat compliance | Dit beleid is geconfigureerd voor alle beheerde bureaubladapparaten van Microsoft. Een apparaat wordt gerapporteerd als niet-compatibel wanneer het afdrijft van de vereiste beveiligingsconfiguratie.

## <a name="windows-diagnostic-data"></a>Diagnostische gegevens van Windows

 Apparaten worden ingesteld voor het verstrekken van uitgebreide diagnostische gegevens aan Microsoft onder een bekende commerciële id. It-beheerders kunnen deze instellingen niet wijzigen als onderdeel van Microsoft Managed Desktop. Voor klanten in GDPR-regio's (General Data Protection Regulation) kunnen gebruikers het niveau van de verstrekte diagnostische gegevens verlagen, maar de service wordt beperkt. Microsoft Managed Desktop kan bijvoorbeeld niet de gegevens verzamelen die nodig zijn om itereren op instellingen en beleidsregels om optimaal te voldoen aan de prestaties en beveiligingsbehoeften. Zie Diagnostische gegevens van Windows configureren [in uw organisatie voor meer informatie.](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>Beveiligings-addendum

 In deze sectie worden de beleidsregels beschreven die worden geïmplementeerd naast het standaardbeleid voor beheerd bureaublad van Microsoft dat wordt vermeld in [standaardbeleid.](#default-policies) Deze configuratie is ontworpen met financiële services en sterk gereguleerde bedrijfstakken in gedachten, met optimalisatie voor de hoogste beveiliging en met behoud van de productiviteit van de gebruiker.

 ### <a name="additional-security-policies"></a>Extra beveiligingsbeleid

 Deze beleidsregels worden toegevoegd om de beveiliging voor sterk gereguleerde bedrijfstakken te verhogen. 
 - **Beveiligingscontrole:** Microsoft controleert apparaten met [Microsoft Defender voor Eindpunt.](/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) Als er een bedreiging wordt gedetecteerd, zal Microsoft de klant op de hoogte stellen, het apparaat isoleren en het probleem op afstand verhelpen. 
 - **PowerShell V2 uitschakelen:** Microsoft heeft PowerShell V2 in augustus 2017 verwijderd. Deze functie is uitgeschakeld op alle beheerde bureaubladapparaten van Microsoft. Zie [Windows PowerShell 2.0 Deprecation](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)voor meer informatie over deze wijziging.