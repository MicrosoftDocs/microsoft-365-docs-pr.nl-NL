---
title: Microsoft Threat Protection-pijlers configureren voor de proefversie of prototypeomgeving
description: U kunt de Microsoft Threat Protection-pijlers configureren, zoals Office 365 ATP, Azure ATP, Microsoft Cloud app Security en Microsoft Defender ATP voor uw proefversie of pilot omgeving.
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1778e8485e859d01e4eec40c7a0d404636e27e8d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199647"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-or-pilot-environment"></a>Microsoft Threat Protection-pijlers configureren voor uw proefversie of pilot omgeving

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection


U maakt een Microsoft Threat Protection-proefversie voor proef omgevingen of pilot omgevingen en de implementatie hiervan is een proces van drie fasen:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Uw proefabonnement voor Microsoft Threat Protection of een testomgeving voorbereiden" />
      <br/>Fase 1: voorbereiding </a><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="Uw Microsoft Threat Protection-proefversie Lab of pilot omgeving instellen" />
      <br/>Fase 2: instellen </a><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Configureer elke Microsoft Threat Protection-pijler voor uw proefabonnement voor Microsoft Threat Protection of een proef omgeving en de interne eindpunten" />
      <br/>Fase 3: & onboard configureren </a><br>
</td>


  </tr>
</table>

U bevindt zich momenteel in de configuratiefase.


De voorbereiding is essentieel voor een succesvolle implementatie. In dit artikel wordt u begeleid over de punten die u in overweging moet nemen wanneer u de implementatie van Microsoft Defender ATP gaat voorbereiden.


## <a name="microsoft-threat-protection-pillars"></a>Microsoft Threat Protection-pijlers
Microsoft Threat Protection bestaat uit vier pijlers. Hoewel u met de vier Microsoft Threat Protection-gebruikers al een waarde kunt opgeven voor de veiligheid van uw netwerkorganisatie, kunt u de meeste waarden opgeven voor de vier Microsoft Threat Protection-pijler.
<br>
![Afbeelding of_Microsoft oplossing voor beveiliging van bedreigingen voor gebruikers, Azure Advanced Threat Protection voor eindpunten van Microsoft Defender Advanced Threat Protection, voor Cloud-apps, Microsoft Cloud app Security en voor gegevens, Office 365 Advanced Threat Protection  ](../../media/mtp-eval-31.png) <br>

In deze sectie wordt u begeleid bij de configuratie:
-   Office 365 Advanced Threat Protection
-   Azure Advanced Threat Protection 
-   Microsoft Cloud App Security
-   Microsoft Defender Advanced Threat Protection


## <a name="configure-office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection configureren
>[!NOTE]
>Sla deze stap over als u Office 365 Advanced Threat Protection al hebt ingeschakeld. 

Er is een PowerShell-module genaamd *Office 365 Advanced Threat Protection recommended configuration Analyzer (Orca)* waarmee enkele van deze instellingen kunnen worden vastgesteld. Als u een beheerder van de Tenant uitvoert, kunt u met Get-ORCAReport een beoordeling maken van de antispam, anti-spam en andere instellingen voor bericht hygiëne. U kunt deze module downloaden van https://www.powershellgallery.com/packages/ORCA/ . 

