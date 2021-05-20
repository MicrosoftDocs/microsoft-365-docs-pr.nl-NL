---
title: Microsoft Defender voor Eindpunt voor overheidsklanten in de VS
description: Meer informatie over de vereisten en mogelijkheden van Microsoft Defender for Endpoint voor klanten van de Amerikaanse overheid
keywords: overheid, gcc, hoog, vereisten, mogelijkheden, defender, Microsoft Defender voor eindpunt, eindpunt, dod
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
ms.openlocfilehash: 0276f0464f898d3675e4cc1d6b69185e7e390a87
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572667"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>Microsoft Defender voor Eindpunt voor overheidsklanten in de VS

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint voor klanten van de Amerikaanse overheid, gebouwd in de Azure US Government-omgeving, gebruikt dezelfde onderliggende technologieën als Defender voor Endpoint in Azure Commercial.

Dit aanbod is beschikbaar voor GCC-, GCC High- en DoD-klanten en is gebaseerd op dezelfde preventie, detectie, onderzoek en herstel als de commerciële versie. Er zijn echter enkele verschillen in de beschikbaarheid van mogelijkheden voor dit aanbod.

> [!NOTE]
> Als u een GCC klant bent die Defender for Endpoint in Commercial gebruikt, raadpleegt u de openbare documentatiepagina's.

## <a name="licensing-requirements"></a>Licentievereisten
Microsoft Defender for Endpoint voor klanten van de Amerikaanse overheid vereist een van de volgende Microsoft-volumelicentieaanbiedingen:

### <a name="desktop-licensing"></a>Desktoplicenties
GCC | GCC hoog | Dod
:---|:---|:---
Windows 10 Enterprise E5 GCC | Windows 10 Enterprise E5 voor GCC High | Windows 10 Enterprise E5 voor DOD
| | Microsoft 365 E5 voor GCC High | Microsoft 365 G5 voor DOD
| | Microsoft 365 G5-beveiliging voor GCC high | Microsoft 365 G5 Beveiliging voor DOD
Microsoft Defender voor eindpunt - GCC | Microsoft Defender voor eindpunt voor GCC hoog | Microsoft Defender voor eindpunt voor DOD

### <a name="server-licensing"></a>Serverlicenties
GCC | GCC hoog | Dod
:---|:---|:---
Microsoft Defender voor Endpoint Server GCC | Microsoft Defender voor Endpoint Server voor GCC high | Microsoft Defender voor Endpoint Server voor DOD
Azure Defender voor servers | Azure Defender voor servers - Overheid | Azure Defender voor servers - Overheid

<br />

## <a name="portal-urls"></a>Portal-URL's
Hieronder volgen de URL's van de Microsoft Defender for Endpoint-portal voor klanten van de Amerikaanse overheid:

Type klant | Portal-URL
:---|:---
GCC | https://gcc.securitycenter.microsoft.us
GCC hoog | https://securitycenter.microsoft.us
Dod | https://securitycenter.microsoft.us

<br />

## <a name="endpoint-versions"></a>Eindpuntversies

### <a name="standalone-os-versions"></a>Zelfstandige versies van besturingssystemen
De volgende versies van het besturingssysteem worden ondersteund:

