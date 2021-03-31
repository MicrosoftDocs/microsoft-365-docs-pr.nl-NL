---
title: Bestaande apparaten zelf registreren
description: Herbruikbare apparaten registreren die u mogelijk al zelf hebt, zodat ze kunnen worden beheerd door Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
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
ms.openlocfilehash: 1703e4ed4ea0f3306edf6fdf07ab9c97a9266d4f
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445564"
---
# <a name="register-existing-devices-yourself"></a>Bestaande apparaten zelf registreren

>[!NOTE]
>In dit onderwerp worden de stappen beschreven voor het opnieuw gebruiken van apparaten die u al hebt en registreren in Microsoft Managed Desktop. Als u met gloednieuwe apparaten werkt, volgt u in plaats daarvan de stappen in Nieuwe apparaten [registreren in Microsoft Managed Desktop.](register-devices-self.md)

Het proces voor Partners wordt beschreven in [Stappen voor Partners om apparaten te registreren.](register-devices-partner.md)

Microsoft Managed Desktop kan werken met gloednieuwe apparaten of u kunt apparaten die u mogelijk al hebt opnieuw gebruiken (waarvoor u deze opnieuw moet weergeven). U kunt apparaten registreren met Microsoft Managed Desktop in de Microsoft Endpoint Manager-portal.

## <a name="prepare-to-register-existing-devices"></a>Voorbereidingen treffen om bestaande apparaten te registreren


Als u bestaande apparaten wilt registreren, volgt u de volgende stappen:

