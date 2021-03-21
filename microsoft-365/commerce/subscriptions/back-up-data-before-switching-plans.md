---
title: Een back-up maken van gegevens voordat u van plan verandert
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: a1da52c9-2167-4973-9e6d-492314a79b87
description: Back-up maken van Outlook-, OneDrive-, Yammer- en SharePoint-inhoud voordat u Microsoft 365-abonnementen verandert.
ms.openlocfilehash: d29d4e739a9328a63a491696ba26bee5b1947f0a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924058"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>Een back-up maken van gegevens voordat u overschakelt naar Microsoft 365 voor Bedrijven-abonnementen

Als een gebruiker wordt overgeschakeld naar een ander abonnement dat minder gegevensgerelateerde services heeft of als een gebruiker de organisatie verlaat, kan een kopie van de gegevens die zijn opgeslagen in Microsoft 365, worden gedownload voordat hij of zij overschakelt naar het nieuwe abonnement.

Als u een gebruiker verplaatst naar een abonnement dat dezelfde of meer services heeft, hoeft u geen back-up te maken van gebruikersgegevens. Zie [Gebruikers verplaatsen naar een ander abonnement.](./move-users-different-subscription.md)
  
## <a name="save-a-copy-of-outlook-information"></a>Een kopie van Outlook-gegevens opslaan

Als gebruikers Outlook hebben, kunnen ze [e-mail,](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) contactpersonen en agenda exporteren of back-up maken naar een PST-bestand van Outlook voordat hun abonnement wordt overgeschakeld.
  
Nadat de overstap naar het nieuwe abonnement is voltooid, kunnen gebruikers e-mail, contactpersonen en agenda importeren [uit een PST-bestand](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)van Outlook.
  
## <a name="save-files-stored-in-onedrive-for-business"></a>Bestanden opslaan die zijn opgeslagen in OneDrive voor Bedrijven

Voordat gebruikers worden overgeschakeld naar een ander abonnement, kunnen gebruikers bestanden en mappen downloaden van OneDrive of SharePoint naar een andere locatie, zoals een map op de harde schijf van hun computer of een [bestands](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) delen in het netwerk van de organisatie.
  
## <a name="save-yammer-information"></a>Yammer-gegevens opslaan

Beheerders kunnen alle berichten, notities, bestanden, onderwerpen, gebruikers en groepen exporteren naar een ZIP-bestand. Zie Gegevens exporteren [vanuit Yammer Enterprise](/yammer/manage-security-and-compliance/export-yammer-enterprise-data)voor meer informatie. Ontwikkelaars kunnen hiervoor ook [de Yammer-API](https://go.microsoft.com/fwlink/p/?linkid=842495) gebruiken.
  
## <a name="how-to-save-sharepoint-information"></a>SharePoint-gegevens opslaan

Als een gebruiker is overgeschakeld van een abonnement met SharePoint Online naar een abonnement dat deze niet heeft, wordt de **SharePoint-tegel** niet meer weergegeven in het Microsoft 365-menu.
  
Als het nieuwe abonnement zich echter binnen dezelfde organisatie bevindt als het vorige abonnement, hebben gebruikers nog steeds toegang tot de teamsite van SharePoint. Ze kunnen notitieblokken, documenten, taken en agenda's bekijken en bijwerken via de rechtstreekse URL naar de teamsite.
  
> [!TIP]
> We adviseren gebruikers naar de teamsite te gaan voordat het abonnement wordt gewijzigd en de URL als een favoriet of bladwijzer in hun browser op te slaan.
  
De URL van de teamwebsite heeft standaard de volgende vorm:
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

waar  _\<orgDomain\>_ is de URL van de organisatie.
  
Bijvoorbeeld, als het domein van de organisatie contoso.onmicrosoft.com is, dan is de rechtstreekse URL naar de teamsite https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx.
  
Gebruikers kunnen natuurlijk ook op elk gewenst moment SharePoint Online-documenten van de teamsite in SharePoint downloaden naar hun lokale computer of naar een andere locatie.