---
title: Eenvoudige mobiliteit en beveiliging uitschakelen
f1.keywords: NOCSH
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Verwijder groepen of beleidsregels om basis mobiliteit en beveiliging uit te schakelen.
ms.openlocfilehash: 54f78cc30e5259ad5244ce3a8fc6d0f46a395d7c
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336810"
---
# <a name="turn-off-basic-mobility-and-security"></a>Eenvoudige mobiliteit en beveiliging uitschakelen

Als u eenvoudige mobiliteit en beveiliging effectief wilt uitschakelen, verwijdert u groepen personen die zijn gedefinieerd door beveiligingsgroepen uit het beleid voor Apparaatbeheer of verwijdert u de beleidsregels zelf.

- Verwijder groepen gebruikers door gebruikersbeveiligingsgroepen te verwijderen uit de beleidsregels die u hebt gemaakt.
    
- Schakel eenvoudige mobiliteit en beveiliging voor iedereen uit door alle basis beleidsregels voor mobiliteit en beveiliging van beveiligingsapparaten te verwijderen.
    
Met deze opties verwijdert u de basis mobiliteit en beveiligings naleving voor apparaten in uw organisatie. Helaas kunt u de basis mobiliteit en beveiliging van basis van de burger en beveiliging van uw site helaas niet eenvoudig opzeggen. 

>[!IMPORTANT]
>Let op de gevolgen voor de apparaten van gebruikers wanneer u gebruikersbeveiligingsgroepen verwijdert uit beleidsregels of de beleidsregels zelf verwijdert. U kunt bijvoorbeeld e-mail profielen en e-mailberichten in de cache verwijderen, afhankelijk van het apparaat. Zie  [Wat gebeurt er wanneer u een beleid verwijdert of een gebruiker uit het beleid verwijdert?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact) voor meer informatie.

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Beveiligingsgroepen van een gebruiker verwijderen uit de basis beleidsregels voor mobiliteit en beveiliging van apparaten

1. In uw browsertype:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selecteer een apparaatbeleid en selecteer **beleid bewerken**. 

3. Selecteer op de pagina  **implementatie** de   optie **verwijderen**.
    
4. Selecteer onder  **groepen**een beveiligingsgroep.

5. Selecteer  **verwijderen**en selecteer **Opslaan**.
    

## <a name="remove-basic-mobility-and-security-device-policies"></a>Basisbeleid voor mobiliteit en beveiliging van apparaten verwijderen

1.  In uw browsertype:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) . 

2.  Selecteer een apparaatbeleid en selecteer vervolgens  **beleid verwijderen**.
    
3.  Selecteer in het waarschuwingsvenster de optie **Ja**.

>[!NOTE] 
>Zie voor meer informatie over het deblokkeren van apparaten als uw organisatie vasthoudt, het blogbericht over het [verwijderen van toegangsbeheer van mobiele apparaten voor Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).