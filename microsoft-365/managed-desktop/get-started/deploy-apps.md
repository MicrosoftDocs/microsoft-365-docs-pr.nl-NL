---
title: Apps implementeren op apparaten
description: Informatie voor het toevoegen en implementeren van apps aan Microsoft Managed Desktop-apparaten.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie, apps, line-of-business apps, LOB-apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 6d35ee7a4a7755a043136f33600abad424956032
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529395"
---
# <a name="deploy-apps-to-devices"></a>Apps implementeren op apparaten
Een deel van de onboarding naar Microsoft Managed Desktop omvat het toevoegen en implementeren van apps op de apparaten van uw gebruiker. Zodra u de Microsoft Managed Desktop-portal gebruikt, u uw apps toevoegen en implementeren. 

Het totale proces ziet er als volgt uit:
1. [Apps toevoegen aan microsoft Managed Desktop-portal](#1) : dit kunnen bestaande LOB-apps (line-of-business) zijn of apps uit de Microsoft Store voor Bedrijven die u hebt gesynchroniseerd met Intune. 
2. [Azure Active Directory (AD)-groepen maken voor app-toewijzing](#2) - U gebruikt deze groepen om app-toewijzing te beheren.
3. [Apps toewijzen aan uw gebruikers](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Stap 1: Apps toevoegen aan Microsoft Managed Desktop-portal
U [Win32- of Windows MSI-apps](#lob-apps)of [Microsoft Store voor Bedrijven-apps](#msfb-apps) toevoegen aan Microsoft Managed Desktop en deze vervolgens implementeren op Microsoft Managed Desktop-apparaten.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32- of Windows MSI-apps naar Microsoft Managed Desktop

U uw LOB-apps (Line-of-Business) toevoegen aan de Microsoft Managed Desktop-portal. Zie [Microsoft Managed Desktop-appvereisten](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)voor informatie over vereisten voor apps die zijn geïnstalleerd op Microsoft Managed Desktop-apparaten.

In deze procedure selecteert u welk type app u wilt toevoegen en configureert en uploadt u de appbron. 

**Uw LOB-app of Windows-app toevoegen aan de Microsoft Managed Desktop-portal**

U zich aanmelden bij de Microsoft Managed Desktop-portal of u aanmelden bij Intune en vervolgens zoeken naar Microsoft Managed Desktop. We tonen aanmelden bij microsoft Managed Desktop-portal. 

1.    Meld u aan bij [microsoft Managed Desktop Admin-portal](https://aka.ms/mmdportal). 
2.    Selecteer onder **Voorraad**de optie **Apps**.
3.    Selecteer **Toevoegen**in de werkbelasting apps .
4.    Selecteer **in De app Toevoegen**de optie **Line-of-business-app of Windows-app** **(Win32).**
    - Zie Een [Windows-line-of-business-app toevoegen aan Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) voor instructies over het toevoegen en configureren van line-of-business-apps als u **de app Line-of-business**hebt geselecteerd.
    - Als u **de Windows-app (Win32) hebt**geselecteerd, raadpleegt u [Win32-appbeheer](https://docs.microsoft.com/intune/apps-win32-app-management) voor instructies voor het toevoegen en configureren van Windows-apps.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Microsoft Store voor Bedrijven-apps
Als u zich nog niet hebt aangemeld bij Microsoft Store voor Bedrijven, u zich aanmelden wanneer u voor apps winkelt. Nadat u uw apps hebt, u deze synchroniseren met Microsoft Managed Desktop. 

**Apps kopen in de Microsoft Store voor Bedrijven**

1. Meld u aan bij [Microsoft Store voor Bedrijven](https://businessstore.microsoft.com) met uw Microsoft Store voor Bedrijven-beheeraccount.
2. Selecteer **Winkel voor mijn groep**.
3. Gebruik Zoeken om te zoeken of de gewenste app is en selecteer de app.
4. Selecteer Op de productdetails de optie **De app ophalen.** Microsoft Store voegt de app toe aan **uw producten** voor uw organisatie.

**Een synchronisatie tussen Intune en Microsoft Store voor Bedrijven afdwingen**
1. Aanmelden bij [Azure-portal](https://portal.azure.com/) als Intune-beheerder of Globale beheerder voor uw tenant
2. Selecteer **Alle services > Intune**. Intune staat in de sectie Monitoring + Management.
3. Selecteer in het deelvenster Intune de optie **Client-apps**en selecteer **vervolgens Microsoft Store voor Bedrijven**.
4. Selecteer **Inschakelen** om uw Microsoft Store voor Bedrijven-apps te synchroniseren met Intune.
    - Als u dit nog niet hebt gedaan, meldt u zich aan en koppelt u uw Microsoft Store voor Bedrijven-account aan Intune
    - Selecteer de taal waarin apps in de Microsoft Store voor Bedrijven worden weergegeven in uw Intune-console
    - Selecteer **Synchroniseren** om uw Microsoft Store voor Bedrijven-apps te synchroniseren met Intune.
    - Controleer of de synchronisatie tussen Microsoft Store voor Bedrijven en Intune actief is (volgende stap). 

**Controleren of een synchronisatie tussen Intune en Microsoft Store voor Bedrijven actief is**
1. Meld u aan bij [Microsoft Store voor Bedrijven](https://businessstore.microsoft.com) met uw Microsoft Store voor Bedrijven-beheeraccount.
2. Selecteer **Beheren**.
3. Selecteer **Instellingen** en selecteer **Vervolgens Distribueren**.
4. Controleer onder **Beheergereedschappen**of Intune wordt vermeld en of de status **Actief**is .  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Stap 2: Azure AD-groepen maken

Maak drie Azure AD-groepen voor elke app. In deze tabel worden de groepen beschreven die u nodig hebt (Beschikbaar, Vereist en Verwijderen). 

Type app-toewijzing |    Groepsgebruik    | Voorbeeld Azure AD-naam
--- | --- | ---
Beschikbaar |  De app is beschikbaar via de Company Portal-app of -website. | MMD – *appnaam* – Beschikbaar
Vereist |  De app is geïnstalleerd op apparaten in de geselecteerde groepen. | MMD – *appnaam* – Vereist
Verwijderen |  De app is verwijderd van apparaten in de geselecteerde groepen. | MMD – *appnaam* – Verwijderen

Voeg uw gebruikers toe aan deze groepen om de app beschikbaar te maken, de app te installeren of de app te verwijderen van hun Microsoft Managed Desktop-apparaat. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Stap 3: Apps toewijzen aan uw gebruikers

**De app toewijzen aan uw gebruikers**

1. Meld u aan bij [microsoft Managed Desktop Admin-portal](https://aka.ms/mmdportal).
2. Selecteer **Apps**in het deelvenster Beheerd bureaublad .
3. Selecteer in de werkbelasting apps de app waaraan u gebruikers wilt toewijzen en selecteer **Gebruikersgroepen toewijzen.**
4. Selecteer voor de specifieke app een toewijzingstype (Beschikbaar, Vereist, Verwijderen) en wijs de juiste groep toe.
5. Selecteer **OK**in het deelvenster Apps toewijzen.


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
