---
title: De installatie van Microsoft 365 voor bedrijven plannen
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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Meer informatie over de vereisten en aandachtspunten voor de overstap naar Microsoft 365 voor bedrijven.
ms.openlocfilehash: fd8d644e0c207165c7ecb6e72cca8bb4318edf09
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350325"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>De installatie van Microsoft 365 voor bedrijven plannen

Dit artikel is bedoeld voor personen die zijn geabonneerd op een abonnement op Microsoft 365 voor bedrijven.
  
Voordat u uw organisatie naar Microsoft 365 overbrengt, zijn er vereisten om te vergaderen, informatie die u nodig hebt en beslissingen die u moet nemen.


  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>Gegevens die u bij de hand moet hebben voordat u de installatiewizard uitvoert

Wanneer u klaar bent om de wizard Setup uit te voeren en uw domein te verplaatsen naar Microsoft 365, hebt u de volgende informatie nodig:
  
- Lijst met personen die u wilt toevoegen aan Microsoft 365. Ook al hebt u ze al toegevoegd aan Microsoft 365, als u uw domeingegevens bijwerkt, moet u de namen ervan opgeven.

- Hoe u op de hoogte wordt gesteld van de gebruikers-ID en het wachtwoord van uw werknemers, zodat ze zich kunnen aanmelden. Gaat u ze bellen om deze gegevens door te geven? Of stuurt u deze gegevens naar hun persoonlijke e-mailadres? Ze hebben geen toegang tot hun e-mail, dus u kunt deze niet gebruiken.

- Als u een domeinnaam voor uw organisatie hebt (zoals contoso.com) **en** u een abonnement hebt op Microsoft-e-mail, moet u weten waar uw domein is geregistreerd en aanmeldingsgegevens hebben.

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>Wat gebeurt er wanneer u de installatiewizard van Microsoft 365 uitvoert

De installatiewizard begeleidt u bij het installeren van de Microsoft 365-apps op uw computer, het toevoegen en bevestigen van uw domein, het toevoegen van gebruikers en het toewijzen van licenties, en het verbinden van uw domein.

> [!NOTE]
> Als u [beheerdersrollen wilt toewijzen aan Microsoft 365 voor bedrijven](../add-users/assign-admin-roles.md) voor de gebruikers die u in de wizard toevoegt, kunt u dat later doen op de pagina **gebruikers** . 
  
Als u de installatiewizard niet voltooit, kunt u de installatietaken op elk moment voltooien vanuit het instellen van het [Beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2024339)  >  **Setup**. Van hieruit kunt u e-mail en contactpersonen migreren van een andere e-mail service, het domein van uw beheerdersaccount wijzigen, uw factureringsgegevens beheren, gebruikers toevoegen of verwijderen, wachtwoorden opnieuw instellen en andere zakelijke functies uitvoeren. Zie voor meer informatie over de verschillen tussen de wizard Setup en de **instellings** pagina [verschillen tussen de installatiewizard van Microsoft 365 en de instellings pagina](o365-setup-wizard-and-setup-page.md).

