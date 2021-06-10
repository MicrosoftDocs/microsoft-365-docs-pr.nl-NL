---
title: Beveiliging in de cloud in Microsoft Defender Antivirus
description: Schakel beveiliging in de cloud in om te profiteren van snelle en geavanceerde beveiligingsfuncties.
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
> De Microsoft Defender Antivirus cloudservice is een mechanisme voor het leveren van bijgewerkte beveiliging voor uw netwerk en eindpunten. Hoewel het een cloudservice wordt genoemd, is het niet alleen beveiliging voor bestanden die zijn opgeslagen in de cloud. in plaats van gedistribueerde resources en machine learning te gebruiken om uw eindpunten te beschermen tegen een snelheid die veel sneller is dan traditionele beveiligingsintelligentie-updates.

Microsoft Defender Antivirus maakt gebruik van meerdere detectie- en preventietechnologieën om nauwkeurige, realtime en intelligente beveiliging te bieden. [Maak gebruik van de geavanceerde technologieën die de kern van Microsoft Defender voor endpoint-beveiliging](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)van de volgende generatie zijn.

U kunt Microsoft Defender Antivirus beveiliging in de cloud op verschillende manieren in- of uitschakelen:

- Microsoft Intune
- Microsoft Endpoint Manager
- Groepsbeleid
- PowerShell-cmdlets.

 U kunt de app ook in- of uitschakelen in afzonderlijke clients met de Windows-beveiliging app.

Zie [Microsoft Cloud-beveiliging gebruiken voor](cloud-protection-microsoft-defender-antivirus.md) een overzicht van Microsoft Defender Antivirus beveiliging in de cloud.

Zie Netwerkverbindingen configureren en valideren voor meer informatie over de specifieke vereisten voor netwerkconnectiviteit om ervoor te zorgen dat uw eindpunten verbinding kunnen maken met de door de cloud geleverde [beveiligingsservice.](configure-network-connections-microsoft-defender-antivirus.md)

