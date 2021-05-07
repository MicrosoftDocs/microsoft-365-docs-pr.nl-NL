---
title: Data Encryption in OneDrive for Business and SharePoint Online
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: Meer informatie over de basiselementen van versleuteling voor gegevensbeveiliging in OneDrive voor Bedrijven en SharePoint Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ca93d04fa21487ad054cd9cb924dff1fc15abfbd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162087"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a>Data Encryption in OneDrive for Business and SharePoint Online

Meer informatie over de basiselementen van versleuteling voor gegevensbeveiliging in OneDrive voor Bedrijven en SharePoint Online.
  
## <a name="security-and-data-encryption-in-office-365"></a>Beveiligings- en gegevensversleuteling in Office 365

Microsoft 365 is een zeer veilige omgeving die uitgebreide beveiliging biedt in meerdere lagen: fysieke beveiliging van datacenters, netwerkbeveiliging, toegangsbeveiliging, toepassingsbeveiliging en gegevensbeveiliging. In dit artikel wordt specifiek aandacht besteedt aan de versleutelingszijde van gegevensbeveiliging tijdens de overdracht en de rest van de gegevensbeveiliging voor OneDrive voor Bedrijven en SharePoint Online.
  
Bekijk in de volgende video hoe gegevensversleuteling werkt.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a>Versleuteling van gegevens die onderweg zijn

In OneDrive voor Bedrijven en SharePoint Online zijn er twee scenario's waarin gegevens de datacenters worden binnen- en afgesloten.
  
- **Clientcommunicatie met de server** Voor communicatie OneDrive voor Bedrijven internet wordt gebruikgemaakt van SSL-/TLS-verbindingen. Alle SSL-verbindingen worden tot stand gebracht met behulp van 2048-bits toetsen.

- **Gegevensverkeer tussen datacenters** De primaire reden voor het verplaatsen van gegevens tussen datacenters is dat georeplicatie het herstel van rampen mogelijk maakt. U kunt bijvoorbeeld SQL Server transactielogboeken en blobopslagdelta's langs deze pijp laten gaan. Hoewel deze gegevens al worden verzonden via een privénetwerk, is deze verder beveiligd met de beste versleuteling. 

## <a name="encryption-of-data-at-rest"></a>Versleuteling van gegevens in rust

Versleuteling in rust bevat twee onderdelen: BitLocker versleuteling op schijfniveau en versleuteling per bestand van klantinhoud.
  
BitLocker wordt geïmplementeerd voor OneDrive voor Bedrijven en SharePoint online in de service. Versleuteling per bestand is ook beschikbaar in OneDrive voor Bedrijven en SharePoint Online in Microsoft 365 multi-tenant en nieuwe speciale omgevingen die zijn gebaseerd op multi-tenanttechnologie.
  
Hoewel BitLocker gegevens op een schijf versleutelt, gaat versleuteling per bestand nog verder door een unieke versleutelingssleutel voor elk bestand op te geven. Bovendien wordt elke update voor elk bestand versleuteld met een eigen versleutelingssleutel. Voordat ze worden opgeslagen, worden de sleutels van de versleutelde inhoud opgeslagen op een fysiek aparte locatie dan de inhoud. Elke stap van deze versleuteling maakt gebruik van Advanced Encryption Standard (AES) met 256 bitstoetsen en is compatibel met Federal Information Processing Standard (FIPS) 140-2. De versleutelde inhoud wordt verdeeld over een aantal containers in het datacenter en elke container heeft unieke referenties. Deze referenties worden opgeslagen op een afzonderlijke fysieke locatie van de inhoud of de inhoudstoetsen.
  
Zie FIPS 140-2 Compliance voor meer informatie over naleving van [FIPS 140-2.](/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105))
  
Versleuteling op bestandsniveau maakt gebruik van blobopslag om vrijwel onbeperkte opslaggroei te bieden en ongeëvenaarde beveiliging mogelijk te maken. Alle klantinhoud in OneDrive voor Bedrijven en SharePoint Online wordt gemigreerd naar blobopslag. Deze gegevens worden als volgende beveiligd:
  
1. Alle inhoud is versleuteld, mogelijk met meerdere sleutels, en verspreid over het datacenter. Elk bestand dat moet worden opgeslagen, is onderverdeeld in een of meer segmenten, afhankelijk van de grootte. Vervolgens wordt elk segment versleuteld met een eigen unieke sleutel. Updates worden op dezelfde manier verwerkt: de set wijzigingen of delta's die door een gebruiker worden verzonden, is onderverdeeld in segmenten en elk bestand wordt versleuteld met een eigen sleutel.

2. Al deze segmenten, bestanden, stukken bestanden en update delta's, worden opgeslagen als blobs in onze blobstore. Ze zijn ook willekeurig verdeeld over meerdere blobcontainers.

3. De 'kaart' die wordt gebruikt om het bestand opnieuw te assembleren op basis van de onderdelen, wordt opgeslagen in de inhoudsdatabase.

4. Elke blobcontainer heeft zijn eigen unieke referenties per toegangstype (lezen, schrijven, opsnoemen en verwijderen). Elke set referenties wordt bewaard in de beveiligde Key Store en wordt regelmatig vernieuwd.

Met andere woorden, er zijn drie verschillende soorten winkels die betrokken zijn bij versleuteling per bestand in rust, elk met een afzonderlijke functie:
  
- Inhoud wordt opgeslagen als versleutelde blobs in de blobstore. De sleutel voor elk deel van de inhoud wordt versleuteld en afzonderlijk opgeslagen in de inhoudsdatabase. De inhoud zelf heeft geen idee hoe deze kan worden ontsleuteld.

- De inhoudsdatabase is een SQL Server database. De map bevat de map die nodig is om alle inhoudsblobs in de blobstore te zoeken en opnieuw in elkaar te zetten, evenals de sleutels die nodig zijn om deze blobs te ontsleutelen.

Elk van deze drie opslagonderdelen, de blobstore, de inhoudsdatabase en het Sleutelopslag, is fysiek gescheiden. De gegevens die in een van de onderdelen worden opgehouden, kunnen alleen niet worden gebruikt. Dit biedt een ongeëvenaard beveiligingsniveau. Zonder toegang tot alle drie is het onmogelijk om de sleutels van de segmenten op te halen, de sleutels te ontsleutelen om ze bruikbaar te maken, de toetsen te koppelen aan de bijbehorende segmenten, een stuk te ontsleutelen of een document te reconstrueren uit de samenstellende segmenten.