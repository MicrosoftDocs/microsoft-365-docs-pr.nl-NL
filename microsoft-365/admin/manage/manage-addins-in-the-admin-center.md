---
title: Invoegtoepassingen beheren in het beheercentrum
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Meer informatie over het gebruik van gecentraliseerde invoegvoegingen voor het implementeren van invoegingen voor gebruikers en groepen in uw organisatie.
ms.openlocfilehash: 8503ed7ea2e088a8e17b52e619ee999aa05f497a
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579288"
---
# <a name="manage-add-ins-in-the-admin-center"></a>Invoegtoepassingen beheren in het beheercentrum

Met Office-invoegvoegingen kunt u uw documenten aan uw persoonlijke voorkeur personaliseren en de manier waarop u toegang krijgt tot informatie op het web stroomlijnen (zie [Uw Office-invoegvoeging gebruiken).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) 

Nadat een beheerder invoegvoegingen voor gebruikers in een organisatie heeft geïmplementeerd, kan de beheerder invoegingen in- of uitschakelen, bewerken, verwijderen en beheren.

Zie Invoegvoegingen implementeren in het beheercentrum voor meer informatie over het installeren van invoegvoegingen vanuit het [beheercentrum.](./manage-deployment-of-add-ins.md)
  
## <a name="add-in-states"></a>Statussen van invoegtoepassingen

Een invoegvoegvoeging kan de status **Aan** of **Uit** hebben.
  
|**Status**|**Hoe de status optreedt**|**Impact**|
|:-----|:-----|:-----|
|**Actief**  <br/> |De beheerder heeft de invoegtoepassing geüpload en toegewezen aan gebruikers of groepen.  <br/> |Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, zien de invoegtoepassing in de desbetreffende clients.  <br/> |
|**Uitgeschakeld**  <br/> |De beheerder heeft de invoegtoepassing uitgeschakeld.  <br/> |Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, hebben niet langer toegang tot de invoegtoepassing.  <br/> Als de status van de invoegtoepassing wordt gewijzigd in Actief, hebben de gebruikers en groepen opnieuw toegang tot de invoegtoepassing.  <br/> |
|**Verwijderd**  <br/> |De beheerder heeft de invoegtoepassing verwijderd.  <br/> |Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, hebben niet langer toegang tot de invoegtoepassing.  <br/> |
   
U kunt een invoegvoeginvoeging verwijderen als deze niet meer wordt gebruikt. Het uitschakelen van een invoeging kan bijvoorbeeld zinvol zijn als een invoeging alleen wordt gebruikt in bepaalde tijden van het jaar.

## <a name="delete-an-add-in"></a>Een invoeging verwijderen

U kunt ook een invoegvoeging verwijderen die is geïmplementeerd.

1. Ga in het beheercentrum naar de pagina **Instellingen**  >  **services & invoegvoegingen.**

     > [!NOTE]
    > Het beheercentrum wordt bijgewerkt naar implementatieervaring met geïntegreerde apps. Als u de bovenstaande stappen niet ziet, gaat u naar de sectie Gecentraliseerde implementatie door naar **Geïntegreerde**  >  **instellingen-apps te gaan.** Kies invoegingen boven aan de pagina Geïntegreerde **apps.**

2. Selecteer de geïmplementeerde invoegvoegvoeging.

3. Klik op **Invoeg toevoegen verwijderen.** Verwijder de knop Invoeg toevoegen in de rechteronderhoek.

4. Valideer uw selecties en kies **Invoeging verwijderen.**

## <a name="edit-add-in-access"></a>Invoegtoegang bewerken

Na de implementatie kunnen beheerders ook gebruikerstoegang tot invoegvoegingen beheren.

1. Ga in het beheercentrum naar de pagina **Instellingen**  >  **services & invoegvoegingen.**

     > [!NOTE]
    > Het beheercentrum wordt bijgewerkt naar implementatieervaring met geïntegreerde apps. Als u de bovenstaande stappen niet ziet, gaat u naar de sectie Gecentraliseerde implementatie door naar **Geïntegreerde**  >  **instellingen-apps te gaan.** Kies invoegingen boven aan de pagina Geïntegreerde **apps.**

2. Selecteer de geïmplementeerde invoegvoegvoeging.

3. Klik op **Bewerken onder** Wie **heeft Access.**

4. Sla de wijzigingen op.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Invoegversies voorkomen door de Office Store uit te schakelen voor alle clients (behalve Outlook)

> [!NOTE]
> De installatie van Outlook-invoegtoepassingen wordt beheerd via een [ander proces](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins).

Als organisatie kunt u het downloaden van nieuwe Office-invoegtoepassingen vanuit Office Store verhinderen. Dit kunt u doen in combinatie met Gecentraliseerde implementatie om ervoor te zorgen dat alleen invoegtoepassingen die door organisaties zijn goedgekeurd voor gebruikers binnen de organisatie worden geïmplementeerd.
  
