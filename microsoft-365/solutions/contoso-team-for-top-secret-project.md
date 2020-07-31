---
title: Geïsoleerd team voor een topgeheim project van de Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: 'Samenvatting: Hoe Contoso een team met beveiligingsisolatie gebruikte voor een topgeheim project om een nieuwe reeks producten en diensten te ontwikkelen.'
ms.openlocfilehash: f7b38a7ef43cdb50b46f3e37f855f490dc32cfdf
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/29/2020
ms.locfileid: "46521623"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Geïsoleerd team voor een topgeheim project van de Contoso Corporation

Na een executive offsite, Contoso's CEO bestelde de ontwikkeling van een nieuwe suite van producten en diensten die contoso's winst zou kunnen verdubbelen in de komende vijf jaar. Het topgeheime project voor de ontwikkeling van het bedrijfs-, engineering- en marktplan kreeg de naam **Project 2X** en belangrijke medewerkers in het hele bedrijf werden aangeworven. 

De tijdslijnen voor onderzoek en ontwikkeling waren strak, wat betekende dat samenwerking efficiënt moest zijn en moest zorgen voor veilige vergaderingen, lopende gesprekken en bestandsopslag.

De resulterende deliverables voor Project 2X waren bedrijfsplannen, product- en technische specificaties en marketingmaterialen en -schema's in de vorm van Word-, Excel- en PowerPoint-bestanden. 

Vanwege hun gevoelige aard, toegang tot deze bestanden waren:

- Beperkt tot Project 2X-teamleden.
- Versleuteld en beveiligd met machtigingen om alleen toegang te verlenen tot Project 2X-teamleden, zelfs als de bestanden buiten hun beveiligde mappen zijn gedistribueerd.

Contoso IT-medewerkers gebruikten een [team met beveiligingsisolatie](secure-teams-security-isolation.md) voor Project 2X en deze stappen.

## <a name="step-1-created-a-private-team"></a>Stap 1: Een privéteam gemaakt

Om eerst de toegang tot de onderliggende SharePoint-site voor het team te beschermen, hebben de IT-beheerders van Contoso het [aanbevolen SharePoint-toegangsbeleid](../enterprise/sharepoint-file-access-policies.md)geconfigureerd.

Vervolgens heeft een It-beheerder van Contoso een nieuw privéteam met de naam Project 2X gemaakt en de gebruikersaccounts van project 2x-medewerkers als leden toegevoegd.

Zie [Een privéteam maken](secure-teams-security-isolation.md#create-a-private-team)voor de configuratiedetails.

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>Stap 2: Een gevoeligheidslabel gemaakt voor het Project 2X-team

Contoso-beheerders hebben een nieuw gevoeligheidslabel met de naam **Project 2X** gemaakt dat:

- Vereist versleuteling.
- Hiermee kunnen machtigingen voor co-auteur worden verleend voor de Project 2X Microsoft 365-groep.

Bestanden in de sectie **Documenten** van de onderliggende SharePoint-site van Project 2X zijn beveiligd door:

- De sitemachtigingen, die alleen toegang bieden aan leden van de Project 2X Microsoft 365-groep.
- Het project 2X-gevoeligheidslabel, met versleuteling en machtigingen die met het bestand worden uitgevoerd als het wordt verplaatst of gekopieerd van de site.

Zie [Een gevoeligheidslabel maken](secure-teams-security-isolation.md#create-a-sensitivity-label)voor de configuratiedetails.

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>Stap 3: De onderliggende SharePoint-site configureren

Om eerst de toegang tot de onderliggende SharePoint-site voor het team te beschermen, hebben de IT-beheerders van Contoso het [aanbevolen SharePoint-toegangsbeleid](../enterprise/sharepoint-file-access-policies.md)geconfigureerd.

Vervolgens hebben ze extra machtigingsinstellingen voor de site geconfigureerd om te voorkomen dat Project 2X toegang tot de site deelt. Zie [SharePoint-instellingen voor een team met beveiligingsisolatie voor](secure-teams-security-isolation.md#sharepoint-settings)de configuratiedetails.

Hier is de resulterende configuratie van het Project 2X team.

![De resulterende configuratie van het Project 2X-team](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>Stap 4: Getrainde Project 2X-teamleden

Contoso security personeel opgeleid het Project 2X teamleden in een verplichte cursus die hen stapte door:

- Toegang tot het nieuwe Project 2X-team, vergaderingen en chats gebruiken en samenwerken aan teambestanden.
- Nieuwe bestanden in het team maken en nieuwe bestanden lokaal uploaden.
- Een demonstratie van hoe het DLP-beleid voorkomt dat bestanden extern worden gedeeld.
- Bestanden labelen met het Project 2X-gevoeligheidslabel.
- Een demonstratie van hoe het Project 2X-label een bestand beschermt, zelfs wanneer het team verlaat.

Het eindresultaat was een veilige omgeving waarin Project 2X-teamleden samenwerkten in een veilige omgeving voor chats, vergaderingen en bestanden.

Hier vindt u een voorbeeld van een bestand dat is opgeslagen in de onderliggende Project 2X-site met het label Project 2X-gevoeligheid toegewezen.

![Een voorbeeld van een bestand dat is opgeslagen in de onderliggende Project 2X-site](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

In een paar gevallen hebben project 2x-teamleden bestanden gedownload die door het Project 2X-label zijn beveiligd, naar een lokaal station voor offline werk. Echter, na te zijn gevraagd voor referenties bij het openen van hen, realiseerden ze hun fout en verwijderde ze.

Vanwege de samenwerkingsomgeving van Teams en de beveiligingsfuncties van Microsoft 365 werden de details van Project 2X geheim gehouden voor de duur van het project. Contoso kondigde haar plannen aan en is bezig met de uitrol van de nieuwe producten en diensten tot grote vreugde van haar klanten en investeerders en de ergernis van haar concurrenten.

## <a name="next-step"></a>Volgende stap

[Implementeer een team met beveiligingsisolatie](secure-teams-security-isolation.md) in uw organisatie.

