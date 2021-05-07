---
title: Behoudvergrendeling gebruiken om wijzigingen in bewaarbeleid en bewaarlabelbeleid te beperken
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Behoudvergrendeling gebruiken met bewaarbeleid en bewaarlabelbeleid om te voldoen aan wettelijke vereisten en te beveiliging tegen malafide beheerders.
ms.openlocfilehash: 72f667b970b4257a3a540fb74a121c620892b56d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162079"
---
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a>Behoudvergrendeling gebruiken om wijzigingen in bewaarbeleid en bewaarlabelbeleid te beperken

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Met behoudvergrendeling wordt een bewaarbeleid of bewaarlabelbeleid vergrendeld, zodat niemand—ook een globale beheerder, het beleid kan uitschakelen, het beleid kan verwijderen of minder beperkend kan maken. Deze configuratie kan nodig zijn voor wettelijke vereisten en kan helpen beveiliging tegen malafide beheerders.

Wanneer een bewaarbeleid is vergrendeld:

- Niemand kan het beleid uitschakelen of verwijderen
- Locaties kunnen worden toegevoegd, maar niet worden verwijderd
- U kunt de retentieperiode verlengen, maar niet verlagen

Wanneer een retentielabelbeleid is vergrendeld:

- Niemand kan het beleid uitschakelen of verwijderen
- Locaties kunnen worden toegevoegd, maar niet worden verwijderd
- Labels kunnen worden toegevoegd, maar niet worden verwijderd

Samengevat: een vergrendeld beleid kan worden verhoogd of uitgebreid, maar kan niet worden beperkt of uitgeschakeld.

> [!IMPORTANT]
> Voordat u een bewaarbeleid of bewaarlabelbeleid vergrendelt, is het van essentieel belang dat u de gevolgen begrijpt en controleert of dit vereist is voor uw organisatie. Het kan bijvoorbeeld nodig zijn om te voldoen aan wettelijke vereisten. Beheerders kunnen dit beleid niet uitschakelen of verwijderen nadat de behoudvergrendeling is toegepast.

Behoudvergrendeling configureren nadat u een [bewaarbeleid](create-retention-policies.md)hebt gemaakt of een bewaarlabelbeleid dat u [publiceert](create-apply-retention-labels.md) of [automatisch toepast](apply-retention-labels-automatically.md). 

> [!NOTE]
> Als u een labelbeleid vergrendelt, voorkomt u niet dat een beheerder de retentieperiode verkort van een label dat is opgenomen in het vergrendelde beleid. Aan deze vereiste, met andere beperkingen, kan worden voldaan wanneer u een label configureert om items te markeren als een [regelgevend record](records-management.md#records).

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a>Een bewaarbeleid of bewaarlabelbeleid vergrendelen

U moet PowerShell gebruiken als u Behoudvergrendeling nodig hebt. Omdat beheerders een beleid voor bewaren niet kunnen uitschakelen of verwijderen nadat deze vergrendeling is toegepast, is het inschakelen van deze functie niet beschikbaar in de gebruikersinterface om te beveiligen tegen onbedoelde configuratie.

Alle beleid voor retentie en met elke configuratie bieden ondersteuning voor Behoudvergrendeling.

1. [Verbinding maken met Beveiligings- en compliancecentrum van Powershell](/powershell/exchange/connect-to-scc-powershell).

2. Zoek de naam van het beleid dat u wilt vergrendelen door [Get-RetentionCompliancePolicy](/powershell/module/exchange/get-retentioncompliancepolicy) uit te voeren. Bijvoorbeeld:
    
   ![Lijst met bewaarbeleid in PowerShell](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. Als u een Behoudvergrendeling op het beleid wilt instellen, moet u de [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) cmdlet uitvoeren met de naam van het beleid en de parameter *RestrictiveRetention* ingesteld op waar:
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    Bijvoorbeeld:
    
    ![RestrictiveRetention parameter in PowerShell](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     Lees en bevestig, wanneer u daarom wordt gevraagd, de beperkingen die gelden bij deze configuratie door **Y** in te voeren:
    
   ![Vragen om te bevestigen dat u een bewaarbeleid wilt vergrendelen in PowerShell](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

Er is nu een Behoudvergrendeling op het beleid geplaatst. Voer ter bevestiging de `Get-RetentionCompliancePolicy` opnieuw uit, maar geef de beleidsnaam op en geef de beleidsparameters weer:

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

**RestrictiveRetention** moet nu ingesteld zijn op **Waar**. Bijvoorbeeld:

![Vergrendeld beleid met alle parameters die worden weergegeven in PowerShell](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a>Zie ook

[Bronnen om je te helpen te voldoen aan wettelijke vereisten voor informatiebeheer en recordbeheer](retention-regulatory-requirements.md)