---
title: Bestaande apparaten zelf registreren
description: Hergebruikte apparaten registreren u hebt mogelijk al een nieuwe versie van Microsoft die door Microsoft worden beheerd
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 51c241c46a4c8745bcae169a1c1d89e5c4393f2f
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289137"
---
# <a name="register-existing-devices-yourself"></a>Bestaande apparaten zelf registreren

>[!NOTE]
>In dit onderwerp worden de stappen beschreven die u moet uitvoeren om apparaten die u al hebt, opnieuw te gebruiken en deze te registreren in Microsoft Managed Desktop. Als u werkt met merk-nieuwe apparaten, volgt u de stappen in [nieuwe apparaten registreren in Microsoft Managed Desktop](register-devices-self.md) .

Het proces voor partners wordt gedocumenteerd in [stappen voor partners om apparaten te registreren](register-devices-partner.md).

Microsoft Managed Desktop kan met gloednieuwe apparaten werken, maar u kunt ook apparaten die u al hebt, opnieuw gebruiken (welke u de afbeelding opnieuw moet maken. U kunt apparaten registreren met behulp van de beheerde portal voor Microsoft-bureaubladbeheer.

## <a name="prepare-to-register-existing-devices"></a>Voorbereidingen treffen om bestaande apparaten te registreren


Voer de volgende stappen uit als u bestaande apparaten wilt registreren:

1. [De hardware-hash voor elk apparaat verkrijgen.](#obtain-the-hardware-hash)
2. [De hash-gegevens samenvoegen](#merge-hash-data)
3. [Registreer de apparaten in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).
4. [Controleer nog of de afbeelding klopt.](#check-the-image)
5. [Het apparaat leveren](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>De hardware-hash verkrijgen

Microsoft Managed Desktop identificeert elk apparaat uniek door te verwijzen naar de hardware-hash. U hebt vier opties voor het verkrijgen van deze informatie van apparaten die u al gebruikt:

- Neem contact op met de leverancier van de fabrikant voor het auto pilot-registratiebestand, waaronder de hardware-hashes.
- Gegevens verzamelen in [Microsoft endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).
- Voer een Windows PowerShell-script uit, hetzij via [Active Directory](#active-directory-powershell-script-method) of [handmatig](#manual-powershell-script-method) op elk apparaat, en verzamel de resultaten in een bestand.
- Start elk apparaat, maar voer de installatie van Windows niet uit, en [Verzamel de hashes op een verwisselbaar flashstation](#flash-drive-method).

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

U kunt Microsoft endpoint Configuration Manager gebruiken om de hardware-hashes te verzamelen van bestaande apparaten die u wilt registreren bij Microsoft Managed Desktop.

> [!IMPORTANT]
> Voor elk apparaat waarop u deze informatie wilt hebben, moet Windows 10, versie 1703 of hoger worden uitgevoerd. 

Als u al deze voorwaarden hebt voldaan, kunt u de gegevens op de volgende manier verzamelen:

1. Selecteer op de console van Configuration Manager de optie **monitoring**. 
2. Vouw in de werkruimte **bewaking het knooppunt rapporten uit** , vouw **rapporten**uit en selecteer het knooppunt **Hardware-algemeen** . 
3. Voer het rapport uit, de gegevens van de **Windows auto pilot-apparaten**en Bekijk de resultaten.
4. Selecteer het pictogram **exporteren** in de rapportweergave en kies de optie **CSV (door komma's gescheiden)** .
5. Nadat u het bestand hebt opgeslagen, moet u de resultaten filteren op alleen de apparaten die u wilt registreren met Microsoft Managed Desktop en de gegevens naar Microsoft beheerde [Portal beheer Portal](https://aka.ms/mmdportal)uploaden, selecteert u **apparaten** in het linker navigatiedeelvenster. Selecteer **+ register apparaten**. de invliegen wordt geopend:


Zie [apparaten registreren met behulp van de beheer Portal](#register-devices-by-using-the-admin-portal) voor meer informatie.


#### <a name="active-directory-powershell-script-method"></a>Scriptmethode voor Active Directory PowerShell

In een Active Directory-omgeving kunt u de `Get-WindowsAutoPilotInfo` PowerShell-cmdlet gebruiken om de gegevens op afstand te verzamelen van apparaten in Active Directory-groepen met behulp van WinRM. U kunt ook de `Get-AD Computer` cmdlet gebruiken en gefilterde resultaten weergeven voor een specifieke naam van een hardware model in de catalogus. Voordat u dit doet, moet u eerst deze voorwaarden bevestigen en vervolgens de stappen uitvoeren:

- WinRM is ingeschakeld.
- De apparaten die u registreert, zijn actief op het netwerk (dat wil zeggen dat ze niet zijn verbonden of uitgeschakeld).
- Zorg dat u een parameter voor domeinreferenties hebt die gemachtigd is om extern uit te voeren op de apparaten.
- Zorg ervoor dat de toegang tot WMI is toegestaan door Windows Firewall. Voer hiertoe de volgende stappen uit:

    1. Open het Configuratiescherm van **Windows Defender firewall** en selecteer **een app of functie toestaan via Windows Defender firewall**.
    
    2. U kunt **WMI (Windows Management Instrumentation)** zoeken in de lijst, inschakelen voor **privé en openbaar**, en selecteer vervolgens **OK**.

1.  Open een PowerShell-prompt met beheerdersrechten.

2.  Voer *een* van deze scripts uit:

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. Toegang krijgen tot mappen waar zich mogelijk vermeldingen bevinden voor de apparaten. Verwijdert vermeldingen voor elk apparaat uit *alle* directory's, waaronder Windows Server Active Directory Domain Services en Azure Active Directory. Het kan een paar uur duren voordat de bewerking is voltooid.

4. Toegangsbeheer services waarbij mogelijk vermeldingen voor de apparaten zijn. Verwijdert vermeldingen voor elk apparaat uit *alle* beheerservices, waaronder Microsoft-Configuratiebeheer, Microsoft intune en Windows auto pilot. Het kan een paar uur duren voordat de bewerking is voltooid.

U kunt nu doorgaan met het [registreren van apparaten](#register-devices-by-using-the-admin-portal).

#### <a name="manual-powershell-script-method"></a>Handmatige PowerShell-scriptmethode

1.  Open een PowerShell-prompt met beheerdersrechten.
2.  Uitgevoerd `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Uitgevoerd `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4. [De hash-gegevens samenvoegen.](#merge-hash-data)

#### <a name="flash-drive-method"></a>Methode Flash Drive

1. Op een ander apparaat dan de computer die u registreert, voegt u een USB-station in.
2. Open een PowerShell-prompt met beheerdersrechten.
3. Uitgevoerd `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. Schakel het apparaat in dat u registreert, maar *start niet de installatie*. Als u de installatie-ervaring per ongeluk start, moet u het apparaat opnieuw instellen of opnieuw instellen.
5. Plaats het USB-station en druk op SHIFT + F10.
6. Open een PowerShell-prompt met beheerdersrechten en voer vervolgens de opdracht uit `cd <pathToUsb>` .
7. Uitgevoerd `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Uitgevoerd `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. Verwijder het USB-station en sluit het apparaat af door het uit te voeren `shutdown -s -t 0`
10. [De hash-gegevens samenvoegen.](#merge-hash-data)

>[!IMPORTANT]
>Kracht niet op het apparaat dat u wilt registreren totdat u de registratie voor het apparaat hebt voltooid. 



### <a name="merge-hash-data"></a>Hash-gegevens samenvoegen

Als u de hardware-hashgegevens hebt verzameld via de handmatige methoden voor PowerShell of Flash Drive, moet u de gegevens in de CSV-bestanden samenvatten in één bestand om de registratie te voltooien. Hier ziet u een voorbeeld van een PowerShell-script om dit eenvoudig te maken:

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

Met de hash-gegevens die zijn samengevoegd met een CSV-bestand, kunt u nu verdergaan met [de registratie van de apparaten](#register-devices-by-using-the-admin-portal).


#### <a name="register-devices-by-using-the-admin-portal"></a>Apparaten registreren met behulp van de beheer Portal

Selecteer in de [Beheer Portal](https://aka.ms/mmdportal)van Microsoft Managed Desktop de optie **apparaten** in het linker navigatiedeelvenster. Selecteer **+ register apparaten**. de invliegen wordt geopend:

[![Invliegen na het selecteren van apparaten voor registreren, apparaten met kolommen weergeven voor toegewezen gebruikers, serienummers, status, laatste datum en ouderdom](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Volg deze stappen:

1. In **bestand uploaden**geeft u het pad op naar het CSV-bestand dat u eerder hebt gemaakt.

1. Selecteer **apparaten registreren**. Het systeem voegt de apparaten toe aan uw lijst met apparaten op de **Blade van apparaten**, gemarkeerd als **AutopilotRegistrationRequested**. Registratie duurt meestal minder dan 10 minuten en wanneer het apparaat succesvol wordt weergegeven als u **klaar bent** , wordt de gebruiker gevraagd het programma te gebruiken.


U kunt de voortgang van apparaatregistratie controleren op de hoofdpagina **met beheerde Microsoft-bureaublad apparaten** . Mogelijke Staten hebben aangegeven:

| Status | Beschrijving |
|---------------|-------------|
| AutopilotRegistrationRequested | De registratie is nog niet voltooid. Ga later terug. |
| Registratie mislukt | Registreren kon niet worden voltooid. Zie [problemen met apparaatregistratie oplossen](#troubleshooting-device-registration) voor meer informatie. |
| Klaar voor gebruiker | De registratie is gelukt en het apparaat is nu gereed voor levering aan de gebruiker. Microsoft Managed Desktop verstuurt deze door de eerste keer instellen, dus u hoeft verder geen voorbereidingen te treffen. |
| Actief | Het apparaat is doorgegeven aan de gebruiker en is geregistreerd bij uw Tenant. Dit geeft ook aan dat ze regelmatig gebruikmaken van het apparaat. |
| Inactief | Het apparaat is doorgegeven aan de gebruiker en is geregistreerd bij uw Tenant. Ze hebben dit echter niet onlangs gebruikt (in de afgelopen 7 dagen).  | 

#### <a name="troubleshooting-device-registration"></a>Problemen met apparaatregistratie oplossen

| Foutbericht | Details |
|---------------|-------------|
| Apparaat niet gevonden | Dit apparaat kan niet worden geregistreerd omdat er geen overeenkomsten zijn gevonden voor de verstrekte fabrikant, model of serienummer. Bevestig deze waarden met de leverancier van uw apparaat. |
| De hardware-hash is niet geldig | De hardware-hash die u hebt opgegeven voor dit apparaat werd niet goed opgemaakt. Controleer de hardware-hash en voer vervolgens opnieuw in. |
| Apparaat al geregistreerd | Dit apparaat is al geregistreerd voor uw organisatie. Geen verdere actie vereist. |
| Apparaat geclaimd door een andere organisatie | Dit apparaat is al door een andere organisatie geclaimd. Neem contact op met de leverancier van uw apparaat. |
| Onverwachte fout | Uw aanvraag kon niet automatisch worden verwerkt. Neem contact op met de ondersteuning en voer de aanvraag-ID in: <requestId> |

### <a name="check-the-image"></a>De afbeelding controleren

Als uw apparaat afkomstig is van een leverancier van Microsoft beheerde desktop partners, moet de afbeelding correct zijn.

U kunt de afbeelding ook zelf toepassen als u dat wilt. Als u aan de slag wilt gaan, neemt u contact op met de Microsoft-medewerker waarmee u samenwerkt en worden de locatie en de stappen beschreven voor het toepassen van de afbeelding.

### <a name="deliver-the-device"></a>Het apparaat leveren

> [!IMPORTANT]
> Voordat u het apparaat aan de gebruiker laat overleveren, controleert u of u de [juiste licenties](../get-ready/prerequisites.md) voor die gebruiker hebt verkregen en toegepast.

Als alle licenties worden toegepast, kunt u de [gebruikers voorbereiden op het gebruik van apparaten](get-started-devices.md)en vervolgens uw gebruiker het apparaat laten opstarten en doorgaan met de installatie van Windows.









