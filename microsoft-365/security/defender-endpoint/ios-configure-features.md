---
title: Microsoft Defender voor eindpunt configureren voor iOS-functies
description: Beschrijft hoe u MICROSOFT Defender ATP voor iOS-functies implementeert
keywords: microsoft, defender, atp, ios, configureren, functies, ios
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
ms.openlocfilehash: 0e351f6500d5076e724653d0fde1940592dd1ae5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687483"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a>Microsoft Defender voor eindpunt configureren voor iOS-functies

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> Defender voor Eindpunt voor iOS zou een VPN gebruiken om de functie Webbeveiliging te bieden. Dit is geen gewone VPN en is een lokale/self-looping VPN die geen verkeer buiten het apparaat neemt.

## <a name="conditional-access-with-defender-for-endpoint-for-ios"></a>Voorwaardelijke toegang met Defender voor eindpunt voor iOS  
Microsoft Defender voor Eindpunt op iOS, samen met Microsoft Intune en Azure Active Directory, maakt het afdwingen van apparaat compliance en beleid voor voorwaardelijke toegang mogelijk op basis van apparaatrisiconiveaus. Defender for Endpoint is een MTD-oplossing (Mobile Threat Defense) die u kunt implementeren om gebruik te maken van deze mogelijkheid via Intune.

Zie Defender voor Eindpunt en [Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)voor meer informatie over het instellen van Voorwaardelijke toegang met Defender voor eindpunt voor iOS.

## <a name="web-protection-and-vpn"></a>Webbeveiliging en VPN

Defender voor Eindpunt voor iOS bevat standaard de functie voor webbeveiliging en schakelt deze in. [Webbeveiliging helpt](web-protection-overview.md) om apparaten te beveiligen tegen webbedreigingen en gebruikers te beschermen tegen phishingaanvallen. Defender voor Endpoint voor iOS gebruikt een VPN om deze beveiliging te bieden. Let op: dit is een lokale VPN en in tegenstelling tot traditionele VPN wordt netwerkverkeer niet buiten het apparaat verzonden.

Hoewel deze standaard is ingeschakeld, zijn er mogelijk bepaalde gevallen waarvoor u VPN moet uitschakelen. U wilt bijvoorbeeld bepaalde apps uitvoeren die niet werken wanneer een VPN is geconfigureerd. In dergelijke gevallen kunt u ervoor kiezen om VPN uit te schakelen vanuit de app op het apparaat door de onderstaande stappen uit te voeren:

1. Open de app Instellingen  op uw iOS-apparaat, klik of tik **op Algemeen** en vervolgens **op VPN.**
1. Klik of tik op de knop 'i' voor Microsoft Defender ATP.
1. Schakel Verbinding maken **op aanvraag uit om** VPN uit te schakelen.

    > [!div class="mx-imgBorder"]
    > ![VPN config connect on demand](images/ios-vpn-config.png)

> [!NOTE]
> Webbeveiliging is niet beschikbaar wanneer VPN is uitgeschakeld. Als u Webbeveiliging opnieuw wilt inschakelen, opent u de Microsoft Defender voor Eindpunt-app op het apparaat en klikt of tikt u op **Start VPN**.

## <a name="co-existence-of-multiple-vpn-profiles"></a>Co-bestaan van meerdere VPN-profielen

Apple iOS biedt geen ondersteuning voor meerdere VPN's voor het hele apparaat om tegelijk actief te zijn. Hoewel er meerdere VPN-profielen op het apparaat kunnen bestaan, kan er slechts één VPN tegelijk actief zijn.


## <a name="configure-compliance-policy-against-jailbroken-devices"></a>Compliancebeleid configureren voor jailbroken apparaten

Om ervoor te zorgen dat bedrijfsgegevens niet worden gebruikt op iOS-apparaten met een jailbroken, raden we u aan het volgende compliancebeleid in te stellen op Intune.

> [!NOTE]
> Op dit moment biedt Microsoft Defender voor Eindpunt in iOS geen bescherming tegen scenario's met een jailbreak. Als het apparaat wordt gebruikt op een jailbroken apparaat, kunnen in specifieke scenario's gegevens die door de toepassing worden gebruikt, zoals uw bedrijfs-e-mail-id en bedrijfsprofielafbeelding (indien beschikbaar), lokaal worden getoond.

Volg de onderstaande stappen om een compliancebeleid te maken tegen jailbroken apparaten.

1. Ga [in het Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431)naar Beleid voor naleving van   ->  **apparaten**  ->  **Beleid maken.** Selecteer 'iOS/iPadOS' als platform en klik op **Maken.**

    > [!div class="mx-imgBorder"]
    > ![Beleid maken](images/ios-jb-policy.png)

2. Geef een naam op van het beleid, bijvoorbeeld 'Compliancebeleid voor jailbreak'.
3. Klik op de pagina nalevingsinstellingen op om de sectie **Apparaattoestand** uit te vouwen en klik **op Blokkeren** voor **jailbroken apparaten.**

    > [!div class="mx-imgBorder"]
    > ![Beleidsinstellingen](images/ios-jb-settings.png)

4. Selecteer in *de sectie Actie voor niet-naleving* de acties volgens uw vereisten en selecteer **Volgende.**

    > [!div class="mx-imgBorder"]
    > ![Beleidsacties](images/ios-jb-actions.png)

5. Selecteer in *de sectie* Opdrachten de gebruikersgroepen die u wilt opnemen voor dit beleid en selecteer **vervolgens Volgende**.
6. Controleer in **de sectie Controleren+Maken** of alle ingevoerde gegevens juist zijn en selecteer vervolgens **Maken.**

## <a name="configure-custom-indicators"></a>Aangepaste indicatoren configureren

Met Defender voor Eindpunt voor iOS kunnen beheerders ook aangepaste indicatoren configureren op iOS-apparaten. Zie Indicatoren beheren voor meer informatie over het configureren van aangepaste [indicatoren.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)

> [!NOTE]
> Defender voor Eindpunt voor iOS ondersteunt het maken van aangepaste indicatoren alleen voor IP-adressen en URL's/domeinen.

## <a name="report-unsafe-site"></a>Onveilige site rapporteren

Phishingwebsites doen zich voor als betrouwbare websites om uw persoonlijke of financiële gegevens te verkrijgen. Ga naar [de pagina Feedback geven over netwerkbeveiliging](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) als u een website wilt rapporteren die een phishingsite kan zijn.

## <a name="battery-consumption-issues-on-ios-when-microsoft-defender-for-endpoint-is-installed"></a>Problemen met batterijverbruik in iOS wanneer Microsoft Defender voor Eindpunt is geïnstalleerd

Het batterijgebruik door een app wordt door Apple berekend op basis van een groot aantal factoren, waaronder cpu- en netwerkgebruik. Microsoft Defender voor Eindpunt gebruikt een lokale/lus-back VPN op de achtergrond om het webverkeer te controleren op schadelijke websites of verbindingen. Netwerkpakketten van een app worden door deze controle heen en daardoor wordt het batterijgebruik van Microsoft Defender voor Eindpunt onjuist berekend. Dit geeft een onjuiste indruk voor de gebruiker. Het werkelijke batterijverbruik van Microsoft Defender voor Eindpunt is lager dan wat wordt weergegeven op de pagina Batterijinstellingen op het apparaat. Dit is gebaseerd op tests die zijn uitgevoerd in de Microsoft Defender voor Eindpunt-app om het batterijverbruik te begrijpen.

Ook de GEBRUIKTE VPN is een lokale VPN en in tegenstelling tot traditionele VPN's wordt netwerkverkeer niet buiten het apparaat verzonden.
