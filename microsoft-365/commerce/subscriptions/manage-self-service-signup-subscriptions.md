---
title: Abonnementen voor selfservice-aanmelding beheren
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Meer informatie over het beheren van gratis selfservice-abonnementen voor uw organisatie.
ms.openlocfilehash: 81c67292a394c62d6057022babb88aa8796b9b3d
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403244"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>Abonnementen voor selfservice-aanmelding beheren

## <a name="what-are-self-service-sign-up-subscriptions"></a>Wat zijn selfservice-abonnementen?

Er zijn een beperkt aantal gratis self-service aanmeldingsabonnementen waarvoor gebruikers in uw organisatie zich kunnen aanmelden. Een gebruiker kan zich alleen aanmelden voor en zelf een selfservice-abonnement gebruiken. Deze abonnementen worden weergegeven op de pagina **Uw producten,** zijn gemarkeerd als **Gratis**en hebben een notitie met de tekst: "Dit is een gratis abonnement dat wordt geactiveerd door gebruikers in uw bedrijf." U zelfservice-aanmeldingsabonnementen beheren door gebruikers te blokkeren zich aan te melden en door gratis abonnementen te verwijderen waarvoor gebruikers zich hebben aangemeld. Zie [Zelfserviceaanmelden gebruiken in uw organisatie](../../admin/misc/self-service-sign-up.md)voor meer informatie over het aanmelden voor selfservice en de beschikbare abonnementen.

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>Wat zijn deze abonnementen anders dan self-service aankoopabonnementen?

Self-service aanmeldingsabonnementen zijn gratis en zijn beschikbaar voor een grotere lijst met producten dan selfservice-aankoopabonnementen. Wanneer een gebruiker zich aanmeldt voor een selfservice-aankoopabonnement, is hij verantwoordelijk voor het betalen ervan. Ook zijn abonnementen voor selfservice-aankopen alleen beschikbaar voor Power Platform-producten (Power BI, Power Apps en Power Automate). Zie [Veelgestelde vragen over selfserviceaankopen](self-service-purchase-faq.md)voor meer informatie.

## <a name="block-users-from-signing-up"></a>Gebruikers blokkeren om zich aan te melden

U gebruikt de cmdlet [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) met de parameter **AllowAdHocSubscriptions** om te bepalen of gebruikers zich kunnen aanmelden voor zelfbedieningsabonnementen. Zie [Hoe beheer ik selfservice-instellingen?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>Een selfservice-abonnement verwijderen

> [!IMPORTANT]
> Wanneer u een selfservice-abonnement verwijdert, blokkeert u dat alle gebruikers toegang krijgen tot hun gegevens en e-mail en alle gegevens en e-mail verwijderen.

1. Ga in het beheercentrum naar de pagina **Facturering**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten.</a>
2. Zoek het selfservice-abonnement dat u wilt verwijderen. Selecteer **abonnement verwijderen**in de sectie Instellingen **& acties** .
3. Schakel in het deelvenster **Abonnement verwijderen** het selectievakje in en schakel vervolgens **Abonnement verwijderen**in.

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>Ik heb een selfservice-abonnement dat het verwijderen van directory's blokkeert

De selfservice-aanmeldingsproducten waarvoor individuele gebruikers zich kunnen aanmelden, maken ook een gastgebruiker voor verificatie in uw Azure AD-map. Om gegevensverlies te voorkomen, blokkeren deze selfserviceproducten het verwijderen van directorytotdat ze volledig uit de map zijn verwijderd. Ze kunnen alleen worden verwijderd door de Azure AD-beheerder. Zie [Een map verwijderen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto)voor meer informatie.