---
title: Apparaatconfiguratie
description: Meer informatie over de standaard beleidsregels die worden toegepast op Microsoft beheerde bureaublad apparaten.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 5533284d4a3f55a51b3017a64e4c353b4ec71352
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846226"
---
# <a name="device-configuration"></a>Apparaatconfiguratie


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Wanneer u een nieuw Microsoft-beheerd bureaublad instelt, garanderen we dat het de juiste configuratie heeft voor Microsoft Managed Desktop. Dit omvat een set standaard beleidsregels die zijn ingesteld als onderdeel van het onboarding-proces. U kunt deze beleidsregels zo nodig afleveren met behulp van MDM (Mobile Device Management). Voor meer informatie raadpleegt u [Mobile Device Management](https://docs.microsoft.com/windows/client-management/mdm/). 

>[!NOTE]
>Om conflicten te voorkomen, moet u deze beleidsregels niet aanpassen.

De apparaten worden geleverd met een Handtekeningafbeelding en vervolgens aan het Azure Active Directory-domein wanneer de eerste gebruiker zich aanmeldt. Het apparaat moet automatisch beleidsregels en toepassingen installeren zonder interventie van uw IT-personeel.

## <a name="default-policies"></a>Standaardbeleid

In deze tabel vindt u een overzicht van de standaard beleidsregels die worden toegepast op alle door Microsoft beheerde bureaublad apparaten tijdens het inrichten van apparatuur. Alle gedetecteerde wijzigingen die niet door Microsoft beheerde bureaublad activiteiten zijn goedgekeurd en objecten die door Microsoft worden beheerd bureaublad worden beheerd, worden hersteld.

Beleid | Beschrijving
--- | ---
Beveiligings basislijn | [Microsoft Security Baseline](https://docs.microsoft.com/windows/device-security/windows-security-baselines) voor MDM is geconfigureerd voor alle door Microsoft beheerde bureaublad apparaten. Deze basislijn is de industriestandaard configuratie. Het is openbaar, goed getest en is gecontroleerd door Microsoft Security experts, zodat Microsoft beheerde bureaublad apparaten en apps veilig blijven in de moderne werkplek. <br><br>Om bedreigingen te beperken in de voortdurende beveiligings bedreiging liggend, wordt de Microsoft-beveiligings basis met de onderdelenupdate van Windows 10 bijgewerkt en geïmplementeerd op Microsoft beheerde bureaublad apparaten.<br><br>Zie [Windows-beveiligings lijnen](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)voor meer informatie.
Door Microsoft beheerde bureaublad beveiligingssjabloon | Een set aanbevolen wijzigingen in de beveiligings basis die de gebruikerservaring optimaliseert.  Deze wijzigingen worden beschreven in [de beveiligings addendum](#security-addendum). Updates van de beleidsregels voor het beleid worden naar wens gelangd.  
Implementatie bijwerken | Gebruik Windows Update voor bedrijven voor het uitvoeren van geleidelijke implementatie van software-updates. IT-beheerders kunnen de instellingen voor het implementatie Groepsbeleid niet wijzigen. Zie de [manier waarop updates worden afgehandeld in Microsoft beheerde bureaubladversie](updates.md)voor meer informatie over implementatie op basis van groepen.
Verbindingen met datalimiet | Standaard worden updates via verbindingen met een datalimiet (zoals LTE-netwerken) uitgeschakeld, hoewel elke gebruiker deze functie onafhankelijk kan inschakelen bij **instellingen > updates > geavanceerde opties**. Als u wilt toestaan dat alle gebruikers updates kunnen inschakelen via verbindingen met een datalimiet, [dient u een wijzigingsaanvraag](../working-with-managed-desktop/admin-support.md)in te dienen, zodat deze instelling voor alle apparaten wordt ingeschakeld.
| Apparaatcompatibiliteit | Deze beleidsregels zijn geconfigureerd voor alle beheerde bureaublad apparaten van Microsoft. Een apparaat wordt gemeld als niet-compatibel wanneer het afkomstig is van onze benodigde beveiligingsconfiguratie.

## <a name="windows-diagnostic-data"></a>Diagnostische gegevens voor Windows

 Apparaten worden ingesteld om uitgebreide diagnostische gegevens aan Microsoft onder een bekende commerciële identificatie te geven. Als onderdeel van Microsoft Managed Desktop kunnen IT-beheerders deze instellingen niet wijzigen. Voor klanten in de algemene verordening gegevensbescherming (AVG), kunnen gebruikers het niveau van diagnostische gegevens verlagen, maar er is een minder service voor minder informatie. De gegevens die nodig zijn voor het nalopen van de instellingen en het beleid, kunnen niet door Microsoft worden beheerd. Zie [Windows diagnostische gegevens in uw organisatie configureren](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level) voor meer informatie.

## <a name="security-addendum"></a>Beveiligings addendum

 In deze sectie wordt een overzicht gegeven van de beleidsregels die worden geïmplementeerd naast het standaardbeleid voor het Microsoft-beheer dat wordt weergegeven in [standaardbeleid](#default-policies). Deze configuratie is bedoeld voor financiële services en best gereguleerde industrieën waarmee u rekening moet houden bij de beste beveiliging voor het behoud van gebruikers productiviteit.

 ### <a name="additional-security-policies"></a>Extra beveiligingsbeleid

 Deze beleidsregels worden toegevoegd om de beveiliging voor zeer gereguleerde industrieën te bevorderen. 
 - **Beveiligings monitoring** : Microsoft controleert apparaten met behulp [van Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Als een bedreiging wordt gedetecteerd, waarschuwt Microsoft de klant, isoleert het apparaat en corrigeert het probleem extern. 
 - **PowerShell V2 uitschakelen** : Microsoft verwijdert PowerShell v2 in augustus 2017. Deze functie is uitgeschakeld op alle Microsoft beheerde bureaublad apparaten. Zie voor meer informatie over deze wijziging [Windows PowerShell 2,0 afschaffing](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/).
