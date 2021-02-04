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
description: Hier vindt u antwoorden op veelgestelde vragen over het verplaatsen van kerngegevens naar een nieuw geografisch Office 365-datacenter.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7e59622e35604ebd9befbbe17a8a125ed15e101
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094653"
---
# <a name="data-move-general-faq"></a>Algemene veelgestelde vragen over het verplaatsen van gegevens

Hier vindt u antwoorden op algemene vragen over het verplaatsen van belangrijke klantgegevens naar een nieuw geografisch datacenter.
  
## <a name="what-customers-are-eligible-to-request-a-move"></a>Welke klanten komen in aanmerking om een overstap aan te vragen?
  
Bestaande commerciële Microsoft 365-klanten die een land hebben geselecteerd dat in aanmerking komt voor het nieuwe datacenter geo, kunnen een overstap aanvragen. Het programma bestaat alleen voor tenants met een in aanmerking komende landcode die is toegewezen aan de Microsoft 365-tenant om belangrijke klantgegevens in rust te migreren voor in aanmerking komende workloads naar het bijbehorende Geografische Microsoft 365-datacenter. Raadpleeg de pagina Hoe u [uw dataverhuising](request-your-data-move.md) aanvraagt om te bevestigen dat het land in aanmerking komt.   

## <a name="how-do-we-define-core-customer-data"></a>Hoe definiëren we basisklantgegevens?
 
