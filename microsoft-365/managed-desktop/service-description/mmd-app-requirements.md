---
title: Vereisten voor Microsoft Managed Desktop-apps
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5889a4e80f44349b4f149ee4f2a631f12b32251e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637850"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Vereisten voor Microsoft Managed Desktop-apps

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
Om de prestaties, betrouwbaarheid en bruikbaarheid van Microsoft Managed Desktop-apparaten te garanderen, mag de zakelijke app van een klant geen ernstige invloed hebben op de gebruikerservaring of de beveiligingshouding wijzigen. Daarom moeten de zakelijke toepassingen die u wilt implementeren naar Microsoft Managed Desktop-apparaten voldoen aan de vereisten in dit onderwerp.

## <a name="application-condition"></a>Toepassingsvoorwaarde

Het is belangrijk dat toepassingen geen negatieve invloed hebben op de Microsoft Managed Desktop-omgeving. Hieronder volgen de vereisten waaraan een toepassing moet voldoen om een toepassing te kunnen implementeren. Voor een bepaalde toepassing of stuurprogramma kan Microsoft afzien van de hierin vermelde eis. Microsoft kan besluiten om een toepassing of stuurprogramma te verwijderen die een negatieve invloed heeft op de prestaties en betrouwbaarheid van Microsoft Managed Desktop-apparaten.

## <a name="centrally-managed-apps"></a>Centraal beheerde apps

Alle toepassingen en stuurprogramma's die op Microsoft Managed Devices zijn geïnstalleerd, moeten worden geïmplementeerd via Microsoft Intune, de Microsoft Store of de Microsoft Store voor Bedrijven. indien beschikbaar, worden stuurprogramma's ook geïmplementeerd via de Windows Update-service. 

## <a name="prohibited-app-classes"></a>Verboden app-lessen

Bepaalde toepassingstypen zijn niet toegestaan op Microsoft Managed Desktop-apparaten:
- Anti-virus-, beveiligings- of auditsoftware van derden
- Versies van Microsoft Office voorafgaand aan Microsoft 365 Apps voor bedrijven
- Toepassingen die andere software van derden installeren of bundelen

## <a name="restricted-app-behaviors"></a>Beperkt app-gedrag

Bepaalde app-gedragkan een negatieve invloed hebben op de gebruikerservaring of een beveiligingsrisico vormen voor Microsoft Managed Desktop-apparaten. Apps met het volgende gedrag mogen niet worden uitgevoerd in de Microsoft Managed Desktop-omgeving zonder een specifieke van Microsoft.

Gebruikerservaring:
- Achtergrondservices installeren
- Zichzelf toevoegen aan het opstartpad van Windows
- Toepassingen die afhankelijk zijn van stuurprogramma's
- Webbrowsers van derden

Beveiliging:
- De bevoegdheden van de eindgebruiker verhogen
- Fungeren als app store of een ingebouwde extensiemanager
- Hebben bekende beveiligingsproblemen
- Toegang tot gegevens van eindgebruikers versleutelen of beperken
- Is niet ondertekend of is ondertekend met behulp van een certificaat dat niet wordt oprollen naar een vertrouwde root


## <a name="driver-deployment"></a>Stuurprogramma-implementatie

Microsoft Managed Desktop ondersteunt alleen apparaatstuurprogramma's die beschikbaar zijn via Windows Update of geïnstalleerdpostvak met het Microsoft Managed Device. 

Als een toepassing vereist dat een specifiek stuurprogramma(s) wordt uitgevoerd, wordt dit beschouwd als een beperkte toepassing en is een uitzondering vereist voordat deze wordt geïmplementeerd op Microsoft Managed Desktop. 

