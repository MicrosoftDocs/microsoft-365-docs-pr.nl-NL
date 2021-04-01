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
ms.openlocfilehash: 734712994d47fcb234ba988bb4d185d09f3267d0
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471055"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Microsoft 365 Gebruiksanalyse inschakelen

Microsoft 365 gebruiksanalyse is nog niet beschikbaar voor de Amerikaanse overheid van Microsoft 365.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Stappen voor het inschakelen van Microsoft 365 Gebruiksanalyse

Als u wilt beginnen met gebruiksanalyses van Microsoft 365, moet u eerst de gegevens beschikbaar stellen in het Microsoft 365-beheercentrum en vervolgens de sjabloon-app starten in Power BI.
  
### <a name="get-power-bi"></a>Power BI downloaden

Als u Power BI nog niet hebt, kunt u [zich registreren voor Power BI Pro.](https://go.microsoft.com/fwlink/p/?linkid=845347) Selecteer **Gratis proberen** om u aan te melden voor een proefabonnement of Nu kopen **om** Power BI Pro te downloaden.
  
  
U kunt ook **Products** uitvouwen om een versie van Power BI te kopen. 

> [!NOTE]
> U hebt een Power BI Pro-licentie nodig om een sjabloon-app te installeren, aan te passen en te distribueren. Zie Vereisten voor [meer informatie.](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)

Als u uw gegevens wilt delen, hebben u en de personen met wie u de gegevens deelt, een Power BI Pro-licentie nodig of moet de inhoud zich in een werkruimte in een [Power BI Premium-service hebben.](/power-bi/service-premium-what-is) 
  
### <a name="enable-the-template-app"></a>De sjabloon-app inschakelen

Als u de sjabloon-app wilt inschakelen, moet u een globale **beheerder zijn.**
  
Zie [beheerdersrollen voor](../add-users/about-admin-roles.md) meer informatie. 
  
1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>. 
    
2. Zoek op **de** pagina Gebruik de **microsoft 365-gebruiksanalysekaart** en selecteer **Aan de slag.**
    
3. Stel gegevens beschikbaar maken voor **Microsoft 365** gebruiksanalyse voor Power BI in op Opslaan in het deelvenster Rapporten **dat wordt** \> **geopend.** 
  
Het proces voor het verzamelen van gegevens wordt in twee tot 48 uur voltooid, afhankelijk van de grootte van uw tenant. De knop **Ga naar Power BI** zal ingeschakeld zijn (niet langer grijs) als het verzamelen van gegevens is voltooid. 
    
### <a name="start-the-template-app"></a>De sjabloon-app starten

Als u de sjabloon-app wilt starten, moet u een globale **beheerder,** **rapportlezer,** **Exchange-beheerder,** **Skype voor Bedrijven-beheerder** of **SharePoint-beheerder zijn.** 
  
1. Kopieer de tenant-id en selecteer **Ga naar Power BI.**
    
2.  Meld u aan wanneer u in Power BI komt. Selecteer **vervolgens Apps** Downloaden van -> **apps** in het navigatiemenu.    
  
3. In het tabblad **Apps** typt u Microsoft 365 in het zoekvak en selecteer vervolgens **Microsoft 365 Gebruiksanalyse** \> **Koop het vandaag nog**.

    [![Selecteer Nu krijgen](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  Zodra de app is geïnstalleerd. Selecteer de tegel om deze te openen.

5.  Selecteer **Verken de app** om de app te bekijken met voorbeeldgegevens. Kies **Verbinding** maken om de app te verbinden met de gegevens van uw organisatie.

6.  Kies **Verbinding** maken in het scherm Verbinding maken met **Microsoft 365** gebruiksanalyse en typ vervolgens de tenant-id (zonder streepjes) die u hebt gekopieerd in stap (1) en selecteer **Volgende**.
    
7. Selecteer in het volgende scherm **OAuth2** als **verificatiemethode** \> **Aanmelden**. Als u een andere verificatiemethode kiest, mislukt de verbinding met de sjabloon-app.
    
    ![Microsoft-account kiezen als verificatiemethode](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. Nadat de sjabloon-app is instantiated, is het Microsoft 365-dashboard voor gebruiksanalyse beschikbaar in de webwinkel van Power BI. Het eerste laden van het dashboard duurt 2 tot 30 minuten.
  
Aggregaten op tenantniveau zijn beschikbaar in alle rapporten nadat u zich heeft geaggregeerd. **Details op gebruikersniveau zijn pas beschikbaar rond de 5e van de volgende kalendermaand na** het kiezen van de . Dit is van invloed op alle rapporten onder Gebruikersactiviteit (Zie Navigeren en gebruik de rapporten in Gebruiksanalyse van [Microsoft 365](navigate-and-utilize-reports.md) voor tips over het weergeven en gebruiken van deze rapporten).
    
## <a name="make-the-collected-data-anonymous"></a>Verzamelde gegevens anoniem maken

Alleen hoofdbeheerders kunnen de gegevens die worden verzameld voor alle rapporten anoniem maken. Hiermee worden identificeerbare gegevens zoals gebruikers-, groeps- en sitenamen in rapporten en in de sjabloon-app verborgen.
  
1. Ga in het beheercentrum naar **instellingen** \> **voor organisatie-instellingen** en kies onder **het tabblad Services** de optie **Rapporten.**
    
2. Selecteer **Rapporten** en kies vervolgens **Anonieme id's weergeven.** Deze instelling wordt toegepast op zowel de gebruiksrapporten als op de sjabloon-app.
  
3. Selecteer **Wijzigingen opslaan**.