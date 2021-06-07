---
title: Records declareren met behulp van retentielabels
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Records declareren met behulp van retentielabels
ms.openlocfilehash: fed988d2f880e4c0af1321cfb6ef4a873bd4e7ab
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730544"
---
# <a name="declare-records-by-using-retention-labels"></a>Records declareren met behulp van retentielabels

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Als u documenten en e-mailberichten wilt declareren als [records](records-management.md#records), gebruikt u [retentielabels](retention.md#retention-labels) die de inhoud markeren als een **record** of een **regelgevingsrecord**.

Zie [Beperkingen vergelijken voor welke acties zijn toegestaan of geblokkeerd](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked) als u niet zeker weet of u een record of een regelgevingsrecord moet gebruiken. Als u regelgevingsrecords wilt gebruiken, moet u eerst een PowerShell-opdracht uitvoeren, zoals beschreven in de volgende sectie.

Vervolgens kunt u deze labels publiceren in een beleid voor retentielabels, zodat gebruikers en beheerders deze kunnen toepassen op inhoud, of voor labels die items markeren als records (maar niet al regelgevingsrecords), deze labels automatisch toepassen op inhoud die u als record wilt declareren.

## <a name="how-to-display-the-option-to-mark-content-as-a-regulatory-record"></a>De optie voor het markeren van inhoud als regelgevingsrecord weergeven

>[!NOTE] 
> De volgende procedure is een controleerbare actie, waarbij **De optie regelgevend record voor bewaarlabels is ingeschakeld** wordt geregistreerd in de sectie [Activiteiten met bewaarbeleid en bewaarlabels](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities) van het auditlogboek.

Standaard wordt de optie voor bewaarlabels om inhoud te markeren als een regelgevingsrecord niet weergegeven in de wizard voor retentielabels. Als u deze optie wilt weergeven, moet u eerst een PowerShell-opdracht uitvoeren:

1. [Maak verbinding met het Office 365-beveiligings- en compliancecentrum PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

2. Voer de volgende cmdlet uit:
    
    ```powershell
    Set-RegulatoryComplianceUI -Enabled $true
    ````
    Er wordt niet gevraagd om te bevestigen en de instelling wordt onmiddellijk van kracht.

Als u van gedachten verandert over de weergave van deze optie in de wizard voor retentielabels, dan kunt u deze weer verbergen door dezelfde cmdlet met de waarde **false** uit te voeren: `Set-RegulatoryComplianceUI -Enabled $false` 

## <a name="configuring-retention-labels-to-declare-records"></a>Retentielabels configureren om records te declareren

Wanneer u een retentielabel maakt vanuit de **Record Management**-oplossing in het Microsoft 365-compliancecentrum, kunt u items markeren als record. Als u de PowerShell-opdracht heeft uitgevoerd in de vorige sectie, dan kunt u items ook markeren als regelgevingsrecord.

Bijvoorbeeld:

![Een retentielabel configureren om inhoud te markeren als een record of regelgeving](../media/recordversioning6.png)

Wanneer u dit retentielabel gebruikt, kunt u dit voortaan toepassen op documenten in SharePoint of OneDrive en e-mails in Exchange indien nodig. 

Voor volledige instructies:

- [Retentielabels maken en deze toepassen in apps](create-apply-retention-labels.md)

- [Een retentielabel automatisch toepassen op inhoud](apply-retention-labels-automatically.md) (wordt niet ondersteund voor regelgevingsrecords)


## <a name="applying-the-configured-retention-label-to-content"></a>Het geconfigureerde retentielabel toepassen op inhoud

Wanneer retentielabels die items markeren als een record of regelgevingsrecord, beschikbaar worden gemaakt zodat gebruikers deze kunnen toepassen in apps:

- Voor Exchange kan elke gebruiker met schrijftoegang tot het postvak deze labels toepassen. 
- Voor SharePoint en OneDrive kan elke gebruiker in de standaardgroep Leden (het machtigingsniveau Bijdragen) deze labels toepassen.

Voorbeeld van een document dat als record is gemarkeerd met een retentielabel:

![Detailvenster voor document met recordlabel](../media/recordversioning7.png)

## <a name="next-steps"></a>Volgende stappen

Zie [Veelvoorkomende scenario's voor recordbeheer](get-started-with-records-management.md#common-scenarios-for-records-management) voor een lijst met scenario's die worden ondersteund door recordbeheer.
