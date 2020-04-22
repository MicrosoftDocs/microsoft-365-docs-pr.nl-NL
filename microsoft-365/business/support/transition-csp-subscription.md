---
title: Een Microsoft 365 Business CSP-abonnement overschakelen
description: Ontdek hoe u een Microsoft 365 Business CSP-abonnement overschakelen van preview naar algemene beschikbaarheid (GA).
author: jasongroce
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-mar
ms.author: jasgro
ms.topic: article 
ms.prod: microsoft-365-business
localization_priority: Normal
audience: microsoft-business 
keywords: Microsoft 365 Business, Microsoft 365, SMB, overgangs-CSP-abonnement
ms.date: 11/01/2017
ms.openlocfilehash: da56ce5bc70dfed5a3e86c739ef3c940b4ac1511
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635059"
---
# <a name="transition-a-microsoft-365-business-csp-subscription"></a>Een Microsoft 365 Business CSP-abonnement overschakelen

Als u een Microsoft 365 Business Preview-CSP-abonnement hebt, volgt u deze handleiding om erachter te komen hoe u uw bestaande preview-abonnement overzetten naar Microsoft 365 Business GA (algemene beschikbaarheid).

**Een voorbeeldabonnement overschakelen naar GA**

1. Meld u aan bij <a href="https://partnercenter.microsoft.com" target="_blank">Partner Center</a>.
2. Selecteer **klanten**in het dashboard en zoek en selecteer vervolgens de bedrijfsnaam.

    De abonnementen voor het bedrijf worden vermeld.

    ![Abonnementen van klanten in Partnercenter](../../media/pc_customer_subscriptions_1.png)
    
3. Selecteer op de pagina **Abonnementen van** het bedrijf de optie **Abonnement toevoegen**.
4. Selecteer op de pagina **Nieuw abonnement** de optie **Klein bedrijf** en selecteer Vervolgens **Microsoft 365 Business** in de lijst.
5. Voeg het aantal licenties toe en selecteer **Volgende: Controleer** het abonnement en selecteer **Vervolgens Verzenden**.

    ![Bekijk het nieuwe abonnement op Microsoft 365 Business](../../media/pc_customer_reviewnewsubscription.png)

    Op **licentiegebaseerde abonnementen** worden **Microsoft 365 Business Preview** en Microsoft **365 Business**weergegeven. U schorst het Preview-abonnement als volgende.

6. Selecteer **Microsoft 365 Business Preview**.
7. Selecteer op de pagina **Microsoft 365 Business Preview** de optie **Opgeschort** om het Preview-abonnement op te schorten.

    ![Het Microsoft 365 Business Preview-abonnement opschorten](../../media/pc_customer_m365bpreview_suspend.png)

8. Selecteer **Verzenden** om te bevestigen.

    Controleer **op** de pagina Abonnementen of de **Microsoft 365 Business Preview-status** **opgeschort wordt weergegeven.**

    ![De status van het Voorbeeld-abonnement bevestigen is opgeschort](../../media/pc_customer_m365bpreview_suspend_confirm.png)

9. Optioneel u ook de licentieovereenkomst valideren. Volg deze stappen om dit te doen:
    1. Selecteer **Gebruikers en licenties** op de pagina Abonnementen **van** het bedrijf.
    2. Selecteer **op** de pagina Gebruikers en licenties een gebruiker.
    3. Controleer op de pagina van de gebruiker de sectie **Licenties toewijzen** en controleer of microsoft **365 Business wordt**weergegeven.

        ![De Microsoft 365 Business-licentie is toegewezen aan de gebruiker](../../media/pc_customer_userslicenses_m365b_validate.png)

## <a name="impact-to-customers-and-users-during-and-after-transition"></a>Impact voor klanten en gebruikers tijdens en na transitie

Er is geen impact op klanten en gebruikers tijdens de overgang en na de overgang.

## <a name="impact-to-customers-who-dont-transition"></a>Impact voor klanten die niet overstappen

