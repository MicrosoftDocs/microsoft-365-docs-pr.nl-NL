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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Informatie over het implementeren van invoegingen voor gebruikers en groepen in uw organisatie met Gecentraliseerde implementatie in het beheercentrum.
ms.openlocfilehash: 4dc7552f2341097b95e763297d2f701f162f83ec
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454392"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Invoegtoepassingen implementeren in het beheercentrum

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Met Office-invoegtoepassingen kunt u uw documenten aan uw persoonlijke voorkeur aanpassen en de manier waarop u toegang krijgt tot informatie op internet stroomlijnen (zie [Uw Office-invoegtoepassing gebruiken](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Als beheerder kunt u Office-invoegingen voor de gebruikers in uw organisatie implementeren met behulp van de functie Gecentraliseerde implementatie in het Microsoft 365-beheercentrum. Gecentraliseerde implementatie is de aanbevolen en meest veelzijdige manier voor de meeste beheerders om invoegtoepassingen te implementeren voor gebruikers en groepen binnen een organisatie. 

Zie Bepalen of Gecentraliseerde implementatie van invoeghulp voor uw organisatie werkt voor meer informatie over hoe u bepaalt of uw organisatie Gecentraliseerde implementatie [kan ondersteunen.](centralized-deployment-of-add-ins.md)

Zie Invoegingen beheren in het beheercentrum voor meer informatie over het beheren van invoegingen na [de implementatie.](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  Voor Word gebruiken Excel en [](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) PowerPoint een SharePoint-app-catalogus om invoegingen te implementeren voor gebruikers in een on-premises omgeving zonder verbinding met Microsoft 365 en/of ondersteuning voor SharePoint-invoegvoegingen vereist. Voor Outlook gebruikt u het Configuratiescherm van Exchange om te implementeren in een on-premises omgeving zonder verbinding met Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Aanbevolen werkwijze voor de implementatie van Office-invoegtoepassingen

Als u invoegingen wilt uitrollen met behulp van een gefaseeerde aanpak, raden we het volgende aan:
  
1. Rol de invoeging uit naar een klein aantal belanghebbenden in het bedrijf en leden van de IT-afdeling. Als de implementatie is geslaagd, gaat u naar stap 2.
    
2. Rol de invoegrol uit naar meer personen binnen het bedrijf. Evalueer opnieuw de resultaten en ga verder met de volledige implementatie als dit lukt.
    
3. Voer een volledige implementatie uit voor alle gebruikers.
    
Afhankelijk van de grootte van de doelgroep, kunt u uitrolstappen toevoegen of verwijderen.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Een Office-invoeg office implementeren via het beheercentrum

Voordat u begint, bekijkt u Bepalen of Gecentraliseerde implementatie [van invoegingen voor uw organisatie werkt.](centralized-deployment-of-add-ins.md)
  
1. Ga in het beheercentrum naar de **pagina** Instellingen \> **voor invoegingen.** Als u de pagina voor **invoeg** apps  niet ziet, gaat u naar de pagina Geïntegreerde \>  \> **apps-invoegingen in Instellingen.**
    
2. Selecteer **Invoeg toevoegen implementeren** boven aan de pagina en selecteer vervolgens **Volgende.**
 
    > [!NOTE]
    > Het beheercentrum wordt bijgewerkt naar de implementatie-ervaring met Geïntegreerde apps. Geïntegreerde apps zijn alleen zichtbaar voor globale beheerders, terwijl voor andere gebruikers de oude ervaring nog steeds bestaat. Als u de bovenstaande stappen niet ziet, gaat u naar de sectie Gecentraliseerde implementatie via **Geïntegreerde**  >  **apps instellingen.** Kies invoegingen boven aan de pagina Geïntegreerde **apps.**
    
3. Selecteer een optie en volg de instructies.
  
4. Als u de optie hebt geselecteerd voor het toevoegen van een invoeg office store, selecteert u de invoeg graag. </br>

    U kunt beschikbare invoegingen weergeven op basis van categorieën: **Voorgesteld voor u,** **Beoordeling** of **Naam.** In de Office Store zijn alleen gratis invoegingen beschikbaar. Betaalde invoegtoepassingen worden momenteel niet ondersteund. Nadat u een invoeg toevoeg hebt geselecteerd, accepteert u de voorwaarden om door te gaan. <br/> 

    > [!NOTE] 
    > Met de optie Office Store worden updates en verbeteringen automatisch geïmplementeerd voor gebruikers.

5. Selecteer op de volgende pagina **Iedereen,** **Specifieke gebruikers/groepen** of Alleen **ik** om op te geven voor wie de invoeg mail is geïmplementeerd. Gebruik het zoekvak om specifieke gebruikers of groepen te zoeken. <br/>

    > [!NOTE] 
    > Zie de staten van de invoeg graag zien als u meer wilt weten over andere staten die van toepassing zijn op [een invoeg toepassing.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)
  
6. Selecteer **Implementeren.**
  
7. Er verschijnt een groene tik wanneer de invoeg toevoeg wordt geïmplementeerd. Volg de instructies op de pagina om de invoeging te testen.

    > [!NOTE]
    > Mogelijk moeten gebruikers Office opnieuw in gang zet om het pictogram van de invoegapp op het app-lint weer te geven. Het kan 24 uur duren voordat Outlook-invoegingen worden weergegeven op app-linten.
    
8. Wanneer u klaar bent, selecteert u **Volgende.** Als u alleen voor uzelf hebt  geïmplementeerd, kunt u Wijzigen wie toegang heeft tot invoegvoeging om te implementeren voor meer gebruikers.

    Als u de invoeg toepassing hebt geïmplementeerd in andere leden van uw organisatie, volgt u de instructies om de implementatie van de invoeg toepassing aan te kondigen. <br/>
  
    Het is een goede gewoonte om gebruikers en groepen te laten weten dat de geïmplementeerde invoeg graag wordt gebruikt. Overweeg om een e-mailbericht te verzenden waarin wordt beschreven wanneer en hoe u de invoeg toevoeg kunt gebruiken. Neem help-inhoud of veelgestelde vragen op (of een koppeling hier naar) die gebruikers kunnen helpen bij problemen met de invoegverbinding.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Overwegingen bij het toewijzen van een invoegtoepassing aan gebruikers en groepen

Globale beheerders en Exchange-beheerders kunnen een invoeging aan iedereen of aan specifieke gebruikers en groepen toewijzen. Elke optie heeft gevolgen:
  
- **Iedereen** Met deze optie wordt de invoegoptie toegewezen aan elke gebruiker in de organisatie. Gebruik deze optie niet te vaak en alleen voor invoegtoepassingen die echt universeel voor uw organisatie zijn. 
    
- **Gebruikers** Als u een invoeg toevoegt aan een individuele gebruiker en u de invoeg toevoegt aan een nieuwe gebruiker, moet u eerst de nieuwe gebruiker toevoegen.
    
- **Groepen** Als u een invoeg toevoegt aan een groep, wordt aan gebruikers die aan de groep worden toegevoegd, automatisch de invoeging toegewezen. Wanneer een gebruiker uit een groep wordt verwijderd, heeft de gebruiker geen toegang meer tot de invoegvoegvoeging. In beide gevallen hoeft de beheerder geen extra actie uit te voeren. 

- **Alleen ik** Als u alleen aan uzelf een invoeg mailaccount toewijst, wordt de invoeg mail alleen aan uw account toegewezen. Dit is ideaal voor het testen van de invoeg mail.
    
De juiste optie voor uw organisatie is afhankelijk van uw configuratie. Het is echter raadzaam opdrachten te maken met behulp van groepen. Als beheerder vindt u het mogelijk gemakkelijker om invoegingen te beheren door groepen te gebruiken en het lidmaatschap van deze groepen te beheren in plaats van steeds afzonderlijke gebruikers toe te wijzen. In sommige gevallen wilt u de toegang tot een kleine groep gebruikers beperken door toewijzingen aan specifieke gebruikers aan te brengen door gebruikers handmatig toe te wijzen.
  
## <a name="more-about-office-add-ins-security"></a>Meer informatie over beveiliging van Office-invoegingen

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
    > De beheerder hoeft een LOB-invoeging niet te verwijderen om een update uit te kunnen doen.   In de sectie Invoegingen kan beheerder gewoon op de LOB-invoeghoek klikken en de knop Bijwerken **in** de rechteronderhoek kiezen. Update werkt alleen als de versie van de nieuwe invoegversie groter is dan de versie van de bestaande invoegversie.   
    
- **Office Store-invoegtoepassing:** Als een beheerder een invoegtoepassing in de Office Store heeft geselecteerd (als een invoegtoepassing in de Office Store wordt bijgewerkt), wordt de invoegtoepassing later bijgewerkt in Gecentraliseerde implementatie. De volgende keer dat de betreffende Office-toepassingen worden gestart, wordt de invoegtoepassing bijgewerkt. De webtoepassing kan elk moment worden gewijzigd. 
  
## <a name="learn-more"></a>Meer informatie

[Invoegtoepassingen beheren in het beheercentrum](manage-addins-in-the-admin-center.md)

[Uw eerste Word-taakvenster invoeging maken.](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator)

[Minderjarigen en het verkrijgen van invoegingen in de store](minors-and-acquiring-addins-from-the-store.md)
  
[PowerShell-cmdlets voor Gecentraliseerde implementatie gebruiken om invoegingen te beheren](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[Problemen oplossen: Gebruiker ziet geen invoegingen](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
