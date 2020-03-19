---
title: Registreer zelf nieuwe apparaten
description: Apparaten zelf registreren zodat ze kunnen worden beheerd door Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 1d4ca01e7b791dafc952b62a5f5dd59263b31546
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/07/2020
ms.locfileid: "42812034"
---
# <a name="register-new-devices-yourself"></a>Registreer zelf nieuwe apparaten

Microsoft Managed Desktop kan werken met gloednieuwe apparaten of u apparaten die u misschien al hebt opnieuw gebruiken (waarvoor u ze opnieuw moet afbeelding smaken). U apparaten registreren met Microsoft Managed Desktop op de Azure Portal.

> [!NOTE]
> Samenwerken met een partner om apparaten te verkrijgen? Als dat zo is, hoeft u zich geen zorgen te maken over het verkrijgen van de hardware hashes; Dat regelen ze wel voor je. Zorg ervoor dat uw partner een relatie met u aangaat in het [Partnercentrum](https://partner.microsoft.com/dashboard) en dat deze bevoegdheden voor Azure Active Directory en Office 365 bevatten. Uw partner kan meer informatie krijgen bij [Partner Center help.](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer) Zodra deze relatie is vastgesteld, zal uw partner gewoon apparaten namens u registreren - geen verdere actie die van u wordt verlangd. Zie Stappen voor partners om [apparaten te registreren](register-devices-partner.md)als u de details wilt zien of als uw partner vragen heeft. Zodra de apparaten zijn geregistreerd, u doorgaan met [het controleren van de afbeelding](#check-the-image) en het leveren van de [apparaten](#deliver-the-device) aan uw gebruikers.

## <a name="prepare-to-register-brand-new-devices"></a>Voorbereiden om gloednieuwe apparaten te registreren


Zodra u de nieuwe apparaten in de hand hebt, volgt u de volgende stappen:

1. [Verkrijg de hardwarehash voor elk apparaat.](#obtain-the-hardware-hash)
2. [De hashgegevens samenvoegen](#merge-hash-data)
3. [Registreer de apparaten in Microsoft Managed Desktop](#register-devices).
4. [Controleer nogmaals of de afbeelding correct is.](#check-the-image)
5. [Het apparaat leveren](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>De hardwarehash verkrijgen

Microsoft Managed Desktop identificeert elk apparaat uniek door te verwijzen naar de hardwarehash. Je hebt drie opties voor het verkrijgen van deze informatie:

- Vraag uw OEM-leverancier naar het AutoPilot-registratiebestand, dat de hardwarehashes bevat.
- Voer een [Windows PowerShell-script](#powershell-script-method) uit op elk apparaat en verzamel de resultaten in een bestand.
- Start elk apparaat- maar voltooi de Installatie-ervaring van Windows niet - en [verzamel de hashes op een verwisselbaar flashstation.](#flash-drive-method)

#### <a name="powershell-script-method"></a>PowerShell-scriptmethode

1.  Open een PowerShell-prompt met beheerdersrechten.
2.  Uitvoeren`Install-Script -Name Get-MMDRegistrationInfo`
3.  Uitvoeren`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`

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

>[!IMPORTANT]
>Ga niet meer in op het apparaat dat u registreert totdat u de registratie voor het apparaat hebt voltooid. 


### <a name="merge-hash-data"></a>Hashgegevens samenvoegen

U moet de gegevens in de CSV-bestanden in één bestand hebben gecombineerd om de registratie te voltooien. Hier is een voorbeeld PowerShell script om dit eenvoudig te maken:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`
### <a name="register-devices"></a>Apparaten registreren

Het CSV-bestand moet zich in een bepaalde indeling voor registratie hebben. Als u de gegevens zelf hebt verzameld in de vorige stappen, moet het bestand al in de juiste indeling zijn; als u het bestand van een leverancier verkrijgt, moet u mogelijk de indeling aanpassen.

>[!NOTE]
>Voor uw gemak u een [voorbeeld CSV-bestand](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv)downloaden.

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






