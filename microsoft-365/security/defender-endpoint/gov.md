---
title: Microsoft Defender voor Eindpunt voor klanten van de Amerikaanse overheid
description: Meer informatie over de vereisten en mogelijkheden van Microsoft Defender voor eindpunt voor klanten van de Amerikaanse overheid
keywords: government, gcc, high, requirements, capabilities, defender, defender atp, mdatp, endpoint, dod
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1fd128a9b734606039438db1f6d9fbc36e93a3b9
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199007"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>Microsoft Defender voor Eindpunt voor klanten van de Amerikaanse overheid

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint voor klanten van de Amerikaanse overheid, gebouwd in de Amerikaanse Azure Government-omgeving, gebruikt dezelfde onderliggende technologieën als Defender for Endpoint in Azure Commercial.

Dit aanbod is beschikbaar voor klanten van GCC, GCC High en DoD en is gebaseerd op dezelfde preventie, detectie, onderzoek en herstel als de commerciële versie. Er zijn echter enkele verschillen in de beschikbaarheid van mogelijkheden voor deze aanbieding.

> [!NOTE]
> Als u een GCC-klant bent die Defender voor Eindpunt gebruikt in Commercieel, raadpleegt u de openbare documentatiepagina's.

## <a name="licensing-requirements"></a>Licentievereisten
Klanten van Microsoft Defender voor Endpoint voor de Amerikaanse overheid hebben een van de volgende aanbiedingen voor volumelicenties van Microsoft nodig:

### <a name="desktop-licensing"></a>Bureaubladlicenties
GCC | GCC High | DoD
:---|:---|:---
Windows 10 Enterprise E5 GCC | Windows 10 Enterprise E5 voor GCC High | Windows 10 Enterprise E5 voor DOD
| | Microsoft 365 E5 voor GCC High | 
| | Microsoft 365 G5-beveiliging voor GCC High | 
Microsoft Defender voor Eindpunt - GCC | Microsoft Defender voor Eindpunt voor GCC High | Microsoft Defender voor Eindpunt voor DOD

### <a name="server-licensing"></a>Serverlicenties
GCC | GCC High | DoD
:---|:---|:---
Microsoft Defender voor Endpoint Server GCC | Microsoft Defender voor Endpoint Server voor GCC High | Microsoft Defender voor Endpoint Server voor DOD
Azure Defender voor servers | Azure Defender voor servers - Overheid | Azure Defender voor servers - Overheid

> [!NOTE]
> DoD-licenties zijn alleen beschikbaar bij algemene beschikbaarheid van DoD.

<br>

## <a name="portal-urls"></a>Portal-URL's
De volgende zijn de URL's van de Microsoft Defender for Endpoint-portal voor klanten van de Amerikaanse overheid:

Klanttype | Portal-URL
:---|:---
GCC | https://gcc.securitycenter.microsoft.us
GCC High | https://securitycenter.microsoft.us
DoD (PREVIEW) | https://securitycenter.microsoft.us

<br>

## <a name="endpoint-versions"></a>Endpoint-versies

### <a name="standalone-os-versions"></a>Zelfstandige OS-versies
De volgende besturingssysteemversies worden ondersteund:

