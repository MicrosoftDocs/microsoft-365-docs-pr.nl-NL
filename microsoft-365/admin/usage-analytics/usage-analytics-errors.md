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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Informatie over het oplossen van problemen met de app Microsoft 365 gebruiksanalyse.
ms.openlocfilehash: bf8e4ece7b1e310d91f418f5388cae9aa27f2aa7
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841433"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Problemen oplossen voor Microsoft 365 Gebruiksanalyse

Raadpleeg de volgende lijst met foutmeldingen voor hulp bij de meest voorkomende problemen met het Microsoft 365 Gebruiksanalyse.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>De aanvraag kan niet worden verwerkt. U moet eerst een abonnement op deze gegevens opzeggen via het Microsoft 365-Beheercentrum

 **Fout code:** 422 
  
 **Waar wordt dit bericht weergegeven:** In Power BI wanneer u verbinding maakt met de sjabloon app Microsoft 365 gebruiksanalyse of wanneer u de Microsoft 365-rapportage-Api's direct aanroept. 
  
 **Oorzaak:** Voordat u verbinding kunt maken met de app, moet u zich abonneren op de gegevens in het Microsoft 365-Beheercentrum. Als u deze stap niet eerst kunt voltooien, kunt u geen verbinding maken met de sjabloon-app, zelfs niet als u uw Microsoft 365-Tenant-ID opgeeft. 
  
 **Oplossing voor deze fout:** Als u zich wilt abonneren op de gegevens, gaat u naar het Beheercentrum \> **rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> en zoekt u de tegel Microsoft 365 gebruiksanalyse op de hoofdpagina van het dashboard. Selecteer de knop **aan de slag** en klik in het deelvenster **rapporten** dat wordt geopend, de optie **gegevens beschikbaar maken voor Microsoft 365 Usage Analytics voor Power bi** instellen en **Opslaan** .
  
## <a name="we-are-processing-your-data"></a>Uw gegevens worden verwerkt

 **Waar wordt dit bericht weergegeven:** In de tegel **Microsoft 365 gebruiksanalyse** in het dashboard **gebruik** in het Microsoft 365-Beheercentrum. 
  
 **Oorzaak:** Wanneer u [zich aanmeldt om gegevens te zien in de sjabloon-app](enable-usage-analytics.md) van het microsoft 365-Beheercentrum, begint het microsoft 365-systeem met het genereren van historische gebruiksgegevens voor uw organisatie. Afhankelijk van de grootte van uw tenant kan dit 2 tot 48 uur duren. 
  
 **Oplossing:** Even geduld, maar als het bericht na 3 dagen nog niet **is veranderd in uw gegevens** , kunt u [contact opnemen met de ondersteuning van Microsoft 365 voor bedrijven](../contact-support-for-business-products.md).
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>De aanvraag kan momenteel niet worden verwerkt. De gegevens voor uw organisatie worden nog voorbereid

 **Foutcode:** 423 
  
 **Waar wordt dit bericht weergegeven:** In Power BI, wanneer u verbinding maakt met de app Microsoft 365 gebruiksanalyse of wanneer u de Microsoft 365-rapportage-Api's direct aanroept. 
  
 **Oorzaak:** Wanneer u [zich aanmeldt om gegevens in de sjabloon-app te zien](enable-usage-analytics.md) vanuit het Beheercentrum, wordt 365 er begonnen met het genereren van historische gebruiksgegevens voor uw organisatie. Afhankelijk van de grootte van de Tenant, kan deze stap twee uur tot 48 uur duren. 
  
 **Oplossing:** Maar als het bericht nog niet is veranderd in **uw gegevens zijn gereed** , [neemt u contact op met de ondersteuning van Microsoft 365 voor bedrijven](../contact-support-for-business-products.md).
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>De opgegeven tenant-id heeft niet de juiste indeling

 **Foutcode:** 400 
  
 **Waar wordt dit bericht weergegeven:** In Power BI, wanneer u verbinding maakt met de app Microsoft 365 gebruiksanalyse of wanneer u de Microsoft 365-rapportage-Api's direct aanroept. 
  
 **Oorzaak:** De Tenant-ID is een GUID en moet de indeling XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX hebben. Als u een andere tekenreeks opgeeft in het invoervak van de Tenant, krijgt u deze fout. 
  
 **Oplossing voor deze fout:** Ga naar het Beheercentrum \> **rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> en zoek de tegel Microsoft 365 Usage Analytics op de hoofdpagina van het dashboard. De Tenant-ID wordt weergegeven op de tegel. U kunt het hierheen kopiëren en plakken in het dialoogvenster voor het maken van verbinding met de sjabloon-app. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>De opgegeven tenant-id wordt niet herkend door het systeem

 **Foutcode:** 404 
  
 **Waar wordt dit bericht weergegeven:** In Power BI wanneer u verbinding maakt met de sjabloon app Microsoft 365 gebruiksanalyse of wanneer u de Microsoft 365-rapportage-Api's direct aanroept. 
  
 **Oorzaak:** De opgegeven Tenant-ID is niet geldig of bestaat niet. 
  
 **Oplossing voor deze fout:** Ga naar het Beheercentrum \> **rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> en zoek de tegel Microsoft 365 Usage Analytics op de hoofdpagina van het dashboard. De Tenant-ID wordt weergegeven op de tegel. U kunt het hierheen kopiëren en plakken in het dialoogvenster voor het maken van verbinding met de sjabloon-app. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Voer uw referenties nogmaals in om u opnieuw aan te melden bij Power BI

