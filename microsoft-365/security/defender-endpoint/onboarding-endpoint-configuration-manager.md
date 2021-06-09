---
title: Onboarden met behulp van Microsoft Endpoint Configuration Manager
description: Meer informatie over het onboarden van Microsoft Defender voor Eindpunt met Microsoft Endpoint Configuration Manager
keywords: onboarding, configuration, deploy, deployment, endpoint configuration manager, Microsoft Defender for Endpoint, collection creation, endpoint detection response, next generation protection, attack surface reduction, microsoft endpoint configuration manager
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: eab23ddeb9011e80cf2835b8d38b2d3fad4b7089
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843504"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a>Onboarden met behulp van Microsoft Endpoint Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Dit artikel maakt deel uit van de implementatiehandleiding en fungeert als voorbeeld voor onboarding. 

In het [onderwerp Planning](deployment-strategy.md) zijn verschillende methoden beschikbaar gesteld voor onboard-apparaten voor de service. In dit onderwerp wordt de architectuur voor comanagement besproken. 

![Afbeelding van cloud-native architectuur ](images/co-management-architecture.png)
 *Diagram van omgevingsarchitectuur*


Hoewel Defender voor Eindpunt ondersteuning biedt voor onboarding van verschillende eindpunten en hulpprogramma's, worden deze niet in dit artikel beschreven. Zie Onboarding overview (Overzicht van onboarding) voor informatie over algemene onboarding met behulp van andere ondersteunde implementatiehulpmiddelen en [-methoden.](onboarding.md)



In dit onderwerp worden gebruikers begeleid in:
- Stap 1: Onboarding Windows apparaten aan de service 
- Stap 2: Defender configureren voor endpoint-mogelijkheden

In deze onboarding-richtlijnen wordt u begeleid door de volgende basisstappen die u moet nemen bij het gebruik van Microsoft Endpoint Configuration Manager:
- **Een verzameling maken in Microsoft Endpoint Configuration Manager**
- **Microsoft Defender configureren voor endpoint-mogelijkheden met Microsoft Endpoint Configuration Manager**

>[!NOTE]
>Alleen Windows apparaten worden in dit voorbeeld geïmplementeerd. 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a>Stap 1: Onboard Windows apparaten met Microsoft Endpoint Configuration Manager

### <a name="collection-creation"></a>Verzameling maken
Als u Windows 10 apparaten met Microsoft Endpoint Configuration Manager wilt gebruiken, kan de implementatie gericht zijn op een bestaande verzameling of kan er een nieuwe verzameling worden gemaakt om te testen. 

Onboarding met behulp van hulpmiddelen, zoals groepsbeleid of handmatige methode, installeert geen agent op het systeem. 

Binnen de Microsoft Endpoint Configuration Manager console wordt het onboardingproces geconfigureerd als onderdeel van de nalevingsinstellingen binnen de console.

Elk systeem dat deze vereiste configuratie ontvangt, blijft die configuratie behouden zolang de Configuration Manager-client dit beleid blijft ontvangen vanaf het beheerpunt. 

Volg de onderstaande stappen om eindpunten aan te Microsoft Endpoint Configuration Manager.

1. Navigeer Microsoft Endpoint Configuration Manager console naar **Apparaatverzamelingen activa en \> \> complianceoverzicht.**            

    ![Afbeelding van Microsoft Endpoint Configuration Manager wizard1](images/configmgr-device-collections.png)

2. Klik met de **rechtermuisknop op Apparaatverzameling** en **selecteer Apparaatverzameling maken.**

    ![Afbeelding van Microsoft Endpoint Configuration Manager wizard2](images/configmgr-create-device-collection.png)

3. Geef een **naam en** verzameling **beperken op** en selecteer vervolgens **Volgende.**

    ![Afbeelding van Microsoft Endpoint Configuration Manager wizard3](images/configmgr-limiting-collection.png)

4. Selecteer **Regel toevoegen** en kies **Queryregel.**

    ![Afbeelding van Microsoft Endpoint Configuration Manager wizard4](images/configmgr-query-rule.png)

5.  Klik **op Volgende** in de wizard Direct **lidmaatschap** en klik op **Queryverklaring bewerken.**

     ![Afbeelding van Microsoft Endpoint Configuration Manager wizard5](images/configmgr-direct-membership.png)

6. Selecteer **Criteria** en kies vervolgens het sterpictogram.

     ![Afbeelding van Microsoft Endpoint Configuration Manager wizard6](images/configmgr-criteria.png)

7. Houd criteriumtype als eenvoudige **waarde,** kies waar als besturingssysteem **- buildnummer**, operator **groter dan** of gelijk aan en waarde **14393** en klik op **OK.**

    ![Afbeelding van Microsoft Endpoint Configuration Manager wizard7](images/configmgr-simple-value.png)

