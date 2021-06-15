---
title: Beheerde maptoegang inschakelen
keywords: Gecontroleerde maptoegang, windows 10, Windows Defender, ransomware, beveiligen, bestanden, mappen, inschakelen, inschakelen, gebruiken
description: Informatie over het beveiligen van uw belangrijke bestanden door gecontroleerde maptoegang in te stellen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.topic: article
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ed0859e6018d171b48aac83d394eacbd2163c37b
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924681"
---
# <a name="enable-controlled-folder-access"></a>Beheerde maptoegang inschakelen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[Met gecontroleerde maptoegang](controlled-folders.md) kunt u waardevolle gegevens beschermen tegen schadelijke apps en bedreigingen, zoals ransomware. Gecontroleerde maptoegang is opgenomen in Windows 10 en Windows Server 2019.

U kunt beheerde maptoegang inschakelen met behulp van een van de volgende methoden:

* [Windows-beveiliging app](#windows-security-app)
* [Microsoft Endpoint Manager](#endpoint-manager)
* [Mobile Device Management (MDM)](#mobile-device-management-mdm)
* [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
* [Groepsbeleid](#group-policy)
* [PowerShell](#powershell)

[Met de auditmodus](evaluate-controlled-folder-access.md) kunt u testen hoe de functie werkt (en gebeurtenissen controleren) zonder dat dit gevolgen heeft voor het normale gebruik van het apparaat.

Instellingen voor groepsbeleid die het samenvoegen van de lokale beheerderslijst uitschakelen, overschrijven de instellingen voor beheerde maptoegang. Ze overschrijven ook beveiligde mappen en toegestane apps die door de lokale beheerder zijn ingesteld via beheerde maptoegang. Deze beleidsregels omvatten:

* Microsoft Defender Antivirus Gedrag **van lokale beheerders samenvoegen configureren voor lijsten**
* System Center Endpoint Protection Toestaan **dat gebruikers uitsluitingen en overschrijven toevoegen**

Zie Voorkomen of toestaan dat gebruikers lokaal microsoft Defender AV-beleidsinstellingen wijzigen voor meer informatie over het uitschakelen van het samenvoegen van lokale [lijst.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus)

## <a name="windows-security-app"></a>Windows-beveiliging app

1. Open de Windows-beveiliging app door het schildpictogram op de taakbalk te selecteren. U kunt ook zoeken in het startmenu voor **Defender.**

2. Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk) en selecteer **vervolgens Ransomware-beveiliging.**

3. Stel de schakelknop voor **gecontroleerde maptoegang in** op **Aan.**

> [!NOTE]
> Als beheerde maptoegang is geconfigureerd met groepsbeleids-, PowerShell- of MDM-CSP's, wordt de status gewijzigd in de Windows-beveiliging-app na een herstart van het apparaat.
> Als de functie is ingesteld op **auditmodus** met een van deze hulpprogramma's, Windows-beveiliging de app de status **Uit.**
> Als u gebruikersprofielgegevens beschermt, raden we aan dat het gebruikersprofiel zich op het standaardstation Windows installeren.

## <a name="endpoint-manager"></a>Endpoint Manager

1. Meld u aan bij de [Endpoint Manager](https://endpoint.microsoft.com) en open **Endpoint Security**.

2. Ga naar **Attack Surface Reduction**  >  **Policy**.

3. Selecteer **Platform,** kies **Windows 10 en hoger** en selecteer het profiel Attack Surface Reduction **rules**  >  **Create**.

4.  Geef het beleid een naam en voeg een beschrijving toe. Selecteer **Volgende**.

5.  Schuif omlaag naar de onderkant, selecteer **de vervolgkeuzekeuzeknop** Mapbeveiliging inschakelen en kies **Inschakelen.**

6.  Selecteer **Lijst met extra mappen die moeten worden beveiligd** en voeg de mappen toe die moeten worden beveiligd.

7.  Selecteer **Lijst met apps die toegang hebben tot beveiligde** mappen en voeg de apps toe die toegang hebben tot beveiligde mappen.

8.  Selecteer **Bestanden en paden uitsluiten van regels** voor het verlagen van het aanvalsoppervlak en voeg de bestanden en paden toe die moeten worden uitgesloten van de regels voor het verminderen van het aanvalsoppervlak.

9.  Selecteer de **profieltoewijzingen, wijs** alle & **alle** apparaten toe en selecteer **Opslaan.**

10.  Selecteer **Volgende om** elk geopend blad op te slaan en vervolgens **Maken.**

   > [!NOTE]
   > Jokertekens worden ondersteund voor toepassingen, maar niet voor mappen. Submappen zijn niet beveiligd. Toegestane apps blijven gebeurtenissen activeren totdat ze opnieuw worden gestart.

## <a name="mobile-device-management-mdm"></a>Mobile Device Management (MDM)

Gebruik [de configuratieserviceprovider ./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender) (CSP) om apps in staat te stellen om wijzigingen aan te brengen in beveiligde mappen.

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. Ga Microsoft Endpoint Configuration Manager naar Assets **and Compliance**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard**.

2. Selecteer **Home**  >  **Create Exploit Guard Policy**.

3. Voer een naam en een beschrijving in, selecteer **Gecontroleerde maptoegang** en selecteer **Volgende.**

4. Kies of u wijzigingen blokkeert of controleert, andere apps toestaat of andere mappen toevoegt en selecteer **Volgende.**
   > [!NOTE]
   > Wilcard wordt ondersteund voor toepassingen, maar niet voor mappen. Submappen zijn niet beveiligd. Toegestane apps blijven gebeurtenissen activeren totdat ze opnieuw worden gestart.

5. Controleer de instellingen en selecteer **Volgende om** het beleid te maken.

6. Nadat het beleid is gemaakt, **sluit u**.

## <a name="group-policy"></a>Groepsbeleid

1. Open op uw apparaat voor [](https://technet.microsoft.com/library/cc731212.aspx)groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.**

2. Ga in de **Groepsbeleidsbeheereditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen**.

3. Vouw de boom uit Windows **onderdelen > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Gecontroleerde maptoegang.**

4. Dubbelklik op de instelling **Beheerde maptoegang configureren** en stel de optie in op **Ingeschakeld.** In de sectie Opties moet u een van de volgende opties opgeven:
    * **Inschakelen:** schadelijke en verdachte apps mogen geen wijzigingen aanbrengen in bestanden in beveiligde mappen. Er wordt een melding verstrekt in het Windows gebeurtenislogboek.
    * **Uitschakelen (standaard)** - De functie Voor gecontroleerde maptoegang werkt niet. Alle apps kunnen wijzigingen aanbrengen in bestanden in beveiligde mappen.
    * **Controlemodus:** wijzigingen zijn toegestaan als een schadelijke of verdachte app probeert een wijziging aan te brengen in een bestand in een beveiligde map. Het wordt echter opgenomen in het logboek Windows gebeurtenislogboek waarin u de impact op uw organisatie kunt beoordelen.
    * **Alleen schijfwijzigingen blokkeren:** pogingen van niet-vertrouwde apps om naar schijfsectoren te schrijven, worden aangemeld Windows gebeurtenislogboek. Deze logboeken zijn te vinden in **toepassingen en serviceslogboeken** > Microsoft > Windows > Windows Defender > Operational > ID 1123.
    * **Alleen** controleschijfwijzigingen: alleen pogingen om te schrijven naar beveiligde schijfsectoren worden opgenomen in het gebeurtenislogboek van Windows (onder Toepassingen en **serviceslogboeken**  >  **van Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational**  >  **ID 1124).** Pogingen om bestanden in beveiligde mappen te wijzigen of te verwijderen, worden niet opgenomen.

      ![Schermafbeelding van de groepsbeleidsoptie Ingeschakeld en Auditmodus geselecteerd in de vervolgkeuzekeuze](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> Als u gecontroleerde maptoegang volledig wilt inschakelen, moet u de optie Groepsbeleid instellen op Ingeschakeld en Blokkeren **selecteren** in de vervolgkeuzelijst Opties. 

## <a name="powershell"></a>PowerShell

1. Typ **powershell** in het menu Start, klik met **de rechtermuisknop Windows PowerShell** en selecteer Uitvoeren als **beheerder.**

2. Voer de volgende cmdlet in:

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

U kunt de functie in de auditmodus inschakelen door in plaats van `AuditMode` `Enabled` .

Gebruik `Disabled` deze functie om de functie uit te schakelen.

## <a name="see-also"></a>Zie ook

* [Belangrijke mappen beveiligen met gecontroleerde maptoegang](controlled-folders.md)
* [Beheerde maptoegang aanpassen](customize-controlled-folders.md)
* [Microsoft Defender voor Eindpunt evalueren](evaluate-mde.md)
