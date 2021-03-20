---
title: Meer informatie over beheerde basisapparaten voor mobiliteit en beveiliging
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Gebruik Windows PowerShell voor meer informatie over basismobiliteits- en beveiligingsapparaten in uw organisatie.
ms.openlocfilehash: 92fcd6f39ffff97d7a4ecd2a69626ece54b481b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904250"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Meer informatie over beheerde basisapparaten voor mobiliteit en beveiliging

In dit artikel wordt beschreven hoe u Windows PowerShell gebruikt voor meer informatie over de apparaten in uw organisatie die u hebt ingesteld voor Basismobiliteit en Beveiliging.

Hier ziet u een overzicht van de apparaatdetails die voor u beschikbaar zijn.

|**Details**|**Waar moet u naar zoeken in PowerShell**|
|:----------------|:------------------------------------------------------------------------------|
|Apparaat is geregistreerd voor Basismobiliteit en Beveiliging. Zie Uw mobiele apparaat registreren met [basismobiliteit en beveiliging voor meer informatie.](enroll-your-mobile-device.md)|De waarde van de *parameter isManaged*   is:<br/>**True**= apparaat is geregistreerd.<br/>**False**= apparaat is niet geregistreerd. |
|Apparaat voldoet aan het beveiligingsbeleid van uw apparaat. Zie Apparaatbeveiligingsbeleid [maken voor meer informatie](create-device-security-policies.md)|De waarde van de *parameter IsCompliant*   is:<br/>**Waar**   = apparaat voldoet aan beleidsregels.<br/>**Onwaar**   = apparaat voldoet niet aan beleidsregels.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="PowerShell-parameters voor basismobiliteit en beveiliging":::

>[!NOTE]
>De opdrachten en scripts in dit artikel geven ook informatie weer over apparaten die worden beheerd door [Microsoft Intune.](https://www.microsoft.com/cloud-platform/microsoft-intune)

## <a name="before-you-begin"></a>Voordat u begint

Er zijn een paar dingen die u moet instellen om de opdrachten en scripts uit te voeren die in dit artikel worden beschreven.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Stap 1: De Azure Active Directory-module voor Windows PowerShell downloaden en installeren

Zie Verbinding maken met [Microsoft 365 met PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell)voor meer informatie over deze stappen.

1. Ga naar Microsoft Online Services Sign-In Assistent voor [IT-professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950)en   selecteer Downloaden voor Microsoft Online Services  **Aanmeldingsassistent**.

2. Installeer de module Microsoft Azure Active Directory voor Windows PowerShell met deze stappen:

    1. Open een PowerShell-opdrachtprompt op beheerdersniveau.  

    2. Voer de installatie-module MSOnline uit.

    3. Als u wordt gevraagd om de NuGet provider te installeren, typt u Y en drukt u op ENTER.

    4. Als u wordt gevraagd om de module van PSGallery te installeren, typt u Y en drukt u op ENTER.

    5. Sluit na de installatie het powershell-opdrachtvenster.

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Stap 2: Verbinding maken met uw Microsoft 365-abonnement

1. Voer in de Windows Azure Active Directory-module voor Windows PowerShell de volgende opdracht uit.  

    $UserCredential = Get-Credential

2. Typ in het dialoogvenster Aanmeldingsaanvraag voor Windows PowerShell de gebruikersnaam en het wachtwoord voor uw globale beheerdersaccount van Microsoft 365 en selecteer **OK.**

3. Voer de volgende opdracht uit.

    Connect-MsolService -Credential $UserCredential

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Stap 3: Zorg ervoor dat u PowerShell-scripts kunt uitvoeren

>[!NOTE]
>U kunt deze stap overslaan als u al bent ingesteld voor het uitvoeren van PowerShell-scripts.

Als u het script Get-MsolUserDeviceComplianceStatus.ps1 uitvoeren, moet u het uitvoeren van PowerShell-scripts inschakelen.

1. Selecteer start op uw Windows-bureaublad **en** typ vervolgens Windows PowerShell. Klik met de rechtermuisknop op Windows PowerShell en selecteer **vervolgens Uitvoeren als beheerder.**

2. Voer de volgende opdracht uit.

    Set-ExecutionPolicy RemoteSigned

3. Wanneer u daarom wordt gevraagd, typt u Y en drukt u op Enter.

**Voer de Get-MsolDevice cmdlet uit om details weer te geven voor alle apparaten in uw organisatie**

1. Open de Microsoft Azure Active Directory-module voor Windows PowerShell.  

2. Voer de volgende opdracht uit.

    Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_. RegisteredOwners.Count -gt 0}

Zie  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)voor meer voorbeelden.

