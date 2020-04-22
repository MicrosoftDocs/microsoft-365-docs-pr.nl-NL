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
description: 'Samenvatting: Hoe Contoso een SharePoint-site implementeerde voor sterk gereguleerde gegevens voor een eenvoudigere samenwerking tussen zijn onderzoeksteams.'
ms.openlocfilehash: 0a4bc2f685cf015611da62ebbed000218f37f31e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634250"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>SharePoint-site voor zeer vertrouwelijke digitale activa van de Contoso Corporation

Contoso's meest waardevolle activa zijn de intellectuele eigendom in de vorm van bedrijfsgeheimen, zoals gepatenteerde productietechnieken, en ontwerpspecificaties voor producten die in ontwikkeling zijn. Deze assets waren in digitale vorm, oorspronkelijk opgeslagen als bestanden op een SharePoint Server 2016-site. Toen Contoso Microsoft 365 Enterprise inzette, wilden ze hun on-premises digitale assets naar de cloud overzetten voor gemakkelijkere toegang en meer open samenwerking tussen onderzoeksteams in Parijs, Moskou, New York, Beijing en Bangalore. 
  
Vanwege hun gevoelige aard moet de toegang tot deze bestanden echter:

- Beperkt tot de groep mensen die toegang hebben tot hen. 
- Beschermd met een DLP-beleid (Data Loss Prevention) om te voorkomen dat gebruikers ze buiten de site distribueren.
- Versleuteld en beveiligd met machtigingen om te voorkomen dat onbevoegde gebruikers toegang krijgen tot hun inhoud, zelfs als ze buiten de site worden gedistribueerd.

Security- en SharePoint-beheerders in de IT-afdeling van Contoso besloten een [SharePoint-site](teams-sharepoint-online-sites-highly-regulated-data.md)te gebruiken voor sterk gereguleerde gegevens.
  
Contoso gebruikte deze stappen om een SharePoint-teamsites voor hun onderzoeksteams te maken en te beveiligen.

## <a name="step-1-created-a-private-sharepoint-team-site"></a>Stap 1: Een eigen SharePoint-teamsite maken

Om de toegang tot de SharePoint-site te beschermen, heeft Contoso IT het [aanbevolen SharePoint-toegangsbeleid](sharepoint-file-access-policies.md)geconfigureerd.

Vervolgens stelden De it-beheerders van Contoso een lijst samen van de gebruikersaccounts van de onderzoekers in hun kantoren in Parijs, Moskou, New York, Beijing en Bangalore. 

Vervolgens heeft een Contoso IT-beheerder een nieuwe privéteamsite met de naam **Research** gemaakt en alle gebruikersaccounts voor zijn onderzoekers toegevoegd.

Vervolgens configureerden ze extra machtigingsinstellingen voor de site om te voorkomen dat onderzoekers toegang tot de site delen en om te voorkomen dat niet-onderzoekers toegang tot de site aanvragen.

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a>Stap 2: De site configureren voor een restrictief DLP-beleid

Ten eerste pasten Contoso-beheerders het bestaande **label voor zeer vertrouwelijke** bewaartoepassing toe op de map Documenten van de **onderzoekssite.**

Vervolgens hebben ze een nieuw DLP-beleid gemaakt met de naam **Research** dat:

- Gebruikt het **highly confidential** retention label. 
- Blokkeert gebruikers wanneer ze proberen een digitaal actief te delen op de **onderzoekssite** buiten Contoso.

Zie [SharePoint-bestanden beveiligen met bewaarlabels en DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)voor de configuratiegegevens.

## <a name="step-3-created-a-sensitivity-sublabel-for-the-site"></a>Stap 3: Een sublabel gevoeligheid voor de site maken

Contoso-beheerders hebben een nieuw sublabel voor gevoeligheid gemaakt met de naam **Research Teams** van het **label Highly Confidential** dat:

- Vereist versleuteling.
- Machtigingen voor co-auteur toestaan voor de **Groep Onderzoek** Microsoft 365
- Van toepassing op de **Groep Onderzoek** Microsoft 365

Hier is de resulterende configuratie van de **research** team site voor zeer vertrouwelijke activa.

![De resulterende configuratie van de research team site voor zeer vertrouwelijke activa](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

Bestanden in mappen van de **onderzoekssite** worden beschermd door:

- De sitemachtigingen, die alleen toegang geven tot leden van de **Groep Research** Microsoft 365.
- Het **Research** DLP-beleid, dat gebruik maakt van het **label Highly Confidential** retention en instellingen die voorkomen dat het bestand wordt gedeeld met externe gebruikers.
- Het sublabel voor gevoeligheid **van Onderzoeksteams,** met versleuteling en machtigingen die met het bestand reizen als het wordt verplaatst of gekopieerd van de **onderzoekssite.**

Hier is een voorbeeld van een bestand dat is opgeslagen op de **onderzoekssite** met het sublabel Gevoeligheid **van onderzoeksteams** toegewezen.

![De resulterende configuratie van de research team site voor zeer vertrouwelijke activa](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-4-migrated-the-on-premises-sharepoint-research-data"></a>Stap 4: De on-premises SharePoint-onderzoeksgegevens gemigreerd

Contoso-beheerders hebben alle on-premises onderzoeksbestanden in de on-premises SharePoint Server 2016-site verplaatst naar mappen in de nieuwe SharePoint-site **voor onderzoek.**

## <a name="step-5-trained-their-researchers"></a>Stap 5: Getrainde hun onderzoekers

Contoso-beveiligingspersoneel heeft de leden van de **Research** Microsoft 365-groep getraind in een verplichte cursus die hen doorzette:

- Hoe toegang te krijgen tot de nieuwe **Research-site** en de bestaande bestanden.
- hoe ze nieuwe bestanden op de site kunnen maken en nieuwe bestanden kunnen uploaden die lokaal zijn opgeslagen.
- Een demonstratie van hoe het **Research** DLP-beleid blokkeert dat bestanden extern worden gedeeld.
- Hoe bestanden te labelen met het sublabel **Gevoeligheid van onderzoeksteams.**
- Een demonstratie van hoe het **sublabel van** de Onderzoeksteams een bestand beschermt, zelfs wanneer het van de site wordt gelekt.

Het eindresultaat is een veilige omgeving waarin de onderzoekers in een beveiligde omgeving kunnen samenwerken in een beveiligde omgeving aan bestanden met onderzoeksinformatie. 

Als een onderzoeksdocument met het sublabel **Research Teams** de **onderzoekssite** verlaat, wordt het alleen versleuteld en toegankelijk voor leden van de **Research** Microsoft 365-groep met geldige gebruikersaccountgegevens.

## <a name="next-step"></a>Volgende stap

[Implementeren](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in uw organisatie.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)
