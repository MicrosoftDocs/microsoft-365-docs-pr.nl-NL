---
title: Instellingen interacties tussen Microsoft 365 Groepen en SharePoint
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Meer informatie over interacties tussen instellingen Microsoft 365 groepen en SharePoint
ms.openlocfilehash: 23e9553ce07514b18bafada5c93bcadab19806fe
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538157"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Instellingen interacties tussen Microsoft 365 Groepen en SharePoint

Sommige instellingen voor Microsoft 365 groepen en SharePoint in Microsoft 365, met name met betrekking tot delen en het maken van groepen en teamsite's, overlappen elkaar. In dit artikel vindt u beschrijvingen van deze interacties en aanbevolen procedures voor het werken met deze instellingen.

![Venn-diagram met SharePoint, Yammer en groepenfuncties](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>De effecten van SharePoint-instellingen op Microsoft 365 groepen

|SharePoint instelling|Omschrijving|Effect op Microsoft 365 groepen|Aanbeveling|
|:-----------------|:----------|:-----------------------------|:-------------|
|Extern delen voor organisatie en site|Hiermee wordt bepaald of sites, bestanden en mappen kunnen worden gedeeld met personen buiten de organisatie.|Als SharePoint- en groepeninstellingen niet overeenkomen, kunnen gasten in de groep worden geblokkeerd voor toegang tot de site of is externe toegang mogelijk beschikbaar op de site, maar niet in de groep.|Als u de instellingen voor delen wilt wijzigen, controleert u de instellingen voor groepen en SharePoint site-instellingen voor teamsites die met de groep zijn verbonden.<br><br>Zie [Samenwerken met gasten op een site.](./collaborate-in-site.md)|
|Domein toestaan/blokkeren|Hiermee kunt u voorkomen dat inhoud wordt gedeeld met opgegeven domeinen.|Groepen herkennen geen SharePoint lijsten toestaan of blokkeren. Gebruikers van domeinen die niet zijn toegestaan in SharePoint kunnen toegang krijgen tot SharePoint via een groep.|Manage domain allow/block lists for Azure AD and SharePoint together. Maak een organisatiebreed beheerproces voor het toestaan en blokkeren van domeinen.<br><br>Zie [SharePoint domeininstellingen en](/sharepoint/restricted-domains-sharing) Azure [AD-domeininstellingen](/azure/active-directory/b2b/allow-deny-list)|
|Alleen gebruikers in specifieke beveiligingsgroepen toestaan extern te delen|Hiermee geeft u beveiligingsgroepen op die sites, mappen en bestanden extern kunnen delen.|Deze instelling heeft geen invloed op groepseigenaren die groepen extern delen. Groepsgasten hebben toegang tot de bijbehorende SharePoint site.||
|SharePoint instellingen voor het delen van site|Hiermee bepaalt u wie de site rechtstreeks buiten het groepslidmaatschap kan delen. Dit is geconfigureerd door de eigenaar van de groep of site.|Deze instelling is niet rechtstreeks van invloed op de groep, maar kan wel toestaan dat gebruikers worden toegevoegd aan een site en geen toegang hebben tot andere groepsbronnen|U kunt deze instelling gebruiken om het delen van de site rechtstreeks te beperken en de sitetoegang via de groep te beheren.|
|Gebruikers sites laten maken vanaf SharePoint startpagina en OneDrive|Hiermee geeft u op of gebruikers nieuwe SharePoint kunnen maken.|Als deze instelling is uitgeschakeld, kunnen gebruikers nog steeds teamsites met een groep maken door een groep te maken.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>De effecten van Microsoft 365 groepen op SharePoint

|Microsoft 365 groepen instellen|Omschrijving|Effect op SharePoint|Aanbeveling|
|:---------------------------|:----------|:-------------------|:-------------|
|Beleid voor naamgeving|Hiermee geeft u groepsnaamvoorvoegsels en achtervoegsels op en geblokkeerde woorden voor het maken van groepen|Beleidsregels worden afgedwongen voor gebruikers die teamsites met een groep maken, maar niet communicatiesites of sites met andere sjablonen.|Maak indien nodig afzonderlijke naamgevingslijnen voor communicatiesites.|
|Groepstoegang voor gasten|Hiermee geeft u aan of personen buiten de organisatie kunnen worden toegevoegd aan groepen.|Als SharePoint- en groepeninstellingen niet overeenkomen, kunnen gasten in de groep worden geblokkeerd voor toegang tot de site of is externe toegang mogelijk beschikbaar op de site, maar niet in de groep.|Als u de instellingen voor delen wilt wijzigen, controleert u de instellingen voor groepen en SharePoint site-instellingen voor teamsites die met de groep zijn verbonden.<br><br>Zie [Samenwerken met gasten op een site](./collaborate-in-site.md)|
|Groep maken per beveiligingsgroep|Groepen kunnen alleen worden gemaakt door leden van een specifieke beveiligingsgroep.|Gebruikers die geen lid zijn van de beveiligingsgroep, kunnen geen teamsite met een groep maken.|Zorg ervoor dat uw proces voor het aanvragen van een groep instructies bevat voor het aanvragen van een site.|
|Verloopbeleid groep|Hiermee geeft u een periode op waarna groepen die niet actief worden gebruikt, automatisch worden verwijderd.|Wanneer de groep wordt verwijderd, wordt ook de SharePoint site verwijderd. Inhoud die is beveiligd met bewaarbeleid, blijft behouden.|Gebruik verloopbeleid om te voorkomen dat ongebruikte groepen en sites worden overgeslagen.|

## <a name="related-topics"></a>Verwante onderwerpen

[Planning van samenwerkingsbeheer stap voor stap](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Uw samenwerkingsbeheerplan maken](collaboration-governance-first.md)

[Samenwerken met personen buiten uw organisatie](./collaborate-with-people-outside-your-organization.md)

[Gebruikers hun eigen sites laten maken in SharePoint](/sharepoint/manage-site-creation)