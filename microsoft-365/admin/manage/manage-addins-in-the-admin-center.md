---
title: Invoegtoepassingen beheren in het beheercentrum
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Meer informatie over het implementeren van invoegtoepassingen voor gebruikers en groepen in uw organisatie met behulp van gecentraliseerde implementatie in het beheercentrum.
ms.openlocfilehash: caaea8404c099f56704d21684323a4b20e61f52d
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103091"
---
# <a name="manage-add-ins-in-the-admin-center"></a>Invoegtoepassingen beheren in het beheercentrum

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Met Office-invoegtoepassingen u uw documenten personaliseren en de manier waarop u toegang krijgt tot informatie op internet te stroomlijnen (zie [Start met uw Office-invoegtoepassing).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) 

Nadat een beheerder invoegtoepassingen voor gebruikers in een organisatie heeft geïmplementeerd, kan de beheerder invoegtoepassingen uitschakelen of in- of uitschakelen, bewerken, verwijderen en de toegang tot de invoegtoepassingen beheren.

Zie Invoegtoepassingen implementeren in het beheercentrum voor meer informatie over het installeren van [invoegtoepassingen vanuit het beheercentrum.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)
  
## <a name="add-in-states"></a>Statussen van invoegtoepassingen

Een invoegtoepassing kan in **de** aan- of **uit-status** zijn.
  
|**Status**|**Hoe de status optreedt**|**Impact**|
|:-----|:-----|:-----|
|**Actief**  <br/> |De beheerder heeft de invoegtoepassing geüpload en toegewezen aan gebruikers of groepen.  <br/> |Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, zien de invoegtoepassing in de desbetreffende clients.  <br/> |
|**Uitgeschakeld**  <br/> |De beheerder heeft de invoegtoepassing uitgeschakeld.  <br/> |Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, hebben niet langer toegang tot de invoegtoepassing.  <br/> Als de status van de invoegtoepassing wordt gewijzigd in Actief, hebben de gebruikers en groepen opnieuw toegang tot de invoegtoepassing.  <br/> |
|**Verwijderd**  <br/> |De beheerder heeft de invoegtoepassing verwijderd.  <br/> |Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, hebben niet langer toegang tot de invoegtoepassing.  <br/> |
   
Overweeg een invoegtoepassing te verwijderen als niemand deze niet meer gebruikt. Het uitschakelen van een invoegtoepassing kan bijvoorbeeld zinvol zijn als een invoegtoepassing alleen wordt gebruikt op specifieke tijden van het jaar.

## <a name="delete-an-add-in"></a>Een invoegtoepassing verwijderen

U ook een invoegtoepassing verwijderen die is geïmplementeerd.

1. Ga in het beheercentrum **Settings**naar de  >  **pagina Instellingenservices & invoegtoepassingen.**

2. Selecteer de geïmplementeerde invoegtoepassing.

3. Klik op **Invoegtoepassing verwijderen**. Verwijder de invoegknop rechtsonder.

4. Valideer uw selecties en kies **Invoegtoepassing verwijderen.**

## <a name="edit-add-in-access"></a>Invoegtoepassingstoegang bewerken

Na de implementatie kunnen beheerders ook de toegang van gebruikers tot invoegtoepassingen beheren.

1. Ga in het beheercentrum **Settings**naar de  >  **pagina Instellingenservices & invoegtoepassingen.**

2. Selecteer de geïmplementeerde invoegtoepassing.

3. Klik op **Bewerken** onder **Wie heeft Toegang**.

4. Sla de wijzigingen op.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Downloads van invoegtoepassing voorkomen door de Office Store voor alle clients uit te schakelen (behalve Outlook)

> [!NOTE]
> De installatie van Outlook-invoegtoepassingen wordt beheerd via een [ander proces](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).

Als organisatie kunt u het downloaden van nieuwe Office-invoegtoepassingen vanuit Office Store verhinderen. Dit kunt u doen in combinatie met Gecentraliseerde implementatie om ervoor te zorgen dat alleen invoegtoepassingen die door organisaties zijn goedgekeurd voor gebruikers binnen de organisatie worden geïmplementeerd.
  
**Overname van invoegtoepassing uitschakelen**
  
