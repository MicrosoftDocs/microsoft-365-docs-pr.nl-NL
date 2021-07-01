---
title: Microsoft Defender voor Endpoint Device Control Verwisselbare Storage Access Control
description: Een walk-through over Microsoft Defender voor Endpoint
keywords: verwisselbare opslagmedia
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8b32ab5162e0022d9500f7ddba2fe5bbca1017e7
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229573"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Microsoft Defender voor Endpoint Device Control Verwisselbare Storage Access Control

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Met Microsoft Defender voor Endpoint Device Control Verwisselbaar Storage Access Control kunt u de volgende taak uitvoeren:
- het lezen, schrijven of uitvoeren van toegang tot verwisselbare opslag, met of zonder uitsluiting, toestaan of voorkomen

|Privilege |Machtiging  |
|---------|---------|
|Toegang    |  Lezen, Schrijven, Uitvoeren       |
|Actiemodus    |    Controleren, Toestaan, Voorkomen     |
|CSP-ondersteuning   |   Ja      |
|Ondersteuning voor GPO    |   Ja      |
|Ondersteuning op basis van gebruikers     |   Ja      |
|Ondersteuning op basis van machines    |    Ja     |

## <a name="prepare-your-endpoints"></a>Uw eindpunten voorbereiden

Verwisselbare Storage Access Control implementeren op Windows 10 apparaten met antimalwareclient **versie 4.18.2103.3 of hoger.**

- **4.18.2104 of hoger:** SerialNumberId, VID_PID, filepath-based GPO support, ComputerSid

- **4.18.2105** of hoger : Jokertekenondersteuning toevoegen voor HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, de combinatie van specifieke gebruiker op een specifieke computer, verwijderbare SSD (een SanDisk Extreme SSD)/USB Attached SCSI (UAS) ondersteuning

:::image type="content" source="images/powershell.png" alt-text="De PowerShell-interface":::

> [!NOTE]
> Geen van Windows-beveiliging onderdelen hoeft actief te zijn, u kunt Verwisselbaar Storage Access Control uitvoeren, onafhankelijk van Windows-beveiliging status.

## <a name="policy-properties"></a>Beleidseigenschappen

U kunt de volgende eigenschappen gebruiken om een verwisselbare opslaggroep te maken:

**Naam van eigenschap: groeps-id**

1. Beschrijving: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), een unieke id, vertegenwoordigt de groep en wordt gebruikt in het beleid.

**Eigenschapsnaam: DescriptorIdList**

1. Beschrijving: Vermeld de apparaateigenschappen die u wilt gebruiken voor de groep.
Vermeld de apparaateigenschappen die u wilt gebruiken voor de groep.
Zie voor elke apparaateigenschappen de sectie **Apparaateigenschappen** hierboven voor meer informatie.

1. Opties:

    - Primaire id
        - VerwisselbareMediaDevices
        - CdRomDevices
    - DeviceId
    - HardwareId
    - InstancePathId: InstancePathId is een tekenreeks die het apparaat in het systeem uniek identificeert, bijvoorbeeld USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0. Het getal aan het einde **(bijvoorbeeld&0)** vertegenwoordigt de beschikbare sleuf en kan veranderen van apparaat naar apparaat. Voor de beste resultaten gebruikt u een jokerteken aan het einde. Bijvoorbeeld: USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611*
    - FriendlyNameId
    - SerialNumberId
    - VID
    - PID
    - VID_PID
        - 0751_55E0: overeenkomen met dit exacte VID/PID-paar
        - _55E0: overeenkomen met alle media met PID=55E0
        - 0751_: overeenkomen met alle media met VID=0751
        
**Eigenschapsnaam: MatchType** 

1. Beschrijving: Wanneer er meerdere apparaateigenschappen worden gebruikt in de DescriptorIDList, definieert MatchType de relatie.

1. Opties:

    - MatchAll: Alle kenmerken onder de DescriptorIdList zijn **En-relatie;** Als de beheerder bijvoorbeeld DeviceID en InstancePathID plaatst, controleert het systeem voor elke aangesloten USB of de USB aan beide waarden voldoet.
    - MatchAny: De kenmerken onder de DescriptorIdList zijn **Of-relatie;** Als de beheerder bijvoorbeeld DeviceID en InstancePathID plaatst, voert het systeem voor elke aangesloten  USB de afdwinging uit, zolang de USB een identieke Apparaat-id- of Exemplaar-id-waarde heeft. 

Hieronder volgen de eigenschappen van het toegangsbeheerbeleid:

**Naam van eigenschap: PolicyRuleId**

1. Beschrijving: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), een unieke id, vertegenwoordigt het beleid en wordt gebruikt in de rapportage en probleemoplossing.

**Naam van eigenschap: IncludedIdList**

