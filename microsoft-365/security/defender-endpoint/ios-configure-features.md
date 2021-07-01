---
title: Microsoft Defender voor eindpunt configureren voor iOS-functies
description: Beschrijft hoe u Microsoft Defender voor Eindpunt implementeert voor iOS-functies
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, configure, features, ios
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 749e03cb9d14476245baea82c21d322d4d726aad
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230005"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a>Microsoft Defender voor eindpunt configureren voor iOS-functies

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> Defender voor Eindpunt in iOS zou een VPN gebruiken om de functie Webbeveiliging te bieden. Dit is geen gewone VPN en is een lokale/self-looping VPN die geen verkeer buiten het apparaat neemt.

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a>Voorwaardelijke toegang met Defender voor Eindpunt in iOS  
Microsoft Defender voor Eindpunt op iOS, samen met Microsoft Intune en Azure Active Directory, maakt het afdwingen van apparaat compliance en beleid voor Voorwaardelijke toegang mogelijk op basis van apparaatrisicoscore. Defender for Endpoint is een MTD-oplossing (Mobile Threat Defense) die u kunt implementeren om gebruik te maken van deze mogelijkheid via Intune.

Zie Defender voor Eindpunt en [Intune](/mem/intune/protect/advanced-threat-protection)voor meer informatie over het instellen van Voorwaardelijke toegang met Defender voor Eindpunt in iOS.

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a>Jailbreakdetectie door Microsoft Defender voor Eindpunt
Microsoft Defender voor Eindpunt heeft de mogelijkheid om niet-beheerde en beheerde apparaten te detecteren die in de bajes staan. Als wordt vastgesteld dat een apparaat een jailbroken is, wordt een waarschuwing met hoog risico gerapporteerd aan het Beveiligingscentrum en als Voorwaardelijke toegang is ingesteld op basis van de apparaatrisicoscore, wordt het apparaat geblokkeerd voor toegang tot bedrijfsgegevens.

## <a name="web-protection-and-vpn"></a>Webbeveiliging en VPN

Defender voor Eindpunt in iOS bevat standaard de functie voor webbeveiliging en schakelt deze in. [Webbeveiliging helpt](web-protection-overview.md) om apparaten te beveiligen tegen webbedreigingen en gebruikers te beschermen tegen phishingaanvallen. Defender voor Endpoint in iOS gebruikt een VPN om deze beveiliging te bieden. Let op: dit is een lokale VPN en in tegenstelling tot traditionele VPN wordt netwerkverkeer niet buiten het apparaat verzonden.

Hoewel deze standaard is ingeschakeld, zijn er mogelijk bepaalde gevallen waarvoor u VPN moet uitschakelen. U wilt bijvoorbeeld bepaalde apps uitvoeren die niet werken wanneer een VPN is geconfigureerd. In dergelijke gevallen kunt u ervoor kiezen om VPN uit te schakelen vanuit de app op het apparaat door de onderstaande stappen uit te voeren:

1. Open op uw iOS-apparaat de **Instellingen** app, klik of tik **op Algemeen** en vervolgens **op VPN.**
1. Klik of tik op de knop 'i' voor Microsoft Defender voor Eindpunt.
1. Schakel de optie **Verbinding maken op aanvraag uit om** VPN uit te schakelen.

    > [!div class="mx-imgBorder"]
    > ![VPN config connect on demand](images/ios-vpn-config.png)

> [!NOTE]
> Webbeveiliging is niet beschikbaar wanneer VPN is uitgeschakeld. Als u Webbeveiliging opnieuw wilt inschakelen, opent u de Microsoft Defender voor Eindpunt-app op het apparaat en klikt of tikt u op **Start VPN**.

## <a name="co-existence-of-multiple-vpn-profiles"></a>Co-bestaan van meerdere VPN-profielen

Apple iOS biedt geen ondersteuning voor meerdere VPN's voor het hele apparaat om tegelijk actief te zijn. Hoewel er meerdere VPN-profielen op het apparaat kunnen bestaan, kan er slechts één VPN tegelijk actief zijn.

## <a name="configure-microsoft-defender-for-endpoint-risk-signal-in-app-protection-policy-mam"></a>Microsoft Defender configureren voor eindpuntrisicosignaal in app-beveiligingsbeleid (MAM)

Microsoft Defender voor Eindpunt kan worden geconfigureerd voor het verzenden van bedreigingssignalen die moeten worden gebruikt in app-beveiligingsbeleid (APP, ook wel MAM genoemd) op iOS/iPadOS. Met deze mogelijkheid kunt u Microsoft Defender voor Eindpunt gebruiken om de toegang tot bedrijfsgegevens te beschermen tegen niet-geregistreerde apparaten.

Stappen voor het instellen van app-beveiligingsbeleid met Microsoft Defender voor Eindpunt zijn als hieronder:

