---
title: Uw installatie van Microsoft 365 voor bedrijven plannen
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
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Meer informatie over wat u moet doen om uw Microsoft 365 voor bedrijven in te stellen.
ms.openlocfilehash: d02e1aaf03449bd976b8db549274002b3ebb6ed6
ms.sourcegitcommit: b458277f0a9937555bc6c5b3fb2a41613f7cc9a9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2020
ms.locfileid: "43794031"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>Uw installatie van Microsoft 365 voor bedrijven plannen

Dit artikel is voor mensen die zich hebben geabonneerd op een Microsoft 365 voor bedrijfsabonnement.
  
Er zijn een paar dingen die u moet beslissen en informatie die u bij de hand moet hebben, voordat u uw organisatie naar Microsoft 365 verplaatst.
  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>Informatie die u bij de hand hebt voordat u de wizard Setup uitvoert

Wanneer u klaar bent om de wizard Setup uit te voeren en uw domein naar Microsoft 365 te verplaatsen, vindt u hier de informatie die u bij de hand moet hebben:
  
- Lijst met personen die u wilt toevoegen aan Microsoft 365. Zelfs als u ze al aan Microsoft 365 hebt toegevoegd, moet u hun namen hier invoeren als u uw domeingegevens bijwerkt.

- Hoe u uw werknemers op de hoogte gaat stellen van hun gebruikersnaam en wachtwoord, zodat ze zich kunnen aanmelden. Gaat u ze bellen om deze gegevens door te geven? Of stuurt u deze gegevens naar hun persoonlijke e-mailadres? Ze hebben geen toegang tot hun e-mail, dus je dat niet gebruiken.

- Als u een domeinnaam voor uw organisatie hebt (zoals contoso.com) **en** u van plan bent microsoft-e-mail te gebruiken, moet u weten waar uw domein is geregistreerd en aanmeldingsgegevens hebben.

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>Wat gebeurt er wanneer u de wizard Microsoft 365-installatie uitvoert

De wizard Setup leidt u door het installeren van de Microsoft 365-apps op uw computer, het toevoegen en verifiëren van uw domein, het toevoegen van gebruikers en het toewijzen van licenties aan hen en het verbinden van uw domein.

> [!NOTE]
> Als u [beheerdersrollen in Microsoft 365 voor Bedrijven](../add-users/assign-admin-roles.md) wilt toewijzen aan de gebruikers die u in de wizard toevoegt, u dat later op de pagina **Gebruikers** doen. 
  
Als u de wizard Setup niet voltooit, u de installatietaken op elk gewenst moment voltooien vanuit**de installatievan** [het beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2024339) > . Vanaf hier u e-mail en contactpersonen migreren vanuit een andere e-mailservice, het domein van uw beheerdersaccount wijzigen, uw factureringsgegevens beheren, gebruikers toevoegen of verwijderen, wachtwoorden opnieuw instellen en andere zakelijke functies uitvoeren. Zie [Verschillen tussen de installatiewizard van Microsoft 365 en de pagina Setup](o365-setup-wizard-and-setup-page.md)voor meer informatie over de verschillen tussen de wizard Setup en de installatiepagina . **Setup**

Als u ergens vastloopt, kunt u ons altijd bellen. [We zijn er om u te helpen.](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>Wanneer kunt u de installatiewizard beter niet gebruiken? Active Directory-synchronisatie en hybride omgevingen

Er zijn een paar scenario's die het migreren van gegevens of gebruikers uit on-premises omgevingen of het opzetten van een hybride systeem dat directory synchronisatie omvat omvatten. Als u in een van beide categorieën zit, volgt u de instructies in deze artikelen:
  
- Zie [Adreslijstsynchronisatie instellen voor Microsoft 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)en om inzicht te krijgen in de verschillende identiteitsmodellen in Microsoft 365, lees [Microsoft 365 identity en Azure Active Directory](https://docs.microsoft.com/office365/enterprise/about-office-365-identity)om adreslijstsynchronisatie in te stellen met uw on-premises Active Directory.

- Als u een hybride implementatie van Exchange wilt installeren, vindt u hier de volledige set instructies die u begeleiden bij de verschillende manieren waarop u een hybride implementatie van Exchange kunt installeren (inclusief het instellen van DNS-records): [Implementatieassistent van Exchange Server](https://aka.ms/exdeploy)

- Zie [Hybride zoeken in SharePoint](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint) als u een hybride SharePoint, en met name hybride zoek- en sitefuncties, wilt installeren.

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>Overstappen naar Microsoft 365 in één keer of in fasen

- **Wilt u uw organisatie in één keer verplaatsen naar Microsoft 365?** Als dat het zo is, bent u van plan om uw domein meteen naar Microsoft 365 te verplaatsen. Begin met het uitvoeren van de wizard Microsoft 365-instelling; het zal u vragen om uw domein in te stellen.

- **Wilt u geleidelijk overgaan naar Microsoft 365?** Als u gefaseerd naar Microsoft 365 wilt overstappen, slaat u de installatiewizard van Microsoft 365 over en overweegt u microsoft 365-functies in de volgende volgorde aan te nemen:

    1. [Voeg uw werknemers toe aan Microsoft 365,](../add-users/add-users.md) zodat ze de Office-apps kunnen downloaden en installeren.

    2. [Download en installeer de Office-apps](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) zodat u Word, Excel en PowerPoint op uw computer en apparaten kunt gebruiken.

    3. [Microsoft Teams instellen](#plan-for-teams) voor uw vergaderingen.

    4. [Verplaats uw inhoud naar Microsoft 365-cloudopslag](set-up-file-storage-and-sharing.md) (OneDrive- of SharePoint-teamsites).

    5. Wanneer u klaar bent, selecteert u in het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2024339) **Setup** in het linkernavigatiedeelvenster en gebruikt u de pagina **Setup** om uw domein [en e-mail](add-domain.md)te verplaatsen.

## <a name="check-that-your-devices-meet-system-requirements"></a>Controleren of uw apparaten aan systeemvereisten voldoen

Elke persoon in uw organisatie kan de Office 2016-reeks apps (Word, Excel, PowerPoint, enzovoort) installeren op maximaal vijf pc's en Macs. Raadpleeg de vereisten voor besturingssysteem en computer voor de installatie van [Office 2016-pakketten](https://go.microsoft.com/fwlink/?LinkId=534827) voor bedrijven.
  
Mobiele apps kunnen worden geïnstalleerd op iOS-, Android- en Windows-apparaten. Meer informatie over de ondersteuning voor mobiele apparaten en browsers vindt u in [Systeemvereisten voor Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>E-mail plannen

Als u van plan bent om van een bestaande e-mailservice naar Microsoft 365 te gaan, duurt het meestal twee dagen om over te stappen.
  
### <a name="plan-for-email-downtime"></a>E-maildowntime plannen
  
Als u Microsoft 365 gaat gebruiken voor uw e-mail:
  
- Als u uw zakelijke e-mailadres (zoals *\@rob contoso.com)* wilt verplaatsen van een andere e-mailservice naar Microsoft 365, moet u uw e-mail doorsturen om naar uw nieuwe Microsoft 365-postvak te worden bezorgd. U doet dit door **de gegevens van uw gebruikers migreren** te selecteren op de pagina **Setup,** waar we u stap voor stap begeleiden bij de updates die u bij uw domeinhost moet uitvoeren.

- Wanneer u de domeinhost hebt bijgewerkt, duurt het doorgaans een tot twee uur voordat de wijzigingen van kracht zijn. Maar wees ervan bewust dat het soms kan duren tot 72 uur voor de wijzigingen bij te werken op het internet.

- Omdat u mogelijk downtime voor e-mail hebt, raden we u aan om 's avonds of in een weekend over te schakelen naar Microsoft-e-mail wanneer u minder e-mails ontvangt.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>De overschakeling van bestaande e-mailberichten, contactpersonen en agenda plannen
  
Als u Microsoft 365 gaat gebruiken voor uw e-mailaccount, u uw bestaande e-mail, contactpersonen en agenda meenemen. Met de pagina **Setup** u uw bestaande e-mail en contactpersonen voor de meeste scenario's verplaatsen. We hebben ook stapsgewijze instructies voor het verplaatsen van één of meer postvakken.
  
|**Hoeveel postvakken?**|**Aanbeveling**|
|:-----|:-----|
|Slechts enkele  <br/> |Als u de pagina **Setup** niet wilt gebruiken om de postvakken te migreren, u eigenaren van het postvak laten migreren hun eigen e-mail en contactpersonen. Zie [E-mail en contactpersonen migreren naar Microsoft 365 voor bedrijven](migrate-email-and-contacts-admin.md).  <br/> |
|Meerdere  <br/> |Zie [G Suite-postvakken migreren naar Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)als u migreert vanuit Gmail.  <br/> Zie [Manieren om meerdere e-mailaccounts te migreren naar Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)als u migreert van een andere e-mailprovider, waaronder Exchange.  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Bestandsopslag en -migratie plannen

Microsoft 365 biedt cloudopslag voor particulieren, kleine organisaties en ondernemingen. Zie [Waar u documenten opslaan in Microsoft 365](https://support.office.com/article/c7c20284-bc94-47f4-9728-d28e9daf0790.aspx)voor meer informatie over wat u waar moet opslaan.
  
- **U honderden bestanden verplaatsen** naar [OneDrive](https://support.office.com/article/45114744-6D42-45CD-8975-F9617819BDEB.aspx) of naar een [SharePoint-teamsite.](https://support.office.com/article/da549fb1-1fcb-4167-87d0-4693e93cb7a0.aspx#__toc384119242) U kunt 100 bestanden tegelijk uploaden. Upload geen bestanden die groter zijn dan 2 GB, de maximale bestandsgrootte.
  
- **Als u enkele duizenden bestanden naar** Microsoft 365-opslag wilt verplaatsen, controleert u de [SharePoint Online-limieten](https://go.microsoft.com/fwlink/p/?LinkID=856113). Het is raadzaam om een hulpprogramma voor migratie te gebruiken of een [partner](https://go.microsoft.com/fwlink/?linkid=391089) in te schakelen om u te helpen met de migratie. Voor informatie over de migratie van een groot aantal bestanden raadpleegt u de [Gebruikershandleiding voor SharePoint Online- en OneDrive-migratie](https://go.microsoft.com/fwlink/?LinkId=723574).
  
## <a name="plan-for-teams"></a>Plannen voor teams

U Microsoft Teams gebruiken om te bellen naar andere mensen in uw organisatie die een abonnement hebben. Als uw organisatie bijvoorbeeld 10 personen heeft, u elkaar bellen en chaten met Teams zonder speciale instelling. Zie [Aan de slag met Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start)voor meer informatie.

Zie [Microsoft Teams uitrollen](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams)voor grotere organisaties of als u vanuit Skype voor Bedrijven, on-premises of hybride implementaties vertrekt.
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Integratie met Active Directory of andere software plannen

- **Wilt u integreren met uw on-premises Active Directory?** U uw on-premises Active Directory integreren met Microsoft 365 met Azure Active Directory Connect. Zie [Adreslijstsynchronisatie instellen voor Microsoft 365 voor](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)instructies.
  
- **Wilt u Microsoft 365 integreren met software van andere bedrijven?** Als u Microsoft 365 moet integreren met andere software in uw organisatie, raden we u aan [een partner in](https://go.microsoft.com/fwlink/?linkid=391089) te huren om u te helpen met uw implementatie.
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>Wilt u dat iemand u helpt bij het instellen van Microsoft 365?

- **Als u minder dan 50 werknemers hebt:**

  - **Vraag om hulp en wij bellen u**. Nadat u Microsoft 365 hebt gekocht, hebt u toegang tot het beheercentrum (u hoeft de installatie niet uit te voeren om er te komen). Selecteer onder aan het beheercentrum **hulp nodig?** Beschrijf het probleem en u wordt gebeld. 
  - **Bel [Microsoft 365 voor Zakelijke ondersteuning](../contact-support-for-business-products.md) met uw vragen.** We zijn er om u te helpen. 
  - **U kunt overwegen een [Microsoft-partner](https://go.microsoft.com/fwlink/?linkid=391089)** in te huren. Als u weinig tijd hebt of geavanceerde vereisten hebt (zoals het verplaatsen van duizenden bestanden naar Microsoft 365-cloudopslag of integratie met andere software), kan een ervaren partner een grote hulp zijn. 

- **Als u meer dan 50 werknemers hebt**, is het [FastTrack Onboarding Center](https://go.microsoft.com/fwlink/?LinkId=517115) beschikbaar om u te helpen met de implementatie. 
