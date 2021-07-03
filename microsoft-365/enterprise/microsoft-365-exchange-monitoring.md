---
title: Exchange Online-bewaking voor Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: Gebruik Exchange Online-bewaking voor informatie over e-mailincidenten of -adviezen in Microsoft 365.
ms.openlocfilehash: 3d88378449879d451b21ba8bf2a7b5c3032a2c07
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286439"
---
# <a name="exchange-online-monitoring-for-microsoft-365"></a>Exchange Online-bewaking voor Microsoft 365

Je kunt Exchange Online-bewaking in het Microsoft 365-beheercentrum gebruiken het controleren van de status van de Exchange Online-service voor het Microsoft 365-abonnement van je organisatie. Exchange Online-bewaking biedt informatie over incidenten en adviezen die worden verzameld in deze categorieën:

- **Infrastructuur**: Probleem wordt gedetecteerd in de Microsoft 365-infrastructuur die Microsoft bezit voor regelmatige updates en het probleem op te lossen. Gebruikers kunnen bijvoorbeeld geen toegang tot Exchange Online krijgen vanwege problemen met Exchange of andere Microsoft 365-cloudinfrastructuur.
- **Infrastructuur van derden**: Probleem wordt gedetecteerd in infrastructuur van derden waarvan uw organisatie afhankelijk is en vereist actie van uw organisatie voor een oplossing. Gebruikersverificatietransacties worden bijvoorbeeld beperkt door een externe beveiligingstokenservice (STS)-provider die voorkomt dat gebruikers verbinding maken met Exchange Online.
- **Infrastructuur van klant**: Probleem wordt gedetecteerd in je organisatie-infrastructuur en vereist actie van je organisatie voor een oplossing. Gebruikers kunnen bijvoorbeeld geen toegang tot Exchange Online krijgen omdat ze geen verificatietoken kunnen verkrijgen van de STS-provider die door je organisatie wordt gehost, vanwege een verlopen certificaat.

Hier volgt een voorbeeld van de pagina **Servicestatus** in het Microsoft 365-beheercentrum, beschikbaar via **Status > Servicestatus**.

![De pagina Servicestatus in het Microsoft 365-beheercentrum](../media/microsoft-365-exchange-monitoring/service-health-dashboard-example.png)

De waarde van de kolom **Status** geeft aan of de service in orde is of adviezen of incidenten heeft op basis van de cloudservices die Microsoft onderhoudt. 

De waarde van de kolom **Problemen van uw organisatie en derden** geeft aan dat de infrastructuur van uw organisatie of de software van derden de servicestatuservaring van uw gebruikers met Exchange Online beïnvloedt. Adviezen of incidenten vereisten *uw* acties om te worden opgelost.

Hier volgt een voorbeeld van de **Exchange Online**-bewakingspagina in het Microsoft 365-beheercentrum, beschikbaar via **Status > Servicestatus > Exchange Online**.

![De pagina Exchange Online-bewaking in het Microsoft 365-beheercentrum](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example.png)

Met de **Exchange Online**-bewakingspagina kan je zien of de Exchange-service in orde is en of er gerelateerde incidenten of adviezen zijn. Met Exchange Online-bewaking kan je de servicestatus voor specifieke e-mailscenario's bekijken en signalen in bijna realtime bekijken zodat je de impact per scenario kan bepalen. 

## <a name="requirements"></a>Vereisten

Deze preview is ingeschakeld voor klanten die aan deze vereisten voldoen: 

- De organisatie heeft een licentie nodig voor ten minste 5000 stuks van een van de volgende producten of een combinatie ervan: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. 

  Uw organisatie heeft bijvoorbeeld 3000 Office 365 E3-licenties en 2500 Microsoft 365 E5-licenties, op een totaal van 5500 licenties van in aanmerking komende producten.

- Je organisatie heeft ten minste 50 maandelijks actieve Exchange Online-gebruikers nodig.

Met Exchange-bewaking kan je de status voor de volgende e-mailclients bekijken op basis van de leesactiviteit voor e-mail:

- Outlook Bureaublad
- Webversie van Outlook
- Systeemeigen e-mailclients van iOS en Android 
- Mobiele Outlook-app in iOS en Android 
- Outlook Mac-client

Voor deze clients kunt u het aantal actieve gebruikers in de afgelopen 30 minuten zien op basis van gebruikers die een e-mail lezen, evenals het aantal incidenten en adviezen in het dashboard. Deze gegevens worden vergeleken met hetzelfde interval van de vorige week om te zien of er een probleem is. 

>[!Note]
> Het aantal actieve gebruikers wordt gemeten voor één activiteit, bijvoorbeeld een gebruiker leest een e-mail. Het geldt alleen voor de afgelopen 30 minuten van activiteit.
>

Je kunt de Exchange Online-status ook bewaken voor de volgende scenario's:

- **E-mailstroom**: Het aantal berichten dat zonder vertraging in een postvak is bezorgd nadat het bericht het Microsoft 365-netwerk heeft bereikt. 
- **Basisverificatie en Moderne verificatie**: Het aantal gebruikers dat is gevalideerd in de Exchange Online-service.

