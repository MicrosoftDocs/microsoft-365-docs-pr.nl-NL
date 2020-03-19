---
title: Gegevens handmatig uitwisselen tussen twee Office 365-accounts
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
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: Informatie over het handmatig overbrengen van gegevens tussen twee Office 365-accounts wanneer u het abonnement of de bedrijfsnaam hebt gewijzigd of meerdere abonnementen in één hebt gecombineerd.
ms.openlocfilehash: 91f9d7b17a0296931393a89ff95d70628400c61a
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42805792"
---
# <a name="transfer-data-manually-between-two-office-365-accounts"></a>Gegevens handmatig uitwisselen tussen twee Office 365-accounts

Het kost heel wat tijd en moeite om gegevens over te brengen naar een ander Office 365-account aangezien dit een handmatig en ingewikkeld proces is. Het betreft hier trouwens een proces dat niet wordt ondersteund. We zullen u wel op weg helpen.
  
> [!CAUTION]
> Er is een down time tijdens het proces waarin e-mail, Skype voor Bedrijven en een openbare website die wordt gehost op Office 365 niet werken. Gebruikers krijgen nieuwe gebruikersnamen en wachtwoorden, en ze moeten Outlook opnieuw instellen.

**In de volgende gevallen mag u gegevens alleen handmatig overbrengen volgens de instructies in dit onderwerp:**
  
- U moet overstappen op een abonnement in een andere servicefamilie.

- De naam van uw bedrijf is gewijzigd en u hebt besloten om een nieuw abonnement te nemen en uw gegevens te migreren omdat u domeinnamen wilt gebruiken die de nieuwe bedrijfsnaam bevatten.

- U moet meerdere abonnementen in één nieuw abonnement samenvoegen.

> [!IMPORTANT]
> Als u [van abonnement moet veranderen](../../commerce/subscriptions/switch-to-a-different-plan.md) en u de wizard Veranderen van abonnement kunt gebruiken, hoeft u de gegevens niet handmatig over te brengen en worden services niet onderbroken. Dit is ook zo als u gegevens moet overbrengen naar een nieuw abonnement in dezelfde abonnementsfamilie en de wizard Veranderen van abonnement niet werkt.

