---
title: Microsoft 365 Defender-pijlers configureren voor de proefversie of prototypeomgeving
description: Microsoft 365 Defender-pijlers configureren, zoals Microsoft Defender for Office 365, Microsoft Defender for Identity, Microsoft Cloud app Security en Microsoft Defender for Endpoint, voor uw proefabonnement op de testomgeving.
keywords: Configureer de Microsoft Threat Protection-proefversie, configuratie van Microsoft Threat Protection, Configureer prototypeproject voor Microsoft Threat Protection, Microsoft Threat Protection, pijlers voor Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 240ffd7ec8d46da33c43ec2f9cb50cf59c89f11b
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131295"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>Microsoft 365 Defender-pijlers configureren voor uw proefversie of pilot omgeving

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender


U maakt een Microsoft 365-proefabonnement voor proef omgevingen of pilot omgevingen en de implementatie ervan is een proces van drie fasen:

|[![Fase 1: voorbereiding](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[Fase 1: voorbereiding](prepare-mtpeval.md) |[![Fase 2: instellen](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[Fase 2: instellen](setup-mtpeval.md) |![Fase 3: onboarding](../../media/phase-diagrams/onboard.png)<br/>Fase 3: onboarding | [![Terug naar de pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Terug naar de pilot Playbook](mtp-pilot.md) |
|--|--|--|--|
|| |*Dat is alles!* | |

U bevindt zich momenteel in de configuratiefase.

De voorbereiding is essentieel voor een succesvolle implementatie. In dit artikel wordt u begeleid over de punten waarmee u rekening moet houden wanneer u Microsoft Defender voor eindpunten gaat voorbereiden.


## <a name="microsoft-365-defender-pillars"></a>Microsoft 365 Defender-pijlers
Microsoft 365 Defender bestaat uit vier pijlers. Hoewel één van de voorwaarden van de veiligheid van uw netwerkorganisatie al waarden kan bieden, bieden de vier Microsoft 365 Defender-pijltjes de meeste waarden.

![Afbeelding of_Microsoft 365, oplossing voor gebruikers, Microsoft Defender for-eindpunten, Microsoft Defender for endpoints, voor Cloud-apps, Microsoft Cloud app Security en voor gegevens, Microsoft Defender voor Office 365](../../media/mtp/m365pillars.png)

In deze sectie wordt u begeleid bij de configuratie:
-   Microsoft Defender voor Office 365
-   Microsoft Defender for Identity 
-   Microsoft Cloud App Security
-   Microsoft Defender voor Eindpunt 


## <a name="configure-microsoft-defender-for-office-365"></a>Microsoft Defender voor Office 365 configureren

>[!NOTE]
>Sla deze stap over als u al Defender voor Office 365 hebt ingeschakeld. 

Er is een PowerShell-module genaamd *Office 365 Advanced Threat Protection recommended configuration Analyzer (Orca)* waarmee enkele van deze instellingen kunnen worden vastgesteld. Als u een beheerder van de Tenant uitvoert, kunt u met Get-ORCAReport een beoordeling maken van de antispam, anti-spam en andere instellingen voor bericht hygiëne. U kunt deze module downloaden van https://www.powershellgallery.com/packages/ORCA/ . 

1. Ga naar de [beveiligings & beleid voor nalevings centrum van Office 365](https://protection.office.com/homepage)  >  **Threat management**  >  **Policy**.

   ![Afbeelding of_Office 365 beveiligings & beleidsregels voor het beleid voor nalevings centrum](../../media/mtp-eval-32.png)
 
2. Klik op **anti malafide**, selecteer **maken** en vul de Beleidsnaam en beschrijving in. Klik op **Volgende**.

   ![Afbeelding of_Office 365 beveiligings & beleids pagina voor naleving van het nalevings centrum, waarin u uw beleid kunt benoemen](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Uw geavanceerde anti phishingfilter bewerken in Microsoft Defender voor Office 365. Wijzig de **Geavanceerde fraude drempel** in **2-agressief**.

3. Klik op het vervolgkeuzemenu **een voorwaarde toevoegen** en selecteer uw domein (en) als domein van de ontvanger. Klik op **Volgende**.

   ![Afbeelding of_Office 365 beveiligings & beleid voor naleving van het anti-phishingfilter waarop u een voorwaarde voor de toepassing kunt toevoegen](../../media/mtp-eval-34.png)
 
4. Controleer uw instellingen. Klik op **dit beleid maken** om te bevestigen. 

   ![Afbeelding of_Office 365 beveiligings & beleidsregels voor nalevings centrum waar u de instellingen kunt controleren en klikt u op de knop dit beleid maken](../../media/mtp-eval-35.png)
 
5. Selecteer **veilige bijlagen** en selecteer de optie **ATP inschakelen voor SharePoint, OneDrive en Microsoft teams** .

   ![Afbeelding of_Office 365 beveiligings & compliance Center waarop u ATP kunt inschakelen voor SharePoint, OneDrive en Microsoft teams](../../media/mtp-eval-36.png)

6. Klik op het pictogram + om een nieuw beleid voor veilige bijlagen te maken, wanneer u dit wilt toepassen als het domein van de geadresseerde voor uw domeinen. Klik op **Opslaan**.

   ![Afbeelding of_Office 365 beveiligings & compliance Center-pagina waar u een nieuw beleid voor het maken van een veilige bijlage kunt maken](../../media/mtp-eval-37.png)
 
7. Selecteer vervolgens het beleid voor **veilige koppelingen** en klik op het potloodpictogram om het standaardbeleid te bewerken.

8. Zorg ervoor dat de optie **niet bijhouden wanneer gebruikers op optie voor veilige koppelingen klikken** niet is geselecteerd, terwijl de andere opties zijn geselecteerd. Zie [instellingen voor veilige koppelingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) voor meer informatie. Klik op **Opslaan**. 

   ![Afbeelding of_Office 365 beveiligings & compliance Center waarin wordt aangegeven dat de optie niet wordt bijgehouden wanneer gebruikers op veilig klikken niet is geselecteerd.](../../media/mtp-eval-38.png)

9. Selecteer vervolgens het **anti-malwarebeleid** , selecteer het standaardbeleid en kies het potloodpictogram.

10. Klik op **instellingen** en selecteer **Ja en gebruik de standaard Meldingstekst om het** detecteren van **malware** te activeren. Schakel het **filter common Attachment types** in. Klik op **Opslaan**.

    ![Afbeelding of_Office 365 beveiligings & pagina nalevings centrum waarin wordt aangegeven dat de antwoord op de malware-detectie is ingeschakeld met standaard melding en dat het filter common Attachment types is ingeschakeld.](../../media/mtp-eval-39.png)
  
11. Ga naar het [Office 365-beveiligings & compliance](https://protection.office.com/homepage)  >  **Search**  >  **audit log Search** en Schakel controle in.

    ![Afbeelding of_Office 365 beveiligings & compliance Center waarop u de zoekopdracht in het audit logboek kunt inschakelen](../../media/mtp-eval-40.png)

12. Microsoft Defender voor Office 365 integreren met Microsoft Defender voor eindpunt. Ga naar de [beveiligings & van het compliance Center-Beheercentrum van Office 365](https://protection.office.com/homepage)  >  **Threat management**  >  **Explorer** en selecteer **Microsoft Defender for Endpoint Settings** in de rechterbovenhoek van het scherm. Schakel in het dialoogvenster verbindingsfunctie van Defender voor eindpunt het selectievakje **verbinding maken met Microsoft Defender voor eindpunt** in.

    ![Afbeelding of_Office 365 beveiligings & compliance Center waarop u Microsoft Defender for Endpoint-verbinding kunt inschakelen](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>Microsoft Defender configureren voor identiteit

>[!NOTE]
>Sla deze stap over als u Microsoft Defender al hebt ingeschakeld voor identiteit

1. Ga naar [Microsoft 365 Beveiligingscentrum](https://security.microsoft.com/info) > Selecteer **meer resources**  >  **Microsoft Defender for Identity**.

   ![Pagina of_Microsoft 365-Beveiligingscentrum met de optie voor het openen van Microsoft Defender voor identiteit](../../media/mtp-eval-42.png)

2. Klik op **maken** om de wizard Microsoft Defender for Identity te starten. 

   ![Afbeelding van de wizardpagina voor het verwijderen van de wizard of_Microsoft voor de identiteit waarop u moet klikken op de knop maken](../../media/mtp-eval-43.png)

3. Kies **een gebruikersnaam en wachtwoord opgeven om verbinding te maken met uw Active Directory-forest**.  

   ![Afbeelding of_Microsoft Defender voor de welkomstpagina van de identiteit](../../media/mtp-eval-44.png)

4. Voer uw on-premises Active Directory-referenties in. Dit kan elk gebruikersaccount zijn met leestoegang tot Active Directory.

   ![Afbeelding of_Microsoft Defender voor de identiteit Directory Services-pagina waar u uw referenties moet invoeren](../../media/mtp-eval-45.png)

5. Kies vervolgens **Update sensoren** en zet bestand over naar uw domeincontroller.

   ![Afbeelding of_Microsoft Defender voor de identiteits pagina waar u de instellingen van een sensor downloaden kunt selecteren](../../media/mtp-eval-46.png)

6. Start de Microsoft Defender voor de installatie van de identiteits sensor en voer de wizard uit.

   ![Afbeelding of_Microsoft Defender voor identiteits pagina waarop u moet klikken op volgende om de wizard Microsoft Defender for Identity sensor te volgen](../../media/mtp-eval-47.png)
 
7. Klik op **volgende** bij het implementatietype van de sensor.

   ![Afbeelding of_Microsoft Defender voor identiteits pagina waarop u moet klikken op volgende om naar de volgende pagina te gaan](../../media/mtp-eval-48.png)
 
8. Kopieer de toegangscode omdat u deze moet typen, naast de wizard.

   ![Afbeelding of_the sensoren waar u de toegangstoets moet typen die u moet typen op de volgende pagina van de wizard voor het instellen van de installatie van Microsoft Defender voor Identity-sensor](../../media/mtp-eval-49.png)
 
9. Kopieer de toegangstoets in de wizard en klik op **installeren**. 

   ![Of_Microsoft afbeelding van de pagina van de wizard van de Identity-sensor voor de pagina waar u de toegangstoets moet invoeren en klik vervolgens op de knop installeren.](../../media/mtp-eval-50.png)

10. Gefeliciteerd, u hebt Microsoft Defender geconfigureerd voor de identiteit op uw domeincontroller.

    ![Afbeelding van de installatie van de wizard of_Microsoft Defender voor de Identity-sensor waarop u moet klikken op de knop Voltooien](../../media/mtp-eval-51.png)
 
11. Selecteer in de sectie [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) Settings * * Microsoft Defender for Endpoint * * en zet vervolgens de wisselknop. Klik op **Opslaan**. 

    ![Afbeelding of_the Microsoft Defender for Identity Settings-pagina waar u de wisselknop Microsoft Defender for Endpoint moet inschakelen](../../media/mtp-eval-52.png)

>[!NOTE]
>Windows Defender ATP is opnieuw als Microsoft Defender voor eindpunt aangemerkt. Wijzigingen die u in alle portals aanbrengt, worden doorgevoerd in de consistentie.


## <a name="configure-microsoft-cloud-app-security"></a>Beveiligingsupdates voor Microsoft Cloud app configureren

>[!NOTE]
>Sla deze stap over als u de beveiligingsversie van de Microsoft Cloud-app al hebt ingeschakeld. 

1. Ga naar het [Microsoft 365-Beveiligingscentrum](https://security.microsoft.com/info)voor  >  **meer informatie** over beveiliging van de  >  **Microsoft Cloud-app**.

   ![Pagina of_Microsoft 365 Beveiligingscentrum, waarop u de Microsoft Cloud app Card kunt zien en moet klikken op de knop openen](../../media/mtp-eval-53.png)

2. Als u op de informatie vragen om Microsoft Defender for Identity te integreren, selecteert u **Microsoft Defender inschakelen voor Identity Data Integration**.
  
   ![Afbeelding of_the informatie vraagt om Microsoft Defender te integreren voor de identiteit waar u de koppeling Microsoft Defender voor Identity Data Integration moet selecteren](../../media/mtp-eval-54.png)

   > [!NOTE]
   > Als u deze vraag niet ziet, betekent dit dat uw Microsoft Defender voor Identity Data Integration al is ingeschakeld. Als u dat nog niet weet, neemt u contact op met uw IT-beheerder om te bevestigen. 

3. Ga naar **instellingen**, schakel de wisselknop **Microsoft Defender voor Identity Integration** in en klik op **Opslaan**. 

   ![Afbeelding van of_the pagina instellingen waar u de wisselknop Microsoft Defender voor Identity Integration moet inschakelen en klik op opslaan](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > Voor nieuwe Microsoft Defender voor identiteits exemplaren wordt deze schakeloptie voor integratie automatisch ingeschakeld. Controleer of uw Microsoft Defender voor Identity-integratie is ingeschakeld voordat u verder gaat met de volgende stap.
 
4. Selecteer onder de instellingen voor Cloud detectie de optie **Microsoft Defender for Endpoint Integration** en schakel vervolgens de integratie in. Klik op **Opslaan**.

   ![Afbeelding of_the Microsoft Defender voor eindpunt voor pagina met het selectievakje niet-goedgekeurde apps blokkeren onder Microsoft Defender voor eindpunt-integratie is geselecteerd. Selecteer opslaan.](../../media/mtp-eval-56.png)

5. Selecteer onder instellingen voor Cloud detectie de optie **gebruikers verrijking** en schakel vervolgens integratie met Azure Active Directory in.

   ![Afbeelding van de sectie voor het verrijking van gebruikers waarbij het selectievakje verrijkte gebruikers-id's met Azure Active Directory-gebruikersnamen is geselecteerd](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>Microsoft Defender voor eindpunt configureren

>[!NOTE]
>Sla deze stap over als u Microsoft Defender voor eindpunten al hebt ingeschakeld.

1. Ga naar het [Microsoft 365-Beveiligingscentrum](https://security.microsoft.com/info)  >  **meer bronnen**  >  **Microsoft Defender-Beveiligingscentrum**. Klik op **openen**.

   ![De optie afbeelding of_Microsoft Defender-Beveiligingscentrum op de pagina Microsoft 365 Security Center](../../media/mtp-eval-58.png)
 
2. Volg de wizard Microsoft Defender voor eindpunt. Klik op **Volgende**. 

   ![Pagina of_the van de welkomst wizard van het Microsoft Defender-Beveiligingscentrum](../../media/mtp-eval-59.png)

3. Kies op basis van de gewenste locatie voor gegevensopslag, het bewaarbeleid voor de gegevens, de organisatie grootte en opt-in voor Voorbeeldfuncties.

   ![Afbeelding of_the pagina voor het selecteren van het land voor de opslag van de gegevens, het bewaarbeleid en de grootte van de organisatie. Klik op volgende wanneer u klaar bent met selecteren.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > U kunt een aantal instellingen, zoals de opslaglocatie van de gegevens, achteraf niet wijzigen. 

   Klik op **Volgende**. 

4. Klik op **Doorgaan** om uw Microsoft Defender for Endpoint-Tenant in te richten.

   ![Afbeelding of_the pagina waarin u wordt gevraagd Klik op de knop Doorgaan om een Cloud exemplaar te maken](../../media/mtp-eval-61.png)

5. Haal de eindpunten binnen via Groepsbeleid, Microsoft Endpoint Manager of door een lokaal script uit te voeren naar Microsoft Defender for Endpoint. Voor de eenvoud wordt in deze handleiding het lokale script gebruikt.

6. Klik op **pakket downloaden** en kopieer het onboarding-script naar uw eindpunt (en).

   ![Afbeelding of_page u wordt gevraagd op de knop pakket downloaden te klikken om het onboarding-script naar uw eindpunt of eindpunten te kopiëren.](../../media/mtp-eval-62.png)

7. Voer op het eindpunt het onboarding-script uit als beheerder en kies Y. 

   ![Afbeelding of_the commandline waarbij u het onboarding-script uitvoert en kies Y om door te gaan](../../media/mtp-eval-63.png)

8. Gefeliciteerd, u hebt het eerste eindpunt geboardd.

   ![Afbeelding of_the commandline waarbij u de bevestiging ontvangt dat u het eerste eindpunt hebt binnengebracht. Druk op een toets om door te gaan](../../media/mtp-eval-64.png)

9. Kopieer-Plak de detectietest via de wizard Microsoft Defender for Endpoint.

   ![Afbeelding of_the een detectietest stap uitvoeren waarbij u op kopiëren klikt om het opsporings testscript te kopiëren dat u in de opdrachtprompt moet plakken](../../media/mtp-eval-65.png)

10. Kopieer het PowerShell-script naar een opdrachtprompt met verhoogde bevoegdheid en voer deze opdracht uit. 

    ![Afbeelding of_command aanwijzing waar u het PowerShell-script moet kopiëren naar een opdrachtprompt met verhoogde bevoegdheid en deze kunt uitvoeren](../../media/mtp-eval-66.png)

11. Selecteer in de wizard aan de **slag met Microsoft Defender voor eindpunt** .

    ![Afbeelding of_the bevestigingsprompt van de wizard waarop u moet klikken met Microsoft Defender voor eindpunt](../../media/mtp-eval-67.png)
 
12. Ga naar het [Microsoft Defender-Beveiligingscentrum](https://securitycenter.windows.com/). Ga naar **instellingen** en selecteer **geavanceerde functies**. 

    ![Afbeelding of_Microsoft menu instellingen van het Beveiligingscentrum van Defender, waarin u geavanceerde functies moet selecteren](../../media/mtp-eval-68.png)

13. Schakel de integratie met **Microsoft Defender for Identity** in.  

    ![Afbeelding van geavanceerde functies in de of_Microsoft van het Defender-Beveiligingscentrum, Microsoft Defender for Identity Option Option en moet worden ingeschakeld](../../media/mtp-eval-69.png)

14. Schakel de integratie met **Office 365 Threat Intelligence** in.

    ![Afbeelding van geavanceerde functies in de of_Microsoft van het Defender-Beveiligingscentrum, de optie Office 365 Threat Intelligence, die u moet inschakelen](../../media/mtp-eval-70.png)

15. Schakel integratie met **Microsoft Cloud app Security** in.

    ![Afbeelding of_Microsoft geavanceerde functies in het Beveiligingscentrum van Defender, de optie voor beveiliging van de Microsoft Cloud-app, die u moet inschakelen](../../media/mtp-eval-71.png)

16. Schuif omlaag en klik op **Voorkeuren opslaan** om de nieuwe integraties te bevestigen.

    ![Afbeelding of_Save knop Voorkeuren waarop u moet klikken](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>De Microsoft 365 Defender-service starten

>[!NOTE]
>Vanaf 1 juni 2020 maakt Microsoft de functies van Microsoft 365 Defender automatisch voor alle in aanmerking komende tenants. Zie het [artikel Microsoft Tech Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) voor meer informatie over licenties. 


Ga naar [Microsoft 365 Beveiligingscentrum](https://security.microsoft.com/homepage). Ga naar **instellingen** en selecteer **Microsoft 365 Defender**.

![Schermafbeelding of_Microsoft 365 van de optie schermafbeelding van de pagina met instellingen voor Microsoft 365 Beveiligingscentrum ](../../media/mtp-eval-72b.png) <br>

Zie [Microsoft 365 Defender inschakelen](mtp-enable.md)voor uitgebreide informatie. 

Gefeliciteerd! U hebt zojuist een proefabonnement voor Microsoft 365 Defender gemaakt of een testomgeving. U kunt nu vertrouwd raken met de gebruikersinterface van Microsoft 365 Defender. Lees hier wat u kunt zien van de volgende Microsoft 365-interactieve handleiding en leer hoe u elk dashboard gebruikt voor uw dagelijkse beveiligingsbewerkingen.


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

Vervolgens kunt u een aanval simuleren en kijken hoe de functies voor cross product detectie, waarschuwingen maken en automatisch reageren op een aanval met een bestand op een eindpunt.

## <a name="next-step"></a>Volgende stap
|[Simulatie fase aanval](mtp-pilot-simulate.md) | Voer de simulatie van een aanval uit voor de testomgeving van Microsoft 365 Defender.
|:-------|:-----|
