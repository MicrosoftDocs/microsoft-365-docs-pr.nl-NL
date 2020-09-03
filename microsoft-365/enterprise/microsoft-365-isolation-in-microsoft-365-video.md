---
title: Tenant isolatie in Office 365 video
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
description: In dit artikel vindt u een beschrijving van de manier waarop de afzonderlijke Video's van de Tenant in Office 365 video worden bewaard.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 626a995fc5a3ac971c48cc87bec1017134e87b88
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332242"
---
# <a name="tenant-isolation-in-office-365-video"></a>Tenant isolatie in Office 365 video

> [!NOTE]
> Video van Office 365 wordt vervangen door Microsoft stream. Als u meer wilt weten over de nieuwe Enterprise video-service waarmee u informatie toevoegt aan de samenwerking aan Video's en meer wilt weten over de overgangs abonnementen voor actuele Microsoft 365-Video's, raadpleegt [u de video overgang van Office 365 naar Microsoft stream Overview](https://docs.microsoft.com/stream/migrate-from-office-365).

## <a name="introduction"></a>Inleiding

Azure-opslag wordt gebruikt om gegevens op te slaan voor meerdere Office 365-Services, waaronder Office 365 video en Sway. Azure Storage bevat Blobopslag, wat een zeer schaalbaar, REST, Cloud object archief is dat wordt gebruikt voor het opslaan van ongestructureerde gegevens. Azure Storage maakt gebruik van een simpel toegangsbeheer model. elk Azure-abonnement kan een of meer opslag accounts maken. Elk Opslagaccount heeft één geheime sleutel die wordt gebruikt voor het beheren van de toegang tot alle gegevens in dat Opslagaccount. Dit ondersteunt het typische scenario waarbij opslag is gekoppeld aan toepassingen en die toepassingen volledig kunnen worden beheerd voor de bijbehorende gegevens. Sway slaat bijvoorbeeld inhoud op in azure Storage. Alle klant inhoud voor Sway wordt opgeslagen in gedeelde Azure-opslagaccounts. De inhoud van elke gebruiker bevindt zich in een aparte directorystructuur van blob's in azure-opslag.

De systemen die de toegang tot klanten omgevingen beheren (bijvoorbeeld de Azure-Portal, SMAPI, etc.) worden geïsoleerd binnen een Azure-toepassing die door Microsoft wordt beheerd. Dit is logisch van de infrastructuur voor klant toegang van de klanten toepassingen en opslaglaag.

## <a name="tenant-isolation-in-office-365-video"></a>Tenant isolatie in Office 365 video

[Video van Office 365](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) is een Enterprise-Portal waarmee organisaties met een zwaarbeveiligde, organisatie grote bestemming voor het plaatsen, delen en ontdekken van video-inhoud kunnen worden gebruikt. In Office 365 video worden de Video's van elke Tenant geïsoleerd en versleuteld en versleuteld op alle locaties en zijn deze alleen beschikbaar voor geverifieerde gebruikers die toegang hebben tot de Video's van de organisatie. In Office 365 video wordt dit met een combinatie van technologieën verwezenlijkt:

- SharePoint Online wordt gebruikt voor het opslaan van het videobestand en de metagegevens (video titel, beschrijving, enzovoort). Dit levert ook de laag beveiliging en compliance (waaronder verificatie) en zoekfuncties.
- Azure Media Services biedt transcode ring, adaptieve streaming, Secure Delivery (met AES-versleuteling) en Miniature functies.

[Azure Media Services](https://azure.microsoft.com/services/media-services/) is een platform-as-serviceaanbieding voor het inschakelen van end-to-end media-werkstromen in de Cloud. Het platform biedt een REST API voor het uploaden, coderen, versleutelen (met PlayReady) en aflevering van media via Azure-datacenters over de hele wereld.

Alle uploads voor Office 365 video vindt u via HTTPS. Wanneer een videobestand wordt geüpload, wordt dit opgeslagen in SharePoint Online en wordt een kopie van het bestand verzonden via een versleuteld kanaal naar Azure Media Services. Azure Media Services verstuurt de video in meerdere indelingen die geoptimaliseerd zijn voor het weergeven van de ervaring (zoals mobiel, lage bandbreedte, hoge bandbreedte, enzovoort). Deze bestanden, samen met het oorspronkelijke bestand dat is verkregen tijdens het uploaden, worden opgeslagen in Azure Blob Storage. De bestanden worden versleuteld met AES 128 per MPEG common Encryption verpakking-algoritme (of een eerdere PlayReady-versie) voor afspelen en versleuteld met een 256 AES-opslag versleuteling in azure-Blobopslag. (Met de Azure Media Services client SDK kunnen klanten bepalen welke versleuteling wordt gebruikt). Een klant kon bijvoorbeeld Azure Media Services-opslag versleuteling (AES 256) toepassen op een groot media-activum voordat u het Azure-Blobopslag uploadt.)

Azure Media Services genereert ook een miniatuur voor de video, die wordt verstuurd samen met miniatuur gegevens van miniaturen naar SharePoint Online via een versleuteld kanaal.
