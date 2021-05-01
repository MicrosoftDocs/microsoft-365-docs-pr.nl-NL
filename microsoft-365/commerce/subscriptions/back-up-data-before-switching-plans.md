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
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
- PPM_jmueller
ms.reviewer: jkinma
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Back-Outlook, OneDrive, Yammer en SharePoint voordat u de Microsoft 365 wijzigen.
ms.date: 03/17/2021
ms.openlocfilehash: cdbeb7267105742082358dcd985e8fd1052a5679
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107422"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>Een back-up maken van gegevens voordat Microsoft 365 voor bedrijven-abonnementen

Als een gebruiker wordt overgeschakeld naar een ander abonnement dat minder gegevensgerelateerde services heeft of als een gebruiker de organisatie verlaat, kan een kopie van de gegevens die zijn opgeslagen in Microsoft 365 worden gedownload voordat hij of zij overschakelt naar het nieuwe abonnement.

Als u een gebruiker verplaatst naar een abonnement dat dezelfde of meer services heeft, hoeft u geen back-up te maken van gebruikersgegevens. Zie [Gebruikers verplaatsen naar een ander abonnement.](./move-users-different-subscription.md)
  
## <a name="save-a-copy-of-outlook-information"></a>Een kopie van de Outlook opslaan

Als gebruikers Outlook hebben, kunnen ze e-mail, contactpersonen en agenda exporteren of back-up maken naar een Outlook [PST-bestand](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) voordat hun abonnement wordt overgeschakeld.
  
Nadat de overstap naar het nieuwe abonnement is voltooid, kunnen gebruikers e-mail, contactpersonen en agenda importeren uit een [Outlook PST-bestand.](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)
  
## <a name="save-files-stored-in-onedrive-for-business"></a>Bestanden opslaan die zijn opgeslagen in OneDrive voor Bedrijven

Voordat gebruikers worden overgeschakeld naar een ander abonnement, kunnen gebruikers bestanden en mappen downloaden van OneDrive of SharePoint naar een andere locatie, zoals een map op de harde schijf van hun computer of een [bestands](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) delen in het netwerk van de organisatie.
  
## <a name="save-yammer-information"></a>Gegevens Yammer opslaan

Beheerders kunnen alle berichten, notities, bestanden, onderwerpen, gebruikers en groepen exporteren naar een ZIP-bestand. Zie Gegevens exporteren van [Yammer Enterprise.](/yammer/manage-security-and-compliance/export-yammer-enterprise-data) Ontwikkelaars kunnen de [Yammer API](https://go.microsoft.com/fwlink/p/?linkid=842495) ook gebruiken om dit te doen.
  
## <a name="how-to-save-sharepoint-information"></a>SharePoint-gegevens opslaan

Als een gebruiker is overgeschakeld van een abonnement dat SharePoint Online heeft naar een abonnement dat deze niet heeft, wordt de **tegel SharePoint** niet meer weergegeven in het Microsoft 365 menu.
  
Als het nieuwe abonnement zich echter binnen dezelfde organisatie bevindt als het vorige abonnement, hebben gebruikers nog steeds toegang tot de teamsite van SharePoint. Ze kunnen notitieblokken, documenten, taken en agenda's bekijken en bijwerken via de rechtstreekse URL naar de teamsite.
  
> [!TIP]
> We adviseren gebruikers naar de teamsite te gaan voordat het abonnement wordt gewijzigd en de URL als een favoriet of bladwijzer in hun browser op te slaan.
  
De URL van de teamwebsite heeft standaard de volgende vorm:
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

waar  _\<orgDomain\>_ is de URL van de organisatie.
  
Bijvoorbeeld, als het domein van de organisatie contoso.onmicrosoft.com is, dan is de rechtstreekse URL naar de teamsite `https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx`.
  
Gebruikers kunnen natuurlijk ook op elk gewenst moment SharePoint Online-documenten van de teamsite in SharePoint downloaden naar hun lokale computer of naar een andere locatie.