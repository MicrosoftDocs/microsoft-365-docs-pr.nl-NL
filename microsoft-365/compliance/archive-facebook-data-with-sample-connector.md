---
title: Een verbindingslijn instellen om Facebook-gegevens te archiveren
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
description: Meer informatie over het instellen van & verbindingslijn gebruiken in het Microsoft 365 compliancecentrum om & archiefgegevens van Facebook Business-pagina's te Microsoft 365.
ms.openlocfilehash: 616466a3af83c1558184526aa463f68c10ef9e70
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162068"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a>Een verbindingslijn instellen om Facebook-gegevens te archiveren (voorbeeld)

Gebruik een verbindingslijn in het Microsoft 365 compliancecentrum om gegevens van Facebook Business-pagina's te importeren en te archiveren Microsoft 365. Nadat u de verbindingslijn hebt ingesteld en geconfigureerd, wordt er verbinding gemaakt met de Facebook Business-pagina (op een geplande basis), wordt de inhoud van Facebook-items geconverformeerd naar een e-mailberichtindeling en worden deze items vervolgens geïmporteerd in een postvak in Microsoft 365.

Nadat de Facebook-gegevens zijn geïmporteerd, kunt u Microsoft 365 compliancefuncties zoals Proces bewaring, Inhoud zoeken, In-Place Archiveren, Auditing, Communicatie compliance en Microsoft 365 bewaarbeleid toepassen op de Facebook-gegevens. Als een postvak bijvoorbeeld in de bewaring van rechtszaken wordt geplaatst of is toegewezen aan een bewaarbeleid, blijven de Facebook-gegevens behouden. U kunt gegevens van derden doorzoeken met Inhoud zoeken of het postvak koppelen waarin de Facebook-gegevens zijn opgeslagen met een bewaarder in een Advanced eDiscovery geval. Met een connector voor het importeren en archiveren van Facebook-gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Vereisten voor het instellen van een connector voor Facebook Business-pagina's

Voltooi de volgende vereisten voordat u een verbindingslijn kunt instellen en configureren in het Microsoft 365 compliancecentrum om gegevens te importeren en te archiveren van de Facebook Business-pagina's van uw organisatie. 

- U hebt een Facebook-account nodig voor de bedrijfspagina's van uw organisatie (u moet zich aanmelden bij dit account bij het instellen van de verbindingslijn). Op dit moment kunt u alleen gegevens archiveren van Facebook Business-pagina's. u kunt geen gegevens archiveren van afzonderlijke Facebook-profielen.

