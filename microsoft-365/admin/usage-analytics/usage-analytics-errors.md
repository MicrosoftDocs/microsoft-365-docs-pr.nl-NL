---
title: Problemen oplossen voor Microsoft 365 Gebruiksanalyse
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
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
description: Meer informatie over het oplossen van problemen met de Sjabloon-app Microsoft 365 Usage Analytics.
ms.openlocfilehash: 7164aa246a79a8d8c5aa50d995b53b6221003c01
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212147"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Problemen oplossen voor Microsoft 365 Gebruiksanalyse

Raadpleeg de volgende lijst met foutmeldingen voor hulp bij de meest voorkomende problemen met het Microsoft 365 Gebruiksanalyse.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>De aanvraag kan niet worden verwerkt. U moet zich eerst abonneren op deze gegevens van het Microsoft 365-beheercentrum

 **Foutcode :** 422 
  
 **Waar u dit bericht ziet:** In Power BI wanneer u verbinding maakt met de Microsoft 365 Usage Analytics-sjabloon-app of wanneer u rechtstreeks de Microsoft 365 Reporting API's belt. 
  
 **Oorzaak:** Voordat u verbinding maken met de app, moet u zich abonneren op de gegevens van het Microsoft 365-beheercentrum. Als deze stap niet als eerste wordt uitgevoerd, u geen verbinding maken met de sjabloon-app, zelfs niet als u uw Microsoft 365-tenant-id opgeeft. 
  
 **Ga als volgt te werk om deze fout op te lossen:** Als u zich wilt abonneren op \> de gegevens, gaat u naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">beheercentrum</a> **Rapporten** \> Gebruik en zoek de Microsoft 365 usage analytics tegel op de hoofddashboard pagina. Selecteer de knop **Aan de slag** en schakel in het deelvenster **Rapporten** dat wordt geopend de **gebruiksanalyses voor Power BI beschikbaar maken voor Microsoft 365** in en **Opslaan**.
  
## <a name="we-are-processing-your-data"></a>Uw gegevens worden verwerkt

 **Waar u dit bericht ziet:** Ga naar de tegel **Microsoft 365-analysevan gebruik** op het **dashboard Gebruik** in het Microsoft 365-beheercentrum. 
  
 **Oorzaak:** Wanneer u zich aanschrijft voor het zien van [gegevens in de sjabloon-app](enable-usage-analytics.md) van het Microsoft 365-beheercentrum, begint het Microsoft 365-systeem met het genereren van historische gebruiksgegevens voor uw organisatie. Afhankelijk van de grootte van uw tenant kan dit 2 tot 48 uur duren. 
  
 **Om dit op te lossen:** Wees geduldig, maar als het bericht niet verandert in Uw gegevens na 3 dagen **klaar zijn,** neemt [u contact op met Microsoft 365 voor zakelijke ondersteuning.](../contact-support-for-business-products.md)
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>De aanvraag kan momenteel niet worden verwerkt. De gegevens voor uw organisatie worden nog voorbereid

 **Foutcode:** 423 
  
 **Waar u dit bericht ziet:** In Power BI wanneer u verbinding maakt met de Microsoft 365 Usage Analytics-sjabloon-app of wanneer u rechtstreeks de Microsoft 365 Reporting API's belt. 
  
 **Oorzaak:** Wanneer u zich aanschrijft voor het zien van [gegevens in de sjabloon-app](enable-usage-analytics.md) vanuit het beheercentrum, begint het Microsoft 365-systeem met het genereren van historische gebruiksgegevens voor uw organisatie. Afhankelijk van de grootte van uw tenant kan dit 2 tot 48 uur duren. 
  
 **Om dit op te lossen:** Wees geduldig, maar als het bericht niet verandert in **Uw gegevens is klaar,** zelfs 3 dagen sinds de initiatie, [contact opnemen met Microsoft 365 voor zakelijke ondersteuning](../contact-support-for-business-products.md).
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>De opgegeven tenant-id heeft niet de juiste indeling

 **Foutcode:** 400 
  
 **Waar u dit bericht ziet:** In Power BI wanneer u verbinding maakt met de Microsoft 365 Usage Analytics-sjabloon-app of wanneer u rechtstreeks de Microsoft 365 Reporting API's belt. 
  
 **Oorzaak:** de tenant-id is een GUID en moet de volgende indeling hebben: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. Als u een andere tekenreeks opgeeft in het invoervak, wordt deze fout weergegeven. 
  
 **Ga als volgt te werk om deze fout op te lossen:** Ga naar het \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">beheercentrum</a> **Rapporten** \> Gebruik en zoek de Microsoft 365 usage analytics tegel op de belangrijkste dashboard pagina. De tenant-id wordt vermeld op de tegel. U het vanaf hier kopiëren en plakken in het dialoogvenster voor verbinding maken met de sjabloon-app. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>De opgegeven tenant-id wordt niet herkend door het systeem

 **Foutcode:** 404 
  
 **Waar u dit bericht ziet:** In Power BI wanneer u verbinding maakt met de Microsoft 365 Usage Analytics-sjabloon-app of wanneer u rechtstreeks de Microsoft 365 Reporting API's belt. 
  
 **Oorzaak:** De tenant-id die u hebt opgegeven is niet geldig of bestaat niet. 
  
 **Ga als volgt te werk om deze fout op te lossen:** Ga naar het \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">beheercentrum</a> **Rapporten** \> Gebruik en zoek de Microsoft 365 usage analytics tegel op de belangrijkste dashboard pagina. De tenant-id wordt vermeld op de tegel. U het vanaf hier kopiëren en plakken in het dialoogvenster voor verbinding maken met de sjabloon-app. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Voer uw referenties nogmaals in om u opnieuw aan te melden bij Power BI

