---
title: Een Microsoft 365 Business CSP-abonnement overstappen
description: Ontdek hoe u een CSP-Microsoft 365 Business kunt overstappen van preview naar algemene beschikbaarheid (GA).
author: jasongroce
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-mar
- AdminSurgePortfolio
ms.author: jasongroce
ms.topic: article
manager: jasonh
ms.prod: microsoft-365-business
localization_priority: Normal
audience: microsoft-business
keywords: Microsoft 365 Business, Microsoft 365, SMB, overgang CSP-abonnement
ms.date: 11/01/2017
ms.openlocfilehash: 3f6c71edb50cc3c5509e61a83efb64185c10648d
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924998"
---
# <a name="transition-a-microsoft-365-business-csp-subscription"></a>Een Microsoft 365 Business CSP-abonnement overstappen

Als u een Microsoft 365 Business Preview CSP-abonnement hebt, volgt u deze handleiding om te zien hoe u uw bestaande preview-abonnement kunt overstappen naar Microsoft 365 Business GA (algemene beschikbaarheid).

**Een voorbeeldabonnement overstappen op GA**

1. Meld u aan bij <a href="https://partnercenter.microsoft.com" target="_blank">partnercentrum.</a>
2. Selecteer klanten in het dashboard **en** zoek en selecteer de bedrijfsnaam.

    De abonnementen voor het bedrijf worden weergegeven.

    ![Abonnementen van klanten in partnercentrum](../../media/pc_customer_subscriptions_1.png)
    
3. Selecteer op de pagina **Abonnementen van het** bedrijf de optie Abonnement **toevoegen.**
4. Selecteer op **de pagina** Nieuw abonnement de optie **Kleine bedrijven** en selecteer **Microsoft 365 Business** in de lijst.
5. Voeg het aantal licenties toe en selecteer **Volgende: Controleren** om het abonnement te bekijken en selecteer **vervolgens Verzenden.**

    ![Het nieuwe abonnement voor Microsoft 365 Business](../../media/pc_customer_reviewnewsubscription.png)

    De **op licentie gebaseerde abonnementen worden weergegeven** Microsoft 365 Business **Preview** en **Microsoft 365 Business.** Het preview-abonnement wordt vervolgens opgeschort.

6. Selecteer **Microsoft 365 Business Voorbeeld.**
7. Selecteer op **Microsoft 365 Business pagina Voorbeeld** de optie Opgeschort **om** het preview-abonnement op te schorten.

    ![Het preview Microsoft 365 Business-abonnement opschorten](../../media/pc_customer_m365bpreview_suspend.png)

8. Selecteer **Verzenden om** te bevestigen.

    Controleer op **de pagina Abonnementen** of de status Microsoft 365 Business **preview** wordt **weergegeven.**

    ![Controleren of de status van het Preview-abonnement is opgeschort](../../media/pc_customer_m365bpreview_suspend_confirm.png)

9. Desgewenst kunt u ook de licentieovereenkomst valideren. Ga hiervoor als volgt te werk:
    1. Selecteer **Gebruikers en licenties op** de pagina Abonnementen van **het** bedrijf.
    2. Selecteer een **gebruiker op de pagina** Gebruikers en licenties.
    3. Controleer op de pagina van  de gebruiker de sectie Licenties toewijzen en bevestig dat deze **Microsoft 365 Business.**

        ![Controleer of Microsoft 365 Business licentie is toegewezen aan de gebruiker](../../media/pc_customer_userslicenses_m365b_validate.png)

## <a name="impact-to-customers-and-users-during-and-after-transition"></a>Gevolgen voor klanten en gebruikers tijdens en na de overgang

Er is geen invloed op klanten en gebruikers tijdens de overgang en na de overgang.

## <a name="impact-to-customers-who-dont-transition"></a>Gevolgen voor klanten die niet overstappen

