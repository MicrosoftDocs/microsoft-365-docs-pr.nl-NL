---
title: Uw installatie van Microsoft 365 voor Bedrijven plannen
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
description: Meer informatie over de vereisten en overwegingen voor het maken van de overstap naar Microsoft 365 voor Bedrijven.
ms.openlocfilehash: 7ec1fae211ec42afd510ee431a3ea7e17e2fd16b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914064"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>Uw installatie van Microsoft 365 voor Bedrijven plannen

Dit artikel is bedoeld voor personen die zich hebben geabonneerd op een Microsoft 365 voor Bedrijven-abonnement.
  
Voordat u uw organisatie naar Microsoft 365 verplaatst, zijn er vereisten die u moet voldoen, informatie die u bij de hand moet hebben en beslissingen die u moet nemen.


  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>Informatie die u bij de hand moet hebben voordat u de installatiewizard uit te voeren

Wanneer u klaar bent om de installatiewizard uit te voeren en uw domein naar Microsoft 365 te verplaatsen, vindt u de volgende informatie:
  
- Lijst met personen die u wilt toevoegen aan Microsoft 365. Zelfs als u ze al hebt toegevoegd aan Microsoft 365, moet u hun namen hier invoeren als u uw domeingegevens bij werkt.

- Hoe u uw werknemers op de hoogte gaat stellen van hun gebruikers-id en wachtwoord, zodat ze zich kunnen aanmelden. Gaat u ze bellen om deze gegevens door te geven? Of stuurt u deze gegevens naar hun persoonlijke e-mailadres? Ze hebben geen toegang tot hun e-mail, dus dat kunt u niet gebruiken.

- Als u een domeinnaam voor uw organisatie hebt (zoals **contoso.com)** en u van plan bent microsoft-e-mail te gebruiken, moet u weten waar uw domein is geregistreerd en aanmeldingsgegevens hebben.

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>Wat gebeurt er wanneer u de installatiewizard van Microsoft 365 uit runt

Met de installatiewizard kunt u de Microsoft 365-apps op uw computer installeren, uw domein toevoegen en verifiëren, gebruikers toevoegen en licenties toewijzen en uw domein verbinden.

> [!NOTE]
> Als u beheerdersrollen [in Microsoft 365](../add-users/assign-admin-roles.md) voor Bedrijven wilt toewijzen aan de gebruikers die u in de wizard toevoegt, kunt u dat later doen op **de** pagina Gebruikers. 
  
Als u de installatiewizard niet voltooit, kunt u op elk moment setuptaken uitvoeren vanuit [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2024339)  >  **Setup.** Hier kunt u e-mail en contactpersonen migreren van een andere e-mailservice, het domein van uw beheerdersaccount wijzigen, uw factureringsgegevens beheren, gebruikers toevoegen of verwijderen, wachtwoorden opnieuw instellen en andere zakelijke functies uitvoeren. Zie Verschillen tussen de installatiewizard  van [Microsoft 365](o365-setup-wizard-and-setup-page.md)en de pagina Setup voor meer informatie over de verschillen tussen de installatiewizard en de pagina Setup.