1. Stel de verbinding in van uw Microsoft Endpoint Manager tenant met Microsoft Defender voor Eindpunt. Ga in [het Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431)naar **Tenant Administration** Connectors en tokens Microsoft Defender voor Eindpunt (onder Platform kruis) of Endpoint Security Microsoft Defender voor Eindpunt (onder Setup) en schakel de schakelaars in onder  >    >   App Protection   >   Policy Instellingen **voor iOS.**
1. Kies Opslaan. De **verbindingsstatus** is nu ingesteld op **Ingeschakeld.**
1. Beleid voor app-beveiliging maken: Nadat de installatie van de Microsoft Defender voor eindpuntconnector is voltooid, gaat u naar **Apps** App-beveiligingsbeleid (onder Beleid) om een nieuw beleid te maken of een bestaand beleid  >   bij te werken.
1. Selecteer het platform, **apps, gegevensbescherming, Instellingen** voor Toegangsvereisten die uw organisatie voor uw beleid vereist.
1. Onder **Voorwaarden voor voorwaardelijke** start Apparaat vindt u de instelling Max  >   **toegestaan apparaatbedreigingsniveau.** Dit moet zijn geconfigureerd op Laag, Gemiddeld, Hoog of Beveiligd. De acties die voor u beschikbaar zijn, zijn **Toegang blokkeren** of **Gegevens wissen.** Mogelijk ziet u een informatief dialoogvenster om ervoor te zorgen dat uw verbindingslijn is ingesteld voordat deze instelling van kracht wordt. Als de verbindingslijn al is ingesteld, kunt u dit dialoogvenster negeren.
1. Werk af met Opdrachten en sla uw beleid op.

Zie beleidsinstellingen voor [iOS-appbeveiliging](/mem/intune/apps/app-protection-policy-settings-ios)voor meer informatie over mam- of appbeveiligingsbeleid.

### <a name="deploying-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>Microsoft Defender voor Eindpunt implementeren voor MAM of op niet-geregistreerde apparaten

Microsoft Defender voor Eindpunt op iOS maakt het scenario Voor app-beveiliging mogelijk en is beschikbaar in de Apple App Store.

Eindgebruikers moeten de nieuwste versie van de app rechtstreeks vanuit de Apple App Store installeren.

## <a name="configure-compliance-policy-against-jailbroken-devices"></a>Compliancebeleid configureren voor jailbroken apparaten

Om ervoor te zorgen dat bedrijfsgegevens niet worden gebruikt op iOS-apparaten met een jailbroken, raden we u aan het volgende compliancebeleid in te stellen op Intune.

> [!NOTE]
> Jailbreakdetectie is een mogelijkheid die wordt geleverd door Microsoft Defender voor Eindpunt in iOS. U wordt echter aangeraden dit beleid in te stellen als een extra verdedigingslaag tegen scenario's met een jailbreak.

Volg de onderstaande stappen om een compliancebeleid te maken tegen jailbroken apparaten.

1. Ga [Microsoft Endpoint Manager beheercentrum naar](https://go.microsoft.com/fwlink/?linkid=2109431)Beleid voor naleving van **apparaten**  ->    ->  **Beleid maken.** Selecteer 'iOS/iPadOS' als platform en klik op **Maken.**

    > [!div class="mx-imgBorder"]
    > ![Beleid maken](images/ios-jb-policy.png)

2. Geef een naam op van het beleid, bijvoorbeeld 'Compliancebeleid voor jailbreak'.
3. Klik op de pagina nalevingsinstellingen op om de sectie **Apparaattoestand** uit te vouwen en klik **op Blokkeren** voor **jailbroken apparaten.**

    > [!div class="mx-imgBorder"]
    > ![Beleid Instellingen](images/ios-jb-settings.png)

4. Selecteer in **de sectie Actie voor niet-naleving** de acties volgens uw vereisten en selecteer **Volgende.**

    > [!div class="mx-imgBorder"]
    > ![Beleidsacties](images/ios-jb-actions.png)

5. Selecteer in **de sectie** Opdrachten de gebruikersgroepen die u wilt opnemen voor dit beleid en selecteer **vervolgens Volgende**.
6. Controleer in **de sectie Controleren+Maken** of alle ingevoerde gegevens juist zijn en selecteer vervolgens **Maken.**

## <a name="configure-custom-indicators"></a>Aangepaste indicatoren configureren

Met Defender voor Eindpunt in iOS kunnen beheerders ook aangepaste indicatoren configureren op iOS-apparaten. Zie Indicatoren beheren voor meer informatie over het configureren van aangepaste [indicatoren.](/microsoft-365/security/defender-endpoint/manage-indicators)

> [!NOTE]
> Defender voor Eindpunt in iOS ondersteunt het maken van aangepaste indicatoren alleen voor IP-adressen en URL's/domeinen.

## <a name="report-unsafe-site"></a>Onveilige site rapporteren

Phishingwebsites doen zich voor als betrouwbare websites om uw persoonlijke of financiële gegevens te verkrijgen. Ga naar [de pagina Feedback geven over netwerkbeveiliging](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) als u een website wilt rapporteren die een phishingsite kan zijn.

