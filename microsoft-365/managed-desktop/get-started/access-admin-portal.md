---
title: Ga naar de beheerdersportal
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 5adf57c2397c4de3c5ea8622a2a9be7207ebf152
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379300"
---
# <a name="access-the-admin-portal"></a>Toegang tot de beheerportal

De gateway naar de Microsoft beheerde bureaublad service is de Microsoft [Azure-Portal](https://portal.azure.com). Zie de [documentatie van Azure Portal](https://docs.microsoft.com/azure/azure-portal/)voor meer informatie over het gebruiken en aanpassen van uw Azure Portal-ervaring. Nu beschikbaar in het voorbeeld kunt u Microsoft Managed Desktop ook vinden in [Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Als u niet bekend bent met de mogelijkheden van deze portal voor Apparaatbeheer, raadpleegt u de [documentatie Microsoft Endpoint Manager](https://docs.microsoft.com/mem/).

> [!NOTE]
> Als u echter kiest voor het openen van Microsoft Managed Desktop, in [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) of de [Azure-Portal](https://portal.azure.com), worden de volgende browsers ondersteund:
> - Microsoft Edge (nieuwste versie)
> - Microsoft Internet Explorer 11
> - Safari (nieuwste versie, alleen Mac)
> - Chrome (nieuwste versie)
> - Firefox (nieuwste versie)

Voor het beheren van de Microsoft beheerde bureaubladfuncties voor de beheerfuncties van Azure portal of Microsoft-eindpunten hebt u specifieke machtigingen nodig. U kunt beheerderstoegang tot deze functies binnen uw organisatie beheren via toegangsbeheer op basis van rollen (RBAC). U kunt verschillende Azure Active Directory (Azure AD)-beheerdersrollen en ingebouwde aangepaste rollen maken om meer controle over te geven aan verschillende functies in de portal van Microsoft Managed Desktop admin. Zie [machtigingen voor beheerdersrollen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)voor meer informatie over de functies van Azure Active Directory. In tegenstelling tot Azure AD-beheerdersrollen die van toepassing zijn op diverse Microsoft-producten en-services, zijn aangepaste rollen specifiek voor Microsoft Managed Desktop en garanderen ze alleen toegang tot de beheerfuncties voor deze service. Beheerders kunnen aangepaste rollen toewijzen aan gebruikers afzonderlijk of in combinatie met Azure AD-beheerdersrollen om Microsoft Managed Desktop-machtigingen toe te voegen aan bestaande beheerdersaccounts.

Met de onderstaande rollen kunnen verschillende toegangsniveaus worden toegewezen:

|Functie Azure AD  |Beheerde Microsoft-bureaublad machtigingen  |
|---------|---------|
|Globale beheerder     | Beheerders die met deze rol werken, hebben **Lees-en schrijfmachtigingen voor alle functies** in de portal van Microsoft beheerde bureaubladbeheer.         |
|Algemene lezer     | Beheerders met deze rol hebben **alleen-lezen machtigingen voor alle functies** in de Microsoft beheerde portal van de bureaublad beheerder.         |
|InTune-service beheerder     |  Beheerders die met deze rol werken, hebben **Lees-en schrijfmachtigingen voor functies die niet gerelateerd zijn aan beveiliging** in de Microsoft beheerde portal van de bureaublad beheerder.       |
|Service ondersteuningsbeheerder     | Beheerders die met deze rol werken, hebben **Lees-en schrijfmachtigingen voor functies die niet gerelateerd zijn aan beveiliging** in de Microsoft beheerde portal van de bureaublad beheerder.         |
|Beveiligingsbeheerder | Beheerders met deze rol hebben **alleen-lezen machtigingen voor alle functies** en **schrijfmachtigingen voor gerelateerde functies** in Microsoft Managed desktop in de beheerportal. |
|Beveiligings lezer |Beheerders met deze rol hebben **alleen-lezen machtigingen voor alle functies** in de Microsoft beheerde portal van de bureaublad beheerder.|

> [!IMPORTANT]
> Alleen de rol van globale beheerder heeft de juiste machtigingen voor het *registreren* van uw organisatie in Microsoft Managed Desktop. Azure Active Directory-rollen bieden gebruikersaccounts bevoegdheden in diverse Microsoft-services. Wanneer u de registratie hebt voltooid met Microsoft Managed Desktop, dient u altijd de rol te gebruiken met de *minste* bevoegdheden die nodig zijn om uw andere taken uit te voeren.

 
|Aangepaste rol  |Beheerde Microsoft-bureaublad machtigingen  |
|---------|---------|
|Microsoft beheerde bureaublad service beheerder  | Wanneer deze rol aan een gebruiker is toegewezen, biedt deze rol de beheerder **Lees-en schrijfmachtigingen voor functies die niet gerelateerd zijn aan beveiliging** in de Microsoft beheerde bureaubladbeheer Portal.  |
|Microsoft beheerde bureaublad service lezer | Wanneer deze rol aan een gebruiker is toegewezen, biedt deze rol de **alleen-lezen machtigingen van de beheerder tot functies die niet gerelateerd zijn aan beveiliging** van de beheerde portal van de Microsoft-bureaublad beheerder. |
|Microsoft beheerde bureaublad beveiligingsbeheer |Wanneer deze functie aan een gebruiker is toegewezen, biedt deze rol de beheerder **Lees-en schrijfmachtigingen alleen voor beveiligingsfuncties** in de Microsoft beheerde bureaubladbeheer Portal.   |

> [!NOTE]
> De beveiligingsfuncties omvatten beveiligingskwesties, beheer van beveiligings contactpersonen, het beheer van beveiligingsaanvragen voor de beveiliging, en toegang tot gerelateerde rapporten. 

## <a name="assigning-roles-to-administrators"></a>Rollen toewijzen aan beheerders

Als u hulp nodig hebt bij het toewijzen van Azure Active Directory-rollen, raadpleegt u [machtigingen voor beheerdersrollen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

Voor een eenvoudig beheer van de ingebouwde rollen is een beveiligingsgroep gemaakt voor elke aangepaste rol (bijvoorbeeld ' rollen van modern Workplace-Security Manager '). Voer de volgende stappen uit als u gebruikers wilt toewijzen aan een van de beveiligingsgroepen:
1.  Ga naar de Azure-Portal en ga naar de Azure Active Directory-Blade.
2.  Selecteer groepen aan de linkerkant.
3.  Zoek naar rollen voor moderne werkplekken en selecteer de groep die is gekoppeld aan de rol die u wilt toewijzen. 
4.  Selecteer leden aan de linkerkant en selecteer vervolgens + leden toevoegen op de opdrachtbalk.
5.  Voer het e-mailadres in van de persoon die wordt toegevoegd. Als ze een externe gebruiker zijn, moet u deze uitnodigen voordat u de groep kunt toewijzen.
6.  Selecteer onderaan selecteren.

> [!NOTE]
> Het nesten van beveiligingsgroepen voor roltoewijzing wordt momenteel niet ondersteund. 
