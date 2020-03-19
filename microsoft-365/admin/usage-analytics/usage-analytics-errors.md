---
title: Problemen oplossen voor Microsoft 365 Gebruiksanalyse
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Meer informatie over het oplossen van problemen met de sjabloon-app Microsoft 365 Usage Analytics.
ms.openlocfilehash: a9da79a6d7760f7876de7a6321554545d411f6be
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42806177"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Problemen oplossen voor Microsoft 365 Gebruiksanalyse

Raadpleeg de volgende lijst met foutmeldingen voor hulp bij de meest voorkomende problemen met het Microsoft 365 Gebruiksanalyse.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>De aanvraag kan niet worden verwerkt. U moet zich eerst abonneren op deze gegevens van het Microsoft 365-beheercentrum

 **Foutcode :** 422 
  
 **Waar u dit bericht te zien krijgt:** In Power BI wanneer u verbinding maakt met de microsoft 365-sjabloonapp Voor gebruiksanalyse of wanneer u rechtstreeks de Microsoft 365 Reporting API's belt. 
  
 **Oorzaak:** Voordat u verbinding maken met de app, moet u zich abonneren op de gegevens van het Microsoft 365-beheercentrum. Als deze stap niet eerst wordt uitgevoerd, u geen verbinding maken met de sjabloon-app, zelfs niet als u uw Microsoft 365-tenant-id opgeeft. 
  
 **Ga als volgt te werk om deze fout op te lossen:** Als u zich wilt abonneren op \> de gegevens, gaat u naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">beheercentrum</a> **Rapporten** \> Gebruik en zoekt u de tegel Microsoft 365-gebruiksanalyse op de hoofdpagina van het dashboard. Selecteer de knop **Aan de slag** en schakel vervolgens in het deelvenster **Rapporten** dat wordt geopend de **gebruiksanalyses voor Microsoft 365 beschikbaar** maken voor Power BI-instelling op en **Opslaan**.
  
## <a name="we-are-processing-your-data"></a>Uw gegevens worden verwerkt

 **Waar u dit bericht te zien krijgt:** In de tegel **Gebruiksanalyse van Microsoft 365** op het dashboard **Gebruik** in het Microsoft 365-beheercentrum. 
  
 **Oorzaak:** Wanneer u zich inschrijft voor het zien van [gegevens in de sjabloon-app](enable-usage-analytics.md) van het Microsoft 365-beheercentrum, begint het Microsoft 365-systeem historische gebruiksgegevens voor uw organisatie te genereren. Afhankelijk van de grootte van uw tenant kan dit 2 tot 48 uur duren. 
  
 **Ga als volgt te werk:** Wees geduldig, maar als het bericht niet wordt gewijzigd in **uw gegevens is klaar** na 3 dagen, neem dan contact op met Microsoft [365 voor zakelijke ondersteuning](../contact-support-for-business-products.md).
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>De aanvraag kan momenteel niet worden verwerkt. De gegevens voor uw organisatie worden nog voorbereid

 **Foutcode:** 423 
  
 **Waar u dit bericht te zien krijgt:** In Power BI wanneer u verbinding maakt met de microsoft 365-sjabloonapp Voor gebruiksanalyse of wanneer u rechtstreeks de Microsoft 365 Reporting API's belt. 
  
 **Oorzaak:** Wanneer u zich inschrijft voor het zien van [gegevens in de sjabloon-app](enable-usage-analytics.md) van het beheercentrum, begint het Microsoft 365-systeem historische gebruiksgegevens voor uw organisatie te genereren. Afhankelijk van de grootte van uw tenant kan dit 2 tot 48 uur duren. 
  
 **Ga als volgt te werk:** Wees geduldig, maar als het bericht niet verandert in **uw gegevens is klaar,** zelfs 3 dagen sinds de initiatie, [contact opnemen met Microsoft 365 voor zakelijke ondersteuning](../contact-support-for-business-products.md).
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>De opgegeven tenant-id heeft niet de juiste indeling

 **Foutcode:** 400 
  
 **Waar u dit bericht te zien krijgt:** In Power BI wanneer u verbinding maakt met de microsoft 365-sjabloonapp Voor gebruiksanalyse of wanneer u rechtstreeks de Microsoft 365 Reporting API's belt. 
  
 **Oorzaak:** de tenant-id is een GUID en moet de volgende indeling hebben: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. Als u een andere tekenreeks opgeeft in het invoervak, wordt deze fout weergegeven. 
  
 **Ga als volgt te werk om deze fout op te lossen:** Ga naar het \> beheercentrum **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a> en zoek de Microsoft 365-gebruiksanalysetegel op de hoofdpagina van het dashboard. De tenant-id wordt vermeld op de tegel. U het vanaf hier kopiëren en in het dialoogvenster plakken om verbinding te maken met de sjabloon-app. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>De opgegeven tenant-id wordt niet herkend door het systeem

 **Foutcode:** 404 
  
 **Waar u dit bericht te zien krijgt:** In Power BI wanneer u verbinding maakt met de microsoft 365-sjabloonapp Voor gebruiksanalyse of wanneer u rechtstreeks de Microsoft 365 Reporting API's belt. 
  
 **Oorzaak:** De tenant-id die u hebt opgegeven is niet geldig of bestaat niet. 
  
 **Ga als volgt te werk om deze fout op te lossen:** Ga naar het \> beheercentrum **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a> en zoek de Microsoft 365-gebruiksanalysetegel op de hoofdpagina van het dashboard. De tenant-id wordt vermeld op de tegel. U het vanaf hier kopiëren en in het dialoogvenster plakken om verbinding te maken met de sjabloon-app. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Voer uw referenties nogmaals in om u opnieuw aan te melden bij Power BI

