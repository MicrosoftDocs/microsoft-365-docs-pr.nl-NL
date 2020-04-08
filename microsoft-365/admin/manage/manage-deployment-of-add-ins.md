---
title: Implementatie van Office 365-invoegins beheren in het beheercentrum
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Leer om invoegingen te implementeren voor gebruikers en groepen in uw organisatie met behulp van gecentraliseerde implementatie in het beheercentrum.
ms.openlocfilehash: 74c1ceb8e9d2193e7ad7afd2b339d29d54780517
ms.sourcegitcommit: 732bb72a0b5ae09cb39536185aa29d6097ec72fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2020
ms.locfileid: "43189015"
---
# <a name="manage-deployment-of-office-365-add-ins-in-the-microsoft-365-admin-center"></a>De implementatie van Office 365-invoegtoepassingen in het Microsoft 365-beheercentrum beheren

Met Office-invoegtoepassingen kunt u uw documenten aan uw persoonlijke voorkeur aanpassen en de manier waarop u toegang krijgt tot informatie op internet stroomlijnen (zie [Uw Office-invoegtoepassing gebruiken](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)). Als beheerder u Office-invoegtoepassing implementeren voor de gebruikers in uw organisatie. U dit doen met de functie Gecentraliseerde implementatie in het Microsoft 365-beheercentrum.
  
Gecentraliseerde implementatie is de aanbevolen en meest veelzijdige manier voor de meeste beheerders om invoegtoepassingen te implementeren voor gebruikers en groepen binnen een organisatie. Zie [Bepalen of Gecentraliseerde implementatie van invoegtoepassingen voor uw Office 365-organisatie werkt](centralized-deployment-of-add-ins.md) voor meer informatie over hoe u bepaalt of uw organisatie Gecentraliseerde implementatie kan ondersteunen.
  
Gecentraliseerde implementatie biedt de volgende voordelen:
  
- Een globale beheerder kan een invoegtoepassing rechtstreeks aan een gebruiker toewijzen, aan meerdere gebruikers via een groep, of aan iedereen in de tenant.
    
- Wanneer de betreffende Office-toepassing wordt gestart, wordt de invoegtoepassing automatisch voor de gebruiker gedownload. Als de invoegtoepassing opdrachten voor de invoegtoepassing ondersteunt, wordt de invoegtoepassing automatisch in het lint in de Office-toepassing weergegeven.
    
- Invoegtoepassingen worden niet meer weergegeven voor gebruikers als de beheerder de invoegtoepassing uitschakelt of verwijdert, of als de gebruiker wordt verwijderd uit Azure Active Directory of uit een groep waaraan de invoegtoepassing is toegewezen.
    
> [!NOTE]
>  Gebruik voor Word, Excel en PowerPoint een [SharePoint-app-catalogus](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) om invoegtoepassingen te implementeren voor gebruikers in een on-premises omgeving zonder verbinding met Office 365 en/of zonder dat er ondersteuning voor SharePoint-invoegtoepassingen is vereist. >  Maak voor Outlook gebruik van het Configuratiescherm van Exchange voor de implementatie in een on-premises omgeving zonder verbinding met Office 365. > 
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Aanbevolen werkwijze voor de implementatie van Office-invoegtoepassingen

Overweeg de invoegtoepassingen in fasen uit te rollen om de implementatie goed te laten verlopen. De volgende werkwijze wordt aanbevolen:
  
1. Rol de invoegtoepassing uit naar een klein aantal belanghebbenden in het bedrijf en leden van de IT-afdeling. Controleer of de implementatie goed is verlopen en ga verder met stap 2 als dat het geval is.
    
2. Rol de invoegtoepassing uit naar een grotere groep personen binnen het bedrijf die van de invoegtoepassing gebruik zullen maken. Controleer opnieuw de resultaten en ga als alles goed is verlopen verder met de volgende stap voor een volledige implementatie.
    
3. Rol de invoegtoepassing volledig uit naar de gehele doelgroep.
    
Afhankelijk van de grootte van de doelgroep, kunt u eventueel uitrolstappen toevoegen of verwijderen.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Een Office-invoegtoepassing implementeren met behulp van het beheercentrum

