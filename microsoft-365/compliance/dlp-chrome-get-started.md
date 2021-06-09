---
title: Aan de slag met Microsoft compliance-extensie
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Bereid de Microsoft compliance-extensie voor en implementeer deze.
ms.openlocfilehash: 5a2fa5958117d14715292245924dce2ff63b09a0
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843828"
---
# <a name="get-started-with-microsoft-compliance-extension"></a>Aan de slag met de Microsoft compliance-extensie

Gebruik deze procedures om de Compliance-extensie van Microsoft uit te rollen.

## <a name="before-you-begin"></a>Voordat u begint

Als u de Compliance-extensie van Microsoft wilt gebruiken, moet het apparaat onboarded zijn in Endpoint DLP. Bekijk deze artikelen als u nog niet zo vertrouwd bent met DLP of Endpoint DLP

- [Meer informatie over de Copliance-extensie van Microsoft](dlp-chrome-learn-about.md)
- [Meer informatie over preventie van gegevensverlies](dlp-learn-about-dlp.md)
- [Een DLP-beleid maken, testen en afstemmen](create-test-tune-dlp-policy.md)
- [Een DLP-beleid maken vanuit een sjabloon](create-a-dlp-policy-from-a-template.md)
- [Meer informatie over preventie van gegevensverlies van eindpunten](endpoint-dlp-learn-about.md)
- [Aan de slag met preventie van gegevensverlies van eindpunten](endpoint-dlp-getting-started.md)
- [Hulpprogramma’s en methoden voor onboarding voor Windows 10-apparaten](dlp-configure-endpoints.md)
- [Apparaat-proxy en instellingen voor internetverbinding voor Endpoint DLP configureren.](endpoint-dlp-configure-proxy.md)
- [Preventie van gegevensverlies van eindpunten gebruiken](endpoint-dlp-using.md)

### <a name="skusubscriptions-licensing"></a>SKU/abonnementenlicenties

Voordat u aan de slag gaat, moet u uw [abonnement op Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) en eventuele invoegtoepassingen bevestigen. Als u DLP-functionaliteit voor eindpunten wilt openen en gebruiken, moet u een van deze abonnementen of invoegtoepassingen hebben.

- Microsoft 365 E5
- Microsoft 365 A5 (EDU)
- Microsoft 365 E5 Compliance
- Microsoft 365 A5 Compliance
- Microsoft 365 E5 Information Protection en governance
- Microsoft 365 A5 Information Protection en governance

