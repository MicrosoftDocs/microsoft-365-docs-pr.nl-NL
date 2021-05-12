---
title: Beheerde maptoegang aanpassen
description: Voeg andere mappen toe die moeten worden beveiligd door gecontroleerde maptoegang of sta apps toe die wijzigingen in belangrijke bestanden onjuist blokkeren.
keywords: Gecontroleerde maptoegang, windows 10, Windows Defender, ransomware, beveiligen, bestanden, mappen, aanpassen, map toevoegen, app toevoegen, toestaan, uitvoerbaar toevoegen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 05/10/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: e12368b6241a2c79eead66ed77b30b7864af3955
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326531"
---
# <a name="customize-controlled-folder-access"></a>Beheerde maptoegang aanpassen

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Met gecontroleerde maptoegang kunt u waardevolle gegevens beschermen tegen schadelijke apps en bedreigingen, zoals ransomware. Gecontroleerde maptoegang wordt ondersteund op Windows Server 2019 en Windows 10 clients. In dit artikel wordt beschreven hoe u de mogelijkheden voor beheerde maptoegang kunt aanpassen en worden de volgende secties beschreven:

- [Extra mappen beveiligen](#protect-additional-folders)
- [Apps toevoegen die toegang moeten krijgen tot beveiligde mappen](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [Ondertekende uitvoerbare bestanden toestaan om beveiligde mappen te openen](#allow-signed-executable-files-to-access-protected-folders)
- [De melding aanpassen](#customize-the-notification)

> [!IMPORTANT]
> Met gecontroleerde maptoegang worden apps gecontroleerd op activiteiten die als schadelijk worden gedetecteerd. Soms worden legitieme apps geblokkeerd om wijzigingen aan te brengen in uw bestanden. Als gecontroleerde maptoegang van invloed is op de productiviteit van uw organisatie, kunt u overwegen deze functie in de [auditmodus](audit-windows-defender.md) uit te voeren om de impact volledig te beoordelen.

## <a name="protect-additional-folders"></a>Extra mappen beveiligen

Gecontroleerde maptoegang is van toepassing op veel systeemmappen en standaardlocaties, waaronder mappen zoals **Documenten,** **Afbeeldingen** en **Films.** U kunt andere mappen toevoegen die moeten worden beveiligd, maar u kunt de standaardmappen in de standaardlijst niet verwijderen.

Het toevoegen van andere mappen aan gecontroleerde maptoegang kan handig zijn voor gevallen waarin u geen bestanden opgeslagen in de standaardbibliotheken Windows of als u de standaardlocatie van uw bibliotheken hebt gewijzigd.

U kunt ook netwerkaandelen en in kaart gebrachte stations opgeven. Omgevingsvariabelen en jokertekens worden ondersteund. Zie Jokertekens gebruiken in de lijsten met bestandsnaam en mappenpad of uitbreidingsuitsluiting voor informatie over het gebruik [van jokertekens.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

U kunt de Windows-beveiliging, groepsbeleid, PowerShell-cmdlets of configuratieproviders voor mobiel apparaatbeheer gebruiken om beveiligde mappen toe te voegen en te verwijderen.

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a>De app Windows-beveiliging gebruiken om extra mappen te beveiligen

1. Open de Windows-beveiliging app door het schildpictogram op de taakbalk te selecteren of door te zoeken naar *beveiliging* in het menu Start.

2. Selecteer **Virusbeveiliging & en** schuif omlaag naar de sectie **Ransomware-beveiliging.**

3. Selecteer **Beveiliging van ransomware beheren** om het deelvenster **Ransomware-beveiliging te** openen.

4. Selecteer onder **de sectie Gecontroleerde maptoegang** de optie **Beveiligde mappen.**

5. Kies **Ja** in de **prompt Gebruikerstoegangsbesturingselement.** Het **deelvenster Beveiligde mappen** wordt weergegeven.

6. Selecteer **Een beveiligde map toevoegen** en volg de aanwijzingen om mappen toe te voegen.

### <a name="use-group-policy-to-protect-additional-folders"></a>Groepsbeleid gebruiken om extra mappen te beveiligen

1. Open op uw computer voor groepsbeleidsbeheer de [Console groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true). 

2. Klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **bewerken.**

3. Ga in **de Editor voor groepsbeleidsbeheer** naar **Beheersjablonen voor**  >    >  **computerconfiguratiebeleid.**

4. Vouw de structuur uit Windows **onderdelen van**  >  **Microsoft Defender Antivirus**  >  **Windows Defender Beheerde maptoegang** van Exploit  >  Guard. <br/>**OPMERKING**: In oudere versies van Windows ziet u mogelijk Windows Defender Antivirus **in** plaats van **Microsoft Defender Antivirus.**

5. Dubbelklik op **Geconfigureerde beveiligde mappen** en stel de optie in op **Ingeschakeld.** Selecteer **Weergeven** en geef elke map op die u wilt beveiligen.

6. Implementeer het groepsbeleidsobject zoals u gewoonlijk doet.

### <a name="use-powershell-to-protect-additional-folders"></a>PowerShell gebruiken om extra mappen te beveiligen

1. Typ **PowerShell** in het menu Start, klik met **de rechtermuisknop Windows PowerShell** en selecteer Uitvoeren als **beheerder**

2. Typ de volgende PowerShell-cmdlet, vervangen door het pad van de `<the folder to be protected>` map (zoals `"c:\apps\"` ):

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. Herhaal stap 2 voor elke map die u wilt beveiligen. Mappen die zijn beveiligd, zijn zichtbaar in de Windows-beveiliging app.

   :::image type="content" source="images/cfa-allow-folder-ps.png" alt-text="PowerShell-venster met cmdlet weergegeven":::

> [!IMPORTANT]
> Gebruik deze app om apps toe te voegen of toe te voegen `Add-MpPreference` aan de lijst en niet `Set-MpPreference` . Als u `Set-MpPreference` de cmdlet gebruikt, wordt de bestaande lijst overschreven.

### <a name="use-mdm-csps-to-protect-additional-folders"></a>MDM-CSP's gebruiken om extra mappen te beveiligen

Gebruik [de configuratieserviceprovider ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) (CSP) om apps toe te staan om wijzigingen aan te brengen in beveiligde mappen.

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a>Specifieke apps toestaan om wijzigingen aan te brengen in gecontroleerde mappen

U kunt opgeven of bepaalde apps altijd als veilig worden beschouwd en schrijftoegang geven tot bestanden in beveiligde mappen. Het toestaan van apps kan handig zijn als een bepaalde app die u kent en vertrouwt, wordt geblokkeerd door de functie voor toegang tot beheerde mappen.

> [!IMPORTANT]
> Standaard worden Windows apps toegevoegd die worden beschouwd als vriendelijk voor de toegestane lijst. Dergelijke apps die automatisch worden toegevoegd, worden niet opgenomen in de lijst die wordt weergegeven in de Windows-beveiliging app of met de bijbehorende PowerShell-cmdlets. U hoeft de meeste apps niet toe te voegen. Voeg alleen apps toe als ze worden geblokkeerd en u kunt hun betrouwbaarheid controleren.

Wanneer u een app toevoegt, moet u de locatie van de app opgeven. Alleen de app op die locatie heeft toegang tot de beveiligde mappen. Als de app (met dezelfde naam) zich op een andere locatie bevindt, wordt deze niet toegevoegd aan de allowlist en kan deze worden geblokkeerd door gecontroleerde maptoegang.

Een toegestane toepassing of service heeft alleen schrijftoegang tot een gecontroleerde map nadat deze is gestart. Een updateservice blijft bijvoorbeeld gebeurtenissen activeren nadat deze is toegestaan totdat deze is gestopt en opnieuw wordt gestart.

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a>De beveiligings-Windows Defender gebruiken om specifieke apps toe te staan

1. Open de Windows-beveiliging app door te zoeken in het startmenu voor **Beveiliging.**

2. Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk) en selecteer vervolgens **Beveiliging tegen ransomware beheren.**

3. Selecteer onder **de sectie Gecontroleerde maptoegang** de optie **Een app toestaan via Gecontroleerde maptoegang**

4. Selecteer **Een toegestane app toevoegen** en volg de aanwijzingen om apps toe te voegen.

   :::image type="content" source="images/cfa-allow-app.png" alt-text="Knop Toegestane app toevoegen":::

### <a name="use-group-policy-to-allow-specific-apps"></a>Groepsbeleid gebruiken om specifieke apps toe te staan

1. Open op uw apparaat voor [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.**

2. Ga in de **Groepsbeleidsbeheereditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen**.

3. Vouw de structuur uit Windows **onderdelen van**  >  **Microsoft Defender Antivirus**  >  **Windows Defender Beheerde maptoegang** van Exploit  >  Guard.

4. Dubbelklik op de instelling **Toegestane toepassingen configureren** en stel de optie in op **Ingeschakeld.** Selecteer **Elke** app laten zien en invoeren.

### <a name="use-powershell-to-allow-specific-apps"></a>PowerShell gebruiken om specifieke apps toe te staan

1. Typ **PowerShell** in het menu Start, klik met **de rechtermuisknop Windows PowerShell** en selecteer Uitvoeren als **beheerder**
2. Voer de volgende cmdlet in:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    Als u bijvoorbeeld de  uitvoerbaretest.exein de map *C:\apps* wilt toevoegen, is de cmdlet als volgt:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   Blijf gebruiken om `Add-MpPreference -ControlledFolderAccessAllowedApplications` meer apps toe te voegen aan de lijst. Apps die met deze cmdlet zijn toegevoegd, worden weergegeven in de Windows-beveiliging app.

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="PowerShell-cmdlet om een app toe te staan":::

> [!IMPORTANT]
> Gebruik deze app om apps toe te voegen `Add-MpPreference` of toe te voegen aan de lijst. Als u `Set-MpPreference` de cmdlet gebruikt, wordt de bestaande lijst overschreven.

### <a name="use-mdm-csps-to-allow-specific-apps"></a>MDM-CSP's gebruiken om specifieke apps toe te staan

Gebruik [de configuratieserviceprovider ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) (CSP) om apps toe te staan om wijzigingen aan te brengen in beveiligde mappen.

## <a name="allow-signed-executable-files-to-access-protected-folders"></a>Ondertekende uitvoerbare bestanden toestaan om beveiligde mappen te openen

Met Microsoft Defender voor endpoint-certificaat- en bestandsindicatoren kunnen ondertekende uitvoerbare bestanden toegang krijgen tot beveiligde mappen. Zie Indicatoren maken op basis van certificaten voor meer [informatie over de implementatie.](indicator-certificates.md)

> [!Note]
> Dit is niet van toepassing op scripting-engines, waaronder Powershell

## <a name="customize-the-notification"></a>De melding aanpassen

Zie [Waarschuwingsmeldingen](configure-email-notifications.md)configureren in Microsoft Defender voor Eindpunt voor meer informatie over het aanpassen van de melding wanneer een regel wordt geactiveerd en blokkeert.

## <a name="see-also"></a>Zie ook

- [Belangrijke mappen beveiligen met gecontroleerde maptoegang](controlled-folders.md)
- [Beheerde maptoegang inschakelen](enable-controlled-folders.md)
- [Regels voor het verminderen van aanvalsoppervlakken evalueren](evaluate-attack-surface-reduction.md)
