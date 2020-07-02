---
title: 'Stap 4: Windows-gegevensbescherming configureren'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Informatie en implementatie van Windows-gegevensbescherming in Microsoft 365.
ms.openlocfilehash: c7b76ef28d41810d6e9e45e98adb7a94cf8ae2f4
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005720"
---
# <a name="step-4-configure-windows-information-protection"></a>Stap 4: Windows-gegevensbescherming configureren

*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*

![Fase 6: Gegevensbescherming](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Nu er steeds meer persoonlijke apparaten voor werk worden gebruikt, is er een verhoogd risico dat apps en apparaten vertrouwelijke bedrijfsgegevens lekken. Bijvoorbeeld wanneer een werknemer per ongeluk een afbeelding van een marketingplan voor een toekomstig product naar een site voor sociale media stuurt of een bestand met zeer vertrouwelijke informatie op in hun openbare cloudopslag opslaat. 

Met Windows-gegevensbescherming kunt u bescherming bieden tegen dit soort gegevenslekken op Windows 10-apparaten. Zie voor meer informatie [Uw ondernemingsgegevens beveiligen met Windows-gegevensbescherming](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).

In Microsoft 365 Enterprise is Windows-gegevensbescherming een combinatie van Windows 10 Enterprise en Microsoft Intune, dat inbegrepen is in uw abonnement. 

U kunt Windows-gegevensbescherming als volgt in uw organisatie implementeren met Microsoft 365 Enterprise:

1. Registreer uw Windows-apparaten bij Intune. U had dit moeten hebben gedaan in [Fase 5: beheer voor mobiele apparaten](mobility-infrastructure.md).

2. Maak een [Intune-beleid voor Windows-gegevensbescherming](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).

   -    Controleer of u de lijst met beveiligde apps hebt ingevuld.
  
   - Kies uw Windows-gegevensbeveiligingsniveau.

U kunt Windows-gegevensbescherming ook gebruiken met[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-configmgr). 

Zie [Aanbevolen procedures voor Windows-gegevensbescherming]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) voor meer informatie.

Zie de [afsluitcriteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) voor deze stap als tussentijds controlepunt.

## <a name="next-step"></a>Volgende stap

|||
|:-------|:-----|
|![Stap 5](../media/stepnumbers/Step5.png)|[Preventie van gegevensverlies configureren](infoprotect-data-loss-prevention.md)|


