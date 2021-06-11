---
title: Microsoft Defender voor Endpoint Device Control Verwisselbare Storage beveiliging
description: Inzicht in de 'mogelijkheden die helpen voorkomen dat gebruiker of computer of beide niet-geautoriseerde verwisselbare opslagmedia gebruiken
keywords: verwisselbare opslagmedia
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c9b97c2157ba8090628af23b2ab54cf38f04d8c6
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538385"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender voor Endpoint Device Control Verwisselbare Storage beveiliging

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender voor Endpoint Device Control Verwisselbare Storage beveiliging voorkomt dat gebruiker of computer of beide niet-geautoriseerde verwisselbare opslagmedia gebruiken.

## <a name="protection-policies"></a>Beveiligingsbeleid

### <a name="device-installation"></a>Apparaatinstallatie

**Mogelijkheden:** voorkom installatie met of zonder uitsluiting op basis van verschillende apparaateigenschappen.

**Beschrijving**
- Toegepast op machineniveau: hetzelfde beleid geldt voor aangemelde gebruikers.
- Ondersteunt MEM en GPO.
- Ondersteunde '[Apparaateigenschappen'](#device-properties)zoals vermeld.
- Zie Usb-apparaten en andere verwisselbare media beheren met Microsoft Defender voor eindpunt voor meer informatie over [Windows.](control-usb-devices-using-intune.md)

**Ondersteund platform** - Windows 10

**Beschrijving**
- Toegepast op machineniveau: hetzelfde beleid geldt voor aangemelde gebruikers
- Zie Apparaatbesturingselement voor macOS voor specifieke informatie [over macOS.](mac-device-control-overview.md)
 
**Ondersteund platform** - macOS Catalina 10.15.4+ (met systeemextensies ingeschakeld)

### <a name="removable-storage-access-control"></a>Verwisselbare opslagToegangsbesturingselement

**Mogelijkheden**
- *Controle* Lees of Schrijf of Voer toegang tot verwisselbare opslag uit op basis van verschillende apparaateigenschappen, met of zonder uitsluiting.
- *Voorkomen* Lees- of schrijf- of uitvoertoegang met of zonder uitsluiting - Specifiek apparaat toestaan op basis van verschillende apparaateigenschappen.

**Beschrijving**
- Toegepast op een computer of gebruiker of beide: sta alleen specifieke personen toe die lees-/schrijf-/uitvoertoegang tot specifieke verwisselbare opslag op een bepaalde computer uitvoeren.
- Ondersteuning voor MEM OMA-URI en GPO.
- Ondersteunde '[Apparaateigenschappen'](#device-properties)zoals vermeld.
- Zie Verwisselbare Windows Access Control voor [verwisselbare opslag voor functies](device-control-removable-storage-access-control.md)in de Windows.

**Ondersteund platform** - Windows 10

**Beschrijving**
- Toegepast op machineniveau: hetzelfde beleid geldt voor aangemelde gebruikers.
- Zie Apparaatbesturingselement voor macOS voor specifieke informatie [over macOS.](mac-device-control-overview.md)
 
**Ondersteund platform** - macOS Catalina 10.15.4+ (met systeemextensies ingeschakeld)

### <a name="windows-portable-device-access-control"></a>Windows Portable Device Access Control

**Mogelijkheden:** toegang tot lezen of schrijven weigeren tot een Windows draagbaar [apparaat,](/windows-hardware/drivers/portable/)bijvoorbeeld: Tablet, iPhone.

**Beschrijving**
- Toegepast op een computer of gebruiker of beide.
- Ondersteuning voor MEM OMA-URI en GPO.

**Ondersteund platform** - Windows 10

### <a name="endpoint-dlp-removable-storage"></a>Verwisselbare opslag van eindpunt DLP

**Mogelijkheden:** controleer of waarschuw of voorkom dat een gebruiker een item of informatie kopieert naar verwisselbare media of USB-apparaat.

**Beschrijving** - Zie Meer informatie over het voorkomen Microsoft 365 endpoint voor meer Windows informatie over het voorkomen van [gegevensverlies.](../../compliance/endpoint-dlp-learn-about.md)

**Ondersteund platform** - Windows 10

### <a name="bitlocker"></a>BitLocker 

**Mogelijkheden**
- Blokkeer gegevens die moeten worden geschreven naar verwisselbare stations die niet BitLocker beveiligd.
- Toegang tot verwisselbare stations blokkeren, tenzij ze zijn versleuteld op een computer die eigendom is van uw organisatie
 
**Beschrijving** - Zie Windows - Verwisselbaar station BitLocker voor [meer Instellingen.](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings)

**Ondersteund platform** - Windows 10

## <a name="device-properties"></a>Apparaateigenschappen

Met Microsoft Defender for Endpoint Device Control Verwisselbare Storage Protection kunt u de verwisselbare opslagtoegang beperken op basis van de eigenschappen die in de onderstaande tabel worden beschreven:


|Eigenschapsnaam  |Toepasselijke beleidsregels  |Van toepassing op besturingssystemen  |Beschrijving  |
|---------|---------|---------|---------|
|Apparaatklasse    |     [USB-apparaten en andere verwisselbare media beheren met Microsoft Defender voor Eindpunt](control-usb-devices-using-intune.md)     |   Windows      |  Zie apparaatconfiguratieklasse voor informatie over [apparaat-id-indelingen.](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors) **Opmerking:** Apparaatinstallatie kan worden toegepast op alle apparaten, niet alleen op verwisselbare opslag.       |
|Primaire id   |     Verwisselbare opslagToegangsbesturingselement    |   Windows      |      De primaire id bevat verwisselbare opslag en cd/dvd.   |
|Apparaat-id     |  [Usb-apparaten en andere verwisselbare media beheren met Microsoft Defender voor Eindpunt;](control-usb-devices-using-intune.md) Verwisselbare opslagToegangsbesturingselement       |      Windows   |    Zie Standaard USB-id's [](/windows-hardware/drivers/install/standard-usb-identifiers)voor informatie over apparaat-id-indelingen, bijvoorbeeld USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07      |
|Hardware-id     |     [Usb-apparaten en andere verwisselbare media beheren met Microsoft Defender voor Eindpunt;](control-usb-devices-using-intune.md) Verwisselbare opslagToegangsbesturingselement    |     Windows    |    Een tekenreeks heeft het apparaat in het systeem geïdentificeerd, bijvoorbeeld USBSTOR\DiskGeneric_Flash_Disk______8.07; **Opmerking:** Hardware-id is niet uniek; verschillende apparaten kunnen dezelfde waarde delen.|
|Exemplaar-id    | Apparaatinstallatie; Verwisselbare opslagToegangsbesturingselement     |     Windows    |   Een tekenreeks identificeert het apparaat in het systeem, bijvoorbeeld USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0      |
|Vriendelijke naam     |     Verwisselbare opslagToegangsbesturingselement    |   Windows      |    Een tekenreeks die is gekoppeld aan het apparaat, bijvoorbeeld Generic Flash Disk USB Device     |
|Leverancier-id/product-id     |  Verwisselbare opslagToegangsbesturingselement       |   Windows Mac      |     Leverancier-id is de leveranciercode met vier cijfers die door de USB-commissie aan de leverancier wordt toegewezen. Product-id is de viercijferige productcode die de leverancier aan het apparaat toewijst. Ondersteunings jokerteken.    |
|Serienummer     |     Verwisselbare opslagToegangsbesturingselement    |      Windows Mac   |     Bijvoorbeeld <SerialNumberId>002324B534BCB431B000058A</SerialNumberId>    |

## <a name="related-topic"></a>Verwant onderwerp

- [Microsoft Defender voor Endpoint Device Control Verwisselbare Storage Access Control](device-control-removable-storage-access-control.md)

