---
title: Microsoft Compliance Manager en de AVG
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager is een gratis hulpprogramma voor risicoanalyse op basis van werkstroom in de Microsoft Service Trust Portal. Met Compliance Manager kunt u nalevingsactiviteiten met betrekking tot Microsoft-cloudservices bijhouden, toewijzen en controleren.
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "52161432"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a>Microsoft Compliance Manager en de AVG

De Algemene verordening gegevensbescherming (AVG) van de Europese Unie kan van invloed zijn op uw compliancestrategie en specifieke acties voor het beheren van gebruikers- en klantgegevens die worden gebruikt in Compliance Manager.

## <a name="user-privacy-settings"></a>Privacyinstellingen voor gebruikers

Volgens bepaalde regelgeving moet een organisatie gegevens uit de gebruikersgeschiedenis kunnen verwijderen. Compliance Manager biedt **gebruikers privacy Instellingen** functies waarmee beheerders:
  
- [Een gebruiker zoeken](#search-for-a-user)
- [Een rapport met de accountgegevensgeschiedenis exporteren](#export-a-report-of-account-data-history)
- [Gebruikersgeschiedenis verwijderen](#delete-user-data-history)
  
## <a name="search-for-a-user"></a>Een gebruiker zoeken

Een gebruiker zoeken:
  
1. Voer de e-mailalias van de gebruiker in (de informatie links van het @-symbool) en kies de domeinnaam in de lijst met domeinachtervoegsels aan de rechterkant. Controleer voor organisaties met meerdere geregistreerde domeinen het achtervoegsel van de domeinnaam om te controleren of het juist is.

2. Wanneer u de gebruikersnaam correct hebt ingevoerd, selecteert u **Zoeken.**

3. Voor gebruikersaccounts die niet worden geretourneerd, wordt op de pagina **Gebruiker niet gevonden weergegeven.** Controleer de e-mailadresgegevens van de gebruiker en correcties indien nodig. Als u opnieuw wilt proberen, **selecteert** u Zoeken .

4. Voor geretourneerde gebruikersaccounts verandert de tekst van de knop van **Zoeken in** **Leegmaken.** Dit geeft aan dat het geretourneerde gebruikersaccount de bedrijfscontext is voor de extra functies en dat deze functies van toepassing zijn op dit gebruikersaccount.

5. Als u zoekresultaten wilt leeg maken en wilt zoeken naar een andere gebruiker, selecteert u **Clear**.

## <a name="export-a-report-of-account-data-history"></a>Een rapport met de accountgegevensgeschiedenis exporteren

Voor elk geïdentificeerd gebruikersaccount kunt u een rapport genereren met afhankelijkheden die aan het account zijn gekoppeld. Met deze informatie kunt u de geopende actie-items opnieuw toewijzen of ervoor zorgen dat u toegang hebt tot eerder geüpload bewijs.
  
 Een rapport genereren en exporteren:
  
1. Selecteer **Exporteren** om een rapport te genereren en te downloaden van de actie-items voor compliancebeheer die momenteel zijn toegewezen aan het geretourneerde gebruikersaccount en de lijst met documenten die door die gebruiker zijn geüpload. Als er geen toegewezen acties of geüploade documenten zijn, wordt in een foutbericht 'Geen gegevens voor deze gebruiker' weergegeven.

2. Het rapport wordt gedownload op de achtergrond van het actieve browservenster, als u geen downloadpopup ziet die u de downloadgeschiedenis van uw browser wilt controleren.

3. Open het document om de rapportgegevens te bekijken.

> [!IMPORTANT]
> De rapportgegevens zijn geen historische lijst met statuswijzigingen in de toewijzingsgeschiedenis van actieitem. Het gegenereerde rapport is een momentopname van het besturingselement Actie-items die zijn toegewezen op het moment dat het rapport wordt uitgevoerd (datum- en tijdstempel in het rapport). Een volgende herplaatsing van actie-items resulteert bijvoorbeeld in verschillende momentopnamerapportgegevens als het rapport opnieuw voor dezelfde gebruiker wordt gegenereerd.
  
## <a name="delete-user-data-history"></a>Gebruikersgeschiedenis verwijderen

Hiermee stelt u alle besturingselementactie-items in die zijn toegewezen aan de geretourneerde gebruiker op 'niet-toegewezen'. Hiermee stelt **u de geüploade waarde** in voor documenten die door de geretourneerde gebruiker zijn geüpload naar 'gebruiker verwijderd'.
  
De geschiedenis van het gebruikersaccount actie-item en de uploadgeschiedenis van documenten verwijderen:
  
1. Selecteer **Verwijderen**.

    Er wordt een bevestigingsdialoogvenster weergegeven: " Hiermee worden alle opdrachten voor actie-items en de uploadgeschiedenis van het document voor *de geselecteerde gebruiker verwijderd. Deze actie is permanent. Weet u zeker dat u wilt doorgaan?*"

2. Als u ok **wilt blijven selecteren,** selecteert u anders **Annuleren.**
