---
title: Microsoft 365 Gebruiksanalyse inschakelen
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Meer informatie over het verzamelen van gegevens voor uw tenant met de Microsoft 365 de sjabloon-app Gebruiksanalyse in Power BI.
ms.openlocfilehash: c0e39a307ee75c661e0f91fcbbcfeae3d95c7257
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394747"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Microsoft 365 Gebruiksanalyse inschakelen

Microsoft 365 gebruiksanalyse is nog niet beschikbaar voor Microsoft 365 Amerikaanse overheidsgemeenschap.

## <a name="before-you-begin"></a>Voordat u begint

Als u wilt beginnen met Microsoft 365 gebruiksanalyse, moet u eerst de gegevens beschikbaar maken in de Microsoft 365-beheercentrum en vervolgens de sjabloon-app starten in Power BI.

## <a name="get-power-bi"></a>Power BI downloaden

Als u nog geen Power BI hebt, kunt u [zich registreren voor Power BI Pro.](https://go.microsoft.com/fwlink/p/?linkid=845347) Selecteer **Gratis proberen** om u aan te melden voor een proefabonnement of Nu kopen **om** uw Power BI Pro.


U kunt ook **Products** uitvouwen om een versie van Power BI te kopen.

> [!NOTE]
> U hebt een Power BI Pro nodig om een sjabloon-app te installeren, aan te passen en te distribueren. Zie Vereisten voor [meer informatie.](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)

Als u uw gegevens wilt delen, hebben zowel u als de personen met wie u de gegevens deelt, een Power BI Pro-licentie nodig of moet de inhoud zich in een werkruimte in een [Power BI premium-service.](/power-bi/service-premium-what-is)

## <a name="enable-the-template-app"></a>De sjabloon-app inschakelen

Als u de sjabloon-app wilt inschakelen, moet u een globale **beheerder zijn.**

Zie [beheerdersrollen voor](../add-users/about-admin-roles.md) meer informatie.

1. Ga in het beheercentrum naar het **tabblad Instellingen** \> **instellingen** \> **services.**

2. Selecteer op **het tabblad** Services de optie  **Rapporten**.

3. Stel in het deelvenster Rapporten dat wordt geopend rapportgegevens beschikbaar maken voor **Microsoft 365 gebruiksanalyse** voor Power BI op **Opslaan** \> .

Het proces voor het verzamelen van gegevens wordt in twee tot 48 uur voltooid, afhankelijk van de grootte van uw tenant. De knop **Ga naar Power BI** zal ingeschakeld zijn (niet langer grijs) als het verzamelen van gegevens is voltooid.

## <a name="start-the-template-app"></a>De sjabloon-app starten

Als u de sjabloon-app wilt starten, moet u een globale **beheerder,** **rapportlezer,** Exchange **beheerder,** Skype voor Bedrijven **beheerder** of SharePoint beheerder **zijn.**

1. Kopieer de tenant-id en selecteer **Ga naar Power BI.**

2. Meld u aan wanneer u in Power BI komt. Selecteer **vervolgens Apps** Downloaden van -> **apps** in het navigatiemenu.

3. In het tabblad **Apps** typt u Microsoft 365 in het zoekvak en selecteer vervolgens **Microsoft 365 Gebruiksanalyse** \> **Koop het vandaag nog**.

    [![Selecteer Nu krijgen](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)

4. Zodra de app is geïnstalleerd. Selecteer de tegel om deze te openen.

5. Selecteer **Verken de app** om de app te bekijken met voorbeeldgegevens. Kies **Verbinding maken** om de app te verbinden met de gegevens van uw organisatie.

6. Kies **Verbinding maken**, op het **scherm Verbinding maken** voor Microsoft 365 gebruiksanalyse, typ vervolgens de tenant-id (zonder streepjes) die u hebt gekopieerd in stap (1) en selecteer **Volgende**.

7. Selecteer in het volgende scherm **OAuth2** als **verificatiemethode** \> **Aanmelden**. Als u een andere verificatiemethode kiest, mislukt de verbinding met de sjabloon-app.

    ![Microsoft-account kiezen als verificatiemethode](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)

8. Nadat de sjabloon-app is instantiated, is Microsoft 365 dashboard voor gebruiksanalyse beschikbaar in Power BI op internet. Het eerste laden van het dashboard duurt 2 tot 30 minuten.

Aggregaten op tenantniveau zijn beschikbaar in alle rapporten nadat u zich heeft geaggregeerd. **Details op gebruikersniveau zijn pas beschikbaar rond de 5e van de volgende kalendermaand na** het kiezen van de . Dit is van invloed op alle rapporten onder Gebruikersactiviteit (Zie Navigeren en gebruik de rapporten in Microsoft 365 [gebruiksanalyse](navigate-and-utilize-reports.md) voor tips over het weergeven en gebruiken van deze rapporten).

## <a name="make-the-collected-data-anonymous"></a>Verzamelde gegevens anoniem maken

Alleen hoofdbeheerders kunnen de gegevens die worden verzameld voor alle rapporten anoniem maken. Hiermee worden identificeerbare gegevens zoals gebruikers-, groeps- en sitenamen in rapporten en in de sjabloon-app verborgen.

1. Ga in het beheercentrum naar de **Instellingen** Organisatie Instellingen en kies onder het \> tabblad **Services** de optie **Rapporten.**

2. Selecteer **Rapporten** en kies vervolgens **Anonieme id's weergeven.** Deze instelling wordt toegepast op zowel de gebruiksrapporten als op de sjabloon-app.

3. Selecteer **Wijzigingen opslaan**.

## <a name="related-content"></a>Verwante inhoud

[Over gebruiksanalyse](usage-analytics.md) (artikel)\
[De nieuwste versie van gebruiksanalyse](get-the-latest-version-of-usage-analytics.md) (artikel)\
[Navigeren en de rapporten gebruiken in Microsoft 365 gebruiksanalyse](navigate-and-utilize-reports.md) (artikel)