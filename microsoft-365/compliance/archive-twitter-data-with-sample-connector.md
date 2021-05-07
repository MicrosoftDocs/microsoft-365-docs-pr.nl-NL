---
title: Een connector instellen voor het archiveren van Twitter-gegevens
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
description: Lees hoe beheerders een native connector kunnen instellen en gebruiken om Twitter-gegevens te importeren in Microsoft 365.
ms.openlocfilehash: 277af8ea7367936c4c9528a8ca50ccd678745bf6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162076"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a>Een verbindingslijn instellen voor het archiveren van Twitter-gegevens (preview)

Gebruik een connector in het Microsoft 365 compliancecentrum om gegevens van Twitter te importeren en te archiveren Microsoft 365. Nadat u de verbindingslijn hebt ingesteld en geconfigureerd, wordt er verbinding gemaakt met het Twitter-account van uw organisatie (op een geplande basis), wordt de inhoud van een item geconverformeerd naar een e-mailberichtindeling en worden deze items vervolgens geïmporteerd in een postvak in Microsoft 365.

Nadat de Twitter-gegevens zijn geïmporteerd, kunt u Microsoft 365 compliancefuncties zoals Procesvoering, Inhoud zoeken, In-Place Archiveren, Auditing en Microsoft 365 bewaarbeleid toepassen op de Twitter-gegevens. Als een postvak bijvoorbeeld in de bewaring van rechtszaken wordt geplaatst of is toegewezen aan een bewaarbeleid, blijven de Twitter-gegevens behouden. U kunt gegevens van derden doorzoeken met Inhoud zoeken of het postvak koppelen waarin de Twitter-gegevens zijn opgeslagen met een bewaarder in een Advanced eDiscovery geval. Met een connector voor het importeren en archiveren van Twitter-gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

Nadat Twitter-gegevens zijn geïmporteerd, kunt u Microsoft 365 compliancefuncties zoals Procesvoering, Inhoud zoeken, In-Place Archiveren, Auditing, Communicatie compliance en Microsoft 365 bewaarbeleid toepassen op de gegevens die zijn opgeslagen in het postvak. U kunt bijvoorbeeld zoeken in Twitter-gegevens met Inhoud zoeken of het postvak koppelen waarin de gegevens zijn opgeslagen aan een bewaarder in een Advanced eDiscovery geval. Met een connector voor het importeren en archiveren van Twitter-gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="before-you-set-up-a-connector"></a>Voordat u een verbindingslijn in stelt

Voltooi de volgende vereisten voordat u een connector kunt instellen en configureren in het Microsoft 365 compliancecentrum om gegevens te importeren en te archiveren vanuit het Twitter-account van uw organisatie.

- U hebt een Twitter-account voor uw organisatie nodig. u moet zich aanmelden bij dit account bij het instellen van de verbindingslijn.