OS-versie | GCC | GCC High | DoD (PREVIEW)
:---|:---|:---|:---
Windows 10, versie 20H2 (met [KB4586853](https://support.microsoft.com/help/4586853)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, versie 2004 (met [KB4586853](https://support.microsoft.com/help/4586853)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, versie 1909 (met [KB4586819](https://support.microsoft.com/help/4586819)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, versie 1903 (met [KB4586819](https://support.microsoft.com/help/4586819)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, versie 1809 (met [KB4586839](https://support.microsoft.com/help/4586839)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, versie 1803 (met [KB4598245](https://support.microsoft.com/help/4598245)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, versie 1709 | ![Nee](images/svg/check-no.svg)<br>Opmerking: Wordt niet ondersteund | ![Ja ](images/svg/check-yes.svg) met [KB4499147](https://support.microsoft.com/help/4499147)<br>Opmerking: [Afgeschaft,](https://docs.microsoft.com/lifecycle/announcements/revised-end-of-service-windows-10-1709)kunt u een upgrade uitvoeren | ![Nee](images/svg/check-no.svg)<br>Opmerking: Wordt niet ondersteund
Windows 10, versie 1703 en eerder | ![Nee](images/svg/check-no.svg)<br>Opmerking: Wordt niet ondersteund | ![Nee](images/svg/check-no.svg)<br>Opmerking: Wordt niet ondersteund | ![Nee](images/svg/check-no.svg)<br>Opmerking: Wordt niet ondersteund
Windows Server 2019 (met [KB4586839](https://support.microsoft.com/help/4586839)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2016 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 8.1 Enterprise | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 8 Pro | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 7 SP1 Enterprise | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 7 SP1 Pro | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Linux | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
macOS | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Android | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog
iOS | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog

> [!NOTE]
> Wanneer een patch is opgegeven, moet deze worden geïmplementeerd vóór de onboarding van het apparaat om Defender voor Eindpunt te configureren naar de juiste omgeving.

> [!NOTE]
> Probeert u Windows-apparaten die ouder zijn dan Windows 10 of Windows Server 2019 aan te sluiten met [Microsoft Monitoring Agent?](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma) U moet 'Azure US Government' kiezen onder 'Azure Cloud' als u [](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) de installatiewizard gebruikt [of](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)als u een opdrachtregel of een [script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) gebruikt, de parameter 'OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE' in te stellen op 1.

### <a name="os-versions-when-using-azure-defender-for-servers"></a>OS-versies bij het gebruik van Azure Defender voor servers
De volgende besturingssysteemversies worden ondersteund bij het gebruik van [Azure Defender voor servers:](https://docs.microsoft.com/azure/security-center/security-center-wdatp)

OS-versie | GCC | GCC High | DoD (PREVIEW)
:---|:---|:---|:---
Windows Server 2016 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)

<br>

## <a name="required-connectivity-settings"></a>Vereiste connectiviteitsinstellingen
Als een proxy of firewall standaard al het verkeer blokkeert en alleen specifieke domeinen toestaat, voegt u de domeinen in het downloadbare blad toe aan de lijst met toegestane domeinen.

In de volgende downloadbare spreadsheet worden de services en de bijbehorende URL's vermeld waar uw netwerk verbinding mee moet kunnen maken. Controleer of er geen firewall- of netwerkfilterregels zijn waarmee de toegang tot deze URL's wordt ontzegd of dat er speciaal voor hen een regel *voor* toestaan wordt gemaakt.

Spreadsheet met domeinenlijst | Beschrijving
:-----|:-----
![Thumb image for Microsoft Defender for Endpoint URLLs spreadsheet](images/mdatp-urls.png)<br/> | Spreadsheet met specifieke DNS-records voor servicelocaties, geografische locaties en besturingssysteem. <br><br>[Download de spreadsheet hier.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

Zie Apparaatproxy- en [internetverbindingsinstellingen configureren](configure-proxy-internet.md)voor meer informatie.

> [!NOTE]
> Het spreadsheet bevat ook commerciële URL's, controleer of u de tabbladen 'US Gov' controleert. <br> Zoek bij het filteren naar de records met het label 'US Gov' en uw specifieke cloud onder de kolom Geografie.

<br>

## <a name="api"></a>API
In plaats van de openbare URL's in onze [API-documentatie,](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/apis-intro)moet u de volgende URL's gebruiken:

Eindpunttype | GCC | GCC High & DoD (PREVIEW)
:---|:---|:---
Aanmelden | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
Defender voor Endpoint API | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br>

## <a name="feature-parity-with-commercial"></a>Functiepariteit met commercieel
Defender voor Eindpunt heeft geen volledige pariteit met het commerciële aanbod. Hoewel ons doel is om alle commerciële functies en functionaliteit te leveren aan onze klanten van de Amerikaanse overheid, zijn er nog enkele mogelijkheden die we willen markeren.

Dit zijn de bekende hiaten vanaf februari 2021:

Functienaam | GCC | GCC High | DoD (PREVIEW)
:---|:---|:---|:---
Geautomatiseerd onderzoek en herstel: Live-antwoord | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Geautomatiseerd onderzoek en herstel: Reactie op Waarschuwingen voor Office 365 | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog
E-mailmeldingen | ![Nee](images/svg/check-no.svg) Uitrol | ![Nee](images/svg/check-no.svg) Uitrol | ![Nee](images/svg/check-no.svg) Uitrol
Evaluatielaboratorium | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Beheer en API's: rapport over de status en naleving van apparaten | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Beheer en API's: integratie met producten van derden | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Beheer en API's: Streaming API | ![Ja](images/svg/check-yes.svg) | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Beheer en API's: rapport bedreigingsbeveiliging | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Bedreigings- & kwetsbaarheidsbeheer | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Dreigingsanalyse | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Filteren van webinhoud | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Integraties: Azure Sentinel | ![Ja](images/svg/check-yes.svg) | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Integraties: Microsoft Cloud App Security | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog
Integraties: Microsoft Compliance Manager | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog
Integraties: Microsoft Defender voor identiteit | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog
Integraties: Microsoft Defender voor Office 365 | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog
Integraties: Microsoft Endpoint DLP | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog
Integraties: Microsoft Intune | ![Ja](images/svg/check-yes.svg) | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Integraties: Microsoft Power Automate & Azure Logic Apps | ![Ja](images/svg/check-yes.svg) | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Integraties: Skype voor Bedrijven / Teams | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Microsoft Threat Experts | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog
