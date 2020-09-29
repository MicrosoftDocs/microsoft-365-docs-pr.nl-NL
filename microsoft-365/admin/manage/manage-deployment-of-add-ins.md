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
description: Informatie over het implementeren van invoegtoepassingen voor gebruikers en groepen in uw organisatie met behulp van gecentraliseerde implementatie in het Beheercentrum.
ms.openlocfilehash: 20ebdfd2072c49fabadcbaf66dead54e75f9becd
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/29/2020
ms.locfileid: "48304790"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Invoegtoepassingen implementeren in het beheercentrum

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Met Office-invoegtoepassingen kunt u uw documenten aan uw persoonlijke voorkeur aanpassen en de manier waarop u toegang krijgt tot informatie op internet stroomlijnen (zie [Uw Office-invoegtoepassing gebruiken](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Als beheerder kunt u Office-invoegtoepassingen implementeren voor de gebruikers in uw organisatie met behulp van de gecentraliseerde implementatie functie in het Microsoft 365-Beheercentrum. Gecentraliseerde implementatie is de aanbevolen en meest veelzijdige manier voor de meeste beheerders om invoegtoepassingen te implementeren voor gebruikers en groepen binnen een organisatie. 

Zie [bepalen of gecentraliseerde implementatie van invoegtoepassingen werkt voor uw organisatie](centralized-deployment-of-add-ins.md)voor meer informatie over hoe u kunt bepalen of uw organisatie ondersteuning biedt voor gecentraliseerde implementatie.

Zie [Invoegtoepassingen beheren in het Beheercentrum](manage-addins-in-the-admin-center.md) voor meer informatie over het beheren van invoegtoepassingen na implementatie.
  
> [!NOTE]
>  Voor Word, Excel en PowerPoint kunt u een [SharePoint-app-catalogus](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) gebruiken om invoegtoepassingen te implementeren voor gebruikers in een on-premises omgeving zonder dat er een verbinding met microsoft 365 en/of ondersteuning voor SharePoint-invoegtoepassingen is vereist. Voor Outlook gebruikt u het Configuratiescherm van Exchange voor de implementatie in een on-premises omgeving zonder verbinding met Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Aanbevolen werkwijze voor de implementatie van Office-invoegtoepassingen

U wordt aangeraden het volgende te doen om invoegtoepassingen uit te voeren met behulp van een gephase aanpak:
  
1. Implementeer de invoegtoepassing voor een klein aantal belanghebbenden en medewerkers van de IT-afdeling. Als de implementatie slaagt, gaat u naar stap 2.
    
2. Implementeer de invoegtoepassing voor meer personen binnen het bedrijf. En, als dit is gelukt, de resultaten voltooien en doorgaan met volledige implementatie.
    
3. Voer een volledige implementatie uit voor alle gebruikers.
    
Afhankelijk van de grootte van de doelgroep, kunt u implementatie stappen toevoegen of verwijderen.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Een Office-invoegtoepassing implementeren via het Beheercentrum

Zie [bepalen of gecentraliseerde implementatie van invoegtoepassingen werkt voor uw organisatie](centralized-deployment-of-add-ins.md)voordat u begint.
  
1. Ga in het Beheercentrum naar de pagina **Settings** met \> **invoegtoepassingen** voorinstellingen. Als u de pagina met **invoeg** toepassingen niet ziet, gaat u naar de pagina met invoegtoepassingen voor de **instellingen** voor \> **geïntegreerde apps** \> **Add-ins** .
    
2. Selecteer **invoegtoepassing implementeren** boven aan de pagina en selecteer **volgende**.
 
    > [!NOTE]
    > Het Beheercentrum wordt bijgewerkt naar de implementatie ervaring met geïntegreerde apps. Als u de bovenstaande stappen niet ziet, gaat u naar de sectie gecentraliseerde implementatie door naar de **instellingen**van de  >  **geïntegreerde apps**te gaan. Kies invoeg **toepassingen**op de bovenkant van de pagina **geïntegreerde apps** .
    
3. Selecteer een optie en volg de instructies.
  
4. Als u de optie voor het toevoegen van een invoegtoepassing uit de Office Store hebt geselecteerd, maakt u de selectie van de invoegtoepassing. </br>

    U kunt beschikbare invoegtoepassingen op Categorieën weergeven: **voorgesteld voor u**, **beoordeling**of **naam**. Alleen gratis invoegtoepassingen zijn beschikbaar in de Office Store. Betaalde invoegtoepassingen worden momenteel niet ondersteund. Wanneer u een invoegtoepassing hebt geselecteerd, accepteert u de voorwaarden om door te gaan. <br/> 

    > [!NOTE] 
    > Met de optie Office Store worden updates en verbeteringen automatisch aan gebruikers toegevoegd.

5. Selecteer op de volgende pagina **iedereen**, **specifieke gebruikers/groepen**, of **alleen ik** wil opgeven met wie de invoegtoepassing wordt geïmplementeerd. Gebruik het vak Zoeken om specifieke gebruikers of groepen te vinden. <br/>

    > [!NOTE] 
    > Zie [Staten van invoegtoepassingen](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)voor meer informatie over andere statussen die van toepassing zijn op een invoegtoepassing.
  
6. Selecteer **implementeren**.
  
7. Wanneer de invoegtoepassing wordt geïmplementeerd, wordt een groen vinkje weergegeven. Volg de instructies op de pagina om de invoegtoepassing te testen.

    > [!NOTE]
    > Gebruikers moeten mogelijk Office opnieuw starten om het pictogram van de invoegtoepassing weer te geven op het lint van de app. Het kan 24 uur duren voordat Outlook-invoegtoepassingen worden weergegeven op het lint van de app.
    
8. Selecteer **volgende**wanneer u klaar bent. Als u alleen aan uzelf hebt gedistribueerd, kunt u **wijzigen wie toegang heeft tot de invoegtoepassing** selecteren om meer gebruikers te implementeren.

    Als u de invoegtoepassing hebt geïmplementeerd voor andere leden van uw organisatie, volgt u de instructies voor het aankondigen van de implementatie van de invoegtoepassing. <br/>
  
    Het is een goede gewoonte om gebruikers en groepen te informeren dat de geïmplementeerde invoegtoepassing beschikbaar is. Overweeg om een e-mailbericht te verzenden met een beschrijving wanneer en hoe u de invoegtoepassing kunt gebruiken. U kunt inhoud of veelgestelde vragen opnemen of koppelen die gebruikers kunnen helpen als ze problemen hebben met de invoegtoepassing.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Overwegingen bij het toewijzen van een invoegtoepassing aan gebruikers en groepen

Beheerders kunnen een invoegtoepassing aan iedereen of aan specifieke gebruikers en groepen toewijzen. Elke optie heeft gevolgen:
  
- **Iedereen** Met deze optie wordt de invoegtoepassing toegewezen aan alle gebruikers in de organisatie. Gebruik deze optie niet te vaak en alleen voor invoegtoepassingen die echt universeel voor uw organisatie zijn. 
    
- **Gebruikers** van Als u een invoegtoepassing toewijst aan een individuele gebruiker en de invoegtoepassing vervolgens implementeert voor een nieuwe gebruiker, moet u eerst de nieuwe gebruiker toevoegen.
    
- **Groep** Als u een invoegtoepassing toewijst aan een groep, worden de gebruikers die aan de groep zijn toegevoegd, automatisch toegewezen aan de invoegtoepassing. Wanneer een gebruiker wordt verwijderd uit een groep, heeft de gebruiker geen toegang meer tot de invoegtoepassing. In beide gevallen hoeft u geen extra actie te ondernemen van de beheerder. 

- **Alleen ik** Als u een invoegtoepassing alleen aan uzelf toewijst, wordt de invoegtoepassing toegewezen aan uw account, wat ideaal is voor het testen van de invoegtoepassing.
    
De juiste optie voor uw organisatie is afhankelijk van de configuratie. We raden u echter aan om opdrachten te maken met behulp van groepen. Als beheerder kunt u het beheer van invoegtoepassingen eenvoudiger maken met behulp van groepen en het lidmaatschap van de groepen beheren in plaats van afzonderlijke gebruikers tegelijk toe te wijzen. In sommige gevallen wilt u de toegang tot een klein aantal gebruikers beperken door toewijzingen aan specifieke gebruikers toe te voegen door gebruikers handmatig toe te wijzen.
  
## <a name="more-about-office-add-ins-security"></a>Meer informatie over beveiliging van Office-invoegtoepassingen

Office-invoegtoepassingen bevatten een XML-manifestbestand dat gegevens over de invoegtoepassing bevat. Het belangrijkste is echter dat het manifestbestand naar een webapplicatie verwijst die alle code en logica bevat. Invoegtoepassingen kennen talloze mogelijkheden. Met behulp van invoegtoepassingen kunt u bijvoorbeeld:
  
- Gegevens weergeven.
    
- Het document van een gebruiker lezen om op context gebaseerde services te bieden.
    
- Gegevens van het document van een gebruiker lezen of er gegevens naar schrijven.
    
Zie [Office Add-ins platform overview](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins) (Overzicht van platforms voor Office-invoegtoepassingen), met name de sectie Anatomy of an Office Add-in (Anatomie van een Office-invoegtoepassing).
  
Voor interactie met het document van de gebruiker moet de invoegtoepassing declareren welke machtiging er in het manifest is vereist. Een JavaScript API-model voor toestemming voor toegang bestaande uit vijf niveaus vormt de basis voor privacy en veiligheid voor gebruikers van invoegtoepassingen voor taakvensters. De meeste invoegtoepassingen in de Office Store zijn van het niveau ReadWriteDocument. Vrijwel alle invoegtoepassingen ondersteunen ten minste het niveau ReadDocument. Zie [Requesting permissions for API use in content and task pane add-ins](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins) (Machtigingen aanvragen voor API-gebruik in invoegtoepassingen voor inhouds- en taakvensters) voor meer informatie over machtigingsniveaus.
  
Wanneer een manifest wordt bijgewerkt, worden de wijzigingen voornamelijk aangebracht aan het pictogram en de tekst van de invoegtoepassing. Af en toe worden opdrachten van invoegtoepassingen gewijzigd. De machtigingen van de invoegtoepassing worden echter niet gewijzigd. De webtoepassing waar alle code en logica voor de invoegtoepassing wordt uitgevoerd, kan op elk moment worden gewijzigd, wat kenmerkend is voor webtoepassingen.
  
Updates voor invoegtoepassingen worden als volgt uitgevoerd:
  
- **Line-Of-Business-invoegtoepassing:** In dit geval, waarbij een beheerder een manifest expliciet heeft geüpload, wordt vereist dat de beheerder een nieuw manifestbestand uploadt zodat het wijzigen van metagegevens wordt ondersteund. De volgende keer dat de betreffende Office-toepassingen worden gestart, wordt de invoegtoepassing bijgewerkt. De webtoepassing kan elk moment worden gewijzigd. 

    > [!NOTE]
    > De beheerder hoeft geen LOB-invoegtoepassing te verwijderen voor het doen van een update.   In de sectie invoegtoepassingen kan de beheerder simpelweg op de LOB-invoegtoepassing klikken en vervolgens in de rechterbenedenhoek de **knop bijwerken** kiezen. Update werkt alleen als de versie van de nieuwe invoegtoepassing groter is dan de versie van de bestaande invoegtoepassing.   
    
- **Office Store-invoegtoepassing:** Als een beheerder een invoegtoepassing in de Office Store heeft geselecteerd (als een invoegtoepassing in de Office Store wordt bijgewerkt), wordt de invoegtoepassing later bijgewerkt in Gecentraliseerde implementatie. De volgende keer dat de betreffende Office-toepassingen worden gestart, wordt de invoegtoepassing bijgewerkt. De webtoepassing kan elk moment worden gewijzigd. 
  
## <a name="learn-more"></a>Meer informatie

[Invoegtoepassingen beheren in het beheercentrum](manage-addins-in-the-admin-center.md)

[Office-invoegtoepassingen maken](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins-fundamentals).

[Minderjarigen en het verkrijgen van invoegtoepassingen uit de Store](minors-and-acquiring-addins-from-the-store.md)
  
[PowerShell-cmdlets voor gecentraliseerde implementatie gebruiken om invoegtoepassingen te beheren](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[Problemen oplossen: gebruikers kunnen geen invoegtoepassingen zien](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
