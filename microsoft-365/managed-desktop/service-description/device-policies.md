---
title: Apparaatconfiguratie
description: Meer informatie over het standaardbeleid dat wordt toegepast op Microsoft Managed Desktop-apparaten.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: d8de760fb4690af6675b67678b2441773993a8e5
ms.sourcegitcommit: 48a45b0d2c60d4d79669174f462603a43f272875
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/18/2020
ms.locfileid: "42808784"
---
# <a name="device-configuration"></a>Apparaatconfiguratie


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Wanneer een nieuw Microsoft Managed Desktop-apparaat wordt ingesteld, zorgen we ervoor dat de juiste configuratie is geoptimaliseerd voor Microsoft Managed Desktop. Dit omvat een set standaardbeleidsregels die zijn ingesteld als onderdeel van het onboarding-proces. Dit beleid wordt waar mogelijk geleverd met Behulp van Mobile Device Management (MDM). Zie [Mobile Device Management](https://docs.microsoft.com/windows/client-management/mdm/)voor meer informatie. 

>[!NOTE]
>Om conflicten te voorkomen, wijzig dit beleid niet.

Apparaten komen met een handtekeningafbeelding en sluiten zich vervolgens aan bij het Azure Active Directory-domein wanneer de eerste gebruiker zich aanmeldt. Het apparaat installeert automatisch vereist beleid en toepassingen zonder tussenkomst van uw IT-personeel.

## <a name="default-policies"></a>Standaardbeleid

In deze tabel wordt het standaardbeleid weergegeven dat wordt toegepast op alle Beheerde Bureaubladapparaten van Microsoft tijdens het inrichten van apparaten. Alle gedetecteerde wijzigingen die niet zijn goedgekeurd door Microsoft Managed Desktop Operations Team in objecten die door Microsoft Managed Desktop worden beheerd, worden teruggezet.

Beleid | Beschrijving
--- | ---
Basislijn voor beveiliging | [Microsoft-beveiligingsbasislijn](https://docs.microsoft.com/windows/device-security/windows-security-baselines) voor MDM is geconfigureerd voor alle Microsoft Managed Desktop-apparaten. Deze basislijn is de industriestandaardconfiguratie. Het is openbaar vrijgegeven, goed getest, en is beoordeeld door Microsoft security experts om Microsoft Managed Desktop apparaten en apps veilig te houden in de moderne werkplek. <br><br>Om bedreigingen in het voortdurend evoluerende landschap van beveiligingsbedreigingen te beperken, wordt de microsoft-beveiligingsbasislijn bijgewerkt en geïmplementeerd op Microsoft Managed Desktop-apparaten met elke Windows 10-functie-update.<br><br>Zie [Beveiligingsbasislijn voor Windows 10 voor](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/)meer informatie.
Microsoft Managed Desktop aanbevolen beveiligingssjabloon | Een reeks aanbevolen wijzigingen in de beveiligingsbasislijn die de gebruikerservaring optimaliseren.  Deze wijzigingen worden gedocumenteerd in [het Beveiligingsaddendum.](#security-addendum) Updates van het beleidsaddendum vinden zo nodig plaats.  
Implementatie bijwerken | Gebruik Windows Update voor Bedrijven om de geleidelijke implementatie van software-updates uit te voeren. IT-beheerders kunnen de instellingen voor het beleid van de implementatiegroep niet wijzigen. Zie Hoe updates worden verwerkt [in Microsoft Managed Desktop](updates.md)voor meer informatie over groepsimplementatie.
Diagnostische gegevens | Apparaten worden ingesteld om verbeterde diagnostische gegevens aan Microsoft te verstrekken onder een bekende commerciële id. Als onderdeel van Microsoft Managed Desktop kunnen IT-beheerders deze instellingen niet wijzigen. Voor klanten in de algemene gegevensbeschermingsverordening (GDPR)-regio's kunnen eindgebruikers het niveau van diagnostische gegevens dat wordt verstrekt verlagen, maar er zal een vermindering van de service zijn. Microsoft Managed Desktop kan bijvoorbeeld niet de gegevens verzamelen die nodig zijn om instellingen en beleidsregels te herhalen om zo goed mogelijk aan de prestaties en beveiligingsbehoeften te voldoen. Zie Diagnostische gegevens configureren van Windows in uw organisatie voor meer [informatie.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)
Verbindingen met datalimiet | Standaard worden updates via verbindingen met datalimiet (zoals LTE-netwerken) uitgeschakeld, hoewel elke gebruiker deze functie onafhankelijk kan inschakelen in **Instellingen > Updates > geavanceerde opties.** Als u alle gebruikers wilt toestaan updates in te schakelen via verbindingen met een [datalimiet, dient u een wijzigingsverzoek](../working-with-managed-desktop/admin-support.md)in, waarmee deze instelling voor alle apparaten wordt ingeschakeld.
| Naleving van het apparaat | Deze beleidsregels zijn geconfigureerd voor alle Beheerde Desktop-apparaten van Microsoft. Een apparaat wordt gerapporteerd als niet-compatibel wanneer het afdrijft van onze vereiste beveiligingsconfiguratie.

 ## <a name="security-addendum"></a>Beveiligingsaddendum

 In deze sectie wordt het beleid beschreven dat wordt geïmplementeerd naast het standaard beleid voor beheerde bureaublad van Microsoft dat wordt vermeld in [standaardbeleid](#default-policies). Deze configuratie is ontworpen met financiële services en sterk gereguleerde industrieën in het achterhoofd, optimaliseren voor de hoogste beveiliging met behoud van de productiviteit van de gebruiker.

 ### <a name="additional-security-policies"></a>Aanvullend beveiligingsbeleid

 Dit beleid wordt toegevoegd om de veiligheid voor sterk gereguleerde industrieën te verhogen. 
 - **Beveiligingscontrole**: Microsoft controleert apparaten met behulp van [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Als een bedreiging wordt gedetecteerd, zal Microsoft de klant hiervan op de hoogte stellen, het apparaat isoleren en het probleem op afstand verhelpen. 
 - **PowerShell V2 uitschakelen**: Microsoft heeft PowerShell V2 in augustus 2017 verwijderd. Deze functie is uitgeschakeld op alle Beheerde Desktop-apparaten van Microsoft. Zie [Windows PowerShell 2.0-afschaffing](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)voor meer informatie over deze wijziging.
