---
title: Indicatoren maken op basis van certificaten
ms.reviewer: ''
description: Indicatoren maken op basis van certificaten die de detectie, preventie en uitsluiting van entiteiten definiëren.
keywords: ioc, certificaat, certificaten, beheren, toegestaan, geblokkeerd, blokkeren, schoon, schadelijk, bestandshash, ip-adres, url's, domein
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
ms.openlocfilehash: 8cf611e38bc781c2302f70f6491bb827410235b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164679"
---
# <a name="create-indicators-based-on-certificates"></a>Indicatoren maken op basis van certificaten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

U kunt indicatoren voor certificaten maken. Enkele veelgebruikte gevallen zijn:

- Scenario's wanneer u blokkeringstechnologieën moet implementeren, zoals regels voor het verlagen van het oppervlak van aanvallen en gecontroleerde maptoegang, maar het gedrag van ondertekende toepassingen moet toestaan door het certificaat toe te voegen aan de lijst toestaan. [](attack-surface-reduction.md) [](controlled-folders.md)
- Het gebruik van een specifieke ondertekende toepassing in uw organisatie blokkeren. Door een indicator te maken om het certificaat van de toepassing te blokkeren, voorkomt Windows Defender AV dat bestandsuitvoeringen worden uitgevoerd (blokkeren en herstellen) en de automatische controle en herstel zich hetzelfde gedragen.


### <a name="before-you-begin"></a>Voordat u begint

Het is belangrijk om de volgende vereisten te begrijpen voordat u indicatoren voor certificaten maakt:

- Deze functie is beschikbaar als uw organisatie Windows Defender Antivirus gebruikt en cloudbeveiliging is ingeschakeld. Zie Beveiliging in de [cloud beheren voor meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)
- De versie van de Antimalware-client moet 4.18.1901.x of hoger zijn.
- Ondersteund op computers op Windows 10, versie 1703 of hoger, Windows Server 2016 en 2019.
- De definities voor virus- en bedreigingsbeveiliging moeten up-to-date zijn.
- Deze functie ondersteunt momenteel het invoeren van . CER of . PEM-bestandsextensies.

>[!IMPORTANT]
> - Een geldig bladcertificaat is een handtekeningcertificaat dat een geldig certificeringspad heeft en moet zijn geketend aan de Hoofdcertificaatinstantie (CA) die door Microsoft wordt vertrouwd.  U kunt ook een aangepast (zelf ondertekend) certificaat gebruiken zolang het wordt vertrouwd door de client (Root CA-certificaat is geïnstalleerd onder de lokale computer 'Vertrouwde hoofdcertificeringsinstanties').
>- De kinderen of ouders van de IOC's voor het certificaat toestaan/blokkeren worden niet opgenomen in de IoC-functionaliteit toestaan/blokkeren, alleen bladcertificaten worden ondersteund.
>- Ondertekende microsoft-certificaten kunnen niet worden geblokkeerd.

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a>Maak een indicator voor certificaten op de pagina Instellingen:

>[!IMPORTANT]
> Het kan maximaal 3 uur duren om een certificaat-IoC te maken en te verwijderen.

1. Selecteer instellingenindicatoren in het  >  **navigatiedeelvenster.**  

2. Selecteer het **tabblad** Certificaat.

3. Selecteer **Indicator toevoegen.**

4. Geef de volgende details op:
   - Indicator: geef de details van de entiteit op en definieer de afloop van de indicator.
   - Actie: geef de actie op die moet worden ondernomen en geef een beschrijving op.
   - Bereik: definieer het bereik van de machinegroep.

5. Bekijk de details op het tabblad Overzicht en klik vervolgens op **Opslaan.**

## <a name="related-topics"></a>Verwante onderwerpen
- [Indicatoren maken](manage-indicators.md)
- [Indicatoren voor bestanden maken](indicator-file.md)
- [Indicatoren maken voor IPs en URL's/domeinen](indicator-ip-domain.md)
- [Indicatoren beheren](indicator-manage.md)
