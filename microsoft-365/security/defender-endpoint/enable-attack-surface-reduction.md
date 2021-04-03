---
title: Regels voor het verminderen van aanvalsoppervlakken inschakelen
description: Schakel ASR-regels (Attack Surface Reduction) in om uw apparaten te beschermen tegen aanvallen met macro's, scripts en veelgebruikte technieken voor insinjectie.
keywords: Surface Reduction attack, hips, host intrusion prevention system, protection rules, anti-exploit, anti-exploit, exploit, infection prevention, enable, turn on
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.openlocfilehash: 84947057abbd456dee5cbf5d0c6fea37f679d9ad
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570946"
---
# <a name="enable-attack-surface-reduction-rules"></a>Regels voor het verminderen van aanvalsoppervlakken inschakelen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[Asr-regels (Attack Surface Reduction Rules)](attack-surface-reduction.md) helpen voorkomen dat malware vaak misbruik maakt van apparaten en netwerken. U kunt ASR-regels instellen voor apparaten met een van de volgende versies en versies van Windows:
- Windows 10 Pro, [versie 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) of hoger
- Windows 10 Enterprise, [versie 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) of hoger
- Windows Server, [versie 1803 (halfjaarlijks kanaal)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) of hoger
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Elke ASR-regel bevat een van de drie instellingen:

- Niet geconfigureerd: de ASR-regel uitschakelen
- Blokkering: De ASR-regel inschakelen
- Audit: evalueren hoe de ASR-regel van invloed is op uw organisatie als deze is ingeschakeld

