---
title: Basis Veelgestelde vragen over de mobiliteit en beveiliging
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Veelgestelde vragen over basis mobiliteit en beveiliging.
ms.openlocfilehash: a79b7df53f717d511603ec57e09ce4d6c523d14d
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336838"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>Basis Veelgestelde vragen over de mobiliteit en beveiliging

Dit artikel bevat veelgestelde vragen over basis mobiliteit en beveiliging, een functie waarmee u mobiele apparaten in Microsoft 365 kunt beheren en beveiligen. Als u geen antwoord kunt vinden op uw vraag, laat het ons weten door een opmerking op de pagina te plaatsen, zodat we uw vraag kunnen beantwoorden aan dit artikel.

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>Hoe kan ik eenvoudige mobiliteit en beveiliging weergeven? Ik zie het niet in het Microsoft 365-Beheercentrum

1.  Activeer basis mobiliteit en beveiliging door naar de pagina [Office 365 Security & compliance](https://protection.office.com/) te gaan.   

2.  Ga naar preventie van gegevensverlies > Apparaatbeheer.   

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>Hoe kan ik aan de slag met Apparaatbeheer in eenvoudige mobiliteit en beveiliging?

U moet vier stappen uitvoeren om aan de slag te gaan met eenvoudige mobiliteit en beveiliging: 

1. Activeer basis mobiliteit en beveiliging door naar het [Office 365-beveiligings & naleving](https://protection.office.com/)te gaan.
    
2. Ga naar preventie van gegevensverlies > Apparaatbeheer > apparaatbeleid.
    
3. Maak beleidsregels voor Apparaatbeheer en pas deze toe voor groepen gebruikers die zijn ingesteld in beveiligingsgroepen. We raden u aan eerst het beleid te implementeren in een kleine testgroep. Zie voor meer informatie het artikel [beveiligingsbeleid voor apparaten maken voor eenvoudige mobiliteit en beveiliging](create-device-security-policies-in-basic-mmobility-and-security.md).      

4. Gebruikers voor wie een beleidsregel is toegepast, wordt gevraagd hun apparaat te registreren wanneer ze toegang proberen te krijgen tot gegevens van Microsoft 365. Zie voor meer informatie [uw mobiele apparaat registreren met behulp van eenvoudige mobiliteit en beveiliging](enroll-your-mobile-device-using-basic-mobility-and-security.md).

Zie [eenvoudige mobiliteit en beveiliging instellen](set-up-basic-mobility-and-security.md)voor meer informatie.

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Ik probeer een eenvoudige mobiliteit en beveiliging in te stellen, maar het lijkt erop te zitten. Voor de Microsoft 365-service status is een tijdje ' inrichten ' weergegeven. Wat kan ik doen?

Het kan enige tijd duren voordat de dienst klaar is voor gebruik. Wanneer de inrichting is voltooid, ziet u de pagina Mobile Device Management for Microsoft 365. Neem contact op met de ondersteuning als u 24 uur hebt gewacht en de status nog steeds wordt ingericht. Zie [nog steeds hulp nodig?](https://support.microsoft.com/office/frequently-asked-questions-about-basic-mobility-and-security-3871f99c-c9db-4a23-86f9-902c1b02f58d#bkmk_needhelp) voor ondersteuningsopties. 

## <a name="what-can-i-do-if-device-enrollment-fails"></a>Wat kan ik doen als apparaatregistratie mislukt?

Als u problemen ondervindt bij het registreren van een apparaat dat is geregistreerd, controleert u eerst het volgende:

- Controleer of het apparaat niet al is geregistreerd bij een andere provider voor mobiel Apparaatbeheer, zoals intune.
    
- Controleer of het apparaat is ingesteld op de juiste datum en tijd.
    
- Overschakelen naar een ander WIFI-of mobiel netwerk op het apparaat.
    
- Voor Android-of iOS-apparaten verwijdert u de app intune Company portal van het apparaat en installeert u deze opnieuw.
    
Als de registratie nog steeds niet werkt, raadpleegt u [problemen met eenvoudige mobiliteit en beveiliging oplossen](troubleshoot-basic-mobility-and-security.md).

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Wat is het verschil tussen intune en basis mobiliteit en beveiliging?

Basis mobiliteit en beveiliging wordt gehost door de intune-service. Het is een subset van intune-Services, geleverd als een extra voordeel van Microsoft 365 en is een ingebouwde oplossing van de Cloud voor het beheren van apparaten in uw organisatie. Voor een vergelijking naast elkaar van de twee services die u kunt gebruiken om te bepalen of het gebruik van intune of basis mobiliteit en beveiliging voor Microsoft 365 het best geschikt voor u is, raadpleegt u [kiezen tussen basisbeveiliging en intune](choose-between-basic-mobility-and-security-and-intune.md).

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>Hoe werken beleidsregels voor basis mobiliteit en beveiliging? Hoe stel ik ze in? Wilt u ze uitschakelen?

Wanneer u de eerste configuratie voor mobiliteit en beveiliging hebt voltooid, maakt u beleidsregels en past u deze toe aan groepen gebruikers in het beveiligings & nalevings centrum. Voor beleidsregels moeten gebruikers van de beleidsregels de juiste mobiliteit en beveiliging gebruiken voordat het apparaat kan worden gebruikt voor toegang tot de gegevens van Microsoft 365. De beleidsregels die u instelt, bepalen hoe vaak wachtwoorden moeten opnieuw worden ingesteld of of gegevensversleuteling is vereist. Zie voor meer informatie het artikel [beveiligingsbeleid voor apparaten maken in Basisbeperkingen voor de mobiliteit en beveiliging](create-device-security-policies-in-basic-mmobility-and-security.md)   en [Microsoft 365-nalevings centrum](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8).

Voor stapsgewijze instructies voor het maken en implementeren van apparaatprofielen, raadpleegt u [beveiligingsbeleid voor apparaten maken in eenvoudige mobiliteit en beveiliging](create-device-security-policies-in-basic-mmobility-and-security.md).

Als u een bepaalde groep gebruikers wilt uitsluiten van invloed op beleidsregels, kunt u een groep toevoegen aan de groep uitzonderingen.

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>Kan ik overstappen van Exchange ActiveSync-Apparaatbeheer op basis van mobiliteit en beveiliging voor Microsoft 365?

Als u al Exchange ActiveSync-beleidsregels gebruikt om mobiele apparaten te beheren, kunt u de basisstappen en beveiliging gebruiken door de stappen te volgen voor het instellen van basis mobiliteit en beveiliging. Zie [beveiliging van gebruikers en apparaten beschermen](https://go.microsoft.com/fwlink/?LinkId=615145) en [basis mobiliteit en beveiliging instellen](set-up-basic-mobility-and-security.md)voor meer informatie.

Wanneer u de beleidsregels die u maakt, in basis van mobiliteit en beveiliging toepast voor groepen gebruikers, worden deze genegeerd door de beleidsregels voor het postvak voor mobiele apparaten en de regels voor Apparaattoegang die u eerder in het Exchange-Beheercentrum voor die gebruikers hebt gemaakt.

Als een apparaat is ingeschreven voor basis mobiliteit en beveiliging, wordt het postvak beleid mobiele apparaten van Exchange ActiveSync of de regel voor het openen van apparaten op het apparaat genegeerd.

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>Ik heb basis mobiliteit en beveiliging ingesteld, maar nu wil ik deze verwijderen. Wat zijn de stappen?

Helaas kunt u de basis mobiliteit en beveiliging van basis van de burger en beveiliging van uw site helaas niet eenvoudig opzeggen. U kunt de groep gebruikers ook verwijderen door gebruikersbeveiligingsgroepen te verwijderen uit het apparaatbeleid dat u hebt gemaakt. U kunt ook de optie voor iedereen uitschakelen door het apparaatbeleid te verwijderen, zodat ze niet worden ingesteld. Zie [eenvoudige mobiliteit en beveiliging](turn-off-basic-mobility-and-security.md)uitschakelen voor meer informatie.