In de volgende tabel wordt een overzicht van de gevolgen voor klanten die niet overstappen van een Microsoft 365 Business Preview-abonnement naar een Microsoft 365 Business-abonnement.

|       | T-0 naar T+30     | T+30 naar T+60 | T+60 naar T+120 | Voorbij T+120  |
|-------|-----------------|--------------|---------------|---------------|
| **Status** | In respijtperiode | Verlopen      | Handicap      | Gedeprovisioneerd |
| **Gevolgen voor de service**                                                        |
| **Microsoft 365 Business-beheerportal** | Geen invloed op functionaliteit | Geen invloed op functionaliteit | Kan gebruikers toevoegen/verwijderen, abonnementen kopen.</br> Kan geen licenties toewijzen/intrekken. | Het abonnement van de klant en alle gegevens worden verwijderd. Beheerder kan andere betaalde abonnementen beheren. |
| **Office-apps**                         | Geen gevolgen voor de eindgebruiker | Geen gevolgen voor de eindgebruiker | Office voert de modus voor verminderde functionaliteit in.</br> Gebruikers kunnen alleen bestanden bekijken. | Office voert de modus voor verminderde functionaliteit in.</br> Gebruikers kunnen alleen bestanden bekijken. |
| **Cloudservices (SharePoint Online, Exchange Online, Skype, Teams en meer)** | Geen gevolgen voor de eindgebruiker | Geen gevolgen voor de eindgebruiker | Eindgebruikers en beheerders hebben geen toegang tot gegevens in de cloud. | Het abonnement van de klant en alle gegevens worden verwijderd. |
| **EM+S-componenten** | Geen impact van de beheerder</br> Geen gevolgen voor de eindgebruiker | Geen impact van de beheerder</br> Geen gevolgen voor de eindgebruiker | Capaciteit wordt niet langer afgedwongen.</br> Zie [de gevolgen voor mobiele apparaten bij het verlopen van het abonnement](#mobile-device-impacts-upon-subscription-expiration) en windows [10-pc heeft gevolgen voor het verlopen van het abonnement](#windows-10-pc-impacts-upon-subscription-expiration) voor meer informatie. | Capaciteit wordt niet langer afgedwongen.</br> Zie [de gevolgen voor mobiele apparaten bij het verlopen van het abonnement](#mobile-device-impacts-upon-subscription-expiration) en windows [10-pc heeft gevolgen voor het verlopen van het abonnement](#windows-10-pc-impacts-upon-subscription-expiration) voor meer informatie. |
| **Windows 10 Business** | Geen impact van de beheerder</br> Geen gevolgen voor de eindgebruiker | Geen impact van de beheerder</br> Geen gevolgen voor de eindgebruiker | Capaciteit wordt niet langer afgedwongen.</br> Zie [de gevolgen voor mobiele apparaten bij het verlopen van het abonnement](#mobile-device-impacts-upon-subscription-expiration) en windows [10-pc heeft gevolgen voor het verlopen van het abonnement](#windows-10-pc-impacts-upon-subscription-expiration) voor meer informatie. | Capaciteit wordt niet langer afgedwongen.</br> Zie [de gevolgen voor mobiele apparaten bij het verlopen van het abonnement](#mobile-device-impacts-upon-subscription-expiration) en windows [10-pc heeft gevolgen voor het verlopen van het abonnement](#windows-10-pc-impacts-upon-subscription-expiration) voor meer informatie. |
| **Azure AD-aanmelding op een Windows 10-pc** | Geen impact van de beheerder</br> Geen gevolgen voor de eindgebruiker | Geen impact van de beheerder</br> Geen gevolgen voor de eindgebruiker | Geen impact van de beheerder</br> Geen gevolgen voor de eindgebruiker | Zodra de tenant is verwijderd, kan een gebruiker zich alleen aanmelden met lokale referenties. Beeld het apparaat opnieuw op als er geen lokale referenties zijn. |

## <a name="mobile-device-impacts-upon-subscription-expiration"></a>Gevolgen voor mobiele apparaten bij verlopen abonnement

In de volgende tabel wordt een overzicht van de impact op het app-beheerbeleid op mobiele apparaten.

|                            | Volledig gelicentieerde ervaring                      | T+60 dagen na afloop          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Werkbestanden verwijderen van een inactief apparaat** | Werkbestanden worden verwijderd na geselecteerde dagen | Werkbestanden blijven op de persoonlijke apparaten van de gebruiker staan |
| **Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven** | Werkbestanden kunnen alleen worden opgeslagen in OneDrive voor Bedrijven | Werkbestanden kunnen overal worden opgeslagen |
| **Werkbestanden versleutelen** | Werkbestanden worden versleuteld | Werkbestanden worden niet meer versleuteld.</br> Beveiligingsbeleid wordt verwijderd en Office-gegevens in apps worden verwijderd. |
| **Pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps** | Beperkte toegang tot apps | Geen toegangsbeperking op app-niveau |
| **Pincode opnieuw instellen wanneer aanmelding mislukt** | Beperkte toegang tot apps | Geen toegangsbeperking op app-niveau |
| **Gebruikers verplichten zich opnieuw aan te melden nadat Office-apps zijn inactief** | Aanmelden vereist | Aanmelden is niet nodig |
| **Toegang weigeren tot werkbestanden op opengebroken of geroote apparaten** | Werkbestanden zijn niet toegankelijk op jailbroken/gewortelde apparaten | Werkbestanden kunnen worden geopend op jailbroken / geworteld apparaten |
| **Gebruikers toestaan inhoud van Office-apps naar Persoonlijke apps te kopiëren** | Kopiëren/plakken beperkt tot apps die beschikbaar zijn als onderdeel van het Microsoft 365-abonnement | Kopiëren/plakken beschikbaar voor alle apps |

## <a name="windows-10-pc-impacts-upon-subscription-expiration"></a>Windows 10 PC heeft gevolgen voor verlopen abonnement

In de volgende tabel wordt een overzicht van de impact op het configuratiebeleid voor Windows 10-apparaten.

|                            | Volledig gelicentieerde ervaring                      | T+60 dagen na afloop          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Pc's beschermen tegen bedreigingen met Windows Defender** | In- en uitschakelen valt buiten de gebruikersbesturingselement | Gebruiker kan Windows Defender in- of uitschakelen op de Windows 10-pc |
| **Bescherm pc's tegen internetdreigingen in Microsoft Edge** | Pc-beveiliging in Microsoft Edge | Gebruiker kan pc-beveiliging in- of uitschakelen in Microsoft Edge |
| **Apparaatscherm uitschakelen wanneer u niet actief bent** | Beheerder definieert intervalbeleid voor schermtime-out | Schermtime-out kan worden geconfigureerd door de eindgebruiker |
| **Gebruikers toestaan om apps te downloaden vanuit de Microsoft Store** | Beheerder bepaalt of een gebruiker apps kan downloaden uit de Microsoft Store | Gebruiker kan op elk gewenst moment apps downloaden uit de Microsoft Store |
| **Gebruikers toestaan om Cortana te openen** | Beheerder definieert beleid voor gebruikerstoegang tot Cortana | Gebruikersapparaten die Cortana in- of uitschakelen |
| **Gebruikers toestaan tips en advertenties van Microsoft te ontvangen** | Beheerder definieert beleid voor gebruikers ontvangen tips en advertenties van Microsoft | Gebruiker kan tips en advertenties van Microsoft in- en uitschakelen |
| **Gebruikers toestaan om inhoud uit Office-apps te kopiëren naar persoonlijke apps** | Beheerder definieert beleid om Windows 10-apparaten up-to-date te houden | Gebruikers kunnen beslissen wanneer ze Windows bijwerken |
