---
title: Een connector instellen voor het archiveren van WeChat-gegevens in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Een verbindingslijn instellen en gebruiken in het Microsoft 365 compliancecentrum om WeChat-gegevens te importeren en te archiveren in Microsoft 365.
ms.openlocfilehash: 3ee858cd09c1b6c7bd29dc5e2162753df9f5544a
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861625"
---
# <a name="set-up-a-connector-to-archive-wechat-data-preview"></a>Een connector instellen voor het archiveren van WeChat-gegevens (voorbeeld)

Gebruik de TeleMessage-connector in het Microsoft 365 compliancecentrum om WeChat- en WeCom-gesprekken, chats, bijlagen, bestanden en teruggeroepen berichten te importeren en te archiveren. Nadat u een verbindingslijn hebt ingesteld en geconfigureerd, maakt deze verbinding met het TeleMessage-account van uw organisatie en importeert u de mobiele communicatie van werknemers met de TeleMessage WeChat-archiver naar postvakken in Microsoft 365.

Nadat weChat Archiver-connectorgegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties zoals Litigation Hold, eDiscovery, In-Place Archiving, Auditing, Communicatie compliance en Microsoft 365 bewaarbeleid toepassen op WeChat-communicatiegegevens. U kunt bijvoorbeeld zoeken in WeChat-communicatie met Inhoud zoeken of het postvak met de WeChat Archiver-connectorgegevens koppelen aan een bewaarder in een Advanced eDiscovery geval. Met een WeChat Archiver-connector voor het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan corporate governance-voorschriften en regelgevingsbeleid.

## <a name="overview-of-archiving-wechat-communication-data"></a>Overzicht van het archiveren van WeChat-communicatiegegevens

In het volgende overzicht wordt uitgelegd hoe het gebruik van een verbindingslijn voor het archiveren van WeChat-communicatiegegevens in Microsoft 365.

![Archiveringswerkstroom voor WeChat Archiver-gegevens](../media/WeChatConnectorWorkflow.png)

1. Uw organisatie werkt met TeleMessage om een WeChat Archiver-connector in te stellen.

2. In realtime worden de WeChat-gegevens van uw organisatie gekopieerd naar de TeleMessage-site.

3. De WeChat Archiver-connector die u in het Microsoft 365-compliancecentrum maakt, maakt elke dag verbinding met de TeleMessage-site en brengt de e-mailberichten van de afgelopen 24 uur over naar een beveiligd Azure Storage-gebied in de Microsoft Cloud.

4. De verbindingslijn importeert de mobiele communicatie-items naar het postvak van een specifieke gebruiker. Er wordt een nieuwe map met de naam WeChat Archiver gemaakt in het postvak van de specifieke gebruiker en de items worden er in geïmporteerd. De verbindingslijn wordt toegewezen met behulp van de waarde van de eigenschap *E-mailadres van de* gebruiker. Elk e-mailbericht bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer van het e-mailbericht. Naast automatische gebruikerstoewijzing met  de waarde van de eigenschap E-mailadres van de gebruiker, kunt u ook een aangepaste toewijzing definiëren door een CSV-toewijzingsbestand te uploaden. Dit toewijzingsbestand moet het mobiele nummer van de gebruiker en het bijbehorende Microsoft 365 postvak voor elke gebruiker bevatten. Als u automatische gebruikerstoewijzing inschakelen en een aangepaste toewijzing biedt, wordt voor elk e-mailitem eerst naar aangepast toewijzingsbestand gekijken. Als er geen geldige Microsoft 365 wordt gevonden die overeenkomt met het mobiele nummer van een gebruiker, gebruikt de verbindingslijn de eigenschap E-mailadres van de gebruiker van het e-mailitem. Als de verbindingslijn geen geldige Microsoft 365-gebruiker vindt in het  aangepaste toewijzingsbestand of de eigenschap van het e-mailadres van het e-mailitem, wordt het item niet geïmporteerd.

## <a name="before-you-set-up-a-connector"></a>Voordat u een verbindingslijn in stelt

- Werk met TeleMessage om een WeChat-archiefconnector in te stellen. Zie De [WeChat-archiver voor TeleMessage](https://www.telemessage.com/microsoft-365-activation-for-wechat-archiver/)activeren voor meer Microsoft 365.

- Stel een TeleMessage-connector in voor Microsoft 365 en krijg een geldig bedrijfsbeheeraccount. Zie Order voor mobiel [archiveren Microsoft 365 voor meer informatie.](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-microsoft-365/)

- Registreer alle gebruikers die WeChat moeten archiveren in het TeleMessage-account met hetzelfde e-mailadres dat wordt gebruikt voor het Microsoft 365 account van de gebruiker.

- U moet de Tencent WeCom-app installeren op de mobiele telefoons van gebruikers in uw organisatie en deze activeren. Met de WeCom-app kunnen gebruikers communiceren en chatten met andere WeChat- en WeCom-gebruikers.

- De gebruiker die een WeChat Archiver-connector maakt in het Microsoft 365 compliancecentrum, moet de rol Postvak importeren exporteren in Exchange Online. Dit is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in het compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

- Deze gegevensconnector is beschikbaar in GCC omgevingen in de Microsoft 365 amerikaanse overheidscloud. Toepassingen en services van derden kunnen betrekking hebben op het opslaan, verzenden en verwerken van klantgegevens van uw organisatie op systemen van derden die buiten de Microsoft 365-infrastructuur vallen en daarom niet worden gedekt door de toezeggingen van Microsoft 365 compliance en gegevensbescherming. Microsoft geeft niet aan dat het gebruik van dit product om verbinding te maken met toepassingen van derden betekent dat deze toepassingen van derden compatibel zijn met FEDRAMP.

## <a name="create-a-wechat-archiver-connector"></a>Een WeChat Archiver-connector maken

Volg de stappen in deze sectie om een WeChat Archiver-connector te maken in het Microsoft 365 compliancecentrum. De connector gebruikt de informatie die u verstrekt om verbinding te maken met de TeleMessage-site en weChat-communicatiegegevens over te brengen naar de bijbehorende gebruikerspostvakken in Microsoft 365.

1. Ga naar <https://compliance.microsoft.com> en klik vervolgens op **Gegevensconnectoren**  >  **WeChat Archiver.**

2. Klik op **de pagina Productbeschrijving van WeChat Archiver** op **Verbindingslijn toevoegen**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer op de pagina Aanmelden bij **TeleMessage** onder Stap 3 de vereiste informatie in de volgende vakken in en klik vervolgens op **Volgende**.

    - **Gebruikersnaam:** uw gebruikersnaam voor TeleMessage.

    - **Wachtwoord:** Uw TeleMessage-wachtwoord.

5. Nadat de verbindingslijn is gemaakt, kunt u het pop-upvenster sluiten naar de volgende pagina.

6. Schakel op **de pagina Gebruikerstoewijzing** automatische gebruikerstoewijzing in. U kunt ook een aangepast CSV-bestand voor gebruikerstoewijzing uploaden.

7. Klik **op Volgende,** bekijk de instellingen en klik vervolgens **op Voltooien** om de verbindingslijn te maken.

8. Ga naar het **tabblad Connectors** op de pagina **Gegevensconnectors** om de voortgang van het importproces voor de nieuwe verbindingslijn te bekijken.

## <a name="known-issues"></a>Bekende problemen

- Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.
