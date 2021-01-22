---
title: De installatie van Microsoft 365 voor Bedrijven plannen
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
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Lees meer over de vereisten en overwegingen voor de overstap naar Microsoft 365 voor Bedrijven.
ms.openlocfilehash: 9158ad5a56b78fd8173ae81a2e9e4a5bd51633ca
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926820"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>De installatie van Microsoft 365 voor Bedrijven plannen

Dit artikel is bedoeld voor personen die een abonnement hebben op Microsoft 365 voor Bedrijven.
  
Voordat u uw organisatie over overstapt op Microsoft 365, zijn er vereisten waar u aan moet voldoen, informatie die u nodig hebt en beslissingen die u moet nemen.


  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>Informatie die u bij de hand moet hebben voordat u de installatiewizard gaat uitvoeren

Wanneer u klaar bent om de installatiewizard uit te voeren en uw domein naar Microsoft 365 te verplaatsen, hebt u de volgende informatie nodig:
  
- Lijst met personen die u wilt toevoegen aan Microsoft 365. Zelfs als u ze al hebt toegevoegd aan Microsoft 365, moet u hun namen hier invoeren als u uw domeingegevens bij werkt.

- Hoe u uw werknemers gaat informeren over hun gebruikers-id en wachtwoord, zodat ze zich kunnen aanmelden. Gaat u ze bellen om deze gegevens door te geven? Of stuurt u deze gegevens naar hun persoonlijke e-mailadres? Ze hebben geen toegang tot hun e-mail, dus die kunt u niet gebruiken.

- Als u een domeinnaam voor uw organisatie hebt (zoals **contoso.com)** en u e-mail van Microsoft wilt gaan gebruiken, moet u weten waar uw domein is geregistreerd en uw aanmeldingsgegevens hebben.

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>Wat gebeurt er wanneer u de installatiewizard van Microsoft 365 gebruikt

De installatiewizard laat u weten hoe u de Microsoft 365-apps installeert op uw computer, uw domein toevoegt en verifieert, gebruikers toevoegt en licenties toewijst en uw domein verbindt.

> [!NOTE]
> Als u [beheerdersrollen in Microsoft 365](../add-users/assign-admin-roles.md) voor Bedrijven wilt toewijzen aan de gebruikers die u toevoegt aan de wizard, kunt u dat later doen op de **pagina** Gebruikers. 
  
