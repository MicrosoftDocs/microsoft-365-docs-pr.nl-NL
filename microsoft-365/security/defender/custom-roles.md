---
title: Aangepaste rollen voor toegangsbeheer op basis van rollen
description: Informatie over het beheren van aangepaste rollen in Microsoft 365 beveiligingscentrum
keywords: access, permissions, Microsoft 365 Defender, M365, security, MCAS, Cloud App Security, Microsoft Defender for Endpoint, scope, scoping, RBAC, roles-based access, custom roles-based access, roles-based auth, RBAC in MDO, roles, rolegroups, permissions inheritance, fine-grained permissions
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 9dfa9f113c0a7d57360c2da6105cbfa07fcf6a99
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935687"
---
# <a name="custom-roles-in-role-based-access-control-for-microsoft-365-defender"></a>Aangepaste rollen in op rollen gebaseerd toegangsbeheer voor Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Van toepassing op:**

- Microsoft 365 Defender
 
Er zijn twee typen rollen die kunnen worden gebruikt om toegang te krijgen tot Microsoft 365 Defender:
- **Hoofdrollen Azure Active Directory (AD)**
- **Aangepaste rollen**

Toegang tot Microsoft 365 Defender kan gezamenlijk worden beheerd met behulp van globale rollen [in Azure Active Directory (AAD)](m365d-permissions.md)

Als u meer flexibiliteit en controle nodig hebt over de toegang tot specifieke productgegevens, kan Microsoft 365 Defender-toegang ook worden beheerd door aangepaste rollen te maken via elke beveiligingsportal.  

Met een aangepaste rol die is gemaakt via Microsoft Defender voor Eindpunt, kan bijvoorbeeld toegang worden tot de relevante productgegevens, waaronder eindpuntgegevens in het Microsoft 365 beveiligingscentrum. Een aangepaste rol die is gemaakt via Microsoft Defender voor Office 365, biedt toegang tot de relevante productgegevens, waaronder E-mail & samenwerkingsgegevens in het Microsoft 365 beveiligingscentrum.

Gebruikers met bestaande aangepaste rollen hebben toegang tot gegevens in het Microsoft 365 beveiligingscentrum op basis van hun bestaande werkbelastingmachtigingen zonder extra configuratie vereist.

## <a name="create-and-manage-custom-roles"></a>Aangepaste rollen maken en beheren
Aangepaste rollen en machtigingen kunnen worden gemaakt en afzonderlijk worden beheerd via elk van de volgende beveiligingsportalen: 

- Microsoft Defender voor eindpunt: [rollen bewerken in Microsoft Defender voor eindpunt](../defender-endpoint/user-roles.md)
- Microsoft Defender voor Office 365: [machtigingen in het beveiligings- & compliancecentrum](../office-365-security/permissions-in-the-security-and-compliance-center.md?preserve-view=true&view=o365-worldwide)
- Microsoft Cloud App Security: [beheerderstoegang beheren](/cloud-app-security/manage-admins)

Elke aangepaste rol die is gemaakt via een afzonderlijke portal, biedt toegang tot de gegevens van de relevante productportal. Een aangepaste rol die bijvoorbeeld is gemaakt via Microsoft Defender voor Eindpunt, biedt alleen toegang tot Gegevens van Defender voor eindpunten.

> [!TIP]
> Machtigingen en rollen kunnen ook worden weergegeven via het Microsoft 365 beveiligingscentrum door Machtigingen & rollen te selecteren in het navigatiedeelvenster. Toegang tot Microsoft Cloud App Security (MCAS) wordt beheerd via de MCAS-portal en bepaalt ook de toegang tot Microsoft Defender voor identiteit.  Zie [Microsoft Cloud App Security](/cloud-app-security/manage-admins)

> [!NOTE]
> Aangepaste rollen die zijn gemaakt in Microsoft Cloud App Security hebben ook toegang tot Microsoft Defender voor identiteitsgegevens. Gebruikers met gebruikersgroepbeheerder of app/instantiebeheerder Microsoft Cloud App Security kunnen geen toegang krijgen tot Microsoft Cloud App Security gegevens via het Microsoft 365 beveiligingscentrum.

## <a name="manage-permissions-and-roles-in-the-microsoft-365-security-center"></a>Machtigingen en rollen beheren in het Microsoft 365 beveiligingscentrum
Machtigingen en rollen kunnen ook worden beheerd in het Microsoft 365 beveiligingscentrum:

1. Meld u aan bij het Microsoft 365 beveiligingscentrum bij security.microsoft.com.
2. Selecteer in het navigatiedeelvenster **Machtigingen & rollen.**
3. Selecteer onder **de kop Machtigingen** de optie **Rollen**.

> [!NOTE]
> Dit geldt alleen voor Defender voor Office 365 en Defender voor Eindpunt. Toegang voor andere werkbelastingen moet worden uitgevoerd in de relevante portals.


