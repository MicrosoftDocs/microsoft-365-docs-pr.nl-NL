---
title: Een Microsoft 365 Business CSP-abonnement overstappen 
description: Ontdek hoe u een Microsoft 365 Business CSP-abonnement overstappen van preview naar GA. 
author: jasongroce
ms.author: jasgro
ms.topic: article 
ms.prod: microsoft-365-business
localization_priority: Normal
audience: microsoft-business 
keywords: Microsoft 365 Business, Microsoft 365, SMB, transitie CSP-abonnement
ms.date: 11/01/2017
ms.openlocfilehash: 72e620df69a425ca7e5c41c5a6651bc0f7f533de
ms.sourcegitcommit: b535fe233234fd25146cfe15478e20d954f71e03
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2019
ms.locfileid: "38748336"
---
# <a name="transition-a-microsoft-365-business-csp-subscription"></a>Een Microsoft 365 Business CSP-abonnement overstappen

Als u een Microsoft 365 Business preview CSP-abonnement hebt, volgt u deze handleiding om erachter te komen hoe u uw bestaande preview-abonnement overstappen op Microsoft 365 Business GA (algemene beschikbaarheid).

**Een preview-abonnement overstappen op GA**

1. Meld u aan bij het <a href="https://partnercenter.microsoft.com" target="_blank">partner centrum</a>.
2. Selecteer in het dashboard **klanten**, en zoek en selecteer de naam van het bedrijf.

    De abonnementen voor het bedrijf worden weergegeven.

    ![Abonnementen van klanten in het partner centrum](images/pc_customer_subscriptions_1.png)
    
3. Selecteer op de pagina **abonnementen** van het bedrijf **abonnement toevoegen**.
4. Selecteer op de pagina **Nieuw abonnement** de optie **Small Business** en selecteer vervolgens **Microsoft 365 Business** in de lijst.
5. Voeg het aantal licenties toe en selecteer vervolgens **volgende: controleren** om het abonnement te bekijken en selecteer vervolgens **verzenden**.

    ![Bekijk het nieuwe abonnement op Microsoft 365 Business](images/pc_customer_reviewnewsubscription.png)

    De **abonnementen op basis van licentie** worden weergegeven **Microsoft 365 Business preview** en **Microsoft 365 Business**. U onderbreekt het preview-abonnement volgende.

6. Selecteer **Microsoft 365 Business preview**.
7. Selecteer op de pagina **Microsoft 365 Business preview** **geschorst** om het preview-abonnement op te schorten.

    ![Het Microsoft 365 Business preview-abonnement opschorten](images/pc_customer_m365bpreview_suspend.png)

8. Selecteer **verzenden** om te bevestigen.

    Controleer op de pagina **abonnementen** of de status van **Microsoft 365 Business preview** is **opgeschort**.

    ![Bevestig dat de status van het preview-abonnement is opgeschort](images/pc_customer_m365bpreview_suspend_confirm.png)

9. U desgewenst ook de gebruiksrechtovereenkomst valideren. Volg deze stappen om dit te doen:
    1. Selecteer **gebruikers en licenties** op de pagina **abonnementen** van het bedrijf.
    2. Selecteer een gebruiker op de pagina **gebruikers en licenties** .
    3. Vink op de pagina van de gebruiker de sectie **licenties toewijzen** aan en bevestig dat **Microsoft 365 Business**wordt weergegeven.

        ![Bevestig dat de Microsoft 365 business-licentie aan de gebruiker is toegewezen](images/pc_customer_userslicenses_m365b_validate.png)

## <a name="impact-to-customers-and-users-during-and-after-transition"></a>Impact op klanten en gebruikers tijdens en na de transitie

Er is geen invloed op klanten en gebruikers tijdens de overgang en na de overgang.

## <a name="impact-to-customers-who-dont-transition"></a>Impact op klanten die niet overstappen

De volgende tabel bevat een overzicht van de gevolgen voor klanten die niet overstappen van een Microsoft 365 Business preview-abonnement op een Microsoft 365 Business-abonnement.

