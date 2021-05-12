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
description: 'Maak snelle koppelingen naar uw e-mail, documenten, apps, SharePoint sites, externe sites en andere bronnen door aangepaste tegels toe te voegen aan het start programma voor apps. '
ms.openlocfilehash: 598cfeb75fc811c87519c4479fa8fcab450466c3
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327208"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Aangepaste tegels toevoegen aan het startprogramma voor apps

In Microsoft 365 kunt u snel en eenvoudig toegang krijgen tot uw e-mail, agenda's, documenten en apps met behulp van het start start-programma voor apps[(meer informatie).](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) Dit zijn apps die u krijgt met Microsoft 365 en aangepaste apps die u toevoegt vanuit [de SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) of Azure [AD.](/previous-versions/office/office-365-api/)
  
U kunt aan het startprogramma voor apps uw eigen aangepaste tegels toevoegen die verwijzen naar SharePoint-sites, externe sites, oude apps en meer. De aangepaste tegel verschijnt onder **Alle** apps in het startprogramma voor apps, maar u kunt de tegel vastmaken aan de **Start**-apps en uw gebruikers instructies geven dit ook te doen. Hierdoor kunt u eenvoudig sites, apps en resources vinden die relevant zijn bij het uitvoeren van uw taken. In het onderstaande voorbeeld wordt een aangepaste tegel gebruikt met de naam 'Contoso Portal' voor toegang tot de SharePoint-intranetsite van een organisatie. 
  
![Start start start-app](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Een aangepaste tegel toevoegen aan het startprogramma voor apps

1. Meld u als globale beheerder aan bij het beheercentrum, ga naar Instellingen Organisatie Instellingen en kies  >  het **profieltabblad** Organisatie.
    
2. Kies op **het tabblad** Organisatieprofiel de optie **Aangepaste startpagina voor apps.**
  
3. Selecteer **Een aangepaste tegel toevoegen.** 
  
4. Typ in het vak **Tegelnaam** een naam voor de nieuwe tegel. Deze naam wordt weergegeven in de tegel. 
    
5. Voer een **URL van de website voor** de tegel in. Dit is de locatie waar uw gebruikers naartoe moeten gaan wanneer ze de tegel in het start. Gebruik HTTPS in de URL.

    > [!TIP]
    > Als u een tegel voor een SharePoint-site maakt, gaat u naar deze site, kopieert u de URL en plakt u deze hier. De URL van uw standaardteamsite ziet er als volgende uit: `https://<company_name>.sharepoint.com` 
  
6. Voer een **URL in van de afbeelding** voor de tegel. De afbeelding wordt weergegeven op de pagina Mijn apps en het startprogramma voor apps.

    > [!TIP]
    > De afbeelding moet 60x60 pixels zijn en beschikbaar zijn voor iedereen in uw organisatie zonder verificatie.

7. Voer een **Beschrijving** in voor de tegel. U ziet dit wanneer u de tegel op de pagina Mijn apps selecteert en **App-details selecteert.** 
  
8. Selecteer **Wijzigingen opslaan om** de aangepaste tegel te maken. 
    
    U en uw gebruikers zien nu de aangepaste tegel in het startprogramma voor apps op het tabblad **Alle**. 

    > [!NOTE]
    > Als u de aangepaste tegel niet ziet die in de vorige stappen is gemaakt, controleer dan of er een Exchange Online-postvak aan u is toegewezen en of u zich ten minste één keer bij uw postvak hebt aangemeld. Deze stappen zijn vereist voor aangepaste tegels in Microsoft 365. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. Ga in het beheercentrum naar **het tabblad Instellingen** organisatie  >  **Instellingen**  >  **organisatieprofiel.**
    
2. Selecteer op **de profielpagina** Organisatie naast Aangepaste tegels **voor uw organisatie** toevoegen de optie **Bewerken.**

3. Werk de **Tegelnaam**, **URL**, **Beschrijving** of **Afbeeldings-URL** voor de aangepaste tegel bij (zie [Een aangepaste tegel toevoegen aan het startprogramma voor apps](#add-a-custom-tile-to-the-app-launcher)).
    
4. Selecteer **Bijwerken** \> **sluiten.** 
    
Als u een aangepaste tegel wilt verwijderen, **selecteert** u in het venster Aangepaste tegels de tegel en **selecteert u Tegel**  >  **verwijderen.** 
  
## <a name="whats-next"></a>En nu?

Naast het toevoegen van tegels aan het startbalk voor apps, kunt u ook tegels voor het startvenster voor apps toevoegen aan de navigatiebalk[(meer informatie).](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985) Als u het uiterlijk van uw Microsoft 365 wilt aanpassen aan het merk van uw organisatie, zie Het thema Microsoft 365 [aanpassen.](../setup/customize-your-organization-theme.md)
