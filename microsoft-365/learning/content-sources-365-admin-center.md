---
title: Leerinhoudsbronnen configureren voor Microsoft Viva Learning (Preview) in het Microsoft 365 beheercentrum
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 04/30/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Informatie over het configureren van bronnen voor leerinhoud voor Microsoft Viva Learning (Preview) in het Microsoft 365 beheercentrum.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: b2e6ab6306db9a5ac9d91226431e5876cc244499
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245418"
---
# <a name="configure-learning-content-sources-for-microsoft-viva-learning-preview-in-the-microsoft-365-admin-center"></a>Leerinhoudsbronnen configureren voor Microsoft Viva Learning (Preview) in het Microsoft 365 beheercentrum

> [!NOTE]
> De informatie in dit artikel heeft betrekking op een voorbeeldproduct dat aanzienlijk kan worden gewijzigd voordat het commercieel wordt uitgebracht. 

De beheerders van het Microsoft 365-beheercentrum kunnen instellingen met betrekking tot Viva Learning (Preview) beheren en de bronnen voor leerinhoud configureren door de rol van kennisbeheerder toe te wijzen aan geselecteerde personen in uw organisatie.

De beheerder selecteert welke andere bronnen van leerinhoud (bijvoorbeeld SharePoint of ondersteunde bronnen van externe inhoudsproviders) beschikbaar zijn voor gebruikers van Viva Learning (Preview). De beheerder configureert deze bronnen om ervoor te zorgen dat de inhoud beschikbaar is voor zoeken en ontdekken en kan worden bekeken door de werknemers die Viva Learning (Preview) gebruiken.

> [!NOTE]
>  Gebruikers melden zich aan bij niet-Microsoft en LinkedIn Learning Pro in een browser of ingesloten viewer. Voor dit geconfigureerde leren gelden de afzonderlijke licentie-, privacy- en servicevoorwaarden tussen uw organisatie en de derde partij, en niet de voorwaarden van Viva Learning (Preview). Voordat u dit type leerproces selecteert, controleert u of er een overeenkomst is gesloten voor uw organisatie en gebruikers.

## <a name="assign-the-knowledge-admin-role-optional"></a>De rol van kennisbeheerder toewijzen (optioneel)

U moet een globale Microsoft 365 zijn om deze taken uit te voeren.

> [!TIP]
> De kennisbeheerder moet redelijk technisch zijn en over bestaande SharePoint-beheerdersreferenties, bij voorkeur iemand die goed bekend is met het onderwijs, leren, trainen of werknemerservaring in de organisatie.

### <a name="add-a-knowledge-admin"></a>Een kennisbeheerder toevoegen

Als u een kennisbeheerder voor Viva Learning (Preview) wilt toevoegen, volgt u de volgende stappen:

1.  Ga in de linkernavigatie van het Microsoft 365 beheercentrum naar **Rollen.**

2.  Selecteer op **de** pagina Rollen op het **tabblad Azure AD** de optie Knowledge **Administrator.**
 
3.  Selecteer in **het deelvenster Kennisbeheerder** **toegewezen beheerders** en selecteer vervolgens **Toevoegen.**

     ![Pagina Rollen in het Microsoft 365 beheercentrum met het deelvenster Kennisbeheerder om een gebruiker toe te voegen.](../media/learning/learning-add-knowledge-admin-1.png)

3.  Selecteer in **het deelvenster** Beheerders toevoegen de persoon die u voor de rol kiest en selecteer **vervolgens Toevoegen.**

     ![Pagina Rollen in het Microsoft 365 beheercentrum met het deelvenster Beheerders toevoegen om een gebruiker toe te voegen.](../media/learning/learning-add-knowledge-admin-2.png)

### <a name="remove-a-knowledge-admin"></a>Een kennisbeheerder verwijderen

Als u een kennisbeheerder voor Viva Learning (Preview) wilt verwijderen, volgt u de volgende stappen:

1.  Ga in de linkernavigatie van het Microsoft 365 beheercentrum naar **Rollen.**

2.  Ga op **de pagina** Rollen naar het tabblad **Azure AD** en selecteer **kennisbeheerder.**
 
3.  Selecteer in **het deelvenster** Kennisbeheerder op **het** tabblad Toegewezen beheerders de optie Verwijderen **en** selecteer vervolgens de persoon die u uit de rol wilt verwijderen. Als u wilt bevestigen, selecteert u **Verwijderen.**

     ![Pagina Rollen in het Microsoft 365 beheercentrum met het deelvenster Toegewezen beheerders om een gebruiker te verwijderen.](../media/learning/learning-remove-knowledge-admin-1.png)

## <a name="configure-settings-for-the-learning-content-sources"></a>Instellingen configureren voor de leerinhoudsbronnen

U moet een globale Microsoft 365 of kennisbeheerder zijn om deze taken uit te voeren.

Als u instellingen wilt configureren voor leerinhoudsbronnen in Viva Learning, volgt u de volgende stappen:

1.  Ga in de linkernavigatie van het Microsoft 365 beheercentrum **naar Instellingen**  >  **Organisatie-instellingen.**

2.  Selecteer op **de pagina Organisatie-instellingen** op het **tabblad Services** de optie Viva **Learning (voorbeeld)**.

     ![Instellingen pagina in het Microsoft 365 beheercentrum met de weergegeven Leer-app.](../media/learning/learning-sharepoint-configure1.png)

