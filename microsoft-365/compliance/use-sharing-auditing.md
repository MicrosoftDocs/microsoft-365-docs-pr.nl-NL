---
title: Controle delen gebruiken in het auditlogboek
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.collection:
- M365-security-compliance
- SPO_Content
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: Beheerder kan leren hoe u auditing voor delen gebruikt in Microsoft 365 auditlogboek om resources te identificeren die worden gedeeld met gebruikers buiten hun organisatie.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d26a8022f8d59aeb56a03c50ae546777c882ef7a
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "52161479"
---
# <a name="use-sharing-auditing-in-the-audit-log"></a>Controle delen gebruiken in het auditlogboek

Delen is een belangrijke activiteit in SharePoint Online en OneDrive voor Bedrijven, en wordt veel gebruikt in organisaties. Beheerders kunnen delen controleren in het auditlogboek gebruiken om te bepalen hoe delen wordt gebruikt in hun organisatie. 
  
## <a name="the-sharepoint-sharing-schema"></a>Het schema SharePoint delen

Gebeurtenissen voor delen (met inbegrip van gebeurtenissen met betrekking tot het delen van beleid en koppelingen voor delen) verschillen op één primaire manier van bestands- en mapgerelateerde gebeurtenissen: de ene gebruiker voert een actie uit die van invloed is op een andere gebruiker. Bijvoorbeeld wanneer een resource gebruiker A gebruiker B toegang geeft tot een bestand. In dit voorbeeld is gebruiker A de *waarnemende gebruiker en* gebruiker B de *doelgebruiker.* In het SharePoint bestandsschema is de actie van de waarnemende gebruiker alleen van invloed op het bestand zelf. Wanneer gebruiker A een bestand opent, is de acteergebruiker de enige informatie die nodig is in de **gebeurtenis FileAccessed.** Om dit verschil aan te pakken, is er een afzonderlijk schema, SharePoint schema *delen,* dat meer informatie over het delen van gebeurtenissen vast legt. Dit zorgt ervoor dat beheerders inzicht hebben in wie een resource heeft gedeeld en met de gebruiker met wie de resource is gedeeld. 
  
Het schema Delen bevat twee extra velden in een auditrecord met betrekking tot het delen van gebeurtenissen: 
  
- **TargetUserOrGroupType:** Hiermee wordt aangegeven of de doelgebruiker of groep lid, gast, SharePointGroup, Beveiligingsgroep of Partner is.

- **TargetUserOrGroupName:** Slaat de UPN of naam op van de doelgebruiker of -groep met een resource (Gebruiker B in het vorige voorbeeld). 

Deze twee velden kunnen, naast andere eigenschappen uit het auditlogboekschema, zoals Gebruiker, Bewerking en  Datum, het volledige verhaal vertellen over welke gebruiker welke *resource* heeft gedeeld met wie en *wanneer.*  
  
Er is nog een schema-eigenschap die belangrijk is voor het gedeelde verhaal. Wanneer u de zoekresultaten van het auditlogboek exporteert, worden in de **kolom AuditData** in het geëxporteerde CSV-bestand gegevens over het delen van gebeurtenissen opgeslagen. Wanneer een gebruiker bijvoorbeeld een site deelt met een andere gebruiker, wordt dit bereikt door de doelgebruiker toe te voegen aan een SharePoint groep. De **kolom AuditData** legt deze gegevens vast om beheerders context te bieden. Zie [Stap 2 voor](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) instructies over het parseren van de gegevens in de kolom **AuditData.**

## <a name="sharepoint-sharing-events"></a>SharePoint delen van gebeurtenissen

Delen wordt gedefinieerd door wanneer een gebruiker *(de* waarnemende gebruiker) een resource wil delen met een andere gebruiker (de *doelgebruiker).* Auditrecords met betrekking tot het delen van een resource met een externe gebruiker (een gebruiker die buiten uw organisatie is en geen gastaccount heeft in het Azure Active Directory van uw organisatie) worden geïdentificeerd door de volgende gebeurtenissen, die zijn geregistreerd in het auditlogboek:

- **SharingInvitationCreated:** Een gebruiker in uw organisatie heeft geprobeerd een resource (waarschijnlijk een site) te delen met een externe gebruiker. Dit resulteert in een uitnodiging voor extern delen die naar de doelgebruiker is verzonden. Er wordt op dit moment geen toegang tot de resource verleend.

- **SharingInvitationAccepted:** De externe gebruiker heeft de uitnodiging voor delen geaccepteerd die door de waarnemende gebruiker is verzonden en heeft nu toegang tot de resource.

