---
title: Problemen oplossen voor Microsoft 365 Gebruiksanalyse
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Meer informatie over het oplossen van problemen met de Microsoft 365 De sjabloon-app Gebruiksanalyse.
ms.openlocfilehash: 74ee32ae015421a2352474daefa0eaa0a53fbbc9
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52293733"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Problemen oplossen voor Microsoft 365 Gebruiksanalyse

Raadpleeg de volgende lijst met foutmeldingen voor hulp bij de meest voorkomende problemen met het Microsoft 365 Gebruiksanalyse.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>De aanvraag kan niet worden verwerkt. U moet zich eerst abonneren op deze gegevens vanuit het Microsoft 365 beheercentrum

 **Foutcode:** 422 
  
 **Waar ziet u dit bericht:** In Power BI wanneer u verbinding maakt met de Microsoft 365 De sjabloon-app Gebruiksanalyse of wanneer u rechtstreeks de Microsoft 365 Api's voor rapportage. 
  
 **Oorzaak:** Voordat u verbinding kunt maken met de app, moet u zich abonneren op de gegevens van het Microsoft 365 beheercentrum. Als deze stap niet eerst wordt uitgevoerd, kunt u geen verbinding maken met de sjabloon-app, zelfs niet als u uw tenant-id Microsoft 365 toevoegen. 
  
 **Deze fout oplossen:** Als u zich wilt abonneren op de gegevens, gaat u naar het beheercentrum Rapportengebruik en zoekt u de Microsoft 365 de tegel Gebruiksanalyse \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> op de pagina met het hoofddashboard. Selecteer de **knop Aan** de  slag en schakel in het deelvenster Rapporten dat wordt geopend de optie Gegevens beschikbaar maken voor Microsoft 365 **gebruiksanalyse** voor Power BI instelling in en **Opslaan.**
  
## <a name="we-are-processing-your-data"></a>Uw gegevens worden verwerkt

 **Waar ziet u dit bericht:** In de **Microsoft 365 de tegel Gebruiksanalyse** op het dashboard **Gebruik** in het Microsoft 365 beheercentrum. 
  
 **Oorzaak:** Wanneer u [ervoor kiest om](enable-usage-analytics.md) gegevens in de sjabloon-app te zien vanuit het Microsoft 365-beheercentrum, begint het Microsoft 365 met het genereren van historische gebruiksgegevens voor uw organisatie. Afhankelijk van de grootte van uw tenant kan dit 2 tot 48 uur duren. 
  
 **U kunt dit als volgende oplossen:** Wees geduldig, maar als het bericht  na 3 dagen nog niet is gewijzigd in Uw gegevens, neemt u [contact op met Microsoft 365 ondersteuning voor bedrijven.](../../business-video/get-help-support.md)
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>De aanvraag kan momenteel niet worden verwerkt. De gegevens voor uw organisatie worden nog voorbereid

 **Foutcode:** 423 
  
 **Waar ziet u dit bericht:** In Power BI, wanneer u verbinding maakt met de Microsoft 365 De sjabloon-app Gebruiksanalyse of wanneer u rechtstreeks de app Reporting API's Microsoft 365 bellen. 
  
 **Oorzaak:** Wanneer u [ervoor kiest om](enable-usage-analytics.md) gegevens in de sjabloon-app te zien vanuit het beheercentrum, begint het Microsoft 365 met het genereren van historische gebruiksgegevens voor uw organisatie. Afhankelijk van de grootte van uw tenant, kan deze stap tussen twee uur en 48 uur duren. 
  
 **U kunt dit als volgende oplossen:** Wees geduldig, maar als het bericht niet wordt gewijzigd in Uw gegevens **is** zelfs 3 dagen na de initiatie gereed, neemt u [contact op met Microsoft 365 voor zakelijke ondersteuning.](../../business-video/get-help-support.md)
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>De opgegeven tenant-id heeft niet de juiste indeling

 **Foutcode:** 400 
  
 **Waar ziet u dit bericht:** In Power BI, wanneer u verbinding maakt met de Microsoft 365 De sjabloon-app Gebruiksanalyse of wanneer u rechtstreeks de app Reporting API's Microsoft 365 bellen. 
  
 **Oorzaak:** De tenant-id is een guid en moet de indeling xxxxxxxx-xxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx hebben. Als u een andere tekenreeks in het invoervak van de tenant invoert, krijgt u deze foutmelding. 
  
 **Deze fout oplossen:** Ga naar het beheercentrum Rapportengebruik en zoek de Microsoft 365 de tegel \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Gebruiksanalyse op de pagina met het hoofddashboard. De tenant-id wordt weergegeven op de tegel. U kunt het hier kopiëren en plakken in het dialoogvenster om verbinding te maken met de sjabloon-app. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>De opgegeven tenant-id wordt niet herkend door het systeem

 **Foutcode:** 404 
  
 **Waar ziet u dit bericht:** In Power BI wanneer u verbinding maakt met de Microsoft 365 De sjabloon-app Gebruiksanalyse of wanneer u rechtstreeks de Microsoft 365 Api's voor rapportage. 
  
 **Oorzaak:** De tenant-id die u hebt opgegeven, is niet geldig of bestaat niet. 
  
 **Deze fout oplossen:** Ga naar het beheercentrum Rapportengebruik en zoek de Microsoft 365 de tegel \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Gebruiksanalyse op de pagina met het hoofddashboard. De tenant-id wordt weergegeven op de tegel. U kunt het hier kopiëren en plakken in het dialoogvenster om verbinding te maken met de sjabloon-app. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Voer uw referenties nogmaals in om u opnieuw aan te melden bij Power BI

