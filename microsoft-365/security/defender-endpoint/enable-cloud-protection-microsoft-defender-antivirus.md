---
title: Cloudbeveiliging inschakelen in Microsoft Defender Antivirus
description: Schakel cloudbezorgde beveiliging in om te profiteren van snelle en geavanceerde beveiligingsfuncties.
keywords: Microsoft Defender Antivirus, antimalware, beveiliging, cloud, blok op het eerste gezicht
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c45fb4b60e3c20c2001cc0008ecc8154e854273
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572055"
---
# <a name="turn-on-cloud-delivered-protection"></a>Door cloud geleverde beveiliging inschakelen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> De Microsoft Defender Antivirus cloudservice is een mechanisme voor het leveren van bijgewerkte beveiliging aan uw netwerk en eindpunten. Hoewel het een cloudservice wordt genoemd, is het niet alleen bescherming voor bestanden die in de cloud zijn opgeslagen; In plaats daarvan gebruikt het gedistribueerde resources en machine learning om bescherming te bieden aan uw eind punten met een snelheid die veel sneller is dan traditionele updates voor beveiligings intelligentie.

Microsoft Defender Antivirus maakt gebruik van meerdere detectie- en preventietechnologieën om nauwkeurige, realtime en intelligente bescherming te bieden. [Maak kennis met de geavanceerde technologieën in de kern van Microsoft Defender voor endpoint-beveiliging](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)van de volgende generatie .

U kunt Microsoft Defender Antivirus cloudbeveiliging op verschillende manieren in- of uitschakelen:

- Microsoft Intune
- Microsoft Endpoint Manager
- Groepsbeleid
- PowerShell-cmdlets.

 U kunt het ook in- of uitschakelen bij afzonderlijke clients met de Windows-beveiliging-app.

Zie [Microsoft-cloudbeveiliging gebruiken](cloud-protection-microsoft-defender-antivirus.md) voor een overzicht van Microsoft Defender Antivirus cloudbeveiliging.

Zie [Netwerkverbindingen configureren en valideren](configure-network-connections-microsoft-defender-antivirus.md)voor meer informatie over de specifieke vereisten voor netwerkverbindingen om ervoor te zorgen dat uw eind punten verbinding kunnen maken met de door de cloud geleverde beveiligingsservice.

> [!NOTE]
> In Windows 10 is er geen verschil tussen de **basis-** en geavanceerde rapportageopties **die** in dit onderwerp worden beschreven. Dit is een verouderd onderscheid en het kiezen van een van beide instellingen resulteert in hetzelfde niveau van cloud-geleverde beveiliging. Er is geen verschil in het type of de hoeveelheid informatie die wordt gedeeld. Zie de [Privacyverklaring van Microsoft](https://go.microsoft.com/fwlink/?linkid=521839)voor meer informatie over wat we verzamelen.

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>Intune gebruiken om cloudbeveiliging in te schakelen

1. Ga naar het Microsoft Endpoint Manager admin center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) en log in.

2. Selecteer **apparaatconfiguratie > profielen** in het deelvenster **Start.**

3. Selecteer het profieltype **Apparaatbeperkingen** dat u wilt configureren. Zie [Apparaatbeperkingsinstellingen configureren in Microsoft Intune](/intune/device-restrictions-configure)als u een nieuw profieltype **Apparaatbeperkingen** wilt maken.

4. Instellingen **voor**  >  **eigenschappenconfiguratie selecteren:**  >  **Microsoft Defender Antivirus** bewerken.

5. Selecteer **Inschakelen op** de door de cloud **geleverde beveiligingsschakelaar** .

6. Selecteer **alle** gegevens automatisch verzenden in de vervolgkeuzelijst Gebruikers vragen vóór het indienen van **voorbeelden.**

Zie [Wat zijn Microsoft Intune apparaatprofielen voor](/intune/device-profiles) meer informatie over Intune-apparaatprofielen, inclusief het maken en configureren van hun instellingen.

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>Gebruik Microsoft Endpoint Manager om cloudbeveiliging in te schakelen

1. Ga naar het Microsoft Endpoint Manager admin center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) en log in.

2. Kies **Endpoint security**  >  **Antivirus**.

