---
title: Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal
description: Vertel ons met wie we contact moeten opnemen voor elk aandachtsgebied.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8a5775d90f592aa5f64dd5f379fb37278032d87
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529801"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal

Er zijn verschillende manieren waarop microsoft Managed Desktop-service met klanten communiceert. Om de communicatie te stroomlijnen en ervoor te zorgen dat we contact opnemen met de juiste mensen, moet u een set beheerderscontacten bieden. Microsoft Managed Desktop IT Operations neemt contact op met deze personen voor problemen met het oplossen van problemen met uw tenant.

> [!IMPORTANT]
> Mogelijk hebt u deze contactpersonen al toegevoegd in de portal Beheerder. Als dat het geval is, moet u nu even de tijd nemen om te controleren of de lijst met contactpersonen juist is, omdat Microsoft Managed Desktop deze **moet** kunnen bereiken als zich een ernstig incident voordoet.

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Azure Active Directory-toegang voor microsoft Managed Desktop Admin-portal

Microsoft Managed Desktop Admin-portal vereist dat mensen die toegang hebben tot de portal een van deze Azure Active Directory (AD)-rollen hebben:
- Globale beheerder
- Intune-servicebeheerder
- Global Reader
- Beheerder van serviceondersteuning

De globale beheerder moet degene zijn die uw organisatie moet inschrijven in Microsoft Managed Desktop. Alle vijf rollen hebben dezelfde toegang binnen de portal voor beheerders om taken te initiëren en weer te geven. Zie [Machtigingen administratorrol in Azure Active Directory voor](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)meer informatie over het toewijzen van deze rollen in Azure AD. 

## <a name="admin-contact-areas-of-focus"></a>Aandachtsgebieden voor contactpersonen voor beheerders

Admin contacten moeten de beste persoon of groep die vragen kan beantwoorden en beslissingen te nemen voor verschillende gebieden van focus. **Microsoft Managed Desktop Operations neemt contact op met deze beheerderscontactpersonen voor vragen over ondersteuningsverzoeken die door de klant zijn ingediend.** Deze beheerderscontactpersonen ontvangen meldingen voor updates voor ondersteuningsverzoeken en nieuwe berichten. Deze gebieden omvatten:

Aandachtsgebied | Voor vragen over
--- | ---
App-verpakking | Problemen met app-verpakking oplossen
Apparaten | Apparaatstatus, probleemoplossing met Microsoft Managed Desktop-apparaten
Beveiliging | Problemen met beveiliging oplossen met Microsoft Managed Desktop-apparaten
IT-helpdesk | in gevallen waarin ons ondersteuningspersoneel tickets voor eindgebruikers overhandigt buiten microsoft Managed Desktop-ondersteuningsgebieden 
Overige | Voor kwesties die niet onder andere gebieden vallen

**Wie u ook kiest voor deze contactpersonen, moet de kennis en autoriteit hebben om beslissingen te nemen voor uw Microsoft Managed Desktop-omgeving.** Wanneer u aan boord bent van uw Microsoft Managed Desktop-omgeving, wordt u gevraagd contactpersonen toe te voegen voor uw lokale helpdesk en beveiliging. 

Beheerderscontacten zijn vereist wanneer u [een ondersteuningsverzoek indient.](../service-description/support.md) U moet een beheerderscontact hebben voor het focusgebied van het ondersteuningsverzoek. 

**Beheerderscontactpersonen toevoegen**

1.  Meld u aan bij [microsoft Managed Desktop-beheerportal](https://aka.ms/mwaasportal). 

2.  Selecteer onder **Ondersteuning**de optie **Beheerderscontactpersonen**. 

    ![Ondersteuningsmenu, Beheerderscontacten in de buurt van de bovenbovenhoek geselecteerd](../../media/admincontacts.png)

3. Kies **Toevoegen**.

    ![Admin portal, Knop Toevoegen, links van Exporteren en Vernieuwen](../../media/adminadd.png)

4.  Selecteer een **scherpsgebied** en voer de informatie voor de contactpersoon in. 

    ![de lijst met aandachtsgebieden, zoals Andere, Apps en Beveiliging](../../media/areaoffocus.png)

5. Herhaal dit voor elk scherpstelgebied. 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Stappen om aan de slag te gaan met Microsoft Managed Desktop

1. Beheerderscontacten toevoegen en verifiëren in de beheerportal (dit onderwerp)
2. [Voorwaardelijke toegang aanpassen](conditional-access.md)
3. [Licenties toewijzen](assign-licenses.md)
4. [InTune-bedrijfsportal installeren op apparaten](company-portal.md)
5. [Enterprise State Roaming inschakelen](enterprise-state-roaming.md)
6. [Microsoft Managed Desktop-apparaten instellen](set-up-devices.md)
7. [Uw gebruikers voorbereiden om apparaten te gebruiken](get-started-devices.md)
8. [Apps implementeren op apparaten](deploy-apps.md)
