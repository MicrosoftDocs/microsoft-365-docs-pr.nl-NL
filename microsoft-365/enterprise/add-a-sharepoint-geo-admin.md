---
title: Een geo-beheerder toevoegen of verwijderen
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: Wilt u afzonderlijke beheerders configureren voor elke geografische locatie? Meer informatie over het toevoegen of verwijderen van een geobeheerder in Microsoft 365 Multi-Geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 32fe5e934e6a3d6f18c802c3c427974e67c1b454
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905598"
---
# <a name="add-or-remove-a-geo-administrator-in-microsoft-365-multi-geo"></a>Een geobeheerder toevoegen of verwijderen in Microsoft 365 Multi-Geo

U kunt afzonderlijke beheerders configureren voor elke geografische locatie die u in uw tenant hebt. Deze beheerders hebben toegang tot de SharePoint Online en OneDrive instellingen die specifiek zijn voor hun geografische locatie.

Sommige services, zoals het termstore, worden vanaf de centrale locatie beheerd en gerepliceerd naar satellietlocaties. De geobeheerder voor de centrale locatie heeft hier toegang toe, terwijl geobeheerders voor satellietlocaties dat niet doen.

Globale beheerders en SharePoint onlinebeheerders hebben nog steeds toegang tot instellingen op de centrale locatie en alle satellietlocaties.

## <a name="configuring-geo-administrators"></a>Geobeheerders configureren

Voor het configureren van geobeheerders is SharePoint Online PowerShell-module vereist.

Gebruik [Verbinding maken-SPOService](/powershell/module/sharepoint-online/Connect-SPOService) om verbinding te maken met het beheercentrum van de geografische locatie waar u de geobeheerder wilt toevoegen. (Bijvoorbeeld Connect-SPOServicehttps://ContosoEUR-admin.sharepoint.com.)

Als u de bestaande geobeheerders van een locatie wilt weergeven, voer dan `Get-SPOGeoAdministrator`

### <a name="adding-a-user-as-a-geo-admin"></a>Een gebruiker toevoegen als geobeheerder

Als u een gebruiker wilt toevoegen als een geobeheerder, moet u `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`

Als u een gebruiker wilt verwijderen als geobeheerder van een locatie, moet u  `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`

### <a name="adding-a-group-as-a-geo-admin"></a>Een groep toevoegen als geobeheerder

U kunt als geobeheerder een beveiligingsgroep of een beveiligingsgroep met e-mail toevoegen. (Distributiegroepen en Microsoft 365 Groepen worden niet ondersteund.)

Als u een groep wilt toevoegen als geobeheerder, voer dan `Add-SPOGeoAdministrator -GroupAlias <alias>`

Als u een groep als geobeheerder wilt verwijderen, voer dan `Remove-SPOGeoAdministrator -GroupAlias <alias>`

Niet alle beveiligingsgroepen hebben een groepsalias. Als u een beveiligingsgroep wilt toevoegen die geen alias heeft, kunt u [Get-MsolGroup](/powershell/module/msonline/get-msolgroup) uitvoeren om een lijst met groepen op te halen, de ObjectID van uw beveiligingsgroep te zoeken en vervolgens het volgende uit te voeren:

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

Als u een groep wilt verwijderen met behulp van de ObjectID, voert u `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`

## <a name="related-topics"></a>Verwante onderwerpen

[Add-SPOGeoAdministrator](/powershell/module/sharepoint-online/add-spogeoadministrator)

[Get-SPOGeoAdministrator](/powershell/module/sharepoint-online/get-spogeoadministrator)

[Remove-SPOGeoAdministrator](/powershell/module/sharepoint-online/remove-spogeoadministrator)

[Een alias (MailNickName) instellen voor een beveiligingsgroep](/powershell/module/azuread/set-azureadgroup)