Als u ergens vastloopt, kunt u ons altijd bellen. [We zijn er om u te helpen.](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>Wanneer kunt u de installatiewizard beter niet gebruiken? Active Directory-synchronisatie en hybride omgevingen

Er zijn een paar scenario's die bestaan uit het migreren van gegevens of gebruikers uit on-premises omgevingen of het instellen van een hybride systeem met adreslijstsynchronisatie. Als u in een van de categorieën valt, volgt u de instructies in deze artikelen:
  
- Als u adreslijstsynchronisatie wilt instellen met uw on-premises Active Directory, leest u Adreslijstsynchronisatie instellen voor [Microsoft 365](../../enterprise/set-up-directory-synchronization.md)en leest u Meer informatie over microsoft [365-identiteit](../../enterprise/about-microsoft-365-identity.md)en Azure Active Directory voor meer informatie over de verschillende identiteitsmodellen in Microsoft 365.

- Als u een hybride implementatie van Exchange wilt installeren, vindt u hier de volledige set instructies die u begeleiden bij de verschillende manieren waarop u een hybride implementatie van Exchange kunt installeren (inclusief het instellen van DNS-records): [Implementatieassistent van Exchange Server](/exchange/exchange-deployment-assistant)

- Zie [Hybride zoeken in SharePoint](/SharePoint/hybrid/hybrid-search-in-sharepoint) als u een hybride SharePoint, en met name hybride zoek- en sitefuncties, wilt installeren.

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>In één keer of in fasen naar Microsoft 365 gaan

- **Wilt u uw organisatie in één keer verplaatsen naar Microsoft 365?** Als dat het juiste is, wilt u uw domein direct verplaatsen naar Microsoft 365. Begin met het uitvoeren van de installatiewizard van Microsoft 365; u wordt gevraagd uw domein in te stellen.

- **Wilt u geleidelijk naar Microsoft 365 gaan?** Als u in fasen naar Microsoft 365 wilt gaan, kunt u de installatiewizard van Microsoft 365 overslaan en microsoft 365-functies in de volgende volgorde gebruiken:

    1. [Voeg uw werknemers toe aan Microsoft 365,](../add-users/add-users.md) zodat ze de Office-apps kunnen downloaden en installeren.

    2. [Download en installeer de Office-apps](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) zodat u Word, Excel en PowerPoint op uw computer en apparaten kunt gebruiken.

    3. [Stel Microsoft Teams in voor](#plan-for-teams) uw vergaderingen.

    4. [Verplaats uw inhoud naar Microsoft 365-cloudopslag](set-up-file-storage-and-sharing.md) (OneDrive- of SharePoint-teamsites).

    5. Wanneer u klaar bent, selecteert u in het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2024339) **Setup** in het linkernavigatiedeelvenster en gebruikt u de pagina Setup om uw domein en e-mail [te verplaatsen.](add-domain.md) 

## <a name="check-that-your-devices-meet-system-requirements"></a>Controleren of uw apparaten aan systeemvereisten voldoen

Elke persoon in uw organisatie kan de Office 2016-suite met apps (Word, Excel, PowerPoint, en meer) installeren op maximaal vijf pc's en Macs. Raadpleeg de vereisten voor besturingssysteem en computer voor de installatie van [Office 2016-pakketten](https://go.microsoft.com/fwlink/?LinkId=534827) voor bedrijven.
  
Mobiele apps kunnen worden geïnstalleerd op iOS-, Android- en Windows-apparaten. Meer informatie over de ondersteuning voor mobiele apparaten en browsers vindt u in [Systeemvereisten voor Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>E-mail plannen

Als u van een bestaande e-mailservice wilt overstappen op Microsoft 365, duurt het meestal twee dagen voordat u overschakelt.
  
### <a name="plan-for-email-downtime"></a>E-maildowntime plannen
  
Als u Microsoft 365 gaat gebruiken voor uw e-mail:
  
- Als u uw zakelijke e-mailadres (zoals *rob \@ contoso.com)* wilt verplaatsen van een andere e-mailservice naar Microsoft 365, moet u uw e-mail rechtstreeks naar uw nieuwe Microsoft 365-postvak sturen. U doet dit door de gegevens  van uw **gebruikers** migreren te selecteren op de pagina Setup, waar we u stapsgewijs begeleiden bij de updates die u moet maken bij uw domeinhost.

- Wanneer u de domeinhost hebt bijgewerkt, duurt het doorgaans een tot twee uur voordat de wijzigingen van kracht zijn. Maar let op: het kan soms tot 72 uur duren voordat de wijzigingen op internet worden bijgewerkt.

- Omdat u mogelijk e-mailonderbreking hebt, raden we u aan om tijdens een avond of weekend over te schakelen naar Microsoft-e-mail wanneer u minder e-mailberichten ontvangt.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>De overschakeling van bestaande e-mailberichten, contactpersonen en agenda plannen
  
Als u Microsoft 365 gaat gebruiken voor uw e-mailaccount, kunt u uw bestaande e-mail, contactpersonen en agenda meenemen. Met **de pagina** Setup kunt u uw bestaande e-mail en contactpersonen verplaatsen voor de meeste scenario's. We hebben ook stapsgewijze instructies voor het verplaatsen van één of meer postvakken.
  
|**Hoeveel postvakken?**|**Aanbeveling**|
|:-----|:-----|
|Slechts enkele  <br/> |Als u de pagina Setup  niet wilt gebruiken om de postvakken te migreren, kunt u postvakkeneigenaren hun eigen e-mail en contactpersonen laten migreren. Zie [E-mail en contactpersonen migreren naar Microsoft 365 voor Bedrijven.](migrate-email-and-contacts-admin.md)  <br/> |
|Meerdere  <br/> |Zie G Suite-postvakken migreren naar [Microsoft 365](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)als u migreert vanuit Gmail.  <br/> Zie Manieren om meerdere e-mailaccounts te migreren naar [Microsoft 365](/Exchange/mailbox-migration/mailbox-migration)als u migreert van een andere e-mailprovider, waaronder Exchange.  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Bestandsopslag en -migratie plannen

Microsoft 365 biedt cloudopslag voor personen, kleine organisaties en ondernemingen. Zie Where you can store documents in Microsoft 365 (Waar kunt u documenten opslaan [in Microsoft 365)](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790)voor informatie over waar u waar moet opslaan.
  
- **U kunt honderden bestanden verplaatsen naar** [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) of naar een [SharePoint-teamsite.](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242) U kunt 100 bestanden tegelijk uploaden. Upload geen bestanden die groter zijn dan 2 GB, de maximale bestandsgrootte.
  
- **Als u enkele duizenden bestanden wilt verplaatsen** naar Microsoft 365-opslag, controleert u de [SharePoint Online-limieten.](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) Het is raadzaam om een hulpprogramma voor migratie te gebruiken of een [partner](https://go.microsoft.com/fwlink/?linkid=391089) in te schakelen om u te helpen met de migratie. Voor informatie over de migratie van een groot aantal bestanden raadpleegt u de [Gebruikershandleiding voor SharePoint Online- en OneDrive-migratie](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets).
  
## <a name="plan-for-teams"></a>Plannen voor Teams

U kunt Microsoft Teams gebruiken om te bellen naar andere personen in uw organisatie die uw abonnement hebben. Als uw organisatie bijvoorbeeld tien personen heeft, kunt u met Teams bellen en chatberichten maken zonder speciale instellingen. Zie Aan de slag [met Microsoft Teams voor meer informatie.](/MicrosoftTeams/get-started-with-teams-quick-start)

Zie Microsoft Teams implementeren voor grotere organisaties of als u begint met Skype voor [Bedrijven,](/MicrosoftTeams/how-to-roll-out-teams)on-premises of hybride implementaties.
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Integratie met Active Directory of andere software plannen

- **Wilt u integreren met uw on-premises Active Directory?** U kunt uw on-premises Active Directory integreren met Microsoft 365 met Behulp van Azure Active Directory Connect. Zie Adreslijstsynchronisatie instellen voor [Microsoft 365](../../enterprise/set-up-directory-synchronization.md)voor instructies.
  
- **Wilt u Microsoft 365 integreren met software van andere bedrijven?** Als u Microsoft 365 wilt integreren met andere software in uw organisatie, raden we u aan een [partner](https://go.microsoft.com/fwlink/?linkid=391089) in te huren om u te helpen bij uw implementatie.
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>Wilt u dat iemand u helpt bij het instellen van Microsoft 365?

- **Als u minder dan 50 werknemers hebt:**

  - **Vraag om hulp en wij bellen u**. Nadat u Microsoft 365 hebt gekocht, hebt u toegang tot het beheercentrum (u hoeft de installatie niet uit te voeren om het te openen). Selecteer Hulp nodig onder aan het **beheercentrum?** Beschrijf het probleem en u wordt gebeld. 
  - **Bel [Microsoft 365 voor Bedrijven-ondersteuning](../contact-support-for-business-products.md) met uw vragen.** We zijn er om u te helpen. 
  - **U kunt overwegen een [Microsoft-partner](https://go.microsoft.com/fwlink/?linkid=391089)** in te huren. Als u weinig tijd hebt of geavanceerde vereisten hebt (zoals het verplaatsen van duizenden bestanden naar De cloudopslag van Microsoft 365 of het integreren met andere software), kan een ervaren partner een grote hulp zijn. 

- **Als u meer dan 50 werknemers hebt**, is het [FastTrack Onboarding Center](https://go.microsoft.com/fwlink/?LinkId=517115) beschikbaar om u te helpen met de implementatie.