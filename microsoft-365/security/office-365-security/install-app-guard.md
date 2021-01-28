---
title: Application Guard voor Office 365 voor beheerders
keywords: Application Guard, beveiliging, isolatie, geïsoleerde container, hardwarematige isolatie
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
description: Geniet van de nieuwste isolatie op basis van hardware. Voorkomen dat huidige en opkomende aanvallen, zoals misbruik of kwaadaardige koppelingen, geen productiviteit voor werknemers en beveiliging van de werknemers kunnen storen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9a9c9270f61661982108da518d1bf24d2a717b6a
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029724"
---
# <a name="application-guard-for-office-for-admins"></a>Application Guard voor Office voor beheerders

**Van toepassing op:** Word, Excel en PowerPoint voor Microsoft 365, Windows 10 Enterprise

Microsoft Defender Application Guard voor Office (Application Guard voor Office) helpt voorkomen dat niet-vertrouwde bestanden toegang krijgen tot vertrouwde bronnen, zodat uw onderneming veilig blijft tegen nieuwe en opkomende aanvallen. Dit artikel helpt beheerders bij het instellen van apparaten voor een preview van Application Guard voor Office. Dit artikel bevat informatie over systeemvereisten en installatiestappen voor het inschakelen van Application Guard voor Office op een apparaat.

## <a name="prerequisites"></a>Vereisten

### <a name="minimum-hardware-requirements"></a>Minimale hardwarevereisten

* **CPU**: 64-bits, vier kernen (fysiek of virtueel), virtualisatie-extensies (Intel VT-x of AMD-V), Kern i5-equivalent of hoger aanbevolen
* **Fysiek geheugen**: 8 GB RAM
* **Harde schijf**: 10 GB beschikbare ruimte op het systeemstation (SSD aanbevolen)

### <a name="minimum-software-requirements"></a>Minimale softwarevereisten

* **Windows 10**: Windows 10 Enterprise Edition, client Build versie 2004 (20H1) Build 19041 of hoger
* **Office**: Office Current Channel Build versie 2011 16.0.13530.10000 of hoger
* **Update pakket**: cumulatieve maandelijkse beveiligings update voor Windows 10 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

Voor gedetailleerde systeemvereisten raadpleegt u [systeemvereisten voor Microsoft Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard). Voor meer informatie over Office-Update kanalen, raadpleegt u [overzicht van update kanalen voor Microsoft 365](https://docs.microsoft.com/deployoffice/overview-update-channels).

### <a name="licensing-requirements"></a>Licentievereisten

* Microsoft 365 E5 of Microsoft 365 E5-beveiliging

## <a name="deploy-application-guard-for-office"></a>Application Guard voor Office implementeren

### <a name="enable-application-guard-for-office"></a>Application Guard voor Office inschakelen

1. Download en installeer de **cumulatieve maandelijkse beveiligingsupdates voor Windows 10 KB4571756**.

2. Selecteer **Microsoft Defender Application Guard** onder Windows-functies en selecteer **OK**. Als u de functie Application Guard inschakelt, wordt de computer opnieuw opgestart. U kunt ervoor kiezen om nu of na stap 3 opnieuw te starten.

   ![Het dialoogvenster Windows-functies met AG](../../media/ag03-deploy.png)

   De functie kan ook worden ingeschakeld door de volgende PowerShell-opdracht als Administrator uit te voeren:

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. Zoeken naar **Microsoft Defender Application Guard in** de bewerkingsmodus, een Groepsbeleid in de **Beheersjablonen voor de computer, Windows- \\ \\ onderdelen \\ Microsoft Defender Application Guard**. Schakel dit beleid in door een waarde in te stellen onder opties als **2** of **3**, en selecteer vervolgens **OK** of **toepassen**.

   ![AG inschakelen in de beheerde modus](../../media/ag04-deploy.png)

   In plaats daarvan kunt u het bijbehorende Cryptografiebeleid instellen:

   > OMA-URI: **./device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** <br> Gegevenstype: **geheel getal** <br> Waarde: **2**

4. Start het systeem opnieuw op.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>Diagnostische gegevens instellen & feedback voor het verzenden van volledige gegevens

In deze stap wordt gecontroleerd of de gegevens die nodig zijn voor het identificeren en oplossen van problemen Microsoft bereiken. Voer de volgende stappen uit om diagnostische gegevens voor uw Windows-apparaat in te schakelen:

1. Open **instellingen** in het menu Start.

   ![Menu Start](../../media/ag05-diagnostic.png)

2. Selecteer **Privacy** in **Windows-instellingen**.

   ![Menu instellingen van Windows](../../media/ag06-diagnostic.png)

3. Selecteer onder privacy de optie **Diagnostische gegevens & feedback** en selecteer **optionele diagnostische gegevens**.

   ![Het menu diagnostisch en feedback](../../media/ag07a-diagnostic.png)

Raadpleeg voor meer informatie over het configureren van diagnostische [gegevens voor Windows de informatie over het configureren van diagnostische gegevens voor Windows in uw organisatie](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Controleren of Application Guard voor Office is ingeschakeld en werkt

Voordat u bevestigt dat Application Guard voor Office is ingeschakeld, start u Word, Excel of PowerPoint op een apparaat waarop het beleid is geïmplementeerd. Zorg dat Office is geactiveerd. Mogelijk moet u uw werk identiteit gebruiken om eerst het Office-product te activeren.

Als u wilt controleren of Application Guard voor Office is ingeschakeld, start u Word, Excel of PowerPoint en opent u vervolgens een niet-vertrouwd document. U kunt bijvoorbeeld een document openen dat is gedownload van Internet of een e-mailbijlage van iemand buiten uw organisatie.

Wanneer u een niet-vertrouwd bestand voor het eerst opent, ziet u mogelijk een openingsscherm van Office, zoals in het volgende voorbeeld. Het kan enige tijd worden weergegeven wanneer Application Guard voor Office wordt geactiveerd en het bestand wordt geopend. Volgende openingen van niet-vertrouwde bestanden moeten sneller zijn.

![Beginscherm van de Office-app](../../media/ag08-confirm.png)

Wanneer u opent, moet het bestand enkele visuele indicatoren weergeven die het bestand hebt geopend in Application Guard voor Office:

* Een bijschrift op het lint

  ![Document bestand met kleine app Guard-notitie](../../media/ag09-confirm.png)

* Het toepassingspictogram met een schild op de taakbalk

  ![Pictogram op de taakbalk](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>Application Guard voor Office configureren

Office ondersteunt de volgende beleidsregels zodat u de mogelijkheden van Application Guard voor Office kunt configureren. U kunt deze beleidsregels configureren via Groepsbeleid of via de service Office Cloud beleid.

> [!NOTE]
> Door deze beleidsregels te configureren, kunt u bepaalde functies uitschakelen voor bestanden die zijn geopend in Application Guard voor Office.

|Beleid|Beschrijving|
|---|---|
|Gebruik Application Guard voor Office niet|Als u dit beleid inschakelt, wordt in Word, Excel en PowerPoint de isolatie container voor beveiligde weergave gebruikt in plaats van Application Guard voor Office. Dit beleid kan worden gebruikt om Application Guard voor Office tijdelijk uit te schakelen wanneer er problemen zijn met de uitvoering van de ondersteuning van Microsoft Edge.|
|De pre-creatie van Application Guard voor Office container configureren|Met deze beleidsinstelling wordt bepaald of de container Application Guard for Office, voor het isoleren van niet-vertrouwde bestanden, vooraf is gemaakt voor verbeterde runtime prestaties. Als u deze instelling inschakelt, kunt u het aantal dagen opgeven dat een container vooraf moet worden gemaakt of de ingebouwde Office-invoeg heuristisch maken.
|Kopiëren en plakken van Office-documenten die zijn geopend in Application Guard voor Office niet toestaan|Als u dit beleid inschakelt, kan een gebruiker inhoud van een document dat in Application Guard voor Office is geopend, niet kopiëren en plakken in een document dat buiten de toepassing is geopend.|
|Hardwareversnelling uitschakelen in Application Guard voor Office|Met dit beleid wordt bepaald of Application Guard voor Office gebruikmaakt van hardwareversnelling om afbeeldingen weer te geven. Als u deze instelling inschakelt, wordt Application Guard voor Office gebruikt voor de rendering op basis van software (CPU) en worden geen grafische Stuurprogramma's van derden geladen, noch wordt er verbinding gemaakt met grafische hardware.
|Niet-ondersteunde bestandstypen beveiliging uitschakelen in Application Guard voor Office|Met dit beleid kunt u bepalen of de functie Guard voor Office niet-ondersteunde bestandstypen moet worden geopend of dat de omleiding naar beveiligde weergave wordt ingeschakeld.
|Camera-en microfoon toegang uitschakelen voor documenten die zijn geopend in Application Guard voor Office|Door dit beleid in te schakelen, verwijdert u Office Access voor de camera en microfoon binnen Application Guard voor Office.|
|Afdrukken beperken van documenten die zijn geopend in Application Guard voor Office|Als u dit beleid inschakelt, worden de printers beperkt die een gebruiker kan afdrukken vanuit een bestand dat is geopend in Application Guard voor Office. U kunt bijvoorbeeld dit beleid gebruiken om te voorkomen dat gebruikers alleen afdrukken naar een PDF-bestand.|
|Voorkomen dat gebruikers Application Guard voor Office-beveiliging van bestanden verwijderen|Als u dit beleid inschakelt, wordt de optie (binnen de Office-toepassings ervaring) verwijderd om Application Guard voor Office-beveiliging uit te schakelen of om een bestand te openen buiten Application Guard voor Office. <p> **Opmerking:** Gebruikers kunnen dit beleid wel omzeilen door de eigenschap van het selectievakje van de Web-eigenschap uit het bestand handmatig te verwijderen of door een document naar een vertrouwde locatie te verplaatsen.|
|

> [!NOTE]
> Voor de volgende beleidsregels moet de gebruiker zich afmelden, waarna u zich opnieuw aanmeldt voor Windows om de kracht te laten:
>
> * Kopiëren/plakken uitschakelen voor documenten die zijn geopend in Application Guard voor Office
> * Afdrukken beperken voor documenten die zijn geopend in Application Guard voor Office
> * Camera-en microfoon toegang uitschakelen voor documenten die zijn geopend in Application Guard voor Office

## <a name="submit-feedback"></a>Feedback verzenden

### <a name="submit-feedback-via-feedback-hub"></a>Feedback verzenden via de feedback-hub

Als u problemen ondervindt bij het starten van Application Guard voor Office, wordt u aangeraden uw feedback te verzenden via de feedback-hub:

1. Open de **feedback-hub-app** en meld u aan.

2. Als er een dialoogvenster wordt weergegeven bij het starten van Application Guard, selecteert u **naar Microsoft melden** in het dialoogvenster fout om een nieuwe feedback verzending te starten. U kunt ook naar <https://aka.ms/mdagoffice-fb> de juiste categorie voor Application Guard selecteren en vervolgens **+ &nbsp; nieuwe feedback toevoegen** in de rechterbovenhoek selecteren.

3. Voer een samenvatting in het vak **uw feedback samenvatten** als dit nog niet is ingevuld.

4. Voer een gedetailleerde beschrijving in van het probleem dat zich heeft voorgedaan en welke stappen u in het vak **uitgebreide uitleg** en selecteer **volgende**.

5. Selecteer de bel naast **probleem**. Zorg ervoor dat de geselecteerde categorie **beveiliging en privacy \> Microsoft Defender Application Guard – Office** is en selecteer **volgende**.

6. Selecteer **nieuwe feedback** en vervolgens **volgende**.

7. Tracering verzamelen over het probleem:

   1. Vouw de tegel **mijn probleem opnieuw maken** uit.

   2. Als u problemen ondervindt tijdens het uitvoeren van Application Guard, opent u een exemplaar van Application Guard. Als u een exemplaar opent, kunt u de tracering van de toepassing in de Application Guard-container als volgt bekijken.

   3. Selecteer **opname starten** en wacht totdat de Tegel stopt en *opname stoppen*.

   4. Verreproduceer het probleem met Application Guard. De voortplanting omvat mogelijk een exemplaar van Application Guard en wacht totdat het is mislukt, of het opnieuw produceren van een probleem in een actief Application Guard-exemplaar.

   5. Selecteer de tegel **opname stoppen** .

   6. Onderhouds instantie (s) van Application Guard, ook gedurende enkele minuten na het indienen, zodat de diagnostische gegevens van containers ook kunnen worden verzameld.

8. Voeg relevante schermafbeeldingen of bestanden met betrekking tot het probleem toe.

9. Selecteer **Submit**.

### <a name="submit-feedback-via-office-customer-voice"></a>Feedback indienen via spraak van Office Customer

U kunt ook binnen Office feedback verzenden als het probleem optreedt wanneer Office-documenten worden geopend in Application Guard. Ga naar de [Office Insider](https://insider.office.com/handbook) -handleiding voor het verzenden van feedback.

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>Integratie met Microsoft Defender voor eindpunten en Microsoft Defender voor Office 365

Application Guard voor Office is geïntegreerd met Microsoft Defender voor eindpunten, zodat u kunt controleren welke schadelijke activiteiten er in de geïsoleerde omgeving plaatsvinden.

Microsoft Defender voor eindpunt is een beveiligings platform dat is ontworpen om Enterprise-netwerken te helpen voorkomen, het detecteren, onderzoeken en beantwoorden van geavanceerde bedreigingen. Zie [Microsoft Defender for Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp)voor meer informatie over dit platform. Als u meer wilt weten over onboarding-apparaten naar dit platform, raadpleegt u apparaten inactief voor [de Microsoft Defender for Endpoint-service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).

U kunt Microsoft Defender voor Office 365 ook configureren voor gebruik van Defender voor eindpunten. Zie voor meer informatie de functies [Defender voor Office 365 integreren met Microsoft Defender voor eindpunt](integrate-office-365-ti-with-wdatp.md).

## <a name="limitations-and-considerations"></a>Beperkingen en overwegingen

* Application Guard voor Office is een beperkte modus die niet-vertrouwde documenten isoleert, zodat deze geen toegang heeft tot vertrouwde bedrijfsbronnen, een intranet, de identiteit van de gebruiker en willekeurige bestanden op de computer. Als een gebruiker een functie met een afhankelijkheid van een van deze toegang wil gebruiken, bijvoorbeeld om een afbeelding in te voegen vanuit een lokaal bestand op de schijf, mislukt de toegang en krijgt u een vraag zoals in het volgende voorbeeld. Gebruikers moeten de bescherming van Application Guard van het document verwijderen om een niet-vertrouwd document toegang te bieden tot vertrouwde bronnen.

  ![Dialoogvenster met de mededeling dat u de functie veilig kunt gebruiken, is deze functie niet beschikbaar](../../media/ag10-limitations.png)

  > [!NOTE]
  > Adviseer gebruikers zich alleen te beschermen tegen bescherming als ze het bestand en de bron van de persoon en de naam ervan vertrouwen.

* Actieve inhoud in documenten, zoals macro's en ActiveX-besturingselementen, is uitgeschakeld in Application Guard voor Office. Gebruikers moeten Application Guard-beveiliging verwijderen om actieve inhoud in te schakelen.

* Niet-vertrouwde bestanden van netwerkshares of bestanden die zijn gedeeld vanuit OneDrive, OneDrive voor bedrijven of SharePoint Online van een andere organisatie die als alleen-lezen worden geopend in Application Guard. Gebruikers kunnen een lokale kopie van een bestand opslaan om verder te werken in de container of beveiliging te verwijderen om rechtstreeks met het oorspronkelijke bestand te werken.

* Bestanden die zijn beveiligd met IRM (Information Rights Management), worden standaard geblokkeerd. Als gebruikers dergelijke bestanden willen openen in de beveiligde weergave, moet een beheerder beleidsinstellingen configureren voor niet-ondersteunde bestandstypen voor de organisatie.

* Aanpassingen aan Office-toepassingen in Application Guard voor Office blijven niet behouden wanneer een gebruiker zich afmeldt en zich opnieuw aanmeldt of nadat het apparaat opnieuw is opgestart.

* Alleen hulpprogramma's voor toegankelijkheid die de UIA-Framework gebruiken, bieden een toegankelijke ervaring voor bestanden die worden geopend in Application Guard voor Office.

* Netwerkverbinding is vereist voor de eerste lancering van Application Guard na de installatie. Voor de validatie van de licentie is connectiviteit vereist voor Application Guard.

* In de sectie info in het document kan de *laatste wijziging door* de eigenschap **WDAGUtilityAccount** weergeven als de gebruiker. WDAGUtilityAccount is de anonieme gebruiker die is geconfigureerd in Application Guard. De identiteit van de bureaublad gebruiker wordt niet gedeeld in de Application Guard-container.

## <a name="performance-optimizations-for-application-guard-for-office"></a>Prestatie optimaliseringen voor Application Guard voor Office

In deze sectie wordt een overzicht gegeven van de prestatie optimaliseringen die worden gebruikt in Application Guard voor Office. Met behulp van deze informatie kunnen beheerders rapporten van gebruikers identificeren die betrekking hebben op de prestaties van Office of het algehele systeem wanneer Application Guard is ingeschakeld.

Application Guard maakt gebruik van een gevirtualiseerde container om niet-vertrouwde documenten van het systeem te isoleren. Het proces voor het maken van een container en het instellen van de Application Guard-container voor het openen van Office-documenten heeft een prestatie overbelasting die van invloed kan zijn op de gebruikerservaring wanneer gebruikers een niet-vertrouwd document openen.

Als u gebruikers wilt voorzien van de verwachte ervaring voor het openen van bestanden, maakt Application Guard logica om een container vooraf te maken wanneer aan de volgende heuristisch wordt voldaan: een gebruiker heeft in de afgelopen 28 dagen een bestand geopend in de beveiligde weergave of in Application Guard.

Wanneer deze heuristisch is bereikt, maakt Office een Application Guard-container voor de gebruiker nadat deze zich heeft aangemeld bij Windows. Hoewel deze voorbereidende bewerking wordt uitgevoerd, kan het systeem trager prestaties ondervinden, maar het resultaat wordt weergegeven zodra de bewerking is voltooid.

> [!NOTE]
> De hints die nodig zijn voor de heuristiek om de container vooraf te maken, worden gegenereerd door Office-toepassingen wanneer een gebruiker deze gebruikt. Als een gebruiker Office installeert op een nieuw systeem waarbij Application Guard is ingeschakeld, wordt de container niet vooraf gemaakt totdat een gebruiker de eerste keer een niet-vertrouwd document opent. De gebruiker houdt in dat u het eerste bestand langer kunt openen in Application Guard.

## <a name="known-issues"></a>Bekende problemen

* Als u webkoppelingen selecteert, `http` `https` wordt de browser niet geopend.
* Het plakken van inhoud met tekstopmaak (RTF) in Office-documenten die met Application Guard is geopend, wordt op dit moment niet ondersteund.
* Updates voor .NET veroorzaakte bestanden die niet kunnen worden geopend in Application Guard. Als tijdelijke oplossing kunnen gebruikers hun apparaat opnieuw opstarten wanneer ze dit probleem voordoen. Meer informatie over het probleem vindt [u bij een foutbericht bij het openen van een foutbericht bij het openen van Windows Defender Application Guard of Windows sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).
