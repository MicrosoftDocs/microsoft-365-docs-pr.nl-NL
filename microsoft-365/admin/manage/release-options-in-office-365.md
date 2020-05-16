---
title: De standaard- of gerichte releaseopties instellen
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Meer informatie over het instellen van de releaseoptie voor nieuwe product- en functiesupdates in het Microsoft 365-beheercentrum.
ms.openlocfilehash: 2738cf7af32d2e15b0c2c790a241dabbb1f104bc
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262315"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>De standaard- of gerichte releaseopties instellen

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Met Microsoft 365 ontvangt u nieuwe productupdates en -functies zodra deze beschikbaar zijn in plaats van om de paar jaar dure updates uit te voeren. U kunt beheren hoe uw organisatie deze updates ontvangt. U kunt u bijvoorbeeld registreren voor een vroege release, zodat uw organisatie updates als eerste ontvangt. U kunt bepaalde personen aanwijzen die als enigen de updates ontvangen. Of u blijft het standaardreleaseschema volgen en ontvangt de updates later. In dit artikel worden de verschillende releaseopties uitgelegd en hoe u deze gebruiken voor uw organisatie.
  
> [!IMPORTANT]
> De in dit artikel beschreven Microsoft 365-updates zijn van toepassing op Microsoft 365, SharePoint Online en Exchange Online. Ze zijn niet van toepassing op Skype voor Bedrijven en gerelateerde services. Deze release opties zijn gericht, best effort manieren om wijzigingen in Microsoft 365 release, maar kan niet worden gegarandeerd te allen tijde of voor alle updates. 
  
## <a name="how-it-works---release-validation"></a>Hoe het werkt: validatie van releases

Elke nieuwe release wordt eerst getest en gevalideerd door het featureteam, vervolgens door het hele Microsoft 365-functieteam, gevolgd door heel Microsoft. Na intern testen en valideren bestaat de volgende stap uit een **Targeted Release** (eerder bekend als First Release) voor klanten die zich aanmelden. Bij elke release-ring verzamelt Microsoft feedback en valideert de kwaliteit verder door belangrijke gebruiksgegevens te controleren. Deze reeks van toenemende validatie is ingesteld om er voor te zorgen dat de mondiale release zo robuust mogelijk is. De releases worden in de volgende afbeelding geïllustreerd. 
  
![Validatieringen vrijgeven voor Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
Voor belangrijke updates worden klanten in eerste instantie op de hoogte gebracht door de [Microsoft 365 Roadmap.](https://products.office.com/business/office-365-roadmap) Naarmate een update dichter bij de uitrol komt, wordt deze gecommuniceerd via uw [Microsoft 365 Message Center.](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)

> [!NOTE]
> U hebt een Microsoft 365- of Azure AD-account nodig om toegang te krijgen tot uw Berichtencentrum via het [beheercentrum.](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center) Microsoft 365 home plan gebruikers hebben geen admin center.


## <a name="standard-release"></a>Standard Release

Dit is de standaardoptie waarbij u en uw gebruikers de nieuwste updates ontvangen wanneer ze breed worden uitgebracht voor alle klanten.
  
Een goede gewoonte is om de meerderheid van de gebruikers in **Standard release** en IT-professionals en power users in **Targeted release** om nieuwe functies te evalueren en teams voor te bereiden op zakelijke gebruikers en leidinggevenden te ondersteunen. 
  
> [!NOTE]
> Als u van het First Release-programma teruggaat naar het Standard Release-programma, hebben uw gebruikers mogelijk geen toegang meer tot functies die nog niet zijn opgenomen in het Standard Release-programma. 
  
## <a name="targeted-release"></a>Targeted Release

Met deze optie zien u en uw gebruikers als eersten de nieuwste updates en kunt u helpen het product te vormen door vroege feedback te geven. U kunt bepalen of de vroege updates naar afzonderlijke personen of naar de hele organisatie worden gestuurd.
  
> [!IMPORTANT]
> Bij grote of complexe updates duurt dit mogelijk langer dan bij andere updates zodat er geen gebruikers negatief worden beïnvloed. De exacte tijdlijn van een release kan niet worden gegarandeerd. 
  
### <a name="targeted-release-for-entire-organization"></a>Targeted Release voor de hele organisatie

Als u [de releaseoptie instelt in het beheercentrum](#set-up-the-release-option-in-the-admin-center) voor deze optie, krijgen al uw gebruikers de gerichte release-ervaring. Voor organisaties met meer dan 300 gebruikers wordt een testabonnement op deze optie aanbevolen. Neem contact op met uw Microsoft-contactpersoon voor meer informatie. 
  
### <a name="targeted-release-for-selected-users"></a>Targeted Release voor specifieke gebruikers

Als u [de releaseoptie inhet beheercentrum](#set-up-the-release-option-in-the-admin-center) voor deze optie instelt, u specifieke gebruikers, meestal powerusers, definiëren om vroege toegang tot functies en functionaliteit te ontvangen. 
  
## <a name="benefits-of-targeted-release"></a>Voordelen van Targeted Release

Met gerichte release kunnen beheerders, wijzigingsmanagers of iemand anders die verantwoordelijk is voor Microsoft 365-updates zich voorbereiden op de komende wijzigingen door ze te laten zien:
  
- Nieuwe updates testen en valideren voordat deze worden uitgebracht voor alle gebruikers in de organisatie.
    
- Meldingen en documentatie voor gebruikers voorbereiden voordat de updates mondiaal worden uitgebracht.
    
- Een interne helpdesk in verband met aanstaande updates voorbereiden
    
- Beoordelingen betreffende naleving en beveiliging doornemen.
    
- Besturingselementen voor functies gebruiken om de uitgifte van updates voor eindgebruikers te reguleren.
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>De releaseoptie instellen in het beheercentrum

U de manier wijzigen waarop uw organisatie Microsoft 365-updates ontvangt door deze stappen te volgen. Je moet een globale beheerder in Microsoft 365 zijn om je aan te melden.
  
> [!IMPORTANT]
> Het kan tot 24 uur duren voordat de onderstaande wijzigingen van kracht worden in Microsoft 365. Als u zich afmeldt nadat u het programma hebt ingeschakeld, hebben uw gebruikers mogelijk geen toegang meer tot functies waarvan de geplande release nog niet beschikbaar is. 
  
1. Ga in het beheercentrum **Settings**naar de  >  **instelling Instellingen van de organisatie**en kies onder het tabblad **Organisatieprofiel** de **optie Voorkeuren vrijgeven**.

5. Als u gerichte release wilt uitschakelen, selecteert u **Standaardrelease**en selecteert u **Wijzigingen opslaan**. 
    
6. Als u gerichte release wilt inschakelen voor alle gebruikers in uw organisatie, selecteert u **Gerichte release voor iedereen**en selecteert u Wijzigingen **opslaan**. 
    
7. Als u gerichte release voor sommige mensen in uw organisatie wilt inschakelen, selecteert u **Gerichte release voor geselecteerde gebruikers**en selecteert u Wijzigingen **opslaan**. 
    
8. Kies **Gebruikers selecteren** om gebruikers één voor één toe te voegen of Gebruikers **uploaden** om ze in bulk toe te voegen.
    
9. Wanneer u klaar bent met het toevoegen van gebruikers, selecteert u **Wijzigingen opslaan**.


  
## <a name="learn-more"></a>Meer informatie

Ontdek hoe u [berichten beheert](https://docs.microsoft.com/office365/admin/manage/message-center) in uw [Microsoft 365-berichtencentrum](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) om meldingen te ontvangen over aankomende Microsoft 365-updates en -releases.
