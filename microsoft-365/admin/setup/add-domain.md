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
description: Voeg uw domein toe aan Microsoft 365 in het Microsoft 365-Beheercentrum door een DNS-record toe te voegen aan uw DNS-host. De installatiewizard begeleidt u bij het proces.
ms.openlocfilehash: 3a4cd31a37eb01570f58e9cdb83940640768a273
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644613"
---
# <a name="add-a-domain-to-microsoft-365"></a>Een domein toevoegen aan Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

 **[Raadpleeg de veelgestelde vragen over domeinen](domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
 *Als u domeinen wilt toevoegen, wijzigen of verwijderen, **moet** u een **globale beheerder** van een [zakelijk of Enterprise-abonnement](https://products.office.com/business/office)zijn. Deze wijzigingen zijn van invloed op de hele Tenant, *aangepaste beheerders* of *gewone gebruikers* kunnen deze wijzigingen niet aanbrengen.*  

 Ga als volgt te werk om het instellen van een domein toe te voegen, in te stellen of door te gaan. 

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
    
2. Ga naar de pagina **instellingen**  >  **domeinen** . 

3. Selecteer **domein toevoegen**.
    
4. Voer de naam in van het domein dat u wilt toevoegen en selecteer **volgende**.
    
5. Kies hoe u wilt bevestigen dat u de eigenaar van het domein bent.
    
    1. Als bij uw domeinregistratie [domein verbinding](#domain-connect-registrars-integrating-with-microsoft-365)wordt gebruikt, [worden uw records](../get-help-with-domains/domain-connect.md) in Microsoft automatisch ingesteld op basis van de registratie en wordt de verbinding met Microsoft 365 bevestigd. U gaat terug naar het Beheercentrum en Microsoft zal uw domein vervolgens automatisch laten verifiëren.
    2. U kunt een TXT-record gebruiken om uw domein te verifiëren. Selecteer dit en selecteer **volgende** om instructies te zien voor het toevoegen van deze DNS-record aan de website van uw bewaarder. Dit kan 30 minuten duren voordat u de record hebt toegevoegd. 
    3. U kunt een tekstbestand toevoegen aan de website van uw domein. Selecteer en Download het txt-bestand via de wizard Setup en upload het bestand naar de map op het hoogste niveau van uw website. Het pad naar het bestand moet er ongeveer als volgt `http://mydomain.com/ms39978200.txt` uitzien: U wordt bevestigd dat u de eigenaar bent van het domein door het bestand op uw website te zoeken.
    
6. Kies hoe u de DNS-wijzigingen wilt aanbrengen voor Microsoft zodat uw domein wordt gebruikt.
    
    1. Kies **de DNS-records voor mij toevoegen** als uw registratie [domein verbinding](#domain-connect-registrars-integrating-with-microsoft-365)ondersteunt, en Microsoft [uw records automatisch instelt](../get-help-with-domains/domain-connect.md) door u aan te melden bij uw registratie en om de verbinding met Microsoft 365 te bevestigen.
    2. Kies **Ik voeg de DNS-records zelf toe** als u alleen bepaalde microsoft 365-Services wilt toevoegen aan uw domein of als u dit later wilt overslaan. **Kies deze optie als u precies weet wat u doet.**

7. Als u ervoor kiest om *DNS-records zelf toe te voegen*  , selecteert u **volgende** en ziet u een pagina met alle records die u moet toevoegen aan uw registratie website om uw domein in te stellen. 

    Als uw domeinregistrar niet wordt herkend door de portal, kunt u [deze algemene instructies volgen.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Bekijk onze lijst met [hostspecifieke instructies](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) om uw host te vinden en volg de stappen om alle records toe te voegen die u nodig hebt. 
    
    Als u niet weet wie de DNS-hostingprovider of domeinregistrar voor uw domein is, raadpleegt u [Zoeken naar uw domeinregistrar of DNS-hostingprovider](../get-help-with-domains/find-your-domain-registrar.md).
    
    Als u op een later tijdstip wilt wachten, selecteert u alle services opheffen en klikt u op **Doorgaan**, of in de vorige verbindings stap voor domein kiest u **meer opties** en selecteert u **deze voortaan overslaan**.
    
8. Selecteer **Voltooien** -u bent klaar.

## <a name="add-or-edit-custom-dns-records"></a>Aangepaste DNS-records toevoegen of bewerken

Voer de onderstaande stappen uit om een aangepaste record toe te voegen voor een website of een service van een andere leverancier.

1. Meld u aan bij het Microsoft-Beheercentrum <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Ga naar de pagina **instellingen**   >  **domeinen** .

3. Selecteer een domein op de pagina **Domeinen**. 
    
4. Selecteer **aangepaste records**onder **DNS-instellingen**. Selecteer vervolgens **nieuwe aangepaste record**.

5. Selecteer het type DNS-record dat u wilt toevoegen en typ de gegevens voor de nieuwe record.
    
6. Kies **Opslaan**.

## <a name="registrars-with-domain-connect"></a>Registraties met domein verbinding

Met de [met de domein Connect](https://www.domainconnect.org/) ingeschakelde registraties kunt u uw domein toevoegen aan microsoft 365 in drie stappen die een paar minuten duren. 
  
In de wizard wordt bevestigd dat u de eigenaar van het domein bent en worden de records van uw domein automatisch ingesteld, zodat e-mail wordt bezorgd bij Microsoft 365 en andere Microsoft 365-Services, zoals teams, werken met uw domein.
  
> [!NOTE]
> Start de wizard pas nadat u hebt gecontroleerd of pop-ups zijn toegestaan in uw browser.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Domein Connect-service registraties integreren met Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [EuroDNS](https://www.eurodns.com/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress.com](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer of WildWestDomains (GoDaddy resellers met SecureServer DNS-hosting)
    - Voorbeelden:
        - [DomainsPricedRight](https://www.domainspricedright.com/products/domain-registration)
        - [DomainRightNow](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a>Wat gebeurt er met mijn e-mail en website?

Wanneer u klaar bent met de installatie, wordt de MX-record voor uw domein bijgewerkt zodat deze verwijst naar Microsoft 365 en alle e-mailberichten voor uw domein komen te staan bij Microsoft 365. Zorg ervoor dat u gebruikers hebt toegevoegd en postvakken hebt ingesteld in Microsoft 365 voor iedereen die e-mail op uw domein ontvangt.
  
Als uw bedrijf een website heeft, blijft die gewoon werken. De installatiestappen voor domein verbinding hebben geen invloed op uw website.

## <a name="related-articles"></a>Verwante artikelen

[Veelgestelde vragen over domeinen](domains-faq.md)

[Wat is een domein?](../get-help-with-domains/what-is-a-domain.md)

[Een domeinnaam kopen in Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)

[Uw domein instellen (host-specifieke instructies)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
