---
title: Pijlers voor microsoft threat protection configureren voor de proeflabomgeving
description: Pijlers voor microsoft threat protection configureren, Office 365 ATP, Azure ATP, Microsoft Cloud App Security en Microsoft Defender ATP voor uw proeflabomgeving
keywords: microsoft Threat Protection-proefversie configureren, microsoft threat protection-proefconfiguratie, microsoft threat protection-pijlers configureren, pijlers voor Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 8a435b220343bd0353f2e0ef85ddf856ebf3e8aa
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049938"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-environment"></a>Pijlers voor Microsoft Threat Protection configureren voor uw proeflabomgeving

**Van toepassing op:**
- Microsoft Threat Protection


Het maken van een Microsoft Threat Protection-proeflabomgeving en het implementeren ervan is een proces in drie fasen:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Uw Microsoft Threat Protection-proeflabomgeving voorbereiden" />
      <br/>Fase 1: Voorbereiden</a><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Uw Microsoft Threat Protection-proefomgeving instellen" />
      <br/>Fase 2: Setup</a><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Configureer elke Microsoft Threat Protection-pijler voor uw Microsoft Threat Protection-proeflabomgeving en on-board-eindpunten" />
      <br/>Fase 3: & onboard configureren</a><br>
</td>


  </tr>
</table>

U bevindt zich momenteel in de configuratiefase.


Voorbereiding is de sleutel tot een succesvolle implementatie. In dit artikel wordt u begeleid op de punten die u moet overwegen als u zich voorbereidt op de implementatie van Microsoft Defender ATP.


## <a name="microsoft-threat-protection-pillars"></a>Pijlers voor Microsoft Threat Protection
Microsoft Threat Protection bestaat uit vier pijlers. Hoewel één pijler al waarde kan bieden aan de beveiliging van uw netwerkorganisatie, biedt het inschakelen van de vier pijlers van Microsoft Threat Protection uw organisatie de meeste waarde.

![Image of_Microsoft Threat Protection-oplossing voor gebruikers, Azure Advanced Threat Protection, voor endpoints Microsoft Defender Advanced Threat Protection, voor cloud-apps, Microsoft Cloud App Security en voor gegevens, Office 365 Advanced Threat Protection  ](../../media/mtp-eval-31.png) <br>

In deze sectie u het volgende configureren:
-   Office 365 Advanced Threat Protection
-   Azure Advanced Threat Protection 
-   Microsoft Cloud App Security
-   Microsoft Defender Advanced Threat Protection


## <a name="configure-office-365-advanced-threat-protection"></a>Geavanceerde bedreigingsbeveiliging van Office 365 configureren
>[!NOTE]
>Sla deze stap over als u Office 365 Advanced Threat Protection al hebt ingeschakeld. 

Er is een PowerShell-module genaamd de *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* die helpt bij het bepalen van een aantal van deze instellingen. Wanneer deze als beheerder in uw tenant wordt uitgevoerd, helpt get-ORCAReport bij het genereren van een beoordeling van de instellingen voor antispam, anti-phish en andere instellingen voor berichthygiëne. U deze module downloaden van https://www.powershellgallery.com/packages/ORCA/ . 