2. Beschrijving: De groep(en) waar het beleid op wordt toegepast. Als er meerdere groepen worden toegevoegd, wordt het beleid toegepast op alle media in al deze groepen.

3. Opties: De groeps-id/GUID moet in dit exemplaar worden gebruikt.

In het volgende voorbeeld ziet u het gebruik van GroupID:

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

**Eigenschapsnaam: ExcludedIDList**

Beschrijving: De groep(en) waar het beleid niet op wordt toegepast.

Opties: De groeps-id/GUID moet in dit exemplaar worden gebruikt.

**Naam van eigenschap: invoer-id**

1. Beschrijving: Eén beleidsregel kan meerdere vermeldingen bevatten; Elke vermelding met een unieke GUID geeft apparaatbeheer één beperking aan.

**Eigenschapsnaam: Type**

1. Beschrijving: Definieert de actie voor de verwisselbare opslaggroepen in IncludedIDList.
    - Afdwinging: Toestaan of weigeren
    - Audit: AuditAllowed or AuditDenied 

2. Opties:

    - Toestaan
    - Weigeren
    - AuditAllowed: Definieert melding en gebeurtenis wanneer toegang is toegestaan
    - AuditDenied: Definieert melding en gebeurtenis wanneer toegang wordt geweigerd; moet samenwerken met **Vermelding weigeren.**

Wanneer er conflicttypen voor dezelfde media zijn, wordt het eerste conflict in het beleid toegepast. Een voorbeeld van een conflicttype is **Toestaan** en **Weigeren.**

**Naam van eigenschap: Sid**

Beschrijving: Hiermee bepaalt u of u dit beleid moet toepassen op specifieke gebruikers of gebruikersgroep; een vermelding kan maximaal één Sid hebben en een vermelding zonder dat sid betekent dat het beleid op de computer wordt toegepast.

**Naam van eigenschap: ComputerSid**

Beschrijving: Hiermee bepaalt u of u dit beleid moet toepassen op een specifieke machine- of machinegroep; één invoer kan maximaal één ComputerSid hebben en een vermelding zonder computerSid betekent dat u het beleid op de computer moet toepassen. Als u een vermelding wilt toepassen op een specifieke gebruiker en specifieke computer, voegt u zowel Sid als ComputerSid toe aan dezelfde vermelding.

**Eigenschapsnaam: Opties**

Beschrijving: Definieert of u een melding wilt weergeven of niet.

   :::image type="content" source="images/device-status.png" alt-text="Het scherm waarop de status van het apparaat kan worden gezien":::

Opties: 0-4. Wanneer Toestaan of Weigeren typen is geselecteerd:

   - 0: niets
   - 4: Schakel **AuditAllowed en** **AuditDenied uit** voor deze vermelding. Zelfs als **Blokkering** wordt uitgevoerd en **de instelling AuditDenied** is geconfigureerd, wordt er geen melding in het systeem uitgevoerd.

   Wanneer Type **AuditAllowed of** **AuditDenied** is geselecteerd:

   - 0: niets
   - 1: melding tonen
   - 2: gebeurtenis verzenden
   - 3: melding tonen en gebeurtenis verzenden

**Naam van eigenschap: AccessMask**

Beschrijving: Definieert de toegang.

Opties 1-7:
  - 1: Lezen
  - 2: Schrijven
  - 3: Lezen en schrijven
  - 4: Uitvoeren
  - 5: Lezen en uitvoeren
  - 6: Schrijven en uitvoeren
  - 7: Lezen en schrijven en uitvoeren

## <a name="common-removable-storage-access-control-scenarios"></a>Veelvoorkomende verwisselbare Storage Access Control-scenario's

Om u vertrouwd te maken met Microsoft Defender voor eindpuntverwisselbaar Storage Access Control, hebben we een aantal veelvoorkomende scenario's voor u opgesteld die u kunt volgen.

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>Scenario 1: Schrijf- en uitvoertoegang tot iedereen voorkomen, maar sta specifieke goedgekeurde USB's toe

1. Groepen aanmaken

    1. Groep 1: Eventuele verwisselbare opslag en cd/dvd. Een voorbeeld van een verwisselbare opslag en cd/dvd is: Groep **9b28fae8-72f7-4267-a1a5-685f747a7146** in het voorbeeld Elk verwisselbaar Storage- en [cd-dvd-Group.xml-bestand.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)
    
    2. Groep 2: Goedgekeurde USB's op basis van apparaateigenschappen. Een voorbeeld van deze use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.

    > [!NOTE]
    > U moet vervangen `&` door `&amp;` in de waarde.

2. Beleid maken

    1. Beleid 1: Schrijf- en uitvoertoegang blokkeren, maar goedgekeurde USB's toestaan. Een voorbeeld van deze use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in het voorbeeld [scenario 1 Blokschrijven](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) en Access uitvoeren, maar goedgekeurd USBs.xml-bestand toestaan.
    
    2. Beleid 2: Controle schrijf- en uitvoertoegang tot toegestane USB's. Een voorbeeld van deze use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in het voorbeeld [van Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a>Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs

