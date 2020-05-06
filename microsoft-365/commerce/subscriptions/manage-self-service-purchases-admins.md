---
title: Selfservice-aankopen beheren (beheerders)
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
- commerce
search.appverid:
- MET150
description: Beheerders kunnen leren hoe ze selfservice-aankopen kunnen beheren die door gebruikers in hun organisatie worden gedaan.
ms.openlocfilehash: 7074a829bed3e65a160a9a33afb4f2b130f6c8d1
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046178"
---
# <a name="manage-self-service-purchases-admin"></a>Selfservice-aankopen beheren (Beheerders)

Als beheerder u selfservice-aankopen zien die door mensen in uw organisatie zijn gedaan. U het product, de naam van de koper, de gekochte abonnementen, de vervaldatum, de aankoopprijs en toegewezen gebruikers voor elke selfserviceaankoop bekijken. Indien nodig voor uw organisatie, u self-service inkoop per product via PowerShell uitschakelen. U hebt hetzelfde beleid voor gegevensbeheer en -toegang ten opzichte van producten die zijn gekocht via selfservice-aankoop of centraal.

U ook bepalen of gebruikers in uw organisatie zelfservice-aankopen kunnen doen. Zie [AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module voor](allowselfservicepurchase-powershell.md)meer informatie.

## <a name="view-self-service-subscriptions"></a>Selfservice-abonnementen weergeven

1. Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten.</a>

2. Kies naast **Resultaten verfijnen**in de vervolgkeuzelijst **Accounttype** de optie **Selfservice**.

3. Als u meer details over een abonnement wilt bekijken, kiest u er een in de lijst.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Zien wie licenties heeft voor een abonnement op selfservice-aankoop

1. Ga in het beheercentrum naar de pagina **Factureringslicenties.** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a>

2. Kies het filterpictogram en kies **Self-service**.

3. Selecteer een product om licenties te zien die aan mensen zijn toegewezen.

    > [!NOTE]
    > Als er meerdere aankopen voor een product zijn, wordt dat product slechts één keer vermeld en wordt in de kolom **Beschikbare hoeveelheid** het totaal van alle abonnementen weergegeven die voor dat product zijn gekocht.

4. De lijst **Gebruikers** wordt gegroepeerd op de namen van mensen die selfservice-aankopen hebben gedaan.

5. Als u een lijst met gebruikers met licenties voor deze abonnementen wilt exporteren, kiest u de abonnementen die u wilt exporteren en kiest u **Gebruikers exporteren**.

## <a name="disable-or-enable-self-service-purchases"></a>Selfservice-aankopen uitschakelen of inschakelen

U selfservice-aankopen voor gebruikers in uw organisatie uitschakelen of inschakelen. De **MSCommerce** PowerShell-module bevat een **PolicyID-parameterwaarde** voor **AllowSelfServicePurchase** waarmee u bepalen of gebruikers in uw organisatie selfservice-aankopen kunnen doen en voor welke producten.

U de **MSCommerce** PowerShell-module gebruiken om:

- De standaardstatus van de parameter **AllowSelfServicePurchase** &mdash; weergeven, ongeacht of deze is ingeschakeld of uitgeschakeld per product
- Bekijk een lijst met toepasselijke producten en of selfservice-aankoop is ingeschakeld of uitgeschakeld
- De huidige instelling voor een specifiek product weergeven of wijzigen om het in te schakelen of uit te schakelen

Zie [AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module voor](allowselfservicepurchase-powershell.md)meer informatie.

## <a name="centralize-licenses-under-a-single-subscription"></a>Licenties centraliseren onder één abonnement

U bestaande licenties toewijzen of aanvullende abonnementen aanschaffen via bestaande overeenkomsten voor gebruikers die zijn toegewezen aan selfservice-aankopen. Nadat u deze centraal aangeschafte licenties hebt toegewezen, u kopers vragen hun bestaande abonnementen op te zeggen.

1. Meld u aan bij het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">beheercentrum</a> met uw globale beheerder- of factureringsbeheeraccount.

2. Ga naar de pagina<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Services voor factureringsaankopen.</a> **Billing** > 

3. Zoek en kies het product dat u wilt kopen en kies **kopen**.

4. Voer de resterende stappen uit om uw aankoop te voltooien.

5. Volg de stappen in [Weergave met licenties voor een selfservicegekocht abonnement](#view-who-has-licenses-for-a-self-service-purchase-subscription) om een lijst met gebruikers te exporteren om te verwijzen in stap 6.

6. Licenties toewijzen aan iedereen die een licentie heeft in het andere abonnement. Zie [Licenties toewijzen aan gebruikers voor](../../admin/manage/assign-licenses-to-users.md)volledige stappen.

7. Neem contact op met de persoon die het abonnement voor selfservice-aankopen heeft gekocht en vraag hem of zij het abonnement op te zeggen.

## <a name="need-help-contact-us"></a>Hulp nodig? Neem contact met ons op.

Zie Veelgestelde vragen over [selfservice-aankopen](self-service-purchase-faq.md)voor veelgestelde vragen over selfservice-aankopen.

Als u vragen hebt of hulp nodig hebt bij selfservice-aankopen, neemt u [contact op met de ondersteuning.](../../admin/contact-support-for-business-products.md)
