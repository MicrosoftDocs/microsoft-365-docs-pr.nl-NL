---
title: Microsoft 365 gegevens vernietiging
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Een overzicht van Microsoft-beleidsregels voor recycling, verwijdering of vernietiging van Microsoft 365 datacenter-schijven en servers.
ms.openlocfilehash: 981903db68a79632285d7c5170aeb22014940a4a
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47331847"
---
# <a name="microsoft-365-data-destruction"></a>Microsoft 365 gegevens vernietiging

## <a name="physical-data-destruction"></a>Fysieke gegevens vernietiging

Microsoft heeft een standaardbeleid voor het verwerken van de recycling en verwijdering van schijfstations en mislukt of het intrekken van servers. Voordat u Microsoft 365-schijven opnieuw gebruikt, voert Microsoft een fysiek zuiveringsproces af op basis van nationale Institute of Standard 800-88 (de[NIST SP 800-88-richtlijnen voor media-Opschooning](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf)). Aangezien alle schijfstations in Microsoft 365 zijn versleuteld met BitLocker-volume versleuteling 800-88, is de voorwaarden voor het gebruik van de Microsoft-service niet-compatibel. Niettemin voert Microsoft dit proces uit.

Niet-gebruikte schijven binnen Microsoft 365-datacenters worden fysiek vernietigd en gecontroleerd via het ISO-proces. Activumtype bepaalt de juiste manier van verwijdering. Voor harde schijven die u niet kunt wissen, gebruikt Microsoft een vernietigings proces om de media te vernietigen en het herstel van gegevens te verbreken. Schijven worden bijvoorbeeld fysiek vernietigd, pulverized of verbrand. Microsoft behoudt alle records van de vernietiging en voert een vergelijkbaar verzuiverings proces voor servers opnieuw in met Microsoft 365. Deze richtlijnen bestaan uit elektronische en materiële verzuivering.

Voor elk datacenter wordt een fysiek destructie proces op de site gebruikt om de schijven van de site te verwijderen. Voor elk gebied van het datacenter wordt een beveiligde opslagruimte gebruikt voor de opslagmedia die zijn aangewezen voor de verwijdering van schijven. Elk veilig bin-station bevat bewaking van videomonitoring. Nadat een BGS-opslagruimte van ongeveer 50% is, is het team van site services contact met het fysieke Beveiligingsteam om de verwijdering te coördineren. Medewerkers van site services en beveiliging van Office Verwijder de beveiligde verplaatsings opslaglocatie en zet deze in een aangewezen beveiligde-opslagruimte. Beleidsregels en procedures voor het gebruik van apparatuur tijdens de verwijdering worden regelmatig getest, waaronder procedures om te voorkomen dat apparatuur wordt goedgekeurd voor vernietiging.

Bij de vernietiging van gegevens worden schijven gewist op een wijze die voldoet aan het NIST 800-88 (indien mogelijk) en vervolgens ingedeeld in een industriële versnipperder en fysieke demolished. Microsoft houdt de verantwoordelijkheid voor de activa die het datacenter verlaten, met behulp van het NIST SP 800-88 consistent te reinigen en te wissen, activum vernietiging, versleuteling, nauw keuren, nauwkeurig inventariseren, bijhouden en bescherming van een keten tijdens het transport. Dit proces wordt gecontroleerd via de televisie met een gesloten circuit en een certificaat van vernietiging wordt na voltooiing verstrekt.

Microsoft gebruikt voor het wissen van gegevens van [extreme protocol oplossingen](https://www.enterprisedataerasure.com/) (WPA). De WPA-software ondersteunt de ondersteuning van het NIST SP 800-88 voor het reinigen en wissen/veilig verwijderen. Voordat u ze opschoont of vervuilt, wordt er een inventaris gemaakt door Microsoft Asset Manager. Als een leverancier wordt gebruikt voor vernietiging, biedt de leverancier een certificaat van vernietiging voor elk verloren activum, dat door de activa Manager wordt gevalideerd.

## <a name="virtual-data-destruction"></a>Virtuele gegevens vernietiging

Microsoft beschikt over beleid voor het verwerken van gegevens en procedures voor de juiste virtuele vernietiging van gegevens om te beschermen tegen de mogelijkheid van gegevens die niet geschikt zijn voor het delen van gegevens tussen service tenants of die toegankelijk zijn na de verwijdering van de service. Gegevens die zijn verwijderd uit de service in één Tenant is niet toegankelijk voor een andere service Tenant, ook niet als een van de onderliggende fysieke opslag opnieuw is toegewezen. Dit is een resultaat van de samengestelde effecten van verschillende technologieën voor virtualisatie en fragmentatie, die worden gebruikt voor het schalen van virtuele omgevingen, het actieve gedrag van toepassingen in elke service-Tenant (zoals [pagina 0](https://docs.microsoft.com/office365/securitycompliance/office-365-exchange-online-data-deletion#page-zeroing)), en de vereiste versleutelings processen voor media en toepassingen.