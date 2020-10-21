---
title: Uw e-mailadres wijzigen om uw aangepaste domein te gebruiken
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
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: 'Wijzig uw eerste e-mailadres in een vriendelijk e-mailadres, zoals tom@fourthcoffee.com. Hiervoor moet u een domeinnaam kopen en toevoegen aan Microsoft 365. '
ms.openlocfilehash: 7b5ab62ea99af52c61ca4ba6a7e9ea37604ddf19
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645537"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Uw e-mailadres wijzigen om uw aangepaste domein te gebruiken

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
::: moniker range="o365-worldwide"

Uw eerste e-mailadres in Microsoft 365 omvat. onmicrosoft.com, bijvoorbeeld tom@fourthcoffee.onmicrosoft.com. U kunt dit wijzigen in een handiger adres, zoals flip@fourthcoffee.com. U hebt eerst een eigen domeinnaam nodig, zoals fourthcoffee.com. Het is fijn als u al een domeinnaam hebt. Als dit nog niet het geval is, leert u hoe u [een domeinnaam kunt kopen bij een domeinregistrar](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-germany"

Uw eerste e-mailadres in Office 365 Duitsland omvat. onmicrosoft.de, bijvoorbeeld tom@fourthcoffee.onmicrosoft.de. U kunt dit aanpassen aan een vriendelijkere adres, zoals tom@fourthcoffee.de. U hebt uw eigen domeinnaam nodig, zoals fourthcoffee.de eerst. Het is fijn als u al een domeinnaam hebt. Als dit nog niet het geval is, leert u hoe u [een domeinnaam kunt kopen bij een domeinregistrar](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

Uw eerste e-mailadres in Office 365, beheerd door 21Vianet, bevat partner.onmschina.cn, zoals tom@fourthcoffee.partner.onmschina.cn. U kunt dit aanpassen aan een vriendelijkere adres, zoals tom@fourthcoffee.cn. U hebt uw eigen domeinnaam nodig, zoals fourthcoffee.cn eerst. Het is fijn als u al een domeinnaam hebt. Als dit nog niet het geval is, leert u hoe u [een domeinnaam kunt kopen bij een domeinregistrar](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

Wanneer u het e-mailadres van uw domein wijzigt in Microsoft 365, moet u de MX-record van uw domein tijdens de installatie bijwerken, zodat alle e-mail die naar dit domein wordt verzonden, wordt verzonden naar Microsoft 365. Zorg ervoor dat u gebruikers hebt toegevoegd en postvakken hebt gemaakt in Microsoft 365 voor iedereen die e-mail in uw domein heeft voordat u de MX-record wijzigt. Wilt u de e-mail niet voor iedereen in uw domein verplaatsen naar Microsoft 365? U kunt stappen uitvoeren om [Microsoft 365 met slechts een paar e-mailadressen te testen](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide).
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Uw e-mailadres wijzigen om uw aangepaste domein te gebruiken met het Microsoft 365-Beheercentrum

U moet een hoofd beheerdersaccount hebben om deze stappen uit te voeren. 

::: moniker range="o365-worldwide"

1. Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>. 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>. 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. Ga naar het Beheercentrum <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>. 

::: moniker-end 

2. Ga naar de **Setup**  >  pagina**domeinen** instellen. 

3. Op de pagina **Domeinen** selecteert u **Domein toevoegen**.
    
4. Volg de stappen om te bevestigen dat u eigenaar van het domein bent en om uw e-mailadres te wijzigen.
    
U wordt begeleid om alles juist in te stellen met uw domein in Microsoft 365.

> [!NOTE]
> Als u geen Exchange-licentie gebruikt, kunt u het domein niet gebruiken voor het verzenden of ontvangen van e-mailberichten van de Microsoft 365-Tenant.
  
## <a name="related-articles"></a>Verwante artikelen

[Een aangepast domein kopen met Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)
 
