---
title: Hoe kunnen beveiligingsfuncties in microsoft 365 Business Premium-kaart worden toegewezen aan Intune-instellingen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 8/13/2018
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: aad21b1a-c775-469a-b89c-c5d1d59d27db
description: Lees hoe beveiligingsfuncties in de Microsoft 365 Business Premium-kaart voor Intune-instellingen bekijken. Het abonnement biedt u een licentie om Intune-instellingen te wijzigen.
ms.openlocfilehash: ce75073f748f6005a843e31f7c38d06b38a3c706
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401573"
---
# <a name="how-do-protection-features-in-microsoft-365-business-premium-map-to-intune-settings"></a>Hoe kunnen beveiligingsfuncties in microsoft 365 Business Premium-kaart worden toegewezen aan Intune-instellingen

## <a name="android-and-ios-application-protection-settings"></a>Beveiligingsinstellingen voor Android- en iOS-toepassingen

In de volgende tabel vindt u informatie over hoe de beleidsinstellingen voor Android- en iOS-toepassingen worden toegewezen aan Intune-instellingen.
  
Als u de instelling Intune wilt vinden, meldt u zich aan met uw Microsoft 365 Business Premium-beheerdersreferenties en gaat u naar **beheercentra**en **vervolgens Intune**.
  
 > [!IMPORTANT]
 > 
 > Met een Microsoft 365 Business Premium-abonnement krijgt u de licentie om alle Intune-instellingen te wijzigen. Zie [Inleiding tot Intune om aan de slag te gaan.](https://docs.microsoft.com/intune/introduction-intune)
  
Selecteer bijvoorbeeld de gewenste &mdash; beleidsnaam, Toepassingsbeleid voor Android &mdash; en kies Vervolgens **Beleidsinstellingen**.
  
Onder **Werkbestanden beveiligen bij verlies of diefstal van apparaten**
  
|**Beleidsinstelling voor Android- of iOS-toepassingen**|**Intune-instelling(en)**|
|:-----|:-----|
|Werkbestanden van een inactief apparaat verwijderen na  <br/> |Offline-interval (dagen) voordat app-gegevens worden gewist  <br/> |
|Gebruikers dwingen om werkbestanden op te slaan in OneDrive voor Bedrijven  <br/> Let op: alleen toegestaan in OneDrive voor Bedrijven  <br/> |Selecteren in welke opslagapparaten zakelijke gegevens kunnen worden opgeslagen  <br/> |
|||
   
Onder **Beheren hoe gebruikers Office-bestanden op mobiele apparaten openen**
  
|**Beleidsinstelling voor Android- of iOS-toepassingen**|**Intune-instelling(en)**|
|:-----|:-----|
|Werkbestanden van een inactief apparaat verwijderen na  <br/> |Offline-interval (dagen) voordat app-gegevens worden gewist  <br/> |
|Gebruikers dwingen om werkbestanden op te slaan in OneDrive voor Bedrijven  <br/> Let op: alleen toegestaan in OneDrive voor Bedrijven  <br/> |Selecteren in welke opslagapparaten zakelijke gegevens kunnen worden opgeslagen  <br/> |
|Werkbestanden versleutelen  <br/> |App-gegevens versleutelen  <br/> |
|Onder **Beheren hoe gebruikers Office-bestanden op mobiele apparaten openen** <br/> ||
|Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps  <br/> | Pincode vereisen voor toegang  <br/>  Hiermee wordt het volgende ingesteld:  <br/> **Eenvoudige pincode toestaan** op **Ja** <br/> **Lengte van de pincode** op 4  <br/> **Gebruik van vingerafdruk in plaats van pincode toestaan** op **Ja** <br/> **App-pincode uitschakelen wanneer de pincode van het apparaat wordt beheerd** op **Nee** <br/> |
|Pincode opnieuw instellen wanneer het inloggen vaak mislukt (dit wordt uitgeschakeld als pincode niet nodig is)  <br/> |Aantal pogingen voordat pincode opnieuw wordt ingesteld  <br/> |
|Gebruikers verplichten zich opnieuw aan te melden nadat Office-apps niet actief zijn geweest (dit is uitgeschakeld als pincode niet vereist is)  <br/> | Toegangsvereisten opnieuw controleren na (minuten)  <br/>  Hiermee wordt het volgende ingesteld:  <br/> **Timeout** wordt ingesteld op minuten  <br/>  Dit is gelijk aan het aantal minuten dat u in Microsoft 365 Business hebt ingesteld.  <br/> **Offline respijtperiode** is standaard ingesteld op 720 minuten  <br/> |
|Toegang weigeren tot werkbestanden op opengebroken of geroote apparaten  <br/> |Verhinderen dat beheerde apps worden uitgevoerd op apparaten die zijn opengebroken of geroot.  <br/> |
|Gebruikers toestaan om inhoud uit Office-apps te kopiëren naar persoonlijke apps  <br/> | Knippen, kopiëren en plakken beperken met andere apps  <br/>  Als de Microsoft 365 Business Premium-optie is ingesteld op **Aan,** worden deze drie opties ook ingesteld op **Alle apps** in Intune:  <br/> **Apps toestaan gegevens over te dragen op andere apps** <br/> **Apps toestaan gegevens te ontvangen van andere apps** <br/> **Knippen, kopiëren en plakken met andere apps beperken** <br/>  Als optie Microsoft 365 Business is ingesteld op **Aan**, dan worden alle Intune-opties als volgt ingesteld:  <br/> **Apps toestaan gegevens over te dragen op andere apps** wordt ingesteld op **Door beleid beheerde apps** <br/> **Apps toestaan gegevens te ontvangen van andere apps** wordt ingesteld op **Alle apps** <br/> **Knippen, kopiëren en plakken met andere apps beperken** wordt ingesteld op **Door beleid beheerde apps met inplakken** <br/> |
|||
   
## <a name="windows-10-app-protection-settings"></a>Beveiligingsinstellingen voor Windows 10-app

In de volgende tabel vindt u informatie over hoe de beleidsinstellingen voor Windows 10-toepassingen worden toegewezen aan Intune-instellingen.
  
Als u de instelling Intune wilt vinden, meldt u zich aan met uw Microsoft 365 Business Premium-beheerdersreferenties en gaat u naar [azure-portal](https://portal.azure.com). Selecteer **Meer services**en typ Instemt in het **filter**. Selecteer **Intune App Protection** App \> **Policy**.
  
 > [!IMPORTANT]
 >
 >Met een Microsoft 365 Business Premium-abonnement u alleen de Intune-instellingen wijzigen die worden toegewezen aan de instellingen die beschikbaar zijn in Microsoft 365 Business Premium. 
  
Als u de beschikbare instellingen wilt bekijken, selecteert u de gewenste beleidsnaam en kiest u **Vervolgens Algemene, Toewijzingen**, **Toegestane apps**, **Vrijgestelde apps,** **Vereiste instellingen**of Geavanceerde **instellingen** in het linkernavigatiedeelvenster. 
  
|**Beleidsinstelling voor Windows 10-toepassingen**|**Intune-instelling(en)**|
|:-----|:-----|
|Werkbestanden versleutelen  <br/> |**Geavanceerde instellingen** \> **Gegevensbescherming**: **Versleutelingssleutels intrekken bij het ongedaan maken van de registratie** en **Toegang tot beveiligde gegevens intrekken wanneer het apparaat wordt ingeschreven bij MDM** zijn beide ingesteld op **Aan**.  <br/> |
|Voorkomen dat gebruikers bedrijfsgegevens kopiëren naar persoonlijke bestanden  <br/> |**Verplichte instellingen** \> **Modus Windows Information Protection**. **Aan** in Microsoft 365 Business Premium maps naar: **Overrides**verbergen , **Uit** in Microsoft 365 Business Premium maps naar: **Uit**.  <br/> |
|Toegangsbeheer Office-documenten  <br/> | Als dit is ingesteld **op Aan** in Microsoft 365 Business Premium,  <br/> **Geavanceerde instellingen** \> **Toegang**, **Windows Hello voor Bedrijven gebruiken als methode om u aan te melden bij Windows** ingesteld op **Aan**, in combinatie met de volgende instellingen:  <br/> **Het minimum aantal tekens instellen dat is vereist voor de pincode** wordt ingesteld op **4**.  <br/> **Het gebruik van hoofdletters in de pincode voor Windows Hello voor Bedrijven configureren** wordt ingesteld op **Geen hoofdletters gebruiken in een pincode**.  <br/> **Het gebruik van kleine letters in de pincode voor Windows Hello voor Bedrijven configureren** wordt ingesteld op **Geen kleine letters gebruiken in een pincode**.  <br/> **Het gebruik van speciale tekens in de pincode voor Windows Hello voor Bedrijven configureren** wordt ingesteld op **Geen speciale tekens toestaan in een pincode**.  <br/> **Geef de periode (in dagen) op dat een pincode kan worden gebruikt voordat het systeem vereist dat de gebruiker wijzigt** op **0**.  <br/> **Het aantal oude pincodes dat kan worden toegewezen aan een gebruikersaccount opgeven die niet opnieuw kunnen worden gebruikt** wordt ingesteld op **0**.  <br/> **Het aantal toegestane mislukte authenticaties voordat een apparaat wordt gewist** wordt net zo ingesteld als in Microsoft 365 Business (standaardwaarde 5).  <br/> **De maximale hoeveelheid tijd (in minuten) die het apparaat niet-actief mag zijn voordat het apparaat wordt vergrendeld met een pincode of wachtwoord** wordt net zo ingesteld als in Microsoft 365 Business.  <br/> |
|Herstel of beveiligde gegevens toestaan  <br/> |**Geavanceerde instellingen** \> **Gegevensbescherming**: **Het pictogram voor ondernemingsgegevensbescherming weergeven** en **Azure RMS voor WIP gebruiken** worden ingesteld op **Aan**.  <br/> |
|Aanvullende cloudlocaties van bedrijf beschermen  <br/> |**Geavanceerde instellingen** \> **Beveiligde domeinen** en **Cloudresources** geven domeinen en SharePoint-sites weer.  <br/> |
|Bestanden die worden gebruikt door deze apps zijn beveiligd  <br/> |De lijst met beveiligde apps wordt weergegeven in **Toegestane apps**.  <br/> |
|||
   
## <a name="windows-10-device-protection-settings"></a>Beveiligingsinstellingen voor Windows 10-apparaten

In de volgende tabel vindt u informatie over hoe de apparaatconfiguratie voor Windows 10-apparaten wordt toegewezen aan Intune-instellingen.
  
Als u de instelling Intune wilt vinden, meldt u zich aan met uw Microsoft 365 Business Premium-beheerdersreferenties en gaat u naar [Azure-portal,](https://portal.azure.com)selecteert u **Meer services**en typt u Intune in het **filter**en selecteert u **Intune-configuratieprofielen** \> **voor apparaten** \> **Profiles**. Then select **Device policy for Windows 10** \> **Properties** \> **Settings**.
  
|**Beleidsinstelling voor Windows 10-apparaten**|**Intune-instelling(en)**|
|:-----|:-----|
|Bescherm pc's tegen virussen en andere bedreigingen met Windows Defender Antivirus  <br/> |Bewaking in realtime toestaan = Aan  <br/> Cloudbeveiliging toestaan = Aan  <br/> Gebruikers vragen voorbeelden te verzenden = Veilige voorbeelden automatisch verzenden (niet-persoonsgegevens standaard automatisch verzenden)  <br/> |
|Bescherm pc's tegen internetdreigingen in Microsoft Edge  <br/> |**SmartScreen** in **Instellingen van Edge-browser** wordt ingesteld op **Verplicht**.  <br/> |
|Apparaatscherm uitschakelen indien inactief gedurende (minuten)  <br/> |Maximum aantal minuten inactief voordat scherm wordt vergrendeld (minuten)  <br/> |
|Gebruikers toestaan om apps te downloaden vanuit de Microsoft Store  <br/> |Aangepast URI-beleid  <br/> |
|Gebruikers toestaan om Cortana te openen  <br/> |**Algemeen** \> **Cortana** is ingesteld om in Intune te **blokkeren** wanneer het is ingesteld om **te vertrekken** in Microsoft 365 Business Premium.  <br/> |
|Gebruikers toestaan om Windows-tips en reclame van Microsoft te ontvangen  <br/> |**Windows spotlight**, allemaal geblokkeerd als dit is ingesteld op **uit** in Microsoft 365 Business Premium.  <br/> |
|Windows 10-apparaten automatisch bijwerken  <br/> | Deze instelling staat in **Microsoft Intune** \> **Service-updates - Windows 10 Update-ringen,** kies **Updatebeleid voor Windows 10-apparaten**en vervolgens **Properties** \> **Eigenschappeninstellingen**.  <br/>  Wanneer de instelling Microsoft 365 Business Premium is ingesteld **op Aan,** zijn alle volgende instellingen ingesteld:  <br/> **Servicebranch** is ingesteld op **CB** (CBB wanneer dit is uitgeschakeld in Microsoft 365 Business Premium).  <br/> **Microsoft-productupdates** wordt ingesteld op **Toestaan**.  <br/> **Windows-stuurprogramma's** wordt ingesteld op **Toestaan**.  <br/> **Gedrag van automatische updates** wordt ingesteld op **Automatisch installeren op het tijdstip voor onderhoud** met:  <br/> **Start gebruikstijd** ingesteld op **6 uur**.  <br/> **Einde gebruikstijd** ingesteld op **22 uur**.  <br/> **Uitstelperiode voor kwaliteitsupdates (dagen)** wordt ingesteld op **0**.  <br/> **Uitstelperiode voor onderdelenupdates (dagen)** wordt ingesteld op **0**.  <br/> **Delivery Optimization-downloadmodus** wordt ingesteld op **HTTP gemengd met peers achter hetzelfde NAT**.  <br/> |
|||
   

