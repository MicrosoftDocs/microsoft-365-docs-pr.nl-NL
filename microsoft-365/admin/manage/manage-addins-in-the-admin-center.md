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
description: Meer informatie over het gebruik van Gecentraliseerde invoegvoeg graag voor het implementeren van invoegingen voor gebruikers en groepen in uw organisatie.
ms.openlocfilehash: 5366bd5be80559f23490aeb54f9417a189169e12
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114199"
---
# <a name="manage-add-ins-in-the-admin-center"></a>Invoegtoepassingen beheren in het beheercentrum

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Met Office-invoegvoegingen kunt u uw documenten aan uw persoonlijke voorkeur personaliseren en de manier waarop u toegang krijgt tot informatie op internet stroomlijnen (zie [Uw Office-invoegonderdeel gebruiken).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) 

Nadat een beheerder invoegingen voor gebruikers in een organisatie heeft geïmplementeerd, kan de beheerder invoegingen in- of uitschakelen, bewerken, verwijderen en de toegang tot de invoegingen beheren.

Zie Invoegingen implementeren in het beheercentrum voor meer informatie over het installeren van invoeg graag vanuit [het beheercentrum.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)
  
## <a name="add-in-states"></a>Statussen van invoegtoepassingen

Een invoeg mag de status **Aan of** **Uit** hebben.
  
|**Status**|**Hoe de status optreedt**|**Impact**|
|:-----|:-----|:-----|
|**Actief**  <br/> |De beheerder heeft de invoegtoepassing geüpload en toegewezen aan gebruikers of groepen.  <br/> |Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, zien de invoegtoepassing in de desbetreffende clients.  <br/> |
|**Uitgeschakeld**  <br/> |De beheerder heeft de invoegtoepassing uitgeschakeld.  <br/> |Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, hebben niet langer toegang tot de invoegtoepassing.  <br/> Als de status van de invoegtoepassing wordt gewijzigd in Actief, hebben de gebruikers en groepen opnieuw toegang tot de invoegtoepassing.  <br/> |
|**Verwijderd**  <br/> |De beheerder heeft de invoegtoepassing verwijderd.  <br/> |Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, hebben niet langer toegang tot de invoegtoepassing.  <br/> |
   
U kunt een invoeginvoeging verwijderen als deze door niemand meer wordt gebruikt. Het uitschakelen van een invoeg mag bijvoorbeeld zinvol zijn als een invoeg mag worden gebruikt in bepaalde tijden van het jaar.

## <a name="delete-an-add-in"></a>Een invoeg toevoegen verwijderen

U kunt ook een geïmplementeerde invoeg procenten verwijderen.

1. Ga in het beheercentrum naar de **pagina**  >  **Instellingenservices &-invoegingen.**

     > [!NOTE]
    > Het beheercentrum wordt bijgewerkt naar de implementatie-ervaring met Geïntegreerde apps. Als u de bovenstaande stappen niet ziet, gaat u naar de sectie Gecentraliseerde implementatie via **Geïntegreerde**  >  **apps instellingen.** Kies invoegingen boven aan de pagina Geïntegreerde **apps.**

2. Selecteer de geïmplementeerde invoegvoeging.

3. Klik op **Invoeg toevoegen verwijderen.** Verwijder de knop in de rechteronderhoek.

4. Valideer uw selecties en kies **Invoeg toevoegen verwijderen.**

## <a name="edit-add-in-access"></a>Invoegtoegang bewerken

Na de implementatie kunnen beheerders ook de gebruikerstoegang tot invoegingen beheren.

1. Ga in het beheercentrum naar de **pagina**  >  **Instellingenservices &-invoegingen.**

     > [!NOTE]
    > Het beheercentrum wordt bijgewerkt naar de implementatie-ervaring met Geïntegreerde apps. Als u de bovenstaande stappen niet ziet, gaat u naar de sectie Gecentraliseerde implementatie via **Geïntegreerde**  >  **apps instellingen.** Kies invoegingen boven aan de pagina Geïntegreerde **apps.**

2. Selecteer de geïmplementeerde invoegvoeging.

3. Klik op **Bewerken** onder **Wie heeft Access.**

4. Sla de wijzigingen op.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Downloads van invoeg apps voorkomen door de Office Store voor alle clients uit te schakelen (behalve Outlook)

> [!NOTE]
> De installatie van Outlook-invoegtoepassingen wordt beheerd via een [ander proces](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).

Als organisatie kunt u het downloaden van nieuwe Office-invoegtoepassingen vanuit Office Store verhinderen. Dit kunt u doen in combinatie met Gecentraliseerde implementatie om ervoor te zorgen dat alleen invoegtoepassingen die door organisaties zijn goedgekeurd voor gebruikers binnen de organisatie worden geïmplementeerd.
  
