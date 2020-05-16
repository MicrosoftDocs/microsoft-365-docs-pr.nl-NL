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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Meer informatie over het verzamelen van gegevens voor uw tenant met de sjabloon-app Microsoft 365 Usage Analytics in Power BI.
ms.openlocfilehash: 3c5e1a35b93b755b92710f0499599d849a6c251c
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262533"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Microsoft 365 Gebruiksanalyse inschakelen

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Microsoft 365-gebruiksanalyses zijn ook beschikbaar voor de Microsoft 365-overheidsgemeenschap van de Amerikaanse overheid.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Stappen voor het inschakelen van Microsoft 365 Gebruiksanalyse

Om aan de slag te gaan met Microsoft 365-gebruiksanalyses moet u de gegevens eerst beschikbaar maken in het Microsoft 365-beheercentrum en vervolgens de sjabloon-app starten in Power BI.
  
### <a name="get-power-bi"></a>Power BI downloaden

Als u nog geen Power BI hebt, u [zich aanmelden voor Power BI Pro.](https://go.microsoft.com/fwlink/p/?linkid=845347) Selecteer **Probeer je gratis** aan te melden voor een proefversie of Koop **nu** om Power BI Pro te krijgen.
  
  
U kunt ook **Products** uitvouwen om een versie van Power BI te kopen. 

> [!NOTE]
> U hebt een Power BI Pro-licentie nodig om een sjabloon-app te installeren, aan te passen en te distribueren. Zie [Voorwaarden voor](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)meer informatie.

U hebt een Power BI Pro-licentie nodig om uw inhoud te delen, en de mensen met wie u deze deelt, doen dat ook, of de inhoud moet zich in een werkruimte in een [Premium-capaciteit bevinden.](https://docs.microsoft.com/power-bi/service-premium-what-is) 
  
### <a name="enable-the-template-app"></a>De sjabloon-app inschakelen

Als u de sjabloon-app wilt inschakelen, moet u een **globale beheerder**zijn, **rapportlezer,** **Exchange-beheerder,** **Skype voor Bedrijven-beheerder**of **SharePoint-beheerder**. 
  
Zie [Over beheerdersrollen](../add-users/about-admin-roles.md) voor meer informatie. 
  
1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>. 
    
2. Zoek **op** de pagina Gebruik de **Microsoft 365-analysekaart voor gebruik** en selecteer Aan de **slag**.
    
3. Stel gegevens beschikbaar maken **voor Microsoft 365-gebruiksanalyses voor Power BI** **in** het deelvenster Rapporten dat wordt \> **Save**geopend. 
  
Hiermee wordt het gegevensverzamelingsproces gestart, en dit zal voltooid worden in 2 tot 48 uur, afhankelijk van de grootte van uw tenant. De knop **Ga naar Power BI** zal ingeschakeld zijn (niet langer grijs) als het verzamelen van gegevens is voltooid. 
    
### <a name="initiate-the-template-app"></a>De sjabloon-app starten

Als u de sjabloon-app wilt starten, moet u een **globale beheerder**zijn, **rapportlezer,** **Exchange-beheerder,** **Skype voor Bedrijven-beheerder**of **SharePoint-beheerder**. 
  
1. Kopieer de tenant-id en selecteer **Ga naar Power BI**.
    
2.  Meld u aan wanneer u in Power BI komt. Selecteer Apps->Apps ophalen in het navigatiemenu.    
  
3. In het tabblad **Apps** typt u Microsoft 365 in het zoekvak en selecteer vervolgens **Microsoft 365 Gebruiksanalyse** \> **Koop het vandaag nog**.

    [![Selecteer Nu weergeven](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  Zodra de app is geïnstalleerd. Klik op de tegel om deze te openen.

5.  Klik **op App verkennen** om de app te bekijken met voorbeeldgegevens. Klik **op Verbinding maken** om de app te verbinden met de gegevens van uw organisatie.

6.  Nadat u op **Verbinding hebt**geklikt , typt u in het scherm Verbinding maken met **Microsoft 365 gebruiksanalyse** de tenant-id die u in stap (1) Volgende hebt \> **Next**gekopieerd.
    
7. Selecteer in het volgende scherm **oAuth2** als **de verificatiemethode** \> **Aanmelden**. Als u een andere verificatiemethode kiest, mislukt de verbinding met de sjabloon-app.
    
    ![Choose oAuth2 as authentication method](../../media/ac85a360-c278-4c60-8aa3-68f4828f1d96.png)
  
8. Zodra de sjabloon-app is geinstantieerd, is het Microsoft 365-dashboard voor gebruiksanalyse beschikbaar in Power BI op internet. Het eerste laden van het dashboard duurt 2 tot 30 minuten.
  
Samengevoegde gegevens op tenantniveau zijn beschikbaar in alle rapporten. **Gegevens op gebruikersniveau zijn pas beschikbaar na de 1e of 15e dag van de kalendermaand na aanmelding**. Dit heeft gevolgen voor alle rapporten onder Gebruikersactiviteit (Zie [Navigeren en gebruik de rapporten in Microsoft 365-gebruiksanalyses](navigate-and-utilize-reports.md) voor tips over het bekijken en gebruiken van deze rapporten).
    
## <a name="make-the-collected-data-anonymous"></a>Verzamelde gegevens anoniem maken

Alleen hoofdbeheerders kunnen de gegevens die worden verzameld voor alle rapporten anoniem maken. Hiermee worden identificeerbare informatie zoals gebruikers-, groeps- en sitenamen verborgen in rapporten en in de sjabloon-app.
  
1. Ga in het beheercentrum **Settings** naar de \> **instellingen van de organisatie Instellingen**en kies onder het tabblad **Services** de optie **Rapporten**.
    
2. Selecteer **Rapporten**en kies vervolgens voor **Anonieme id's weergeven**. Deze instelling wordt zowel toegepast op de gebruiksrapporten als op de sjabloon-app.
  
3. Selecteer **Wijzigingen opslaan**.