|       | T-0 tot T + 30     | T + 30 tot T + 60 | T + 60 tot T + 120 | Beyond T + 120  |
|-------|-----------------|--------------|---------------|---------------|
| **Status** | In respijtperiode | Verlopen      | Handicap      | Deprovisioned |
| **Impact op de service**                                                        |
| **Microsoft 365 Business admin Portal** | Geen invloed op functionaliteit | Geen invloed op functionaliteit | toevoegen/verwijderen van gebruikers, abonnementen aanschaffen.</br> Kan geen licenties toewijzen/intrekken. | Abonnement van de klant en alle gegevens worden verwijderd. Admin kan andere betaalde abonnementen beheren. |
| **Office-apps**                         | Geen gevolgen voor eindgebruikers | Geen gevolgen voor eindgebruikers | Office voert de modus voor verminderde functionaliteit uit.</br> Gebruikers kunnen alleen bestanden bekijken. | Office voert de modus voor verminderde functionaliteit uit.</br> Gebruikers kunnen alleen bestanden bekijken. |
| **Cloud Services (SharePoint Online, Exchange Online, Skype, teams en meer)** | Geen gevolgen voor eindgebruikers | Geen gevolgen voor eindgebruikers | Eindgebruikers en beheerders hebben geen toegang tot gegevens in de Cloud. | Abonnement van de klant en alle gegevens worden verwijderd. |
| **EM + S componenten** | Geen invloed op admin</br> Geen gevolgen voor eindgebruikers | Geen invloed op admin</br> Geen gevolgen voor eindgebruikers | De capaciteit wordt niet langer afgedwongen.</br> Zie de [impact van mobiele apparaten op de vervaldatum](#mobile-device-impacts-upon-subscription-expiration) van het abonnement en de [gevolgen van Windows 10 PC bij het verlopen van abonnementen](#windows-10-pc-impacts-upon-subscription-expiration) voor meer informatie. | De capaciteit wordt niet langer afgedwongen.</br> Zie de [impact van mobiele apparaten op de vervaldatum](#mobile-device-impacts-upon-subscription-expiration) van het abonnement en de [gevolgen van Windows 10 PC bij het verlopen van abonnementen](#windows-10-pc-impacts-upon-subscription-expiration) voor meer informatie. |
| **Windows 10 Business** | Geen invloed op admin</br> Geen gevolgen voor eindgebruikers | Geen invloed op admin</br> Geen gevolgen voor eindgebruikers | De capaciteit wordt niet langer afgedwongen.</br> Zie de [impact van mobiele apparaten op de vervaldatum](#mobile-device-impacts-upon-subscription-expiration) van het abonnement en de [gevolgen van Windows 10 PC bij het verlopen van abonnementen](#windows-10-pc-impacts-upon-subscription-expiration) voor meer informatie. | De capaciteit wordt niet langer afgedwongen.</br> Zie de [impact van mobiele apparaten op de vervaldatum](#mobile-device-impacts-upon-subscription-expiration) van het abonnement en de [gevolgen van Windows 10 PC bij het verlopen van abonnementen](#windows-10-pc-impacts-upon-subscription-expiration) voor meer informatie. |
| **Azure AD-aanmelding bij een Windows 10-PC** | Geen invloed op admin</br> Geen gevolgen voor eindgebruikers | Geen invloed op admin</br> Geen gevolgen voor eindgebruikers | Geen invloed op admin</br> Geen gevolgen voor eindgebruikers | Zodra de Tenant is verwijderd, kan een gebruiker zich alleen aanmelden met lokale referenties. Herbeeld het apparaat als er geen lokale referenties. |

## <a name="mobile-device-impacts-upon-subscription-expiration"></a>Het mobiele apparaat heeft invloed op de vervaldatum van het abonnement

De volgende tabel bevat een overzicht van de gevolgen voor het app-beheerbeleid op mobiele apparaten.

|                            | Volledig gelicentieerde ervaring                      | T + 60 dagen na afloop          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Werkbestanden verwijderen van een inactief apparaat** | Werkbestanden worden na geselecteerde dagen verwijderd | Werkbestanden blijven op de persoonlijke apparaten van de gebruiker staan |
| **Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven** | Werkbestanden kunnen alleen worden opgeslagen in OneDrive voor bedrijven | Werkbestanden kunnen overal worden opgeslagen |
| **Werkbestanden versleutelen** | Werkbestanden worden versleuteld | Werkbestanden worden niet meer versleuteld.</br> Beveiligingsbeleid wordt verwijderd en Office-gegevens in apps worden verwijderd. |
| **PINCODE of vingerafdruk vereisen voor toegang tot Office-apps** | Beperkte toegang tot apps | Geen toegangsbeperking op app-niveau |
| **PINCODE opnieuw instellen wanneer de aanmelding mislukt** | Beperkte toegang tot apps | Geen toegangsbeperking op app-niveau |
| **Vereisen dat gebruikers zich opnieuw aanmelden nadat Office-apps inactief zijn geweest** | Aanmelden vereist | Geen aanmelding vereist |
| **Toegang weigeren tot werkbestanden op opengebroken of geroote apparaten** | Werkbestanden kunnen niet worden geopend op jailbroken/geroote apparaten | Werkbestanden kunnen worden benaderd op jailbroken/geroote apparaten |
| **Gebruikers toestaan inhoud van Office-apps naar persoonlijke apps te kopiëren** | Kopiëren/plakken beperkt tot apps die beschikbaar zijn als onderdeel van Microsoft 365 Business Subscription | Kopiëren/plakken beschikbaar voor alle apps |

## <a name="windows-10-pc-impacts-upon-subscription-expiration"></a>Windows 10 PC heeft gevolgen bij het verlopen van het abonnement

De volgende tabel bevat een overzicht van de gevolgen voor het configuratiebeleid voor Windows 10-apparaten.

|                            | Volledig gelicentieerde ervaring                      | T + 60 dagen na afloop          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Pc's beschermen tegen dreigingen met Windows Defender** | In-en uitschakelen is buiten de gebruikersbesturing | Gebruiker kan Windows Defender in-of uitschakelen op de Windows 10-PC |
| **Bescherm pc's tegen internetdreigingen in Microsoft Edge** | PC-beveiliging in Microsoft Edge | Gebruiker kan PC-beveiliging in-of uitschakelen in Microsoft Edge |
| **Apparaatscherm uitschakelen wanneer deze inactief is** | Admin definieert time-outinterval beleid voor scherm | Scherm timeout kan worden geconfigureerd door eindgebruiker |
| **Gebruikers toestaan om apps te downloaden vanuit de Microsoft Store** | Beheerder bepaalt of een gebruiker apps uit de Microsoft Store kan downloaden | Gebruiker kan apps downloaden van de Microsoft Store op elk gewenst moment |
| **Gebruikers toestaan om Cortana te openen** | Admin definieert beleid voor gebruikers toegang tot Cortana | Gebruikers apparaten om Cortana aan/uit te zetten |
| **Gebruikers toestaan om tips en advertenties van Microsoft te ontvangen** | Admin definieert beleid voor gebruikers ontvangen tips en advertenties van Microsoft | Gebruiker kan tips en advertenties van Microsoft in-of uitschakelen |
| **Gebruikers toestaan om inhoud uit Office-apps te kopiëren naar persoonlijke apps** | Admin definieert beleid om Windows 10-apparaten up-to-date te houden | Gebruikers kunnen bepalen wanneer Windows moet worden bijgewerkt |
