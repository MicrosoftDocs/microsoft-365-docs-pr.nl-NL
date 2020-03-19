---
title: Beheerderscontactpersonen toevoegen en verifiëren in de portal Beheerder
description: Vertel ons met wie we contact moeten opnemen voor elk gebied van focus.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5a980c1e15a6cbc098647139caf48f813b36b040
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812758"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>Beheerderscontactpersonen toevoegen en verifiëren in de portal Beheerder

Er zijn verschillende manieren waarop de Microsoft Managed Desktop-service communiceert met klanten. Om de communicatie te stroomlijnen en ervoor te zorgen dat we de juiste mensen controleren, moet u een reeks beheerderscontacten bieden. Microsoft Managed Desktop IT Operations neemt contact op met deze mensen voor problemen met het oplossen van problemen met uw tenant.

> [!IMPORTANT]
> Mogelijk hebt u deze contactpersonen al toegevoegd aan de portal Beheerder. Als dat zo is, neem dan even de tijd om dubbel te controleren of de lijst met contactpersonen juist is, omdat Microsoft Managed Desktop ze **moet** kunnen bereiken als er zich een ernstig incident voordoet.

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Azure Active Directory-toegang voor microsoft Managed Desktop Admin-portal

Microsoft Managed Desktop Admin portal vereist dat mensen die toegang hebben tot de portal hebben een van deze Azure Active Directory (AD) rollen:
- Globale beheerder
- Servicebeheerder instemmen
- Globale lezer
- Service Support Administrator

De globale beheerder moet degene zijn die uw organisatie moet inschrijven in Microsoft Managed Desktop. Alle vijf rollen hebben dezelfde toegang binnen de portal Beheerder om taken te initiëren en weer te geven. Zie [Beheerdersrolmachtigingen in Azure Active Directory voor](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)meer informatie over het toewijzen van deze rollen in Azure AD. 

## <a name="admin-contact-areas-of-focus"></a>Contactgebieden voor beheerders

Beheerderscontacten moeten de beste persoon of groep zijn die vragen kan beantwoorden en beslissingen kan nemen voor verschillende aandachtsgebieden. **Microsoft Managed Desktop Operations neemt contact op met deze beheerderscontactpersonen voor vragen over ondersteuningsverzoeken die door de klant zijn ingediend.** Deze beheerderscontactpersonen ontvangen meldingen voor updates van ondersteuningsverzoeken en nieuwe berichten. Deze gebieden omvatten:

Aandachtsgebied | Voor vragen over
--- | ---
App-verpakking | Probleemoplossing voor app-verpakking
Apparaten | Apparaatstatus, probleemoplossing met Microsoft Managed Desktop-apparaten
Beveiliging | Beveiligingsproblemen oplossen met Microsoft Managed Desktop-apparaten
IT-helpdesk | in gevallen waarin onze ondersteuningsmedewerkers tickets van eindgebruikers buiten de ondersteuningsgebieden van Microsoft Managed Desktop overhandigen 
Andere | Voor kwesties die niet onder andere gebieden vallen

**Wie u ook kiest voor deze contactpersonen, moet de kennis en de bevoegdheid hebben om beslissingen te nemen voor uw Microsoft Managed Desktop-omgeving.** Wanneer u uw Microsoft Managed Desktop-omgeving aan boord maakt, wordt u gevraagd contactpersonen toe te voegen voor uw lokale helpdesk en beveiliging. 

Beheerderscontactpersonen zijn vereist wanneer u [een ondersteuningsverzoek indient.](../service-description/support.md) U moet een beheerderscontactpersoon hebben voor het focusgebied van de ondersteuningsaanvraag. 

**Beheerderscontactpersonen toevoegen**

1.  Meld u aan bij [de beheerportal van Microsoft Managed Desktop](https://aka.ms/mwaasportal). 

2.  Selecteer onder **Ondersteuning**de optie **Beheerderscontactpersonen**. 

    ![Ondersteuningsmenu, Beheerderscontactpersonen in de buurt van de beste geselecteerde](../../media/admincontacts.png)

3. Selecteer **Toevoegen**.

    ![Beheerportaal, Knop Toevoegen, links van exporteren en vernieuwen](../../media/adminadd.png)

4.  Selecteer een **scherpstelgebied** en voer de informatie voor de contactpersoon in. 

    ![de lijst met aandachtsgebieden, zoals Andere, Apps en Beveiliging](../../media/areaoffocus.png)

5. Herhaal dit voor elk aandachtsgebied. 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Stappen om aan de slag te gaan met Microsoft Managed Desktop

1. Beheerderscontactpersonen toevoegen en verifiëren in de portal Beheerder (dit onderwerp)
2. [Voorwaardelijke toegang aanpassen](conditional-access.md)
3. [Licenties toewijzen](assign-licenses.md)
4. [Intune Company Portal installeren op apparaten](company-portal.md)
5. [Enterprise State Roaming inschakelen](enterprise-state-roaming.md)
6. [Beheerde bureaubladapparaten van Microsoft instellen](set-up-devices.md)
7. [Uw gebruikers klaar maken voor gebruiksapparaten](get-started-devices.md)
8. [Apps implementeren op apparaten](deploy-apps.md)
