---
title: Het Microsoft Defender voor Eindpunt instellen voor macOS-beleid in Jamf Pro
description: Meer informatie over het instellen van het Microsoft Defender voor eindpunt voor macOS-beleid in Jamf Pro
keywords: beleid, microsoft, defender, Microsoft Defender voor Eindpunt, Mac, installatie, implementatie, verwijdering, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 577eea6e678b6a5d60e5bb8f2fbaaae25d239577
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230065"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a>Het Microsoft Defender voor Eindpunt instellen voor macOS-beleid in Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Defender voor Eindpunt op Mac](microsoft-defender-endpoint-mac.md)

Deze pagina begeleidt u bij de stappen die u moet ondernemen om macOS-beleid in te stellen in Pro.

U moet de volgende stappen ondernemen:

1. [Het Onboarding-pakket voor Microsoft Defender voor eindpunten kopen](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [Een configuratieprofiel maken in Jamf Pro met behulp van het onboarding-pakket](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [Microsoft Defender configureren voor eindpuntinstellingen](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [Instellingen voor meldingen van Microsoft Defender voor eindpunt configureren](#step-4-configure-notifications-settings)

5. [Microsoft AutoUpdate configureren (MAU)](#step-5-configure-microsoft-autoupdate-mau)

6. [Volledige schijftoegang verlenen aan Microsoft Defender voor Eindpunt](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [Kernel-extensie goedkeuren voor Microsoft Defender voor Eindpunt](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [Systeemextensies goedkeuren voor Microsoft Defender voor Eindpunt](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [Netwerkextensie configureren](#step-9-configure-network-extension)

10. [Scans plannen met Microsoft Defender voor Eindpunt op macOS](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [Microsoft Defender voor eindpunt implementeren in macOS](#step-11-deploy-microsoft-defender-for-endpoint-on-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a>Stap 1: Het Onboarding-pakket voor Microsoft Defender voor eindpunten kopen

1. Ga [Microsoft Defender-beveiligingscentrum](https://securitycenter.microsoft.com)naar Instellingen > **Onboarding.**

2. Selecteer macOS als besturingssysteem en Mobile Device Management /Microsoft Intune als implementatiemethode.

    ![Afbeelding van Microsoft Defender-beveiligingscentrum](images/onboarding-macos.png)

3. Selecteer **Onboarding-pakket downloaden** (WindowsDefenderATPOnboardingPackage.zip).

4. Extract `WindowsDefenderATPOnboardingPackage.zip` .

5. Kopieer het bestand naar de gewenste locatie. Bijvoorbeeld. `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a>Stap 2: Een configuratieprofiel maken in Jamf Pro met behulp van het onboarding-pakket

1. Zoek het bestand `WindowsDefenderATPOnboarding.plist` in de vorige sectie.

   ![Afbeelding van WindowsDefenderATPOnboarding-bestand](images/plist-onboarding-file.png)


2. Selecteer nieuw in het Pro **Jamf.**

    ![Afbeelding van het maken van een nieuw Jamf-Pro dashboard](images/jamf-pro-configure-profile.png)

3. Voer de volgende details in:

   **Algemeen**
   - Naam: MDATP-onboarding voor macOS
   - Beschrijving: MDATP EDR onboarding voor macOS
   - Categorie: Geen
   - Distributiemethode: Automatisch installeren
   - Niveau: Computerniveau

4. Selecteer **in & Aangepaste Instellingen** **configureren.**

    ![Afbeelding van de configureren app en aangepaste instellingen](images/jamfpro-mac-profile.png)

5. Selecteer **Upload Bestand (PLIST-bestand)** en voer in **Voorkeursdomein** de volgende opties in: `com.microsoft.wdav.atp` .

    ![Afbeelding van het uploadbestand van de jamfpro-plist](images/jamfpro-plist-upload.png)

    ![Afbeelding van bestandsbestandsbestand uploaden Lijstbestand](images/jamfpro-plist-file.png)

6. Selecteer **Openen** en selecteer het onboarding-bestand.

    ![Afbeelding van onboarding-bestand](images/jamfpro-plist-file-onboard.png)

7. Selecteer **Upload**.

    ![Afbeelding van het uploaden van een plistbestand](images/jamfpro-upload-plist.png)

8. Selecteer het **tabblad Bereik.**

    ![Afbeelding van het tabblad Bereik](images/jamfpro-scope-tab.png)

9. Selecteer de doelcomputers.

    ![Afbeelding van doelcomputers](images/jamfpro-target-computer.png)

    ![Afbeelding van doelen](images/jamfpro-targets.png)

10. Kies **Opslaan**.

    ![Afbeelding van implementatiedoelcomputers](images/jamfpro-deployment-target.png)

    ![Afbeelding van geselecteerde doelcomputers](images/jamfpro-target-selected.png)

11. Selecteer **Gereed**.

    ![Afbeelding van doelgroepcomputers](images/jamfpro-target-group.png)

    ![Lijst met configuratieprofielen](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a>Stap 3: Microsoft Defender configureren voor eindpuntinstellingen

U kunt JAMF Pro GUI gebruiken om afzonderlijke instellingen van de Microsoft Defender-configuratie te bewerken of de oudere methode gebruiken door een configuratie Plist te maken in een teksteditor en deze te uploaden naar JAMF-Pro.

Houd er rekening mee dat u exact `com.microsoft.wdav` moet gebruiken als het **voorkeursdomein**, Microsoft Defender gebruikt alleen deze naam en om `com.microsoft.wdav.ext` de beheerde instellingen te laden!

(De versie kan in zeldzame gevallen worden gebruikt wanneer u liever gui-methode gebruikt, maar ook een instelling moet configureren die nog niet aan het `com.microsoft.wdav.ext` schema is toegevoegd.)

### <a name="gui-method"></a>GUI-methode

1. Download schema.jsbestand uit [de opslagplaats](https://github.com/microsoft/mdatp-xplat/tree/master/macos/schema) van Defender GitHub opslaan in een lokaal bestand:

    ```bash
    curl -o ~/Documents/schema.json https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/schema/schema.json
    ```

2. Maak een nieuw configuratieprofiel onder Computers -> Configuratieprofielen en voer de volgende details in op het **tabblad** Algemeen:

    ![Nieuw profiel](images/644e0f3af40c29e80ca1443535b2fe32.png)

    - Naam: MDATP MDAV-configuratie-instellingen
    - Beschrijving:\<blank\>
    - Categorie: Geen (standaard)
    - Niveau: Computerniveau (standaard)
    - Distributiemethode: Automatisch installeren (standaard)

3. Schuif omlaag naar het **tabblad & Aangepaste Instellingen,** selecteer Externe  **toepassingen,** klik op Toevoegen en gebruik Aangepast **schema** als bron om te gebruiken voor het voorkeursdomein.

    ![Aangepast schema toevoegen](images/4137189bc3204bb09eed3aabc41afd78.png)

4. Voer `com.microsoft.wdav` het voorkeursdomein in,  klik op **Schema** toevoegen en Upload de schema.jsbestand dat is gedownload in stap 1. Klik op **Opslaan**.

    ![Upload schema](images/a6f9f556037c42fabcfdcb1b697244cf.png)

5. U kunt alle ondersteunde configuratie-instellingen van Microsoft Defender hieronder zien onder **Voorkeursdomeineigenschappen.** Klik **op Eigenschappen toevoegen/verwijderen** om de instellingen te selecteren die u wilt beheren en klik op **Ok** om uw wijzigingen op te slaan. (Instellingen niet-geselecteerd links niet wordt opgenomen in de beheerde configuratie, kan een eindgebruiker deze instellingen configureren op hun machines.)

    ![Beheerde instellingen selecteren](images/817b3b760d11467abe9bdd519513f54f.png)

6. Waarden van de instellingen wijzigen in gewenste waarden. U kunt op **Meer informatie klikken** om documentatie voor een bepaalde instelling op te halen. (U kunt op **Plist-voorbeeld klikken** om te controleren hoe de configuratie-plist eruit zal zien. Klik **op Formuliereditor** om terug te keren naar de visuele editor.)

    ![Instellingenwaarden wijzigen](images/a14a79efd5c041bb8974cb5b12b3a9b6.png)

7. Selecteer het **tabblad Bereik.**

    ![Configuratieprofielbereik](images/9fc17529e5577eefd773c658ec576a7d.png)

8. Selecteer **De machinegroep van Contoso.**

9. Selecteer **Toevoegen** en selecteer **opslaan.**

    ![Configuratie-instellingen - toevoegen](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Configuratie-instellingen - opslaan](images/6f093e42856753a3955cab7ee14f12d9.png)

10. Selecteer **Gereed**. U ziet het nieuwe **configuratieprofiel.**

    ![Configuratie-instellingen - klaar](images/dd55405106da0dfc2f50f8d4525b01c8.png)

Microsoft Defender voegt na een tijd nieuwe instellingen toe. Deze nieuwe instellingen worden toegevoegd aan het schema en er wordt een nieuwe versie gepubliceerd naar Github.
U hoeft alleen maar updates te hebben door een bijgewerkt schema te downloaden, een bestaand configuratieprofiel te bewerken en **schema** bewerken op het tabblad & **Aangepaste Instellingen** bewerken.

### <a name="legacy-method"></a>Oudere methode

1. Gebruik de volgende configuratie-instellingen voor Microsoft Defender voor Eindpunt:

    - enableRealTimeProtection
    - passiveMode

    >[!NOTE]
    >Als u van plan bent een AV van derden voor macOS uit te voeren, is deze standaard niet `true` ingeschakeld.

    - uitsluitingen
    - excludedPath
    - uitgeslotenFileExtension
    - uitgeslotenFileName
    - uitsluitingenMergePolicy
    - toegestaanThreats

    >[!NOTE]
    >EICAR is opgenomen in het voorbeeld, als u een proof-of-concept doormaakt, verwijdert u deze vooral als u EICAR test.

    - disallowedThreatActions
    - potentially_unwanted_application
    - archive_bomb
    - cloudService
    - automaticSampleSubmission
    - tags
    - StatusMenuIcon verbergen

     Zie Eigenschappenlijst voor [configuratieprofiel Van Jamf voor meer informatie.](mac-preferences.md#property-list-for-jamf-configuration-profile)

     ```XML
     <?xml version="1.0" encoding="UTF-8"?>
     <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
     <plist version="1.0">
     <dict>
         <key>antivirusEngine</key>
         <dict>
             <key>enableRealTimeProtection</key>
             <true/>
             <key>passiveMode</key>
             <false/>
             <key>exclusions</key>
             <array>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <false/>
                     <key>path</key>
                     <string>/var/log/system.log</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <true/>
                     <key>path</key>
                     <string>/home</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileExtension</string>
                     <key>extension</key>
                     <string>pdf</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileName</string>
                     <key>name</key>
                     <string>cat</string>
                 </dict>
             </array>
             <key>exclusionsMergePolicy</key>
             <string>merge</string>
             <key>allowedThreats</key>
             <array>
                 <string>EICAR-Test-File (not a virus)</string>
             </array>
             <key>disallowedThreatActions</key>
             <array>
                 <string>allow</string>
                 <string>restore</string>
             </array>
             <key>threatTypeSettings</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>potentially_unwanted_application</string>
                     <key>value</key>
                     <string>block</string>
                 </dict>
                 <dict>
                     <key>key</key>
                     <string>archive_bomb</string>
                     <key>value</key>
                     <string>audit</string>
                 </dict>
             </array>
             <key>threatTypeSettingsMergePolicy</key>
             <string>merge</string>
         </dict>
         <key>cloudService</key>
         <dict>
             <key>enabled</key>
             <true/>
             <key>diagnosticLevel</key>
             <string>optional</string>
             <key>automaticSampleSubmission</key>
             <true/>
         </dict>
         <key>edr</key>
         <dict>
             <key>tags</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>GROUP</string>
                     <key>value</key>
                     <string>ExampleTag</string>
                 </dict>
             </array>
         </dict>
         <key>userInterface</key>
         <dict>
             <key>hideStatusMenuIcon</key>
             <false/>
         </dict>
     </dict>
     </plist>
     ```

2. Sla het bestand op als `MDATP_MDAV_configuration_settings.plist` .

3. Open in het dashboard Pro Jamf computers **en** daar **configuratieprofielen.** Klik op **Nieuw(* en ga naar het **tabblad** Algemeen.

    ![Nieuw profiel](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. Voer de volgende details in:

    **Algemeen**

    - Naam: MDATP MDAV-configuratie-instellingen
    - Beschrijving:\<blank\>
    - Categorie: Geen (standaard)
    - Distributiemethode: Automatisch installeren(standaard)
    - Niveau: Computerniveau(standaard)

    ![Afbeelding van MDATP MDAV-configuratie-instellingen](images/3160906404bc5a2edf84d1d015894e3b.png)

5. Selecteer **in & Aangepaste Instellingen** **configureren.**

    ![Afbeelding van app en aangepaste instellingen](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. Selecteer **Upload Bestand (PLIST-bestand)**.

    ![Afbeelding van configuratie-instellingen plistbestand](images/6f85269276b2278eca4bce84f935f87b.png)

7. Typ **in Het domein** Voorkeuren en selecteer Upload `com.microsoft.wdav` **PLIST-bestand.**

    ![Afbeelding van het domein configuratie-instellingenvoorkeuren](images/db15f147dd959e872a044184711d7d46.png)

8. Selecteer **Bestand kiezen.**

    ![Afbeelding van configuratie-instellingen kies bestand](images/526e978761fc571cca06907da7b01fd6.png)

9. Selecteer de **MDATP_MDAV_configuration_settings.plist** en selecteer **Openen.**

    ![Afbeelding van configuratie-instellingen voor mdatpmdav](images/98acea3750113b8dbab334296e833003.png)

10. Selecteer **Upload**.

    ![Afbeelding van het uploaden van configuratie-instellingen](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![Afbeelding van de uploadafbeelding van configuratie-instellingen](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    >Als u het Intune-bestand uploadt, krijgt u de volgende foutmelding:<br>
    >![Afbeelding van configuratie-instellingen intune-bestand uploaden](images/8e69f867664668796a3b2904896f0436.png)


11. Kies **Opslaan**.

    ![Afbeelding van configuratie-instellingen Afbeelding opslaan](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. Het bestand wordt geüpload.

    ![Afbeelding van het bestand met configuratie-instellingen dat is geüpload](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![Afbeelding van het bestand met configuratie-instellingen dat is geüpload](images/a422e57fe8d45689227e784443e51bd1.png)

13. Selecteer het **tabblad Bereik.**

    ![Afbeelding van het bereik van configuratie-instellingen](images/9fc17529e5577eefd773c658ec576a7d.png)

14. Selecteer **De machinegroep van Contoso.**

15. Selecteer **Toevoegen** en selecteer **opslaan.**

    ![Afbeelding van configuratie-instellingen addsav](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Afbeelding van configuratie-instellingen opslaan add](images/6f093e42856753a3955cab7ee14f12d9.png)

16. Selecteer **Gereed**. U ziet het nieuwe **configuratieprofiel.**

    ![Afbeelding van configuratie-instellingen config profielafbeelding](images/dd55405106da0dfc2f50f8d4525b01c8.png)

## <a name="step-4-configure-notifications-settings"></a>Stap 4: Instellingen voor meldingen configureren

Deze stappen zijn van toepassing op macOS 10.15 (Catalina) of hoger.

1. Selecteer in het Pro Dashboard Van Jamf de optie **Computers** en vervolgens **Configuratieprofielen.**

2. Klik **op Nieuw** en voer de volgende details in voor **Opties:**

    - Tabblad **Algemeen**:
        - **Naam**: MDATP MDAV-meldingsinstellingen
        - **Beschrijving**: macOS 10.15 (Catalina) of hoger
        - **Categorie:** Geen *(standaard)*
        - **Distributiemethode:** Automatisch installeren *(standaard)*
        - **Niveau:** Computerniveau *(standaard)*

        ![Afbeelding van het nieuwe macOS-configuratieprofielscherm](images/c9820a5ff84aaf21635c04a23a97ca93.png)

    - **Tabmeldingen,** klik **op Toevoegen** en voer de volgende waarden in:
        - **Bundel-id:**`com.microsoft.wdav.tray`
        - **Kritieke waarschuwingen:** Klik op **Uitschakelen**
        - **Meldingen:** Klik op **Inschakelen**
        - **Type bannerwaarschuwing:** Selecteer **Opnemen** en **Tijdelijk** *(standaard)*
        - **Meldingen op vergrendelingsscherm**: Klik op **Verbergen**
        - **Meldingen in het systeemcentrum:** klik op **Weergeven**
        - **Pictogram badge-app:** klik op **Weergeven**

        ![Afbeelding van configuratie-instellingen mdatpmdav-meldingenvak](images/7f9138053dbcbf928e5182ee7b295ebe.png)

    - **TabMeldingen**, klik nog **een** keer op Toevoegen, schuif omlaag naar **Nieuwe meldingen Instellingen**
        - **Bundel-id:**`com.microsoft.autoupdate2`
        - De rest van de instellingen configureren op dezelfde waarden als hierboven

        ![Afbeelding van configuratie-instellingen mdatpmdav-meldingen mau](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)

        Houd er rekening mee dat u nu twee 'tabellen' met meldingsconfiguraties hebt, een voor **Bundel-id: com.microsoft.wdav.tray** en een voor **Bundel-id: com.microsoft.autoupdate2**. Hoewel u waarschuwingsinstellingen kunt configureren op basis van uw vereisten,  moeten bundel-1D's exact hetzelfde zijn als eerder beschreven en moet de schakelknop Opnemen zijn **aan** voor **meldingen.**

3. Selecteer het **tabblad** Bereik en selecteer **vervolgens Toevoegen.**

    ![Afbeelding van het bereik van configuratie-instellingen](images/441aa2ecd36abadcdd8aed03556080b5.png)

4. Selecteer **De machinegroep van Contoso.**

5. Selecteer **Toevoegen** en selecteer **opslaan.**

    ![Afbeelding van configuratie-instellingen contoso machine grp opslaan](images/09a275e321268e5e3ac0c0865d3e2db5.png)

    ![Afbeelding van configuratie-instellingen toevoegen opslaan](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

6. Selecteer **Gereed**. U ziet het nieuwe **configuratieprofiel.**
    ![Afbeelding van configuratie-instelling klaar img](images/633ad26b8bf24ec683c98b2feb884bdf.png)

## <a name="step-5-configure-microsoft-autoupdate-mau"></a>Stap 5: Microsoft AutoUpdate configureren (MAU)

1. Gebruik de volgende configuratie-instellingen voor Microsoft Defender voor Eindpunt:

      ```XML
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
   <plist version="1.0">
   <dict>
    <key>ChannelName</key>
    <string>Current</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
   </dict>
   </plist>
   ```

2. Sla het op als `MDATP_MDAV_MAU_settings.plist` .

3. Selecteer algemeen in Pro **Jamf-dashboard.**

    ![Afbeelding van configuratie-instelling algemene afbeelding](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. Voer de volgende details in:

    **Algemeen**

    - Naam: MDATP MDAV MAU-instellingen
    - Beschrijving: Microsoft AutoUpdate-instellingen voor MDATP voor macOS
    - Categorie: Geen (standaard)
    - Distributiemethode: Automatisch installeren(standaard)
    - Niveau: Computerniveau(standaard)

5. Selecteer **in & Aangepaste Instellingen** **configureren.**

    ![Afbeelding van de configuratie-app en aangepaste instellingen](images/1f72e9c15eaafcabf1504397e99be311.png)

6. Selecteer **Upload Bestand (PLIST-bestand)**.

    ![Afbeelding van configuratie-instelling plist](images/1213872db5833aa8be535da57653219f.png)

7. Selecteer **in Voorkeursdomein:** `com.microsoft.autoupdate2` en selecteer Upload **PLIST-bestand.**

    ![Afbeelding van configuratie-instelling pref-domein](images/1213872db5833aa8be535da57653219f.png)

8. Selecteer **Bestand kiezen.**

    ![Afbeelding van configuratie-instelling kiesbestand](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. Selecteer **MDATP_MDAV_MAU_settings.plist**.

    ![Afbeelding van configuratie-instelling mdatpmdavmau-instellingen](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. Selecteer **Upload**.
    ![Afbeelding van configuratie-instellinglimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)

    ![Afbeelding van configuratie-uplimg](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. Kies **Opslaan**.

    ![Afbeelding van configuratie-instelling saveimg](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. Selecteer het **tabblad Bereik.**

     ![Afbeelding van configuratie-instelling scopetab](images/10ab98358b2d602f3f67618735fa82fb.png)

13. Kies **Toevoegen**.

    ![Afbeelding van configuratie-instelling addimg1](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![Afbeelding van configuratie-instelling addimg2](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![Afbeelding van configuratie-instelling addimg3](images/321ba245f14743c1d5d51c15e99deecc.png)

14. Selecteer **Gereed**.

    ![Afbeelding van configuratie-instelling doneimage](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a>Stap 6: Volledige schijftoegang verlenen aan Microsoft Defender voor eindpunt

1. Selecteer configuratieprofielen in Pro Dashboard **Jamf.**

    ![Afbeelding van configuratie-instelling configprofiel](images/264493cd01e62c7085659d6fdc26dc91.png)

2. Selecteer **+ Nieuw**.

3. Voer de volgende details in:

    **Algemeen**
    - Naam: MDATP MDAV - Volledige schijftoegang verlenen aan EDR en AV
    - Beschrijving: In macOS Catalina of nieuwer, het nieuwe beleid voor privacyvoorkeuren
    - Categorie: Geen
    - Distributiemethode: Automatisch installeren
    - Niveau: Computerniveau


    ![Afbeelding van configuratie-instelling algemeen](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. Selecteer **in Beleidsbesturingselement Privacyvoorkeuren configureren** **de optie Configureren.**

    ![Afbeelding van configuratie-privacybeleid](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. Voer **in Beleidsbeheer privacyvoorkeuren** de volgende details in:

    - Id: `com.microsoft.wdav`
    - Id-type: bundel-id
    - Codevereiste: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`


    ![Afbeelding van configuratie-instelling privacyvoorkeursbeleidsgegevens](images/22cb439de958101c0a12f3038f905b27.png)

6. Selecteer **+ Toevoegen.**

    ![Afbeelding van configuratie-instelling Systeembeleid alle bestanden toevoegen](images/bd93e78b74c2660a0541af4690dd9485.png)

    - Onder App of service: Instellen op **SystemPolicyAllFiles**

    - Onder 'toegang': Instellen op **Toestaan**

7. Selecteer **Opslaan** (niet de optie rechtsonder).

    ![Afbeelding van configuratie-instelling sla afbeeldingen op](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. Klik op `+` het bord naast App Access **om** een nieuw item toe te voegen.

    ![Afbeelding van de configuratie-instelling app-toegang](images/tcc-add-entry.png)

9. Voer de volgende details in:

    - Id: `com.microsoft.wdav.epsext`
    - Id-type: bundel-id
    - Codevereiste: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

10. Selecteer **+ Toevoegen.**

    ![Afbeelding van configuratie-instelling tCC epsext-invoer](images/tcc-epsext-entry.png)

    - Onder App of service: Instellen op **SystemPolicyAllFiles**

    - Onder 'toegang': Instellen op **Toestaan**

11. Selecteer **Opslaan** (niet de optie rechtsonder).

    ![Afbeelding van configuratie-instelling tCC epsext afbeelding2](images/tcc-epsext-entry2.png)

12. Selecteer het **tabblad Bereik.**

    ![Afbeelding van het configuratiebereik](images/2c49b16cd112729b3719724f581e6882.png)

13. Selecteer **+ Toevoegen.**

    ![Afbeelding van configuratie-instellings-addimage](images/57cef926d1b9260fb74a5f460cee887a.png)

14. Selecteer **Computergroepen >** **onder Groepsnaam** > **selecteer Contoso's MachineGroup.**

    ![Afbeelding van configuratie-instelling contoso machinegrp](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. Kies **Toevoegen**.

16. Kies **Opslaan**.

17. Selecteer **Gereed**.

    ![Afbeelding van configuratie-instelling donimg](images/809cef630281b64b8f07f20913b0039b.png)

    ![Afbeelding van configuratie-instelling donimg2](images/6c8b406ee224335a8c65d06953dc756e.png)

U kunt ook [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) downloaden en uploaden naar JAMF-configuratieprofielen, zoals beschreven in Aangepaste configuratieprofielen implementeren met Behulp van [Jamf-Pro| Methode 2: Upload configuratieprofiel naar Jamf](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)Pro.

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a>Stap 7: Kernel-extensie goedkeuren voor Microsoft Defender voor Eindpunt

> [!CAUTION]
> Apple Silicon (M1) apparaten bieden geen ondersteuning voor KEXT. De installatie van een configuratieprofiel met KEXT-beleid mislukt op deze apparaten.

1. Selecteer in **de configuratieprofielen** **+ Nieuw**.

    ![Een schermafbeelding van een bericht op sociale media dat beschrijving automatisch wordt gegenereerd](images/6c8b406ee224335a8c65d06953dc756e.png)

2. Voer de volgende details in:

    **Algemeen**

    - Naam: MDATP MDAV Kernel Extension
    - Beschrijving: MDATP kernel extension (kext)
    - Categorie: Geen
    - Distributiemethode: Automatisch installeren
    - Niveau: Computerniveau

    ![Afbeelding van configuratie-instellingen mdatpmdav-kernel](images/24e290f5fc309932cf41f3a280d22c14.png)

3. Selecteer **configureren goedgekeurde kernelextensies** **configureren.**

    ![Afbeelding van configuratie-instellingen goedgekeurd kernel ext](images/30be88b63abc5e8dde11b73f1b1ade6a.png)


4. Voer **in Goedgekeurde kernelextensies** de volgende details in:

    - Weergavenaam: Microsoft Corp.
    - Team-id: UBF8T346G9

    ![Afbeelding van de uitbreiding configuratie-instellingen appr kernel](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. Selecteer het **tabblad Bereik.**

    ![Afbeelding van het tabblad Configuratie-instellingenbereik img](images/0df36fc308ba569db204ee32db3fb40a.png)

6. Selecteer **+ Toevoegen.**

7. Selecteer **Computergroepen** > **onder Groepsnaam** > selecteer **De machinegroep van Contoso.**

8. Selecteer **+ Toevoegen.**

    ![Afbeelding van configuratie-instellingen om afbeeldingen toe te voegen](images/0dde8a4c41110dbc398c485433a81359.png)

9. Kies **Opslaan**.

    ![Afbeelding van configuratie-instellingen saveimag](images/0add8019b85a453b47fa5c402c72761b.png)

10. Selecteer **Gereed**.

    ![Afbeelding van configuratie-instellingen doneimag](images/1c9bd3f68db20b80193dac18f33c22d0.png)

U kunt ook [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) downloaden en uploaden naar JAMF-configuratieprofielen, zoals beschreven in Aangepaste configuratieprofielen implementeren met Behulp van [Jamf-Pro| Methode 2: Upload configuratieprofiel naar Jamf](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)Pro.

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a>Stap 8: Systeemextensies goedkeuren voor Microsoft Defender voor eindpunt

1. Selecteer in **de configuratieprofielen** **+ Nieuw**.

    ![Een schermafbeelding van een bericht op sociale media dat beschrijving automatisch wordt gegenereerd](images/6c8b406ee224335a8c65d06953dc756e.png)

2. Voer de volgende details in:

    **Algemeen**

    - Naam: MDATP MDAV System Extensions
    - Beschrijving: MDATP-systeemextensies
    - Categorie: Geen
    - Distributiemethode: Automatisch installeren
    - Niveau: Computerniveau

    ![Afbeelding van configuratie-instellingen sysext nieuwe prof](images/sysext-new-profile.png)

3. Selecteer **configureren in Systeemextensies.** 

   ![Afbeelding van configuratie-instellingen sysext config](images/sysext-configure.png)

4. Voer **in Systeemextensies** de volgende details in:

   - Weergavenaam: Microsoft Corp. Systeemextensies
   - Systeemextensietypen: Toegestane systeemextensies
   - Teamaanduiding: UBF8T346G9
   - Toegestane systeemextensies:
     - **com.microsoft.wdav.epsext**
     - **com.microsoft.wdav.netext**

    ![Afbeelding van configuratie-instellingen sysextconfig2](images/sysext-configure2.png)

5. Selecteer het **tabblad Bereik.**

    ![Afbeelding van het bereik van configuratie-instellingen](images/0df36fc308ba569db204ee32db3fb40a.png)

6. Selecteer **+ Toevoegen.**

7. Selecteer **Computergroepen** > **onder Groepsnaam** > selecteer **De machinegroep van Contoso.**

8. Selecteer **+ Toevoegen.**

   ![Afbeelding van addima configuratie-instellingen](images/0dde8a4c41110dbc398c485433a81359.png)

9. Kies **Opslaan**.

   ![Afbeelding van sysext-bereik configuratie-instellingen](images/sysext-scope.png)

10. Selecteer **Gereed**.

    ![Afbeelding van configuratie-instellingen sysext-final](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a>Stap 9: Netwerkextensie configureren

Als onderdeel van de mogelijkheden voor endpointdetectie en -antwoord controleert Microsoft Defender voor Eindpunt op macOS het socketverkeer en rapporteert deze informatie aan de Microsoft Defender-beveiligingscentrum portal. Met het volgende beleid kan de netwerkextensie deze functionaliteit uitvoeren.

Deze stappen zijn van toepassing op macOS 10.15 (Catalina) of hoger.

1. Selecteer in het Pro Dashboard Van Jamf de optie **Computers** en vervolgens **Configuratieprofielen.**

2. Klik **op Nieuw** en voer de volgende details in voor **Opties:**

    - Tabblad **Algemeen**:
        - **Naam**: Microsoft Defender ATP Network Extension
        - **Beschrijving**: macOS 10.15 (Catalina) of hoger
        - **Categorie:** Geen *(standaard)*
        - **Distributiemethode:** Automatisch installeren *(standaard)*
        - **Niveau:** Computerniveau *(standaard)*

    - **Tab-inhoudsfilter:**
        - **Filternaam:** Microsoft Defender ATP-inhoudsfilter
        - **Id**: `com.microsoft.wdav`
        - Serviceadres , **Organisatie**, **Gebruikersnaam**, **Wachtwoord**, **Certificaat** leeg laten (**Opnemen** is *niet* geselecteerd) 
        - **Filterorder**: Inspector
        - **Socket Filter**: `com.microsoft.wdav.netext`
        - **Vereiste socketfilter**: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
        - Velden **voor netwerkfilter** leeg laten (**Opnemen** is *niet* geselecteerd)

        Houd er rekening mee dat **id,** **socketfilter** en **socketfilter de** exacte waarden vereist zijn, zoals hierboven is aangegeven.

        ![Afbeelding van configuratie-instelling mdatpmdav](images/netext-create-profile.png)

3. Selecteer het **tabblad Bereik.**

   ![Afbeelding van het sco-tabblad configuratie-instellingen](images/0df36fc308ba569db204ee32db3fb40a.png)

4. Selecteer **+ Toevoegen.**

5. Selecteer **Computergroepen** > **onder Groepsnaam** > selecteer **De machinegroep van Contoso.**

6. Selecteer **+ Toevoegen.**

    ![Afbeelding van configuratie-instellingen adim](images/0dde8a4c41110dbc398c485433a81359.png)

7. Kies **Opslaan**.

    ![Afbeelding van configuratie-instellingen savimg netextscop](images/netext-scope.png)

8. Selecteer **Gereed**.

    ![Afbeelding van configuratie-instellingen netextfinal](images/netext-final.png)

U kunt ook [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) downloaden en uploaden naar JAMF-configuratieprofielen, zoals beschreven in Aangepaste configuratieprofielen implementeren met Behulp van [Jamf-Pro| Methode 2: Upload configuratieprofiel naar Jamf](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)Pro.


## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>Stap 10: Scans plannen met Microsoft Defender voor Eindpunt op macOS
Volg de instructies over [Scans plannen met Microsoft Defender voor Eindpunt op macOS](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).


## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a>Stap 11: Microsoft Defender voor eindpunt implementeren in macOS

1. Ga naar de plaats waar u hebt `wdav.pkg` opgeslagen.

    ![Afbeelding van verkenner wdav pkg](images/8dde76b5463047423f8637c86b05c29d.png)

2. Wijzig de naam in `wdav_MDM_Contoso_200329.pkg` .

    ![Afbeelding van verkenner1 wdavmdmpkg](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. Open het jamf-Pro dashboard.

    ![Afbeelding van configuratie-instellingen jamfpro](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. Selecteer uw computer en klik op het tandwielpictogram bovenaan en selecteer **vervolgens Computerbeheer.**

    ![Afbeelding van configuratie-instellingen compmgmt](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. Selecteer **in Pakketten**+ **Nieuw.**
    ![Een afbeelding met vogelbeschrijving automatisch gegenereerd pakket nieuw](images/57aa4d21e2ccc65466bf284701d4e961.png)

6. Voer **in Nieuw pakket** de volgende details in:

    **Tabblad Algemeen**
    - Weergavenaam: Laat deze nu leeg. Omdat deze opnieuw wordt ingesteld wanneer u uw pkg kiest.
    - Categorie: Geen (standaard)
    - Bestandsnaam: Bestand kiezen

    ![Afbeelding van het algemene tabblad Configuratie-instellingen](images/21de3658bf58b1b767a17358a3f06341.png)

    Open het bestand en wijs het aan `wdav.pkg` of `wdav_MDM_Contoso_200329.pkg` .

    ![Schermafbeelding van een computerscherm Beschrijving automatisch gegenereerd](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. Selecteer **Openen**. Stel de **weergavenaam in** op **Microsoft Defender Advanced Threat Protection en Microsoft Defender Antivirus.**

    **Manifestbestand** is niet vereist. Microsoft Defender voor Eindpunt werkt zonder Manifestbestand.

    **Tabblad Opties**<br> Standaardwaarden behouden.

    **Tabblad Beperkingen**<br> Standaardwaarden behouden.

     ![Afbeelding van het beperkingstabblad configuratie-instellingen](images/56dac54634d13b2d3948ab50e8d3ef21.png)

8. Kies **Opslaan**. Het pakket wordt geüpload naar Pro.

   ![Afbeelding van configuratie-instellingen pack upl jamf pro](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   Het kan enkele minuten duren voordat het pakket beschikbaar is voor implementatie.

   ![Afbeelding van configuratie-instellingen pack upl](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. Ga naar de **pagina Beleid.**

    ![Afbeelding van configuratie-instellingen polocies](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. Selecteer **+ Nieuw om** een nieuw beleid te maken.

    ![Afbeelding van nieuwe configuratie-instellingen](images/847b70e54ed04787e415f5180414b310.png)


11. Voer **in het** algemeen de volgende details in:

    - Weergavenaam: MDATP Onboarding Contoso 200329 v100.86.92 of hoger

    ![Afbeelding van configuratie-instellingenmdatponboard](images/625ba6d19e8597f05e4907298a454d28.png)

12. Selecteer **Terugkerend inchecken.**

    ![Afbeelding van configuratie-instellingen die opnieuw worden checkin](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)


13. Kies **Opslaan**.

14. Selecteer **Pakketten > Configureren.**

    ![Afbeelding van configuratie-instellingenpakket configureren](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. Selecteer de **knop Toevoegen** naast Microsoft Defender Advanced Threat Protection **en Microsoft Defender Antivirus.**

    ![Afbeelding van configuratie-instellingen die MDATP en MDA toevoegen](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. Kies **Opslaan**.

    ![Afbeelding van configuratie-instellingensavimg](images/9d6e5386e652e00715ff348af72671c6.png)

17. Selecteer het **tabblad Bereik.**

    ![Afbeelding van scptab configuratie-instellingen](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. Selecteer de doelcomputers.

    ![Afbeelding van configuratie-instellingen tgtcomp](images/6eda18a64a660fa149575454e54e7156.png)

    **Bereik**

    Kies **Toevoegen**.

    ![Afbeelding van configuratie-instellingen ad1img](images/1c08d097829863778d562c10c5f92b67.png)

    ![Afbeelding van configuratie-instellingen ad2img](images/216253cbfb6ae738b9f13496b9c799fd.png)

    **SelfService**

    ![Afbeelding van selfservice configuratie-instellingen](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. Selecteer **Gereed**.

    ![Afbeelding van configuratie-instellingen do1img](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![Afbeelding van configuratie-instellingen do2img](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




