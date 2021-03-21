---
title: Aangepaste rollen voor toegangsbeheer op basis van rollen
description: Meer informatie over het beheren van aangepaste rollen in het Microsoft 365-beveiligingscentrum
keywords: access, permissions, MTP, Microsoft Threat Protection, M365, security, MCAS, MDATP, Cloud App Security, Microsoft Defender Advanced Threat Protection, scope, scoping, RBAC, roles-based access, custom roles-based access, roles-based auth, RBAC in MDO, roles, rolegroups, permissions inheritance, fine-grained permissions
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 35ac4e26406fe6fde1385008b527dc4865e0392b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928926"
---
# <a name="custom-roles-in-role-based-access-control-for-microsoft-365-defender"></a>Aangepaste rollen in toegangsbeheer op basis van rollen voor Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Van toepassing op:**

- Microsoft 365 Defender
 
Er zijn twee typen rollen die kunnen worden gebruikt voor toegang tot Microsoft 365 Defender:
- **Ad-rollen (Global Azure Active Directory)**
- **Aangepaste rollen**

Toegang tot Microsoft 365 Defender kan gezamenlijk worden beheerd met behulp van [globale rollen in Azure Active Directory (AAD)](mtp-permissions.md)

Als u meer flexibiliteit en controle nodig hebt over de toegang tot specifieke productgegevens, kan microsoft 365 Defender-toegang ook worden beheerd door aangepaste rollen te maken via elke beveiligingsportal.  

Met een aangepaste rol die is gemaakt via Microsoft Defender voor Eindpunt, kan bijvoorbeeld toegang worden tot de relevante productgegevens, inclusief eindpuntgegevens in het Microsoft 365-beveiligingscentrum. Op dezelfde manier biedt een aangepaste rol die is gemaakt via Microsoft Defender voor Office 365 toegang tot de relevante productgegevens, waaronder E-mail & samenwerkingsgegevens in het Microsoft 365-beveiligingscentrum.

Gebruikers met bestaande aangepaste rollen hebben toegang tot gegevens in het Microsoft 365-beveiligingscentrum op basis van hun bestaande werkbelastingmachtigingen zonder extra configuratie vereist.

## <a name="create-and-manage-custom-roles"></a>Aangepaste rollen maken en beheren
Aangepaste rollen en machtigingen kunnen worden gemaakt en afzonderlijk worden beheerd via elk van de volgende beveiligingsportalen: 

- Microsoft Defender voor eindpunt: [rollen bewerken in Microsoft Defender voor eindpunt](/windows/security/threat-protection/microsoft-defender-atp/user-roles)
- Microsoft Defender voor Office 365: [machtigingen in het beveiligings- & compliancecentrum](../office-365-security/permissions-in-the-security-and-compliance-center.md?preserve-view=true&view=o365-worldwide)
- Microsoft Cloud App Security – [Beheerderstoegang beheren](/cloud-app-security/manage-admins)

Elke aangepaste rol die is gemaakt via een afzonderlijke portal, biedt toegang tot de gegevens van de relevante productportal. Een aangepaste rol die bijvoorbeeld is gemaakt via Microsoft Defender voor Eindpunt, biedt alleen toegang tot Gegevens van Defender voor eindpunten.

> [!TIP]
> Machtigingen en rollen zijn ook toegankelijk via het Microsoft 365-beveiligingscentrum door Machtigingen & rollen te selecteren in het navigatiedeelvenster. Toegang tot Microsoft Cloud App Security (MCAS) wordt beheerd via de MCAS-portal en bepaalt ook de toegang tot Microsoft Defender voor identiteit.  Zie [Microsoft Cloud App Security](/cloud-app-security/manage-admins)

> [!NOTE]
> Aangepaste rollen die zijn gemaakt in Microsoft Cloud App Security hebben ook toegang tot Microsoft Defender voor identiteitsgegevens. Gebruikers met gebruikersgroepbeheerder of app-/exemplaarbeheerder Microsoft Cloud App Security-rollen hebben geen toegang tot beveiligingsgegevens van Microsoft Cloud App via het Microsoft 365-beveiligingscentrum.

## <a name="manage-permissions-and-roles-in-the-microsoft-365-security-center"></a>Machtigingen en rollen beheren in het Microsoft 365-beveiligingscentrum
Machtigingen en rollen kunnen ook worden beheerd in het Microsoft 365-beveiligingscentrum:

1. Meld u aan bij het Microsoft 365-beveiligingscentrum security.microsoft.com.
2. Selecteer in het navigatiedeelvenster **Machtigingen & rollen.**
3. Selecteer onder **de kop Machtigingen** de optie **Rollen**.

> [!NOTE]
> Dit geldt alleen voor Defender voor Office 365 en Defender voor Eindpunt. Toegang voor andere werkbelastingen moet worden uitgevoerd in de relevante portals.


