---
title: Interacties tussen Microsoft 365 Groepen en SharePoint
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
description: Meer informatie over instellingeninteracties tussen Microsoft 365 Groepen en SharePoint
ms.openlocfilehash: e1aeaca792fb551de503bd4c68256ccf14f45022
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921034"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Interacties tussen Microsoft 365 Groepen en SharePoint

Sommige instellingen voor Microsoft 365 Groepen en SharePoint in Microsoft 365, met name met betrekking tot delen en het maken van groepen en teamsite's, overlappen elkaar. In dit artikel vindt u beschrijvingen van deze interacties en aanbevolen procedures voor het werken met deze instellingen.

![Venn-diagram met SharePoint-, Yammer- en groepenfuncties](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>De effecten van SharePoint-instellingen op Microsoft 365-groepen

|SharePoint-instelling|Beschrijving|Effect op Microsoft 365-groepen|Aanbeveling|
|:-----------------|:----------|:-----------------------------|:-------------|
|Extern delen voor organisatie en site|Hiermee wordt bepaald of sites, bestanden en mappen kunnen worden gedeeld met personen buiten de organisatie.|Als de instellingen voor SharePoint en groepen niet overeenkomen, kunnen gasten in de groep worden geblokkeerd voor toegang tot de site of is externe toegang mogelijk beschikbaar op de site, maar niet in de groep.|Wanneer u de instellingen voor delen verandert, controleert u zowel de instellingen voor groepen als de SharePoint-site-instellingen voor teamsites die met de groep zijn verbonden.<br><br>Zie [Samenwerken met gasten op een site.](./collaborate-in-site.md)|
|Domein toestaan/blokkeren|Hiermee kunt u voorkomen dat inhoud wordt gedeeld met opgegeven domeinen.|Groepen herkennen geen SharePoint-lijsten toestaan of blokkeren. Gebruikers van domeinen die niet zijn toegestaan in SharePoint, kunnen toegang krijgen tot SharePoint via een groep.|Beheer lijsten met domein toestaan/blokkeren voor Azure AD en SharePoint samen. Maak een organisatiebreed beheerproces voor het toestaan en blokkeren van domeinen.<br><br>Zie [SharePoint-domeininstellingen en](/sharepoint/restricted-domains-sharing) [Azure AD-domeininstellingen](/azure/active-directory/b2b/allow-deny-list)|
|Alleen gebruikers in specifieke beveiligingsgroepen toestaan extern te delen|Hiermee geeft u beveiligingsgroepen op die sites, mappen en bestanden extern kunnen delen.|Deze instelling heeft geen invloed op groepseigenaren die groepen extern delen. Groepsgasten hebben toegang tot de bijbehorende SharePoint-site.||
|Instellingen voor delen van SharePoint-site|Hiermee bepaalt u wie de site rechtstreeks buiten het groepslidmaatschap kan delen. Dit is geconfigureerd door de eigenaar van de groep of site.|Deze instelling is niet rechtstreeks van invloed op de groep, maar kan wel toestaan dat gebruikers worden toegevoegd aan een site en geen toegang hebben tot andere groepsbronnen|U kunt deze instelling gebruiken om het delen van de site rechtstreeks te beperken en de sitetoegang via de groep te beheren.|
|Gebruikers sites laten maken vanaf de Startpagina van SharePoint en OneDrive|Hiermee geeft u op of gebruikers nieuwe SharePoint-sites kunnen maken.|Als deze instelling is uitgeschakeld, kunnen gebruikers nog steeds teamsites met een groep maken door een groep te maken.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>De effecten van de instelling voor Microsoft 365-groepen in SharePoint

|Instelling voor Microsoft 365-groepen|Beschrijving|Effect op SharePoint|Aanbeveling|
|:---------------------------|:----------|:-------------------|:-------------|
|Beleid voor naamgeving|Hiermee geeft u groepsnaamvoorvoegsels en achtervoegsels op en geblokkeerde woorden voor het maken van groepen|Beleidsregels worden afgedwongen voor gebruikers die teamsites met een groep maken, maar niet communicatiesites of sites met andere sjablonen.|Maak indien nodig afzonderlijke naamgevingslijnen voor communicatiesites.|
|Groepstoegang voor gasten|Hiermee geeft u aan of personen buiten de organisatie kunnen worden toegevoegd aan groepen.|Als de instellingen voor SharePoint en groepen niet overeenkomen, kunnen gasten in de groep worden geblokkeerd voor toegang tot de site of is externe toegang mogelijk beschikbaar op de site, maar niet in de groep.|Wanneer u de instellingen voor delen verandert, controleert u zowel de instellingen voor groepen als de SharePoint-site-instellingen voor teamsites die met de groep zijn verbonden.<br><br>Zie [Samenwerken met gasten op een site](./collaborate-in-site.md)|
|Groep maken per beveiligingsgroep|Groepen kunnen alleen worden gemaakt door leden van een specifieke beveiligingsgroep.|Gebruikers die geen lid zijn van de beveiligingsgroep, kunnen geen teamsite met een groep maken.|Zorg ervoor dat uw proces voor het aanvragen van een groep instructies bevat voor het aanvragen van een site.|
|Verloopbeleid groep|Hiermee geeft u een periode op waarna groepen die niet actief worden gebruikt, automatisch worden verwijderd.|Wanneer de groep wordt verwijderd, wordt ook de bijbehorende SharePoint-site verwijderd. Inhoud die is beveiligd met bewaarbeleid, blijft behouden.|Gebruik verloopbeleid om te voorkomen dat ongebruikte groepen en sites worden overgeslagen.|

## <a name="related-topics"></a>Verwante onderwerpen

[Planning van samenwerkingsbeheer stap voor stap](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Uw samenwerkingsbeheerplan maken](collaboration-governance-first.md)

[Samenwerken met personen buiten uw organisatie](./collaborate-with-people-outside-your-organization.md)

[Gebruikers hun eigen sites laten maken in SharePoint](/sharepoint/manage-site-creation)