**Aanschaf van invoeg graag uitschakelen**
  
1. Ga in het beheercentrum naar de pagina **Instellingen** \> [Services &amp; invoegtoepassingen](https://go.microsoft.com/fwlink/p/?linkid=2053743).

     > [!NOTE]
    > Het beheercentrum wordt bijgewerkt naar de implementatie-ervaring met Geïntegreerde apps. Als u de bovenstaande stappen niet ziet, gaat u naar de sectie Gecentraliseerde implementatie via **Geïntegreerde**  >  **apps instellingen.** Kies invoegingen boven aan de pagina Geïntegreerde **apps.**
    
3. Selecteer Apps en services die eigendom zijn **van gebruikers.**
    
4. De optie voor gebruikers toegang geven tot de Office Store, is uit.

Hierdoor wordt voorkomen dat alle gebruikers de volgende invoegtoepassingen via de store kunnen aanschaffen.
  
- Invoegtoepassingen voor Word, Excel en PowerPoint 2016 van:
    
  - Windows
    
  - Mac
    
  - Office
    
    
- Aanschaf die begint vanuit **AppSource**
    
- Invoegingen in Microsoft 365
    
Een gebruiker die toegang probeert te krijgen tot de Store ziet het volgende bericht: Microsoft 365 is geconfigureerd om individuele aanschaf van **Office Store-invoegingen te voorkomen.**
  
Ondersteuning voor het uitschakelen van Office Store is beschikbaar in de volgende versies:
  
- Windows: 16.0.9001 - Momenteel beschikbaar.
    
- Mac: 16.10.18011401: momenteel beschikbaar.
    
- iOS: 2.9.18010804: momenteel beschikbaar.
    
- Het web: momenteel beschikbaar.
    
Hiermee wordt niet voorkomen dat een beheerder Gecentraliseerde implementatie gebruikt om invoegtoepassingen vanuit Office Store toe te wijzen.
  
Om te voorkomen dat een gebruiker zich aanmeldt met een Microsoft-account, kunt u ervoor zorgen dat er alleen kan worden aangemeld met het account van de organisatie. Zie Identiteit, verificatie en autorisatie [in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)voor meer informatie.  

> [!NOTE]
> Als u voorkomt dat gebruikers toegang krijgen tot de Office Store, kunnen ze [ook Geen Office-invoegvoegingen sideloaden voor tests.](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)

## <a name="more-about-the-end-user-experience-with-add-ins"></a>Meer informatie over de ervaring van eindgebruikers met invoegingen

Nadat u een invoegtoepassingen hebt geïmplementeerd, kunnen uw eindgebruikers deze gaan gebruiken in hun Office-toepassingen (zie Uw [Office-invoegtoepassingen gebruiken).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) De invoeg feit wordt weergegeven op alle platforms die door de invoegvoeg toevoeg worden ondersteund.
  
Als de invoegtoepassing opdrachten van de invoegtoepassing ondersteunt, verschijnen de opdrachten in het Office-lint. In het volgende voorbeeld wordt de opdracht **Bronvermelding zoeken** weergegeven voor de invoegtoepassing **Bronvermeldingen**. 

![Office-lint met bronvermeldingen zoeken](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Als de geïmplementeerde invoegtoepassing geen ondersteuning biedt voor opdrachten van de invoegtoepassing of als u alle geïmplementeerde invoegtoepassingen wilt weergeven, kunt u ze weergeven via **Mijn invoegtoepassingen**. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>In Word 2016, Excel 2016 of PowerPoint 2016

1. Selecteer **\> Mijn invoegvoegingen invoegen.** 
    
2. Selecteer het tabblad **Beheerd door beheerder** in het venster Office-invoegtoepassingen. 
    
3. Dubbelklik op de invoegtoepassing die u eerder hebt geïmplementeerd (in dit voorbeeld **Bronvermeldingen** ). <br/>![Tabblad Beheerd door beheerder van de pagina Office-invoegvoegingen](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>In Outlook

1. Selecteer **Invoegingen** ophalen op het lint **Start.**<br/>![Knop Store in Outlook](../../media/getaddinsicon.png)
  
2. Selecteer **beheerde beheerder** in het linkernavigatiebalkje. 

## <a name="learn-more"></a>Meer informatie

[Invoegtoepassingen implementeren in het beheercentrum](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

Lees meer over het maken en bouwen van [Office-invoegtoepassingen](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).
  
[PowerShell-cmdlets voor Gecentraliseerde implementatie gebruiken om invoegingen te beheren.](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[Problemen oplossen: Gebruiker ziet geen invoegingen](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[Minderjarigen en het verkrijgen van invoegingen uit de Microsoft Store](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)
