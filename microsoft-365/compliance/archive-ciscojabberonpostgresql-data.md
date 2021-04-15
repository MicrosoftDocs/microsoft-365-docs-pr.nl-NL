---
title: Een connector instellen voor het archiveren van Cisco Jabber op PostgreSQL-gegevens in Microsoft 365
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Meer informatie over het instellen en gebruiken van een connector in het Microsoft 365-compliancecentrum voor het importeren en archiveren van gegevens van Cisco Jabber op PostgreSQL naar Microsoft 365.
ms.openlocfilehash: 47cd3c7e9d3717426fbcf43bf1b0df16bbe2cf80
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51767081"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-postgresql-data-preview"></a>Een connector instellen voor het archiveren van Cisco Jabber op PostgreSQL-gegevens (preview)

Gebruik een Veritas-connector in het Microsoft 365-compliancecentrum om gegevens van het Cisco Jabber-platform te importeren en te archiveren naar gebruikerspostvakken in uw Microsoft 365-organisatie. Veritas biedt een Cisco Jabber op [PostgreSQL-connector](https://www.veritas.com/insights/merge1/jabber) die is geconfigureerd om items uit de gegevensbron van derden vast te leggen (op regelmatige basis) en deze items te importeren in Microsoft 365. De connector converteert de inhoud, zoals berichten, chats en gedeelde inhoud van Cisco Jabber op PostgreSQL naar een e-mailberichtindeling en importeert deze items vervolgens in het postvak van de gebruiker in Microsoft 365.

Nadat Cisco Jabber op PostgreSQL-gegevens is opgeslagen in postvakken van gebruikers, kunt u nalevingsfuncties van Microsoft 365 toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels. Als u een Cisco Jabber op PostgreSQL-connector gebruikt om gegevens in Microsoft 365 te importeren en te archiveren, kan uw organisatie voldoen aan het overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-cisco-jabber-on-postgresql-data"></a>Overzicht van het archiveren van Cisco Jabber op PostgreSQL-gegevens

In het volgende overzicht wordt uitgelegd hoe u een connector gebruikt om de Cisco Jabber te archiveren op PostgreSQL-gegevens in Microsoft 365.

![Archiveringswerkstroom voor Cisco Jabber op PostgreSQL-gegevens](../media/CiscoJabberonPostgreSQLConnectorWorkflow.png)

1. Uw organisatie werkt samen met Cisco Jabber op PostgreSQL om een Cisco Jabber in te stellen en te configureren op de PostgreSQL-site.

2. Eenmaal per 24 uur worden Cisco Jabber op PostgreSQL-items gekopieerd naar de Veritas Merge1-site. De connector converteert ook Cisco Jabber op PostgreSQL-items naar een e-mailberichtindeling.

3. De Cisco Jabber op PostgreSQL-connector die u maakt in het Microsoft 365-compliancecentrum, maakt elke dag verbinding met de Veritas Merge1-site en draagt de Jabber-inhoud over naar een beveiligde Azure Storage-locatie in de Microsoft-cloud.

4. De connector importeert de geconverteerde items in de postvakken van specifieke gebruikers met behulp van de waarde van de eigenschap *E-mail* van de automatische gebruikerstoewijzing, zoals beschreven in [stap 3.](#step-3-map-users-and-complete-the-connector-setup) Een submap in de map Postvak IN met de naam **Cisco Jabber op PostgreSQL** wordt gemaakt in de postvakken van de gebruiker en items worden geïmporteerd in die map. De verbindingslijn doet dit met behulp van de waarde van de eigenschap *E-mail.* Elk Jabber-item bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer aan het item.

## <a name="before-you-begin"></a>Voordat u begint

- Maak een Merge1-account voor Microsoft-connectors. Neem hiervoor contact op met [Veritas Customer Support.](https://www.veritas.com/content/support/en_US) U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.

- De gebruiker die de Cisco Jabber maakt op PostgreSQL-connector in stap 1 (en deze voltooit in stap 3) moet zijn toegewezen aan de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in het Microsoft 365-compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen maken of [Rollengroepen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) wijzigen in het artikel 'Rollengroepen beheren in Exchange Online' voor meer informatie.

## <a name="step-1-set-up-the-cisco-jabber-on-postgresql-connector"></a>Stap 1: Cisco Jabber instellen op PostgreSQL-connector

De eerste stap is toegang tot de pagina Gegevensconnectoren in het Microsoft 365-compliancecentrum en het maken van een **verbindingslijn** voor Jabber-gegevens.

1. Ga naar <https://compliance.microsoft.com> en klik vervolgens op **Gegevensconnectoren** &gt; **Cisco Jabber op PostgreSQL**.

2. Klik op **de pagina Cisco Jabber op de pagina PostgreSQL-productbeschrijving** op **Verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**

5. Meld u aan bij uw Merge1-account om de verbindingslijn te configureren.

## <a name="step-2-configure-the-cisco-jabber-on-postgresql-on-the-veritas-merge1-site"></a>Stap 2: De Cisco Jabber configureren op PostgreSQL op de Veritas Merge1-site

De tweede stap is het configureren van de Cisco Jabber op PostgreSQL-connector op de Veritas Merge1-site. Zie Gebruikershandleiding voor connectors van derden samenvoegen voor informatie over het configureren van de Cisco [Jabber-connector](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20PostgreSQL%20User%20Guide.pdf)op PostgreSQL.

Nadat u op **Opslaan &** Voltooien  hebt geklikt, wordt de pagina Gebruikerstoewijzing in de wizard Verbindingslijn in het Microsoft 365-compliancecentrum weergegeven.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Stap 3: Gebruikers in kaart brengen en de configuratie van de connector voltooien

Als u gebruikers wilt in kaart brengen en de configuratie van de connector wilt voltooien in het Microsoft 365-compliancecentrum, volgt u de volgende stappen:

1. Schakel automatische gebruikerstoewijzing in op de pagina Cisco Jabber toewijzen op **PostgreSQL-gebruikers naar Microsoft 365-gebruikers.** De Cisco Jabber op PostgreSQL-items bevatten een eigenschap met de naam *E-mail,* die e-mailadressen bevat voor gebruikers in uw organisatie. Als de connector dit adres kan koppelen aan een Microsoft 365-gebruiker, worden de items geïmporteerd in het postvak van die gebruiker.

2. Klik **op Volgende,** controleer uw instellingen en ga naar de pagina Gegevensconnectors om de voortgang van het importproces voor de nieuwe **verbindingslijn** te bekijken.

## <a name="step-4-monitor-the-cisco-jabber-on-postgresql-connector"></a>Stap 4: De Cisco Jabber controleren op De PostgreSQL-connector

Nadat u de Cisco Jabber op De PostgreSQL-connector hebt gebruikt, kunt u de connectorstatus bekijken in het Microsoft 365-compliancecentrum.

1. Ga naar <https://compliance.microsoft.com/> en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op het tabblad Connectors en selecteer vervolgens de Cisco Jabber op **PostgreSQL-connector** om de flyoutpagina weer te geven, die de eigenschappen en informatie over de **verbindingslijn** bevat.

3. Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

- Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items groter dan 10 MB, maar ondersteuning voor grotere items is later beschikbaar.