Belangrijke klantgegevens is een term die verwijst naar een subset van klantgegevens die zijn gedefinieerd in de Voorwaarden voor [Microsoft Online Services:](https://aka.ms/ost) 
- Exchange Online-postvakinhoud (e-mailberichten, agenda-items en de inhoud van e-mailbijlagen)
- Inhoud van de SharePoint Online-site en de bestanden die op die site zijn opgeslagen
- Bestanden die zijn geüpload naar OneDrive voor Bedrijven 

## <a name="what-is-in-scope-for-teams-migration"></a>Wat is het bereik voor Teams-migratie?

Naast Exchange Online, SharePoint Online en OneDrive voor Bedrijven Microsoft migreert Teams-gegevens naar het lokale datacenter. 
- Teams-chatberichten, waaronder privéberichten en kanaalberichten. 
- Teams-afbeeldingen die worden gebruikt in chats. 

Teams-bestanden worden opgeslagen in SharePoint Online en Teams-chatbestanden worden opgeslagen in OneDrive voor Bedrijven. Voicemail, agenda en contactpersonen worden opgeslagen in Exchange Online. In veel gevallen worden Exchange Online, SharePoint Online en OneDrive voor Bedrijven al gebruikt door de klant in het geografische datacenter en maken ze ook deel uit van het Microsoft 365-migratieprogramma voor landen die hiervoor in aanmerking komen.

## <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a>Op welk punt is de migratie voltooid, zodat de kernklantgegevens van mijn tenant worden opgeslagen in mijn nieuwe geografische regio?

Als gevolg van gedeelde afhankelijkheden tussen Exchange Online en SharePoint Online/OneDrive voor Bedrijven, kan een migratie pas als voltooid worden beschouwd als beide services zijn gemigreerd. Exchange Online en SharePoint Online/OneDrive voor Bedrijven worden vaak op afzonderlijke tijden en onafhankelijk van elkaar gemigreerd. Tenantbeheerders van klanten ontvangen een bevestiging in het Berichtencentrum wanneer elke servicemigratie is voltooid en kunnen de kaart met de gegevenslocatie op elk moment in het beheercentrum bekijken om de belangrijkste klantgegevens in rustlocatie voor elke service te bevestigen.

## <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a>Hoe zorgt u ervoor dat mijn klantgegevens veilig zijn tijdens de overstap en dat er geen downtime is?
  
Gegevensver verplaatste gegevens zijn een back-endservicebewerking met minimale gevolgen voor eindgebruikers. Functies die kunnen worden beïnvloed, worden weergegeven in [Tijdens en na het verplaatsen van uw gegevens.](during-and-after-your-data-move.md) We houden ons aan de Overeenkomst op serviceniveau van [Microsoft Online Services (SLA)](https://go.microsoft.com/fwlink/p/?LinkId=523897) voor beschikbaarheid, dus klanten hoeven zich niet voor te bereiden op of te controleren tijdens de overstap. 
  
Alle Microsoft 365-services uitvoeren dezelfde versies in de datacenters, zodat u kunt rekenen op consistente functionaliteit. Uw service wordt gedurende het hele proces volledig ondersteund.
  
## <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a>Wat is het effect van verschillende services in verschillende geografische regio's?

Sommige van de Microsoft 365-services bevinden zich mogelijk in verschillende geografische regio's voor sommige bestaande klanten en voor klanten die midden in het overstapproces zitten. Onze services worden onafhankelijk van elkaar uitgevoerd en hebben geen invloed op de gebruikerservaring als dit het geval is. Voor het opslaan van gegevens kan een tenantmigratie echter pas als voltooid worden beschouwd als zowel Exchange Online als SharePoint Online/OneDrive voor Bedrijven naar hetzelfde geografische datacenter is gemigreerd.

 ## <a name="where-is-my-core-customer-data-located"></a>Waar bevinden zich mijn kernklantgegevens?

Tenantbeheerders van klanten kunnen de kaart met de gegevenslocatie op elk moment in het beheercentrum bekijken om de kerngegevens van de klant in rust te bevestigen voor elke service, met name voor de tenant.  We publiceren ook de locatie van geografische datacenters, datacenters en locatie van Office 365-klantgegevens op de [interactieve microsoft 365-datacenterkaarten ](https://office.com/datamaps) als referentie voor de huidige standaardklantgegevens op rustlocaties voor nieuwe tenants. U kunt de locatie van uw klantgegevens in rust controleren via de sectie Gegevenslocatie onder uw organisatieprofiel in het Microsoft 365-beheercentrum.  
 
## <a name="when-will-i-be-able-to-request-a-move"></a>Wanneer kan ik een overstap aanvragen?
  
Raadpleeg de pagina [Hoe u de pagina voor het verplaatsen van gegevens aanvraagt](request-your-data-move.md) voor ondersteunde timeframes voor de geografische datacenters.
  
## <a name="how-can-i-request-to-be-moved"></a>Hoe kan ik vragen om te worden verplaatst?
  
In aanmerking komende klanten zien een pagina in hun [Microsoft 365-beheercentrum.](https://admin.microsoft.com/) Zie Hoe [u het verplaatsen van uw gegevens aanvraagt](request-your-data-move.md) voor instructies over hoe u een overstap aanvraagt. 
  
## <a name="can-i-change-my-selection-after-requesting-a-move"></a>Kan ik mijn selectie wijzigen nadat ik een overstap heb gevraagd?
  
Het is niet mogelijk dat wij u uit het proces verwijderen nadat u uw aanvraag hebt ingediend.
  
## <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a>Wat gebeurt er als ik niet vóór de deadline een overstap aanvraag?
  
We kunnen geen migratieaanvragen accepteren na de geopende inschrijvingsperiode.

## <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a>Wat moet ik doen als ik mijn gegevens wil verplaatsen om de netwerkprestaties te verbeteren?
  
Fysieke nabijheid van een Microsoft 365-datacenter biedt geen garantie voor betere netwerkprestaties. Er zijn veel factoren en onderdelen die van invloed zijn op de netwerkprestaties tussen de eindgebruiker en de Microsoft 365-service. Zie Netwerkplanning en prestaties optimaliseren voor [Microsoft 365](network-planning-and-performance.md)voor meer informatie over deze en prestaties optimaliseren.
  
 ## <a name="do-all-the-services-move-their-data-on-the-same-day"></a>Verplaatsen alle services hun gegevens op dezelfde dag?
 
Elke service wordt onafhankelijk verplaatst en verplaatst de gegevens waarschijnlijk op verschillende tijdstippen.
  
 ## <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a>Kan ik kiezen wanneer ik wil dat mijn gegevens worden verplaatst?
 
Klanten kunnen geen specifieke datum selecteren, ze kunnen hun overstap niet uitstellen en we kunnen geen specifieke datum of periode voor de overstap delen.
  
 ## <a name="can-you-share-when-my-data-will-be-moved"></a>Kunt u delen wanneer mijn gegevens worden verplaatst?
  
Gegevensver verplaatste gegevens zijn een back-endbewerking met minimale gevolgen voor eindgebruikers. De complexiteit, precisie en schaal waarop we gegevens moeten verplaatsen binnen een globaal beheerde en geautomatiseerde omgeving, verbieden ons om te delen wanneer een gegevensver verplaatsen naar verwachting zal worden voltooid voor uw tenant of een andere tenant. Klanten ontvangen één bevestiging in het Berichtencentrum per deelnemende service wanneer de gegevensverplaatsing is voltooid. 
  
 ## <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a>Wat gebeurt er als gebruikers services openen terwijl de gegevens worden verplaatst?

Zie [Tijdens en na het verplaatsen van](during-and-after-your-data-move.md) uw gegevens voor een volledige lijst met functies die mogelijk beperkt zijn tijdens gedeelten van het verplaatsen van gegevens voor elke service. 
  
 ## <a name="how-do-i-know-the-move-is-complete"></a>Hoe weet ik of de overstap is voltooid?
  
Bekijk het Microsoft 365-berichtencentrum om te bevestigen dat het verplaatsen van de gegevens van elke service is voltooid. Wanneer de gegevens van elke service worden verplaatst, wordt er een kennisgeving van voltooiing geplaatst, zodat u drie kennisgevingen krijgt over de voltooiing: één voor elk Exchange Online, SharePoint Online en Skype voor Bedrijven Online. U kunt ook de locatie van uw klantgegevens in rust controleren via de sectie Gegevenslocatie onder uw organisatieprofiel in het Microsoft 365-beheercentrum.  
  
## <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a>Ik ben een Microsoft 365-klant in een van de nieuwe geografische datacenters, maar toen ik me heb aangemeld, heb ik een ander land geselecteerd. Hoe kan ik worden verplaatst naar het nieuwe geografische datacenter?

Het is niet mogelijk om het aanmeldingsland te wijzigen dat is gekoppeld aan uw tenant. In plaats daarvan moet u een nieuwe Microsoft 365-tenant met een nieuw abonnement maken en uw gebruikers en gegevens handmatig verplaatsen naar de nieuwe tenant.
  
## <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a>Wat gebeurt er als we bezig zijn met de migratie van e-mailgegevens naar Microsoft 365 tijdens de overstap naar Exchange Online?

Dit is een veelvoorkomende situatie en wordt volledig ondersteund.  Migratie van de cloud tussen geografische datacenters heeft geen invloed op on-premises migraties naar postvakken in de cloud.
  
 ## <a name="can-i-pilot-some-users"></a>Kan ik sommige gebruikers piloten?
  
U kunt een afzonderlijke proef tenant maken om de connectiviteit te testen, maar de proef tenant kan op geen enkele manier worden gecombineerd met uw bestaande tenant.

## <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a>Ik wil niet wachten totdat Microsoft mijn gegevens verplaatst. Kan ik een nieuwe tenant maken en mijzelf verplaatsen?
  
Ja, het proces zal echter niet zo naadloos verlopen als wanneer Microsoft de gegevens verplaatst.
  
Als u een nieuwe tenant maakt nadat het nieuwe geografische datacenter beschikbaar is, wordt de nieuwe tenant gehost in de nieuwe geografische regio. Deze nieuwe tenant staat volledig los van de vorige tenant en u bent verantwoordelijk voor het verplaatsen van alle gebruikerspostvakken, site-inhoud, domeinnamen en andere gegevens. U kunt de naam van de tenant niet van de ene tenant naar de andere verplaatsen. We raden u aan te wachten op het overstapprogramma van Microsoft, omdat we alle instellingen, gegevens en abonnementen voor uw gebruikers gaan verplaatsen.
  
## <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a>Mijn klantgegevens zijn al verplaatst naar een nieuw geografisch datacenter. Kan ik teruggaan?
 
Nee, dit is niet mogelijk. Klanten die zijn verplaatst naar nieuwe geografische datacenters kunnen niet worden terug verplaatst. Als klant in elke regio zult u dezelfde service-, prestatie- en beveiligingscontroles ervaren als voorheen. [Microsoft 365 Multi Geo](https://aka.ms/multi-geo) is voor sommige klanten beschikbaar als een invoeg situatie en hiermee kan één tenant meerdere satellietge geo's maken en gebruikersgegevens verplaatsen naar die geo's met gegevens op locatie.
  
## <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a>Zijn Microsoft 365-tenants die worden gehost in de nieuwe datacenters beschikbaar voor gebruikers buiten het land?
  
Ja. Microsoft onderhoudt een groot, globaal netwerk met openbare internetverbindingen in meer dan 130 locaties in 35 landen over de hele wereld met peering-overeenkomsten met meer dan 2700 internetproviders (ISP's). Gebruikers hebben toegang tot de datacenters, waar ze zich ook bevinden op internet.

## <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a>Mijn tenant heeft de [invoeginstelling Multi Geo geconfigureerd.](https://aka.ms/multi-geo) Kan ik me nog steeds registreren voor mijn tenant in het Microsoft 365-verplaatsprogramma om mijn standaard geo te wijzigen en elke gebruiker die zich niet in een satellietgebied verplaatst naar de nieuwe standaard geo?

Ja, uw tenant komt in aanmerking voor registratie, maar er zijn belangrijke overwegingen, omdat verplaatsen op tenantniveau niet volledig wordt ondersteund voor klanten die Multi-Geo hebben geconfigureerd.

SharePoint Online en OneDrive voor Bedrijven kunnen niet via dit programma migreren naar het nieuwe datacenter op tenantniveau. De klantbeheerder kan OneDrive voor Bedrijven-shares zo configureren dat deze naar een beschikbare regio wordt verplaatst met Multi-Geo, maar de standaardlocatie voor de tenant kan niet worden gewijzigd nadat Multi-Geo is geconfigureerd voor een tenant.

Voor klanten die zich hebben ingeschakeld voor migratie: we verplaatsen alle Exchange Online-postvakken van de huidige standaardlocatie naar de geografische locatie van uw nieuwe lokale datacenter en werken de standaard exchange Online-regio bij. We verplaatsen geen EXO-postvakken die zijn geconfigureerd in Multi Geo-satellietgebieden, om de locatie van satellietregiogegevens te blijven respecteren zoals u had bedoeld. 

## <a name="related-topics"></a>Verwante onderwerpen

[Belangrijke gegevens verplaatsen naar nieuwe geografische datacenters in Microsoft 365](moving-data-to-new-datacenter-geos.md)

[De verplaatsing van uw gegevens aanvragen](request-your-data-move.md)

[Microsoft 365 Multi Geo](https://aka.ms/multi-geo)

[Interactieve Microsoft 365-datacenterkaart](https://office.com/datamaps)

[Ondersteuning voor Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkID=522459)

[Nieuwe geografische datacenters voor Microsoft Dynamics CRM Online](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[Azure-services per regio](https://azure.microsoft.com/regions/)