|**Taken**|**Stappen**|
|:-----|:-----|
|Koop het abonnement waarop u wilt overstappen.  <br/> |Tijdens de registratie geeft u aan welke bedrijfsnaam u wilt gebruiken in de domeinnamen die standaard worden gemaakt:  *uwbedrijf*  .onmicrosoft.com,  *uwbedrijf*  -public.sharepoint.com en  *uwbedrijf*  .sharepoint.com. U moet voor  *uwbedrijf*  een andere naam gebruiken dan voor bestaande abonnementen.  <br/> > [!NOTE]>  Nadat u een abonnement hebt opgezegd, duurt het meestal minimaal een paar maanden voordat de namen van de standaarddomeinen met  *uwbedrijf*  van het opgezegde abonnement worden vrijgegeven in onze systemen. Zelfs als u van plan bent om alle gegevens van uw oude Office 365-abonnement op te slaan, en dat abonnement op te zeggen, is de oude waarde voor  *uwbedrijf*  niet onmiddellijk beschikbaar voor gebruik in een nieuw abonnement.           |
|Verwijder uw aangepaste domein uit uw oude Office 365-abonnement.  <br/> | Volg de [vereiste stappen voorafgaand aan het verwijderen van een domein](remove-a-domain.md) om de domeinnaam te verwijderen uit de e-mailadressen van gebruikers en om DNS-records te verwijderen voor e-mail en Lync voor het aangepaste domein. Als uw openbare website wordt gehost in Office 365, moet u ook de CNAME-record verwijderen die naar deze site verwijst.  <br/> > [!IMPORTANT]>  Nadat u de MX-record hebt verwijderd waarmee e-mail in dit aangepaste domein wordt bezorgd, hebben gebruikers geen toegang meer tot e-mail totdat u het domein hebt toegevoegd aan uw nieuwe account , de nieuwe MX-record hebt toegevoegd en gebruikers hebt ingesteld. Wanneer u de DNS-records voor Lync verwijdert, werkt Lync niet meer. Op het moment dat u de CNAME-record verwijdert die naar uw openbare website verwijst, is de site niet meer beschikbaar.           [Verwijder het domein](remove-a-domain.md) .  <br/> |
|Stel uw aangepaste domein in voor het nieuwe abonnement en voeg de gebruikers toe.  <br/> | Stel het nieuwe abonnement in en vergeet niet de vereiste DNS-records voor uw aangepaste domein te maken.  <br/>  Voeg de gebruikers toe, met e-mailadressen in uw aangepaste domein.  <br/> |
|Breng gegevens van het oude abonnement over naar uw nieuwe abonnement.  <br/> | Meld u in afzonderlijke browservensters bij beide accounts aan:  <br/>  Klik met de rechtermuisknop op het pictogram van Internet Explorer en open twee InPrivate-browservensters. U kunt verschillende referenties gebruiken in de twee vensters om u bij beide accounts aan te melden.  <br/> [Beheerinstellingen uitwisselen tussen abonnementen](#email) <br/> [Structuur en gegevens van teamsite overbrengen](#transfer-team-site-structure-and-data) <br/> [Een openbare website overbrengen naar een ander abonnement](#transfer-a-public-website-between-subscriptions) <br/> [Beheerinstellingen uitwisselen tussen abonnementen](#email) <br/> |
|Zeg het abonnement op dat u wilt beëindigen door te bellen met Microsoft Ondersteuning voor Office 365.  <br/> | Controleer of het nieuwe abonnement werkt en alle gegevens zijn overgebracht.  <br/>  [Neem contact op met de klantenservice](../contact-support-for-business-products.md) om uw oude abonnement op te zeggen.  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>Beheerinstellingen uitwisselen tussen abonnementen

Ga naar de volgende pagina's van elk account en stel het nieuwe account in op basis van de instellingen van het oude account.
  
Als u gegevens overbrengt van Office 365 naar Office 365 Premium voor middelgrote bedrijven of Office 365 Enterprise, zijn de beheerpagina's anders ingericht. Bekijk een [introductievideo over Office 365 Enterprise](https://support.office.com/article/11f7b4a0-1294-4e94-9238-beaae26efa9c.aspx) en ga naar de volgende pagina's voor beheerinstellingen.
  
Voor Office 365 Enterprise en Office 365 Premium voor middelgrote bedrijven:
  
|**Locatie**|**Doel**|
|:-----|:-----|
|**Beheer** \> **Office 365** \> **Service-instellingen** <br/> |Selecteer elk tabblad voor instellingen voor e-mail, sites, Lync, gebruikerssoftware, wachtwoorden, community, rechtenbeheer en mobiel.  <br/> |
|**Beheer** \> **Exchange** <br/> | Instellingen van Exchange Online  <br/> |
|**Beheer** \> **SharePoint** <br/> | Instellingen van SharePoint Online  <br/> |
|**Beheerder** \> **Skype voor Bedrijven** <br/> |Aanvullende Instellingen voor Skype voor Bedrijven  <br/> |

Voor Office 365 voor Professionals en Kleine Bedrijven
  
|**Locatie**|**Doel**|
|:-----|:-----|
|**Beheer** \> **Instellingen voor de gehele organisatie beheren** <br/> |Beheerinstellingen  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>Een openbare website overbrengen naar een ander abonnement

Als u een openbare website host in Office 365, moet u deze opslaan en opnieuw maken voor het nieuwe abonnement.
  
> [!NOTE]
> Als uw openbare website wordt gehost bij een DNS-hostingprovider, hoeft u niets aan te passen. De overstap heeft dan geen gevolgen voor de site.
  
Als u een documentbibliotheek of de inhoud van een lijst in SharePoint Online wilt opslaan in bestandsshares of op een lokale computer, raadpleegt u [Handmatige migratie van SharePoint Online-inhoud](https://go.microsoft.com/fwlink/p/?LinkId=402910).
  
> [!NOTE]
> De Public Site Content Migration App is niet geschikt om gegevens over te brengen naar een ander abonnement.
  
## <a name="transfer-team-site-structure-and-data"></a>Structuur en gegevens van teamsite overbrengen

Er zijn verschillende manieren om de gegevens van een teamsite op te slaan of over te brengen:
  
- U kunt de oude site opslaan als een sjabloon en vervolgens de sjabloon importeren in de nieuwe site.

- Als u documenten wilt overdragen, maakt u eerst handmatig uw hiërarchie opnieuw op de nieuwe site. Vervolgens kunt u beide SharePoint-teamsites tegelijk openen, beide documentbibliotheken openen met Windows Verkenner, en de documenten kopiëren en plakken. Bekijk deze [video: over het kopiëren of verplaatsen van bibliotheekbestanden met de opdracht Openen in Verkenner](https://support.office.com/article/c27bc6f3-7b38-4c29-b947-5d00c7153384.aspx).

- Als u gegevens in een lijst wilt overbrengen, slaat u de [lijst op als een sjabloon](https://support.office.com/article/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393.aspx) en gebruikt u de sjabloon om de lijst opnieuw te maken op de nieuwe site.

- [Zie Informatie over handmatige migratie van SharePoint Online-inhoud](https://support.microsoft.com/kb/2783484)als u een documentbibliotheek of lijstinhoud uit een SharePoint Online-omgeving (OneDrive voor Bedrijven of teamsites) wilt opslaan om shares of naar een lokale computer in te dienen.

## <a name="transfer-users-data-between-subscriptions"></a>Gegevens van gebruikers overbrengen naar een ander abonnement

### <a name="email"></a>E-mail:

Vraag gebruikers om [hun e-mail, contactpersonen, taken en agendagegevens](https://support.office.com/article/0996ece3-57c6-49bc-977b-0d1892e2aacc.aspx) over te brengen nadat u het nieuwe abonnement hebt ingesteld. Ze kunnen hun oude e-mail raadplegen door de oorspronkelijke gebruikersnaam op te geven, zoals sue@contoso.onmicrosoft.com.
  
### <a name="onedrive-for-business-data"></a>OneDrive voor Bedrijven-gegevens:

Vraag gebruikers om [OneDrive voor Bedrijven-inhoud naar hun computer te](https://support.office.com/article/59b1de2b-519e-4d3a-8f45-51647cf291cd.aspx)kopiëren/synchroniseren en deze vervolgens weer toe te voegen aan hun nieuwe abonnement.