1. [Verkrijg de hardwarehash voor elk apparaat.](#obtain-the-hardware-hash)
2. [De hashgegevens samenvoegen](#merge-hash-data)
3. [Registreer de apparaten in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).
4. [Controleer of de afbeelding juist is.](#check-the-image)
5. [Het apparaat leveren](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>De hardwarehash verkrijgen

Microsoft Managed Desktop identificeert elk apparaat uniek door te verwijzen naar de hardware-hash. U hebt vier opties voor het verkrijgen van deze informatie op apparaten die u al gebruikt:

- Vraag uw OEM-leverancier om het AutoPilot-registratiebestand, dat de hardwarehashes bevat.
- Gegevens verzamelen in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).
- Voer een Windows PowerShell-script uit, [](#manual-powershell-script-method) hetzij via [Active Directory](#active-directory-powershell-script-method) of handmatig op elk apparaat, en verzamel de resultaten in een bestand.
- Start elk apparaat, maar voltooi de Installatie-ervaring van Windows niet en verzamel de [hashes op een verwisselbaar flashstation.](#flash-drive-method)

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

U kunt Microsoft Endpoint Configuration Manager gebruiken om de hardwarehashes te verzamelen van bestaande apparaten die u wilt registreren bij Microsoft Managed Desktop.

> [!IMPORTANT]
> Alle apparaten voor wie u deze informatie wilt ontvangen, moeten Windows 10, versie 1703 of hoger gebruiken. 

Als u aan al deze vereisten hebt voldaan, kunt u de gegevens als volgt verzamelen:

1. Selecteer in de console Configuration Manager de optie **Controleren.** 
2. Vouw in de werkruimte Controle het knooppunt **Rapportage** uit, vouw **Rapporten** uit en selecteer het **knooppunt Hardware - Algemeen.** 
3. Voer het rapport uit, **Windows Autopilot-apparaatgegevens** en bekijk de resultaten.
4. Selecteer in de rapportviewer het **pictogram Exporteren** en kies de **optie CSV (door komma's** scheidingstekens).
5. Nadat u het bestand hebt opgeslagen, moet u de resultaten filteren op alleen de apparaten die u wilt registreren bij Microsoft Managed Desktop en de gegevens uploaden naar Microsoft Managed Desktop. Open Microsoft Endpoint Manager en navigeer naar **het** menu Apparaten, zoek vervolgens naar de sectie Beheerd bureaublad van Microsoft en selecteer **Apparaten.** Selecteer **+ Registreer apparaten**, waarmee een in-fly-in wordt geopend om nieuwe apparaten te registreren.


Raadpleeg Apparaten [registreren via de beheerportal voor](#register-devices-by-using-the-admin-portal) meer informatie.


#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell-scriptmethode

In een Active Directory-omgeving kunt u de PowerShell-cmdlet gebruiken om de gegevens op afstand te verzamelen van `Get-WindowsAutoPilotInfo` apparaten in Active Directory-groepen met behulp van WinRM. U kunt ook de cmdlet gebruiken en gefilterde resultaten krijgen voor een specifieke naam van `Get-AD Computer` het hardwaremodel in de catalogus. Voordat u verdergaat, bevestigt u eerst deze vereisten en gaat u verder met de stappen:

- WinRM is ingeschakeld.
- De apparaten die u wilt registreren, zijn actief op het netwerk (dat wil zeggen dat ze niet zijn losgekoppeld of uitgeschakeld).
- Zorg ervoor dat u een domeinreferentieparameter hebt die toestemming heeft om extern uit te voeren op de apparaten.
- Zorg ervoor dat Windows Firewall toegang biedt tot WMI. Ga als volgt te werk om dit te doen:

    1. Open het **configuratiescherm van Windows Defender Firewall** en selecteer Een app of functie toestaan via Windows Defender **Firewall.**
    
    2. Zoek **Windows Management Instrumentation (WMI)** in de lijst, schakel privé en **openbaar** in en selecteer **OK.**

1.  Open een PowerShell-prompt met beheerdersrechten.

2.  Voer *een van deze* scripts uit:

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. Toegang tot alle directories waar mogelijk vermeldingen voor de apparaten staan. Verwijder items voor elk apparaat uit *alle mappen,* inclusief Windows Server Active Directory Domain Services en Azure Active Directory. Het kan enkele uren duren voordat de verwijdering volledig is verwerkt.

4. Access management services where there might beentries for the devices. Verwijder items voor elk apparaat uit *alle* beheerservices, waaronder Microsoft Endpoint Configuration Manager, Microsoft Intune en Windows Autopilot. Het kan enkele uren duren voordat de verwijdering volledig is verwerkt.

U kunt nu doorgaan met het [registreren van apparaten.](#register-devices-by-using-the-admin-portal)

#### <a name="manual-powershell-script-method"></a>Handmatige PowerShell-scriptmethode

1.  Open een PowerShell-prompt met beheerdersrechten.
2.  Uitvoeren `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Uitvoeren `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4. [Voeg de hashgegevens samen.](#merge-hash-data)

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
10. [Voeg de hashgegevens samen.](#merge-hash-data)

>[!IMPORTANT]
>Gebruik het apparaat dat u registreert pas weer aan als u de registratie voor het apparaat hebt voltooid. 



### <a name="merge-hash-data"></a>Hashgegevens samenvoegen

Als u de hardwarehashgegevens hebt verzameld met de handmatige PowerShell- of flashstationmethoden, moet u de gegevens in de CSV-bestanden nu in één bestand combineren om de registratie te voltooien. Hier is een voorbeeld van een PowerShell-script om het eenvoudig te maken:

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

Als de hashgegevens zijn samengevoegd tot één CSV-bestand, kunt u nu doorgaan met het [registreren van de apparaten.](#register-devices-by-using-the-admin-portal)


#### <a name="register-devices-by-using-the-admin-portal"></a>Apparaten registreren met behulp van de beheerportal

Selecteer [in Microsoft Endpoint Manager](https://endpoint.microsoft.com/)de optie **Apparaten** in het linkernavigatiedeelvenster. Zoek de sectie Microsoft Managed Desktop van het menu en selecteer **Apparaten.** Selecteer + **Registreer** apparaten in de werkruimte Beheerde bureaubladapparaten van Microsoft, waarmee u een fly-in opent om nieuwe apparaten te registreren.

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Ga als volgt te werk:

1. Geef **in Bestand uploaden** een pad op naar het CSV-bestand dat u eerder hebt gemaakt.

1. Selecteer **Apparaten registreren.** Het systeem voegt de apparaten toe aan uw lijst met apparaten op het **apparaatblad**, gemarkeerd als **Registratie in behandeling.** Registratie duurt meestal minder dan 10 minuten en  wanneer het apparaat is geslaagd, wordt het apparaat als Gereed voor gebruiker gebruikt, wat betekent dat het klaar is en wacht totdat een gebruiker het gaat gebruiken.


U kunt de voortgang van apparaatregistratie op de hoofdpagina controleren. Mogelijke staten die daar zijn gerapporteerd, zijn:

| Status | Omschrijving |
|---------------|-------------|
| Registratie in behandeling | Registratie is nog niet klaar. Controleer het later opnieuw. |
| Registratie is mislukt | Registratie kan niet worden voltooid. Raadpleeg [Apparaatregistratie oplossen voor](#troubleshooting-device-registration) meer informatie. |
| Klaar voor gebruiker | Registratie is geslaagd en het apparaat is nu klaar om aan de gebruiker te worden geleverd. Microsoft Managed Desktop begeleidt ze bij de eerste keer instellen, zodat u geen verdere voorbereidingen hoeft te treffen. |
| Actief | Het apparaat is geleverd aan de gebruiker en heeft zich geregistreerd bij uw tenant. Dit geeft ook aan dat ze het apparaat regelmatig gebruiken. |
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

Als uw apparaat afkomstig is van een Microsoft Managed Desktop-partnerleverancier, moet de afbeelding juist zijn.

U kunt de afbeelding ook zelf toepassen als u dat wilt. Als u wilt beginnen, neemt u contact op met de Microsoft-vertegenwoordiger met wie u werkt. Deze vertegenwoordiger geeft u de locatie en stappen voor het toepassen van de afbeelding.

### <a name="deliver-the-device"></a>Het apparaat leveren

> [!IMPORTANT]
> Voordat u het apparaat aan uw gebruiker aflevert, [](../get-ready/prerequisites.md) moet u ervoor zorgen dat u de juiste licenties voor die gebruiker hebt verkregen en toegepast.

Als alle licenties worden toegepast, kunt u uw gebruikers voorbereiden op het gebruik van apparaten [en](get-started-devices.md)vervolgens kan uw gebruiker het apparaat starten en doorgaan met de Installatie-ervaring van Windows.









