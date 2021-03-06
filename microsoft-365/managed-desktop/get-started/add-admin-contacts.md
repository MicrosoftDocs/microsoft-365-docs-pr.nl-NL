---
title: Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal
description: Laat ons weten met wie we contact moeten opnemen voor elk focusgebied.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ba4f1b0e4b2e00334dbffb4bf0aa9edb1b8c5622
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286919"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal

Er zijn verschillende manieren waarop Microsoft Managed Desktop met klanten communiceert. Om de communicatie te stroomlijnen en ervoor te zorgen dat we contact hebben met de juiste personen, moet u een set beheerderscontacten verstrekken. Microsoft Managed Desktop IT Operations neemt contact op met deze personen voor hulp bij het oplossen van problemen met uw tenant.

> [!IMPORTANT]
> Mogelijk hebt u deze contactpersonen al toegevoegd aan de beheerportal. Als dat het geval is, kunt u nu even controleren of  de lijst met contactpersonen juist is, omdat Microsoft Managed Desktop moet kunnen bereiken als er een ernstig incident optreedt.

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Azure Active Directory toegang voor Microsoft Managed Desktop-beheerportal

Microsoft Managed Desktop Beheerdersportal vereist dat personen die toegang hebben tot de portal een van deze Azure Active Directory (AD) rollen hebben:

- Globale beheerder
- Intune-servicebeheerder
- Algemene lezer
- Serviceondersteuningsbeheerder

De globale beheerder moet degene zijn die uw organisatie inschrijft voor Microsoft Managed Desktop. Alle vijf rollen hebben dezelfde toegang binnen de beheerportal om taken te starten en weer te geven. Zie Beheerdersrolmachtigingen in Azure Active Directory voor meer informatie over het toewijzen van [deze rollen in](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)Azure AD.

## <a name="admin-contact-areas-of-focus"></a>Contactgebieden van beheerder met focus

Beheerderscontacten moeten de beste persoon of groep zijn die vragen kan beantwoorden en beslissingen kunnen nemen voor verschillende aandachtsgebieden. **Microsoft Managed Desktop Operations neemt contact op met deze beheerderscontacten voor vragen over ondersteuningsaanvragen die door de klant zijn ingediend.** Deze beheerderscontacten ontvangen meldingen voor ondersteuningsverzoekupdates en nieuwe berichten. Deze gebieden zijn:

Focusgebied | Voor vragen over
--- | ---
App-verpakking | App-verpakking oplossen
Apparaten | Apparaattoestand, probleemoplossing met Microsoft Managed Desktop apparaten
Beveiliging | Beveiligingsproblemen met Microsoft Managed Desktop oplossen
IT-helpdesk | in gevallen waarin ons ondersteuningspersoneel gebruikerstickets overhandt buiten Microsoft Managed Desktop ondersteuningsgebieden 
Overige | Voor problemen die niet onder andere gebieden vallen

**Wie u ook kiest voor deze contactpersonen, moet de kennis en bevoegdheid hebben om beslissingen te nemen voor uw Microsoft Managed Desktop omgeving.** Wanneer u uw Microsoft Managed Desktop invoegt, wordt u gevraagd contactpersonen toe te voegen voor uw lokale helpdesk en beveiliging. 

Beheerderscontacten zijn vereist wanneer u [een ondersteuningsaanvraag indient.](../service-description/support.md) U moet een beheerdercontactcontact hebben voor het focusgebied van de ondersteuningsaanvraag.

**Beheerderscontacten toevoegen**

1. Meld u aan [bij Microsoft Endpoint Manager.](https://endpoint.microsoft.com)

2. Zoek **onder Tenantbeheer** naar de **sectie Microsoft Managed Desktop** vervolgens **Beheerderscontacten.**

3. Kies **Toevoegen**.

4. Selecteer een **gebied met focus** en voer de gegevens voor de contactpersoon in. 

    ![de lijst met focusgebieden, zoals Overige, Apps en Beveiliging](../../media/areaoffocus.png)

5. Herhaal dit voor elk focusgebied.

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Stappen om aan de slag te gaan met Microsoft Managed Desktop

1. Beheerderscontacten toevoegen en verifiëren in de beheerportal (dit onderwerp)
2. [Voorwaardelijke toegang aanpassen](conditional-access.md)
3. [Licenties toewijzen](assign-licenses.md)
4. [InTune-bedrijfsportal installeren op apparaten](company-portal.md)
5. [Enterprise State Roaming inschakelen](enterprise-state-roaming.md)
6. [Microsoft Managed Desktop-apparaten instellen](set-up-devices.md)
7. [Uw gebruikers voorbereiden om apparaten te gebruiken](get-started-devices.md)
8. [Apps implementeren op apparaten](deploy-apps.md)
