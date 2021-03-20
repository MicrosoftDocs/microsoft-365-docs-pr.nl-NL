---
title: De opties Standaard of Targeted Release instellen
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Meer informatie over het instellen van de releaseoptie voor nieuwe product- en functiesupdates in het Microsoft 365-beheercentrum.
ms.openlocfilehash: f500aac89495c55d27fc4afb699254653786422d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915204"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>De opties Standaard of Targeted Release instellen

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

> [!IMPORTANT]
> De microsoft 365-updates die in dit artikel worden beschreven, zijn van toepassing op Microsoft 365, SharePoint Online en Exchange Online. Deze releaseopties zijn doelgerichte manieren om wijzigingen in Microsoft 365 vrij te geven, maar kunnen niet altijd of voor alle updates worden gegarandeerd. Ze zijn niet van toepassing op Microsoft 365-apps, Skype voor Bedrijven, Microsoft Teams en gerelateerde services. Zie Overzicht van updatekanalen voor Microsoft 365-apps voor informatie over releaseopties voor [Microsoft 365-apps.](/deployoffice/overview-update-channels)

Met Microsoft 365 ontvangt u nieuwe productupdates en -functies zodra deze beschikbaar komen in plaats van om de paar jaar dure updates uit te voeren. U kunt beheren hoe uw organisatie deze updates ontvangt. U kunt u bijvoorbeeld registreren voor een vroege release, zodat uw organisatie updates als eerste ontvangt. U kunt bepaalde personen aanwijzen die als enigen de updates ontvangen. Of u blijft het standaardreleaseschema volgen en ontvangt de updates later. In dit artikel worden de verschillende releaseopties beschreven en wordt uitgelegd hoe u deze voor uw organisatie kunt gebruiken.

## <a name="how-it-works---release-validation"></a>Hoe het werkt: validatie van releases

Een nieuwe release wordt eerst getest en gevalideerd door het functieteam, vervolgens door het hele Microsoft 365-functieteam, gevolgd door heel Microsoft. Na intern testen en valideren bestaat de volgende stap uit een **Targeted Release** (eerder bekend als First Release) voor klanten die zich aanmelden. Bij elke release-ring verzamelt Microsoft feedback en valideert de kwaliteit verder door belangrijke gebruiksgegevens te controleren. Deze reeks van toenemende validatie is ingesteld om er voor te zorgen dat de mondiale release zo robuust mogelijk is. De releases worden in de volgende afbeelding geïllustreerd. 
  
