---
title: Tijdens en na het verplaatsen van uw gegevens
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.collection: SPO_Content
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: f47e3e09-b1dc-4b80-b6ea-fd6e0933407f
f1.keywords:
- NOCSH
description: Gegevens verplaatsingen bestaan uit een back-end en worden weergegeven wanneer door Microsoft services en bijbehorende gegevens voor uw Tenant worden verplaatst naar een nieuw datacenter-geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d2e63dd046f62f07e367b3632f96bf7261b99c9c
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333698"
---
# <a name="during-and-after-your-data-move"></a>Tijdens en na het verplaatsen van uw gegevens

Gegevens worden verplaatst met een back-end-bewerking met minimale gevolgen voor eindgebruikers. U hoeft geen actie te ondernemen terwijl Microsoft elke service en bijbehorende gegevens voor uw Tenant naar een nieuw datacenter-geografische plaats levert. De gegevensoverdracht en validering vindt plaats op de achtergrond met de minimale impact van de gebruikers.
  
> [!NOTE]
> Voor elke service wordt de plaats van een bericht herhaald. Daarom ziet u de hierboven gereduceerde functionaliteit voor elke service op een ander moment. 
  
Bekijk het Microsoft 365-berichtencentrum ter bevestiging wanneer u de chatfunctie voor alle Exchange Online, SharePoint Online en teams-chatservice uitvoert. Zoals u in de onderstaande tabel ziet, kan het tot 24 maanden duren na het einde van de registratieperiode voor het voltooien van de kern klantgegevens bij de rest van het nieuwe datacenter geo.   

|**Klanten met een land in**|**Alle verplaatste wordt voltooid door**|
|:-----|:-----|
|Australië, Nieuw-Zeeland, Fiji  <br/> |Woensdag 1 juli 2022  <br/> |
|Japan   <br/> |Woensdag 1 juli 2022  <br/> |
|India  <br/> |Woensdag 1 juli 2022  <br/> |
|Canada  <br/> |Woensdag 1 juli 2022  <br/> |
|Zuid-Korea  <br/> |Woensdag 1 juli 2022  <br/> |
|Verenigd Koninkrijk  <br/> |Woensdag 1 juli 2022  <br/> |
|Frankrijk  <br/> |Woensdag 1 juli 2022  <br/> |
|Verenigde Arabische Emiraten  <br/> |Woensdag 1 juli 2022  <br/> |
|Zuid-Afrika  <br/> |Woensdag 1 juli 2022  <br/> |
|Zwitserland, Liechtenstein  <br/> |Woensdag 1 juli 2022  <br/> |
|Noorwegen  <br/> |Woensdag 1 november 2022  <br/> |
|Duitsland  <br/> |Woensdag 1 april 2023  <br/> |

## <a name="exchange-online"></a>Exchange Online

Aangezien het tijd is om elke gebruiker naar de nieuwe datacenter geo voor één Tenant te verplaatsen, zijn sommige gebruikers nog steeds in het oude datacenter geo voor de verhuizing, terwijl andere gebruikers zich in de nieuwe naam van het datacenter bevinden. Dit betekent dat sommige functies waarmee u meerdere postvakken opent, mogelijk niet volledig werken tijdens een periode van het verplaatsings proces, wat de laatste week kan zijn. Een beschrijving van de functies in de volgende secties.
  
### <a name="open-shared-folder-in-outlook-web-access"></a>Gedeelde mappen openen in Outlook Web Access

Sommige gebruikers openen een gedeelde e-mailmap vanuit een ander postvak (dat de gebruiker lees-of schrijfmachtigingen heeft) in Outlook Web Access met behulp van de functie gedeelde map. In de volgende tabel wordt beschreven hoe de toegang tot gedeelde mappen werkt tijdens het verplaatsen van een postvak. Houd er rekening mee dat gebruikers met volledige machtigingen voor een gedeeld postvak de e-mail kunnen openen via Outlook Web Access wanneer u onderweg bent. 
  
|**Configuratie**|**Beschrijving**|
|:-----|:-----|
|De gebruiker beschikt over de machtiging postvakmappen voor een ander Postvak  <br/> |Mogelijk beperkt.  <br/> Als de gebruiker A en Postvak B niet binnen de geo-verhuizing van de Tenant overstappen, kan gebruiker A de map Postvak B niet openen in Outlook Web Access als gebruiker A only gemachtigd is voor een bepaalde map in Postvak B.  <br/> Als u een gedeelde map wilt toevoegen, klikt u met de rechtermuisknop op de gebruikersnaam in het linker navigatiedeelvenster en klikt u op **gedeelde map toevoegen**.  <br/> |
|Gebruiker met de machtiging volledig postvak voor een ander Postvak  <br/> |Volledig ondersteund.  <br/> Als gebruiker A de machtiging Volledige toegang heeft tot postvak B, kan gebruiker A klikken op de gedeelde map in het linker navigatiedeelvenster in Outlook Web Access om een venster met postvak B te openen.  Gebruikers kunnen een gedeeld postvak openen via Outlook Web Access tijdens de verhuizing zonder nadelige gevolgen. De beperking geldt alleen voor het delen van een map in een postvak.           |
  
