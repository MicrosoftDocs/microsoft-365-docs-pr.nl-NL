---
title: Bestaande apparaten zelf registreren
description: Registreer hergebruikte apparaten die u misschien al zelf hebt, zodat ze kunnen worden beheerd door Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: abe9e63eb4fcd31993bd26822dc445ff0e48e369
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101483"
---
# <a name="register-existing-devices-yourself"></a>Bestaande apparaten zelf registreren

>[!NOTE]
>In dit onderwerp worden de stappen beschreven die u uitvoeren om apparaten die u al hebt, opnieuw te gebruiken en deze te registreren in Microsoft Managed Desktop. Als u met gloednieuwe apparaten werkt, volgt u de stappen in [Het registreren van nieuwe apparaten in Microsoft Managed Desktop zelf.](register-devices-self.md)

Het proces voor partners wordt gedocumenteerd in [Stappen voor partners om apparaten te registreren.](register-devices-partner.md)

Microsoft Managed Desktop kan werken met gloednieuwe apparaten of u apparaten die u mogelijk al hebt hergebruiken (waarvoor u ze opnieuw moet imagen). U apparaten registreren met behulp van de Microsoft Managed Desktop Admin Portal.

## <a name="prepare-to-register-existing-devices"></a>Voorbereiden om bestaande apparaten te registreren


Voer de volgende stappen uit om bestaande apparaten te registreren:

