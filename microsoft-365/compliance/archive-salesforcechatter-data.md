---
title: Een connector instellen voor het archiveren van Salesforce Chatter-gegevens in Microsoft 365
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
description: Beheerders kunnen een connector instellen voor het importeren en archiveren van Salesforce Chatter-gegevens van Veritas naar Microsoft 365. Met deze connector kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365. Nadat u deze gegevens hebt gearchiveerd, kunt u compliancefuncties, zoals juridische bewaring, inhoudszoekbeleid en bewaarbeleid, gebruiken om gegevens van derden te beheren.
ms.openlocfilehash: c04dc3026eaa5abb23b332dbae826c052344da31
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162321"
---
# <a name="set-up-a-connector-to-archive-salesforce-chatter-data"></a>Een connector instellen voor het archiveren van Salesforce Chatter-gegevens

Gebruik een Veritas-connector in het Microsoft 365 compliancecentrum om gegevens van het Salesforce Chatter-platform te importeren en te archiveren in gebruikerspostvakken in uw Microsoft 365 organisatie. Veritas biedt een [Salesforce Chatter-connector](http://globanet.com/chatter/) die items uit de gegevensbron van derden vast legt en deze items importeert naar Microsoft 365. De connector converteert de inhoud, zoals chats, bijlagen en berichten van Salesforce Chatter naar een e-mailberichtindeling en importeert deze items vervolgens in het postvak van de gebruiker in Microsoft 365.

Nadat Salesforce Chatter-gegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels. Als u een Salesforce Chatter-connector gebruikt om gegevens te importeren en te archiveren in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-salesforce-chatter-data"></a>Overzicht van het archiveren van Salesforce Chatter-gegevens

In het volgende overzicht wordt uitgelegd hoe u een verbindingslijn gebruikt om de Salesforce Chatter-gegevens te archiveren in Microsoft 365.

![Archiveringswerkstroom voor Salesforce Chatter-gegevens](../media/SalesforceChatterConnectorWorkflow.png)

1. Uw organisatie werkt samen met Salesforce Chatter om een Salesforce Chatter-site in te stellen en te configureren.

2. Eens in de 24 uur worden Salesforce Chatter-items gekopieerd naar de Veritas Merge1-site. De connector bevat ook Salesforce Chatter-items naar een e-mailberichtindeling.

3. De Salesforce Chatter-connector die u maakt in het Microsoft 365 compliancecentrum, maakt elke dag verbinding met de Veritas Merge1-site en draagt de Chatter-inhoud over naar een veilige Azure Storage-locatie in de Microsoft-cloud.

4. De connector importeert de geconverteerde items in de postvakken van specifieke gebruikers met behulp van de waarde van de eigenschap *E-mail* van de automatische gebruikerstoewijzing, zoals beschreven in [stap 3.](#step-3-map-users-and-complete-the-connector-setup) Een submap in de map Postvak IN met de naam **Salesforce Chatter** wordt gemaakt in de postvakken van gebruikers en items worden geïmporteerd in die map. De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.* Elk Chatter-item bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer van het item.

## <a name="before-you-begin"></a>Voordat u begint

- Maak een Merge1-account voor Microsoft-connectors. Neem contact op met [Veritas Customer Support](https://www.veritas.com/content/support/)om een account te maken. U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.

- Maak een Salesforce-toepassing en verkrijg een token bij [https://salesforce.com](https://salesforce.com) . U moet zich aanmelden bij het Salesforce-account als beheerder en een persoonlijk token van een gebruiker krijgen om gegevens te importeren. Daarnaast moeten triggers worden gepubliceerd op de Chatter-site om updates, verwijderen en bewerken vast te leggen. Deze triggers maken een bericht op een kanaal en Samenvoegen1 legt de informatie vast uit het kanaal. Zie Gebruikershandleiding voor connectors van derden samenvoegen [voor stapsgewijs](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf)instructies over het maken van de toepassing en het verkrijgen van het token.

- De gebruiker die de Salesforce Chatter-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in het Microsoft 365 compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-set-up-the-salesforce-chatter-connector"></a>Stap 1: De Salesforce Chatter-connector instellen

De eerste stap is toegang tot de pagina Gegevensconnectoren in het Microsoft 365 compliancecentrum en een **verbindingslijn** maken voor Chatter-gegevens.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik vervolgens op **Gegevensconnectoren**  >  **Salesforce Chatter**.

2. Klik op **de pagina Productbeschrijving van Salesforce Chatter** op **Verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**

5. Meld u aan bij uw Merge1-account om de verbindingslijn te configureren.

## <a name="step-2-configure-the-salesforce-chatter-on-the-veritas-merge1-site"></a>Stap 2: De Salesforce-chatfunctie configureren op de Veritas Merge1-site

De tweede stap is het configureren van de Salesforce Chatter-connector op de Veritas Merge1-site. Zie Gebruikershandleiding voor [connectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf)van derden samenvoegen voor informatie over het configureren van de Salesforce Chatter-connector.

Nadat u op Opslaan & Voltooien  hebt geklikt, wordt de pagina Gebruikerstoewijzing in de wizard Verbindingslijn in Microsoft 365 compliancecentrum weergegeven. 

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Stap 3: Gebruikers in kaart brengen en de configuratie van de connector voltooien

Als u gebruikers wilt in kaart brengen en de configuratie van de verbindingslijn wilt voltooien in het Microsoft 365 compliancecentrum, volgt u de volgende stappen:

1. Schakel op **de pagina Gebruikers van Salesforce Chatter toewijzen Microsoft 365 gebruikers automatisch** toewijzen in. De Salesforce Chatter-items bevatten een eigenschap met de naam E-mail, die e-mailadressen bevat voor gebruikers in uw organisatie. Als de verbindingslijn dit adres kan koppelen aan Microsoft 365 gebruiker, worden de items geïmporteerd in het postvak van die gebruiker.

2. klik **op Volgende,** controleer uw instellingen en ga naar de pagina Gegevensconnectors om de voortgang van het importproces voor de nieuwe **verbindingslijn** te bekijken.

## <a name="step-4-monitor-the-salesforce-chatter-connector"></a>Stap 4: De Salesforce Chatter-connector controleren

Nadat u de Salesforce Chatter-connector hebt gebruikt, kunt u de verbindingslijnstatus bekijken in het Microsoft 365 compliancecentrum.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. klik op **het tabblad Connectors** en klik vervolgens op de Salesforce **Chatter-verbindingslijn** om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.

3. Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

- Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.