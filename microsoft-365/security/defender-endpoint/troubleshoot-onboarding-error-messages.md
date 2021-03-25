---
title: Problemen met onboarding en foutberichten oplossen
description: Problemen met onboarding en foutmelding oplossen tijdens het voltooien van de installatie van Microsoft Defender voor Eindpunt.
keywords: probleemoplossing, probleemoplossing, Azure Active Directory, onboarding, foutbericht, foutberichten, Microsoft Defender voor eindpunt
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 1b769c1b3e4201802ea6150358568bf57894d305
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185803"
---
# <a name="troubleshoot-subscription-and-portal-access-issues"></a>Problemen met abonnementen en portaltoegang oplossen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troublshootonboarding-abovefoldlink)

Op deze pagina vindt u gedetailleerde stappen om problemen op te lossen die kunnen optreden bij het instellen van uw Microsoft Defender voor Eindpunt-service.

Als u een foutbericht ontvangt, geeft het Microsoft Defender-beveiligingscentrum een gedetailleerde uitleg over wat het probleem is en worden relevante koppelingen verstrekt.

## <a name="no-subscriptions-found"></a>Geen abonnementen gevonden

Als u tijdens het openen van  het Microsoft Defender-beveiligingscentrum een bericht krijgt dat er geen abonnementen zijn gevonden, betekent dit dat de Azure Active Directory (Azure AD) die wordt gebruikt om zich aan te melden bij de gebruiker bij de portal, geen Microsoft Defender voor Eindpunt-licentie heeft.

Mogelijke redenen:
- De Windows E5- en Office E5-licenties zijn afzonderlijke licenties.
- De licentie is aangeschaft, maar niet ingericht voor dit Azure AD-exemplaar.
    - Het kan een probleem zijn met het inrichten van licenties.
    - Het kan zijn dat u de licentie per ongeluk hebt ingericht op een andere Microsoft Azure AD dan de licentie die voor verificatie in de service wordt gebruikt.

In beide gevallen moet u contact opnemen met microsoft-ondersteuning bij algemene ondersteuning van Microsoft Defender voor [endpoint-](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) of [volumelicentieondersteuning.](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx)

![Afbeelding van geen gevonden abonnementen](images/atp-no-subscriptions-found.png)

## <a name="your-subscription-has-expired"></a>Uw abonnement is verlopen

Als u tijdens het openen van het Microsoft Defender-beveiligingscentrum een bericht krijgt **dat** uw abonnement is verlopen, is uw onlineserviceabonnement verlopen. Microsoft Defender for Endpoint-abonnement heeft, net als elk ander onlineserviceabonnement, een vervaldatum. 

U kunt ervoor kiezen om de licentie op elk moment te verlengen of uit te breiden. Bij toegang tot de portal  na de vervaldatum wordt een bericht van uw abonnement dat is verlopen, weergegeven met een optie om het offboarding-pakket van het apparaat te downloaden, mocht u ervoor kiezen om de licentie niet te verlengen.

> [!NOTE]
> Om veiligheidsredenen verloopt het pakket dat wordt gebruikt voor Offboard-apparaten 30 dagen na de datum waarop het is gedownload. Verlopen offboarding-pakketten die naar een apparaat zijn verzonden, worden geweigerd. Wanneer u een offboarding-pakket downloadt, wordt u op de hoogte gesteld van de vervaldatum van de pakketten en wordt het ook opgenomen in de pakketnaam.

![Afbeelding van verlopen abonnement](images/atp-subscription-expired.png)

## <a name="you-are-not-authorized-to-access-the-portal"></a>U bent niet gemachtigd om toegang te krijgen tot de portal

Als u een U bent niet gemachtigd om toegang te krijgen tot de **portal,** moet u er rekening mee houden dat Microsoft Defender voor Eindpunt een beveiligingscontrole, incidentonderzoek en antwoordproduct is en dat de toegang tot de portal daarom wordt beperkt en gecontroleerd door de gebruiker.
Zie Gebruikerstoegang toewijzen [**aan de portal voor meer informatie.**](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection)

![Afbeelding van niet geautoriseerde toegang tot portal](images/atp-not-authorized-to-access-portal.png)

## <a name="data-currently-isnt-available-on-some-sections-of-the-portal"></a>Gegevens zijn momenteel niet beschikbaar in sommige secties van de portal
Als in het portaldashboard en andere secties een foutbericht wordt weergegeven, zoals 'Gegevens zijn momenteel niet beschikbaar':

![Afbeelding van gegevens die momenteel niet beschikbaar zijn](images/atp-data-not-available.png)

U moet de subdomeinen en `securitycenter.windows.com` alle subdomeinen daar onder toestaan. Bijvoorbeeld `*.securitycenter.windows.com`.


## <a name="portal-communication-issues"></a>Problemen met portalcommunicatie
Als u problemen ondervindt met toegang tot de portal, ontbrekende gegevens of beperkte toegang tot gedeelten van de portal, moet u controleren of de volgende URL's zijn toegestaan en worden geopend voor communicatie.

- `*.blob.core.windows.net`
- `crl.microsoft.com`
- `https://*.microsoftonline-p.com`
- `https://*.securitycenter.windows.com` 
- `https://automatediracs-eus-prd.securitycenter.windows.com`
- `https://login.microsoftonline.com`
- `https://login.windows.net`
- `https://onboardingpackagescusprd.blob.core.windows.net`
- `https://secure.aadcdn.microsoftonline-p.com` 
- `https://securitycenter.windows.com` 
- `https://static2.sharepointonline.com` 



