---
title: Gebruikers toestemming voor apps beheren in Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Meer informatie over toestemming van gebruikers voor apps en hoe u deze in kunt stellen om apps van derden toegang te geven tot de Microsoft 365 gebruikersgegevens.
ms.openlocfilehash: 629e64494c6d72a13c3b155370a8f47505e9fa20
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53391229"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Gebruikers toestemming voor apps beheren in Microsoft 365

Met deze instelling bepaalt u of gebruikers die toestemming kunnen geven voor apps die OpenID-Verbinding maken en OAuth 2.0 gebruiken voor aanmelding en aanvragen voor toegang tot gegevens. Een app kan worden gemaakt vanuit uw eigen organisatie, of deze kan afkomstig zijn van een andere Office 365 of een externe organisatie.

Als u deze instelling int, vragen deze apps gebruikers om toestemming voor toegang tot de gegevens van uw organisatie en kunnen gebruikers kiezen of ze deze mogen toestaan. Als u deze instelling uit schakelen, moeten beheerders toestemming geven voor deze apps voordat gebruikers deze kunnen gebruiken. In dit geval kunt u overwegen een toestemmingswerkstroom voor beheerders in te stellen in de Azure-portal, zodat gebruikers een aanvraag voor goedkeuring van beheerders kunnen verzenden om een geblokkeerde app te gebruiken.

Een gebruiker kan alleen toegang geven voor apps waarvan ze de eigenaar zijn en waarvoor toegang tot hun Office 365-gegevens is vereist. Ze kunnen apps geen toestemming geven voor het gebruik van gegevens van anderen.

## <a name="turning-user-consent-on-or-off"></a>Toestemming van gebruikers in- of uitschakelen

U kunt als eerste de toestemming van gebruikers voor apps in- of uitschakelen.

1. Ga in het beheercentrum naar de **pagina Instellingen** Instellingen \> **voor Organisaties**  >  [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) en selecteer vervolgens Gebruikers **toestemming voor apps.**

2. Selecteer op **de pagina Gebruikers toestemming voor apps** de optie om toestemming van gebruikers in of uit te schakelen.

## <a name="related-content"></a>Verwante inhoud 

[De werkstroom voor beheerdersmachtiging](/azure/active-directory/manage-apps/configure-admin-consent-workflow) configureren (artikel)\
[Toestemming voor toepassingen beheren en toestemmingsaanvragen evalueren](/azure/active-directory/manage-apps/manage-consent-requests) (artikel)