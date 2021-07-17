---
title: Voorbeeld en test Windows 11 met Microsoft Managed Desktop
description: Hoe u 11 Windows in uw omgeving
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8dee18909d82656bcfb3e63fdc078328c678e660
ms.sourcegitcommit: ea8de1b48adb6df92fb9351ea862184a9f16cbbb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/16/2021
ms.locfileid: "53461385"
---
# <a name="preview-and-test-windows-11-with-microsoft-managed-desktop"></a>Voorbeeld en test Windows 11 met Microsoft Managed Desktop

 Registreren en deelnemen aan het compatibiliteitstestprogramma Windows 11 in uw Microsoft Managed Desktop omgeving. Zie voor meer informatie Windows 11 en Microsoft Managed Desktop over het algemeen [Windows 11 en Microsoft Managed Desktop.](../intro/win11-overview.md) 

## <a name="check-device-eligibility"></a>Apparaat in aanmerking komen controleren

Tot op heden voldoet meer dan 95% Microsoft Managed Desktop apparaten aan geschiktheidscriteria voor Windows [11](/windows/whats-new/windows-11-requirements). U kunt gegevens over de geschiktheidsstatus van uw apparaten op Microsoft Managed Desktop. Als u de aanvraag wilt indienen, gaat u als volgt te werk:

1. Open een nieuwe serviceaanvraag met het Microsoft Managed Desktop Service Engineering-team. Zie Ondersteuning voor beheerders als u meer informatie nodig hebt over het indienen [van de aanvraag.](admin-support.md)
2. Gebruik deze waarden voor de velden:
    - Titel: Windows 11 apparaat in aanmerking komen
    - Type aanvraag: informatie aanvragen
    - Categorie: Apparaten
    - Subcategorie: Overige


## <a name="add-devices-to-the-windows-11-test-group"></a>Apparaten toevoegen aan de Windows 11-testgroep

Begin met het toevoegen van apparaten aan de apparaatgroep **\[ (Modern Workplace \] Windows 11 Pre-Release Test Devices)** die zijn gemaakt voor het testen en evalueren van Windows 11. Apparaten in deze groep krijgen nieuwe Windows 11 builds en Microsoft Managed Desktop basislijnconfiguraties zodra ze beschikbaar komen en worden gecontroleerd op betrouwbaarheidsproblemen.

U kunt een van uw bestaande of nieuwe apparaten kiezen voor Windows 11-tests, maar u moet geen productieapparaten in deze groep registreren vanwege het verhoogde risico op fouten of compatibiliteitsproblemen in pre-release builds. Eerdere apparaatgroeptoewijzingen worden verwijderd na toewijzing aan deze groep.

Als u uw apparaten wilt registreren in de pre-release testgroep:

1. Open een nieuwe serviceaanvraag met het Microsoft Managed Desktop Service Engineering-team.
2. Gebruik deze waarden voor de velden:
    - Titel: Windows 11 compatibiliteitsinschrijving
    - Aanvraagtype: Aanvraag wijzigen
    - Categorie: Apparaten
    - Subcategorie: toewijzing van de implementatiegroep
3. Vermeld in het beschrijvingsveld de serienummers van de apparaten die u wilt gebruiken voor Windows 11 testen. Houd er rekening mee dat, indien van de opgegeven apparaten, nog niet zijn geïmplementeerd in uw Microsoft Managed Desktop tenant.

## <a name="prioritize-applications-to-submit-to-test-base"></a>Prioriteit geven aan toepassingen die moeten worden ingediend bij Test Base

Bedrijfskritische toepassingen zijn de beste kandidaten voor meer validatie in een gesloten Windows 11 omgeving. We kunnen u helpen prioriteit te geven aan apps Windows 11 testen op basis van gebruiks- en betrouwbaarheidsgegevens. Als u onze aanbevelingen wilt aanvragen, volgt u de volgende stappen:

1. Open een nieuwe serviceaanvraag met het Microsoft Managed Desktop Service Engineering-team. Zie Ondersteuning voor beheerders als u meer informatie nodig hebt over het indienen [van de aanvraag.](admin-support.md)
2. Gebruik deze waarden voor de velden:
    - Titel: Windows 11 testbasiskandidaten
    - Type aanvraag: informatie aanvragen
    - Categorie: Apps
    - Subcategorie: Overige

## <a name="report-issues"></a>Problemen met rapport

Als u problemen Windows 11 compatibiliteitsproblemen ondervindt met uw line-of-business- of Microsoft 365-apps, meldt u deze aan ons voor onderzoek en herstel. Als u een probleem wilt rapporteren, volgt u de volgende stappen:

1. Open een nieuwe serviceaanvraag met het Microsoft Managed Desktop Service Engineering-team.
2. Gebruik deze waarden voor de velden:
    - Titel: Windows 11 compatibiliteitstests
    - Type aanvraag: Incident
    - Categorie: Apparaten
    - Subcategorie: Windows upgrade/update
3. Beschrijf het gedrag en hoe ernstig het uw bedrijf in een productieomgeving zou hinderen.

Microsoft Managed Desktop triages en behandelt problemen met pre-release builds op basis van het effect op de productiviteit. Hoewel onze servicebeschrijving geen betrekking heeft op problemen met pre-release builds, overleggen we met klantbeheerders om ervoor te zorgen dat problemen die de productiviteit van gebruikers blokkeren worden opgelost voordat de migratie binnen een bepaalde tenant wordt begonnen.
