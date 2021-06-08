---
title: Microsoft Defender voor endpoint Device Control Printer Protection
description: Microsoft Defender for Endpoint Device Control Printer Protection blokkeert afdrukken via niet-bedrijfsprinters of niet-goedgekeurde USB-printer.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: v-lsaldanha
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: 431497ded684543c33d91c49a0da47e92297321f
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809228"
---
# <a name="device-control-printer-protection"></a>Apparaatbesturingselement printerbeveiliging 

Microsoft Defender for Endpoint Device Control Printer Protection blokkeert afdrukken via niet-bedrijfsprinters of niet-goedgekeurde USB-printer.

## <a name="licensing"></a>Licenties 

Voordat u aan de slag gaat met Printerbeveiliging, moet u [uw Microsoft 365 bevestigen.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) Als u Printerbeveiliging wilt openen en gebruiken, moet u het volgende hebben:

- Microsoft 365 E3 voor functionaliteit/beleidsimplementatie 
- Microsoft 365 E5 voor rapportage 

## <a name="permission"></a>Machtiging 

Voor beleidsimplementatie in Intune moet het account machtigingen hebben voor het maken, bewerken, bijwerken of verwijderen van apparaatconfiguratieprofielen als u beleid wilt implementeren via OMA-URI. U kunt aangepaste rollen maken of een van de ingebouwde rollen gebruiken met deze machtigingen:  

- Rol beleid en profielbeheer. 
- Of aangepaste rol met machtigingen maken/bewerken/bijwerken/lezen/verwijderen/rapporten weergeven ingeschakeld voor apparaatconfiguratieprofielen  
- Of globale beheerder

Als u apparaatconfiguratierapporten wilt zien, moet het account rapportenmachtigingen hebben. U kunt aangepaste rollen maken of de ingebouwde rollen gebruiken met deze machtigingen:  

- Globale beveiligingsbeheerder
- Beveiligingsbeheerder
- Beveiligingslezer 

## <a name="prepare-your-endpoints"></a>Uw eindpunten voorbereiden

Zorg ervoor dat de Windows 10 die u van plan bent printerbeveiliging te implementeren om aan deze vereisten te voldoen.

1. Deelnemen aan het Insider-programma.

1. De volgende Windows-updates zijn geïnstalleerd. 

    - Voor Windows 1809: installatie Windows [KB5003217 bijwerken](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46) 
    - Voor Windows 1909: installatie Windows [KB5003212 bijwerken](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)
    - Voor Windows 2004 of hoger 
    
1. Als u beleid wilt implementeren via groepsbeleid, moet het apparaat MDATP zijn. als u van plan bent beleid te implementeren via MEM, moet het apparaat zijn verbonden met Intune.

## <a name="deploy-device-control-printer-protection-policy"></a>Apparaatbesturingselement printerbeveiligingsbeleid implementeren

U kunt het beleid implementeren via Groepsbeleid of Intune.

| Title | Beschrijving | CSP-ondersteuning | Ondersteuning voor GPO | Ondersteuning op basis van gebruikers | Ondersteuning op basis van machines |
|:--|:--|:--|:--|:--|:--|
|**Apparaatbesturingselement afdrukbeperkingen inschakelen**|Personen blokkeren om af te drukken via een niet-zakelijke printer|Ja|Ja|Ja|Ja|
|**Lijst met goedgekeurde usb-verbonden afdrukapparaten**\*|Specifieke USB-printer toestaan|Ja|Ja|Ja|Ja|
|||||||

\* Dit beleid moet samen met Afdrukbeperkingen apparaatbesturingselement **inschakelen worden gebruikt**
## <a name="deploy-policy-via-intune"></a>Beleid implementeren via Intune 

Voor Intune ondersteunt apparaatbesturingselementprinterbeveiliging op dit moment alleen OMA-URI.

**Scenario 1: Voorkomen dat personen afdrukken via een niet-zakelijke printer** 

 - Beleid toepassen op computer: 

    - ./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl 

- Beleid toepassen op gebruiker: 

    - ./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser 

De CSP-ondersteuningsreeks `` <enabled/>`` met: 

:::image type="content" source="../../media/customeditrow.png" alt-text="aangepaste bewerkingsrij":::

**Scenario 2: Specifieke goedgekeurde USB-printers toestaan**

- Beleid toepassen op computer: 

    - ./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices 

- Beleid toepassen op gebruiker: 

    - ./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser  

De CSP-ondersteuningsreeks met goedgekeurde USB-printers via de eigenschap ApprovedUsbPrintDevices, `` <enabled/><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>`` bijvoorbeeld: 

:::image type="content" source="../../media/editrow.png" alt-text="rij bewerken":::

## <a name="deploy-policy-via-group-policy"></a>Beleid implementeren via groepsbeleid 

Als het apparaat niet is verbonden met Intune, kunt u het beleid ook implementeren via groepsbeleid. 

**Scenario 1: Voorkomen dat personen afdrukken via een niet-zakelijke printer** 

- Beleid toepassen op computer: 

    - Computerconfiguratie > beheersjablonen > Printer: Apparaatbesturingselement afdrukbeperkingen inschakelen 

- Beleid toepassen op gebruiker: 

    - Gebruikersconfiguratie > beheersjablonen > configuratiescherm > printers: Apparaatbesturingselementafdrukbeperkingen inschakelen 

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="beperkingen voor het afdrukken van apparaten inschakelen":::
 

**Scenario 2: Specifieke goedgekeurde USB-printers toestaan**

- Beleid toepassen op computer: 

    - Computerconfiguratie > beheersjablonen > printer: lijst met goedgekeurde afdrukapparaten met USB-verbinding 

- Beleid toepassen op gebruiker:  

    - Gebruikersconfiguratie > beheersjablonen > configuratiescherm > printers: Lijst met goedgekeurde usb-aangesloten afdrukapparaten 
 
 :::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="lijst met goedgekeurde usb-verbonden afdrukapparaten":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a>Apparaatbesturingselement printerbeveiligingsgegevens weergeven in microsoft Defender voor eindpuntportal 

In [Microsoft 365 beveiligingscentrum ziet](https://security.microsoft.com) u afdrukken die zijn geblokkeerd door het beleid voor apparaatbesturingselementprinterbeveiliging hierboven.
 
```sql
DeviceEvents 

|where ActionType == 'PrintJobBlocked' 

| extend parsed=parse_json(AdditionalFields) 

| extend PrintedFile=tostring(parsed.JobOrDocumentName) 

| extend PrintPortName=tostring(parsed.PortName) 

| extend PrinterName=tostring(parsed.PrinterName) 

| extend Policy=tostring(parsed.RestrictionReason)  

| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName,Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields 

| order by Timestamp desc 
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="geavanceerd zoeken":::
