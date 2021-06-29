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
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.date: 06/02/2021
ms.openlocfilehash: cb56872be3cef2e094583e59a702707f79355743
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177619"
---
# <a name="enable-attack-surface-reduction-rules"></a>Regels voor het verminderen van aanvalsoppervlakken inschakelen

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[Asr-regels (Attack Surface Reduction Rules)](attack-surface-reduction.md) helpen voorkomen dat malware vaak misbruik maakt van apparaten en netwerken.

## <a name="requirements"></a>Vereisten

Surface Reduction-functies voor aanvallen in Windows versies

U kunt regels voor de beperking van de surface voor aanvallen instellen voor apparaten met een van de volgende versies en versies van Windows:

- Windows 10 Pro, versie [1709](/windows/whats-new/whats-new-windows-10-version-1709) of hoger
- Windows 10 Enterprise, versie [1709](/windows/whats-new/whats-new-windows-10-version-1709) of hoger
- Windows Server, [versie 1803 (halfjaarlijks kanaal)](/windows-server/get-started/whats-new-in-windows-server-1803) of hoger
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

U hebt het volgende nodig om de volledige set regels voor het verlagen van het aanvalsoppervlak te gebruiken:

- Windows Defender Antivirus als primaire AV (realtime beveiliging op)
- [Cloud-Delivery Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) op (voor sommige regels is dat vereist)
- Windows 10 Enterprise E5- of E3-licentie of Microsoft 365 zakelijke licentie

Hoewel voor de beperkingsregels voor aanvallen geen [Windows E5-licentie is vereist,](/windows/deployment/deploy-enterprise-licenses)hebt u met een Windows E5-licentie geavanceerde beheermogelijkheden, zoals monitoring, analyse en werkstromen, beschikbaar in Defender voor Eindpunt, evenals rapportage- en configuratiemogelijkheden in het Microsoft 365-beveiligingscentrum. Deze geavanceerde mogelijkheden zijn niet beschikbaar met een E3-licentie, maar u kunt Gebeurtenisviewer nog steeds gebruiken om gebeurtenissen met de surface reduction-regel te bekijken.

Elke ASR-regel bevat een van de vier instellingen:

- **Niet geconfigureerd:** de ASR-regel uitschakelen
- **Blokkeren:** De ASR-regel inschakelen
- **Controleren:** evalueren hoe de ASR-regel van invloed is op uw organisatie als deze is ingeschakeld
- **Waarschuwen:** Schakel de ASR-regel in, maar laat de eindgebruiker het blok omzeilen

> [!IMPORTANT]
> Momenteel wordt de waarschuwingsmodus niet ondersteund voor drie ASR-regels wanneer u ASR-regels configureert in Microsoft Endpoint Manager (MEM). Zie Gevallen waarin de [waarschuwingsmodus niet wordt ondersteund](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)voor meer informatie.

Het wordt ten zeerste aanbevolen om ASR-regels te gebruiken met een Windows E5-licentie (of soortgelijke licentie-SKU) om te profiteren van de geavanceerde controle- en rapportagemogelijkheden die beschikbaar zijn in [Microsoft Defender](microsoft-defender-endpoint.md) voor Eindpunt (Defender voor Eindpunt). Als u echter een andere licentie hebt, zoals Windows Professional of Windows E3 die geen geavanceerde controle- en rapportagemogelijkheden bevatten, kunt u uw eigen hulpprogramma's voor monitoring en rapportage ontwikkelen boven op de gebeurtenissen die op elk eindpunt worden gegenereerd wanneer ASR-regels worden geactiveerd (bijvoorbeeld Doorsturen van gebeurtenissen).

> [!TIP]
> Zie Licenties Windows licenties voor meer [Windows 10 Windows](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) en ontvang de handleiding [Volumelicenties voor Windows 10.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)

U kunt regels voor het verminderen van de surface van aanvallen inschakelen met behulp van een van deze methoden:

