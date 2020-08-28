---
title: Beveiligingsinstellingen voor apparaten bewerken of maken voor Windows 10-Pc's
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Meer informatie over de instellingen die beschikbaar zijn in Microsoft 365 voor bedrijven om Windows 10-apparaten te beveiligen.
ms.openlocfilehash: bd992113403c7134fb32bc6cced5bf216843241b
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289150"
---
# <a name="edit-or-create-device-protection-settings-for-windows-10-pcs"></a>Beveiligingsinstellingen voor apparaten bewerken of maken voor Windows 10-Pc's

Dit artikel is van toepassing op Microsoft 365 Business Premium.

Nadat u de standaardinstellingen voor Windows-beveiliging instellen hebt ingesteld op de pagina instellen, kunt u nieuwe items toevoegen die van toepassing zijn op alle gebruikers of voor een set gebruikers. U kunt ook een van de gemaakte wijzigingen bewerken.

## <a name="create-protection-settings-for-windows-10-devices"></a>Beveiligingsinstellingen voor Windows 10-apparaten maken

Bekijk een video over het beveiligen van Windows 10-apparaten met Microsoft 365 Business Premium:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
2. Kies in het linkernavigatievenster de optie **apparaten** \> **beleid** \> **toevoegen**.
3. Voer in het deelvenster **Beleid toevoegen** een unieke naam in voor dit beleid. 
4. Kies onder **Beleidstype** **Configuratie voor Windows 10-apparaat**.
5. Vouw **Windows 10-apparaten beveiligen** uit \> configureer de instellingen op de manier die u wilt. Zie [beschikbare instellingen](#available-settings)voor meer informatie. 
    
    U kunt altijd de koppeling **Standaardwaarden herstellen** gebruiken om terug te keren naar de standaardinstelling. 
    
    ![Add policy pane with Windows 10 Device configuration selected](../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. Bepaal nu **Voor wie zijn deze instellingen?** Als u niet de standaardbeveiligingsgroep **Alle gebruikers** wilt gebruiken, kies **Wijzigen**, zoek de beveiligingsgroep die deze instellingen ontvangt \> **Selecteer**.
7. Kies ten slotte, **Klaar** om het beleid op te slaan en dit toe te wijzen aan apparaten. 

## <a name="edit-windows-10-protection-settings"></a>Beveiligingsinstellingen voor Windows 10 bewerken
 
1. Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.     
2. Kies in het linkernavigatievenster de optie **apparaten** \> **beleid** .
1. Kies een bestaand beleid voor Windows-apparaten en klik vervolgens op **bewerken**.
1. Kies **bewerken** naast een instelling die u wilt wijzigen en klik vervolgens op **Opslaan**.

## <a name="available-settings"></a>Beschikbare instellingen

Alle instellingen zijn standaard **ingeschakeld**. De volgende instellingen zijn beschikbaar.
  
Zie [hoe beveiligingsfuncties in Microsoft 365 Premium zijn toegewezen aan intune-instellingen](map-protection-features-to-intune-settings.md)voor meer informatie. 
  
|||
|:-----|:-----|
|Instelling  <br/> |Beschrijving  <br/> |
|Bescherm pc's tegen virussen en andere bedreigingen met Windows Defender-antivirussoftware  <br/> |Daarvoor moet Windows Defender-antivirussoftware zijn ingeschakeld om pc's te beschermen tegen de gevaren die verbinding met internet met zich meebrengt.  <br/> |
|Bescherm pc's tegen internetdreigingen in Microsoft Edge  <br/> |Hiermee worden instellingen in Edge ingeschakeld die gebruikers helpen beschermen tegen schadelijke websites en downloads.  <br/> |
|Gebruik regels die de kwetsbaarheid voor aanvallen van apparaten verminderen  <br/> |Wanneer deze optie is ingeschakeld, kunnen hiermee acties en apps worden geblokkeerd die doorgaans door malware worden gebruikt om apparaten te infecteren. Deze instelling is alleen beschikbaar als Windows Defender Antivirus is ingesteld op Aan. Zie [Kwetsbaarheid voor aanvallen verminderen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) voor meer informatie.  <br/> |
|Mappen beschermen tegen bedreigingen, zoals ransomware  <br/> |Deze instelling maakt gebruik van gecontroleerde mappentoegang om bedrijfsgegevens te beschermen tegen wijzigingen die worden aangebracht door verdachte of kwaadaardige apps, zoals ransomware. Deze typen apps worden geblokkeerd zodat er geen wijzigingen in beveiligde mappen kunnen worden aangebracht. Deze instelling is alleen beschikbaar als Windows Defender Antivirus is ingesteld op Aan. Zie [mappen beveiligen met Controlled map Access](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) voor meer informatie.  <br/> |
|Netwerktoegang tot mogelijke schadelijke inhoud op internet voorkomen  <br/> |Met deze instelling kunt u uitgaande verbindingen van gebruikers blokkeren naar Internet locaties op basis van een goede reputatie, waarop u phishing, exploits of andere schadelijke inhoud kunt hosten. Deze instelling is alleen beschikbaar als Windows Defender antivirus is ingesteld op **aan**. Zie [uw netwerk beveiligen](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus)voor meer informatie.  <br/> |
|Bestanden en mappen op pc's beschermen tegen onbevoegde toegang met BitLocker  <br/> |Bitlocker beschermt gegevens door de harde schijven van de computer te versleutelen en te beschermen tegen blootstelling van gegevens als een computer zoekraakt of wordt gestolen. Raadpleeg voor meer informatie [BitLocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000).  <br/> |
|Gebruikers toestaan om apps te downloaden vanuit de Microsoft Store  <br/> |Hiermee kunnen gebruikers apps downloaden en installeren vanuit de Microsoft Store. Omdat apps kunnen variëren van spelletjes tot productiviteitsprogramma's, laten we deze instelling **ingeschakeld**, maar u kunt de instelling uitschakelen voor extra beveiliging.  <br/> |
|Gebruikers toestaan om Cortana te openen  <br/> |Cortana kan erg handig zijn. Cortana kan instellingen voor u in-of uitschakelen, een routebeschrijving opgeven en ervoor zorgen dat u op de hoogte bent van afspraken, zodat we **deze instelling standaard** behouden.  <br/> |
|Gebruikers toestaan om Windows-tips en reclame van Microsoft te ontvangen  <br/> |Windows-tips kunnen handig zijn en gebruikers op weg helpen wanneer er nieuwe functies beschikbaar zijn.  <br/> |
|Windows 10-apparaten automatisch bijwerken  <br/> |Hiermee ontvangen Windows 10-apparaten automatisch de nieuwste updates.  <br/> |
|Apparaatscherm uitschakelen indien inactief gedurende deze periode  <br/> |Hiermee weet u zeker dat bedrijfsgegevens beveiligd zijn als een gebruiker niet actief is. Een gebruiker kan in een openbare locatie werken, zoals een café, en even weggaan of afgeleid worden, waardoor de informatie op het apparaat gemakkelijk door onbekenden bekeken kan worden. Met deze instelling kunt u bepalen hoelang de gebruiker inactief kan zijn voordat het scherm wordt uitgeschakeld.  <br/> |
