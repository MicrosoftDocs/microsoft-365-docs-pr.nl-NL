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
description: Ontdek hoe u gegevens handmatig overdraagt tussen twee Microsoft 365-accounts wanneer u het abonnement of de bedrijfsnaam wijzigde of meerdere abonnementen in één combineren.
ms.openlocfilehash: 6e64872ad7e145b63eb71d89ea2d69e5d8697eb6
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780167"
---
# <a name="transfer-data-manually-between-two-accounts"></a>Gegevens handmatig overbrengen tussen twee accounts

Bereid je voor om je mouwen op te stropen en een deel van de tijd in je agenda te blokkeren: het overbrengen van gegevens tussen twee Microsoft 365-accounts is een handmatig, ingewikkeld en tijdrovend proces. Het betreft hier trouwens een proces dat niet wordt ondersteund. We zullen u wel op weg helpen.
  
> [!CAUTION]
> Er zal een tijds aantal zijn tijdens het proces waarin e-mail, Skype voor Bedrijven en een openbare website die worden gehost op Microsoft 365 niet werken. Gebruikers krijgen nieuwe gebruikersnamen en wachtwoorden, en ze moeten Outlook opnieuw instellen.

**In de volgende gevallen mag u gegevens alleen handmatig overbrengen volgens de instructies in dit onderwerp:**
  
- U moet overstappen op een abonnement in een andere servicefamilie.

- De naam van uw bedrijf is gewijzigd en u hebt besloten om een nieuw abonnement te nemen en uw gegevens te migreren omdat u domeinnamen wilt gebruiken die de nieuwe bedrijfsnaam bevatten.

- U moet meerdere abonnementen in één nieuw abonnement samenvoegen.

> [!IMPORTANT]
> Als u [van abonnement moet veranderen](../../commerce/subscriptions/switch-to-a-different-plan.md) en u de wizard Veranderen van abonnement kunt gebruiken, hoeft u de gegevens niet handmatig over te brengen en worden services niet onderbroken. Dit is ook zo als u gegevens moet overbrengen naar een nieuw abonnement in dezelfde abonnementsfamilie en de wizard Veranderen van abonnement niet werkt.