1. Ga in het beheercentrum naar de pagina**Instellingen** \> [Services &amp; invoegtoepassingen](https://go.microsoft.com/fwlink/p/?linkid=2053743).
    
3. Selecteer **apps en services van gebruikers.**
    
4. Schakel de optie uit om gebruikers toegang te geven tot het Office-winkel.

Hierdoor wordt voorkomen dat alle gebruikers de volgende invoegtoepassingen via de store kunnen aanschaffen.
  
- Invoegtoepassingen voor Word, Excel en PowerPoint 2016 van:
    
  - Windows
    
  - Mac
    
  - Office
    
    
- Aanschaf die begint vanuit **AppSource**
    
- Invoegtoepassingen binnen Microsoft 365
    
Een gebruiker die toegang probeert te krijgen tot de store, ziet het volgende bericht: **Sorry, Microsoft 365 is geconfigureerd om individuele acquisitie van Office Store-invoegtoepassingen te voorkomen.**
  
Ondersteuning voor het uitschakelen van Office Store is beschikbaar in de volgende versies:
  
- Windows: 16.0.9001 - Momenteel beschikbaar.
    
- Mac: 16.10.18011401: momenteel beschikbaar.
    
- iOS: 2.9.18010804: momenteel beschikbaar.
    
- Het web - Momenteel beschikbaar.
    
Hiermee wordt niet voorkomen dat een beheerder Gecentraliseerde implementatie gebruikt om invoegtoepassingen vanuit Office Store toe te wijzen.
  
Om te voorkomen dat een gebruiker zich aanmeldt met een Microsoft-account, kunt u ervoor zorgen dat er alleen kan worden aangemeld met het account van de organisatie. Zie [Identiteit, verificatie en autorisatie in Office 2016 voor](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)meer informatie.  

## <a name="more-about-the-end-user-experience-with-add-ins"></a>Meer over de ervaring van de eindgebruiker met invoegtoepassingen

Nadat u een invoegtoepassing hebt geïmplementeerd, kunnen uw eindgebruikers deze gaan gebruiken in hun Office-toepassingen (zie [Start met uw Office-invoegtoepassing).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) De invoegtoepassing wordt weergegeven op alle platforms die de invoegtoepassing ondersteunt.
  
Als de invoegtoepassing opdrachten van de invoegtoepassing ondersteunt, verschijnen de opdrachten in het Office-lint. In het volgende voorbeeld wordt de opdracht **Bronvermelding zoeken** weergegeven voor de invoegtoepassing **Bronvermeldingen**. 

![Office-lint met zoekvermeldingen](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Als de geïmplementeerde invoegtoepassing geen ondersteuning biedt voor opdrachten van de invoegtoepassing of als u alle geïmplementeerde invoegtoepassingen wilt weergeven, kunt u ze weergeven via **Mijn invoegtoepassingen**. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>In Word 2016, Excel 2016 of PowerPoint 2016

1. Selecteer ** \> Mijn invoegtoepassingen invoegen**. 
    
2. Selecteer het tabblad **Beheerd door beheerder** in het venster Office-invoegtoepassingen. 
    
3. Dubbelklik op de invoegtoepassing die u eerder hebt geïmplementeerd (in dit voorbeeld **Bronvermeldingen** ). <br/>![Tabblad Beheerde van de pagina Office-invoegtoepassingen](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>In Outlook

1. Selecteer op **het** startlint de optie **Invoegtoepassingen ophalen**.<br/>![Knop Store in Outlook](../../media/getaddinsicon.png)
  
2. Selecteer **Beheerd beheer** in het linkernavigatiesysteem. 

## <a name="learn-more"></a>Meer informatie

[Invoegtoepassingen implementeren in het beheercentrum](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

Lees meer over het maken en bouwen van [Office-invoegtoepassingen](https://go.microsoft.com/fwlink/p/?linkid=846362).
  
[Gebruik Gecentraliseerde PowerShell-cmdlets voor het beheren van invoegtoepassingen.](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[Problemen oplossen: gebruiker ziet geen invoegtoepassingen](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[Minderjarigen en het verwerven van invoegtoepassingen uit de Microsoft Store](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)