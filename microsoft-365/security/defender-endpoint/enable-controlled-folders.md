---
title: Gecontroleerde maptoegang inschakelen
keywords: Gecontroleerde maptoegang, windows 10, Windows Defender, ransomware, beveiligen, bestanden, mappen, inschakelen, inschakelen, gebruiken
description: Informatie over het beveiligen van uw belangrijke bestanden door gecontroleerde maptoegang in te stellen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a35c18d805ef3645659f49b8340cbb4cabab2f8d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165067"
---
# <a name="enable-controlled-folder-access"></a>Gecontroleerde maptoegang inschakelen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[Met gecontroleerde maptoegang](controlled-folders.md) kunt u waardevolle gegevens beschermen tegen schadelijke apps en bedreigingen, zoals ransomware. Gecontroleerde maptoegang is inbegrepen in Windows 10 en Windows Server 2019.

U kunt beheerde maptoegang inschakelen met behulp van een van de volgende methoden:

* [Windows-beveiligingsapp](#windows-security-app)
* [Microsoft Intune](#intune)
* [Mobile Device Management (MDM)](#mobile-device-management-mdm)
* [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
* [Groepsbeleid](#group-policy)
* [PowerShell](#powershell)

[Met de auditmodus](evaluate-controlled-folder-access.md) kunt u testen hoe de functie werkt (en gebeurtenissen controleren) zonder dat dit gevolgen heeft voor het normale gebruik van het apparaat.

Instellingen voor groepsbeleid die het samenvoegen van de lokale beheerderslijst uitschakelen, overschrijven de instellingen voor beheerde maptoegang. Ze overschrijven ook beveiligde mappen en toegestane apps die door de lokale beheerder zijn ingesteld via beheerde maptoegang. Deze beleidsregels omvatten:

* Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**
* System Center Endpoint Protection **Allow users to add exclusions and overrides**

Zie Voorkomen of toestaan dat gebruikers lokaal microsoft Defender AV-beleidsinstellingen wijzigen voor meer informatie over het uitschakelen van het samenvoegen van lokale [lijst.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged)

## <a name="windows-security-app"></a>Windows-beveiligingsapp

1. Open de Windows Security-app door het schildpictogram op de taakbalk te selecteren. U kunt ook zoeken in het startmenu voor **Defender.**

2. Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk) en selecteer **vervolgens Ransomware-beveiliging.**

3. Stel de schakelknop voor **gecontroleerde maptoegang in** op **Aan.**

> [!NOTE]
> Als beheerde maptoegang is geconfigureerd met groepsbeleid, PowerShell- of MDM-CSP's, wordt de status gewijzigd in de Windows Security-app na een herstart van het apparaat.
> Als de functie is ingesteld op **auditmodus** met een van deze hulpprogramma's, wordt in de Windows-beveiligings-app de status **Uit gebruikt.**
> Als u gebruikersprofielgegevens beschermt, wordt u aangeraden het gebruikersprofiel op het standaardstation voor Windows-installatie te plaatsen.

## <a name="intune"></a>Intune

1. Meld u aan bij [de Azure-portal](https://portal.azure.com) en open Intune.

2. Ga naar **Apparaatconfiguratieprofielen**  >    >  **Profiel maken.**

3. Noem het profiel een naam, kies **Windows 10 en hoger** en **Endpoint-beveiliging.** <br/> ![Eindpuntbeveiligingsprofiel maken](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile) <br/>

4. Ga naar **Configure**  >  **Windows Defender Exploit Guard Controlled folder**  >  **access**  >  **Enable**.

5. Typ het pad naar elke toepassing die toegang heeft tot beveiligde mappen en het pad naar een andere map die bescherming nodig heeft. Kies **Toevoegen**.<br/> ![Gecontroleerde maptoegang inschakelen in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)<br/>

   > [!NOTE]
   > Wilcard wordt ondersteund voor toepassingen, maar niet voor mappen. Submappen zijn niet beveiligd. Toegestane apps blijven gebeurtenissen activeren totdat ze opnieuw worden gestart.

6. Selecteer **OK om** elk geopend blad op te slaan en Te **maken.**

7. Selecteer de **profieltoewijzingen, wijs** **alle gebruikers & alle apparaten** en Opslaan **aan.**

## <a name="mobile-device-management-mdm"></a>Mobile Device Management (MDM)

Gebruik [de configuratieserviceprovider ./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) (CSP) om apps in staat te stellen om wijzigingen aan te brengen in beveiligde mappen.

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. Ga in Microsoft Endpoint Configuration Manager naar **Assets and Compliance**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard**.

2. Selecteer **Home**  >  **Create Exploit Guard Policy**.

3. Voer een naam en een beschrijving in, selecteer **Gecontroleerde maptoegang** en selecteer **Volgende.**

4. Kies of u wijzigingen blokkeert of controleert, andere apps toestaat of andere mappen toevoegt en selecteer **Volgende.**
   > [!NOTE]
   > Wilcard wordt ondersteund voor toepassingen, maar niet voor mappen. Submappen zijn niet beveiligd. Toegestane apps blijven gebeurtenissen activeren totdat ze opnieuw worden gestart.

5. Controleer de instellingen en selecteer **Volgende om** het beleid te maken.

6. Nadat het beleid is gemaakt, **sluit u**.

## <a name="group-policy"></a>Groepsbeleid

1. Open op uw apparaat voor [](https://technet.microsoft.com/library/cc731212.aspx)groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.**

2. Ga in **de Groepsbeleidseditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen.**

3. Vouw de structuur uit naar **Windows-onderdelen > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Gecontroleerde maptoegang.**

4. Dubbelklik op de instelling **Beheerde maptoegang configureren** en stel de optie in op **Ingeschakeld.** In de sectie Opties moet u een van de volgende opties opgeven:
    * **Inschakelen:** schadelijke en verdachte apps mogen geen wijzigingen aanbrengen in bestanden in beveiligde mappen. Er wordt een melding gegeven in het Windows-gebeurtenislogboek.
    * **Uitschakelen (standaard)** - De functie Voor gecontroleerde maptoegang werkt niet. Alle apps kunnen wijzigingen aanbrengen in bestanden in beveiligde mappen.
    * **Controlemodus:** wijzigingen zijn toegestaan als een schadelijke of verdachte app probeert een wijziging aan te brengen in een bestand in een beveiligde map. Het wordt echter opgenomen in het Windows-gebeurtenislogboek, waar u de impact op uw organisatie kunt beoordelen.
    * **Alleen schijfwijzigingen blokkeren:** pogingen van niet-vertrouwde apps om naar schijfsectoren te schrijven, worden geregistreerd in het Windows-gebeurtenislogboek. Deze logboeken zijn te vinden in toepassingen en **serviceslogboeken** > Microsoft > Windows > Windows Defender > Operational > ID 1123.
    * **Alleen controleschijfwijzigingen:** alleen pogingen om te schrijven naar beveiligde schijfsectoren worden opgenomen in het Windows-gebeurtenislogboek (onder Toepassingen en **serviceslogboeken**  >  **Microsoft**  >  **Windows Windows**  >  **Defender**  >  **Operational**  >  **ID 1124).** Pogingen om bestanden in beveiligde mappen te wijzigen of te verwijderen, worden niet opgenomen.

      ![Schermafbeelding van de groepsbeleidsoptie Ingeschakeld en Auditmodus geselecteerd in de vervolgkeuzekeuze](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> Als u gecontroleerde maptoegang volledig wilt inschakelen, moet u de optie Groepsbeleid instellen op Ingeschakeld en Blokkeren **selecteren** in de vervolgkeuzelijst Opties. 

## <a name="powershell"></a>PowerShell

1. Typ **powershell** in het menu Start, klik met de rechtermuisknop op **Windows PowerShell** en selecteer **Uitvoeren als beheerder.**

2. Voer de volgende cmdlet in:

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

U kunt de functie in de auditmodus inschakelen door in plaats van `AuditMode` `Enabled` .

Gebruik `Disabled` deze functie om de functie uit te schakelen.

## <a name="see-also"></a>Zie ook

* [Belangrijke mappen beveiligen met gecontroleerde maptoegang](controlled-folders.md)
* [Beheerde maptoegang aanpassen](customize-controlled-folders.md)
* [Microsoft Defender voor eindpunt evalueren](evaluate-atp.md)
