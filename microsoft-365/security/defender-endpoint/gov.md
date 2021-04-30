---
title: Microsoft Defender voor Eindpunt voor overheidsklanten in de VS
description: Meer informatie over de vereisten en mogelijkheden van Microsoft Defender voor eindpunt voor klanten van de Amerikaanse overheid
keywords: government, gcc, high, requirements, capabilities, defender, Microsoft Defender for Endpoint, endpoint, dod
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
ms.openlocfilehash: 1f0005ed4614a8d01d2a64e8853be99a204825c8
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086811"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>Microsoft Defender voor Eindpunt voor overheidsklanten in de VS

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint voor klanten van de Amerikaanse overheid, ingebouwd in de Azure US Government-omgeving, gebruikt dezelfde onderliggende technologieën als Defender voor Eindpunt in Azure Commercial.

Dit aanbod is beschikbaar voor klanten GCC, GCC High en DoD en is gebaseerd op dezelfde preventie, detectie, onderzoek en herstel als de commerciële versie. Er zijn echter enkele verschillen in de beschikbaarheid van mogelijkheden voor deze aanbieding.

> [!NOTE]
> Als u een klant bent GCC Defender voor Eindpunt in Commercieel gebruikt, raadpleegt u de openbare documentatiepagina's.

## <a name="licensing-requirements"></a>Licentievereisten
Klanten van Microsoft Defender voor Endpoint voor de Amerikaanse overheid hebben een van de volgende aanbiedingen voor volumelicenties van Microsoft nodig:

### <a name="desktop-licensing"></a>Bureaubladlicenties
GCC | GCC Hoog | DoD
:---|:---|:---
Windows 10 Enterprise E5 GCC | Windows 10 Enterprise E5 voor GCC High | Windows 10 Enterprise E5 voor DOD
| | Microsoft 365 E5 voor GCC High | Microsoft 365 G5 voor DOD
| | Microsoft 365 G5-beveiliging voor GCC Hoog | Microsoft 365 G5-beveiliging voor dod
Microsoft Defender voor Eindpunt - GCC | Microsoft Defender voor Eindpunt voor GCC High | Microsoft Defender voor Eindpunt voor DOD

### <a name="server-licensing"></a>Serverlicenties
GCC | GCC Hoog | DoD
:---|:---|:---
Microsoft Defender voor Endpoint Server GCC | Microsoft Defender voor Endpoint Server voor GCC High | Microsoft Defender voor Endpoint Server voor DOD
Azure Defender voor servers | Azure Defender voor servers - Overheid | Azure Defender voor servers - Overheid

<br />

## <a name="portal-urls"></a>Portal-URL's
De volgende zijn de URL's van de Microsoft Defender for Endpoint-portal voor klanten van de Amerikaanse overheid:

Klanttype | Portal-URL
:---|:---
GCC | https://gcc.securitycenter.microsoft.us
GCC Hoog | https://securitycenter.microsoft.us
DoD | https://securitycenter.microsoft.us

<br />

## <a name="endpoint-versions"></a>Endpoint-versies

### <a name="standalone-os-versions"></a>Zelfstandige OS-versies
De volgende besturingssysteemversies worden ondersteund:

