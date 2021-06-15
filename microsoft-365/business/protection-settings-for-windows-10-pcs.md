---
title: Instellingen voor apparaatbeveiliging bewerken of maken voor Windows 10 pc's
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Meer informatie over instellingen die beschikbaar zijn in Microsoft 365 voor bedrijven om uw Windows 10 beveiligen.
ms.openlocfilehash: 4859681d5e71a61b8a5dd58114bce899f485967a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925314"
---
# <a name="edit-or-create-device-protection-settings-for-windows-10-pcs"></a>Instellingen voor apparaatbeveiliging bewerken of maken voor Windows 10 pc's

Dit artikel is van toepassing op Microsoft 365 Business Premium.

Nadat u standaardbeveiligingsinstellingen Windows ingesteld op de pagina Setup, kunt u nieuwe instellingen toevoegen die van toepassing zijn op alle gebruikers of een set gebruikers. U kunt ook alle gemaakte bewerkingen bewerken.

## <a name="create-protection-settings-for-windows-10-devices"></a>Beveiligingsinstellingen maken voor Windows 10 apparaten

Bekijk een video over het beveiligen van Windows 10 apparaten met Microsoft 365 Business Premium:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
2. Kies in de  linkernavigatienavigatie de optie \> **Apparatenbeleid** \> **toevoegen.**
3. Voer in het deelvenster **Beleid toevoegen** een unieke naam in voor dit beleid. 
4. Kies onder **Beleidstype** **Configuratie voor Windows 10-apparaat**.
5. Vouw **Windows 10-apparaten beveiligen** uit \> configureer de instellingen op de manier die u wilt. Zie Beschikbare instellingen [voor meer informatie.](#available-settings) 
    
    U kunt altijd de koppeling **Standaardwaarden herstellen** gebruiken om terug te keren naar de standaardinstelling. 
    
    ![Add policy pane with Windows 10 Device configuration selected](../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. Bepaal nu **Voor wie zijn deze instellingen?** Als u niet de standaardbeveiligingsgroep **Alle gebruikers** wilt gebruiken, kies **Wijzigen**, zoek de beveiligingsgroep die deze instellingen ontvangt \> **Selecteer**.
7. Kies ten slotte, **Klaar** om het beleid op te slaan en dit toe te wijzen aan apparaten. 

## <a name="edit-windows-10-protection-settings"></a>Beveiligingsinstellingen Windows 10 bewerken
 
1. Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.     
2. Kies in de  linkernavigatienavigatie de optie \> **Apparatenbeleid.**
1. Kies een bestaand Windows apparaatbeleid en vervolgens **Bewerken.**
1. Kies **Bewerken** naast een instelling die u wilt wijzigen en klik vervolgens op **Opslaan.**

## <a name="available-settings"></a>Beschikbare instellingen

Alle instellingen zijn standaard **ingeschakeld**. De volgende instellingen zijn beschikbaar.
  
Zie Hoe kunnen beveiligingsfuncties [in Microsoft 365 Premium Intune-instellingen](map-protection-features-to-intune-settings.md)voor meer informatie. 


|Instelling  <br/> |Beschrijving  <br/> |
|:-----|:-----|
|Bescherm pc's tegen virussen en andere bedreigingen met Windows Defender-antivirussoftware  <br/> |Daarvoor moet Windows Defender-antivirussoftware zijn ingeschakeld om pc's te beschermen tegen de gevaren die verbinding met internet met zich meebrengt.  <br/> |
|Bescherm pc's tegen internetdreigingen in Microsoft Edge  <br/> |Hiermee worden instellingen in Edge ingeschakeld die gebruikers helpen beschermen tegen schadelijke websites en downloads.  <br/> |
|Gebruik regels die de kwetsbaarheid voor aanvallen van apparaten verminderen  <br/> |Wanneer deze optie is ingeschakeld, kunnen hiermee acties en apps worden geblokkeerd die doorgaans door malware worden gebruikt om apparaten te infecteren. Deze instelling is alleen beschikbaar als Windows Defender Antivirus is ingesteld op Aan. Zie [Kwetsbaarheid voor aanvallen verminderen](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) voor meer informatie.  <br/> |
|Mappen beschermen tegen bedreigingen, zoals ransomware  <br/> |Deze instelling maakt gebruik van gecontroleerde mappentoegang om bedrijfsgegevens te beschermen tegen wijzigingen die worden aangebracht door verdachte of kwaadaardige apps, zoals ransomware. Deze typen apps worden geblokkeerd zodat er geen wijzigingen in beveiligde mappen kunnen worden aangebracht. Deze instelling is alleen beschikbaar als Windows Defender Antivirus is ingesteld op Aan. Zie [Mappen beveiligen met gecontroleerde maptoegang](/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) voor meer informatie.  <br/> |
|Netwerktoegang tot mogelijke schadelijke inhoud op internet voorkomen  <br/> |Gebruik deze instelling om uitgaande gebruikersverbindingen te blokkeren met internetlocaties met een lage reputatie die phishingpraktijken, exploits of andere schadelijke inhoud kunnen hosten. Deze instelling is alleen beschikbaar als Windows Defender Antivirus is ingesteld op **Aan.** Zie Uw netwerk [beveiligen voor meer informatie.](/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus)  <br/> |
|Bestanden en mappen op pc's beschermen tegen onbevoegde toegang met BitLocker  <br/> |Bitlocker beschermt gegevens door de harde schijven van de computer te versleutelen en te beschermen tegen blootstelling van gegevens als een computer zoekraakt of wordt gestolen. Zie Veelgestelde vragen [over Bitlocker voor meer informatie.](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)  <br/> |
|Gebruikers toestaan om apps te downloaden vanuit de Microsoft Store  <br/> |Hiermee kunnen gebruikers apps downloaden en installeren vanuit de Microsoft Store. Omdat apps kunnen variëren van spelletjes tot productiviteitsprogramma's, laten we deze instelling **ingeschakeld**, maar u kunt de instelling uitschakelen voor extra beveiliging.  <br/> |
|Gebruikers toestaan om Cortana te openen  <br/> |Cortana kan erg nuttig zijn! Cortana kan instellingen voor u in- of uitschakelen, aanwijzingen geven en ervoor zorgen dat u op tijd bent voor afspraken, dus deze instelling blijft standaard **ingeschakeld.**  <br/> |
|Gebruikers toestaan om Windows-tips en reclame van Microsoft te ontvangen  <br/> |Windows-tips kunnen handig zijn en gebruikers op weg helpen wanneer er nieuwe functies beschikbaar zijn.  <br/> |
|Windows 10-apparaten automatisch bijwerken  <br/> |Hiermee ontvangen Windows 10-apparaten automatisch de nieuwste updates.  <br/> |
|Apparaatscherm uitschakelen indien inactief gedurende deze periode  <br/> |Hiermee weet u zeker dat bedrijfsgegevens beveiligd zijn als een gebruiker niet actief is. Een gebruiker kan in een openbare locatie werken, zoals een café, en even weggaan of afgeleid worden, waardoor de informatie op het apparaat gemakkelijk door onbekenden bekeken kan worden. Met deze instelling kunt u bepalen hoelang de gebruiker inactief kan zijn voordat het scherm wordt uitgeschakeld.  <br/> |