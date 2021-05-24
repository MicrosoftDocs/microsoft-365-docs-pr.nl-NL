---
title: Beheren hoe en waar updates Microsoft Defender Antivirus ontvangen
description: Beheer de fallback-volgorde voor hoe Microsoft Defender Antivirus beveiligingsupdates ontvangt.
keywords: updates, beveiligingslijnlijnen, beveiliging, fallback order, ADL, MMPC, UNC, bestandspad, delen, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 52fe64b096b24dfc52a97fb664e408c5aeb701f4
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624207"
---
# <a name="manage-the-sources-for-microsoft-defender-antivirus-protection-updates"></a>De bronnen beheren voor updates voor de Microsoft Defender Antivirus-beveiliging

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=22154037)

<a id="protection-updates"></a>
<!-- this has been used as anchor in VDI content -->

Het up-to-date houden van uw antivirusbeveiliging is essentieel. Er zijn twee onderdelen voor het beheren van beveiligingsupdates voor Microsoft Defender Antivirus: 
- *Waar* de updates van worden gedownload; en 
- *Wanneer* updates worden gedownload en toegepast. 

In dit artikel wordt beschreven hoe u kunt opgeven waar updates moeten worden gedownload (dit wordt ook wel de terugvalorder genoemd). Zie [Het Microsoft Defender Antivirus updates beheren](manage-updates-baselines-microsoft-defender-antivirus.md) en basislijnen toepassen voor een overzicht van hoe updates werken en hoe u andere aspecten van updates configureert (zoals het plannen van updates).

> [!IMPORTANT]
> Microsoft Defender Antivirus Beveiligingsintelligentie-updates worden geleverd Windows Update en vanaf maandag 21 oktober 2019 zijn alle beveiligingsintelligentie-updates exclusief ondertekend met SHA-2. Uw apparaten moeten worden bijgewerkt ter ondersteuning van SHA-2 om uw beveiligingsinformatie bij te werken. Zie [SHA-2 Code Signing Support 2019 voor Windows en WSUS voor](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)meer informatie.  


<a id="fallback-order"></a>

## <a name="fallback-order"></a>Terugvalorder

Meestal configureert u eindpunten om updates afzonderlijk te downloaden van een primaire bron, gevolgd door andere bronnen in volgorde van prioriteit, op basis van uw netwerkconfiguratie. Updates worden verkregen uit bronnen in de volgorde die u opgeeft. Als een bron niet beschikbaar is, wordt de volgende bron in de lijst onmiddellijk gebruikt.

Wanneer updates worden gepubliceerd, wordt enige logica toegepast om de grootte van de update te minimaliseren. In de meeste gevallen worden alleen de verschillen tussen de meest recente update en de update die momenteel is geïnstalleerd (dit wordt de delta genoemd) op het apparaat gedownload en toegepast. De grootte van de delta is echter afhankelijk van twee belangrijke factoren:
- De leeftijd van de laatste update op het apparaat; en 
- De bron die wordt gebruikt om updates te downloaden en toe te passen. 

Hoe ouder de updates op een eindpunt, hoe groter de download. U moet echter ook rekening houden met de downloadfrequentie. Een vaker bijgewerkte planning kan leiden tot meer netwerkgebruik, terwijl een minder frequent schema kan leiden tot grotere bestandsgrootten per download. 

Er zijn vijf locaties waar u kunt opgeven waar een eindpunt updates moet krijgen: 