De volgende tabel bevat een overzicht van de gevolgen voor klanten die niet overstappen van een Microsoft 365 Business Preview-abonnement naar een Microsoft 365 Business abonnement.

|       | T-0 tot en met T+30     | T+30 naar T+60 | T+60 naar T+120 | Voorbij T+120  |
|-------|-----------------|--------------|---------------|---------------|
| **Status** | In respijtperiode | Verlopen      | Uitgeschakeld      | Deprovisioned |
| **Service-effecten**                                                        |
| **Microsoft 365 Business beheerportal** | Geen invloed op functionaliteit | Geen invloed op functionaliteit | Kan gebruikers toevoegen/verwijderen, abonnementen kopen.</br> U kunt geen licenties toewijzen/intrekken. | Het abonnement van de klant en alle gegevens worden verwijderd. Beheerder kan andere betaalde abonnementen beheren. |
| **Office apps**                         | Geen gevolgen voor eindgebruikers | Geen gevolgen voor eindgebruikers | Office in de modus Beperkte functionaliteit.</br> Gebruikers kunnen alleen bestanden bekijken. | Office in de modus Beperkte functionaliteit.</br> Gebruikers kunnen alleen bestanden bekijken. |
| **Cloudservices (SharePoint Online, Exchange Online, Skype, Teams en meer)** | Geen gevolgen voor eindgebruikers | Geen gevolgen voor eindgebruikers | Eindgebruikers en beheerders hebben geen toegang tot gegevens in de cloud. | Het abonnement van de klant en alle gegevens worden verwijderd. |
| **EM+S-onderdelen** | Geen invloed van beheerder</br> Geen gevolgen voor eindgebruikers | Geen invloed van beheerder</br> Geen gevolgen voor eindgebruikers | De mogelijkheid wordt niet meer afgedwongen.</br> Zie [Gevolgen voor mobiel apparaat bij het](#mobile-device-impacts-upon-subscription-expiration) verlopen van het abonnement en Windows 10 van [pc-effecten op het verlopen van](#windows-10-pc-impacts-upon-subscription-expiration) het abonnement voor meer informatie. | De mogelijkheid wordt niet meer afgedwongen.</br> Zie [Gevolgen voor mobiel apparaat bij het](#mobile-device-impacts-upon-subscription-expiration) verlopen van het abonnement en Windows 10 van [pc-effecten op het verlopen van](#windows-10-pc-impacts-upon-subscription-expiration) het abonnement voor meer informatie. |
| **Windows 10 Business** | Geen invloed van beheerder</br> Geen gevolgen voor eindgebruikers | Geen invloed van beheerder</br> Geen gevolgen voor eindgebruikers | De mogelijkheid wordt niet meer afgedwongen.</br> Zie [Gevolgen voor mobiel apparaat bij het](#mobile-device-impacts-upon-subscription-expiration) verlopen van het abonnement en Windows 10 van [pc-effecten op het verlopen van](#windows-10-pc-impacts-upon-subscription-expiration) het abonnement voor meer informatie. | De mogelijkheid wordt niet meer afgedwongen.</br> Zie [Gevolgen voor mobiel apparaat bij het](#mobile-device-impacts-upon-subscription-expiration) verlopen van het abonnement en Windows 10 van [pc-effecten op het verlopen van](#windows-10-pc-impacts-upon-subscription-expiration) het abonnement voor meer informatie. |
| **Azure AD-aanmelding bij een Windows 10 pc** | Geen invloed van beheerder</br> Geen gevolgen voor eindgebruikers | Geen invloed van beheerder</br> Geen gevolgen voor eindgebruikers | Geen invloed van beheerder</br> Geen gevolgen voor eindgebruikers | Wanneer de tenant is verwijderd, kan een gebruiker zich alleen aanmelden met lokale referenties. Afbeelding van het apparaat opnieuw maken als er geen lokale referenties zijn. |

## <a name="mobile-device-impacts-upon-subscription-expiration"></a>Gevolgen voor mobiel apparaat bij verlopen abonnement

In de volgende tabel worden de gevolgen voor het beleid voor app-beheer op mobiele apparaten samengevat.

|                            | Volledig gelicentieerde ervaring                      | T+60 dagen na verloop van tijd          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Werkbestanden verwijderen van een inactief apparaat** | Werkbestanden worden na geselecteerde dagen verwijderd | Werkbestanden blijven op de persoonlijke apparaten van de gebruiker staan |
| **Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven** | Werkbestanden kunnen alleen worden opgeslagen in OneDrive voor Bedrijven | Werkbestanden kunnen overal worden opgeslagen |
| **Werkbestanden versleutelen** | Werkbestanden worden versleuteld | Werkbestanden worden niet meer versleuteld.</br> Beveiligingsbeleid wordt verwijderd en Office gegevens in apps verwijderd. |
| **Pincode of vingerafdruk vereisen om toegang te krijgen tot Office apps** | Beperkte toegang tot apps | Geen toegangsbeperking op app-niveau |
| **Pincode opnieuw instellen wanneer aanmelden mislukt** | Beperkte toegang tot apps | Geen toegangsbeperking op app-niveau |
| **Gebruikers verplichten zich opnieuw aan te melden nadat Office apps inactief zijn geweest** | Aanmelding vereist | Aanmelden is niet vereist |
| **Toegang weigeren tot werkbestanden op opengebroken of geroote apparaten** | Werkbestanden kunnen niet worden gebruikt op jailbroken/geroote apparaten | Werkbestanden kunnen worden gebruikt op jailbroken/geroote apparaten |
| **Gebruikers toestaan inhoud te kopiëren van Office apps naar persoonlijke apps** | Kopiëren/plakken beperkt tot apps die beschikbaar zijn als onderdeel van Microsoft 365-abonnement | Kopiëren/plakken beschikbaar voor alle apps |

## <a name="windows-10-pc-impacts-upon-subscription-expiration"></a>Windows 10 Pc heeft gevolgen voor het verlopen van het abonnement

In de volgende tabel wordt een overzicht van de invloed op Windows 10 beleid voor apparaatconfiguratie.

|                            | Volledig gelicentieerde ervaring                      | T+60 dagen na verloop van tijd          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Pc's beschermen tegen bedreigingen met Windows Defender** | In-/uitschakelen valt buiten het beheer van de gebruiker | Gebruiker kan de Windows Defender in- Windows 10 pc |
| **Bescherm pc's tegen internetdreigingen in Microsoft Edge** | Pc-beveiliging in Microsoft Edge | Gebruiker kan pc-beveiliging in- of uitschakelen in Microsoft Edge |
| **Apparaatscherm uitschakelen inactief** | Beheerder definieert het intervalbeleid voor schermtijd | Scherm time-out kan worden geconfigureerd door eindgebruiker |
| **Gebruikers toestaan om apps te downloaden vanuit de Microsoft Store** | Beheerder definieert of een gebruiker apps kan downloaden van Microsoft Store | Gebruiker kan op elk gewenst moment apps Microsoft Store downloaden |
| **Gebruikers toestaan om Cortana te openen** | Beheerder definieert beleid voor gebruikerstoegang tot Cortana | Gebruikersapparaten om Cortana in- of uit te schakelen |
| **Gebruikers toestaan tips en advertenties van Microsoft te ontvangen** | Beheerder definieert beleid voor gebruikers ontvangen tips en advertenties van Microsoft | Gebruiker kan tips en advertenties van Microsoft in- of uitschakelen |
| **Gebruikers toestaan om inhoud uit Office-apps te kopiëren naar persoonlijke apps** | Beheerder definieert beleid om Windows 10 apparaten up-to-date te houden | Gebruikers kunnen bepalen wanneer ze hun Windows |
