---
title: Algemene veelgestelde vragen over het verplaatsen van gegevens
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 1f01bc6f-5d37-4d14-bdd3-9d94a1e23e14
f1.keywords:
- NOCSH
description: Hier vindt u antwoorden op veelgestelde vragen over het verplaatsen van kerngegevens naar een nieuw Office 365 datacenter-geografische.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 043c5ee5206b30cbbc656c8886c806c2b7c2361c
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333568"
---
# <a name="data-move-general-faq"></a>Algemene veelgestelde vragen over het verplaatsen van gegevens

Hier vindt u antwoorden op algemene vragen over het verplaatsen van kern klantgegevens op rest naar een nieuw datacenter-geo.
  
## <a name="what-customers-are-eligible-to-request-a-move"></a>Welke klanten komen in aanmerking om een verplaatsing te aanvragen?
  
Bestaande commerciële Microsoft 365-klanten die in aanmerking komen voor het nieuwe datacenter centrum, kunnen een verhuizing indienen.  Het programma bestaat alleen voor tenants met een in aanmerking komend landcode die is toegewezen aan de Microsoft 365-Tenant om kern klantgegevens te migreren naar het overeenkomstige Microsoft 365 datacenter.  Kijk op de pagina [hoe u uw gegevens verhuizing vraagt](request-your-data-move.md) om te bevestigen dat de landen in aanmerking komen.   

## <a name="how-do-we-define-core-customer-data"></a>Hoe definiëren we kerngegevens van klanten?
 
