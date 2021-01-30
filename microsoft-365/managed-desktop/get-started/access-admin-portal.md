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
ms.openlocfilehash: c2a5b7f837d6c43369301820019732ca3aef83bf
ms.sourcegitcommit: ea8a096df5acedecdce1780969f2b189c3fadf73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2021
ms.locfileid: "50053845"
---
# <a name="access-the-admin-portal"></a>Toegang tot de beheerportal

Uw gateway voor de beheerde bureaubladservice van Microsoft is [Microsoft Endpoint Manager.](https://endpoint.microsoft.com/) Als u niet bekend bent met de mogelijkheden van deze portal voor apparaatbeheer, bekijkt u de documentatie [van Microsoft Endpoint Manager.](https://docs.microsoft.com/mem/)

> [!NOTE]
> In [Microsoft Endpoint Manager worden](https://endpoint.microsoft.com/) de volgende browsers ondersteund:
> - Microsoft Edge (nieuwste versie)
> - Microsoft Internet Explorer 11
> - Safari (nieuwste versie, alleen voor Mac)
> - Chrome (nieuwste versie)
> - Firefox (nieuwste versie)

Uw beheeraccount heeft specifieke machtigingen nodig om toegang te krijgen tot de beheerfuncties van Microsoft Managed Desktop in Azure Portal of Microsoft Endpoint Manager. U kunt de beheerderstoegang tot deze functies binnen uw organisatie beheren met toegangsbeheer op basis van rollen. Verschillende beheerdersrollen in Azure Active Directory (Azure AD) en ingebouwde aangepaste rollen zijn beschikbaar om meer gedetailleerde controle te bieden over de verschillende functies in de beheerportal van Microsoft Managed Desktop. Zie Beheerdersrolmachtigingen in Azure Active Directory voor meer informatie over rollen [in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) In tegenstelling tot rollen van Azure AD-beheerders die van toepassing zijn op verschillende Microsoft-producten en -services, zijn aangepaste rollen specifiek voor Het beheerde bureaublad van Microsoft en garanderen deze alleen toegang tot de beheerfuncties voor deze service. Beheerders kunnen aangepaste rollen aan gebruikers afzonderlijk of in combinatie met Azure AD-beheerdersrollen toewijzen om Machtigingen voor Beheerd bureaublad van Microsoft toe te voegen aan bestaande beheerdersaccounts.

Elk van de onderstaande rollen kan worden toegewezen om verschillende toegangsniveaus te bieden:

|Azure AD-rol  |Machtigingen voor Microsoft Beheerd bureaublad  |
|---------|---------|
|Globale beheerder     | Beheerders met deze rol hebben lees- en **schrijfmachtigingen voor alle functies** in de portal van Microsoft Beheerd bureaubladbeheerder.         |
|Algemene lezer     | Beheerders met deze rol hebben **alleen-lezenmachtigingen voor alle functies** in de portal beheerde bureaubladbeheerder van Microsoft.         |
|Intune-servicebeheerder     |  Beheerders met deze rol hebben lees- en **schrijfmachtigingen** voor functies die niet gerelateerd zijn aan beveiliging in de beheerportal van Microsoft Beheerd bureaublad.       |
|Serviceondersteuningsbeheerder     | Beheerders met deze rol hebben **alleen-lezenmachtigingen** voor functies die niet gerelateerd zijn aan beveiliging en schrijfmachtigingen voor het beheren van **ondersteuningsaanvragen** in de portal voor beheerde bureaubladbeheerder van Microsoft.         |
|Beveiligingsbeheerder | Beheerders met deze rol hebben **alleen-lezenmachtigingen** voor alle functies en schrijfmachtigingen voor beveiligingsgerelateerde functies **in** het beheerde bureaublad van Microsoft in de beheerportal. |
|Beveiligingslezer |Beheerders met deze rol hebben **alleen-lezenmachtigingen voor alle functies** in de portal beheerde bureaubladbeheerder van Microsoft.|

> [!IMPORTANT]
> Alleen de rol globale beheerder heeft de benodigde machtigingen voor het *registreren* van uw organisatie bij Het beheerde bureaublad van Microsoft. Let op: met rollen in Azure Active Directory worden gebruikersaccountbevoegdheden verleend voor diverse Microsoft-services. Nadat u de inschrijving met Microsoft Managed Desktop hebt voltooid, moet u altijd de rol gebruiken met de minste *bevoegdheden* die nodig zijn om uw andere taken uit te voeren.

 
|Aangepaste rol  |Machtigingen voor Microsoft Beheerd bureaublad  |
|---------|---------|
|Beheerde Microsoft Desktop Service-beheerder  | Wanneer deze rol aan een gebruiker is toegewezen, geeft deze rol de beheerder lees- en schrijfmachtigingen voor functies die niet gerelateerd zijn aan beveiliging **in** de beheerportal van Microsoft Managed Desktop.  |
|Microsoft Managed Desktop Service Reader | Wanneer deze rol aan een gebruiker  is toegewezen, geeft deze rol de beheerder alleen-lezenmachtigingen voor functies die niet gerelateerd zijn aan beveiliging in de portal van Microsoft Beheerd bureaublad-beheer. |
|Microsoft Managed Desktop Security Manager |Wanneer deze rol aan een gebruiker is toegewezen, geeft deze rol alleen lees- en schrijfmachtigingen voor beveiligingsfuncties **in** de portal beheerde bureaubladbeheerder van Microsoft.   |

> [!NOTE]
> Beveiligingsfuncties zijn onder andere communicatie op het gebied van beveiliging, beheer van beveiligingscontacten, beheer van beveiligingsgerelateerde ondersteuningsaanvragen en toegang tot beveiligingsrapporten. 

## <a name="assigning-roles-to-administrators"></a>Rollen toewijzen aan beheerders

Zie Beheerdersrolmachtigingen in Azure Active Directory als u hulp nodig hebt bij het toewijzen van [Azure Active Directory-rollen.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

Om het eenvoudig te maken om ingebouwde rollen te beheren, is er een beveiligingsgroep voor elke aangepaste rol (bijvoorbeeld 'Modern Workplace Roles – Security Manager'). Als u gebruikers wilt toewijzen aan een van de beveiligingsgroepen, gaat u als volgt te werk:
1.  Ga naar de portal van Microsoft Endpoint Manager.
2.  Selecteer **Groepen** aan de linkerkant.
3.  Zoek naar **Moderne werkplekrollen** en selecteer vervolgens de groep die is gekoppeld aan de rol die u wilt toewijzen. 
4.  Selecteer **Leden** aan de linkerkant en selecteer vervolgens **+ Leden toevoegen** op de opdrachtbalk.
5.  Voer het e-mailadres in van de persoon die wordt toegevoegd. Als hij of zij gast is, moet u hem of haar uitnodigen voordat u de groep kunt toewijzen.
6.  Selecteer **Onderaan** Selecteren.

> [!NOTE]
> Het nesten van beveiligingsgroepen voor roltoewijzing wordt momenteel niet ondersteund. 