- Uw organisatie moet een geldig Azure-abonnement hebben. Als u geen bestaand Azure-abonnement hebt, kunt u zich registreren voor een van de volgende opties:

    - [Registreren voor een gratis Azure-abonnement van één jaar](https://azure.microsoft.com/free)

    - [Registreren voor een Pay-As-You-Go Azure-abonnement](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Het [gratis Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) abonnement dat is inbegrepen bij uw Microsoft 365-abonnement biedt geen ondersteuning voor de connectors in het beveiligings- & compliancecentrum.

- De connector voor Facebook Business-pagina's kan in totaal 200.000 items in één dag importeren. Als er meer dan 200.000 Facebook Business-items in een dag zijn, worden geen van deze items geïmporteerd in Microsoft 365.

- De gebruiker die de aangepaste connector in het Microsoft 365 compliancecentrum (in stap 5) in stelt, moet de rol Postvak importeren exporteren in Exchange Online. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Stap 1: Een app maken in Azure Active Directory

De eerste stap is het registreren van een nieuwe app in Azure Active Directory (AAD). Deze app komt overeen met de web-app-resource die u implementeert in stap 4 en stap 5 voor de Facebook-connector. 

Zie Een app maken in Azure Active Directory voor [stapsgewijse instructies.](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)

Tijdens het voltooien van deze stap (met behulp van de vorige stapsgewijse instructies), wordt de volgende informatie opgeslagen in een tekstbestand. Deze waarden worden gebruikt in latere stappen in het implementatieproces.

- AAD-toepassings-id

- AAD-toepassingsgeheim

- Tenant-id

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Stap 2: De connectorwebservice implementeren van GitHub naar uw Azure-account

De volgende stap is het implementeren van de broncode voor de connector-app voor Facebook Business-pagina's waarmee de Facebook-API wordt gebruikt om verbinding te maken met uw Facebook-account en gegevens op te halen, zodat u deze kunt importeren in Microsoft 365. De Facebook-connector die u voor uw organisatie implementeert, uploadt de items van uw Facebook Business-pagina's naar de Azure Storage locatie die in deze stap is gemaakt. Nadat u een Verbindingslijn voor Facebook-zakelijke pagina's hebt gemaakt in het Microsoft 365 compliancecentrum (in stap 5), kopieert de importservice de gegevens van de Facebook-bedrijfspagina's vanaf de Azure Storage-locatie naar een postvak in uw Microsoft 365 organisatie. Zoals u eerder hebt uitgelegd in [de](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) sectie Vereisten, moet u een geldig Azure-abonnement hebben om een Azure Storage maken.

Zie De connectorwebservice implementeren van GitHub azure-account voor [stapsgewijse instructies.](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)

In de stapsgewijs instructies voor het voltooien van deze stap geeft u de volgende informatie:

- APISecretKey: u maakt dit geheim tijdens de voltooiing van deze stap. Deze wordt gebruikt in stap 5.

- TenantId: de tenant-id van uw Microsoft 365 organisatie die u hebt gekopieerd na het maken van de Facebook-connector-app in Azure Active Directory stap 1.

Nadat u deze stap hebt uitgevoerd, moet u de URL van de Azure-app-service kopiëren https://fbconnector.azurewebsites.net) (bijvoorbeeld. U moet deze URL gebruiken om stap 3, stap 4 en stap 5 te voltooien.

## <a name="step-3-register-the-web-app-on-facebook"></a>Stap 3: De web-app registreren op Facebook

De volgende stap is het maken en configureren van een nieuwe app op Facebook. De Facebook-verbindingslijn voor zakelijke pagina's die u in stap 5 maakt, gebruikt de Facebook-web-app om te communiceren met de Facebook-API om gegevens te verkrijgen van de Facebook Business-pagina's van uw organisatie.

Zie De [Facebook-app registreren](deploy-facebook-connector.md#step-3-register-the-facebook-app)voor stapsgewijse instructies.

Tijdens het voltooien van deze stap (door de stapsgewijse instructies te volgen), kunt u de volgende gegevens opslaan in een tekstbestand. Deze waarden worden gebruikt om de Facebook-connector-app te configureren in stap 4.

- Facebook-toepassing-id

- Facebook-toepassingsgeheim

- Facebook-webhooks verifiëren token

## <a name="step-4-configure-the-facebook-connector-app"></a>Stap 4: De Facebook-connector-app configureren

De volgende stap is het toevoegen van configuratie-instellingen aan de Facebook-connector-app die u hebt geüpload toen u de Azure Web App-resource maakte in stap 1. U doet dit door naar de startpagina van de connector-app te gaan en deze te configureren.

Zie De [Facebook-connector-app configureren](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)voor stapsgewijse instructies.

Tijdens het voltooien van deze stap (door de stapsgewijs instructies te volgen), geeft u de volgende informatie op (die u na het voltooien van de vorige stappen hebt gekopieerd naar een tekstbestand):

- Facebook-toepassing-id (verkregen in stap 3)

- Facebook-toepassingsgeheim (verkregen in stap 3)

- Facebook-webhaken verifiëren token (verkregen in stap 3)

- Azure Active Directory toepassings-id (de AAD-toepassings-id die is verkregen in stap 1)

- Azure Active Directory toepassingsgeheim (het AAD-toepassingsgeheim dat is verkregen in stap 1)

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a>Stap 5: Een verbindingslijn voor Facebook Business-pagina's instellen in het Microsoft 365 compliancecentrum

De laatste stap is het instellen van de verbindingslijn in het Microsoft 365 compliancecentrum dat gegevens van uw Facebook Business-pagina's importeert naar een opgegeven postvak in Microsoft 365. Nadat u deze stap hebt voltooid, wordt Microsoft 365 de importservice gegevens van uw Facebook Business-pagina's geïmporteerd naar Microsoft 365.

Zie Stap 5: Een Facebook-connector instellen in het Microsoft 365 [compliancecentrum voor stapsgewijse instructies.](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center) 

Tijdens het voltooien van deze stap (door de stapsgewijs instructies te volgen), geeft u de volgende informatie op (die u na het voltooien van de stappen hebt gekopieerd naar een tekstbestand).

- AAD-toepassings-id (verkregen in stap 1)

- URL van azure-appservice (verkregen in stap 1; bijvoorbeeld: https://fbconnector.azurewebsites.net)

- APISecretKey (die u hebt gemaakt in stap 2)