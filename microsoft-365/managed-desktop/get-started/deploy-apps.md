---
title: Apps implementeren op apparaten
description: Informatie voor het toevoegen en implementeren van apps op Microsoft Managed Desktop-apparaten.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie, apps, line-of-business apps, LOB-apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9fd6efc56441cfbe8a05404319246c5e0bbe10ab
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046326"
---
# <a name="deploy-apps-to-devices"></a>Apps implementeren op apparaten
Een deel van onboarding naar Microsoft Managed Desktop omvat het toevoegen en implementeren van apps op de apparaten van uw gebruiker. Zodra u de Microsoft Managed Desktop-portal gebruikt, u uw apps toevoegen en implementeren. 

Het totale proces ziet er als volgt uit:
1. [Apps toevoegen aan Microsoft Managed Desktop-portal](#1) - Dit kunnen bestaande LOB-apps (Line-of-Business) zijn of apps uit De Microsoft Store voor Bedrijven die u hebt gesynchroniseerd met Intune. 
2. [Azure Active Directory -groepen (AD) maken voor app-toewijzing](#2) - U gebruikt deze groepen om app-toewijzing te beheren.
3. [Apps toewijzen aan uw gebruikers](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Stap 1: Apps toevoegen aan Microsoft Managed Desktop-portal
U [Win32- of Windows MSI-apps](#lob-apps)of [Microsoft Store for Business-apps](#msfb-apps) toevoegen aan Microsoft Managed Desktop en deze vervolgens implementeren op Microsoft Managed Desktop-apparaten.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32- of Windows MSI-apps naar Microsoft Managed Desktop

U uw LOB-apps (line-of-business) toevoegen aan microsoft Managed Desktop-portal. Zie [Microsoft Managed Desktop-app-vereisten](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)voor informatie over vereisten voor apps die zijn geïnstalleerd op Microsoft Managed Desktop-apparaten.

In deze procedure selecteert u welk type app u wilt toevoegen en configureert en uploadt u de app-bron. 

**Uw LOB-app of Windows-app toevoegen aan Microsoft Managed Desktop-portal**

U zich aanmelden bij microsoft Managed Desktop-portal of u aanmelden bij Intune en vervolgens zoeken naar Microsoft Managed Desktop. We tonen aanmelden bij Microsoft Managed Desktop-portal. 

1.    Meld u aan bij [microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal). 
2.    Selecteer **Onder Inventaris**de optie **Apps**.
3.    Selecteer in de werkbelasting Apps de optie **Toevoegen**.
4.    Selecteer in **App toevoegen**de optie **Line-of-business-app** of **Windows-app (Win32).**
    - Als u **de line-of-business-app hebt**geselecteerd, raadpleegt u Een [Windows-line-of-business-app toevoegen aan Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) voor instructies over het toevoegen en configureren van bedrijfsapps.
    - Als u **De Windows-app (Win32) hebt**geselecteerd, raadpleegt u [Win32-appbeheer](https://docs.microsoft.com/intune/apps-win32-app-management) voor instructies over het toevoegen en configureren van Windows-apps.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Microsoft Store voor Bedrijven-apps
Als u zich nog niet hebt aangemeld bij Microsoft Store for Business, u zich aanmelden wanneer u apps koopt. Nadat u uw apps hebt, u ze synchroniseren met Microsoft Managed Desktop. 

**Apps kopen in de Microsoft Store voor Bedrijven**

1. Meld u aan bij [Microsoft Store for Business](https://businessstore.microsoft.com) met uw Microsoft Store voor Bedrijven-beheerdersaccount.
2. Selecteer **Winkelen voor mijn groep**.
3. Gebruik Zoeken om de gewenste app te vinden en selecteer de app.
4. Selecteer de app **downloaden**in de productdetails. Microsoft Store voegt de app toe aan **Uw producten** voor uw organisatie.

**Synchronisatie tussen Intune en Microsoft Store voor Bedrijven forceren**
1. Meld u aan bij [Azure Portal](https://portal.azure.com/) als Intune-beheerder of globale beheerder voor uw tenant
2. Selecteer **Alle services > Intune**. Intune bevindt zich in de sectie Monitoring + Management.
3. Selecteer in het deelvenster Intune **client-apps**en selecteer **Vervolgens Microsoft Store voor Bedrijven**.
4. Selecteer **Inschakelen** om uw Microsoft Store for Business-apps te synchroniseren met Intune.
    - Als u dit nog niet hebt gedaan, meldt u zich aan en koppelt u uw Microsoft Store for Business-account aan Intune
    - Selecteer de taal waarin apps in de Microsoft Store voor Bedrijven worden weergegeven in uw Intune-console
    - Selecteer **Synchroniseren** om uw Microsoft Store for Business-apps te synchroniseren met Intune.
    - Controleer of de synchronisatie tussen Microsoft Store for Business en Intune actief is (volgende stap). 

**Controleren of een synchronisatie tussen Intune en Microsoft Store voor Bedrijven actief is**
1. Meld u aan bij [Microsoft Store for Business](https://businessstore.microsoft.com) met uw Microsoft Store voor Bedrijven-beheerdersaccount.
2. Selecteer **Beheren**.
3. Selecteer **Instellingen** en selecteer **Vervolgens Distribueren**.
4. Controleer **onder Beheergereedschappen**of Intune wordt vermeld en of de status **Actief**is .  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Stap 2: Azure AD-groepen maken

Maak drie Azure AD-groepen voor elke app. In deze tabel worden de groepen beschreven die u nodig hebt (Beschikbaar, Vereist en Verwijderen). 

Type app-toewijzing |    Groepsgebruik    | Voorbeeld azure AD-naam
--- | --- | ---
Beschikbaar |  De app is beschikbaar via de bedrijfsportal-app of -website. | MMD – *app-naam* – Beschikbaar
Vereist |  De app is geïnstalleerd op apparaten in de geselecteerde groepen. | MMD – *app-naam* – Vereist
Verwijderen |  De app wordt verwijderd van apparaten in de geselecteerde groepen. | MMD – *app-naam* – Verwijderen

Voeg uw gebruikers toe aan deze groepen om de app beschikbaar te stellen, de app te installeren of de app te verwijderen van hun Microsoft Managed Desktop-apparaat. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Stap 3: Apps toewijzen aan uw gebruikers

**De app toewijzen aan uw gebruikers**

1. Meld u aan bij [microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).
2. Selecteer **Apps**in het deelvenster Beheerd bureaublad .
3. Selecteer in de werkbelasting Apps de app waaraan u gebruikers wilt toewijzen en selecteer **Gebruikersgroepen toewijzen**.
4. Selecteer voor de specifieke app een toewijzingstype (Beschikbaar, Vereist, Verwijderen) en wijs de juiste groep toe.
5. Selecteer **OK**in het deelvenster Apps toewijzen .


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