Foutcode: 302
  
 **Waar ziet u dit bericht:** In Power BI wanneer u verbinding maakt met de Microsoft 365 De sjabloon-app Gebruiksanalyse of wanneer u rechtstreeks de Microsoft 365 Api's voor rapportage. 
  
 **Oorzaak:** De autorisatie is mislukt en u moet uw referenties mogelijk opnieuw invoeren. 
  
 **Oplossing:** Meld u af en weer aan bij Power BI. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>U bent niet gemachtigd voor toegang tot deze gegevens. Om toegang te krijgen tot de gegevens van deze service moet u een globale beheerder of een van de productbeheerders zijn

 **Foutcode:** 403 
  
 **Waar ziet u dit bericht:** In Power BI wanneer u verbinding maakt met de Microsoft 365 De sjabloon-app Gebruiksanalyse of wanneer u rechtstreeks de Microsoft 365 Api's voor rapportage. 
  
 **Oorzaak:** De autorisatiecode is mislukt omdat de gebruiker die verbinding heeft gemaakt met de sjabloon-app niet over het juiste machtigingsniveau voor toegang tot deze gegevens heeft. 
  
 **Deze fout oplossen:** Geef de referenties op van een gebruiker die een globale **beheerder, Exchange-beheerder,**  **Skype voor Bedrijven-beheerder,** **SharePoint-beheerder,** **globale** lezer of rapportlezer is om verbinding te maken met de sjabloon-app. Zie [Beheerdersrollen voor](../add-users/about-admin-roles.md) meer informatie. 
  
## <a name="refresh-failed"></a>Vernieuwen mislukt

 **Waar wordt dit bericht weergegeven:** E-mail van Power BI of de status mislukt in de vernieuwingsgeschiedenis. 
  
 **Oorzaak:** Soms worden de referenties van de gebruiker die verbinding heeft gemaakt met de sjabloon-app opnieuw ingesteld en niet bijgewerkt in de verbindingsinstellingen van de sjabloon-app, waardoor de gebruiker foutfouten bij vernieuwen ziet. 
  
 **Deze fout oplossen:** Zoek Power BI gegevensset die overeenkomt met de Microsoft 365 app Gebruiksanalyse, selecteer vernieuwen plannen en geef uw beheerdersreferenties op.  
  
Als dat niet werkt, moet u de cache wissen en de sjabloon-app opnieuw maken.
  
  
