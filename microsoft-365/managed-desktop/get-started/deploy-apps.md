---
title: Apps implementeren op apparaten
description: Informatie over het toevoegen en implementeren van apps aan Microsoft beheerde bureaublad apparaten.
keywords: Microsoft Managed Desktop, Microsoft 365, service, Documentatie, apps, line-of-Business-Apps, LOB-apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eb8b984550f301af9d99e738f6db4623aa2cc86
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769104"
---
# <a name="deploy-apps-to-devices"></a>Apps implementeren op apparaten
Een onderdeel van onboarding voor Microsoft Managed Desktop bevat het toevoegen en implementeren van apps aan de apparaten van uw gebruikers. Wanneer u de Microsoft beheerde bureaublad Portal gebruikt, kunt u uw apps toevoegen en implementeren. 

Het algehele proces ziet er als volgt uit:
1. [Apps toevoegen aan de beheerde bureaublad portal van Microsoft](#1) : dit kan bestaan uit bestaande LOB-apps (line-of-Business), of apps uit Microsoft Store voor bedrijven die u met intune hebt gesynchroniseerd. 
2. [Azure Active Directory (AD) groepen maken voor app-toewijzing](#2) : u gebruikt deze groepen om de app-toewijzing te beheren.
3. [Apps aan uw gebruikers toewijzen](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Stap 1: apps toevoegen aan de beheerde bureaublad portal van Microsoft
U kunt [Win32-of Windows MSI-](#lob-apps)apps of [Microsoft Store for Business-Apps](#msfb-apps) toevoegen aan het Microsoft-beheer bureaublad en ze vervolgens implementeren op Microsoft beheerde bureaublad apparaten.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32-of Windows MSI-apps op basis van de Microsoft beheerde bureaubladversie

U kunt uw LOB-apps (line-of-Business) toevoegen aan de beheerde bureaublad portal van Microsoft. Zie vereisten voor de [beheerde bureaublad-app](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)voor meer informatie over de vereisten voor apps die zijn geïnstalleerd op Microsoft beheerde bureaublad apparaten.

Bij deze procedure selecteert u het type app dat u wilt toevoegen en vervolgens configureert en uploadt u de app-bron. 

**Uw LOB-app of Windows-app toevoegen aan de beheerde bureaublad portal van Microsoft**

U kunt zich aanmelden bij Microsoft beheerde bureaublad Portal, of u kunt zich aanmelden bij intune en vervolgens zoeken naar Microsoft Managed Desktop. We tonen het aanmelden bij Microsoft beheerde bureaublad Portal. 

1.    Meld u aan bij de [Portal van Microsoft beheerde bureaubladbeheer](https://aka.ms/mmdportal). 
2.    Selecteer onder **voorraad** **apps** .
3.    Selecteer **toevoegen** in de apps-werkbelasting.
4.    Selecteer in **app toevoegen** de optie **line-of-Business** of **Windows-app (Win32)** .
    - Als u een **line-of-Business-app** hebt geselecteerd, raadpleegt u [een Windows line-of-Business-app toevoegen aan Microsoft intune](https://docs.microsoft.com/intune/lob-apps-windows) voor instructies over het toevoegen en configureren van line-of-Business-Apps.
    - Als u **Windows-app (Win32)** hebt geselecteerd, raadpleegt u [Win32 app Management](https://docs.microsoft.com/intune/apps-win32-app-management) for instructies over het toevoegen en configureren van Windows-apps.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Apps voor Microsoft Store voor bedrijven
Als u zich nog niet hebt aangemeld bij Microsoft Store voor bedrijven, kunt u zich registreren wanneer u voor apps moet winkelen. Wanneer u uw apps hebt, kunt u deze synchroniseren met Microsoft Managed Desktop. 

**Apps kopen in de Microsoft Store voor bedrijven**

1. Meld u aan bij [Microsoft Store voor bedrijven](https://businessstore.microsoft.com) met uw beheerdersaccount voor Microsoft Store voor bedrijven.
2. Selecteer **winkel voor mijn groep** .
3. Gebruik de zoekfunctie om de gewenste app te vinden en selecteer de app.
4. Selecteer op de productgegevens **de optie Get the app** . Microsoft Store voegt de app toe aan **uw producten** voor uw organisatie.

**Een synchronisatie tussen intune en Microsoft Store voor bedrijven afdwingen**
1. Meld u aan bij het [Beheercentrum van Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Tenant beheer**  >  **connectors en tokens**  >  **Microsoft Store voor bedrijven** .
3. Selecteer **synchroniseren** om de apps die u in de Microsoft Store hebt gekocht, op te downloaden in intune.

**Controleren of een synchronisatie tussen intune en Microsoft Store voor bedrijven actief is**
1. Meld u aan bij [Microsoft Store voor bedrijven](https://businessstore.microsoft.com) met uw beheerdersaccount voor Microsoft Store voor bedrijven.
2. Selecteer **beheren** .
3. Selecteer **instellingen** en selecteer **verdelen** .
4. Controleer onder **beheerprogramma's** of intune wordt weergegeven en of de status **actief** is.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Stap 2: Azure AD-groepen maken

Maak drie Azure AD-groepen voor elke app. In deze tabel vindt u een overzicht van de groepen die u nodig hebt (beschikbaar, vereist en verwijderen). 

Type app-toewijzing |    Groepsgebruik    | Voorbeeld van Azure AD naam
--- | --- | ---
Beschikbaar |  De app is beschikbaar in de bedrijfs portal-app of-website. | MMD – *app-naam* – beschikbaar
Vereist |  De app is geïnstalleerd op apparaten in de geselecteerde groepen. | MMD – *app-naam* – vereist
Verwijderen |  De app wordt verwijderd van apparaten in de geselecteerde groepen. | MMD – *app-naam* – verwijderen

Voeg uw gebruikers toe aan deze groepen om de app beschikbaar te maken, de app te installeren of de app te verwijderen van het Microsoft-beheerapparaat. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Stap 3: apps aan uw gebruikers toewijzen

**De app toewijzen aan uw gebruikers**

1. Meld u aan bij de [Portal van Microsoft beheerde bureaubladbeheer](https://aka.ms/mmdportal).
2. Selecteer **apps** in het deelvenster beheerde bureaubladversie.
3. Selecteer in de apps op de app waaraan u gebruikers wilt toewijzen en selecteer **gebruikersgroepen toewijzen** .
4. Selecteer voor de specifieke app een type toewijzing (beschikbaar, vereist, verwijderen) en wijs de juiste groep toe.
5. Selecteer in het deelvenster apps toewijzen de optie **OK** .


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Stappen om aan de slag te gaan met Microsoft Managed Desktop

1. [Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal](add-admin-contacts.md)
2. [Voorwaardelijke toegang aanpassen](conditional-access.md)
3. [Licenties toewijzen](assign-licenses.md)
4. [Intune Company Portal implementeren](company-portal.md)
5. [Enterprise State Roaming inschakelen](enterprise-state-roaming.md)
6. [Apparaten instellen](set-up-devices.md)
7. [Uw gebruikers voorbereiden om apparaten te gebruiken](get-started-devices.md)
8. Apps implementeren (dit onderwerp)


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
