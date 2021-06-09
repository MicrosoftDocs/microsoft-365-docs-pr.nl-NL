---
title: Onboarden met behulp van Microsoft Endpoint Manager
description: Meer informatie over het onboarden van Microsoft Defender voor Eindpunt met Microsoft Endpoint Manager
keywords: onboarding, configuration, deploy, deployment, endpoint manager, Microsoft Defender for Endpoint, collection creation, endpoint detection response, next generation protection, attack surface reduction, microsoft endpoint manager
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
ms.openlocfilehash: f3442528f6d9239219f0b4638f75758a055717de
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842636"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a>Onboarden met behulp van Microsoft Endpoint Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Dit artikel maakt deel uit van de implementatiehandleiding en fungeert als voorbeeld voor onboarding. 

In het [onderwerp Planning](deployment-strategy.md) zijn verschillende methoden beschikbaar gesteld voor onboard-apparaten voor de service. Dit onderwerp heeft betrekking op de cloud-native architectuur. 

![Afbeelding van cloud-native architectuur ](images/cloud-native-architecture.png)
 *Diagram van omgevingsarchitectuur*

Hoewel Defender voor Eindpunt ondersteuning biedt voor onboarding van verschillende eindpunten en hulpprogramma's, worden deze niet in dit artikel beschreven. Zie Onboarding overview (Overzicht van onboarding) voor informatie over algemene onboarding met behulp van andere ondersteunde implementatiehulpmiddelen en [-methoden.](onboarding.md)


[Microsoft Endpoint Manager](/mem/endpoint-manager-overview) is een oplossingsplatform waarmee verschillende services worden geseenigd. Het omvat [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) voor apparaatbeheer in de cloud.


In dit onderwerp worden gebruikers begeleid in:
- Stap 1: Onboarding devices to the service by creating a group in Microsoft Endpoint Manager (MEM) to assign configurations on
- Stap 2: Defender configureren voor endpoint-mogelijkheden met Microsoft Endpoint Manager

In deze onboarding-richtlijnen wordt u begeleid door de volgende basisstappen die u moet nemen bij het gebruik van Microsoft Endpoint Manager:

