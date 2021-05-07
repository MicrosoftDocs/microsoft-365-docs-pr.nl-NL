---
title: Onboarden Windows 10-apparaten via Groepsbeleid
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Gebruik Groepsbeleid om het configuratiepakket te implementeren op Windows 10 apparaten, zodat ze zijn aan boord van de service.
ms.openlocfilehash: 284de5169324b6da4038cfe0b50b2f2ffa40e3fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "52162699"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>Onboard Windows 10 apparaten met groepsbeleid 

**Van toepassing op:**

- [Microsoft 365 Preventie van gegevensverlies in eindpunten (DLP)](./endpoint-dlp-learn-about.md)
- Groepsbeleid

> [!NOTE]
> Als u gp-updates (Group Policy) wilt gebruiken om het pakket te implementeren, moet u zich Windows Server 2008 R2 of hoger.

> Voor Windows Server 2019 moet u mogelijk NT AUTHORITY\Well-Known-System-Account vervangen door NT AUTHORITY\SYSTEM van het XML-bestand dat door de groepsbeleidsvoorkeur wordt gemaakt.

## <a name="onboard-devices-using-group-policy"></a>Onboarden apparaten met Groepsbeleid

1. Open het GP-configuratiepakket .zip bestand *(DeviceComplianceOnboardingPackage.zip)* dat u hebt gedownload van de wizard Service onboarding. U kunt het pakket ook krijgen in [het Microsoft Compliance Center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)

2. Selecteer in het navigatiedeelvenster **Instellingen**  >  **Onboarding van apparaat.**

3. Selecteer groepsbeleid in **het veld** **Implementatiemethode.**

4. Klik **op Pakket downloaden** en sla het .zip op.

5. Haal de inhoud van het .zip naar een gedeelde, alleen-lezen locatie die toegankelijk is voor het apparaat. U moet een map met de naam *OptionalParamsPolicy en* het bestand *DeviceComplianceLocalOnboardingScript.cmd hebben.*

6. Open de GPMC (Group [Policy Management Console),](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

7. Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie,** vervolgens **Voorkeuren** en vervolgens **naar Configuratiescherminstellingen.**

8. Klik met de rechtermuisknop **op Geplande taken,** wijs **Nieuw** aan en klik vervolgens op Onmiddellijke **taak (ten minste Windows 7).**

9. Ga in **het** venster Taak dat wordt geopend naar het **tabblad** Algemeen. Klik **onder Beveiligingsopties** **op Gebruiker of Groep wijzigen** en typ SYSTEEM en klik vervolgens op Namen **controleren** en vervolgens **OP OK.** NT AUTHORITY\SYSTEM wordt weergegeven als het gebruikersaccount dat de taak als wordt uitgevoerd.

10. Schakel **Uitvoeren in of de gebruiker al** dan niet is aangemeld en schakel het selectievakje Uitvoeren met hoogste **bevoegdheden** in.

11. Ga naar het **tabblad Acties** en klik op **Nieuw...** Zorg ervoor **dat Een programma starten** is geselecteerd in het **veld** Actie. Voer de bestandsnaam en locatie in van het gedeelde *WindowsDefenderATPOnboardingScript.cmd-bestand.*

12. Klik **op OK** en sluit alle geopende GPMC-vensters.


## <a name="offboard-devices-using-group-policy"></a>Offboard-apparaten met groepsbeleid
Om veiligheidsredenen verloopt het pakket dat wordt gebruikt voor Offboard-apparaten 30 dagen na de datum waarop het is gedownload. Verlopen offboarding-pakketten die naar een apparaat zijn verzonden, worden geweigerd. Wanneer u een offboarding-pakket downloadt, wordt u op de hoogte gesteld van de vervaldatum van de pakketten en wordt het ook opgenomen in de pakketnaam.

> [!NOTE]
> Onboarding- en offboarding-beleid mag niet tegelijkertijd op hetzelfde apparaat worden geïmplementeerd, anders veroorzaakt dit onvoorspelbare botsingen.

1. Haal het offboarding-pakket op in [het Microsoft Compliance Center.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)

2. Selecteer in het navigatiedeelvenster **Instellingen**  >  **/Device onboarding**  >  **Offboarding**.

3. Selecteer groepsbeleid in **het veld** **Implementatiemethode.**

4. Klik **op Pakket downloaden** en sla het .zip op.

5. Haal de inhoud van het .zip naar een gedeelde, alleen-lezen locatie die toegankelijk is voor het apparaat. U moet een bestand met de naam *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* hebben.

6. Open de GPMC (Group [Policy Management Console),](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

7. Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie,** vervolgens **Voorkeuren** en vervolgens **naar Configuratiescherminstellingen.**

8. Klik met de rechtermuisknop **op Geplande taken,** wijs **Nieuw** aan en klik vervolgens op **Onmiddellijke taak.**

9. Ga in **het** venster Taak dat wordt geopend naar het **tabblad** Algemeen. Kies het lokale SYSTEEM-gebruikersaccount (BUILTIN\SYSTEM) onder **Beveiligingsopties.**

10. Schakel **Uitvoeren in of de gebruiker al** dan niet is aangemeld en schakel het selectievakje Uitvoeren met hoogste **bevoegdheden** in.

11. Ga naar het **tabblad Acties** en klik op **Nieuw...**. Zorg ervoor **dat Een programma starten** is geselecteerd in het **veld** Actie. Voer de bestandsnaam en de locatie van het gedeelde  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd-bestand* in.

12. Klik **op OK** en sluit alle geopende GPMC-vensters.

> [!IMPORTANT]
> Offboarding zorgt ervoor dat het apparaat stopt met het verzenden van sensorgegevens naar de portal, maar gegevens van het apparaat.


## <a name="monitor-device-configuration"></a>Apparaatconfiguratie controleren
Met Groepsbeleid is er geen optie om de implementatie van beleidsregels op de apparaten te controleren. Monitoring kan rechtstreeks in de portal of met behulp van de verschillende implementatiehulpmiddelen worden uitgevoerd.

## <a name="monitor-devices-using-the-portal"></a>Apparaten controleren met behulp van de portal
1. Ga naar [Microsoft Compliance Center.](https://compliance.microsoft.com/)
2. Klik **op De lijst** Apparaten.
3. Controleer of apparaten worden weergegeven.

> [!NOTE]
> Het kan enkele dagen duren voordat apparaten worden weergegeven in de **lijst Apparaten.** Dit omvat de tijd die nodig is voor de distributie van het beleid naar het apparaat, de tijd die nodig is voordat de gebruiker zich aanmeldt en de tijd die nodig is voor het eindpunt om te beginnen met rapporteren.


## <a name="related-topics"></a>Verwante onderwerpen
- [Onboard Windows 10 apparaten met Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Onboarden Windows 10-apparaten met hulpmiddelen voor Mobile Device Management](dlp-configure-endpoints-mdm.md)
- [Onboarden Windows 10-apparaten met een lokaal script](dlp-configure-endpoints-script.md)
- [Onboarden niet-permanente virtual desktop infrastructure (VDI)-apparaten](dlp-configure-endpoints-vdi.md)
- [Een detectietest uitvoeren op een nieuw ingebouwde Microsoft Defender voor eindpuntapparaten](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Problemen met Microsoft Defender Advanced Threat Protection onboarding oplossen](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)