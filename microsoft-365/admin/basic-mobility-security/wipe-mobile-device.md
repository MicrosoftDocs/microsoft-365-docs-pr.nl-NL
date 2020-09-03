---
title: Een mobiel apparaat wissen in eenvoudige mobiliteit en beveiliging
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
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
description: Gebruik ingebouwde basis mobiliteit en beveiliging om informatie van ingeschreven apparaten te verwijderen.
ms.openlocfilehash: 4d854c7d4d81cd0b49ec7f81a49de5478b08f049
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336815"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Een mobiel apparaat wissen in eenvoudige mobiliteit en beveiliging

U kunt ingebouwde mobiliteit en beveiliging voor Microsoft 365 gebruiken om alleen organisatiegegevens te verwijderen, of om de fabrieksinstellingen te herstellen om alle gegevens van een mobiel apparaat te verwijderen en de fabrieksinstellingen te herstellen.

## <a name="before-you-begin"></a>Voordat u begint

Op mobiele apparaten kunnen gevoelige organisatiegegevens worden opgeslagen en krijgt u toegang tot de Microsoft 365-bronnen van uw organisatie. Als u de gegevens van uw organisatie wilt beschermen, kunt u de fabrieks gegevens opnieuw instellen of verwijderen:
    
- **Fabrieksinstellingen**: Hiermee verwijdert u alle gegevens op het mobiele apparaat van een gebruiker, waaronder geïnstalleerde toepassingen, Foto's en persoonlijke gegevens. Wanneer het wissen is voltooid, wordt het apparaat hersteld naar de fabrieksinstellingen.
    
- **Bedrijfsgegevens verwijderen**: Hiermee verwijdert u alleen bedrijfsgegevens en laat u geïnstalleerde toepassingen, Foto's en persoonlijke gegevens op het mobiele apparaat van een gebruiker ongewijzigd.   

- **Wanneer een apparaat wordt gewist (Factory opnieuw instellen of verwijderen van bedrijfsgegevens)**, wordt het apparaat verwijderd uit de lijst met beheerde apparaten.
    
- **Automatisch een apparaat opnieuw instellen**: u kunt een basisniveau voor mobiliteit en beveiliging instellen waarmee automatisch de instelling van een apparaat wordt hersteld nadat de gebruiker het wachtwoord van het apparaat een bepaald aantal keren probeert in te voeren. Als u dit wilt doen, volgt u de stappen in [beveiligingsbeleid voor apparaat maken in eenvoudige mobiliteit en beveiliging](create-device-security-policies-in-basic-mmobility-and-security.md).
    
- **Als u wilt weten wat de gebruikerservaring** zijn wanneer u zijn of haar apparaat wist, raadpleegt u  [Wat zijn de gevolgen voor gebruiker en apparaat?](#whats-the-user-and-device-impact).   

## <a name="wipe-a-mobile-device"></a>Een mobiel apparaat wissen

1. Ga naar het [Microsoft 365-Beheercentrum](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).
    
2. Typ Mobile Device Management in het zoekveld en selecteer **Mobile Device Management** in de lijst met resultaten. 

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Basisopties voor mobiele apparaten en Secruity":::

3. Selecteer **apparaten beheren**.

4. Selecteer het apparaat dat u wilt wissen.

5. Selecteer **beheren**.

6. Selecteer het type wissen op afstand dat u wilt uitvoeren.

    - Als u volledig wilt wissen en de fabrieksinstellingen van het apparaat wilt herstellen, selecteert u **fabrieksinstellingen opnieuw instellen**.
    - Als u selectief wilt wissen en alleen Microsoft 365-organisatiegegevens wilt verwijderen, selecteert u **bedrijfsgegevens verwijderen**.
    - Als u het apparaat wilt verwijderen uit uw organisatie, selecteert u **apparaat verwijderen**.

7. Selecteer **Ja** om te bevestigen.

## <a name="how-do-i-know-it-worked"></a>Hoe weet ik dat het werkt?

Het mobiele apparaat in de lijst met beheerde apparaten wordt niet meer weergegeven.

## <a name="why-would-you-want-to-wipe-a-device"></a>Waarom zou u een apparaat willen wissen?

Een apparaat wissen om de volgende redenen:

- Mobiele apparaten zoals smartphones en tablets worden altijd langer uitgebreid. Dit houdt in dat uw gebruikers gevoelige bedrijfsinformatie, zoals een persoonlijke identificatie of vertrouwelijke communicatie, bewaren en overal ter verduidelijking kunnen gebruiken. Als een van deze mobiele apparaten verloren gaat of wordt gestolen, kunt u het apparaat wissen, zodat de gegevens van uw organisatie niet op de juiste basis worden beëindigd.
- Wanneer een gebruiker de organisatie verlaat met een persoonlijk apparaat dat is geregistreerd voor basis mobiliteit en beveiliging, kunt u het voorkomen dat bedrijfsgegevens met die gebruiker worden gebruikt door de fabrieksinstellingen opnieuw in te voeren.
- Als uw organisatie mobiele apparaten biedt aan gebruikers, moet u mogelijk uw apparaten van tijd tot tijd opnieuw toewijzen. Door een fabriek opnieuw in te stellen op een apparaat voordat u deze aan een nieuwe gebruiker toewijst, zorgt u ervoor dat eventuele gevoelige informatie van de vorige eigenaar wordt verwijderd.

## <a name="whats-the-user-and-device-impact"></a>Wat zijn de gevolgen voor gebruiker en apparaat?

Het wissen wordt onmiddellijk naar het mobiele apparaat verzonden en het apparaat is gemarkeerd als niet-compatibel in azure Active Directory. Wanneer alle gegevens worden verwijderd wanneer een apparaat opnieuw is ingesteld op de fabrieksinstellingen, wordt in de volgende tabel beschreven welke inhoud wordt verwijderd voor elk type apparaat wanneer u bedrijfsgegevens verwijdert.

|**Inhouds dispace**|**iOS 10 en hoger**|**Android 5 en hoger**|
|:-----|:-----|:-----|
|Microsoft 365-app-gegevens worden gewist als het apparaat is beveiligd met de beveiligings beleidsregels van de intune-app. De apps worden niet verwijderd. Voor apparaten die niet zijn beveiligd met een Mobile Application Management-beleid (MAM), worden in Outlook en OneDrive geen gegevens in de cache verwijderd.<br/>**Opmerking** Voor het toepassen van een intune-beveiligingsbeleid moet u een intune-licentie hebben.|Ja|Ja|
|Beleidsinstellingen die zijn toegepast op basis mobiliteit en beveiliging op apparaten, worden niet meer afgedwongen. gebruikers kunnen de instellingen wijzigen.|Ja|Ja|
|E-mail profielen die zijn gemaakt door basis mobiliteit en beveiliging, worden verwijderd en e-mail in de cache op het apparaat wordt verwijderd.|Ja|N.v.t.|
>[!NOTE] 
>De bedrijfs portal-app is beschikbaar in de App Store voor iOS en de Play Store voor Android-apparaten.

## <a name="related-topics"></a>Verwante onderwerpen

[Eenvoudige mobiliteit en beveiliging instellen](set-up-basic-mobility-and-security.md)