De belangrijkste klantgegevens zijn een term die verwijst naar een subset van klantgegevens die zijn gedefinieerd in de [Microsoft Online Services-voorwaarden](https://aka.ms/ost): 
- Postvak inhoud van Exchange Online (e-mail hoofdtekst, agenda-items en de inhoud van e-mailbijlagen)
- Site-inhoud van SharePoint Online en de bestanden die zijn opgeslagen op deze site
- Bestanden die zijn geüpload naar OneDrive voor bedrijven 

## <a name="what-is-in-scope-for-teams-migration"></a>Wat is de omvang van het migreren van teams?

Naast Exchange Online, SharePoint Online en OneDrive voor bedrijven; Microsoft migreert teams-gegevens naar het lokale datacenter.  
- Chatberichten van teams, inclusief persoonlijke berichten en kanaalberichten. 
- Afbeeldingen van teams die in chats worden gebruikt. 

Teams-bestanden worden opgeslagen in OneDrive voor bedrijven-en teams-Chat bestanden zijn opgeslagen in OneDrive voor bedrijven.  Voicemail, agenda, chatgeschiedenis en contactpersonen worden opgeslagen in Exchange Online.  In veel gevallen worden Exchange Online, SharePoint Online en OneDrive voor bedrijven al gebruikt door de klant in het lokale datacenter, en maakt ook deel uit van het Microsoft 365-migratieprogramma voor in aanmerking komende klant landen.

## <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a>Op welk moment is mijn migratie voltooid, zodat de primaire klantgegevens van mijn Tenant worden opgeslagen op een plaats in de nieuwe geo?

Vanwege gedeelde afhankelijkheden tussen Exchange Online en SharePoint Online/OneDrive voor bedrijven, kan alle migratie niet worden voltooid wanneer beide services worden gemigreerd.  Exchange Online en SharePoint Online/OneDrive voor bedrijven worden vaak overal van elkaar gemigreerd en apart.  Tenantbeheerders van klanten ontvangen een bevestiging in het berichtencentrum wanneer elke Service migratie is voltooid en de kaart voor gegevenslocaties op elk moment kan weergeven in het Beheercentrum om de belangrijkste klantgegevens op plaats te bevestigen voor elke service.

## <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a>Hoe zorgt u ervoor dat de gegevens van mijn klant veilig zijn tijdens de verhuizing en dat ik geen tijd meer heb?
  
Gegevens verplaatsen is een back-end-servicebewerking met minimale impact voor eindgebruikers. Functies die kunnen worden beïnvloed, worden weergegeven in [en na het verplaatsen van uw gegevens](during-and-after-your-data-move.md). We houden aan de [Service overeenkomst voor Microsoft Online Services (Sla)](https://go.microsoft.com/fwlink/p/?LinkId=523897) voor de beschikbaarheid, zodat klanten niets moeten voorbereiden op de overstap en deze kunnen volgen. 
  
Alle Microsoft 365-Services voeren dezelfde versies uit in het datacenter, zodat u kunt garanderen dat u beschikt over de consistente functionaliteit. Uw service wordt in het hele proces volledig ondersteund.
  
## <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a>Wat is het effect van het hebben van verschillende services in verschillende GEOS?

Sommige van de services van Microsoft 365 bevinden zich mogelijk in verschillende GEOS voor sommige bestaande klanten en voor klanten in het midden van het verplaatsings proces. Onze diensten werken afzonderlijk van elkaar en er is geen invloed op de gebruikerservaring als dit het geval is.Voor data-woonplaats is het echter niet mogelijk om een Tenant migratie als voltooid te beschouwen totdat Exchange Online en SharePoint Online/OneDrive voor bedrijven worden gemigreerd naar hetzelfde datacenter geo.

 ## <a name="where-is-my-core-customer-data-located"></a>Waar bevinden zich mijn kerngegevens van klanten?

Tenantbeheerders van klanten kunnen op elk gewenst moment de kaart voor gegevenslocaties weergeven in het Beheercentrum om de belangrijkste klantgegevens op plaats te bevestigen voor elke service, specifiek voor hun Tenant.We publiceren ook de locatie van datacenter GEOS, datacenters en locatie van Office 365 CustomerData op het [Microsoft 365 Interactive datacenter ](https://office.com/datamaps) , als referentie voor de huidige standaard basisgegevens voor de primaire klant op rest locaties voor nieuwe tenants.  U kunt de locatie van uw klantgegevens op hun plaats controleren via de sectie gegevenslocatie onder uw organisatieprofiel in het Microsoft 365-Beheercentrum.  
 
## <a name="when-will-i-be-able-to-request-a-move"></a>Wanneer kan ik een verhuizing aanvragen?
  
Kijk naar de pagina [hoe u uw gegevens verhuizing aanvraagt](request-your-data-move.md) voor ondersteunde tijds gebieden voor uw datacenter geo.
  
## <a name="how-can-i-request-to-be-moved"></a>Hoe kan ik verzoeken om te worden verplaatst?
  
In aanmerking komende klanten zien een pagina in het [Microsoft 365-Beheercentrum](https://admin.microsoft.com/). Lees [hoe u uw gegevens kunt](request-your-data-move.md) aanwijzen voor instructies over het aanvragen van een verhuizing. 
  
## <a name="can-i-change-my-selection-after-requesting-a-move"></a>Kan ik mijn selectie wijzigen na een verzoek om een verplaatsing?
  
Het is niet mogelijk dat wij u uit het proces verwijderen nadat u uw aanvraag hebt verzonden.
  
## <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a>Wat gebeurt er als ik geen overgang aanvragen voor de deadline?
  
We kunnen geen aanvragen voor de migratie accepteren na de open registratieperiode.

## <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a>Wat moet ik doen als ik mijn gegevens wil verplaatsen om betere netwerkprestaties te kunnen bereiken?
  
De fysieke nabijheid van een datacenter van Microsoft 365 biedt geen garanties voor een betere prestaties van het netwerk. Er zijn veel factoren en onderdelen die van invloed zijn op de prestaties van het netwerk tussen de eindgebruikers en de Microsoft 365-service. Zie [netwerk planning en prestaties optimaliseren voor Microsoft 365](network-planning-and-performance.md)voor meer informatie over deze en prestaties optimaliseren.
  
 ## <a name="do-all-the-services-move-their-data-on-the-same-day"></a>Worden de gegevens van alle services op dezelfde dag verplaatst?
 
Elke service verplaatst afzonderlijke en verplaatste de gegevens waarschijnlijk op verschillende momenten.
  
 ## <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a>Kan ik kiezen wanneer ik wil dat mijn gegevens worden verplaatst?
 
Klanten kunnen geen specifieke datum selecteren, ze kunnen hun verhuizing niet vertragen en kunnen geen specifieke datum of periode voor de verhuizing delen.
  
 ## <a name="can-you-share-when-my-data-will-be-be-moved"></a>Kunt u delen wanneer mijn gegevens worden verplaatst?
  
Gegevens worden verplaatst met een back-end-bewerking met minimale gevolgen voor eindgebruikers. De complexiteit, nauwkeurigheid en schaal waarop gegevens in een wereldwijde en geautomatiseerde omgeving moeten worden verplaatst, kunnen niet delen wanneer een Data verplaatsing naar verwachting wordt voltooid voor de Tenant of een andere afzonderlijke Tenant. Klanten ontvangen één bevestiging in berichtencentrum per deelnemende dienst, wanneer het verplaatsen van gegevens is voltooid. 
  
 ## <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a>Wat gebeurt er als gebruikers toegang krijgen tot services terwijl de gegevens worden verplaatst?

Bekijk [tijdens en nadat de gegevens zijn verplaatst](during-and-after-your-data-move.md) voor een volledige lijst met functies die kunnen worden beperkt tijdens de verplaatsing van gegevens voor elke service. 
  
 ## <a name="how-do-i-know-the-move-is-complete"></a>Hoe weet ik dat de overstap is voltooid?
  
Bekijk het berichtencentrum van Microsoft 365 om te bevestigen dat de verhuizing van de gegevens van elke service is voltooid. Wanneer de gegevens van alle services worden verplaatst, plaatsen we een melding voor de voltooiing, zodat u drie meldingen krijgt: één voor Exchange Online, SharePoint Online en Skype voor bedrijven online.  U kunt ook de locatie van uw klantgegevens op een plaats controleren via de sectie gegevenslocatie onder uw organisatieprofiel in het Microsoft 365-Beheercentrum.  
  
## <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a>Ik ben een Microsoft 365-klant in een van de nieuwe datacenter GEOS, maar wanneer ik me heb geregistreerd, heb ik een ander land geselecteerd. Hoe kan ik naar de nieuwe datacenter-geografische verplaatsen?

Het is niet mogelijk om het land te wijzigen dat aan uw Tenant is gekoppeld. In plaats daarvan moet u een nieuwe Microsoft 365-Tenant met een nieuw abonnement maken en uw gebruikers en gegevens handmatig verplaatsen naar de nieuwe Tenant.
  
## <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a>Wat gebeurt er als er een e-mail gegevensmigratie naar Microsoft 365 wordt uitgevoerd tijdens de verhuizing van Exchange Online?

Dit is een zeer veelvoorkomend scenario en wordt volledig ondersteund.  Cloud migratie tussen datacenter GEOS verstoort geen enkele on-premisis-migratie van Cloud postvakken.
  
 ## <a name="can-i-pilot-some-users"></a>Kan ik sommige gebruikers prototypen?
  
U kunt een afzonderlijke proef Tenant maken om de verbinding te testen, maar de Tenant voor de proefversie kan niet op een andere manier worden gecombineerd met uw bestaande Tenant.

## <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a>Ik wil niet wachten tot Microsoft de gegevens verplaatst. Kan ik gewoon een nieuwe Tenant maken en deze verplaatsen?
  
Ja, maar het proces is niet zo perfect als wanneer Microsoft de gegevensverplaatsing gaat uitvoeren.
  
Als u een nieuwe Tenant maakt nadat de nieuwe datacenter geo beschikbaar is, wordt de nieuwe Tenant gehost in de nieuwe geo. Deze nieuwe Tenant is helemaal los van uw vorige Tenant en u bent verantwoordelijk voor het verplaatsen van alle gebruikerspostvakken, site-inhoud, domeinnamen en andere gegevens. Houd er rekening mee dat u de naam van de Tenant niet van de ene naar de andere Tenant kunt verplaatsen. We raden u aan te wachten op het Microsoft-programma voor het verplaatsen van uw gebruikers, omdat we alle instellingen, gegevens en abonnementen voor uw gebruikers overzetten.
  
## <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a>Mijn klantgegevens zijn al verplaatst naar een nieuw datacenter-geo. Kan ik teruggaan?
 
Nee, dit is niet mogelijk. Gebruikers die zijn verplaatst naar nieuwe geo-datacenters, kunnen niet meer worden teruggezet. Als klant van enige geo hebt u dezelfde kwaliteit van service, prestatie en beveiligingsfuncties zoals u eerder hebt gebruikt.  [Microsoft 365 multi geo](https://aka.ms/multi-geo) is voor sommige klanten beschikbaar als een invoegtoepassing en biedt een enkele Tenant voor het maken van meerdere Satellite GEOS en het verplaatsen van gebruikersgegevens naar die GEOS met data woonplaats toezeggingen.
  
## <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a>Worden Microsoft 365-tenants in de nieuwe datacenters beschikbaar voor gebruikers buiten het land?
  
Ja. Microsoft houdt een groot mondiaal netwerk bij met openbare internetverbindingen in meer dan 130 locaties in 35 landen overal ter wereld met peering-overeenkomsten met meer dan 2.700 Internet service providers. Gebruikers hebben toegang tot het datacenter, ongeacht waar ze zich bevinden op internet.

## <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a>Mijn Tenant heeft de [invoegtoepassing voor meervoudige geo](https://aka.ms/multi-geo)geconfigureerd. Kan ik nog steeds registreren in mijn Tenant in het Microsoft 365-programma voor verplaatsen om mijn standaard geo te wijzigen en geen gebruikers in een satelliet gebied naar de nieuwe standaard geo te verplaatsen?

Ja, uw Tenant komt in aanmerking om u aan te melden, maar er zijn belangrijke aandachtspunten voor de verhuizing van tenantniveau wordt niet volledig ondersteund voor klanten die meerdere geografische niveaus hebben geconfigureerd.

SharePoint Online en OneDrive voor bedrijven kunnen niet worden gemigreerd naar de nieuwe datacenter-geografische versie op tenantniveau via dit programma.  De klant beheerder kan delen van OneDrive voor bedrijven configureren om naar elk gewenst gebied te gaan met behulp van multi-geografische gebieden, maar de standaardlocatie voor de Tenant kan niet worden gewijzigd nadat meerdere geografische gebruikers voor een Tenant zijn geconfigureerd.

Voor klanten die inbellen bij een migratie, verplaatsen we alle Exchange Online-postvakken van uw huidige standaard geografische geo naar uw nieuwe lokale datacenter, en werken de standaard Exchange Online regio bij.  We verplaatsen geen EXO-postvakken die zijn geconfigureerd in gebieden met een meervoudige geo-satelliet om rekening te houden met de satelliet regiogegevens woonplaats zoals u dat wilt.  

## <a name="related-topics"></a>Verwante onderwerpen

[Basisgegevens verplaatsen naar nieuwe Microsoft 365 datacenter GEOS](moving-data-to-new-datacenter-geos.md)

[De verplaatsing van uw gegevens aanvragen](request-your-data-move.md)

[Microsoft 365 multi geo](https://aka.ms/multi-geo)

[Microsoft 365 Interactive datacenter kaart](https://office.com/datamaps)

[Ondersteuning voor Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkID=522459)

[Nieuwe datacenter GEOS voor Microsoft Dynamics CRM Online](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[Azure-Services op regio](https://azure.microsoft.com/regions/)
