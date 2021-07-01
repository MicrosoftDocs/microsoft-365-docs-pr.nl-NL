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
ms.openlocfilehash: 2edee1b08f137d3e4f977b4d6800c1b0fc0e0473
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228169"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Meer informatie over beheerde basisapparaten voor mobiliteit en beveiliging

In dit artikel wordt beschreven hoe u Windows PowerShell voor meer informatie over de apparaten in uw organisatie die u hebt ingesteld voor Basismobiliteit en Beveiliging.

Hier ziet u een overzicht van de apparaatdetails die voor u beschikbaar zijn.

|**Details**|**Waar moet u naar zoeken in PowerShell**|
|:----------------|:------------------------------------------------------------------------------|
|Apparaat is geregistreerd voor Basismobiliteit en Beveiliging. Zie Uw mobiele apparaat registreren met [basismobiliteit en beveiliging voor meer informatie.](enroll-your-mobile-device.md)|De waarde van de *parameter isManaged*   is:<br/>**True**= apparaat is geregistreerd.<br/>**False**= apparaat is niet geregistreerd. |
|Apparaat voldoet aan het beveiligingsbeleid van uw apparaat. Zie Apparaatbeveiligingsbeleid [maken voor meer informatie](create-device-security-policies.md)|De waarde van de *parameter IsCompliant*   is:<br/>**Waar**   = apparaat voldoet aan beleidsregels.<br/>**Onwaar**   = apparaat voldoet niet aan beleidsregels.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="PowerShell-parameters voor basismobiliteit en beveiliging":::

> [!NOTE]
> De opdrachten en scripts in dit artikel geven ook informatie weer over apparaten die worden beheerd door [Microsoft Intune.](https://www.microsoft.com/cloud-platform/microsoft-intune)

## <a name="before-you-begin"></a>Voordat u begint

Er zijn een paar dingen die u moet instellen om de opdrachten en scripts uit te voeren die in dit artikel worden beschreven.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Stap 1: Download en installeer de Azure Active Directory module voor Windows PowerShell

Zie voor meer informatie over deze stappen [Verbinding maken te Microsoft 365 powershell.](/office365/enterprise/powershell/connect-to-office-365-powershell)

1. Ga naar Microsoft Online Services Sign-In Assistent voor [IT-professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)en   selecteer Downloaden voor Microsoft Online Services  **Aanmeldingsassistent**.

2. Installeer de module Microsoft Azure Active Directory voor Windows PowerShell met deze stappen:

    1. Open een PowerShell-opdrachtprompt op beheerdersniveau.

    2. Voer de `Install-Module MSOnline` opdracht uit.

    3. Als u wordt gevraagd om de NuGet provider te installeren, typt u Y en drukt u op ENTER.

    4. Als u wordt gevraagd om de module van PSGallery te installeren, typt u Y en drukt u op ENTER.

    5. Sluit na de installatie het powershell-opdrachtvenster.

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Stap 2: Verbinding maken uw Microsoft 365 abonnement

1. Voer in Windows Azure Active Directory module voor Windows PowerShell de volgende opdracht uit.

   ```powershell
   $UserCredential = Get-Credential
   ```

2. Typ in Windows PowerShell dialoogvenster Aanvraag voor referenties de gebruikersnaam en het wachtwoord voor uw Microsoft 365 globale beheerdersaccount en selecteer **OK.**

3. Voer de volgende opdracht uit:

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Stap 3: Zorg ervoor dat u PowerShell-scripts kunt uitvoeren

> [!NOTE]
> U kunt deze stap overslaan als u al bent ingesteld voor het uitvoeren van PowerShell-scripts.

Als u het script Get-MsolUserDeviceComplianceStatus.ps1 uitvoeren, moet u het uitvoeren van PowerShell-scripts inschakelen.

1. Selecteer op Windows bureaublad **Start** en typ Windows PowerShell. Klik met de rechtermuisknop Windows PowerShell en selecteer vervolgens **Uitvoeren als beheerder.**

2. Voer de volgende opdracht uit:

   ```powershell
   Set-ExecutionPolicy  RemoteSigned
   ```

3. Wanneer u daarom wordt gevraagd, typt u Y en drukt u op Enter.

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a>Voer de Get-MsolDevice cmdlet uit om details weer te geven voor alle apparaten in uw organisatie

1. Open de Microsoft Azure Active Directory module voor Windows PowerShell.

2. Voer de volgende opdracht uit:

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

Zie  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)voor meer voorbeelden.