- [Microsoft Update](https://support.microsoft.com/help/12373/windows-update-faq)
- [Windows Serverupdateservice](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/core/servers/manage/updates)
- [Netwerkbestands delen](#unc-share)
- [Beveiligingsintelligentie-updates voor Microsoft Defender Antivirus en andere Microsoft-antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates) (Uw beleid en register kunnen dit vermeld hebben als Microsoft Centrum voor beveiliging tegen schadelijke software (MMPC) beveiligingsinformatie, de voormalige naam.)

Om het beste beschermingsniveau te garanderen, zorgt Microsoft Update voor snelle versies, wat betekent dat er regelmatig kleinere downloads worden gedownload. De Windows serverupdateservice, Microsoft Endpoint Configuration Manager en microsoft-beveiligingsinformatieupdates leveren minder frequente updates. De delta kan dus groter zijn, wat resulteert in grotere downloads. 

> [!IMPORTANT]
> Als u [](https://www.microsoft.com/security/portal/definitions/adl.aspx) microsoft beveiligingsinformatiepagina-updates hebt ingesteld als een terugvalbron na Windows Server Update Service of Microsoft Update, worden updates alleen gedownload van beveiligingsinformatie-updates wanneer de huidige update als verouderd wordt beschouwd. (Dit is standaard zeven opeenvolgende dagen dat u geen updates kunt toepassen van de Windows Server Update Service of Microsoft Update-services).
> U kunt echter wel het aantal dagen instellen voordat de beveiliging als verouderd [wordt gerapporteerd.](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)<p>
> Vanaf maandag 21 oktober 2019 zijn beveiligingsintelligentie-updates uitsluitend SHA-2 ondertekend. Apparaten moeten worden bijgewerkt ter ondersteuning van SHA-2 om de meest recente beveiligingsinformatie-updates te krijgen. Zie [SHA-2 Code Signing Support 2019 voor Windows en WSUS voor](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)meer informatie.

Elke bron heeft standaardscenario's die afhankelijk zijn van de configuratie van uw netwerk, naast hoe vaak updates worden gepubliceerd, zoals wordt beschreven in de volgende tabel:

|Locatie | Voorbeeldscenario |
|---|---|
|Windows Serverupdateservice | U gebruikt Windows serverupdateservice om updates voor uw netwerk te beheren.|
|Microsoft Update | U wilt dat uw eindpunten rechtstreeks verbinding maken met Microsoft Update. Dit kan handig zijn voor eindpunten die onregelmatig verbinding maken met uw bedrijfsnetwerk, of als u de serverupdateservice niet gebruikt om uw updates te beheren Windows serverupdateservice.|
|Bestands delen | U hebt apparaten die niet met internet zijn verbonden (zoals VM's). U kunt uw VM-host met internetverbinding gebruiken om de updates naar een netwerk delen te downloaden, waaruit de VM's de updates kunnen verkrijgen. Zie de [VDI-implementatiehandleiding](deployment-vdi-microsoft-defender-antivirus.md) voor de manier waarop bestandsaandelen kunnen worden gebruikt in VDI-omgevingen (Virtual Desktop Infrastructure).|
|Microsoft Endpoint Manager | U gebruikt Microsoft Endpoint Manager om uw eindpunten bij te werken.|
|Beveiligingsinformatieupdates voor Microsoft Defender Antivirus en andere Microsoft-antimalware (voorheen MMPC genoemd) |[Zorg ervoor dat uw apparaten worden bijgewerkt om SHA-2 te ondersteunen.](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus) Microsoft Defender Antivirus Beveiligingsintelligentie-updates worden geleverd Windows Update en vanaf maandag 21 oktober 2019 zijn beveiligingsinformatie-updates sha-2 exclusief ondertekend. <br/>Download de meest recente beveiligingsupdates vanwege een recente infectie of om een sterke basisafbeelding in te stellen voor [VDI-implementatie.](deployment-vdi-microsoft-defender-antivirus.md) Deze optie moet over het algemeen alleen worden gebruikt als een definitieve fallbackbron en niet als primaire bron. Deze wordt alleen gebruikt als updates niet kunnen worden gedownload van Windows Server Update Service of Microsoft Update voor een [bepaald aantal dagen.](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)|

U kunt de volgorde beheren waarin updatebronnen worden gebruikt met groepsbeleid, Microsoft Endpoint Configuration Manager, PowerShell-cmdlets en WMI.

> [!IMPORTANT]
> Als u de Windows serverupdateservice als downloadlocatie in stelt, moet u de updates goedkeuren, ongeacht het beheerprogramma dat u gebruikt om de locatie op te geven. U kunt een automatische goedkeuringsregel instellen Windows serverupdateservice, die handig kan zijn als updates minimaal eenmaal per dag binnenkomen. Zie Updates voor eindpuntbeveiliging [synchroniseren in zelfstandige Windows serverupdateservice voor meer informatie.](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)

In de procedures in dit artikel wordt eerst beschreven hoe  u de volgorde instelt en vervolgens hoe u de optie Bestands delen instelt als u deze hebt ingeschakeld.

## <a name="use-group-policy-to-manage-the-update-location"></a>Groepsbeleid gebruiken om de updatelocatie te beheren

1. Open op uw groepsbeleidsbeheercomputer de [console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

2. Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**

3. Klik **op Beleid** en vervolgens op **Beheersjablonen.**

4. Vouw de structuur uit Windows **onderdelen > Windows Defender > handtekeningupdates** en configureer de volgende instellingen:

   1.  Dubbelklik op de instelling De volgorde van bronnen definiëren voor het downloaden van **beveiligingsinformatieupdates** en stel de optie in op **Ingeschakeld.**

   2.  Voer de volgorde van bronnen in, gescheiden door één pijp, bijvoorbeeld: `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC` , zoals wordt weergegeven in de volgende schermafbeelding.

   ![Schermafbeelding van groepsbeleidsinstelling met de volgorde van bronnen](images/defender/wdav-order-update-sources.png)

   3. Klik op **OK**. Hiermee wordt de volgorde van beveiligingsupdatebronnen ingesteld.

   4. Dubbelklik op de **instelling Bestandsaandelen definiëren voor het downloaden van beveiligingsinformatieupdates** en stel de optie in op **Ingeschakeld.**

   5. Voer de bestandsbestandsbron in. Als u meerdere bronnen hebt, voert u elke bron in in de volgorde waarin deze moet worden gebruikt, gescheiden door één pijp. Gebruik [standaard UNC-notatie om](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) het pad aan te geven, bijvoorbeeld: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name` .  Als u geen paden typt, wordt deze bron overgeslagen wanneer de VM updates downloadt.

   6. Klik op **OK**. Hiermee wordt de volgorde van bestandsaandelen ingesteld wanneer naar die bron wordt verwezen in de groepsbeleidsinstelling De **volgorde van bronnen definiëren...**

> [!NOTE]
> Voor Windows 10, versies 1703 tot en met 1809, is het beleidspad **Windows Onderdelen > Microsoft Defender Antivirus >** Handtekeningupdates Voor Windows 10, versie 1903, is het beleidspad Windows Onderdelen > Microsoft Defender Antivirus > **Beveiligingsinformatieupdates**

## <a name="use-configuration-manager-to-manage-the-update-location"></a>Configuration Manager gebruiken om de updatelocatie te beheren

Zie [Beveiligingsintelligentie-updates configureren Endpoint Protection](/configmgr/protect/deploy-use/endpoint-definition-updates) voor meer informatie over het configureren van Microsoft Endpoint Manager (huidige vertakking).


## <a name="use-powershell-cmdlets-to-manage-the-update-location"></a>PowerShell-cmdlets gebruiken om de updatelocatie te beheren

Gebruik de volgende PowerShell-cmdlets om de updatevolgorde in te stellen.

```PowerShell
Set-MpPreference -SignatureFallbackOrder {LOCATION|LOCATION|LOCATION|LOCATION}
Set-MpPreference -SignatureDefinitionUpdateFileSharesSource {\\UNC SHARE PATH|\\UNC SHARE PATH}
```
Zie de volgende artikelen voor meer informatie:
- [Set-MpPreference -SignatureFallbackOrder](/powershell/module/defender/set-mppreference)
- [Set-MpPreference -SignatureDefinitionUpdateFileSharesSource](/powershell/module/defender/set-mppreference#-signaturedefinitionupdatefilesharessources)
- [PowerShell-cmdlets gebruiken om powershell-cmdlets te configureren en Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Defender-cmdlets](/powershell/module/defender/index)

## <a name="use-windows-management-instruction-wmi-to-manage-the-update-location"></a>Gebruik Windows Management Instruction (WMI) om de updatelocatie te beheren

Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class voor de volgende eigenschappen:

```WMI
SignatureFallbackOrder
SignatureDefinitionUpdateFileSharesSource
```

Zie de volgende artikelen voor meer informatie:
- [Windows Defender WMIv2-API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="use-mobile-device-management-mdm-to-manage-the-update-location"></a>Mobile Device Management (MDM) gebruiken om de updatelocatie te beheren

Zie [Beleid CSP - Defender/SignatureUpdateFallbackOrder](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder) voor meer informatie over het configureren van MDM.

## <a name="what-if-were-using-a-third-party-vendor"></a>Wat gebeurt er als we een externe leverancier gebruiken?

In dit artikel wordt beschreven hoe u updates configureert en beheert voor Microsoft Defender Antivirus. Leveranciers van derden kunnen echter worden gebruikt om deze taken uit te voeren. 

Stel dat Contoso Fabrikam heeft aangenomen om de beveiligingsoplossing te beheren, waaronder Microsoft Defender Antivirus. Fabrikam gebruikt meestal [Windows Management Instrumentation,](./use-wmi-microsoft-defender-antivirus.md) [PowerShell-cmdlets](./use-powershell-cmdlets-microsoft-defender-antivirus.md)of Windows [command-line](./command-line-arguments-microsoft-defender-antivirus.md) om patches en updates te implementeren. 

> [!NOTE]
> Microsoft test geen oplossingen van derden voor het beheren van Microsoft Defender Antivirus.

<a id="unc-share"></a>
## <a name="create-a-unc-share-for-security-intelligence-updates"></a>Een UNC-share maken voor beveiligingsinformatie-updates

Stel een netwerkbestands delen (UNC/mapped station) in om beveiligingsinformatieupdates van de MMPC-site te downloaden met behulp van een geplande taak.

1. Maak in het systeem waarop u het delen wilt inrichten en de updates wilt downloaden, een map waarop u het script wilt opslaan.
    ```DOS
    Start, CMD (Run as admin)
    MD C:\Tool\PS-Scripts\
    ```

2. Maak de map waarop u de handtekeningupdates wilt opslaan.
    ```DOS
    MD C:\Temp\TempSigs\x64
    MD C:\Temp\TempSigs\x86
    ```

3. Download het PowerShell-script van [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4.](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)

4. Klik **op Handmatig downloaden.**

5. Klik **op Het onbewerkte nupkg-bestand downloaden.**

6. Haal het bestand op.

7. Kopieer het bestand SignatureDownloadCustomTask.ps1 naar de map die u eerder hebt gemaakt, C:\Tool\PS-Scripts\ .

8. Gebruik de opdrachtregel om de geplande taak in te stellen.
    > [!NOTE]
    > Er zijn twee soorten updates: volledig en delta.
   - Voor x64 delta:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $true -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - Voor x64 full:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $false -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - Voor x86 delta:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $true -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - Voor x86 full:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $false -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

    > [!NOTE]
    > Wanneer de geplande taken worden gemaakt, vindt u deze in de taakplanning onder Microsoft\Windows\Windows Defender
9. Voer elke taak handmatig uit en controleer of u gegevens (mpam-d.exe, mpam-fe.exe en nis_full.exe) in de volgende mappen hebt (mogelijk hebt u verschillende locaties gekozen):

   - C:\Temp\TempSigs\x86
   - C:\Temp\TempSigs\x64

   Als de geplande taak mislukt, voert u de volgende opdrachten uit:

    ```DOS
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $False -destDir C:\Temp\TempSigs\x64"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $True -destDir C:\Temp\TempSigs\x64"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $False -destDir C:\Temp\TempSigs\x86"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $True -destDir C:\Temp\TempSigs\x86"
    ```
    > [!NOTE]
    > Problemen kunnen ook het gevolg zijn van het uitvoeringsbeleid.
    
10. Een share maken die verwijst naar C:\Temp\TempSigs (bijvoorbeeld \\ server\updates).
    > [!NOTE]
    > Geverifieerde gebruikers moeten minimaal 'Lees'-toegang hebben.
11. Stel de locatie voor delen in het beleid in op het delen.

    > [!NOTE]
    > Voeg de map x64 (of x86) niet toe aan het pad. Het mpcmdrun.exe wordt automatisch toegevoegd.

## <a name="related-articles"></a>Verwante artikelen

- [Implementatie van Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Updates Microsoft Defender Antivirus en basislijnen toepassen](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Updates beheren voor eindpunten die verouderd zijn](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Op basis van gebeurtenissen afgedwongen updates beheren](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Updates voor mobiele apparaten en VM's beheren](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
