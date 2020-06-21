---
title: Back-up van gegevens voordat u plannen wijzigt
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
description: Maak een back-up van Outlook-, OneDrive-, Yammer- en SharePoint-inhoud voordat u Microsoft 365-abonnementen wijzigt.
ms.openlocfilehash: 9acc97f65bb5b471cb992d7f01cd299192b74a52
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818529"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>Back-up van gegevens voordat u van Microsoft 365 overschakelt voor bedrijfsabonnementen

Als een gebruiker wordt overgeschakeld naar een ander abonnement dat minder gegevensgerelateerde services heeft of als een gebruiker de organisatie verlaat, kan een kopie van zijn gegevens die zijn opgeslagen in Microsoft 365 worden gedownload voordat deze worden overgeschakeld naar het nieuwe abonnement.
  
## <a name="save-a-copy-of-outlook-information"></a>Een kopie van Outlook-gegevens opslaan

Als gebruikers Outlook hebben, kunnen ze [e-mail, contactpersonen en agenda exporteren of back-upen naar een PST-bestand van Outlook](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) voordat hun abonnement wordt ingeschakeld.
  
Nadat de overschakeling naar het nieuwe abonnement is voltooid, kunnen gebruikers [e-mail, contactpersonen en agenda importeren uit een PST-bestand in Outlook](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac).
  
## <a name="save-files-stored-in-onedrive-for-business"></a>Bestanden opslaan die zijn opgeslagen in OneDrive voor Bedrijven

Voordat gebruikers worden overgeschakeld naar een ander abonnement, kunnen gebruikers [bestanden en mappen downloaden van OneDrive of SharePoint](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) naar een andere locatie, zoals een map op de harde schijf van hun computer of een bestandsshare in het netwerk van de organisatie.
  
## <a name="save-yammer-information"></a>Yammer-gegevens opslaan

Beheerders kunnen alle berichten, notities, bestanden, onderwerpen, gebruikers en groepen exporteren naar een ZIP-bestand. Zie [Gegevens exporteren uit Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data)voor meer informatie. Ontwikkelaars kunnen de [Yammer API](https://go.microsoft.com/fwlink/p/?linkid=842495) ook gebruiken om dit te doen.
  
## <a name="how-to-save-sharepoint-information"></a>SharePoint-gegevens opslaan

Als een gebruiker wordt overgeschakeld van een abonnement met SharePoint Online naar een abonnement dat het niet heeft, wordt de **SharePoint-tegel** niet meer weergegeven in het Microsoft 365-menu.
  
However, as long as the new subscription is within the same organization as the one they are switched from, users will still be able to access the SharePoint team site. They can view and update notebooks, documents, tasks, and calendars by using the direct URL to the team site.
  
> [!TIP]
> We adviseren gebruikers naar de teamsite te gaan voordat het abonnement wordt gewijzigd en de URL als een favoriet of bladwijzer in hun browser op te slaan.
  
De URL van de teamwebsite heeft standaard de volgende vorm:
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

waar _\<orgDomain\>_ is de URL van de organisatie.
  
Bijvoorbeeld, als het domein van de organisatie contoso.onmicrosoft.com is, dan is de rechtstreekse URL naar de teamsite https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx.
  
Gebruikers kunnen natuurlijk ook op elk gewenst moment SharePoint Online-documenten van de teamsite in SharePoint downloaden naar hun lokale computer of naar een andere locatie.