Het wordt ten zeerste aanbevolen om ASR-regels te gebruiken met een Windows E5-licentie (of soortgelijke licentie-SKU) om te profiteren van de geavanceerde controle- en rapportagemogelijkheden die beschikbaar zijn in [Microsoft Defender voor](https://docs.microsoft.com/windows/security/threat-protection) Eindpunt (Defender voor Eindpunt). Voor andere licenties, zoals Windows Professional of E3 die geen toegang hebben tot geavanceerde monitoring- en rapportagemogelijkheden, kunt u echter uw eigen hulpprogramma's voor monitoring en rapportage ontwikkelen boven op de gebeurtenissen die op elk eindpunt worden gegenereerd wanneer ASR-regels worden geactiveerd (bijvoorbeeld Gebeurtenis doorsturen).

> [!TIP]
> Zie Windows [10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) voor meer informatie over Windows-licenties en de [handleiding Volumelicenties voor Windows 10.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)

U kunt regels voor het verminderen van de surface van aanvallen inschakelen met behulp van een van deze methoden:

- [Microsoft Intune](#intune)
- [Mobile Device Management (MDM)](#mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [Groepsbeleid](#group-policy)
- [PowerShell](#powershell)

Beheer op ondernemingsniveau, zoals Intune of Microsoft Endpoint Manager, wordt aanbevolen. Ondernemingsbeheer overschrijft alle conflicterende groepsbeleids- of PowerShell-instellingen bij het opstarten.

## <a name="exclude-files-and-folders-from-asr-rules"></a>Bestanden en mappen uitsluiten van ASR-regels

U kunt voorkomen dat bestanden en mappen worden geëvalueerd door de meeste regels voor het verminderen van het oppervlak van de aanval. Dit betekent dat zelfs als een ASR-regel bepaalt dat het bestand of de map schadelijk gedrag bevat, het bestand niet wordt uitgevoerd. Hierdoor kunnen onveilige bestanden mogelijk worden uitgevoerd en uw apparaten kunnen worden geïnfecteerd.

U kunt asr-regels ook uitsluiten van triggering op basis van certificaat- en bestandshashes door opgegeven Defender voor eindpuntbestands- en certificaatindicatoren toe te staan. (Zie [Indicatoren beheren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)

> [!IMPORTANT]
> Het uitsluiten van bestanden of mappen kan de beveiliging die door ASR-regels wordt geboden, aanzienlijk verminderen. Uitgesloten bestanden mogen worden uitgevoerd en er wordt geen rapport of gebeurtenis opgenomen.
> Als asr-regels bestanden detecteren die volgens u niet moeten worden gedetecteerd, moet u eerst de auditmodus gebruiken om de [regel te testen.](evaluate-attack-surface-reduction.md)


U kunt afzonderlijke bestanden of mappen opgeven (met behulp van mappaden of volledig gekwalificeerde resourcenamen), maar u kunt niet opgeven op welke regels de uitsluitingen van toepassing zijn. Een uitsluiting wordt alleen toegepast wanneer de uitgesloten toepassing of service wordt gestart. Als u bijvoorbeeld een uitsluiting toevoegt voor een updateservice die al wordt uitgevoerd, blijft de updateservice gebeurtenissen activeren totdat de service is gestopt en opnieuw wordt gestart.

ASR-regels ondersteunen omgevingsvariabelen en jokertekens. Zie Jokertekens gebruiken in de lijsten met bestandsnaam en mappenpad of uitbreidingsuitsluiting voor informatie over het gebruik [van jokertekens.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)

De volgende procedures voor het inschakelen van ASR-regels bevatten instructies voor het uitsluiten van bestanden en mappen.

## <a name="intune"></a>Intune

1. Selecteer **Apparaatconfiguratieprofielen.**  >   Kies een bestaand eindpuntbeveiligingsprofiel of maak een nieuw profiel. Als u een nieuw profiel wilt maken, **selecteert u Profiel maken** en voert u informatie voor dit profiel in. Selecteer **Voor profieltype** de optie **Eindpuntbeveiliging.** Als u een bestaand profiel hebt gekozen, **selecteert** u Eigenschappen en selecteert u **vervolgens Instellingen**.

2. Selecteer in **het deelvenster Endpoint** protection **de optie Windows Defender Exploit Guard** en selecteer vervolgens Attack Surface **Reduction**. Selecteer de gewenste instelling voor elke ASR-regel.

3. Voer **onder Attack Surface Reduction uitzonderingen** afzonderlijke bestanden en mappen in. U kunt ook Importeren **selecteren om** een CSV-bestand te importeren dat bestanden en mappen bevat om uit te sluiten van ASR-regels. Elke regel in het CSV-bestand moet als volgt worden opgemaakt:

   `C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`

4. Selecteer **OK** in de drie configuratievensters. Selecteer vervolgens **Maken** als u een nieuw eindpuntbeveiligingsbestand maakt of **Opslaan** als u een bestaand bestand bewerkt.

## <a name="mdm"></a>MDM

Gebruik [de configuratieserviceprovider ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) (CSP) om de modus voor elke regel afzonderlijk in te schakelen en in te stellen.

Hieronder volgt een voorbeeld voor verwijzing, met [GUID-waarden voor ASR-regels.](attack-surface-reduction.md#attack-surface-reduction-rules)

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

De waarden voor het inschakelen, uitschakelen of inschakelen in de auditmodus zijn:

- Uitschakelen = 0
- Blokkering (ASR-regel inschakelen) = 1
- Audit = 2

Gebruik [de CSP (Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider) om uitsluitingen toe te voegen.

Voorbeeld:

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> Zorg ervoor dat u OMA-URI-waarden zonder spaties typt.

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. Ga in Microsoft Endpoint Configuration Manager naar **Assets and Compliance**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard**.

2. Selecteer **Home**  >  **Create Exploit Guard Policy**.

3. Voer een naam en een beschrijving in, selecteer **Attack Surface Reduction** en selecteer **Volgende**.

4. Kies welke regels acties blokkeren of controleren en selecteer **Volgende.**

5. Controleer de instellingen en selecteer **Volgende om** het beleid te maken.

6. Nadat het beleid is gemaakt, **sluit u**.

## <a name="group-policy"></a>Groepsbeleid

> [!WARNING]
> Als u uw computers en apparaten beheert met Intune, Configuration Manager of een ander beheerplatform op ondernemingsniveau, overschrijft de beheersoftware eventuele conflicterende instellingen voor groepsbeleid bij het opstarten.

1. Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.** [](https://technet.microsoft.com/library/cc731212.aspx)

2. Ga in **de Groepsbeleidseditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen.**

3. Vouw de boom uit naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Microsoft Defender Exploit  >  **Guard** Attack  >  **surface reduction**.

4. Selecteer **Aanvalsoppervlakbeperkingsregels configureren** en selecteer **Ingeschakeld.** Vervolgens kunt u de afzonderlijke status voor elke regel instellen in de sectie Opties.

   Selecteer **Toon...** en voer de regel-id in de kolom **Waardenaam** en de door u gekozen status in de **kolom** Waarde als volgt in:

   - Uitschakelen = 0
   - Blokkering (ASR-regel inschakelen) = 1
   - Audit = 2

   ![Groepsbeleidsinstelling met een lege regel-id voor de beperking van het oppervlak van de aanval en een waarde van 1](/microsoft-365/security/defender-endpoint/images/asr-rules-gp)

5. Als u bestanden en mappen wilt uitsluiten van ASR-regels, selecteert u de instelling Bestanden en paden uitsluiten van de instelling Surface **Reduction** Attack en stelt u de optie **in op Ingeschakeld.** Selecteer **Weergeven** en voer elk bestand of elke map in de kolom **Waardenaam** in. Voer **0** in de kolom **Waarde** in voor elk item.

> [!WARNING]
> Gebruik geen aanhalingstekens omdat deze niet worden ondersteund voor de kolom **Waardenaam** of **Waarde.**

## <a name="powershell"></a>PowerShell

> [!WARNING]
> Als u uw computers en apparaten beheert met Intune, Configuration Manager of een ander beheerplatform op ondernemingsniveau, overschrijft de beheersoftware eventuele conflicterende PowerShell-instellingen bij het opstarten. Als u wilt dat gebruikers de waarde kunnen definiëren met PowerShell, gebruikt u de optie 'Gebruiker gedefinieerd' voor de regel in het beheerplatform.

1. Typ **powershell** in het menu Start, klik met de rechtermuisknop op **Windows PowerShell** en selecteer **Uitvoeren als beheerder.**

2. Voer de volgende cmdlet in:

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    Als u ASR-regels wilt inschakelen in de auditmodus, gebruikt u de volgende cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    Als u ASR-regels wilt uitschakelen, gebruikt u de volgende cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > U moet de status afzonderlijk opgeven voor elke regel, maar u kunt regels en toestanden combineren in een door komma's gescheiden lijst.
    >
    > In het volgende voorbeeld worden de eerste twee regels ingeschakeld, wordt de derde regel uitgeschakeld en wordt de vierde regel ingeschakeld in de auditmodus:
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    U kunt ook het `Add-MpPreference` werkwoord PowerShell gebruiken om nieuwe regels toe te voegen aan de bestaande lijst.

    > [!WARNING]
    > `Set-MpPreference` wordt altijd de bestaande set regels overschreven. Als u wilt toevoegen aan de bestaande set, moet u deze in plaats daarvan `Add-MpPreference` gebruiken.
    > U kunt een lijst met regels en de huidige status verkrijgen met behulp `Get-MpPreference` van .

3. Als u bestanden en mappen wilt uitsluiten van ASR-regels, gebruikt u de volgende cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    Blijf gebruiken om `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` meer bestanden en mappen toe te voegen aan de lijst.

    > [!IMPORTANT]
    > Gebruik deze app om apps toe te voegen `Add-MpPreference` of toe te voegen aan de lijst. Als u `Set-MpPreference` de cmdlet gebruikt, wordt de bestaande lijst overschreven.

## <a name="related-articles"></a>Verwante artikelen

- [Aanvalsoppervlakken verminderen met regels voor het beperken van de surface van de aanval](attack-surface-reduction.md)

- [De beperking van het oppervlak van de aanval evalueren](evaluate-attack-surface-reduction.md)

- [Veelgestelde vragen over kwetsbaarheid voor aanvallen verminderen](attack-surface-reduction.md)
