---
title: Instellingen interacties tussen Microsoft 365 groepen en SharePoint
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
description: Meer informatie over instellingen interacties tussen Microsoft 365 groepen en SharePoint
ms.openlocfilehash: e8d4189c2d945d5a6d2aa78bd7ea980a77360ce0
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377555"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Instellingen interacties tussen Microsoft 365 groepen en SharePoint

Bepaalde instellingen voor Microsoft 365-groepen en SharePoint in Microsoft 365, met name met het maken van delen en het maken van groepen en team sites, overlappen elkaar onderling. In dit artikel vindt u beschrijvingen van deze interacties en aanbevolen procedures voor het werken met deze instellingen.

![Venn-diagram van functies van SharePoint, Yammer en groepen](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>De effecten van SharePoint-instellingen voor Microsoft 365-groepen

|SharePoint-instelling|Beschrijving|Effect voor Microsoft 365-groepen|Aanbeveling|
|:-----------------|:----------|:-----------------------------|:-------------|
|Extern delen voor organisatie en site|Hiermee bepaalt u of sites, bestanden en mappen kunnen worden gedeeld met personen buiten de organisatie.|Als de instellingen voor SharePoint en groepen niet overeenkomen, is het mogelijk dat gasten in de groep zijn geblokkeerd voor het openen van de site of omdat externe toegang beschikbaar is op de site, maar niet op de groep.|Wanneer u instellingen voordelen wijzigt, schakelt u de optie beide groepen en de instellingen van de SharePoint-site in voor team sites die met groepen zijn verbonden.<br><br>Zie [samenwerken met gasten op een site](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site).|
|Domein toestaan/blokkeren|Maakt of verhindert dat inhoud met opgegeven domeinen wordt gedeeld.|Groepen worden niet door SharePoint toegestaan of geblokkeerd lijsten herkend. Gebruikers van domeinen die niet zijn toegestaan in SharePoint kunnen toegang krijgen tot SharePoint via een groep.|De weergave van domein toestaan/blokkeren voor Azure AD en SharePoint samen beheren. Maak een beheerproces voor hele organisatie voor het toestaan en blokkeren van domeinen.<br><br>Zie [SharePoint-Domeininstellingen](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) en [Azure AD-Domeininstellingen](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
|Toestaan dat alleen gebruikers in bepaalde beveiligingsgroepen extern delen|Hiermee geeft u beveiligingsgroepen op die sites, mappen en bestanden extern kunnen delen.|Deze instelling geldt niet voor groepseigenaren die extern groepen delen. Groeps gasten hebben toegang tot de bijbehorende SharePoint-site.||
|Instellingen voordelen van SharePoint-sites|Bepaalt wie de site direct kan delen buiten het groepslidmaatschap. Dit is de naam van de groep of site-eigenaar.|Deze instelling is niet rechtstreeks van invloed op de groep, maar het is ook mogelijk dat gebruikers worden toegevoegd aan een site en geen toegang hebben tot andere groeps resources.|U kunt deze instelling gebruiken om het delen van de site direct te beperken en de site toegang via de groep te beheren.|
|Gebruikers sites laten maken vanaf de startpagina van SharePoint en OneDrive|Hiermee geeft u op of gebruikers nieuwe SharePoint-sites kunnen maken.|Als deze instelling is uitgeschakeld, kunnen gebruikers wel team sites met groepen maken door een groep te maken.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>De effecten van de instelling Microsoft 365 groepen in SharePoint

|Instelling voor Microsoft 365-groepen|Beschrijving|Effect op SharePoint|Aanbeveling|
|:---------------------------|:----------|:-------------------|:-------------|
|Beleid voor naamgeving|Hiermee geeft u de naam van de groepsnaam en achtervoegsels en de geblokkeerde woorden voor het maken van een groep op|Beleidsregels worden afgedwongen voor gebruikers die met een groep verbonden team sites maken, maar geen Communicatiesites of sites met andere sjablonen.|Maak indien nodig aparte instructies voor de naamgeving van Communicatiesites.|
|Gasttoegang voor groepen|Hiermee geeft u op of personen buiten de organisatie kunnen worden toegevoegd aan groepen.|Als de instellingen voor SharePoint en groepen niet overeenkomen, is het mogelijk dat gasten in de groep zijn geblokkeerd voor het openen van de site of omdat externe toegang beschikbaar is op de site, maar niet op de groep.|Wanneer u instellingen voordelen wijzigt, schakelt u de optie beide groepen en de instellingen van de SharePoint-site in voor team sites die met groepen zijn verbonden.<br><br>Zie [samenwerken met gasten op een site](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site)|
|Groepen maken op basis van beveiligingsgroep|Groepen kunnen alleen worden gemaakt door leden van een bepaalde beveiligingsgroep.|Gebruikers die geen lid zijn van de beveiligingsgroep, kunnen geen team site met een groep maken.|Zorg ervoor dat uw proces voor het aanvragen van een groep de instructies bevat voor het aanvragen van een site.|
|Verloopbeleid voor groepen|Hiermee wordt een periode opgegeven waarna groepen die niet actief worden gebruikt, automatisch worden verwijderd.|Wanneer de groep is verwijderd, wordt de gekoppelde SharePoint-site ook verwijderd. Inhoud die is beveiligd met een bewaarbeleid blijft behouden.|Gebruik verloopbeleid om sprawl van ongebruikte groepen en sites te voorkomen.|

## <a name="related-topics"></a>Verwante onderwerpen

[Samenwerken met personen buiten uw organisatie](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Sites maken in SharePoint beheren](https://docs.microsoft.com/sharepoint/manage-site-creation)