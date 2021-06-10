---
title: Application Guard voor Office 365 voor beheerders
keywords: toepassingsbeveiliging, beveiliging, isolatie, geïsoleerde container, hardwareisolatie
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
description: De nieuwste informatie over isolatie op hardwarebasis. Voorkomen dat huidige en nieuwe aanvallen, zoals exploits of schadelijke koppelingen, de productiviteit van werknemers en de beveiliging van het bedrijf verstoren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d0fa6ad884c6b21457c8359cf82e32e4b8c100ba
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488309"
---
# <a name="application-guard-for-office-for-admins"></a>Application Guard voor Office voor beheerders

**Van toepassing op:** Word, Excel en PowerPoint voor Microsoft 365, Windows 10 Enterprise

Microsoft Defender Application Guard voor Office (Application Guard voor Office) helpt voorkomen dat niet-vertrouwde bestanden toegang krijgen tot vertrouwde bronnen, zodat uw bedrijf veilig is tegen nieuwe en nieuwe aanvallen. In dit artikel worden beheerders door het instellen van apparaten voor een voorbeeld van Application Guard voor Office. Het bevat informatie over systeemvereisten en installatiestappen om Application Guard in te Office op een apparaat.

## <a name="prerequisites"></a>Vereisten

### <a name="minimum-hardware-requirements"></a>Minimale hardwarevereisten

* **CPU:** 64-bits, 4-cores (fysiek of virtueel), virtualisatieextensies (Intel VT-x OF AMD-V), Core i5-equivalent of hoger aanbevolen
* **Fysiek geheugen:** 8 GB RAM
* **Harde schijf:** 10 GB vrije ruimte op het systeemstation (SSD aanbevolen)

### <a name="minimum-software-requirements"></a>Minimale softwarevereisten

