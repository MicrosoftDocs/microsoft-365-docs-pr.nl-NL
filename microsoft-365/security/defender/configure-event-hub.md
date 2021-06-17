---
title: Uw gebeurtenishub configureren
description: Meer informatie over het configureren van uw Event Hub
keywords: event hub, configureren, inzichten
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.openlocfilehash: d28ad22721e22dfd0dc5962bd46bab2b45469781
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985585"
---
# <a name="configure-your-event-hub"></a>Uw gebeurtenishub configureren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Meer informatie over het configureren van uw Event Hub, zodat deze gebeurtenissen kan opnemen vanuit Microsoft 365 Defender.


## <a name="setup-the-required-resource-provider-in-the-event-hub-subscription"></a>De vereiste resourceprovider instellen in het Event Hub-abonnement


1. Meld u aan bij [Azure Portal](https://portal.azure.com).
1. Selecteer **Abonnementen { Selecteer het abonnement dat de \> ***gebeurtenishub zal worden geïmplementeerd bij***} \> Resourceproviders.**
1. Controleer of de **Microsoft.Insights-provider** is geregistreerd. Als u dit niet doet, registreert u het.

![Afbeelding van resourceproviders in Microsoft Azure](../../media/f893db7a7b1f7aa520e8b9257cc72562.png)

## <a name="setup-azure-active-directory-app-registration"></a>Installatie Azure Active Directory app-registratie


>! [OPMERKING] U moet de rol beheerder of Azure Active Directory (AAD) moeten zijn ingesteld zodat niet-beheerders apps kunnen registreren. U moet ook een rol eigenaar of beheerder van Gebruikerstoegang hebben om de serviceprincipaal een rol toe te wijzen.  
>Zie Een [Azure AD-app maken & service principal in de portal - Microsoft identity platform Microsoft Docs voor \| meer informatie.](/azure/active-directory/develop/howto-create-service-principal-portal)

1. Maak een nieuwe registratie (waarmee inherent een serviceprincipaal wordt gemaakt) in Azure Active Directory **\> App-registraties \> Nieuwe registratie.**

1. Vul het formulier in met alleen de naam (omleidings-URI is niet vereist).

    ![Afbeelding van een toepassing registreren](../../media/336bc84e6be23900c43232b4ef0c253c.png)

    ![Afbeelding van overzichtsgegevens](../../media/06ac04c4ff713c2065cec2ef2f99a294.png)

1. Maak een geheim door te klikken op **Certificaten & nieuwe \> clientgeheim:**

    ![Afbeelding van certificaten en geheimen](../../media/d2ef88d3d2310d2c60c294b569cdf02e.png)

>[!WARNING]
>**U hebt geen toegang meer tot het clientgeheim,** dus sla het op.

## <a name="setup-event-hub-namespace"></a>Setup Event Hub namespace


1. Een naamruimte voor gebeurtenishubs maken:

    Ga **naar Event Hubs \> Add** and select the pricing tier, throughput units and Auto-Inflate (requires standard pricing and under features) appropriate for the load you are expecting.  
    Zie Prijzen [- Event Hubs \| ](https://azure.microsoft.com/en-us/pricing/details/event-hubs/) Microsoft Azure

    >[!NOTE]
    > U kunt een bestaande gebeurtenishub gebruiken, maar de doorvoer en schaal worden ingesteld op naamruimteniveau, dus het is raadzaam om een gebeurtenishub in de eigen naamruimte te plaatsen.

   ![Afbeelding van de naamruimte van gebeurtenishub](../../media/ebc4ca37c342ad1da75c4aee4018e51a.png)

1. U hebt ook de resource-id van deze naamruimte voor gebeurtenishubs nodig. Ga naar de naamruimte-eigenschappen van de naamruimte van Azure Event \> Hubs. Kopieer de tekst onder Resource-id en neem deze op voor gebruik tijdens de sectie Configuratie M365 hieronder. 

    ![Afbeelding van eigenschappen](../../media/759498162a4e93cbf17c4130d704d164.png)

1. Nadat de naamruimte van de gebeurtenishub is gemaakt, moet u de App Registration Service Principal toevoegen als lezer, Azure Event Hubs Data Receiver en de gebruiker die zich als inzender bij Microsoft 365 Defender zal aanmelden (dit kan ook op resourcegroep- of abonnementsniveau).

    Dit gebeurt in **Event Hubs Namespace \> Access Control (IAM) \> Add** and verify under **Role assignments**:

    ![Afbeelding van toegangsbeheer](../../media/9c9c29137b90d5858920202d87680d16.png)

## <a name="setup-event-hub"></a>Setup Event Hub


**Optie 1:**

U kunt een gebeurtenishub maken in uw Naamruimte **en** alle gebeurtenistypen (tabellen) die u selecteert om te exporteren, worden in deze **ene** gebeurtenishub geschreven.

**Optie 2:**

In plaats van alle gebeurtenistypen (tabellen) te exporteren naar één gebeurtenishub, kunt u elke tabel exporteren naar een andere gebeurtenishub in de naamruimte van de gebeurtenishub (één gebeurtenishub per gebeurtenistype).  

In deze optie maakt Microsoft 365 Defender gebeurtenishubs voor u.  
>[!NOTE]
> Als u een naamruimte voor  gebeurtenishubs gebruikt die geen deel uitmaakt van een gebeurtenishubcluster, kunt u alleen maximaal 10 gebeurtenistypen (tabellen) kiezen om te exporteren in elke Export-Instellingen die u definieert, vanwege een Azure-beperking van 10 gebeurtenishubs per naamruimte voor gebeurtenishubs.

Bijvoorbeeld:

![Afbeelding van voorbeeldgebeurtenishub](../../media/005c1f6c10c34420d387f594987f9ffe.png)

Als u deze optie kiest, kunt u naar de sectie Configureren [Microsoft 365 Defender om e-mailtabellen te](#configure-microsoft-365-defender-to-send-email-tables) verzenden.

Maak een Event Hub in uw Naamruimte door **Event Hubs \> + Event Hub te selecteren.**

Het aantal partities zorgt voor extra doorvoer via parallelisme, dus het is raadzaam om dit aantal te verhogen op basis van de belasting die u verwacht.  
Standaardwaarden voor het bewaren en vastleggen van berichten van 1 en Uit worden aanbevolen.

![Afbeelding van gebeurtenishub maken](../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png)

Voor deze gebeurtenishub (geen naamruimte) moet u een beleid voor gedeelde toegang configureren met Verzenden, Claims beluisteren. Klik op het beleid voor gedeelde toegang van de gebeurtenishub **\> + \> Toevoegen** en geef het vervolgens een beleidsnaam (niet elders gebruikt) en controleer **Verzenden** en **luisteren.**

![Afbeelding van beleid voor gedeelde toegang](../../media/1867d13f46dc6a0f4cdae6cf00df24db.png)

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a>E-Microsoft 365 Defender voor het verzenden van e-mailtabellen configureren


### <a name="setup-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a>Installatie Microsoft 365 Defender e-mailtabellen verzenden naar Splunk via Event Hub


1. Meld u aan Microsoft 365 Defender <https://security.microsoft.com> bij met een account dat voldoet aan alle volgende rolvereisten:

    - Inzenderrol op het resourceniveau *Van gebeurtenishub-naamruimte* of hoger voor de gebeurtenishub waar u naar wilt exporteren. Zonder deze optie krijgt u een exportfout wanneer u de instellingen probeert op te slaan.

    - Global Admin or Security Admin Role on the tenant tied to Microsoft 365 Defender and Azure.

    ![Afbeelding van beveiligingsportal](../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png)

1. Klik op **Raw Data Export \> +Add**.

    U gebruikt nu de gegevens die u hierboven hebt opgenomen.

    **Naam:** Dit is lokaal en moet alles zijn wat in uw omgeving werkt.

    **Gebeurtenissen doorsturen naar gebeurtenishub:** Schakel dit selectievakje in.

    **Event-Hub Resource-id:** dit is de naamruimteresource-id voor gebeurtenishub die u hierboven hebt opgenomen bij het instellen van de gebeurtenishub.

    **Naam van gebeurtenis-hub:** Als u een gebeurtenishub hebt gemaakt in de naamruimte van de gebeurtenishub, plakt u de naam Event Hub die u hierboven hebt opgenomen.

    Als u ervoor kiest om Microsoft 365 Defender gebeurtenishubs per gebeurtenistypen (tabellen) voor u te laten maken, laat u dit veld leeg.

    **Gebeurtenistypen:** Selecteer de geavanceerde zoektabellen die u wilt doorsturen naar de gebeurtenishub en ga vervolgens verder met uw aangepaste app. Waarschuwingstabellen zijn afkomstig Microsoft 365 Defender, Apparatentabellen zijn afkomstig van Microsoft Defender voor Eindpunt (EDR) en E-mailtabellen zijn afkomstig van Microsoft Defender voor Office 365. E-mailgebeurtenissen registreert alle e-mailtransacties. De URL (SafeLinks), Bijlage (Safe Bijlagen) en Post Delivery Events (ZAP) worden ook opgenomen en kunnen worden gekoppeld aan het veld E-mailgebeurtenissen in het veld NetworkMessageId.

    ![Afbeelding van streaming API-instellingen](../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png)

1. Klik op **Verzenden.**

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a>Controleren of de gebeurtenissen worden geëxporteerd naar de gebeurtenishub


U kunt controleren of gebeurtenissen naar de gebeurtenishub worden verzonden door een basisquery geavanceerd zoeken uit te voeren. Selecteer **Geavanceerde \> \> huntingquery en** voer de volgende query in:

```
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

Op deze manier ziet u hoeveel e-mailberichten er in het laatste uur zijn ontvangen en hoeveel e-mailberichten in alle andere tabellen zijn samengevoegd. U ziet ook of u gebeurtenissen ziet die naar de gebeurtenishub kunnen worden geëxporteerd. Als dit aantal 0 laat zien, ziet u geen gegevens die naar de gebeurtenishub gaan.

![Afbeelding van geavanceerde jacht](../../media/c305e57dc6f72fa9eb035943f244738e.png)

Nadat u hebt geverifieerd dat er gegevens moeten worden geëxporteerd, kunt u de gebeurtenishub bekijken om te controleren of berichten binnenkomen. Dit kan maximaal één uur duren. 
 
1. Ga in Azure naar **Event Hubs \> Klik op de Namespace Event \> Hubs Klik op de Event \> Hub.**  
1. Schuif **onder** Overzicht omlaag en in de grafiek Berichten ziet u Inkomende berichten. Als u geen resultaten ziet, worden er geen berichten voor de aangepaste app opgenomen.

    ![Afbeelding van het overzichtstabblad met berichten](../../media/e88060e315d76e74269a3fc866df047f.png)
