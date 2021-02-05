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
description: Informatie over hoe u begint met het verzamelen van gegevens voor uw tenant met behulp van de sjabloon-app Microsoft 365 Gebruiksanalyse in Power BI.
ms.openlocfilehash: 98ae107b6777ac97d0be3b37847117c6e20be63d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114235"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Microsoft 365 Gebruiksanalyse inschakelen

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Microsoft 365 Gebruiksanalyse is nog niet beschikbaar voor de Microsoft 365 US Government Community.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Stappen voor het inschakelen van Microsoft 365 Gebruiksanalyse

Als u aan de slag wilt met Microsoft 365 Gebruiksanalyse, moet u eerst de gegevens beschikbaar maken in het Microsoft 365-beheercentrum en vervolgens de sjabloon-app starten in Power BI.
  
### <a name="get-power-bi"></a>Power BI downloaden

Als u nog geen Power BI hebt, kunt u zich [registreren voor Power BI Pro.](https://go.microsoft.com/fwlink/p/?linkid=845347) Selecteer **Gratis proberen** om u aan te melden voor een proefversie of Nu kopen **om** Power BI Pro te downloaden.
  
  
U kunt ook **Products** uitvouwen om een versie van Power BI te kopen. 

> [!NOTE]
> U hebt een Power BI Pro-licentie nodig om een sjabloon-app te installeren, aan te passen en te distribueren. Zie Vereisten voor [meer informatie.](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)

Als u uw gegevens wilt delen, hebben zowel u als de personen met wie u de gegevens deelt een Power BI Pro-licentie nodig of moet de inhoud zich in een werkruimte in een [Power BI Premium-service hebben.](https://docs.microsoft.com/power-bi/service-premium-what-is) 
  
### <a name="enable-the-template-app"></a>De sjabloon-app inschakelen

Als u de sjabloon-app wilt inschakelen, moet u een globale **beheerder zijn.**
  
Meer [informatie over beheerdersrollen.](../add-users/about-admin-roles.md) 
  
1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>. 
    
2. Zoek op **de** pagina Gebruik de **Kaart Microsoft 365 Gebruiksanalyse** en selecteer **Aan de slag.**
    
3. Stel in het deelvenster Rapporten dat wordt geopend, Gegevens beschikbaar maken voor **Microsoft 365** Gebruiksanalyse voor Power BI in **bij** \> **opslaan.** 
  
Het proces voor het verzamelen van gegevens wordt in twee tot 48 uur voltooid, afhankelijk van de grootte van uw tenant. De knop **Ga naar Power BI** zal ingeschakeld zijn (niet langer grijs) als het verzamelen van gegevens is voltooid. 
    
### <a name="start-the-template-app"></a>De sjabloon-app starten

Als u de sjabloon-app wilt starten, moet u een globale **beheerder,** **rapportlezer,** **Exchange-beheerder,** **Skype** voor Bedrijven-beheerder of **SharePoint-beheerder zijn.** 
  
1. Kopieer de tenant-id en selecteer **Ga naar Power BI.**
    
2.  Meld u aan wanneer u in Power BI komt. Selecteer **vervolgens Apps** downloaden -> **uit** het navigatiemenu.    
  
3. In het tabblad **Apps** typt u Microsoft 365 in het zoekvak en selecteer vervolgens **Microsoft 365 Gebruiksanalyse** \> **Koop het vandaag nog**.

    [![Selecteer Nu krijgen](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  Nadat de app is geïnstalleerd. Selecteer de tegel om deze te openen.

5.  Selecteer **De app Verkennen** om de app met voorbeeldgegevens weer te geven. Kies **Verbinding maken** om de app te verbinden met de gegevens van uw organisatie.

6.  Kies **Verbinden,** typ in het scherm Verbinding maken met **Microsoft 365** Gebruiksanalyse de tenant-id (zonder streepjes) die u in stap 1 hebt gekopieerd en selecteer **Volgende.**
    
7. Selecteer **OAuth2** in het volgende scherm als de **verificatiemethode** \> **Aanmelden.** Als u een andere verificatiemethode kiest, mislukt de verbinding met de sjabloon-app.
    
    ![Microsoft-account kiezen als verificatiemethode](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. Nadat de sjabloon-app is instantiated, is het dashboard voor Microsoft 365 Gebruiksanalyse beschikbaar in Power BI op het web. Het eerste laden van het dashboard duurt 2 tot 30 minuten.
  
Statistische tenantniveau zijn beschikbaar in alle rapporten nadat u zich heeftmeld. **Gebruikersdetails zijn pas beschikbaar** rond de vijfde van de volgende kalendermaand nadat u zich heeft gekozen. Dit is van invloed op alle rapporten onder Gebruikersactiviteit (zie Navigeren en de rapporten [gebruiken in Microsoft 365](navigate-and-utilize-reports.md) Gebruiksanalyse voor tips over het weergeven en gebruiken van deze rapporten).
    
## <a name="make-the-collected-data-anonymous"></a>Verzamelde gegevens anoniem maken

Alleen hoofdbeheerders kunnen de gegevens die worden verzameld voor alle rapporten anoniem maken. Hierdoor worden identificatiegegevens zoals namen van gebruikers, groepen en site's verborgen in rapporten en in de sjabloon-app.
  
1. Ga in het beheercentrum  naar Instellingen organisatie-instellingen en kies rapporten op het \>  **tabblad Services.** 
    
2. Selecteer **Rapporten** en kies voor **Het weergeven van anonieme id's.** Deze instelling wordt zowel op de gebruiksrapporten als op de sjabloon-app toegepast.
  
3. Selecteer **Wijzigingen opslaan**.