## <a name="run-a-script-to-get-device-details"></a>Een script uitvoeren om apparaatdetails op te halen

Sla eerst het script op uw computer op.

1. Kopieer en plak de volgende tekst in Kladblok.

   ```powershell
   param (
   [PSObject[]]$users = @(),
   [Switch]$export,
   [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
   [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
   [System.Collections.IDictionary]$script:schema = @{
   DeviceId = ''
   DeviceOSType = ''
   DeviceOSVersion = ''
   DeviceTrustLevel = ''
   DisplayName = ''
   IsCompliant = ''
   IsManaged = ''
   ApproximateLastLogonTimestamp = ''
   DeviceObjectId = ''
   RegisteredOwnerUpn = ''
   RegisteredOwnerObjectId = ''
   RegisteredOwnerDisplayName = ''
   }
   function createResultObject
   {
   [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
   return $resultObject
   }
   If ($users.Count -eq 0)
   {
   $users = Get-MsolUser
   }
   [PSObject[]]$result = foreach ($u in $users)
   {
   [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
   foreach ($d in $devices)
   {
   [PSObject]$deviceResult = createResultObject
   $deviceResult.DeviceId = $d.DeviceId
   $deviceResult.DeviceOSType = $d.DeviceOSType
   $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
   $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
   $deviceResult.DisplayName = $d.DisplayName
   $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
   $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
   $deviceResult.DeviceObjectId = $d.ObjectId
   $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
   $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
   $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
   $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
   $deviceResult
   }
   }
   If ($export)
   {
   $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
   }
   Else
   {
   $result
   }
   ```

2. Sla het op als een Windows PowerShell scriptbestand met behulp van de bestandsextensie .ps1; bijvoorbeeld Get-MsolUserDeviceComplianceStatus.ps1.

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Voer het script uit om apparaatgegevens voor één gebruikersaccount op te halen

1. Open de Microsoft Azure Active Directory module voor Windows PowerShell.

2. Ga naar de map waar u het script hebt opgeslagen. Als u de opdracht bijvoorbeeld hebt opgeslagen in C:\PS-Scripts, voer dan de volgende opdracht uit.

   ```powershell
   cd C:\PS-Scripts
   ```

3. Voer de volgende opdracht uit om de gebruiker te identificeren voor wie u apparaatgegevens wilt krijgen. In dit voorbeeld worden details voor bar@example.com.

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. Voer de volgende opdracht uit om het script te starten.

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

De gegevens worden geëxporteerd naar uw Windows bureaublad als een CSV-bestand. U kunt extra parameters gebruiken om de bestandsnaam en het pad van de CSV op te geven.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Voer het script uit om apparaatgegevens voor een groep gebruikers op te halen

1. Open de Microsoft Azure Active Directory module voor Windows PowerShell.

2. Ga naar de map waar u het script hebt opgeslagen. Als u de opdracht bijvoorbeeld hebt opgeslagen in C:\PS-Scripts, voer dan de volgende opdracht uit.

   ```powershell
   cd C:\PS-Scripts
   ```

3. Voer de volgende opdracht uit om de groep te identificeren voor wie u apparaatgegevens wilt krijgen. In dit voorbeeld worden details voor gebruikers in de groep FinanceStaff op de voor u staan.

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. Voer de volgende opdracht uit om het script te starten.

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

De gegevens worden geëxporteerd naar uw Windows bureaublad als een CSV-bestand. U kunt extra parameters gebruiken om de bestandsnaam en het pad van de CSV op te geven.

## <a name="related-topics"></a>Gerelateerde onderwerpen

[Microsoft Verbinding maken is met pensioen](/collaborate/connect-redirect)

[Overzicht van de Basic Mobility en Security](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)
