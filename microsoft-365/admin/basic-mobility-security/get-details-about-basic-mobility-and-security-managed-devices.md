---
title: Meer informatie over basis apparatuur voor de mobiliteit en beveiliging
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
description: Gebruik Windows PowerShell voor informatie over de basis-en beveiligingsapparaten van uw organisatie.
ms.openlocfilehash: 7b041e54d512291163616d3b61973cef989cec5c
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336813"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Meer informatie over basis apparatuur voor de mobiliteit en beveiliging

In dit artikel leest u hoe u Windows PowerShell kunt gebruiken voor informatie over de apparaten in uw organisatie die u instelt voor eenvoudige mobiliteit en beveiliging.

Dit is een uitsplitsing van de details van het apparaat.

|**Details**|**Waarnaar moet worden gezocht in PowerShell**|
|:----------------|:------------------------------------------------------------------------------|
|Apparaat is ingeschreven voor eenvoudige mobiliteit en beveiliging. Zie voor meer informatie [uw mobiele apparaat registreren met behulp van eenvoudige mobiliteit en beveiliging](enroll-your-mobile-device-using-basic-mobility-and-security.md)|De waarde van de *isManaged*   parameter isManaged is:<br/>**Waar**= apparaat is ingeschreven.<br/>**Onwaar**= apparaat is niet geregistreerd. |
|Apparaat is compatibel met uw beveiligingsbeleid voor apparaten. Zie [beveiligingsbeleid voor apparaten maken](create-device-security-policies-in-basic-mmobility-and-security.md) voor meer informatie.|De waarde van de *isCompliant*   parameter isCompliant is:<br/>**Waar**   = apparaat is compatibel met beleidsregels.<br/>**Onwaar**   = apparaat is niet compatibel met beleidsregels.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Basisparameters voor mobiliteit en beveiliging PowerShell":::

>[!NOTE]
>De opdrachten en scripts in dit artikel geven ook details weer over de apparaten die door [Microsoft intune](https://www.microsoft.com/cloud-platform/microsoft-intune)worden beheerd.

## <a name="before-you-begin"></a>Voordat u begint

Er zijn een paar dingen die u moet instellen om de opdrachten en scripts uit te voeren die in dit artikel worden beschreven.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Stap 1: de Azure Active Directory-module voor Windows PowerShell downloaden en installeren

Zie [verbinding maken met Microsoft 365 met PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)voor meer informatie over deze stappen.

1. Ga naar de [Microsoft Online Services-aanmeldhulp voor IT-professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950)   en selecteer  **downloaden voor Microsoft Online Services-aanmeldhulp**.   

2. Installeer de module Microsoft Azure Active Directory voor Windows PowerShell met deze stappen:   

    1. Open een opdrachtprompt voor de PowerShell-beheerniveau.  

    2. Voer de installatie-module MSOnline uit.
    
    3. Als u wordt gevraagd om de NuGet provider te installeren, typt u Y en drukt u op ENTER.   

    4. Als u wordt gevraagd om de module van PSGallery te installeren, typt u Y en drukt u op ENTER.   

    5. Na de installatie sluit u het PowerShell-opdrachtvenster.
    
### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Stap 2: verbinding maken met uw Microsoft 365-abonnement

1. Voer de volgende opdracht uit in de Windows Azure Active Directory-module voor Windows PowerShell.  

    $UserCredential = Get-Credential

2. Typ in het dialoogvenster referentie aanvraag voor Windows PowerShell de gebruikersnaam en het wachtwoord voor uw globale beheerdersaccount van Microsoft 365 en selecteer **OK**.
    
3. Voer de volgende opdracht uit.
    
    Connect-MsolService-Credential $UserCredential

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Stap 3: controleren of u PowerShell-scripts kunt uitvoeren

>[!NOTE]
>U kunt deze stap overslaan als u al bent geconfigureerd voor het uitvoeren van PowerShell-scripts.

Als u het Get-MsolUserDeviceComplianceStatus.ps1 script wilt uitvoeren, moet u de uitvoering van PowerShell-scripts inschakelen.

1. Selecteer op het Windows-bureaublad de optie **Start**en typ Windows PowerShell. Klik met de rechtermuisknop op Windows PowerShell en selecteer **als administrator uitvoeren**.

2. Voer de volgende opdracht uit.
    
    Set-ExecutionPolicy RemoteSigned

3. Wanneer u hierom wordt gevraagd, typt u Y en drukt u op ENTER.
    
**De cmdlet Get-MsolDevice uitvoeren om de details weer te geven van alle apparaten in uw organisatie**

1. Open de Microsoft Azure Active Directory-module voor Windows PowerShell.  

2. Voer de volgende opdracht uit.
    
    Get-MsolDevice-all-ReturnRegisteredOwners | Where-object {$ _. RegisteredOwners. Count-gt 0}

Zie  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)voor meer voorbeelden.

## <a name="run-a-script-to-get-device-details"></a>Een script uitvoeren om details van apparaat te achterhalen

Sla eerst het script op uw computer op.

1. Kopieer en plak de volgende tekst in Kladblok.  

2.  wil zeggen param
    

3.  [PSObject []] $users = @ (),
    

4.  [Schakeloptie] $export
    

5.  [Tekenreeks] $exportFileName = "UserDeviceComplianceStatus_" + (Get-date-indeling "yyMMdd_HHMMss") + ". csv",
    

