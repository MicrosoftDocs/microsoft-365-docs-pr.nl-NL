---
title: Application Guard voor Office 365 (openbare preview) voor beheerders
keywords: Application Guard, beveiliging, isolatie, geïsoleerde container, hardwarematige isolatie
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Geniet van de nieuwste isolatie op basis van hardware. Voorkomen dat huidige en opkomende aanvallen, zoals misbruik of kwaadaardige koppelingen, geen productiviteit voor werknemers en beveiliging van de werknemers kunnen storen.
ms.openlocfilehash: 32a8705255bf4ae4f0e3678de9cd812b64107cfd
ms.sourcegitcommit: 57b37a3ce40f205c7320d5be1a0d906dd492b863
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405539"
---
# <a name="application-guard-for-office-public-preview-for-admins"></a>Application Guard voor Office (openbare preview) voor beheerders


**Van toepassing op:** Word, Excel en PowerPoint voor Microsoft 365, Windows 10 Enterprise

>[!IMPORTANT]
>Sommige gegevens zijn gerelateerd aan een voorvrijgegeven product, dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend kan worden gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.


Microsoft Defender Application Guard voor Office (Application Guard voor Office) helpt voorkomen dat niet-vertrouwde bestanden toegang krijgen tot vertrouwde bronnen, zodat uw onderneming veilig blijft tegen nieuwe en opkomende aanvallen. Dit artikel helpt beheerders bij het instellen van apparaten voor een preview van Application Guard voor Office. Dit artikel bevat informatie over systeemvereisten en installatiestappen voor het inschakelen van Application Guard voor Office op een apparaat.

## <a name="prerequisites"></a>Vereisten

### <a name="minimum-hardware-requirements"></a>Minimale hardwarevereisten

* **CPU**: 64-bits, vier kernen (fysiek of virtueel), virtualisatie-extensies (Intel VT-x of AMD-V), Kern i5-equivalent of hoger aanbevolen
* **Fysiek geheugen**: 8 GB RAM
* **Harde schijf**: 10 GB beschikbare ruimte op het systeemstation (SSD aanbevolen)

### <a name="minimum-software-requirements"></a>Minimale softwarevereisten

* **Windows 10**: Windows 10 Enterprise Edition, client Build versie 2004 (20H1) Build 19041
* **Office**: Office Beta-kanaal Build versie 2008 16.0.13212 of hoger
* **Update pakket**: cumulatieve maandelijkse beveiligingsupdates voor Windows 10 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756) 

