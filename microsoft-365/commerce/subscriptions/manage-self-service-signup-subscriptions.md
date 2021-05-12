---
title: Selfservice-abonnementen beheren
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: Meer informatie over het beheren van gratis selfservice-abonnementen voor uw organisatie.
ms.date: 03/17/2021
ms.openlocfilehash: b469515a649399c71ef64ba2567dfa376f21e9a7
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333216"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>Selfservice-abonnementen beheren

## <a name="what-are-self-service-sign-up-subscriptions"></a>Wat zijn selfservice-abonnementen?

Er is een beperkt aantal gratis selfservice-abonnementen beschikbaar voor gebruikers in uw organisatie om zich voor aan te melden. Een gebruiker kan zich alleen registreren voor en een selfservice-abonnement voor zichzelf gebruiken. U beheert selfservice-abonnementen door te blokkeren dat gebruikers zich kunnen registreren en door gratis abonnementen te verwijderen waar gebruikers zich voor hebben aangemeld. Zie Selfservice registreren in uw organisatie voor meer informatie over [selfservice-aanmelding](../../admin/misc/self-service-sign-up.md)en de beschikbare abonnementen.

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>Een lijst met selfservice-abonnementen weergeven

1. Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.
2. Selecteer op **het** tabblad Producten het filterpictogram en selecteer vervolgens **Gratis.** Er wordt een lijst met alle selfservice-abonnementen weergegeven.

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>Hoe verschillen deze abonnementen van abonnementen voor selfserviceaankoop?

Selfservice-abonnementen zijn gratis en zijn beschikbaar voor een grotere lijst met producten dan abonnementen voor selfserviceaankoop. Wanneer een gebruiker zich meldt voor een selfservice-aankoopabonnement, is hij of zij verantwoordelijk voor het betalen ervan. Selfservice-abonnementen zijn alleen beschikbaar voor Power Platform-producten (Power BI, Power Apps en Power Automate), Project en Visio. Zie Veelgestelde vragen over [selfservice-aankopen voor meer informatie.](self-service-purchase-faq.md)

## <a name="block-users-from-signing-up"></a>Gebruikers blokkeren om zich aan te melden

U gebruikt de cmdlet [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) met de parameter **AllowAdHocSubscriptions** om te bepalen of gebruikers zich kunnen registreren voor selfservice-abonnementen. Zie Hoe beheer ik [selfservice-instellingen?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings) voor meer informatie.

## <a name="delete-a-self-service-sign-up-subscription"></a>Een selfservice-abonnement verwijderen

> [!IMPORTANT]
> Wanneer u een selfservice-abonnement verwijdert, blokkeert u dat alle gebruikers toegang hebben tot hun gegevens en e-mail en verwijdert u alle gegevens en e-mail.

1. Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.
2. Selecteer op **het** tabblad Producten het filterpictogram en selecteer vervolgens **Gratis.**
3. Selecteer het selfservice-abonnement dat u wilt verwijderen. 
4. Selecteer op de pagina **Abonnementsgegevens** in de sectie Abonnementen en betalingsinstellingen de optie **Abonnement verwijderen.**
5. Schakel in **het deelvenster** Abonnement verwijderen het selectievakje in en selecteer vervolgens **Abonnement verwijderen.**

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>Ik heb een selfservice-abonnement dat adreslijstverhaling blokkeert

De selfservice-aanmeldingsproducten waar afzonderlijke gebruikers zich voor kunnen registreren, maken ook een gastgebruiker voor verificatie in uw Azure AD-adreslijst. Om gegevensverlies te voorkomen, blokkeren deze selfserviceproducten adreslijstverhalingen totdat ze volledig uit de adreslijst zijn verwijderd. Ze kunnen alleen worden verwijderd door de Azure AD-beheerder. Zie Een adreslijst verwijderen in Azure Active Directory voor [meer informatie.](/azure/active-directory/users-groups-roles/directory-delete-howto)
