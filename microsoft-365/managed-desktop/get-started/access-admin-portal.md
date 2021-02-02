---
title: Ga naar de beheerdersportal
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
description: Hoe u de beheerportal kunt vinden en gebruiken, inclusief het beheren van de toegang tot de portal.
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 5b7ba0db52f06f7b3f6fce596015b56c8e46c6c2
ms.sourcegitcommit: 2c4c7ebe9bea52765ece0ed27d3ea77313711b10
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/01/2021
ms.locfileid: "50068951"
---
# <a name="access-the-admin-portal"></a>Toegang tot de beheerportal

Uw gateway voor de beheerde bureaubladservice van Microsoft is [Microsoft Endpoint Manager.](https://endpoint.microsoft.com/) Als u niet bekend bent met de mogelijkheden van deze portal voor apparaatbeheer, kunt u de documentatie [van Microsoft Endpoint Manager lezen.](https://docs.microsoft.com/mem/)

> [!NOTE]
> In [Microsoft Endpoint Manager worden](https://endpoint.microsoft.com/) de volgende browsers ondersteund:
> - Microsoft Edge (nieuwste versie)
> - Microsoft Internet Explorer 11
> - Safari (nieuwste versie, alleen voor Mac)
> - Chrome (nieuwste versie)
> - Firefox (nieuwste versie)

Uw beheeraccount heeft specifieke machtigingen nodig om toegang te krijgen tot de beheerfuncties van Microsoft Managed Desktop in Microsoft Endpoint Manager. U kunt de beheerderstoegang tot deze functies binnen uw organisatie beheren met toegangsbeheer op basis van rollen. Verschillende beheerdersrollen in Azure Active Directory (Azure AD) en ingebouwde microsoft Managed Desktop-rollen zijn beschikbaar voor gedetailleerdere controle over de verschillende functies in de beheerportal van Microsoft Managed Desktop. Zie Beheerdersrolmachtigingen in Azure Active Directory voor meer informatie over rollen [in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) In tegenstelling tot rollen van Azure AD-beheerders die van toepassing zijn op verschillende Microsoft-producten en -services, zijn de ingebouwde rollen specifiek voor het beheerde bureaublad van Microsoft en garanderen ze alleen toegang tot de beheerfuncties voor deze service. Beheerders kunnen ingebouwde rollen toewijzen aan gebruikers afzonderlijk of in combinatie met beheerdersrollen in Azure AD om Machtigingen voor beheerd bureaublad toe te voegen aan bestaande beheerdersaccounts.

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a>Azure Active Directory-rollen met Microsoft Managed Desktop Access

|Azure AD-rol  |Machtigingen voor Microsoft Beheerd bureaublad  |
|---------|---------|
|Globale beheerder     | Beheerders met deze rol hebben lees- en **schrijfmachtigingen voor alle functies** in de portal beheerde bureaubladbeheerder van Microsoft.         |
|Algemene lezer     | Beheerders met deze rol hebben **alleen-lezenmachtigingen voor alle functies** in de portal beheerde bureaubladbeheerder van Microsoft.         |
|Intune-servicebeheerder     |  Beheerders met deze rol hebben lees- en **schrijfmachtigingen** voor functies die niet gerelateerd zijn aan beveiliging in de beheerportal van Microsoft Beheerd bureaublad.       |
|Beheerder serviceondersteuning     | Beheerders met deze rol hebben **alleen-lezenmachtigingen** voor functies die niet gerelateerd zijn aan beveiliging en schrijfmachtigingen voor het beheren van **ondersteuningsaanvragen** in de portal voor beheerde bureaubladbeheerder van Microsoft.         |
|Beveiligingsbeheerder | Beheerders met deze rol hebben **alleen-lezenmachtigingen** voor alle functies en schrijfmachtigingen voor beveiligingsgerelateerde functies **in** het beheerde bureaublad van Microsoft in de beheerportal. |
|Beveiligingslezer |Beheerders met deze rol hebben **alleen-lezenmachtigingen voor alle functies** in de portal beheerde bureaubladbeheerder van Microsoft.|

Zie Beheerdersrolmachtigingen in Azure Active Directory als u hulp nodig hebt bij het toewijzen van [Azure Active Directory-rollen.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

> [!IMPORTANT]
> Alleen de rol globale beheerder heeft de benodigde machtigingen voor het *registreren* van uw organisatie in Het beheerde bureaublad van Microsoft. Let op: met rollen in Azure Active Directory worden gebruikersaccountbevoegdheden verleend voor diverse Microsoft-services. Nadat u zich hebt ingeschreven met Microsoft Managed Desktop, moet u altijd de rol gebruiken met de minste *bevoegdheden* die nodig zijn om uw andere taken uit te voeren.

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a>Ingebouwde rollen geleverd door Het beheerde bureaublad van Microsoft


|Ingebouwde rol  |Machtigingen voor Microsoft Beheerd bureaublad  |
|---------|---------|
|Beheerde Microsoft Desktop Service-beheerder  | Wanneer deze rol aan een gebruiker is toegewezen, geeft deze rol de beheerder lees- en schrijfmachtigingen voor functies die niet gerelateerd zijn aan beveiliging **in** de beheerportal van Microsoft Managed Desktop.  |
|Microsoft Managed Desktop Service Reader | Wanneer deze rol aan een gebruiker  is toegewezen, geeft deze rol de beheerder alleen-lezenmachtigingen voor functies die niet gerelateerd zijn aan beveiliging in de beheerportal van Microsoft Managed Desktop. |
|Microsoft Managed Desktop Security Manager |Wanneer deze rol aan een gebruiker is toegewezen, geeft deze rol alleen lees- en schrijfmachtigingen voor beveiligingsfuncties **in** de portal beheerde bureaubladbeheerder van Microsoft.   |

> [!NOTE]
> Beveiligingsfuncties zijn onder andere communicatie op het gebied van beveiliging, beheer van beveiligingscontacten, beheer van beveiligingsgerelateerde ondersteuningsaanvragen en toegang tot beveiligingsrapporten. 

### <a name="assigning-built-in-roles-to-administrators"></a>Ingebouwde rollen toewijzen aan beheerders

Voor het beheren van ingebouwde rollen is er een beveiligingsgroep voor elke aangepaste rol met de naam 'Modern Workplace Roles - _Role_ Name ' (bijvoorbeeld 'Modern Workplace Roles – Security Manager'). Als u gebruikers wilt toewijzen aan een van deze beveiligingsgroepen, gaat u als volgt te werk:
1.  Ga naar de portal van Microsoft Endpoint Manager.
2.  Selecteer **Groepen** aan de linkerkant.
3.  Zoek naar **Moderne werkplekrollen** en selecteer vervolgens de groep die is gekoppeld aan de rol die u wilt toewijzen. 
4.  Selecteer **Leden** aan de linkerkant en selecteer vervolgens **+ Leden toevoegen** op de opdrachtbalk.
5.  Voer het e-mailadres in van de persoon die wordt toegevoegd. Als hij of zij een gast is, moet u hem of haar uitnodigen voordat u de groep kunt toewijzen.
6.  Selecteer **Onderaan** Selecteren.

> [!NOTE]
> Het nesten van beveiligingsgroepen voor roltoewijzing wordt momenteel niet ondersteund. 
