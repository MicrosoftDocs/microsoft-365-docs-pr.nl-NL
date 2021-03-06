---
title: Problemen met Microsoft Defender voor Eindpunt op Android oplossen
description: Problemen oplossen voor Microsoft Defender voor Eindpunt op Android
keywords: microsoft, defender, Microsoft Defender voor Eindpunt, mde, android, cloud, connectiviteit, communicatie
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
ms.openlocfilehash: 18afd4aa160ec345839d23719d1b3fcce21654ec
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246354"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a>Problemen met Microsoft Defender voor Eindpunt op Android oplossen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Wanneer u een apparaat onboardt, ziet u mogelijk aanmeldingsproblemen nadat de app is geïnstalleerd.

Tijdens onboarding kunt u problemen ondervinden bij het aanmelden nadat de app op uw apparaat is geïnstalleerd.

In dit artikel vindt u oplossingen voor het oplossen van aanmeldingsproblemen.  

## <a name="sign-in-failed---unexpected-error"></a>Aanmelden mislukt - onverwachte fout
**Aanmelden is mislukt: Onverwachte** *fout, probeer het later*

![Afbeelding van fout bij aanmelden mislukt Onverwachte fout](images/f9c3bad127d636c1f150d79814f35d4c.png)

**Bericht:**

Onverwachte fout, probeer het later

**Oorzaak:**

Er is een oudere versie van de app 'Microsoft Authenticator' op uw apparaat geïnstalleerd.

**Oplossing:**

Nieuwste versie en [versie](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) van Microsoft Authenticator in de Google Play Store installeren en het opnieuw proberen

## <a name="sign-in-failed---invalid-license"></a>Aanmelden mislukt - ongeldige licentie

**Aanmelden mislukt:** *Ongeldige licentie, neem contact op met beheerder*

![Afbeelding van aanmelden mislukt neem contact op met beheerder](images/920e433f440fa1d3d298e6a2a43d4811.png)

**Bericht:** *Ongeldige licentie, neem contact op met de beheerder*

**Oorzaak:**

U hebt geen Microsoft 365 toegewezen of uw organisatie heeft geen licentie voor Microsoft 365 Enterprise abonnement.

**Oplossing:**

Neem contact op met uw beheerder voor hulp.

## <a name="report-unsafe-site"></a>Onveilige site rapporteren

Phishingwebsites doen zich voor als betrouwbare websites om uw persoonlijke of financiële gegevens te verkrijgen. Ga naar [de pagina Feedback geven over netwerkbeveiliging](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) als u een website wilt rapporteren die een phishingsite kan zijn.

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a>Phishingpagina's worden niet geblokkeerd op sommige OEM-apparaten

**Van toepassing op:** Alleen specifieke OEM's

-   **Xiaomi**

Phishing en schadelijke webbedreigingen die worden gedetecteerd door Defender voor Eindpunt voor Android, worden niet geblokkeerd op sommige Xiaomi-apparaten. De volgende functionaliteit werkt niet op deze apparaten.

![Afbeelding van site die onveilig is gerapporteerd](images/0c04975c74746a5cdb085e1d9386e713.png)


**Oorzaak:**

Xiaomi-apparaten bevatten een nieuw machtigingsmodel. Hierdoor wordt voorkomen dat in Defender voor Eindpunt voor Android pop-upvensters worden weergegeven terwijl deze op de achtergrond wordt uitgevoerd.

Machtiging voor Xiaomi-apparaten: 'Pop-upvensters weergeven terwijl u op de achtergrond werkt'.

![Afbeelding van pop-upinstelling](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

**Oplossing:**

Schakel de vereiste machtiging in op Xiaomi-apparaten.

- Pop-upvensters weergeven terwijl deze op de achtergrond worden uitgevoerd.
