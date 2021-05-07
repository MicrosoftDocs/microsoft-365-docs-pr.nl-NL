---
title: Een verbindingslijn instellen om AT-&-Sms/MMS-netwerkgegevens te archiveren
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
description: Beheerders kunnen een TeleMessage-connector instellen voor het importeren en archiveren van Sms en MMS-gegevens uit het AT-&T Mobile Network. Op deze manier kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365, zodat u compliancefuncties, zoals juridische bewaring, inhoudszoekbeleid en bewaarbeleid, kunt gebruiken om de gegevens van derden van uw organisatie te beheren.
ms.openlocfilehash: a67e6caa8a610c8dac76ac6397c54115b310904b
ms.sourcegitcommit: b169f6ad3e44a7fcebf77f43be9eb5edd84ea5ef
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/28/2021
ms.locfileid: "52162774"
---
# <a name="set-up-a-connector-to-archive-att-smsmms-data"></a>Een connector instellen voor het archiveren van AT-&T Sms/MMS-gegevens

Gebruik een TeleMessage-connector in het Microsoft 365 compliancecentrum om Sms en MMS-gegevens te importeren en te archiveren vanuit AT&T Mobile Network. Nadat u een verbindingslijn hebt ingesteld en geconfigureerd, wordt er eenmaal per dag verbinding met het AT&T-netwerk van uw organisatie en worden Sms- en MMS-gegevens geïmporteerd in postvakken in Microsoft 365.

Nadat Sms en MMS-berichten zijn opgeslagen in postvakken van gebruikers, kunt u Microsoft 365 compliancefuncties zoals Proces bewaring, Inhoud zoeken en Microsoft 365 bewaarbeleid toepassen op AT&T-netwerkgegevens. U kunt bijvoorbeeld at-&T-netwerkgegevens zoeken met Inhoud zoeken of het postvak met de AT&T-netwerkconnectorgegevens koppelen aan een bewaarder in een Advanced eDiscovery geval. Als u een AT-&T-netwerkconnector gebruikt om gegevens te importeren en te archiveren in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-att-network-data"></a>Overzicht van het archiveren van AT-&T-netwerkgegevens

In het volgende overzicht wordt uitgelegd hoe het gebruik van een connector voor het archiveren van AT-&T-netwerkgegevens in Microsoft 365.

![Archiveringswerkstroom att-netwerk](../media/ATTNetworkConnectorWorkflow.png)