## <a name="required-roles-and-permissions"></a>Vereiste rollen en machtigingen
In de volgende tabel worden de rollen en machtigingen beschreven die nodig zijn voor toegang tot elke geïntegreerde ervaring in elke werkbelasting. Rollen die in de onderstaande tabel zijn gedefinieerd, verwijzen naar aangepaste rollen in afzonderlijke portals en zijn niet verbonden met globale rollen in Azure AD, zelfs niet als ze op dezelfde naam staan.

> [!NOTE]
> Voor incidentbeheer zijn beheermachtigingen vereist voor alle producten die deel uitmaken van het incident.
 
| **Een van de volgende rollen zijn vereist voor Microsoft 365 Defender**  | **Een van de volgende rollen is vereist voor Defender voor Eindpunt**  | **Een van de volgende rollen is vereist voor Defender voor Office 365** | **Een van de volgende rollen zijn vereist voor cloud-app-beveiliging** | 
|---------|---------|---------|---------|
| Onderzoeksgegevens weergeven: <ul><li>Waarschuwingspagina</li> <li>Waarschuwingenwachtrij</li> <li>Incidenten</li>  <li>Incidentwachtrij</li> <li>Actiecentrum</li></ul>| Gegevensbeveiligingsbewerkingen weergeven | <ul><li>Alleen-weergeven Waarschuwingen beheren </li> <li>Organisatieconfiguratie</li><li>Auditlogboeken</li> <li>Alleen-weergeven auditlogboeken</li> <li>Beveiligingslezer</li> <li>Beveiligingsbeheerder</li><li>Alleen-weergeven geadresseerden</li></ul>  | <ul><li>Algemeen beheerder</li> <li>Beveiligingsbeheerder</li> <li>Beheerder voor naleving</li> <li>Beveiligingsoperator</li> <li>Beveiligingslezer</li> <li>Algemene lezer</li></ul> |
| Gegevens over jagen weergeven | Gegevensbeveiligingsbewerkingen weergeven | <ul><li>Beveiligingslezer</li> <li>Beveiligingsbeheerder</li> <li>Alleen-weergeven geadresseerden</li> | <ul><li>Algemeen beheerder</li> <li>Beveiligingsbeheerder</li> <li>Beheerder voor naleving</li> <li>Beveiligingsoperator</li> <li>Beveiligingslezer</li> <li>Algemene lezer</li></ul> |
| Waarschuwingen en incidenten beheren | Onderzoek naar waarschuwingen | <ul><li>Waarschuwingen beheren</li> <li>Beveiligingsbeheerder</li> | <ul><li>Algemeen beheerder</li> <li>Beveiligingsbeheerder</li> <li>Beheerder voor naleving</li> <li>Beveiligingsoperator</li> <li>Beveiligingslezer</li></ul> |
| Herstel van actiecentrum | Actieve herstelacties : beveiligingsbewerkingen | Zoeken en zuiveren | |
| Aangepaste detecties instellen | Beveiligingsinstellingen beheren |<ul><li>Waarschuwingen beheren</li> <li>Beveiligingsbeheerder</li></ul> | <ul><li>Algemeen beheerder</li> <li>Beveiligingsbeheerder</li> <li>Beheerder voor naleving</li> <li>Beveiligingsoperator</li> <li>Beveiligingslezer</li> <li>Algemene lezer</li></ul> |
| Bedreigingsanalyse | Waarschuwingen en incidenten: <ul><li>Gegevensbeveiligingsbewerkingen weergeven</li></ul>TVM-risico's:<ul><li>Gegevens weergeven - Bedreigings- en kwetsbaarheidsbeheer</li></ul> | Waarschuwingen en incidenten:<ul> <li>Alleen-weergeven Waarschuwingen beheren</li> <li>Waarschuwingen beheren</li> <li>Organisatieconfiguratie</li><li>Auditlogboeken</li> <li>Alleen-weergeven auditlogboeken</li><li>Beveiligingslezer</li> <li>Beveiligingsbeheerder</li><li>Alleen-weergeven geadresseerden</li> </ul> E-mailpogingen voorkomen: <ul><li>Beveiligingslezer</li> <li>Beveiligingsbeheerder</li><li>Alleen-weergeven geadresseerden</li> | Niet beschikbaar voor MCAS- of MDI-gebruikers |

Als u bijvoorbeeld de zoekgegevens van Microsoft Defender voor Eindpunt wilt bekijken, zijn machtigingen voor gegevensbeveiligingsbewerkingen weergeven vereist.  

Als u de gegevens van Microsoft Defender voor Office 365 wilt bekijken, hebben gebruikers een van de volgende rollen nodig:  

- Gegevensbeveiligingsbewerkingen weergeven
- Beveiligingslezer
- Beveiligingsbeheerder
- Alleen-weergeven geadresseerden

## <a name="related-topics"></a>Verwante onderwerpen
- [Toegang tot Microsoft 365 Defender beheren](mtp-permissions.md)
- [Beheerderstoegang voor MCAS beheren](/cloud-app-security/manage-admins)