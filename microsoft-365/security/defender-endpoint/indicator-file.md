---
title: Indicatoren voor bestanden maken
ms.reviewer: ''
description: Maak indicatoren voor een bestandshash die de detectie, preventie en uitsluiting van entiteiten definieert.
keywords: bestand, hash, beheren, toegestaan, geblokkeerd, blokkeren, schoon, schadelijk, bestandshash, ip-adres, url's, domein
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
ms.openlocfilehash: 35a0b66a4cdc4cf39c15329eda2e0aafced79f34
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199607"
---
# <a name="create-indicators-for-files"></a>Indicatoren voor bestanden maken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

U kunt verdere verspreiding van een aanval in uw organisatie voorkomen door potentieel schadelijke bestanden of vermoedelijke malware te verbieden. Als u een potentieel schadelijk bestand voor draagbaar uitvoerbaar (PE) kent, kunt u dit blokkeren. Deze bewerking voorkomt dat deze wordt gelezen, geschreven of uitgevoerd op machines in uw organisatie.

U kunt op twee manieren indicatoren voor bestanden maken:
- Door een indicator te maken via de pagina Instellingen
- Door een contextuele indicator te maken met behulp van de knop Indicator toevoegen op de pagina met bestandsgegevens

### <a name="before-you-begin"></a>Voordat u begint
Het is belangrijk om de volgende vereisten te begrijpen voordat u indicatoren voor bestanden maakt:

- Deze functie is beschikbaar als uw organisatie Windows Defender Antivirus gebruikt en cloudbeveiliging is ingeschakeld. Zie Technologieën van de volgende generatie gebruiken in Microsoft Defender Antivirus via beveiliging in de cloud voor [meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- De versie van de Antimalware-client moet 4.18.1901.x of hoger zijn.
- Ondersteund op computers op Windows 10, versie 1703 of hoger, Windows Server 2016 en 2019.
- Als u bestanden wilt blokkeren, moet u eerst de functie Blokkeren of toestaan [in-/uitschakelen  ](advanced-features.md) in Instellingen.
- Deze functie is ontworpen om te voorkomen dat verdachte malware (of mogelijk schadelijke bestanden) van internet wordt gedownload. Het ondersteunt momenteel draagbare uitvoerbare (PE)-bestanden, waaronder _.exe-_ en _.dll-bestanden._ De dekking wordt in de tijd uitgebreid.

De prestaties kunnen worden beïnvloed als u grote bestanden kopieert vanuit een netwerk delen naar uw lokale apparaat, met name via een VPN-verbinding. 

> [!IMPORTANT]
> - De functie Toestaan of blokkeren kan niet worden uitgevoerd op bestanden als de classificatie van het bestand aanwezig is in de cache van het apparaat vóór de actie toestaan of blokkeren 
> - Vertrouwde ondertekende bestanden worden anders behandeld. Defender voor Eindpunt is geoptimaliseerd voor het verwerken van schadelijke bestanden. Het blokkeren van vertrouwde ondertekende bestanden kan in sommige gevallen gevolgen hebben voor de prestaties.
> - Bestandsblokken worden meestal binnen een paar minuten afgedwongen, maar kunnen meer dan 30 minuten duren.
> - Als er conflicterende beleidsregels voor bestandsindicatoren zijn, wordt het handhavingsbeleid van het veiligere beleid toegepast. Een sha-256-indicatorbeleid voor bestandshash heeft bijvoorbeeld voorrang op een MD5-indicatorbeleid voor bestandshash als beide hashtypen hetzelfde bestand definiëren.

### <a name="create-an-indicator-for-files-from-the-settings-page"></a>Een indicator voor bestanden maken op de pagina Instellingen

1. Selecteer instellingenindicatoren in het  >  **navigatiedeelvenster.**  

2. Selecteer het **tabblad Bestandshash.**

3. Selecteer **Indicator toevoegen.**

4. Geef de volgende details op:
   - Indicator: geef de details van de entiteit op en definieer de afloop van de indicator.
   - Actie: geef de actie op die moet worden ondernomen en geef een beschrijving op.
   - Bereik: definieer het bereik van de machinegroep.

5. Bekijk de details op het tabblad Overzicht en klik vervolgens op **Opslaan.**

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a>Een contextuele indicator maken op de pagina met bestandsgegevens
Een van de opties bij het [uitvoeren van antwoordacties in een bestand](respond-file-alerts.md) is het toevoegen van een indicator voor het bestand. 

Wanneer u een indicatorhash voor een bestand toevoegt, kunt u ervoor kiezen om een waarschuwing te verhogen en het bestand te blokkeren wanneer een computer in uw organisatie dit probeert uit te voeren.

Bestanden die automatisch worden geblokkeerd door een indicator, worden niet weergegeven in het actiecentrum van het bestand, maar de waarschuwingen blijven wel zichtbaar in de wachtrij Waarschuwingen.


## <a name="related-topics"></a>Verwante onderwerpen
- [Indicatoren maken](manage-indicators.md)
- [Indicatoren maken voor IPs en URL's/domeinen](indicator-ip-domain.md)
- [Indicatoren maken op basis van certificaten](indicator-certificates.md)
- [Indicatoren beheren](indicator-manage.md)
