---
title: Invoegtoepassingen implementeren in het beheercentrum
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Meer informatie over het implementeren van invoegtoepassingen voor gebruikers en groepen in uw organisatie met behulp van gecentraliseerde implementatie in het beheercentrum.
ms.openlocfilehash: 4e9a3a4b7182bfd452c63abd03836623dc77260c
ms.sourcegitcommit: f7566dd6010744c72684efdc37f4471672330b61
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138242"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Invoegtoepassingen implementeren in het beheercentrum

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Met Office-invoegtoepassingen kunt u uw documenten aan uw persoonlijke voorkeur aanpassen en de manier waarop u toegang krijgt tot informatie op internet stroomlijnen (zie [Uw Office-invoegtoepassing gebruiken](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Als beheerder u Office-invoegtoepassingen implementeren voor de gebruikers in uw organisatie met behulp van de functie Gecentraliseerde implementatie in het Microsoft 365-beheercentrum. Gecentraliseerde implementatie is de aanbevolen en meest veelzijdige manier voor de meeste beheerders om invoegtoepassingen te implementeren voor gebruikers en groepen binnen een organisatie. 

Zie [Bepalen of Gecentraliseerde implementatie van invoegtoepassingen werkt voor uw organisatie voor](centralized-deployment-of-add-ins.md)meer informatie over hoe u bepalen of uw organisatie gecentraliseerde implementatie kan ondersteunen.

Zie [Invoegtoepassingen beheren in het beheercentrum voor](manage-addins-in-the-admin-center.md) meer informatie over het beheren van invoegtoepassingen na implementatie
  
> [!NOTE]
>  Voor Word gebruiken Excel en PowerPoint een [SharePoint-app-catalogus](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) om invoegtoepassingen te implementeren voor gebruikers in een on-premises omgeving zonder dat er verbinding is met Microsoft 365 en/of ondersteuning voor SharePoint-invoegtoepassingen. Gebruik voor Outlook het Configuratiescherm van Exchange om te implementeren in een on-premises omgeving zonder verbinding met Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Aanbevolen werkwijze voor de implementatie van Office-invoegtoepassingen

Als u invoegtoepassingen wilt uitrollen met behulp van een gefaseerde aanpak, raden we u het volgende aan:
  
1. Rol de add-in uit naar een kleine set van zakelijke stakeholders en leden van de IT-afdeling. Als de implementatie succesvol is, gaat u naar stap 2.
    
2. Rol de add-in uit naar meer personen binnen het bedrijf. Nogmaals, evalueren van de resultaten en, indien succesvol, blijven met volledige implementatie.
    
3. Voer een volledige implementatie uit voor alle gebruikers.
    
Afhankelijk van de grootte van de doelgroep u uitrolstappen toevoegen of verwijderen.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Een Office-invoegtoepassing implementeren met het beheercentrum

Zie [Bepalen of Gecentraliseerde implementatie van invoegtoepassingen werkt voor uw organisatie.](centralized-deployment-of-add-ins.md)
  
1. Ga in het beheercentrum **Settings** naar de pagina \> **Instellingen invoegtoepassingen.**
    
2. Selecteer **Invoegtoepassing** implementeren boven aan de pagina en selecteer **Volgende**.
    
3. Selecteer een optie en volg de instructies.
  
4. Als u de optie hebt geselecteerd om een invoegtoepassing toe te voegen in de Office Store, maakt u uw invoegselectie. </br>

    U beschikbare invoegtoepassingen bekijken op categorieën: **Voorgestelde categorieën,** **Waardering**of **Naam**. Alleen gratis invoegtoepassingen zijn beschikbaar in de Office Store. Betaalde invoegtoepassingen worden momenteel niet ondersteund. Nadat u een invoegtoepassing hebt geselecteerd, accepteert u de algemene voorwaarden om door te gaan. <br/> 

    > [!NOTE] 
    > Met de optie Office Store worden updates en verbeteringen automatisch voor gebruikers doorgevoerd.

5. Selecteer op de volgende pagina **Iedereen**, **Specifieke gebruikers/groepen**of **Just me** om aan te geven aan wie de invoegtoepassing is geïmplementeerd. Gebruik het vak Zoeken om specifieke gebruikers of groepen te zoeken. <br/>

    > [!NOTE] 
    > Zie [Invoegtoepassingsstaten](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)voor meer informatie over andere statussen die van toepassing zijn op een invoegtoepassing.
  
6. Selecteer **Implementeren**.
  
7. Er verschijnt een groene teek wanneer de invoegtoepassing wordt geïmplementeerd. Volg de instructies op de pagina om de invoegtoepassing te testen.

    > [!NOTE]
    > Gebruikers moeten office mogelijk opnieuw starten om het invoegpictogram op het app-lint weer te geven. Het kan tot 24 uur duren voordat Outlook-invoegtoepassingen op app-linten worden weergegeven.
    
8. Selecteer **Volgende**als u klaar bent. Als u alleen bent geïmplementeerd, u Wijzigen selecteren **die toegang heeft tot invoegtoepassing** om te implementeren voor meer gebruikers.

    Als u de invoegtoepassing hebt geïmplementeerd voor andere leden van uw organisatie, volgt u de instructies om de implementatie van de invoegtoepassing aan te kondigen. <br/>
  
    Het is een goede gewoonte om gebruikers en groepen te informeren dat de geïmplementeerde invoegtoepassing beschikbaar is. Overweeg een e-mail te verzenden waarin wordt beschreven wanneer en hoe u de invoegtoepassing gebruiken. Voeg inhoud of veelgestelde vragen toe aan Help-inhoud of veelgestelde vragen die gebruikers kunnen helpen als ze problemen hebben met de invoegtoepassing.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Overwegingen bij het toewijzen van een invoegtoepassing aan gebruikers en groepen

Beheerders kunnen een invoegtoepassing aan iedereen of aan specifieke gebruikers en groepen toewijzen. Elke optie heeft gevolgen:
  
- **Iedereen** Met deze optie wordt de invoegtoepassing toegewezen aan elke gebruiker in de organisatie. Gebruik deze optie niet te vaak en alleen voor invoegtoepassingen die echt universeel voor uw organisatie zijn. 
    
- **Gebruikers** Als u een invoegtoepassing toewijst aan een individuele gebruiker en vervolgens de invoegtoepassing implementeert voor een nieuwe gebruiker, moet u eerst de nieuwe gebruiker toevoegen.
    
- **Groepen** Als u een invoegtoepassing toewijst aan een groep, krijgen gebruikers die aan de groep zijn toegevoegd, automatisch de invoegtoepassing toegewezen. Wanneer een gebruiker uit een groep wordt verwijderd, verliest de gebruiker de toegang tot de invoegtoepassing. In beide gevallen is er geen extra actie vereist van de beheerder. 

- **Alleen ik.** Als u een invoegtoepassing aan uzelf toewijst, wordt de invoegtoepassing alleen toegewezen aan uw account, wat ideaal is voor het testen van de invoegtoepassing.
    
De juiste optie voor uw organisatie is afhankelijk van uw configuratie. We raden echter aan om opdrachten te maken door gebruik te maken van groepen. Als beheerder u het gemakkelijker vinden om invoegtoepassingen te beheren door groepen te gebruiken en het lidmaatschap van die groepen te beheren in plaats van elke keer individuele gebruikers toe te wijzen. In sommige situaties u de toegang tot een kleine groep gebruikers beperken door toewijzingen aan specifieke gebruikers te maken door gebruikers handmatig toe te wijzen.
  
## <a name="more-about-office-add-ins-security"></a>Meer informatie over beveiliging van Office-invoegtoepassingen

Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:
  
- Gegevens weergeven.
    
- Het document van een gebruiker lezen om op context gebaseerde services te bieden.
    
- Gegevens van het document van een gebruiker lezen of er gegevens naar schrijven.
    
Zie [Office Add-ins platform overview](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins) (Overzicht van platforms voor Office-invoegtoepassingen), met name de sectie Anatomy of an Office Add-in (Anatomie van een Office-invoegtoepassing).
  
To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).
  
When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.
  
Updates voor invoegtoepassingen worden als volgt uitgevoerd:
  
- **Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 

    > [!NOTE]
    > De beheerder hoeft geen LOB-invoegtoepassing te verwijderen voor het uitvoeren van een update.   In de sectie Invoegtoepassingen kan admin eenvoudig op de LOB-invoegtoepassing klikken en de **knop Bijwerken** rechtsonder kiezen. Update werkt alleen als de versie van de nieuwe invoegtoepassing groter is dan die van de bestaande invoegtoepassing.   
    
- **Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 
  
## <a name="learn-more"></a>Meer informatie

[Invoegtoepassingen beheren in het beheercentrum](manage-addins-in-the-admin-center.md)

[Building Office In-ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins-fundamentals).

[Minderjarigen en het verwerven van add-ins uit de winkel](minors-and-acquiring-addins-from-the-store.md)
  
[Gecentraliseerde PowerShell-cmdlets voor gecentraliseerde implementatie gebruiken om invoegtoepassingen te beheren](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[Problemen oplossen: gebruiker ziet geen invoegtoepassingen](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
