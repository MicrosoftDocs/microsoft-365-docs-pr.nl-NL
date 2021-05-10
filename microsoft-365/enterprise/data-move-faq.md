---
title: Algemene veelgestelde vragen over het verplaatsen van gegevens
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 1f01bc6f-5d37-4d14-bdd3-9d94a1e23e14
f1.keywords:
- NOCSH
description: Antwoorden vinden op veelgestelde vragen (veelgestelde vragen) over het verplaatsen van kerngegevens naar een nieuwe Office 365 datacenter geo.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 46dfdddc50c62970b679a130b3cccf692648cd5c
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52298050"
---
# <a name="data-move-general-faq"></a>Algemene veelgestelde vragen over het verplaatsen van gegevens

Hier vindt u antwoorden op algemene vragen over het verplaatsen van kerngegevens van klanten in rust naar een nieuw datacenter.
  
## <a name="what-customers-are-eligible-to-request-a-move"></a>Welke klanten komen in aanmerking om een overstap aan te vragen?
  
Bestaande Microsoft 365 commerciële klanten die een land hebben geselecteerd dat in aanmerking komt voor het nieuwe datacenter, kunnen een overstap aanvragen. Het programma bestaat alleen voor tenants met een in aanmerking komende landcode die is toegewezen aan de Microsoft 365-tenant om de belangrijkste klantgegevens in rust te migreren voor in aanmerking komende werkbelastingen naar de bijbehorende Microsoft 365 datacenter geo. Raadpleeg de pagina [Gegevens](request-your-data-move.md) verplaatsen aanvragen om te bevestigen dat het land in aanmerking komt.   

## <a name="how-do-we-define-core-customer-data"></a>Hoe definiëren we basisgegevens van klanten?
 
