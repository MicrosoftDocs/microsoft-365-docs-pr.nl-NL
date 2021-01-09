---
title: Microsoft 365-Apps testen en implementeren
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: U kunt Microsoft-en Microsoft-partner-apps voor gebruikers en groepen in uw organisatie zoeken, testen en implementeren via de Integrated apps Portal in het Microsoft 365-Beheercentrum.
ms.openlocfilehash: b0dc6277461ff03e8aae2e820543f8e5d9e2303c
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790188"
---
# <a name="test-and-deploy-microsoft-365-apps-in-the-microsoft-365-admin-center"></a>Microsoft 365-Apps testen en implementeren in het Microsoft 365-Beheercentrum

Met het Microsoft 365-Beheercentrum kunt u Microsoft-en Microsoft-partner-Apps implementeren vanaf één locatie. De mogelijkheid om gekochte en gelicentieerde apps van Microsoft en Microsoft-partners via de Integrated apps portal te zoeken, te testen en te implementeren, biedt het gemak en de voordelen die uw organisatie nodig heeft om de Business Services regelmatig bij te werken en op efficiënte wijze uit te voeren.  

Als u meer informatie wilt over het aanschaffen en licenties van Microsoft 365-apps voor uw organisatie, raadpleegt u het blogbericht met de naam [beheerde en implementeer Microsoft 365-apps in het Microsoft 365-Beheercentrum](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324).
  
## <a name="manage-apps-in-the-integrated-apps-portal"></a>Apps beheren in de Integrated apps Portal

Door geïntegreerde apps te kiezen in het Microsoft 365-Beheercentrum, kunt u het testen en de implementatie van aangeschafte en gelicentieerde Microsoft-partner-apps beheren. 

1. Kies in het Beheercentrum in de navigatiebalk aan de linkerkant **instellingen** en kies vervolgens **geïntegreerde apps**. 

2. Kies een app met de **status** van **meer beschikbare apps**.

3. Selecteer **implementeren** boven aan de pagina naast het bericht waarin wordt gevraagd om te worden geïmplementeerd.

    Voor sommige apps moet u gebruikers toevoegen voordat u **implementeren** kunt selecteren.

    a. Selecteer **gebruikers toevoegen**, kies **volledige implementatie** en kies vervolgens **hele organisatie** of **specifieke gebruikers/groepen**.

    Specifieke gebruikers/groepen kunnen een Microsoft 365-groep, een beveiligingsgroep of een gedistribueerde groep zijn.

    U kunt ook **implementatie testen** kiezen als u liever de app implementeert voor de volledige organisatie.

    b. Selecteer **bijwerken**, **gereed** en nu de optie **toepassen** op het tabblad **overzicht** .  

4. Controleer de app-gegevens en selecteer vervolgens **implementeren**. 

5. Selecteer **gereed** op de pagina **implementatie voltooid** . 

    Controleer de details van de test of volledige implementatie op het tabblad **overzicht** .

## <a name="find-published-apps-for-testing-and-full-deployment"></a>Gepubliceerde apps zoeken voor testen en volledige implementatie 

U kunt gepubliceerde apps die nog niet zijn opgenomen in de lijst op de pagina geïntegreerde apps zoeken, testen en volledig implementeren. Door de apps te kopen en via licentie te verlenen aan het Beheercentrum, kunt u Microsoft-en Microsoft-partner-apps aan uw lijst toevoegen vanaf één locatie.

1. Kies in het Beheercentrum in de navigatiebalk aan de linkerkant **instellingen** en kies vervolgens **geïntegreerde apps**. 

2. Selecteer **apps downloaden** boven de lijst met apps.

3. Selecteer de app die u wilt implementeren op de pagina **Microsoft 365 apps** gepubliceerd apps en kies **nu downloaden**.

4. Accepteer de machtigingen en selecteer vervolgens **Doorgaan**.

5. Selecteer **implementeren** boven aan de pagina naast het bericht waarin wordt gevraagd om te worden geïmplementeerd.

    Voor sommige apps moet u gebruikers toevoegen voordat u **implementeren** kunt selecteren.

    a. Selecteer **gebruikers toevoegen**, kies **volledige implementatie** en kies vervolgens **hele organisatie** of **specifieke gebruikers/groepen**.

    Specifieke gebruikers/groepen kunnen een Microsoft 365-groep, een beveiligingsgroep of een gedistribueerde groep zijn.

    U kunt ook **implementatie testen** kiezen als u liever de app implementeert voor de volledige organisatie.

    b. Selecteer **bijwerken**, **gereed**, en nu de optie **implementeren** op het tabblad **overzicht** .  

6. Controleer de app-gegevens en selecteer vervolgens **implementeren**. 

7. Selecteer **gereed** op de pagina **implementatie voltooid** . 

    Controleer de details van de test of volledige implementatie op het tabblad **overzicht** .

In het Microsoft 365-Beheercentrum is de **status** van de geïmplementeerde apps **OK** met een **implementatie type** **test implementatie**, **volledige implementatie** of **aangepast**, en de datum waarop u de app hebt geïmplementeerd.

> [!NOTE]
> Als een app eerder is geïmplementeerd dan de portal van Integrated apps, is het **implementatie type** **aangepast.**

## <a name="unsupported-scenarios"></a>Niet-ondersteunde scenario's

De volgende scenario's worden momenteel niet ondersteund voor implementaties van de Integrated apps portal:

- De app of invoegtoepassing is gekoppeld aan meer dan één software als een service (SaaS)-aanbieding.
- De SaaS-app is gekoppeld aan apps en invoegtoepassingen, maar er is geen gekoppelde AADid.
- Twee SaaS-apps delen dezelfde AADid en ze zijn gekoppeld aan apps of invoegtoepassingen.
  