---
title: Apps implementeren op apparaten
description: Informatie voor het toevoegen en implementeren van apps op Microsoft Managed Desktop-apparaten.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie, apps, line-of-business-apps, LOB-apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8bfc53d46bdcb91c16e9f4a1ddbc8ab3f6dfb47e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922024"
---
# <a name="deploy-apps-to-devices"></a>Apps implementeren op apparaten
Onderdeel van onboarding bij Microsoft Managed Desktop is het toevoegen en implementeren van apps op de apparaten van uw gebruiker. Wanneer u de Microsoft Managed Desktop-portal gebruikt, kunt u uw apps toevoegen en implementeren. 

Het totale proces ziet er als volgende uit:
1. [Apps toevoegen aan Microsoft Managed Desktop Portal:](#1) dit kunnen bestaande LOB-apps (Line-of-Business) zijn of apps uit de Microsoft Store voor Bedrijven die u hebt gesynchroniseerd met Intune. 
2. [Ad-groepen (Azure Active Directory) maken voor](#2) app-toewijzing: u gebruikt deze groepen om app-toewijzing te beheren.
3. [Apps toewijzen aan uw gebruikers](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Stap 1: Apps toevoegen aan Microsoft Managed Desktop Portal
U kunt [Win32- of Windows MSI-apps](#lob-apps)of Microsoft Store voor Bedrijven-apps toevoegen aan Microsoft Managed Desktop en deze vervolgens implementeren op Microsoft Managed Desktop-apparaten. [](#msfb-apps)

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32- of Windows MSI-apps naar Microsoft Managed Desktop

U kunt uw LOB-apps (Line-of-Business) toevoegen aan de Microsoft Managed Desktop-portal. Zie [Microsoft Managed Desktop-appvereisten](../service-description/mmd-app-requirements.md)voor informatie over vereisten voor apps die zijn geïnstalleerd op Microsoft Managed Desktop-apparaten.

In deze procedure selecteert u welk type app u wilt toevoegen en configureert en uploadt u de app-bron. 

**Uw LOB-app of Windows-app toevoegen aan microsoft managed desktopportal**

U kunt zich aanmelden bij de Microsoft Managed Desktop Portal of u aanmelden bij Intune en vervolgens zoeken naar Microsoft Managed Desktop. We laten zien dat u zich aanmeldt bij de Microsoft Managed Desktop-portal. 

1.    Meld u aan bij [de Microsoft Managed Desktop Admin Portal](https://aka.ms/mmdportal). 
2.    Selecteer **onder Inventaris** de optie **Apps.**
3.    Selecteer toevoegen in de werkbelasting **apps.**
4.    Selecteer **in App toevoegen** de optie **Line-of-Business-app of Windows-app** **(Win32)**.
    - Als u **line-of-business-app** hebt geselecteerd, zie [Een Windows-line-of-business-app](/intune/lob-apps-windows) toevoegen aan Microsoft Intune voor instructies over het toevoegen en configureren van line-of-business-apps.
    - Als u **Windows-app (Win32)** hebt geselecteerd, zie [Win32-appbeheer](/intune/apps-win32-app-management) voor instructies over het toevoegen en configureren van Windows-apps.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Microsoft Store voor Bedrijven-apps
Als u zich nog niet hebt aangemeld bij de Microsoft Store voor Bedrijven, kunt u zich registreren wanneer u naar apps winkelt. Nadat u uw apps hebt, kunt u deze synchroniseren met Microsoft Managed Desktop. 

**Apps kopen in de Microsoft Store voor Bedrijven**

1. Meld u aan [bij de Microsoft Store voor Bedrijven met](https://businessstore.microsoft.com) uw Microsoft Store voor Bedrijven-account.
2. Selecteer **Winkelen voor mijn groep.**
3. Gebruik Zoeken om te zoeken naar de beste app en selecteer de app.
4. Selecteer in de **productdetails De app downloaden.** Microsoft Store voegt de app toe aan **Uw producten** voor uw organisatie.

**Een synchronisatie forceer tussen Intune en Microsoft Store voor Bedrijven**
1. Meld u aan bij [het Microsoft Endpoint Manager-beheercentrum.](https://go.microsoft.com/fwlink/?linkid=2109431)
2. Selecteer **Tenantbeheer**  >  **connectors en tokens** Microsoft Store voor  >  **Bedrijven**.
3. Selecteer **Synchroniseren** om de apps die u hebt gekocht in de Microsoft Store in Intune te krijgen.

**Controleren of een synchronisatie tussen Intune en Microsoft Store voor Bedrijven actief is**
1. Meld u aan [bij de Microsoft Store voor Bedrijven met](https://businessstore.microsoft.com) uw Microsoft Store voor Bedrijven-account.
2. Selecteer **Beheren.**
3. Selecteer **Instellingen** en selecteer vervolgens **Distribueren.**
4. Controleer **onder Beheerhulpmiddelen** of Intune wordt vermeld en of de status **Actief** is.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Stap 2: Azure AD-groepen maken

Maak drie Azure AD-groepen voor elke app. In deze tabel worden de groepen beschreven die u nodig hebt (Beschikbaar, Vereist en Verwijderen). 

App-toewijzingstype |    Groepsgebruik    | Voorbeeld Azure AD-naam
--- | --- | ---
Beschikbaar |  De app is beschikbaar via de bedrijfsportal-app of -website. | MMD – *naam van app* – Beschikbaar
Vereist |  De app is geïnstalleerd op apparaten in de geselecteerde groepen. | MMD – *naam van app* – Vereist
Verwijderen |  De app wordt verwijderd van apparaten in de geselecteerde groepen. | MMD – *naam van app* – Verwijderen

Voeg uw gebruikers toe aan deze groepen om de app beschikbaar te maken, de app te installeren of de app te verwijderen van hun Microsoft Managed Desktop-apparaat. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Stap 3: Apps toewijzen aan uw gebruikers

**De app toewijzen aan uw gebruikers**

1. Meld u aan bij [de Microsoft Managed Desktop Admin Portal](https://aka.ms/mmdportal).
2. Selecteer apps in het deelvenster Beheerd **bureaublad.**
3. Selecteer in de werkbelasting Apps de app aan wie u gebruikers wilt toewijzen en selecteer **Gebruikersgroepen toewijzen.**
4. Selecteer voor de specifieke app een toewijzingstype (Beschikbaar, Vereist, Verwijderen) en wijs de juiste groep toe.
5. Selecteer OK in het deelvenster Apps **toewijzen.**


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