## <a name="required-roles-and-permissions"></a>Vereiste rollen en machtigingen
In de volgende tabel worden de rollen en machtigingen beschreven die nodig zijn voor toegang tot elke geïntegreerde ervaring in elke werkbelasting. Rollen die in de onderstaande tabel zijn gedefinieerd, verwijzen naar aangepaste rollen in afzonderlijke portals en zijn niet verbonden met globale rollen in Azure AD, zelfs niet als ze op dezelfde naam staan.

> [!NOTE]
> Voor incidentbeheer zijn beheermachtigingen vereist voor alle producten die deel uitmaken van het incident.
 
| **Een van de volgende rollen is vereist voor Microsoft 365 Defender**  | **Een van de volgende rollen is vereist voor Defender voor Eindpunt**  | **Een van de volgende rollen is vereist voor Defender voor Office 365** | **Een van de volgende rollen is vereist voor Cloud App Security** | 
|---------|---------|---------|---------|
| Onderzoeksgegevens weergeven: <ul><li>Waarschuwingspagina</li> <li>Waarschuwingenwachtrij</li> <li>Incidenten</li>  <li>Incidentwachtrij</li> <li>Actiecentrum</li></ul>| Gegevensbeveiligingsbewerkingen weergeven | <ul><li>Alleen-weergeven Waarschuwingen beheren </li> <li>Organisatieconfiguratie</li><li>Auditlogboeken</li> <li>Alleen-weergeven auditlogboeken</li> <li>Beveiligingslezer</li> <li>Beveiligingsbeheerder</li><li>Alleen-weergeven geadresseerden</li></ul>  | <ul><li>Bedrijfsbeheerder</li> <li>Beveiligingsbeheerder</li> <li>Compliancebeheerder</li> <li>Beveiligingsoperator</li> <li>Beveiligingslezer</li> <li>Algemene lezer</li></ul> |
| Gegevens over jagen weergeven | Gegevensbeveiligingsbewerkingen weergeven | <ul><li>Beveiligingslezer</li> <li>Beveiligingsbeheerder</li> <li>Alleen-weergeven geadresseerden</li> | <ul><li>Bedrijfsbeheerder</li> <li>Beveiligingsbeheerder</li> <li>Compliancebeheerder</li> <li>Beveiligingsoperator</li> <li>Beveiligingslezer</li> <li>Algemene lezer</li></ul> |
| Waarschuwingen en incidenten beheren | Onderzoek naar waarschuwingen | <ul><li>Waarschuwingen beheren</li> <li>Beveiligingsbeheerder</li> | <ul><li>Bedrijfsbeheerder</li> <li>Beveiligingsbeheerder</li> <li>Compliancebeheerder</li> <li>Beveiligingsoperator</li> <li>Beveiligingslezer</li></ul> |
| Herstel van actiecentrum | Actieve herstelacties : beveiligingsbewerkingen | Zoeken en zuiveren | |
| Aangepaste detecties instellen | Beveiligingsinstellingen beheren |<ul><li>Waarschuwingen beheren</li> <li>Beveiligingsbeheerder</li></ul> | <ul><li>Bedrijfsbeheerder</li> <li>Beveiligingsbeheerder</li> <li>Compliancebeheerder</li> <li>Beveiligingsoperator</li> <li>Beveiligingslezer</li> <li>Algemene lezer</li></ul> |
| Dreigingsanalyse | Waarschuwingen en incidenten: <ul><li>Gegevensbeveiligingsbewerkingen weergeven</li></ul>TVM-risico's:<ul><li>Gegevens weergeven - Bedreiging en vulnerability management</li></ul> | Waarschuwingen en incidenten:<ul> <li>Alleen-weergeven Waarschuwingen beheren</li> <li>Waarschuwingen beheren</li> <li>Organisatieconfiguratie</li><li>Auditlogboeken</li> <li>Alleen-weergeven auditlogboeken</li><li>Beveiligingslezer</li> <li>Beveiligingsbeheerder</li><li>Alleen-weergeven geadresseerden</li> </ul> E-mailpogingen voorkomen: <ul><li>Beveiligingslezer</li> <li>Beveiligingsbeheerder</li><li>Alleen-weergeven geadresseerden</li> | Niet beschikbaar voor MCAS- of MDI-gebruikers |

Als u bijvoorbeeld de zoekgegevens van Microsoft Defender voor Eindpunt wilt bekijken, zijn machtigingen voor gegevensbeveiligingsbewerkingen weergeven vereist.  

Als u op zoek naar gegevens van Microsoft Defender voor Office 365 wilt weergeven, hebben gebruikers een van de volgende rollen nodig:  

- Gegevensbeveiligingsbewerkingen weergeven
- Beveiligingslezer
- Beveiligingsbeheerder
- Alleen-weergeven geadresseerden

## <a name="related-topics"></a>Verwante onderwerpen
- [Toegang tot Microsoft 365 Defender beheren](m365d-permissions.md)
- [Beheerderstoegang voor MCAS beheren](/cloud-app-security/manage-admins)