3. Selecteer een antivirusprofiel. (Als u er nog geen hebt of als u een nieuw profiel wilt maken, raadpleegt u [Instellingen voor apparaatbeperking configureren in Microsoft Intune](/intune/device-restrictions-configure).

4. Selecteer **Eigenschappen**. Kies vervolgens naast **Configuratie-instellingen** de optie **Bewerken**.

5. Vouw **Cloudbeveiliging** uit en selecteer vervolgens in de lijst **met beschermingsniveaus** die in de cloud worden geleverd een van de volgende opties:
   - **Hoog**: Past een sterk detectieniveau toe.
   - **Hoog plus:** gebruikt het **hoge** niveau en past aanvullende beschermingsmaatregelen toe (kan de prestaties van de klant beïnvloeden).
   - **Nultolerantie:** Blokkeert alle onbekende uitvoerbare bestanden.

6. Selecteer **Controleren + opslaan** en kies Opslaan . 

Zie Antimalwarebeleid maken en implementeren voor meer informatie over het configureren van [Microsoft Endpoint Configuration Manager: Cloudbeveiligingsservice](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>Groepsbeleid gebruiken om cloudbeveiliging in te schakelen

1. Open op uw apparaat voor groepsbeleidsbeheer de [Console voor groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))en klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken**.

2. Ga in de **Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie**.

3. Selecteer **Beheersjablonen**.

4. De structuur uitvouwen om **onderdelen > Microsoft Defender Antivirus > MAPS te Windows**

5. Dubbelklik op **Deelnemen aan Microsoft MAPS**. Zorg ervoor dat de optie is ingeschakeld en is ingesteld op **BasisKAARTEN** of **Geavanceerde MAPS**. Selecteer **OK**.

6. Dubbelklik op **Bestandsvoorbeelden verzenden wanneer verdere analyse vereist is**. Zorg ervoor dat de eerste optie is ingesteld **op Ingeschakeld** en dat de andere opties zijn ingesteld op:

    1. **Stuur veilige monsters** (1)
    2. **Stuur alle monsters** (3)

        >[!NOTE]
        > De optie **Veilige monsters verzenden** (1) betekent dat de meeste monsters automatisch worden verzonden. Bestanden die waarschijnlijk persoonlijke informatie bevatten, worden nog steeds gevraagd en vereisen extra bevestiging.
        > Als u de optie **instelt op Altijd vragen** (0), wordt de beveiligingsstatus van het apparaat verlaagd. Als u deze instelt op **Nooit verzenden** (2), werkt de functie Blokkeren bij het [eerste zicht](configure-block-at-first-sight-microsoft-defender-antivirus.md) van Microsoft Defender voor eindpunt niet.

7. Selecteer **OK**.

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>PowerShell-cmdlets gebruiken om door de cloud geleverde beveiliging in te schakelen

De volgende cmdlets kunnen door de cloud geleverde beveiliging inschakelen:

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Zie [PowerShell-cmdlets gebruiken om Microsoft Defender Antivirus- en Defender-cmdlets te configureren en](use-powershell-cmdlets-microsoft-defender-antivirus.md) [](/powershell/module/defender/)uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus. [Beleid CSP - Defender](/windows/client-management/mdm/policy-csp-defender) heeft ook meer informatie specifiek over [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).

>[!NOTE]
> U kunt **ook -SubmitSamplesConsent** instellen op `SendSafeSamples` (de standaardinstelling), `NeverSend` of `AlwaysPrompt` . De `SendSafeSamples` instelling betekent dat de meeste monsters automatisch worden verzonden. Bestanden die waarschijnlijk persoonlijke informatie bevatten, worden nog steeds gevraagd en vereisen extra bevestiging.

>[!WARNING]
> Instelling **-SubmitSamplesConsent** naar `NeverSend` of verlaagt het `AlwaysPrompt` beveiligingsniveau van het apparaat. Bovendien betekent het instellen `NeverSend` dat de functie Blokkeren op het eerste [zicht](configure-block-at-first-sight-microsoft-defender-antivirus.md) van Microsoft Defender voor eindpunt niet werkt.

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a>Gebruik Windows Management Instruction (WMI) om cloudbeveiliging in te schakelen

Gebruik de methode [ **Set** van de](/previous-versions/windows/desktop/defender/set-msft-mppreference) klasse MSFT_MpPreference voor de volgende eigenschappen:

```WMI
MAPSReporting
SubmitSamplesConsent
```

Zie [Windows Defender WMIv2 API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) voor meer informatie over toegestane parameters

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>Cloudbeveiliging inschakelen voor individuele clients met de Windows-beveiliging-app

> [!NOTE]
> Als de **instelling Lokale instelling configureren voor het rapporteren van Microsoft MAPS** Group Policy is ingesteld op **Uitgeschakeld,** wordt de **cloudbeveiligingsinstelling** in Windows Instellingen grijs weergegeven en niet beschikbaar. Wijzigingen die zijn aangebracht via een groepsbeleidsobject, moeten eerst worden geïmplementeerd op afzonderlijke eindpunten voordat de instelling wordt bijgewerkt in de Windows-instellingen.

1. Open de Windows-beveiliging app door het schildpictogram in de taakbalk te selecteren of door in het startmenu te zoeken naar **Defender**.

2. Selecteer de tegel **Virus & bedreigingsbeveiliging** (of het schildpictogram in de linkermenubalk) en vervolgens het label **Virus & bedreigingsbeveiligingsinstellingen:**

    ![Schermafbeelding van het instellingenlabel voor virus- en bedreigingsbeveiliging in de app voor Windows-beveiliging](images/defender/wdav-protection-settings-wdsc.png)

3. Controleer of **Cloudgebaseerde beveiliging** en **automatische voorbeeldinzending** zijn ingeschakeld **op Aan**.

> [!NOTE]
> Als automatische voorbeeldinzending is geconfigureerd met Groepsbeleid, wordt de instelling grijs weergegeven en is deze niet beschikbaar.

## <a name="related-articles"></a>Verwante artikelen

- [De time-outperiode voor cloudblokkering configureren](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [Blok op het eerste gezicht configureren](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [PowerShell-cmdlets gebruiken om Microsoft Defender Antivirus te beheren](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Help Windows pc's beveiligen met Endpoint Protection voor Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]
- [Verdediger cmdlets](/powershell/module/defender/)
- [Microsoft-cloudbeveiliging gebruiken in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)
- [Antimalwarebeleid maken en implementeren: cloudbeveiligingsservice](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
