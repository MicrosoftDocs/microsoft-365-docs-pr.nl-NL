---
title: Licenties en services van Microsoft 365 weergeven met PowerShell
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
description: In dit artikel wordt uitgelegd hoe u PowerShell kunt gebruiken voor het bekijken van informatie over licenties, services en licenties die beschikbaar zijn in uw Microsoft 365-organisatie.
ms.openlocfilehash: 3275a513de3c114076e792ab6c5ef86b1413571c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689190"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a>Licenties en services van Microsoft 365 weergeven met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Elk Microsoft 365-abonnement bestaat uit de volgende onderdelen:

- **Licentie plannen** Dit zijn ook wel licentie-abonnementen of Microsoft 365-abonnementen. Met licentie plannen wordt bepaald welke Microsoft 365-services beschikbaar zijn voor gebruikers. Uw Microsoft 365-abonnement kan meerdere licentie abonnementen bevatten. Een voorbeeld van een licentie plan is Microsoft 365 E3.
    
- **Services** Dit worden ook wel service-abonnementen genoemd. Services zijn de Microsoft 365-producten,-functies en-functies die beschikbaar zijn in elk licentie plan, bijvoorbeeld Exchange Online en Microsoft 365-apps voor Enterprise (voorheen Office 365 ProPlus). Gebruikers kunnen een licentie aan hen toewijzen vanuit verschillende licentie plannen die toegang hebben tot verschillende services.
    
- **Licentie** Elk licentie plan bevat het aantal licenties dat u hebt aangeschaft. U kunt licenties toewijzen aan gebruikers, zodat ze gebruikmaken van de Microsoft 365-services die zijn gedefinieerd door het licentie plan. Voor elke gebruikersaccount is minimaal één licentie vereist, zodat ze zich kunnen aanmelden bij Microsoft 365 en de services kunnen gebruiken.
    
Met PowerShell voor Microsoft 365 kunt u informatie weergeven over de beschikbare licentie-abonnementen, licenties en services in uw Microsoft 365-organisatie. Zie voor meer informatie over de producten, functies en services die beschikbaar zijn in de verschillende Office 365-abonnementen, [Office 365-abonnement opties](https://go.microsoft.com/fwlink/p/?LinkId=691147).


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph module gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Voer de volgende opdracht uit om samenvattingsinformatie weer te geven over uw huidige licentie plannen en de beschikbare licenties voor elk abonnement:
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

De resultaten bevatten:
  
- **SkuPartNumber:** Hier ziet u de beschikbare licentie plannen voor uw organisatie. Voorbeeld: `ENTERPRISEPACK` de naam van het licentie plan voor Office 365 Enterprise E3.
    
- **Ingeschakeld:** Het aantal licenties dat u hebt aangeschaft voor een specifiek licentie plan.
    
- **ConsumedUnits:** Het aantal licenties dat u hebt toegewezen aan gebruikers uit een specifiek licentie plan.
    
Als u informatie wilt bekijken over de Microsoft 365-services die in al uw licentie plannen beschikbaar zijn, geeft u eerst een lijst met uw licentie plannen weer.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Vervolgens slaat u de gegevens van het licentie plan op in een variabele.

```powershell
$licenses = Get-AzureADSubscribedSku
```

Vervolgens kunt u de services in een specifiek licentie plan weergeven.

```powershell
$licenses[<index>].ServicePlans
```

\<index> is een geheel getal dat het rijnummer van het licentie plan opgeeft in de weergave van de `Get-AzureADSubscribedSku | Select SkuPartNumber` opdracht, min 1.

Als de weergave van de opdracht bijvoorbeeld `Get-AzureADSubscribedSku | Select SkuPartNumber` :

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

Voer de volgende opdracht uit om de services voor het ENTERPRISEPREMIUM-licentie plan weer te geven:

```powershell
$licenses[2].ServicePlans
```

ENTERPRISEPREMIUM is de derde rij. Daarom is de indexwaarde (3-1) of 2.

Voor een volledige lijst met licentie plannen (ook wel productnamen genoemd), de opgenomen serviceplannen en de bijbehorende beschrijvende namen, raadpleegt u [productnamen en serviceplan-id's voor licenties](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

>[!Note]
>Er is een PowerShell-script beschikbaar waarmee de procedures die in dit onderwerp worden beschreven, worden geautomatiseerd. Met name kunt u met het script services weergeven en uitschakelen in uw Microsoft 365-organisatie, waaronder Sway. Zie [toegang tot Sway met PowerShell uitschakelen](disable-access-to-sway-with-microsoft-365-powershell.md)voor meer informatie.
>
    
Voer de volgende opdracht uit om samenvattingsinformatie weer te geven over uw huidige licentie plannen en de beschikbare licenties voor elk abonnement:
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>De PowerShell-core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met **MSOL** in de naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

De resultaten bevatten de volgende informatie:
  
- **AccountSkuId:** Geef de beschikbare licentie plannen voor uw organisatie weer met behulp van de syntaxis `<CompanyName>:<LicensingPlan>` .  _\<CompanyName>_ is de waarde die u hebt opgegeven bij het registreren in Microsoft 365 en is uniek voor uw organisatie. De _\<LicensingPlan>_ waarde is hetzelfde voor iedereen. Met de waarde is de bedrijfsnaam bijvoorbeeld de naam van het `litwareinc:ENTERPRISEPACK`  `litwareinc` licentie plan en de naam van het licentie plan  `ENTERPRISEPACK` , de naam van het systeem voor Office 365 Enterprise E3.
    
- **ActiveUnits:** Het aantal licenties dat u hebt aangeschaft voor een specifiek licentie plan.
    
- **WarningUnits:** Het aantal licenties in een licentie plan dat u niet hebt verlengd, en dat na de respijtperiode van 30 dagen verloopt.
    
- **ConsumedUnits:** Het aantal licenties dat u hebt toegewezen aan gebruikers uit een specifiek licentie plan.
    
Voer de volgende opdracht uit als u meer informatie wilt bekijken over de Microsoft 365-services die beschikbaar zijn in al uw licentie abonnementen:
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

In de volgende tabel ziet u de Microsoft 365-serviceplannen en de beschrijvende namen voor de meest gebruikte services. Het kan zijn dat uw lijst met Serviceabonnementen verschillend is. 
  
|**Service plan**|**Beschrijving**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Beheer van Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Microsoft 365-apps voor Enterprise *(eerder Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype voor Bedrijven Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online Abonnement 2  <br/> |
   
Voor een volledige lijst met licentie plannen (ook wel productnamen genoemd), de opgenomen serviceplannen en de bijbehorende beschrijvende namen, raadpleegt u [productnamen en serviceplan-id's voor licenties](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

Als u informatie wilt bekijken over de Microsoft 365-services die beschikbaar zijn in een specifiek licentie plan, gebruikt u de volgende syntaxis.
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

In dit voorbeeld worden de services weergegeven die beschikbaar zijn in het licentie plan abonnement litwareinc: Enterprise Pack (Office 365 Enterprise E3).
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, licenties en groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