1. [Verkrijg de hardwarehash voor elk apparaat.](#obtain-the-hardware-hash)
2. [De hash-gegevens samenvoegen](#merge-hash-data)
3. [Registreer de apparaten in Microsoft Managed Desktop](#register-devices).
4. [Controleer of de afbeelding juist is.](#check-the-image)
5. [Het apparaat leveren](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>De hardwarehash verkrijgen

Microsoft Managed Desktop identificeert elk apparaat op unieke wijze door te verwijzen naar de hardwarehash. Je hebt vier opties om deze informatie te verkrijgen van apparaten die je al gebruikt:

- Vraag uw OEM-leverancier om het AutoPilot-registratiebestand, dat de hardwarehashes bevat.
- Een aangepast rapport maken in [Configuratiebeheer](#configuration-manager).
- Voer een Windows PowerShell-script uit met [Active Directory](#active-directory-powershell-script-method) of [handmatig](#manual-powershell-script-method) op elk apparaat en verzamel de resultaten in een bestand.
- Start elk apparaat - maar voltooi de Windows-installatieervaring niet - en [verzamel de hashes op een verwisselbaar flashstation](#flash-drive-method).

#### <a name="configuration-manager"></a>Configuration Manager

U Microsoft Endpoint Configuration Manager gebruiken om de hardwarehashes te verzamelen van bestaande apparaten die u wilt registreren bij Microsoft Managed Desktop.

> [!IMPORTANT]
> Alle apparaten waarvoor u deze informatie wilt krijgen, moeten Windows 10, versie 1703 of hoger hebben uitgevoerd. U hebt ook een apparaat nodig dat een Configuratiebeheerclient is die is verbonden met de site Configuration Manager (Current Branch). U hebt ook de rol Van het rapportagepuntsitesysteem in uw omgeving nodig met SQL Server Reporting Services ingeschakeld. 

Als u aan al deze voorwaarden hebt voldaan, u de informatie verzamelen door de volgende stappen te volgen:

1. Selecteer In de console Configuratiebeheer de optie **Controle**. 
2. Vouw **rapportage**uit in de werkruimte Controle en selecteer **vervolgens Rapporten**. 
3. Selecteer **op** het tabblad Start in de sectie **Maken** de optie **Rapport maken** om de wizard Rapport maken te openen. 
4. Stel **op** de pagina Informatie de volgende instellingen in: 
    - **Naam:** Geef een naam op voor het rapport. 
    - **Beschrijving:** Geef een beschrijving op voor het rapport. 
    - **Server:** Hiermee geeft u de naam weer van de rapportserver waarop u dit rapport maakt. 
    - **Pad:** Selecteer **Bladeren** om een map op te geven waarin u het rapport wilt opslaan. 
5. Selecteer **Volgende**. 
6. Bekijk **op** de pagina Samenvatting de instellingen. Selecteer **Vorige** om de instellingen te wijzigen of selecteer **Volgende** om het rapport in Configuratiebeheer te maken. 
7. Selecteer **op** de pagina Voltooiing **sluiten** om de wizard af te sluiten en **open Rapportbouwer** om de rapportinstellingen in te voeren. Voer uw gebruikersaccount en wachtwoord in als u daarom wordt gevraagd en selecteer **OK.** Als Rapportbouwer niet op het apparaat is geïnstalleerd, wordt u gevraagd deze te installeren. Selecteer **Uitvoeren om Rapportbouwer te installeren,** die nodig is om rapporten te wijzigen en te maken. 


**Geef in Microsoft Report Builder**de SQL-instructie voor het rapport op en volg de volgende stappen:

1. Selecteer **gegevenssets**in het linkerdeelvenster en klik vervolgens met de rechtermuisknop op **Gegevensset toevoegen**.
2. Ga naar het tabblad **Query** en voer de naam in als *DataSet0*. 
3. Selecteer **Een gegevensset gebruiken die is ingesloten in mijn rapport;** Rapportbouwer wordt geopend.
4. Selecteer **gegevensbron**in **Rapportbouwer:**. Selecteer de standaardgegevensbron, die moet beginnen met 'AutoGen'. 
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




5. Navigeer naar het tabblad **Veld,** wehre-waarden voor **veldnaam** en **veldbron** moeten al worden ingevuld. Als dit niet het gaat, selecteert u **Toevoegen**en selecteert u **Queryveld**. Voer de **veldnaam** en **veldbron in**.
6. Herhaal dit voor elk van deze waarden: 
    - Fabrikant 
    - Model 
    - Serieel_getal 
    - HardwareHash
7. Kies **OK**.

**Definieer vervolgens de rapportweergave en maak het rapport** door de volgende stappen te volgen:

1. Selecteer **tabel of matrix**; een nieuwe wizard wordt geopend.
2. Selecteer **in Een gegevensset**kiezen de optie **Een bestaande gegevensset kiezen in dit rapport of een gedeelde gegevensset**.  
3. Selecteer **DataSet0** (de standaardinstelling) en selecteer **Volgende**.
4. Sleep **fabrikant,** **model**en **serienummer** naar het vak **Rijgroepen.** Sleep **HardwareHash** naar het vak **Waarden** en selecteer **Volgende**.
5. Schakel de selectievakjes uit voor **Subtotalen en eindtotalen en** **Groepen Vouwen/samenvouwen**. Selecteer **Volgende**.
6. Selecteer **Voltooien**.
7. Selecteer **Uitvoeren** om uw rapport uit te voeren. Controleer of het rapport de informatie bevat die u verwacht. Selecteer indien nodig **Het ontwerp** om terug te keren naar de ontwerpweergave om het rapport te wijzigen.
8. Selecteer **Opslaan** om het rapport op te slaan op de rapportserver. U het nieuwe rapport uitvoeren in het knooppunt Rapporten in de werkruimte Bewaken. 

**Ten slotte exporteert u het rapport en gebruikt u het om apparaten te registreren** door deze stappen te volgen. (U hoeft alleen stappen 1 en 2 van deze sectie te volgen als u na de vorige stappen hebt weggevigerd.):

1. Selecteer In de console Configuratiebeheer de optie **Controle**.
2. Vouw **rapportage**uit in **Bewaking**en selecteer **vervolgens Rapporten**.
3. Zoek het rapport met de naam die u eerder hebt gemaakt.
4. Klik met de rechtermuisknop op dit rapport en selecteer **Uitvoeren**.
5. Selecteer **exporteren** in het dialoogvenster dat wordt geopend en selecteer **Opslaan als CSV**.
6. In deze versie van het rapport worden hashes geëxtraheerd van alle Windows 10-apparaten waarmee Configuration Manager communiceert. U moet de resultaten filteren op alleen die apparaten die u wilt registreren bij Microsoft Managed Desktop.


> [!IMPORTANT]
> Met de query in Configuratiebeheer staan geen spaties toe in geëxporteerde kolomnamen. Daarom heb je tijdens de stappen 'Serial_Number' en 'HardwareHash' ingevoerd. Nu u het geëxporteerde CSV-bestand hebt, moet u de rapportkoppen bewerken om *serienummer* en *hardwarehash* te lezen, zoals hier wordt weergegeven voordat u verdergaat met apparaatregistratie.

Nu u overgaan tot [apparaten registreren met behulp van de Admin Portal](#register-devices-by-using-the-admin-portal).


#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell-scriptmethode

In een Active Directory-omgeving u de `Get-MMDRegistrationInfo` PowerShell-cmdlet gebruiken om de informatie op afstand te verzamelen van apparaten in Active Directory Groups met Behulp van WinRM. U de cmdlet ook gebruiken `Get-AD Computer` en gefilterde resultaten krijgen voor een specifieke hardwaremodelnamen die in de catalogus zijn opgenomen. Als u dit wilt doen, bevestigt u eerst deze vereisten en gaat u vervolgens verder met de stappen:

- WinRM is ingeschakeld.
- De apparaten die u wilt registreren, zijn actief in het netwerk (dat wil zeggen dat ze niet zijn losgekoppeld of uitgeschakeld).
- Zorg ervoor dat u een parameter voor domeinreferenties hebt die toestemming heeft om op afstand op de apparaten uit te voeren.
- Zorg ervoor dat Windows Firewall toegang biedt tot WMI. Voer hiervoor de volgende stappen uit:
    1. Open het configuratiescherm van **Het Configuratiescherm** van Windows Defender Firewall en selecteer **Een app of functie toestaan via Windows Defender Firewall**.
    2. Zoek **Windows Management Instrumentation (WMI)** in de lijst, schakel zowel privé als **openbaar**in en selecteer **vervolgens OK**.

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
3. Toegang tot alle mappen waar er mogelijk vermeldingen voor de apparaten. Verwijder vermeldingen voor elk apparaat uit *alle* mappen, waaronder Windows Server Active Directory Domain Services en Azure Active Directory. Wees ervan bewust dat deze verwijdering kan een paar uur duren om volledig te verwerken.
4. Toegangsbeheerservices waar mogelijk vermeldingen voor de apparaten zijn. Verwijder vermeldingen voor elk apparaat uit *alle* beheerservices, waaronder Microsoft Endpoint Configuration Manager, Microsoft Intune en Windows Autopilot. Wees ervan bewust dat deze verwijdering kan een paar uur duren om volledig te verwerken.

Nu u overgaan tot [het registreren van apparaten.](#register-devices)

#### <a name="manual-powershell-script-method"></a>Handmatige PowerShell-scriptmethode

1.  Open een PowerShell-prompt met beheerdersrechten.
2.  Uitvoeren`Install-Script -Name Get-MMDRegistrationInfo`
3.  Uitvoeren`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
4. [Voeg de hash-gegevens samen.](#merge-hash-data)

#### <a name="flash-drive-method"></a>Flash-stationmethode

1. Plaats een ander apparaat dan het apparaat dat u registreert, een USB-station.
2. Open een PowerShell-prompt met beheerdersrechten.
3. Uitvoeren`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`
4. Schakel het apparaat in dat u registreert, maar *start de installatie-ervaring niet.* Als u per ongeluk de installatie-ervaring start, moet u het apparaat opnieuw instellen of opnieuwimen.
5. Plaats het USB-station en druk op Shift + F10.
6. Open een PowerShell-prompt met beheerdersrechten en voer `cd <pathToUsb>` vervolgens uit .
7. Uitvoeren`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Uitvoeren`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
9. Verwijder het USB-station en schakel het apparaat uit door`shutdown -s -t 0`
10. [Voeg de hash-gegevens samen.](#merge-hash-data)

>[!IMPORTANT]
>Geef het apparaat dat u opnieuw registreert niet weer aan totdat u de registratie ervoor hebt voltooid. 



### <a name="merge-hash-data"></a>Hash-gegevens samenvoegen

Als u de hardwarehashgegevens hebt verzameld via de handmatige PowerShell- of flashdrive-methoden, moet u de gegevens in de CSV-bestanden nu hebben gecombineerd in één bestand om de registratie te voltooien. Hier volgt een PowerShell-script om dit eenvoudig te maken:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

Met de hash-gegevens samengevoegd in één CSV-bestand, u nu doorgaan met [het registreren van de apparaten.](#register-devices)

### <a name="register-devices"></a>Apparaten registreren

Het CSV-bestand moet in een bepaald formaat voor registratie staan. Als u de gegevens zelf hebt verzameld in de vorige stappen, moet het bestand al in de juiste indeling zijn. als u het bestand bij een leverancier verkrijgt, moet u mogelijk het formaat aanpassen.

>[!NOTE]
>Voor uw gemak u een [sjabloon](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) voor dit CSV-bestand downloaden.

Uw bestand moet **exact dezelfde kolomkoppen** bevatten als de voorbeeldkoppen (fabrikant, model, enz.), maar uw eigen gegevens voor de andere rijen. Als u de sjabloon gebruikt, opent u deze in een tekstbewerkingsgereedschap zoals Kladblok en u overwegen alle gegevens in rij 1 alleen te laten, waarbij alleen gegevens in rij 2 en lager worden invoeren. 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>Als u vergeet een van de voorbeeldgegevens te wijzigen, mislukt de registratie.

#### <a name="register-devices-by-using-the-admin-portal"></a>Apparaten registreren met behulp van de adminportal

Selecteer **Apparaten** in het linkernavigatiedeelvenster in de Microsoft Managed Desktop [Admin Portal.](https://aka.ms/mmdportal) Selecteer **+ Apparaten registreren**; de fly-in opent:

[![Fly-in na het selecteren van Apparaten registreren, apparaten met kolommen voor toegewezen gebruikers, serienummer, status, laatst geziene datum en leeftijd vermelden](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)


[//]: # (Helaas is dit niet waar. We kunnen deze notitie verwijderen - maar laat het nu tot we een kans om te chatten over.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Volg deze stappen:

1. Geef in **Bestandsupload**een pad op naar het CSV-bestand dat u eerder hebt gemaakt.
2. Optioneel u een **bestel-id** of **aankoop-id** toevoegen voor uw eigen trackingdoeleinden. Er zijn geen indelingsvereisten voor deze waarden.
3. Selecteer **Apparaten registreren**. Het systeem voegt de apparaten toe aan uw lijst met apparaten op het **apparaatblad,** gemarkeerd als **Registratie in behandeling.** Registratie duurt meestal minder dan 10 minuten, en wanneer het apparaat succesvol is, wordt weergegeven als **Klaar voor de gebruiker,** wat betekent dat het klaar is en wacht tot een eindgebruiker begint te gebruiken.


U de voortgang van apparaatregistratie volgen op de hoofdpagina **van Microsoft Managed Desktop - Devices.** Mogelijke staten gemeld zijn er:

| Status | Beschrijving |
|---------------|-------------|
| Inschrijving in behandeling | Registratie is nog niet gedaan. Kom later terug. |
| Registratie is mislukt | De inschrijving kon niet worden voltooid. Raadpleeg [de registratie van het apparaat voor probleemoplossing](#troubleshooting-device-registration) voor meer informatie. |
| Klaar voor de gebruiker | De registratie is geslaagd en het apparaat is nu klaar om te worden geleverd aan de eindgebruiker. Microsoft Managed Desktop begeleidt ze door de eerste tijdset-up, dus u hoeft geen verdere voorbereidingen te treffen. |
| Actief | Het apparaat is geleverd aan de eindgebruiker en ze hebben zich geregistreerd bij uw tenant. Dit geeft ook aan dat ze het apparaat regelmatig gebruiken. |
| Inactief | Het apparaat is geleverd aan de eindgebruiker en ze hebben zich geregistreerd bij uw tenant. Ze hebben het apparaat echter niet onlangs (in de afgelopen 7 dagen) gebruikt.  | 

#### <a name="troubleshooting-device-registration"></a>Apparaatregistratie oplossen

| Foutbericht | Details |
|---------------|-------------|
| Apparaat niet gevonden | We konden dit apparaat niet registreren omdat we geen overeenkomst konden vinden voor de geleverde fabrikant, het model of het serienummer. Bevestig deze waarden met uw apparaatleverancier. |
| Hardware hash niet geldig | De hardwarehash die u voor dit apparaat hebt geleverd, is niet correct opgemaakt. Controleer de hardware hash en vervolgens opnieuw in te dienen. |
| Apparaat al geregistreerd | Dit apparaat is al geregistreerd bij uw organisatie. Geen verdere actie vereist. |
| Apparaat geclaimd door een andere organisatie | Dit apparaat is al geclaimd door een andere organisatie. Neem contact op met uw apparaatleverancier. |
| Onverwachte fout | Uw aanvraag kan niet automatisch worden verwerkt. Neem contact op met de ondersteuning en geef de aanvraag-id op:<requestId> |

### <a name="check-the-image"></a>De afbeelding controleren

Als uw apparaat afkomstig is van een microsoft managed desktop-partnerleverancier, moet de afbeelding correct zijn.

U bent ook van harte welkom om de afbeelding toe te passen op uw eigen als u dat liever. Neem voor u contact op met de Microsoft-vertegenwoordiger waarmee u werkt en deze biedt u de locatie en stappen voor het toepassen van de afbeelding.

### <a name="deliver-the-device"></a>Het apparaat leveren

> [!IMPORTANT]
> Voordat u het apparaat aan uw gebruiker overhandigt, moet u ervoor zorgen dat u de [juiste licenties](../get-ready/prerequisites.md) voor die gebruiker hebt verkregen en toegepast.

Als alle licenties worden toegepast, u [uw gebruikers klaar maken om apparaten te gebruiken,](get-started-devices.md)en vervolgens kan uw gebruiker het apparaat opstarten en doorgaan met de Windows-installatieervaring.









