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
description: Meer informatie over het verzamelen van gegevens voor uw tenant met de sjabloon-app Microsoft 365 Usage Analytics in Power BI.
ms.openlocfilehash: 20228b0e2070065834ce203e22af619480311367
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502947"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Microsoft 365 Gebruiksanalyse inschakelen

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Microsoft 365-gebruiksanalyses zijn nog niet beschikbaar voor microsoft 365-overheidscommunity van de Amerikaanse overheid.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Stappen voor het inschakelen van Microsoft 365 Gebruiksanalyse

Als u aan de slag wilt met Microsoft 365-gebruiksanalyses, moet u eerst de gegevens beschikbaar stellen in het Microsoft 365-beheercentrum en vervolgens de sjabloon-app in Power BI starten.
  
### <a name="get-power-bi"></a>Power BI downloaden

Als u nog geen Power BI hebt, u [zich aanmelden voor Power BI Pro.](https://go.microsoft.com/fwlink/p/?linkid=845347) Selecteer **Probeer je gratis** aan te melden voor een proefversie of Koop **nu** om Power BI Pro te krijgen.
  
  
U kunt ook **Products** uitvouwen om een versie van Power BI te kopen. 

> [!NOTE]
> U hebt een Power BI Pro-licentie nodig om een sjabloon-app te installeren, aan te passen en te distribueren. Zie [Voorwaarden](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)voor meer informatie.

U hebt een Power BI Pro-licentie nodig om uw inhoud te delen, en de mensen met wie u deze deelt, doen dat ook, of de inhoud moet zich in een werkruimte bevinden in een [Premium-capaciteit.](https://docs.microsoft.com/power-bi/service-premium-what-is) 
  
### <a name="enable-the-template-app"></a>De sjabloon-app inschakelen

Als u de sjabloon-app wilt inschakelen, moet u een **globale beheerder**, **rapportlezer**, **Exchange-beheerder,** **Skype voor Bedrijven-beheerder**of **SharePoint-beheerder**zijn. 
  
Zie [Over beheerdersrollen](../add-users/about-admin-roles.md) voor meer informatie. 
  
1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>. 
    
2. Zoek op de pagina **Gebruik** de **Microsoft 365-gebruiksanalysekaart** en selecteer **Aan de slag**.
    
3. Stel in het deelvenster Rapporten dat wordt geopend, de gegevens beschikbaar maken **voor Microsoft 365-gebruiksanalyses voor Power BI** in **Opslaan.** \> **Save** 
  
Hiermee wordt het gegevensverzamelingsproces gestart, en dit zal voltooid worden in 2 tot 48 uur, afhankelijk van de grootte van uw tenant. De knop **Ga naar Power BI** zal ingeschakeld zijn (niet langer grijs) als het verzamelen van gegevens is voltooid. 
    
### <a name="initiate-the-template-app"></a>De sjabloon-app starten

Als u de sjabloon-app wilt starten, moet u een **globale beheerder**, **rapportlezer**, **Exchange-beheerder,** **Skype voor Bedrijven-beheerder**of **SharePoint-beheerder**zijn. 
  
1. Kopieer de tenant-id en selecteer **Ga naar Power BI**.
    
2.  Meld u aan wanneer u in Power BI komt. Selecteer Apps->Apps ophalen in het navigatiemenu.    
  
3. In het tabblad **Apps** typt u Microsoft 365 in het zoekvak en selecteer vervolgens **Microsoft 365 Gebruiksanalyse** \> **Koop het vandaag nog**.

    [![Selecteer Nu ophalen](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  Zodra de app is geïnstalleerd. Klik op de tegel om deze te openen.

5.  Klik **op De app verkennen** om de app met voorbeeldgegevens weer te geven. Klik **op Verbinding** maken om de app te koppelen aan de gegevens van uw organisatie.

6.  Nadat u **op Verbinding**hebt geklikt , typt u in het scherm Verbinding maken met Microsoft **365-gebruiksanalyse** de tenant-id (zonder streepjes) die u in stap hebt gekopieerd (1) en selecteert u **Volgende**.
    
7. Selecteer **oAuth2** in het volgende scherm als **verificatiemethode** \> **Aanmelden.** Als u een andere verificatiemethode kiest, mislukt de verbinding met de sjabloon-app.
    
    ![Choose oAuth2 as authentication method](../../media/ac85a360-c278-4c60-8aa3-68f4828f1d96.png)
  
8. Zodra de sjabloon-app is gehe momentediated, is het Microsoft 365 usage analytics-dashboard beschikbaar in Power BI op het web. Het eerste laden van het dashboard duurt 2 tot 30 minuten.
  
Samengevoegde gegevens op tenantniveau zijn beschikbaar in alle rapporten. **Gegevens op gebruikersniveau zijn pas beschikbaar na de 1e of 15e dag van de kalendermaand na aanmelding**. Dit heeft gevolgen voor alle rapporten onder Gebruikersactiviteit (Zie [Navigeren en gebruik de rapporten in Microsoft 365-gebruiksanalyses](navigate-and-utilize-reports.md) voor tips over het bekijken en gebruiken van deze rapporten).
    
## <a name="make-the-collected-data-anonymous"></a>Verzamelde gegevens anoniem maken

Alleen hoofdbeheerders kunnen de gegevens die worden verzameld voor alle rapporten anoniem maken. Hiermee worden identificeerbare informatie zoals gebruikers-, groeps- en sitenamen verborgen in rapporten en in de sjabloon-app.
  
1. Ga in het beheercentrum naar **de** \> **instellingeninstellingen van organisatie**en kies onder tabblad **Services** De optie **Rapporten**.
    
2. Selecteer **Rapporten**en kies vervolgens voor **Anonieme id's weergeven**. Deze instelling wordt zowel toegepast op de gebruiksrapporten als op de sjabloon-app.
  
3. Selecteer **Wijzigingen opslaan**.