1. Uw organisatie werkt met TeleMessage om een AT-&T-netwerkconnector in te stellen. Zie AT [&T Network Archiver voor meer informatie.](https://www.telemessage.com/office365-activation-for-atnt-network-archiver/)

2. In realtime worden Sms en MMS-berichten van het AT-&T-netwerk van uw organisatie gekopieerd naar de TeleMessage-site.

3. De AT&T-netwerkconnector die u maakt in het compliancecentrum van Microsoft 365 maakt elke dag verbinding met de TeleMessage-site en brengt de Sms- en MMS-berichten van de afgelopen 24 uur over naar een veilige Azure Storage-locatie in de Microsoft-cloud. De connector converteert ook de inhoud van Sms en MMS-berichten naar een e-mailberichtindeling.

4. De connector importeert de mobiele communicatie-items naar het postvak van specifieke gebruikers. Er wordt een nieuwe map met **de naam AT&T Sms/MMS Network Archiver** gemaakt in het postvak van de gebruiker en de items worden er in geïmporteerd. De connector doet deze toewijzing met behulp van de waarde van de *eigenschap E-mailadres van de* gebruiker. Elk Sms en MMS-bericht bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer aan het bericht.
 
   Naast automatische gebruikerstoewijzing met  de waarde van de eigenschap E-mailadres van de gebruiker, kunt u ook een aangepaste toewijzing definiëren door een CSV-toewijzingsbestand te uploaden. Dit toewijzingsbestand bevat het mobiele telefoonnummer en het bijbehorende Microsoft 365 e-mailadres voor gebruikers in uw organisatie. Als u zowel automatische gebruikerstoewijzing als aangepaste toewijzing inschakelen, wordt voor elk e-mailitem eerst het aangepaste toewijzingsbestand door de verbindingslijn verkend. Als er geen geldige Microsoft 365 wordt gevonden die overeenkomt met een mobiel telefoonnummer, gebruikt de verbindingslijn de waarden in de eigenschap e-mailadres van het item dat het probeert te importeren. Als de connector geen geldige gebruiker Microsoft 365 in het aangepaste toewijzingsbestand of in de eigenschap e-mailadres van het e-mailitem, wordt het item niet geïmporteerd.

## <a name="before-you-begin"></a>Voordat u begint

Sommige implementatiestappen die nodig zijn om AT-&T-netwerkgegevens te archiveren, zijn extern van Microsoft 365 en moeten zijn voltooid voordat u de verbindingslijn in het compliancecentrum kunt maken.

- Bestel de [mobiele archiverservice bij TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) en ontvang een geldig beheeraccount voor uw organisatie. U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in het compliancecentrum.

- Verkrijg uw AT&T-account en factureringscontactgegevens, zodat u de onboardingformulieren voor TeleMessage kunt invullen en de berichtarchiveringsservice kunt bestellen bij AT&T.

- Registreer alle gebruikers die AT&T Sms/MMS Network archiveren in het TeleMessage-account. Wanneer u gebruikers registreert, moet u hetzelfde e-mailadres gebruiken dat wordt gebruikt voor hun Microsoft 365 account.

- Uw werknemers moeten mobiele telefoons hebben die eigendom zijn van het bedrijf en die aansprakelijk zijn voor bedrijven op het mobiele at&T-netwerk. Het archiveren van berichten in Microsoft 365 is niet beschikbaar voor byod-apparaten (Bring Your Own Devices).

- Aan de gebruiker die een AT-&T-netwerkconnector maakt, moet de rol Postvak importeren exporteren in Exchange Online. Dit is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in het Microsoft 365 compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="create-a-att-network-connector"></a>Een AT-&T-netwerkconnector maken

Nadat u de vereisten hebt voltooid die in de vorige sectie zijn beschreven, kunt u een AT-&T-netwerkconnector maken in het Microsoft 365 compliancecentrum. De verbindingslijn gebruikt de informatie die u verstrekt om verbinding te maken met de TeleMessage-site en om Sms- en MMS-berichten over te brengen naar de bijbehorende postvakken van gebruikers in Microsoft 365.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik vervolgens op **Gegevensconnectoren**  \  **AT&T-netwerk.**

2. Klik op **de pagina AT&T Network-productbeschrijving** op **Verbindingslijn toevoegen**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer op de pagina Aanmelden bij **TeleMessage** onder Stap 3 de vereiste informatie in de volgende vakken in en klik vervolgens op **Volgende**.

   - **Gebruikersnaam:** Uw TeleMessage-gebruikersnaam.

   - **Wachtwoord:** Uw TeleMessage-wachtwoord.

5. Nadat de verbindingslijn is gemaakt, kunt u het pop-upvenster sluiten en naar de volgende pagina gaan.

6. Schakel op **de pagina Gebruikerstoewijzing** automatische gebruikerstoewijzing in. Als u aangepaste toewijzing wilt inschakelen, uploadt u een CSV-bestand dat de gebruikerstoewijzingsgegevens bevat en klikt u vervolgens op **Volgende.**

7. Controleer de instellingen en klik vervolgens op **Voltooien om** de verbindingslijn te maken.

8. Ga naar het **tabblad Connectors** op de pagina Gegevensconnectoren in het compliancecentrum om de voortgang van het importproces voor de nieuwe **verbindingslijn** te bekijken.

## <a name="known-issues"></a>Bekende problemen

- Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.