- Uw organisatie moet een geldig Azure-abonnement hebben. Als u geen bestaand Azure-abonnement hebt, kunt u zich registreren voor een van de volgende opties:

    - [Registreren voor een gratis Azure-abonnement van één jaar](https://azure.microsoft.com/free) 

    - [Registreren voor een Pay-As-You-Go Azure-abonnement](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Het [gratis Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) abonnement dat is inbegrepen bij uw Microsoft 365-abonnement biedt geen ondersteuning voor de connectors in het beveiligings- & compliancecentrum.

- De Twitter-connector kan in totaal 200.000 items in één dag importeren. Als er meer dan 200.000 Twitter-items in een dag zijn, worden geen van deze items geïmporteerd in Microsoft 365.

- De gebruiker die de Twitter-connector in het Microsoft 365 compliancecentrum (in stap 5) in stelt, moet de rol Postvak importeren exporteren in Exchange Online. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Stap 1: Een app maken in Azure Active Directory

De eerste stap is het registreren van een nieuwe app in Azure Active Directory (AAD). Deze app komt overeen met de web-app-resource die u implementeert in stap 2 voor de Twitter-connector.

Zie Een app maken in Azure Active Directory voor [stapsgewijse instructies.](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)

Tijdens het voltooien van deze stap (door de stapsgewijs instructies te volgen), worden de volgende gegevens opgeslagen in een tekstbestand. Deze waarden worden gebruikt in latere stappen in het implementatieproces.

- AAD-toepassings-id

- AAD-toepassingsgeheim

- Tenant-id

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>Stap 2: Connectorwebservice implementeren van GitHub repository naar uw Azure-account

De volgende stap is het implementeren van de broncode voor de Twitter-connector-app waarmee twitter-API wordt gebruikt om verbinding te maken met uw Twitter-account en gegevens op te halen, zodat u deze kunt importeren in Microsoft 365. De Twitter-connector die u voor uw organisatie implementeert, uploadt de items van het Twitter-account van uw organisatie naar de Azure Storage locatie die in deze stap is gemaakt. Nadat u een Twitter-connector hebt gemaakt in het Microsoft 365 compliancecentrum (in stap 5), kopieert de service Microsoft 365 Importeren de Twitter-gegevens van de Azure Storage-locatie naar een postvak in Microsoft 365. Zoals eerder is uitgelegd in de sectie Voordat [u een](#before-you-set-up-a-connector) verbindingslijn in stelt, moet u een geldig Azure-abonnement hebben om een Azure Storage maken.

De broncode voor de Twitter-connector-app implementeren:

1. Ga naar [deze GitHub site.](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)

2. Klik **op Implementeren naar Azure.**

Zie De connectorwebservice implementeren van GitHub azure-account voor [stapsgewijse instructies.](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)

Terwijl u de stapsgewijse instructies volgt om deze stap te voltooien, geeft u de volgende informatie op

- APISecretKey: u maakt dit geheim tijdens de voltooiing van deze stap. Deze wordt gebruikt in stap 5.

- tenantId: De tenant-id van uw Microsoft 365 organisatie die u hebt gekopieerd na het maken van de Twitter-app in Azure Active Directory stap 1.

Nadat u deze stap hebt doorlopen, moet u de app Service-URL kopiëren `https://twitterconnector.azurewebsites.net` (bijvoorbeeld). U moet deze URL gebruiken om stap 3, stap 4 en stap 5 te voltooien.

## <a name="step-3-create-developer-app-on-twitter"></a>Stap 3: Ontwikkelaars-app maken op Twitter

De volgende stap is het maken en configureren van een ontwikkelaars-app op Twitter. De aangepaste connector die u in stap 7 maakt, gebruikt de Twitter-app om te communiceren met de Twitter-API om gegevens te verkrijgen uit het Twitter-account van uw organisatie.

Zie De [Twitter-app maken](deploy-twitter-connector.md#step-3-create-the-twitter-app)voor stapsgewijse instructies.

Tijdens het voltooien van deze stap (door de stapsgewijse instructies te volgen), kunt u de volgende gegevens opslaan in een tekstbestand. Deze waarden worden gebruikt om de Twitter-connector-app te configureren in stap 4.

- Twitter API-sleutel

- Twitter API Secret Key

- Twitter Access-token

- Twitter Access Token Secret

## <a name="step-4-configure-the-twitter-connector-app"></a>Stap 4: De Twitter-connector-app configureren

De volgende stap is het toevoegen van configuratie-instellingen aan de Twitter-connector-app die u hebt geïmplementeerd in stap 2. U doet dit door naar de startpagina van de connector-app te gaan en deze te configureren.

Zie De connectorweb-app [configureren](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)voor stapsgewijse instructies.

Tijdens de voltooiing van deze stap (door de stapsgewijs instructies te volgen), geeft u de volgende informatie op (die u na het voltooien van de vorige stappen hebt gekopieerd naar een tekstbestand):

- Twitter API-sleutel (verkregen in stap 3)

- Twitter API Secret Key (verkregen in stap 3)

- Twitter Access-token (verkregen in stap 3)

- Twitter Access Token Secret (verkregen in stap 3)

- Azure Active Directory toepassings-id (de AAD-toepassings-id die is verkregen in stap 1)

- Azure Active Directory toepassingsgeheim (het AAD-toepassingsgeheim dat is verkregen in stap 1)

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>Stap 5: Een Twitter-connector instellen in het Microsoft 365 compliancecentrum

De laatste stap is het instellen van de Twitter-connector in het Microsoft 365 compliancecentrum dat gegevens uit het Twitter-account van uw organisatie importeert naar een opgegeven postvak in Microsoft 365. Nadat u deze stap hebt voltooid, Microsoft 365 de importservice gegevens uit het Twitter-account van uw organisatie importeren in Microsoft 365.

Zie Een Twitter-connector instellen in het Microsoft 365 [compliancecentrum voor stapsgewijse instructies.](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center) 

Tijdens het voltooien van deze stap (door de stapsgewijs instructies te volgen), geeft u de volgende informatie op (die u hebt gekopieerd naar een tekstbestand nadat u de stappen hebt voltooid).

- Url van azure-appservice (verkregen in stap 2; `https://twitterconnector.azurewebsites.net` bijvoorbeeld)

- APISecretKey (die u hebt gemaakt in stap 2)