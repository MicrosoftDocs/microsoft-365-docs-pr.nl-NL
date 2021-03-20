---
title: Een domein toevoegen aan Microsoft 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Voeg uw domein toe aan Microsoft 365 in het Microsoft 365-beheercentrum door een DNS-record toe te voegen aan uw DNS-host. Met de installatiewizard loopt u door het proces.
ms.openlocfilehash: 30bce7dd207532c441fdfaf572add44baec16d8d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914268"
---
# <a name="add-a-domain-to-microsoft-365"></a>Een domein toevoegen aan Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

 **[Raadpleeg de veelgestelde vragen over domeinen](domains-faq.yml)** als u niet kunt vinden wat u zoekt. 
  
 *Als u domeinen wilt toevoegen, wijzigen of verwijderen, **moet** u een **globale beheerder** van een bedrijfs- of [ondernemingsplan zijn.](https://products.office.com/business/office) Deze wijzigingen zijn van invloed op de hele tenant, *aangepaste beheerders* of *gewone* gebruikers kunnen deze wijzigingen niet aanbrengen.*  

 Volg deze stappen om een domein toe te voegen, in te stellen of te blijven instellen. 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end
::: moniker range="o365-germany"

1. Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end
    
2. Ga naar de **pagina**  >  **Instellingendomeinen.** 

3. Selecteer **Domein toevoegen.**
    
4. Voer de naam in van het domein dat u wilt toevoegen en selecteer **Volgende.**
    
5. Kies hoe u wilt controleren of u de eigenaar bent van het domein.
    
    1. Als uw domeinregistrar [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365)gebruikt, worden uw [records](../get-help-with-domains/domain-connect.md) automatisch ingesteld door u aan te melden bij uw registrar en de verbinding met Microsoft 365 te bevestigen. U wordt teruggegeven aan het beheercentrum en Microsoft controleert vervolgens automatisch uw domein.
    2. U kunt een TXT-record gebruiken om uw domein te verifiëren. Selecteer dit en selecteer **Volgende om** instructies te zien voor het toevoegen van deze DNS-record aan de website van uw registrar. Dit kan tot 30 minuten duren voordat u de record hebt toegevoegd. 
    3. U kunt een tekstbestand toevoegen aan de website van uw domein. Selecteer en download het TXT-bestand in de installatiewizard en upload het bestand vervolgens naar de map op het hoogste niveau van uw website. Het pad naar het bestand moet er ongeveer hetzelfde uitzien als: `http://mydomain.com/ms39978200.txt` . We bevestigen dat u de eigenaar bent van het domein door het bestand op uw website te zoeken.
    
6. Kies hoe u de DNS-wijzigingen wilt aanbrengen die microsoft nodig heeft om uw domein te gebruiken.
    
    1. Kies **Add the DNS records for me** if your registrar supports Domain [Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft will set up your [records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.
    2. Kies **Ik voeg de DNS-records** zelf toe als u alleen specifieke Microsoft 365-services wilt toevoegen aan uw domein of als u dit voor nu wilt overslaan en dit later wilt doen. **Kies deze optie als u precies weet wat u doet.**

7. Als u zelf *DNS-records*  wilt toevoegen, selecteert u **Volgende** en ziet u een pagina met alle records die u moet toevoegen aan de website van uw registrars om uw domein in te stellen. 

    Als uw domeinregistrar niet wordt herkend door de portal, kunt u [deze algemene instructies volgen.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Bekijk onze lijst met [hostspecifieke instructies](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) om uw host te vinden en volg de stappen om alle records toe te voegen die u nodig hebt. 
    
    Als u niet weet wie de DNS-hostingprovider of domeinregistrar voor uw domein is, raadpleegt u [Zoeken naar uw domeinregistrar of DNS-hostingprovider](../get-help-with-domains/find-your-domain-registrar.md).
    
    Als u later wilt wachten, deselecteert u alle services en klikt u  op Doorgaan **of** kiest u in de vorige domeinverbindingsstap Meer opties en selecteert u Dit voor **nu overslaan.**
    
8. Selecteer **Voltooien-** u bent klaar!

## <a name="add-or-edit-custom-dns-records"></a>Aangepaste DNS-records toevoegen of bewerken

Volg de onderstaande stappen om een aangepaste record toe te voegen voor een website of service van derden.

1. Meld u aan bij het Microsoft-beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Ga naar de **pagina**   >  **Instellingendomeinen.**

3. Selecteer een domein op de pagina **Domeinen**. 
    
4. Selecteer **onder DNS-instellingen** aangepaste **records**; selecteer vervolgens **Nieuwe aangepaste record.**

5. Selecteer het type DNS-record dat u wilt toevoegen en typ de gegevens voor de nieuwe record.
    
6. Kies **Opslaan**.

## <a name="registrars-with-domain-connect"></a>Registrars met Domain Connect

[Met domain](https://www.domainconnect.org/) connect-registrars kunt u uw domein toevoegen aan Microsoft 365 in een proces in drie stappen dat minuten duurt. 
  
In de wizard bevestigen we dat u de eigenaar bent van het domein en vervolgens automatisch de records van uw domein, zodat e-mail naar Microsoft 365 en andere Microsoft 365-services, zoals Teams, met uw domein werkt.
  
> [!NOTE]
> Start de wizard pas nadat u hebt gecontroleerd of pop-ups zijn toegestaan in uw browser.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Domain Connect-registrars die integreren met Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [EuroDNS](https://www.eurodns.com/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress.com](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer of WildWestDomains (GoDaddy-resellers met SecureServer DNS-hosting)
    - Voorbeelden:
        - [DomainsPricedRight](https://www.domainspricedright.com/products/domain-registration)
        - [DomainRightNow](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a>Wat gebeurt er met mijn e-mail en website?

Nadat u klaar bent met de installatie, wordt de MX-record voor uw domein bijgewerkt om te wijzen naar Microsoft 365 en wordt alle e-mail voor uw domein naar Microsoft 365 verzonden. Zorg ervoor dat u gebruikers hebt toegevoegd en postvakken hebt ingesteld in Microsoft 365 voor iedereen die e-mail op uw domein ontvangt.
  
Als uw bedrijf een website heeft, blijft die gewoon werken. De installatiestappen voor Domain Connect hebben geen invloed op uw website.

## <a name="related-articles"></a>Verwante artikelen

[Veelgestelde vragen over domeinen](domains-faq.yml)

[Wat is een domein?](../get-help-with-domains/what-is-a-domain.md)

[Een domeinnaam kopen in Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)

[Uw domein instellen (host-specifieke instructies)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)