## <a name="run-a-script-to-get-device-details"></a>Een script uitvoeren om apparaatdetails op te halen

Sla eerst het script op uw computer op.

1. Kopieer en plak de volgende tekst in Kladblok.  

2.  param (

3.  [PSObject[]]$users = @(),

4.  [Schakel]$export,

5.  [Tekenreeks]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",

6.  [Tekenreeks]$exportPath = [Omgeving]::GetFolderPath("Bureaublad")

7.  )

9.  [System.Collections.IDictionary]$script:schema = @{

11.  DeviceId = ''

12.  DeviceOSType = ''

13.  DeviceOSVersion = ''

14.  DeviceTrustLevel = ''

15.  DisplayName = ''

16.  IsCompliant = ''

17.  IsManaged = ''

18.  ApproximateLastLogonTimestamp = ''

19.  DeviceObjectId = ''

20.  RegisteredOwnerUpn = ''

21.  RegisteredOwnerObjectId = ''
    

22.  RegisteredOwnerDisplayName = ''
    

23.  }
    

25.  functie createResultObject
    

26.  {
    

28.  [PSObject]$resultObject = New-Object -TypeName PSObject -Eigenschap $script:schema
    

30.  retourn $resultObject
    

31.  }
    

33.  Als ($users. Aantal -eq 0)
    

34.  {
    

35.  $users = Get-MsolUser
    

36.  }
    

38.  [PSObject[]]$result = foreach ($u in $users)
    

39.  {
    

41.  [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
    

42.  foreach ($d in $devices)
    

43.  {
    

44.  [PSObject]$deviceResult = createResultObject
    

45.  $deviceResult.DeviceId = $d.DeviceId
    

46.  $deviceResult.DeviceOSType = $d.DeviceOSType
    

47.  $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
    

48.  $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
    

49.  $deviceResult.DisplayName = $d.DisplayName
    

50.  $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
    

51.  $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
    

52.  $deviceResult.DeviceObjectId = $d.ObjectId
    

53.  $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
    

54.  $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
    

55.  $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
    

56.  $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
    

58.  $deviceResult
    

59.  }
    

61.  }
    

63.  Als ($export)
    

64.  {
    

65.  $result | Export-Csv -pad ($exportPath + " \" + $exportFileName) -NoTypeInformation
    

66.  }
    

67.  Else
    

68.  {
    

69.  $result
    

70.  }
    

71.  Sla het op als een Windows PowerShell-scriptbestand met de bestandsextensie .ps1; bijvoorbeeld Get-MsolUserDeviceComplianceStatus.ps1.   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Voer het script uit om apparaatgegevens voor één gebruikersaccount op te halen

1. Open de Microsoft Azure Active Directory-module voor Windows PowerShell.
    
2. Ga naar de map waar u het script hebt opgeslagen. Als u de opdracht bijvoorbeeld hebt opgeslagen in C:\PS-Scripts, voer dan de volgende opdracht uit.
    
    cd C:\PS-Scripts

3. Voer de volgende opdracht uit om de gebruiker te identificeren voor wie u apparaatgegevens wilt krijgen. In dit voorbeeld worden details voor bar@example.com.
    
    $u = Get-MsolUser -UserPrincipalName bar@example.com

4. Voer de volgende opdracht uit om het script te starten.

    .\Get-MsolUserDeviceComplianceStatus.ps1 -Gebruiker $u -Exporteren

De gegevens worden geëxporteerd naar uw Windows-bureaublad als csv-bestand. U kunt extra parameters gebruiken om de bestandsnaam en het pad van de CSV op te geven.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Voer het script uit om apparaatgegevens voor een groep gebruikers op te halen

1. Open de Microsoft Azure Active Directory-module voor Windows PowerShell.
    
2. Ga naar de map waar u het script hebt opgeslagen. Als u de opdracht bijvoorbeeld hebt opgeslagen in C:\PS-Scripts, voer dan de volgende opdracht uit.   

    cd C:\PS-Scripts

3. Voer de volgende opdracht uit om de groep te identificeren voor wie u apparaatgegevens wilt krijgen. In dit voorbeeld worden details voor gebruikers in de groep FinanceStaff op de voor u staan. 

    $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_. ObjectId }

4. Voer de volgende opdracht uit om het script te starten.

    .\Get-MsolUserDeviceComplianceStatus.ps1 -Gebruiker $u -Exporteren

De gegevens worden geëxporteerd naar uw Windows-bureaublad als csv-bestand. U kunt extra parameters gebruiken om de bestandsnaam en het pad van de CSV op te geven.

## <a name="related-topics"></a>Verwante onderwerpen

[Microsoft Connect is met pensioen](/collaborate/connect-redirect)

[Overzicht van de Basic Mobility en Security](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)