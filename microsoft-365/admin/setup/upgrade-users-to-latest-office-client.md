---
title: Uw Office 365 voor bedrijven-gebruikers upgraden naar de nieuwste Office-client
f1.keywords:
- NOCSH
ms.author: janellem
author: janellem
manager: eliree
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.custom:
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: Meer informatie over het upgraden van uw gebruikers naar de nieuwste Office-client.
ms.openlocfilehash: 3d9c92a5362889db69926552848ba4c71d7c4c42
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42805992"
---
# <a name="upgrade-your-office-365-for-business-users-to-the-latest-office-client"></a>Uw Office 365 voor bedrijven-gebruikers upgraden naar de nieuwste Office-client

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 bereikt einde ondersteuning

Office 2010 loopt op 13 oktober 2020 aan de kant. Wanneer Office 2010 zijn einde van de ondersteuning bereikt, biedt Microsoft niet langer het volgende:

- Technische ondersteuning voor problemen

- Bugfixes voor problemen die worden ontdekt

- Beveiligingsoplossingen voor kwetsbaarheden die worden ontdekt

Zie [office 2010-eindondersteuningsroadmap](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap) voor meer informatie.

 **Is dit het juiste onderwerp voor jou?**
  
 Als u de beheerder bent die verantwoordelijk is voor het Office 365 voor Bedrijven-abonnement in uw organisatie, bent u op de juiste plaats. Beheerders zijn meestal verantwoordelijk voor taken zoals het beheren van gebruikers, het opnieuw instellen van wachtwoorden, het beheren van Office-installaties en het toevoegen of verwijderen van licenties.

 Als u geen beheerder bent en u een [Office voor thuisproduct](https://support.office.com/article/28cbc8cf-1332-4f04-9123-9b660abb629e.aspx#BKMK_OfficePlans) hebt, raadpleegt u [Hoe kan ik Office upgraden](https://support.office.com/article/ee68f6cf-422f-464a-82ec-385f65391350.aspx) voor informatie over het upgraden van uw oudere versie voor thuisgebruik van Office.

## <a name="getting-ready-to-upgrade"></a>Klaar om te upgraden

Als beheerder bepaalt u welke versie van Office-mensen in uw organisatie kan worden geïnstalleerd. We raden u ten zeerste aan om gebruikers in uw organisatie te helpen met oudere versies van Office, zoals Office 2010, Office 2013 of Office 2016-upgrade naar de nieuwste versie om te profiteren van de beveiligings- en productiviteitsverbeteringen.

## <a name="upgrade-steps"></a>Stappen bijwerken

Gebruik de onderstaande stappen om voor uw gebruikers een upgrade uit te voeren naar de meest recente Office-bureaubladclient. U wordt aangeraden deze stappen te lezen voordat u begint met het upgradeproces.
  
## <a name="step-1---check-system-requirements"></a>Stap 1: systeemvereisten controleren

[Controleer de systeemvereisten](https://products.office.com/office-system-requirements) voor Office om te controleren of uw apparaten compatibel zijn met de nieuwste versie van Office. Nieuwere versies van Office kunnen bijvoorbeeld niet worden geïnstalleerd op computers met Windows XP of Windows Vista.
  
> [!TIP]
> Als u gebruikers in uw organisatie hebt met oudere versies van Windows op hun pc's of laptops, raden we u aan te upgraden naar Windows 10. Windows 7 heeft het einde van de ondersteuning bereikt. Lees [Ondersteuning voor Windows 7 eindigt in januari 2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) voor meer info.

Bekijk de [windows 10-systeemvereisten](https://www.microsoft.com/windows/windows-10-specifications) om te zien of u hun besturingssystemen upgraden.

### <a name="check-application-compatibility"></a>Toepassingscompatibiliteit controleren

Om een succesvolle upgrade te garanderen is het raadzaam om na te gaan met welke Office-toepassingen, met inbegrip van VBA-scripts, macro's, externe invoegtoepassingen, complexe documenten en spreadsheets, u werkt en de compatibiliteit hiervan met de meest recente versie van Office te beoordelen.
  
Bijvoorbeeld: als u invoegtoepassingen van derden met uw huidige Office-installatie gebruikt, neemt u contact op met de fabrikant om te controleren of de invoegtoepassingen compatibel zijn met de nieuwste versie van Office.
  
## <a name="step-2---check-your-existing-subscription-plan"></a>Stap 2: uw bestaande abonnement controleren

In sommige Office 365-abonnementen is niet de volledige bureaubladversie van Office opgenomen en de stappen voor het uitvoeren van een upgrade verschillen als Office niet in uw abonnement is opgenomen.
  
Weet u niet zeker welk abonnement u hebt? Zie [Welk Office 365 voor Bedrijven-abonnement heb ik?](../admin-overview/what-subscription-do-i-have.md)
  
Als uw bestaande abonnement Office omvat, gaat u naar [Stap 3: Office verwijderen](#step-3---uninstall-office).
  
Als Office niet is opgenomen in uw bestaande abonnement, selecteert u een van de volgende opties:
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>Upgradeopties voor abonnementen waarin Office niet is opgenomen

 **Optie 1: Office-abonnementen overschakelen**

Stap over op een abonnement waarin Office is opgenomen. Zie [Overstappen op een ander Office 365 voor Bedrijven-abonnement](../../commerce/subscriptions/switch-to-a-different-plan.md).

**Optie 2: Individuele, eenmalige aankopen van Office kopen of Office kopen via een volumelicentie**

 - Koop een individuele, eenmalige aankoop van Office. Zie [Office &amp; Home Business](https://products.office.com/home-and-business) of Office [Professional](https://products.office.com/professional)

     OF

 - Koop meerdere exemplaren van Office via een volumelicentie. Zie [Suites vergelijken die beschikbaar zijn als volumelicentie](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).

## <a name="step-3---uninstall-office"></a>Stap 3: Office verwijderen

Voordat u de nieuwste versie van Office installeert, raden we u aan alle oudere versies van Office te verwijderen. Als u echter van gedachten verandert over het upgraden van Office, moet u de volgende instanties noteren waarin u Office niet opnieuw installeren nadat u het hebt geïnstalleerd.
  
We raden u aan als u invoegtoepassingen van derden hebt, contact op te nemen met de fabrikant om te zien of er een update is die werkt met de nieuwste versie van Office.

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>De te verwijderen versie van Office selecteren

- [Vanaf een pc](https://support.office.com/article/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8.aspx)

- [Van een Mac](https://support.office.com/article/eefa1199-5b58-43af-8a3d-b73dc1a8cae3.aspx)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>Bekende problemen bij het opnieuw installeren van oudere versies van Office nadat u het programma hebt verwijderd

 **Office via een volumelicentie** Als u geen toegang meer hebt tot de bronbestanden van deze volumelicentieversies van Office, u deze niet opnieuw installeren.

 **Office vooraf geïnstalleerd op uw computer** Als u geen schijf of productcode meer hebt (als Office er een heeft) u deze niet opnieuw installeren.

 **Niet-ondersteunde Office 365-abonnementen** Als uw exemplaar van Office is verkregen via beëindigde abonnementen, zoals Office 365 Voor Professionals en Kleine Bedrijven Premium of Office 365 Middelgrote bedrijven, u geen oudere versie van Office installeren, tenzij u de productcode hebt die bij uw abonnement is geleverd.

Als u de oudere versie van Office en de nieuwste versie graag beide geïnstalleerd wilt hebben, kunt u in [Install and use different versions of Office on the same PC](https://support.office.com/article/6ebb44ce-18a3-43f9-a187-b78c513788bf.aspx) (Meerdere versies van Office op dezelfde pc installeren en gebruiken) een lijst raadplegen met de versies waarvoor dit wordt ondersteund. Het is bijvoorbeeld handig over beide versies te beschikken, als u invoegtoepassingen van derden hebt geïnstalleerd met een oudere versie van Office en u niet zeker weet of deze compatibel zijn met de nieuwste versie.

## <a name="step-4---assign-office-licenses-to-users"></a>Stap 4: Office-licenties toewijzen aan gebruikers

Als u dit nog niet hebt gedaan, wijst u licenties toe aan gebruikers in uw organisatie die Office moeten installeren, raadpleegt u [Licenties toewijzen aan gebruikers in Office 365 voor Bedrijven](../manage/assign-licenses-to-users.md).
  
## <a name="step-5---install-office"></a>Stap 5: Office installeren

Nadat u hebt geverifieerd dat de gebruikers die u wilt upgraden, alle licenties hebben, is de laatste stap om ze Office te laten installeren, Office [downloaden en installeren of opnieuw installeren op uw pc of Mac.](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx)
  
> [!TIP]
> Zie [Instellingen voor softwaredownloaden beheren in Office 365](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365)als u niet wilt dat uw gebruikers Office zelf installeren. U het [Hulpprogramma voor office-implementatie](https://docs.microsoft.com/DeployOffice/overview-of-the-office-2016-deployment-tool) gebruiken om de Office-software naar uw lokale netwerk te downloaden en Office vervolgens te implementeren met behulp van de softwareimplementatiemethode die u doorgaans gebruikt.
