---
title: Kenmerken voor het beleid voor informatiebelemmering
description: Dit artikel is een verwijzing naar de Azure Active Directory kenmerken van gebruikersaccounts die u kunt gebruiken om segmenten voor informatiebarrière te definiëren.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee410bf455e770087da7999ad2019c17419a8e00
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162060"
---
# <a name="attributes-for-information-barrier-policies"></a>Kenmerken voor het beleid voor informatiebelemmering

Bepaalde kenmerken in Azure Active Directory kunnen worden gebruikt om gebruikers te segmenteren. Wanneer segmenten zijn gedefinieerd, kunnen deze segmenten worden gebruikt als filters voor beleidsregels voor informatiebarrière. U kunt bijvoorbeeld  Afdeling gebruiken om segmenten van gebruikers te definiëren per afdeling binnen uw organisatie (ervan uitgaande dat er geen enkele werknemer tegelijk werkt voor twee afdelingen).

In dit artikel wordt beschreven hoe u kenmerken kunt gebruiken met informatiebarrières en bevat het een lijst met kenmerken die kunnen worden gebruikt. Zie de volgende bronnen voor meer informatie over informatiebarrières:

- [Informatiebelemmeringen](information-barriers.md)
- [Beleid definiëren voor informatiebarrières in Microsoft Teams](information-barriers-policies.md)
- [Beleid voor informatiebarrière bewerken (of verwijderen)](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>Kenmerken gebruiken in beleidsregels voor informatiebarrière

De kenmerken in dit artikel kunnen worden gebruikt om segmenten van gebruikers te definiëren of te bewerken. Uw gedefinieerde segmenten dienen als parameters *(usergroupfilter-waarden* genoemd) in [beleidsregels voor informatiebarrière.](information-barriers-policies.md)

1. Bepaal welk kenmerk u wilt gebruiken om segmenten te definiëren. (Zie de [sectie Verwijzing](#reference) in dit artikel.)

2. Zorg ervoor dat de gebruikersaccounts waarden hebben ingevuld voor de kenmerken die u hebt geselecteerd in stap 1. Bekijk gebruikersaccountgegevens en bewerk zo nodig gebruikersaccounts om kenmerkwaarden op te nemen. 

    - Zie Eigenschappen van gebruikersaccounts configureren met powershell als u meerdere Office 365 accounts wilt bewerken (of PowerShell wilt gebruiken om één account [te bewerken).](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)

    - Zie Profielgegevens van een gebruiker toevoegen of [bijwerken](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)met behulp van Azure Active Directory.

3. [Segmenten definiëren met PowerShell,](information-barriers-policies.md#define-segments-using-powershell)vergelijkbaar met de volgende voorbeelden:

    |**Voorbeeld**|**Cmdlet**|
    |:----------|:---------|
    | Een segment met de naam Segment1 definiëren met het kenmerk Afdeling | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | Een segment met de naam SegmentA definiëren met het kenmerk MemberOf (stel dat dit kenmerk groepsnamen bevat, zoals 'BlueGroup') | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | Een segment met de naam DayTraders definiëren met ExtensionAttribute1 (stel dat dit kenmerk functietitels bevat, zoals 'DayTrader') | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > Wanneer u segmenten definieert, gebruikt u hetzelfde kenmerk voor al uw segmenten. Als u bijvoorbeeld bepaalde segmenten definieert met *Afdeling,* definieert u alle segmenten met behulp van *Afdeling.* Definieer sommige segmenten niet met *Behulp van Afdeling* en andere segmenten met *MemberOf.* Zorg ervoor dat de segmenten elkaar niet overlappen. elke gebruiker moet aan precies één segment worden toegewezen.

## <a name="reference"></a>Referentiematerialen

De volgende tabel bevat de kenmerken die u kunt gebruiken met informatiebarrières.

|**Azure Active Directory eigenschapsnaam <br/> (LDAP-weergavenaam)**|**Exchange eigenschapsnaam**|
|:---------------------------------------------------------------|:-------------------------|
| Co | Co |
| Company | Company |
| Department | Department |
| ExtensionAttribute1 | CustomAttribute1 |
| ExtensionAttribute2 | CustomAttribute2 |
| ExtensionAttribute3 | CustomAttribute3 |
| ExtensionAttribute4 | CustomAttribute4 |
| ExtensionAttribute5 | CustomAttribute5 |
| ExtensionAttribute6 | CustomAttribute6 |
| ExtensionAttribute7 | CustomAttribute7 |
| ExtensionAttribute8 | CustomAttribute8 |
| ExtensionAttribute9 | CustomAttribute9 |
| ExtensionAttribute10 | CustomAttribute10 |
| ExtensionAttribute11 | CustomAttribute11 |
| ExtensionAttribute12 | CustomAttribute12 |
| ExtensionAttribute13 | CustomAttribute13 |
| ExtensionAttribute14 | CustomAttribute14 |
| ExtensionAttribute15 | CustomAttribute15 |
| MSExchExtensionCustomAttribute1 | ExtensionCustomAttribute1 |
| MSExchExtensionCustomAttribute2 | ExtensionCustomAttribute2 |
| MSExchExtensionCustomAttribute3 | ExtensionCustomAttribute3 |
| MSExchExtensionCustomAttribute4 | ExtensionCustomAttribute4 |
| MSExchExtensionCustomAttribute5 | ExtensionCustomAttribute5 |
| MailNickname | Alias |
| PhysicalDeliveryOfficeName | Office |
| Postcode | Postcode |
| ProxyAddresses | EmailAddresses |
| StreetAddress | StreetAddress |
| TargetAddress | ExternalEmailAddress |
| UsageLocation | UsageLocation |
| UserPrincipalName | UserPrincipalName |
| E-mail | WindowsEmailAddress |
| Beschrijving | Beschrijving |
| LidVan | MemberOfGroup |

## <a name="resources"></a>Resources

- [Beleid definiëren voor informatiebarrières in Microsoft Teams](information-barriers-policies.md)
- [Problemen met informatiebelemmeringen oplossen](information-barriers-troubleshooting.md)
- [Informatiebelemmeringen](information-barriers.md)