Kerngegevens van klanten is een term die verwijst naar een subset klantgegevens die zijn gedefinieerd in de [Voorwaarden voor Microsoft Online Services:](https://aka.ms/ost) 
- Exchange Online postvakinhoud (e-mail, agenda-items en de inhoud van e-mailbijlagen)
- SharePoint Onlinesite-inhoud en de bestanden die op die site zijn opgeslagen
- Bestanden die zijn geüpload naar OneDrive voor Bedrijven 

## <a name="what-is-in-scope-for-teams-migration"></a>Wat is het bereik voor Teams migratie?

Naast Exchange Online, SharePoint Online en OneDrive voor Bedrijven; Microsoft migreert Teams gegevens naar het lokale datacenter. 
- Teams chatberichten, waaronder privéberichten en kanaalberichten. 
- Teams afbeeldingen die worden gebruikt in chats. 

Teams bestanden worden opgeslagen in SharePoint Online en Teams chatbestanden worden opgeslagen in OneDrive voor Bedrijven. Voicemail, agenda en contactpersonen worden opgeslagen in Exchange Online. In veel gevallen worden Exchange Online, SharePoint Online en OneDrive voor Bedrijven al gebruikt door de klant in de geo van het lokale datacenter en maken ze ook deel uit van het Microsoft 365 migratieprogramma voor in aanmerking komende klantlanden.

## <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a>Op welk moment is mijn migratie voltooid, zodat de belangrijkste klantgegevens van mijn tenant in rust worden opgeslagen in mijn nieuwe geo?

Vanwege gedeelde afhankelijkheden tussen Exchange Online en SharePoint Online/OneDrive voor Bedrijven, kan een migratie pas als voltooid worden beschouwd als beide services zijn gemigreerd. Exchange Online en SharePoint Online/OneDrive voor Bedrijven vaak op afzonderlijke tijden en onafhankelijk van elkaar migreren. Klanttenatiebeheerders ontvangen een bevestiging in het Berichtencentrum wanneer elke servicemigratie is voltooid en kunnen de gegevenslocatiekaart op elk moment in het beheercentrum bekijken om de belangrijkste klantgegevens op rustlocatie voor elke service te bevestigen.

## <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a>Hoe zorgt u ervoor dat mijn klantgegevens veilig zijn tijdens de verhuizing en dat ik geen downtime ervaar?
  
Gegevensverhuising is een back-endservicebewerking met minimale gevolgen voor eindgebruikers. Functies die kunnen worden beïnvloed, worden weergegeven in [Tijdens en na de gegevens verplaatsen.](during-and-after-your-data-move.md) We houden ons aan de [Sla (Microsoft Online Services Service Level Agreement)](https://go.microsoft.com/fwlink/p/?LinkId=523897) voor beschikbaarheid, dus er is niets dat klanten hoeven voor te bereiden of te controleren tijdens de overstap. 
  
Alle Microsoft 365 services uitvoeren dezelfde versies in de datacenters, zodat u verzekerd bent van consistente functionaliteit. Uw service wordt gedurende het hele proces volledig ondersteund.
  
## <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a>Wat is het effect van het hebben van verschillende services in verschillende geografische regio's?

Sommige van de Microsoft 365 services bevinden zich mogelijk in verschillende geografische regio's voor sommige bestaande klanten en voor klanten die zich midden in het verhuisproces bevinden. Onze services worden onafhankelijk van elkaar uitgevoerd en hebben geen invloed op de gebruikerservaring als dit het geval is. Voor gegevensverhuizingsdoeleinden kan een tenantmigratie echter niet als voltooid worden beschouwd totdat zowel Exchange Online als SharePoint Online/OneDrive voor Bedrijven worden gemigreerd naar dezelfde datacenter-geo.

 ## <a name="where-is-my-core-customer-data-located"></a>Waar bevinden zich mijn belangrijkste klantgegevens?

Klanttenatiebeheerders kunnen de gegevenslocatiekaart op elk moment in het beheercentrum bekijken om de belangrijkste klantgegevens op rustlocatie voor elke service te bevestigen, met name voor de tenant.  We publiceren ook de locatie van datacentero's, datacenters en locatie van klantgegevens van Office 365 op de [interactieve datacenterkaarten van Microsoft 365](https://office.com/datamaps) als referentie voor de huidige standaardgegevens van de basisklant op rustlocaties voor nieuwe tenants. U kunt de locatie van uw klantgegevens in rust verifiëren via de sectie Gegevenslocatie onder uw organisatieprofiel in het Microsoft 365 beheercentrum.  
 
## <a name="when-will-i-be-able-to-request-a-move"></a>Wanneer kan ik een verhuizing aanvragen?
  
Raadpleeg de pagina [Gegevens verplaatsen aanvragen](request-your-data-move.md) voor ondersteunde tijdframes voor uw datacenter-geo.
  
## <a name="how-can-i-request-to-be-moved"></a>Hoe kan ik vragen om te worden verplaatst?
  
In aanmerking komende klanten zien een pagina in [hun Microsoft 365 beheercentrum.](https://admin.microsoft.com/) Zie [Uw gegevens verplaatsen aanvragen voor](request-your-data-move.md) instructies over het aanvragen van een verhuizing. 
  
## <a name="can-i-change-my-selection-after-requesting-a-move"></a>Kan ik mijn selectie wijzigen nadat ik om een verhuizing heb gevraagd?
  
Het is voor ons niet mogelijk om u uit het proces te verwijderen nadat u uw aanvraag hebt ingediend.
  
## <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a>Wat gebeurt er als ik geen verhuizing aanvraag vóór de deadline?
  
We kunnen geen aanvragen voor migratie accepteren na de open inschrijvingsperiode.

## <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a>Wat moet ik doen als ik mijn gegevens wil verplaatsen om betere netwerkprestaties te krijgen?
  
Fysieke nabijheid van een Microsoft 365 datacenter is geen garantie voor betere netwerkprestaties. Er zijn veel factoren en onderdelen die van invloed zijn op de netwerkprestaties tussen de eindgebruiker en de Microsoft 365 service. Zie Netwerkplanning en prestatieafstemming voor meer informatie over deze en prestatieafstemming [voor Microsoft 365.](network-planning-and-performance.md)
  
 ## <a name="do-all-the-services-move-their-data-on-the-same-day"></a>Verplaatsen alle services hun gegevens op dezelfde dag?
 
Elke service wordt onafhankelijk van elkaar verplaatst en de gegevens worden waarschijnlijk op verschillende tijdstippen verplaatst.
  
 ## <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a>Kan ik kiezen wanneer ik mijn gegevens wil laten worden verplaatst?
 
Klanten kunnen geen specifieke datum selecteren, ze kunnen hun overstap niet uitstellen en we kunnen geen specifieke datum of tijdsperiode voor de verhuisdatum delen.
  
 ## <a name="can-you-share-when-my-data-will-be-moved"></a>Kunt u delen wanneer mijn gegevens worden verplaatst?
  
Gegevensverbewegingen zijn een back-endbewerking met minimale gevolgen voor eindgebruikers. De complexiteit, precisie en schaal waarmee we gegevens moeten verplaatsen in een wereldwijd beheerde en geautomatiseerde omgeving, kunnen we niet delen wanneer een gegevensverhuis naar verwachting wordt voltooid voor uw tenant of een andere tenant. Klanten ontvangen één bevestiging in het Berichtencentrum per deelnemende service wanneer de gegevensverplaatsing is voltooid. 
  
 ## <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a>Wat gebeurt er als gebruikers services openen terwijl de gegevens worden verplaatst?

Zie [Tijdens en na het](during-and-after-your-data-move.md) verplaatsen van gegevens voor een volledige lijst met functies die mogelijk tijdens gedeelten van de gegevensverhuising voor elke service zijn beperkt. 
  
 ## <a name="how-do-i-know-the-move-is-complete"></a>Hoe weet ik of de overstap is voltooid?
  
Bekijk het Microsoft 365 berichtencentrum om te bevestigen dat de gegevens van elke service zijn verplaatst. Wanneer de gegevens van elke service worden verplaatst, wordt er een melding voor voltooiing geplaatst, zodat u drie voltooiingsinformatie krijgt: één voor Exchange Online, SharePoint Online en Skype voor Bedrijven Online. U kunt ook de locatie van uw klantgegevens in rust verifiëren via de sectie Gegevenslocatie onder uw organisatieprofiel in het Microsoft 365 beheercentrum.  
  
## <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a>Ik ben een Microsoft 365 klant in een van de nieuwe datacenter-geos, maar toen ik me had aangemeld, heb ik een ander land geselecteerd. Hoe kan ik worden verplaatst naar het nieuwe datacenter geo?

Het is niet mogelijk om het aanmeldingsland te wijzigen dat is gekoppeld aan uw tenant. In plaats daarvan moet u een nieuwe tenant Microsoft 365 een nieuw abonnement maken en uw gebruikers en gegevens handmatig verplaatsen naar de nieuwe tenant.
  
## <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a>Wat gebeurt er als we bezig zijn met het migreren van e-mailgegevens Microsoft 365 tijdens de Exchange Online verplaatsen?

Dit is een veelvoorkomende scenario en wordt volledig ondersteund.  Cloudmigratie tussen datacentergeo's heeft geen invloed op on-premises migraties naar cloudpostvakken.
  
 ## <a name="can-i-pilot-some-users"></a>Kan ik sommige gebruikers piloten?
  
U kunt een afzonderlijke proef tenant maken om verbinding te testen, maar de proef tenant kan op geen enkele manier worden gecombineerd met uw bestaande tenant.

## <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a>Ik wil niet wachten totdat Microsoft mijn gegevens verplaatst. Kan ik gewoon een nieuwe tenant maken en mezelf verplaatsen?
  
Ja, maar het proces zal niet zo naadloos verlopen als wanneer Microsoft de gegevens verplaatst.
  
Als u een nieuwe tenant maakt nadat de nieuwe datacenter-geo beschikbaar is, wordt de nieuwe tenant gehost in de nieuwe geo. Deze nieuwe tenant staat volledig los van uw vorige tenant en u bent verantwoordelijk voor het verplaatsen van alle gebruikerspostvakken, site-inhoud, domeinnamen en andere gegevens. Houd er rekening mee dat u de naam van de tenant niet van de ene tenant naar de andere kunt verplaatsen. We raden u aan te wachten op het verhuisprogramma van Microsoft, aangezien we alle instellingen, gegevens en abonnementen voor uw gebruikers verplaatsen.
  
## <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a>Mijn klantgegevens zijn al verplaatst naar een nieuw datacenter. Kan ik teruggaan?
 
Nee, dit is niet mogelijk. Klanten die naar nieuwe geografische datacenters zijn verplaatst, kunnen niet worden terug verplaatst. Als klant in elke geografische regio ervaart u dezelfde kwaliteit van service, prestaties en beveiligingsbesturingselementen als voorheen. [Microsoft 365 Multi Geo](https://aka.ms/multi-geo) is beschikbaar voor sommige klanten als een invoegvoeggebruik en kan één tenant meerdere satellietgeo's maken en gebruikersgegevens verplaatsen naar die geo's met toezeggingen voor gegevenslocatie.
  
## <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a>Zijn Microsoft 365 tenants die worden gehost in de nieuwe datacenters beschikbaar voor gebruikers buiten het land?
  
Ja. Microsoft onderhoudt een groot wereldwijd netwerk met openbare internetverbinding op meer dan 130 locaties in 35 landen over de hele wereld met peering-overeenkomsten met meer dan 2.700 internetproviders (internetproviders). Gebruikers hebben toegang tot de datacenters vanaf de plaats waar ze zich op internet bevinden.

## <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a>Mijn tenant heeft de invoeging [Multi Geo geconfigureerd.](https://aka.ms/multi-geo) Kan ik me nog steeds registreren voor mijn tenant in het Microsoft 365 Move Program om mijn standaard geo te wijzigen en elke gebruiker die zich niet in een satellietgebied in de nieuwe standaardlocatie belandt, te verplaatsen?

Ja, uw tenant komt in aanmerking om zich in te schrijven, maar er zijn belangrijke aandachtspunten omdat de tenantverhuising niet volledig wordt ondersteund voor klanten die Multi-Geo hebben geconfigureerd.

SharePoint Online en OneDrive voor Bedrijven kan niet migreren naar het nieuwe datacenter geo op tenantniveau via dit programma. De klantbeheerder kan OneDrive voor Bedrijven-aandelen configureren om met Multi-Geo naar een beschikbare regio te gaan, maar de standaardlocatie voor de tenant kan niet worden gewijzigd nadat Multi-Geo is geconfigureerd voor een tenant.

Voor klanten die zich voor migratie hebben geselecteerd: we verplaatsen alle Exchange Online postvakken van uw huidige standaard geo naar uw nieuwe lokale datacenter-geo en werken de standaardlocatie Exchange Online bij. We verplaatsen geen EXO-postvakken die zijn geconfigureerd in satellietregio's met meerdere geo's om de gegevenslocatie van satellietregio's te blijven respecteren zoals u hebt bedoeld. 

## <a name="related-topics"></a>Verwante onderwerpen

[Kerngegevens verplaatsen naar nieuwe Microsoft 365 datacenter-geo's](moving-data-to-new-datacenter-geos.md)

[De verplaatsing van uw gegevens aanvragen](request-your-data-move.md)

[Microsoft 365 Multi Geo](https://aka.ms/multi-geo)

[Microsoft 365 interactieve datacenterkaart](https://office.com/datamaps)

[Microsoft 365 Ondersteuning](../business-video/get-help-support.md)

[Nieuwe datacenter-geo's voor Microsoft Dynamics CRM Online](/power-platform/admin/new-datacenter-regions)
  
[Azure-services per regio](https://azure.microsoft.com/regions/)