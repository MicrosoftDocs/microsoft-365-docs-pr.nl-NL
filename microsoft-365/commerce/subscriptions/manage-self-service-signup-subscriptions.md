---
title: Selfservice registratie abonnementen beheren
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
description: Meer informatie over het beheren van gratis selfservice registratie abonnementen voor uw organisatie.
ms.openlocfilehash: fb70d0c40d4358abc227c8f6ff4a0e0dce1a7265
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48647829"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>Selfservice registratie abonnementen beheren

## <a name="what-are-self-service-sign-up-subscriptions"></a>Wat zijn Self-serviceregistratie abonnementen?

U kunt een beperkt aantal gratis selfservice registratie abonnementen instellen waarmee gebruikers in uw organisatie zich kunnen registreren. Een gebruiker kan zich alleen aanmelden voor een self-service-aanmeldings abonnement. Deze abonnementen worden weergegeven op de pagina **uw producten** , zijn gemarkeerd als **gratis**en hebben de tekst ' Dit is een gratis abonnement dat wordt geactiveerd door gebruikers in uw bedrijf. ' U kunt Self-Serviceabonnementen voor eenmalige aanmelding beheren door gebruikers te blokkeren met een registratie, en door gratis abonnementen te verwijderen waarop gebruikers zich hebben geregistreerd. Zie [selfservice registratie gebruiken in uw organisatie](../../admin/misc/self-service-sign-up.md)voor meer informatie over selfservice registratie en de beschikbare abonnementen.

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>Wat is het verschil tussen de abonnementen voor selfservice aankopen?

Selfservice registratie abonnementen zijn gratis en zijn beschikbaar voor een grotere lijst met producten dan selfservice Purchase-abonnementen. Wanneer een gebruiker zich registreert voor een self-service Purchase-abonnement, zijn ze verantwoordelijk voor de betaling ervan. Ook selfservice Purchase-abonnementen zijn alleen beschikbaar voor Power platform-producten (Power BI, Power apps en Power Automatiseer). Voor meer informatie raadpleegt u [Veelgestelde vragen over self-service aankopen](self-service-purchase-faq.md).

## <a name="block-users-from-signing-up"></a>Voorkomen dat gebruikers zich aanmelden

Met de cmdlet [**set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) met de parameter **AllowAdHocSubscriptions** kunt u aangeven of gebruikers zich kunnen registreren voor Self-serviceregistratie abonnementen. Voor meer informatie raadpleegt [u hoe kan ik selfservice-instellingen beheren?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>Een self-serviceregistratie abonnement verwijderen

> [!IMPORTANT]
> Wanneer u een abonnement voor selfservice registratie verwijdert, blok keert alle gebruikers de toegang tot de gegevens en e-mail en verwijder alle gegevens en e-mail.

1. Ga in het Beheercentrum naar de pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten</a> factureren.
2. Zoek het self-service-aanmeldings abonnement dat u wilt verwijderen. Selecteer in de sectie **instellingen & acties** de optie **abonnement verwijderen**.
3. In het deelvenster **abonnement verwijderen** schakelt u het selectievakje in en selecteert u vervolgens **abonnement verwijderen**.

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>Ik heb een self-serviceregistratie abonnement dat de verwijdering van de map blokkeert

De selfservice registratie producten waarmee afzonderlijke gebruikers zich kunnen registreren voor het ook maken van een gastgebruiker voor verificatie in de Azure AD-Directory. Om verlies van gegevens te voorkomen, blok keert deze selfservice producten Directory verwijdering totdat ze volledig uit de adreslijst worden verwijderd. Ze kunnen alleen worden verwijderd door de Azure AD-beheerder. Zie [een map verwijderen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto)voor meer informatie.