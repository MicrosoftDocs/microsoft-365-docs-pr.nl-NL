---
title: Microsoft 365 voor bedrijfsworkloads
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Werk de gebruikers in uw organisatie in voor de productiviteitsworkloads van Microsoft 365 voor ondernemingen.
ms.openlocfilehash: 0e1658655c4b97a7e571d1ac09c4b2edcc6c82ce
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268274"
---
# <a name="microsoft-365-for-enterprise-workloads"></a>Microsoft 365 voor bedrijfsworkloads

Als u wilt profiteren van de voordelen van de creativiteit en het teamwork van Microsoft 365 voor ondernemingen, kunt u de volgende workloads op uw basisinfrastructuur implementeren:

- [Microsoft Teams](teams-workload.md)
- [Exchange Online](exchangeonline-workload.md)
- [SharePoint en OneDrive](sharepoint-online-onedrive-workload.md)

Zie het artikel over [migratie](migration-microsoft-365-enterprise-workload.md) voor een algemene routekaart voor het migreren van uw hele organisatie naar Microsoft 365 voor ondernemingen, inclusief Microsoft Office-clientproducten, on-premises Office Server-producten en Microsoft Windows-apparaten.

Hier volgen de workloads in de algemene implementatiehandleiding voor Microsoft 365 voor ondernemingen:

![Workloads in de algemene implementatiehandleiding voor Microsoft 365 voor ondernemingen](../media/deploy-workloads/m365-deploy-content-arch-workloads.png)

## <a name="foundation-infrastructure-prerequisites"></a>Vereisten voor de basisinfrastructuur

*Idealiter* dient u workloads te implementeren nadat u alle fasen van de [basisinfrastructuur](deploy-foundation-infrastructure.md) hebt geconfigureerd. Dit zorgt ervoor dat alle onderliggende basislagen aanwezig zijn, zodat u uw gebruikers en hun apparaten integratie, beveiliging en de beste ervaring kunt bieden.

| Fase | Resultaat |
|:-------|:-----|
| Netwerk | Uw netwerk wordt bijgewerkt voor optimale prestaties met Microsoft 365-cloudservices. |
| Identiteit | Identiteit wordt met sterke verificatie voor gebruikersaccounts en bescherming voor beheerdersaccounts gesynchroniseerd en beveiligd. |
| Windows 10 Enterprise | Voor computers met Windows 7 of Windows 8.1 kunt u een upgrade uitvoeren naar Windows 10 Enterprise en op nieuwe apparaten wordt Windows 10 Enterprise geïnstalleerd. |
| Microsoft 365-apps voor ondernemingen | Bestaande gebruikers van Microsoft Office kunnen een upgrade uitvoeren naar Microsoft 365-apps voor ondernemingen. |
| Mobile Device Management | Uw apparaten kunnen worden geregistreerd en beheerd. |
| Gegevensbeveiliging | Microsoft 365-functies voor informatiebescherming worden geconfigureerd en uw gevoeligheidslabels of Azure Information Protection-labels zijn gereed om documenten en e-mail te beschermen. |

Vergeet niet dat dit het ideale geval is en dat het plannen, configureren en testen veel tijd in beslag kan nemen, met name in grote organisaties met een bestaande infrastructuur en meerdere locaties. Het voltooien van alle fasen op alle locaties is niet nodig om sneller meer bedrijfswaarde uit Microsoft 365 voor ondernemingen te halen. 

Hier volgen enkele veelvoorkomende workloads die u onmiddellijk kunt implementeren: 

- Nadat de fase **Identiteit** van de basisinfrastructuur voor de gebruikers is geïmplementeerd, worden door veel organisaties ook de volgende workloads geïmplementeerd:
  - [Microsoft 365-apps voor ondernemingen](office365proplus-infrastructure.md) gecombineerd met [OneDrive](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise). Microsoft 365-apps voor ondernemingen biedt de beveiliging van moderne verificatie en de gebruikerservaring van de nieuwste Microsoft Office-client. De migratie van persoonlijke bestanden van gebruikers naar OneDrive vermindert de hoeveelheid infrastructuur en de noodzaak om lokale mappen en stations te ondersteunen.
  - [Exchange Online](exchangeonline-workload.md), zodat gebruikers e-mail in de cloud kunnen gebruiken.
- Als u sterk gereglementeerde digitale activa niet onmiddellijk in de cloud wilt opslaan, kunt u [Microsoft Teams](teams-workload.md) en [SharePoint](sharepoint-online-onedrive-workload.md) voor uw gebruikers implementeren voorafgaand aan de fase **Informatiebescherming**.

U moet zelf bepalen hoe u de configuratie van vereiste fasen van de basisinfrastructuur wilt implementeren om te voldoen aan de behoeften van uw bedrijf.

### <a name="best-practice"></a>Aanbevolen procedures

Het wordt ten zeerste aangeraden de fase **Identiteit** van de basisinfrastructuur te implementeren en uit te voeren voordat u uw gebruikers op workloads of scenario's gaat inwerken.

Met de fase **Identiteit** wordt gegarandeerd dat uw cloud-identiteit, of deze nu alleen voor de cloud is of dat deze wordt gesynchroniseerd met uw on-premises Active Directory Domain Services (AD DS), de gebruikers- en computeraccounts en -groepen bevat voor het beheren van verificatie en toegang. Voor alle gebruikers moet een sterke verificatie worden uitgevoerd met een sterke bescherming van beheerdersaccounts voordat de digitale activa van uw organisatie in de Microsoft 365-cloud worden geplaatst.

Hoewel de implementatie van de fase **Netwerken** fundamenteel en zeer belangrijk is voor de prestaties in het algemeen, kan deze fase worden uitgevoerd terwijl uw gebruikers voor workloads worden ingewerkt, waarbij niet mag worden vergeten dat de prestaties van de workloads en services van Microsoft 365 in de loop van de tijd beter worden. Dit geldt met name voor ondernemingen met meerdere locaties en een combinatie van edge-apparaten en internetverbindingen.