- **AnonymousLinkCreated:** Er wordt een anonieme koppeling (ook wel een koppeling 'Iedereen' genoemd) gemaakt voor een resource. Omdat een anonieme koppeling kan worden gemaakt en vervolgens gekopieerd, is het redelijk om ervan uit te gaan dat elk document met een anonieme koppeling is gedeeld met een doelgebruiker.

- **AnonymousLinkUsed:** Zoals de naam al aangeeft, wordt deze gebeurtenis geregistreerd wanneer een anonieme koppeling wordt gebruikt om toegang te krijgen tot een resource. 

- **SecureLinkCreated:** Een gebruiker heeft een 'specifieke personenkoppeling' gemaakt om een resource te delen met een bepaalde persoon. Deze doelgebruiker kan iemand zijn die buiten uw organisatie valt. De persoon met wie de resource wordt gedeeld, wordt geïdentificeerd in de auditrecord voor de **gebeurtenis AddedToSecureLink.** De tijdstempels voor deze twee gebeurtenissen zijn nagenoeg identiek.

- **AddedToSecureLink:** Een gebruiker is toegevoegd aan een specifieke personenkoppeling. Gebruik het **veld TargetUserOrGroupName** in deze gebeurtenis om de gebruiker te identificeren die is toegevoegd aan de bijbehorende specifieke personenkoppeling. Deze doelgebruiker kan iemand zijn die buiten uw organisatie valt.

## <a name="sharing-auditing-work-flow"></a>Werkstroom voor auditing delen
  
Wanneer een gebruiker (de waarnemende gebruiker) een resource wil delen met een andere gebruiker (de doelgebruiker), controleert SharePoint (of OneDrive voor Bedrijven) eerst of het e-mailadres van de doelgebruiker al is gekoppeld aan een gebruikersaccount in de adreslijst van de organisatie. Als de doelgebruiker zich in de adreslijst (en heeft een bijbehorend gastgebruikersaccount), doet SharePoint de volgende dingen:
  
-  Direct worden de machtigingen van de doelgebruiker toegewezen om toegang te krijgen tot de resource door de doelgebruiker toe te voegen aan de juiste SharePoint groep en een **gebeurtenis AddedToGroup te** logboeken. 
    
- Hiermee wordt een melding voor delen verzonden naar het e-mailadres van de doelgebruiker.
    
- Registreert een **SharingSet-gebeurtenis.** Deze gebeurtenis heeft een vriendelijke naam van 'Gedeeld bestand, map of site' onder **Activiteiten** voor delen en toegang aanvragen in de activiteiten picker van het zoekprogramma voor auditlogboek. Zie de schermafbeelding in [stap 1.](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file) 
    
Als een gebruikersaccount voor de doelgebruiker zich niet in de adreslijst SharePoint doet u het volgende: 
    
   - Registreert een van de volgende gebeurtenissen op basis van de manier waarop de resource wordt gedeeld:
   
      - **AnonymousLinkCreated**
   
      - **SecureLinkCreated**
   
      - **AddedToSecureLink** 

      - **SharingInvitationCreated** (deze gebeurtenis wordt alleen geregistreerd wanneer de gedeelde resource een site is)
    
   - Wanneer de doelgebruiker de uitnodiging voor delen accepteert die naar hem of haar is verzonden (door op de koppeling in de uitnodiging te klikken), registreert SharePoint een **gebeurtenis sharingInvitationAccepted** en wijst de doelgebruiker machtigingen toe om toegang te krijgen tot de resource. Als de doelgebruiker een anonieme koppeling wordt verzonden, wordt de **gebeurtenis AnonymousLinkUsed** geregistreerd nadat de doelgebruiker de koppeling gebruikt om toegang te krijgen tot de resource. Voor veilige koppelingen wordt een **FileAccessed-gebeurtenis** geregistreerd wanneer een externe gebruiker de koppeling gebruikt om toegang te krijgen tot de resource.

Aanvullende informatie over de doelgebruiker wordt ook vastgelegd, zoals de identiteit van de gebruiker die de uitnodiging heeft ontvangen en de gebruiker die de uitnodiging accepteert. In sommige gevallen kunnen deze gebruikers (of e-mailadressen) verschillen. 

## <a name="how-to-identify-resources-shared-with-external-users"></a>Resources identificeren die met externe gebruikers zijn gedeeld

Een veelvoorkomende vereiste voor beheerders is het maken van een lijst met alle resources die zijn gedeeld met gebruikers buiten de organisatie. Door auditing voor delen in Office 365 gebruiken, kunnen beheerders deze lijst genereren. Deze zijn als volgt.
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>Stap 1: Gebeurtenissen voor delen zoeken en de resultaten exporteren naar een CSV-bestand

