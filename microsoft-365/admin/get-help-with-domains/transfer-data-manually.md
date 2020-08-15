---
title: Gegevens handmatig overbrengen tussen twee accounts
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: Meer informatie over het handmatig overzetten van gegevens tussen twee Microsoft 365-accounts wanneer u de naam van het abonnement of de bedrijfsnaam wijzigt of meerdere abonnementen combineert.
ms.openlocfilehash: 91ea4140f0460e1f8cc1243f1b5f203738dcc9ee
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685508"
---
# <a name="transfer-data-manually-between-two-accounts"></a>Gegevens handmatig overbrengen tussen twee accounts

Voorbereidingen treffen voor het samenstellen van uw mof en een deel van de tijd in uw agenda blokkeren: gegevens overbrengen tussen twee Microsoft 365-accounts is een handmatig, ingewikkeld en tijdrovend proces. Het betreft hier trouwens een proces dat niet wordt ondersteund. We zullen u wel op weg helpen.
  
> [!CAUTION]
> Tijdens het proces is het niet mogelijk om e-mail, Skype voor bedrijven en een openbare website gehost op Microsoft 365. Gebruikers krijgen nieuwe gebruikersnamen en wachtwoorden, en ze moeten Outlook opnieuw instellen.

**In de volgende gevallen mag u gegevens alleen handmatig overbrengen volgens de instructies in dit onderwerp:**
  
- U moet overstappen op een abonnement in een andere servicefamilie.

- De naam van uw bedrijf is gewijzigd en u hebt besloten om een nieuw abonnement te nemen en uw gegevens te migreren omdat u domeinnamen wilt gebruiken die de nieuwe bedrijfsnaam bevatten.

- U moet meerdere abonnementen in één nieuw abonnement samenvoegen.

> [!IMPORTANT]
> Als u [van abonnement moet veranderen](../../commerce/subscriptions/switch-to-a-different-plan.md) en u de wizard Veranderen van abonnement kunt gebruiken, hoeft u de gegevens niet handmatig over te brengen en worden services niet onderbroken. Dit is ook zo als u gegevens moet overbrengen naar een nieuw abonnement in dezelfde abonnementsfamilie en de wizard Veranderen van abonnement niet werkt.

