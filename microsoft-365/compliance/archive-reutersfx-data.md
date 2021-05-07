---
title: Een connector instellen voor het archiveren van Reuters FX-gegevens in Microsoft 365
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
description: Beheerders kunnen een connector instellen voor het importeren en archiveren van Reuters FX-gegevens van Veritas naar Microsoft 365. Met deze connector kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365. Nadat u deze gegevens hebt gearchiveerd, kunt u compliancefuncties, zoals juridische bewaring, inhoudszoekbeleid en bewaarbeleid, gebruiken om gegevens van derden te beheren.
ms.openlocfilehash: d9d73cd28a64b76651de6024ec39faf7b406c219
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162340"
---
# <a name="set-up-a-connector-to-archive-reuters-fx-data"></a>Een connector instellen voor het archiveren van Reuters FX-gegevens

Gebruik een Veritas-connector in het Microsoft 365 compliancecentrum om gegevens van het Reuters FX-platform te importeren en te archiveren naar postvakken van gebruikers in uw Microsoft 365 organisatie. Veritas biedt u een [Reuters FX-connector](https://globanet.com/reuters-fx/) die is geconfigureerd om items uit de gegevensbron van derden vast te leggen (op regelmatige basis) en deze items vervolgens te importeren in Microsoft 365. De connector converteert de valuta- en fx-tarieven van het Reuters FX-account naar een e-mailberichtindeling en importeert deze items vervolgens in het postvak van de gebruiker in Microsoft 365.

Nadat Reuters FX-gegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels en communicatie compliance. Met een Reuters FX-connector voor het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-reuters-fx-data"></a>Overzicht van het archiveren van Reuters FX-gegevens

In het volgende overzicht wordt uitgelegd hoe het gebruik van een connector voor het archiveren van Reuters FX-gegevens in Microsoft 365.

![Archiveringswerkstroom voor Reuters FX-gegevens](../media/ReutersFXConnectorWorkflow.png)

1. Uw organisatie werkt samen met Reuters FX om een Reuters FX-site in te stellen en te configureren.

2. Elke 24 uur worden Reuters FX-items gekopieerd naar de Veritas Merge1-site. De verbindingslijn converteert de items ook naar een e-mailberichtindeling.

3. De Reuters FX-connector die u maakt in het Microsoft 365 compliancecentrum, maakt elke dag verbinding met de Veritas Merge1-site en draagt de inhoud over naar een veilige Azure Storage-locatie in de Microsoft-cloud.

4. De connector importeert de items in de postvakken van specifieke gebruikers met behulp van de waarde van de eigenschap *E-mail* van de automatische gebruikerstoewijzing, zoals beschreven in [stap 3.](#step-3-map-users-and-complete-the-connector-setup) Een submap in de map Postvak IN met de naam **Reuters FX** wordt gemaakt in de postvakken van de gebruiker en de items worden geïmporteerd in die map. De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.* Elk Reuters FX-item bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer aan het item.

## <a name="before-you-begin"></a>Voordat u begint

- Maak een Veritas Merge1-account voor Microsoft-connectors. Neem contact op met [Veritas Customer Support](https://globanet.com/contact-us)om een account te maken. U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.

- De gebruiker die de Reuters FX-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in het Microsoft 365 compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-set-up-the-reuters-fx-connector"></a>Stap 1: De Reuters FX-connector instellen

De eerste stap is om toegang te krijgen tot de pagina **Gegevensconnectoren** in de Microsoft 365 en een connector te maken voor Reuters FX-gegevens.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik vervolgens op **Gegevensconnectoren**  >  **Reuters FX**.

2. Klik op **de pagina Productbeschrijving van Reuters FX** op **Verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**

5. Meld u aan bij uw Merge1-account om de verbindingslijn te configureren.

## <a name="step-2-configure-the-reuters-fx-connector-on-the-veritas-merge1-site"></a>Stap 2: De Reuters FX-connector configureren op de Veritas Merge1-site

De tweede stap is het configureren van de Reuters FX-connector op de Veritas Merge1-site. Zie Gebruikershandleiding voor connectors van derden samenvoegen voor informatie over het configureren van de Reuters [FX-connector.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20FX%20User%20Guide%20.pdf)

Nadat u op **Opslaan &** Voltooien  hebt geklikt, wordt de pagina Gebruikerstoewijzing in de wizard verbindingslijn in het Microsoft 365 compliancecentrum weergegeven.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Stap 3: Gebruikers in kaart brengen en de configuratie van de connector voltooien

Als u gebruikers wilt in kaart brengen en de configuratie van de verbindingslijn wilt voltooien in het Microsoft 365 compliancecentrum, volgt u de onderstaande stappen:

1. Schakel op **de pagina Map Reuters FX-gebruikers Microsoft 365 automatische** gebruikerstoewijzing in.

   Reuters FX-items bevatten een eigenschap met de naam *E-mail,* die e-mailadressen bevat voor gebruikers in uw organisatie. Als de verbindingslijn dit adres kan koppelen aan Microsoft 365 gebruiker, worden de items geïmporteerd in het postvak van die gebruiker.

2. Klik **op Volgende,** bekijk uw instellingen en ga naar de pagina Gegevensconnectors om de voortgang van het importproces voor de nieuwe **verbindingslijn** te bekijken.

## <a name="step-4-monitor-the-reuters-fx-connector"></a>Stap 4: De Reuters FX-connector controleren

Nadat u de Reuters FX-connector hebt gebruikt, kunt u de connectorstatus bekijken in het Microsoft 365 compliancecentrum.

1. Ga naar <https://compliance.microsoft.com/> en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **het tabblad Connectors** en selecteer vervolgens de **Reuters FX-connector** om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.

3. Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

- Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.