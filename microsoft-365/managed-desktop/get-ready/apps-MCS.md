---
title: Werken met Microsoft Consulting Services
description: Voorbereidingen en stappen die u moet volgen om samen te werken met MCS om uw apps te verpakken
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 7a967f5e4b2678b55ed87f2eaa68590703c55805
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840884"
---
# <a name="working-with-microsoft-consulting-services"></a>Werken met Microsoft Consulting Services

U kunt contact houden met Microsoft Consulting Services (MCS) om uw apps te laten verpakken voor gebruik met Microsoft Managed Desktop. Voor meer informatie kunt u contact opnemen met uw accountvertegenwoordiger om contact op te nemen met MCS en het specifieke app-verpakkingsproject te bekijken.

## <a name="roles-and-responsibilities"></a>Rollen en verantwoordelijkheden

Als u wilt werken met mcs-app-verpakking, **moet u de volgende elementen leveren:**

- De broninstallateurbestanden (bijvoorbeeld setup.exe of .msi).
- De installatie-instructies, met informatie over hoe de uiteindelijke installatie eruit moet zien. Moet er bijvoorbeeld een bureaubladsnelkoppeling naar de app zijn? Wat moet de zichtbaarheid van de app zijn? Moet de app verbinding maken met een server en zo ja, welke? Zie de aanvraagsjabloon [voor aanvraag voor toepassingen voor meer informatie.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)
- U moet uw eigen acceptatietest uitvoeren om te controleren of de app werkt zoals u dat nodig hebt in uw omgeving.

**MCS zorgt voor de volgende acties:**

- Controleren of de app is verboden of beperkt in de Microsoft Managed Desktop omgeving.
- Testen van de installatie, het starten en verwijderen van de app om ervoor te zorgen dat de app compatibel is met Windows 10. Als MCS een compatibiliteitsprobleem detecteert, wordt de app door mcs overgehandigd aan het [App Assure-programma](/fasttrack/products-and-capabilities#app-assure) voor herstel.
- De app inpakken op uw specificatie en vervolgens app-implementatie testen met Microsoft Intune.

## <a name="app-delivery-schedule"></a>Planning voor app-bezorging

Start het verpakkingsproces door de app-informatie te uploaden naar de Microsoft Managed Desktop portal. Het verpakkingsteam bekijkt elke donderdag nieuwe inzendingen. Na controle en verpakking worden de verpakte apps de volgende vrijdag bezorgd. Er kunnen maximaal vijf apps per week worden verpakt om te starten, maar de service kan worden opgeschaald naar uw behoeften.

![agenda met app-instroom op een donderdag (de 21e in dit voorbeeld), mediavalidatie de volgende dag, verpakking op de volgende maandag (de 25e) en app-bezorging op de volgende vrijdag (de 29e)](../../media/MCS-cal.png)

U krijgt een melding zodra de app is geleverd. Op dat moment hebt u 21 dagen de tijd om acceptatietests uit te voeren en het werk in de Microsoft Managed Desktop goed te keuren. Als u tijdens uw acceptatietest een probleem met de app ontdekt, weigert u de app in de Microsoft Managed Desktop-portal en wordt u via e-mail verbonden met een MCS-packager om het probleem te begrijpen en op te lossen.

## <a name="testing-accounts-and-environment"></a>Accounts en omgeving testen

Het verpakkingsteam kan de migratie naar Microsoft Intune voltooien door bepaalde machtigingen op te geven:

- Toegang tot Microsoft Intune app-implementatiemogelijkheden voor de packager om de app toe te voegen en toe te wijzen
- Testgroepen, gebruikersaccounts en licenties voor de verwerkers om de apps te kunnen testen

MCS gebruikt deze machtigingen om de volgende acties uit te voeren:

- Ervoor zorgen dat de app werkt op een virtuele computer die is geconfigureerd voor Microsoft Managed Desktop
- De app uploaden naar Microsoft Intune voor implementatie naar uw gebruikers

Zonder deze machtigingen kan MCS verder gaan, maar kunnen ze de toepassingen niet uploaden naar uw omgeving.