![Releasevalidatieringen voor Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
Voor belangrijke updates krijgen klanten in eerste instantie een melding via de [Routekaart voor Microsoft 365.](https://products.office.com/business/office-365-roadmap) Naarmate een update dichter bij de uitrol komt, wordt deze gecommuniceerd via uw [Microsoft 365-berichtencentrum.](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)

> [!NOTE]
> U hebt een Microsoft 365- of Azure AD-account nodig om toegang te krijgen tot uw Berichtencentrum via [het beheercentrum.](/office365/admin/admin-overview/about-the-admin-center) Gebruikers van een Microsoft 365 Home-abonnement hebben geen beheercentrum.


## <a name="standard-release"></a>Standard Release

Dit is de standaardoptie waarbij u en uw gebruikers de meest recente updates ontvangen wanneer ze breed worden uitgebracht voor alle klanten.
  
Een goede gewoonte is om de meerderheid van de gebruikers in standard release en **IT-professionals** en power users achter te laten in **targeted release** om nieuwe functies te evalueren en teams voor te bereiden om zakelijke gebruikers en leidinggevenden te ondersteunen. 
  
> [!NOTE]
> Als u van het First Release-programma teruggaat naar het Standard Release-programma, hebben uw gebruikers mogelijk geen toegang meer tot functies die nog niet zijn opgenomen in het Standard Release-programma. 
  
## <a name="targeted-release"></a>Targeted Release

Met deze optie zien u en uw gebruikers als eersten de nieuwste updates en kunt u helpen het product te vormen door vroege feedback te geven. U kunt bepalen of de vroege updates naar afzonderlijke personen of naar de hele organisatie worden gestuurd.
  
> [!IMPORTANT]
> Bij grote of complexe updates duurt dit mogelijk langer dan bij andere updates zodat er geen gebruikers negatief worden beïnvloed. De exacte tijdlijn van een release kan niet worden gegarandeerd. 
  
### <a name="targeted-release-for-entire-organization"></a>Targeted Release voor de hele organisatie

Als u [de releaseoptie in het beheercentrum](#set-up-the-release-option-in-the-admin-center) voor deze optie in stelt, krijgen al uw gebruikers de targeted release-ervaring. Voor organisaties met meer dan 300 gebruikers wordt een testabonnement op deze optie aanbevolen. Neem contact op met uw Microsoft-contactpersoon voor meer informatie. 
  
### <a name="targeted-release-for-selected-users"></a>Targeted Release voor specifieke gebruikers

Als u [de releaseoptie in](#set-up-the-release-option-in-the-admin-center) het beheercentrum voor deze optie in stelt, kunt u specifieke gebruikers definiëren, meestal power users, om vroegtijdige toegang te krijgen tot functies en functionaliteit. 
  
## <a name="benefits-of-targeted-release"></a>Voordelen van Targeted Release

Met een gerichte release kunnen beheerders, wijzigingsmanagers of andere verantwoordelijken voor Microsoft 365-updates zich voorbereiden op de komende wijzigingen door ze te laten:
  
- Nieuwe updates testen en valideren voordat deze worden uitgebracht voor alle gebruikers in de organisatie.
    
- Meldingen en documentatie voor gebruikers voorbereiden voordat de updates mondiaal worden uitgebracht.
    
- Een interne helpdesk in verband met aanstaande updates voorbereiden
    
- Beoordelingen betreffende naleving en beveiliging doornemen.
    
- Besturingselementen voor functies gebruiken om de uitgifte van updates voor eindgebruikers te reguleren.
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>De releaseoptie instellen in het beheercentrum

U kunt de manier wijzigen waarop uw organisatie Microsoft 365-updates ontvangt door deze stappen uit te voeren. U moet een globale beheerder zijn in Microsoft 365 om u aan te kunnen.
  
> [!IMPORTANT]
> Het kan tot 24 uur duren voordat de onderstaande wijzigingen van kracht worden in Microsoft 365. Als u zich afmeldt nadat u het programma hebt ingeschakeld, hebben uw gebruikers mogelijk geen toegang meer tot functies waarvan de geplande release nog niet beschikbaar is. 
  
1. Ga in het beheercentrum naar **instellingen** organisatieinstelling en kies onder het tabblad  >  Organisatieprofiel de optie **Releasevoorkeuren.** 

5. Als u gerichte release wilt uitschakelen, selecteert u **Standaardversie** en **selecteert u Vervolgens Wijzigingen opslaan.** 
    
6. Als u een gerichte release wilt inschakelen voor alle gebruikers in uw organisatie, **selecteert** u Targeted release voor iedereen en selecteert u **Vervolgens Wijzigingen opslaan.** 
    
7. Als u gerichte release wilt inschakelen voor sommige personen in uw organisatie, **selecteert** u Targeted release voor geselecteerde gebruikers en selecteert u **Vervolgens Wijzigingen opslaan.** 
    
8. Kies **Gebruikers selecteren** om gebruikers één voor één toe te voegen of Gebruikers uploaden **om** ze bulksgewijs toe te voegen.
    
9. Wanneer u klaar bent met het toevoegen van gebruikers, selecteert u **Wijzigingen opslaan.**


  
## <a name="learn-more"></a>Meer informatie

Ontdek hoe u [berichten beheert](/office365/admin/manage/message-center) in uw [Microsoft 365-berichtencentrum](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) om meldingen te krijgen over toekomstige Updates en releases van Microsoft 365.