Foutcode: 302
  
 **Waar u dit bericht ziet:** In Power BI wanneer u verbinding maakt met de Microsoft 365 Usage Analytics-sjabloon-app of wanneer u rechtstreeks de Microsoft 365 Reporting API's belt. 
  
 **Oorzaak:** De autorisatie is mislukt en u moet uw referenties mogelijk opnieuw invoeren. 
  
 **Oplossing:** Meld u af en weer aan bij Power BI. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>U bent niet gemachtigd voor toegang tot deze gegevens. Om toegang te krijgen tot de gegevens van deze service moet u een globale beheerder of een van de productbeheerders zijn

 **Foutcode:** 403 
  
 **Waar u dit bericht ziet:** In Power BI wanneer u verbinding maakt met de Microsoft 365 Usage Analytics-sjabloon-app of wanneer u rechtstreeks de Microsoft 365 Reporting API's belt. 
  
 **Oorzaak:** De autorisatiecode is mislukt omdat de gebruiker die verbinding heeft gemaakt met de sjabloon-app niet het juiste machtigingsniveau heeft om toegang te krijgen tot deze gegevens. 
  
 **Ga als volgt te werk om deze fout op te lossen:** Geef de referenties op van een gebruiker die een **globale beheerder**is, **Exchange-beheerder,** **Skype voor Bedrijven-beheerder,** **SharePoint-beheerder,** **Globale lezer** of **Rapportlezer** om verbinding te maken met de sjabloon-app. Zie [Over beheerdersrollen](../add-users/about-admin-roles.md) voor meer informatie. 
  
## <a name="refresh-failed"></a>Vernieuwen mislukt

 **Waar wordt dit bericht weergegeven:** E-mail van Power BI of de status mislukt in de vernieuwingsgeschiedenis. 
  
 **Oorzaak:** Soms worden de referenties van de gebruiker die verbinding heeft gemaakt met de sjabloon-app opnieuw ingesteld en niet bijgewerkt in de verbindingsinstellingen van de sjabloon-app, waardoor de gebruiker fouten bij het vernieuwen te zien krijgt. 
  
 **Ga als volgt te werk om deze fout op te lossen:** Zoek in Power BI de gegevensset die overeenkomt met de sjabloon-app Microsoft 365 Usage Analytics, selecteer **vernieuwen plannen** en geef uw beheerdersreferenties op. 
  
Als dat niet werkt, moet u de cache wissen en de sjabloon-app opnieuw maken.
  
  
