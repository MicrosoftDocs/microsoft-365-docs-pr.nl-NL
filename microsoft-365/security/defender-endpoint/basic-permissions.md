---
title: Basismachtigingen gebruiken om toegang te krijgen tot het Microsoft Defender-beveiligingscentrum
description: Meer informatie over het gebruik van basismachtigingen voor toegang tot de Microsoft Defender for Endpoint-portal.
keywords: gebruikersrollen toewijzen, lees- en schrijftoegang toewijzen, alleen-lezentoegang toewijzen, gebruiker, gebruikersrollen, rollen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: cb5762d2a9e4b62432aba6dacd1033ddc3c7daf2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163669"
---
# <a name="use-basic-permissions-to-access-the-portal"></a>Basismachtigingen gebruiken om toegang te krijgen tot de portal

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft Azure Active Directory
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

Raadpleeg de onderstaande instructies voor het gebruik van basismachtigingenbeheer.

U kunt een van de volgende oplossingen gebruiken:
- Azure PowerShell
- Azure-portal

Voor gedetailleerde controle over machtigingen schakelt u over naar toegangsbesturingselement [op basis van rollen.](rbac.md)

## <a name="assign-user-access-using-azure-powershell"></a>Gebruikerstoegang toewijzen met Azure PowerShell
U kunt gebruikers toewijzen met een van de volgende machtigingsniveaus:
- Volledige toegang (lezen en schrijven)
- Alleen-lezen toegang

### <a name="before-you-begin"></a>Voordat u begint

- Installeer Azure PowerShell. Zie Azure PowerShell installeren en configureren voor meer [informatie.](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)<br>

    > [!NOTE]
    > U moet de PowerShell-cmdlets uitvoeren op een verhoogde opdrachtregel.

- Maak verbinding met uw Azure Active Directory. Zie [Connect-MsolService](https://docs.microsoft.com/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true)voor meer informatie.

**Volledige toegang** <br>
Gebruikers met volledige toegang kunnen zich aanmelden, alle systeemgegevens bekijken en waarschuwingen oplossen, bestanden indienen voor uitgebreide analyse en het onboarding-pakket downloaden.
Als u volledige toegangsrechten toewijst, moeten de gebruikers worden toegevoegd aan de ingebouwde rollen 'Beveiligingsbeheerder' of 'Globale beheerder'.

**Alleen-lezen toegang** <br>
Gebruikers met alleen-lezen toegang kunnen zich aanmelden, alle waarschuwingen en gerelateerde informatie bekijken.
Ze kunnen geen waarschuwingstoestanden wijzigen, bestanden indienen voor uitgebreide analyse of statuswijzigingsbewerkingen uitvoeren.
Als u alleen-lezentoegangsrechten toewijst, moeten de gebruikers worden toegevoegd aan de ingebouwde azure AD-rol 'Beveiligingslezer'.

Gebruik de volgende stappen om beveiligingsrollen toe te wijzen:

- Voor **lees- en schrijftoegang** wijst u gebruikers toe aan de rol van beveiligingsbeheerder met de volgende opdracht:

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- Voor **alleen-lezentoegang** wijst u gebruikers toe aan de rol van de beveiligingslezer met de volgende opdracht:

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

Zie Groepsleden toevoegen of verwijderen met Azure Active Directory voor [meer informatie.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

## <a name="assign-user-access-using-the-azure-portal"></a>Gebruikerstoegang toewijzen met de Azure-portal

Zie Beheerders- en [niet-beheerdersrollen](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)toewijzen aan gebruikers met Azure Active Directory voor meer informatie.

## <a name="related-topic"></a>Gerelateerd onderwerp

- [Portaltoegang beheren met RBAC](rbac.md)
