---
title: Een connector instellen voor het archiveren van Cisco Jabber op Oracle-gegevens in Microsoft 365
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
description: Meer informatie over het instellen en gebruiken van een connector in het Microsoft 365-compliancecentrum om gegevens van Cisco Jabber op Oracle te importeren en te archiveren naar Microsoft 365.
ms.openlocfilehash: c3a2d64605eb3cda235c73964507a82c940187fe
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51767085"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-oracle-data-preview"></a>Een connector instellen voor het archiveren van Cisco Jabber op Oracle-gegevens (preview)

Gebruik een Veritas-connector in het Microsoft 365-compliancecentrum om gegevens uit het Cisco Jabber-platform op Oracle te importeren en te archiveren naar postvakken van gebruikers in uw Microsoft 365-organisatie. Veritas biedt een [Cisco Jabber](https://www.veritas.com/insights/merge1/jabber) op Oracle-connector die is geconfigureerd om items uit de gegevensbron van derden vast te leggen (op regelmatige basis) en deze items te importeren in Microsoft 365. De connector converteert de inhoud zoals bestanden en bestandsbewerkingen, opmerkingen en gedeelde inhoud van Cisco Jabber op Oracle naar een e-mailberichtindeling en importeert deze items vervolgens in het postvak van de gebruiker in Microsoft 365.

Nadat Cisco Jabber op Oracle-gegevens is opgeslagen in gebruikerspostvakken, kunt u nalevingsfuncties van Microsoft 365 toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels. Met een Cisco Jabber op Oracle-connector voor het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-cisco-jabber-on-oracle-data"></a>Overzicht van het archiveren van Cisco Jabber op Oracle-gegevens

In het volgende overzicht wordt uitgelegd hoe u een connector gebruikt om de Cisco Jabber te archiveren op Oracle-gegevens in Microsoft 365.

![Archiveringswerkstroom voor Cisco Jabber op Oracle-gegevens](../media/CiscoJabberOnOracleConnectorWorkflow.png)

1. Uw organisatie werkt samen met Cisco Jabber op Oracle om een Cisco Jabber op Oracle-site in te stellen en te configureren.

2. Eenmaal per 24 uur worden Cisco Jabber op Oracle-items gekopieerd naar de Veritas Merge1-site. De connector converteert ook Cisco Jabber op Oracle-items naar een e-mailberichtindeling.

3. De Cisco Jabber op Oracle-connector die u maakt in het Microsoft 365-compliancecentrum, maakt elke dag verbinding met de Veritas Merge1-site en draagt de Jabber-inhoud over naar een beveiligde Azure Storage-locatie in de Microsoft-cloud.

4. De connector importeert de geconverteerde items in de postvakken van specifieke gebruikers met behulp van de waarde van de eigenschap *E-mail* van de automatische gebruikerstoewijzing, zoals beschreven in [stap 3.](#step-3-map-users-and-complete-the-connector-setup) Een submap in de map Postvak IN met de naam **Cisco Jabber op Oracle** wordt gemaakt in de postvakken van de gebruiker en items worden geïmporteerd in die map. De verbindingslijn doet dit met behulp van de waarde van de eigenschap *E-mail.* Elk Jabber-item bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer aan het item.

## <a name="before-you-begin"></a>Voordat u begint

- Maak een Merge1-account voor Microsoft-connectors. Neem hiervoor contact op met [Veritas Customer Support.](https://www.veritas.com/content/support/en_US) U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.

- De gebruiker die de Cisco Jabber op Oracle-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in het Microsoft 365-compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen maken of [Rollengroepen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) wijzigen in het artikel 'Rollengroepen beheren in Exchange Online' voor meer informatie.

## <a name="step-1-set-up-the-cisco-jabber-on-oracle-connector"></a>Stap 1: Cisco Jabber instellen op Oracle-connector

De eerste stap is toegang tot de pagina Gegevensconnectoren in het Microsoft 365-compliancecentrum en het maken van een **verbindingslijn** voor Jabber-gegevens.

1. Ga naar <https://compliance.microsoft.com> en klik vervolgens op **Gegevensconnectoren**  >  **Cisco Jabber op Oracle.**

2. Klik op **de pagina Cisco Jabber op** Oracle-productbeschrijving op **Verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**

5. Meld u aan bij uw Merge1-account om de verbindingslijn te configureren.

## <a name="step-2-configure-the-cisco-jabber-on-oracle-on-the-veritas-merge1-site"></a>Stap 2: De Cisco Jabber configureren op Oracle op de Veritas Merge1-site

De tweede stap is het configureren van de Cisco Jabber op Oracle-connector op de Veritas Merge1-site. Zie Handleiding Connectors van derden samenvoegen voor informatie over het configureren van de Cisco [Jabber-connector](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20Oracle%20User%20Guide.pdf)op Oracle.

Nadat u op **Opslaan &** Voltooien  hebt geklikt, wordt de pagina Gebruikerstoewijzing in de wizard Verbindingslijn in het Microsoft 365-compliancecentrum weergegeven.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Stap 3: Gebruikers in kaart brengen en de configuratie van de connector voltooien

Als u gebruikers wilt in kaart brengen en de configuratie van de connector wilt voltooien in het Microsoft 365-compliancecentrum, volgt u de volgende stappen:

1. Schakel op **de pagina Cisco Jabber toewijzen op Oracle-gebruikers naar Microsoft 365-gebruikers** automatische gebruikerstoewijzing in. De Cisco Jabber op Oracle-items bevatten een eigenschap *met* de naam E-mail, die e-mailadressen bevat voor gebruikers in uw organisatie. Als de connector dit adres kan koppelen aan een Microsoft 365-gebruiker, worden de items geïmporteerd in het postvak van die gebruiker.

2. Klik **op Volgende,** controleer uw instellingen en ga naar de pagina Gegevensconnectors om de voortgang van het importproces voor de nieuwe **verbindingslijn** te bekijken.

## <a name="step-4-monitor-the-cisco-jabber-on-oracle-connector"></a>Stap 4: De Cisco Jabber-connector op Oracle-connector controleren

Nadat u de Cisco Jabber op Oracle-connector hebt gebruikt, kunt u de connectorstatus bekijken in het Microsoft 365-compliancecentrum.

1. Ga naar <https://compliance.microsoft.com/> en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **het tabblad Connectors** en selecteer vervolgens **de Cisco Jabber** op Oracle-connector om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.

3. Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

- Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items groter dan 10 MB, maar ondersteuning voor grotere items is later beschikbaar.
