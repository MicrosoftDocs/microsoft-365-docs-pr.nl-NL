---
title: Registreer bestaande apparaten zelf
description: Registreer opnieuw gebruikte apparaten die u mogelijk al zelf hebt, zodat ze kunnen worden beheerd door Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: a971d8dc413e7794aa48c0b39cc0f42e511739ed
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42809510"
---
# <a name="register-existing-devices-yourself"></a>Registreer bestaande apparaten zelf

>[!NOTE]
>In dit onderwerp worden de stappen beschreven die u gebruiken om apparaten die u al hebt opnieuw te gebruiken en deze te registreren in Microsoft Managed Desktop. Als u met gloednieuwe apparaten werkt, volgt u in plaats daarvan zelf de stappen in [Nieuwe apparaten registreren in Microsoft Managed Desktop.](register-devices-self.md)

Het proces voor partners wordt gedocumenteerd in [Stappen voor Partners om apparaten te registreren.](register-devices-partner.md)

Microsoft Managed Desktop kan werken met gloednieuwe apparaten of u apparaten die u misschien al hebt opnieuw gebruiken (waarvoor u ze opnieuw moet afbeelding smaken). U apparaten registreren met Microsoft Managed Desktop op de Azure Portal.

## <a name="prepare-to-register-existing-devices"></a>Voorbereiden om bestaande apparaten te registreren


Voer de volgende stappen uit om bestaande apparaten te registreren:

