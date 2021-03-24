---
title: Microsoft 365 Defender-pilaren configureren voor het proeflaboratorium of de testomgeving
description: Configureer Microsoft 365 Defender-pilaren, zoals Microsoft Defender voor Office 365, Microsoft Defender voor identiteit, Microsoft Cloud App-beveiliging en Microsoft Defender voor eindpunt, voor uw proeflab of testomgeving.
keywords: Proefversie van Microsoft Threat Protection configureren, proefversie van Microsoft Threat Protection configureren, Microsoft Threat Protection-testproject configureren, Microsoft Threat Protection-pijlers configureren, Microsoft Threat Protection-pijlers
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 5ab4019751a26507fcc80007d3262f20f861d25c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057986"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>Microsoft 365 Defender-pilaren configureren voor uw proeflaboratorium of testomgeving

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender


Het maken van een proeflaboratorium of testomgeving van Microsoft 365 Defender en de implementatie ervan is een proces in drie fasen:

|[![Fase 1: Voorbereiden](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)<br/>[Fase 1: Voorbereiden](prepare-m365d-eval.md) |[![Fase 2: Instellen](../../media/phase-diagrams/setup.png)](setup-m365deval.md)<br/>[Fase 2: Instellen](setup-m365deval.md) |![Fase 3: Onboard](../../media/phase-diagrams/onboard.png)<br/>Fase 3: Onboard | [![Terug naar pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[Terug naar pilot playbook](m365d-pilot.md) |
|--|--|--|--|
|| |*U bent er!* | |

U bent momenteel in de configuratiefase.

Voorbereiding is essentieel voor een geslaagde implementatie. In dit artikel wordt u begeleid over de punten die u moet overwegen terwijl u zich voorbereidt op de implementatie van Microsoft Defender voor Eindpunt.


## <a name="microsoft-365-defender-pillars"></a>Microsoft 365 Defender-pilaren
Microsoft 365 Defender bestaat uit vier pilaren. Hoewel één pijler al waarde kan bieden voor de beveiliging van uw netwerkorganisatie, geeft het inschakelen van de vier Microsoft 365 Defender-pijlers uw organisatie de meeste waarde.

![Image of_Microsoft 365 Defender solution for users, Microsoft Defender for Identity, for endpoints Microsoft Defender for Endpoint, for cloud apps, Microsoft Cloud App Security, and for data, Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

In deze sectie wordt u begeleid bij het configureren:
-   Microsoft Defender voor Office 365
-   Microsoft Defender for Identity 
-   Microsoft Cloud App Security
-   Microsoft Defender for Endpoint


## <a name="configure-microsoft-defender-for-office-365"></a>Microsoft Defender configureren voor Office 365

>[!NOTE]
>Sla deze stap over als u Defender voor Office 365 al hebt ingeschakeld. 

Er is een PowerShell-module genaamd *de Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* waarmee u bepaalde van deze instellingen kunt bepalen. Wanneer u wordt uitgevoerd als een beheerder in uw tenant, helpt get-ORCAReport bij het genereren van een beoordeling van de instellingen voor antispam, anti-phish en andere berichthygiëne. U kunt deze module downloaden van https://www.powershellgallery.com/packages/ORCA/ . 

1. Navigeer naar het beveiligingsbeleid van [Office 365 & Compliance Center](https://protection.office.com/homepage)Threat  >  **Management**  >  **Policy**.

   ![Pagina of_Office beveiligingsbeleid van 365 & compliancecentrum bedreigingsbeheer](../../media/mtp-eval-32.png)
 
2. Klik **op Anti-phishing,** selecteer **Maken** en vul de naam en beschrijving van het beleid in. Klik op **Volgende**.

   ![Afbeelding of_Office 365-beveiligingspagina & anti-phishingbeleidspagina van het Compliancecentrum, waar u uw beleid een naam kunt geven](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Bewerk uw geavanceerde anti-phishingbeleid in Microsoft Defender voor Office 365. Geavanceerde **phishingdrempel wijzigen** in **2 - Agressief.**

3. Klik op **de vervolgkeuzelijst** Een voorwaarde toevoegen en selecteer uw domein(en) als geadresseerdedomein. Klik op **Volgende**.

   ![Afbeelding of_Office 365 Security & Compliance Center anti-phishing policy page where you can add a condition for its application](../../media/mtp-eval-34.png)
 
4. Controleer uw instellingen. Klik **op Dit beleid maken om** dit te bevestigen. 

   ![Afbeelding of_Office 365 Security & Compliance Center anti-phishing policy page where you can review your settings and click the create this policy button](../../media/mtp-eval-35.png)
 
5. Selecteer **Veilige bijlagen en** selecteer de optie **ATP voor SharePoint, OneDrive en Microsoft Teams** in- en uit.

   ![Afbeelding of_Office 365-pagina Beveiligings- & compliancecentrum waar u ATP voor SharePoint, OneDrive en Microsoft Teams kunt in-](../../media/mtp-eval-36.png)

6. Klik op het pictogram + om een nieuw beleid voor veilige bijlagen te maken en pas dit toe als geadresseerdedomein op uw domeinen. Klik op **Opslaan**.

   ![Afbeelding of_Office pagina 365 Beveiligingscentrum & waar u een nieuw beleid voor veilige bijlagen kunt maken](../../media/mtp-eval-37.png)
 
7. Selecteer vervolgens het beleid **voor veilige** koppelingen en klik vervolgens op het potloodpictogram om het standaardbeleid te bewerken.

8. Zorg ervoor dat de optie **Niet bijhouden wanneer gebruikers op** veilige koppelingen klikken niet is geselecteerd, terwijl de overige opties zijn geselecteerd. Zie [Instellingen voor veilige koppelingen](/microsoft-365/security/defender-365-security/recommended-settings-for-eop-and-office365) voor meer informatie. Klik op **Opslaan**. 

   ![Afbeelding of_Office pagina 365 Beveiligingscentrum & waarin wordt weergegeven dat de optie Niet bijhouden wanneer gebruikers op veilig klikken niet is geselecteerd](../../media/mtp-eval-38.png)

9. Selecteer vervolgens het **anti-malwarebeleid,** selecteer de standaardinstelling en kies het potloodpictogram.

10. Klik **op Instellingen** en selecteer Ja en gebruik de **standaardmeldingstekst** om reactie op **malwaredetectie in te stellen.** Schakel het **filter Algemene bijlagetypen** in. Klik op **Opslaan**.

    ![Afbeelding of_Office pagina Beveiligings- & compliancecentrum van 365, waaruit blijkt dat de reactie op malwaredetectie is ingeschakeld met standaardmelding en dat het filter voor algemene bijlagetypen is ingeschakeld](../../media/mtp-eval-39.png)
  
11. Ga naar [Office 365 Security & Search](https://protection.office.com/homepage)Audit log search and turn  >    >   Auditing on.

    ![Afbeelding of_Office pagina 365 Beveiligingscentrum & waar u de zoekopdracht Auditlogboek kunt in-](../../media/mtp-eval-40.png)

12. Integreer Microsoft Defender voor Office 365 met Microsoft Defender voor Eindpunt. Ga naar [Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat Management Explorer en selecteer Microsoft Defender voor Eindpuntinstellingen in de rechterbovenhoek van het  >    >   scherm.  Schakel in het dialoogvenster Verbinding tussen Defender voor eindpunten **Verbinding maken met Microsoft Defender voor Eindpunt in.**

    ![Afbeelding of_Office 365-beveiligings- & pagina compliancecentrum waarin u Verbinding met Microsoft Defender voor eindpunt kunt in-](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>Microsoft Defender configureren voor identiteit

>[!NOTE]
>Sla deze stap over als u Microsoft Defender voor identiteit al hebt ingeschakeld

1. Ga naar [het Microsoft 365-beveiligingscentrum >](https://security.microsoft.com/info) selecteer Meer **resources** Microsoft Defender  >  **voor identiteit.**

   ![Afbeelding of_Microsoft 365-beveiligingscentrum met een optie om Microsoft Defender voor identiteit te openen](../../media/mtp-eval-42.png)

2. Klik **op Maken** om de wizard Microsoft Defender voor identiteit te starten. 

   ![Afbeelding of_Microsoft wizard Defender voor identiteit waar u op knop Maken moet klikken](../../media/mtp-eval-43.png)

3. Kies **Een gebruikersnaam en wachtwoord opgeven om verbinding te maken met uw Active Directory-forest.**  

   ![Welkomstpagina of_Microsoft Defender voor identiteit](../../media/mtp-eval-44.png)

4. Voer uw on-premises Active Directory-referenties in. Dit kan elk gebruikersaccount zijn dat leestoegang heeft tot Active Directory.

   ![Afbeelding of_Microsoft defender voor identiteitslijstservicespagina waar u uw referenties moet plaatsen](../../media/mtp-eval-45.png)

5. Kies vervolgens **Sensor instellen downloaden en** bestand overbrengen naar uw domeincontroller.

   ![Afbeelding of_Microsoft defender voor identiteitspagina waar u Sensorinstallatie downloaden kunt selecteren](../../media/mtp-eval-46.png)

6. Voer de installatie van de Microsoft Defender voor identiteits sensor uit en begin de wizard te volgen.

   ![Afbeelding of_Microsoft defender voor identiteitspagina waar u naast moet klikken om de sensorwizard van Microsoft Defender voor identiteit te volgen](../../media/mtp-eval-47.png)
 
7. Klik **op Volgende** bij het type sensorimplementatie.

   ![Afbeelding of_Microsoft defender voor identiteitspagina waar u naast moet klikken om naar de volgende pagina te gaan](../../media/mtp-eval-48.png)
 
8. Kopieer de toegangssleutel omdat u deze vervolgens moet invoeren in de wizard.

   ![Afbeelding of_the pagina met sensoren waar u de toegangstoets moet kopiëren die u moet invoeren op de volgende pagina met de installatiewizard van de Microsoft Defender voor identiteits sensor](../../media/mtp-eval-49.png)
 
9. Kopieer de toegangssleutel naar de wizard en klik op **Installeren.** 

   ![Afbeelding of_Microsoft wizard Wizard Defender voor identiteits sensor waar u de toegangssleutel moet verstrekken en klik vervolgens op de knop Installeren](../../media/mtp-eval-50.png)

10. Gefeliciteerd, u hebt Microsoft Defender voor identiteit geconfigureerd op uw domeincontroller.

    ![Afbeelding of_Microsoft installatie van de wizard Installatie van de defender voor identiteits sensor, waarbij u op de knop Voltooien moet klikken](../../media/mtp-eval-51.png)
 
11. Selecteer onder [de sectie Instellingen](https://go.microsoft.com/fwlink/?linkid=2040449) voor Microsoft Defender voor identiteit de optie **Microsoft Defender voor Eindpunt **, en schakel de schakelaar in. Klik op **Opslaan**. 

    ![Afbeelding of_the pagina met instellingen voor Microsoft Defender voor identiteit waarin u de schakelknop Microsoft Defender voor eindpunt moet in-](../../media/mtp-eval-52.png)

> [!NOTE]
> Windows Defender ATP is hernoemd als Microsoft Defender voor Eindpunt. Wijzigingen wijzigen in al onze portals worden uitgerold voor consistentie.


## <a name="configure-microsoft-cloud-app-security"></a>Microsoft Cloud App-beveiliging configureren

> [!NOTE]
> Sla deze stap over als u Microsoft Cloud App-beveiliging al hebt ingeschakeld. 

1. Ga naar [Microsoft 365 Security Center](https://security.microsoft.com/info)More  >  **Resources** Microsoft Cloud  >  **App Security**.

   ![Afbeelding of_Microsoft 365-beveiligingscentrumpagina waar u de Kaart van Microsoft Cloud App kunt zien en op de knop Openen moet klikken](../../media/mtp-eval-53.png)

2. Selecteer Microsoft Defender inschakelen voor **identiteitsgegevensintegratie** bij de informatieprompt voor het integreren van Microsoft Defender voor identiteit.
  
   ![Afbeelding of_the informatieprompt om Microsoft Defender voor identiteit te integreren, waarbij u de koppeling Microsoft Defender voor integratie van identiteitsgegevens inschakelen moet selecteren](../../media/mtp-eval-54.png)

   > [!NOTE]
   > Als u deze prompt niet ziet, kan dit betekenen dat uw Microsoft Defender voor identiteitsgegevensintegratie al is ingeschakeld. Als u het echter niet zeker weet, neem dan contact op met uw IT-beheerder om dit te bevestigen. 

3. Ga naar **Instellingen,** schakel de schakelknop **Microsoft Defender voor identiteitsintegratie** in en klik op **Opslaan.** 

   ![Afbeelding of_the pagina met instellingen waar u de schakelknop Voor identiteitsintegratie van Microsoft Defender in moet schakelen en klik vervolgens op Opslaan](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > Voor nieuwe Microsoft Defender voor identiteits-exemplaren wordt deze schakelknop voor integratie automatisch ingeschakeld. Controleer of uw Microsoft Defender voor identiteitsintegratie is ingeschakeld voordat u verdergaat met de volgende stap.
 
4. Selecteer onder de instellingen voor clouddetectie de optie **Microsoft Defender voor endpoint-integratie** en schakel de integratie in. Klik op **Opslaan**.

   ![Afbeelding of_the microsoft Defender voor eindpuntpagina waarin het selectievakje Niet-geanctioneerde apps blokkeren onder Microsoft Defender voor endpoint-integratie is geselecteerd. Klik op Opslaan.](../../media/mtp-eval-56.png)

5. Selecteer onder Instellingen voor clouddetectie de optie **Gebruikersverrijking** en schakel vervolgens de integratie met Azure Active Directory in.

   ![Afbeelding van de sectie Gebruikersverrijking waarin het selectievakje voor het verrijken van ontdekte gebruikers-id's met Azure Active Directory-gebruikersnamen is geselecteerd](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>Microsoft Defender configureren voor eindpunt

>[!NOTE]
>Sla deze stap over als u Microsoft Defender voor Eindpunt al hebt ingeschakeld.

1. Ga naar [Microsoft 365 Security Center](https://security.microsoft.com/info)More  >  **Resources** Microsoft Defender  >  **Security Center**. Klik **op Openen.**

   ![Afbeelding of_Microsoft Defender-beveiligingscentrum op de pagina Microsoft 365-beveiligingscentrum](../../media/mtp-eval-58.png)
 
2. Volg de wizard Microsoft Defender voor eindpunt. Klik op **Volgende**. 

   ![Pagina of_the microsoft Defender Security Center welkomstwizard](../../media/mtp-eval-59.png)

3. Kies op basis van uw voorkeurslocatie voor gegevensopslag, beleid voor gegevensretentie, organisatiegrootte en opt-in voor voorbeeldfuncties.

   ![Afbeelding of_the pagina om uw land voor gegevensopslag, bewaarbeleid en organisatiegrootte te selecteren. Klik op volgende wanneer u klaar bent met selecteren.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > U kunt sommige instellingen, zoals de locatie voor gegevensopslag, achteraf niet wijzigen. 

   Klik op **Volgende**. 

4. Klik **op Doorgaan** en de Microsoft Defender voor Eindpunt-tenant wordt ingericht.

   ![Afbeelding of_the pagina met de vraag of u op de knop Doorgaan klikt om uw cloud-exemplaar te maken](../../media/mtp-eval-61.png)

5. Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint. Voor de eenvoud wordt in deze handleiding het lokale script gebruikt.

6. Klik **op Pakket downloaden** en kopieer het onboarding-script naar uw eindpunten.

   ![Afbeelding of_page u op de knop Pakket downloaden klikt om het onboarding-script naar uw eindpunt of eindpunten te kopiëren](../../media/mtp-eval-62.png)

7. Voer op het eindpunt het onboarding-script uit als beheerder en kies Y. 

   ![Afbeelding of_the commandline waar u het onboarding-script uitwerkt en Y kiest om door te gaan](../../media/mtp-eval-63.png)

8. Gefeliciteerd, u hebt uw eerste eindpunt aan boord.

   ![Afbeelding of_the commandline waar u de bevestiging krijgt dat u uw eerste eindpunt hebt onboarded. Druk op een toets om door te gaan](../../media/mtp-eval-64.png)

9. Kopieer de detectietest vanuit de wizard Microsoft Defender voor eindpunt.

   ![Afbeelding of_the een detectieteststap uitvoeren waarbij u op Kopiëren moet klikken om het detectietestscript te kopiëren dat u in de opdrachtprompt moet plakken](../../media/mtp-eval-65.png)

10. Kopieer het PowerShell-script naar een opdrachtprompt met verhoogde opdracht en voer het uit. 

    ![Image of_command prompt where you should copy the PowerShell script to an elevated command prompt and run it](../../media/mtp-eval-66.png)

11. Selecteer **Start using Microsoft Defender for Endpoint from** the Wizard.

    ![Afbeelding of_the bevestigingsprompt van de wizard waarin u op Start using Microsoft Defender for Endpoint klikt](../../media/mtp-eval-67.png)
 
12. Ga naar [het Microsoft Defender-beveiligingscentrum.](https://securitycenter.windows.com/) Ga naar **Instellingen** en selecteer geavanceerde **functies.** 

    ![Afbeelding of_Microsoft menu Instellingen van het Defender-beveiligingscentrum waarin u Geavanceerde functies moet selecteren](../../media/mtp-eval-68.png)

13. Schakel de integratie met **Microsoft Defender voor identiteit in.**  

    ![Afbeelding of_Microsoft Geavanceerde functies van het Defender Security Center, optie microsoft Defender voor identiteit die u moet in- of uitschakelen](../../media/mtp-eval-69.png)

14. Schakel de integratie met **Office 365 Threat Intelligence in.**

    ![Afbeelding of_Microsoft Geavanceerde functies van het Defender Security Center, optie voor Office 365 Threat Intelligence die u moet in- of uitschakelen](../../media/mtp-eval-70.png)

15. Schakel integratie in met **Microsoft Cloud App Security.**

    ![Image of_Microsoft Defender Security Center Advanced features, Microsoft Cloud App Security option toggle that you need to turn on](../../media/mtp-eval-71.png)

16. Schuif omlaag en klik **op Voorkeuren opslaan om** de nieuwe integraties te bevestigen.

    ![Knop of_Save afbeeldingsvoorkeuren waar u op moet klikken](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>De Microsoft 365 Defender-service starten

>[!NOTE]
>Vanaf 1 juni 2020 worden microsoft 365 Defender-functies automatisch in gebruik gemaakt voor alle in aanmerking komende tenants. Zie dit [Artikel van de Microsoft Tech Community over het in aanmerking komen voor](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) licenties voor meer informatie. 


Ga naar [het Microsoft 365-beveiligingscentrum.](https://security.microsoft.com/homepage) Ga naar **Instellingen** en selecteer **microsoft 365 Defender.**

![Afbeelding of_Microsoft 365 Defender-optie schermafbeelding van de pagina Instellingen van het Microsoft 365-beveiligingscentrum ](../../media/mtp-eval-72b.png) <br>

Zie [Microsoft 365 Defender in- en in- en uit- zetten voor uitgebreidere richtlijnen.](m365d-enable.md) 

Gefeliciteerd! U hebt zojuist uw proeflaboratorium of testomgeving voor Microsoft 365 Defender gemaakt. Nu kunt u vertrouwd raken met de gebruikersinterface van Microsoft 365 Defender! Bekijk wat u kunt leren van de volgende interactieve Microsoft 365 Defender-handleiding en weet hoe u elk dashboard kunt gebruiken voor uw dagelijkse beveiligingstaken.


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

Vervolgens kunt u een aanval simuleren en zien hoe de verschillende productmogelijkheden waarschuwingen detecteren, maken en automatisch reageren op een bestandloze aanval op een eindpunt.

## <a name="next-step"></a>Volgende stap

- [Een testwaarschuwing genereren:](generate-test-alert.md) voer een aanvalssimulatie uit in uw Proeflab van Microsoft 365 Defender.