![Een voorbeeld van het bewaken van de Exchange-status voor e-mailbezorging](../media/microsoft-365-exchange-monitoring/exhange-monitoring-scenario-example.png)

Voor al deze scenario's zijn de belangrijkste getallen voor de afgelopen 30 minuten in het hoofddashboard. Gedetailleerde weergaven voor elk van deze scenario's tonen de trend in bijna realtime voor zeven dagen met aggregatie van 30 minuten vergeleken met de vorige week. 

## <a name="send-us-feedback"></a>Geef ons feedback

U kunt op twee manieren feedback geven:

- Gebruik de optie **Feedback geven** die beschikbaar is op elke pagina van het Microsoft 365-beheercentrum.
- Verzend feedback met behulp van de koppeling **Is deze post nuttig?** voor een specifiek incident of advies.

![De koppeling 'Is deze post nuttig?' voor een specifiek incident of advies](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example-incident-feedback.png)

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

#### <a name="1-why-dont-i-see-exchange-online-monitoring-under-health-in-the-microsoft-365-admin-center"></a>1. Waarom zie ik 'Exchange Online-bewaking' niet onder Status in het Microsoft 365-beheercentrum? 

Controleer eerst of je het nieuwe beheercentrum hebt ingeschakeld op de **Startpagina** van het Microsoft 365-beheercentrum. 

Controleer vervolgens of je aan beide van de volgende vereisten voldoet: 

- De organisatie heeft een licentie nodig voor ten minste 5000 stuks van een van de volgende producten of een combinatie ervan: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. 
- Uw organisatie heeft ten minste vijftig maandelijks actieve Exchange Online-gebruikers nodig.

Als het aantal licenties voor uw organisatie minder dan 5000 gebruikers telt en het aantal maandelijks actieve gebruikers minder dan 50 gebruikers telt, wordt Exchange Online-bewaking pas ingeschakeld zodra aan deze vereisten wordt voldaan.

#### <a name="2-the-active-user-count-in-the-dashboard-for-each-client-appears-to-be-low-we-have-a-lot-of-active-licenses-assigned-to-users-what-does-this-mean"></a>2. Het aantal actieve gebruikers in het dashboard voor elke client lijkt laag te zijn. We hebben veel actieve licenties aan gebruikers toegewezen. Wat betekent dit? 

Het aantal actieve gebruikers dat in de bewaking wordt weergegeven is gebaseerd op een periode van 30 minuten waarin gebruikers de activiteit hebben uitgevoerd die in de functie is uitgelicht. Dit mag niet worden verward met het gebruiksaantal. Bekijk het gebruiksaantal door activiteitsrapporten te gebruiken in het Microsoft 365-beheercentrum (**Rapporten > Gebruik**).

#### <a name="3-will-there-be-other-monitoring-scenarios-for-other-services-such-as-teams-and-sharepoint"></a>3. Zullen er andere bewakingsscenario's zijn voor andere services zoals Teams en SharePoint? 

Microsoft heeft deze ervaring rechtstreeks geïntegreerd in het dashboard Servicestatus in het Microsoft 365-beheercentrum. Dit zal Microsoft mogelijkheden geven voor het uitbreiden van bewakingsscenario's naar andere services. Dit zal worden aangekondigd wanneer er nieuws over is. 

#### <a name="4-what-is-the-plan-for-general-availability-of-this-experience"></a>4. Wat is het plan voor algemene beschikbaarheid van deze ervaring? 

Microsoft heeft Exchange Online-bewaking rechtstreeks geïntegreerd in het dashboard **Servicestatus** in het Microsoft 365-beheercentrum. 

Met deze nieuwe geïntegreerde ervaring is Microsoft van plan om uw feedback te verzamelen en vervolgens ons plan voor algemene beschikbaarheid te definiëren.

#### <a name="5-is-this-a-free-included-or-paid-extra-feature"></a>5. Is dit een gratis (inbegrepen) of betaalde (extra) functie? 

Deze functie is in openbare preview en alleen beschikbaar voor klanten die voldoen aan de vereisten in vraag 1.

<!--
>[!Note]
>INTERNAL: That decision is pending
>
--> 

#### <a name="6-how-do-i-provide-feedback"></a>6. Hoe kan ik feedback geven? 

Voor algemene feedback gebruik je het pictogram **Feedback geven** in de rechterbenedenhoek van de **Exchange Online**-bewakingspagina. 

Voor feedback over incidenten of adviezen gebruik je de koppeling **Is deze post nuttig?**.

#### <a name="7-where-is-the-data-instrumented-for-the-scenarios-that-show-activity-trends"></a>7. Waar zijn de gegevens voor de scenario‘s die activiteitentrends weergeven geïnstrumenteerd?

De gegevens worden in de Exchange Online-service ondergebracht. Als er een fout optreedt voordat de aanvraag Exchange Online bereikt of als er een fout in Exchange Online optreedt, krijgt u een daling van de activiteit te zien.
