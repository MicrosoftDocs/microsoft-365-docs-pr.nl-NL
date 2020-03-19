---
title: Werken met Microsoft Consulting Services
description: voorbereiding en stappen die moeten worden gevolgd om met MCS samen te werken om uw apps te verpakken
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie, apps, MCS, verpakking
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0cb4da85b5548ced757197a3af818e212b065b47
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806829"
---
# <a name="working-with-microsoft-consulting-services"></a>Werken met Microsoft Consulting Services

U contact opnemen met Microsoft Consulting Services (MCS) om uw apps te laten verpakken voor gebruik met Microsoft Managed Desktop. Werk voor meer informatie samen met uw accountvertegenwoordiger contact op met MCS en bereik uw specifieke app-verpakkingsproject.

## <a name="roles-and-responsibilities"></a>Rollen en verantwoordelijkheden

Als u wilt werken met mcs-appverpakking, **moet u deze elementen opgeven:**

- De broninstallatiebestanden (bijvoorbeeld setup.exe of .msi).
- De installatie-instructies, met details over hoe de uiteindelijke installatie eruit moet zien. Moet er bijvoorbeeld een snelkoppeling naar de app zijn? Wat moet de zichtbaarheid van de app zijn? Moet de app verbinding maken met een server en zo ja, welke? Zie voor meer informatie de sjabloon voor de [aanvraag voor de aanvraag](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)voor de verpakking van toepassingen .
- U moet uw eigen acceptatietests uitvoeren om te controleren of de app werkt zoals u dat nodig hebt in uw omgeving.

**MCS zal deze acties verzorgen:**

- Controleren of de app verboden of beperkt is in de Microsoft Managed Desktop-omgeving.
- Het testen van de installatie, het starten en verwijderen van de app om compatibiliteit met Windows 10 te garanderen. Als MCS een compatibiliteitsprobleem ontdekt, geven ze de app af aan het [Desktop App Assure-programma](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) voor herstel.
- De app in pakken volgens uw specificatie en vervolgens de implementatie van apps testen met Behulp van Microsoft Intune.

## <a name="app-delivery-schedule"></a>App-leveringsschema

Start het verpakkingsproces door de app-informatie te uploaden naar de Microsoft Managed Desktop-portal. Het verpakkingsteam bespreekt elke donderdag nieuwe inzendingen. Na beoordeling en verpakking worden de verpakte apps de volgende vrijdag geleverd. Maximaal vijf apps per week kunnen worden verpakt om te starten, maar de service kan worden geschaald om aan uw behoeften te voldoen.

![agenda met app-instroom op een donderdag (de 21e in dit voorbeeld), mediavalidatie de volgende dag, verpakking op de volgende maandag (de 25e) en app-levering op de daaropvolgende vrijdag (de 29e)](../../media/MCS-cal.png)

U ontvangt een melding zodra de app is geleverd. Op dat moment hebt u 21 dagen de tijd om acceptatietests uit te voeren en het werk af te tekenen in de Microsoft Managed Desktop-portal. Als u tijdens uw acceptatietest een probleem met de app ontdekt, weigert u de app in de Microsoft Managed Desktop-portal en wordt u via e-mail verbonden met een MCS-pakketer om het probleem te begrijpen en op te lossen.

## <a name="testing-accounts-and-environment"></a>Het testen van accounts en omgeving

Als u de migratie naar Microsoft Intune wilt voltooien, raden we u aan bepaalde machtigingen te verstrekken:
 
-   Toegang tot de app-implementatiemogelijkheden van Microsoft Intune voor de verpakker om de app toe te voegen en toe te wijzen 
-   Test groepen, gebruikersaccounts en licenties voor de verpakkers om de apps te kunnen testen

MCS gebruikt deze machtigingen om de volgende acties uit te voeren:
 
-   Ervoor zorgen dat de app werkt op virtuele machine die is geconfigureerd voor Microsoft Managed Desktop
-   De app uploaden naar Microsoft Intune voor implementatie naar uw gebruikers

Zonder deze machtigingen is het mogelijk voor MCS om verder te gaan, maar ze zullen niet in staat zijn om de toepassingen te uploaden naar uw omgeving.


