---
title: Microsoft 365 Business Basic instellen
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
- BEA160
description: Meer informatie over het instellen van uw abonnement op Microsoft 365 Business Basic.
ms.openlocfilehash: f7569645753f292760f32ba932aac7b83c602b72
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393821"
---
# <a name="set-up-microsoft-365-business-basic"></a>Microsoft 365 Business Basic instellen

## <a name="watch-set-up-microsoft-365-business-basic"></a>Bekijk: Microsoft 365 Business Basic instellen

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vk3W]

Als u deze video nuttig vond, raadpleegt u dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](../../business-video/index.yml).

## <a name="add-your-domain-to-personalize-sign-in"></a>Uw domein toevoegen om uw aanmelding te personaliseren

Wanneer u Microsoft 365 Business Basic aanschaft, hebt u de mogelijkheid om een domein te gebruiken dat u bezit of een domein te kopen tijdens de registratie.

- Als u tijdens de registratie een nieuw domein hebt gekocht, is uw domein helemaal ingesteld en kunt u doorgaan met [Gebruikers toevoegen en licenties toewijzen](#add-users-and-assign-licenses).

 ::: moniker range="o365-worldwide"

1. Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end 

2. Kies **Naar setup** om de wizard te starten.
    
3. Voer in de stap **Domein toevoegen** de domeinnaam in die u wilt gebruiken (zoals contoso.com).

    > [!IMPORTANT]
    > Als u tijdens de registratie een domein hebt gekocht, ziet u de stap **Een domein toevoegen** hier niet. Go in plaats daarvan naar [Gebruikers toevoegen](#add-users-and-assign-licenses).

    
4. Volg de stappen in de wizard om [DNS-records te maken bij een DNS-hostingprovider voor Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) waarmee wordt geverifieerd of u eigenaar bent van het domein. Als u uw domeinhost kent, raadpleeg dan ook [Een domein toevoegen aan Microsoft 365](/microsoft-365/admin/setup/add-domain).

    Als uw hostingprovider GoDaddy of een andere host is die is ingeschakeld met [domeinverbinding](/office365/admin/get-help-with-domains/domain-connect), is het proces eenvoudig en wordt u automatisch gevraagd om u aan te melden en u namens Microsoft te laten verifiëren.

    ![Selecteer Autoriseren op de pagina GoDaddy Toegang bevestigen.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>Gebruikers toevoegen en licenties toewijzen

U kunt gebruikers toevoegen in de wizard, maar u kunt ook [gebruikers later toevoegen](../add-users/add-users.md) in het beheercentrum. Als u een lokale domeincontroller hebt, kunt u ook gebruikers toevoegen met [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).

## <a name="add-users-in-the-wizard"></a>Gebruikers toevoegen in de wizard

Alle gebruikers die u toevoegt in de wizard krijgen automatisch een Microsoft 365 Business Basic-licentie toegewezen.

1. Als uw Microsoft 365 Business Basic-abonnement bestaande gebruikers heeft (als u bijvoorbeeld Azure AD Connect hebt gebruikt), hebt u de optie om nu licenties aan hen toe te wijzen. Wijs nu licenties aan hen toe.

2. Nadat u de gebruikers hebt toegevoegd, krijgt u ook een optie voor het delen van inloggegevens met de toegevoegde gebruikers. U kunt de inloggegevens afdrukken, per e-mail versturen of downloaden.

## <a name="connect-your-domain"></a>Uw domein verbinden

> [!NOTE]
> Als u ervoor hebt gekozen om het domein. onmicrosoft te gebruiken of Azure AD Connect hebt gebruikt voor het instellen van gebruikers, wordt deze stap niet weergegeven.
  
Als u services wilt instellen, moet u enkele records bij uw DNS-host of domeinregistrar bijwerken.
  
1. Meestal wordt uw registrar automatisch gedetecteerd met de wizard Setup, en wordt een koppeling weergegeven naar stapsgewijze instructies voor het bijwerken van uw NS-records op de website van de registrar. Zo niet, gaat u naar[Naamservers wijzigen voor het instellen van Office 365 bij een domeinregistrar](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md). 

    - Als u bestaande DNS-records hebt, bijvoorbeeld een bestaande website, maar uw DNS-host is ingeschakeld voor [domeinverbinding](/office365/admin/get-help-with-domains/domain-connect), kiest u **Records toevoegen voor mij**. Accepteer alle standaardinstellingen op de pagina **Uw online services kiezen**, kies **Volgende** en kies **Autoriseren** op de pagina van uw DNS-host.
    - Als u bestaande DNS-records hebt met andere DNS-hosts (niet ingeschakeld voor domeinverbinding), kunt u uw eigen DNS-records beheren om ervoor te zorgen dat de bestaande services verbonden blijven. Zie [Basisinformatie over domeinen](/office365/admin/get-help-with-domains/dns-basics) voor meer informatie.

2. Volg de stappen in de wizard en e-mail en andere services worden voor u ingesteld.

    Wanneer het aanmeldingsproces is voltooid, wordt u doorgestuurd naar het beheercentrum, waar u gebruikers kunt toevoegen en licenties kunt toewijzen. Nadat u de eerste installatie hebt voltooid, kunt u de pagina **Instellingen** in het beheercentrum gebruiken om door te gaan met het instellen en configureren van de services die bij uw abonnementen worden geleverd.

    Voor meer informatie over de installatiewizard en de **Installatie** pagina in het beheercentrum, raadpleegt u [Verschil tussen de installatiewizard en de installatiepagina](o365-setup-wizard-and-setup-page.md).