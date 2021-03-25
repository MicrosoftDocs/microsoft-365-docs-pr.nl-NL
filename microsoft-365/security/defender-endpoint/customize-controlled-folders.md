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
ms.date: 03/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 0962913df63e6837664cdb8ff79710d66e66977c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199903"
---
# <a name="customize-controlled-folder-access"></a>Beheerde maptoegang aanpassen

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)


Met gecontroleerde maptoegang kunt u waardevolle gegevens beschermen tegen schadelijke apps en bedreigingen, zoals ransomware. Gecontroleerde maptoegang wordt ondersteund op Windows Server 2019- en Windows 10-clients.

In dit artikel wordt beschreven hoe u de mogelijkheden voor beheerde maptoegang kunt aanpassen en worden de volgende secties beschreven:

- [Extra mappen beveiligen](#protect-additional-folders)
- [Apps toevoegen die toegang moeten krijgen tot beveiligde mappen](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [Ondertekende uitvoerbare bestanden toestaan om beveiligde mappen te openen](#allow-signed-executable-files-to-access-protected-folders)
- [De melding aanpassen](#customize-the-notification)

> [!IMPORTANT]
> Met gecontroleerde maptoegang worden apps gecontroleerd op activiteiten die als schadelijk worden gedetecteerd. Soms worden legitieme apps geblokkeerd om wijzigingen aan te brengen in uw bestanden. Als gecontroleerde maptoegang van invloed is op de productiviteit van uw organisatie, kunt u overwegen deze functie in de [auditmodus](audit-windows-defender.md) uit te voeren om de impact volledig te beoordelen.

## <a name="protect-additional-folders"></a>Extra mappen beveiligen

Gecontroleerde maptoegang is van toepassing op veel systeemmappen en standaardlocaties, waaronder mappen zoals **Documenten,** **Afbeeldingen** en **Films.** U kunt extra mappen toevoegen die moeten worden beveiligd, maar u kunt de standaardmappen in de standaardlijst niet verwijderen.

Het toevoegen van andere mappen aan gecontroleerde maptoegang kan handig zijn voor gevallen waarin u geen bestanden opgeslagen in de standaard Windows-bibliotheken of als u de standaardlocatie van uw bibliotheken hebt gewijzigd.

U kunt ook netwerkaandelen en in kaart gebrachte stations opgeven. Omgevingsvariabelen en jokertekens worden ondersteund. Zie Jokertekens gebruiken in de lijsten met bestandsnaam en mappenpad of uitbreidingsuitsluiting voor informatie over het gebruik [van jokertekens.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)

U kunt de Windows Security-app, groepsbeleid, PowerShell-cmdlets of configuratieproviders voor mobiel apparaatbeheer gebruiken om extra beveiligde mappen toe te voegen en te verwijderen.

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a>De Windows Security-app gebruiken om extra mappen te beveiligen

1. Open de Windows Security-app door het schildpictogram op de taakbalk te selecteren of door in het startmenu naar Beveiliging te **zoeken.**

2. Selecteer **Virusbeveiliging & en** schuif omlaag naar de sectie **Ransomware-beveiliging.**

3. Selecteer **Beveiliging van ransomware beheren** om het deelvenster **Ransomware-beveiliging te** openen.

4. Selecteer onder **de sectie Gecontroleerde maptoegang** de optie **Beveiligde mappen.**

5. Kies **Ja** in de **prompt Gebruikerstoegangsbesturingselement.** Het **deelvenster Beveiligde mappen** wordt weergegeven.

4. Selecteer **Een beveiligde map toevoegen** en volg de aanwijzingen om mappen toe te voegen.

### <a name="use-group-policy-to-protect-additional-folders"></a>Groepsbeleid gebruiken om extra mappen te beveiligen

1. Open op uw groepsbeleidscomputer de console Groepsbeleidsbeheer, [](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **bewerken.**

2. Ga in **de Groepsbeleidseditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen.**

3. Vouw de boom uit naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Windows Defender Exploit Guard  >  **Controlled** map  >  **access**.

4. Dubbelklik op **Geconfigureerde beveiligde mappen** en stel de optie in op **Ingeschakeld.** Selecteer **Weergeven** en voer elke map in.

### <a name="use-powershell-to-protect-additional-folders"></a>PowerShell gebruiken om extra mappen te beveiligen

1. Typ **PowerShell** in het menu Start, klik met de rechtermuisknop op **Windows PowerShell en** selecteer Uitvoeren als **beheerder**

2. Voer de volgende cmdlet in:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. Herhaal stap 2 totdat u alle mappen hebt toegevoegd die u wilt beveiligen. Mappen die worden toegevoegd, zijn zichtbaar in de Windows-beveiligingsapp.

   ![Schermafbeelding van een PowerShell-venster met de cmdlet hierboven ingevoerd](/microsoft-365/security/defender-endpoint/images/cfa-allow-folder-ps)

> [!IMPORTANT]
> Gebruik deze app om apps toe te voegen `Add-MpPreference` of toe te voegen aan de lijst. Als u `Set-MpPreference` de cmdlet gebruikt, wordt de bestaande lijst overschreven.

### <a name="use-mdm-csps-to-protect-additional-folders"></a>MDM-CSP's gebruiken om extra mappen te beveiligen

Gebruik [de configuratieserviceprovider ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) (CSP) om apps toe te staan om wijzigingen aan te brengen in beveiligde mappen.

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a>Specifieke apps toestaan om wijzigingen aan te brengen in gecontroleerde mappen

U kunt opgeven of bepaalde apps altijd als veilig worden beschouwd en schrijftoegang geven tot bestanden in beveiligde mappen. Het toestaan van apps kan handig zijn als een bepaalde app die u kent en vertrouwt, wordt geblokkeerd door de functie voor toegang tot beheerde mappen.

> [!IMPORTANT]
> Standaard worden in Windows apps toegevoegd die als vriendelijk worden beschouwd aan de toegestane lijst. Dergelijke apps die automatisch worden toegevoegd, worden niet opgenomen in de lijst die wordt weergegeven in de Windows Security-app of met de bijbehorende PowerShell-cmdlets. U hoeft de meeste apps niet toe te voegen. Voeg alleen apps toe als ze worden geblokkeerd en u kunt hun betrouwbaarheid controleren.

Wanneer u een app toevoegt, moet u de locatie van de app opgeven. Alleen de app op die locatie heeft toegang tot de beveiligde mappen. Als de app (met dezelfde naam) zich op een andere locatie bevindt, wordt deze niet toegevoegd aan de lijst met toegestane bestanden en kan deze worden geblokkeerd door gecontroleerde maptoegang.

Een toegestane toepassing of service heeft alleen schrijftoegang tot een gecontroleerde map nadat deze is gestart. Een updateservice blijft bijvoorbeeld gebeurtenissen activeren nadat deze is toegestaan totdat deze is gestopt en opnieuw wordt gestart.

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a>De Windows Defender-beveiligingsapp gebruiken om specifieke apps toe te staan

1. Open de Windows Security-app door te zoeken in het startmenu voor **Beveiliging.**

2. Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk) en selecteer vervolgens **Beveiliging tegen ransomware beheren.**

3. Selecteer onder **de sectie Gecontroleerde maptoegang** de optie **Een app toestaan via Gecontroleerde maptoegang**

4. Selecteer **Een toegestane app toevoegen** en volg de aanwijzingen om apps toe te voegen.

   :::image type="content" source="images/cfa-allow-app.png" alt-text="Knop Toegestane app toevoegen":::

### <a name="use-group-policy-to-allow-specific-apps"></a>Groepsbeleid gebruiken om specifieke apps toe te staan

1. Open op uw apparaat voor [](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.**

2. Ga in **de Groepsbeleidseditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen.**

3. Vouw de boom uit naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Windows Defender Exploit Guard  >  **Controlled** map  >  **access**.

4. Dubbelklik op de instelling **Toegestane toepassingen configureren** en stel de optie in op **Ingeschakeld.** Selecteer **Elke** app laten zien en invoeren.

### <a name="use-powershell-to-allow-specific-apps"></a>PowerShell gebruiken om specifieke apps toe te staan

1. Typ **PowerShell** in het menu Start, klik met de rechtermuisknop op **Windows PowerShell en** selecteer Uitvoeren als **beheerder**
2. Voer de volgende cmdlet in:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    Als u bijvoorbeeld de  uitvoerbaretest.exein de map *C:\apps* wilt toevoegen, is de cmdlet als volgt:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   Blijf gebruiken om `Add-MpPreference -ControlledFolderAccessAllowedApplications` meer apps toe te voegen aan de lijst. Apps die met deze cmdlet zijn toegevoegd, worden weergegeven in de Windows Security-app.

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="PowerShell-cmdlet om een app toe te staan":::

> [!IMPORTANT]
> Gebruik deze app om apps toe te voegen `Add-MpPreference` of toe te voegen aan de lijst. Als u `Set-MpPreference` de cmdlet gebruikt, wordt de bestaande lijst overschreven.

### <a name="use-mdm-csps-to-allow-specific-apps"></a>MDM-CSP's gebruiken om specifieke apps toe te staan

Gebruik [de configuratieserviceprovider ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) (CSP) om apps toe te staan om wijzigingen aan te brengen in beveiligde mappen.

## <a name="allow-signed-executable-files-to-access-protected-folders"></a>Ondertekende uitvoerbare bestanden toestaan om beveiligde mappen te openen

Met Microsoft Defender voor endpoint-certificaat- en bestandsindicatoren kunnen ondertekende uitvoerbare bestanden toegang krijgen tot beveiligde mappen. Zie Indicatoren maken op basis van certificaten voor meer [informatie over de implementatie.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)

> [!Note]
> Dit is niet van toepassing op scripting-engines, waaronder Powershell

## <a name="customize-the-notification"></a>De melding aanpassen

Zie [Waarschuwingsmeldingen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications)configureren in Microsoft Defender voor Eindpunt voor meer informatie over het aanpassen van de melding wanneer een regel wordt geactiveerd en blokkeert.

## <a name="see-also"></a>Zie ook

- [Belangrijke mappen beveiligen met gecontroleerde maptoegang](controlled-folders.md)
- [Gecontroleerde maptoegang inschakelen](enable-controlled-folders.md)
- [Regels voor het verlagen van het oppervlak van de aanval evalueren](evaluate-attack-surface-reduction.md)
