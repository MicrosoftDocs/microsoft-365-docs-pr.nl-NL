---
title: Instellingen interacties tussen Microsoft 365 groepen, teams en SharePoint
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
description: Meer informatie over instellingen interacties tussen Microsoft 365 groepen, teams en SharePoint
ms.openlocfilehash: 3a6d4e057f88410a8808ea133bf7e579d0041228
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377543"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Instellingen interacties tussen Microsoft 365 groepen, teams en SharePoint

Bepaalde instellingen voor Microsoft 365-groepen, Microsoft teams en SharePoint in Microsoft 365, met name in verband met het maken van delen en het maken van een groep/team en het maken van SharePoint-sites, overlappen elkaar. In dit artikel vindt u beschrijvingen van deze interacties en aanbevolen procedures voor het werken met deze instellingen.

![Venn-diagram van functies van SharePoint, teams en groepen](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>De effecten van SharePoint-instellingen voor groepen en teams

|SharePoint-instelling|Beschrijving|Effect voor groepen en teams in Microsoft 365|Aanbeveling|
|:-----------------|:----------|:---------------------------------------|:-------------|
|Extern delen voor organisatie en site|Hiermee bepaalt u of sites, bestanden en mappen kunnen worden gedeeld met personen buiten de organisatie.|Als de instellingen voor SharePoint, groepen en teams niet overeenkomen, is het mogelijk dat gasten in het team geen toegang hebben tot de site of onverwachte externe toegang kunnen plaatsvinden.|Wanneer u de instellingen voordelen wijzigt, schakelt u de optie instellingen voor groepen, teams-instellingen en SharePoint-site-instellingen in voor op groepen gekoppelde team sites.<br><br> Zie [samenwerken met gasten in een team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)|
|Domein toestaan/blokkeren|Maakt of verhindert dat inhoud met opgegeven domeinen wordt gedeeld.|Voor groepen en teams wordt niet toegestaan lijsten van SharePoint toestaan of blokkeren herkend. Gebruikers van domeinen die niet zijn toegestaan in SharePoint kunnen toegang krijgen tot SharePoint-sites of inhoud via een team.|De weergave van domein toestaan/blokkeren voor Azure AD en SharePoint samen beheren. Maak een beheerproces voor hele organisatie voor het toestaan en blokkeren van domeinen.<br><br>Zie [SharePoint-Domeininstellingen](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) en [Azure AD-Domeininstellingen](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
|Toestaan dat alleen gebruikers in bepaalde beveiligingsgroepen extern delen|Hiermee geeft u beveiligingsgroepen op die SharePoint-sites, mappen en bestanden extern kunnen delen.|Met deze instelling wordt niet voorkomen dat team eigenaren teams extern delen. Team gasten hebben toegang tot de bijbehorende SharePoint-site.||
|Instellingen voordelen van SharePoint-sites|Bepaalt wie de site rechtstreeks kan delen buiten het team lidmaatschap. Dit wordt geconfigureerd door de eigenaar van het team of de site.|Deze instelling is niet rechtstreeks van invloed op het team, maar het is wel toegestaan dat gebruikers worden toegevoegd aan een site en geen toegang hebben tot het team zelf of met de resources van andere teams.|U kunt deze instelling gebruiken om het delen van de site direct te beperken en de site toegang te beheren via het team.|
|Gebruikers sites laten maken vanaf de startpagina van SharePoint en OneDrive|Hiermee geeft u op of gebruikers nieuwe SharePoint-sites kunnen maken.|Als deze instelling is uitgeschakeld, kunnen gebruikers wel team sites met groepen maken door een team te maken.||

## <a name="the-effects-of-groups-settings-on-teams"></a>De effecten van groepsinstellingen in teams

|Instelling voor Microsoft 365-groepen|Beschrijving|Effect op teams|Aanbeveling|
|:---------------------------|:----------|:--------------|:-------------|
|Beleid voor naamgeving|Hiermee geeft u de naam van de groepsnaam en achtervoegsels en de geblokkeerde woorden voor het maken van een groep op|Beleidsregels worden afgedwongen voor gebruikers die teams maken.||
|Gasttoegang voor groepen|Hiermee geeft u op of personen buiten de organisatie kunnen worden toegevoegd aan groepen.|Als de instellingen voor gast delen van de groepen of teams zijn uitgeschakeld, kan het team niet worden gedeeld met gasten.|Wanneer u instellingen voor het delen van gasten wijzigt, controleert u de instellingen voor teams, groepen en de SharePoint-site die is gekoppeld aan het team.<br><br> Zie [samenwerken met gasten in een team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)|
|Groepen maken op basis van beveiligingsgroep|Groepen kunnen alleen worden gemaakt door leden van een bepaalde beveiligingsgroep.|Gebruikers die geen lid zijn van de beveiligingsgroep, kunnen geen team maken.|Zorg ervoor dat uw proces voor het aanvragen van een groep de instructies bevat voor het aanvragen van een team of een SharePoint-site.|
|Verloopbeleid voor groepen|Hiermee wordt een periode opgegeven waarna groepen die niet actief worden gebruikt, automatisch worden verwijderd.|Wanneer de groep is verwijderd, worden het team en de gekoppelde SharePoint-site ook verwijderd. Inhoud die is beveiligd met een bewaarbeleid blijft behouden.|Gebruik een verloopbeleid om te voorkomen dat ongebruikte teams, groepen en sites worden sprawl.|

## <a name="related-topics"></a>Verwante onderwerpen

[Samenwerken met personen buiten uw organisatie](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Sites maken in SharePoint beheren](https://docs.microsoft.com/sharepoint/manage-site-creation)