## <a name="sharepoint-online"></a>SharePoint Online

Wanneer SharePoint Online wordt verplaatst, worden de gegevens van de volgende services ook verplaatst:
  
- Eén station voor bedrijven
    
- Microsoft 365-Video Services
    
- Office in een browser
    
- Microsoft 365-apps voor ondernemingen
    
- Visio Pro voor Microsoft 365
    
Nadat u uw SharePoint Online-gegevens hebt verplaatst, ziet u mogelijk een of meer van de volgende effecten:
  
### <a name="microsoft-365-video-services"></a>Microsoft 365-Video Services

- De verhuizing voor video duurt langer dan de overstap voor de rest van uw inhoud in SharePoint Online.
    
- Nadat de inhoud van de SharePoint Online-inhoud is verplaatst, wordt er een tijdsbestek weergegeven wanneer Video's niet kunnen worden afgespeeld.
    
- We verwijderen de overschreven kopieën van het vorige datacenter en schrijven ze opnieuw in het nieuwe datacenter.
    
### <a name="search"></a>Vinden

Wanneer u uw SharePoint Online-gegevens verplaatst, worden uw zoekindexen en zoekinstellingen naar een nieuwe locatie gemigreerd. Tot de verhuizing van de SharePoint Online-gegevens is **voltooid** , blijven de gebruikers van de index op de oorspronkelijke locatie. In de nieuwe locatie wordt de zoekfunctie automatisch gestart wanneer u uw SharePoint Online-gegevens hebt verplaatst. Vanaf dit punt en de volgende behartiging kunnen we uw gebruikers uit de gemigreerde index gebruiken. Wijzigingen in uw inhoud die plaatsvond na de migratie, worden niet opgenomen in de gemigreerde index totdat ze worden gemigreerd. De meeste klanten merken niet dat het resultaat minder vers is nadat we de overstap van de SharePoint Online-gegevens hebben voltooid, maar sommige klanten kunnen de eerste 24-48 uur trager maken 
  
De volgende zoekfuncties zijn van invloed op:
  
- Zoekresultaten en zoek webonderdelen: resultaten worden niet meegenomen na de migratie totdat ze de verkenning opvangen. 
    
- Delve: Delve omvat geen wijzigingen die zijn doorgevoerd na de migratie totdat ze de verkenning opvangen.
    
- Populariteits-en zoekrapporten voor de site: aantallen voor Excel-rapporten op de nieuwe locatie zijn alleen gemigreerd van de gemigreerde aantallen en tellingen van gebruiksrapporten die worden uitgevoerd nadat de SharePoint Online-gegevens zijn verplaatst. Het aantal van de tussentijdse periode gaat verloren en kan niet worden hersteld. Deze periode is meestal een paar dagen. Sommige klanten ondervinden mogelijk minder of meer verlies.
    
- Video portal: aantal en statistieken voor de VideoPortal weergeven afhankelijk van de statistieken voor Excel-rapporten, zodat de aantallen en statistieken voor de VideoPortal worden weergegeven voor dezelfde periode als voor de Excel-rapporten.
    
- eDiscovery: items die tijdens de migratie zijn gewijzigd, worden niet weergegeven totdat de wijzigingen worden opgehaald.
    
- Bescherming tegen verlies van gegevens (DLP): beleidsregels worden niet afgedwongen voor items die worden gewijzigd totdat het verkennen de wijzigingen worden opgehaald.

## <a name="microsoft-teams"></a>Microsoft Teams

Behalve Exchange Online, SharePoint Online en OneDrive voor bedrijven migreert Microsoft teams-chatservice gegevens naar het lokale datacenter.

- Chatberichten van teams, inclusief persoonlijke berichten en kanaalberichten.
- Afbeeldingen van teams die in chats worden gebruikt.

Teams-bestanden worden opgeslagen in OneDrive voor bedrijven-en teams-Chat bestanden zijn opgeslagen in OneDrive voor bedrijven. Voicemail, agenda, chatgeschiedenis en contactpersonen worden opgeslagen in Exchange Online. In veel gevallen worden Exchange Online, SharePoint Online en OneDrive voor bedrijven al gebruikt door de klant in het lokale datacenter, en maakt ook deel uit van het Microsoft 365-migratieprogramma voor in aanmerking komende klant landen.

## <a name="skype-for-business"></a>Skype voor Bedrijven

Skype voor bedrijven-verplaatsingen zijn niet meer beschikbaar.  [Skype voor bedrijven online wordt](https://docs.microsoft.com/lifecycle/announcements/skype-for-business-online-retirement) op 31 juli 2021 teruggetrokken. Na die tijd is de service niet langer toegankelijk. 
  
## <a name="related-topics"></a>Verwante onderwerpen 
 
[De verplaatsing van uw gegevens aanvragen](request-your-data-move.md)
    
[Algemene veelgestelde vragen over het verplaatsen van gegevens](data-move-faq.md)
  
[Nieuwe datacenter GEOS voor Microsoft Dynamics CRM Online](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[Azure-Services op regio](https://azure.microsoft.com/regions/)