OS-versie | GCC | GCC Hoog | DoD
:---|:---|:---|:---
Windows 10, versie 20H2 (met [KB4586853](https://support.microsoft.com/help/4586853)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, versie 2004 (met [KB4586853](https://support.microsoft.com/help/4586853)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, versie 1909 (met [KB4586819](https://support.microsoft.com/help/4586819)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, versie 1903 (met [KB4586819](https://support.microsoft.com/help/4586819)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, versie 1809 (met [KB4586839](https://support.microsoft.com/help/4586839)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, versie 1803 (met [KB4598245](https://support.microsoft.com/help/4598245)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, versie 1709 | ![Nee](images/svg/check-no.svg)<br />Opmerking: Wordt niet ondersteund | ![Ja ](images/svg/check-yes.svg) met [KB4499147](https://support.microsoft.com/help/4499147)<br />Opmerking: [Afgeschaft,](https://docs.microsoft.com/lifecycle/announcements/revised-end-of-service-windows-10-1709)kunt u een upgrade uitvoeren | ![Nee](images/svg/check-no.svg)<br />Opmerking: Wordt niet ondersteund
Windows 10, versie 1703 en eerder | ![Nee](images/svg/check-no.svg)<br />Opmerking: Wordt niet ondersteund | ![Nee](images/svg/check-no.svg)<br />Opmerking: Wordt niet ondersteund | ![Nee](images/svg/check-no.svg)<br />Opmerking: Wordt niet ondersteund
Windows Server 2019 (met [KB4586839](https://support.microsoft.com/help/4586839)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2016 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 8.1 Enterprise | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 8 Pro | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 7 SP1 Enterprise | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 7 SP1 Pro | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Linux | ![Ja](images/svg/check-yes.svg) In voorbeeld<br />Zie onderstaande notitie | ![Ja](images/svg/check-yes.svg) In voorbeeld<br />Zie onderstaande notitie | ![Ja](images/svg/check-yes.svg) In voorbeeld<br />Zie onderstaande notitie
macOS | ![Ja](images/svg/check-yes.svg) In voorbeeld<br />Zie onderstaande notitie | ![Ja](images/svg/check-yes.svg) In voorbeeld<br />Zie onderstaande notitie | ![Ja](images/svg/check-yes.svg) In voorbeeld<br />Zie onderstaande notitie
Android | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog
iOS | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog

> [!NOTE]
> Wanneer een patch is opgegeven, moet deze worden geïmplementeerd vóór de onboarding van het apparaat om Defender voor Eindpunt te configureren naar de juiste omgeving.

> [!NOTE]
> Probeert u Windows apparaten die ouder zijn dan Windows 10 of Windows Server 2019 aan te Windows [Microsoft Monitoring Agent?](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma) U moet 'Azure US Government' kiezen onder 'Azure Cloud' als u [](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) de installatiewizard gebruikt [of](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)als u een opdrachtregel of een [script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) gebruikt, de parameter 'OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE' in te stellen op 1.

> [!NOTE]
> U hebt versie 101.25.72 en hoger nodig voor Linux en versie 101.25.69 en hoger voor macOS.

### <a name="os-versions-when-using-azure-defender-for-servers"></a>OS-versies bij het gebruik van Azure Defender voor servers
De volgende besturingssysteemversies worden ondersteund bij het gebruik van [Azure Defender voor servers:](https://docs.microsoft.com/azure/security-center/security-center-wdatp)

OS-versie | GCC | GCC Hoog | DoD
:---|:---|:---|:---
Windows Server 2019 | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Windows Server 2016 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)

<br />

## <a name="required-connectivity-settings"></a>Vereiste connectiviteitsinstellingen
Als een proxy of firewall standaard al het verkeer blokkeert en alleen specifieke domeinen toestaat, voegt u de domeinen in het downloadbare blad toe aan de lijst met toegestane domeinen.

In de volgende downloadbare spreadsheet worden de services en de bijbehorende URL's vermeld waar uw netwerk verbinding mee moet kunnen maken. Controleer of er geen firewall- of netwerkfilterregels zijn waarmee de toegang tot deze URL's wordt ontzegd of dat er speciaal voor hen een regel *voor* toestaan wordt gemaakt.

Spreadsheet met domeinenlijst | Beschrijving
:-----|:-----
![Thumb image for Microsoft Defender for Endpoint URLLs spreadsheet](images/mdatp-urls.png)<br/> | Spreadsheet met specifieke DNS-records voor servicelocaties, geografische locaties en besturingssysteem. <br /><br />[Download de spreadsheet hier.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

Zie Apparaatproxy- en [internetverbindingsinstellingen configureren](configure-proxy-internet.md)voor meer informatie.

> [!NOTE]
> Het spreadsheet bevat ook commerciële URL's, controleer of u de tabbladen 'US Gov' controleert.
> 
> Zoek bij het filteren naar de records met het label 'US Gov' en uw specifieke cloud onder de kolom Geografie.

### <a name="service-backend-ip-ranges"></a>IP-bereik met back-over-service

Als uw netwerkapparaten geen DNS-regels ondersteunen, gebruikt u in plaats daarvan IP-bereik.

Defender for Endpoint voor klanten van de Amerikaanse overheid is gebouwd in de Azure US Government-omgeving, geïmplementeerd in de volgende regio's:

- AzureCloud.usgovtexas
- AzureCloud.usgovvirginia

U kunt de Azure IP-bereik vinden in [Azure IP-bereik en ServiceLabels – US Government Cloud](https://www.microsoft.com/download/details.aspx?id=57063).

> [!NOTE]
> Als cloudoplossing kunnen de IP-adresbereiken worden gewijzigd. U wordt aangeraden over te gaan op regels op basis van DNS.

<br />

## <a name="api"></a>API
In plaats van de openbare URL's in onze [API-documentatie,](apis-intro.md)moet u de volgende URL's gebruiken:

Eindpunttype | GCC | GCC Hoge & DoD
:---|:---|:---
Aanmelden | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
Defender voor Endpoint API | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br />

## <a name="feature-parity-with-commercial"></a>Functiepariteit met commercieel
Defender for Endpoint voor klanten van de Amerikaanse overheid heeft geen volledige pariteit met het commerciële aanbod. Hoewel ons doel is om alle commerciële functies en functionaliteit te leveren aan onze klanten van de Amerikaanse overheid, zijn er nog enkele mogelijkheden die we willen markeren.

Dit zijn de bekende hiaten vanaf april 2021:

Functienaam | GCC | GCC Hoog | DoD
:---|:---|:---|:---
Beheer en API's: Streaming API | ![Ja](images/svg/check-yes.svg) | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Filteren van webinhoud | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Integraties: Azure Sentinel | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) Waarschuwingen <br /> ![Nee](images/svg/check-no.svg) Incidenten & Onbewerkte gegevens: In ontwikkeling | ![Ja](images/svg/check-yes.svg) Waarschuwingen <br /> ![Nee](images/svg/check-no.svg) Incidenten & Onbewerkte gegevens: In ontwikkeling
Integraties: Microsoft Cloud App Security | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Integraties: Microsoft Compliance Manager | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Integraties: Microsoft Defender voor identiteit | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Integraties: Microsoft Endpoint DLP | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog
Integraties: Microsoft Intune | ![Ja](images/svg/check-yes.svg) | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Integraties: Microsoft Power Automate & Azure Logic Apps | ![Ja](images/svg/check-yes.svg) | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Microsoft Threat Experts | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog | ![Nee](images/svg/check-no.svg) On engineering backlog