-   [Doelapparaten of gebruikers identificeren](#identify-target-devices-or-users)

    -   Een groep Azure Active Directory maken (gebruiker of apparaat)

-   [Een configuratieprofiel maken](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)

    -   In Microsoft Endpoint Manager begeleiden we u bij het maken van een afzonderlijk beleid voor elke mogelijkheid.





## <a name="resources"></a>Resources


Hier volgen de koppelingen die u nodig hebt voor de rest van het proces:

-   [MEM-portal](https://aka.ms/memac)

-   [Beveiligingscentrum](https://securitycenter.windows.com/)

-   [Basislijnen voor Intune-beveiliging](/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

Voor meer informatie over Microsoft Endpoint Manager, raadpleegt u deze bronnen:
- [Microsoft Endpoint Manager pagina](/mem/)
- [Blogbericht over convergentie van Intune en ConfigMgr](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [Inleidingsvideo over MEM](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a>Stap 1: Onboard-apparaten door een groep te maken in EENM om configuraties toe te wijzen aan
### <a name="identify-target-devices-or-users"></a>Doelapparaten of gebruikers identificeren
In deze sectie maken we een testgroep om uw configuraties aan toe te wijzen.

>[!NOTE]
>Intune gebruikt Azure Active Directory (Azure AD) groepen om apparaten en gebruikers te beheren. Als Intune-beheerder kunt u groepen instellen die aan uw organisatiebehoeften voldoen.<br>
Zie Groepen toevoegen om [gebruikers en apparaten te ordenen voor meer informatie.](/mem/intune/fundamentals/groups-add)

### <a name="create-a-group"></a>Een groep maken

1.  Open de MEM-portal.

2.  Open **Groepen > nieuwe groep.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal1](images/66f724598d9c3319cba27f79dd4617a4.png)

3.  Voer details in en maak een nieuwe groep.

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal2](images/b1e0206d675ad07db218b63cd9b9abc3.png)

4.  Voeg uw testgebruiker of -apparaat toe.

5.  Open de **nieuwe groep in het deelvenster Groepen >** Alle groepen.

6.  Selecteer **Leden > Leden toevoegen.**

7.  Zoek uw testgebruiker of -apparaat en selecteer deze.

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal3](images/149cbfdf221cdbde8159d0ab72644cd0.png)

8.  Uw testgroep heeft nu een lid om te testen.

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a>Stap 2: Configuratiebeleid maken om Microsoft Defender te configureren voor endpoint-mogelijkheden
In de volgende sectie maakt u een aantal configuratiebeleidsregels.

Ten eerste is er een configuratiebeleid om te selecteren welke groepen gebruikers of apparaten worden onboarded bij Defender for Endpoint:

- [Detectie van en reactie op eindpunt](#endpoint-detection-and-response) 

Vervolgens gaat u door met het maken van verschillende typen eindpuntbeveiligingsbeleid:

- [Beveiliging van de volgende generatie](#next-generation-protection)
- [Kwetsbaarheid voor aanvallen verminderen](#attack-surface-reduction--attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a>Detectie van en reactie op eindpunt

1.  Open de MEM-portal.

2.  **Navigeer naar endpointbeveiliging > endpointdetectie en -antwoord.** Klik op **Profiel maken.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal4](images/58dcd48811147feb4ddc17212b7fe840.png)

3.  Selecteer **onder Platform de Windows 10 en Hoger, Profiel - Eindpuntdetectie en -antwoord > Maken.**

4.  Voer een naam en beschrijving in en selecteer **Volgende.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)

5.  Selecteer zo nodig instellingen en selecteer  **vervolgens Volgende**.

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal6](images/cea7e288b5d42a9baf1aef0754ade910.png)

    > [!NOTE]
    > In dit geval is dit automatisch ingevuld omdat Defender voor Eindpunt al is geïntegreerd met Intune. Zie Microsoft Defender voor eindpunt inschakelen [in Intune](/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp)voor meer informatie over de integratie.
    > 
    > De volgende afbeelding is een voorbeeld van wat u ziet wanneer Microsoft Defender voor Eindpunt NIET is geïntegreerd met Intune:
    >
    > ![Afbeelding van Microsoft Endpoint Manager portal7](images/2466460812371ffae2d19a10c347d6f4.png)

6.  Voeg indien nodig bereiklabels toe en selecteer **Volgende.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal8](images/ef844f52ec2c0d737ce793f68b5e8408.png)

7.  Voeg de testgroep toe door op Groepen **selecteren te klikken om uw** groep op te nemen en te kiezen en selecteer vervolgens **Volgende.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal9](images/fc3525e20752da026ec9f46ab4fec64f.png)

8.  Controleer en accepteer en selecteer vervolgens **Maken.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal10](images/289172dbd7bd34d55d24810d9d4d8158.png)

9.  U kunt uw voltooide beleid bekijken.

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal11](images/5a568b6878be8243ea2b9d82d41ed297.png)

### <a name="next-generation-protection"></a>Beveiliging van de volgende generatie

1.  Open de MEM-portal.

2.  Ga naar **Endpoint-beveiligingsprogramma'> Antivirus > Beleid maken.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal12](images/6b728d6e0d71108d768e368b416ff8ba.png)

3.  Selecteer **Platform - Windows 10 en Hoger - Windows en Profiel - Microsoft Defender Antivirus > Maken.**

4.  Voer naam en beschrijving in en selecteer **Volgende.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal13](images/a7d738dd4509d65407b7d12beaa3e917.png)

5.  Op de **pagina Configuratie-instellingen:** Stel de configuraties in die u nodig hebt voor Microsoft Defender Antivirus (Cloudbeveiliging, Uitsluitingen, Real-Time Beveiliging en Herstel).

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)

6.  Voeg indien nodig bereiklabels toe en selecteer **Volgende.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal15](images/2055e4f9b9141525c0eb681e7ba19381.png)