1. Groepen aanmaken

    1. Groep 1: Eventuele verwisselbare opslag en cd/dvd. Een voorbeeld van dit gebruiksvoorbeeld is: Groep **9b28fae8-72f7-4267-a1a5-685f747a7146** in het voorbeeld Een verwisselbaar Storage- en [cd-dvd-Group.xml-bestand.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)
    
    2. Groep 2: Niet-goedgekeurde USB's op basis van apparaateigenschappen, bijvoorbeeld Leverancier-id/product-id, vriendelijke naam – Groep **65fa649a-a111-4912-9294-fb6337a25038** in het voorbeeld Van niet-goedgekeurde [USB's Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) bestand. 

    > [!NOTE]
    > U moet vervangen `&` door `&amp;` in de waarde.

2. Beleid maken

    1. Beleid 1: De toegang voor schrijven en uitvoeren blokkeren tot alle niet-goedgekeurde USB's, behalve blokkeren. Een voorbeeld van deze use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in het voorbeeld van Scenario 2 Audit Write and Execute access to all but block specific [unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.
    
    2. Beleid 2: audit schrijf- en uitvoertoegang tot anderen. Een voorbeeld van deze use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in het voorbeeld [van Scenario 2 Audit Write and Execute access to others.xmlfile.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)

## <a name="deploying-and-managing-policy-via-group-policy"></a>Beleid implementeren en beheren via groepsbeleid

Met de functie Storage Access Control kunt u beleid via groepsbeleid toepassen op gebruiker of apparaat of beide.

### <a name="licensing"></a>Licenties

Voordat u aan de slag gaat met Verwisselbaar Storage Access Control, moet u uw Microsoft 365 [bevestigen.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2) Als u verwisselbare Storage access control wilt openen en gebruiken, moet u Microsoft 365 E3 of Microsoft 365 E5.

### <a name="deploying-policy-via-group-policy"></a>Beleid implementeren via groepsbeleid

