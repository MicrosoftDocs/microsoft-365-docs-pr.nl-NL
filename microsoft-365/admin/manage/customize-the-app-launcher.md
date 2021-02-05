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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'Snel koppelingen maken naar uw e-mailberichten, documenten, apps, SharePoint-sites, externe sites en andere bronnen door aangepaste tegels toe te voegen aan het startpunt voor apps. '
ms.openlocfilehash: 96d059b252b63e48e20edb29861cf8233e220e34
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114187"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Aangepaste tegels toevoegen aan het startprogramma voor apps

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

In Microsoft 365 hebt u snel en eenvoudig toegang tot uw e-mail, agenda's, documenten en apps met behulp van het start programma voor apps[(meer informatie).](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) Dit zijn apps die u krijgt bij Microsoft 365, evenals aangepaste apps die u toevoegt uit [de SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) of [Azure AD.](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)
  
U kunt aan het startprogramma voor apps uw eigen aangepaste tegels toevoegen die verwijzen naar SharePoint-sites, externe sites, oude apps en meer. De aangepaste tegel verschijnt onder **Alle** apps in het startprogramma voor apps, maar u kunt de tegel vastmaken aan de **Start**-apps en uw gebruikers instructies geven dit ook te doen. Hierdoor kunt u eenvoudig sites, apps en resources vinden die relevant zijn bij het uitvoeren van uw taken. In het onderstaande voorbeeld wordt een aangepaste tegel gebruikt met de naam 'Contoso Portal' voor toegang tot de SharePoint-intranetsite van een organisatie. 
  
![Start start voor apps](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Een aangepaste tegel toevoegen aan het startprogramma voor apps

1. Meld u aan bij het beheercentrum als globale beheerder, ga naar Instellingen organisatie-instellingen en kies  >  het **tabblad Organisatieprofiel.**
    
2. Kies op **het tabblad Organisatieprofiel** de **tegel Aangepaste startpagina voor apps.**
  
3. Selecteer **Een aangepaste tegel toevoegen.** 
  
4. Typ in het vak **Tegelnaam** een naam voor de nieuwe tegel. Deze naam wordt weergegeven in de tegel. 
    
5. Voer een **URL van de website** voor de tegel in. Dit is de locatie waar u uw gebruikers naartoe wilt laten gaan wanneer ze de tegel selecteren in het startaar voor apps. Gebruik HTTPS in de URL.<br/>TIP: Als u een tegel voor een SharePoint-site maakt, gaat u naar die site, kopieert u de URL en plakt u deze hier. De URL van uw standaardteamsite ziet er zo uit: `https://<company_name>.sharepoint.com` 
  
6. Voer een **URL van de afbeelding voor** de tegel in. De afbeelding wordt weergegeven op de pagina Mijn apps en het startprogramma voor apps.<br/>TIP: De afbeelding moet 60x60 pixels zijn en beschikbaar zijn voor iedereen in uw organisatie, zonder verificatie te vereisen.

7. Voer een **Beschrijving** in voor de tegel. U ziet dit wanneer u de tegel selecteert op de pagina Mijn apps en **app-details selecteert.** 
  
8. Selecteer **Wijzigingen opslaan** om de aangepaste tegel te maken. 
    
U en uw gebruikers zien nu de aangepaste tegel in het startprogramma voor apps op het tabblad **Alle**. 
  
## <a name="promote-the-tile-to-app-launcher"></a>De tegel promoveren naar het start start starten van apps

1. Selecteer het pictogram voor het startpictogram voor apps en selecteer **alle apps.** 
    
2. Zoek de nieuwe tegel voor uw app, selecteer het beletselteken en kies **Vastmaken aan starter.**
  
    > [!NOTE]
    > Als u de aangepaste tegel niet ziet die in de vorige stappen is gemaakt, controleer dan of er een Exchange Online-postvak aan u is toegewezen en of u zich ten minste één keer bij uw postvak hebt aangemeld. Deze stappen zijn vereist voor aangepaste tegels in Microsoft 365. 
  
> [!IMPORTANT]
> Zowel u als uw gebruikers moeten deze stappen uitvoeren om aangepaste tegels te promoveren van de pagina Mijn apps naar het startprogramma voor apps. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. Ga in het beheercentrum naar het tabblad **Organisatieprofiel**  >  **instellingen**  >   </a> organisatie.
    
2. Selecteer Op de **profielpagina Organisatie,** naast **Aangepaste tegels voor uw** organisatie toevoegen, de optie **Bewerken.**

3. Werk de **Tegelnaam**, **URL**, **Beschrijving** of **Afbeeldings-URL** voor de aangepaste tegel bij (zie [Een aangepaste tegel toevoegen aan het startprogramma voor apps](#add-a-custom-tile-to-the-app-launcher)).
    
4. Selecteer **Bijwerken** \> **sluiten.** 
    
Als u een aangepaste tegel wilt verwijderen, **selecteert** u de tegel in het venster Aangepaste tegels en **selecteert u Tegel**  >  **verwijderen.** 
  
## <a name="whats-next"></a>En nu?

Naast het toevoegen van tegels aan het startvenster voor apps, kunt u ook tegels uit het startvenster voor apps toevoegen aan de navigatiebalk[(meer informatie).](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985) Zie Het thema [Microsoft 365](../setup/customize-your-organization-theme.md)aanpassen om het uiterlijk van Microsoft 365 aan te passen aan het merk van uw organisatie.
  