1. [Verkrijg de hardwarehash voor elk apparaat.](#obtain-the-hardware-hash)
2. [De hashgegevens samenvoegen](#merge-hash-data)
3. [Registreer de apparaten in Microsoft Managed Desktop](#register-devices).
4. [Controleer nogmaals of de afbeelding correct is.](#check-the-image)
5. [Het apparaat leveren](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>De hardwarehash verkrijgen

Microsoft Managed Desktop identificeert elk apparaat uniek door te verwijzen naar de hardwarehash. Je hebt vier opties om deze informatie te verkrijgen van apparaten die je al gebruikt:

- Vraag uw OEM-leverancier naar het AutoPilot-registratiebestand, dat de hardwarehashes bevat.
- Een aangepast rapport maken in [Configuration Manager](#configuration-manager).
- Voer een Windows PowerShell-script uit - met [Active Directory](#active-directory-powershell-script-method) of [handmatig](#manual-powershell-script-method) op elk apparaat - en verzamel de resultaten in een bestand.
- Start elk apparaat- maar voltooi de Installatie-ervaring van Windows niet - en [verzamel de hashes op een verwisselbaar flashstation.](#flash-drive-method)

#### <a name="configuration-manager"></a>Configuration Manager

U Microsoft Endpoint Configuration Manager gebruiken om de hardwarehashes te verzamelen van bestaande apparaten die u wilt registreren bij Microsoft Managed Desktop.

> [!IMPORTANT]
> Alle apparaten waarvoor u deze informatie wilt krijgen, moeten Windows 10, versie 1703 of hoger gebruiken. U hebt ook een apparaat nodig dat een configuration manager-client is die is verbonden met de site Configuration Manager (Current Branch). U hebt ook de rol van het rapporteringspuntsitesysteem nodig die in uw omgeving is ingesteld met SQL Server Reporting Services ingeschakeld. 

Als u aan al deze vereisten hebt voldaan, u de informatie verzamelen door de volgende stappen te volgen:

1. Selecteer in de console Configuratiebeheer de optie **Controle**. 
2. Vouw in de werkruimte Controle **rapporten**uit en selecteer **Rapporten**. 
3. Selecteer op het tabblad **Start** in de sectie **Maken** de optie **Rapport maken** om de wizard Rapport maken te openen. 
4. Stel op de pagina **Informatie** de volgende instellingen in: 
    - **Naam:** Geef een naam op voor het rapport. 
    - **Beschrijving:** Geef een beschrijving voor het rapport op. 
    - **Server:** Hiermee wordt de naam weergegeven van de rapportserver waarop u dit rapport maakt. 
    - **Pad:** Selecteer **Bladeren** om een map op te geven waarin u het rapport wilt opslaan. 
5. Selecteer **Volgende**. 
6. Controleer op de **pagina Overzicht** de instellingen. Selecteer **Vorige** om de instellingen te wijzigen of selecteer **Volgende** om het rapport te maken in Configuratiebeheer. 
7. Selecteer **op** de pagina Voltooien de optie **Sluiten** om de wizard af te sluiten en open **Rapportbouwer** om de rapportinstellingen in te voeren. Voer uw gebruikersaccount en wachtwoord in als u wordt gevraagd en selecteer **OK.** Als Rapportbouwer niet op het apparaat is geïnstalleerd, wordt u gevraagd het apparaat te installeren. Selecteer **Uitvoeren om Rapportbouwer te installeren**, wat nodig is om rapporten te wijzigen en te maken. 


**Geef in Microsoft Report Builder**de SQL-instructie voor het rapport op en volg de volgende stappen:

1. Selecteer in het linkerdeelvenster **Gegevenssets**en klik vervolgens met de rechtermuisknop op **Gegevensset toevoegen**.
2. Ga naar het tabblad **Query** en voer de naam als *DataSet0*in . 
3. Selecteer **Een gegevensset gebruiken die is ingesloten in mijn rapport**; Rapportbouwer wordt geopend.
4. Selecteer **gegevensbron**in **Rapportbouwer:**. Selecteer de standaardgegevensbron, die moet beginnen met "AutoGen". 
5. Kies **Querytype als tekst**en voer deze query in:




```sql
SELECT comp.manufacturer0      AS Manufacturer,  
       comp.model0             AS Model,  
       bios.serialnumber0      AS Serial_Number,  
       mdm.devicehardwaredata0 AS HardwareHash  
FROM   Fn_rbac_gs_computer_system(@UserSIDs) comp

       INNER JOIN Fn_rbac_gs_pc_bios(@UserSIDs) bios  
               ON comp.resourceid = bios.resourceid  
       INNER JOIN Fn_rbac_gs_mdm_devdetail_ext01(@UserSIDs) mdm  
               ON comp.resourceid = mdm.resourceid
```




5. Navigeer naar het tabblad **Veld,** wehre-waarden **voor Veldnaam** en **veldbron** moeten al worden ingevuld. Als dit niet het zo is, selecteert u **Toevoegen**en selecteert u **Queryveld**. Voer de **veldnaam** en **veldbron in**.
6. Herhaal dit voor elk van deze waarden: 
    - Fabrikant 
    - Model 
    - Serieel_getal 
    - HardwareHash
7. Selecteer **OK**.

**Definieer vervolgens de rapportweergave en maak het rapport** door de volgende stappen te volgen:

1. Tabel **of matrix selecteren**; er wordt een nieuwe wizard geopend.
2. Selecteer **in Een gegevensset kiezen**de optie Een bestaande **gegevensset kiezen in dit rapport of een gedeelde gegevensset**.  
3. Selecteer **DataSet0** (de standaardinstelling) en selecteer **Volgende**.
4. **Sleep fabrikant,** **model**en **serienummer naar** het vak **Rijgroepen.** Sleep **HardwareHash** naar het vak **Waarden** en selecteer **Volgende**.
5. Schakel de selectievakjes voor **Subtotalen en eindtotalen weergeven en groepen** **Uitvouwen/samenvouwen uit.** Selecteer **Volgende**.
6. Selecteer **Voltooien**.
7. Selecteer **Uitvoeren** om uw rapport uit te voeren. Controleer of het rapport de informatie bevat die u verwacht. Selecteer indien nodig **Ontwerp** om terug te keren naar de ontwerpweergave om het rapport te wijzigen.
8. Selecteer **Opslaan** om het rapport op te slaan op de rapportserver. U het nieuwe rapport uitvoeren in het knooppunt Rapporten in de werkruimte Controle. 

**Exporteer ten slotte het rapport en gebruik het om apparaten te registreren** door deze stappen te volgen. (U hoeft alleen de stappen 1 en 2 van deze sectie te volgen als u na de vorige stappen hebt weggenavigeerd.):

1. Selecteer in de console Configuratiebeheer de optie **Controle**.
2. Vouw **in Monitoring** **Rapportage**uit en selecteer vervolgens **Rapporten**.
3. Zoek het rapport met de naam die u eerder hebt gemaakt.
4. Klik met de rechtermuisknop op dit rapport en selecteer **Uitvoeren**.
5. Selecteer **exporteren** en selecteer **Opslaan als CSV**in het dialoogvenster dat wordt geopend.
6. Deze versie van rapport haalt hashes uit alle Windows 10-apparaten waarmee Configuration Manager communiceert. U moet resultaten filteren op alleen die apparaten die u wilt registreren bij Microsoft Managed Desktop.


> [!IMPORTANT]
> De query in Configuratiebeheer staat geen spaties toe in geëxporteerde kolomnamen. daarom heb je in de stappen 'Serial_Number' en 'HardwareHash' ingevoerd. Nu u het geëxporteerde CSV-bestand hebt, moet u de rapportkoppen bewerken om *serienummer* en *hardwarehash* te lezen, zoals hier wordt weergegeven voordat u verdergaat met apparaatregistratie.

Nu u overgaan tot [Apparaten registreren met behulp van de Azure Portal.](#register-devices-by-using-the-azure-portal)


#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell-scriptmethode

In een Active Directory-omgeving `Get-MMDRegistrationInfo` kunt u de PowerShell-cmdlet gebruiken om de informatie van apparaten in Active Directory-groepen op afstand te verzamelen met Behulp van WinRM. U de `Get-AD Computer` cmdlet ook gebruiken en gefilterde resultaten krijgen voor een specifieke hardwaremodelnamen die in de catalogus zijn opgenomen. Bevestig hiervoor eerst deze vereisten en ga vervolgens verder met de stappen:

- WinRM is ingeschakeld.
- De apparaten die u wilt registreren, zijn actief op het netwerk (dat wil zeggen dat ze niet zijn losgekoppeld of uitgeschakeld).
- Zorg ervoor dat u een parameter voor domeinreferenties hebt die toestemming heeft om op afstand uit te voeren op de apparaten.
- Zorg ervoor dat Windows Firewall toegang geeft tot WMI. Voer hiervoor de volgende stappen uit:
    1. Open het configuratiescherm **van Windows Defender Firewall** en selecteer Een app of functie toestaan via Windows Defender **Firewall**.
    2. Zoek **Windows Management Instrumentation (WMI)** in de lijst, schakel in voor zowel Privé als **Openbaar**en selecteer **VERVOLGENS OK**.

1.  Open een PowerShell-prompt met beheerdersrechten.
2.  Voer *een* van deze scripts uit:
```powershell
Install-script -name Get-MMDRegistrationInfo 
#example one – leverage Get-ADComputer to enumerate devices 
Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname>
```
```powershell 
#example two – target specific devices: 
Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
```
3. Krijg toegang tot mappen waar er mogelijk vermeldingen voor de apparaten zijn. Verwijder vermeldingen voor elk apparaat uit *alle* mappen, waaronder Windows Server Active Directory Domain Services en Azure Active Directory. Houd er rekening mee dat deze verwijdering een paar uur kan duren om volledig te verwerken.
4. Toegangsbeheerservices waar mogelijk vermeldingen voor de apparaten zijn. Verwijder vermeldingen voor elk apparaat uit *alle* beheerservices, waaronder Microsoft Endpoint Configuration Manager, Microsoft Intune en Windows Autopilot. Houd er rekening mee dat deze verwijdering een paar uur kan duren om volledig te verwerken.

Nu u overgaan tot [het registreren van apparaten.](#register-devices)

#### <a name="manual-powershell-script-method"></a>Handmatige PowerShell-scriptmethode

1.  Open een PowerShell-prompt met beheerdersrechten.
2.  Uitvoeren`Install-Script -Name Get-MMDRegistrationInfo`
3.  Uitvoeren`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
4. [Voeg de hashgegevens samen.](#merge-hash-data)

#### <a name="flash-drive-method"></a>Flash-stationmethode

1. Plaats een USB-station op een ander apparaat dan het apparaat dat u registreert.
2. Open een PowerShell-prompt met beheerdersrechten.
3. Uitvoeren`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`
4. Schakel het apparaat in dat u registreert, maar *start de installatie-ervaring niet.* Als u per ongeluk de installatie-ervaring start, moet u het apparaat opnieuw instellen of opnieuw inbeelden.
5. Plaats het USB-station en druk op Shift + F10.
6. Open een PowerShell-prompt met beheerdersrechten en voer vervolgens uit `cd <pathToUsb>`.
7. Uitvoeren`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Uitvoeren`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
9. Verwijder het USB-station en schakel het apparaat vervolgens uit door`shutdown -s -t 0`
10. [Voeg de hashgegevens samen.](#merge-hash-data)

>[!IMPORTANT]
>Ga niet meer in op het apparaat dat u registreert totdat u de registratie voor het apparaat hebt voltooid. 



### <a name="merge-hash-data"></a>Hashgegevens samenvoegen

Als u de hardwarehashgegevens hebt verzameld volgens de handmatige PowerShell- of flashdrive-methoden, moet u nu de gegevens in de CSV-bestanden in één bestand hebben gecombineerd om de registratie te voltooien. Hier is een voorbeeld PowerShell script om dit eenvoudig te maken:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

Als de hashgegevens zijn samengevoegd tot één CSV-bestand, u nu doorgaan [met het registreren van de apparaten.](#register-devices)

### <a name="register-devices"></a>Apparaten registreren

Het CSV-bestand moet zich in een bepaalde indeling voor registratie hebben. Als u de gegevens zelf hebt verzameld in de vorige stappen, moet het bestand al in de juiste indeling zijn; als u het bestand van een leverancier verkrijgt, moet u mogelijk de indeling aanpassen.

>[!NOTE]
>Voor uw gemak u een [sjabloon](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) voor dit CSV-bestand downloaden.

Uw bestand moet **exact dezelfde kolomkoppen** bevatten als de voorbeeldkop (fabrikant, model, enz.), maar uw eigen gegevens voor de andere rijen. Als u de sjabloon gebruikt, opent u deze in een tekstbewerkingstool zoals Kladblok en overweegt u alle gegevens alleen in rij 1 achter te laten en alleen gegevens in rijen 2 en lager in te voeren. 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>Als u vergeet een van de voorbeeldgegevens te wijzigen, mislukt de registratie.

#### <a name="register-devices-by-using-the-azure-portal"></a>Apparaten registreren met behulp van de Azure Portal

Selecteer **Apparaten** in het linkernavigatiedeelvenster in de [Azure-portal](https://aka.ms/mmdportal)van Microsoft Managed Desktop. Selecteer **+ Apparaten registreren**; de fly-in opent:

[![Fly-in na het selecteren van Register-apparaten, het vermelden van apparaten met kolommen voor toegewezen gebruikers, serienummer, status, laatst geziene datum en leeftijd](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)


[//]: # (Helaas is dit niet waar. We kunnen deze notitie verwijderen - maar laten het nu totdat we een kans hebben om erover te praten.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Voer de volgende stappen uit:

1. Geef **in Het uploaden van**bestanden een pad naar het CSV-bestand dat u eerder hebt gemaakt.
2. Optioneel u een **bestel-id** of **aankoop-id** toevoegen voor uw eigen trackingdoeleinden. Er zijn geen indelingsvereisten voor deze waarden.
3. Selecteer **Apparaten registreren**. Het systeem voegt de apparaten toe aan uw lijst met apparaten op het **apparaatblad**, gemarkeerd als **Registratie in behandeling**. Registratie duurt meestal minder dan 10 minuten, en wanneer het apparaat succesvol is, wordt het weergegeven als **Klaar voor de gebruiker,** wat betekent dat het klaar is en wacht tot een eindgebruiker begint te gebruiken.


U de voortgang van de apparaatregistratie controleren op de hoofdpagina **Microsoft Managed Desktop - Devices.** Mogelijke staten die daar worden gemeld zijn:

| Status | Beschrijving |
|---------------|-------------|
| Registratie in behandeling | Registratie is nog niet gedaan. Kom later terug. |
| Registratie is mislukt | De registratie kon niet worden voltooid. Raadpleeg [apparaatregistratie probleemoplossing](#troubleshooting-device-registration) voor meer informatie. |
| Klaar voor gebruik | Registratie geslaagd en het apparaat is nu klaar om te worden geleverd aan de eindgebruiker. Microsoft Managed Desktop begeleidt hen door de eerste set-up, dus u hoeft zich niet verder te voorbereiden. |
| Actief | Het apparaat is geleverd aan de eindgebruiker en ze hebben zich geregistreerd bij uw tenant. Dit geeft ook aan dat ze regelmatig gebruik maken van het apparaat. |
| Inactief | Het apparaat is geleverd aan de eindgebruiker en ze hebben zich geregistreerd bij uw tenant. Ze hebben het apparaat echter niet recent gebruikt (in de afgelopen 7 dagen).  | 

#### <a name="troubleshooting-device-registration"></a>Apparaatregistratie oplossen

| Foutbericht | Details |
|---------------|-------------|
| Apparaat niet gevonden | We konden dit apparaat niet registreren omdat we geen overeenkomst konden vinden voor de meegeleverde fabrikant, model of serienummer. Bevestig deze waarden met uw apparaatleverancier. |
| Hardwarehash niet geldig | De hardwarehash die u voor dit apparaat hebt opgegeven, is niet correct geformatteerd. Controleer de hardwarehash en voer deze vervolgens opnieuw in. |
| Apparaat al geregistreerd | Dit apparaat is al geregistreerd bij uw organisatie. Geen verdere actie vereist. |
| Apparaat dat is geclaimd door een andere organisatie | Dit apparaat is al geclaimd door een andere organisatie. Neem contact op met uw apparaatleverancier. |
| Onverwachte fout | Uw aanvraag kan niet automatisch worden verwerkt. Neem contact op met de ondersteuning en geef de aanvraag-id op:<requestId> |

### <a name="check-the-image"></a>De afbeelding controleren

Als uw apparaat afkomstig is van een Microsoft Managed Desktop-partnerleverancier, moet de afbeelding correct zijn.

U bent ook van harte welkom om de afbeelding alleen toe te passen als u dat liever hebt. Neem om aan de slag te gaan contact op met de Microsoft-vertegenwoordiger waarmee u werkt en geeft u de locatie en stappen voor het toepassen van de afbeelding.

### <a name="deliver-the-device"></a>Het apparaat leveren

> [!IMPORTANT]
> Voordat u het apparaat aan uw gebruiker overhandigt, moet u ervoor zorgen dat u de [juiste licenties](../get-ready/prerequisites.md) voor die gebruiker hebt verkregen en toegepast.

Als alle licenties worden toegepast, u [uw gebruikers klaar maken om apparaten te gebruiken,](get-started-devices.md)en vervolgens kan uw gebruiker het apparaat opstarten en doorgaan met de Windows-installatie-ervaring.









