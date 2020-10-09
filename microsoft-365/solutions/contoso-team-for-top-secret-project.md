---
title: Geïsoleerd team voor een hoofd-geheim project van Contoso B.v.
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/14/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: 'Overzicht: hoe contoso een team gebruikte met behulp van beveiligings isolatie voor een hoofd-geheim project om een nieuwe suite met producten en services te ontwikkelen.'
ms.openlocfilehash: 16d10f5d6e5b5939172c02746c9324eb20b6987e
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399487"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Geïsoleerd team voor een hoofd-geheim project van Contoso B.v.

Na een uitvoerend manager heeft de directeur van Contoso de ontwikkeling van een nieuwe suite van producten en diensten besteld die in de komende vijf jaar de winstgevendste functies kon opleveren. Het belangrijkste geheim project voor het ontwikkelen van het bedrijf, de engineering en de markt van een markt met name **project** , IT-medewerkers en IT-medewerkers zijn gewerfd. 

De tijdlijnen voor onderzoek en ontwikkeling waren strak, wat bedoeld voor de samenwerking en het zorgen voor veilig vergaderen, lopende gesprekken en bestandsopslag.

De resultaten van project 2X waren bedrijfsplannen, specificaties van producten en technische specificaties, en marketingmaterialen en planningen in de vorm van Word-, Excel-en PowerPoint-bestanden. 

Vanwege hun gevoelige aard zijn de toegang tot deze bestanden:

- Beperkt tot project en teamleden en senior leiderschap.
- Versleuteld en beveiligd met machtigingen voor toegang tot project en de teamleden en senior leiderschap, zelfs als de bestanden buiten hun beveiligde mappen zijn gedistribueerd.

Contoso IT-personeel heeft een [team gebruikt met beveiligings isolatie](secure-teams-security-isolation.md) voor project 2 en deze stappen.

## <a name="step-1-created-a-private-team"></a>Stap 1: een privé team maken

Als u de toegang tot de onderliggende SharePoint-site voor het team wilt beveiligen, zijn de beheerders van Contoso IT de [Aanbevolen beleidsregels voor toegang tot SharePoint](../security/office-365-security/sharepoint-file-access-policies.md)geconfigureerd.

Vervolgens heeft een contoso IT-beheerder een nieuw privé team gemaakt met de naam Project 2 en worden de gebruikersaccounts van project en de werknemers toegevoegd als leden. Ze hebben ook het team geconfigureerd, zodat alleen project van team eigenaren persoonlijke kanalen kan maken.

Zie [een privé team maken](secure-teams-security-isolation.md#create-a-private-team)voor meer informatie over de configuratie.

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>Stap 2: een gevoeligheids label voor het project, 2 en team maken

Contoso-beheerders hebben een nieuwe vertrouwelijkheids label gemaakt, met de naam **Project 2** :

- Versleuteling ingeschakeld.
- Machtigingen voor Co-Author toegestaan voor de groep project 2 en Microsoft 365.
- Toegestane Viewer machtigingen voor de Senior leiderschaps groep.
- Toegang tot niet-beheerde apparaten is geblokkeerd.

Bestanden in de sectie **documenten** van het onderliggende project van de SharePoint-site zijn beschermd door:

- De site machtigingen, die alleen volledige machtigingen toestaan voor leden van het project en de Microsoft 365-groep en machtigingen voor lezen voor de Senior leiderschaps groep.
- Het bestand voor de vertrouwelijkheids label van het project en de machtigingen die met het bestand worden verplaatst of gekopieerd van de site.

Zie [een gevoeligheids label maken](secure-teams-security-isolation.md#create-a-sensitivity-label)voor meer informatie over de configuratie.

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>Stap 3: de onderliggende SharePoint-site is geconfigureerd

Als u de toegang tot de onderliggende SharePoint-site voor het team wilt beveiligen, zijn de beheerders van Contoso IT de [Aanbevolen beleidsregels voor toegang tot SharePoint](../security/office-365-security/sharepoint-file-access-policies.md)geconfigureerd.

Vervolgens hebben ze extra machtigingsinstellingen voor de site geconfigureerd:

- Om te voorkomen dat project en groepsleden toegang kunnen delen tot de site. Zie voor meer informatie over de configuratie van [SharePoint-instellingen voor een team met beveiligings isolatie](secure-teams-security-isolation.md#sharepoint-settings).
- Voor leesmachtigingen voor de Senior leiderschaps groep.

Vervolgens hebben ze extra machtigingsinstellingen voor de site geconfigureerd om te voorkomen dat project en groepsleden toegang kunnen delen tot de site. 

Als private-kanalen voor het project van twee 2X werden gemaakt, zijn de groepseigenaren uitgeschakeld voor het delen van gasten en stelt u de standaardkoppeling voordelen in op de waarde van **bepaalde personen** .

Dit is de uitkomst van de configuratie van het project en het team en het team van beveiligings isolatie.

![De resultaten configuratie van het project en het team.](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>Stap 4: opgeleid project van teamleden

Contoso beveiligingspersoneel heeft het project en de teamleden getraind in een verplichte cursus waarin ze worden getrapt:

- U kunt toegang krijgen tot het nieuwe project van het team, van vergaderingen en chats, en hoe u kunt samenwerken aan team bestanden.
- Het maken van nieuwe bestanden in het team en het uploaden van nieuwe bestanden die lokaal zijn gemaakt.
- Een label voor het delen van bestanden met het vertrouwelijkheids label van project 2.
- In dit voorblad kunt u zien hoe het project en het label een bestand beschermt, zelfs als het team van het team valt.

Het eindresultaat is een veilige omgeving waarin project van teamleden in een beveiligde omgeving is samengewerkt voor chat gesprekken, vergaderingen en bestanden.

Hier ziet u een voorbeeld van een bestand dat is opgeslagen in het onderliggende project en de site van het onderliggende project.

![Een voorbeeld van een bestand dat is opgeslagen in het onderliggende project van de site.](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

In een aantal gevallen hebben project en teamleden gedownloade bestanden die zijn beveiligd door het project en het label voor een lokaal station voor offline werken. 

Wanneer u de persoon opent, kunt u zich echter eerst een foutmelding krijgen en de referenties verwijderen.

Vanwege de samenwerkingsomgeving van teams en de beveiligingsfuncties van Microsoft 365, zijn de details van project 2X lang geheim voor de duur van het project. Contoso heeft zijn of haar plannen bekendgemaakt en is bezig met de implementatie van de nieuwe producten en diensten in het licht van zijn klanten en beleggers en de Chagrin van zijn concurrenten.

## <a name="next-step"></a>Volgende stap

[Implementeer een team met beveiligings isolatie](secure-teams-security-isolation.md) in uw organisatie.

