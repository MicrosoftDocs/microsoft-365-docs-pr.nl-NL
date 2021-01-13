---
title: Werken met Microsoft Consulting Services
description: voorbereiding en stappen die u moet volgen om te werken met MCS om uw apps te pakken
keywords: Microsoft Managed Desktop, Microsoft 365, service, Documentatie, apps, MCS, verpakking
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f8c4e427c536577ea2fc768d4930b9d4db6ac697
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841421"
---
# <a name="working-with-microsoft-consulting-services"></a>Werken met Microsoft Consulting Services

U kunt deelnemen aan Microsoft Consulting Services (MCS) om uw apps te laten inpakken voor gebruik met Microsoft Managed Desktop. Neem voor exacte informatie contact op met uw accountvertegenwoordiger om contact op te nemen met MCS en uw specifieke app-verpakkings project te bereiken.

## <a name="roles-and-responsibilities"></a>Rollen en verantwoordelijkheden

Als u wilt werken met een pakket met de MCS-app, **moet u deze elementen geven**:

- De bronprogramma bestanden (bijvoorbeeld setup.exe of. msi).
- De installatie-instructies, waarop u informatie kunt opgeven over de manier waarop de definitieve installatie moet opletten. Moet u bijvoorbeeld een snelkoppeling op het bureaublad van de app vinden? Wat moet de zichtbaarheid van de app? Moet de app verbinding maken met een server en zo ja, welke? Voor meer informatie raadpleegt u de [aanvraag sjabloon toepassings verpakking](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).
- U moet uw eigen Acceptatietest uitvoeren om te controleren of de app werkt zoals u deze nodig hebt in uw omgeving.

**MCS voert de volgende handelingen uit:**

- Controleren of de app is verboden of niet wordt toegestaan in de Microsoft beheerde bureaubladomgeving.
- Tests voor installatie, opstarten en verwijdering van de app voor compatibiliteit met Windows 10. Als met MCS een compatibiliteitsprobleem wordt gedetecteerd, wordt de app in de app voor de [bureaublad-app](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) voor herstel uitgeschakeld.
- Verpakt de app met uw specificatie en test app-implementatie met Microsoft intune.

## <a name="app-delivery-schedule"></a>Leveringsschema voor apps

Start het pakket met de app-gegevens naar de Microsoft beheerde bureaublad Portal. Het verpakkings team beoordeelt telkens elke donderdag nieuwe inzendingen. Na onderzoek en verpakking worden de ingepakte apps na vrijdag afgeleverd. Er kunnen maximaal vijf apps per week worden ingepakt en u kunt aan de slag met de service, zodat de service aan uw wensen voldoet.

![agenda met de app-instroom in een donderdag (de 21 in dit voorbeeld), media validatie de volgende dag, verpakking op de volgende maandag (de 25e) en de bezorging van de app op de volgende vrijdag (de 29)](../../media/MCS-cal.png)

U ontvangt een melding wanneer de app is geleverd. Op dit moment hebt u 21 dagen voor het uitvoeren van acceptatie testen en het goedkeuren van het werk in de Microsoft beheerde bureaublad Portal. Als u een probleem met de app ontdekt tijdens het testen van uw acceptatie, moet u de app in de Microsoft Managed Desktop Portal afwijzen en wordt u via e-mail verbonden met een MCS-pakket om het probleem te begrijpen en op te lossen.

## <a name="testing-accounts-and-environment"></a>Accounts en omgevingen testen

Als u wilt dat het team de migratie naar Microsoft intune uitvoert, is het raadzaam bepaalde machtigingen te verlenen:
 
-   Toegang tot implementatie functies voor app Microsoft intune voor de pakket functie voor het toevoegen en toewijzen van de app 
-   Testgroepen, gebruikersaccounts en licenties voor de packages om de apps te kunnen testen

MCS maakt gebruik van deze machtigingen om de volgende acties uit te voeren:
 
-   Ervoor zorgen dat de app werkt op de virtuele machine die is geconfigureerd voor Microsoft Managed Desktop
-   De app uploaden naar Microsoft intune for Deployment voor uw gebruikers

Zonder deze machtigingen is het mogelijk dat de MCS doorschakelt, maar de toepassingen kan niet worden geüpload naar uw omgeving.


