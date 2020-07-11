---
title: Nieuwe apparaten zelf registreren
description: Registreer apparaten zelf zodat ze kunnen worden beheerd door Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 3c43c42ba2cb1feb339ad61b76d28fde4ed94298
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101657"
---
# <a name="register-new-devices-yourself"></a>Nieuwe apparaten zelf registreren

Microsoft Managed Desktop kan werken met gloednieuwe apparaten of u apparaten die u mogelijk al hebt hergebruiken (waarvoor u ze opnieuw moet imagen). U apparaten registreren met behulp van de Microsoft Managed Desktop Admin Portal.

> [!NOTE]
> Werken met een partner om apparaten te verkrijgen? Als dat zo is, hoeft u zich geen zorgen te maken over het verkrijgen van de hardware hashes; Dat regelen ze wel voor je. Zorg ervoor dat uw partner een relatie met u aangaat in het [Partner Center.](https://partner.microsoft.com/dashboard) Uw partner kan meer informatie leren bij [Partner Center help.](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer) Zodra deze relatie tot stand is gekomen, zal uw partner eenvoudig apparaten namens u registreren - geen verdere actie van u vereist. Zie Stappen voor partners om [apparaten te registreren](register-devices-partner.md)als u de gegevens wilt zien of als uw partner vragen heeft. Zodra de apparaten zijn geregistreerd, u doorgaan met [het controleren van de afbeelding](#check-the-image) en het leveren van de [apparaten](#deliver-the-device) aan uw gebruikers.

## <a name="prepare-to-register-brand-new-devices"></a>Voorbereiden om gloednieuwe apparaten te registreren


Zodra u de nieuwe apparaten in de hand hebt, volgt u de volgende stappen:

1. [Verkrijg de hardwarehash voor elk apparaat.](#obtain-the-hardware-hash)
2. [De hash-gegevens samenvoegen](#merge-hash-data)
3. [Registreer de apparaten in Microsoft Managed Desktop](#register-devices).
4. [Controleer of de afbeelding juist is.](#check-the-image)
5. [Het apparaat leveren](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>De hardwarehash verkrijgen

Microsoft Managed Desktop identificeert elk apparaat op unieke wijze door te verwijzen naar de hardwarehash. Je hebt drie opties voor het verkrijgen van deze informatie:

- Vraag uw OEM-leverancier om het AutoPilot-registratiebestand, dat de hardwarehashes bevat.
- Voer een [Windows PowerShell-script](#powershell-script-method) uit op elk apparaat en verzamel de resultaten in een bestand.
- Start elk apparaat - maar voltooi de Windows-installatieervaring niet - en [verzamel de hashes op een verwisselbaar flashstation](#flash-drive-method).

#### <a name="powershell-script-method"></a>PowerShell-scriptmethode

1.  Open een PowerShell-prompt met beheerdersrechten.
2.  Uitvoeren`Install-Script -Name Get-MMDRegistrationInfo`
3.  Uitvoeren`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`

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

>[!IMPORTANT]
>Geef het apparaat dat u opnieuw registreert niet weer aan totdat u de registratie ervoor hebt voltooid. 


### <a name="merge-hash-data"></a>Hash-gegevens samenvoegen

U moet de gegevens in de CSV-bestanden hebben gecombineerd in één bestand om de registratie te voltooien. Hier volgt een PowerShell-script om dit eenvoudig te maken:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`
### <a name="register-devices"></a>Apparaten registreren

Het CSV-bestand moet in een bepaald formaat voor registratie staan. Als u de gegevens zelf hebt verzameld in de vorige stappen, moet het bestand al in de juiste indeling zijn. als u het bestand bij een leverancier verkrijgt, moet u mogelijk het formaat aanpassen.

>[!NOTE]
>Voor uw gemak u een [voorbeeld van CSV-bestand](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv)downloaden.

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






