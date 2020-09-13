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
ms.openlocfilehash: 2ac0bb01c1a941d460e92c7e75e765ceb85b2bc0
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546572"
---
# <a name="access-the-admin-portal"></a>Toegang tot de beheerportal

De gateway naar de Microsoft beheerde bureaublad service is de Microsoft [Azure-Portal](https://portal.azure.com). Zie de [documentatie van Azure Portal](https://docs.microsoft.com/azure/azure-portal/)voor meer informatie over het gebruiken en aanpassen van uw Azure Portal-ervaring. Nu beschikbaar in het voorbeeld kunt u Microsoft Managed Desktop ook vinden in [Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Als u niet bekend bent met de mogelijkheden van deze portal voor Apparaatbeheer, raadpleegt u de [documentatie Microsoft Endpoint Manager](https://docs.microsoft.com/mem/).

Voor het beheren van de Microsoft beheerde bureaubladfuncties voor de beheerfuncties van Azure portal of Microsoft-eindpunten hebt u specifieke machtigingen nodig. U kunt beheerderstoegang tot deze functies binnen uw organisatie beheren via toegangsbeheer op basis van rollen (RBAC). Er zijn verschillende Azure AD-beheerdersrollen en ingebouwde aangepaste rollen beschikbaar voor een uitgebreidere controle over verschillende functies in de portal van de beheerde bureaublad beheerder. Zie [machtigingen voor beheerdersrollen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)voor meer informatie over de functies van Azure Active Directory. In tegenstelling tot de beheerdersrollen die van toepassing zijn op diverse Microsoft-producten en-services, zijn aangepaste rollen specifiek voor Microsoft Managed Desktop en garanderen ze alleen toegang tot de beheerfuncties voor deze service. Beheerders kunnen aangepaste rollen aan gebruikers afzonderlijk of in combinatie met beheerdersrollen toewijzen om Microsoft beheerde bureaublad machtigingen toe te voegen aan bestaande beheerdersaccounts.

Met de onderstaande rollen kunnen verschillende toegangsniveaus worden toegewezen:

|Functie Azure AD  |Beheerde Microsoft-bureaublad machtigingen  |
|---------|---------|
|Globale beheerder     | Beheerders die met deze rol werken, hebben **Lees-en schrijfmachtigingen** voor alle functies in de portal van Microsoft beheerde bureaubladbeheer.         |
|Algemene lezer     | Beheerders met deze rol hebben **alleen-lezen machtigingen** voor alle functies in de Microsoft beheerde portal van de bureaublad beheerder.         |
|InTune-service beheerder     |  Beheerders die met deze rol werken, hebben **Lees-en schrijfmachtigingen** voor alle functies in de portal van Microsoft beheerde bureaubladbeheer. **Wijziging:** De basis beheerders van september 2020 hebben geen toegang tot beveiligingsfuncties die door Microsoft worden beheerd op het bureaublad.       |
|Service ondersteuningsbeheerder     | Beheerders die met deze rol werken, hebben **Lees-en schrijfmachtigingen** voor alle functies in de portal van Microsoft beheerde bureaubladbeheer. **Wijziging:** De basis beheerders van september 2020 hebben geen toegang tot beveiligingsfuncties die door Microsoft worden beheerd op het bureaublad.         |
|Beveiligingsbeheerder | **(In Preview September 2020)** Beheerders met deze rol hebben alleen-lezen machtigingen voor alle functies en schrijfmachtigingen voor gerelateerde functies in Microsoft Managed desktop in de beheerportal. |
|Beveiligings lezer | **(In Preview September 2020)**  Beheerders met deze rol hebben alleen-lezen machtigingen voor alle functies in de Microsoft beheerde portal van de bureaublad beheerder.|

> [!IMPORTANT]
> Alleen de rol van globale beheerder heeft de juiste machtigingen voor het *registreren* van uw organisatie in Microsoft Managed Desktop. Azure Active Directory-rollen bieden gebruikersaccounts bevoegdheden in diverse Microsoft-services. Wanneer u de registratie hebt voltooid met Microsoft Managed Desktop, dient u altijd de rol te gebruiken met de *minste* bevoegdheden die nodig zijn om uw andere taken uit te voeren.

 
|Aangepaste rol  |Beheerde Microsoft-bureaublad machtigingen  |
|---------|---------|
|Microsoft beheerde bureaublad service beheerder  | **(In Preview September 2020)** Wanneer een gebruiker aan een gebruiker is toegewezen, biedt deze rol de beheerder **lees & schrijfmachtigingen voor functies die niet gerelateerd zijn aan beveiliging** in de Microsoft Managed Desktop-beheerportal.  |
|Microsoft beheerde bureaublad service lezer | **(In Preview September 2020)** Wanneer de gebruiker aan een gebruiker is toegewezen, biedt deze rol de beheerder de **machtiging alleen-lezen voor functies die niet gerelateerd zijn aan de beveiliging** van de beheerde portal van de Microsoft-bureaublad beheerder. |
|Microsoft beheerde bureaublad beveiligingsbeheer | **(In Preview September 2020)** Wanneer de gebruiker aan een gebruiker is toegewezen, biedt deze rol de beheerder **alleen & schrijfmachtigingen voor de beveiligingsfuncties** van de Microsoft beheerde bureaubladbeheer Portal.   |

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