* **Windows 10**: Windows 10 Enterprise versie, Client build versie 2004 (20H1) build 19041 of hoger
* **Office:** Office Current-kanaal en Monthly Enterprise-kanaal, build versie 2011 16.0.13530.10000 of hoger. Zowel 32-bits als 64-bits versies van Office worden ondersteund.
* **Updatepakket:** Windows 10 cumulatieve maandelijkse beveiligingsupdate [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

Voor gedetailleerde systeemvereisten raadpleegt u [Systeemvereisten voor Microsoft Defender Application Guard.](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard) Raadpleeg ook de handleidingen van de computerfabrikant over het inschakelen van virtualisatietechnologie.
Zie Overzicht van updatekanalen voor Office updatekanalen voor [Microsoft 365.](/deployoffice/overview-update-channels)

### <a name="licensing-requirements"></a>Licentievereisten

* Microsoft 365 E5 of Microsoft 365 E5 Security

## <a name="deploy-application-guard-for-office"></a>Application Guard implementeren voor Office

### <a name="enable-application-guard-for-office"></a>Application Guard inschakelen voor Office

1. Download en installeer **Windows 10 cumulatieve maandelijkse beveiligingsupdates KB4571756**.

2. Selecteer **Microsoft Defender Application Guard** onder Windows Functies en selecteer **OK.** Als u de functie Application Guard inschakelen, wordt een systeem opnieuw opgestart. U kunt ervoor kiezen om nu of na stap 3 opnieuw op te starten.

   ![Windows Dialoogvenster Functies met AG](../../media/ag03-deploy.png)

   De functie kan ook worden ingeschakeld door de volgende PowerShell-opdracht uit te voeren als beheerder:

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. Zoek naar **Microsoft Defender Application Guard in de beheerde** modus , een groepsbeleid in Beheersjablonen voor **computerconfiguratie Windows Onderdelen \\ \\ \\ Microsoft Defender Application Guard**. Schakel dit beleid in door de waarde onder Opties in te stellen als **2** of **3** en vervolgens OK of Toepassen **te** **selecteren.**

   ![AG inschakelen in beheerde modus](../../media/ag04-deploy.png)

   In plaats daarvan kunt u het bijbehorende CSP-beleid instellen:

   > OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Instellingen/AllowWindowsDefenderApplicationGuard** <br> Gegevenstype: **Integer** <br> Waarde: **2**

4. Start het systeem opnieuw.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>Diagnostische gegevens & om volledige gegevens te verzenden

> [!NOTE]
> Dit is niet vereist, maar het configureren van optionele diagnostische gegevens helpt bij het opsporen van gerapporteerde problemen.

Deze stap zorgt ervoor dat de gegevens die nodig zijn om problemen te identificeren en op te lossen, microsoft bereiken. Volg deze stappen om diagnostische gegevens op uw Windows in te stellen:

1. Open **Instellingen** in het menu Start.

   ![Menu Start](../../media/ag05-diagnostic.png)

2. Selecteer **Windows Instellingen** op **Privacy**.

   ![Windows Instellingen menu](../../media/ag06-diagnostic.png)

3. Selecteer onder Privacy de optie **Diagnostics & feedback** en selecteer **Optionele diagnostische gegevens.**

   ![Menu Diagnostische gegevens en feedback](../../media/ag07a-diagnostic.png)

Voor meer informatie over het configureren Windows diagnostische instellingen raadpleegt u [Configureren Windows diagnostische gegevens in uw organisatie.](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Controleren of Application Guard voor Office is ingeschakeld en werkt

Voordat u bevestigt dat Application Guard voor Office is ingeschakeld, start u Word, Excel of PowerPoint op een apparaat waarop het beleid is geïmplementeerd. Zorg ervoor Office is geactiveerd. Mogelijk moet u uw werkidentiteit gebruiken om het Office te activeren.

Als u wilt controleren of Application Guard voor Office is ingeschakeld, start u Word, Excel of PowerPoint en opent u vervolgens een niet-vertrouwd document. U kunt bijvoorbeeld een document openen dat is gedownload van internet of een e-mailbijlage van iemand buiten uw organisatie.

Wanneer u voor het eerst een niet-vertrouwd bestand opent, ziet u mogelijk een welkomstscherm Office zoals in het volgende voorbeeld. Het kan enige tijd worden weergegeven terwijl Application Guard voor Office wordt geactiveerd en het bestand wordt geopend. Volgende openingen van niet-vertrouwde bestanden moeten sneller zijn.

![Office-app welkomstscherm](../../media/ag08-confirm.png)

Wanneer het bestand wordt geopend, moet het een paar visuele indicatoren weergeven dat het bestand is geopend in Application Guard voor Office:

* Een bijgesprek op het lint

  ![Doc-bestand met kleine notitie app-beveiliging](../../media/ag09-confirm.png)

* Het toepassingspictogram met een schild op de taakbalk

  ![Pictogram op de taakbalk](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>Application Guard configureren voor Office

Office ondersteunt het volgende beleid, zodat u de mogelijkheden van Application Guard kunt configureren voor Office. Dit beleid kan worden geconfigureerd via groepsbeleidsregels of via de [Office cloudbeleidsservice.](/DeployOffice/overview-office-cloud-policy-service)
Zie configuratie die is ingesteld door uw beheerder door groepsbeleidsinstellingen te bekijken in Beheersjablonen voor gebruikersconfiguratie **\\ Microsoft Office \\ 2016 \\ Instellingen Trust Center Application \\ \\ Guard**.


> [!NOTE]
> Als u dit beleid configureert, kunt u bepaalde functies uitschakelen voor bestanden die in Application Guard zijn geopend voor Office.

|Beleid|Beschrijving|
|---|---|
|Gebruik Application Guard niet voor Office|Als u dit beleid inschakelen, worden Word, Excel en PowerPoint de isolatiecontainer Beveiligde weergave gebruikt in plaats van Application Guard voor Office. Dit beleid kan worden gebruikt om Application Guard tijdelijk uit te Office wanneer er problemen zijn bij het inschakelen van het Microsoft Edge.|
|Application Guard configureren voor Office container vóór het maken|Dit beleid bepaalt of de Application Guard voor Office container, voor het isoleren van niet-vertrouwde bestanden, vooraf is gemaakt voor verbeterde run-time prestaties. Als u deze instelling inschakelen, kunt u het aantal dagen opgeven om door te gaan met het vooraf maken van een container of de Office ingebouwde heuristische pre-create van de container.
|Kopieer/plak niet toestaan voor documenten die Office geopend in Application Guard voor Office|Als u dit beleid inschakelen, voorkomt u dat een gebruiker inhoud kopieert en past uit een document dat is geopend in Application Guard Office naar een document dat buiten het document wordt geopend.|
|Hardwareversnelling uitschakelen in Application Guard voor Office|Dit beleid bepaalt of Application Guard voor Office hardwareversnelling gebruikt om afbeeldingen weer te geven. Als u deze instelling inschakelen, gebruikt Application Guard voor Office softwarematige weergave (CPU) en worden er geen grafische stuurprogramma's van derden geladen of wordt er geen interactie met verbonden grafische hardware gebruikt.
|Niet-ondersteunde bestandstypenbeveiliging uitschakelen in Application Guard voor Office|Dit beleid bepaalt of Application Guard voor Office niet-ondersteunde bestandstypen wordt geopend of dat de omleiding naar beveiligde weergave wordt ingeschakeld.
|Camera- en microfoontoegang uitschakelen voor documenten die zijn geopend in Application Guard voor Office|Als u dit beleid inschakelen, Office toegang tot de camera en microfoon in Application Guard voor Office.|
|Het afdrukken beperken van documenten die zijn geopend in Application Guard voor Office|Als u dit beleid inschakelen, worden de printers beperkt die een gebruiker kan afdrukken vanuit een bestand dat is geopend in Application Guard voor Office. U kunt dit beleid bijvoorbeeld gebruiken om te beperken dat gebruikers alleen afdrukken naar PDF.|
|Voorkomen dat gebruikers Application Guard verwijderen voor Office beveiliging op bestanden|Als u dit beleid inschakelen, wordt de optie (binnen de Office-toepassingservaring) verwijderd om Application Guard uit te schakelen voor Office-beveiliging of om een bestand buiten Application Guard te openen voor Office. <p> **Opmerking:** Gebruikers kunnen dit beleid nog steeds omzeilen door de eigenschap Mark-of-the-Web handmatig uit het bestand te verwijderen of door een document te verplaatsen naar een vertrouwde locatie.|
|

> [!NOTE]
> Voor het volgende beleid moet de gebruiker zich aanmelden en zich opnieuw aanmelden om Windows van kracht te worden:
>
> * Kopiëren/plakken uitschakelen voor documenten die zijn geopend in Application Guard voor Office
> * Afdrukken beperken voor documenten die zijn geopend in Application Guard voor Office
> * Camera- en microfoontoegang uitschakelen voor documenten die zijn geopend in Application Guard voor Office

## <a name="submit-feedback"></a>Feedback verzenden

### <a name="submit-feedback-via-feedback-hub"></a>Feedback verzenden via feedbackhub

Als u problemen ondervindt bij het starten van Application Guard voor Office, wordt u aangeraden uw feedback in te dienen via feedbackhub:

1. Open de **Feedback Hub-app** en meld u aan.

2. Als u tijdens het starten van Application Guard een foutdialoogvenster krijgt, **selecteert** u Rapporteren aan Microsoft in het dialoogvenster Fout om een nieuwe feedbackinzending te starten. Ga anders naar de juiste categorie voor Application Guard en selecteer vervolgens <https://aka.ms/mdagoffice-fb> **+ &nbsp; Nieuwe feedback toevoegen** rechtsboven.

3. Voer een samenvatting in het vak **Uw feedback samenvatten** als deze nog niet voor u is ingevuld.

4. Voer een gedetailleerde beschrijving in van het probleem dat u hebt ervaren en welke stappen u hebt ondernomen in het vak Meer **informatie** en selecteer **Volgende.**

5. Selecteer de bel naast **Probleem.** Zorg ervoor dat de geselecteerde categorie Beveiligings- en **\> privacy-Microsoft Defender Application Guard - Office** is en selecteer vervolgens **Volgende.**

6. Selecteer **Nieuwe feedback** en vervolgens **Volgende**.

7. Traces verzamelen over het probleem:

   1. Vouw de **tegel Mijn probleem opnieuw maken** uit.

   2. Als het probleem optreedt terwijl Application Guard wordt uitgevoerd, opent u een exemplaar van Application Guard. Als u een exemplaar opent, kunnen extra traceringen worden verzameld vanuit de container Application Guard.

   3. Selecteer **Opname starten** en wacht totdat de tegel stopt met draaien en zeg Opname *stoppen.*

   4. Reproduceer het probleem volledig met Application Guard. Reproductie kan bestaan uit een poging om een application guard-exemplaar te starten en te wachten totdat het mislukt, of een probleem reproduceren in een lopend Application Guard-exemplaar.

   5. Selecteer de **tegel Opname** stoppen.

   6. Houd alle lopende Application Guard-exemplaren geopend, zelfs enkele minuten na de indiening, zodat containerdiagnose ook kan worden verzameld.

8. Voeg relevante schermafbeeldingen of bestanden bij die betrekking hebben op het probleem.

9. Selecteer **Verzenden**.

### <a name="submit-feedback-via-office-customer-voice"></a>Feedback verzenden via Office Customer Voice

U kunt ook feedback verzenden van binnen Office als het probleem zich voordeed wanneer Office documenten worden geopend in Application Guard. Raadpleeg het Office [Insider-handboek voor](https://insider.office.com/handbook) het indienen van feedback.

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>Integratie met Microsoft Defender voor Eindpunt en Microsoft Defender voor Office 365

Application Guard voor Office is geïntegreerd met Microsoft Defender voor Eindpunt om te controleren en te waarschuwen voor schadelijke activiteiten die zich in de geïsoleerde omgeving voordeden.

[Safe Documenten in Microsoft E365 E5](/microsoft-365/security/office-365-security/safe-docs) is een functie waarmee Microsoft Defender voor Eindpunt wordt gebruikt om documenten te scannen die zijn geopend in Application Guard voor Office. Voor een extra beveiligingslaag kunnen gebruikers Application Guard niet verlaten voor Office totdat de resultaten van de scan zijn vastgesteld.

Microsoft Defender for Endpoint is een beveiligingsplatform dat is ontworpen om bedrijfsnetwerken te helpen geavanceerde bedreigingen te voorkomen, te detecteren, te onderzoeken en erop te reageren. Zie Microsoft Defender voor Eindpunt voor meer informatie over [dit platform.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) Zie Onboard devices to the Microsoft Defender for Endpoint service (Onboard [devices to the Microsoft Defender for Endpoint service)](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)voor meer informatie over onboarding-apparaten voor dit platform.

U kunt Microsoft Defender ook zo configureren Office 365 te werken met Defender voor Eindpunt. Zie Defender integreren voor Office 365 met [Microsoft Defender voor Eindpunt voor meer informatie.](integrate-office-365-ti-with-mde.md)

## <a name="limitations-and-considerations"></a>Beperkingen en overwegingen

* Application Guard voor Office is een beveiligde modus die niet-vertrouwde documenten isoleert, zodat ze geen toegang hebben tot vertrouwde bedrijfsresources, een intranet, de identiteit van de gebruiker en willekeurige bestanden op de computer. Als een gebruiker toegang probeert te krijgen tot een functie die afhankelijk is van dergelijke toegang, bijvoorbeeld door een afbeelding vanuit een lokaal bestand op schijf in te voegen, mislukt de toegang en wordt een prompt zoals in het volgende voorbeeld gemaakt. Als u een niet-vertrouwd document toegang wilt geven tot vertrouwde bronnen, moeten gebruikers de beveiliging van Application Guard uit het document verwijderen.

  ![Dialoogvenster waarin staat dat deze functie niet beschikbaar is om u te helpen uw veiligheid te bewaren](../../media/ag10-limitations.png)

  > [!NOTE]
  > Adviseer gebruikers om alleen de beveiliging te verwijderen als ze het bestand en de bron ervan vertrouwen of waar het vandaan komt.

* Actieve inhoud in documenten zoals macro's en ActiveX besturingselementen worden uitgeschakeld in Application Guard voor Office. Gebruikers moeten Application Guard-beveiliging verwijderen om actieve inhoud in te stellen.

* Niet-vertrouwde bestanden van netwerkaandelen of bestanden die worden gedeeld vanuit OneDrive, OneDrive voor Bedrijven of SharePoint Online vanuit een andere organisatie, worden als alleen-lezen geopend in Application Guard. Gebruikers kunnen een lokale kopie van dergelijke bestanden opslaan om in de container te blijven werken of beveiliging verwijderen om rechtstreeks met het oorspronkelijke bestand te werken.

* Bestanden die zijn beveiligd met IRM (Information Rights Management) worden standaard geblokkeerd. Als gebruikers dergelijke bestanden in de beveiligde weergave willen openen, moet een beheerder beleidsinstellingen configureren voor niet-ondersteunde bestandstypen voor de organisatie.

* Eventuele aanpassingen aan Office toepassingen in Application Guard voor Office blijven bestaan nadat een gebruiker zich aftekent en zich opnieuw meldt of nadat het apparaat opnieuw is gestart.

* Alleen hulpprogramma's voor toegankelijkheid die gebruikmaken van het UIA-framework kunnen een toegankelijke ervaring bieden voor bestanden die in Application Guard worden geopend voor Office.

* Netwerkconnectiviteit is vereist voor de eerste lancering van Application Guard na de installatie. Connectiviteit is vereist voor Application Guard om de licentie te valideren.

* In de sectie Info van het document kan de eigenschap Laatst gewijzigd *door* **WDAGUtilityAccount** als gebruiker worden weergegeven. WDAGUtilityAccount is de anonieme gebruiker die is geconfigureerd in Application Guard. De identiteit van de bureaubladgebruiker wordt niet gedeeld in de container Application Guard.

## <a name="performance-optimizations-for-application-guard-for-office"></a>Prestatie-optimalisaties voor Application Guard voor Office

In deze sectie vindt u een overzicht van de prestatieoptimalisaties die worden gebruikt in Application Guard voor Office. Deze informatie kan beheerders helpen bij het opsporen van rapporten van gebruikers met betrekking tot de prestaties van Office of het algemene systeem wanneer Application Guard is ingeschakeld.

Application Guard gebruikt een gevirtualiseerde container om niet-vertrouwde documenten te isoleren van het systeem. Het proces van het maken van een container en het instellen van de container Application Guard om Office-documenten te openen, heeft een prestatie-overhead die een negatieve invloed kan hebben op de gebruikerservaring wanneer gebruikers een niet-vertrouwd document openen.

Om gebruikers de verwachte ervaring voor het openen van bestanden te bieden, gebruikt Application Guard logica om een container vooraf te maken wanneer aan de volgende heuristische wordt voldaan op een systeem: Een gebruiker heeft een bestand geopend in de beveiligde weergave of Application Guard in de afgelopen 28 dagen.

Wanneer aan deze heuristische wordt voldaan, Office een Application Guard-container voor de gebruiker maken nadat ze zich hebben Windows. Hoewel deze bewerking vooraf wordt uitgevoerd, kan het systeem trage prestaties ervaren, maar het effect wordt opgelost zodra de bewerking is voltooid.

> [!NOTE]
> De hints die nodig zijn voor de heuristische manier om de container vooraf te maken, worden gegenereerd door Office toepassingen als een gebruiker deze gebruikt. Als een gebruiker Office installeert op een nieuw systeem waarin Application Guard is ingeschakeld, wordt de container pas vóór de eerste keer door Office geopend nadat een gebruiker een niet-vertrouwd document op het systeem opent. De gebruiker ziet dat het langer duurt om dit eerste bestand te openen in Application Guard.

## <a name="known-issues"></a>Bekende problemen

* Als u `http` webkoppelingen (of `https` ) selecteert, wordt de browser niet geopend.
* Inhoud of afbeeldingen van rtf-indeling (Rich Text Format) in Office documenten die met Application Guard zijn geopend, worden op dit moment niet ondersteund.
* De standaardinstelling voor niet-ondersteunde bestandstypenbeveiligingsbeleid is het blokkeren van het openen van niet-vertrouwde niet-ondersteunde bestandstypen IRM, CSV of HTML.
* Updates voor .NET kunnen ertoe leiden dat bestanden niet worden geopend in Application Guard. Als tijdelijke oplossing kunnen gebruikers hun apparaat opnieuw opstarten wanneer ze deze fout zien. Meer informatie over het probleem bij [Het ontvangen van een foutbericht](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)bij het openen van Windows Defender Application Guard of Windows Sandbox.