|**Taken**|**Stappen**|
|:-----|:-----|
|Koop het abonnement waarop u wilt overstappen.  <br/> |Tijdens de registratie geeft u aan welke bedrijfsnaam u wilt gebruiken in de domeinnamen die standaard worden gemaakt:  *uwbedrijf*  .onmicrosoft.com,  *uwbedrijf*  -public.sharepoint.com en  *uwbedrijf*  .sharepoint.com. U moet voor  *uwbedrijf*  een andere naam gebruiken dan voor bestaande abonnementen.  <br/> > [!NOTE]>  Nadat u een abonnement hebt opgezegd, duurt het meestal minimaal een paar maanden voordat de namen van de standaarddomeinen met  *uwbedrijf*  van het opgezegde abonnement worden vrijgegeven in onze systemen. Zelfs als u van plan bent om al uw gegevens op te slaan vanuit uw oude Microsoft 365-abonnement en het abonnement te annuleren, is de oude  *yourcompany*  waarde niet direct beschikbaar voor gebruik in een nieuw abonnement.           |
|Verwijder uw aangepaste domein uit uw oude Microsoft 365-abonnement.  <br/> | Volg de [vereiste stappen voorafgaand aan het verwijderen van een domein](remove-a-domain.md) om de domeinnaam te verwijderen uit de e-mailadressen van gebruikers en om DNS-records te verwijderen voor e-mail en Lync voor het aangepaste domein. Als u uw openbare website host op Microsoft 365, moet u ook de CNAME-record verwijderen die hieraan verwijst.  <br/> > [!IMPORTANT]>  Nadat u de MX-record hebt verwijderd waarmee e-mail in dit aangepaste domein wordt bezorgd, hebben gebruikers geen toegang meer tot e-mail totdat u het domein hebt toegevoegd aan uw nieuwe account , de nieuwe MX-record hebt toegevoegd en gebruikers hebt ingesteld. Wanneer u de DNS-records voor Lync verwijdert, werkt Lync niet meer. Op het moment dat u de CNAME-record verwijdert die naar uw openbare website verwijst, is de site niet meer beschikbaar.           [Verwijder het domein](remove-a-domain.md) .  <br/> |
|Stel uw aangepaste domein in voor het nieuwe abonnement en voeg de gebruikers toe.  <br/> | Stel het nieuwe abonnement in en vergeet niet de vereiste DNS-records voor uw aangepaste domein te maken.  <br/>  Voeg de gebruikers toe, met e-mailadressen in uw aangepaste domein.  <br/> |
|Breng gegevens van het oude abonnement over naar uw nieuwe abonnement.  <br/> | Meld u in afzonderlijke browservensters bij beide accounts aan:  <br/>  Klik met de rechtermuisknop op het pictogram van uw browser en open twee persoonlijke browservensters. U kunt verschillende referenties gebruiken in de twee vensters om u bij beide accounts aan te melden.  <br/> [Beheerinstellingen uitwisselen tussen abonnementen](#email) <br/> [Structuur en gegevens van teamsite overbrengen](#transfer-team-site-structure-and-data) <br/> [Een openbare website overbrengen naar een ander abonnement](#transfer-a-public-website-between-subscriptions) <br/> [Beheerinstellingen uitwisselen tussen abonnementen](#email) <br/> |
|Annuleer het abonnement voor het abonnement waarvoor u klaar bent door Microsoft ondersteuning te bellen voor Microsoft 365.  <br/> | Controleer of het nieuwe abonnement werkt en alle gegevens zijn overgebracht.  <br/>  [Neem contact op met de klantenservice](../contact-support-for-business-products.md) om uw oude abonnement te annuleren.  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>Beheerinstellingen uitwisselen tussen abonnementen

Ga naar de volgende pagina's van elk account en stel het nieuwe account in op basis van de instellingen van het oude account.
  
Als u gegevens van Microsoft 365 overzet naar Microsoft 365 voor middelgrote en grote ondernemingen of Microsoft 365 Enterprise, zijn de beheerders pagina's anders gestructureerd. Bekijk een [video: Kennismaken met Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365/admin/), en ga naar de volgende locaties om de beheerdersinstellingen te bekijken.
  
Voor Microsoft 365 Enterprise en Microsoft 365 voor middelgrote en grote ondernemingen:
  
|**Locatie**|**Doel**|
|:-----|:-----|
|**Beheer** \> **Microsoft 365** \> **Service-instellingen** <br/> |Selecteer elk tabblad voorinstellingen voor e-mail, sites, Lync, gebruikers software, wachtwoorden, Community, Rights Management en mobiel.  <br/> |
|**Beheer** \> **Exchange** <br/> | Instellingen van Exchange Online  <br/> |
|**Beheer** \> **SharePoint** <br/> | Instellingen van SharePoint Online  <br/> |
|**Beheer** \> **Skype voor bedrijven** <br/> |Extra instellingen voor Skype voor bedrijven  <br/> |

Voor Microsoft 365 voor professionals en kleine bedrijven
  
|**Locatie**|**Doel**|
|:-----|:-----|
|**Beheer** \> **Instellingen voor de gehele organisatie beheren** <br/> |Beheerinstellingen  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>Een openbare website overbrengen naar een ander abonnement

Als u een openbare website gehost op Microsoft 365, moet u deze opslaan en opnieuw maken voor uw nieuwe abonnement.
  
> [!NOTE]
> Als uw openbare website wordt gehost bij een DNS-hostingprovider, hoeft u niets aan te passen. De overstap heeft dan geen gevolgen voor de site.
  
Als u een documentbibliotheek of de inhoud van een lijst in SharePoint Online wilt opslaan in bestandsshares of op een lokale computer, raadpleegt u [Handmatige migratie van SharePoint Online-inhoud](https://go.microsoft.com/fwlink/p/?LinkId=402910).
  
> [!NOTE]
> De Public Site Content Migration App is niet geschikt om gegevens over te brengen naar een ander abonnement.
  
## <a name="transfer-team-site-structure-and-data"></a>Structuur en gegevens van teamsite overbrengen

Er zijn verschillende manieren om de gegevens van een teamsite op te slaan of over te brengen:
  
- U kunt de oude site opslaan als een sjabloon en vervolgens de sjabloon importeren in de nieuwe site.

- Als u documenten wilt overbrengen, moet u de hiërarchie eerst handmatig opnieuw maken op de nieuwe site. Vervolgens kunt u beide SharePoint-teamsites tegelijk openen, beide documentbibliotheken openen met Windows Verkenner, en de documenten kopiëren en plakken. Bekijk deze [video: over het kopiëren of verplaatsen van bibliotheekbestanden met de opdracht Openen in Verkenner](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790).

- Als u gegevens in een lijst wilt overbrengen, slaat u de [lijst op als een sjabloon](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393) en gebruikt u de sjabloon om de lijst opnieuw te maken op de nieuwe site.

- Als u een documentbibliotheek of Lijstinhoud van een SharePoint Online-omgeving (OneDrive voor bedrijven of team sites) wilt opslaan in bestandsshares of op een lokale computer, raadpleegt u [informatie over handmatige migratie van SharePoint Online-inhoud](https://support.microsoft.com/kb/2783484).

## <a name="transfer-users-data-between-subscriptions"></a>Gegevens van gebruikers overbrengen naar een ander abonnement

### <a name="email"></a>E-mail:

Vraag gebruikers om [hun e-mail, contactpersonen, taken en agendagegevens](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) over te brengen nadat u het nieuwe abonnement hebt ingesteld. Ze kunnen hun oude e-mail raadplegen door de oorspronkelijke gebruikersnaam op te geven, zoals sue@contoso.onmicrosoft.com.
  
### <a name="onedrive-for-business-data"></a>Gegevens van OneDrive voor bedrijven:

Vraag gebruikers [OneDrive voor bedrijven-inhoud op hun computer te](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd)kopiëren/synchroniseren en voeg deze vervolgens weer toe aan het nieuwe abonnement.
