---
title: Overgang van een Cryptografieprovider van Microsoft 365 Business abonnement 
description: Ontdek hoe u een Cryptografieprovider van Microsoft 365 Business-abonnement van voorbeeld op GA. kan overgaan 
author: jasongroce
ms.author: jasgro
ms.topic: article 
ms.prod: microsoft-365-business
localization_priority: Normal
audience: microsoft-business 
keywords: Microsoft Business 365, Microsoft 365, SMB, overgang CSP-abonnement
ms.date: 11/01/2017
ms.openlocfilehash: 8109c0b00f06a15c12bbccf89e7f49dc3fa4b34a
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "26982482"
---
# <a name="transition-a-microsoft-365-business-csp-subscription"></a>Overgang van een Cryptografieprovider van Microsoft 365 Business abonnement

Als u een Cryptografieprovider van Microsoft 365 Business Preview-abonnement hebt, volg dan deze handleiding om erachter te komen hoe u uw bestaande voorbeeld-abonnement op Microsoft 365 Business NH (algemene beschikbaarheid) kan overgaan.

**Het overstappen van een abonnement voorbeeld op NH**

1. Log in bij <a href="https://partnercenter.microsoft.com" target="_blank">Partner Center</a>.
2. Van het dashboard, **klanten**, selecteren en zoeken en selecteren de naam van het bedrijf.

    De abonnementen voor het bedrijf worden weergegeven.

    ![Abonnementen in het midden van de Partner van de klant](images/pc_customer_subscriptions_1.png)
    
3. Selecteer in de pagina **abonnementen** van het bedrijf, **abonnement toevoegen**.
4. **Nieuw abonnement** op de pagina Selecteer **Small business** en selecteer vervolgens **Microsoft 365 Business** in de lijst.
5. Het aantal licenties toevoegen en selecteer vervolgens **volgende: Bekijk** het abonnement bekijken en selecteer vervolgens **indienen**.

    ![Bekijk het nieuwe abonnement op Microsoft 365 Business](images/pc_customer_reviewnewsubscription.png)

    De **abonnementen op basis van een licentie** geeft **Microsoft 365 Business Preview** en **Microsoft 365 Business**. U moet het abonnement voorbeeld volgende onderbreking.

6. Selecteer **Microsoft Business 365 voorvertoning**.
7. Selecteer op de pagina **Microsoft 365 Business Preview** **uitgesteld** tot schorsing van het abonnement voorbeeld.

    ![Schorsing van het abonnement op Microsoft 365 Business Preview](images/pc_customer_m365bpreview_suspend.png)

8. Selecteer **verzenden** om te bevestigen.

    Bevestig dat de status van **Microsoft 365 Business Preview** **onderbroken wordt**in de pagina **abonnementen** .

    ![Controleer dat de status van het voorbeeld-abonnement is uitgesteld.](images/pc_customer_m365bpreview_suspend_confirm.png)

9. U kunt desgewenst ook de gebruiksrechtovereenkomst valideren. Ga hiervoor als volgt te werk:
    1. Selecteer **gebruikers en licenties** in de pagina **abonnementen** van het bedrijf.
    2. Selecteer een gebruiker op de pagina **gebruikers en licenties** .
    3. Pagina van de gebruiker de sectie voor het **toewijzen van licenties** en controleer dat het bevat **Microsoft 365 Business**.

        ![Controleer dat de Microsoft 365 Business licentie is toegewezen aan de gebruiker](images/pc_customer_userslicenses_m365b_validate.png)

## <a name="impact-to-customers-and-users-during-and-after-transition"></a>Impact op klanten en gebruikers tijdens en na de overgang

Er is geen impact op klanten en gebruikers tijdens de overgang en overgang van de post.

## <a name="impact-to-customers-who-dont-transition"></a>Impact op klanten die geen overgang

In de volgende tabel bevat een overzicht van de gevolgen voor klanten die geen overgang van een abonnement op Microsoft 365 Business Preview op een Microsoft 365 Business abonnement.

