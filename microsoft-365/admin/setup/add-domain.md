---
title: Een domein toevoegen aan Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.openlocfilehash: 86ca8f986624ad37f780961cb58923ea0a1b2308
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857377"
---
# <a name="add-a-domain-to-office-365"></a>Een domein toevoegen aan Office 365

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
    
2. Ga naar de pagina > **Instellingendomeinen.** **Settings** 

3. Selecteer **Domein toevoegen**.
    
4. Voer de naam in van het domein dat u wilt toevoegen en selecteer **Volgende**.
    
5. Kies hoe u wilt controleren of u eigenaar bent van het domein.
    
    1. Als uw domein is geregistreerd&amp;bij GoDaddy of 11, selecteert u **Aanmelden volgende** > **Next** en stelt Office 365 uw records [automatisch in.](../get-help-with-domains/domain-connect.md)
    
    2. U kunt een e-mailbericht met een verificatiecode laten verzenden naar de geregistreerde contactpersoon voor het domein. Als u de e-mail niet herkent of hebt, u de derde optie gebruiken.
    
    3. U kunt een TXT-record gebruiken om uw domein te verifiëren. Selecteer dit en selecteer **Volgende** om instructies te bekijken voor het toevoegen van deze DNS-record aan de website van uw registrar. Dit kan tot 30 minuten duren voordat u de record hebt toegevoegd. 
    
6. Kies hoe u de DNS-wijzigingen wilt aanbrengen die nodig zijn om Office uw domein te laten gebruiken.
    
    1. Kies **De DNS-records voor mij toevoegen** als u wilt dat Office uw DNS automatisch configureert. 
    
  
    2. Kies **Ik voeg de DNS-records zelf toe** als u alleen specifieke Office 365-services aan uw domein wilt koppelen of als u dit nu wilt overslaan en dit later wilt doen. **Kies deze optie als u precies weet wat u doet.**
    
7. Als u ervoor kiest om *zelf DNS-records toe* te voegen, selecteert u **Volgende** en ziet u een pagina met alle records die u moet toevoegen aan de website van uw registrars om uw domein in te stellen. 
    
  
  
    Als uw domeinregistrar niet wordt herkend door de portal, kunt u [deze algemene instructies volgen.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Bekijk onze lijst met [hostspecifieke instructies](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) om uw host te vinden en volg de stappen om alle records toe te voegen die u nodig hebt. 
    
    Als u niet weet wie de DNS-hostingprovider of domeinregistrar voor uw domein is, raadpleegt u [Zoeken naar uw domeinregistrar of DNS-hostingprovider](../get-help-with-domains/find-your-domain-registrar.md).
    
    Als u wilt wachten tot later, schuift u naar de onderkant en selecteert **u Deze stap overslaan**.
    
8. Selecteer **Voltooien** - je bent klaar! 

## <a name="related-articles"></a>Verwante artikelen

[Veelgestelde vragen over domeinen](domains-faq.md)

[Wat is een domein?](../get-help-with-domains/what-is-a-domain.md)

[Een domeinnaam kopen in Office 365](../get-help-with-domains/buy-a-domain-name.md)

[Uw domein instellen (host-specifieke instructies)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[Hulp krijgen bij Office 365-domeinen](../get-help-with-domains/get-help-with-domains.yml)
