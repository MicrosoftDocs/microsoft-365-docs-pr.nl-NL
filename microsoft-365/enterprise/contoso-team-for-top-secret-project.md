---
title: Team voor een zeer geheim project van Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Samenvatting: Hoe Contoso een team gebruikte voor sterk gereguleerde gegevens voor een topgeheim project om een nieuwe reeks producten en diensten te ontwikkelen.'
ms.openlocfilehash: 310ef33d4add7d71616aee8808515ca90536d8c1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636496"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a>Team voor een zeer geheim project van Contoso Corporation

Na een executive offsite, Contoso's CEO beval de ontwikkeling van een nieuwe suite van producten en diensten die de winst van Contoso zou kunnen verdubbelen in de komende vijf jaar. Het topgeheime project voor de ontwikkeling van het bedrijfs-, engineering- en marktplan kreeg de naam **Project 2X** en belangrijke medewerkers in het hele bedrijf werden aangeworven. 

De tijdlijnen voor onderzoek en ontwikkeling waren strak, wat betekende dat samenwerking efficiënt moest zijn en moest zorgen voor veilige vergaderingen, lopende gesprekken en bestandsopslag.

De resulterende deliverables voor Project 2X waren bedrijfsplannen, product- en engineeringspecificaties en marketingmaterialen en -schema's in de vorm van Word-, Excel- en PowerPoint-bestanden. 

Vanwege hun gevoelige aard, de toegang tot deze bestanden waren:

- Beperkt tot Project 2X-teamleden.
- Beschermd met een DLP-beleid (Data Loss Prevention) om te voorkomen dat Project 2X-teamleden ze buiten het team delen.
- Versleuteld en beveiligd met machtigingen om alleen toegang te verlenen aan Project 2X-teamleden, zelfs als de bestanden buiten Contoso zijn gedistribueerd.

Het [IT-personeel](secure-teams-highly-regulated-data-scenario.md) van Contoso gebruikte een team voor sterk gereguleerde gegevens voor Project 2X en deze stappen.

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a>Stap 1: Een privéteam maken en de onderliggende SharePoint-site vergrendeld

Om de toegang tot de onderliggende SharePoint-site voor het team te beschermen, hebben De IT-beheerders van Contoso het [aanbevolen SharePoint-toegangsbeleid](sharepoint-file-access-policies.md)geconfigureerd.

Vervolgens heeft een It-beheerder van Contoso een nieuw privéteam met de naam Project 2X gemaakt en de gebruikersaccounts van Project 2X-medewerkers als leden toegevoegd.

Vervolgens hebben ze extra machtigingsinstellingen voor de site geconfigureerd om te voorkomen dat Project 2X toegang tot de site deelt en om te voorkomen dat andere toegang tot de site aanvragen.

Zie [SharePoint-instellingen voor een sterk gereguleerd team voor](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams)de configuratiegegevens.

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a>Stap 2: Een DLP-beleid en de onderliggende site configureren voor een bewaarlabel 

Ten eerste pasten Contoso-beheerders het bestaande **label voor zeer vertrouwelijke** bewaarwaarde toe op de sectie **Documenten** van de onderliggende SharePoint-site van het Project 2X-team.

Vervolgens hebben ze een nieuw DLP-beleid gemaakt met de naam **Project 2X** dat:

- Gebruikt het highly confidential retention label.
- Blokkeert gebruikers wanneer ze proberen een bestand te delen in het Project 2X-team buiten Contoso.

Zie Bestanden beveiligen [in teams met bewaarlabels en DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp)voor de configuratiegegevens.

## <a name="step-3-created-a-sensitivity-label-for-the-project-2x-team"></a>Stap 3: Een gevoeligheidslabel maken voor het Project 2X-team

Contoso-beheerders hebben een nieuw gevoeligheidslabel gemaakt met de naam **Project 2X** dat:

- Vereist versleuteling.
- Hiermee kunnen machtigingen voor co-auteur worden toegestaan voor de Project 2X Microsoft 365-groep.

Hier is de resulterende configuratie van het Project 2X-team.

![De resulterende configuratie van het Project 2X-team](../media/contoso-team-for-highly-confidential-assets/final-config.png)
 
Bestanden in de sectie Documenten van de onderliggende Project 2X SharePoint-site zijn beveiligd door:

- De sitemachtigingen, die alleen toegang geven tot leden van de Project 2X Microsoft 365-groep.
- Het label Highly Confidential retention, dat automatisch wordt toegewezen aan nieuwe bestanden.
- Een DLP-beleid dat het label Highly Confidential retention en instellingen gebruikt die voorkomen dat het bestand wordt gedeeld met externe gebruikers.
- Het label Voor de gevoeligheid van Project 2X, met versleuteling en machtigingen die met het bestand reizen als het wordt verplaatst of gekopieerd van de site.

Hier is een voorbeeld van een bestand dat is opgeslagen in de onderliggende Project 2X-site met het label Sterk gereguleerd bewaren en het label Project 2X-gevoeligheid toegewezen.

![Een voorbeeld van een bestand dat is opgeslagen in de onderliggende Project 2X-site](../media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a>Stap 4: Getrainde Project 2X-teamleden

Contoso security medewerkers trainden de Project 2X teamleden in een verplichte cursus die hen door:

- Hoe u toegang krijgt tot het nieuwe Project 2X-team, vergaderingen en chats gebruiken en samenwerken aan teambestanden.
- Nieuwe bestanden maken in het team en nieuwe bestanden uploaden die lokaal zijn gemaakt.
- Een demonstratie van hoe het DLP-beleid blokkeert dat bestanden extern worden gedeeld.
- Bestanden labelen met het label Project 2X-gevoeligheid.
- Een demonstratie van hoe het Project 2X-label een bestand beschermt, zelfs wanneer het team verlaat.

Het eindresultaat was een veilige omgeving waarin Project 2X-teamleden samenwerkten in een veilige omgeving voor chats, vergaderingen en bestanden.

In een paar gevallen hebben project 2X-teamleden bestanden die door het Project 2X-label zijn beveiligd, gedownload naar een lokale schijf voor offline werk. Echter, na te zijn gevraagd om referenties bij het openen van hen, realiseerden ze hun fout en verwijderde ze.

Vanwege de samenwerkingsomgeving van Teams en de beveiligingsfuncties van Microsoft 365 werden de details van Project 2X geheim gehouden voor de duur van het project. Contoso kondigde haar plannen aan en is bezig met de uitrol van de nieuwe producten en diensten tot grote vreugde van haar klanten en investeerders en de ergernis van haar concurrenten.

## <a name="next-step"></a>Volgende stap

[Implementeren](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in uw organisatie.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)
