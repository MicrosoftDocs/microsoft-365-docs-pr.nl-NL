---
title: Nieuwe apparaten zelf registreren
description: Registreer apparaten zelf zodat ze kunnen worden beheerd door Microsoft Managed Desktop
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: a66ad53faf1b38c3db4ab4446dbc1d175fbd99e4
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289533"
---
# <a name="register-new-devices-yourself"></a>Nieuwe apparaten zelf registreren

Microsoft Managed Desktop kunt werken met gloednieuwe apparaten of u kunt apparaten die u mogelijk al hebt opnieuw gebruiken (waarvoor u ze opnieuw moet maken). U kunt apparaten registreren met Microsoft Managed Desktop in de Microsoft Endpoint Manager portal.

> [!NOTE]
> Werkt u samen met een partner om apparaten te verkrijgen? Als dat zo is, hoeft u zich geen zorgen te maken over het verkrijgen van de hardwarehashes. ze zullen dat voor u doen. Zorg ervoor dat uw partner een relatie met u heeft in het [Partnercentrum.](https://partner.microsoft.com/dashboard) Uw partner kan meer informatie krijgen bij [Help voor partnercentrum.](/partner-center/request-a-relationship-with-a-customer) Wanneer deze relatie tot stand is gebracht, registreert uw partner alleen apparaten namens u, zonder verdere actie van u. Zie Stappen voor Partners om apparaten te registreren als u de details wilt zien of als uw partner vragen [heeft.](register-devices-partner.md) Nadat de apparaten zijn geregistreerd, kunt u doorgaan met het controleren van de [afbeelding](#check-the-image) en het leveren van [de apparaten](#deliver-the-device) aan uw gebruikers.



## <a name="prepare-to-register-brand-new-devices"></a>Voorbereidingen treffen om gloednieuwe apparaten te registreren


Wanneer u de nieuwe apparaten hebt, volgt u de volgende stappen:

1. [Verkrijg de hardwarehash voor elk apparaat.](#obtain-the-hardware-hash)
2. [De hashgegevens samenvoegen](#merge-hash-data)
3. [Registreer de apparaten in Microsoft Managed Desktop.](#register-devices-by-using-the-admin-portal)
4. [Controleer of de afbeelding juist is.](#check-the-image)
5. [Het apparaat leveren](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>De hardwarehash verkrijgen

Microsoft Managed Desktop elk apparaat uniek identificeert door te verwijzen naar de hardwarehash. U hebt drie opties voor het verkrijgen van deze informatie:

- Vraag uw OEM-leverancier om het AutoPilot-registratiebestand, dat de hardwarehashes bevat.
- Voer een [Windows PowerShell script uit](#powershell-script-method) op elk apparaat en verzamel de resultaten in een bestand.
- Start elk apparaat, maar voltooi de configuratie-Windows niet en verzamel de [hashes op een verwisselbaar flashstation.](#flash-drive-method)

#### <a name="powershell-script-method"></a>PowerShell-scriptmethode

U kunt het [ powershell-scriptGet-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) powershell gebruiken op de website van de PowerShell-galerie. Zie Apparaten toevoegen aan Windows Autopilot voor meer informatie [over apparaatidentificatie en hardwarehash.](/mem/autopilot/add-devices#device-identification)

1. Open een PowerShell-prompt met beheerdersrechten.
2. Uitvoeren `Install-Script -Name Get-WindowsAutoPilotInfo`
3. Uitvoeren `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4. Uitvoeren om te voorkomen dat de volgende `powershell -ExecutionPolicy restricted` onbeperkte scripts worden uitgevoerd.

#### <a name="flash-drive-method"></a>Flashstationmethode

1. Op een ander apparaat dan het apparaat dat u registreert, voegt u een USB-station in.
2. Open een PowerShell-prompt met beheerdersrechten.
3. Uitvoeren `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. Schakel het apparaat in dat u registreert, *maar start de installatie niet.* Als u de installatie-ervaring per ongeluk start, moet u het apparaat opnieuw instellen of opnieuw instellen.
5. Voeg het USB-station in en druk vervolgens op Shift + F10.
6. Open een PowerShell-prompt met beheerdersrechten en voer vervolgens `cd <pathToUsb>` .
7. Uitvoeren `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Uitvoeren `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. Verwijder het USB-station en sluit het apparaat vervolgens af door `shutdown -s -t 0`

> [!IMPORTANT]
> Gebruik het apparaat dat u registreert pas weer aan als u de registratie voor het apparaat hebt voltooid. 

### <a name="merge-hash-data"></a>Hashgegevens samenvoegen

U moet de gegevens in de CSV-bestanden in één bestand laten combineren om de registratie te voltooien. Hier is een voorbeeld van een PowerShell-script om het eenvoudig te maken:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

### <a name="register-devices-by-using-the-admin-portal"></a>Apparaten registreren met behulp van de beheerportal

Selecteer [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)in **het** linkernavigatiedeelvenster apparaten. Zoek naar de Microsoft Managed Desktop van het menu en selecteer **Apparaten.** Selecteer in Microsoft Managed Desktop werkruimte Apparaten Selecteer **+ Registreer** apparaten, waarmee een fly-in wordt geopend om nieuwe apparaten te registreren.

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->

Volg deze stappen:

1. Geef **in Bestand uploaden** een pad op naar het CSV-bestand dat u eerder hebt gemaakt.
2. Selecteer een [apparaatprofiel](../service-description/profiles.md) in de vervolgkeuzelijst.
3. Selecteer **Apparaten registreren.** Het systeem voegt de apparaten toe aan uw lijst met apparaten op **apparaten**, gemarkeerd als **Registratie in behandeling.** Registratie duurt meestal minder dan 10 minuten en  wanneer het apparaat is geslaagd, wordt het apparaat als Gereed voor gebruiker gebruikt, wat betekent dat het klaar is en wacht totdat een gebruiker het gaat gebruiken.

> [!NOTE]
> Als u het lidmaatschap van de Azure Active Directory (AAD) van een apparaat handmatig wijzigt, wordt het automatisch opnieuw toegewezen aan de groep voor het apparaatprofiel en verwijderd uit conflicterende groepen.

U kunt de voortgang van apparaatregistratie op de hoofdpagina controleren. Mogelijke staten die daar zijn gerapporteerd, zijn:

| Status | Omschrijving |
|---------------|-------------|
| Registratie in behandeling | Registratie is nog niet klaar. Controleer het later opnieuw. |
| Registratie is mislukt | Registratie kan niet worden voltooid. Raadpleeg [Apparaatregistratie oplossen voor](#troubleshooting-device-registration) meer informatie. |
| Klaar voor gebruiker | Registratie is geslaagd en het apparaat is nu klaar om aan de gebruiker te worden geleverd. Microsoft Managed Desktop begeleidt hen bij de eerste keer instellen, zodat u geen verdere voorbereidingen hoeft te treffen. |
| Actief | Het apparaat is geleverd aan de gebruiker en heeft zich geregistreerd bij uw tenant. Deze status geeft ook aan dat ze het apparaat regelmatig gebruiken. |
| Inactief | Het apparaat is geleverd aan de gebruiker en heeft zich geregistreerd bij uw tenant. Ze hebben het apparaat echter onlangs (in de afgelopen 7 dagen) niet gebruikt.  | 

#### <a name="troubleshooting-device-registration"></a>Apparaatregistratie oplossen

| Foutbericht | Details |
|---------------|-------------|
| Apparaat niet gevonden | We konden dit apparaat niet registreren omdat we geen overeenkomst konden vinden voor de fabrikant, het model of het serienummer. Bevestig deze waarden bij uw apparaatleverancier. |
| Hardware-hash niet geldig | De hardwarehash die u voor dit apparaat hebt opgegeven, is niet correct opgemaakt. Controleer de hardwarehash en vervolgens opnieuw. |
| Apparaat dat al is geregistreerd | Dit apparaat is al geregistreerd bij uw organisatie. Geen verdere actie vereist. |
| Apparaat dat door een andere organisatie is geclaimd | Dit apparaat is al geclaimd door een andere organisatie. Neem contact op met uw apparaatleverancier. |
| Onverwachte fout | Uw aanvraag kan niet automatisch worden verwerkt. Neem contact op met ondersteuning en geef de aanvraag-id op: <requestId> |

### <a name="check-the-image"></a>De afbeelding controleren

Als uw apparaat afkomstig is van een Microsoft Managed Desktop partnerleverancier, moet de afbeelding juist zijn.

U kunt de afbeelding ook zelf toepassen als u dat wilt. Als u wilt beginnen, neemt u contact op met de Microsoft-vertegenwoordiger met wie u werkt. Deze vertegenwoordiger geeft u de locatie en stappen voor het toepassen van de afbeelding.

### <a name="autopilot-group-tag"></a>Autopilot-groepslabel

Wanneer u de beheerportal gebruikt om apparaten te registreren, wordt automatisch de Microsoft365Managed_Autopilot **Autopilot** Group Tag toegewezen.
De service controleert Microsoft Managed Desktop apparaten dagelijks en wijst de groepstag toe aan alle apparaten die deze nog niet hebben.

### <a name="deliver-the-device"></a>Het apparaat leveren

> [!IMPORTANT]
> Voordat u het apparaat aan uw gebruiker aflevert, [](../get-ready/prerequisites.md) moet u ervoor zorgen dat u de juiste licenties voor die gebruiker hebt verkregen en toegepast.

Als alle licenties worden toegepast, [](get-started-devices.md)kunt u uw gebruikers voorbereiden op het gebruik van apparaten en vervolgens kan uw gebruiker het apparaat starten en doorgaan met de Windows installatie.