- [Microsoft Intune](#intune)
- [Mobile Device Management (MDM)](#mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [Groepsbeleid](#group-policy)
- [PowerShell](#powershell)

Beheer op ondernemingsniveau, zoals Intune of Microsoft Endpoint Manager wordt aanbevolen. Ondernemingsbeheer overschrijft alle conflicterende groepsbeleids- of PowerShell-instellingen bij het opstarten.

## <a name="exclude-files-and-folders-from-asr-rules"></a>Bestanden en mappen uitsluiten van ASR-regels

U kunt voorkomen dat bestanden en mappen worden geëvalueerd door de meeste regels voor het verminderen van het oppervlak van de aanval. Dit betekent dat zelfs als een ASR-regel bepaalt dat het bestand of de map schadelijk gedrag bevat, het bestand niet wordt uitgevoerd. Hierdoor kunnen onveilige bestanden mogelijk worden uitgevoerd en uw apparaten kunnen worden geïnfecteerd.

U kunt asr-regels ook uitsluiten van triggering op basis van certificaat- en bestandshashes door opgegeven Defender voor eindpuntbestands- en certificaatindicatoren toe te staan. (Zie [Indicatoren beheren](manage-indicators.md).)

> [!IMPORTANT]
> Het uitsluiten van bestanden of mappen kan de beveiliging die door ASR-regels wordt geboden, aanzienlijk verminderen. Uitgesloten bestanden mogen worden uitgevoerd en er wordt geen rapport of gebeurtenis opgenomen.
> Als asr-regels bestanden detecteren die volgens u niet moeten worden gedetecteerd, moet u eerst de auditmodus gebruiken om de [regel te testen.](evaluate-attack-surface-reduction.md)

U kunt afzonderlijke bestanden of mappen opgeven (met behulp van mappaden of volledig gekwalificeerde resourcenamen), maar u kunt niet opgeven op welke regels de uitsluitingen van toepassing zijn. Een uitsluiting wordt alleen toegepast wanneer de uitgesloten toepassing of service wordt gestart. Als u bijvoorbeeld een uitsluiting toevoegt voor een updateservice die al wordt uitgevoerd, blijft de updateservice gebeurtenissen activeren totdat de service is gestopt en opnieuw wordt gestart.

ASR-regels ondersteunen omgevingsvariabelen en jokertekens. Zie Jokertekens gebruiken in de lijsten met bestandsnaam en mappenpad of uitbreidingsuitsluiting voor informatie over het gebruik [van jokertekens.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)

De volgende procedures voor het inschakelen van ASR-regels bevatten instructies voor het uitsluiten van bestanden en mappen.

## <a name="intune"></a>Intune

1. Selecteer **Apparaatconfiguratieprofielen.**  >   Kies een bestaand eindpuntbeveiligingsprofiel of maak een nieuw profiel. Als u een nieuw profiel wilt maken, **selecteert u Profiel maken** en voert u informatie voor dit profiel in. Selecteer **Voor profieltype** de optie **Eindpuntbeveiliging.** Als u een bestaand profiel hebt gekozen, **selecteert** u Eigenschappen en selecteert u **Instellingen.**

2. Selecteer in **het deelvenster Endpoint-beveiliging** **Windows Defender Exploit Guard** en selecteer vervolgens Attack Surface **Reduction.** Selecteer de gewenste instelling voor elke ASR-regel.

3. Voer **onder Attack Surface Reduction uitzonderingen** afzonderlijke bestanden en mappen in. U kunt ook Importeren **selecteren om** een CSV-bestand te importeren dat bestanden en mappen bevat om uit te sluiten van ASR-regels. Elke regel in het CSV-bestand moet als volgt worden opgemaakt:

   `C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`

4. Selecteer **OK** in de drie configuratievensters. Selecteer vervolgens **Maken** als u een nieuw eindpuntbeveiligingsbestand maakt of **Opslaan** als u een bestaand bestand bewerkt.

## <a name="mem"></a>MEM

U kunt de Microsoft Endpoint Manager OMA-URI (MEM) gebruiken om aangepaste ASR-regels te configureren. In de volgende procedure wordt de regel [Misbruik van misbruikte, kwetsbare ondertekende stuurprogramma's voor](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) het voorbeeld geblokkeerd.

1. Open het Microsoft Endpoint Manager (MEM)-beheercentrum. Klik in **het** menu Start op **Apparaten,** selecteer **Configuratieprofiel** en klik vervolgens **op Profiel maken.**

   > [!div class="mx-imgBorder"]
   > ![Profiel maken met MEM](images/mem01-create-profile.png)

2. Selecteer **in Een profiel maken** in de volgende twee vervolgkeuzelijsten de volgende opties:

   - Selecteer **in Platform** de Windows 10 en **hoger**
   - Selecteer **Sjablonen in** **profieltype**

   Selecteer **Aangepast** en klik vervolgens op **Maken.**

   > [!div class="mx-imgBorder"]
   > ![PROFIELKENMERKEN VAN MEM-regels](images/mem02-profile-attributes.png)

3. Het hulpprogramma Aangepaste sjabloon wordt geopend voor stap **1 Basisbeginselen.** Typ **in 1** Basisbeginselen in **Naam** een naam voor uw sjabloon en in **Beschrijving** kunt u een beschrijving typen (optioneel).

   > [!div class="mx-imgBorder"]
   > ![BASISKENMERKEN VAN MEM](images/mem03-1-basics.png)

4. Klik op **Volgende**. Stap **2 Configuratie-instellingen** worden geopend. Klik voor OMA-URI-Instellingen op **Toevoegen.** Er worden nu twee opties weergegeven: **Toevoegen** en **exporteren.**

   > [!div class="mx-imgBorder"]
   > ![INSTELLINGEN VOOR MEM-configuratie](images/mem04-2-configuration-settings.png)

5. Klik **nogmaals op** Toevoegen. De **oma-URI-Instellingen** toevoegen wordt geopend. Ga **als volgt te** werk in Rij toevoegen:

   - Typ **in Naam** een naam voor de regel.
   - Typ **in Beschrijving** een korte beschrijving.
   - Typ **of plak in OMA-URI** de specifieke OMA-URI-koppeling voor de regel die u toevoegt.
   - Selecteer **tekenreeks** in **gegevenstype**.
   - Typ **of** plak in Waarde de GUID-waarde, het teken en de statuswaarde zonder \= spaties _(GUID=StateValue)._ Waar: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}

   > [!div class="mx-imgBorder"]
   > ![MEM OMA URI-configuratie](images/mem05-add-row-oma-uri.png)

6. Klik op **Opslaan**. **Rij sluiten** toevoegen. Klik **in Aangepast** op **Volgende.** In stap **3 Bereiklabels** zijn bereiklabels optioneel. Voer een van de volgende handelingen uit:

   - Klik **op Bereiklabels** selecteren, selecteer de bereiktag (optioneel) en klik vervolgens op **Volgende.**
   - Of klik op **Volgende**

7. Selecteer in stap **4 Toewijzingen** **,** in Opgenomen groepen - voor de groepen die u wilt toepassen op deze regel- een van de volgende opties:

   - **Groepen toevoegen**
   - **Alle gebruikers toevoegen**
   - **Alle apparaten toevoegen**

   > [!div class="mx-imgBorder"]
   > ![MEM-opdrachten](images/mem06-4-assignments.png)

8. Selecteer **in Uitgesloten groepen** alle groepen die u van deze regel wilt uitsluiten en klik vervolgens op **Volgende.**

9. Ga als volgt te werk in stap **5** Toepassingsregels voor de volgende instellingen:

   - Selecteer **in** Regel profiel toewijzen **als** of Profiel niet **toewijzen als**
   - Selecteer **in Eigenschap** de eigenschap waarop u deze regel wilt toepassen
   - Voer **in Waarde** de toepasselijke waarde of het waardebereik in

   > [!div class="mx-imgBorder"]
   > ![Regels voor mem-toepassing](images/mem07-5-applicability-rules.png)

10. Klik op **Volgende**. Controleer in **stap 6 Controleren + maken** de instellingen en informatie die u hebt geselecteerd en ingevoerd en klik vervolgens op **Maken.**

    > [!div class="mx-imgBorder"]
    > ![MEM Controleren en maken](images/mem08-6-review-create.png)

    > [!NOTE]
    > Regels zijn actief en leven binnen enkele minuten.

>[!NOTE]
> Conflictafhandeling:
>
> Als u een apparaat twee verschillende ASR-beleidsregels toewijst, is de manier waarop conflicten worden afgehandeld regels die verschillende staten zijn toegewezen, is er geen conflictbeheer en is het resultaat een fout.
>
> Niet-conflicterende regels leiden niet tot een fout en de regel wordt correct toegepast. Het resultaat is dat de eerste regel wordt toegepast en dat de volgende niet-conflicterende regels worden samengevoegd in het beleid.

## <a name="mdm"></a>MDM

Gebruik [de configuratieserviceprovider ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) (CSP) om de modus voor elke regel afzonderlijk in te schakelen en in te stellen.

Hieronder volgt een voorbeeld voor verwijzing, met [GUID-waarden voor ASR-regels.](attack-surface-reduction.md#attack-surface-reduction-rules)

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

De waarden die u wilt inschakelen (blokkeren), uitschakelen, waarschuwen of inschakelen in de auditmodus zijn:

- 0 : Uitschakelen (de ASR-regel uitschakelen)
- 1 : Blokkeren (asr-regel inschakelen)
- 2 : Controleren (evalueren hoe de ASR-regel van invloed is op uw organisatie als deze is ingeschakeld)
- 6 : Waarschuwen (Schakel de ASR-regel in, maar laat de eindgebruiker het blok omzeilen). De waarschuwingsmodus is nu beschikbaar voor de meeste ASR-regels.

Gebruik [de CSP (Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider) om uitsluitingen toe te voegen.

Voorbeeld:

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> Zorg ervoor dat u OMA-URI-waarden zonder spaties typt.

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. Ga Microsoft Endpoint Configuration Manager naar Assets **and Compliance**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard**.

2. Selecteer **Home**  >  **Create Exploit Guard Policy**.

3. Voer een naam en een beschrijving in, selecteer **Attack Surface Reduction** en selecteer **Volgende**.

4. Kies welke regels acties blokkeren of controleren en selecteer **Volgende.**

5. Controleer de instellingen en selecteer **Volgende om** het beleid te maken.

6. Nadat het beleid is gemaakt, **sluit u**.

## <a name="group-policy"></a>Groepsbeleid

> [!WARNING]
> Als u uw computers en apparaten beheert met Intune, Configuration Manager of een ander beheerplatform op ondernemingsniveau, overschrijft de beheersoftware eventuele conflicterende instellingen voor groepsbeleid bij het opstarten.

1. Open op uw computer voor groepsbeleidsbeheer de [Groepsbeleidsbeheerconsole](https://technet.microsoft.com/library/cc731212.aspx), klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken**.

2. Ga in de **Groepsbeleidsbeheereditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen**.

3. Vouw de structuur uit Windows **onderdelen**  >  **Microsoft Defender Antivirus**  >  **Microsoft Defender Exploit Guard**  >  **Attack surface reduction**.

4. Selecteer **Aanvalsoppervlakbeperkingsregels configureren** en selecteer **Ingeschakeld.** Vervolgens kunt u de afzonderlijke status voor elke regel instellen in de sectie Opties.

   Selecteer **Toon...** en voer de regel-id in de kolom **Waardenaam** en de door u gekozen status in de **kolom** Waarde als volgt in:

   - 0 : Uitschakelen (de ASR-regel uitschakelen)
   - 1 : Blokkeren (asr-regel inschakelen)
   - 2 : Controleren (evalueren hoe de ASR-regel van invloed is op uw organisatie als deze is ingeschakeld)
   - 6 : Waarschuwen (Schakel de ASR-regel in, maar laat de eindgebruiker het blok omzeilen)

   :::image type="content" source="images/asr-rules-gp.png" alt-text="ASR-regels in groepsbeleid":::

5. Als u bestanden en mappen wilt uitsluiten van ASR-regels, selecteert u de instelling Bestanden en paden uitsluiten van de instelling Surface **Reduction** Attack en stelt u de optie **in op Ingeschakeld.** Selecteer **Weergeven** en voer elk bestand of elke map in de kolom **Waardenaam** in. Voer **0** in de kolom **Waarde** in voor elk item.

   > [!WARNING]
   > Gebruik geen aanhalingstekens omdat deze niet worden ondersteund voor de kolom **Waardenaam** of **Waarde.**

## <a name="powershell"></a>PowerShell

> [!WARNING]
> Als u uw computers en apparaten beheert met Intune, Configuration Manager of een ander beheerplatform op ondernemingsniveau, overschrijft de beheersoftware eventuele conflicterende PowerShell-instellingen bij het opstarten. Als u wilt dat gebruikers de waarde kunnen definiëren met PowerShell, gebruikt u de optie 'Gebruiker gedefinieerd' voor de regel in het beheerplatform.

1. Typ **powershell** in de Startmenu, klik met **de rechtermuisknop op Windows PowerShell** en selecteer Uitvoeren als **beheerder.**

2. Typ de volgende cmdlet:

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    Als u ASR-regels wilt inschakelen in de auditmodus, gebruikt u de volgende cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    Als u ASR-regels wilt inschakelen in de waarschuwingsmodus, gebruikt u de volgende cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    Gebruik de volgende cmdlet om misbruik van uitgebuite, kwetsbare ondertekende stuurprogramma's in te stellen:

   ```PowerShell
   Add-MpPreference -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Enabled
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
    > `Set-MpPreference` wordt altijd de bestaande set regels overschreven. Als u wilt toevoegen aan de bestaande set, gebruikt u deze `Add-MpPreference` in plaats daarvan.
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

- [Veelgestelde vragen over het verminderen van kwetsbaarheid voor aanvallen](attack-surface-reduction.md)
