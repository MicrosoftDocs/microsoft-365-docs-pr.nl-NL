---
title: Een verbindingslijn instellen voor het archiveren van RingCentral-gegevens in Microsoft 365
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
description: Beheerders kunnen een verbindingslijn instellen voor het importeren en archiveren van RingCentral-gegevens van Veritas naar Microsoft 365. Met deze connector kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365. Nadat u deze gegevens hebt gearchiveerd, kunt u compliancefuncties zoals juridische bewaring, eDiscovery en bewaarbeleid gebruiken om gegevens van derden te beheren.
ms.openlocfilehash: 57c993ce99556677c0161649254b5ab43caace0e
ms.sourcegitcommit: 5d3086da935d4ddc8caf79ff19e3afda812fd061
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2021
ms.locfileid: "53244000"
---
# <a name="set-up-a-connector-to-archive-ringcentral-data"></a>Een verbindingslijn instellen voor het archiveren van RingCentral-gegevens

Gebruik een Veritas-connector in de Microsoft 365-compliancecentrum om gegevens van het RingCentral-platform te importeren en te archiveren naar postvakken van gebruikers in uw Microsoft 365 organisatie. Veritas biedt een [RingCentral-connector](https://www.veritas.com/insights/merge1/ringcentral) die is geconfigureerd om items uit de gegevensbron van derden vast te leggen en deze items te importeren in Microsoft 365. De connector converteert inhoud zoals chats, bijlagen, taken, notities en berichten van RingCentral naar een e-mailberichtindeling en importeert deze items vervolgens in de postvakken van de gebruiker in Microsoft 365.

Nadat RingCentral-gegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels. Als u een RingCentral-connector gebruikt om gegevens te importeren en te archiveren in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-ringcentral-data"></a>Overzicht van het archiveren van RingCentral-gegevens

In het volgende overzicht wordt uitgelegd hoe u een verbindingslijn gebruikt om de RingCentral-gegevens te archiveren in Microsoft 365.

![Archiveringswerkstroom voor RingCentral-gegevens](../media/RingCentralConnectorWorkflow.png)

1. Uw organisatie werkt samen met RingCentral om een RingCentral-site in te stellen en te configureren.

2. Elke 24 uur worden RingCentral-items gekopieerd naar de Veritas Merge1-site. De verbindingslijn converteert ook RingCentral-items naar een e-mailberichtindeling.

3. De RingCentral-verbindingslijn die u maakt in de Microsoft 365-compliancecentrum, maakt elke dag verbinding met de Veritas Merge1-site en draagt de RingCentral-inhoud over naar een veilige Azure Storage-locatie in de Microsoft-cloud.

4. De connector importeert de geconverteerde items in de postvakken van specifieke gebruikers met behulp van de waarde van de eigenschap *E-mail* van de automatische gebruikerstoewijzing, zoals beschreven in [stap 3.](#step-3-map-users-and-complete-the-connector-setup) Er wordt een submap in de map Postvak IN met de naam **RingCentral** gemaakt in de postvakken van de gebruiker en items worden geïmporteerd in die map. De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.* Elk RingCentral-item bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer aan het item.

## <a name="before-you-set-up-a-connector"></a>Voordat u een verbindingslijn in stelt

- Maak een Merge1-account voor Microsoft-connectors. Neem contact op met [Veritas Customer Support](https://www.veritas.com/form/requestacall/ms-connectors-contact)om dit account te maken. U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.

- Maak een RingCentral-toepassing om gegevens op te halen uit uw RingCentral-account. Zie Gebruikershandleiding voor connectors van derden samenvoegen voor stapsgewijse instructies over het maken [van de toepassing.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf)

- De gebruiker die de RingCentral-verbindingslijn maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in de Microsoft 365-compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-set-up-the-ringcentral-connector"></a>Stap 1: De RingCentral-verbindingslijn instellen

De eerste stap is toegang tot de pagina Gegevensconnectoren in de Microsoft 365-compliancecentrum en een **verbindingslijn** maken voor RingCentral-gegevens.

1. Ga naar <https://compliance.microsoft.com> en klik vervolgens op **Gegevensconnectoren**  >  **RingCentral.**

2. Klik op **de pagina RingCentral-productbeschrijving** op **Verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**

5. Meld u aan bij uw Merge1-account om de verbindingslijn te configureren.

## <a name="step-2-configure-the-ringcentral-on-the-veritas-merge1-site"></a>Stap 2: De RingCentral configureren op de Veritas Merge1-site

De tweede stap is het configureren van de RingCentral-connector op de Veritas Merge1-site. Zie Handleiding [Connectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf)van derden samenvoegen voor informatie over het configureren van de RingCentral-connector.

Nadat u op Opslaan & Voltooien  hebt geklikt, wordt de pagina Gebruikerstoewijzing in de wizard Verbindingslijn in Microsoft 365-compliancecentrum weergegeven. 

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Stap 3: Gebruikers in kaart brengen en de configuratie van de connector voltooien

Als u gebruikers wilt in kaart brengen en de configuratie van de verbindingslijn in de Microsoft 365-compliancecentrum, volgt u de volgende stappen:

1. Schakel op **de pagina Ringcentral-gebruikers toewijzen Microsoft 365 gebruikers automatisch** toewijzen in. De RingCentral-items bevatten een eigenschap met de naam *E-mail,* die e-mailadressen bevat voor gebruikers in uw organisatie. Als de verbindingslijn dit adres kan koppelen aan Microsoft 365 gebruiker, worden de items geïmporteerd in het postvak van die gebruiker.

2. Klik **op Volgende,** controleer uw instellingen en ga naar de pagina Gegevensconnectors om de voortgang van het importproces voor de nieuwe **verbindingslijn** te bekijken.

## <a name="step-4-monitor-the-ringcentral-connector"></a>Stap 4: De RingCentral-verbindingslijn controleren

Nadat u de RingCentral-verbindingslijn hebt aan Microsoft 365-compliancecentrum.

1. Ga naar <https://compliance.microsoft.com/> en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **het tabblad Verbindingslijnen** en selecteer vervolgens de **RingCentral-verbindingslijn** om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.

3. Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

- Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.
