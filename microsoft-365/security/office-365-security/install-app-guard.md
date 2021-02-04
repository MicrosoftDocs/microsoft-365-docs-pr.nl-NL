---
title: Application Guard voor Office 365 voor beheerders
keywords: application guard, protection, isolation, isolated container, hardware isolation
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Haal het laatste nieuws op in hardware-isolatie. Voorkomen dat huidige en nieuwe aanvallen, zoals misbruik of schadelijke koppelingen, de productiviteit van werknemers en de bedrijfsbeveiliging verstoren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cf02f6776eb68537486b49c4fe45e8f88eeb38c6
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094877"
---
# <a name="application-guard-for-office-for-admins"></a>Application Guard voor Office voor beheerders

**Van toepassing op:** Word, Excel en PowerPoint voor Microsoft 365, Windows 10 Enterprise

Microsoft Defender Application Guard voor Office (Application Guard voor Office) helpt voorkomen dat niet-vertrouwde bestanden toegang krijgen tot vertrouwde bronnen, zodat uw bedrijf veilig blijft voor nieuwe en nieuwe aanvallen. In dit artikel worden beheerders bij het instellen van apparaten voor een preview van Application Guard voor Office beschreven. Het artikel bevat informatie over systeemvereisten en installatiestappen om Application Guard voor Office op een apparaat in teschakelen.

## <a name="prerequisites"></a>Vereisten

### <a name="minimum-hardware-requirements"></a>Minimale hardwarevereisten

* **CPU:** 64-bits, 4-cores (fysiek of virtueel), virtualisatieextensies (Intel VT-x OR AMD-V), Core i5-equivalent of hoger aanbevolen
* **Fysiek geheugen**: 8 GB RAM
* **Harde schijf:** 10 GB beschikbare ruimte op het systeemstation (SSD aanbevolen)

### <a name="minimum-software-requirements"></a>Minimale softwarevereisten

