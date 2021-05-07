---
title: Een verbindingslijn instellen voor het archiveren van Rode staart Speak-gegevens in Microsoft 365
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
description: Beheerders kunnen een verbindingslijn instellen voor het importeren en archiveren van rode tail Speak-gegevens van Veritas naar Microsoft 365. Met deze connector kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365. Nadat u deze gegevens hebt gearchiveerd, kunt u compliancefuncties, zoals juridische bewaring, inhoudszoekbeleid en bewaarbeleid, gebruiken om gegevens van derden te beheren.
ms.openlocfilehash: ee9540b4000387454eb177f864407e03abd25bc6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162343"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data"></a>Een connector instellen voor het archiveren van Redtail Speak-gegevens

Gebruik een Veritas-connector in het Microsoft 365 compliancecentrum om gegevens te importeren en te archiveren vanuit de Redtail Speak to user mailboxes in your Microsoft 365 organization. Veritas biedt u een [Redtail Speak-connector](https://globanet.com/redtail/) die is geconfigureerd voor het vastleggen van items van de SFTP-server van uw organisatie waar de items worden ontvangen van Redtail. De verbindingslijn converteert de inhoud van Redtail Speak naar een e-mailberichtindeling en importeert deze items vervolgens in het postvak van de gebruiker in Microsoft 365.

Nadat Redtail Speak-gegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels. Als u een Redtail Speak-verbindingslijn gebruikt om gegevens te importeren en te archiveren in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-the-redtail-speak-data"></a>Overzicht van het archiveren van de Redtail Speak-gegevens

In het volgende overzicht wordt uitgelegd hoe u een verbindingslijn gebruikt om de Gegevens van Redtail Speak te archiveren in Microsoft 365.

![Archiveringswerkstroom voor Redtail Speak-gegevens](../media/RedtailSpeakConnectorWorkflow.png)

1. Uw organisatie werkt samen met Redtail Speak om een SMTP-gateway in te stellen en te configureren waar berichten dagelijks worden doorgestuurd van Redtail Speak naar de SFTP-server van uw organisatie.

2. Elke 24 uur worden de Redtail Speak-items gekopieerd naar de Veritas Merge1-site. De connector converteert ook de Redtail Speak-items naar een e-mailberichtindeling.

3. De Redtail Speak-connector die u maakt in het Microsoft 365 compliancecentrum, maakt elke dag verbinding met de Veritas Merge1-site en brengt de berichten over naar een veilige Azure Storage locatie in de Microsoft-cloud.

4. De connector importeert de geconverteerde Redtail Speak-items naar de postvakken van specifieke gebruikers met behulp van de waarde van de eigenschap *E-mail* van de automatische gebruikerstoewijzing, zoals beschreven in [stap 3.](#step-3-map-users-and-complete-the-connector-setup) Er wordt een submap in de map Postvak IN met de naam **Redtail Speak** gemaakt in de postvakken van de gebruiker en de items worden geïmporteerd in die map. De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.* Elk Redtail Speak-item bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer aan het item.

## <a name="before-you-begin"></a>Voordat u begint

- Maak een Veritas Merge1-account voor Microsoft-connectors. Neem contact op met [Veritas Customer Support](https://www.veritas.com/content/support/)om een account te maken. U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.

- In stap 2 moet u de SFTP-server van uw organisatie opgeven. Deze stap is nodig zodat Veritas Merge1 contact kan opnemen om Redtail Speak-gegevens te verzamelen via SFTP.

- De gebruiker die de Connector Redtail Speak Importer maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina Gegevensconnectors in het Microsoft 365 compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online groep. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-set-up-the-redtail-speak-connector"></a>Stap 1: De Verbindingslijn Redtail Speak instellen

De eerste stap is toegang tot de pagina Gegevensconnectoren in het Microsoft 365 compliancecentrum en een **verbindingslijn** maken voor de Gegevens van Redtail Speak.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en selecteer **Gegevensconnectoren** &gt; **Redtail Speak**.

2. Selecteer op **de pagina Redtail Speak** productbeschrijving de optie Nieuwe **verbindingslijn toevoegen.**

3. Selecteer accepteren op de pagina **Servicevoorwaarden.**

4. Voer een unieke naam in die de verbindingslijn identificeert en selecteer **volgende**.

5. Meld u aan bij uw Merge1-account om de verbindingslijn te configureren.

## <a name="step-2-configure-the-redtail-speak-connector-on-the-veritas-merge1-site"></a>Stap 2: De Verbindingslijn Redtail Speak configureren op de Veritas Merge1-site

De tweede stap is het configureren van de Redtail Speak-verbindingslijn op de site Samenvoegen1. Zie Handleiding [Verbindingslijnen](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf)van derden samenvoegen voor informatie over het configureren van de Redtail Speak-connector.

Nadat u Opslaan & hebt  **geselecteerd,** wordt de pagina Gebruikerstoewijzing in de wizard Verbindingslijn in het Microsoft 365 weergegeven.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Stap 3: Gebruikers in kaart brengen en de configuratie van de connector voltooien

Als u gebruikers wilt in kaart brengen en de configuratie van de verbindingslijn wilt voltooien, volgt u de volgende stappen:

1. Schakel automatische **gebruikerstoewijzing in op de pagina Map Redtail Speak Microsoft 365 gebruikers.** De Redtail Speak-items bevatten een eigenschap met de naam E-mail, die e-mailadressen bevat voor gebruikers in uw organisatie. Als de verbindingslijn dit adres kan koppelen aan Microsoft 365 gebruiker, worden de items geïmporteerd in het postvak van die gebruiker.

2. Selecteer **Volgende,** controleer uw instellingen en ga naar de pagina Gegevensconnectors om de voortgang van het importproces voor de nieuwe **verbindingslijn** te bekijken.

## <a name="step-4-monitor-the-redtail-speak-connector"></a>Stap 4: De Verbindingslijn Redtail Speak controleren

Nadat u de Verbindingslijn Redtail Speak hebt gebruikt, kunt u de verbindingslijnstatus weergeven in het Microsoft 365 compliancecentrum.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en selecteer **Gegevensconnectoren** in de linkernavigatienavigatie.

2. Selecteer het **tabblad Verbindingslijnen** en selecteer vervolgens de **Verbindingslijn Redtail Speak** om de flyoutpagina weer te geven. Op deze pagina worden eigenschappen en informatie over de verbindingslijn weergegeven.

3. Selecteer **onder Verbindingsstatus met bron** de koppeling **Logboek** downloaden om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

- Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.