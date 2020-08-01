---
title: Werken met Microsoft Consulting Services
description: voorbereiding en stappen om te volgen om met MCS te werken om uw apps te verpakken
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie, apps, MCS, verpakking
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d2a6c09e1bcb84885e607d133c14e26e08e3c621
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530161"
---
# <a name="working-with-microsoft-consulting-services"></a>Werken met Microsoft Consulting Services

U contact opnemen met Microsoft Consulting Services (MCS) om uw apps te laten verpakken voor gebruik met Microsoft Managed Desktop. Voor exacte details u contact opnemen met uw accountvertegenwoordiger om contact op te nemen met MCS en uw specifieke app-verpakkingsproject te bekijken.

## <a name="roles-and-responsibilities"></a>Rollen en verantwoordelijkheden

Om te werken met MCS app verpakking, **moet u deze elementen:**

- De broninstallateurbestanden (bijvoorbeeld setup.exe of .msi).
- De installatie-instructies, met vermelding van details over hoe de uiteindelijke installatie eruit moet zien. Moet er bijvoorbeeld een snelkoppeling op het bureaublad naar de app zijn? Wat moet de zichtbaarheid van de app zijn? Moet de app verbinding maken met een server en zo ja, welke? Zie de [sjabloon aanvraagaanvraag voor toepassingen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)voor meer informatie.
- U moet uw eigen acceptatietests uitvoeren om te controleren of de app werkt zoals u deze nodig hebt in uw omgeving.

**MCS zal deze acties azen:**

- Controleren of de app verboden of beperkt is in de Microsoft Managed Desktop-omgeving.
- Het testen van de installatie, het starten en verwijderen van de app om compatibiliteit met Windows 10 te garanderen. Als MCS een compatibiliteitsprobleem ontdekt, geven ze de app af aan het [Desktop App Assure-programma](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) voor herstel.
- De app naar uw specificaties verpakken en vervolgens de implementatie van de app testen met Microsoft Intune.

## <a name="app-delivery-schedule"></a>App-leveringsschema

Start het verpakkingsproces door de app-informatie te uploaden naar de Microsoft Managed Desktop-portal. Het verpakkingsteam beoordeelt elke donderdag nieuwe inzendingen. Na beoordeling en verpakking worden de verpakte apps de volgende vrijdag geleverd. Maximaal vijf apps per week kunnen worden verpakt om te starten, maar de service kan worden geschaald om aan uw behoeften te voldoen.

![kalender met app-instroom op een donderdag (de 21e in dit voorbeeld), mediavalidatie de volgende dag, verpakking op de volgende maandag (de 25e) en app-levering op de daaropvolgende vrijdag (de 29e)](../../media/MCS-cal.png)

U ontvangt een melding zodra de app is geleverd. Op dat moment hebt u 21 dagen om acceptatietests uit te voeren en u af te melden voor het werk in de Microsoft Managed Desktop-portal. Als u tijdens uw acceptatietests een probleem met de app ontdekt, weigert u de app in de Microsoft Managed Desktop-portal en wordt u via e-mail verbonden met een MCS-verpakker om het probleem te begrijpen en op te lossen.

## <a name="testing-accounts-and-environment"></a>Accounts en omgeving testen

Als het verpakkingsteam de migratie naar Microsoft Intune wilt voltooien, raden we u aan bepaalde machtigingen op te geven:
 
-   Toegang tot de app-implementatiemogelijkheden van Microsoft Intune voor de verpakker om de app toe te voegen en toe te wijzen 
-   Testgroepen, gebruikersaccounts en licenties voor de verpakkers om de apps te kunnen testen

MCS gebruikt deze machtigingen om de volgende acties uit te voeren:
 
-   Ervoor zorgen dat de app werkt op virtuele machine die is geconfigureerd voor Microsoft Managed Desktop
-   De app uploaden naar Microsoft Intune voor implementatie naar uw gebruikers

Zonder deze machtigingen is het mogelijk voor MCS om verder te gaan, maar ze kunnen de toepassingen niet uploaden naar uw omgeving.