7.  Selecteer groepen die u wilt opnemen, wijs deze toe aan uw testgroep en  **selecteer** Volgende.

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal16](images/48318a51adee06bff3908e8ad4944dc9.png)

8.  Controleer en maak en selecteer vervolgens **Maken.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal17](images/dfdadab79112d61bd3693d957084b0ec.png)

9.  U ziet het configuratiebeleid dat u hebt gemaakt.

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal18](images/38180219e632d6e4ec7bd25a46398da8.png)

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a>Attack Surface Reduction – Attack surface reduction rules

1.  Open de MEM-portal.

2.  **Navigeer naar endpointbeveiliging > Attack surface reduction**.

3.  Selecteer **Beleid maken.**

4.  Selecteer **Platform - Windows 10 en Hoger - Profiel - Attack surface reduction rules > Create**.

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal19](images/522d9bb4288dc9c1a957392b51384fdd.png)

5.  Voer een naam en beschrijving in en selecteer **Volgende.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)

6.  Op de **pagina Configuratie-instellingen:** Stel de configuraties in die u nodig hebt voor De surface reduction-regels van Attack en selecteer vervolgens  **Volgende**.

    > [!NOTE]
    > We configureren alle regels voor het verlagen van de Surface Attack in Audit.
    > 
    > Zie Surface [Reduction Rules attack (Surface Reduction Rules) voor meer informatie.](attack-surface-reduction.md)

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal21](images/dd0c00efe615a64a4a368f54257777d0.png)

7.  Voeg zo nodig bereiklabels toe en selecteer **Volgende.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)

8.  Selecteer groepen die u wilt opnemen en toewijzen aan de testgroep en selecteer vervolgens **Volgende.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal23](images/45cefc8e4e474321b4d47b4626346597.png)

9. Bekijk de details en selecteer vervolgens **Maken.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)

10. Bekijk het beleid.

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal25](images/7a631d17cc42500dacad4e995823ffef.png)

### <a name="attack-surface-reduction--web-protection"></a>Attack Surface Reduction – Web Protection

1.  Open de MEM-portal.

2.  **Navigeer naar endpointbeveiliging > Attack surface reduction**.

3.  Selecteer **Beleid maken.**

4.  Selecteer **Windows 10 en Hoger : webbeveiliging > Maken.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)

5.  Voer een naam en beschrijving in en selecteer **Volgende.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal27](images/5be573a60cd4fa56a86a6668b62dd808.png)

6.  Op de **pagina Configuratie-instellingen:** Stel de configuraties in die u nodig hebt voor webbeveiliging en selecteer vervolgens **Volgende.**

    > [!NOTE]
    > We configureren Webbeveiliging op Blokkeren.
    > 
    > Zie Webbeveiliging voor [meer informatie.](web-protection-overview.md)

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal28](images/6104aa33a56fab750cf30ecabef9f5b6.png)

7.  Voeg **zo nodig bereiklabels > Volgende.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)

8.  Selecteer **Toewijzen aan testgroep > Volgende**.

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal30](images/45cefc8e4e474321b4d47b4626346597.png)

9.  Selecteer **Controleren en maken > Maken.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)

10. Bekijk het beleid.

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager portal32](images/e74f6f6c150d017a286e6ed3dffb7757.png)

## <a name="validate-configuration-settings"></a>Configuratie-instellingen valideren


### <a name="confirm-policies-have-been-applied"></a>Beleid bevestigen is toegepast


Nadat het configuratiebeleid is toegewezen, duurt het enige tijd om toe te passen.

Zie Intune-configuratiegegevens voor [informatie over tijdsinstellingen.](/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned)

Als u wilt bevestigen dat het configuratiebeleid is toegepast op uw testapparaat, volgt u het volgende proces voor elk configuratiebeleid.

