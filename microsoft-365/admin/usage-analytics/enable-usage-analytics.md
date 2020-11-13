---
title: Microsoft 365 Gebruiksanalyse inschakelen
f1.keywords:
- CSH
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Meer informatie over het verzamelen van gegevens voor uw Tenant met behulp van de app Microsoft 365 Usage Analytics template in Power BI.
ms.openlocfilehash: cda5931e81f7ea13208825afa658f1c672a2f326
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071453"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Microsoft 365 Gebruiksanalyse inschakelen

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

De gebruiksanalyse voor Microsoft 365 is nog niet beschikbaar voor Microsoft 365 US Government community.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Stappen voor het inschakelen van Microsoft 365 Gebruiksanalyse

Als u aan de slag wilt met Microsoft 365 use Analytics, moet u eerst de gegevens beschikbaar maken in het Microsoft 365-Beheercentrum en vervolgens de sjabloon-app starten in Power BI.
  
### <a name="get-power-bi"></a>Power BI downloaden

Als u Power BI nog niet hebt, kunt u [zich registreren voor Power bi Pro](https://go.microsoft.com/fwlink/p/?linkid=845347). Selecteer **gratis proberen** om u aan te melden voor een proefabonnement of **Nu kopen** voor Power bi Pro.
  
  
U kunt ook **Products** uitvouwen om een versie van Power BI te kopen. 

> [!NOTE]
> U hebt een Power BI Pro-licentie nodig voor het installeren, aanpassen en distribueren van een sjabloon-app. Voor meer informatie raadpleegt u de [vereisten](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).

Als u uw gegevens wilt delen, moeten zowel u als de personen met wie u de gegevens deelt, een licentie voor Power BI Pro gebruiken, of de inhoud moet zich in een werkruimte in een [Power bi Premium-Service](https://docs.microsoft.com/power-bi/service-premium-what-is)bevinden. 
  
### <a name="enable-the-template-app"></a>De sjabloon-app inschakelen

Als u de sjabloon-app wilt inschakelen, moet u een **globale beheerder** zijn.
  
Zie [informatie over beheerdersrollen](../add-users/about-admin-roles.md) voor meer informatie. 
  
1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>. 
    
2. Zoek op de pagina **gebruik** de kaart **Microsoft 365 Usage Analytics** en selecteer **aan de slag**.
    
3. In het deelvenster rapporten dat wordt geopend, stelt u **gegevens beschikbaar maken voor Microsoft 365 gebruiksanalyse voor Power bi** **in bij** \> **Opslaan**. 
  
Het verzamelen van gegevens wordt in twee tot 48 uur voltooid, afhankelijk van de grootte van de Tenant. De knop **Ga naar Power BI** zal ingeschakeld zijn (niet langer grijs) als het verzamelen van gegevens is voltooid. 
    
### <a name="start-the-template-app"></a>De sjabloon-app starten

U moet een hoofd **beheerder** , **rapportlezer** , **Exchange-beheerder** , **Skype voor bedrijven-beheerder** of **SharePoint-beheerder** zijn om de sjabloon-app te starten. 
  
1. Kopieer de Tenant-ID en selecteer **Go to Power bi**.
    
2.  Meld u aan wanneer u in Power BI komt. **Selecteer vervolgens apps** -> **downloaden** in het navigatiemenu.    
  
3. In het tabblad **Apps** typt u Microsoft 365 in het zoekvak en selecteer vervolgens **Microsoft 365 Gebruiksanalyse** \> **Koop het vandaag nog**.

    [![Selecteer nu kopen](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  Nadat de app is geïnstalleerd. Selecteer de tegel om deze te openen.

5.  Selecteer **app verkennen** om de app met voorbeeldgegevens te bekijken. Kies **verbinding maken** om de app te verbinden met de gegevens van uw organisatie.

6.  Kies **verbinding** , ga naar het scherm **verbinding maken met Microsoft 365 Usage Analytics** en typ de Tenant-id (zonder streepjes) die u in stap 1 hebt gekopieerd, en selecteer **volgende**.
    
7. Selecteer in het volgende scherm **OAuth2** als **verificatiemethode** \> **Aanmelden**. Als u een andere verificatiemethode kiest, mislukt de verbinding met de sjabloon-app.
    
    ![Microsoft-account kiezen als verificatiemethode](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. Nadat de sjabloon-app is geïnstantieerd, is het dashboard Microsoft 365 Usage Analytics beschikbaar in de webversie van Power BI. Het eerste laden van het dashboard duurt 2 tot 30 minuten.
  
Samenvoeging van Tenant niveau is beschikbaar in alle rapporten nadat u zich hebt aangemeld. **Details van gebruikersniveau komen slechts binnen de vijfde van de volgende maand van de volgende maand na het** intrekken. Dit is van invloed op alle rapporten onder gebruikersactiviteit (Zie [navigeren en de rapporten gebruiken in Microsoft 365 gebruiksanalyse](navigate-and-utilize-reports.md) voor tips over het weergeven en gebruiken van deze rapporten).
    
## <a name="make-the-collected-data-anonymous"></a>Verzamelde gegevens anoniem maken

Alleen hoofdbeheerders kunnen de gegevens die worden verzameld voor alle rapporten anoniem maken. Hiermee kunt u identificeerbare informatie zoals namen van gebruikers, groepen en sites verbergen in rapporten en in de sjabloon-app.
  
1. Ga in het Beheercentrum naar instellingen voor **Settings** \> **organisatie** en kies op het tabblad **Services** de optie **rapporten**.
    
2. Selecteer **rapporten** en kies vervolgens deze optie om **anonieme Id's weer te geven**. Deze instelling wordt zowel toegepast op de gebruiksrapporten als voor de sjabloon-app.
  
3. Selecteer **Wijzigingen opslaan**.
