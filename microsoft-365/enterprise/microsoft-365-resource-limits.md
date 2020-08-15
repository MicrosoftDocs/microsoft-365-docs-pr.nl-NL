---
title: Microsoft 365-resource limieten
ms.author: josephd
author: JoeDavies-MSFT
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
description: In dit artikel vindt u informatie over resource limieten voor de verschillende toepassingen in Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6053740d41b02461432243c8527391a4f8ae22ea
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689373"
---
# <a name="resource-limits"></a>Resource limieten

Resource limieten worden afgedwongen met quota's (limieten) en gashendel. Azure Active Directory (Azure AD) en de afzonderlijke Microsoft 365-Services gebruiken beide. Limieten zijn specifiek voor de service, en veranderen over de tijd wanneer nieuwe functies worden toegevoegd. Zie de volgende onderwerpen voor meer informatie over de huidige limieten voor de verschillende services:

- [Azure AD-Servicebeperkingen en-beperkingen](https://docs.microsoft.com/azure/azure-resource-manager/management/azure-subscription-service-limits)
- [Beperkingen in Exchange Online](https://technet.microsoft.com/library/exchange-online-limits.aspx)
- [Beveiligingsbeperkingen voor Exchange Online](https://technet.microsoft.com/library/exchange-online-protection-limits.aspx)
- [Software grenzen en-limieten voor SharePoint Online](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [Limieten voor Skype voor bedrijven](https://technet.microsoft.com/library/skype-for-business-online-limits.aspx)
- [Yammer REST API en tarief limieten](https://developer.yammer.com/docs/rest-api-rate-limits)
- [Limieten voor de bestandsgrootte in Sway](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

Naast deze limieten worden ook enkele mechanismen voor het beperken van de gashendel gebruikt in azure AD en Microsoft 365. De beperking binnen de service is vooral belangrijk, op voorwaarde dat netwerkbronnen in de datacenters van Microsoft zijn geoptimaliseerd voor de grote set klanten die de Services gebruiken. Beperkings mechanismen omvatten:

- Gebruikers van Azure AD en Microsoft 365 stellen gebruikersniveau in voor het beperken van het aantal transacties of gelijktijdig bellen (via script of code) dat door één gebruiker kan worden uitgevoerd.
- Bij het maken van tenants wordt een standaard PowerShell-beleid voor PowerShell toegewezen aan elke Tenant. Deze instellingen zijn van invloed op andere items, zoals het maximum aantal gelijktijdige PowerShell-sessies dat door één beheerder kan worden geopend.
- Elke Exchange Online-klant heeft een standaardbeleid voor Exchange Web Services (EWS) dat is afgestemd op EWS-client bewerkingen en beperkingen die van toepassing zijn op alle Outlook-clients.
