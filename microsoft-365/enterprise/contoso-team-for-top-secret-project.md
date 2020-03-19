---
title: Team voor een topgeheim project van de Contoso Corporation
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
description: 'Samenvatting: Hoe Contoso een team gebruikte voor sterk gereguleerde gegevens voor een topgeheim project om een nieuwe suite van producten en diensten te ontwikkelen.'
ms.openlocfilehash: 58d381751db3e94f35a0c1b8f7a14c191918e754
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805717"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a>Team voor een topgeheim project van de Contoso Corporation

Na een executive offsite, contoso's CEO bestelde de ontwikkeling van een nieuwe suite van producten en diensten die contoso's winst zou kunnen verdubbelen in de komende vijf jaar. Het topgeheime project voor de ontwikkeling van het business, engineering en marktplan kreeg de naam **Project 2X** en belangrijke medewerkers in het hele bedrijf werden aangeworven. 

De tijdlijnen voor onderzoek en ontwikkeling waren krap, wat betekende dat de samenwerking efficiënt moest zijn en veilige vergaderingen, lopende gesprekken en bestandsopslag moest bieden.

De resulterende deliverables voor Project 2X waren bedrijfsplannen, product- en technische specificaties en marketingmateriaal en -schema's in de vorm van Word-, Excel- en PowerPoint-bestanden. 

Vanwege hun gevoelige aard, de toegang tot deze bestanden waren:

- Beperkt tot Project 2X-teamleden.
- Beschermd met een DLP-beleid (Data Loss Prevention) om te voorkomen dat Project 2X-teamleden ze buiten het team delen.
- Versleuteld en beveiligd met machtigingen om alleen toegang toe te staan aan Project 2X-teamleden, zelfs als de bestanden buiten Contoso zijn gedistribueerd.

Contoso IT-medewerkers gebruikten een [team voor sterk gereguleerde gegevens](secure-teams-highly-regulated-data-scenario.md) voor Project 2X en deze stappen.

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a>Stap 1: Een privéteam maken en de onderliggende SharePoint-site vergrendeld

Om de toegang tot de onderliggende SharePoint-site voor het team te beschermen, hebben Contoso IT-beheerders het [aanbevolen SharePoint-toegangsbeleid](sharepoint-file-access-policies.md)geconfigureerd.

Vervolgens heeft een Contoso IT-beheerder een nieuw privéteam gemaakt met de naam Project 2X en de gebruikersaccounts van Project 2X-medewerkers toegevoegd als leden.

Vervolgens hebben ze aanvullende machtigingsinstellingen voor de site geconfigureerd om te voorkomen dat Project 2X toegang tot de site kan delen en om te voorkomen dat andere toegang tot de site zouden aanvragen.

Zie [SharePoint-instellingen voor een sterk gereguleerd team voor](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams)de configuratiegegevens.

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a>Stap 2: Een DLP-beleid en de onderliggende site voor een bewaarlabel geconfigureerd 

Ten eerste hebben Contoso-beheerders het bestaande **zeer vertrouwelijke** Office 365-bewaarlabel toegepast op de sectie **Documenten** van de onderliggende SharePoint-site van het Project 2X-team.

Vervolgens hebben ze een nieuw Office 365 DLP-beleid gemaakt met de naam **Project 2X,** dat:

- Gebruikt het bewaarlabel Zeer vertrouwelijk Office 365.
- Hiermee blokkeert u gebruikers wanneer ze een bestand proberen te delen in het Project 2X-team buiten Contoso.

Zie Bestanden beveiligen [in teams met bewaarlabels en DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp)voor de configuratiegegevens.

## <a name="step-3-created-an-office-365-sensitivity-label-for-the-project-2x-team"></a>Stap 3: Een Office 365-gevoeligheidslabel gemaakt voor het Project 2X-team

Contoso-beheerders hebben een nieuw Office 365-gevoeligheidslabel gemaakt met de naam **Project 2X,** dat:

- Vereist encryptie.
- Hiermee u machtigingen voor co-auteur toestaan voor de groep Project 2X Office 365.

Hier is de resulterende configuratie van het Project 2X-team.

![De resulterende configuratie van het Project 2X-team](../media/contoso-team-for-highly-confidential-assets/final-config.png)
 
Bestanden in de sectie Documenten van de onderliggende SharePoint-site project 2X zijn beveiligd door:

- De sitemachtigingen, die alleen toegang geven tot leden van de Groep Project 2X Office 365.
- Het zeer vertrouwelijke bewaarlabel, dat automatisch wordt toegewezen aan nieuwe bestanden.
- Een DLP-beleid dat het label en de instellingen voor zeer vertrouwelijk bewaaren gebruikt die blokkeren dat het bestand wordt gedeeld met externe gebruikers.
- Het project 2x-gevoeligheidslabel, met versleuteling en machtigingen die met het bestand worden meegenomen als het van de site wordt verplaatst of gekopieerd.

Hier is een voorbeeld van een bestand dat is opgeslagen op de onderliggende Project 2X-site met het hooggereguleerde retentielabel en het toegewezen Label voor gevoeligheid van Project 2X.

![Een voorbeeld van een bestand dat is opgeslagen op de onderliggende Project 2X-site](../media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a>Stap 4: Getraind Project 2X teamleden

Contoso security medewerkers trainde de Project 2X teamleden in een verplichte cursus die hen door:

- Toegang krijgen tot het nieuwe Project 2X-team, vergaderingen en chats gebruiken en samenwerken aan teambestanden.
- Nieuwe bestanden maken in het team en nieuwe bestanden uploaden die lokaal zijn gemaakt.
- Een demonstratie van hoe het DLP-beleid voorkomt dat bestanden extern worden gedeeld.
- Bestanden labelen met het label Project 2X sensitivity.
- Een demonstratie van hoe het Project 2X-label een bestand beschermt, zelfs wanneer het het team verlaat.

Het eindresultaat was een veilige omgeving waarin Project 2X-teamleden samenwerkten in een beveiligde omgeving voor chats, vergaderingen en bestanden.

In een paar gevallen hebben Project 2X-teamleden bestanden gedownload die door het Project 2X-label zijn beveiligd, naar een lokaal station voor offline werk. Echter, na te zijn gevraagd voor referenties bij het openen van hen, realiseerden ze hun fout en verwijderde ze.

Vanwege de samenwerkingsomgeving van Teams en de beveiligingsfuncties van Microsoft 365 werden de details van Project 2X geheim gehouden voor de duur van het project. Contoso kondigde haar plannen aan en is bezig met de uitrol van de nieuwe producten en diensten tot grote vreugde van haar klanten en investeerders en de ergernis van haar concurrenten.

## <a name="next-step"></a>Volgende stap

[Implementeren](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in uw organisatie.

## <a name="see-also"></a>Zie ook

[Microsoft 365-productiviteitsbibliotheek](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)
