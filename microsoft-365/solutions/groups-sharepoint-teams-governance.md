---
title: Instellingen interacties tussen Microsoft 365 groepen, Teams en SharePoint
ms.reviewer: ''
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
description: Meer informatie over interacties tussen instellingen Microsoft 365 groepen, Teams en SharePoint
ms.openlocfilehash: 14a21cd34fe38b47d93d0cbcec5e9cb2a3bc49c7
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539081"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Instellingen interacties tussen Microsoft 365 groepen, Teams en SharePoint

Sommige instellingen voor Microsoft 365 Groepen, Microsoft Teams en SharePoint in Microsoft 365, met name met betrekking tot delen en groeperen/team en SharePoint site maken, overlappen elkaar. In dit artikel vindt u beschrijvingen van deze interacties en aanbevolen procedures voor het werken met deze instellingen.

![Venn-diagram met SharePoint, Teams en groepenfuncties](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>De effecten van SharePoint instellingen voor groepen en teams

|SharePoint instelling|Omschrijving|Effect op Microsoft 365 groepen en Teams|Aanbeveling|
|:-----------------|:----------|:---------------------------------------|:-------------|
|Extern delen voor organisatie en site|Hiermee wordt bepaald of sites, bestanden en mappen kunnen worden gedeeld met personen buiten de organisatie.|Als SharePoint, groepen en Teams niet overeenkomen, kunnen gasten in het team worden geblokkeerd voor toegang tot de site of kan er onverwachte externe toegang optreden.|Als u de instellingen voor delen wilt wijzigen, controleert u De instellingen van groepen, Teams instellingen en SharePoint site-instellingen voor teamsites die met een groep zijn verbonden.<br><br> Zie [Samenwerken met gasten in een team](./collaborate-as-team.md)|
|Domein toestaan/blokkeren|Hiermee kunt u voorkomen dat inhoud wordt gedeeld met opgegeven domeinen.|Groepen en Teams herkennen geen SharePoint toestaan of blokkeren. Gebruikers van domeinen die niet zijn toegestaan in SharePoint kunnen toegang krijgen tot SharePoint sites of inhoud via een team.|Manage domain allow/block lists for Azure AD and SharePoint together. Maak een organisatiebreed beheerproces voor het toestaan en blokkeren van domeinen.<br><br>Zie [SharePoint domeininstellingen en](/sharepoint/restricted-domains-sharing) Azure [AD-domeininstellingen](/azure/active-directory/b2b/allow-deny-list)|
|Alleen gebruikers in specifieke beveiligingsgroepen toestaan extern te delen|Hiermee geeft u beveiligingsgroepen op die SharePoint sites, mappen en bestanden extern kunnen delen.|Deze instelling voorkomt niet dat teameigenaren teams extern kunnen delen. Teamgasten hebben toegang tot de bijbehorende SharePoint site.||
|SharePoint instellingen voor het delen van site|Hiermee bepaalt u wie de site rechtstreeks buiten het teamlidmaatschap kan delen. Dit is geconfigureerd door de team- of site-eigenaar.|Deze instelling is niet rechtstreeks van invloed op het team, maar kan wel toestaan dat gebruikers worden toegevoegd aan een site en geen toegang hebben tot het team zelf of andere Teams resources|U kunt deze instelling gebruiken om het delen van de site rechtstreeks te beperken en sitetoegang via het team te beheren.|
|Gebruikers sites laten maken vanaf SharePoint startpagina en OneDrive|Hiermee geeft u op of gebruikers nieuwe SharePoint kunnen maken.|Als deze instelling is uitgeschakeld, kunnen gebruikers nog steeds teamsites met een groep maken door een team te maken.||

## <a name="the-effects-of-groups-settings-on-teams"></a>De effecten van groepen-instellingen op teams

|Microsoft 365 groepen instellen|Omschrijving|Effect op Teams|Aanbeveling|
|:---------------------------|:----------|:--------------|:-------------|
|Beleid voor naamgeving|Hiermee geeft u groepsnaamvoorvoegsels en achtervoegsels op en geblokkeerde woorden voor het maken van groepen|Beleidsregels worden afgedwongen voor gebruikers die teams maken.||
|Groepstoegang voor gasten|Hiermee geeft u aan of personen buiten de organisatie kunnen worden toegevoegd aan groepen.|Als de instellingen voor het delen van Teams of groepen zijn uitgeschakeld, kan het team niet worden gedeeld met gasten.|Wanneer u de instellingen voor het delen van gasten verandert, controleert u de instellingen voor Teams, Groepen en de SharePoint site die is gekoppeld aan het team.<br><br> Zie [Samenwerken met gasten in een team](./collaborate-as-team.md)|
|Groep maken per beveiligingsgroep|Groepen kunnen alleen worden gemaakt door leden van een specifieke beveiligingsgroep.|Gebruikers die geen lid zijn van de beveiligingsgroep, kunnen geen team maken.|Zorg ervoor dat uw proces voor het aanvragen van een groep instructies bevat voor het aanvragen van een team of een SharePoint site.|
|Verloopbeleid groep|Hiermee geeft u een periode op waarna groepen die niet actief worden gebruikt, automatisch worden verwijderd.|Wanneer de groep wordt verwijderd, worden ook het team en de SharePoint site verwijderd. Inhoud die is beveiligd met bewaarbeleid, blijft behouden.|Gebruik verloopbeleid om te voorkomen dat ongebruikte teams, groepen en sites worden overgeslagen.|

## <a name="related-topics"></a>Verwante onderwerpen

[Planning van samenwerkingsbeheer stap voor stap](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Uw samenwerkingsbeheerplan maken](collaboration-governance-first.md)

[Samenwerken met personen buiten uw organisatie](./collaborate-with-people-outside-your-organization.md)

[Gebruikers hun eigen sites laten maken in SharePoint](/sharepoint/manage-site-creation)