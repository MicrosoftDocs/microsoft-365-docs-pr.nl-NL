---
title: Invoegtoepassingen implementeren in het beheercentrum
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Informatie over het implementeren van invoegvoegingen voor gebruikers en groepen in uw organisatie met gecentraliseerde implementatie in het beheercentrum.
ms.openlocfilehash: 9ded0294912a3c3c99e62913bcdc349de7bae1b5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915384"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Invoegtoepassingen implementeren in het beheercentrum

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

Met Office-invoegtoepassingen kunt u uw documenten aan uw persoonlijke voorkeur aanpassen en de manier waarop u toegang krijgt tot informatie op internet stroomlijnen (zie [Uw Office-invoegtoepassing gebruiken](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Als beheerder kunt u Office-invoegvoegingen implementeren voor de gebruikers in uw organisatie met behulp van de functie Gecentraliseerde implementatie in het Microsoft 365-beheercentrum. Gecentraliseerde implementatie is de aanbevolen en meest veelzijdige manier voor de meeste beheerders om invoegtoepassingen te implementeren voor gebruikers en groepen binnen een organisatie.

Zie Bepalen of gecentraliseerde implementatie van invoegvoegingen werkt voor uw organisatie voor meer informatie over het bepalen of uw organisatie gecentraliseerde implementatie [kan ondersteunen.](centralized-deployment-of-add-ins.md)

Zie Invoegvoegingen beheren in het [beheercentrum](manage-addins-in-the-admin-center.md) voor meer informatie over het beheren van invoegvoegingen na de implementatie.
  
> [!NOTE]
>  Voor Word gebruiken Excel en PowerPoint een [SharePoint-appcatalogus](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) om invoegingen te implementeren voor gebruikers in een on-premises omgeving zonder verbinding met Microsoft 365 en/of ondersteuning voor SharePoint-invoegingen die vereist zijn. Voor Outlook gebruikt u het Exchange-configuratiescherm om te implementeren in een on-premises omgeving zonder verbinding met Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Aanbevolen werkwijze voor de implementatie van Office-invoegtoepassingen

Als u invoegingen wilt uitrollen met behulp van een gefaseerd benadering, raden we het volgende aan:
  
1. De invoegvoeging uitrollen naar een klein aantal belanghebbenden en leden van de IT-afdeling. Als de implementatie is geslaagd, gaat u naar stap 2.
    
2. De invoegvoeging uitrollen naar meer personen binnen het bedrijf. Evalueer nogmaals de resultaten en ga, indien succesvol, verder met de volledige implementatie.
    
3. Voer een volledige implementatie uit voor alle gebruikers.
    
Afhankelijk van de grootte van de doelgroep, kunt u uitrolstappen toevoegen of verwijderen.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Een Office-invoegvoeging implementeren met behulp van het beheercentrum

Zie Bepalen of gecentraliseerde implementatie van [invoegvoegingen](centralized-deployment-of-add-ins.md)werkt voor uw organisatie voordat u begint.
  
1. Ga in het beheercentrum naar de **pagina** \> **Instellingen-invoegvoegingen.** Als u de invoegpagina niet ziet,  gaat u naar de pagina Geïntegreerde  \>  \> **apps-invoegapps** instellingen.

2. Selecteer **Invoegvoegvoeging implementeren** boven aan de pagina en selecteer vervolgens **Volgende.**

    > [!NOTE]
    > Het beheercentrum wordt bijgewerkt naar implementatie-ervaring met geïntegreerde apps. Geïntegreerde apps zijn alleen zichtbaar voor globale beheerders, terwijl voor anderen de oude ervaring nog steeds bestaat. Als u de bovenstaande stappen niet ziet, gaat u naar de sectie Gecentraliseerde implementatie door naar Geïntegreerde  >  **instellingen-apps te gaan.** Kies invoegingen boven aan de pagina Geïntegreerde **apps.**

3. Selecteer een optie en volg de instructies.
  
4. Als u de optie hebt geselecteerd om een invoegvoeging toe te voegen in de Office Store, selecteert u de invoegprocedure. </br>

    U kunt beschikbare invoegvoegingen weergeven op basis van categorieën: Voorgesteld voor **u,** **Waardering** of **Naam.** Alleen gratis invoegvoegingen zijn beschikbaar in de Office Store. Betaalde invoegtoepassingen worden momenteel niet ondersteund. Nadat u een invoeging hebt geselecteerd, accepteert u de voorwaarden om door te gaan. <br/> 

    > [!NOTE]
    > Met de optie Office Store worden updates en verbeteringen automatisch geïmplementeerd voor gebruikers.

5. Selecteer op de volgende pagina **Iedereen**, **Specifieke gebruikers/groepen** of Alleen **ik** om op te geven aan wie de invoegvoeging is geïmplementeerd. Gebruik het vak Zoeken om specifieke gebruikers of groepen te zoeken. <br/>

    > [!NOTE]
    > Zie Invoeg staten voor meer informatie over andere staten die van toepassing zijn op een [invoeging.](./manage-addins-in-the-admin-center.md)
  
6. Selecteer **Implementeren**.
  
7. Er wordt een groene vinkje weergegeven wanneer de invoeging wordt geïmplementeerd. Volg de instructies op de pagina om de invoeging te testen.

    > [!NOTE]
    > Mogelijk moeten gebruikers Office opnieuw lanceren om het invoegpictogram op het app-lint weer te geven. Het kan 24 uur duren voordat Outlook-invoegvoegingen worden weergegeven op app-linten.

8. Wanneer u klaar bent, **selecteert** u Volgende . Als u alleen voor uzelf hebt  geïmplementeerd, kunt u Wijzigen wie toegang heeft tot invoegvoeging om te implementeren voor meer gebruikers.

    Als u de invoegvoeging hebt geïmplementeerd bij andere leden van uw organisatie, volgt u de instructies om de implementatie van de invoeging aan te kondigen. <br/>
  
    Het is een goede gewoonte om gebruikers en groepen te informeren dat de geïmplementeerde invoegvoeging beschikbaar is. U kunt een e-mailbericht verzenden waarin wordt beschreven wanneer en hoe u de invoeging kunt gebruiken. Voeg help-inhoud of veelgestelde vragen toe of koppel deze aan help-vragen die gebruikers kunnen helpen als ze problemen hebben met de invoeging.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Overwegingen bij het toewijzen van een invoegtoepassing aan gebruikers en groepen

Globale beheerders en Exchange-beheerders kunnen een invoegvoeging toewijzen aan iedereen of aan specifieke gebruikers en groepen. Elke optie heeft gevolgen:
  
- **Iedereen** Met deze optie wordt de invoegoptie toegewezen aan elke gebruiker in de organisatie. Gebruik deze optie niet te vaak en alleen voor invoegtoepassingen die echt universeel voor uw organisatie zijn.

- **Gebruikers** Als u een invoeging aan een afzonderlijke gebruiker toewijst en de invoegvoeging vervolgens implementeert voor een nieuwe gebruiker, moet u eerst de nieuwe gebruiker toevoegen.

- **Groepen** Als u een invoeging aan een groep toewijst, krijgen gebruikers die aan de groep worden toegevoegd, automatisch de invoegvoeging toegewezen. Wanneer een gebruiker uit een groep wordt verwijderd, verliest de gebruiker de toegang tot de invoeging. In beide gevallen is er geen extra actie vereist van de beheerder.

- **Alleen ik** Als u alleen aan uzelf een invoeging toewijst, wordt de invoegvoeging alleen aan uw account toegewezen, wat ideaal is voor het testen van de invoeging.

De juiste optie voor uw organisatie is afhankelijk van uw configuratie. Het is echter raadzaam om opdrachten te maken met behulp van groepen. Als beheerder is het mogelijk gemakkelijker om invoegingen te beheren door groepen te gebruiken en het lidmaatschap van die groepen te beheren in plaats van afzonderlijke gebruikers telkens toe te wijzen. In sommige situaties kunt u de toegang tot een kleine set gebruikers beperken door opdrachten aan specifieke gebruikers te maken door gebruikers handmatig toe te wijzen.
  
## <a name="more-about-office-add-ins-security"></a>Meer informatie over beveiliging van Office-invoegvoegingen

Office-invoegtoepassingen bevatten een XML-manifestbestand dat gegevens over de invoegtoepassing bevat. Het belangrijkste is echter dat het manifestbestand naar een webapplicatie verwijst die alle code en logica bevat. Invoegtoepassingen kennen talloze mogelijkheden. Met behulp van invoegtoepassingen kunt u bijvoorbeeld:
  
- Gegevens weergeven.

- Het document van een gebruiker lezen om op context gebaseerde services te bieden.

- Gegevens van het document van een gebruiker lezen of er gegevens naar schrijven.

Zie [Office Add-ins platform overview](/office/dev/add-ins/overview/office-add-ins) (Overzicht van platforms voor Office-invoegtoepassingen), met name de sectie Anatomy of an Office Add-in (Anatomie van een Office-invoegtoepassing).
  
Voor interactie met het document van de gebruiker moet de invoegtoepassing declareren welke machtiging er in het manifest is vereist. Een JavaScript API-model voor toestemming voor toegang bestaande uit vijf niveaus vormt de basis voor privacy en veiligheid voor gebruikers van invoegtoepassingen voor taakvensters. De meeste invoegtoepassingen in de Office Store zijn van het niveau ReadWriteDocument. Vrijwel alle invoegtoepassingen ondersteunen ten minste het niveau ReadDocument. Zie [Requesting permissions for API use in content and task pane add-ins](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins) (Machtigingen aanvragen voor API-gebruik in invoegtoepassingen voor inhouds- en taakvensters) voor meer informatie over machtigingsniveaus.
  
Wanneer een manifest wordt bijgewerkt, worden de wijzigingen voornamelijk aangebracht aan het pictogram en de tekst van de invoegtoepassing. Af en toe worden opdrachten van invoegtoepassingen gewijzigd. De machtigingen van de invoegtoepassing worden echter niet gewijzigd. De webtoepassing waar alle code en logica voor de invoegtoepassing wordt uitgevoerd, kan op elk moment worden gewijzigd, wat kenmerkend is voor webtoepassingen.
  
Updates voor invoegtoepassingen worden als volgt uitgevoerd:
  
- **Line-Of-Business-invoegtoepassing:** In dit geval, waarbij een beheerder een manifest expliciet heeft geüpload, wordt vereist dat de beheerder een nieuw manifestbestand uploadt zodat het wijzigen van metagegevens wordt ondersteund. De volgende keer dat de betreffende Office-toepassingen worden gestart, wordt de invoegtoepassing bijgewerkt. De webtoepassing kan elk moment worden gewijzigd.

    > [!NOTE]
    > Beheerder hoeft geen LOB-invoegvoeging te verwijderen voor het doen van een update.   In de sectie Invoegvoegingen kan beheerder gewoon op de LOB-invoeging klikken en de knop **Bijwerken** in de rechteronderhoek kiezen. Update werkt alleen als de versie van de nieuwe invoegversie groter is dan die van de bestaande invoegversie.

- **Office Store-invoegtoepassing:** Als een beheerder een invoegtoepassing in de Office Store heeft geselecteerd (als een invoegtoepassing in de Office Store wordt bijgewerkt), wordt de invoegtoepassing later bijgewerkt in Gecentraliseerde implementatie. De volgende keer dat de betreffende Office-toepassingen worden gestart, wordt de invoegtoepassing bijgewerkt. De webtoepassing kan elk moment worden gewijzigd.
  
## <a name="learn-more"></a>Meer informatie

[Invoegtoepassingen beheren in het beheercentrum](manage-addins-in-the-admin-center.md)

[Maak uw eerste Word-taakvenster-invoegvenster.](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator)

[Minderjarigen en het verkrijgen van invoegvoegingen in de store](minors-and-acquiring-addins-from-the-store.md)
  
[PowerShell-cmdlets voor gecentraliseerde implementatie gebruiken om invoegvoegingen te beheren](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md)
  
[Probleem oplossen: Gebruiker ziet geen invoegvoegingen](/office365/troubleshoot/access-management/user-not-seeing-add-ins)