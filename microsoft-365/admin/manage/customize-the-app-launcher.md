---
title: Aangepaste tegels toevoegen aan het startprogramma voor apps
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'Maak snelle koppelingen naar uw e-mail, documenten, apps, SharePoint-sites, externe sites en andere bronnen door aangepaste tegels toe te voegen aan het startprogramma voor apps. '
ms.openlocfilehash: e52bad5cdd1809e8aa0d97c681b69daa5143d3fd
ms.sourcegitcommit: 4b73f070747a66874c03fdf670ffdf16f736585a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2020
ms.locfileid: "43103073"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Aangepaste tegels toevoegen aan het startprogramma voor apps

In Office 365 kunt u snel en eenvoudig uw e-mail, agenda's, documenten en apps openen met het startprogramma voor apps van Office 365 ([meer informatie](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). Dit zijn apps die zijn inbegrepen bij Office 365 en aangepaste apps die u toevoegt uit de [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) of [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).
  
U kunt aan het startprogramma voor apps uw eigen aangepaste tegels toevoegen die verwijzen naar SharePoint-sites, externe sites, oude apps en meer. De aangepaste tegel verschijnt onder **Alle** apps in het startprogramma voor apps, maar u kunt de tegel vastmaken aan de **Start**-apps en uw gebruikers instructies geven dit ook te doen. Hierdoor kunt u eenvoudig sites, apps en resources vinden die relevant zijn bij het uitvoeren van uw taken. In het onderstaande voorbeeld wordt een aangepaste tegel gebruikt met de naam 'Contoso Portal' voor toegang tot de SharePoint-intranetsite van een organisatie. 
  
![Startpictogram voor Office 365-apps](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Een aangepaste tegel toevoegen aan het startprogramma voor apps

1. Ga in het beheercentrum naar de **instellingen** > **instellingen** en kies het tabblad **Organisatieprofiel.**
    
2. Kies op het tabblad **Organizenprofiel** de **optie Aangepaste startprogrammategels voor apps**.
  
3. Selecteer **Een aangepaste tegel toevoegen**. 
  
4. Typ in het vak **Tegelnaam** een naam voor de nieuwe tegel. Deze naam wordt weergegeven in de tegel. 
    
5. Voer een **URL van de website** voor de tegel in. Dit is de locatie waar u wilt dat uw gebruikers naartoe gaan wanneer ze de tegel op het startprogramma voor apps selecteren. Gebruik HTTPS in de URL.<br/>TIP: Als u een tegel maakt voor een SharePoint-site, navigeert u naar die site, kopieert u de URL en plakt u deze hier. De URL van uw standaardteamsite ziet er als volgt uit:`https://<company_name>.sharepoint.com` 
  
6. Voer een **URL van de afbeelding** voor de tegel in. De afbeelding wordt weergegeven op de pagina Mijn apps en het startprogramma voor apps.<br/>TIP: De afbeelding moet 60x60 pixels zijn en beschikbaar zijn voor iedereen in uw organisatie zonder verificatie.

7. Voer een **Beschrijving** in voor de tegel. U ziet dit wanneer u de tegel selecteert op de pagina Mijn apps en **app-details**selecteert. 
  
8. Selecteer **Wijzigingen opslaan** om de aangepaste tegel te maken. 
    
U en uw gebruikers zien nu de aangepaste tegel in het startprogramma voor apps op het tabblad **Alle**. 
  
## <a name="promote-the-tile-to-app-launcher"></a>De tegel promoten in App Launcher

1. Selecteer het pictogram startprogramma voor apps en selecteer het **pictogram Alle apps**. 
    
2. Zoek de nieuwe tegel voor uw app, selecteer de ellips en kies **Vastmaken aan launcher**.
  
    > [!NOTE]
    > Als u de aangepaste tegel niet ziet die in de vorige stappen is gemaakt, controleer dan of er een Exchange Online-postvak aan u is toegewezen en of u zich ten minste één keer bij uw postvak hebt aangemeld. Deze stappen zijn vereist voor aangepaste tegels in Office 365. 
  
> [!IMPORTANT]
> Zowel u als uw gebruikers moeten deze stappen uitvoeren om aangepaste tegels te promoveren van de pagina Mijn apps naar het startprogramma voor apps. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. Ga in het beheercentrum naar het profieltabblad **Instellingen** > **instellingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">organisatie.</a>
    
2. Selecteer op de pagina **Organisatieprofiel** naast **Aangepaste tegels toevoegen voor uw organisatie**de optie **Bewerken**.

3. Werk de **Tegelnaam**, **URL**, **Beschrijving** of **Afbeeldings-URL** voor de aangepaste tegel bij (zie [Een aangepaste tegel toevoegen aan het startprogramma voor apps](#add-a-custom-tile-to-the-app-launcher)).
    
4. Selecteer **Sluiten bijwerken** \> **Close**. 
    
Als u een aangepaste tegel wilt verwijderen, selecteert u in het venster **Aangepaste tegels** de tegel en selecteert u Tegel > **Verwijderen** **verwijderen**. 
  
## <a name="whats-next"></a>En nu?

Naast het toevoegen van tegels aan het startprogramma voor apps, kunt u ook tegels uit het startprogramma voor apps toevoegen aan de navigatiebalk van Office 365 ([meer informatie](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). Raadpleeg [Het Office 365-thema aanpassen](../setup/customize-your-organization-theme.md) om het uiterlijk van Office 365 aan te passen aan het merk van uw organisatie.
  

