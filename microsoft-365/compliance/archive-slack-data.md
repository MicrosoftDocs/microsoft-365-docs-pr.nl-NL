---
title: Een connector instellen voor het archiveren van Slack eDiscovery-gegevens in Microsoft 365
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
description: Beheerders kunnen een connector instellen voor het importeren en archiveren van gegevens uit Veritas Slack eDiscovery in Microsoft 365. Met deze connector kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365. Nadat u deze gegevens hebt gearchiveerd, kunt u compliancefuncties, zoals juridische bewaring, inhoudszoekbeleid en bewaarbeleid, gebruiken om gegevens van derden te beheren.
ms.openlocfilehash: 48b0a6d4d5e8f6eafaaf900aa5c773cf4f99fe72
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162309"
---
# <a name="set-up-a-connector-to-archive-slack-ediscovery-data"></a>Een connector instellen voor het archiveren van Slack eDiscovery-gegevens

Gebruik een Veritas-connector in het Microsoft 365 compliancecentrum om gegevens van derden uit sociale media, chat- en documentsamenwerkingsplatforms te importeren en te archiveren in postvakken in uw Microsoft 365 organisatie. Veritas biedt een [Slack-connector](https://globanet.com/slack/) die is geconfigureerd om items uit de gegevensbron van derden vast te leggen (op regelmatige basis) en deze items vervolgens te importeren in Microsoft 365. Slack haalt berichten en bestanden uit de Slack-API en converteert deze naar een e-mailberichtindeling en importeert het item vervolgens in postvakken van gebruikers.

Nadat Slack eDiscovery-gegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels en communicatie compliance. Als u een Slack-connector gebruikt voor het importeren en archiveren van gegevens in Microsoft 365 uw organisatie kan voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-slack-ediscovery-data"></a>Overzicht van het archiveren van Slack eDiscovery-gegevens

In het volgende overzicht wordt uitgelegd hoe het gebruik van een verbindingslijn wordt gebruikt om de Slack-informatie in Microsoft 365.

![Werkstroom voor het archiveren van marges](../media/SlackConnectorWorkflow.png)

1. Uw organisatie werkt met Slack om een Slack-site in te stellen en te configureren.

2. Eens in de 24 uur worden chatberichten van Slack eDiscovery gekopieerd naar de Veritas Merge1-site. De connector converteert ook de inhoud van een chatbericht naar een e-mailberichtindeling.

3. De Slack eDiscovery-connector die u maakt in het Microsoft 365-compliancecentrum, maakt elke dag verbinding met de Veritas Merge1-site en brengt de chatberichten over naar een veilige Azure Storage-locatie in de Microsoft-cloud.

4. De connector importeert de geconverteerde chatberichten in de postvakken van specifieke gebruikers met behulp van de waarde van de eigenschap *E-mail* en automatische gebruikerstoewijzing, zoals beschreven in stap 3. Er wordt een nieuwe submap in de map Postvak IN met de naam **Slack eDiscovery** gemaakt in de postvakken van gebruikers en de chatberichtenitems worden geïmporteerd in die map. De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.* Elk chatbericht bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer aan het chatbericht.

## <a name="before-you-begin"></a>Voordat u begint

- Maak een Veritas Merge1-account voor Microsoft-connectors. Neem contact op met [Veritas Customer Support](https://globanet.com/ms-connectors-contact)om een account te maken. U meld u aan bij dit account wanneer u de verbindingslijn maakt in stap 1.

- Verkrijg de gebruikersnaam en het wachtwoord voor het Slack Enterprise-account van uw organisatie. U moet zich aanmelden bij dit account in stap 2 wanneer u Slack configureert.

- De gebruiker die de Slack eDiscovery-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in het Microsoft 365 compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-set-up-the-slack-ediscovery-connector"></a>Stap 1: De Slack eDiscovery-connector instellen

De eerste stap is toegang tot de pagina Gegevensconnectoren in het Microsoft 365 compliancecentrum en een **verbindingslijn** maken voor Slack-gegevens.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik vervolgens op **Gegevensconnectoren**  >  **Slack eDiscovery**.

2. Klik op **de pagina Productbeschrijving van Slack eDiscovery** op **Verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**

5. Meld u aan bij uw Merge1-account om de verbindingslijn te configureren.

## <a name="step-2-configure-slack-ediscovery"></a>Stap 2: Slack eDiscovery configureren

De tweede stap is het configureren van de Slack eDiscovery-connector op de site Samenvoegen1. Zie Gebruikershandleiding voor connectors van derden [samenvoegen1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf)voor meer informatie over het configureren van de Slack eDiscovery-connector op de site Veritas Merge1.

Nadat u op **Opslaan &** Voltooien  hebt geklikt, wordt de pagina Gebruikerstoewijzing in de wizard verbindingslijn in het Microsoft 365 compliancecentrum weergegeven.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Stap 3: Gebruikers in kaart brengen en de configuratie van de connector voltooien

1. Schakel op **de pagina Externe gebruikers toewijzen Microsoft 365 gebruikers in,** automatische gebruikerstoewijzing in.

   Slack eDiscovery-items bevatten een eigenschap met de naam *E-mail,* die e-mailadressen bevat voor gebruikers in uw organisatie. Als de verbindingslijn dit adres kan koppelen aan Microsoft 365 gebruiker, worden de items geïmporteerd in het postvak van die gebruiker.

2. Klik **op Volgende,** bekijk uw instellingen en ga naar de pagina Gegevensconnectors om de voortgang van het importproces voor de nieuwe **verbindingslijn** te bekijken.

## <a name="step-4-monitor-the-slack-ediscovery-connector"></a>Stap 4: De Slack eDiscovery-connector controleren

Nadat u de Slack eDiscovery-verbindingslijn hebt gebruikt, kunt u de verbindingslijnstatus weergeven in het Microsoft 365 compliancecentrum.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com) en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **het tabblad Verbindingslijnen** en selecteer vervolgens de **Slack eDiscovery-connector** om de flyoutpagina weer te geven. Deze pagina bevat de eigenschappen en informatie over de verbindingslijn.

3. Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat informatie over de gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

- Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.