* **Windows 10**: Windows 10 Enterprise edition, Client Build versie 2004 (20H1) build 19041 of hoger
* **Office:** Office Current-kanaal build versie 2011 16.0.13530.10000 of hoger. Zowel 32 bits- als 64 bitsversies van Office worden ondersteund.
* **Updatepakket:** Windows 10 cumulatieve maandelijkse beveiligingsupdate [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

Raadpleeg de systeemvereisten voor Microsoft Defender Application Guard voor gedetailleerde [systeemvereisten.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard) Zie Overzicht van updatekanalen voor Microsoft 365 voor meer informatie over [Office-updatekanalen.](https://docs.microsoft.com/deployoffice/overview-update-channels)

### <a name="licensing-requirements"></a>Licentievereisten

* Microsoft 365 E5 of Microsoft 365 E5-beveiliging

## <a name="deploy-application-guard-for-office"></a>Application Guard implementeren voor Office

### <a name="enable-application-guard-for-office"></a>Application Guard inschakelen voor Office

1. Download en installeer **windows 10 cumulatieve maandelijkse beveiligingsupdates KB4571756.**

2. Selecteer **Microsoft Defender Application Guard onder** Windows-functies en selecteer **OK.** Als u de functie Application Guard inschakelen, wordt het systeem opnieuw opgestart. U kunt ervoor kiezen om nu opnieuw op te starten of na stap 3.

   ![Dialoogvenster Windows-onderdelen met AAG](../../media/ag03-deploy.png)

   De functie kan ook worden ingeschakeld door de volgende PowerShell-opdracht als administrator uit te voeren:

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. Zoek naar **Microsoft Defender Application Guard in de beheerde modus,** een groepsbeleid in beheersjablonen voor **computerconfiguratie \\ \\ Windows-onderdelen \\ Microsoft Defender Application Guard.** Schakel dit beleid in door de waarde onder Opties in te stellen als **2** of **3** en **vervolgens OK** of Toepassen te **selecteren.**

   ![AG inschakelen in beheerde modus](../../media/ag04-deploy.png)

   In plaats daarvan kunt u het bijbehorende CSP-beleid instellen:

   > OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** <br> Gegevenstype: **Geheel getal** <br> Waarde: **2**

4. Start het systeem opnieuw op.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>Diagnostische gegevens en & om volledige gegevens te verzenden

Deze stap zorgt ervoor dat Microsoft wordt bereikt met de gegevens die nodig zijn voor het identificeren en oplossen van problemen. Volg deze stappen om diagnostische gegevens in teschakelen op uw Windows-apparaat:

1. Open **Instellingen** vanuit het Startmenu.

   ![Startmenu](../../media/ag05-diagnostic.png)

2. Selecteer **Privacy in Windows-instellingen.** 

   ![Menu Windows-instellingen](../../media/ag06-diagnostic.png)

3. Selecteer onder Privacy de **optie Diagnostische & feedback** en selecteer **Optionele diagnostische gegevens.**

   ![Menu Diagnostische gegevens en feedback](../../media/ag07a-diagnostic.png)

Raadpleeg de diagnostische windows-gegevens in uw organisatie configureren voor meer informatie over het configureren van de diagnostische instellingen [van Windows.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Controleren of Application Guard voor Office is ingeschakeld en werkt

Start Word, Excel of PowerPoint op een apparaat waarop het beleid is geïmplementeerd voordat u bevestigt dat Application Guard voor Office is ingeschakeld. Zorg ervoor dat Office is geactiveerd. Mogelijk moet u uw werkidentiteit gebruiken om het Office-product eerst te activeren.

Als u wilt bevestigen dat Application Guard voor Office is ingeschakeld, start u Word, Excel of PowerPoint en opent u een niet-vertrouwd document. U kunt bijvoorbeeld een document openen dat is gedownload van internet of een e-mailbijlage van iemand buiten uw organisatie.

Wanneer u een niet-vertrouwd bestand voor het eerst opent, ziet u mogelijk een welkomstscherm van Office zoals in het volgende voorbeeld. Deze wordt mogelijk enige tijd weergegeven terwijl Application Guard voor Office wordt geactiveerd en het bestand wordt geopend. De volgende openen van niet-vertrouwde bestanden zouden sneller moeten zijn.

![Welkomstscherm van Office-app](../../media/ag08-confirm.png)

Bij het openen moet het bestand een paar visuele indicatoren weergeven dat het bestand is geopend in Application Guard voor Office:

* Een bijroep op het lint

  ![Documentbestand met kleine App Guard-notitie](../../media/ag09-confirm.png)

* Het toepassingspictogram met een schild op de taakbalk

  ![Pictogram op de taakbalk](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>Application Guard configureren voor Office

Office ondersteunt de volgende beleidsregels waarmee u de mogelijkheden van Application Guard voor Office kunt configureren. Dit beleid kan worden geconfigureerd via groepsbeleid of via de Office-cloudbeleidsservice.

> [!NOTE]
> Als u dit beleid configureert, kunnen sommige functies worden uitgeschakeld voor bestanden die worden geopend in Application Guard voor Office.

|Beleid|Beschrijving|
|---|---|
|Gebruik Application Guard niet voor Office|Als u dit beleid inschakelen, wordt in Word, Excel en PowerPoint de isolatiecontainer beveiligde weergave gebruikt in plaats van Application Guard voor Office. Dit beleid kan worden gebruikt om Application Guard tijdelijk uit te schakelen voor Office als er problemen zijn met het inschakelen van Het inschakelen voor Microsoft Edge.|
|Application Guard voor het maken van office-containers configureren|Dit beleid bepaalt of de Application Guard voor Office-container voor het isoleren van niet-vertrouwde bestanden vooraf is gemaakt voor betere run-time prestaties. Als u deze instelling inschakelen, kunt u het aantal dagen opgeven dat een container nog moet worden gemaakt of de container vooraf laten maken door de ingebouwde heuristische functie van Office.
|Kopiëren/plakken niet toestaan voor Office-documenten die zijn geopend in Application Guard voor Office|Als u dit beleid inschakelen, kan een gebruiker geen inhoud kopiëren en kopiëren uit een document dat is geopend in Application Guard voor Office naar een document dat daarbuiten is geopend.|
|Hardwareversnelling uitschakelen in Application Guard voor Office|Dit beleid bepaalt of Application Guard voor Office hardwareversnelling gebruikt om afbeeldingen weer te geven. Als u deze instelling inschakelen, maakt Application Guard voor Office gebruik van renderen op basis van software (CPU) en worden grafische stuurprogramma's van derden niet geladen en wordt er geen interactie mogelijk met verbonden grafische hardware.
|Niet-ondersteunde bestandstypenbeveiliging uitschakelen in Application Guard voor Office|Met dit beleid wordt bepaald of niet-ondersteunde bestandstypen worden geblokkeerd in Application Guard voor Office of dat de omleiding naar de beveiligde weergave wordt ingeschakeld.
|Camera- en microfoontoegang uitschakelen voor documenten die worden geopend in Application Guard voor Office|Als u dit beleid inschakelen, wordt de toegang van Office tot de camera en microfoon in Application Guard voor Office verwijderd.|
|Afdrukken beperken vanuit documenten die zijn geopend in Application Guard voor Office|Als u dit beleid inschakelen, beperkt u de printers waarmee een gebruiker kan afdrukken vanuit een bestand dat is geopend in Application Guard voor Office. U kunt dit beleid bijvoorbeeld gebruiken om gebruikers te beperken om alleen af te drukken naar PDF.|
|Voorkomen dat gebruikers Application Guard voor Office-beveiliging voor bestanden verwijderen|Als u dit beleid inschakelen, wordt de optie (binnen de Office-toepassingservaring) verwijderd om Application Guard uit te schakelen voor Office-beveiliging of om een bestand te openen buiten Application Guard voor Office. <p> **Opmerking:** Gebruikers kunnen dit beleid nog steeds omzeilen door de eigenschap Mark-of-the-Web handmatig uit het bestand te verwijderen of door een document naar een vertrouwde locatie te verplaatsen.|
|

> [!NOTE]
> Voor het volgende beleid moet de gebruiker zich afloggen en zich opnieuw aanmelden bij Windows om van kracht te worden:
>
> * Kopiëren/plakken uitschakelen voor documenten die zijn geopend in Application Guard voor Office
> * Afdrukken beperken voor documenten die zijn geopend in Application Guard voor Office
> * Camera- en microfoontoegang uitschakelen voor documenten die zijn geopend in Application Guard voor Office

## <a name="submit-feedback"></a>Feedback verzenden

### <a name="submit-feedback-via-feedback-hub"></a>Feedback verzenden via de Feedback-hub

Als u problemen ondervindt bij het starten van Application Guard voor Office, wordt u aangeraden uw feedback in te dienen via de Feedback-hub:

1. Open de **app Feedback-hub** en meld u aan.

2. Als er een dialoogvenster met fouten wordt weergegeven tijdens het starten van Application Guard, selecteert u Rapporteren bij **Microsoft** in het dialoogvenster fout om een nieuwe feedback-inzending te starten. Anders navigeert u naar de juiste categorie voor Application Guard en selecteert u nieuwe <https://aka.ms/mdagoffice-fb> **+ &nbsp; feedback toevoegen** in de rechterboventoepassing.

3. Voer een samenvatting in het **vak Uw feedback** samenvatten als dit nog niet voor u is ingevuld.

4. Voer een gedetailleerde beschrijving in van het probleem dat u hebt ervaren en welke stappen u hebt ondernomen in het vak **Meer** informatie. Selecteer vervolgens **Volgende.**

5. Selecteer de bel naast **Probleem.** Zorg ervoor dat de geselecteerde categorie Beveiliging **en privacy Microsoft Defender Application Guard - \> Office** is en selecteer vervolgens **Volgende.**

6. Selecteer **Nieuwe feedback** en vervolgens **Volgende.**

7. Traceringen verzamelen over het probleem:

   1. Vouw de **tegel Mijn probleem opnieuw maken** uit.

   2. Als het probleem dat u ondervindt zich voordoet terwijl Application Guard wordt uitgevoerd, opent u een Application Guard-exemplaar. Bij het openen van een exemplaar kunnen extra traceringen worden verzameld in de Application Guard-container.

   3. Selecteer **Opname starten en** wacht totdat de tegel niet meer draait en *zeg: Opname stoppen.*

   4. Reproduceer het probleem volledig met Application Guard. Verveelvoud alleen wanneer u probeert een Application Guard-exemplaar te starten en te wachten totdat het niet lukt, of een probleem reproduceren in een uitgevoerd Application Guard-exemplaar.

   5. Selecteer de **tegel Opname** stoppen.

   6. Houd alle exemplaren van Application Guard open, zelfs enkele minuten na het indienen, zodat de diagnostische gegevens van containers ook kunnen worden verzameld.

8. Voeg relevante schermafbeeldingen of bestanden toe die betrekking hebben op het probleem.

9. Selecteer **Verzenden.**

### <a name="submit-feedback-via-office-customer-voice"></a>Feedback verzenden via Office Customer Voice

U kunt vanuit Office ook feedback verzenden als het probleem zich voordeed wanneer Office-documenten worden geopend in Application Guard. Raadpleeg het [Office Insider-handboek voor het](https://insider.office.com/handbook) indienen van feedback.

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>Integratie met Microsoft Defender voor eindpunt en Microsoft Defender voor Office 365

Application Guard voor Office is geïntegreerd met Microsoft Defender for Endpoint voor het bewaken en waarschuwen van schadelijke activiteiten in de geïsoleerde omgeving.

Microsoft Defender for Endpoint is een beveiligingsplatform dat is ontworpen om bedrijfsnetwerken te helpen geavanceerde bedreigingen te voorkomen, te detecteren, te onderzoeken en erop te reageren. Zie Microsoft Defender for [Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp)voor meer informatie over dit platform. Zie Onboard-apparaten voor de Microsoft [Defender for Endpoint-service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)voor meer informatie over onboarding-apparaten voor dit platform.

U kunt ook Microsoft Defender voor Office 365 configureren voor gebruik met Defender voor het eindpunt. Raadpleeg Defender voor [Office 365 integreren](integrate-office-365-ti-with-wdatp.md)met Microsoft Defender voor eindpunt voor meer informatie.

## <a name="limitations-and-considerations"></a>Beperkingen en overwegingen

* Application Guard voor Office is een beperkte modus die niet-vertrouwde documenten isoleert, zodat ze geen toegang hebben tot vertrouwde bedrijfsbronnen, een intranet, de identiteit van de gebruiker en willekeurige bestanden op de computer. Als een gebruiker probeert toegang te krijgen tot een functie die afhankelijk is van dergelijke toegang (bijvoorbeeld het invoegen van een afbeelding uit een lokaal bestand op schijf) mislukt de toegang en wordt een prompt zoals in het volgende voorbeeld geproduceerd. Als gebruikers voor een niet-vertrouwd document toegang moeten hebben tot vertrouwde bronnen, moet de beveiliging van Application Guard worden verwijderd uit het document.

  ![Dialoogvenster waarin staat dat deze functie niet beschikbaar is om u te helpen uw veiligheid te behouden](../../media/ag10-limitations.png)

  > [!NOTE]
  > Adviseer gebruikers om de beveiliging alleen te verwijderen als ze het bestand en de bron vertrouwen of waar het vandaan komt.

* Actieve inhoud in documenten, zoals macro's en ActiveX-besturingselementen, is uitgeschakeld in Application Guard voor Office. Gebruikers moeten Application Guard-beveiliging verwijderen om actieve inhoud in teschakelen.

* Niet-vertrouwde bestanden van netwerk shares of bestanden die zijn gedeeld vanuit OneDrive, OneDrive voor Bedrijven of SharePoint Online vanuit een andere organisatie, worden als alleen-lezen geopend in Application Guard. Gebruikers kunnen een lokale kopie van dergelijke bestanden opslaan om in de container te blijven werken of de beveiliging verwijderen om rechtstreeks met het oorspronkelijke bestand te werken.

* Bestanden die worden beveiligd door IRM (Information Rights Management), worden standaard geblokkeerd. Als gebruikers dergelijke bestanden willen openen in de beveiligde weergave, moet een beheerder beleidsinstellingen configureren voor niet-ondersteunde bestandstypen voor de organisatie.

* Aanpassingen van Office-toepassingen in Application Guard voor Office blijven niet aanwezig nadat een gebruiker zich heeft af- en weer heeft meldt zich aan of nadat het apparaat opnieuw is opgestart.

* Alleen hulpprogramma's voor toegankelijkheid die gebruikmaken van het UIA-framework kunnen een toegankelijke ervaring bieden voor bestanden die worden geopend in Application Guard voor Office.

* Netwerkconnectiviteit is vereist voor de eerste keer starten van Application Guard na de installatie. Er is verbinding vereist om de licentie te valideren door Application Guard.

* In de informatiesectie van het document wordt met de eigenschap Laatst gewijzigd *door* **mogelijk WDAGUt heleAccount** weergegeven als gebruiker. WDAGUtilityAccount is de anonieme gebruiker die is geconfigureerd in Application Guard. De identiteit van de bureaubladgebruiker wordt niet gedeeld binnen de Application Guard-container.

## <a name="performance-optimizations-for-application-guard-for-office"></a>Prestatie-optimalisaties voor Application Guard voor Office

Deze sectie bevat een overzicht van de prestatie-optimalisaties die worden gebruikt in Application Guard voor Office. Deze informatie kan beheerders helpen rapporten te diagnosticeren van gebruikers met betrekking tot de prestaties van Office of het algemene systeem wanneer Application Guard is ingeschakeld.

Application Guard gebruikt een gevirtualiseerde container om niet-vertrouwde documenten weg te isoleren van het systeem. Het proces voor het maken van een container en het instellen van de Application Guard-container om Office-documenten te openen, heeft een performance overhead die een negatieve invloed kan hebben op de gebruikerservaring wanneer gebruikers een niet-vertrouwd document openen.

Om gebruikers de verwachte ervaring met het openen van bestanden te bieden, wordt in Application Guard logica gebruikt om vooraf een container te maken wanneer de volgende heuristic aan een systeem is voldaan: Een gebruiker heeft in de afgelopen 28 dagen een bestand geopend in de beveiligde weergave of in Application Guard.

Als aan deze heuristische waarde wordt voldaan, wordt er in Office vooraf een Application Guard-container voor de gebruiker aan het maken nadat deze zich heeft aanmelden bij Windows. Terwijl deze vooraf aan te maken bewerking wordt uitgevoerd, kunnen de prestaties van het systeem traag zijn, maar het effect wordt opgelost zodra de bewerking is voltooid.

> [!NOTE]
> De hints die nodig zijn voor de heuristic container om de container vooraf te maken, worden gegenereerd door Office-toepassingen wanneer een gebruiker deze gebruikt. Als een gebruiker Office installeert op een nieuw systeem waarop Application Guard is ingeschakeld, maakt Office de container pas na de eerste keer dat een gebruiker een niet-vertrouwd document op het systeem opent. De gebruiker ziet dat het langer duurt om dit eerste bestand te openen in Application Guard.

## <a name="known-issues"></a>Bekende problemen

* Als u `http` webkoppelingen (of `https` ) selecteert, wordt de browser niet geopend.
* Het kopiëren van inhoud of afbeeldingen in RTF-indeling (Rich Text Format) in Office-documenten die zijn geopend met Application Guard, wordt op dit moment niet ondersteund.
* Updates voor .NET zorgen ervoor dat bestanden niet kunnen worden geopend in Application Guard. Als tijdelijke oplossing kunnen gebruikers hun apparaat opnieuw opstarten wanneer ze deze fout te zien krijgen. Meer informatie over het probleem bij het ontvangen van een foutbericht bij het openen van [Windows Defender Application Guard of Windows Sandbox.](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)