**Invoegvoeging uitschakelen**
  
1. Ga in het beheercentrum naar de pagina **Instellingen** \> [Services &amp; invoegtoepassingen](https://go.microsoft.com/fwlink/p/?linkid=2053743).

     > [!NOTE]
    > Het beheercentrum wordt bijgewerkt naar implementatieervaring met geïntegreerde apps. Als u de bovenstaande stappen niet ziet, gaat u naar de sectie Gecentraliseerde implementatie door naar **Geïntegreerde**  >  **instellingen-apps te gaan.** Kies invoegingen boven aan de pagina Geïntegreerde **apps.**
    
3. Selecteer **Apps en services die eigendom zijn van gebruikers.**
    
4. U kunt de optie om gebruikers toegang te geven tot de Office Store, uit.

Hierdoor wordt voorkomen dat alle gebruikers de volgende invoegtoepassingen via de store kunnen aanschaffen.
  
- Invoegtoepassingen voor Word, Excel en PowerPoint 2016 van:
    
  - Windows
    
  - Mac
    
  - Office
    
    
- Aanschaf die begint vanuit **AppSource**
    
- Invoegvoegingen binnen Microsoft 365
    
Een gebruiker die toegang probeert te krijgen tot de Store, ziet het volgende bericht: **Microsoft 365 is** geconfigureerd om individuele overname van Office Store-invoegvoegingen te voorkomen.
  
Ondersteuning voor het uitschakelen van Office Store is beschikbaar in de volgende versies:
  
- Windows: 16.0.9001 - Momenteel beschikbaar.
    
- Mac: 16.10.18011401: momenteel beschikbaar.
    
- iOS: 2.9.18010804: momenteel beschikbaar.
    
- Het web- Momenteel beschikbaar.
    
Hiermee wordt niet voorkomen dat een beheerder Gecentraliseerde implementatie gebruikt om invoegtoepassingen vanuit Office Store toe te wijzen.
  
Om te voorkomen dat een gebruiker zich aanmeldt met een Microsoft-account, kunt u ervoor zorgen dat er alleen kan worden aangemeld met het account van de organisatie. Zie Identiteit, verificatie en autorisatie [in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office)voor meer informatie.  

> [!NOTE]
> Als u voorkomt dat gebruikers toegang krijgen tot de Office Store, kunnen ze office-invoegvoegingen ook niet [sideloaden om ze te testen.](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)

## <a name="more-about-the-end-user-experience-with-add-ins"></a>Meer informatie over de ervaring van eindgebruikers met invoegvoegingen

Nadat u een invoegtoepassingen hebt geïmplementeerd, kunnen uw eindgebruikers deze gaan gebruiken in hun Office-toepassingen (zie [Uw Office-invoegtoepassingen gebruiken).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) De invoeging wordt weergegeven op alle platforms die door de invoeging worden ondersteund.
  
Als de invoegtoepassing opdrachten van de invoegtoepassing ondersteunt, verschijnen de opdrachten in het Office-lint. In het volgende voorbeeld wordt de opdracht **Bronvermelding zoeken** weergegeven voor de invoegtoepassing **Bronvermeldingen**. 

![Office-lint met bronvermeldingen zoeken](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Als de geïmplementeerde invoegtoepassing geen ondersteuning biedt voor opdrachten van de invoegtoepassing of als u alle geïmplementeerde invoegtoepassingen wilt weergeven, kunt u ze weergeven via **Mijn invoegtoepassingen**. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>In Word 2016, Excel 2016 of PowerPoint 2016

1. Selecteer **Mijn \> invoegingen invoegen.** 
    
2. Selecteer het tabblad **Beheerd door beheerder** in het venster Office-invoegtoepassingen. 
    
3. Dubbelklik op de invoegtoepassing die u eerder hebt geïmplementeerd (in dit voorbeeld **Bronvermeldingen** ). <br/>![Tabblad Beheerd door beheerder van de pagina Office-invoegvoegingen](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>In Outlook

1. Selecteer op **het lint** Start de **optie Invoegvoegingen ophalen.**<br/>![Knop Store in Outlook](../../media/getaddinsicon.png)
  
2. Selecteer **Beheer beheerd** in het linkernavigatienavigatienavigatiecentrum. 

## <a name="learn-more"></a>Meer informatie

[Invoegtoepassingen implementeren in het beheercentrum](./manage-deployment-of-add-ins.md)

Lees meer over het maken en bouwen van [Office-invoegtoepassingen](/office/dev/add-ins/overview/office-add-ins).
  
[PowerShell-cmdlets met gecentraliseerde implementatie gebruiken om invoegvoegingen te beheren.](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md)
  
[Probleem oplossen: Gebruiker ziet geen invoegvoegingen](/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[Minderjarigen en het verkrijgen van invoegvoegingen in de Microsoft Store](./minors-and-acquiring-addins-from-the-store.md)