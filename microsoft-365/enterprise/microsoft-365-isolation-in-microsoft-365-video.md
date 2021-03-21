---
title: Tenantisolatie in Office 365 Video
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In dit artikel vindt u een uitleg over hoe tenantisolatie de opgeslagen video's van elke tenant gescheiden houdt in Office 365 Video.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fc67b17aa40b3bca9ce6d73ebb7e18319e780339
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918928"
---
# <a name="tenant-isolation-in-office-365-video"></a>Tenantisolatie in Office 365 Video

> [!NOTE]
> Office 365 Video wordt vervangen door Microsoft Stream. Zie Office 365 Video transition to Microsoft Stream overview (Office 365 Video transition to Microsoft Stream overview) voor meer informatie over de nieuwe enterprise videoservice die informatie toevoegt aan videosamenwerking en meer informatie over de overgangsplannen voor huidige Klanten met Microsoft [365 Video.](/stream/migrate-from-office-365)

## <a name="introduction"></a>Inleiding

Azure Storage wordt gebruikt om gegevens op te slaan voor meerdere Office 365-services, waaronder Office 365 Video en Sway. Azure Storage bevat Blob-opslag, een zeer schaalbare, op REST gebaseerde cloudobjectstore die wordt gebruikt voor het opslaan van ongestructureerde gegevens. Azure Storage maakt gebruik van een eenvoudig toegangsbeheermodel. Elk Azure-abonnement kan een of meer opslagaccounts maken. Elk opslagaccount heeft één geheime sleutel die wordt gebruikt om de toegang tot alle gegevens in dat opslagaccount te bepalen. Dit ondersteunt het gebruikelijke scenario waarin opslag is gekoppeld aan toepassingen en deze toepassingen volledige controle hebben over de bijbehorende gegevens. bijvoorbeeld: Sway die inhoud opslaat in Azure Storage. Alle klantinhoud voor Sway wordt opgeslagen in gedeelde Azure-opslagaccounts. De inhoud van elke gebruiker staat in een aparte adreslijststructuur met blobs in Azure-opslag.

De systemen die toegang tot klantomgevingen beheren (bijvoorbeeld de Azure Portal, SMAPI, enzovoort) worden geïsoleerd in een Azure-toepassing die door Microsoft wordt beheerd. Dit scheidt logischerwijs de klanttoegangsinfrastructuur van de klanttoepassingen en de opslaglaag.

## <a name="tenant-isolation-in-office-365-video"></a>Tenantisolatie in Office 365 Video

[Office 365 Video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) is een ondernemingsportal die organisaties een zeer veilige, organisatiebrede bestemming biedt voor het posten, delen en ontdekken van video-inhoud. In Office 365 Video worden de video's van elke tenant geïsoleerd en versleuteld op alle locaties bewaard en zijn ze alleen beschikbaar voor geverifieerde gebruikers die toegang en machtigingen hebben voor de video's van de organisatie. Office 365 Video gebruikt hiervoor een combinatie van technologieën:

- SharePoint Online wordt gebruikt voor het opslaan van het videobestand en metagegevens (videotitel, beschrijving, enzovoort). Het biedt ook de beveiligings- en compliancelaag (inclusief verificatie) en zoekfuncties.
- Azure Media Services biedt transcodering, adaptieve streaming, veilige levering (met AES-versleuteling) en miniatuurfuncties.

[Azure Media Services](https://azure.microsoft.com/services/media-services/) is een platform-as-a-service-aanbieding voor het inschakelen van end-to-end mediawerkstromen in de cloud. Het platform biedt een REST-API voor het uploaden, coderen, versleutelen (met PlayReady) en het leveren van media via Azure-datacenters over de hele wereld.

Alle uploads voor Office 365 Video vinden plaats via HTTPS. Wanneer een videobestand wordt geüpload, wordt het opgeslagen in SharePoint Online en wordt een kopie van het bestand verzonden via een versleuteld kanaal naar Azure Media Services. Azure Media Services transcodeert de video in meerdere indelingen die zijn geoptimaliseerd voor weergave-ervaring (bijvoorbeeld mobiel, lage bandbreedte, hoge bandbreedte, enzovoort). Deze bestanden, samen met het oorspronkelijke bestand dat tijdens het uploaden is verkregen, worden opgeslagen in Azure Blob-opslag. De bestanden worden versleuteld met AES 128 volgens het mpeg-algoritme voor algemene versleuteling (of een eerdere PlayReady-versie) voor afspelen en versleuteld met AES 256-opslagversleuteling voordat ze worden opgeslagen in Azure Blob-opslag. (Met de Azure Media Services Client SDK kunnen klanten bepalen welke versleuteling wordt gebruikt. Een klant kan bijvoorbeeld Azure Media Services-opslagversleuteling (AES 256) toepassen op een hoogwaardig media-activum voordat deze Azure Blob-opslag wordt geüpload.)

Azure Media Services genereert ook een miniatuur voor de video, die wordt verzonden samen met miniatuurmetagegevens naar SharePoint Online via een versleuteld kanaal.