|**Taken**|**Stappen**|
|:-----|:-----|
|Koop het abonnement waarop u wilt overstappen.  <br/> |When you sign up, you specify the company name to use in the initial domain names:  *yourcompany*  .onmicrosoft.com,  *yourcompany*  -public.sharepoint.com, and  *yourcompany*  .sharepoint.com. You need to use a different  *yourcompany*  name than you did for any existing subscriptions.  <br/> > [!NOTE]>  Nadat u een abonnement hebt opgezegd, duurt het meestal minimaal een paar maanden voordat de namen van de standaarddomeinen met  *uwbedrijf*  van het opgezegde abonnement worden vrijgegeven in onze systemen. Zelfs als u van plan bent om al uw gegevens op te slaan van uw oude Microsoft 365-abonnement en dat abonnement op te zeggen, is de oude waarde *van uw bedrijf* niet onmiddellijk beschikbaar voor gebruik in een nieuw abonnement.           |
|Verwijder uw aangepaste domein uit uw oude Microsoft 365-abonnement.  <br/> | Volg de [vereiste stappen voorafgaand aan het verwijderen van een domein](remove-a-domain.md) om de domeinnaam te verwijderen uit de e-mailadressen van gebruikers en om DNS-records te verwijderen voor e-mail en Lync voor het aangepaste domein. Als u uw openbare website host op Microsoft 365, moet u ook de CNAME-record verwijderen die erop wijst.  <br/> > [!IMPORTANT]>  After you remove the MX record that routes email to this custom domain, email will stop working until you have added the domain to your new account, set up the new MX record, and set up your users. When you remove the DNS records for Lync, Lync will stop working. And after you remove the CNAME record that points to your public website, it will not be available.           [Remove the domain](remove-a-domain.md) .  <br/> |
|Stel uw aangepaste domein in voor het nieuwe abonnement en voeg de gebruikers toe.  <br/> | Stel het nieuwe abonnement in en vergeet niet de vereiste DNS-records voor uw aangepaste domein te maken.  <br/>  Voeg de gebruikers toe, met e-mailadressen in uw aangepaste domein.  <br/> |
|Breng gegevens van het oude abonnement over naar uw nieuwe abonnement.  <br/> | Meld u in afzonderlijke browservensters bij beide accounts aan:  <br/>  Right-click the Internet Explorer icon, and open two InPrivate browser windows. You can use different credentials in the two windows to sign in on both accounts.  <br/> [Beheerinstellingen uitwisselen tussen abonnementen](#email) <br/> [Structuur en gegevens van teamsite overbrengen](#transfer-team-site-structure-and-data) <br/> [Een openbare website overbrengen naar een ander abonnement](#transfer-a-public-website-between-subscriptions) <br/> [Beheerinstellingen uitwisselen tussen abonnementen](#email) <br/> |
|Annuleer het abonnement voor het abonnement waarmee u klaar bent door Microsoft Support voor Microsoft 365 te bellen.  <br/> | Controleer of het nieuwe abonnement werkt en alle gegevens zijn overgebracht.  <br/>  [Neem contact op met de klantenservice](../contact-support-for-business-products.md) om uw oude abonnement op te zeggen.  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>Beheerinstellingen uitwisselen tussen abonnementen

Ga naar de volgende pagina's van elk account en stel het nieuwe account in op basis van de instellingen van het oude account.
  
Als u gegevens overdraagt van Microsoft 365 naar Microsoft 365 Midsize Business of Microsoft 365 Enterprise, zijn de beheerderspagina's anders gestructureerd. Bekijk een [video: Introductie van Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365/admin/)en ga naar de volgende plaatsen om de beheerdersinstellingen te bekijken.
  
Voor Microsoft 365 Enterprise en Microsoft 365 Middelgrote bedrijven:
  
|**Locatie**|**Doel**|
|:-----|:-----|
|**Beheerder** \> **Microsoft 365** \> **Service-instellingen** <br/> |Selecteer elk tabblad voor instellingen voor e-mail, sites, Lync, gebruikerssoftware, wachtwoorden, community, rechtenbeheer en mobiel.  <br/> |
|**Beheer** \> **Exchange** <br/> | Instellingen van Exchange Online  <br/> |
|**Beheer** \> **SharePoint** <br/> | Instellingen van SharePoint Online  <br/> |
|**Beheerder** \> **Skype voor Bedrijven** <br/> |Aanvullende Instellingen voor Skype voor Bedrijven  <br/> |

Voor Microsoft 365 kleine bedrijven
  
|**Locatie**|**Doel**|
|:-----|:-----|
|**Beheer** \> **Instellingen voor de gehele organisatie beheren** <br/> |Beheerinstellingen  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>Een openbare website overbrengen naar een ander abonnement

Als u een openbare website hebt die wordt gehost op Microsoft 365, moet u deze opslaan en opnieuw maken op uw nieuwe abonnement.
  
> [!NOTE]
> If your public website is hosted at a DNS hosting provider, no changes are required. It will not be affected by your transition.
  
Als u een documentbibliotheek of de inhoud van een lijst in SharePoint Online wilt opslaan in bestandsshares of op een lokale computer, raadpleegt u [Handmatige migratie van SharePoint Online-inhoud](https://go.microsoft.com/fwlink/p/?LinkId=402910).
  
> [!NOTE]
> De Public Site Content Migration App is niet geschikt om gegevens over te brengen naar een ander abonnement.
  
## <a name="transfer-team-site-structure-and-data"></a>Structuur en gegevens van teamsite overbrengen

Er zijn verschillende manieren om de gegevens van een teamsite op te slaan of over te brengen:
  
- U kunt de oude site opslaan als een sjabloon en vervolgens de sjabloon importeren in de nieuwe site.

- Als u documenten wilt overbrengen, maakt u eerst handmatig uw hiërarchie opnieuw op de nieuwe site. Vervolgens kunt u beide SharePoint-teamsites tegelijk openen, beide documentbibliotheken openen met Windows Verkenner, en de documenten kopiëren en plakken. Bekijk deze [video: over het kopiëren of verplaatsen van bibliotheekbestanden met de opdracht Openen in Verkenner](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790).

- Als u gegevens in een lijst wilt overbrengen, slaat u de [lijst op als een sjabloon](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393) en gebruikt u de sjabloon om de lijst opnieuw te maken op de nieuwe site.

- Zie [Informatie over handmatige migratie van SharePoint Online-inhoud](https://support.microsoft.com/kb/2783484)als u een documentbibliotheek of lijstinhoud wilt opslaan uit een SharePoint Online-omgeving (OneDrive voor Bedrijven of teamsites) voor bestandsshares of naar een lokale computer.

## <a name="transfer-users-data-between-subscriptions"></a>Gegevens van gebruikers overbrengen naar een ander abonnement

### <a name="email"></a>E-mail:

Ask users to [move their email, contacts, tasks, and calendar information](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) after you set up your new subscription. They can get to their old email by using their initial user name, such as sue@contoso.onmicrosoft.com.
  
### <a name="onedrive-for-business-data"></a>Gegevens van OneDrive voor Bedrijven:

Vraag gebruikers om [OneDrive voor Bedrijven-inhoud te](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd)kopiëren/synchroniseren op hun computer en voeg deze vervolgens weer toe aan hun nieuwe abonnement.
