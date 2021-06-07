---
title: Ga naar de beheerdersportal
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
description: De beheerportal zoeken en gebruiken, inclusief het beheren van de toegang tot de portal.
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 2facd506497cbdab42f2d8b051fbd50f82432927
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770599"
---
# <a name="access-the-admin-portal"></a>Toegang tot de beheerportal

Uw gateway naar de Microsoft Managed Desktop service is [Microsoft Endpoint Manager.](https://endpoint.microsoft.com/) Als u niet bekend bent met de mogelijkheden van deze portal voor apparaatbeheer, bekijkt u [de Microsoft Endpoint Manager documentatie.](/mem/)

> [!NOTE]
> In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) worden de volgende browsers ondersteund:
> - Microsoft Edge (nieuwste versie)
> - Safari (nieuwste versie, alleen Mac)
> - Chrome (nieuwste versie)
> - Firefox (nieuwste versie)

Uw beheeraccount heeft specifieke machtigingen nodig om toegang te krijgen tot de Microsoft Managed Desktop beheerfuncties in Microsoft Endpoint Manager. U kunt beheerderstoegang tot deze functies binnen uw organisatie beheren met behulp van toegangsbeheer op basis van rollen. Verschillende Azure Active Directory (Azure AD) beheerdersrollen en ingebouwde Microsoft Managed Desktop-rollen zijn beschikbaar om meer gedetailleerde controle te bieden voor verschillende functies binnen de Microsoft Managed Desktop Admin portal. Zie Beheerdersrolmachtigingen in Azure Active Directory rollen [in](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)Azure Active Directory. In tegenstelling tot Azure AD-beheerdersrollen die van toepassing zijn op verschillende Microsoft-producten en -services, zijn de ingebouwde rollen specifiek voor Microsoft Managed Desktop en garanderen ze alleen toegang tot de beheerdersfuncties voor deze service. Beheerders kunnen ingebouwde rollen individueel of in combinatie met Azure AD-beheerdersrollen toewijzen om Microsoft Managed Desktop machtigingen toe te voegen aan bestaande beheerdersaccounts.

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a>Azure Active Directory rollen met Microsoft Managed Desktop access

|Azure AD-rol  |Microsoft Managed Desktop machtigingen  |
|---------|---------|
|Globale beheerder     | Beheerders met deze rol hebben lees- en **schrijfmachtigingen** voor alle functies in de Microsoft Managed Desktop Admin portal.         |
|Algemene lezer     | Beheerders met deze rol hebben **alleen-lezen machtigingen** voor alle functies in de Microsoft Managed Desktop Admin portal.         |
|Intune-servicebeheerder     |  Beheerders met deze rol hebben lees- en schrijfmachtigingen voor functies die niet gerelateerd zijn aan **beveiliging** in de Microsoft Managed Desktop Admin portal.       |
|Serviceondersteuningsbeheerder     | Beheerders met deze rol hebben **alleen-lezen-machtigingen** voor functies die geen verband houden met beveiliging en schrijven machtigingen voor het beheren van **ondersteuningsaanvragen** in de Microsoft Managed Desktop Admin portal.         |
|Beveiligingsbeheerder | Beheerders met deze rol hebben **alleen-lezen** machtigingen voor alle functies en schrijven machtigingen voor beveiligingsgerelateerde functies **in** Microsoft Managed Desktop in de beheerportal. |
|Beveiligingslezer |Beheerders met deze rol hebben **alleen-lezen machtigingen** voor alle functies in de Microsoft Managed Desktop Admin portal.|

Als u hulp nodig hebt bij het toewijzen van Azure Active Directory rollen, zie [Beheerdersrolmachtigingen in Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

> [!IMPORTANT]
> Alleen de rol Globale beheerder heeft de benodigde machtigingen om *uw* organisatie in te schrijven in Microsoft Managed Desktop. Let op: Azure Active Directory functies geven gebruikersaccounts bevoegdheden op verschillende Microsoft-services. Nadat u zich hebt ingeschreven met Microsoft Managed Desktop, moet u altijd de rol gebruiken met de minste *bevoegdheden* die nodig zijn om uw andere taken uit te voeren.

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a>Ingebouwde rollen die worden geleverd door Microsoft Managed Desktop


|Ingebouwde rol  |Microsoft Managed Desktop machtigingen  |
|---------|---------|
|Microsoft Managed Desktop Servicebeheerder  | Wanneer deze rol aan een gebruiker is toegewezen, geeft deze rol de beheerder lees- en schrijfmachtigingen voor functies die niet gerelateerd zijn aan beveiliging **in** de Microsoft Managed Desktop Admin portal.  |
|Microsoft Managed Desktop Servicelezer | Wanneer deze rol aan een gebruiker is toegewezen, geeft deze rol de beheerder **alleen-lezen** machtigingen voor functies die niet gerelateerd zijn aan beveiliging in de Microsoft Managed Desktop Admin portal. |
|Microsoft Managed Desktop Beveiligingsbeheer |Wanneer deze rol aan een gebruiker is toegewezen, geeft deze beheerder alleen lees- en schrijfmachtigingen voor beveiligingsgerelateerde functies **in** de Microsoft Managed Desktop Admin portal.   |

> [!NOTE]
> Beveiligingsfuncties omvatten beveiligingsgerelateerde communicatie, beheer van beveiligingscontactcontacten, beheer van beveiligingsgerelateerde ondersteuningsaanvragen en toegang tot beveiligingsgerelateerde rapporten. 

### <a name="assigning-built-in-roles-to-user"></a>Ingebouwde rollen toewijzen aan gebruiker

Voor eenvoudig beheer van ingebouwde rollen is er een beveiligingsgroep voor elke aangepaste rol met de naam 'Moderne rollen op de werkplek _-_ rolnaam '(bijvoorbeeld 'Moderne werkplekrollen – Beveiligingsmanager'). Als u gebruikers wilt toewijzen aan een van deze beveiligingsgroepen, volgt u de volgende stappen:
1.  Ga naar de Microsoft Endpoint Manager portal.
2.  Selecteer **Groepen** aan de linkerkant.
3.  Zoek naar **Moderne werkplekrollen** en selecteer vervolgens de groep die is gekoppeld aan de rol die u wilt toewijzen. 
4.  Selecteer **Leden** aan de linkerkant en selecteer **vervolgens + Leden toevoegen** op de opdrachtbalk.
5.  Voer de e-mail in van de persoon die wordt toegevoegd. Als ze een gast zijn, moet u deze uitnodigen voordat u de groep kunt toewijzen.
6.  Selecteer **Selecteren** onderaan.

> [!NOTE]
> Het nesten van beveiligingsgroepen voor rollentoewijzing wordt momenteel niet ondersteund. 

### <a name="assigning-built-in-roles-to-groups"></a>Ingebouwde rollen toewijzen aan groepen

Als u een of meer van de ingebouwde rollen aan een bestaande groep wilt toewijzen, gaat u als volgt te werk:
1. Ga naar [portal.azure.com.](https://portal.azure.com/)
2. Enterprise-toepassingen **zoeken en openen.**
3. Wijzig het **filter toepassingstype** in _Microsoft Applications_ en selecteer **toepassen.**
4. Zoek naar en selecteer _Moderne api's voor klanten op de werkplek._
5. Selecteer **Gebruikers en groepen** in het deelvenster aan de linkerkant en selecteer vervolgens + **Gebruiker/groep toevoegen.**
6. Zoek naar de groep die u wilt gebruiken in **Gebruikers en groepen.**
7. Zoek naar de toepasselijke rol in **Selecteer een rol** en selecteer deze.
8. Selecteer **Toewijzen**.