Foutcode: 302
  
 **Waar wordt dit bericht weergegeven:** In Power BI wanneer u verbinding maakt met de sjabloon app Microsoft 365 gebruiksanalyse of wanneer u de Microsoft 365-rapportage-Api's direct aanroept. 
  
 **Oorzaak:** De autorisatie is mislukt en u moet uw referenties mogelijk opnieuw invoeren. 
  
 **Oplossing:** Meld u af en weer aan bij Power BI. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>U bent niet gemachtigd voor toegang tot deze gegevens. Om toegang te krijgen tot de gegevens van deze service moet u een globale beheerder of een van de productbeheerders zijn

 **Foutcode:** 403 
  
 **Waar wordt dit bericht weergegeven:** In Power BI wanneer u verbinding maakt met de sjabloon app Microsoft 365 gebruiksanalyse of wanneer u de Microsoft 365-rapportage-Api's direct aanroept. 
  
 **Oorzaak:** De autorisatiecode is mislukt omdat de gebruiker die probeerde verbinding te maken met de sjabloon-app niet over het juiste machtigingsniveau beschikt voor toegang tot deze gegevens. 
  
 **Oplossing voor deze fout:** Voer de referenties in van een gebruiker die een **globale beheerder** , **Exchange-beheerder** , **Skype voor bedrijven-beheerder** , **SharePoint-beheerder** , **algemene lezer** of **rapportlezer** is om verbinding te maken met de sjabloon-app. Zie [informatie over beheerdersrollen](../add-users/about-admin-roles.md) voor meer informatie. 
  
## <a name="refresh-failed"></a>Vernieuwen mislukt

 **Waar wordt dit bericht weergegeven:** E-mail van Power BI of de status mislukt in de vernieuwingsgeschiedenis. 
  
 **Oorzaak:** Soms worden de referenties van de gebruiker die verbonden zijn met de sjabloon-app opnieuw ingesteld en niet bijgewerkt in de verbindingsinstellingen van de sjabloon-app, zodat de gebruiker foutberichten vernieuwt. 
  
 **Oplossing voor deze fout:** Zoek in Power BI naar de gegevensset die hoort bij de app Microsoft 365 Usage Analytics-App, selecteer **vernieuwen plannen** en geef uw beheerdersreferenties op. 
  
Als dat niet werkt, wist u de cache en maakt u de sjabloon-app opnieuw.
  
  
