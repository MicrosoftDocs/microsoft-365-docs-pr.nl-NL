---
title: Basic Mobility en Security uitschakelen
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Verwijder groepen of beleidsregels om Basismobiliteit en beveiliging uit te schakelen.
ms.openlocfilehash: 7ec4ec0d47668c21824d8e01e3845d637b9b0922
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228133"
---
# <a name="turn-off-basic-mobility-and-security"></a>Basic Mobility en Security uitschakelen

Als u basismobiliteit en beveiliging effectief wilt uitschakelen, verwijdert u groepen personen die zijn gedefinieerd door beveiligingsgroepen uit het beleid voor apparaatbeheer of verwijdert u het beleid zelf.

- Verwijder groepen gebruikers door gebruikersbeveiligingsgroepen te verwijderen uit het apparaatbeleid dat u hebt gemaakt.

- Schakel Basismobiliteit en beveiliging voor iedereen uit door alle beleidsregels voor basismobiliteits- en beveiligingsapparaat te verwijderen.

Met deze opties worden basishandhaving voor mobiliteit en beveiliging voor apparaten in uw organisatie verwijderd. Het is helaas niet mogelijk om basismobiliteit en beveiliging te 'onteigenen' nadat u deze hebt ingesteld.

> [!IMPORTANT]
> Let op de gevolgen voor de apparaten van gebruikers wanneer u gebruikersbeveiligingsgroepen verwijdert uit beleidsregels of het beleid zelf verwijdert. E-mailprofielen en e-mailberichten met cache kunnen bijvoorbeeld worden verwijderd, afhankelijk van het apparaat. Zie Wat gebeurt er als u een beleid verwijdert of een gebruiker uit het  [beleid verwijdert voor meer informatie?](../../admin/basic-mobility-security/create-device-security-policies.md)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Gebruikersbeveiligingsgroepen verwijderen uit basisbeleid voor mobiliteits- en beveiligingsapparaat

1. In uw browsertype:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selecteer een apparaatbeleid en selecteer **Beleid bewerken.**

3. Selecteer op  **de pagina** Implementatie de   optie **Verwijderen.**

4. Selecteer  **onder Groepen** een beveiligingsgroep.

5. Selecteer  **Verwijderen** en selecteer **Opslaan.**

## <a name="remove-basic-mobility-and-security-device-policies"></a>Beleidsregels voor basismobiliteits- en beveiligingsapparaat verwijderen

1. In uw browsertype:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selecteer een apparaatbeleid en selecteer vervolgens  **Beleid verwijderen.**

3. Selecteer ja in het dialoogvenster **Waarschuwing.**

> [!NOTE]
> Zie het blogbericht Access Control verwijderen uit Mobile Device Management voor Office 365 voor meer stappen om de blokkering van apparaten te [deblokkeren als](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)uw organisatieapparaten nog steeds in een geblokkeerde staat staan.
