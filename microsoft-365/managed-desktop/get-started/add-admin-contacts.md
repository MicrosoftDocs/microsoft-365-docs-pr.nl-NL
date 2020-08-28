---
title: Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal
description: Vertel ons wie u contact moet opnemen voor elk gebied van de focus.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8b287200b1c94ff350f7ba00cf0c4e6bc1b4a71f
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289259"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal

U kunt op verschillende manieren communiceren met klanten via Microsoft beheerde bureaublad service. Voor het stroomlijnen van de communicatie en zorg ervoor dat u de juiste personen controleert, moet u een reeks beheerders contacten opgeven. DOOR Microsoft beheerde bureaublad activiteiten wordt contact opgenomen met deze personen voor hulp bij het oplossen van problemen met de Tenant.

> [!IMPORTANT]
> U hebt deze contactpersonen al toegevoegd aan de beheerportal. Als dit het geval is, kunt u nu even kijken of de lijst met contactpersonen nauwkeurig is, omdat Microsoft Managed Desktop de verbinding **moet** kunnen bereiken als er een ernstig incident plaatsvindt.

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Azure Active Directory Access voor de beheerde portal voor Microsoft-bureaubladbeheer

De portal van de beheerde bureaublad beheerder van Microsoft wordt vereist dat personen die toegang hebben tot de portal een van deze Azure Active Directory (AD) rollen hebben.
- Globale beheerder
- InTune-service beheerder
- Algemene lezer
- Service ondersteuningsbeheerder

De hoofdbeheerder moet de naam van de globale beheerder zijn om uw organisatie in te schrijven op Microsoft Managed Desktop. Alle vijf rollen hebben dezelfde toegang binnen de beheerportal om taken te initiëren en weer te geven. Zie [machtigingen voor beheerdersrollen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)voor meer informatie over het toewijzen van deze rollen in azure AD. 

## <a name="admin-contact-areas-of-focus"></a>Beheerders bereiken van focus

Contactpersonen beheerder moeten de beste persoon of groep zijn die vragen kan beantwoorden en besluiten te nemen voor verschillende gebieden van de focus. **Door Microsoft beheerde bureaublad activiteiten wordt contact opgenomen met deze beheerders contactpersonen voor vragen met ondersteuningsverzoeken die door de klant zijn ingediend.** Deze beheerders contactpersonen ontvangen een melding voor updates van ondersteuningsaanvragen en nieuwe berichten. Dit gebied omvat:

Gebied met focus | Voor vragen over
--- | ---
App-verpakking | App-verpakking oplossen
Apparaten | Apparaatstatusverklaring, probleemoplossing met door Microsoft beheerde bureaublad apparaten
Beveiliging | Beveiligingsproblemen met door Microsoft beheerde bureaublad apparaten oplossen
IT-helpdesk | Wanneer onze ondersteuningsmedewerkers de afdeling ondersteunings gebieden van gebruikers buiten Microsoft beheerde bureaublad ondersteuning bevinden 
Overige | Voor problemen die niet worden bedekt door andere gebieden

**Degene die u voor deze contactpersonen kiest, moet de kennis en bevoegdheid hebben om beslissingen te kunnen nemen voor de Microsoft-beheerde bureaubladomgeving.** Wanneer u de beheerde bureaubladomgeving van Microsoft ophaalt, wordt u gevraagd contactpersonen voor uw lokale helpdesk en beveiliging toe te voegen. 

Beheerders contactpersonen zijn vereist wanneer u [een ondersteuningsaanvraag indient](../service-description/support.md). U moet een beheerders contact hebben voor het focus gebied van het ondersteuningsverzoek. 

**Beheerders contactpersonen toevoegen**

1.  Meld u aan bij de [Portal van Microsoft beheerde bureaubladbeheer](https://aka.ms/mwaasportal). 

2.  Selecteer onder **ondersteuning**de optie **beheerder contactpersonen**. 

    ![Ondersteunings menu, contactpersonen van beheerder, bijna bovenaan geselecteerd](../../media/admincontacts.png)

3. Kies **Toevoegen**.

    ![Beheerportal, knop toevoegen links van exporteren en vernieuwen](../../media/adminadd.png)

4.  Selecteer een **gebied met de focus** en voer de gegevens voor de contactpersoon in. 

    ![de lijst met de focus gebieden, zoals andere, apps en beveiliging](../../media/areaoffocus.png)

5. Herhaal dit voor elk gebied van de focus. 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Stappen om aan de slag te gaan met Microsoft Managed Desktop

1. Beheerders contactpersonen toevoegen en controleren in de beheerportal (dit onderwerp)
2. [Voorwaardelijke toegang aanpassen](conditional-access.md)
3. [Licenties toewijzen](assign-licenses.md)
4. [InTune-bedrijfsportal installeren op apparaten](company-portal.md)
5. [Enterprise State Roaming inschakelen](enterprise-state-roaming.md)
6. [Microsoft Managed Desktop-apparaten instellen](set-up-devices.md)
7. [Uw gebruikers voorbereiden om apparaten te gebruiken](get-started-devices.md)
8. [Apps implementeren op apparaten](deploy-apps.md)