3.  Selecteer in **het deelvenster Viva Learning (Preview)** de leerinhoudsbronnen die u wilt configureren voor de organisatie en selecteer vervolgens **Opslaan.**

     ![Leervenster in het Microsoft 365 beheercentrum met opties voor inhoudsbronnen.](../media/learning/learning-sharepoint-configure2.png)

Van alle bestaande leerbronnen zijn sommige standaard ingeschakeld. Deze leerbronnen zijn:

- LinkedIn Learning (gratis inhoud)
- Microsoft Learn
- Microsoft 365 Training

> [!NOTE]
> LinkedIn gratis inhoud wordt verstrekt aan gebruikers onder het LinkedIn-privacybeleid en de gebruikersovereenkomst. LinkedIn ontvangt het IP-adres van de gebruiker, eventuele cookies die eerder door LinkedIn zijn ingesteld, en stelt een nieuwe cookie in om het gebruik van gratis inhoud bij te houden. Gebruikers zijn niet verplicht zich aan te melden met LinkedIn om gratis inhoud te ontvangen.<br><br>
Voor LinkedIn premium-inhoud heeft uw organisatie een abonnement nodig voor uw team om toegang te krijgen tot die inhoud. Gebruikers moeten zich aanmelden bij LinkedIn om toegang te krijgen tot dat leerproces, dat wordt verstrekt onder de voorwaarden van de voorwaarden van uw organisatie en de gebruikersvoorwaarden met LinkedIn.<br><br> Voor inhoud die niet van Microsoft is (behalve gratis LinkedIn-inhoud), moet uw organisatie een abonnement hebben voor uw gebruikers om toegang te krijgen tot die inhoud met een werkaccount voordat u deze verbinding maakt met Viva Learning (Preview). Persoonlijke abonnementen van gebruikers op niet-Microsoft-leerproviders worden niet geïntegreerd met Viva Learning (Preview). Gebruikers melden zich aan bij niet-Microsoft en LinkedIn Learning Pro in een browser of ingesloten viewer. Als gebruikers naar inhoud gaan waar ze geen organisatieabonnement hebben, zien ze mogelijk een providerpagina waar ze zich kunnen registreren voor een afzonderlijk abonnement. Alle niet-Microsoft-leren wordt verstrekt onder de voorwaarden van de niet-Microsoft-provider en niet als onderdeel van Viva Learning. 

Als u een bron voor leerinhoud wilt in- of uitschakelen, schakelt u het selectievakje naast de bron in. Als een bron is ingeschakeld, wordt een vinkje weergegeven.

## <a name="third-party-content-providers"></a>Inhoudsproviders van derden 

De set beschikbare verbonden leerproviders kan op elk moment veranderen. Meer providers zullen deelnemen naarmate het programma groeit. Beschikbare providers kunnen er ook voor kiezen om hun verbinding met Viva Learning (Preview) te stoppen.

### <a name="skillsoft-as-a-content-source"></a>Skillsoft als inhoudsbron  

Voor Viva Learning (Preview) komen gebruikers die Skillsoft hebben ingeschakeld en ervoor kiezen om Skillsoft-inhoud te bekijken, terecht op een Percipio-pagina met de vraag of ze de Percipio-sitenaam van uw organisatie moeten invoeren. Nadat gebruikers de sitenaam van uw organisatie hebben ingevoerd, worden ze doorgestuurd naar de pagina om zich aan te melden bij de Percipio-site van uw organisatie. Gebruikers melden zich aan met hun bestaande referenties en zien de inhoud die ze oorspronkelijk hebben geselecteerd. Gebruikers worden slechts eenmaal gevraagd de naam van de Percipio-site in te geven, totdat hun browsercache is gewist. Als u deze ervaring voor uw gebruikers wilt stroomlijnen, raden we u aan de naam van uw Percipio-site op te geven in interne communicatie die u verzendt over Viva Learning (Preview).

Dit is bedoeld als een tijdelijke ervaring voor preview en we werken samen met Skillsoft om tenantspecifieke integratie in te stellen voor algemene beschikbaarheid, waardoor de stap wordt overgeslagen waarvoor gebruikers de Percipio-sitenaam van uw organisatie moeten verstrekken. 

### <a name="details-on-microsoft-substrate"></a>Details over Microsoft-substraat  

Voor gegevens die u kopieert naar Viva Learning (Preview) van een niet-Microsoft-service (leerprovider of leerbeheersysteem), kunt u die gegevens niet rechtstreeks in Viva Learning (Preview) extraheren, corrigeren of verwijderen. We vernieuwen de gegevens die u importeert van niet-Microsoft-providers om wijzigingen en verwijderingen in de niet-Microsoft-brongegevens weer te geven.

U moet samenwerken met de leverancier van de niet-Microsoft-service voor het openen, corrigeren, verwijderen of extraheren van gegevens onder de licentie-, service- of privacyvoorwaarden van de niet-Microsoft-service. De wijzigingen die daar zijn aangebracht, worden doorgevoerd in de gegevens die zijn verwerkt voor uw gebruik in Viva Learning (Preview) na voltooiing van de gegevensupdatecyclus van de niet-Microsoft-service en Viva Learning (Preview). Als u de verbinding tussen Viva Learning (Preview) en een niet-Microsoft-service uit schakelen, worden alle gegevens die u eerder uit die service hebt geïmporteerd, verwijderd. 

## <a name="next-step"></a>Volgende stap

[Een SharePoint als een bron van leerinhoud configureren voor Microsoft Viva Learning (preview)](configure-sharepoint-content-source.md)