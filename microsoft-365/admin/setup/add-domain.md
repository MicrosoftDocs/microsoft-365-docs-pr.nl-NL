---
title: Een domein toevoegen aan Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Voeg uw domein toe aan Office 365 in het Microsoft 365-beheercentrum door een DNS-record toe te voegen aan uw DNS-host. De setup wizard begeleidt u door het proces.
ms.openlocfilehash: bab4da6e4a8191d91ccdd38dd54f62f4d790c3b8
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140773"
---
# <a name="add-a-domain-to-office-365"></a>Een domein toevoegen aan Office 365

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum verandert. Als uw ervaring niet overeenkomt met de hier gepresenteerde details, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

 **[Raadpleeg de veelgestelde vragen over domeinen](domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
 *Als u domeinen wilt toevoegen, wijzigen of **verwijderen, moet** u een **globale beheerder** van een [bedrijfs- of ondernemingsplan zijn.](https://products.office.com/business/office) Deze wijzigingen zijn van invloed op de hele tenant, *aangepaste beheerders* of *gewone gebruikers* kunnen deze wijzigingen niet aanbrengen.*  

 Volg deze stappen om een domein toe te voegen, in te stellen of door te gaan met het instellen van een domein. 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end
::: moniker range="o365-germany"

1. Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end
    
2. Ga naar de pagina > **Setup-domeinen.** **Setup** 

3. Selecteer **Domein toevoegen**.
    
4. Voer de naam in van het domein dat u wilt toevoegen en selecteer **Volgende**.
    
5. Kies hoe u wilt controleren of u eigenaar bent van het domein.
    
    1. Als uw domein is geregistreerd&amp;bij GoDaddy of 11, selecteert u **Aanmelden** > **volgende** en stelt Microsoft uw records[automatisch in.](../get-help-with-domains/domain-connect.md)
    
    2. U kunt een e-mailbericht met een verificatiecode laten verzenden naar de geregistreerde contactpersoon voor het domein. Als u de e-mail niet herkent of hebt, u de derde optie gebruiken.
    
    3. U kunt een TXT-record gebruiken om uw domein te verifiëren. Selecteer dit en selecteer **Volgende** om instructies te bekijken voor het toevoegen van deze DNS-record aan de website van uw registrar. Dit kan tot 30 minuten duren voordat u de record hebt toegevoegd. 
    
6. Kies hoe u de DNS-wijzigingen wilt aanbrengen die nodig zijn om Office uw domein te laten gebruiken.
    
    1. Kies **De DNS-records voor mij toevoegen** als u wilt dat Office uw DNS automatisch configureert. 
    
  
    2. Kies **Ik voeg de DNS-records zelf toe** als u alleen specifieke Office 365-services aan uw domein wilt koppelen of als u dit nu wilt overslaan en dit later wilt doen. **Kies deze optie als u precies weet wat u doet.**
    
7. Als u ervoor kiest om *zelf DNS-records toe* te voegen, selecteert u **Volgende** en ziet u een pagina met alle records die u moet toevoegen aan de website van uw registrars om uw domein in te stellen. 
    
  
  
    Als uw domeinregistrar niet wordt herkend door de portal, kunt u [deze algemene instructies volgen.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Bekijk onze lijst met [hostspecifieke instructies](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) om uw host te vinden en volg de stappen om alle records toe te voegen die u nodig hebt. 
    
    Als u niet weet wie de DNS-hostingprovider of domeinregistrar voor uw domein is, raadpleegt u [Zoeken naar uw domeinregistrar of DNS-hostingprovider](../get-help-with-domains/find-your-domain-registrar.md).
    
    Als u wilt wachten tot later, schuift u naar de onderkant en selecteert **u Deze stap overslaan**.
    
8. Selecteer **Voltooien** - je bent klaar! 

## <a name="add-or-edit-custom-dns-records"></a>Aangepaste DNS-records toevoegen of bewerken

Volg de onderstaande stappen om een aangepaste record toe te voegen voor een website of service van derden.

1. Meld u aan bij <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>het Microsoft-beheercentrum op .

2. Ga naar de pagina  > **Instellingendomeinen.** **Settings**

3. Selecteer een domein op de pagina **Domeinen**. 
    
4. Selecteer onder **DNS-instellingen** **aangepaste records**; selecteer vervolgens **Nieuwe aangepaste record**.

5. Selecteer het type DNS-record dat u wilt toevoegen en typ de gegevens voor de nieuwe record.
    
6. Kies **Opslaan**.

## <a name="registrars-with-domain-connect"></a>Registrars met Domain Connect

[Met](https://www.domainconnect.org/) registrars met Domain Connect u uw domein toevoegen aan Microsoft 365 in een proces in drie stappen dat minuten duurt. 
  
In de wizard bevestigen we alleen dat u eigenaar bent van het domein en stellen we de records van uw domein automatisch in, zodat e-mail naar Microsoft 365 en andere Microsoft 365-services, zoals Teams, werkt met uw domein.
  
> [!NOTE]
> Start de wizard pas nadat u hebt gecontroleerd of pop-ups zijn toegestaan in uw browser.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Domain Connect-registrars die integreren met Microsoft 365

- [1&amp;1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [Godaddy](https://www.godaddy.com/)
- [Wordpress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTempel (MediaTempel)](https://mediatemple.net/)
- SecureServer of WildWestDomains (GoDaddy resellers met SecureServer DNS-hosting)
    - [MadDog Domeinen](https://www.maddogdomains.com/)
    - [CheapNames CheapNames](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a>Wat gebeurt er met mijn e-mail en website?

Nadat u klaar bent met de installatie, wordt de MX-record voor uw domein bijgewerkt om naar Microsoft 365 te wijzen en alle e-mail voor uw domein wordt naar Microsoft 365 gaan komen. Zorg dat u in Office 365 gebruikers hebt toegevoegd en postvakken hebt geconfigureerd voor iedereen die een e-mailaccount in uw domein heeft.
  
Als uw bedrijf een website heeft, blijft die gewoon werken. De installatiestappen Domain Connect hebben geen invloed op uw website.

## <a name="related-articles"></a>Verwante artikelen

[Veelgestelde vragen over domeinen](domains-faq.md)

[Wat is een domein?](../get-help-with-domains/what-is-a-domain.md)

[Een domeinnaam kopen in Office 365](../get-help-with-domains/buy-a-domain-name.md)

[Uw domein instellen (host-specifieke instructies)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[Hulp krijgen bij domeinen](../get-help-with-domains/get-help-with-domains.md)