Versie van het besturingssysteem | GCC | GCC hoog | Dod
:---|:---|:---|:---
Windows 10, versie 20H2 (met [KB4586853](https://support.microsoft.com/help/4586853)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, versie 2004 (met [KB4586853](https://support.microsoft.com/help/4586853)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, versie 1909 (met [KB4586819](https://support.microsoft.com/help/4586819)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, versie 1903 (met [KB4586819](https://support.microsoft.com/help/4586819)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, versie 1809 (met [KB4586839](https://support.microsoft.com/help/4586839)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, versie 1803 (met [KB4598245](https://support.microsoft.com/help/4598245)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 10, versie 1709 | ![Nee](images/svg/check-no.svg)<br />Opmerking: wordt niet ondersteund | ![Ja ](images/svg/check-yes.svg) met [KB4499147](https://support.microsoft.com/help/4499147)<br />Opmerking: [Afgeschaft,](/lifecycle/announcements/revised-end-of-service-windows-10-1709)gelieve te upgraden | ![Nee](images/svg/check-no.svg)<br />Opmerking: wordt niet ondersteund
Windows 10, versie 1703 en eerder | ![Nee](images/svg/check-no.svg)<br />Opmerking: wordt niet ondersteund | ![Nee](images/svg/check-no.svg)<br />Opmerking: wordt niet ondersteund | ![Nee](images/svg/check-no.svg)<br />Opmerking: wordt niet ondersteund
Windows Server 2019 (met [KB4586839](https://support.microsoft.com/help/4586839)) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2016 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 8.1 Enterprise | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 8 Pro | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 7 SP1 Onderneming | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows 7 SP1 Pro | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Linux | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
MacOS | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Android | ![Nee](images/svg/check-no.svg) Op technische achterstand | ![Nee](images/svg/check-no.svg) Op technische achterstand | ![Nee](images/svg/check-no.svg) Op technische achterstand
iOS | ![Nee](images/svg/check-no.svg) Op technische achterstand | ![Nee](images/svg/check-no.svg) Op technische achterstand | ![Nee](images/svg/check-no.svg) Op technische achterstand

> [!NOTE]
> Wanneer een patch is opgegeven, moet deze worden geïmplementeerd voordat het apparaat wordt onboarding om Defender for Endpoint te configureren in de juiste omgeving.

> [!NOTE]
> Probeert u Windows apparaten ouder dan Windows 10 of Windows Server 2019 te onboarden met [Microsoft Monitoring Agent](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)? U moet 'Azure US Government' kiezen onder 'Azure Cloud' als u de [installatiewizard](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)gebruikt of als u een [opdrachtregel](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) of een [script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) gebruikt, de parameter 'OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE' instelt op 1.

### <a name="os-versions-when-using-azure-defender-for-servers"></a>Besturingssysteemversies bij gebruik van Azure Defender voor servers
De volgende versies van het besturingssysteem worden ondersteund bij het gebruik van [Azure Defender voor servers:](/azure/security-center/security-center-wdatp)

Versie van het besturingssysteem | GCC | GCC hoog | Dod
:---|:---|:---|:---
Windows Server 2019 | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Windows Server 2016 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)

<br />

## <a name="required-connectivity-settings"></a>Vereiste connectiviteitsinstellingen
Als door een proxy of firewall standaard al het verkeer wordt geblokkeerd en alleen bepaalde domeinen worden toegestaan, voegt u de domeinen die worden vermeld in het downloadbare blad toe aan de lijst met toegestane domeinen.

In het volgende downloadbare werkblad worden de services en de bijbehorende URL's weergegeven waarmee uw netwerk verbinding moet kunnen maken. Controleer of er geen firewall- of netwerkfilterregels zijn die de toegang tot deze URL's weigeren of een *toegestane* regel speciaal voor deze URL's maken.

Lijst met spreadsheets met domeinen | Omschrijving
:-----|:-----
![Duimafbeelding voor microsoft defender voor endpoint-URL's spreadsheet](images/mdatp-urls.png)<br/> | Spreadsheet met specifieke DNS-records voor servicelocaties, geografische locaties en besturingssysteem. <br /><br />[Download hier de spreadsheet.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

Zie [Instellingen voor apparaatproxy en internetverbinding configureren](configure-proxy-internet.md)voor meer informatie.

> [!NOTE]
> De spreadsheet bevat ook commerciële URL's, zorg ervoor dat u de tabbladen "US Gov" controleert.
> 
> Zoek bij het filteren naar de records met het label 'US Gov' en uw specifieke cloud onder de kolom geografie.

### <a name="service-backend-ip-ranges"></a>Ip-bereiken voor serviceback-end

Als uw netwerkapparaten geen DNS-regels ondersteunen, gebruikt u in plaats daarvan IP-bereiken.

Defender for Endpoint voor Us Government-klanten is gebouwd in de Azure US Government-omgeving, geïmplementeerd in de volgende regio's:

- AzureCloud.usgovtexas
- AzureCloud.usgovvirginia

U kunt de Azure IP-bereiken vinden in [Azure IP-bereiken en servicetags - US Government Cloud](https://www.microsoft.com/download/details.aspx?id=57063).

> [!NOTE]
> Als cloudgebaseerde oplossing kunnen de IP-adresbereiken veranderen. Het wordt aanbevolen om over te stappen op DNS-regels.

<br />

## <a name="api"></a>Api
In plaats van de openbare URI's die in onze [API-documentatie](apis-intro.md)worden vermeld, moet u de volgende URI's gebruiken:

Eindpunttype | GCC | GCC High & DoD
:---|:---|:---
inloggen | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
Defender voor Endpoint API | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br />

## <a name="feature-parity-with-commercial"></a>Functiepariteit met commercieel
Defender for Endpoint voor klanten van de Amerikaanse overheid heeft geen volledige pariteit met het commerciële aanbod. Hoewel ons doel is om alle commerciële functies en functionaliteit aan onze klanten van de Amerikaanse overheid te leveren, zijn er enkele mogelijkheden die we nog niet willen benadrukken.

Dit zijn de bekende hiaten:

Functienaam | GCC | GCC hoog | Dod
:---|:---|:---|:---
Beheer en API's: Streaming API | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Filteren van webinhoud | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Integraties: Azure Sentinel | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) Waarschuwingen <br /> ![Nee](images/svg/check-no.svg) Incidenten & Ruwe data: In ontwikkeling | ![Ja](images/svg/check-yes.svg) Waarschuwingen <br /> ![Nee](images/svg/check-no.svg) Incidenten & Ruwe data: In ontwikkeling
Integraties: Microsoft Cloud App Security | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Integraties: Microsoft Compliance Manager | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Integraties: Microsoft Defender voor identiteit | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Integraties: Microsoft Endpoint DLP | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Integraties: Microsoft Intune | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg) | ![Ja](images/svg/check-yes.svg)
Integraties: Microsoft Power Automate & Azure Logic Apps | ![Ja](images/svg/check-yes.svg) | ![Nee](images/svg/check-no.svg) In ontwikkeling | ![Nee](images/svg/check-no.svg) In ontwikkeling
Microsoft Threat Experts | ![Nee](images/svg/check-no.svg) Op technische achterstand | ![Nee](images/svg/check-no.svg) Op technische achterstand | ![Nee](images/svg/check-no.svg) Op technische achterstand
