---
title: Bekijk Microsoft 365 licenties en services met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- O365ITProTrain
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: Hier wordt uitgelegd hoe u PowerShell gebruikt om informatie weer te geven over de licentieplannen, services en licenties die beschikbaar zijn in uw Microsoft 365 organisatie.
ms.openlocfilehash: 08f48301001ee6a40318428f3310eab8b0d0a351
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924634"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a>Bekijk Microsoft 365 licenties en services met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Elk Microsoft 365 abonnement bestaat uit de volgende elementen:

- **Licentieplannen** Deze worden ook wel licentieplannen of Microsoft 365 genoemd. Licentieplannen definiëren de Microsoft 365 services die beschikbaar zijn voor gebruikers. Uw Microsoft 365 kan meerdere licentieplannen bevatten. Een voorbeeld van een licentieplan is Microsoft 365 E3.
    
- **Services** Deze worden ook wel serviceplannen genoemd. Services zijn de Microsoft 365 producten, functies en mogelijkheden die beschikbaar zijn in elk licentieplan, bijvoorbeeld Exchange Online en Microsoft 365-apps voor ondernemingen (voorheen Office 365 ProPlus). Gebruikers kunnen meerdere licenties aan hen hebben toegewezen vanuit verschillende licentieplannen die toegang verlenen tot verschillende services.
    
- **Licenties** Elk licentieplan bevat het aantal licenties dat u hebt gekocht. U wijst licenties toe aan gebruikers, zodat ze de Microsoft 365 services kunnen gebruiken die zijn gedefinieerd in het licentieplan. Voor elk gebruikersaccount is ten minste één licentie van één licentieplan vereist, zodat ze zich kunnen aanmelden bij Microsoft 365 en de services kunnen gebruiken.
    
U kunt PowerShell gebruiken voor Microsoft 365 om details weer te geven over de beschikbare licentieplannen, licenties en services in uw Microsoft 365 organisatie. Zie Voor meer informatie over de producten, functies en services die beschikbaar zijn in verschillende Office 365 abonnementen, [Office 365 Abonnementsopties.](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>De powershell Azure Active Directory powershell gebruiken voor Graph module

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
Voer deze opdracht uit als u overzichtsgegevens wilt weergeven over uw huidige licentieplannen en de beschikbare licenties voor elk abonnement:
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

De resultaten bevatten:
  
- **SkuPartNumber:** Toont de beschikbare licentieplannen voor uw organisatie. Is bijvoorbeeld de `ENTERPRISEPACK` naam van het licentieplan voor Office 365 Enterprise E3.
    
- **Ingeschakeld:** Het aantal licenties dat u hebt gekocht voor een specifiek licentieplan.
    
- **ConsumedUnits:** Het aantal licenties dat u aan gebruikers hebt toegewezen vanuit een specifiek licentieplan.
    
Als u details wilt bekijken over Microsoft 365 services die beschikbaar zijn in al uw licentieplannen, geeft u eerst een lijst met uw licentieplannen weer.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Sla vervolgens de informatie over de licentieplannen op in een variabele.

```powershell
$licenses = Get-AzureADSubscribedSku
```

Vervolgens worden de services weergegeven in een specifiek licentieplan.

```powershell
$licenses[<index>].ServicePlans
```

\<index> is een geheel getal dat het rijnummer van het licentieplan aangeeft vanaf de weergave van de `Get-AzureADSubscribedSku | Select SkuPartNumber` opdracht, min 1.

Als de weergave van de opdracht bijvoorbeeld de volgende `Get-AzureADSubscribedSku | Select SkuPartNumber` is:

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

De opdracht om de services voor het ENTERPRISEPREMIUM-licentieplan weer te geven, is de volgende:

```powershell
$licenses[2].ServicePlans
```

ENTERPRISEPREMIUM is de derde rij. Daarom is de indexwaarde (3 - 1) of 2.

Zie Productnamen en [serviceplanaanduidingen](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)voor licenties voor een volledige lijst met licentieplannen (ook wel productnamen genoemd), de bijbehorende serviceplannen en de bijbehorende vriendelijke namen.

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

>[!Note]
>Er is een PowerShell-script beschikbaar dat de procedures automatiseert die in dit onderwerp worden beschreven. Met het script kunt u services weergeven en uitschakelen in uw Microsoft 365 organisatie, inclusief Sway. Zie Toegang tot [Sway uitschakelen met PowerShell voor meer informatie.](disable-access-to-sway-with-microsoft-365-powershell.md)
>
    
Voer de volgende opdracht uit als u overzichtsinformatie wilt weergeven over uw huidige licentieplannen en de beschikbare licenties voor elk abonnement:
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

De resultaten bevatten de volgende informatie:
  
- **AccountSkuId:** Laat de beschikbare licentieplannen voor uw organisatie zien met de syntaxis `<CompanyName>:<LicensingPlan>` .  _\<CompanyName>_ is de waarde die u hebt opgegeven toen u zich Microsoft 365 en is uniek voor uw organisatie. De _\<LicensingPlan>_ waarde is voor iedereen hetzelfde. In de waarde is bijvoorbeeld de bedrijfsnaam en de naam van het licentieplan de systeemnaam voor Office 365 Enterprise `litwareinc:ENTERPRISEPACK` `litwareinc` `ENTERPRISEPACK` E3.
    
- **ActiveUnits:** Het aantal licenties dat u hebt gekocht voor een specifiek licentieplan.
    
- **WarningUnits:** Het aantal licenties in een licentieplan dat u niet hebt verlengd en dat na de respijtperiode van 30 dagen verloopt.
    
- **ConsumedUnits:** Het aantal licenties dat u aan gebruikers hebt toegewezen vanuit een specifiek licentieplan.
    
Voer de volgende opdracht uit om details Microsoft 365 services weer te geven die beschikbaar zijn in al uw licentieplannen:
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

In de volgende tabel ziet u Microsoft 365 serviceplannen en hun vriendelijke namen voor de meest voorkomende services. Uw lijst met serviceplannen kan anders zijn. 
  
|**Serviceplan**|**Beschrijving**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Microsoft 365-apps voor ondernemingen *(eerder benoemd Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype voor Bedrijven Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online Abonnement 2  <br/> |
   
Zie Productnamen en [serviceplanaanduidingen](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)voor licenties voor een volledige lijst met licentieplannen (ook wel productnamen genoemd), de bijbehorende serviceplannen en de bijbehorende vriendelijke namen.

Gebruik de volgende syntaxis om details Microsoft 365 services weer te geven die beschikbaar zijn in een specifiek licentieplan.
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

In dit voorbeeld ziet u de services die beschikbaar zijn in het licentieplan litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3).
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)