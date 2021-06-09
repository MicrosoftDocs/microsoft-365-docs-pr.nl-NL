---
title: Een verbindingslijn instellen voor het archiveren van O2-netwerkgegevens in Microsoft 365
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
description: Beheerders kunnen een TeleMessage-connector instellen voor het importeren en archiveren van Sms en MMS-gegevens uit het mobiele O2-netwerk in Microsoft 365. Op deze manier kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365, zodat u compliancefuncties, zoals juridische bewaring, inhoudszoekbeleid en bewaarbeleid, kunt gebruiken om de gegevens van derden van uw organisatie te beheren.
ms.openlocfilehash: f2604589fb91d36a8fc4a8d94be88757f198fa58
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822187"
---
# <a name="set-up-a-connector-to-archive-o2-network-data"></a>Een verbindingslijn instellen voor het archiveren van O2-netwerkgegevens

Gebruik een TeleMessage-verbindingslijn in het Microsoft 365 compliancecentrum om berichten en voicemailberichten (Sms) van het mobiele O2-netwerk te importeren en te archiveren. Nadat u een verbindingslijn hebt ingesteld en geconfigureerd, wordt er eenmaal per dag verbinding met het O2-netwerk van uw organisatie en worden Sms en spraakoproepen geïmporteerd naar postvakken in Microsoft 365.

Nadat Sms berichten en spraakoproepen zijn opgeslagen in postvakken van gebruikers, kunt u Microsoft 365 compliancefuncties zoals Litigation Hold, Inhoud zoeken en Microsoft 365 bewaarbeleid toepassen op O2 Netwerkgegevens. U kunt bijvoorbeeld zoeken in O2 Network Sms berichten en spraakoproepen met Inhoud zoeken of het postvak met O2-netwerkgegevens koppelen aan een bewaarder in een Advanced eDiscovery geval. Met een O2-netwerkconnector voor het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-o2-network-data"></a>Overzicht van het archiveren van O2-netwerkgegevens

In het volgende overzicht wordt uitgelegd hoe het gebruik van een verbindingslijn voor het archiveren van O2-netwerkgegevens in Microsoft 365.

![O2 Netwerkarchiveringswerkstroom](../media/O2NetworkConnectorWorkflow.png)

