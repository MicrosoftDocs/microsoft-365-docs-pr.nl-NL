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
description: Meer informatie over toestemming van gebruikers voor apps en hoe u deze in kunt stellen om apps van derden toegang te geven tot microsoft 365-informatie van gebruikers.
ms.openlocfilehash: 1f6f08161d6dd85964f07ec4d48f9f2cc23a1ead
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914556"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Gebruikers toestemming voor apps beheren in Microsoft 365

Met deze instelling bepaalt u of gebruikers die toestemming kunnen geven voor apps die OpenID Connect en OAuth 2.0 gebruiken voor aanmelding en verzoeken om toegang tot gegevens. Een app kan worden gemaakt vanuit uw eigen organisatie, of deze kan afkomstig zijn van een andere Office 365-organisatie of een externe organisatie.

Als u deze instelling int, vragen deze apps gebruikers om toestemming voor toegang tot de gegevens van uw organisatie en kunnen gebruikers kiezen of ze deze mogen toestaan. Als u deze instelling uit schakelen, moeten beheerders toestemming geven voor deze apps voordat gebruikers deze kunnen gebruiken. In dit geval kunt u overwegen een toestemmingswerkstroom voor beheerders in te stellen in de Azure-portal, zodat gebruikers een aanvraag voor goedkeuring van beheerders kunnen verzenden om een geblokkeerde app te gebruiken.

Een gebruiker kan alleen toegang geven voor apps waarvan ze de eigenaar zijn en waarvoor toegang tot hun Office 365-gegevens is vereist. Ze kunnen apps geen toestemming geven voor het gebruik van gegevens van anderen.

## <a name="turning-user-consent-on-or-off"></a>Toestemming van gebruikers in- of uitschakelen
<a name="__toc379982114"> </a>

U kunt als eerste de toestemming van gebruikers voor apps in- of uitschakelen.

1. Ga in het beheercentrum naar de pagina **Instellingen** \> **organisatie-instellingen**  >  [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) en selecteer **vervolgens Gebruikers toestemming voor apps.**

2. Selecteer op **de pagina Gebruikers toestemming voor apps** de optie om toestemming van gebruikers in of uit te schakelen.

## <a name="more-info"></a>Meer informatie
<a name="__toc379982114"> </a>

Lees De toestemmingswerkstroom voor beheerders [configureren](/azure/active-directory/manage-apps/configure-admin-consent-workflow)voor meer informatie over het configureren van uw toestemmingsinstellingen in Azure Active Directory.

Lees Toestemming voor toepassingen beheren en toestemmingsaanvragen evalueren voor meer informatie over het beheren van toestemming van gebruikers [voor](/azure/active-directory/manage-apps/manage-consent-requests)apps.