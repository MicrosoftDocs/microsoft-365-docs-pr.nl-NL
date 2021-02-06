---
title: Microsoft 365 Business Basic instellen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- MET150
- MOE150
- BEA160
description: Meer informatie over het instellen van uw abonnement op Microsoft 365 Business Basic.
ms.openlocfilehash: 43ae19b24058429c9276bd44dd4c3960c792ca0d
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126183"
---
# <a name="set-up-microsoft-365-business-basic"></a>Microsoft 365 Business Basic instellen

 Bekijk een korte video over het instellen van Microsoft 365 Business Basic.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vk3W]

Als u deze video nuttig vond, raadpleegt u dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="add-your-domain-to-personalize-sign-in"></a>Uw domein toevoegen om uw aanmelding te personaliseren

Wanneer u Microsoft 365 Business Basic aanschaft, hebt u de mogelijkheid om een domein te gebruiken dat u bezit of een domein te kopen tijdens de registratie.

- Als u tijdens de registratie een nieuw domein hebt gekocht, is uw domein helemaal ingesteld en kunt u doorgaan met [Gebruikers toevoegen en licenties toewijzen](#add-users-and-assign-licenses).

 ::: moniker range="o365-worldwide"

1. Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Ga naar [dit beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=848041) als u Office 365 Germany gebruikt.

::: moniker-end

::: moniker range="o365-21vianet"

1. Als u Office 365 beheerd door 21Vianet gebruikt, gaat u naar [dit beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=850627).

::: moniker-end 

2. Kies **Naar setup** om de wizard te starten.
    
3. Voer in de stap **Domein toevoegen** de domeinnaam in die u wilt gebruiken (zoals contoso.com).

    > [!IMPORTANT]
    > Als u tijdens de registratie een domein hebt gekocht, ziet u de stap **Een domein toevoegen** hier niet. Ga in plaats daarvan naar [Gebruikers toevoegen](#add-users-and-assign-licenses).

    
4. Volg de stappen in de wizard om [DNS-records te maken bij een DNS-hostingprovider voor Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) waarmee wordt geverifieerd of u eigenaar bent van het domein. Als u weet wat uw domeinhost is, raadpleegt u ook de [hostspecifieke instructies](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Als uw hostingprovider GoDaddy of een andere host is die is ingeschakeld met [domeinverbinding](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), is het proces eenvoudig en wordt u automatisch gevraagd om u aan te melden en u namens Microsoft te laten verifiëren.

    ![Selecteer Autoriseren op de pagina GoDaddy Toegang bevestigen.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>Gebruikers toevoegen en licenties toewijzen

U kunt gebruikers toevoegen in de wizard, maar u kunt ook [gebruikers later toevoegen](../add-users/add-users.md) in het beheercentrum. Als u een lokale domeincontroller hebt, kunt u ook gebruikers toevoegen met [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

## <a name="add-users-in-the-wizard"></a>Gebruikers toevoegen in de wizard

Alle gebruikers die u toevoegt in de wizard krijgen automatisch een Microsoft 365 Business Basic-licentie toegewezen.

1. Als uw Microsoft 365 Business Basic-abonnement bestaande gebruikers heeft (bijvoorbeeld als u Azure AD Connect hebt gebruikt), hebt u een optie om nu licenties aan hen toe te wijzen. Wijs nu licenties aan hen toe.

2. Nadat u de gebruikers hebt toegevoegd, krijgt u ook een optie voor het delen van referenties met de nieuwe gebruikers die u hebt toegevoegd. U kunt deze afdrukken, hun een e-mail sturen of deze downloaden.

## <a name="connect-your-domain"></a>Uw domein verbinden

> [!NOTE]
> Als u ervoor hebt gekozen om het domein. onmicrosoft te gebruiken of Azure AD Connect hebt gebruikt voor het instellen van gebruikers, wordt deze stap niet weergegeven.
  
Als u services wilt instellen, moet u enkele records bij uw DNS-host of domeinregistrar bijwerken.
  
1. Meestal wordt uw registrar automatisch gedetecteerd met de wizard Setup, en wordt een koppeling weergegeven naar stapsgewijze instructies voor het bijwerken van uw NS-records op de website van de registrar. Zo niet, gaat u naar[Naamservers wijzigen voor het instellen van Office 365 bij een domeinregistrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar). 

    - Als u bestaande DNS-records hebt, bijvoorbeeld een bestaande website, maar uw DNS-host is ingeschakeld voor [domeinverbinding](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), kiest u **Records toevoegen voor mij**. Accepteer alle standaardinstellingen op de pagina **Uw online services kiezen**, kies **Volgende** en kies **Autoriseren** op de pagina van uw DNS-host.
    - Als u bestaande DNS-records hebt met andere DNS-hosts (niet ingeschakeld voor domeinverbinding), kunt u uw eigen DNS-records beheren om ervoor te zorgen dat de bestaande services verbonden blijven. Zie [basisprincipes van domeinen](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) voor meer informatie.

2. Volg de stappen in de wizard en e-mail en andere services worden voor u ingesteld.

    Wanneer het aanmeldingsproces is voltooid, wordt u doorgestuurd naar het beheercentrum, waar u gebruikers kunt toevoegen en licenties kunt toewijzen. Nadat u de eerste installatie hebt voltooid, kunt u de pagina **Instellingen** in het beheercentrum gebruiken om door te gaan met het instellen en configureren van de services die bij uw abonnementen worden geleverd.

    Voor meer informatie over de installatiewizard en de **Installatie** pagina in het beheercentrum, raadpleegt u [Verschil tussen de installatiewizard en de installatiepagina](o365-setup-wizard-and-setup-page.md).