Foutcode: 302
  
 **Waar u dit bericht te zien krijgt:** In Power BI wanneer u verbinding maakt met de microsoft 365-sjabloonapp Voor gebruiksanalyse of wanneer u rechtstreeks de Microsoft 365 Reporting API's belt. 
  
 **Oorzaak:** De autorisatie is mislukt en u moet uw referenties mogelijk opnieuw invoeren. 
  
 **Oplossing:** Meld u af en weer aan bij Power BI. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>U bent niet gemachtigd voor toegang tot deze gegevens. Om toegang te krijgen tot de gegevens van deze service moet u een globale beheerder of een van de productbeheerders zijn

 **Foutcode:** 403 
  
 **Waar u dit bericht te zien krijgt:** In Power BI wanneer u verbinding maakt met de microsoft 365-sjabloonapp Voor gebruiksanalyse of wanneer u rechtstreeks de Microsoft 365 Reporting API's belt. 
  
 **Oorzaak:** De autorisatiecode is mislukt omdat de gebruiker die verbinding heeft gemaakt met de sjabloon-app niet het juiste niveau van autorisatie heeft om toegang te krijgen tot deze gegevens. 
  
 **Ga als volgt te werk om deze fout op te lossen:** Geef de referenties op van een gebruiker die een **globale beheerder**, **Exchange-beheerder**, **Skype voor Bedrijven-beheerder,** **SharePoint-beheerder,** **Globale lezer** of **Rapportlezer** is om verbinding te maken met de sjabloon-app. Zie [Informatie over beheerdersrollen](../add-users/about-admin-roles.md) voor meer informatie. 
  
## <a name="refresh-failed"></a>Vernieuwen mislukt

 **Waar wordt dit bericht weergegeven:** E-mail van Power BI of de status mislukt in de vernieuwingsgeschiedenis. 
  
 **Oorzaak:** Soms worden de referenties van de gebruiker die verbinding heeft gemaakt met de sjabloon-app opnieuw ingesteld en niet bijgewerkt in de verbindingsinstellingen van de sjabloon-app waardoor de gebruiker vernieuwingsfouten ziet. 
  
 **Ga als volgt te werk om deze fout op te lossen:** Zoek in Power BI de gegevensset die overeenkomt met de sjabloon-app Microsoft 365 Usage Analytics, selecteer **vernieuwen plannen** en geef uw beheerdersreferenties op. 
  
Als dat niet werkt, wist u de cache en maakt u de sjabloon-app opnieuw.
  
  
