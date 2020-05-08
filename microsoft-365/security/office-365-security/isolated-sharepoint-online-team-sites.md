---
title: Geïsoleerde SharePoint Online-teamsites
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: Meer informatie over geïsoleerde SharePoint Online-teamsites, zoals gebruik, vereisten en functies waarmee ze kunnen worden gebruikt.
ms.openlocfilehash: f88be4b16d7f3a65ba624f7bf4c490b0173883c8
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036702"
---
# <a name="isolated-sharepoint-online-team-sites"></a>Geïsoleerde SharePoint Online-teamsites

 **Overzicht**: meer informatie over de toepassingen voor geïsoleerde SharePoint Online-teamsites.
  
Met SharePoint Online-teamsites kunt u snel een ruimte maken om samen te werken aan notities, documenten, artikelen, een agenda en andere bronnen in Microsoft Office 365. SharePoint Online-teamsites zijn gebaseerd op een Microsoft 365-groep en beschikken over een vereenvoudigd beheermodel om een open samenwerking met een privéset groepsleden of de hele organisatie mogelijk te maken. Met een standaard SharePoint Online-teamsite kunnen leden van de Microsoft 365-groep andere gebruikers uitnodigen en instellingen voor machtigingen beheren.
  
In sommige gevallen wilt u echter voor samenwerking een SharePoint Online-teamsite maken waarbij de machtigingen van die site strak worden beheerd via het groepslidmaatschap en SharePoint Online-machtigingsniveaus die alleen worden beheerd door SharePoint-beheerders. Dit wordt een geïsoleerde site genoemd. De site is alleen beschikbaar voor de groep gebruikers die samenwerken, de inhoud van de site bekijken of de site beheren. Mogelijk hebt u een geïsoleerde site nodig voor het volgende:
  
- Een geheim project binnen uw organisatie.
    
- De locatie voor zeer gevoelige of waardevolle intellectuele eigendommen van uw organisatie.
    
- De bronnen voor een juridische actie van uw organisatie of dat waarop het betrekking heeft.
    
- Als u een abonnement op Microsoft 365 wilt delen tussen meerdere organisaties die elkaar overlappen maar voor het grootste deel als afzonderlijke bedrijfsentiteiten bestaan.
    
Hier volgen de vereisten voor een geïsoleerde site:
  
- Alleen beheerders van SharePoint Online kunnen sitebeheer uitvoeren, zoals groepslidmaatschap voor toegang tot de site en configuratie van aangepaste machtigingen.
    
- Leden van de site kunnen geen andere leden voor de teamsite uitnodigen.
    
- Gebruikers die geen lid zijn van de geïsoleerde site, kunnen geen toegang tot de site aanvragen. Zij krijgen het foutbericht 'Toegang geweigerd' te zien als ze toegang proberen te krijgen tot een URL die is gekoppeld aan de site.
    
Het nadeel van het gecentraliseerde toegangsbeheer en de aangepaste machtigingen door SharePoint Online-beheerders, is dat de site geïsoleerd blijft. Zo kunnen huidige leden geen andere personen uitnodigen (of dit nu opzettelijk of per ongeluk gebeurt) of aangepaste machtigingen configureren voor andere gebruikers in het Microsoft 365-abonnement die geen lid van de site zouden moeten zijn.
  
Een geïsoleerde site kan worden gebruikt in combinatie met andere functies, zoals:
  
- Information Rights Management om ervoor te zorgen dat de bronnen op de site versleuteld blijven, zelfs als ze lokaal worden gedownload en geüpload naar een andere site die voor de hele organisatie beschikbaar is.
    
- Preventie van gegevensverlies om te voorkomen dat gebruikers de bronnen van de site, zoals bestanden, verzenden in een e-mail.
    
## <a name="next-steps"></a>Volgende stappen

Als u een geïsoleerde SharePoint Online-teamsite wilt uitproberen in een proefabonnement, raadpleegt u de stapsgewijze instructies in [de documentatie over een omgeving voor ontwikkelen/testen voor een SharePoint Online-teamsite](isolated-sharepoint-online-team-site-dev-test-environment.md).
  
Als u klaar bent om een geïsoleerde SharePoint Online-teamsite in productie te implementeren, raadpleegt u de stapsgewijze overwegingen voor het ontwerpen in [Een geïsoleerde SharePoint Online-teamsite ontwerpen](design-an-isolated-sharepoint-online-team-site.md).
  
## <a name="see-also"></a>Zie ook

[Een geïsoleerde SharePoint Online-teamsite ontwerpen](design-an-isolated-sharepoint-online-team-site.md)
  
[Een geïsoleerde SharePoint Online-teamsite beheren](manage-an-isolated-sharepoint-online-team-site.md)

[Een geïsoleerde SharePoint Online-teamsite implementeren](deploy-an-isolated-sharepoint-online-team-site.md)