1. Combineer alle groepen binnen `<Groups>` `</Groups>` in één xml-bestand. 

    In de volgende afbeelding ziet u het voorbeeld van scenario 1: Geen schrijf- en uitvoertoegang tot alle, maar wel specifieke goedgekeurde [USB's toestaan.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Het scherm met de configuratie-instellingen waarmee specifieke goedgekeurde USB's op apparaten worden toegestaan":::
    
2. Combineer alle regels binnen `<PolicyRules>` `</PolicyRules>` in één xml-bestand. 

    Als u een specifieke gebruiker wilt beperken, gebruikt u de eigenschap SID in de vermelding. Als er geen SID in de beleidsinvoer staat, wordt de vermelding toegepast op iedereen die zich voor de computer aanmeldt.
    
    In de volgende afbeelding ziet u het gebruik van de eigenschap SID en een voorbeeld van scenario 1: Geen schrijf- en uitvoertoegang tot alle, maar toestaan dat specifieke goedgekeurde [USB's worden gebruikt.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Het scherm met een code die het gebruik van het eigenschapskenmerk SID aangeeft":::

3. Sla zowel regel- als groep XML-bestanden op de map Netwerk delen op en plaats het mappad voor netwerk delen in de instelling Groepsbeleid: **Computerconfiguratie -> Beheersjablonen -> Windows Onderdelen -> Microsoft Defender Antivirus -> Apparaatbeheer: 'Beleidsgroepen** apparaatbeheer definiëren' en 'Beleidsregels voor apparaatbeheer definiëren' .

    - De doelmachine moet toegang hebben tot het netwerk delen om het beleid te hebben. Wanneer het beleid echter is gelezen, is de netwerkverbinding niet meer vereist, zelfs niet na het opnieuw opstarten van de computer.

    :::image type="content" source="images/device-control.png" alt-text="Het scherm Apparaatbesturingselement":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a>Beleid implementeren en beheren via Intune OMA-URI

Met de functie Verwisselbaar Storage Access Control kunt u beleid via OMA-URI toepassen op een gebruiker of apparaat of beide.

### <a name="licensing"></a>Licenties

Voordat u aan de slag gaat met Verwisselbaar Storage Access Control, moet u uw Microsoft 365 [bevestigen.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2) Als u verwisselbare Storage access control wilt openen en gebruiken, moet u Microsoft 365 E3 of Microsoft 365 E5.

### <a name="permission"></a>Machtiging

Voor beleidsimplementatie in Intune moet het account machtigingen hebben voor het maken, bewerken, bijwerken of verwijderen van apparaatconfiguratieprofielen. U kunt aangepaste rollen maken of een van de ingebouwde rollen met deze machtigingen gebruiken.

- Rol beleids- en profielmanager
- Aangepaste rol met machtigingen maken/bewerken/bijwerken/lezen/verwijderen/rapporten weergeven ingeschakeld voor apparaatconfiguratieprofielen
- Globale beheerder

### <a name="deploying-policy-via-oma-uri"></a>Beleid implementeren via OMA-URI

**Microsoft Endpoint Manager https://endpoint.microsoft.com/) -beheercentrum ( -> Apparaten -> Configuratieprofielen -> Profiel maken -> Platform: Windows 10 en hoger & Profiel: Aangepast**

1. Maak voor elke groep een OMA-URI-regel:
    - OMA-URI: 

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData

      Voor een **verwisselbare opslag- en cd/dvd-groep** in het voorbeeld moet de koppeling bijvoorbeeld zijn:

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData

    - Gegevenstype: tekenreeks (XML-bestand)
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="Het xml-bestand voor het gegevenstype TEKENREEKS":::

2. Maak voor elk beleid ook een OMA-URI:

    - OMA-URI: 

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData

      Voor de regel Blokschrijven en Access uitvoeren, maar goedgekeurde **USB's** toestaan in het voorbeeld, moet de koppeling bijvoorbeeld zijn: 

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.

    - Gegevenstype: tekenreeks (XML-bestand)

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="Weergave van XML-bestand voor het gegevenstype TEKENREEKS":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a>Beleid implementeren en beheren met intune-gebruikersinterface

Deze mogelijkheid (in Microsoft Endpoint Manager-beheercentrum (> Apparaten > Configuratieprofielen > Profiel > Platform maken: Windows 10 en https://endpoint.microsoft.com/) hoger & Profiel: Apparaatbesturingselement) is nog niet beschikbaar. 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>Verwisselbare apparaatbesturingselementen Storage Access Control-gegevens weergeven in Microsoft Defender voor Eindpunt

De Microsoft 365 beveiligingsportal toont verwisselbare opslag die is geblokkeerd door het verwisselbare apparaatbesturingselement Storage Access Control. Als u toegang wilt tot Microsoft 365 beveiliging, moet u het volgende abonnement hebben:

- Microsoft 365 voor E5-rapportage

```kusto
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == &quot;RemovableStoragePolicyTriggered&quot; 
| extend parsed=parse_json(AdditionalFields) 
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)  
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)  
| extend MediaBusType = tostring(parsed.BusType)  
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId) 
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaName = tostring(parsed.MediaName) 
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)  
| extend MediaProductId = tostring(parsed.ProductId)  
| extend MediaVendorId = tostring(parsed.VendorId)  
| extend MediaSerialNumber = tostring(parsed.SerialNumber)  
| extend MediaVolume = tostring(parsed.Volume)  
| project Timestamp, DeviceId, DeviceName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber, MediaVolume 
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="Het scherm met de blokkering van de verwisselbare opslag":::

## <a name="frequently-asked-questions"></a>Veelgestelde vragen
**Wat is de beperking van verwisselbare opslagmedia voor het maximum aantal USB's?**

We hebben één USB-groep gevalideerd met 100.000 media- tot 7 MB groot. Het beleid werkt in zowel Intune als GPO zonder prestatieproblemen.

**Waarom werkt het beleid niet?**

De meest voorkomende reden is dat er geen [vereiste antimalwareclientversie is.](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)

Een andere reden kan zijn dat het XML-bestand niet correct is opgemaakt, bijvoorbeeld door de juiste markeringsopmaak voor het teken '&' in het XML-bestand niet te gebruiken, of dat de teksteditor een byteorderteken (BOM) 0xEF 0xBB 0xBF aan het begin van de bestanden toevoegt, waardoor de XML-parsing niet werkt. Een eenvoudige oplossing is om het voorbeeldbestand [te downloaden](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (selecteer **Raw** en vervolgens **Opslaan als)** en vervolgens bij te werken.

Als er een waarde is en het beleid wordt beheerd via groepsbeleid, controleert u of het clientapparaat toegang heeft tot het XML-pad voor beleid.

**Hoe weet ik welke computer een verouderd antimalware-clientversie in de organisatie gebruikt?**

U kunt volgende query gebruiken om de versie van de antimalwareclient op te halen in Microsoft 365 beveiligingsportal:
```kusto
//check the antimalware client version
DeviceFileEvents
| where FileName == "MsMpEng.exe"
| where FolderPath contains @"C:\ProgramData\Microsoft\Windows Defender\Platform\"
| extend PlatformVersion=tostring(split(FolderPath, "\\", 5))
//| project DeviceName, PlatformVersion // check which machine is using legacy platformVersion
| summarize dcount(DeviceName) by PlatformVersion // check how many machines are using which platformVersion
| order by PlatformVersion desc
```