6.  [Tekenreeks] $exportPath = [Environment]:: GetFolderPath ("bureaublad")
    

7.  )
    

9.  [System. Collection. IDictionary] $script: schema = @ {
    

11.  DeviceId = ' '
    

12.  DeviceOSType = ' '
    

13.  DeviceOSVersion = ' '
    

14.  DeviceTrustLevel = ' '
    

15.  DisplayName = ' '
    

16.  IsCompliant = ' '
    

17.  IsManaged = ' '
    

18.  ApproximateLastLogonTimestamp = ' '
    

19.  DeviceObjectId = ' '
    

20.  RegisteredOwnerUpn = ' '
    

21.  RegisteredOwnerObjectId = ' '
    

22.  RegisteredOwnerDisplayName = ' '
    

23.  }
    

25.  createResultObject, functie
    

26.  {
    

28.  [PSObject] $resultObject = New-object-TypeName PSObject-eigenschap $script: schema
    

30.  retour $resultObject
    

31.  }
    

33.  Als ($users. Aantal-EQ 0)
    

34.  {
    

35.  $users = get-MsolUser
    

36.  }
    

38.  [PSObject []] $result = foreach ($u in $users)
    

39.  {
    

41.  [PSObject] $devices = Get-msoldevice-RegisteredOwnerUpn $u. UserPrincipalName
    

42.  foreach ($d in $devices)
    

43.  {
    

44.  [PSObject] $deviceResult = createResultObject
    

45.  $deviceResult. DeviceId = $d. DeviceId
    

46.  $deviceResult. DeviceOSType = $d. DeviceOSType
    

47.  $deviceResult. DeviceOSVersion = $d. DeviceOSVersion
    

48.  $deviceResult. DeviceTrustLevel = $d. DeviceTrustLevel
    

49.  $deviceResult. naam = $d. DisplayName
    

50.  $deviceResult. IsCompliant = $d. GraphDeviceObject. IsCompliant
    

51.  $deviceResult. IsManaged = $d. GraphDeviceObject. IsManaged
    

52.  $deviceResult. DeviceObjectId = $d. ObjectId
    

53.  $deviceResult. RegisteredOwnerUpn = $u. UserPrincipalName
    

54.  $deviceResult. RegisteredOwnerObjectId = $u. ObjectId
    

55.  $deviceResult. RegisteredOwnerDisplayName = $u. DisplayName
    

56.  $deviceResult. ApproximateLastLogonTimestamp = $d. ApproximateLastLogonTimestamp
    

58.  $deviceResult
    

59.  }
    

61.  }
    

63.  Als ($export)
    

64.  {
    

65.  $result | Export-csv-pad ($exportPath + " \" + $exportFileName)-NoTypeInformation
    

66.  }
    

67.  Zaken
    

68.  {
    

69.  $result
    

70.  }
    

71.  Sla het bestand op als een Windows PowerShell-scriptbestand met de bestandsextensie. ps1. Get-MsolUserDeviceComplianceStatus.ps1 bijvoorbeeld.   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Voer het script uit om apparaatgegevens voor één gebruikersaccount op te halen

1. Open de Microsoft Azure Active Directory-module voor Windows PowerShell.
    
2. Ga naar de map waarin u het script hebt opgeslagen. Voer de volgende opdracht uit als u het bestand hebt opgeslagen op C:\PS-Scripts.
    
    CD-C:\PS-Scripts

3. Voer de volgende opdracht uit om de gebruiker te identificeren voor wie u informatie over apparaten wilt hebben. In dit voorbeeld worden gegevens opgehaald voor bar@example.com.
    
    $u = Get-MsolUser-UserPrincipalName bar@example.com

4. Voer de volgende opdracht uit om het script te starten.

    .\Get-MsolUserDeviceComplianceStatus.ps1-gebruikers $u-exporteren

De gegevens worden geëxporteerd naar het Windows-bureaublad als een CSV-bestand. U kunt aanvullende parameters gebruiken om de bestandsnaam en het pad van het CSV-bestand op te geven.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Voer het script uit om informatie over apparaten te krijgen voor een groep gebruikers

1. Open de Microsoft Azure Active Directory-module voor Windows PowerShell.
    
2. Ga naar de map waarin u het script hebt opgeslagen. Voer de volgende opdracht uit als u het bestand hebt opgeslagen op C:\PS-Scripts.   

    CD-C:\PS-Scripts

3. Voer de volgende opdracht uit om te achterhalen met welke groep u apparaatgegevens moet achterhalen. In dit voorbeeld worden de details van gebruikers in de FinanceStaff-groep opgehaald. 

    $u = Get-MsolGroupMember-SearchString "FinanceStaff" | % {Get-MsolUser-ObjectId $ _. ObjectId

4. Voer de volgende opdracht uit om het script te starten.   

    .\Get-MsolUserDeviceComplianceStatus.ps1-gebruikers $u-exporteren

De gegevens worden geëxporteerd naar het Windows-bureaublad als een CSV-bestand. U kunt aanvullende parameters gebruiken om de bestandsnaam en het pad van het CSV-bestand op te geven.

## <a name="related-topics"></a>Verwante onderwerpen

[Microsoft Connect is buiten gebruik gesteld](https://docs.microsoft.com/collaborate/connect-redirect)

[Overzicht van eenvoudige mobiliteit en beveiliging](overview-of-basic-mobility-and-security-for-microsoft-365.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)