1. Uw organisatie werkt samen met TeleMessage en O2 om een O2-netwerkconnector in te stellen. Zie [O2 Network Archiver](https://www.telemessage.com/office365-activation-for-o2-network-archiver)voor meer informatie.

2. Eenmaal per 24 uur worden Sms berichten en spraakoproepen vanuit het O2-netwerk van uw organisatie gekopieerd naar de TeleMessage-site.

3. De O2-netwerkconnector die u maakt in het Microsoft 365-compliancecentrum maakt elke dag verbinding met de TeleMessage-site en brengt de Sms-berichten en spraakoproepen van de afgelopen 24 uur over naar een veilige Azure Storage-locatie in de Microsoft-cloud. De verbindingslijn converteert ook de inhoud van Sms berichten en spraakoproepen naar een e-mailberichtindeling.

4. De connector importeert de mobiele communicatie-items naar het postvak van specifieke gebruikers. Een nieuwe map **met de Sms O2** en Voice Network Archiver wordt gemaakt in het postvak van een specifieke gebruiker en de items worden er in geïmporteerd. De connector doet deze toewijzing met behulp van de waarde van de *eigenschap E-mailadres van de* gebruiker. Elke Sms en gesproken oproep bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer van het bericht.

   Naast automatische gebruikerstoewijzing met  de waarde van de eigenschap E-mailadres van de gebruiker, kunt u ook een aangepaste toewijzing definiëren door een CSV-toewijzingsbestand te uploaden. Dit toewijzingsbestand bevat het mobiele telefoonnummer en het bijbehorende Microsoft 365 e-mailadres voor gebruikers in uw organisatie. Als u zowel automatische gebruikerstoewijzing als aangepaste toewijzing inschakelen, wordt voor elk O2-item eerst naar aangepast toewijzingsbestand gesurfd. Als er geen geldige Microsoft 365-gebruiker wordt gevonden die overeenkomt met het mobiele telefoonnummer van een gebruiker, gebruikt de verbindingslijn de waarden in de eigenschap e-mailadres van het item dat het probeert te importeren. Als de verbindingslijn geen geldige Microsoft 365 in het aangepaste toewijzingsbestand of in de eigenschap e-mailadres van het O2-item vindt, wordt het item niet geïmporteerd.

## <a name="before-you-set-up-a-connector"></a>Voordat u een verbindingslijn in stelt

Sommige implementatiestappen die nodig zijn om O2-netwerkgegevens te archiveren, zijn extern Microsoft 365 en moeten worden voltooid voordat u een verbindingslijn kunt maken in het compliancecentrum.

- Bestel de [O2 Network Archiver-service bij TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) en ontvang een geldig beheeraccount voor uw organisatie. U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in het compliancecentrum.

- Verkrijg uw O2 Network-account en factureringscontactgegevens, zodat u de onboardingformulieren voor TeleMessage kunt invullen en de berichtarchiveringsservice kunt bestellen bij O2.

- Registreer alle gebruikers die O2-Sms en Spraaknetwerkarchivering nodig hebben in het TeleMessage-account. Wanneer u gebruikers registreert, moet u hetzelfde e-mailadres gebruiken dat wordt gebruikt voor hun Microsoft 365 account.

- Uw werknemers moeten mobiele telefoons van het mobiele O2-netwerk hebben die eigendom zijn van uw bedrijf en die aansprakelijk zijn voor bedrijven. Het archiveren van berichten in Microsoft 365 is niet beschikbaar voor byod-apparaten (Bring Your Own Devices).

- De gebruiker die een O2-netwerkconnector maakt, moet de rol Postvak importeren exporteren in Exchange Online. Dit is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in het Microsoft 365 compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

- Deze gegevensconnector is beschikbaar in GCC omgevingen in de Microsoft 365 amerikaanse overheidscloud. Toepassingen en services van derden kunnen betrekking hebben op het opslaan, verzenden en verwerken van klantgegevens van uw organisatie op systemen van derden die buiten de Microsoft 365-infrastructuur vallen en daarom niet worden gedekt door de toezeggingen van Microsoft 365 compliance en gegevensbescherming. Microsoft geeft niet aan dat het gebruik van dit product om verbinding te maken met toepassingen van derden betekent dat deze toepassingen van derden compatibel zijn met FEDRAMP.

## <a name="create-an-o2-network-connector"></a>Een O2-netwerkconnector maken

Nadat u de vereisten hebt voltooid die in de vorige sectie zijn beschreven, kunt u een O2-netwerkconnector maken in het Microsoft 365 compliancecentrum. De verbindingslijn gebruikt de informatie die u verstrekt om verbinding te maken met de TeleMessage-site en Sms berichten en spraakoproepen over te brengen naar de bijbehorende postvakken van gebruikers in Microsoft 365.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik vervolgens op **Gegevensconnectoren** \> **O2 Network**.

2. Klik op **de pagina Productbeschrijving** van O2 Network op **Verbindingslijn toevoegen**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer op de pagina Aanmelden bij **TeleMessage** onder Stap 3 de vereiste informatie in de volgende vakken in en klik vervolgens op **Volgende**.

   - **Gebruikersnaam:** Uw TeleMessage-gebruikersnaam.

   - **Wachtwoord:** Uw TeleMessage-wachtwoord.

5. Nadat de verbindingslijn is gemaakt, kunt u het pop-upvenster sluiten en naar de volgende pagina gaan.

6. Schakel op **de pagina Gebruikerstoewijzing** automatische gebruikerstoewijzing in en klik op **Volgende.** Als u aangepaste toewijzing nodig hebt, uploadt u een CSV-bestand en klikt u op **Volgende.**

7. Controleer de instellingen en klik vervolgens op **Voltooien om** de verbindingslijn te maken.

8. Ga naar het tabblad Connectors op de pagina **Gegevensconnectors** om de voortgang van het importproces voor de nieuwe verbindingslijn te bekijken.

## <a name="known-issues"></a>Bekende problemen

- Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.