8. Selecteer **Volgende** en **Sluiten.**

    ![Afbeelding van Microsoft Endpoint Configuration Manager wizard8](images/configmgr-membership-rules.png)

9. Selecteer **Volgende**.

    ![Afbeelding van Microsoft Endpoint Configuration Manager wizard9](images/configmgr-confirm.png)


Na het voltooien van deze taak hebt u nu een apparaatverzameling met alle Windows 10 eindpunten in de omgeving. 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a>Stap 2: Microsoft Defender configureren voor endpoint-mogelijkheden 
In deze sectie wordt u begeleid bij het configureren van de volgende mogelijkheden met Microsoft Endpoint Configuration Manager op Windows apparaten:

- [**Detectie van en reactie op eindpunt**](#endpoint-detection-and-response)
- [**Beveiliging van de volgende generatie**](#next-generation-protection)
- [**Kwetsbaarheid voor aanvallen verminderen**](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a>Detectie van en reactie op eindpunt
#### <a name="windows-10"></a>Windows 10
Vanuit de Microsoft Defender-beveiligingscentrum is het mogelijk om het '.onboarding'-beleid te downloaden dat kan worden gebruikt om het beleid in System Center Configuration Manager te maken en dat beleid te implementeren op Windows 10 apparaten.

1. Selecteer in Microsoft Defender-beveiligingscentrum portal Instellingen [en vervolgens Onboarding.](https://securitycenter.windows.com/preferences2/onboarding)



2. Selecteer onder Implementatiemethode de ondersteunde versie van **Microsoft Endpoint Configuration Manager.**

    ![Afbeelding van de wizard Onboarding van Microsoft Defender voor eindpunt10](images/mdatp-onboarding-wizard.png)

3. Selecteer **Downloadpakket.**

    ![Afbeelding van de wizard Onboarding van Microsoft Defender voor Eindpunt11](images/mdatp-download-package.png)

4. Sla het pakket op een toegankelijke locatie op.
5. Ga Microsoft Endpoint Configuration Manager naar: Assets **and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.

6. Klik met de **rechtermuisknop Microsoft Defender ATP beleidsregels** en selecteer **Microsoft Defender ATP maken.**

    ![Afbeelding van Microsoft Endpoint Configuration Manager wizard12](images/configmgr-create-policy.png)

7. Voer de naam en beschrijving in, controleer **of Onboarding** is geselecteerd en selecteer **volgende.**

    ![Afbeelding van Microsoft Endpoint Configuration Manager wizard13](images/configmgr-policy-name.png)


8. Klik **op Bladeren**.

9. Ga vanaf stap 4 hierboven naar de locatie van het gedownloade bestand.

10. Klik op **Volgende**.
11. Configureer de Agent met de juiste steekproeven **(Geen** of **Alle bestandstypen).**

    ![Afbeelding van configuratie-instellingen1](images/configmgr-config-settings.png)

12. Selecteer de juiste telemetrie **(Normaal** of **Versneld)** en klik vervolgens op **Volgende.**

    ![Afbeelding van configuratie-instellingen2](images/configmgr-telemetry.png)

14. Controleer de configuratie en klik vervolgens op **Volgende.**

     ![Afbeelding van configuratie-instellingen3](images/configmgr-verify-configuration.png)

15. Klik **op Sluiten** wanneer de wizard is voltooid.

16.  Klik in Microsoft Endpoint Configuration Manager console met de rechtermuisknop op het Beleid van Defender voor eindpunt dat u zojuist hebt gemaakt en selecteer **Implementeren.**

     ![Afbeelding van configuratie-instellingen4](images/configmgr-deploy.png)

17. Selecteer in het rechtervenster de eerder gemaakte verzameling en klik op **OK.**

    ![Afbeelding van configuratie-instellingen5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a>Vorige versies van Windows Client (Windows 7 en Windows 8.1)
Volg de onderstaande stappen om de Defender for Endpoint Workspace ID en Workspace Key te identificeren, die vereist zijn voor het onboarden van eerdere versies van Windows.

1. Selecteer in Microsoft Defender-beveiligingscentrum portal Instellingen > **Onboarding.**

2. Kies onder besturingssysteem **Windows 7 SP1 en 8.1**.

3. Kopieer de **werkruimte-id** en **werkruimtesleutel en** sla ze op. Ze worden later in het proces gebruikt.

    ![Afbeelding van onboarding](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. Installeer de Microsoft Monitoring Agent (MMA). <br>
    MMA wordt momenteel (vanaf januari 2019) ondersteund op de volgende Windows besturingssystemen:

    -   Server-SKU's: Windows Server 2008 SP1 of Nieuwer

    -   Client-SKU's: Windows 7 SP1 en hoger

    De MMA-agent moet worden geïnstalleerd op Windows apparaten. Als u de agent wilt installeren, moeten sommige systemen de update voor klantervaring en diagnostische [telemetrie](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) downloaden om de gegevens met MMA te verzamelen. Deze systeemversies omvatten, maar zijn mogelijk niet beperkt tot:

    -   Windows 8.1

    -   Windows 7

    -   Windows Server 2016

    -   Windows Server 2012 R2

    -   Windows Server 2008 R2

    Met name voor Windows 7 SP1 moeten de volgende patches zijn geïnstalleerd:

    -   [KB4074598 installeren](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)

    -   Installeer een [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (of hoger) **of** 
         [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).
        Installeer beide niet op hetzelfde systeem.

5. Zie de sectie Proxyinstellingen configureren als u een proxy gebruikt om verbinding te maken met internet.

Wanneer u klaar bent, ziet u binnen een uur onboarded eindpunten in de portal.

### <a name="next-generation-protection"></a>Beveiliging van de volgende generatie 
Microsoft Defender Antivirus is een ingebouwde antimalwareoplossing die de volgende generatie bescherming biedt voor desktops, draagbare computers en servers.

1. Ga in Microsoft Endpoint Configuration Manager console naar **Assets and Compliance Overview Endpoint Protection \> \> \> Antimalware Polices** en kies **Antimalwarebeleid maken.**

    ![Afbeelding van antimalwarebeleid](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. Selecteer **Geplande scans**, **Scaninstellingen**, **Standaardacties**, **Realtime** beveiliging **,** **Uitsluitingsinstellingen**, **Geavanceerd**, Bedreiging overschrijven , **Cloud Protection Service** en **Beveiligingsintelligentie-updates** en kies **OK**.

    ![Afbeelding van het volgende beschermingsvenster1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    In bepaalde bedrijfstakken of sommige geselecteerde zakelijke klanten hebben mogelijk specifieke behoeften voor de configuratie van Antivirus.

  
    [Snelle scan versus volledige scan en aangepaste scan](/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    Zie Windows-beveiliging [configuratiekader voor meer informatie.](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)
  
    ![Afbeelding van het volgende beschermingsvenster2](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![Afbeelding van het volgende beschermingsvenster3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![Afbeelding van het volgende beschermingsvenster4](images/a28afc02c1940d5220b233640364970c.png)

    ![Afbeelding van het volgende beschermingsvenster5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![Afbeelding van het volgende beschermingsvenster6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![Afbeelding van het volgende beschermingsvenster7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![Afbeelding van het volgende beschermingsvenster8](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![Afbeelding van het volgende beschermingsvenster9](images/3876ca687391bfc0ce215d221c683970.png)

3. Klik met de rechtermuisknop op het nieuw gemaakte antimalwarebeleid en selecteer **Implementeren.**

    ![Afbeelding van het volgende beveiligingsvenster10](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. Richt het nieuwe antimalwarebeleid op uw Windows 10 en klik op **OK.**

     ![Afbeelding van het volgende beschermingsvenster11](images/configmgr-select-collection.png)

Nadat u deze taak hebt voltooid, hebt u de Windows Defender Antivirus.

### <a name="attack-surface-reduction"></a>Kwetsbaarheid voor aanvallen verminderen
De attack surface reduction-pijler van Defender for Endpoint bevat de functieset die beschikbaar is onder Exploit Guard. Asr-regels (Attack Surface Reduction), Controlled Folder Access, Network Protection en Exploit Protection. 

Al deze functies bieden een auditmodus en een blokmodus. In de auditmodus is er geen effect op de eindgebruiker. Het enige wat u doet, is extra telemetrie verzamelen en beschikbaar maken in de Microsoft Defender-beveiligingscentrum. Het doel van een implementatie is om beveiligingsbesturingselementen stapsgewijs naar de blokmodus te verplaatsen.

Asr-regels instellen in de auditmodus:

1. Ga in Microsoft Endpoint Configuration Manager console naar **Assets and Compliance \> Overview Endpoint Protection Windows Defender Exploit \> \> Guard** en kies **Exploit Guard Policy maken.**

   ![Afbeelding van Microsoft Endpoint Configuration Manager console0](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  Selecteer **Attack Surface Reduction**.
   

3. Stel regels in op **Controleren** en klik op **Volgende.**


    ![Afbeelding van Microsoft Endpoint Configuration Manager console1](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. Bevestig het nieuwe beleid van Exploit Guard door op Volgende te **klikken.**

    ![Afbeelding van Microsoft Endpoint Configuration Manager console2](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. Wanneer het beleid is gemaakt, klikt u op **Sluiten.**

    ![Afbeelding van Microsoft Endpoint Configuration Manager console3](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Afbeelding van Microsoft Endpoint Manager console1](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  Klik met de rechtermuisknop op het nieuw gemaakte beleid en kies **Implementeren.**
    
    ![Afbeelding van Microsoft Endpoint Configuration Manager console4](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. Richt het beleid op de nieuwe Windows 10 en klik op **OK.**

    ![Afbeelding van Microsoft Endpoint Configuration Manager console5](images/0ccfe3e803be4b56c668b220b51da7f7.png)

Nadat u deze taak hebt voltooid, hebt u nu ASR-regels geconfigureerd in de auditmodus.  
  
Hieronder vindt u aanvullende stappen om te controleren of ASR-regels correct worden toegepast op eindpunten. (Dit kan enkele minuten duren)


1. Navigeer vanuit een webbrowser naar <https://securitycenter.windows.com> .

2.  Selecteer **Configuratiebeheer** in het linkermenu.

3. Klik **op Ga naar aanvallen op surface management** in het Surface Management panel van Attack. 
    
    ![Afbeelding van aanvalsoppervlakbeheer](images/security-center-attack-surface-mgnt-tile.png)

4. Klik **op het** tabblad Configuratie in rapporten met de surface reduction rules attack. Hier ziet u het overzicht van asr-regelsconfiguratie en de status van ASR-regels op elke apparaten.

    ![Een schermafbeelding van rapporten over de beperkingsregels voor de surface van de aanval1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. Klik op elk apparaat met configuratiedetails van ASR-regels.

    ![Een schermafbeelding van rapporten met regels voor het verlagen van het aanvalsoppervlak2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

Zie [Asr-regelimplementatie en -detecties optimaliseren](/microsoft-365/security/defender-endpoint/configure-machines-asr)   voor meer informatie.  


#### <a name="set-network-protection-rules-in-audit-mode"></a>Regels voor netwerkbeveiliging instellen in de auditmodus:
1. Ga in Microsoft Endpoint Configuration Manager console naar **Assets and Compliance \> Overview Endpoint Protection Windows Defender Exploit \> \> Guard** en kies **Exploit Guard Policy maken.**

    ![Een schermafbeelding System Center Configuration Manager1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. Selecteer **Netwerkbeveiliging.**

3. Stel de instelling in op **Controleren** en klik op **Volgende.** 

    ![Een schermafbeelding System Center Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. Bevestig het nieuwe beleid voor beveiligingsbeleid door op Volgende te **klikken.**
    
    ![Een schermafbeelding Van GUard-beleid misbruiken1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. Wanneer het beleid is gemaakt, klikt u op **Sluiten.**

    ![Schermafbeelding GUard-beleid misbruiken2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. Klik met de rechtermuisknop op het nieuw gemaakte beleid en kies **Implementeren.**

    ![Een schermafbeelding van Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. Selecteer het beleid voor de nieuwe Windows 10 en kies **OK.**

    ![Een schermafbeelding van Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



Nadat u deze taak hebt voltooid, hebt u netwerkbeveiliging nu geconfigureerd in de auditmodus.

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a>Regels voor gecontroleerde maptoegang instellen in de auditmodus:

1. Ga in Microsoft Endpoint Configuration Manager console naar **Assets and Compliance \> Overview Endpoint Protection Windows Defender Exploit \> \> Guard** en kies **Exploit Guard Policy maken.**

    ![Schermafbeelding van Microsoft Endpoint Configuration Manager3](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. Selecteer **Gecontroleerde maptoegang.**
    
3. Stel de configuratie in op **Controleren** en klik op **Volgende.**

    ![Schermafbeelding van Microsoft Endpoint Configuration Manager4](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. Bevestig het nieuwe beleid voor beveiligingsbeleid door op Volgende te **klikken.**

    ![Schermafbeelding van Microsoft Endpoint Configuration Manager5](images/0a6536f2c4024c08709cac8fcf800060.png)

5. Wanneer het beleid is gemaakt, klikt u op **Sluiten.**

    ![Een schermafbeelding van Microsoft Endpoint Configuration Manager6](images/95d23a07c2c8bc79176788f28cef7557.png)

6. Klik met de rechtermuisknop op het nieuw gemaakte beleid en kies **Implementeren.**

    ![Schermafbeelding van Microsoft Endpoint Configuration Manager7](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  Richt het beleid op de nieuwe Windows 10 en klik op **OK.**

    ![Een schermafbeelding van Microsoft Endpoint Configuration Manager8](images/0ccfe3e803be4b56c668b220b51da7f7.png)

U hebt nu beheerde maptoegang geconfigureerd in de auditmodus.

## <a name="related-topic"></a>Verwant onderwerp
- [Onboarden met behulp van Microsoft Endpoint Manager](onboarding-endpoint-manager.md)