Als u de installatiewizard niet voltooit, kunt u de installatietaken op elk moment uitvoeren vanuit de installatie [van het](https://go.microsoft.com/fwlink/p/?linkid=2024339)  >  **beheercentrum.** Hier kunt u e-mail en contactpersonen migreren van een andere e-mailservice, het domein van uw beheerdersaccount wijzigen, uw factureringsgegevens beheren, gebruikers toevoegen of verwijderen, wachtwoorden opnieuw instellen en andere bedrijfsfuncties uitvoeren. Zie Verschillen tussen de installatiewizard  van [Microsoft 365](o365-setup-wizard-and-setup-page.md)en de pagina Setup voor meer informatie over de verschillen tussen de installatiewizard en de pagina Setup.

Als u ergens vastloopt, kunt u ons altijd bellen. [We zijn er om u te helpen.](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>Wanneer kunt u de installatiewizard beter niet gebruiken? Active Directory-synchronisatie en hybride omgevingen

Er zijn een aantal scenario's waarin gegevens of gebruikers vanuit on-premises omgevingen worden gemigreert of een hybride systeem met adreslijstsynchronisatie wordt gebruikt. Als u in een van deze categorieën zit, volgt u de instructies in deze artikelen:
  
- Als u adreslijstsynchronisatie wilt instellen met uw on-premises Active Directory, leest u Adreslijstsynchronisatie voor [Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)instellen en voor meer informatie over de verschillende identiteitsmodellen in Microsoft 365. Lees Meer informatie over [Microsoft 365-identiteit](https://docs.microsoft.com/microsoft-365/enterprise/about-microsoft-365-identity)en Azure Active Directory.

- Als u een hybride implementatie van Exchange wilt installeren, vindt u hier de volledige set instructies die u begeleiden bij de verschillende manieren waarop u een hybride implementatie van Exchange kunt installeren (inclusief het instellen van DNS-records): [Implementatieassistent van Exchange Server](https://aka.ms/exdeploy)

- Zie [Hybride zoeken in SharePoint](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint) als u een hybride SharePoint, en met name hybride zoek- en sitefuncties, wilt installeren.

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>Stap over op Microsoft 365 in één keer of in fasen

- **Wilt u uw organisatie in één keer over verplaatsen naar Microsoft 365?** Zo ja, dan is het van plan om uw domein direct over te zetten naar Microsoft 365. Start met de installatiewizard van Microsoft 365. wordt u gevraagd uw domein in te stellen.

- **Wilt u geleidelijk over gaan op Microsoft 365?** Als u gefaseer over wilt stappen naar Microsoft 365, slaat u de installatiewizard van Microsoft 365 over en kunt u overwegen Microsoft 365-functies in de volgende volgorde over te nemen:

    1. [Voeg uw werknemers toe aan Microsoft 365,](../add-users/add-users.md) zodat ze de Office-apps kunnen downloaden en installeren.

    2. [Download en installeer de Office-apps](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) zodat u Word, Excel en PowerPoint op uw computer en apparaten kunt gebruiken.

    3. [Stel Microsoft Teams in voor](#plan-for-teams) gebruik voor uw vergaderingen.

    4. [Verplaats uw inhoud naar Cloudopslag in Microsoft 365](set-up-file-storage-and-sharing.md) (OneDrive of SharePoint-teamsites).

    5. Wanneer u klaar bent, [](https://go.microsoft.com/fwlink/p/?linkid=2024339)selecteert u in het beheercentrum **Setup** in het linkernavigatiedeelvenster en gebruikt u de pagina Setup om uw domein en e-mail [te verplaatsen.](add-domain.md) 

## <a name="check-that-your-devices-meet-system-requirements"></a>Controleren of uw apparaten aan systeemvereisten voldoen

Elke persoon in uw organisatie kan het Office 2016-pakket met apps (Word, Excel, PowerPoint, e.d.) installeren op maximaal vijf pc's en Macs. Raadpleeg de vereisten voor besturingssysteem en computer voor de installatie van [Office 2016-pakketten](https://go.microsoft.com/fwlink/?LinkId=534827) voor bedrijven.
  
Mobiele apps kunnen worden geïnstalleerd op iOS-, Android- en Windows-apparaten. Meer informatie over de ondersteuning voor mobiele apparaten en browsers vindt u in [Systeemvereisten voor Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>E-mail plannen

Als u van een bestaande e-mailservice wilt overstappen op Microsoft 365, duurt het meestal twee dagen om over te stappen.
  
### <a name="plan-for-email-downtime"></a>E-maildowntime plannen
  
Als u Microsoft 365 gaat gebruiken voor uw e-mail:
  
- Als u uw zakelijke e-mailadres (zoals *rob \@ contoso.com)* wilt verplaatsen van een andere e-mailservice naar Microsoft 365, moet u uw e-mail om te leiden naar uw nieuwe Microsoft 365-postvak. Hiervoor selecteert  u de gegevens van  uw gebruikers migreren op de pagina Setup, waar we u stap voor stap begeleiden bij de updates die u moet maken bij uw domeinhost.

- Wanneer u de domeinhost hebt bijgewerkt, duurt het doorgaans een tot twee uur voordat de wijzigingen van kracht zijn. Het kan soms wel 72 uur duren voordat de wijzigingen op internet zijn bijgewerkt.

- Omdat er mogelijk e-mailuitvaltijd is, wordt u aangeraden om over te schakelen naar e-mail van Microsoft tijdens een avond of weekend wanneer u minder e-mailberichten ontvangt.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>De overschakeling van bestaande e-mailberichten, contactpersonen en agenda plannen
  
Als u Microsoft 365 gaat gebruiken voor uw e-mailaccount, kunt u uw bestaande e-mail, contactpersonen en agenda meenemen. Op **de pagina** Setup kunt u in de meeste scenario's uw bestaande e-mail en contactpersonen verplaatsen. We hebben ook stapsgewijze instructies voor het verplaatsen van één of meer postvakken.
  
|**Hoeveel postvakken?**|**Aanbeveling**|
|:-----|:-----|
|Slechts enkele  <br/> |Als u de pagina Setup  niet wilt gebruiken om de postvakken te migreren, kunt u postvakeigenaren hun eigen e-mail en contactpersonen laten migreren. Zie [E-mail en contactpersonen migreren naar Microsoft 365 voor Bedrijven.](migrate-email-and-contacts-admin.md)  <br/> |
|Meerdere  <br/> |Zie G Suite-postvakken migreren naar [Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)als u migreert vanuit Gmail.  <br/> Als u migreert van een andere e-mailprovider, met inbegrip van Exchange, bekijkt u Manieren om meerdere e-mailaccounts te migreren [naar Microsoft 365.](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Bestandsopslag en -migratie plannen

Microsoft 365 biedt cloudopslag voor personen, kleine organisaties en ondernemingen. Zie Waar u documenten kunt opslaan [in Microsoft 365](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790)voor meer informatie over wat u waar kunt opslaan.
  
- **U kunt honderden bestanden verplaatsen naar** [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) of naar een [SharePoint-teamsite.](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242) U kunt 100 bestanden tegelijk uploaden. Upload geen bestanden die groter zijn dan 2 GB, de maximale bestandsgrootte.
  
- **Als u enkele duizenden bestanden wilt** verplaatsen naar Microsoft 365-opslag, bekijkt u de limieten voor [SharePoint Online.](https://go.microsoft.com/fwlink/p/?LinkID=856113) Het is raadzaam om een hulpprogramma voor migratie te gebruiken of een [partner](https://go.microsoft.com/fwlink/?linkid=391089) in te schakelen om u te helpen met de migratie. Voor informatie over de migratie van een groot aantal bestanden raadpleegt u de [Gebruikershandleiding voor SharePoint Online- en OneDrive-migratie](https://go.microsoft.com/fwlink/?LinkId=723574).
  
## <a name="plan-for-teams"></a>Plannen voor Teams

U kunt Microsoft Teams gebruiken om te bellen met andere personen in uw organisatie die op uw abonnement zitten. Als uw organisatie bijvoorbeeld uit 10 personen beschikt, kunt u elkaar bellen en chatberichten met behulp van Teams zonder speciale instellingen. Zie Aan de slag [met Microsoft Teams voor meer informatie.](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start)

Zie Microsoft Teams implementeren voor grotere organisaties of als u begint vanuit Skype voor [Bedrijven,](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams)on-premises of hybride implementaties.
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Integratie met Active Directory of andere software plannen

- **Wilt u integreren met uw on-premises Active Directory?** U kunt uw on-premises Active Directory integreren met Microsoft 365 met behulp van Azure Active Directory Connect. Zie [Adreslijstsynchronisatie voor Microsoft 365 instellen voor instructies.](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)
  
- **Wilt u Microsoft 365 integreren met software van andere bedrijven?** Als u Microsoft 365 wilt integreren met andere software in uw organisatie, raden we u aan een [partner](https://go.microsoft.com/fwlink/?linkid=391089) in te huren die u kan helpen met de implementatie.
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>Wilt u dat iemand u kan helpen bij het instellen van Microsoft 365?

- **Als u minder dan 50 werknemers hebt:**

  - **Vraag om hulp en wij bellen u**. Nadat u Microsoft 365 hebt gekocht, kunt u het beheercentrum openen (u hoeft de installatie niet uit te voeren om het te openen). Onderaan in het beheercentrum selecteert u **Hulp nodig?** Beschrijf het probleem en u wordt gebeld. 
  - **Bel [de ondersteuning van Microsoft 365 voor Bedrijven met](../contact-support-for-business-products.md) uw vragen.** We zijn er om u te helpen. 
  - **U kunt overwegen een [Microsoft-partner](https://go.microsoft.com/fwlink/?linkid=391089)** in te huren. Als u weinig tijd hebt of als u geavanceerde vereisten hebt (zoals het verplaatsen van duizenden bestanden naar cloudopslag van Microsoft 365 of integratie met andere software), kan een ervaren partner veel helpen. 

- **Als u meer dan 50 werknemers hebt**, is het [FastTrack Onboarding Center](https://go.microsoft.com/fwlink/?LinkId=517115) beschikbaar om u te helpen met de implementatie. 
