---
title: 'Fase 4: Microsoft 365-apps voor ondernemingen'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: De stappen om de infrastructuur voor Microsoft 365-apps voor ondernemingen voor Microsoft 365 Enterprise te implementeren.
ms.openlocfilehash: 5143ef8872a7ebd119e77c6148288828a39e20d9
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011945"
---
# <a name="phase-4-microsoft-365-apps-for-enterprise"></a>Fase 4: Microsoft 365-apps voor ondernemingen

![Fase 4: Microsoft 365-apps voor ondernemingen](../media/deploy-foundation-infrastructure/O365proplus_icon.png)

*Dit geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise en Microsoft 365 Education*

Microsoft 365 Enterprise omvat Microsoft 365-apps voor ondernemingen, de abonnementsversie van Office. Net als Office 2019 biedt Microsoft 365-apps voor ondernemingen alle Office-toepassingen en worden deze toepassingen rechtstreeks op uw clientapparaten geïnstalleerd. In tegenstelling tot Office 2019 wordt Microsoft 365-apps voor ondernemingen regelmatig bijgewerkt met nieuwe functies en heeft het een licentiemodel voor gebruikers waarmee personen Office kunnen installeren op meerdere apparaten. Zie [Over Microsoft 365-apps voor ondernemingen](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps) voor meer informatie.

In deze fase implementeert u Microsoft 365-apps voor ondernemingen op clientapparaten als onderdeel van Microsoft 365 Enterprise. We raden u aan om naast deze richtlijnen ook gebruik te maken van [Microsoft FastTrack](https://fasttrack.microsoft.com/office) voor hulp bij de implementatie. 

Als u Microsoft 365-apps voor ondernemingen al hebt geïmplementeerd, bekijkt u het [afsluitcriterium](office365proplus-exit-criteria.md) voor deze fase om er zeker van te zijn dat deze voldoet aan de vereiste voorwaarden voor Microsoft 365 Enterprise.

>[!Note]
>Als u zowel Windows 10 Enterprise als Microsoft 365-apps voor ondernemingen samen wilt implementeren, raadpleegt u het [Desktop Deployment Center](desktop-deployment-center-home.md).
>

## <a name="step-1-assess-your-environment"></a>Stap 1: Uw omgeving evalueren

Volg de richtlijnen in [Uw omgeving en vereisten evalueren voor de implementatie van Microsoft 365-apps](https://docs.microsoft.com/DeployOffice/assess-microsoft-365-apps) voordat u Microsoft 365-apps voor ondernemingen implementeert. Deze evaluatie omvat de systeemvereisten, details van uw clientapparaten (zoals architecturen en vereiste talen), licentievereisten, netwerkfunctionaliteit en toepassingscompatibiliteit. Door de beoordeling te voltooien, kunt u belangrijke beslissingen nemen als onderdeel van de planning van uw implementatie.

## <a name="step-2-plan-your-deployment"></a>Stap 2: Uw implementatie plannen

Volg na het beoordelen van uw omgeving de richtlijnen in [Uw implementatie van Microsoft 365-apps plannen](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps) voor het maken van een implementatieplan. Dit plan omvat de volgende beslissingen: 

- Het implementeren van Office, met inbegrip van het programma dat u gaat gebruiken (zoals Microsoft Endpoint Configuration Manager of het Office Deployment Tool) en waar u Office vanuit kunt installeren
- Updates voor Office beheren
- Welke updatekanalen te gebruiken (updatekanalen voor Office bepalen hoe vaak uw gebruikers functie-updates ontvangen voor hun Office-toepassingen)
- De Office-installatiepakketten en -implementatiegroepen die u wilt gebruiken, met inbegrip van welke Office-toepassingen en -talen geïnstalleerd moeten worden voor welke gebruikers

Het [planningsartikel](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps) bevat aanbevolen procedures voor al deze opties, waaronder het beheren van de implementatie, het beheren van uw updates, het definiëren van installatiepakketten en het maken van implementatiegroepen. 

## <a name="step-3-deploy"></a>Stap 3: Implementeren

Kies op basis van uw implementatieplan hoe u wilt implementeren:

- **[Microsoft 365-apps implementeren met Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-configuration-manager):** Beheer uw implementatie met Configuration Manager en download en implementeer Office vanaf distributiepunten op uw netwerk

- **[Microsoft 365-apps implementeren vanuit de cloud](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-cloud):** Beheer uw implementatie met ODT en installeer Office rechtstreeks op clientapparaten vanuit het Office CDN
 
- **[Microsoft 365-apps voor ondernemingen zelf installeren vanuit de Office-portal](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Beheer uw implementatie vanuit de Office-portal en laat uw gebruikers Office rechtstreeks vanuit de portal installeren op hun clientapparaten

Veel organisaties gebruiken een combinatie van deze opties voor verschillende gebruikers. Een organisatie kan bijvoorbeeld voor de meeste gebruikers Configuration Manager gebruiken om Office te implementeren, maar een kleine groep werknemers die niet regelmatig met het interne netwerk verbonden zijn zelf laten installeren. 

Als uw organisatie Configuration Manager gebruikt, raden we u aan een upgrade uit te voeren naar de Huidige vertakking en een update uit te voeren naar de huidige versie. Zie [Welke vertakking van Configuration Manager moet ik gebruiken?](https://docs.microsoft.com/mem/configmgr/core/understand/which-branch-should-i-use) voor meer informatie

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Hoe Microsoft omgaat met Microsoft 365 Enterprise

Lees hoe de experts van Microsoft [updates voor Microsoft 365-apps voor ondernemingen implementeren en beheren](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Hoe Contoso Microsoft 365 Enterprise gebruikt

Bekijk hoe de Contoso Corporation, een fictieve maar representatieve multinational, [Microsoft 365-apps voor ondernemingen heeft geïmplementeerd](contoso-o365pp.md).

![De Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Volgende stap

[Afsluitcriteria voor de infrastructuur voor Microsoft 365-apps voor ondernemingen](office365proplus-exit-criteria.md)