Zie voor gedetailleerde licentie-richtlijnen [Microsoft 365-licentie guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

- Uw organisatie moet een licentie hebben voor Eindpunt-DLP
- Uw apparaten moeten Windows 10 x64 build 1809 of hoger hebben.
- Het apparaat moet de Antimalware-clientversie 4.18.2101.9 of hoger hebben. Controleer uw huidige versie door de **Windows-beveiligingsapp** te openen, selecteer het pictogram **Instellingen** en selecteer vervolgens **Info**.


### <a name="permissions"></a>Machtigingen

Gegevens uit DLP voor eindpunten kunnen worden weergegeven in [Activiteitenverkenner](data-classification-activity-explorer.md). Er zijn zeven rollen die machtigingen verlenen aan Activiteitenverkenner. Het account dat u gebruikt voor het openen van de gegevens, moet lid zijn van een van deze rollen.

- Algemeen beheerder
- Beheerder voor naleving
- Beveiligingsbeheerder
- Gegevensbeheerder voor naleving
- Algemene lezer
- Beveiligingslezer
- Rapportenlezer

### <a name="overall-installation-workflow"></a>Algemene installatiewerkstroom

Het implementeren van de Microsoft compliance-extension is een proces dat uit meerdere fasen bestaat. U kunt ervoor kiezen om op één computer tegelijk te installeren of gebruik Microsoft Endpoint Manager of groepsbeleid voor implementaties binnen de hele organisatie.

1. [Bereid uw apparaten voor](#prepare-your-devices).
2. [Basic Setup Single Machine Selfhost](#basic-setup-single-machine-selfhost)
3. [Implementatie met behulp van Microsoft Endpoint Manager](#deploy-using-microsoft-endpoint-manager)
4. [Implementeren met behulp van groepsbeleid](#deploy-using-group-policy)
5. [De extensie uitproberen](#test-the-extension)
6. [Het dashboard Waarschuwingenbeheer gebruiken om DLP-waarschuwingen in Chrome weer te geven](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)
7. [Chrome DLP-gegevens weergeven in Activiteitenverkenner](#viewing-chrome-dlp-data-in-activity-explorer) 

### <a name="prepare-infrastructure"></a>Infrastructuur voorbereiden

Als u de Microsoft-nalevingsextensie uitrolt naar al uw bewaakte Windows 10-apparaten, moet u Google Chrome verwijderen uit de lijst met niet-verschuldigde apps en niet-verschuldigde browsers. Zie voor meer informatie [Niet-verschuldigde browsers](endpoint-dlp-using.md#unallowed-browsers). Als u de toepassing slechts op enkele apparaten uitrolt, kunt u Chrome op de lijst met niet-verschuldigde browsers of niet-verschuldigde apps laten staan. De Nalevingsextensie van Microsoft slaat de beperkingen over van beide lijsten voor de computers waarop de lijst is geïnstalleerd.  

### <a name="prepare-your-devices"></a>Uw apparaten voorbereiden

1. Gebruik de procedures in deze onderwerpen om uw apparaten in te werken:
    1. [Aan de slag met preventie van gegevensverlies van eindpunten](endpoint-dlp-getting-started.md)
    1. [Hulpprogramma’s en methoden voor onboarding voor Windows 10-apparaten](dlp-configure-endpoints.md)
    1. [Apparaat-proxy en instellingen voor internetverbinding voor Endpoint DLP configureren.](endpoint-dlp-configure-proxy.md)

### <a name="basic-setup-single-machine-selfhost"></a>Basic Setup Single Machine Selfhost

Dit is de aanbevolen methode. 

1. Meld u aan bij de Windows 10-computer waarop u de Microsoft Compliance-extensie wilt installeren en voer dit PowerShell-script als beheerder uit. 

   ```powershell
   Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
   ``` 

2.  Ga naar [Microsoft Compliance-extensie - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).

3.  Installeer de extensie aan de hand van de instructies op de pagina Chrome Web Store.

### <a name="deploy-using-microsoft-endpoint-manager"></a>Implementeren met behulp van Microsoft Endpoint Manager

Gebruik deze instellingsmethode voor implementaties voor de hele organisatie.


##### <a name="enabling-required-registry-key-via-microsoft-endpoint-manager"></a>Vereiste registersleutel inschakelen via Microsoft Endpoint Manager

1.  Maak een PowerShell-script met de volgende inhoud:

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2.  Meld u aan bij het [beheercentrum voor Microsoft Eindpuntbeheer](https://endpoint.microsoft.com).

3.  Ga naar **Apparaten** > **Scripts** en selecteer **Toevoegen**.

4.  Blader naar de locatie van het script dat is gemaakt wanneer hier om wordt gevraagd.

5.  Selecteer de volgende instellingen:
    1. Voer dit script uit met de aanmeldingsreferenties: JA
    1. Controle van scripthandtekening afdwingen: NEE
    1. Voer het script uit in de 64-bits PowerShell-host: JA

6.  Selecteer de juiste apparaatgroepen en pas het beleid toe.

#### <a name="microsoft-endpoint-manager-force-install-steps"></a>Installatiestappen voor Microsoft Endpoint Manager Force

Voordat u de Microsoft Compliance-extensie toevoegt aan de lijst met geforceer geïnstalleerde extensies, is het belangrijk om de Chrome ADMX op te nemen. Stappen voor dit proces in Microsoft Eindpuntbeheer worden beschreven door Google: [Chrome-browser beheren met Microsoft Intune - Help voor Google Chrome Enterprise](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).

 Nadat u het ADMX-account hebt gebruikt, kunt u de onderstaande stappen volgen om een configuratieprofiel voor deze extensie te maken.

1.  Meld u aan bij het Beheercentrum van Microsoft Endpoint Manager (https://endpoint.microsoft.com).

2.  Ga naar Configuratieprofielen.

3.  Selecteer **Profiel maken**.

4.  Selecteer **Windows 10** als platform.

5.  Selecteer **Aangepast** als profieltype.

6.  Selecteer het tabblad **Instellingen**.

7.  Kies **Toevoegen**.

8.  Geef de volgende gegevens op.
    
    OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`<br/>
    Gegevenstype: `String`<br/>
    Waarde: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`

9.  Klik op maken.

### <a name="deploy-using-group-policy"></a>Implementeren met behulp van groepsbeleid

Als u Microsoft Endpoint Manager niet wilt gebruiken, kunt u groepsbeleid gebruiken om de Microsoft-nalevingsextensie in uw organisatie te implementeren

1. Uw apparaten moeten kunnen worden beheerbaar via groepsbeleid en u moet alle Chrome ADMX's importeren in de centrale opslag voor groepsbeleid. Zie voor meer informatie [het Centraal beheerbeleid in Windows](/troubleshoot/windows-client/group-policy/create-and-manage-central-store).

2.  Maak een PowerShell-script met deze PowerShell-opdracht:

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

3.  Open de **console voor groepsbeleidsbeheer** naar uw organisatie-eenheid (OU).

4.  Klik met de rechtermuisknop en selecteer **GPO in dit domein maken en koppel deze hier**. Wanneer hier om wordt gevraagd, wijst u een beschrijvende naam toe aan dit groepsbeleidsobject en maakt u het maken van het object af.

5.  Klik met de rechtermuisknop op de GPO en selecteer **Bewerken**.

6.  Ga naar **Configuratie van computer** > **Voorkeuren** > **Instellingen van het Configuratiescherm** > **Geplande taken**.

7.  Maak een nieuwe directe taak door met de rechtermuisknop te klikken en **Nieuwe taak** > **(ten minste Windows 7)**.

8.  Geef een naam en beschrijving op voor de taak.

9.  Kies het bijbehorende account om de directe taak uit te voeren, bijvoorbeeld NT Authority

10. Selecteer **Uitvoeren met de hoogste bevoegdheden**.

11. Configureer het beleid voor Windows 10.

12. Selecteer op het tabblad **Acties** de actie **Een programma starten**.

13. Voer het pad in naar het programma/script dat is gemaakt in stap 1.

14. Selecteer **Toepassen**.

#### <a name="adding-the-chrome-extension-to-the-forceinstall-list"></a>De Chrome-extensie toevoegen aan de lijst Geforceerd installeren

1.  Ga in de groepsbeleidsbeheereditor naar uw OU.

2.  Vouw het volgende pad uit: **Configuratie van computer/gebruiker** > **Beleid** > **Beheersjablonen** > **Klassieke beheersjablonen** > **Google** > **Google Chrome** > **Extensies**. Dit pad kan variëren, afhankelijk van uw configuratie.

3.  Selecteer **De lijst met geforceerde geïnstalleerde extensies**.

4.  Klik met de rechtermuisknop en **Bewerken**.

5.  Selecteer **Ingeschakeld**.

6.  Selecteer **Weergeven**.

7.  Voeg bij **Waarde** de volgende vermelding toe: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`

8.  Selecteer **OK** klik vervolgens **Toepassen**.

### <a name="test-the-extension"></a>De extensie testen

#### <a name="upload-to-cloud-service-or-access-by-unallowed-browsers-cloud-egress"></a>Naar cloudservice uploaden of openen via niet-toegestane browsers  

1. Maak of haal een gevoelig item op en probeer een bestand te uploaden naar een van de beperkte servicedomeinen van uw organisatie. De gevoelige gegevens moeten overeenkomen met een van onze ingebouwde [Gevoelige informatietypen](sensitive-information-type-entity-definitions.md), of een van de typen gevoelige informatie van uw organisatie. U ontvangt een DLP-pop-upmelding op het apparaat van waaruit u test dat deze actie niet is toegestaan wanneer het bestand is geopend.

#### <a name="testing-other-dlp-scenarios-in-chrome"></a>Andere DLP-scenario's testen in Chrome 

Nu u Chrome hebt verwijderd uit de lijst met niet-toegeziene browsers/apps, kunt u de onderstaande scenario's testen om te controleren of het gedrag voldoet aan de vereisten van uw organisatie:

- Gegevens van een gevoelig item naar een ander document kopiëren met het Klembord
    - Als u wilt testen, opent u in de Chrome-browser een bestand dat is beveiligd tegen kopiëren naar het Klembord en probeert u gegevens uit het bestand te kopiëren.
    - Verwacht resultaat: een DLP-pop-upmelding waarin wordt getoond dat deze actie niet is toegestaan wanneer het bestand is geopend.
- Een document afdrukken
    - Als u wilt testen, opent u een bestand dat is beveiligd tegen afdrukacties in de Chrome-browser en probeert u het bestand af te drukken.
    - Verwacht resultaat: een DLP-pop-upmelding waarin wordt getoond dat deze actie niet is toegestaan wanneer het bestand is geopend.
- Kopiëren naar verwijderbare USB-media
    - Test het bestand door het bestand op te slaan in een verwijderbare mediaopslag.
    - Verwacht resultaat: een DLP-pop-upmelding waarin wordt getoond dat deze actie niet is toegestaan wanneer het bestand is geopend.
- Kopiëren naar netwerkshare
    - Test het bestand door het bestand op te slaan in een netwerkshare.
    - Verwacht resultaat: een DLP-pop-upmelding waarin wordt getoond dat deze actie niet is toegestaan wanneer het bestand is geopend.


### <a name="use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts"></a>Het dashboard Waarschuwingenbeheer gebruiken om DLP-waarschuwingen in Chrome weer te geven

1. Ga in het [Microsoft 365-compliancecentrum](https://compliance.microsoft.com)naar de **pagina Preventie van gegevensverlies** en kies **Waarschuwingen**.

2. Raadpleeg de procedures in [Informatie over het configureren en weergeven van waarschuwingen voor uw DLP-beleid](dlp-configure-view-alerts-policies.md) om waarschuwingen voor uw DLP-beleid voor eindpunten weer te geven.


### <a name="viewing-chrome-dlp-data-in-activity-explorer"></a>Chrome DLP-gegevens weergeven in Activiteitenverkenner

1. Open de [pagina Gegevensclassificatie voor](https://compliance.microsoft.com/dataclassification?viewid=overview) uw domein in het Microsoft 365-compliancecentrum en kies **Activiteitenverkenner**.

2. Raadpleeg de procedures in [Aan de slag met Activiteitenverkenner](data-classification-activity-explorer.md) om alle gegevens voor uw eindpuntapparaten weer te geven en te filteren.

   > [!div class="mx-imgBorder"]
   > ![Activiteitenverkenner-filter voor eindpuntapparaten](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

### <a name="known-issues-and-limitations"></a>Bekende problemen en beperkingen

1. Afdwingen van overschrijven blokkeren voor cloud-uitgang wordt niet ondersteund.
2. De incognitomodus wordt niet ondersteund en moet worden uitgeschakeld.

## <a name="next-steps"></a>Volgende stappen
Nu u onboarded-apparaten hebt en de activiteitsgegevens kunt bekijken in Activiteitenverkenner, kunt u verder gaan met de volgende stap, waarin u DLP-beleid maakt voor het beveiligen van uw gevoelige items.

- [Preventie van gegevensverlies van eindpunten gebruiken](endpoint-dlp-using.md)

## <a name="see-also"></a>Zie ook

- [Meer informatie over Preventie van gegevensverlies voor eindpunten](endpoint-dlp-learn-about.md)
- [Preventie van gegevensverlies voor eindpunten gebruiken](endpoint-dlp-using.md)
- [Meer informatie over preventie van gegevensverlies](dlp-learn-about-dlp.md)
- [Een DLP-beleid maken, testen en afstemmen](create-test-tune-dlp-policy.md)
- [Aan de slag met Activity Explorer](data-classification-activity-explorer.md)
- [Microsoft Defender voor Eindpunt](/windows/security/threat-protection/)
- [Hulpmiddelen en methoden onboarden voor Windows 10-apparaten](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Microsoft 365-abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Azure AD-gekoppelde apparaten](/azure/active-directory/devices/concept-azure-ad-join)
- [De nieuwe Microsoft Edge op basis van Chromium downloaden](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
