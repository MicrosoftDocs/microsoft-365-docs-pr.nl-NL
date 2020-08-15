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
description: Wilt u afzonderlijke beheerders voor elke geografische locatie configureren? Meer informatie over het toevoegen of verwijderen van een geo-beheerder in Microsoft 365 multi-geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9a3d916bfec2c53850f923fb5322298e9ff440ca
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689525"
---
# <a name="add-or-remove-a-geo-administrator-in-microsoft-365-multi-geo"></a>Een geo-beheerder toevoegen of verwijderen in Microsoft 365 multi-geo

U kunt afzonderlijke beheerders configureren voor elke geografische locatie in uw Tenant. Deze beheerders hebben toegang tot de instellingen van SharePoint Online en OneDrive die specifiek zijn voor de geografische locatie.

Sommige services, zoals het termenarchief, worden beheerd vanaf de centrale locatie en worden gerepliceerd naar satelliet locaties. De geo-beheerder voor de centrale locatie heeft toegang tot deze, terwijl geo-beheerders voor satelliet locaties niet.

Globale beheerders en SharePoint Online-beheerders blijven toegang hebben tot de instellingen op de centrale locatie en alle satelliet locaties.

## <a name="configuring-geo-administrators"></a>Geo-beheerders configureren

Voor het configureren van geografische beheerders is PowerShell-module van SharePoint Online vereist.

Gebruik [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/Connect-SPOService) om verbinding te maken met het Beheercentrum van de geografische locatie waar u de geo-beheerder wilt toevoegen. (Bijvoorbeeld Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)

Als u de bestaande geo-beheerders van een locatie wilt weergeven, voert u `Get-SPOGeoAdministrator`

### <a name="adding-a-user-as-a-geo-admin"></a>Een gebruiker toevoegen als een geo-beheerder

Als u een gebruiker wilt toevoegen als een geo-beheerder, voert u `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`

Als u een gebruiker wilt verwijderen als een geo-beheerder van een locatie, voert u  `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`

### <a name="adding-a-group-as-a-geo-admin"></a>Een groep als een geo-beheerder toevoegen

U kunt een beveiligingsgroep of een beveiligingsgroep met e-mail als een geo-beheerder toevoegen. (Distributiegroepen en Microsoft 365 groepen worden niet ondersteund.)

Als u een groep wilt toevoegen als een geo-beheerder, voert u `Add-SPOGeoAdministrator -GroupAlias <alias>`

Als u een groep wilt verwijderen als een geo-beheerder, voert u `Remove-SPOGeoAdministrator -GroupAlias <alias>`

Houd er rekening mee dat niet alle beveiligingsgroepen een groepsalias hebben. Als u een beveiligingsgroep zonder alias wilt toevoegen, voert u [Get-Remove msolgroup](https://docs.microsoft.com/powershell/module/msonline/get-msolgroup) uit om een lijst met groepen op te halen, zoekt u de ObjectID van uw beveiligingsgroep en voert u de volgende opdracht uit:

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

Als u een groep wilt verwijderen met de ObjectID, voert u `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`

## <a name="related-topics"></a>Verwante onderwerpen

[Add-SPOGeoAdministrator](https://docs.microsoft.com/powershell/module/sharepoint-online/add-spogeoadministrator)

[Get-SPOGeoAdministrator](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spogeoadministrator)

[Remove-SPOGeoAdministrator](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spogeoadministrator)

[Een alias (mailnickname) voor een beveiligingsgroep instellen](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup)