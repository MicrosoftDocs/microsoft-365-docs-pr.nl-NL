---
title: De installatie van Office 365 voor Bedrijven plannen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
description: Meer informatie over wat u moet doen om uw Office 365 voor Bedrijven in te stellen.
ms.openlocfilehash: 3b38f0092b323175c6a12170105e781fab21934d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42811386"
---
# <a name="plan-your-setup-of-office-365-for-business"></a>De installatie van Office 365 voor Bedrijven plannen

Dit artikel is bedoeld voor personen met een Office 365 Business-abonnement.
  
Er zijn een paar dingen die u moet beslissen en informatie die u bij de hand moet hebben, voordat u uw organisatie verplaatst naar Office 365.
  
## <a name="info-to-have-on-hand-before-you-run-the-office-365-setup-wizard"></a>Gegevens die u bij de hand moet hebben voordat u de installatiewizard van Office 365 uitvoert

U hebt de volgende gegevens nodig op het moment dat u de installatiewizard van Office 365 gaat uitvoeren en uw domein wilt overzetten naar Office 365:
  
- Lijst met personen die u wilt toevoegen aan Office 365. Zelfs als u ze al hebt toegevoegd aan Office 365, dan nog moet u hun namen hier invoeren wanneer u uw domeingegevens bijwerkt.

- Hoe u uw medewerkers gaat informeren over hun gebruikers-id en wachtwoord voor Office 365, zodat ze zich kunnen aanmelden. Gaat u ze bellen om deze gegevens door te geven? Of stuurt u deze gegevens naar hun persoonlijke e-mailadres? Ze hebben immers geen toegang tot hun e-mail van Office 365, dus die kunt u niet gebruiken.

- Als u een domeinnaam voor uw organisatie hebt (zoals contoso.com) **en** u van plan bent Office 365-e-mail te gebruiken, moet u weten waar uw domein is geregistreerd en u hebt aanmeldingsgegevens.

## <a name="what-happens-when-you-run-the-office-365-setup-wizard"></a>Wat gebeurt er wanneer u de installatiewizard van Office 365 uitvoert

De wizard Setup leidt u door het installeren van de Office 365-apps op uw computer, het toevoegen en verifiëren van uw domein, het toevoegen en toewijzen van licenties aan hen en het verbinden van uw domein.

> [!NOTE]
> Als u [beheerdersrollen in Office 365 voor Bedrijven](../add-users/assign-admin-roles.md) moet toewijzen aan de gebruikers die u in de wizard toevoegt, u dat later doen op de pagina **Gebruikers.** 
  
Als u de wizard Setup niet voltooit, u op elk gewenst moment installatietaken uitvoeren vanuit [het beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2024339) > **Setup**. Vanaf hier u e-mail en contactpersonen migreren vanuit een andere e-mailservice, het domein van uw beheerdersaccount wijzigen, uw factureringsgegevens beheren, gebruikers toevoegen of verwijderen, wachtwoorden opnieuw instellen en andere zakelijke functies uitvoeren. Zie [Verschillen tussen de wizard Office 365-instellingen en de pagina Setup](o365-setup-wizard-and-setup-page.md)voor meer informatie over de verschillen tussen de wizard Setup en de pagina **Setup.**

Als u ergens vastloopt, kunt u ons altijd bellen. [We zijn er om u te helpen.](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>Wanneer kunt u de installatiewizard beter niet gebruiken? Active Directory-synchronisatie en hybride omgevingen

Er zijn een paar scenario's die migrerende gegevens of gebruikers uit on-premises omgevingen omvatten of het instellen van een hybride systeem dat adreslijstsynchronisatie bevat. Als u in beide categorieën valt, volgt u de instructies in deze artikelen:
  
- Voor het instellen van adreslijstsynchronisatie met uw on-premises Active Directory, leest u [Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization). Voor meer informatie over de verschillende identiteitsmodellen in Office 365, leest u [Understanding Office 365 identity and Azure Active Directory](https://docs.microsoft.com/office365/enterprise/about-office-365-identity).

- Als u een hybride implementatie van Exchange wilt installeren, vindt u hier de volledige set instructies die u begeleiden bij de verschillende manieren waarop u een hybride implementatie van Exchange kunt installeren (inclusief het instellen van DNS-records): [Implementatieassistent van Exchange Server](https://aka.ms/exdeploy)

- Zie [Hybride zoeken in SharePoint](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint) als u een hybride SharePoint, en met name hybride zoek- en sitefuncties, wilt installeren.

## <a name="move-to-office-365-all-at-once-or-in-stages"></a>Stap in één keer of in fasen naar Office 365

- **Wilt u uw organisatie in één keer verplaatsen naar Office 365?** Als dat het is, u uw domein meteen verplaatsen naar Office 365. Begin met het uitvoeren van de wizard Office 365-installatie; het zal u vragen om uw domein in te stellen.

- **Wilt u geleidelijk overstappen naar Office 365?** Als u in fasen wilt overstappen op Office 365, slaat u de installatiewizard van Office 365 over en kunt u overwegen de Office 365-functies in de volgende volgorde te gaan gebruiken:

    1. [Voeg uw werknemers toe aan Office 365](../add-users/add-users.md) zodat zij de Office-apps kunnen downloaden en installeren.

    2. [Download en installeer de Office-apps](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) zodat u Word, Excel en PowerPoint op uw computer en apparaten kunt gebruiken.

    3. [Stel Microsoft Teams in](#plan-for-teams) om te gebruiken voor uw vergaderingen.

    4. [Verplaats uw inhoud naar Office 365-cloudopslag](set-up-file-storage-and-sharing.md) (OneDrive- of SharePoint-teamsites).

    5. Wanneer u klaar bent, selecteert u in het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2024339) **Setup** in het linkernavigatiedeelvenster en gebruikt u de pagina **Setup** om [uw domein en e-mail](add-domain.md)te verplaatsen .

## <a name="check-that-your-devices-meet-system-requirements"></a>Controleren of uw apparaten aan systeemvereisten voldoen

Elke persoon in uw organisatie kan de Office 2016-reeks apps (Word, Excel, PowerPoint, enzovoort) installeren op maximaal vijf pc's en Macs. Raadpleeg de vereisten voor besturingssysteem en computer voor de installatie van [Office 2016-pakketten](https://go.microsoft.com/fwlink/?LinkId=534827) voor bedrijven.
  
Mobiele apps kunnen worden geïnstalleerd op iOS-, Android- en Windows-apparaten. Meer informatie over de ondersteuning voor mobiele apparaten en browsers vindt u in [Systeemvereisten voor Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>E-mail plannen

Als u van plan bent om van een bestaande e-mailservice naar Office 365 te gaan, duurt het meestal twee dagen om over te stappen.
  
### <a name="plan-for-email-downtime"></a>E-maildowntime plannen
  
Als u Office 365 gaat gebruiken voor uw e-mail:
  
- Als u uw zakelijke e-mailadres (zoals *rob@contoso.com)* wilt verplaatsen van een andere e-mailservice naar Office 365, moet u uw e-mail naar uw nieuwe Office 365-postvak sturen. U doet dit door **de gegevens van uw gebruikers** migreren op de pagina **Setup** te selecteren, waarbij we u stap voor stap door de updates begeleiden die u bij uw domeinhost moet uitvoeren.

- Wanneer u de domeinhost hebt bijgewerkt, duurt het doorgaans een tot twee uur voordat de wijzigingen van kracht zijn. Maar wees ervan bewust dat het soms kan duren tot 72 uur voor de wijzigingen bij te werken op het internet.

- Omdat er mogelijk e-maildowntime zal zijn, wordt u geadviseerd de overschakeling naar e-mail van Office 365 te plannen tijdens een avond of weekend wanneer u minder e-mailberichten ontvangt.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>De overschakeling van bestaande e-mailberichten, contactpersonen en agenda plannen
  
Als u Office 365 voor uw e-mailaccount wilt gebruiken, kunt u uw bestaande e-mail, contactpersonen en agenda meeverhuizen. Met de pagina **Setup** u uw bestaande e-mail en contactpersonen verplaatsen voor de meeste scenario's. We hebben ook stapsgewijze instructies voor het verplaatsen van één of meer postvakken.
  
|**Hoeveel postvakken?**|**Aanbeveling**|
|:-----|:-----|
|Slechts enkele  <br/> |Als u de pagina **Setup** niet wilt gebruiken om de postvakken te migreren, u postvakeigenaren hun eigen e-mail en contactpersonen laten migreren. Zie [E-mail en contactpersonen migreren naar Office 365 voor Bedrijven](migrate-email-and-contacts-admin.md)  <br/> |
|Meerdere  <br/> |Zie [G Suite-postvakken migreren naar Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)als u migreert vanuit Gmail.  <br/> Zie [Manieren om meerdere e-mailaccounts te migreren naar Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)als u migreert van een andere e-mailprovider, waaronder Exchange.  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Bestandsopslag en -migratie plannen

Office 365 biedt cloudopslag voor particulieren, kleine organisaties en ondernemingen. Zie [Waar u documenten kunt opslaan in Office 365](https://support.office.com/article/c7c20284-bc94-47f4-9728-d28e9daf0790.aspx) voor richtlijnen over wat u waar kunt opslaan.
  
- **U honderden bestanden verplaatsen** naar [OneDrive](https://support.office.com/article/45114744-6D42-45CD-8975-F9617819BDEB.aspx) of naar een [SharePoint-teamsite.](https://support.office.com/article/da549fb1-1fcb-4167-87d0-4693e93cb7a0.aspx#__toc384119242) U kunt 100 bestanden tegelijk uploaden. Upload geen bestanden die groter zijn dan 2 GB, de maximale bestandsgrootte.
  
- **Als u enkele duizenden bestanden wilt verplaatsen** naar Office 365-opslag, bekijk dan de [Limieten voor SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=856113). Het is raadzaam om een hulpprogramma voor migratie te gebruiken of een [partner](https://go.microsoft.com/fwlink/?linkid=391089) in te schakelen om u te helpen met de migratie. Voor informatie over de migratie van een groot aantal bestanden raadpleegt u de [Gebruikershandleiding voor SharePoint Online- en OneDrive-migratie](https://go.microsoft.com/fwlink/?LinkId=723574).
  
## <a name="plan-for-teams"></a>Plan voor teams

U Microsoft Teams gebruiken om te bellen naar andere mensen in uw organisatie die een abonnement hebben. Als uw organisatie bijvoorbeeld 10 personen heeft, u elkaar bellen en e-chaten met Teams zonder speciale instellingen. Zie Aan de [slag met Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start)voor meer informatie.

Zie [Microsoft Teams voor](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams)grotere organisaties of als u begint met Skype voor Bedrijven, on-premises of hybride implementaties.
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Integratie met Active Directory of andere software plannen

- **Wilt u integreren met uw on-premises Active Directory?** Met behulp van Azure Active Directory Connect kunt u uw on-premises Active Directory integreren met Office 365. Zie [Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) voor instructies .
  
- **Wilt u Office 365 integreren met software van andere fabrikanten?** Als u Office 365 moet integreren met andere software in uw organisatie, raden we u aan [een partner](https://go.microsoft.com/fwlink/?linkid=391089) in te huren om u te helpen bij uw implementatie.
  
## <a name="do-you-want-someone-to-help-you-set-up-office-365"></a>Wilt u dat iemand u helpt bij het instellen van Office 365?

- **Als u minder dan 50 werknemers hebt:**

  - **Vraag om hulp en wij bellen u**. Nadat u Office 365 hebt gekocht, hebt u toegang tot het beheercentrum (u hoeft de installatie niet uit te voeren om er bij te komen). Selecteer Hulp nodig onder aan het **beheercentrum?** Beschrijf het probleem en u wordt gebeld. 
  - **Bel [Office 365 voor Bedrijven-ondersteuning](../contact-support-for-business-products.md) met uw vragen**. We zijn er om u te helpen. 
  - **U kunt overwegen een [Microsoft-partner](https://go.microsoft.com/fwlink/?linkid=391089)** in te huren. Als u weinig tijd hebt of ingewikkelde vereisten (zoals het overzetten van duizenden bestanden naar de cloudopslag van Office 365 of integratie met andere software), kan een ervaren partner uitkomst bieden. 

- **Als u meer dan 50 werknemers hebt**, is het [FastTrack Onboarding Center](https://go.microsoft.com/fwlink/?LinkId=517115) beschikbaar om u te helpen met de implementatie. 