Als u ergens vastloopt, kunt u ons altijd bellen. [We zijn er om u te helpen.](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>Wanneer kunt u de installatiewizard beter niet gebruiken? Active Directory-synchronisatie en hybride omgevingen

Er zijn een paar scenario's waarbij u gegevens of gebruikers migreert vanuit een on-premises omgeving of een hybride systeem met adreslijstsynchronisatie gaat instellen. Als u in een van de categorieën bent, volgt u de instructies in de volgende artikelen:
  
- Als u adreslijstsynchronisatie wilt instellen voor uw on-premises Active Directory, raadpleegt u [adreslijstsynchronisatie instellen voor Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)en begrijpt u de verschillende identiteits modellen in microsoft 365 voor informatie [over Microsoft 365-identiteit en Azure Active Directory](https://docs.microsoft.com/microsoft-365/enterprise/about-microsoft-365-identity).

- Als u een hybride implementatie van Exchange wilt installeren, vindt u hier de volledige set instructies die u begeleiden bij de verschillende manieren waarop u een hybride implementatie van Exchange kunt installeren (inclusief het instellen van DNS-records): [Implementatieassistent van Exchange Server](https://aka.ms/exdeploy)

- Zie [Hybride zoeken in SharePoint](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint) als u een hybride SharePoint, en met name hybride zoek- en sitefuncties, wilt installeren.

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>In één keer of in fasen overstappen op Microsoft 365

- **Wilt u uw organisatie allemaal tegelijk naar Microsoft 365 verplaatsen?** Als dit het geval is, gaat u van plan om uw domein direct naar Microsoft 365 te verplaatsen. Begin met het uitvoeren van de wizard Setup van Microsoft 365. u wordt gevraagd uw domein in te stellen.

- **Wilt u geleidelijk overstappen op Microsoft 365?** Als u wilt overstappen op Microsoft 365 in fasen, gaat u verder met de installatiewizard van Microsoft 365 en dient u de Microsoft 365-functies in de volgende volgorde te nemen:

    1. [Voeg uw werknemers toe aan Microsoft 365](../add-users/add-users.md) zodat ze de Office-apps kunnen downloaden en installeren.

    2. [Download en installeer de Office-apps](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) zodat u Word, Excel en PowerPoint op uw computer en apparaten kunt gebruiken.

    3. [Stel Microsoft teams](#plan-for-teams) in die u wilt gebruiken voor uw vergaderingen.

    4. [Verplaats uw inhoud naar Microsoft 365 Cloud Storage](set-up-file-storage-and-sharing.md) (OneDrive-of SharePoint-Team sites).

    5. Wanneer u klaar bent, selecteert u in het [Beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2024339) **instellingen** in het linker navigatiedeelvenster en gebruikt u de **installatie** pagina om [uw domein en e-mail te verplaatsen](add-domain.md).

## <a name="check-that-your-devices-meet-system-requirements"></a>Controleren of uw apparaten aan systeemvereisten voldoen

Iedereen in uw organisatie kan de Office 2016-Suite met apps (Word, Excel, PowerPoint, enzovoort) installeren op maximaal vijf Pc's of Macs. Raadpleeg de vereisten voor besturingssysteem en computer voor de installatie van [Office 2016-pakketten](https://go.microsoft.com/fwlink/?LinkId=534827) voor bedrijven.
  
Mobiele apps kunnen worden geïnstalleerd op iOS-, Android-en Windows-apparaten. Meer informatie over de ondersteuning voor mobiele apparaten en browsers vindt u in [Systeemvereisten voor Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>E-mail plannen

Als u van een bestaande e-mail service wilt overstappen op Microsoft 365, duurt dit meestal twee dagen.
  
### <a name="plan-for-email-downtime"></a>E-maildowntime plannen
  
Ga als volgt te werk als u Microsoft 365 wilt gebruiken voor uw e-mail:
  
- Als u uw zakelijke e-mailadres (zoals *rob \@ contoso.com*) van een andere e-mail service naar Microsoft 365 wilt verplaatsen, moet u uw e-mail naar uw nieuwe Microsoft 365-postvak laten afleveren. Dit doet u door de **gegevens van uw gebruikers migreren** te selecteren op de **installatie** pagina, waar u door de updates wordt begeleid die u moet maken bij uw domein host, stapsgewijs.

- Wanneer u de domeinhost hebt bijgewerkt, duurt het doorgaans een tot twee uur voordat de wijzigingen van kracht zijn. Het kan soms tot 72 uur duren voordat de wijzigingen zijn bijgewerkt op internet.

- Aangezien u mogelijk een e-mail hebt ontvangen, kunt u het beste overstappen op Microsoft-e-mailberichten in een avond of weekend wanneer u minder e-mailberichten ontvangt.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>De overschakeling van bestaande e-mailberichten, contactpersonen en agenda plannen
  
Als u Microsoft 365 voor uw e-mailaccount gaat gebruiken, kunt u uw bestaande e-mail, contactpersonen en agenda met u meenemen. Met de **instellings** pagina kunt u uw bestaande e-mail en contactpersonen voor de meeste scenario's verplaatsen. We hebben ook stapsgewijze instructies voor het verplaatsen van één of meer postvakken.
  
|**Hoeveel postvakken?**|**Aanbeveling**|
|:-----|:-----|
|Slechts enkele  <br/> |Als u de **installatie** pagina niet wilt gebruiken om de postvakken te migreren, kunt u de eigenaar van het postvak hun eigen e-mail en contactpersonen laten migreren. Zie [e-mail en contactpersonen migreren naar Microsoft 365 voor bedrijven](migrate-email-and-contacts-admin.md).  <br/> |
|Meerdere  <br/> |Als u migreert vanuit Gmail, raadpleegt u [G suite-postvakken migreren naar Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes).  <br/> Als u migreert van een andere e-mailprovider, met inbegrip van Exchange, raadpleeg dan [manieren om meerdere e-mailaccounts te migreren naar Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Bestandsopslag en -migratie plannen

Microsoft 365 biedt cloudopslag voor particulieren, kleine bedrijven en ondernemingen. Zie voor meer informatie over waar [u documenten kunt opslaan in Microsoft 365](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790).
  
- **U kunt honderden bestanden verplaatsen** naar [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) of naar een [SharePoint-Team site](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242). U kunt 100 bestanden tegelijk uploaden. Upload geen bestanden die groter zijn dan 2 GB, de maximale bestandsgrootte.
  
- **Als u meerdere duizend bestanden** naar microsoft 365-opslag wilt verplaatsen, raadpleegt u de [limieten voor SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=856113). Het is raadzaam om een hulpprogramma voor migratie te gebruiken of een [partner](https://go.microsoft.com/fwlink/?linkid=391089) in te schakelen om u te helpen met de migratie. Voor informatie over de migratie van een groot aantal bestanden raadpleegt u de [Gebruikershandleiding voor SharePoint Online- en OneDrive-migratie](https://go.microsoft.com/fwlink/?LinkId=723574).
  
## <a name="plan-for-teams"></a>Plannen voor teams

U kunt Microsoft teams gebruiken om te bellen naar andere personen in uw organisatie die deelnemen aan uw abonnement. Als uw organisatie 10 personen bevat, kunt u bijvoorbeeld met behulp van teams bellen en chatten zonder speciale instellingen. Zie [aan de slag met Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start)voor meer informatie.

Zie voor meer [informatie over hoe u Microsoft teams kunt uitrollen](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams), of als u gaat beginnen met Skype voor bedrijven, on-premises of hybride implementaties.
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Integratie met Active Directory of andere software plannen

- **Wilt u integreren met uw on-premises Active Directory?** U kunt uw on-premises Active Directory integreren met Microsoft 365 met behulp van Azure Active Directory Connect. Zie [adreslijstsynchronisatie voor Microsoft 365 instellen](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)voor instructies.
  
- **Wilt u Microsoft 365 integreren met software die door andere bedrijven is gemaakt?** Als u Microsoft 365 moet integreren met andere software in uw organisatie, kunt u het beste [een partner inhuren](https://go.microsoft.com/fwlink/?linkid=391089) om u te helpen met de implementatie.
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>Wilt u dat iemand u helpt bij het instellen van Microsoft 365?

- **Als u minder dan 50 werknemers hebt:**

  - **Vraag om hulp en wij bellen u**. Wanneer u Microsoft 365 koopt, hebt u toegang tot het Beheercentrum (u hoeft Setup niet uit te voeren om het te openen). Selecteer onder in het Beheercentrum de optie **hulp nodig?** Beschrijf het probleem en u wordt gebeld. 
  - **Neem contact op met de [ondersteuning van microsoft 365 for Business](../contact-support-for-business-products.md) met uw vragen**. We zijn er om u te helpen. 
  - **U kunt overwegen een [Microsoft-partner](https://go.microsoft.com/fwlink/?linkid=391089)** in te huren. Als u kort op tijd bent, of als u een grote oplossing hebt (zoals het verplaatsen van duizenden bestanden naar Microsoft 365 Cloud Storage of integratie met andere software), kunt u een ervaren partner een uitgebreide Help maken. 

- **Als u meer dan 50 werknemers hebt**, is het [FastTrack Onboarding Center](https://go.microsoft.com/fwlink/?LinkId=517115) beschikbaar om u te helpen met de implementatie. 
