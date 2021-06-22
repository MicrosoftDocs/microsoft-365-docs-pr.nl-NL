---
title: Een verbindingslijn instellen voor het archiveren van communicatiegegevens van De telegraaf in Microsoft 365
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
description: Beheerders kunnen een TeleMessage-connector instellen voor het importeren en archiveren van Communicatiegegevens van Telegram in Microsoft 365. Op deze manier kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365, zodat u compliancefuncties, zoals juridische bewaring, inhoudszoekbeleid en bewaarbeleid, kunt gebruiken om de gegevens van derden van uw organisatie te beheren.
ms.openlocfilehash: d3fbe02dce56bec01d66351aa69500a3d5d93a37
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054844"
---
# <a name="set-up-a-connector-to-archive-telegram-communications-data-preview"></a>Een verbindingslijn instellen voor het archiveren van Communicatiegegevens van Telegram (voorbeeld)

Gebruik de TeleMessage-connector in de Microsoft 365-compliancecentrum om Chats, bijlagen, bestanden en verwijderde berichten en oproepen van Telegram te importeren en te archiveren. Nadat u een verbindingslijn hebt ingesteld en geconfigureerd, maakt deze verbinding met het TeleMessage-account van uw organisatie en importeert u de mobiele communicatie van werknemers met behulp van de Archiefman van Telegram naar postvakken in Microsoft 365.

Nadat gegevens van de Verbindingslijn van De archieflijn van Telegram zijn opgeslagen in postvakken van gebruikers, kunt u Microsoft 365 compliancefuncties zoals Litigation Hold, Inhoud zoeken en Microsoft 365 bewaarbeleid toepassen op communicatiegegevens van Telegram. U kunt bijvoorbeeld zoeken in communicatie via De communicatie van Telegram met Inhoud zoeken of het postvak met de connectorgegevens van De archieffunctie van Telegram koppelen aan een bewaarder in een Advanced eDiscovery geval. Als u een Verbindingslijn voor Het archief van Telegram gebruikt om gegevens te importeren en te archiveren in Microsoft 365 kan uw organisatie voldoen aan corporate governance-voorschriften en regelgevingsbeleid.

## <a name="overview-of-archiving-telegram-communications-data"></a>Overzicht van het archiveren van communicatiegegevens van Telegram

In het volgende overzicht wordt uitgelegd hoe het gebruik van een verbindingslijn voor het archiveren van communicatiegegevens van De telegram in een Microsoft 365.

![Communicatiearchiveringswerkstroom van Telegram](../media/TelegramConnectorWorkflow.png)

1. Uw organisatie werkt met TeleMessage om een Verbindingslijn voor De Archiefman van Het archief van Het telegram in te stellen. Zie [TeleMessage Telegram Archiver](https://www.telemessage.com/microsoft-365-activation-for-telegram-archiver/)activeren voor meer Microsoft 365.

2. In realtime worden de Gegevens van De TeleMessage van uw organisatie gekopieerd naar de TeleMessage-site.

3. De Verbindingslijn Voor archief van Telegram die u in de Microsoft 365-compliancecentrum maakt, maakt elke dag verbinding met de TeleMessage-site en brengt de e-mailberichten van de afgelopen 24 uur over naar een beveiligd Azure Storage-gebied in de Microsoft Cloud.

4. De verbindingslijn importeert de mobiele communicatie-items naar het postvak van een specifieke gebruiker. In het postvak van de specifieke gebruiker wordt een nieuwe map met de naam Archief van Telegram gemaakt en worden de items in het postvak geïmporteerd. De connector doet deze toewijzing met behulp van de waarde van de *eigenschap E-mailadres van de* gebruiker. Elk e-mailbericht bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer van het e-mailbericht.

> Naast automatische gebruikerstoewijzing met  de waarde van de eigenschap E-mailadres van de gebruiker, kunt u ook een aangepaste toewijzing definiëren door een CSV-toewijzingsbestand te uploaden. Dit toewijzingsbestand moet het mobiele nummer van de gebruiker en het bijbehorende Microsoft 365 postvak voor elke gebruiker bevatten. Als u automatische gebruikerstoewijzing inschakelen en een aangepaste toewijzing biedt, wordt voor elk e-mailitem eerst naar aangepast toewijzingsbestand gekijken. Als er geen geldige Microsoft 365 wordt gevonden die overeenkomt met het mobiele nummer van een gebruiker, gebruikt de verbindingslijn de eigenschap E-mailadres van de gebruiker van het e-mailitem. Als de verbindingslijn geen geldige Microsoft 365-gebruiker vindt in het  aangepaste toewijzingsbestand of de eigenschap van het e-mailadres van het e-mailitem, wordt het item niet geïmporteerd.

## <a name="before-you-set-up-a-connector"></a>Voordat u een verbindingslijn in stelt

- Bestel de [Archiveringsservice van Telegram bij TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) en ontvang een geldig beheeraccount voor uw organisatie. U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in het compliancecentrum.

- Registreer alle gebruikers die een Archivering van Telegram vereisen in het TeleMessage-account. Wanneer u gebruikers registreert, moet u hetzelfde e-mailadres gebruiken dat wordt gebruikt voor hun Microsoft 365 account.

- Installeer de App Archief van Telegram op de mobiele telefoons van uw werknemers en activeer deze. Met de App Archief van Telegram kunnen ze communiceren en chatten met andere Gebruikers van Telegram.

- De gebruiker die in stap 3 een Verbindingslijn Voor archief van Telegram maakt, moet de rol Postvak importeren exporteren in Exchange Online. Dit is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in de Microsoft 365-compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="create-a-telegram-archiver-connector"></a>Een Verbindingslijn voor het archief van Telegram maken

Nadat u de vereisten hebt voltooid die in de vorige sectie zijn beschreven, kunt u de verbindingslijn Van De archiefman van Telegram in de Microsoft 365-compliancecentrum. De verbindingslijn gebruikt de informatie die u verstrekt om verbinding te maken met de TeleMessage-site en draagt communicatiegegevens van Telegram over naar de bijbehorende postvakken van gebruikers in Microsoft 365.

1. Ga naar <https://compliance.microsoft.com> en klik vervolgens op **Gegevensconnectoren >** T **elegram Archiver**.

2. Klik op **de pagina Productbeschrijving van De archiefpagina** van Telegram op **Verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer op de pagina Aanmelden bij **TeleMessage** onder Stap 3 de vereiste informatie in de volgende vakken in en klik vervolgens op **Volgende**.

    - **Gebruikersnaam:** Uw TeleMessage-gebruikersnaam.

    - **Wachtwoord:** Uw TeleMessage-wachtwoord.

5. Nadat de verbindingslijn is gemaakt, kunt u het pop-upvenster sluiten en naar de volgende pagina gaan.

6. Schakel op **de pagina Gebruikerstoewijzing** automatische gebruikerstoewijzing in. Als u aangepaste toewijzing wilt inschakelen, uploadt u een CSV-bestand dat de gebruikerstoewijzingsgegevens bevat en klikt u vervolgens op **Volgende.**

7. Controleer de instellingen en klik vervolgens op **Voltooien om** de verbindingslijn te maken.

8. Ga naar het tabblad Connectors op de pagina **Gegevensconnectors** om de voortgang van het importproces voor de nieuwe verbindingslijn te bekijken.

## <a name="known-issues"></a>Bekende problemen

- Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.