1. Navigeer naar het beleid [voor het beheer van](https://protection.office.com/homepage)& Compliance  >  **Center- beschermingsbeheer**  >  **Policy**.
![Image of_Office 365 Security & Compliance Center Threat management policy page](../../media/mtp-eval-32.png) <br>
 
2. Klik **op ATP-antiphishing,** selecteer **Maken** en vul de beleidsnaam en -beschrijving in. Klik op **Volgende**.
![Afbeelding of_Office 365 Pagina & compliance center-beleidspagina waar u uw beleid benoemen](../../media/mtp-eval-33.png) <br>

>[!NOTE]
>Bewerk uw geavanceerde ATP-antiphishingbeleid. Geavanceerde **phishingdrempel wijzigen** in **2 - Agressief.**
<br>

3. Klik **op** het vervolgkeuzemenu Een voorwaarde toevoegen en selecteer uw domein(en) als geadresseerdedomein. Klik op **Volgende**.
![Afbeelding of_Office 365 Security & Compliance Center anti-phishing beleidspagina waar u een voorwaarde voor de toepassing toevoegen](../../media/mtp-eval-34.png) <br>
 
4. Bekijk je instellingen. Klik **op Dit beleid maken** om dit te bevestigen. 
![Afbeelding of_Office 365 Pagina voor beveiligingsprogramma & Compliance Center waar u uw instellingen bekijken en op de knop Dit beleid maken klikken](../../media/mtp-eval-35.png) <br>
 
5. Selecteer **ATP Safe-bijlagen** en selecteer de optie **ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams.**  
![Afbeelding of_Office 365 pagina Beveiliging & Compliance Center waar u ATP voor SharePoint, OneDrive en Microsoft Teams inschakelen](../../media/mtp-eval-36.png) <br>

6. Klik op het +-pictogram om een nieuw beleid voor veilige bijlagen te maken en het als geadresseerderdomein toe te passen op uw domeinen. Klik op **Opslaan**.
![Afbeelding of_Office 365-pagina Beveiliging & Compliance Center waar u een nieuw beveiligingsbeleid maken](../../media/mtp-eval-37.png) <br>
 
7. Selecteer vervolgens het **atp-beleid voor veilige koppelingen** en klik vervolgens op het potloodpictogram om het standaardbeleid te bewerken.

8. Zorg ervoor dat de optie **Niet volgen wanneer gebruikers op veilige koppelingen klikken,** niet is geselecteerd, terwijl de rest van de opties is geselecteerd. Zie [Instellingen voor veilige koppelingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) voor meer informatie. Klik op **Opslaan**. 
![Afbeelding of_Office 365 Pagina Beveiliging & Compliance Center waaruit blijkt dat de optie Niet bijhouden wanneer gebruikers op safe klikken, niet is geselecteerd](../../media/mtp-eval-38.png) <br>

9. Selecteer vervolgens het **antimalwarebeleid,** selecteer de standaardinstelling en kies het potloodpictogram.

10. Klik **op Instellingen** en selecteer Ja en gebruik de **standaardmeldingstekst** om **malwaredetectiereactie**in te schakelen. Schakel het **filter Algemene bijlagetypen** in. Klik op **Opslaan**.
<br>![Afbeelding of_Office 365 Pagina Beveiliging & Compliance Center waaruit blijkt dat de reactie op malwaredetectie is ingeschakeld met standaardmelding en het filter voor algemene bijlagetypen is ingeschakeld](../../media/mtp-eval-39.png) <br>
  
11. Navigeer naar [Office 365 Security & Search](https://protection.office.com/homepage)  >  **Audit-logboekcontrole**van het Compliance Center en schakel Controle  >  **Audit log search** in.  
![Afbeelding of_Office 365-pagina Beveiliging & Compliance Center waar u de zoekopdracht voor controlelogboek inschakelen](../../media/mtp-eval-40.png) <br>

12. Integreer Office 365 ATP met Microsoft Defender ATP. Navigeer naar [Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat  >  **Management**  >  **Explorer** en selecteer **WDATP-instellingen** in de rechterbovenhoek van het scherm. Schakel verbinding **maken met Windows ATP**in het dialoogvenster Microsoft Defender ATP in .
![Afbeelding of_Office 365-pagina Beveiliging & Compliance Center waar u de ATP-verbinding van Windows Defender inschakelen](../../media/mtp-eval-41.png) <br>

## <a name="configure-azure-advanced-threat-protection"></a>Azure Advanced Threat Protection configureren
>[!NOTE]
>Sla deze stap over als u Azure Advanced Threat Protection al hebt ingeschakeld


1. Navigeer naar [Microsoft 365 Security Center](https://security.microsoft.com/info) > selecteer Meer **resources**Azure Advanced  >  **Threat Protection**.
![Afbeelding of_Microsoft pagina 365 Security Center waar een optie is om Azure Advanced Threat Protection te openen](../../media/mtp-eval-42.png) <br>

2. Klik **op Maken** om de wizard Azure Advanced Threat Protection te starten. 
<br>![Afbeelding of_Azure wizard Geavanceerde bedreigingsbeveiligingpagina waar u op knop Maken moet klikken](../../media/mtp-eval-43.png) <br>

3. Kies **Een gebruikersnaam en wachtwoord opgeven om verbinding te maken met uw Active Directory-forest**.  
![Welkomstpagina of_Azure Geavanceerde bedreigingsbescherming](../../media/mtp-eval-44.png) <br>

4. Voer uw on-premises active directory-referenties in. Dit kan elk gebruikersaccount zijn dat leestoegang tot Active Directory heeft.
![Afbeelding of_Azure pagina met Geavanceerde Threat Protection Directory-services waar u uw referenties moet plaatsen](../../media/mtp-eval-45.png) <br>

5. Kies vervolgens **Sensor setup downloaden** en het bestand overzetten naar uw domeincontroller. 
![Afbeelding of_Azure pagina voor geavanceerde bedreigingsbescherming waar u De installatie van downloadsensoren selecteren](../../media/mtp-eval-46.png) <br>

6. Voer de Azure ATP Sensor Setup uit en begin met het volgen van de wizard.
<br>![Afbeelding of_Azure pagina Geavanceerde bedreigingsbeveiliging waarop u naast de wizard Azure ATP-sensor moet klikken om de wizard Azure ATP-sensor te volgen](../../media/mtp-eval-47.png) <br>
 
7. Klik **op Volgende** bij het type sensorimplementatie.
<br>![Afbeelding of_Azure pagina Geavanceerde bedreigingsbeveiliging waarop u naast de wizard Azure ATP-sensor moet klikken om de wizard Azure ATP-sensor te volgen](../../media/mtp-eval-48.png) <br>
 
8. Kopieer de toegangssleutel zoals u deze vervolgens in de wizard moet invoeren.
![Afbeelding of_the pagina met sensoren waar u de toegangssleutel moet kopiëren die u moet invoeren op de volgende wizard Azure ATP-sensorinstellendingspagina](../../media/mtp-eval-49.png) <br>
 
9. Kopieer de toegangssleutel naar de wizard en klik op **Installeren**. 
<br>![Afbeelding of_Azure wizard Advanced Threat Protection Azure ATP-sensorpagina waar u de toegangssleutel moet bieden en vervolgens op de installatieknop klikt](../../media/mtp-eval-50.png) <br>

10. Gefeliciteerd, u hebt Azure Advanced Threat Protection geconfigureerd op uw domeincontroller.
![Image of_Azure Advanced Threat Protection Azure ATP sensor wizard installation completion where you should click the finish button Image of_Azure Advanced Threat Protection Azure ATP sensor wizard installation completion where you should click the finish button Image of_Azure Advanced Threat Protection Azure ATP sensor wizard installation completion where you should click the finish button Image](../../media/mtp-eval-51.png) <br>
 
11. Selecteer onder de sectie [Azure Azure ATP-instellingen](https://go.microsoft.com/fwlink/?linkid=2040449) de optie **Windows Defender ATP**en schakel de schakelaar in. Klik op **Opslaan**. 
![Afbeelding of_the Azure Azure ATP-instellingenpagina waar u de Windows Defender ATP-schakelaar moet inschakelen](../../media/mtp-eval-52.png) <br>

>[!NOTE]
>Windows Defender ATP is omgedoopt tot Microsoft Defender ATP. Rebranding veranderingen in al onze portalen worden uitgerold voor consistentie.


## <a name="configure-microsoft-cloud-app-security"></a>Beveiliging van Microsoft Cloud App configureren
>[!NOTE]
>Sla deze stap over als u microsoft cloud app-beveiliging al hebt ingeschakeld. 

1. Navigeer naar [Microsoft 365 Security Center](https://security.microsoft.com/info)Meer  >  **bronnen**Microsoft Cloud  >  **App Security**.
![Afbeelding of_Microsoft pagina 365 Security Center waar u Microsoft Cloud App-kaart zien en op de knop openen klikt](../../media/mtp-eval-53.png) <br>

2. Selecteer Azure **ATP-gegevensintegratie inschakelen**bij de informatieprompt voor de integratie van Azure ATP. 
<br>![Afbeelding of_the informatieprompt om Azure ATP te integreren, waarbij u de koppeling Azure ATP-gegevensintegratie moet selecteren](../../media/mtp-eval-54.png) <br>

>[!NOTE]
>Als u deze prompt niet ziet, kan dit betekenen dat uw Azure ATP-gegevensintegratie al is ingeschakeld. Als u het echter niet zeker weet, neemt u contact op met uw IT-beheerder om dit te bevestigen. 

3. Ga naar **Instellingen,** schakel de inschakelschakelschakelschakelschakeling van Azure **ATP-integratie** in en klik op **Opslaan**. 
![Afbeelding of_the instellingenpagina waar u de azure ATP-integratie moet inschakelen en vervolgens op opslaan moet klikken](../../media/mtp-eval-55.png) <br>
>[!NOTE]
>Voor nieuwe Azure ATP-exemplaren wordt deze integratieknop automatisch ingeschakeld. Controleer of uw Azure ATP-integratie is ingeschakeld voordat u naar de volgende stap gaat.
 
4. Selecteer onder de instellingen voor clouddetectie de optie **Microsoft Defender ATP-integratie**en schakel de integratie in. Klik op **Opslaan**.
![Afbeelding of_the Microsoft Defender ATP-pagina waarop het selectievakje niet-goedgekeurde apps blokkeren onder Microsoft Defender ATP-integratie is geselecteerd. Klik op opslaan.](../../media/mtp-eval-56.png) <br>

5. Selecteer onder Instellingen voor clouddetectie de optie **Gebruikersverrijking**en schakel de integratie met Azure Active Directory in.
![Afbeelding van de sectie Gebruikersverrijking waarin het selectievakje Gedetecteerde gebruikers-id's verrijken met Azure Active Directory-gebruikersnamen is geselecteerd](../../media/mtp-eval-57.png) <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a>Geavanceerde bedreigingsbeveiliging van Microsoft Defender configureren
>[!NOTE]
>Sla deze stap over als u microsoft Defender Advanced Threat Protection al hebt ingeschakeld.

1. Navigeer naar [Microsoft 365 Security Center](https://security.microsoft.com/info)Meer  >  **bronnen**Microsoft Defender  >  **Security Center**. Klik op **Openen**.
<br>![Afbeelding of_Microsoft Defender Security Center op de pagina Microsoft 365 Security Center](../../media/mtp-eval-58.png) <br>
 
2. Volg de wizard Geavanceerde bedreigingsbeveiliging van Microsoft Defender. Klik op **Volgende**. 
<br>![Afbeelding of_the welkomstwizardpagina van Microsoft Defender Security Center](../../media/mtp-eval-59.png) <br>

3. Kies op basis van de locatie van uw gewenste gegevensopslag, beleid voor gegevensbewaring, organisatiegrootte en opt-in voor voorbeeldfuncties. 
<br>![Afbeelding of_the pagina om uw land voor gegevensopslag, bewaarbeleid en organisatiegrootte te selecteren. Klik op volgende wanneer u klaar bent met selecteren.](../../media/mtp-eval-60.png) <br>
>[!NOTE]
>U sommige instellingen, zoals de locatie van de gegevensopslag, achteraf niet wijzigen. 
<br>

Klik op **Volgende**. 

4. Klik **op Doorgaan** en hiermee wordt uw Microsoft Defender ATP-tenant invoorziening getroffen.
<br>![Afbeelding of_the pagina met de vraag of u op de knop Doorgaan klikt om uw cloud-exemplaar te maken](../../media/mtp-eval-61.png) <br>

5. Sluit uw eindpunten aan via groepsbeleid, Microsoft Endpoint Manager of door een lokaal script uit te voeren op Microsoft Defender ATP. Voor de eenvoud maakt deze handleiding gebruik van het lokale script.

6. Klik **op Pakket downloaden** en kopieer het onboarding-script naar uw eindpunt(en).  
<br>![Afbeelding of_page u vraagt op de knop Pakket downloaden klikken om het onboarding-script naar uw eindpunt of eindpunten te kopiëren](../../media/mtp-eval-62.png) <br>

7. Voer op uw eindpunt het onboarding-script uit als administrator en kies Y.
<br>![Afbeelding of_the commandline waar u het onboarding-script uitvoert en Y kiest om verder te gaan](../../media/mtp-eval-63.png) <br>

8. Gefeliciteerd, je hebt je eerste eindpunt in gebruik.  
<br>![Afbeelding of_the commandline waar u de bevestiging krijgt dat u uw eerste eindpunt hebt ingebouwde. Druk op elke toets om door te gaan](../../media/mtp-eval-64.png) <br>

9. Kopieer-plak de detectietest van de wizard Microsoft Defender ATP.
<br>![Afbeelding of_the een detectietest stap uit te voeren waarbij u op Kopiëren moet klikken om het detectietestscript te kopiëren dat u in de opdrachtprompt moet plakken](../../media/mtp-eval-65.png) <br>

10. Kopieer het PowerShell-script naar een opdrachtprompt met verhoogde bevoegdheid en voer het uit. 
<br>![Afbeelding of_command vragen waar u het PowerShell-script naar een verhoogde opdrachtprompt moet kopiëren en deze moet uitvoeren](../../media/mtp-eval-66.png) <br>

11. Selecteer **Microsoft Defender ATP starten in** de wizard.
<br>![Afbeelding of_the bevestigingsprompt van de wizard waar u op Start met Microsoft Defender ATP moet klikken](../../media/mtp-eval-67.png) <br>
 
12. Ga naar het [Microsoft Defender Security Center](https://securitycenter.windows.com/). Ga naar **Instellingen** en selecteer **Geavanceerde functies**. 
<br>![Afbeelding of_Microsoft menu Instellingen van Defender Security Center waarin u geavanceerde functies moet selecteren](../../media/mtp-eval-68.png) <br>

13. Schakel de integratie in met **Azure Advanced Threat Protection**.  
<br>![Image of_Microsoft Defender Security Center Geavanceerde functies, Azure Advanced Threat Protection optie schakelen die u moet inschakelen](../../media/mtp-eval-69.png) <br>

14. Schakel de integratie in met **Office 365 Threat Intelligence**.
<br>![Afbeelding of_Microsoft Defender Security Center Geavanceerde functies, Office 365 Threat Intelligence-optie die u moet inschakelen](../../media/mtp-eval-70.png) <br>

15. Schakel integratie met **Microsoft Cloud App Security**in .
<br>![Afbeelding of_Microsoft Defender Security Center Geavanceerde functies, Microsoft Cloud App Security optie schakelen die u moet inschakelen](../../media/mtp-eval-71.png) <br>

16. Schuif omlaag en klik op **Voorkeuren opslaan** om de nieuwe integraties te bevestigen.
<br>![Knop Afbeelding of_Save voorkeuren waarop u moet klikken](../../media/mtp-eval-72.png) <br>

## <a name="start-the-microsoft-threat-protection-service"></a>Microsoft Threat Protection-service starten
>[!NOTE]
>Vanaf 1 juni 2020 schakelt Microsoft automatisch Microsoft Threat Protection-functies in voor alle in aanmerking komende tenants. Zie dit [Microsoft Tech Community-artikel over licentiegeschiktheid](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) voor meer informatie. 
<br>

Ga naar [Microsoft 365 Security Center](https://security.microsoft.com/homepage). Navigeer naar **Instellingen** en selecteer **Microsoft Threat Protection**.
<br>![Image of_Microsoft Threat Protection option screenshot van de pagina Microsoft 365 Security Center Settings](../../media/mtp-eval-72b.png) <br>

Zie [Microsoft-bedreigingsbeveiliging inschakelen](mtp-enable.md)voor een uitgebreidere richtlijnen. 

Gefeliciteerd! U hebt zojuist uw Microsoft Threat Protection-proeflabomgeving gemaakt! Nu u vertrouwd raken met de Microsoft Threat Protection-gebruikersinterface! Bekijk wat u leren en hoe u elke dashboards gebruiken voor uw dagelijkse beveiligingstaken: [interactieve handleiding voor Microsoft Threat Protection](https://aka.ms/MTP-Interactive-Guide).

Vervolgens u een aanval simuleren en zien hoe de cross-productmogelijkheden detecteren, waarschuwingen maken en automatisch reageren op een bestandloze aanval op een eindpunt.

## <a name="next-steps"></a>Volgende stappen
[Een testwaarschuwing genereren](generate-test-alert.md).
