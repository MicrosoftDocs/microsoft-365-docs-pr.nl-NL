---
title: Een meldingsregel voor onboarding of offboarding maken
description: Ontvang een melding wanneer een lokaal onboarding- of offboarding-script wordt gebruikt.
keywords: onboarding, offboarding, lokaal, script, melding, regel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5dfdfc6d14add33154ed4c2370bca458e752125d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187118"
---
# <a name="create-a-notification-rule-when-a-local-onboarding-or-offboarding-script-is-used"></a>Een meldingsregel maken wanneer een lokaal onboarding- of offboarding-script wordt gebruikt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Maak een meldingsregel zodat wanneer een lokaal onboarding- of offboarding-script wordt gebruikt, u hiervan op de hoogte wordt gesteld. 

## <a name="before-you-begin"></a>Voordat u begint
U moet toegang hebben tot:
 - Microsoft Flow (minimaal Flow Plan 1). Zie de pagina [Stroomprijzen voor meer informatie.](https://flow.microsoft.com/pricing/)
 - Azure Table or SharePoint List or Library / SQL DB

## <a name="create-the-notification-flow"></a>De meldingsstroom maken

1. In [flow.microsoft.com](https://flow.microsoft.com/).

2. Ga naar **Mijn stromen > Nieuwe > Gepland - van leeg**. 

    ![Afbeelding van stroom](images/new-flow.png)


3. Een geplande stroom maken.
   1. Voer een stroomnaam in.
   2. Geef het begin en de tijd op.
   3. Geef de frequentie op. Bijvoorbeeld om de 5 minuten.

    ![Afbeelding van de meldingsstroom](images/build-flow.png)

4. Selecteer de knop + om een nieuwe actie toe te voegen. De nieuwe actie is een HTTP-aanvraag voor de Defender for Endpoint security center device(s) API(s). U kunt deze ook vervangen door de out-of-the-box 'WDATP Connector' (actie: 'Machines - Lijst met machines krijgen'). 

    ![Afbeelding van terugkeerpatroon en actie toevoegen](images/recurrence-add.png)


5. Voer de volgende HTTP-velden in:

   - Methode: 'GET' als een waarde om de lijst met apparaten te krijgen.
   - URI: Enter `https://api.securitycenter.microsoft.com/api/machines` .
   - Verificatie: Selecteer 'Active Directory OAuth'.
   - Tenant: Meld u aan bij https://portal.azure.com en navigeer naar **Azure Active Directory > app-registraties** en ontvang de tenant-id-waarde.
   - Doelgroep: `https://securitycenter.onmicrosoft.com/windowsatpservice\`
   - Client-id: Meld u aan bij https://portal.azure.com en navigeer naar Azure Active Directory > **App-registraties** en ontvang de waarde client-id.
   - Referentietype: Selecteer 'Geheim'.
   - Geheim: Meld u aan bij https://portal.azure.com en navigeer naar Azure Active Directory > **app-registraties** en ontvang de tenant-id-waarde.

    ![Afbeelding van de HTTP-voorwaarden](images/http-conditions.png)


6. Voeg een nieuwe stap toe door **Nieuwe actie toevoegen te selecteren** en vervolgens gegevensbewerkingen te **zoeken** en **Parse JSON te selecteren.**

    ![Afbeelding van gegevensbewerkingen](images/data-operations.png)

7. Voeg Body toe in het **veld** Inhoud.

    ![Afbeelding van parse JSON](images/parse-json.png)

8. Selecteer de **voorbeeldlading gebruiken om een schemakoppeling te** genereren.

    ![Afbeelding van parse json met payload](images/parse-json-schema.png)

9. Kopieer en plak het volgende JSON-fragment:

    ```
    {
        "type": "object",
        "properties": {
            "@@odata.context": {
                "type": "string"
            },
            "value": {
                "type": "array",
                "items": {
                    "type": "object",
                    "properties": {
                        "id": {
                            "type": "string"
                        },
                        "computerDnsName": {
                            "type": "string"
                        },
                        "firstSeen": {
                            "type": "string"
                        },
                        "lastSeen": {
                            "type": "string"
                        },
                        "osPlatform": {
                            "type": "string"
                        },
                        "osVersion": {},
                        "lastIpAddress": {
                            "type": "string"
                        },
                        "lastExternalIpAddress": {
                            "type": "string"
                        },
                        "agentVersion": {
                            "type": "string"
                        },
                        "osBuild": {
                            "type": "integer"
                        },
                        "healthStatus": {
                            "type": "string"
                        },
                        "riskScore": {
                            "type": "string"
                        },
                        "exposureScore": {
                            "type": "string"
                        },
                        "aadDeviceId": {},
                        "machineTags": {
                            "type": "array"
                        }
                    },
                    "required": [
                        "id",
                        "computerDnsName",
                        "firstSeen",
                        "lastSeen",
                        "osPlatform",
                        "osVersion",
                        "lastIpAddress",
                        "lastExternalIpAddress",
                        "agentVersion",
                        "osBuild",
                        "healthStatus",
                        "rbacGroupId",
                        "rbacGroupName",
                        "riskScore",
                        "exposureScore",
                        "aadDeviceId",
                        "machineTags"
                    ]
                }
            }
        }
    }

    ```

10.  Haal de waarden op uit de JSON-oproep en controleer of het onboarded-apparaat(en) al is/zijn geregistreerd in de SharePoint-lijst als voorbeeld:
- Zo ja, dan wordt er geen melding geactiveerd
- Als dit niet het probleem is, worden de nieuwe onboarded device(s) geregistreerd in de SharePoint-lijst en wordt er een melding verzonden naar de Defender for Endpoint-beheerder

    ![Afbeelding van toepassen op elk](images/flow-apply.png)

    ![Afbeelding van toepassen op elk met items](images/apply-to-each.png)

11. Voeg **onder** Voorwaarde de volgende expressie toe: 'lengte(body('Get_items')?[' waarde'])' en stelt u de voorwaarde in op gelijk aan 0.

    ![Afbeelding van toepassen op elke voorwaarde](images/apply-to-each-value.png)  
    ![Afbeelding van voorwaarde1 ](images/conditions-2.png) 
     ![ Afbeelding van voorwaarde2](images/condition3.png)  
    ![Afbeelding van e-mail verzenden](images/send-email.png)

## <a name="alert-notification"></a>Waarschuwingsmelding
De volgende afbeelding is een voorbeeld van een e-mailmelding.

![Afbeelding van e-mailmelding](images/alert-notification.png)


## <a name="tips"></a>Tips

- U kunt hier filteren met alleen lastSeen:
    - Elke 60 minuten:
      - Neem alle apparaten die de afgelopen 7 dagen voor het laatst zijn gezien. 

- Voor elk apparaat: 
    - Als de laatst gezien eigenschap zich op het interval van één uur van [-7 dagen, -7 dagen + 60 minuten ] -> Waarschuwing voor offboarding mogelijkheid.
    - Als de eerste keer wordt gezien op het afgelopen uur -> Waarschuwing voor onboarding.

In deze oplossing hebt u geen dubbele waarschuwingen: Er zijn tenants die meerdere apparaten hebben. Het verkrijgen van al deze apparaten kan erg duur zijn en kan paging vereisen.

U kunt de query splitsen in twee query's: 
1.  Voor offboarding neemt u alleen dit interval met behulp van de OData-$filter en meldt u alleen of aan de voorwaarden wordt voldaan.
2.  Neem alle apparaten die het laatst zijn gezien in het afgelopen uur en controleer de eigenschap die het eerst is gezien (als de eerste gezien eigenschap zich op het afgelopen uur heeft voor het laatst gezien, moet de laatst geziene eigenschap er ook zijn). 

