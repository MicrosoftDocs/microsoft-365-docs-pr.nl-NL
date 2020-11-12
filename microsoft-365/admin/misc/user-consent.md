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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Lees meer over de gebruikers vergunning voor apps en hoe u ze kunt inschakelen om apps van derden toegang te geven tot de Microsoft 365-informatie van gebruikers.
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999563"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Gebruikers toestemming voor apps beheren in Microsoft 365

Met deze instelling wordt bepaald of gebruikers die toestemming kunnen geven voor apps die gebruikmaken van OpenID Connect en OAuth 2,0 voor aanmelding en verzoeken om toegang tot gegevens. U kunt een app maken vanuit uw eigen organisatie of deze afkomstig zijn van een andere Office 365-organisatie of een derde partij.

Als u deze instelling inschakelt, vragen de Apps gebruikers om toegang te krijgen tot de gegevens van uw organisatie, en kunnen gebruikers kiezen of ze dit mogen doen. Als u deze instelling uitschakelt, moeten beheerders toestemming verlenen aan deze apps voordat ze ze kunnen gebruiken. In dit geval kunt u een werkstroom voor het beheer van toestemming van de beheerder instellen voor de Azure-Portal, zodat gebruikers een aanvraag voorgoed keuring van de beheerder kunnen verzenden om een geblokkeerde app te gebruiken.

Een gebruiker kan alleen toegang geven voor apps waarvan ze de eigenaar zijn en waarvoor toegang tot hun Office 365-gegevens is vereist. Ze kunnen apps geen toestemming geven voor het gebruik van gegevens van anderen.

## <a name="turning-user-consent-on-or-off"></a>Toestemming verlenen om gebruikers in of uit te schakelen
<a name="__toc379982114"> </a>

Ga als volgt te werk om gebruikers toestemming voor apps in of uit te schakelen.

1. Ga in het Beheercentrum naar de pagina **instellingen** voor de services voor \> **organisatie**  >  [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) -instellingen en selecteer **gebruikers instemming met apps**.

2. Selecteer op de pagina **gebruikers toestemming voor apps** de optie om toestemming van de gebruiker in of uit te schakelen.

## <a name="more-info"></a>Meer informatie
<a name="__toc379982114"> </a>

Zie [de werkstroom voor het beheer van de beheerder configureren](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow)voor meer informatie over het configureren van de instellingen voor toestemming in azure Active Directory.

Voor meer informatie over het beheren van gebruikers toestemming voor apps raadpleegt [u de instemming met toepassingen beheren en verzoeken om toestemming te beoordelen](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).