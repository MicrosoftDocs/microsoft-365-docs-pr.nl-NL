---
title: Een connector instellen voor het archiveren van Yieldbroker-gegevens in Microsoft 365
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
description: Beheerders kunnen een connector instellen voor het importeren en archiveren van Yieldbroker-gegevens van Veritas naar Microsoft 365. Met deze connector kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365. Nadat u deze gegevens hebt gearchiveerd, kunt u compliancefuncties, zoals juridische bewaring, inhoudszoekbeleid en bewaarbeleid, gebruiken om gegevens van derden te beheren.
ms.openlocfilehash: 1f2ca6850057112cc0a97b08811532961a213e89
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162301"
---
# <a name="set-up-a-connector-to-archive-yieldbroker-data"></a>Een connector instellen voor het archiveren van Yieldbroker-gegevens

Gebruik een Veritas-connector in het Microsoft 365 compliancecentrum om gegevens uit de Yieldbroker te importeren en te archiveren naar gebruikerspostvakken in uw Microsoft 365 organisatie. Veritas biedt u een [Yieldbroker-connector](https://globanet.com/yieldbroker/) die is geconfigureerd om items uit de gegevensbron van derden vast te leggen en deze items te importeren in Microsoft 365. De connector converteert de inhoud van Yieldbroker naar een e-mailberichtindeling en importeert deze items vervolgens in het postvak van de gebruiker in Microsoft 365.

Nadat Yieldbroker is opgeslagen in postvakken van gebruikers, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels. Met behulp van een Yieldbroker-connector voor het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-yieldbroker-data"></a>Overzicht van het archiveren van Yieldbroker-gegevens

In het volgende overzicht wordt uitgelegd hoe het gebruik van een verbindingslijn voor het archiveren van de Yieldbroker-gegevens in Microsoft 365.

![Archiveringswerkstroom voor Yieldbroker-gegevens](../media/YieldbrokerConnectorWorkflow.png)

1. Uw organisatie werkt samen met yieldbroker om een Yieldbroker-site in te stellen en te configureren.

2. Eens in de 24 uur worden Yieldbroker-items gekopieerd naar de Veritas Merge1-site. De verbindingslijn converteert ook de inhoud naar een e-mailberichtindeling.

3. De Yieldbroker-connector die u maakt in het Microsoft 365 compliancecentrum, maakt elke dag verbinding met de Veritas Merge1-site en draagt de berichten over naar een veilige Azure Storage locatie in de Microsoft-cloud.

4. De connector importeert de geconverteerde Yieldbroker-items in de postvakken van specifieke gebruikers met behulp van de waarde van de eigenschap *E-mail* van de automatische gebruikerstoewijzing, zoals beschreven in [stap 3.](#step-3-map-users-and-complete-the-connector-setup) Een submap in de map Postvak IN met de naam **Yieldbroker** wordt gemaakt in de postvakken van de gebruiker en de items worden geïmporteerd in die map. De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.* Elke Yieldbroker bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer van het item.

## <a name="before-you-begin"></a>Voordat u begint

- Maak een Veritas Merge1-account voor Microsoft-connectors. Neem contact op met [Veritas Customer Support](https://www.veritas.com/content/support/)om een account te maken. U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.

- De gebruiker die de Yieldbroker-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina Gegevensconnectors in het Microsoft 365 compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-set-up-the-yieldbroker-connector"></a>Stap 1: De Yieldbroker-connector instellen

De eerste stap is toegang tot de pagina Gegevensconnectoren in het Microsoft 365 compliancecentrum en een **verbindingslijn** maken voor de Yieldbroker.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik vervolgens op **Gegevensconnectoren** &gt; **Yieldbroker**.

2. Klik op **de pagina Productbeschrijving opbrengstbroker** op **Nieuwe verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**

5. Meld u aan bij uw Merge1-account om de verbindingslijn te configureren.

## <a name="step-2-configure-the-yieldbroker-connector-on-the-veritas-merge1-site"></a>Stap 2: De Yieldbroker-connector configureren op de Veritas Merge1-site

De tweede stap is het configureren van de Yieldbroker-verbindingslijn op de site Samenvoegen1. Zie Gebruikershandleiding voor connectors van derden samenvoegen voor informatie over het [configureren](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Yieldbroker%20User%20Guide%20.pdf)van de Yieldbroker.

Nadat u op **Opslaan &** Voltooien  hebt geklikt, wordt de pagina Gebruikerstoewijzing in de wizard verbindingslijn in het Microsoft 365 compliancecentrum weergegeven.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Stap 3: Gebruikers in kaart brengen en de configuratie van de connector voltooien

Als u gebruikers wilt in kaart brengen en de configuratie van de verbindingslijn wilt voltooien, volgt u de volgende stappen:

1. Schakel op **de pagina Map Yieldbroker-gebruikers Microsoft 365 automatische** gebruikerstoewijzing in. De Yieldbroker-items bevatten een eigenschap met de naam E-mail, die e-mailadressen bevat voor gebruikers in uw organisatie. Als de verbindingslijn dit adres kan koppelen aan Microsoft 365 gebruiker, worden de items geïmporteerd in het postvak van die gebruiker.

2. Klik **op Volgende,** bekijk uw instellingen en ga naar de pagina Gegevensconnectors om de voortgang van het importproces voor de nieuwe **verbindingslijn** te bekijken.

## <a name="step-4-monitor-the-yieldbroker-connector"></a>Stap 4: De Yieldbroker-connector controleren

Nadat u de Yieldbroker-verbindingslijn hebt maken, kunt u de verbindingslijnstatus weergeven in het Microsoft 365 compliancecentrum.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op het tabblad Connectors en selecteer vervolgens de **Yieldbroker-verbindingslijn** om de flyoutpagina weer te geven, die de eigenschappen en informatie over de **verbindingslijn** bevat.

3. Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

- Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.