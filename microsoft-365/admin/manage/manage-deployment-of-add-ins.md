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
description: Meer informatie over het implementeren van invoegtoepassingen voor gebruikers en groepen in uw organisatie met behulp van gecentraliseerde implementatie in het beheercentrum.
ms.openlocfilehash: 2d3b90a75f38a2c1146c0b0e5470c80b0af2c63f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572271"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Invoegtoepassingen implementeren in het beheercentrum

Met Office-invoegtoepassingen kunt u uw documenten aan uw persoonlijke voorkeur aanpassen en de manier waarop u toegang krijgt tot informatie op internet stroomlijnen (zie [Uw Office-invoegtoepassing gebruiken](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Als beheerder kunt u Office invoegtoepassingen implementeren voor de gebruikers in uw organisatie met behulp van de functie Gecentraliseerde implementatie in het Microsoft 365-beheercentrum. Gecentraliseerde implementatie is de aanbevolen en meest veelzijdige manier voor de meeste beheerders om invoegtoepassingen te implementeren voor gebruikers en groepen binnen een organisatie.

Zie Bepalen of [gecentraliseerde implementatie van invoegtoepassingen werkt voor uw organisatie voor](centralized-deployment-of-add-ins.md)meer informatie over hoe u kunt bepalen of uw organisatie gecentraliseerde implementatie kan ondersteunen.

Zie Invoegtoepassingen beheren in het beheercentrum voor meer informatie over het beheren [van invoegtoepassingen](manage-addins-in-the-admin-center.md) na implementatie.
  
> [!NOTE]
>  Voor Word gebruiken Excel en PowerPoint een [app-catalogus met SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) om invoegtoepassingen te implementeren voor gebruikers in een on-premises omgeving zonder verbinding met Microsoft 365 en/of ondersteuning voor SharePoint invoegtoepassingen die vereist zijn. Gebruik Outlook Exchange configuratiescherm om te implementeren in een on-premises omgeving zonder verbinding met Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Aanbevolen werkwijze voor de implementatie van Office-invoegtoepassingen

Als u invoegtoepassingen wilt uitrollen met behulp van een gefaseerde aanpak, raden we het volgende aan:
  
1. Rol de add-in uit naar een kleine groep zakelijke stakeholders en leden van de IT-afdeling. Als de implementatie is geslaagd, gaat u naar stap 2.
    
2. Rol de invoegtoepassing uit naar meer personen binnen het bedrijf. Evalueer nogmaals de resultaten en ga, indien succesvol, verder met de volledige implementatie.
    
3. Voer een volledige implementatie uit voor alle gebruikers.
    
Afhankelijk van de grootte van de doelgroep kunt u uitrolstappen toevoegen of verwijderen.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Een Office add-in implementeren met behulp van het beheercentrum

Voordat u begint, [raadpleegt u Bepalen of gecentraliseerde implementatie van invoegtoepassingen werkt voor uw organisatie](centralized-deployment-of-add-ins.md).
  
1. Ga in het beheercentrum naar de pagina **Instellingen** \> **Invoegtoepassingen.** Als u de **invoegtoepassingspagina** niet ziet, gaat u naar de pagina **Instellingen** geïntegreerde \>  \> **apps.**

2. Selecteer **Invoegtoepassing implementeren** boven aan de pagina en selecteer **vervolgens Volgende**.

    > [!NOTE]
    > Het beheercentrum wordt bijgewerkt naar de implementatie-ervaring met geïntegreerde apps. Geïntegreerde apps zijn alleen zichtbaar voor globale beheerders, terwijl voor anderen de oude ervaring nog steeds bestaat. Als u de bovenstaande stappen niet ziet, gaat u naar de sectie Gecentraliseerde implementatie door naar **Instellingen** Geïntegreerde apps te  >  gaan. Kies **Invoegtoepassingen** boven aan de pagina **Geïntegreerde apps** .

3. Selecteer een optie en volg de instructies.
  
4. Als u de optie hebt geselecteerd om een invoegtoepassing toe te voegen vanuit de Office Store, maakt u uw invoegtoepassingsselectie. </br>

    U kunt beschikbare invoegtoepassingen per categorie bekijken: **Aanbevolen voor u**, **Beoordeling** of **Naam**. Alleen gratis invoegtoepassingen zijn verkrijgbaar in de Office Store. Betaalde invoegtoepassingen worden momenteel niet ondersteund. Nadat u een invoegtoepassing hebt geselecteerd, accepteert u de algemene voorwaarden om door te gaan. <br/> 

    > [!NOTE]
    > Met de optie Office Store worden updates en verbeteringen automatisch geïmplementeerd voor gebruikers.

5. Selecteer op de volgende pagina **Iedereen**, **Specifieke gebruikers/groepen** of **Alleen ik** om op te geven voor wie de invoegtoepassing is geïmplementeerd. Gebruik het vak Zoeken om specifieke gebruikers of groepen te zoeken. <br/>

    > [!NOTE]
    > Zie [Invoegtoepassingsstatussen](./manage-addins-in-the-admin-center.md)voor meer informatie over andere statussen die van toepassing zijn op een invoegtoepassing.
  
6. Selecteer **Implementeren**.
  
7. Er verschijnt een groen vinkje wanneer de invoegtoepassing wordt geïmplementeerd. Volg de instructies op de pagina om de invoegtoepassing te testen.

    > [!NOTE]
    > Gebruikers moeten mogelijk Office opnieuw starten om het invoegtoepassingspictogram op het app-lint te bekijken. Outlook invoegtoepassingen kunnen tot 24 uur duren om op app-linten te worden weergegeven.

8. Als u klaar bent, selecteert u **Volgende**. Als u alleen voor uzelf hebt geïmplementeerd, kunt u Wijzigen selecteren **wie toegang heeft tot invoegtoepassingen** om te implementeren voor meer gebruikers.

    Als u de invoegtoepassing hebt geïmplementeerd bij andere leden van uw organisatie, volgt u de instructies om de implementatie van de invoegtoepassing aan te kondigen. <br/>
  
    Het is een goede gewoonte om gebruikers en groepen te informeren dat de geïmplementeerde invoegtoepassing beschikbaar is. Overweeg een e-mail te verzenden waarin wordt beschreven wanneer en hoe u de invoegtoepassing gebruikt. Inhoud of veelgestelde vragen over Help opnemen of koppelen die gebruikers kunnen helpen als ze problemen hebben met de invoegtoepassing.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Overwegingen bij het toewijzen van een invoegtoepassing aan gebruikers en groepen

Globale beheerders en Exchange beheerders kunnen een invoegtoepassing toewijzen aan iedereen of aan specifieke gebruikers en groepen. Elke optie heeft gevolgen:
  
- **Iedereen** Met deze optie wordt de invoegtoepassing toegewezen aan elke gebruiker in de organisatie. Gebruik deze optie niet te vaak en alleen voor invoegtoepassingen die echt universeel voor uw organisatie zijn.

- **Gebruikers** Als u een invoegtoepassing toewijst aan een afzonderlijke gebruiker en vervolgens de invoegtoepassing implementeert voor een nieuwe gebruiker, moet u eerst de nieuwe gebruiker toevoegen.

- **Groepen** Als u een invoegtoepassing aan een groep toewijst, krijgen gebruikers die aan de groep zijn toegevoegd automatisch de invoegtoepassing toegewezen. Wanneer een gebruiker uit een groep wordt verwijderd, verliest de gebruiker de toegang tot de invoegtoepassing. In beide gevallen is er geen extra actie vereist van de beheerder.

- **Alleen ik.** Als u een invoegtoepassing alleen aan uzelf toewijst, wordt de invoegtoepassing alleen aan uw account toegewezen, wat ideaal is voor het testen van de invoegtoepassing.

De juiste optie voor uw organisatie is afhankelijk van uw configuratie. We raden u echter aan om toewijzingen te maken met behulp van groepen. Als beheerder kunt u het gemakkelijker vinden om invoegtoepassingen te beheren door groepen te gebruiken en het lidmaatschap van die groepen te beheren in plaats van elke keer afzonderlijke gebruikers toe te wijzen. In sommige situaties kunt u de toegang tot een kleine set gebruikers beperken door toewijzingen aan specifieke gebruikers uit te voeren door gebruikers handmatig toe te wijzen.
  
## <a name="more-about-office-add-ins-security"></a>Meer informatie over Office beveiliging van invoegtoepassingen

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
    > De beheerder hoeft geen LOB-invoegtoepassing te verwijderen voor het uitvoeren van een update.   In het gedeelte Invoegtoepassingen kan de beheerder eenvoudig op de LOB-invoegtoepassing klikken en de **knop Bijwerken** in de rechterbenedenhoek kiezen. Bijwerken werkt alleen als de versie van de nieuwe invoegtoepassing groter is dan die van de bestaande invoegtoepassing.

- **Office Store-invoegtoepassing:** Als een beheerder een invoegtoepassing in de Office Store heeft geselecteerd (als een invoegtoepassing in de Office Store wordt bijgewerkt), wordt de invoegtoepassing later bijgewerkt in Gecentraliseerde implementatie. De volgende keer dat de betreffende Office-toepassingen worden gestart, wordt de invoegtoepassing bijgewerkt. De webtoepassing kan elk moment worden gewijzigd.
  
## <a name="related-content"></a>Verwante onderwerpen

[Invoegtoepassingen beheren in het beheercentrum](manage-addins-in-the-admin-center.md) (artikel)

[Uw eerste invoegtoepassing voor het Word-taakvenster maken](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator) (artikel)

[Minderjarigen en het verkrijgen van add-ins uit de winkel](minors-and-acquiring-addins-from-the-store.md) (artikel)
  
[Gecentraliseerde implementatie PowerShell-cmdlets gebruiken om invoegtoepassingen te beheren](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (artikel)
  
[Problemen oplossen: gebruiker ziet geen invoegtoepassingen](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (artikel)