---
title: Een verbindingslijn instellen om Workplace te archiveren op Facebook-gegevens in Microsoft 365
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
description: Beheerders kunnen een connector instellen voor het importeren en archiveren van gegevens van Workplace van Facebook, die wordt gearchiveerd op de Veritas-site Samenvoegen1, in Microsoft 365. Een verbindingslijn instellen vereist dat u met Veritas werkt Met deze connector kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365, zodat u compliancefuncties, zoals juridische bewaring, inhoud zoeken en bewaarbeleid, kunt gebruiken om de gegevens van derden van uw organisatie te beheren.
ms.openlocfilehash: 25221b1d71fe106f0f6dcf9c629414aeb0de8709
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162304"
---
# <a name="set-up-a-connector-to-archive-workplace-from-facebook-data"></a>Een connector instellen voor het archiveren van Workplace op Facebook-gegevens

Gebruik een Veritas-connector in het Microsoft 365 compliancecentrum om gegevens van Workplace van Facebook te importeren en te archiveren naar postvakken van gebruikers in uw Microsoft 365 organisatie. Veritas biedt een [Workplace from Facebook-connector](https://globanet.com/workplace/) die is geconfigureerd om items uit de gegevensbron van derden vast te leggen (op regelmatige basis) en deze items te importeren in Microsoft 365. De connector converteert de inhoud, zoals chats, bijlagen, berichten en video's van Workplace naar een e-mailberichtindeling en importeert deze items vervolgens in postvakken van gebruikers in Microsoft 365.

Nadat werkplekgegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels en communicatie compliance. Als u Workplace from Facebook Connector gebruikt om gegevens te importeren en te archiveren in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-workplace-from-facebook-data"></a>Overzicht van het archiveren van Werkplek op Facebook-gegevens

In het volgende overzicht wordt uitgelegd hoe het gebruik van een verbindingslijn voor het archiveren van werkplekgegevens in Microsoft 365.

![Archiving workflow for Workplace from Facebook data](../media/WorkplaceConnectorWorkflow.png)

1. Uw organisatie werkt met Workplace van Facebook om een werkpleksite in te stellen en te configureren.

2. Eenmaal per 24 uur worden items van Workplace gekopieerd naar de Veritas Merge1-site. De connector converteert ook de inhoud van deze items naar een e-mailberichtindeling.

3. De Workplace from Facebook-connector die u maakt in het Microsoft 365 compliancecentrum, maakt elke dag verbinding met de Veritas Merge1 en draagt de Workplace-items over naar een veilige Azure Storage-locatie in de Microsoft-cloud.

4. De connector importeert de geconverteerde items in de postvakken van specifieke gebruikers met behulp van de waarde van de eigenschap *E-mail* van de automatische gebruikerstoewijzing, zoals beschreven in stap 3. Er wordt een submap gemaakt in de map Postvak IN met de naam **Workplace van Facebook** en de items van Workplace worden geïmporteerd in die map. De verbindingslijn doet dit met behulp van de waarde van de eigenschap *E-mail.* Elk Workplace-item bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke chat- of postdeelnemer.

## <a name="before-you-begin"></a>Voordat u begint

- Maak een Veritas Merge1-account voor Microsoft-connectors. Neem contact op met [Veritas Customer Support](https://globanet.com/ms-connectors-contact)om dit account te maken. U meld u aan bij dit account wanneer u de verbindingslijn maakt in stap 1.

- Maak een aangepaste integratie voor https://my.workplace.com/work/admin/apps/ het ophalen van gegevens van Workplace via API's voor compliance- en eDiscovery-doeleinden.

   Bij het maken van de integratie genereert het Workplace-platform een set unieke referenties die worden gebruikt om tokens te genereren die worden gebruikt voor verificatie. Deze tokens worden gebruikt in de configuratiewizard Workplace from Facebook connector in stap 2. Zie Gebruikershandleiding voor connectors van derden samenvoegen [voor stapsgewijse](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)instructies over het maken van de toepassingen.

- De gebruiker die de Workplace from Facebook-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in het Microsoft 365 compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-set-up-the-workplace-from-facebook-connector"></a>Stap 1: De Workplace instellen vanuit facebook-connector

De eerste stap is om toegang te krijgen tot de pagina Gegevensconnectoren in het Microsoft 365 compliancecentrum en een **verbindingslijn** te maken voor werkplekgegevens.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik vervolgens op Data **connectors**  >  **Workplace from Facebook**.

2. Klik op **de pagina Werkplek van Facebook-productbeschrijving** op **Verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**

5. Meld u aan bij uw Merge1-account om de verbindingslijn te configureren.

## <a name="step-2-configure-the-workplace-from-facebook-connector-on-the-veritas-merge1-site"></a>Stap 2: De Workplace configureren vanuit Facebook-connector op de Veritas Merge1-site

De tweede stap is het configureren van de Workplace from Facebook connector op de Merge1-site. Zie Gebruikershandleiding voor connectors van derden samenvoegen voor informatie over het configureren van de Workplace [from Facebook-connector.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)

Nadat u op **Opslaan &** Voltooien  hebt geklikt, wordt de pagina Gebruikerstoewijzing in de wizard verbindingslijn in het Microsoft 365 compliancecentrum weergegeven.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Stap 3: Gebruikers in kaart brengen en de configuratie van de connector voltooien

Als u gebruikers wilt in kaart brengen en de configuratie van de verbindingslijn wilt voltooien in het Microsoft 365 compliancecentrum, volgt u de volgende stappen:

1. Schakel op **de pagina Externe gebruikers toewijzen Microsoft 365 gebruikers in,** automatische gebruikerstoewijzing in. De items op de werkplek bevatten een eigenschap met de naam *E-mail* die e-mailadressen bevat voor gebruikers in uw organisatie. Als de verbindingslijn dit adres kan koppelen aan Microsoft 365 gebruiker, worden de items geïmporteerd in het postvak van die gebruiker.

2. Klik **op Volgende,** controleer uw instellingen en ga naar de pagina Gegevensconnectors om de voortgang van het importproces voor de nieuwe **verbindingslijn** te bekijken.

## <a name="step-4-monitor-the-workplace-from-facebook-connector"></a>Stap 4: De werkplek bewaken via de Facebook-connector

Nadat u de Workplace from Facebook-connector hebt gebruikt, kunt u de status van de verbindingslijn bekijken in het Microsoft 365 compliancecentrum.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com) en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **het tabblad Verbindingslijnen** en selecteer vervolgens de **Workplace from Facebook-connector** om de flyoutpagina weer te geven. Deze pagina bevat de eigenschappen en informatie over de verbindingslijn.

3. Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat informatie over de gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

- Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.