Voor gedetailleerde systeemvereisten raadpleegt u [systeemvereisten voor Microsoft Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard). Zie aan de slag met [Office Insider-builds](https://insider.office.com/business/deploy)voor meer informatie over versies van Office Insider preview.

### <a name="licensing-requirements"></a>Licentievereisten
* Microsoft 365 E5 of Microsoft 365 E5-beveiliging

## <a name="deploy-application-guard-for-office"></a>Application Guard voor Office implementeren

### <a name="enable-application-guard-for-office"></a>Application Guard voor Office inschakelen

1.  Download en installeer de **cumulatieve maandelijkse beveiligingsupdates voor Windows 10 KB4571756**. 

2.  Selecteer **Microsoft Defender Application Guard** onder Windows-functies en selecteer **OK**. Als u de functie Application Guard inschakelt, wordt de computer opnieuw opgestart. U kunt ervoor kiezen om nu of na stap 3 opnieuw te starten.

    ![Het dialoogvenster Windows-functies met AG](../../media/ag03-deploy.png)
    
    De functie kan ook worden ingeschakeld door de volgende PowerShell-opdracht als Administrator uit te voeren: 

    ```powershell
    Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard 
    ```

3.  Kijk voor de Microsoft Defender Application Guard in de bewerkingsmodus Groepsbeleid van de **computer configuratie \\ \\ Windows-onderdelen \\ Microsoft Defender Application Guard**. Zet dit beleid aan door de waarde onder opties als **2** of **3** in te stellen en klik vervolgens op **OK** of **toepassen**.

    ![AG inschakelen in de beheerde modus](../../media/ag04-deploy.png)
  
    U kunt ook het bijbehorende Cryptografiebeleid instellen: 

    OMA-URI: **./device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** 
    <br>Gegevenstype: **geheel getal** 
    <br>Waarde: **2**


4.  Start het systeem opnieuw op.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>Diagnostische gegevens instellen & feedback voor het verzenden van volledige gegevens

In deze stap wordt gecontroleerd of de gegevens die nodig zijn voor het identificeren en oplossen van problemen Microsoft bereiken. Voer de volgende stappen uit om diagnostische gegevens voor uw Windows-apparaat in te schakelen:

1.  Open **instellingen** in het menu Start.

    ![Menu Start](../../media/ag05-diagnostic.png)

2.  Selecteer **Privacy**in **Windows-instellingen**.

    ![Menu instellingen van Windows](../../media/ag06-diagnostic.png)

3.  Selecteer onder privacy de optie **Diagnostische gegevens & feedback** en selecteer **optionele diagnostische gegevens**.

    ![Het menu diagnostisch en feedback](../../media/ag07a-diagnostic.png)

Raadpleeg voor meer informatie over het configureren van diagnostische [gegevens voor Windows de informatie over het configureren van diagnostische gegevens voor Windows in uw organisatie](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Controleren of Application Guard voor Office is ingeschakeld en werkt

Voordat u bevestigt dat de toepassing Guard voor Office is ingeschakeld, start u Word, Excel of PowerPoint op een apparaat waarop het beleid is geïmplementeerd. Zorg dat Office is geactiveerd. Mogelijk moet u uw werk identiteit gebruiken om eerst het Office-product te activeren.

Als u wilt controleren of Application Guard voor Office nu is ingeschakeld, start u Word, Excel of PowerPoint en opent u een niet-vertrouwd document. U kunt bijvoorbeeld een document openen dat is gedownload van Internet of een e-mailbijlage van iemand buiten uw organisatie.

Op de eerste lancering van een niet-vertrouwd bestand ziet u mogelijk een openingsscherm van Office zoals hieronder. Het programma kan enige tijd weergeven wanneer Application Guard voor Office wordt geactiveerd en het bestand wordt geopend. Volgende start van niet-vertrouwde bestanden moet sneller zijn.

![Beginscherm van de Office-app](../../media/ag08-confirm.png)


Wanneer u opent, moet het bestand enkele visuele indicatoren weergeven die het bestand hebt geopend in Application Guard voor Office:

* Een bijschrift op het lint

    ![Document bestand met kleine app Guard-notitie](../../media/ag09-confirm.png)
* Het toepassingspictogram met een schild op de taakbalk 

    ![Pictogram op de taakbalk](../../media/ag12-limitations.png)



## <a name="configure-application-guard-for-office"></a>Application Guard voor Office configureren
Office ondersteunt de volgende beleidsregels zodat u de mogelijkheden van Application Guard voor Office kunt configureren. U kunt deze beleidsregels configureren via Groepsbeleid of via de service Office Cloud beleid. 

>[!NOTE] 
> Deze beleidsregels worden binnenkort beschikbaar.
>Daarnaast kunt u met deze beleidsregels bepaalde functies uitschakelen voor bestanden die zijn geopend in Application Guard voor Office.

| Beleid                                                                          | Beschrijving                                                                                                                                                                                                                                                                                             |
|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Application Guard voor Office uitschakelen                                            | Als u dit beleid inschakelt, wordt in Word, Excel en PowerPoint de isolatie container voor beveiligde weergave gebruikt in plaats van Application Guard voor Office. Dit beleid kan worden gebruikt om Application Guard voor Office tijdelijk uit te schakelen wanneer er problemen zijn met de ingeschakelde optie om de rand te verlaten.                                  |
| Kopiëren/plakken uitschakelen voor documenten die zijn geopend in Application Guard                    | Als u dit beleid inschakelt, kan een gebruiker inhoud van een document dat in Application Guard voor Office is geopend, niet kopiëren en plakken naar een document dat buiten het document is geopend.                                                                                                                                   |
| Voorkomen dat gebruikers de bescherming van Application Guard voor bestanden verwijderen               | Als u dit beleid inschakelt, wordt de optie (binnen de Office-toepassings ervaring) verwijderd om Application Guard-beveiliging uit te schakelen of een bestand buiten Application Guard te openen. <br><br>**Opmerking:** Gebruikers kunnen dit beleid wel omzeilen door de eigenschap van het selectievakje van de Web-eigenschap uit het bestand handmatig te verwijderen of door een document naar een vertrouwde locatie te verplaatsen. |
| Afdrukken beperken van documenten die zijn geopend in Application Guard                    | Als u dit beleid inschakelt, wordt de printer beperkt die een gebruiker kan afdrukken vanuit een bestand dat is geopend in Application Guard voor Office. U kunt bijvoorbeeld dit beleid gebruiken om te voorkomen dat gebruikers alleen afdrukken naar een PDF-bestand.                              |
| Camera-en microfoon toegang uitschakelen voor documenten die zijn geopend in Application Guard | Door dit beleid in te schakelen, verwijdert u Office Access tot camera en microfoon binnen Application Guard voor Office.                                                                                                                                                                                                     |
>[!NOTE] 
>Voor de volgende beleidsregels moet de gebruiker zich afmelden bij Windows en opnieuw aanmelden bij Windows, zodat deze van kracht wordt.
> 
> *  Kopiëren/plakken uitschakelen voor documenten die zijn geopend in Application Guard
>*  Afdrukken beperken voor documenten die zijn geopend in Application Guard
> *  Camera-en microfoon toegang voor documenten die zijn geopend in Application Guard uitschakelen


## <a name="submit-feedback"></a>Feedback verzenden

### <a name="submit-feedback-via-feedback-hub"></a>Feedback verzenden via de feedback-hub

Als u problemen ondervindt bij het starten van Application Guard voor Office, wordt u aangeraden uw feedback te verzenden via de feedback-hub:

1.  Open de **feedback-hub-app** en meld u aan.

2.  Als er een dialoogvenster wordt weergegeven bij het starten van Application Guard, selecteert u **naar Microsoft melden** in het dialoogvenster fout om een nieuwe feedback verzending te starten. Anders gaat u naar <https://aka.ms/wdagoffice-fb> de juiste categorie voor Application Guard en selecteert u vervolgens **+ nieuwe feedback toevoegen** in de rechterbovenhoek.

3.  Vul het vak **uw feedback samenvatten** in als dit nog niet is ingevuld.

4.  Voer in het vak uitgebreide beschrijving **uitleggen** een gedetailleerde beschrijving in van het probleem dat zich heeft voorgedaan, en selecteer vervolgens **volgende**.

5.  Selecteer de bel naast probleem. Zorg ervoor dat de geselecteerde categorie **beveiliging en privacy \> Microsoft Defender Application Guard – Office**is en selecteer **volgende**.

6.  Selecteer **nieuwe feedback**en vervolgens **volgende**.

7.  Tracering verzamelen over het probleem:

    1. Vouw de tegel **mijn probleem opnieuw maken** uit.

    2.  Als u problemen ondervindt tijdens het uitvoeren van Application Guard, opent u een exemplaar van Application Guard. Als u dit doet, kunnen er aanvullende traceringen worden verzameld in de Application Guard-container.

    3.  Selecteer **opname starten** en wacht totdat de Tegel stopt en *opname stoppen*.

    4.  Verreproduceer het probleem met Application Guard. Dit omvat mogelijk een exemplaar van Application Guard en wacht totdat het is mislukt, of het opnieuw produceren van een probleem in een actief exemplaar van Application Guard.

    5.  Selecteer de tegel **opname stoppen** .

    6.  Zorg ervoor dat de actieve versie van Application Guard, zelfs voor enkele minuten na het verzenden, is ingeschakeld, zodat de diagnostische gegevens van containers ook kunnen worden verzameld.

8.  Voeg relevante schermafbeeldingen of bestanden met betrekking tot het probleem toe.

9.  Selecteer **Submit**.



### <a name="submit-feedback-via-office-customer-voice"></a>Feedback indienen via spraak van Office Customer

U kunt ook binnen Office feedback verzenden als het probleem optreedt wanneer Office-documenten worden geopend in Application Guard. Ga naar de [Office Insider](https://insider.office.com/handbook) -handleiding voor het verzenden van feedback.

## <a name="integration-with-microsoft-defender-atp-and-office-atp"></a>Integratie met Microsoft Defender ATP en Office ATP

Application Guard voor Office is geïntegreerd met Microsoft Defender Advance Threat Protection (ATP) voor het bewaken en signalering van schadelijke activiteiten in de geïsoleerde omgeving.

Microsoft Defender ATP is een beveiligings platform dat is ontworpen om Enterprise-netwerken te helpen voorkomen, het detecteren, onderzoeken en beantwoorden van geavanceerde bedreigingen. Ga naar de pagina [Microsoft Defender Advanced Threat Protection](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) voor meer informatie over dit platform. Meer informatie over onboarding-apparaten naar dit platform op [interne apparaten in de Microsoft Defender ATP-service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).

U kunt ook Office 365 ATP configureren voor gebruik met Microsoft Defender ATP. Zie [Office 365 ATP integreren met Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp?view=o365-worldwide).

## <a name="limitations-and-considerations"></a>Beperkingen en overwegingen

* Application Guard voor Office is een beperkte modus waarmee niet-vertrouwde documenten worden geïsoleerd van vertrouwde bedrijfsbronnen, intranet, de identiteit van de gebruiker en willekeurige bestanden op de computer. Als een gebruiker een functie probeert te openen die afhankelijk is van een dergelijke toegang, bijvoorbeeld door een afbeelding in te voegen vanuit een lokaal bestand op de schijf, mislukt dit en krijgt u een vraag zoals hieronder aangegeven. Gebruikers moeten de bescherming van Application Guard van het document verwijderen om een niet-vertrouwd document toegang te bieden tot vertrouwde bronnen.

    ![Dialoogvenster met de mededeling dat u de functie veilig kunt gebruiken, is deze functie niet beschikbaar](../../media/ag10-limitations.png)

    >[!NOTE]    
    >Adviseer gebruikers zich alleen te beschermen tegen bescherming als ze het bestand en de bron van de persoon en de naam ervan vertrouwen.

* Actieve inhoud in documenten, zoals macro's en ActiveX-besturingselementen, is uitgeschakeld in Application Guard voor Office. Gebruikers moeten Application Guard-beveiliging verwijderen om actieve inhoud in te schakelen.

* Niet-vertrouwde bestanden die vanuit OneDrive, OneDrive voor bedrijven of SharePoint Online worden gedeeld vanuit OneDrive, OneDrive voor bedrijven of SharePoint Online van een andere organisatie, worden als alleen-lezen geopend in Application Guard. Gebruikers kunnen een lokale kopie van een bestand opslaan om verder te werken in de container of beveiliging te verwijderen om rechtstreeks met het oorspronkelijke bestand te werken.

* Bestanden die zijn beveiligd met IRM (Information Rights Management), gaan open in de beveiligde weergave.
* Aanpassingen aan Office-toepassingen in Application Guard voor Office blijven niet behouden wanneer een gebruiker zich afmeldt en weer aanmeldt, of het apparaat opnieuw opstart. 

* Alleen hulpprogramma's voor toegankelijkheid die de UIA-Framework gebruiken, bieden een toegankelijke ervaring voor bestanden die worden geopend in Application Guard voor Office.

* Netwerkverbinding is vereist voor de eerste lancering van Application Guard na de installatie. Dit is vereist voor Application Guard om de licentie te valideren.
* In de sectie info in het document kan de *laatste wijziging door* de eigenschap WDAGUtilityAccount weergeven als de gebruiker. Dit is de anonieme gebruiker die is geconfigureerd in Application Guard, dat de identiteit van de bureaublad gebruiker niet wordt gedeeld binnen de Application Guard-container. 

## <a name="performance-optimizations-for-application-guard"></a>Prestatie optimaliseringen voor Application Guard 

In deze sectie wordt een overzicht gegeven van de prestatie optimaliseringen die worden gebruikt in Application Guard voor Office. Met behulp van deze informatie kunnen beheerders rapporten van gebruikers identificeren die betrekking hebben op de prestaties van Office of het algehele systeem wanneer Application Guard is ingeschakeld. 

Application Guard maakt gebruik van een gevirtualiseerde container om niet-vertrouwde documenten van het systeem te isoleren. Het proces voor het maken van een container en het instellen van de Application Guard-container voor het openen van Office-documenten heeft een prestatieoverhead die de werking van de gebruikers kan negatief beïnvloeden wanneer gebruikers een niet-vertrouwd document openen. 


Als u gebruikers wilt voorzien van de verwachte ervaring voor het openen van bestanden, wordt in Application Guard logica gebruikt om een container vooraf te maken wanneer aan de volgende heuristisch wordt voldaan: een gebruiker heeft een bestand in de afgelopen 28 dagen geopend in de beveiligde weergave of in Application Guard. 

Wanneer deze heuristisch is bereikt, maakt Office een Application Guard-container voor de gebruiker nadat deze zich heeft aangemeld bij Windows. Wanneer deze PreCreate-bewerking wordt uitgevoerd, kan het systeem trager prestaties ondervinden. Dit wordt opgelost zodra de bewerking is voltooid. 


>[!NOTE] 
>De hints die nodig zijn voor de heuristiek die wordt gebruikt om de container vooraf te maken, worden gegenereerd door Office-toepassingen wanneer een gebruiker deze gebruikt. Als een gebruiker Office installeert op een nieuw systeem waarbij Application Guard is ingeschakeld, wordt de container niet vooraf gemaakt totdat een gebruiker de eerste keer een niet-vertrouwd document opent. De gebruiker houdt in dat u het eerste bestand langer kunt openen in Application Guard. 

## <a name="known-issues-in-preview"></a>Bekende problemen in de preview-versie

* Met klikken op webkoppelingen ( ```http``` of ```https``` ) wordt de browser niet geopend. 
* .NET-updates zorgen ervoor dat bestanden niet worden geopend in Application Guard. Als tijdelijke oplossing kunnen gebruikers hun apparaat opnieuw opstarten wanneer dit probleem optreedt.
    Meer informatie over het probleem vindt [u bij een foutbericht bij het openen van een foutbericht bij het openen van Windows Defender Application Guard of Windows sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).