Raadpleeg [Bepalen of Gecentraliseerde implementatie van invoegtoepassingen voor uw Office 365-organisatie werkt](centralized-deployment-of-add-ins.md) voordat u begint.

  
1. Ga in het Microsoft 365-beheercentrum naar de pagina**Invoegtoepassing** **Instellingen.** > 
    
2. Selecteer **Invoegtoepassing implementeren** boven aan de pagina. Selecteer **Volgende**op de overzichtspagina .
    
3. Selecteer een optie en volg de instructies.
  
4. Als u de optie hebt geselecteerd om een invoegtoepassing toe te voegen in de Office Store, u nu uw invoegselectie maken. De beschikbare invoegtoepassingen worden weergegeven in de categorieën **Voorgesteld voor u**, **Beoordeling** en **Naam**. Er kunnen alleen gratis invoegtoepassingen worden toegevoegd vanuit de Office Store. Betaalde invoegtoepassingen worden momenteel niet ondersteund. Zodra u uw invoegtoepassing hebt geselecteerd, moet u akkoord gaan met een aantal aanvullende algemene voorwaarden om verder te gaan. <br/><br/> OPMERKING: Met de office store-optie worden updates en verbeteringen aan de invoegtoepassing automatisch beschikbaar gesteld aan gebruikers zonder uw tussenkomst.

