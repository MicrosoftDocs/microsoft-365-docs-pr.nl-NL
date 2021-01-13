---
title: Nieuwe apparaten zelf registreren
description: Zelf apparaten registreren, zodat ze kunnen worden beheerd door Microsoft beheerde bureaubladversie
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: df6013f2f7fec32e79557a82f9b56fe4ad487786
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840679"
---
# <a name="register-new-devices-yourself"></a>Nieuwe apparaten zelf registreren

Microsoft Managed Desktop kan met gloednieuwe apparaten werken, maar u kunt ook apparaten opnieuw gebruiken die u al hebt (die u opnieuw wilt instellen. U kunt apparaten registreren met Microsoft Managed desktop in de portal van Microsoft Endpoint Manager.

> [!NOTE]
> Werkt u met een partner om apparaten te verkrijgen? Als dat zo is, hoeft u zich geen zorgen te maken over het verkrijgen van de hardware-hashes. ze zorgen voor u. Zorg ervoor dat uw partner een relatie met u tot stand brengt via het [partner centrum](https://partner.microsoft.com/dashboard). Uw partner kan meer te weten komen in de [Help van partner Center](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer). Wanneer deze relatie tot stand is gebracht, registreert uw partner zichzelf ook voor uw eigen actie – geen verdere actie vereist. Zie [stappen voor partners om apparaten te registreren](register-devices-partner.md)als u de gegevens wilt zien of uw partner vragen heeft. Wanneer de apparaten geregistreerd zijn, kunt u doorgaan met het [controleren van de afbeelding](#check-the-image) en [het leveren van de apparaten](#deliver-the-device) voor uw gebruikers.

## <a name="prepare-to-register-brand-new-devices"></a>Het registreren van gloednieuwe apparaten voorbereiden


Wanneer u de nieuwe apparaten in de hand hebt, volgt u deze stappen:

1. [De hardware-hash voor elk apparaat verkrijgen.](#obtain-the-hardware-hash)
2. [De hash-gegevens samenvoegen](#merge-hash-data)
3. [Registreer de apparaten in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).
4. [Controleer nog of de afbeelding klopt.](#check-the-image)
5. [Het apparaat leveren](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>De hardware-hash verkrijgen

Microsoft Managed Desktop identificeert elk apparaat uniek door te verwijzen naar de hardware-hash. U kunt deze informatie op drie manieren verkrijgen:

- Neem contact op met de leverancier van de fabrikant voor het auto pilot-registratiebestand, waaronder de hardware-hashes.
- Een [Windows PowerShell-script](#powershell-script-method) uitvoeren op elk apparaat en de resultaten in een bestand verzamelen.
- Start elk apparaat, maar voer de installatie van Windows niet uit, en [Verzamel de hashes op een verwisselbaar flashstation](#flash-drive-method).

#### <a name="powershell-script-method"></a>PowerShell-scriptmethode

U kunt het [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell-script op de website van de PowerShell-galerie gebruiken. Zie voor meer informatie over de apparaat-id en de hardware-hash, [apparaten toevoegen aan Windows auto pilot](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification).

1.  Open een PowerShell-prompt met beheerdersrechten.
2.  Uitgevoerd `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Uitgevoerd `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4.  Uitvoeren `powershell -ExecutionPolicy restricted` om te voorkomen dat er volgende niet-beperkte scripts worden uitgevoerd.


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

>[!IMPORTANT]
>Kracht niet op het apparaat dat u wilt registreren totdat u de registratie voor het apparaat hebt voltooid. 


### <a name="merge-hash-data"></a>Hash-gegevens samenvoegen

U moet de gegevens in de CSV-bestanden gecombineerd tot één bestand om de registratie te voltooien. Hieronder ziet u een voorbeeld van een PowerShell-script, zodat u dit eenvoudiger kunt maken:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a>Apparaten registreren met behulp van de beheer Portal

Selecteer in [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)de optie **apparaten** in het linker navigatiedeelvenster. Zoek de sectie Microsoft Managed Desktop van het menu en selecteer **apparaten**. Selecteer op de werkruimte Microsoft Managed Desktop apparaten de optie **+ register apparaten**, waarmee een invlucht wordt geopend om nieuwe apparaten te registreren.

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Ga als volgt te werk:

1. In **bestand uploaden** geeft u het pad op naar het CSV-bestand dat u eerder hebt gemaakt.
3. Selecteer **apparaten registreren**. Het systeem voegt de apparaten toe aan uw lijst met apparaten op **apparaten** **die zijn** gemarkeerd als geregistreerd. Registratie duurt meestal minder dan 10 minuten en wanneer het apparaat succesvol wordt weergegeven als u **klaar bent** , wordt de gebruiker gevraagd het programma te gebruiken.


U kunt de voortgang van apparaatregistratie controleren op de hoofdpagina. Mogelijke Staten hebben aangegeven:

| Status | Beschrijving |
|---------------|-------------|
| Registratie in behandeling | De registratie is nog niet voltooid. Ga later terug. |
| Registratie mislukt | Registreren kon niet worden voltooid. Zie [problemen met apparaatregistratie oplossen](#troubleshooting-device-registration) voor meer informatie. |
| Klaar voor gebruiker | De registratie is gelukt en het apparaat is nu gereed voor levering aan de gebruiker. Microsoft Managed Desktop richt ze voor de eerste keer instellen, dus u hoeft geen verdere voorbereidingen te treffen. |
| Actief | Het apparaat is doorgegeven aan de gebruiker en is geregistreerd bij uw Tenant. Met deze status wordt ook aangegeven dat ze regelmatig gebruikmaken van het apparaat. |
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





