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
ms.openlocfilehash: ec5cfa78852d65db808c4e853f90f5639df25d6f
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300148"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Microsoft Defender voor Endpoint Device Control Verwisselbare Storage beveiliging

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender voor Endpoint Device Control Verwisselbare Storage beveiliging voorkomt dat gebruiker of computer of beide niet-geautoriseerde verwisselbare opslagmedia gebruiken.

**Microsoft Defender for Endpoint Removable Storage Protection**


|Beleid  |Mogelijkheid |Beschrijving  |
|---------|---------|---------|
|Apparaatinstallatie    |  Installatie voorkomen met of zonder uitsluiting - Specifieke apparaten toestaan op basis van verschillende eigenschappen; Zie de sectie [Apparaateigenschappen](#device-properties) hieronder voor meer informatie.        |    Werkt op de computer: Verschillende gebruikers die zich aanmelden bij dezelfde computer, worden beperkt door hetzelfde beleid. Zie Usb-apparaten en andere [verwisselbare media beheren](control-usb-devices-using-intune.md)met Microsoft Defender voor Eindpunt voor meer informatie.     |
|Verwisselbare opslagToegangsbesturingselement      | (1) Controleer lees- of schrijf- of uitvoertoegang tot verwisselbare opslag op basis van verschillende apparaateigenschappen, met of zonder uitzondering. Zie de sectie Apparaateigenschappen hieronder [voor](#device-properties) meer informatie. (2) Lees- of schrijf- of uitvoertoegang voorkomen met of zonder uitsluiting - Specifieke apparaten toestaan op basis van verschillende apparaateigenschappen; Zie de sectie Apparaateigenschappen hieronder [](#device-properties) voor meer informatie over de apparaateigenschappen.     |     Werkt op een computer of gebruiker of beide: Sta alleen specifieke personen toe die lees-/schrijf-/uitvoertoegang tot specifieke verwisselbare opslag op een specifieke computer uitvoeren; voor functie in Windows, zie [Verwisselbare opslagToegangsbesturingselement](device-control-removable-storage-access-control.md); zie Apparaatbesturingselement [voor macOS](mac-device-control-overview.md)voor functie in Mac.     |
|Verwisselbare opslag van eindpunt DLP      |    Controleer of waarschuw of voorkom dat een gebruiker een item of informatie kopieert naar verwisselbare media of USB-apparaten.     |  Zie [Microsoft Endpoint DLP](/compliance/endpoint-dlp-learn-about.md)voor meer informatie.       |
|BitLocker    |     Gegevens blokkeren die moeten worden geschreven naar verwisselbare stations die niet BitLocker beveiligd: Toegang tot verwisselbare stations blokkeren, tenzij ze zijn versleuteld op een computer die eigendom is van uw organisatie.    |   Zie voor meer informatie BitLocker - [Verwisselbaar station Instellingen.](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings#bitlocker---removable-drive-settings.md)      |

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