De eerste stap is het zoeken in het auditlogboek voor het delen van gebeurtenissen. Zie Het auditlogboek doorzoeken in het beveiligings- & compliancecentrum voor meer informatie (inclusief [de vereiste machtigingen) over het doorzoeken van het auditlogboek.](search-the-audit-log-in-security-and-compliance.md)
  
1. Ga naar [https://protection.office.com](https://protection.office.com).
    
2. Meld u aan met uw werk- of schoolaccount.
    
3. Klik in het linkerdeelvenster van & compliancecentrum op **Zoeken in**   >  **het auditlogboek**.
    
    De **zoekpagina auditlogboek** wordt weergegeven. 
    
4. Klik **onder Activiteiten** op Activiteiten en klik op Activiteiten voor delen en **toegang** aanvragen om te zoeken naar gebeurtenissen die betrekking hebben op delen. 
    
    ![Selecteer onder Activiteiten de optie Activiteiten voor het delen en openen van aanvragen](../media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  Selecteer een datum- en tijdbereik om te zoeken naar de gebeurtenissen voor delen die binnen die periode hebben plaatsgevonden. 
    
6. Klik **op Zoeken** om de zoekopdracht uit te voeren. 
    
7. Wanneer de zoekopdracht is voltooid en de resultaten worden weergegeven, klikt u op **Resultaten exporteren** Alle \> **resultaten downloaden.**
    
    Nadat u de exportoptie hebt geselecteerd, wordt u in een bericht onder aan het venster gevraagd het CSV-bestand te openen of op te slaan.
    
8. Klik **op Opslaan** als \> **en** sla het CSV-bestand op in een map op uw lokale computer. 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a>Stap 2: PowerQuery Editor gebruiken om het geëxporteerde auditlogboek op te maken

De volgende stap is het gebruik van de JSON-transformatiefunctie in de Power Query Editor in Excel om elke eigenschap in de **kolom AuditData** (die bestaat uit een JSON-object met meerdere eigenschappen) te splitsen in een eigen kolom. Hiermee kunt u kolommen filteren om records te bekijken die betrekking hebben op delen

Zie 'Stap 2: Het geëxporteerde auditlogboek opmaken met behulp van power queryeditor' in Records voor auditlogboek exporteren, configureren en weergeven voor [stapsgewijse instructies.](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a>Stap 3: Het CSV-bestand filteren op resources die met externe gebruikers zijn gedeeld

De volgende stap is om de CSV te filteren op de verschillende gebeurtenissen met betrekking tot delen die eerder zijn beschreven in de sectie SharePoint [delen van](#sharepoint-sharing-events) gebeurtenissen. U kunt ook de kolom **TargetUserOrGroupType** filteren om alle records weer te geven waarin de waarde van deze eigenschap **Gast** is. 

Nadat u de instructies in de vorige stap hebt gevolgd om het CSV-bestand voor te bereiden met de PowerQuery-editor, gaat u als volgt te werk:
    
1. Open het Excel bestand dat u hebt gemaakt in stap 2. 

2. Klik op **het** tabblad Start op **Sorteren & filteren** en klik vervolgens op **Filteren.**
    
3. Schakel in de vervolgkeuzelijst Sorteren &  **filter** in de kolom Bewerkingen alle selecties uit, selecteer vervolgens een of meer van de volgende gebeurtenissen met betrekking tot delen en klik vervolgens op **Ok.**
 
   - **SharingInvitationCreated**
   
   - **AnonymousLinkCreated**
   
   - **SecureLinkCreated**
   
   - **AddedToSecureLink** 
    
    Excel worden de rijen weergegeven voor de gebeurtenissen die u hebt geselecteerd.
    
4. Ga naar de kolom **TargetUserOrGroupType** en selecteer deze. 
    
5. Schakel in **de vervolgkeuzelijst Sorteren & filter** alle selecties uit en selecteer vervolgens **TargetUserOrGroupType:Guest** en klik op **Ok.**
    
    Nu Excel de rijen voor het delen van gebeurtenissen en waar de doelgebruiker zich buiten uw organisatie, omdat externe gebruikers worden geïdentificeerd door de waarde **TargetUserOrGroupType:Guest.** 
  
> [!TIP]
> Voor de auditrecords die worden weergegeven, identificeert de **kolom ObjectId** de resource die is gedeeld met de doelgebruiker. bijvoorbeeld  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx` .
