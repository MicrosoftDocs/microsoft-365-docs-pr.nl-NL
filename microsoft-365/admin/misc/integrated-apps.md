---
title: Toestemming van gebruikers beheren voor apps in Microsoft 365
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
description: Meer informatie over toestemming van gebruikers voor apps en hoe u deze inschakelen om apps van derden toegang te geven tot de Microsoft 365-gegevens van gebruikers.
ms.openlocfilehash: df81d2cf3e1d796e462d2b9240b8288273ed5372
ms.sourcegitcommit: ff1af42b036bfdf75729db8c78f10cf4642616ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2020
ms.locfileid: "44477170"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Toestemming van gebruikers beheren voor apps in Microsoft 365

Met deze instelling bepaalt u of gebruikers die toestemming kunnen geven aan apps die OpenID Connect en OAuth 2.0 gebruiken voor aanmelding en verzoeken om toegang tot gegevens. Een app kan worden gemaakt vanuit uw eigen organisatie, of deze kan afkomstig zijn van een andere Office 365-organisatie of een derde partij.

Als u deze instelling inschakelt, vragen deze apps gebruikers om toestemming om toegang te krijgen tot de gegevens van uw organisatie en kunnen gebruikers kiezen of ze deze toestaan. Als u deze instelling uitschakelt, moeten beheerders toestemming geven voor deze apps voordat gebruikers ze kunnen gebruiken. Overweeg in dit geval een workflow voor beheerderstoestemming in te stellen in de Azure-portal, zodat gebruikers een verzoek om goedkeuring van beheerders kunnen verzenden om een geblokkeerde app te gebruiken.

Een gebruiker kan alleen toegang geven voor apps waarvan ze de eigenaar zijn en waarvoor toegang tot hun Office 365-gegevens is vereist. Ze kunnen apps geen toestemming geven voor het gebruik van gegevens van anderen.

## <a name="turning-user-consent-on-or-off"></a>Toestemming van de gebruiker in- of uitschakelen
<a name="__toc379982114"> </a>

Zo schakel je toestemming van gebruikers voor apps in of uit.

1. Ga in het beheercentrum naar de pagina **Instellingen** \> **voor**  >  [organisatieservices](https://go.microsoft.com/fwlink/p/?linkid=2053743) en selecteer **vervolgens Toestemming van gebruikers voor apps**.

2. Selecteer **op** de pagina Toestemming voor apps van gebruiker de optie om Geïntegreerde apps in of uit te schakelen.

## <a name="more-info"></a>Meer informatie
<a name="__toc379982114"> </a>

Lees de werkstroom voor [beheerderstoestemming configureren](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow)voor meer informatie over het configureren van uw toestemmingsinstellingen in Azure Active Directory.

Lees Toestemming voor toepassingen beheren [en het evalueren van toestemmingsverzoeken](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests)voor meer informatie over het beheren van toestemming voor apps.