---
title: SharePoint-site voor zeer vertrouwelijke digitale activa van de Contoso Corporation
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
description: 'Samenvatting: Hoe Contoso een SharePoint-site implementeerde voor sterk gereguleerde gegevens voor eenvoudigere samenwerking tussen zijn onderzoeksteams.'
ms.openlocfilehash: a1ffb336e85eb6eb850b53ed14adf947b56642cc
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806821"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>SharePoint-site voor zeer vertrouwelijke digitale activa van de Contoso Corporation

Contoso's meest waardevolle activa zijn de intellectuele eigendom in de vorm van bedrijfsgeheimen, zoals gepatenteerde productietechnieken, en ontwerpspecificaties voor producten die in ontwikkeling zijn. Deze elementen waren in digitale vorm, oorspronkelijk opgeslagen als bestanden op een SharePoint Server 2016-site. Toen Contoso Microsoft 365 Enterprise inzette, wilden ze hun on-premises digitale assets naar de cloud overbrengen voor eenvoudigere toegang en meer open samenwerking tussen onderzoeksteams in Parijs, Moskou, New York, Beijing en Bangalore. 
  
Vanwege hun gevoelige karakter moet de toegang tot deze bestanden echter zijn:

- Beperkt tot de groep mensen die toegang hebben tot hen. 
- Beveiligd met een DLP-beleid (Data Loss Prevention) om te voorkomen dat gebruikers ze buiten de site distribueren.
- Versleuteld en beveiligd met machtigingen om te voorkomen dat onbevoegde gebruikers toegang krijgen tot hun inhoud, zelfs als ze buiten de site worden gedistribueerd.

Beveiligings- en SharePoint-beheerders in de IT-afdeling van Contoso besloten een [SharePoint-site](teams-sharepoint-online-sites-highly-regulated-data.md)te gebruiken voor sterk gereguleerde gegevens.
  
Contoso gebruikte deze stappen om een SharePoint-teamsites voor hun onderzoeksteams te maken en te beveiligen.

## <a name="step-1-created-a-private-sharepoint-team-site"></a>Stap 1: Een privé SharePoint-teamsite maken

Om de toegang tot de SharePoint-site te beschermen, heeft Contoso IT het [aanbevolen SharePoint-toegangsbeleid](sharepoint-file-access-policies.md)geconfigureerd.

Vervolgens stelden Contoso IT-beheerders een lijst samen van de gebruikersaccounts voor de onderzoekers in hun kantoren in Parijs, Moskou, New York, Beijing en Bangalore. 

Vervolgens heeft een Contoso IT-beheerder een nieuwe privéteamsite gemaakt met de naam **Research** en alle gebruikersaccounts voor zijn onderzoekers toegevoegd.

Vervolgens hebben ze extra machtigingsinstellingen voor de site geconfigureerd om te voorkomen dat onderzoekers toegang tot de site delen en om te voorkomen dat niet-onderzoekers toegang tot de site zouden aanvragen.

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a>Stap 2: De site geconfigureerd voor een restrictief DLP-beleid

Ten eerste hebben Contoso-beheerders het bestaande **zeer vertrouwelijke** Office 365-bewaarlabel toegepast op de map Documenten van de **onderzoekssite.**

Vervolgens hebben ze een nieuw Office 365 DLP-beleid met de naam **Research** gemaakt, dat:

- Gebruikt het **bewaarlabel Zeer vertrouwelijk** Office 365. 
- Blokkeert gebruikers wanneer ze proberen om een digitaal actief te delen op de **onderzoekssite** buiten Contoso.

Zie [SharePoint-bestanden beveiligen met bewaarlabels en DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)voor de configuratiegegevens.

## <a name="step-3-created-an-office-365-sensitivity-sublabel-for-the-site"></a>Stap 3: Een sublabel voor gevoeligheid van Office 365 voor de site maken

Contoso-beheerders hebben een nieuw sublabel voor gevoeligheid van Office 365 gemaakt met de naam **Research Teams** van het label **Zeer vertrouwelijk** dat:

- Vereist encryptie.
- Co-auteurmachtigingen toestaan voor de **groep Research** Office 365
- Van toepassing op de **groep Research** Office 365

Hier is de resulterende configuratie van de **research** team site voor zeer vertrouwelijke activa.

![De resulterende configuratie van de onderzoeksteamsite voor zeer vertrouwelijke activa](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

Bestanden in mappen van de **onderzoekssite** worden beschermd door:

- De sitemachtigingen, die alleen toegang bieden tot leden van de **groep Research** Office 365.
- Het **Beleid Voor Onderzoek** DLP, dat het zeer **vertrouwelijke** bewaarlabel en -instellingen gebruikt om te voorkomen dat het bestand wordt gedeeld met externe gebruikers.
- Het gevoeligheidssublabel **van de onderzoeksteams,** met versleuteling en machtigingen die met het bestand reizen als het wordt verplaatst of gekopieerd van de **onderzoekssite.**

Hier is een voorbeeld van een bestand opgeslagen in de **onderzoekssite** met het gevoeligheidssublabel **van onderzoeksteams** toegewezen.

![De resulterende configuratie van de onderzoeksteamsite voor zeer vertrouwelijke activa](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-4-migrated-the-on-premises-sharepoint-research-data"></a>Stap 4: De on-premises SharePoint-onderzoeksgegevens gemigreerd

Contoso-beheerders verplaatsten alle on-premises onderzoeksbestanden op de on-premises SharePoint Server 2016-site naar mappen in de nieuwe SharePoint-onderzoekssite. **Research**

## <a name="step-5-trained-their-researchers"></a>Stap 5: Trainde hun onderzoekers

Contoso-beveiligingspersoneel heeft de leden van de **Research** Office 365-groep opgeleid in een verplichte cursus die hen doorzette:

- Hoe toegang te krijgen tot de nieuwe **onderzoekssite** en de bestaande bestanden.
- Nieuwe bestanden op de site maken en nieuwe bestanden uploaden die lokaal zijn opgeslagen.
- Een demonstratie van hoe het DLP-beleid van Het **Onderzoek** bestanden blokkeert om extern te worden gedeeld.
- Bestanden labelen met het gevoeligheidssublabel **van onderzoeksteams.**
- Een demonstratie van hoe het sublabel van de **Onderzoeksteams** een bestand beschermt, zelfs wanneer het van de site is gelekt.

Het eindresultaat is een veilige omgeving waarin de onderzoekers via Contoso kunnen samenwerken in een beveiligde omgeving aan bestanden met onderzoeksinformatie. 

Als een onderzoeksdocument met het sublabel **Research Teams** de **onderzoekssite** verlaat, is het versleuteld en alleen toegankelijk voor leden van de **Research** Office 365-groep met geldige gebruikersaccountreferenties.

## <a name="next-step"></a>Volgende stap

[Implementeren](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in uw organisatie.

## <a name="see-also"></a>Zie ook

[Microsoft 365-productiviteitsbibliotheek](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)