1. Ga naar de [beveiligings & beleid voor nalevings centrum van Office 365](https://protection.office.com/homepage)  >  **Threat management**  >  **Policy**.
![Afbeelding of_Office 365 beveiligings & beleidsregels voor het beleid voor nalevings centrum](../../media/mtp-eval-32.png) <br>
 
2. Klik op **ATP anti-phishing**, selecteer **maken** en vul de Beleidsnaam en-beschrijving in. Klik op **Volgende**.
![Afbeelding of_Office 365 beveiligings & beleids pagina voor naleving van het nalevings centrum, waarin u uw beleid kunt benoemen](../../media/mtp-eval-33.png) <br>

>[!NOTE]
>Uw Advanced ATP anti phishingfilter-beleid bewerken. Wijzig de **Geavanceerde fraude drempel** in **2-agressief**.
<br>

3. Klik op het vervolgkeuzemenu **een voorwaarde toevoegen** en selecteer uw domein (en) als domein van de ontvanger. Klik op **Volgende**.
![Afbeelding of_Office 365 beveiligings & beleid voor naleving van het anti-phishingfilter waarop u een voorwaarde voor de toepassing kunt toevoegen](../../media/mtp-eval-34.png) <br>
 
4. Controleer uw instellingen. Klik op **dit beleid maken** om te bevestigen. 
![Afbeelding of_Office 365 beveiligings & beleidsregels voor nalevings centrum waar u de instellingen kunt controleren en klikt u op de knop dit beleid maken](../../media/mtp-eval-35.png) <br>
 
5. Selecteer **veilige ATP-bijlagen** en schakel de optie **ATP voor SharePoint, OneDrive en Microsoft teams inschakelen in** .  
![Afbeelding of_Office 365 beveiligings & compliance Center waarop u ATP kunt inschakelen voor SharePoint, OneDrive en Microsoft teams](../../media/mtp-eval-36.png) <br>

6. Klik op het pictogram + om een nieuw beleid voor veilige bijlagen te maken, wanneer u dit wilt toepassen als het domein van de geadresseerde voor uw domeinen. Klik op **Opslaan**.
![Afbeelding of_Office 365 beveiligings & compliance Center-pagina waar u een nieuw beleid voor het maken van een veilige bijlage kunt maken](../../media/mtp-eval-37.png) <br>
 
7. Vervolgens selecteert u het beleid voor **veilige koppelingen voor vrije verbindingen** en klikt u op het potloodpictogram om het standaardbeleid te bewerken.

8. Zorg ervoor dat de optie **niet bijhouden wanneer gebruikers op optie voor veilige koppelingen klikken** niet is geselecteerd, terwijl de andere opties zijn geselecteerd. Zie [instellingen voor veilige koppelingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) voor meer informatie. Klik op **Opslaan**. 
![Afbeelding of_Office 365 beveiligings & compliance Center waarin wordt aangegeven dat de optie niet wordt bijgehouden wanneer gebruikers op veilig klikken niet is geselecteerd.](../../media/mtp-eval-38.png) <br>

9. Selecteer vervolgens het **anti-malwarebeleid** , selecteer het standaardbeleid en kies het potloodpictogram.

10. Klik op **instellingen** en selecteer **Ja en gebruik de standaard Meldingstekst om het** detecteren van **malware**te activeren. Schakel het **filter common Attachment types** in. Klik op **Opslaan**.
<br>![Afbeelding of_Office 365 beveiligings & pagina nalevings centrum waarin wordt aangegeven dat de antwoord op de malware-detectie is ingeschakeld met standaard melding en dat het filter common Attachment types is ingeschakeld.](../../media/mtp-eval-39.png) <br>
  
11. Ga naar het [Office 365-beveiligings & compliance](https://protection.office.com/homepage)  >  **Search**  >  **audit log Search** en Schakel controle in.  
![Afbeelding of_Office 365 beveiligings & compliance Center waarop u de zoekopdracht in het audit logboek kunt inschakelen](../../media/mtp-eval-40.png) <br>

12. Integreer Office 365 ATP met Microsoft Defender ATP. Ga naar de [beveiligings & van het compliance-Beheercentrum van Office 365](https://protection.office.com/homepage)  >  **Threat management**  >  **Explorer** en selecteer **WDATP instellingen** in de rechterbovenhoek van het scherm. Schakel in het dialoogvenster verbinding met Microsoft Defender ATP de optie **verbinding maken met Windows ATP**in.
![Afbeelding of_Office 365 beveiligings & compliance Center, waarop u de Windows Defender ATP-verbinding kunt inschakelen](../../media/mtp-eval-41.png) <br>

## <a name="configure-azure-advanced-threat-protection"></a>Azure Advanced Threat Protection configureren
>[!NOTE]
>Sla deze stap over als u Azure Advanced Threat Protection al hebt ingeschakeld


1. Ga naar [Microsoft 365 Beveiligingscentrum](https://security.microsoft.com/info) > Selecteer **meer bronnen**  >  **Azure Advanced Threat Protection**.
![Of_Microsoft pagina van het Beveiligingscentrum van 365 waarbij er een optie is om Azure Advanced Threat Protection te openen](../../media/mtp-eval-42.png) <br>

2. Klik op **maken** om de wizard van Azure Advanced Threat Protection te starten. 
<br>![Afbeelding of_Azure pagina van de wizard geavanceerde beveiliging van bedreiging waarop u moet klikken op de knop maken](../../media/mtp-eval-43.png) <br>

3. Kies **een gebruikersnaam en wachtwoord opgeven om verbinding te maken met uw Active Directory-forest**.  
![Afbeelding of_Azure welkomstpagina van Advanced Threat Protection](../../media/mtp-eval-44.png) <br>

4. Voer uw on-premises Active Directory-referenties in. Dit kan elk gebruikersaccount zijn met leestoegang tot Active Directory.
![Afbeelding of_Azure pagina met adreslijstservices van Advanced Threat Protection, waar u uw referenties moet invoeren](../../media/mtp-eval-45.png) <br>

5. Kies vervolgens **Update sensoren** en zet bestand over naar uw domeincontroller. 
![Afbeelding of_Azure pagina Geavanceerde beveiliging van bedreiging, waarop u de instellingen voor de Download sensor kunt selecteren](../../media/mtp-eval-46.png) <br>

6. Voer de installatie van de Azure ATP-sensor uit en voer de wizard uit.
<br>![Afbeelding of_Azure pagina Geavanceerde beveiliging tegen bedreigingen waarop u moet klikken op volgende om de wizard Azure ATP-sensor te volgen](../../media/mtp-eval-47.png) <br>
 
7. Klik op **volgende** bij het implementatietype van de sensor.
<br>![Afbeelding of_Azure pagina Geavanceerde beveiliging van bedreiging waarop u moet klikken op volgende om naar de volgende pagina te gaan](../../media/mtp-eval-48.png) <br>
 
8. Kopieer de toegangscode omdat u deze moet typen, naast de wizard.
![Of_the afbeelding van de pagina met sensoren waar u de toegangstoets moet typen die u moet typen op de volgende pagina van de wizard Setup van Azure ATP-sensor](../../media/mtp-eval-49.png) <br>
 
9. Kopieer de toegangstoets in de wizard en klik op **installeren**. 
<br>![Afbeelding of_Azure pagina met geavanceerde Bedreigingsbeveiliging Azure ATP-sensor, waar u de toegangscode moet invoeren en klik vervolgens op de knop installeren.](../../media/mtp-eval-50.png) <br>

10. Gefeliciteerd, u hebt Azure Advanced Threat Protection geconfigureerd op uw domeincontroller.
![Afbeelding of_Azure geavanceerde Bedreigingsbeveiliging Azure ATP-sensor wizard Installatie voltooien waarbij u op de knop Voltooien klikt](../../media/mtp-eval-51.png) <br>
 
11. Selecteer in de sectie instellingen van [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) de optie **Windows Defender ATP**en zet vervolgens de wisselknop. Klik op **Opslaan**. 
![Afbeelding of_the pagina instellingen van Azure Azure ATP waarop u de wisselknop Windows Defender ATP moet inschakelen](../../media/mtp-eval-52.png) <br>

>[!NOTE]
>Windows Defender ATP is opnieuw aangemerkt als Microsoft Defender ATP. Wijzigingen die u in alle portals aanbrengt, worden doorgevoerd in de consistentie.


## <a name="configure-microsoft-cloud-app-security"></a>Beveiligingsupdates voor Microsoft Cloud app configureren
>[!NOTE]
>Sla deze stap over als u de beveiligingsversie van de Microsoft Cloud-app al hebt ingeschakeld. 

1. Ga naar het [Microsoft 365-Beveiligingscentrum](https://security.microsoft.com/info)voor  >  **meer informatie**over beveiliging van de  >  **Microsoft Cloud-app**.
![Pagina of_Microsoft 365 Beveiligingscentrum, waarop u de Microsoft Cloud app Card kunt zien en moet klikken op de knop openen](../../media/mtp-eval-53.png) <br>

2. Als u de informatie wilt hebben over het integreren van Azure ATP, selecteert u **Azure ATP Data Integration inschakelen**. 
<br>![Afbeelding of_the informatie vraagt om Azure ATP te integreren waarbij u de koppeling Azure ATP-gegevensintegratie moet selecteren](../../media/mtp-eval-54.png) <br>

>[!NOTE]
>Als u deze vraag niet ziet, betekent dit dat uw Azure ATP-gegevensintegratie al is ingeschakeld. Als u dat nog niet weet, neemt u contact op met uw IT-beheerder om te bevestigen. 

3. Ga naar **instellingen**, schakel de wisselknop **Azure ATP-integratie** in en klik op **Opslaan**. 
![Afbeelding of_the pagina instellingen waarop u de wisselknop Azure ATP-integratie moet inschakelen en klik op opslaan](../../media/mtp-eval-55.png) <br>
>[!NOTE]
>Voor nieuwe exemplaren van Azure ATP wordt deze schakeloptie voor integratie automatisch ingeschakeld. Controleer of de Azure ATP-integratie is ingeschakeld voordat u verder gaat met de volgende stap.
 
4. Selecteer onder de instellingen voor Cloud detectie de optie **Microsoft Defender ATP-integratie**en schakel vervolgens de integratie in. Klik op **Opslaan**.
![Afbeelding of_the Microsoft Defender ATP-pagina waar het selectievakje niet-goedgekeurde apps blokkeren onder Microsoft Defender ATP-integratie is geselecteerd. Selecteer opslaan.](../../media/mtp-eval-56.png) <br>

5. Selecteer onder instellingen voor Cloud detectie de optie **gebruikers verrijking**en schakel vervolgens integratie met Azure Active Directory in.
![Afbeelding van de sectie voor het verrijking van gebruikers waarbij het selectievakje verrijkte gebruikers-id's met Azure Active Directory-gebruikersnamen is geselecteerd](../../media/mtp-eval-57.png) <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection configureren
>[!NOTE]
>Sla deze stap over als u Microsoft Defender Advanced Threat Protection al hebt ingeschakeld.

1. Ga naar het [Microsoft 365-Beveiligingscentrum](https://security.microsoft.com/info)  >  **meer bronnen**  >  **Microsoft Defender-Beveiligingscentrum**. Klik op **openen**.
<br>![De optie afbeelding of_Microsoft Defender-Beveiligingscentrum op de pagina Microsoft 365 Security Center](../../media/mtp-eval-58.png) <br>
 
2. Volg de wizard Microsoft Defender Advanced Threat Protection. Klik op **Volgende**. 
<br>![Pagina of_the van de welkomst wizard van het Microsoft Defender-Beveiligingscentrum](../../media/mtp-eval-59.png) <br>

3. Kies op basis van de gewenste locatie voor gegevensopslag, het bewaarbeleid voor de gegevens, de organisatie grootte en opt-in voor Voorbeeldfuncties. 
<br>![Afbeelding of_the pagina voor het selecteren van het land voor de opslag van de gegevens, het bewaarbeleid en de grootte van de organisatie. Klik op volgende wanneer u klaar bent met selecteren.](../../media/mtp-eval-60.png) <br>
>[!NOTE]
>U kunt een aantal instellingen, zoals de opslaglocatie van de gegevens, achteraf niet wijzigen. 
<br>

Klik op **Volgende**. 

4. Klik op **Doorgaan** om uw Microsoft Defender ATP-Tenant te richten.
<br>![Afbeelding of_the pagina waarin u wordt gevraagd Klik op de knop Doorgaan om een Cloud exemplaar te maken](../../media/mtp-eval-61.png) <br>

5. Haal uw eindpunten binnen via Groepsbeleid, Microsoft Endpoint Manager of door een lokaal script uit te voeren in Microsoft Defender ATP. Voor de eenvoud wordt in deze handleiding het lokale script gebruikt.

6. Klik op **pakket downloaden** en kopieer het onboarding-script naar uw eindpunt (en).  
<br>![Afbeelding of_page u wordt gevraagd op de knop pakket downloaden te klikken om het onboarding-script naar uw eindpunt of eindpunten te kopiëren.](../../media/mtp-eval-62.png) <br>

7. Voer op het eindpunt het onboarding-script uit als beheerder en kies Y.
<br>![Afbeelding of_the commandline waarbij u het onboarding-script uitvoert en kies Y om door te gaan](../../media/mtp-eval-63.png) <br>

8. Gefeliciteerd, u hebt het eerste eindpunt geboardd.  
<br>![Afbeelding of_the commandline waarbij u de bevestiging ontvangt dat u het eerste eindpunt hebt binnengebracht. Druk op een toets om door te gaan](../../media/mtp-eval-64.png) <br>

9. Kopieer-de detectietest wordt in de wizard van Microsoft Defender ATP geplakt.
<br>![Afbeelding of_the een detectietest stap uitvoeren waarbij u op kopiëren klikt om het opsporings testscript te kopiëren dat u in de opdrachtprompt moet plakken](../../media/mtp-eval-65.png) <br>

10. Kopieer het PowerShell-script naar een opdrachtprompt met verhoogde bevoegdheid en voer deze opdracht uit. 
<br>![Afbeelding of_command aanwijzing waar u het PowerShell-script moet kopiëren naar een opdrachtprompt met verhoogde bevoegdheid en deze kunt uitvoeren](../../media/mtp-eval-66.png) <br>

11. Selecteer in de wizard aan de **slag met Microsoft Defender ATP** .
<br>![Afbeelding of_the bevestigingsprompt van de wizard, waarop u moet klikken op beginnen met Microsoft Defender ATP](../../media/mtp-eval-67.png) <br>
 
12. Ga naar het [Microsoft Defender-Beveiligingscentrum](https://securitycenter.windows.com/). Ga naar **instellingen** en selecteer **geavanceerde functies**. 
<br>![Afbeelding of_Microsoft menu instellingen van het Beveiligingscentrum van Defender, waarin u geavanceerde functies moet selecteren](../../media/mtp-eval-68.png) <br>

13. Schakel de integratie met **Azure Advanced Threat Protection**in.  
<br>![Afbeelding van geavanceerde functies in de of_Microsoft van het Defender-Beveiligingscentrum, de optie voor de geavanceerde beveiliging van de optie Azure-beveiliging van bedreiging die u moet inschakelen](../../media/mtp-eval-69.png) <br>

14. Schakel de integratie met **Office 365 Threat Intelligence**in.
<br>![Afbeelding van geavanceerde functies in de of_Microsoft van het Defender-Beveiligingscentrum, de optie Office 365 Threat Intelligence, die u moet inschakelen](../../media/mtp-eval-70.png) <br>

15. Schakel integratie met **Microsoft Cloud app Security**in.
<br>![Afbeelding of_Microsoft geavanceerde functies in het Beveiligingscentrum van Defender, de optie voor beveiliging van de Microsoft Cloud-app, die u moet inschakelen](../../media/mtp-eval-71.png) <br>

16. Schuif omlaag en klik op **Voorkeuren opslaan** om de nieuwe integraties te bevestigen.
<br>![Afbeelding of_Save knop Voorkeuren waarop u moet klikken](../../media/mtp-eval-72.png) <br>

## <a name="start-the-microsoft-threat-protection-service"></a>Microsoft Threat Protection-service starten
>[!NOTE]
>Vanaf 1 juni 2020 maakt Microsoft automatisch functies in Microsoft Threat Protection voor alle in aanmerking komende tenants. Zie het [artikel Microsoft Tech Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) voor meer informatie over licenties. 
<br>

Ga naar [Microsoft 365 Beveiligingscentrum](https://security.microsoft.com/homepage). Ga naar **instellingen** en selecteer vervolgens **Microsoft Threat Protection**.
<br>![Schermafbeelding van de optie voor beveiliging van de optie afbeelding of_Microsoft bedreiging op de pagina instellingen van Microsoft 365-Beveiligingscentrum ](../../media/mtp-eval-72b.png) <br>

Zie [Microsoft Threat Protection inschakelen](mtp-enable.md)voor uitgebreide informatie. 

Gefeliciteerd! U hebt zojuist een proefabonnement voor Microsoft Threat Protection gemaakt, of pilot omgeving. U kunt nu vertrouwd raken met de gebruikersinterface van Microsoft Threat Protection. Lees wat u kunt leren en leer hoe u elk dashboard gebruikt voor uw dagelijkse beveiligingsbewerkingen: [Microsoft Threat Protection Interactive Guide](https://aka.ms/MTP-Interactive-Guide).

Vervolgens kunt u een aanval simuleren en kijken hoe de functies voor cross product detectie, waarschuwingen maken en automatisch reageren op een aanval met een bestand op een eindpunt.

## <a name="next-step"></a>Volgende stap
|![Simulatie fase aanval](../../media/mtp/run-sim.png) <br>[Simulatie fase aanval](mtp-pilot-simulate.md) | Voer de simulatie van een aanval uit voor de prototypeomgeving Microsoft Threat Protection.
|:-------|:-----|
