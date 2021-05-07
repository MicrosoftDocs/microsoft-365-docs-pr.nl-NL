---
title: Een verbindingslijn instellen voor het archiveren van gegevens van MS-SQL Database
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
description: Beheerders kunnen een verbindingslijn instellen voor het importeren en archiveren van gegevens uit MS-SQL Database. Met deze connector kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365. Nadat u deze gegevens hebt gearchiveerd, kunt u compliancefuncties, zoals juridische bewaring, inhoudszoekbeleid en bewaarbeleid, gebruiken om gegevens van derden te beheren.
ms.openlocfilehash: 494e91085494ba027a80480faba3cfb189cbd928
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162346"
---
# <a name="set-up-a-connector-to-archive-data-from-ms-sql-database"></a>Een verbindingslijn instellen voor het archiveren van gegevens van MS-SQL Database

Gebruik een Veritas-connector in het Microsoft 365 compliancecentrum om gegevens uit MS-SQL Database te importeren en te archiveren in gebruikerspostvakken in uw Microsoft 365 organisatie. Veritas biedt u een MS-SQL Database Importer-connector die is geconfigureerd om items uit een database vast te leggen met behulp van een XML-configuratiebestand en deze items te importeren in Microsoft 365. De verbindingslijn converteert inhoud van MS-SQL Database naar een e-mailberichtindeling en importeert deze items vervolgens in gebruikerspostvakken in Microsoft 365.

Nadat inhoud van MS SQL Database is opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels. Als u een MS-verbindingslijn SQL Database om gegevens te importeren en te archiveren in Microsoft 365, kan uw organisatie voldoen aan het overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-the-ms-sql-data"></a>Overzicht van het archiveren van ms-SQL gegevens

In het volgende overzicht wordt uitgelegd hoe het gebruik van een verbindingslijn voor het archiveren van MS-SQL gegevens in Microsoft 365.

![Archiveringswerkstroom voor MS-SQL gegevens](../media/MSSQLDatabaseConnectorWorkflow.png)

1. Uw organisatie werkt samen met een MS-SQL Database voor het instellen en configureren van een MS-SQL Database site.

2. Elke 24 uur worden MS-SQL Database gekopieerd naar de Veritas Merge1-site. De connector converteert deze inhoud ook naar een e-mailberichtindeling.

3. De MS SQL Database Importer-connector die u maakt in het Microsoft 365-compliancecentrum, maakt elke dag verbinding met de Veritas Merge1-site en draagt de berichten over naar een veilige Azure Storage-locatie in de Microsoft-cloud.

4. De connector importeert de geconverteerde MS-SQL Database items in de postvakken van specifieke gebruikers met behulp van de waarde van de eigenschap *E-mail* van de automatische gebruikerstoewijzing, zoals beschreven in [stap 3.](#step-3-map-users-and-complete-the-connector-setup) Een submap in de map Postvak IN met de naam **MS SQL Database Importer** wordt gemaakt in de postvakken van gebruikers en de items worden geïmporteerd in die map. De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.* Elk item uit de MS-SQL Database bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer van het item.

## <a name="before-you-begin"></a>Voordat u begint

- Maak een Veritas Merge1-account voor Microsoft-connectors. Neem contact op met [Veritas Customer Support](https://www.veritas.com/content/support/)om een account te maken. U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.

- De gebruiker die de MS-SQL Database Importer-connector maakt in stap 1 (en deze in stap 3 voltooit), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina Gegevensconnectors in het Microsoft 365 compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-set-up-the-ms-sql-database-importer-connector"></a>Stap 1: De connector ms-SQL Database Importer instellen

De eerste stap is toegang tot de pagina Gegevensconnectoren in het Microsoft365-compliancecentrum en het maken van een **verbindingslijn** voor de MS-SQL Database.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com) en klik vervolgens op **Gegevensconnectoren**  >  **MS SQL Database Importer**.

2. Klik op **de pagina MS SQL Database Productbeschrijving van Importer** op Nieuwe **verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**

5. Meld u aan bij uw Merge1-account om de verbindingslijn te configureren.

## <a name="step-2-configure-the-ms-sql-database-importer-connector-on-the-veritas-merge1-site"></a>Stap 2: De MS-connector SQL Database importer configureren op de Veritas Merge1-site

De tweede stap is het configureren van de MS-SQL Database Importer-connector op de site Samenvoegen1. Zie Gebruikershandleiding voor connectors van derden samenvoegen voor informatie over het configureren van de [MS-SQL Database](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf)Importer.

Nadat u op **Opslaan &** Voltooien  hebt geklikt, wordt de pagina Gebruikerstoewijzing in de wizard verbindingslijn in het Microsoft 365 compliancecentrum weergegeven.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Stap 3: Gebruikers in kaart brengen en de configuratie van de connector voltooien

Als u gebruikers wilt in kaart brengen en de configuratie van de verbindingslijn wilt voltooien, volgt u de volgende stappen:

1. Schakel op **de pagina Ms-SQL Database gebruikers van Importer Microsoft 365** gebruikers in om automatische gebruikerstoewijzing in te stellen. De MS-SQL Database items bevatten een eigenschap met de naam E-mail, die e-mailadressen bevat voor gebruikers in uw organisatie. Als de verbindingslijn dit adres kan koppelen aan Microsoft 365 gebruiker, worden de items geïmporteerd in het postvak van die gebruiker.

2. Klik **op Volgende,** bekijk uw instellingen en ga naar de pagina Gegevensconnectors om de voortgang van het importproces voor de nieuwe **verbindingslijn** te bekijken.

## <a name="step-4-monitor-the-ms-sql-database-importer-connector"></a>Stap 4: De MS-connector SQL Database Importer controleren

Nadat u de MS-verbindingslijn SQL Database Importer, kunt u de connectorstatus bekijken in het Microsoft 365 compliancecentrum.

1. Ga naar <https://compliance.microsoft.com/> en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **het tabblad Verbindingslijnen** en selecteer vervolgens de **MS-SQL Database** **Importer-connector** om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.

3. Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

- Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.