5. Selecteer **op**de volgende pagina Iedereen , **Specifieke gebruikers/groepen** of **Just me** om aan te geven aan wie de invoegtoepassing is geïmplementeerd. Gebruik het vak Zoeken om de gebruikers of groepen te zoeken waarvoor u de invoegtoepassing wilt implementeren. <br/>OPMERKING: Meer informatie over de andere staten die van toepassing zijn op een invoegtoepassing. Zie [Statussen van invoegtoepassingen](#add-in-states) verderop in dit onderwerp.
  
6. Selecteer **Implementeren**.
  
7. Er verschijnt een groen vinkje wanneer de invoegtoepassing is geïmplementeerd. U de instructies op de pagina volgen om te testen of de invoegtoepassing is geïmplementeerd.

> [!NOTE]
> Gebruikers moeten Office mogelijk opnieuw opstarten om het invoegpictogram op het lint van de app te zien verschijnen. Het kan tot 24 uur duren voordat Outlook-invoegins op de linten van gebruikers worden weergegeven.
    
8. Als u klaar bent, selecteert u **Volgende**. Als u alleen bij uzelf bent geïmplementeerd, u Wijzigen selecteren **wie toegang heeft tot invoegtoepassing** om te implementeren voor meer gebruikers.



Als u de invoegtoepassing hebt geïmplementeerd op andere leden van uw organisatie dan uzelf, volgt u de instructies die worden weergegeven om de implementatie van de invoegtoepassing effectief aan te kondigen. <br/>De invoegtoepassing wordt nu samen met andere apps in Office 365 weergegeven.
  
Laat gebruikers en groepen weten dat u de invoegtoepassing hebt geïmplementeerd en dat deze nu voor hen beschikbaar is. U kunt ook een e-mailbericht naar gebruikers en groepen sturen waarin u beschrijft wanneer en hoe de invoegtoepassing kan worden gebruikt en hoe de invoegtoepassing kan helpen hun werk beter te doen. Neem relevante Help-inhoud of veelgestelde vragen op (of een koppeling hiernaartoe) voor het geval gebruikers problemen met de invoegtoepassing hebben.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Overwegingen bij het toewijzen van een invoegtoepassing aan gebruikers en groepen

Beheerders kunnen een invoegtoepassing aan iedereen of aan specifieke gebruikers en groepen toewijzen. Elke optie heeft gevolgen:
  
- **Iedereen**: Zoals de naam al zegt, wordt met deze optie de invoegtoepassing aan elke gebruiker in de tenant toegewezen. Gebruik deze optie niet te vaak en alleen voor invoegtoepassingen die echt universeel voor uw organisatie zijn. 
    
- **Gebruikers**: Als u een invoegtoepassing aan een individuele gebruiker toewijst, moet u bij de implementatie voor een nieuwe gebruiker eerst die gebruiker toevoegen. Hetzelfde geldt voor het verwijderen van gebruikers. 
    
- **Groepen**: Als u een invoegtoepassing aan een groep toewijst, wordt de invoegtoepassing automatisch toegewezen aan gebruikers die aan de groep zijn toegevoegd. En wanneer een gebruiker uit een groep wordt verwijderd, heeft de gebruiker niet langer toegang tot de invoegtoepassing. In beide gevallen hoeft u als beheerder geen extra actie uit te voeren. 

- **Just me:** Als u een add-in toewijst aan alleen uzelf, wijst dit de invoegtoepassing toe aan alleen uw account. Dit is ideaal als u de add-in eerst wilt testen.
    
Welke optie voor uw organisatie geschikt is, is afhankelijk van uw configuratie. U wordt echter aangeraden toewijzingen via groepen te maken. Als beheerder kunt u mogelijk handiger invoegtoepassingen beheren door gebruik te maken van groepen. U kunt dan het lidmaatschap van deze groepen beheren in plaats van dat u telkens de toegewezen gebruikers moet wijzigen. Aan de andere kant wilt u de toegang in sommige gevallen misschien beperken tot een zeer klein aantal gebruikers en geeft u daarom de voorkeur aan toewijzingen voor specifieke gebruikers. U moet de toegewezen gebruikers dan handmatig beheren.
  
### <a name="add-in-states"></a>Statussen van invoegtoepassingen

Beheerders kunnen de invoegingen die ze implementeren voor alle gebruikers vanuit het Microsoft 365-beheercentrum in- of uitschakelen.

1.    Ga in het beheercentrum naar de pagina **Invoegtoepassing**  **Instellingen.** > 
2.    Selecteer de geïmplementeerde invoegtoepassing. 
3.    Klik op de **statusschakelaar** om de in- of **uit-invoegtoepassing** in te schakelen . **Off** 
4.    Sla de wijzigingen op.  

Een van de drie add-in staten is ook beschikbaar.
 
|**Status**|**Hoe de status optreedt**|**Impact**|
|:-----|:-----|:-----|
|**Actief**  <br/> |De beheerder heeft de invoegtoepassing geüpload en toegewezen aan gebruikers of groepen.  <br/> |Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, zien de invoegtoepassing in de desbetreffende clients.  <br/> |
|**Uitgeschakeld**  <br/> |De beheerder heeft de invoegtoepassing uitgeschakeld.  <br/> |Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, hebben niet langer toegang tot de invoegtoepassing.  <br/> Als de invoegstatus wordt gewijzigd in **Actief,** hebben de gebruikers en groepen er weer toegang toe.  <br/> |
|**Verwijderd**  <br/> |De beheerder heeft de invoegtoepassing verwijderd.  <br/> |Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, hebben niet langer toegang tot de invoegtoepassing.  <br/> |
   
Stel dat u een invoegtoepassing verwijdert omdat deze door niemand meer wordt gebruikt. Het uitschakelen van een invoegtoepassing kan zinvol zijn als een invoegtoepassing alleen in bepaalde perioden van het jaar wordt gebruikt.
  
### <a name="security-of-office-add-ins"></a>Beveiliging van Office-invoegtoepassingen

Office-invoegtoepassingen bevatten een XML-manifestbestand dat gegevens over de invoegtoepassing bevat. Het belangrijkste is echter dat het manifestbestand naar een webapplicatie verwijst die alle code en logica bevat. Invoegtoepassingen kennen talloze mogelijkheden. Met behulp van invoegtoepassingen kunt u bijvoorbeeld:
  
- Gegevens weergeven.
    
- Het document van een gebruiker lezen om op context gebaseerde services te bieden.
    
- Gegevens van het document van een gebruiker lezen of er gegevens naar schrijven.
    
Zie [Office Add-ins platform overview](https://go.microsoft.com/fwlink/p/?linkid=846362) (Overzicht van platforms voor Office-invoegtoepassingen), met name de sectie Anatomy of an Office Add-in (Anatomie van een Office-invoegtoepassing).
  
Voor interactie met het document van de gebruiker moet de invoegtoepassing declareren welke machtiging er in het manifest is vereist. Een JavaScript API-model voor toestemming voor toegang bestaande uit vijf niveaus vormt de basis voor privacy en veiligheid voor gebruikers van invoegtoepassingen voor taakvensters. De meeste invoegtoepassingen in de Office Store zijn van het niveau ReadWriteDocument. Vrijwel alle invoegtoepassingen ondersteunen ten minste het niveau ReadDocument. Zie [Requesting permissions for API use in content and task pane add-ins](https://go.microsoft.com/fwlink/p/?linkid=848863) (Machtigingen aanvragen voor API-gebruik in invoegtoepassingen voor inhouds- en taakvensters) voor meer informatie over machtigingsniveaus.
  
Wanneer een manifest wordt bijgewerkt, worden de wijzigingen voornamelijk aangebracht aan het pictogram en de tekst van de invoegtoepassing. Af en toe worden opdrachten van invoegtoepassingen gewijzigd. De machtigingen van de invoegtoepassing worden echter niet gewijzigd. De webtoepassing waar alle code en logica voor de invoegtoepassing wordt uitgevoerd, kan op elk moment worden gewijzigd, wat kenmerkend is voor webtoepassingen.
  
Updates voor invoegtoepassingen worden als volgt uitgevoerd:
  
- **Line-Of-Business-invoegtoepassing:** In dit geval, waarbij een beheerder een manifest expliciet heeft geüpload, wordt vereist dat de beheerder een nieuw manifestbestand uploadt zodat het wijzigen van metagegevens wordt ondersteund. De volgende keer dat de betreffende Office-toepassingen worden gestart, wordt de invoegtoepassing bijgewerkt. De webtoepassing kan elk moment worden gewijzigd. 

    > [!NOTE]
    > Beheerder hoeft geen LOB-invoegtoepassing te verwijderen voor het uitvoeren van een update.   In de sectie Invoegtoepassing kan Beheerder eenvoudig op de LOB-invoegtoepassing klikken en de **knop Bijwerken** in de rechterbenedenhoek kiezen. Update werkt alleen als de versie van de nieuwe invoegtoepassing groter is dan die van de bestaande invoegtoepassing.   
    
- **Office Store-invoegtoepassing:** Als een beheerder een invoegtoepassing in de Office Store heeft geselecteerd (als een invoegtoepassing in de Office Store wordt bijgewerkt), wordt de invoegtoepassing later bijgewerkt in Gecentraliseerde implementatie. De volgende keer dat de betreffende Office-toepassingen worden gestart, wordt de invoegtoepassing bijgewerkt. De webtoepassing kan elk moment worden gewijzigd. 

### <a name="edit-add-in-access"></a>Invoegtoepassing toegang bewerken

Na implementatie kunnen beheerders ook de toegang van de gebruiker tot invoegingen wijzigen.

1. Ga in het beheercentrum naar de pagina **Instellingenservices** > **& invoegingen.**

2. Selecteer de geïmplementeerde invoegtoepassing.

3. Klik op **Bewerken** onder **Wie heeft toegang**.
4. Sla de wijzigingen op.
    
### <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Invoegdownloads voorkomen door de Office Store voor alle clients uit te schakelen (behalve Outlook)

> [!NOTE]
> De installatie van Outlook-invoegtoepassingen wordt beheerd via een [ander proces](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).

Als organisatie kunt u het downloaden van nieuwe Office-invoegtoepassingen vanuit Office Store verhinderen. Dit kunt u doen in combinatie met Gecentraliseerde implementatie om ervoor te zorgen dat alleen invoegtoepassingen die door organisaties zijn goedgekeurd voor gebruikers binnen de organisatie worden geïmplementeerd.
  
Aanschaf van invoegtoepassingen uitschakelen:
  
1. Ga in het beheercentrum naar de pagina**Instellingen** \> [Services &amp; invoegtoepassingen](https://go.microsoft.com/fwlink/p/?linkid=2053743).
    
3. Selecteer **apps en services die eigendom zijn van gebruikers**.
    
4. Schakel de optie uit om gebruikers toegang te geven tot de Office Store.

Hierdoor wordt voorkomen dat alle gebruikers de volgende invoegtoepassingen via de store kunnen aanschaffen.
  
- Invoegtoepassingen voor Word, Excel en PowerPoint 2016 van:
    
  - Windows
    
  - Mac
    
  - Office
    
    
- Aanschaf die begint vanuit **AppSource**
    
- Invoegtoepassingen in Office 365
    
Een gebruiker die toegang tot de store wil hebben, ziet het volgende bericht: **Office 365 is zodanig geconfigureerd om individuele aanschaf van invoegtoepassingen via Office Store te voorkomen.**
  
Ondersteuning voor het uitschakelen van Office Store is beschikbaar in de volgende versies:
  
- Windows: 16.0.9001 - Momenteel beschikbaar.
    
- Mac: 16.10.18011401: momenteel beschikbaar.
    
- iOS: 2.9.18010804: momenteel beschikbaar.
    
- Het web - Momenteel beschikbaar.
    
Hiermee wordt niet voorkomen dat een beheerder Gecentraliseerde implementatie gebruikt om invoegtoepassingen vanuit Office Store toe te wijzen.
  
Om te voorkomen dat een gebruiker zich aanmeldt met een Microsoft-account, kunt u ervoor zorgen dat er alleen kan worden aangemeld met het account van de organisatie. Kijk [hier](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx) voor meer informatie.
 
  
## <a name="minors-and-acquiring-add-ins-from-the-store"></a>Minderjarigen en het verkrijgen van invoegtoepassingen uit de Store

De Algemene Verordening Gegevensbescherming (AVG) is een Europese verordening die in werking treedt op 25 mei 2018. De AVG biedt gebruikers rechten en beveiliging van hun gegevens. Eén van de aspecten van de AVG is dat persoonsgegevens van minderjarigen niet kunnen worden verzonden naar partijen die niet zijn goedgekeurd door de ouders of voogd. Wat de specifieke leeftijd is om iemand als minderjarig aan te merken, hangt af van het gebied waar de persoon zich bevindt.
  
In de Verenigde Staten, Zuid-Korea, het Verenigd Koninkrijk en de Europese Unie zijn er bijvoorbeeld wettelijke voorschriften voor ouderlijke toestemming. In deze gebieden wordt een minderjarige geblokkeerd (via Azure Active Directory) om nieuwe Office-invoegtoepassingen in de Store te verkrijgen en eerder aangeschafte invoegtoepassingen uit te voeren. In landen zonder wettelijke voorschriften zijn er geen downloadbeperkingen.
  
Een gebruiker wordt als minderjarige aangemerkt op basis van gegevens die zijn opgegeven in Azure Active Directory. De tenantbeheerder is er verantwoordelijk voor om de wettelijke leeftijdsgroep en de ouderlijke toestemming voor die gebruiker op te geven.
  
Als de ouders of voogd toestaan dat een minderjarige een bepaalde invoegtoepassing gebruikt, kan de tenantbeheerder gecentraliseerde implementatie gebruiken om deze invoegtoepassing te implementeren voor alle minderjarigen die toestemming hebben.
  
Als u wilt dat uw school of organisatie voldoet aan de AVG-vereisten voor minderjarigen, moet een van de volgende versies van Office zijn geïmplementeerd in uw school/organisatie.
  
 **Voor Word, Excel, PowerPoint en Project**: 
  
|||
|:-----|:-----|
|**Platform** <br/> |**Buildnummer** <br/> |
|Office 2016 ProPlus maandelijks voor Windows  <br/> |9001.2138   <br/> |
|Office 2016 ProPlus halfjaarlijks  <br/> |8431.2159  <br/> |
|Office 2016 voor Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 voor Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 voor Mac  <br/> |16.11.18020200  <br/> |
|Office voor internet  <br/> |N.v.t.  <br/> |
   
 **Voor Outlook**: 
  
|||
|:-----|:-----|
|**Platform** <br/> |**Buildnummer** <br/> |
|Outlook 2016 voor Windows (MSI)  <br/> |Buildnummer n.t.b.  <br/> |
|Outlook 2016 voor Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 voor Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook Mobile voor iOS  <br/> |2.75.0  <br/> |
|Outlook Mobile voor Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |N.v.t.  <br/> |
   
 **Vereisten voor Office 2013**
  
Word, Excel en PowerPoint 2013 voor Windows ondersteunen dezelfde secundaire controles als Active Directory Authentication Library (ADAL) is ingeschakeld. Er zijn twee opties voor naleving, zoals hierna wordt beschreven.
  
- **ADAL inschakelen**. In dit artikel wordt uiteengezet hoe u ADAL voor Office 2013 kunt inschakelen: [Using Office 365 modern authentication with Office clients](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a).<br/>U hebt ook de registersleutels nodig om ADAL in te schakelen, zoals wordt beschreven in [Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten](../security-and-compliance/enable-modern-authentication.md).<br/>Daarnaast moet u deze updates van april voor Office 2013 installeren:
    
  - [Beschrijving van de beveiligingsupdate voor Outlook 2013: 10 april 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [3 april 2018, update voor Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Schakel ADAL niet in.** Als u ADAL niet kunt inschakelen in Office 2013, bevelen wij aan om Groepsbeleid te gebruiken om de Store voor de Office-clients uit te schakelen. Informatie over het uitschakelen van de app voor Office-instellingen vindt u [hier](https://technet.microsoft.com/library/cc178992.aspx).
    
## <a name="end-user-experience-with-add-ins"></a>Ervaring van eindgebruikers met invoegtoepassingen

Nu u de invoegtoepassing hebt geïmplementeerd, kunnen uw eindgebruikers deze gaan gebruiken in hun Office-toepassingen (zie [Uw Office-invoegtoepassing gebruiken](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)). De invoegtoepassing wordt weergegeven op alle platforms die de invoegtoepassing ondersteunen.
  
Als de invoegtoepassing opdrachten van de invoegtoepassing ondersteunt, verschijnen de opdrachten in het Office-lint. In het volgende voorbeeld wordt de opdracht **Bronvermelding zoeken** weergegeven voor de invoegtoepassing **Bronvermeldingen**. 

![Office-lint met zoekcitaten](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Als de geïmplementeerde invoegtoepassing geen ondersteuning biedt voor opdrachten van de invoegtoepassing of als u alle geïmplementeerde invoegtoepassingen wilt weergeven, kunt u ze weergeven via **Mijn invoegtoepassingen**. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>In Word 2016, Excel 2016 of PowerPoint 2016

1. Selecteer ** \> Mijn invoegingen invoegen**. 
    
2. Selecteer het tabblad **Beheerd door beheerder** in het venster Office-invoegtoepassingen. 
    
3. Dubbelklik op de invoegtoepassing die u eerder hebt geïmplementeerd (in dit voorbeeld **Bronvermeldingen** ). <br/>![Tabblad Beheerd beheer van office-invoegtoepassing](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>In Outlook

1. Selecteer op het lint **Start** de optie **Invoegtoepassing ophalen**.<br/>![Knop Store in Outlook](../../media/getaddinsicon.png)
  
2. Selecteer **Beheerd beheerd door beheerders** in de linkernavigatie.

## <a name="delete-the-add-in"></a>De invoegtoepassing verwijderen

U ook een invoegtoepassing verwijderen die is geïmplementeerd.

1. Ga in het beheercentrum naar de pagina **Instellingenservices** > **& invoegingen.**

2. Selecteer de geïmplementeerde invoegtoepassing.

3. Klik op **Invoegtoepassing verwijderen**. Verwijder de knop Invoegtoepassing rechtsonder.
4. Valideer uw selecties en kies **Invoegtoepassing verwijderen**.
  
## <a name="learn-more"></a>Meer informatie

Lees meer over het maken en bouwen van [Office-invoegtoepassingen](https://go.microsoft.com/fwlink/p/?linkid=846362).
  
[Gebruik gecentraliseerde PowerShell-cmdlets voor het beheren van invoegingen.](https://support.office.com/article/94f4e86d-b8e5-42dd-b558-e6092f830ec9)
  
[Problemen oplossen: gebruiker die geen invoegingen ziet](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
