---
title: Microsoft 365 Defender-pilaren configureren voor de testtest of testomgeving
description: Configureer Microsoft 365 Defender-pilaren, zoals Microsoft Defender voor Office 365, Microsoft Defender for Identity, Microsoft Cloud App Security en Microsoft Defender for Endpoint, voor uw testtestomgeving of pilotomgeving.
keywords: Configureer de proefversie van Microsoft Threat Protection, de configuratie van de proefversie van Microsoft Threat Protection, configureer het Microsoft Threat Protection-pilotproject, configureer Microsoft Threat Protection-pilaren, Microsoft Threat Protection-pilaren
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 78b37d9d435eabce47d360efd630c2e55cadacd1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932236"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>Microsoft 365 Defender-pilaren configureren voor uw testomgeving of testomgeving

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender


Het maken van een testtest of pilotomgeving van Microsoft 365 Defender en deze implementeren bestaat uit drie fasen:

|[![Fase 1: Voorbereiden](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[Fase 1: Voorbereiden](prepare-mtpeval.md) |[![Fase 2: Instellen](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[Fase 2: Instellen](setup-mtpeval.md) |![Fase 3: Onboard](../../media/phase-diagrams/onboard.png)<br/>Fase 3: Onboard | [![Terug naar pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Terug naar pilot playbook](mtp-pilot.md) |
|--|--|--|--|
|| |*U bent hier!* | |

U zit momenteel in de configuratiefase.

Voorbereiding is belangrijk voor elke succesvolle implementatie. In dit artikel wordt u op de punten geleid die u moet overwegen wanneer u zich voorbereidt op de implementatie van Microsoft Defender voor eindpunt.


## <a name="microsoft-365-defender-pillars"></a>Microsoft 365 Defender-pilaren
Microsoft 365 Defender bestaat uit vier pilaren. Hoewel één mogelijkheid al waarde kan leveren aan de beveiliging van uw netwerkorganisatie, geeft het inschakelen van de vier pilaren van Microsoft 365 Defender uw organisatie de meeste waarde.

![Afbeelding of_Microsoft 365 Defender-oplossing voor gebruikers, Microsoft Defender for Identity, voor eindpunten Microsoft Defender voor eindpunt, voor cloud-apps, Microsoft Cloud App-beveiliging en voor gegevens, Microsoft Defender voor Office 365](../../media/mtp/m365pillars.png)

In deze sectie wordt u begeleid bij het configureren:
-   Microsoft Defender voor Office 365
-   Microsoft Defender for Identity 
-   Microsoft Cloud App Security
-   Microsoft Defender for Endpoint


## <a name="configure-microsoft-defender-for-office-365"></a>Microsoft Defender voor Office 365 configureren

>[!NOTE]
>Sla deze stap over als Defender al is ingeschakeld voor Office 365. 

Er is een PowerShell-module, de *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA),* waarmee een aantal van deze instellingen kan worden bepaald. Wanneer get-ORCAReport wordt uitgevoerd als beheerder in uw tenant, wordt een evaluatie gegenereerd van de instellingen voor antispam, anti-phish en andere instellingen voor berichtverhandeling. U kunt deze module downloaden van https://www.powershellgallery.com/packages/ORCA/ . 

1. [Navigeer naar het bedreigingsbeheerbeleid van & Office 365-beveiligingscentrum.](https://protection.office.com/homepage)  >    >  

   ![Afbeelding of_Office 365-beveiligingspagina & compliancecentrum risicobeheerbeleid](../../media/mtp-eval-32.png)
 
2. Klik **op Anti-phishing,** selecteer **Maken** en vul de beleidsnaam en beschrijving in. Klik op **Volgende**.

   ![Afbeelding of_Office 365-pagina & beveiligingscentrum anti-phishingbeleid, waar u uw beleid een naam kunt geven](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Bewerk uw geavanceerde anti-phishingbeleid in Microsoft Defender voor Office 365. Wijzig **de geavanceerde drempelwaarde voor phishing** in **2 - Aggressive**.

3. Klik op **de vervolgkeuzelijst** Een voorwaarde toevoegen en selecteer uw domein(en) als domein van de geadresseerde. Klik op **Volgende**.

   ![Afbeelding of_Office 365-pagina & beveiligingscentrum anti-phishingbeleid, waar u een voorwaarde voor de toepassing kunt toevoegen](../../media/mtp-eval-34.png)
 
4. Controleer uw instellingen. Klik **op Dit beleid maken om** te bevestigen. 

   ![Afbeelding of_Office 365-pagina met beveiligingsinstellingen & compliancecentrum anti-phishingbeleid, waar u uw instellingen kunt bekijken en op de knop Dit beleid maken kunt klikken](../../media/mtp-eval-35.png)
 
5. Selecteer **Veilige bijlagen en** selecteer de optie **ATP voor SharePoint, OneDrive en Microsoft Teams** in turn on.

   ![Afbeelding of_Office 365-pagina & beveiligingscentrum waar u ATP voor SharePoint, OneDrive en Microsoft Teams kunt in-](../../media/mtp-eval-36.png)

6. Klik op het pictogram + om een nieuw beleid voor veilige bijlagen te maken en dit toe te passen als domein van de geadresseerde op uw domeinen. Klik op **Opslaan**.

   ![Afbeelding of_Office 365-pagina &-compliancecentrum waar u een nieuw beleid voor veilige bijlagen kunt maken](../../media/mtp-eval-37.png)
 
7. Selecteer vervolgens het beleid voor **veilige** koppelingen en klik vervolgens op het potloodpictogram om het standaardbeleid te bewerken.

8. Zorg ervoor dat de **optie Niet bijhouden wanneer gebruikers op** veilige koppelingen klikken niet is geselecteerd, terwijl de rest van de opties zijn geselecteerd. Zie [instellingen voor veilige koppelingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) voor meer informatie. Klik op **Opslaan**. 

   ![Afbeelding of_Office 365-pagina & Compliancecentrum waarin wordt weergegeven dat de optie Niet bijhouden wanneer gebruikers op Veilig klikken zijn geselecteerd](../../media/mtp-eval-38.png)

9. Selecteer vervolgens het **antimalwarebeleid,** selecteer het standaardpictogram en kies het potloodpictogram.

10. Klik **op Instellingen** en selecteer Ja en gebruik de **standaardmeldingstekst** om de reactie **op malwaredetectie in teschakelen.** Schakel het **filter Algemene bijlagetypen** in. Klik op **Opslaan**.

    ![Afbeelding van of_Office 365-pagina & Compliancecentrum waarop wordt weergegeven dat de reactie op malwaredetectie is ingeschakeld met standaardmeldingen en dat het filter voor veelgebruikte bijlagetypen is ingeschakeld](../../media/mtp-eval-39.png)
  
11. Ga naar [het Office 365-beveiligings- & zoeken](https://protection.office.com/homepage)in het auditlogboek van het Office 365-beveiligingscentrum en schakel Controle  >    >   in.

    ![Afbeelding of_Office 365-pagina & compliancecentrum waar u de zoekfunctie in het auditlogboek kunt in-](../../media/mtp-eval-40.png)

12. Integreer Microsoft Defender voor Office 365 met Microsoft Defender voor het eindpunt. Ga naar [de Office 365-beveiligings- & Compliancecentrum](https://protection.office.com/homepage)  >  **BedreigingsbeheerVerkenner** en selecteer Instellingen van  >   Microsoft Defender **for Endpoint** in de rechterbovenhoek van het scherm. Schakel in het dialoogvenster Verbinding maken met Defender voor eindpunt **verbinding in met Microsoft Defender voor eindpunt.**

    ![Afbeelding of_Office 365-pagina &-compliancecentrum waarop u de verbinding met Microsoft Defender for Endpoint kunt in- of uit](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>Microsoft Defender configureren voor identiteit

>[!NOTE]
>Sla deze stap over als Microsoft Defender voor identiteit al is ingeschakeld

1. Ga naar [het Microsoft 365-beveiligingscentrum >](https://security.microsoft.com/info) Microsoft Defender voor identiteit meer **bronnen** te  >  **selecteren.**

   ![Afbeelding of_Microsoft de pagina 365-beveiligingscentrum met een optie om Microsoft Defender voor identiteit te openen](../../media/mtp-eval-42.png)

2. Klik **op Maken** om de wizard Microsoft Defender voor identiteit te starten. 

   ![Afbeelding of_Microsoft de pagina van de wizard Defender voor identiteit waarop u moet klikken op de knop Maken](../../media/mtp-eval-43.png)

3. Kies **Geef een gebruikersnaam en wachtwoord op om verbinding te maken met uw Active Directory-forest.**  

   ![Welkomstpagina of_Microsoft Defender for Identity](../../media/mtp-eval-44.png)

4. Voer uw on-premises Active Directory-referenties in. Dit kan elk gebruikersaccount zijn dat leestoegang tot Active Directory heeft.

   ![Afbeelding of_Microsoft de pagina Defender for Identity Directory services waar u uw referenties moet plaatsen](../../media/mtp-eval-45.png)

5. Kies vervolgens **Sensor instellen en** breng het bestand over naar uw domeincontroller.

   ![Afbeelding of_Microsoft de pagina Defender for Identity waar u Sensorinstallatie voor downloaden kunt selecteren](../../media/mtp-eval-46.png)

6. Voer de installatie van Microsoft Defender voor identiteits sensor uit en begin de wizard te volgen.

   ![Afbeelding of_Microsoft de pagina Defender for Identity waarop u moet klikken om de wizard Microsoft Defender for Identity te volgen](../../media/mtp-eval-47.png)
 
7. Klik **op Volgende** bij het implementatietype sensor.

   ![Afbeelding of_Microsoft de pagina Defender for Identity waar u moet klikken om naar de volgende pagina te gaan](../../media/mtp-eval-48.png)
 
8. Kopieer de toegangstoets, omdat u deze vervolgens in de wizard moet invoeren.

   ![Afbeelding of_the sensorenpagina waar u de toegangstoets moet kopiëren die u moet invoeren op de volgende pagina van de wizard Voor identiteits sensorinstellingen van Microsoft Defender for Identity](../../media/mtp-eval-49.png)
 
9. Kopieer de toegangssleutel naar de wizard en klik op **Installeren.** 

   ![Afbeelding of_Microsoft pagina van de wizard Defender for Identity sensor waar u de toegangstoets moet geven en klik vervolgens op de knop Installeren](../../media/mtp-eval-50.png)

10. Gefeliciteerd, u hebt Microsoft Defender voor identiteit geconfigureerd op uw domeincontroller.

    ![Image of_Microsoft Defender for Identity sensor wizard installation completion where you should click the finish button](../../media/mtp-eval-51.png)
 
11. Selecteer [**Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2040449) voor eindpunt ** in de sectie Instellingen voor Microsoft Defender voor identiteit en schakel de schakelknop in. Klik op **Opslaan**. 

    ![Afbeelding of_the de pagina met identiteitsinstellingen van Microsoft Defender waar u de schakelknop Microsoft Defender for Endpoint moet in- of uitschakelen](../../media/mtp-eval-52.png)

>[!NOTE]
>Windows Defender ATP heeft de naam Microsoft Defender voor het eindpunt. Voor consistentie wordt de nieuwe naam van wijzigingen in al onze portals uitgerold.


## <a name="configure-microsoft-cloud-app-security"></a>Beveiliging van Microsoft Cloud-apps configureren

>[!NOTE]
>Sla deze stap over als u Microsoft Cloud App-beveiliging al hebt ingeschakeld. 

1. [Navigeer naar Het Microsoft 365-beveiligingscentrum](https://security.microsoft.com/info)meer bronnen  >  **voor** Microsoft  >  **Cloud App-beveiliging.**

   ![Afbeelding of_Microsoft de pagina 365-beveiligingscentrum waar u de kaart Microsoft Cloud App kunt zien en waarop u moet klikken op de knop Openen](../../media/mtp-eval-53.png)

2. Bij de informatieprompt voor integratie van Microsoft Defender voor identiteit, selecteert u Integratie van Microsoft Defender voor **identiteitsgegevens inschakelen.**
  
   ![Afbeelding of_the informatieprompt voor integratie van Microsoft Defender voor identiteit, waar u de koppeling Koppeling voor integratie van gegevens van Microsoft Defender voor identiteit inschakelen moet selecteren](../../media/mtp-eval-54.png)

   > [!NOTE]
   > Als u deze prompt niet ziet, kan het betekenen dat de integratie van uw Microsoft Defender voor identiteitsgegevens al is ingeschakeld. Als u het echter niet zeker weet, neem dan contact op met uw IT-beheerder om dit te bevestigen. 

3. Ga naar **Instellingen,** schakel de schakelknop Voor identiteitsintegratie **van Microsoft Defender** in en klik op **Opslaan.** 

   ![Afbeelding of_the instellingenpagina waar u de schakelknop voor integratie met Microsoft Defender voor identiteit moet in schakelen en vervolgens op Opslaan moet klikken](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > Voor nieuwe Microsoft Defender voor identiteits-exemplaren is deze schakelknop voor integratie automatisch ingeschakeld. Controleer of uw integratie met Microsoft Defender voor identiteit is ingeschakeld voordat u verdergaat met de volgende stap.
 
4. Selecteer onder de clouddetectie-instellingen **Microsoft Defender voor eindpuntintegratie** en schakel vervolgens de integratie in. Klik op **Opslaan**.

   ![Afbeelding of_the microsoft Defender for Endpoint-pagina waar het selectievakje voor niet-geanctioneerde apps blokkeren onder Integratie met Microsoft Defender voor eindpunt is ingeschakeld. Klik op Opslaan.](../../media/mtp-eval-56.png)

5. Selecteer onder Clouddetectie-instellingen **de optie Gegevensverrijking van** gebruiker en schakel vervolgens de integratie met Azure Active Directory in.

   ![Afbeelding van de sectie Gegevensverrijking van gebruikers waarin het selectievakje voor het verrijken van gevonden gebruikers-id's met Azure Active Directory-gebruikers is ingeschakeld](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>Microsoft Defender voor eindpunt configureren

>[!NOTE]
>Sla deze stap over als u Microsoft Defender voor eindpunt al hebt ingeschakeld.

1. Ga naar [het Microsoft 365-beveiligingscentrum](https://security.microsoft.com/info)  >  **Meer bronnen** Microsoft  >  **Defender-beveiligingscentrum.** Klik **op Openen.**

   ![Afbeelding of_Microsoft de optie Defender-beveiligingscentrum op de pagina Microsoft 365-beveiligingscentrum](../../media/mtp-eval-58.png)
 
2. Volg de wizard Microsoft Defender voor eindpunt. Klik op **Volgende**. 

   ![Afbeelding of_the welkomstwizard van het Microsoft Defender-beveiligingscentrum](../../media/mtp-eval-59.png)

3. Kies op basis van uw voorkeurslocatie voor gegevensopslag, bewaarbeleid, organisatiegrootte en opt-in voor voorbeeldfuncties.

   ![Afbeelding of_the pagina om uw land voor gegevensopslag, bewaarbeleid en de grootte van de organisatie te selecteren. Klik op volgende wanneer u klaar bent met selecteren.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > U kunt sommige instellingen, zoals de opslaglocatie van gegevens, later niet meer wijzigen. 

   Klik op **Volgende**. 

4. Klik **op Doorgaan** om de tenant Microsoft Defender for Endpoint in te stellen.

   ![Afbeelding of_the pagina met de vraag of u op de knop Doorgaan klikt om uw cloud-exemplaar te maken](../../media/mtp-eval-61.png)

5. Werk uw eindpunten in via groepsbeleid, Microsoft Endpoint Manager of door een lokaal script uit te voeren naar Microsoft Defender voor Eindpunt. Om het eenvoudig te houden, wordt in deze handleiding het lokale script gebruikt.

6. Klik **op Pakket downloaden** en kopieer het onboarding-script naar uw eindpunt(en).

   ![Afbeelding of_page u wordt gevraagd op de knop Pakket downloaden te klikken om het onboarding-script naar uw eindpunt of eindpunten te kopiëren](../../media/mtp-eval-62.png)

7. Voer op uw eindpunt het onboarding-script uit als beheerder en kies Y. 

   ![Afbeelding of_the opdrachtlijn waar u het onboarding-script kunt uitvoeren en kies Y om verder te gaan](../../media/mtp-eval-63.png)

8. Gefeliciteerd, u hebt uw eerste eindpunt binnengelaten.

   ![Afbeelding of_the opdrachtlijn waar u de bevestiging krijgt dat u uw eerste eindpunt hebt onboarded. Druk op een toets om door te gaan](../../media/mtp-eval-64.png)

9. Kopieer en plak de detectietest van de wizard Microsoft Defender for Endpoint.

   ![Afbeelding of_the een detectieteststap uit te voeren, waarbij u op Kopiëren klikt om het detectietestscript te kopiëren dat u in de opdrachtprompt moet plakken](../../media/mtp-eval-65.png)

10. Kopieer het PowerShell-script naar een opdrachtprompt met verhoogde bevoegdheid en voer het uit. 

    ![Afbeelding of_command prompt waar u het PowerShell-script naar een opdrachtprompt met verhoogde bevoegdheid moet kopiëren en uitvoeren](../../media/mtp-eval-66.png)

11. Selecteer **Microsoft Defender voor eindpunt gebruiken in** de wizard.

    ![Afbeelding of_the bevestigingsprompt van de wizard waar u moet klikken op Aan de slag met Microsoft Defender voor eindpunt](../../media/mtp-eval-67.png)
 
12. Ga naar het [Microsoft Defender-beveiligingscentrum.](https://securitycenter.windows.com/) Ga naar **Instellingen** en selecteer geavanceerde **functies.** 

    ![Afbeelding of_Microsoft menu Instellingen van Defender-beveiligingscentrum waar u Geavanceerde functies moet selecteren](../../media/mtp-eval-68.png)

13. Schakel de integratie met **Microsoft Defender for Identity in.**  

    ![Afbeelding of_Microsoft Geavanceerde functies van het Defender-beveiligingscentrum, optie Microsoft Defender voor identiteit die u moet in- of uitschakelen](../../media/mtp-eval-69.png)

14. Schakel de integratie met **Office 365 Threat Intelligence in.**

    ![Afbeelding of_Microsoft Geavanceerde functies van het Defender-beveiligingscentrum, optie bedreigingsinformatie van Office 365 die u moet in- of uitschakelen](../../media/mtp-eval-70.png)

15. Schakel integratie met **Microsoft Cloud App Security in.**

    ![Afbeelding of_Microsoft Geavanceerde functies van het Defender-beveiligingscentrum, optie voor beveiliging in Microsoft Cloud-apps die u moet in- of uitschakelen](../../media/mtp-eval-71.png)

16. Schuif omlaag en klik op **Voorkeuren voor opslaan om** de nieuwe integraties te bevestigen.

    ![Knop of_Save voorkeuren waar u op moet klikken](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>De Microsoft 365 Defender-service starten

>[!NOTE]
>Vanaf 1 juni 2020 schakelt Microsoft microsoft 365 Defender-functies automatisch in voor alle in aanmerking komende tenants. Zie dit [artikel in de Microsoft Tech Community over de licentie die in aanmerking](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) komt voor meer informatie. 


Ga naar [het Microsoft 365-beveiligingscentrum.](https://security.microsoft.com/homepage) Ga naar **Instellingen** en selecteer **Microsoft 365 Defender.**

![Afbeelding of_Microsoft 365 Defender-optie schermafbeelding van de pagina Instellingen van het Microsoft 365-beveiligingscentrum ](../../media/mtp-eval-72b.png) <br>

Zie [Microsoft 365 Defender](mtp-enable.md)in te zetten voor een uitgebreidere informatie. 

Gefeliciteerd! U hebt zojuist een testomgeving of testomgeving met Microsoft 365 Defender gemaakt! Nu kunt u vertrouwd raken met de gebruikersinterface van Microsoft 365 Defender. Bekijk wat u kunt leren van de volgende interactieve handleiding van Microsoft 365 Defender en leer hoe u elk dashboard kunt gebruiken voor uw dagelijkse beveiligingsbewerkingstaken.


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

Vervolgens kunt u een aanval simuleren en zien hoe de mogelijkheden van de verschillende producten een eindpunt detecteren, maken en automatisch reageren op een bestandsloze aanval op een eindpunt.

## <a name="next-step"></a>Volgende stap
|[Testfase van aanvallen](mtp-pilot-simulate.md) | Voer de testomgeving met Microsoft 365 Defender uit voor de aanval.
|:-------|:-----|
