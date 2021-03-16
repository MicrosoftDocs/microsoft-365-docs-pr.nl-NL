---
title: Een mobiel apparaat wissen in Basismobiliteit en Beveiliging
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
description: Gebruik de ingebouwde basismobiliteit en beveiliging om gegevens van geregistreerde apparaten te verwijderen.
ms.openlocfilehash: ddf13ef6627d70128064e2d8bd185203244b12e4
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819806"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Een mobiel apparaat wissen in Basismobiliteit en Beveiliging

U kunt ingebouwde basismobiliteit en beveiliging voor Microsoft 365 gebruiken om alleen organisatiegegevens te verwijderen of om een fabrieksherstel uit te voeren om alle gegevens van een mobiel apparaat te verwijderen en deze terug te zetten naar fabrieksinstellingen.

## <a name="before-you-begin"></a>Voordat u begint

Mobiele apparaten kunnen gevoelige organisatiegegevens opslaan en toegang bieden tot de Microsoft 365-resources van uw organisatie. Als u de gegevens van uw organisatie wilt beschermen, kunt u fabrieksinstellingen opnieuw instellen of bedrijfsgegevens verwijderen:

- **Fabrieksinstellingen:** hiermee verwijdert u alle gegevens op het mobiele apparaat van een gebruiker, inclusief geïnstalleerde toepassingen, foto's en persoonlijke gegevens. Wanneer het wissen is voltooid, wordt het apparaat teruggezet naar de fabrieksinstellingen.

- **Bedrijfsgegevens verwijderen:** verwijdert alleen organisatiegegevens en laat geïnstalleerde toepassingen, foto's en persoonlijke gegevens achter op het mobiele apparaat van een gebruiker.

- **Wanneer een apparaat wordt gewist (Fabrieksinstellingen opnieuw instellen of Bedrijfsgegevens verwijderen),** wordt het apparaat verwijderd uit de lijst met beheerde apparaten.
    
- **Automatisch een** apparaat opnieuw instellen: U kunt een basisbeleid voor mobiliteit en beveiliging instellen dat een apparaat automatisch in de fabriek opnieuw wordt ingesteld nadat de gebruiker het wachtwoord van het apparaat een bepaald aantal keren niet heeft geprobeerd in te voeren. Volg hiervoor de stappen in [Apparaatbeveiligingsbeleid maken in basismobiliteit en beveiliging.](create-device-security-policies.md)
    
- **Als u de gebruikerservaring wilt weten** wanneer u het apparaat wist, zie Wat is de invloed van de gebruiker   [en het apparaat?](#whats-the-user-and-device-impact).

## <a name="wipe-a-mobile-device"></a>Een mobiel apparaat wissen

1. Ga naar het [Microsoft 365-beheercentrum.](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)

2. Typ Mobile Device Management in het zoekveld en selecteer **Mobile Device Management** in de lijst met resultaten.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Optie Voor mobiel beheer van basismobiliteit en secruity":::

3. Selecteer **Apparaten beheren.**

4. Selecteer het apparaat dat je wilt wissen.

5. Selecteer **Beheren.**

6. Selecteer het type wissen van op afstand dat je wilt uitvoeren.

    - Als u het apparaat volledig wilt wissen en herstellen naar de fabrieksinstellingen, selecteert u **Fabrieksherstel.**
    - Als u een selectief wissen en alleen microsoft 365-organisatiegegevens wilt verwijderen, selecteert u **Bedrijfsgegevens verwijderen.**
    - Als u het apparaat uit uw organisatie wilt verwijderen, selecteert u **Apparaat verwijderen.**

7. Selecteer **Ja** om te bevestigen.

## <a name="how-do-i-know-it-worked"></a>Hoe weet ik of het heeft gewerkt?

U ziet het mobiele apparaat niet meer in de lijst met beheerde apparaten.

## <a name="why-would-you-want-to-wipe-a-device"></a>Waarom wilt u een apparaat wissen?

Veeg een apparaat om deze redenen af:

- Mobiele apparaten, zoals smartphones en tablets, worden steeds voller. Dit betekent dat het voor uw gebruikers gemakkelijker is om gevoelige bedrijfsgegevens op te slaan, zoals persoonlijke identificatie of vertrouwelijke communicatie, en deze onderweg te openen. Als een van deze mobiele apparaten verloren gaat of wordt gestolen, kan het wissen van het apparaat helpen voorkomen dat de gegevens van uw organisatie in verkeerde handen komen te staan.
- Wanneer een gebruiker de organisatie verlaat met een persoonlijk apparaat dat is geregistreerd voor Basismobiliteit en Beveiliging, kunt u voorkomen dat organisatiegegevens met die gebruiker worden gebruikt door een fabrieksinstellingen uit te voeren.
- Als uw organisatie mobiele apparaten aan gebruikers levert, moet u mogelijk apparaten af en toe opnieuw toewijzen. Als u een fabrieksinstellingen op een apparaat doet voordat u deze aan een nieuwe gebruiker toewijst, zorgt u ervoor dat alle gevoelige informatie van de vorige eigenaar wordt verwijderd.

## <a name="whats-the-user-and-device-impact"></a>Wat zijn de gevolgen voor de gebruiker en het apparaat?

Het wissen wordt direct naar het mobiele apparaat verzonden en het apparaat is gemarkeerd als niet compatibel in Azure Active Directory. Terwijl alle gegevens worden verwijderd wanneer een apparaat wordt teruggezet naar fabrieksinstellingen, wordt in de volgende tabel beschreven welke inhoud voor elk apparaattype wordt verwijderd wanneer een apparaat wanneer u bedrijfsgegevens verwijdert.

|**Inhoudseffect**|**iOS 10 en hoger**|**Android 5 en hoger**|
|:-----|:-----|:-----|
|Microsoft 365-appgegevens worden gewist als het apparaat is beveiligd door intune App Protection-beleid. De apps worden niet verwijderd. Voor apparaten die niet zijn beveiligd met MAM-beleid (Mobile Application Management), worden in Outlook en OneDrive geen gegevens in de cache verwijderd.<br/>**Opmerking** Voor het toepassen van Intune App-beveiligingsbeleid moet u een Intune-licentie hebben.|Ja|Ja|
|Beleidsinstellingen die door Basismobiliteit en Beveiliging worden toegepast op apparaten, worden niet meer afgedwongen. gebruikers kunnen de instellingen wijzigen.|Ja|Ja|
|E-mailprofielen die zijn gemaakt door Basismobiliteit en Beveiliging worden verwijderd en e-mail in de cache op het apparaat wordt verwijderd.|Ja|N.v.t.|
>[!NOTE]
>De bedrijfsportal-app is beschikbaar in de App Store voor iOS en de Play Store voor Android-apparaten.

## <a name="related-topics"></a>Verwante onderwerpen

[Basic Mobility en Security instellen](set-up.md)