> [!NOTE]
> In Windows 10 is er geen verschil  tussen  de opties Voor basisrapportage en Geavanceerd die in dit onderwerp worden beschreven. Dit is een verouderd onderscheid en als u een instelling kiest, wordt hetzelfde niveau van beveiliging in de cloud geleverd. Er is geen verschil in het type of de hoeveelheid informatie die wordt gedeeld. Zie de Privacyverklaring van Microsoft voor meer informatie over wat we [verzamelen.](https://go.microsoft.com/fwlink/?linkid=521839)

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>Intune gebruiken om beveiliging via de cloud in te zetten

1. Ga naar het Microsoft Endpoint Manager beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.

2. Selecteer in **het deelvenster** Start de optie **Apparaatconfiguratie > Profielen.**

3. Selecteer het **profieltype Apparaatbeperkingen** dat u wilt configureren. Als u een nieuw profieltype **Apparaatbeperkingen** wilt maken, gaat u naar Instellingen voor apparaatbeperkingen [configureren in Microsoft Intune.](/intune/device-restrictions-configure)

4. Selecteer **Instellingen voor**  >  **eigenschappenconfiguratie: Bewerken**  >  **Microsoft Defender Antivirus.**

5. Selecteer **Inschakelen** op de schakelknop Beveiliging in de cloud.

6. Selecteer in **de vervolgkeuze van** Gebruikers vragen vóór voorbeeldinzending de optie **Alle gegevens automatisch verzenden.**

Zie Wat zijn Microsoft Intune apparaatprofielen? voor meer informatie over intune-apparaatprofielen, waaronder hoe u hun instellingen kunt maken [en configureren.](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>Gebruik Microsoft Endpoint Manager beveiliging in de cloud in te zetten

1. Ga naar het Microsoft Endpoint Manager beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.

2. Kies **Endpoint Security**  >  **Antivirus**.

3. Selecteer een antivirusprofiel. (Als u nog geen profiel hebt of als u een nieuw profiel wilt maken, zie Apparaatbeperkingsinstellingen [configureren in Microsoft Intune.](/intune/device-restrictions-configure)

4. Selecteer **Eigenschappen**. Kies vervolgens naast **Configuratie-instellingen** de optie **Bewerken.**

5. Vouw **Cloudbeveiliging uit** en  selecteer een van de volgende opties in de lijst beveiligingsniveau in de cloud:
   - **Hoog:** Hiermee wordt een sterk detectieniveau toegepast.
   - **Hoog plus:** gebruikt het **hoge** niveau en past extra beveiligingsmaatregelen toe (mogelijk van invloed op de prestaties van de client).
   - **Nul tolerantie:** blokkeert alle onbekende uitvoerbare bestanden.

6. Selecteer **Controleren+ opslaan** en kies **vervolgens Opslaan.**

Zie Antimalware-beleid maken en implementeren voor meer informatie over het configureren van Microsoft Endpoint Configuration Manager- en [implementatiebeleid: Cloudbeveiligingsservice.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>Groepsbeleid gebruiken om beveiliging via de cloud in te zetten

1. Open op uw apparaat voor [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.**

2. Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**

3. Selecteer **Beheersjablonen.**

4. Vouw de boom uit Windows **onderdelen > Microsoft Defender Antivirus > KAARTEN**

5. Dubbelklik op **Deelnemen aan Microsoft MAPS.** Controleer of de optie is ingeschakeld en ingesteld op **BasisKAARTEN** of **Geavanceerde KAARTEN.** Selecteer **OK**.

6. Dubbelklik op **Bestandsvoorbeelden verzenden wanneer verdere analyse vereist is.** Controleer of de eerste optie is ingesteld op **Ingeschakeld** en of de andere opties zijn ingesteld op:

    1. **Veilige steekproeven verzenden** (1)
    2. **Alle steekproeven verzenden** (3)

        >[!NOTE]
        > De **optie Veilige steekproeven** verzenden (1) betekent dat de meeste steekproeven automatisch worden verzonden. Bestanden die waarschijnlijk persoonlijke gegevens bevatten, worden nog steeds gevraagd en moeten extra worden bevestigd.
        > Als u de optie Altijd **vragen** (0) instelt, wordt de beveiligingstoestand van het apparaat lager. Als u dit **instelt op** [](configure-block-at-first-sight-microsoft-defender-antivirus.md) Nooit verzenden (2) betekent dit dat de functie Blokkeren op het eerste gezicht van Microsoft Defender voor Eindpunt niet werkt.

7. Selecteer **OK**.

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>PowerShell-cmdlets gebruiken om beveiliging via de cloud in te zetten

Met de volgende cmdlets kunt u beveiliging in de cloud in- en uit- zetten:

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Zie [PowerShell-cmdlets gebruiken om powershell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) te configureren en uit te voeren Microsoft Defender Antivirus [defender-cmdlets](/powershell/module/defender/)voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus. [Beleid CSP - Defender](/windows/client-management/mdm/policy-csp-defender) heeft ook meer informatie specifiek over [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).

>[!NOTE]
> U kunt ook **SubmitSamplesConsent instellen** op `SendSafeSamples` (de standaardinstelling), `NeverSend` of `AlwaysPrompt` . De `SendSafeSamples` instelling betekent dat de meeste voorbeelden automatisch worden verzonden. Bestanden die waarschijnlijk persoonlijke gegevens bevatten, worden nog steeds gevraagd en moeten extra worden bevestigd.

>[!WARNING]
> Instelling **-SubmitSamplesConsent** to `NeverSend` or will lower the protection level of the `AlwaysPrompt` device. Bovendien betekent het instellen dat de functie Blokkeren op het eerste gezicht van Microsoft Defender voor Eindpunt `NeverSend` niet werkt. [](configure-block-at-first-sight-microsoft-defender-antivirus.md)

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a>Gebruik Windows managementinstructie (WMI) om beveiliging via de cloud in te zetten

Gebruik de [ **methode Set** of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class voor de volgende eigenschappen:

```WMI
MAPSReporting
SubmitSamplesConsent
```

Zie [WMIv2-API'Windows Defender](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) voor meer informatie over toegestane parameters

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>Beveiliging in de cloud in te stellen voor afzonderlijke clients met de Windows-beveiliging app

> [!NOTE]
> Als de instelling Lokale instelling configureren voor het rapporteren van Microsoft  MAPS-groepsbeleid is ingesteld op **Uitgeschakeld,** is de instelling voor cloudbeveiliging in Windows Instellingen grijs en niet beschikbaar.  Wijzigingen die zijn aangebracht via een groepsbeleidsobject, moeten eerst worden geïmplementeerd op afzonderlijke eindpunten voordat de instelling wordt bijgewerkt in de Windows-instellingen.

1. Open de Windows-beveiliging app door het schildpictogram op de taakbalk te selecteren of door in het startmenu voor Defender te **zoeken.**

2. Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk) en vervolgens het label & instellingen voor **bedreigingsbeveiliging:**

    ![Schermafbeelding van het instellingenlabel voor virus- en bedreigingsbeveiliging in de app voor Windows-beveiliging](images/defender/wdav-protection-settings-wdsc.png)

3. Controleer of **cloudbeveiliging en** automatische voorbeeldinzending zijn overgeschakeld op  **Aan.**

> [!NOTE]
> Als automatische voorbeeldinzending is geconfigureerd met Groepsbeleid, is de instelling grijs en niet beschikbaar.

## <a name="related-articles"></a>Aanverwante artikelen

- [De time-outperiode voor cloudblokkering configureren](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [Blok configureren op het eerste gezicht](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [PowerShell-cmdlets gebruiken om Microsoft Defender Antivirus te beheren](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Help bij het beveiligen Windows pc's met Endpoint Protection voor Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]
- [Defender-cmdlets](/powershell/module/defender/)
- [Microsoft Cloud-beveiliging gebruiken in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)
- [Antimalware-beleid maken en implementeren: Cloudbeveiligingsservice](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