|       | T-0 T + 30     | T + 30 T + 60 | T + 60 T + 120 | Buiten T + 120  |
|-------|-----------------|--------------|---------------|---------------|
| **Status** | In de periode | Verlopen      | Uitgeschakeld      | Deprovisioned |
| **Service-effecten**                                                        |
| **Microsoft 365 Business admin portal** | Geen invloed op de functionaliteit | Geen invloed op de functionaliteit | Kan gebruikers toevoegen/verwijderen, abonnementen kopen.</br> Kan niet toewijzen/intrekken licenties. | Abonnement van de klant en alle gegevens verwijderd. Admin kan andere betaalde abonnementen beheren. |
| **Office-toepassingen**                         | Geen gevolgen voor de eindgebruiker | Geen gevolgen voor de eindgebruiker | Office wordt de modus van verminderde functionaliteit.</br> Gebruikers kunnen bestanden alleen bekijken. | Office wordt de modus van verminderde functionaliteit.</br> Gebruikers kunnen bestanden alleen bekijken. |
| **Cloud services (SharePoint Online, Online Exchange, Skype, Teams en meer)** | Geen gevolgen voor de eindgebruiker | Geen gevolgen voor de eindgebruiker | Eindgebruikers en beheerders hebben geen toegang tot de gegevens in de cloud. | Abonnement van de klant en alle gegevens worden verwijderd. |
| **EM + S onderdelen** | Geen gevolgen voor de admin</br> Geen gevolgen voor de eindgebruiker | Geen gevolgen voor de admin</br> Geen gevolgen voor de eindgebruiker | Mogelijkheid niet meer worden afgedwongen.</br> Zie [mobiel apparaat van invloed is op het abonnement is verlopen](#mobile-device-impacts-upon-subscription-expiration) en [Windows 10 PC effecten bij het abonnement is verlopen](#windows-10-pc-impacts-upon-subscription-expiration) voor meer info. | Mogelijkheid niet meer worden afgedwongen.</br> Zie [mobiel apparaat van invloed is op het abonnement is verlopen](#mobile-device-impacts-upon-subscription-expiration) en [Windows 10 PC effecten bij het abonnement is verlopen](#windows-10-pc-impacts-upon-subscription-expiration) voor meer info. |
| **Windows 10 Business** | Geen gevolgen voor de admin</br> Geen gevolgen voor de eindgebruiker | Geen gevolgen voor de admin</br> Geen gevolgen voor de eindgebruiker | Mogelijkheid niet meer worden afgedwongen.</br> Zie [mobiel apparaat van invloed is op het abonnement is verlopen](#mobile-device-impacts-upon-subscription-expiration) en [Windows 10 PC effecten bij het abonnement is verlopen](#windows-10-pc-impacts-upon-subscription-expiration) voor meer info. | Mogelijkheid niet meer worden afgedwongen.</br> Zie [mobiel apparaat van invloed is op het abonnement is verlopen](#mobile-device-impacts-upon-subscription-expiration) en [Windows 10 PC effecten bij het abonnement is verlopen](#windows-10-pc-impacts-upon-subscription-expiration) voor meer info. |
| **Azure AD-aanmelding op een Windows 10 PC** | Geen gevolgen voor de admin</br> Geen gevolgen voor de eindgebruiker | Geen gevolgen voor de admin</br> Geen gevolgen voor de eindgebruiker | Geen gevolgen voor de admin</br> Geen gevolgen voor de eindgebruiker | Als de huurder wordt verwijderd, kan een gebruiker zich aanmelden met alleen lokale referenties. Het apparaat opnieuw de afbeelding als er geen lokale referenties. |

## <a name="mobile-device-impacts-upon-subscription-expiration"></a>Mobiel apparaat van invloed is op het abonnement is verlopen

De tabel followint bevat een overzicht van de gevolgen voor het beleid voor app op mobiele apparaten.

|                            | Volledige licentie ervaring                      | T + 60 dagen na vervaldatum          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Werkbestanden verwijderen van een apparaat niet-actief** | De werkbestanden worden verwijderd nadat de geselecteerde dagen | Werkbestanden blijven op persoonlijke apparaten van de gebruiker |
| **Afdwingen dat gebruikers alle werkbestanden opslaan in OneDrive voor Bedrijven** | Werkbestanden kunnen alleen worden opgeslagen naar OneDrive voor bedrijven | Werkbestanden kunnen overal worden opgeslagen. |
| **Werkbestanden versleutelen** | Werkbestanden worden gecodeerd | Werkbestanden zijn niet langer gecodeerd.</br> Beveiligingsbeleid worden verwijderd en gegevens op apps Office is verwijderd. |
| **PIN nodig of toegang tot Office apps vingerafdruk** | Beperkte toegang tot apps | Geen beperking van app-niveau |
| **PINCODE opnieuw instellen wanneer het aanmelden is mislukt** | Beperkte toegang tot apps | Geen beperking van app-niveau |
| **Gebruikers moeten zich weer aanmeldt nadat Office apps niet actief zijn** | Inloggen vereist | Niet aanmelden voor het openen van apps |
| **Toegang weigeren tot werkbestanden op opengebroken of geroote apparaten** | Werkbestanden kunnen niet worden geopend op basis van jailbroken/apparaten | Werkbestanden kunnen worden geopend op basis van jailbroken/apparaten |
| **Toestaan dat gebruikers inhoud kopiëren vanuit Office apps naar persoonlijke apps** | Kopiëren en plakken is beperkt tot apps beschikbaar als onderdeel van Microsoft 365 Business abonnement | Kopiëren en plakken, beschikbaar voor alle toepassingen |

## <a name="windows-10-pc-impacts-upon-subscription-expiration"></a>Windows 10 PC effecten bij het abonnement is verlopen

In de volgende tabel bevat een overzicht van de gevolgen voor het beleid van Windows 10 apparaat configureren.

|                            | Volledige licentie ervaring                      | T + 60 dagen na vervaldatum          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Pc beschermen tegen bedreigingen die werken met Windows Defender** | Inschakelen/uitschakelen is buiten de controle van gebruiker | Gebruiker kan in-of uitschakelen Windows Defender op de PC met Windows 10 |
| **Bescherm pc's tegen internetdreigingen in Microsoft Edge** | PC-beveiliging in Microsoft Edge | Gebruiker kan in-of uitschakelen in Microsoft Edge PC-bescherming |
| **Scherm bij inactiviteit van het apparaat uitschakelen** | Admin scherm time interval beleid wordt gedefinieerd | Time-out scherm kan worden geconfigureerd door de eindgebruiker |
| **Gebruikers toestaan om apps te downloaden vanuit de Microsoft Store** | Admin wordt gedefinieerd als een gebruiker apps vanaf de Microsoft Store downloaden kunt | Gebruikers kan downloaden apps van Microsoft Store op elk gewenst moment |
| **Gebruikers toestaan om Cortana te openen** | Admin definieert beleid voor toegang tot Cortana | Gebruikersapparaten in-of uitschakelen Cortana |
| **Toestaan dat gebruikers advertenties en tips van Microsoft wilt ontvangen** | Admin beleid definieert voor een gebruiker ontvangt u tips en advertenties van Microsoft | Gebruiker kan in-of uitschakelen advertenties van Microsoft en tips |
| **Gebruikers toestaan om inhoud uit Office-apps te kopiëren naar persoonlijke apps** | Admin definieert policy Windows 10-apparaten om up-to-date te houden | Gebruikers kunnen zelf beslissen wanneer Windows update |