1.  Open de MEM-portal en ga naar het relevante beleid, zoals wordt weergegeven in de bovenstaande stappen. In het volgende voorbeeld ziet u de volgende generatie beveiligingsinstellingen.

    > [!div class="mx-imgBorder"]
    > [![Afbeelding van Microsoft Endpoint Manager portal33 ](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)

2.  Selecteer het **configuratiebeleid om** de beleidsstatus weer te geven.

    > [!div class="mx-imgBorder"]
    > [![Afbeelding van Microsoft Endpoint Manager portal34 ](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)

3.  Selecteer  **Apparaatstatus om** de status te zien.

    > [!div class="mx-imgBorder"]
    > [![Afbeelding van Microsoft Endpoint Manager portal35 ](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)

4.  Selecteer  **Gebruikersstatus om** de status te zien.

    > [!div class="mx-imgBorder"]
    > [![Afbeelding van Microsoft Endpoint Manager portal36 ](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)

5.  Selecteer  **Status per instelling om** de status te zien.

    >[!TIP]
    >Deze weergave is zeer handig om instellingen te identificeren die conflicteren met een ander beleid.

    > [!div class="mx-imgBorder"]
    > [![Afbeelding van Microsoft Endpoint Manager portal37 ](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)

### <a name="endpoint-detection-and-response"></a>Detectie van en reactie op eindpunt


1.  Voordat u de configuratie gaat toepassen, moet de Defender voor Endpoint Protection service niet worden gestart.

    > [!div class="mx-imgBorder"]
    > [![Afbeelding van het deelvenster Services1 ](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)

2.  Nadat de configuratie is toegepast, moet de Defender voor Endpoint Protection Service worden gestart.

    > [!div class="mx-imgBorder"]
    > [![Afbeelding van het deelvenster Services2 ](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)

3.  Nadat de services op het apparaat zijn uitgevoerd, wordt het apparaat weergegeven in Microsoft Defender-beveiligingscentrum.

    > [!div class="mx-imgBorder"]
    > [![Afbeelding van Microsoft Defender-beveiligingscentrum ](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)

### <a name="next-generation-protection"></a>Beveiliging van de volgende generatie

1.  Voordat u het beleid op een testapparaat kunt toepassen, moet u de instellingen handmatig kunnen beheren, zoals hieronder wordt weergegeven.

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van instellingspagina1](images/88efb4c3710493a53f2840c3eac3e3d3.png)

2.  Nadat het beleid is toegepast, kunt u de instellingen niet handmatig beheren.

    > [!NOTE]
    > In de volgende afbeelding wordt Beveiliging  in de **cloud in-** en in-/uit-/in-/uit-beveiliging weergegeven als beheerd.

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van instellingspagina2](images/9341428b2d3164ca63d7d4eaa5cff642.png)

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a>Attack Surface Reduction – Attack surface reduction rules


1.  Voordat u het beleid op een testapparaat gaat toepassen, pent u een PowerShell-venster en typt `Get-MpPreference` u .

2.  Dit moet reageren met de volgende regels zonder inhoud:

    > AttackSurfaceReductionOnlyExclusions:
    > 
    > AttackSurfaceReductionRules_Actions:
    > 
    > AttackSurfaceReductionRules_Ids:

    ![Afbeelding van opdrachtregel1](images/cb0260d4b2636814e37eee427211fe71.png)

3.  Nadat u het beleid op een testapparaat hebt toegepast, opent u een PowerShell-Windows en typt `Get-MpPreference` u .

4.  Dit moet reageren met de volgende regels met inhoud zoals hieronder wordt weergegeven:

    ![Afbeelding van opdrachtregel2](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="attack-surface-reduction--web-protection"></a>Attack Surface Reduction – Web Protection

1.  Open op het testapparaat een PowerShell-Windows en typ `(Get-MpPreference).EnableNetworkProtection` .

2.  Dit moet reageren met een 0 zoals hieronder wordt weergegeven.

    ![Afbeelding van opdrachtregel3](images/196a8e194ac99d84221f405d0f684f8c.png)

3.  Nadat u het beleid heeft toegepast, opent u een PowerShell-Windows en typt `(Get-MpPreference).EnableNetworkProtection` u .

4.  Dit moet reageren met een 1 zoals hieronder wordt weergegeven.

    ![Afbeelding van opdrachtregel4](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
