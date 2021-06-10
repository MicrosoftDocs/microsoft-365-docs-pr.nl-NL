---
title: Gebruik op rollen gebaseerd toegangsbeheer om fijnkorrelige toegang te verlenen tot Microsoft Defender-beveiligingscentrum
description: Maak rollen en groepen binnen uw beveiligingsbewerkingen om toegang te verlenen tot de portal.
keywords: rbac, rol, gebaseerd, toegang, besturingselement, groepen, besturingselement, laag, aad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d95163bd7caf6e05295fc35b3f9c2bf95230dc83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058182"
---
# <a name="manage-portal-access-using-role-based-access-control"></a>Portaltoegang beheren met behulp van toegangsbeheer op basis van rollen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft Azure Active Directory
- Office 365

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-rbac-abovefoldlink)

Met behulp van RBAC (Role Based Access Control) kunt u rollen en groepen maken binnen uw beveiligingsbewerkingsteam om de juiste toegang tot de portal te verlenen. Op basis van de rollen en groepen die u maakt, hebt u een fijnkorrelige controle over wat gebruikers met toegang tot de portal kunnen zien en doen. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bJ2a]

Grote teams voor geo-gedistribueerde beveiligingsbewerkingen gebruiken meestal een op een laag gebaseerd model om toegang tot beveiligingsportals toe te wijzen en te machtigen. Standaardlagen zijn de volgende drie niveaus:

Laag | Beschrijving
:---|:---
Laag 1 | **Team voor lokale beveiligingsbewerkingen / IT-team** <br> Dit team triages and investigates alerts contained within their geocation and escalates to Tier 2 in cases where a active remediation is required.
Laag 2 | **Team voor regionale beveiligingsbewerkingen** <br> Dit team kan alle apparaten voor hun regio zien en herstelacties uitvoeren.
Laag 3 | **Team voor globale beveiligingsbewerkingen** <br> Dit team bestaat uit beveiligingsexperts en is gemachtigd om alle acties vanuit de portal te bekijken en uit te voeren.

Defender for Endpoint RBAC is ontworpen ter ondersteuning van uw keuzemodel op basis van lagen of rollen en biedt u gedetailleerde controle over welke rollen kunnen worden gezien, apparaten die ze kunnen openen en acties die ze kunnen uitvoeren. Het RBAC-framework is gecentreerd rond de volgende besturingselementen:

- **Bepalen wie specifieke actie kan ondernemen**
  - Maak aangepaste rollen en beheer de mogelijkheden van Defender voor eindpunten die ze met granulariteit kunnen openen.
 
- **Bepalen wie informatie kan zien over specifieke apparaatgroepen of groepen**
  - [Maak apparaatgroepen](machine-groups.md) op basis van specifieke criteria, zoals namen, tags, domeinen en andere, en verleen vervolgens roltoegang aan deze groepen met behulp van een specifieke Azure Active Directory (Azure AD) gebruikersgroep.

Als u op rollen gebaseerde toegang wilt implementeren, moet u beheerdersrollen definiëren, bijbehorende machtigingen toewijzen en Azure AD-gebruikersgroepen toewijzen die aan de rollen zijn toegewezen.


### <a name="before-you-begin"></a>Voordat u begint
Voordat u RBAC gebruikt, is het belangrijk dat u de rollen begrijpt die machtigingen kunnen verlenen en de gevolgen van het in- en uitschakelen van RBAC.


> [!WARNING]
> Voordat u de functie inschakelen, is het belangrijk dat u een rol voor globale beheerder of beveiligingsbeheerder hebt in Azure AD en dat uw Azure AD-groepen klaar zijn om het risico te beperken dat u buiten de portal wordt vergrendeld. 

Wanneer u zich voor het eerst aanmeldt bij Microsoft Defender-beveiligingscentrum, krijgt u volledige toegang of alleen-lezentoegang. Volledige toegangsrechten worden verleend aan gebruikers met beveiligingsbeheerder- of globale beheerdersrollen in Azure AD. Alleen-lezen wordt verleend aan gebruikers met een beveiligingslezerrol in Azure AD. 

Iemand met een rol van globale beheerder van Defender voor Eindpunt heeft onbeperkte toegang tot alle apparaten, ongeacht de apparaatgroepsorganisatie en de toewijzingen voor Azure AD-gebruikersgroepen

> [!WARNING]
> In eerste instantie kunnen alleen personen met globale beheerders- of beveiligingsbeheerdersrechten van Azure AD rollen maken en toewijzen in Microsoft Defender-beveiligingscentrum, daarom is het belangrijk dat de juiste groepen klaar zijn in Azure AD.
>
> **Als u toegangsbeheer op basis van rollen invoegt, kunnen gebruikers met alleen-lezen-machtigingen (bijvoorbeeld gebruikers die zijn toegewezen aan de lezerrol van Azure AD Security) de toegang verliezen totdat ze aan een rol zijn toegewezen.** 
>
>Gebruikers met beheerdersmachtigingen krijgen automatisch de standaard ingebouwde rol van globale beheerder van Defender voor Eindpunt toegewezen met volledige machtigingen. Nadat u zich hebt voor het gebruik van RBAC hebt gekozen, kunt u extra gebruikers die geen Globale Azure AD- of Beveiligingsbeheerders zijn, toewijzen aan de globale beheerdersrol van Defender voor Eindpunt. 
>
> Nadat u zich hebt aangemeld voor het gebruik van RBAC, kunt u niet terugkeren naar de eerste rollen zoals wanneer u zich voor het eerst hebt aangemeld bij de portal. 



## <a name="related-topic"></a>Verwant onderwerp
- [Apparaatgroepen maken en beheren in Microsoft Defender voor Eindpunt](machine-groups.md)
