---
title: Overzicht van het importeren van PST-bestanden
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
ms.custom:
- seo-marvel-apr2020
description: Informatie over het gebruik van de Importservice in het Beveiligings- en compliancecentrum om e-mailgegevens(PST-bestanden) bulksgewijs te importeren in postvakken van gebruikers.
ms.openlocfilehash: c645228598eb9cf0e6edca7104b8977e7eaf72f7
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/29/2021
ms.locfileid: "52162491"
---
# <a name="overview-of-importing-your-organizations-pst-files"></a>Overzicht van het importeren van PST-bestanden

> [!NOTE]
> Dit artikel is bedoeld voor beheerders. Probeert u PST-bestanden te importeren in uw eigen postvak? Zie [E-mail, contactpersonen en agenda importeren uit een .pst-bestand van Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075).

U kunt de importservice in het beveiligings- en compliancecentrum gebruiken om snel PST-bestanden bulksgewijs te importeren in Exchange Online-postvakken in uw organisatie. Er zijn twee manieren om PST-bestanden te importeren in Office 365:

- **Uploaden via het netwerk** ![Uploaden via de cloud](../media/54ab16ee-3822-4551-abef-3d926f4e1c01.png): upload de PST-bestanden via het netwerk naar een tijdelijke Azure-opslaglocatie in de Microsoft-cloud. Vervolgens kunt u de importservice van Office 365 gebruiken om de PST-gegevens te importeren in uw organisatie. 

- **Verzending van station** ![Harde schijf](../media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png): kopieer de PST-bestanden naar een met BitLocker versleutelde harde schijf en verzend de fysieke schijf naar Microsoft. Nadat Microsoft de schijf heeft ontvangen, uploadt een datacentermedewerker de gegevens naar een tijdelijke Azure-opslaglocatie in de Microsoft-cloud. Vervolgens kunt u de importservice van Office 365 gebruiken om degegevens te importeren in uw organisatie.

## <a name="step-by-step-instructions"></a>Stapsgewijze instructies
  
Raadpleeg een van de volgende onderwerpen voor gedetailleerde, stapsgewijze instructies voor het bulksgewijs importeren van PST-bestanden van uw organisatie in Office 365. 

- [PST-bestanden importeren in Office 365 via het netwerk](use-network-upload-to-import-pst-files.md)

- [PST-bestanden importeren door schijfverzending](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a>Importeren van PST-bestanden

Hier ziet u een afbeelding en beschrijving van het volledige PST-importproces. In de afbeelding ziet u de primaire werkstroom en worden de verschillen tussen de netwerkupload- en fysieke verzendmethode uitgelicht.
  
![Werkstroom van PST-importproces](../media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. **De hulpprogramma's voor de PST-import en de sleutel van een persoonlijke Azure-opslaglocatie downloaden**: de eerste stap is het downloaden van het hulpmiddel en de toegangssleutel die worden gebruikt om de PST-bestanden te importeren of te kopiëren naar een harde schijf. U verkrijgt deze op de pagina **Importeren** in het beveiligings- en compliancecentrum. De sleutel biedt u (of medewerkers van het Microsoft-gegevenscentrum bij het verzenden per schijf) de benodigde machtigingen om PST-bestanden te uploaden naar een persoonlijke en beveiligde Azure-opslaglocatie. Deze toegangssleutel is uniek voor uw organisatie en voorkomt onbevoegde toegang tot uw PST-bestanden nadat ze zijn geüpload naar de Microsoft-cloud. Voor het importeren van PST-bestanden in Microsoft 365 hoeft uw organisatie geen apart Azure-abonnement te hebben. 
    
2. **De PST-bestanden uploaden of kopiëren**: de volgende stap is afhankelijk van of u gebruikmaakt van een netwerkupload of schijfverzending om PST-bestanden te importeren. In beide gevallen gebruikt u het hulpmiddel en de beveiligde opslagsleutel die u in de vorige stap hebt verkregen.
    
    - **Uploaden via het netwerk:** het hulpprogramma AzCopy.exe (gedownload in stap 1) wordt gebruikt om uw PST-bestanden te uploaden en op te slaan in een Azure-opslaglocatie in de Microsoft-cloud. De Azure-opslaglocatie waarin u uw PST-bestanden uploadt bevindt zich in hetzelfde regionale Microsoft-datacenter als uw organisatie.
    
      Als u de PST-bestanden die u wilt importeren, wilt uploaden, moeten ze zich bevinden in een bestandsshare of -server in uw organisatie.
    
    - **Verzenden per schijf:** het hulpprogramma WAImportExport.exe (gedownload in stap 1) wordt gebruikt om uw PST-bestanden te kopiëren naar de harde schijf. Dit hulpprogramma versleutelt de harde schijf met BitLocker en kopieert dan de PST-bestanden naar de harde schijf. Net als bij de netwerkupload moeten de PST-bestanden die u wilt kopiëren naar de harde schijf zich bevinden in een bestandsshare of -server in uw organisatie.
    
3. **Een PST-importtoewijzingsbestand maken**: nadat de PST-bestanden zijn geüpload naar de Azure-opslaglocatie of gekopieerd naar de harde schijf is de volgende stap het maken van een bestand met door komma's gescheiden waarden (CSV) waarin wordt aangegeven in welke gebruikerspostvakken de PST-bestanden worden geïmporteerd (en een PST-bestand kan worden geïmporteerd in het primaire postvak of het archiefpostvak van een gebruiker). De Office 365-importservice gebruikt de gegevens om de PST-bestanden te importeren. 
    
4. **Een PST-importtaak maken**: de volgende stap is het maken van een PST-importtaak op de pagina **PST-bestanden importeren** in het beveiligings- en compliancecentrum en het PST-importtoewijzingsbestand te verzenden dat in de vorige stap is gemaakt. Voor het uploaden via het netwerk (omdat de PST-bestanden zijn geüpload naar Azure) analyseert Microsoft 365 de gegevens in de PST-bestanden en biedt u vervolgens de mogelijkheid om filters in te stellen die bepalen welke gegevens daadwerkelijk worden geïmporteerd in de postvakken die zijn opgegeven in het PST-importtoewijzingsbestand. 
    
    Voor de verzending per schijf gebeuren een aantal andere dingen in dit deel van het proces.
    
    - U verzendt de harde schijf fysiek naar een Microsoft-datacenter (het verzendadres voor het Microsoft-datacenter wordt weergegeven wanneer de importtaak wordt gemaakt).
    
    - Wanneer Microsoft de harde schijf ontvangt, zullen medewerkers van het datacentrum de PST-bestanden op de harde schijf uploaden naar de Azure-opslaglocatie voor uw organisatie. Zoals eerder aangegeven, worden uw PST-bestanden geüpload naar een Azure-opslaglocatie die zich in hetzelfde regionale Microsoft-datacenter bevindt als waar uw organisatie zich bevindt.
    
      > [!NOTE]
      > De PST-bestanden op de harde schijf worden geüpload naar Azure binnen 7 tot 10 werkdagen nadat Microsoft de harde schijf heeft ontvangen.

      Net als bij het proces voor het uploaden via het netwerk analyseert Microsoft 365 vervolgens de gegevens in de PST-bestanden en biedt u de mogelijkheid om filters in te stellen die bepalen welke gegevens daadwerkelijk worden geïmporteerd in de postvakken die zijn opgegeven in het PST-importtoewijzingsbestand.
    
    - Microsoft verzendt de harde schijf terug naar u.
    
5. **De PST-gegevens filteren die worden geïmporteerd in de postvakken**: nadat de importtaak is gemaakt (en nadat de PST-bestanden van een taak voor het verzenden per schijf zijn geüpload naar de Azure-opslaglocatie) analyseert Microsoft 365 de gegevens in de PST-bestanden (veilig en beveiligd) door de leeftijd van de items en de verschillende berichttypen in de PST-bestanden te identificeren. Wanneer de analyse is voltooid en de gegevens klaar zijn om te worden geïmporteerd, hebt u de optie om de alle gegevens in de PST-bestanden te importeren of de hoeveelheid gegevens te beperken door filters te gebruiken om te bepalen welke gegevens er worden geïmporteerd. 
    
6. **De PST-importtaak starten**: nadat de importtaak is gestart, gebruikt Microsoft 365 de informatie in het PST-importtoewijzingsbestand om de PST-bestanden vanuit de Azure-opslaglocatie te importeren in de postvakken van de gebruikers. Statusinformatie over de importtaak (inclusief informatie over elk PST-bestand dat wordt geïmporteerd) wordt weergegeven op de pagina **PST-bestanden importeren** in het beveiligings- en compliancecentrum. Wanneer de importtaak is voltooid, wordt de status voor de taak ingesteld op **Voltooid**.
  
## <a name="why-import-email-data-to-microsoft-365"></a>Waarom e-mailgegevens importeren in Microsoft 365?

- Het is een goede manier om de gearchiveerde berichtgegevens van uw organisatie te importeren in Microsoft 365.
    
- U kunt de functie [Intelligent importeren](filter-data-when-importing-pst-files.md) gebruiken om de items in PST-bestanden te filteren die u daadwerkelijk wilt importeren in de doelpostvakken. Hiermee kunt u de hoeveelheid gegevens beperken die wordt geïmporteerd, doordat u bepaalt welke gegevens wel en niet worden geïmporteerd. 
    
- Door e-mailgegevens te importeren in Microsoft 365 voldoet u aan de nalevingsbehoeften van uw organisatie, doordat u het volgende kunt doen:
    
  - [Postvakken archiveren](enable-archive-mailboxes.md) en [onbeperkt archiveren](unlimited-archiving.md) inschakelen zodat gebruikers over meer opslagruimte voor hun postvak beschikken. 
    
  - Postvakken in [juridische bewaring](./create-a-litigation-hold.md) plaatsen om inhoud te behouden. 
    
  - Gebruik het [hulpmiddel Inhoud zoeken](content-search.md) om naar postvakinhoud te zoeken. 
    
  - [eDiscovery-cases](./get-started-core-ediscovery.md) gebruiken om de juridische onderzoeken van uw organisatie te beheren 
    
  - Gebruik [bewaarbeleid](retention.md) in het beveiligings- en compliancecentrum om te bepalen hoelang postvakinhoud wordt bewaard en verwijder dan de inhoud nadat de bewaarperiode is verstreken. 

  - Gebruik [nalevingsbeleid voor communicatie](communication-compliance.md) om berichten te controleren om ervoor te zorgen dat ze voldoen aan berichtstandaarden en voeg een classificatietype toe.
    
- Het importeren van gegevens in Microsoft 365 helpt bij het beschermen tegen gegevensverlies. E-mailgegevens die zijn geïmporteerd in Microsoft 365 nemen de functies voor hoge beschikbaarheid over van Exchange Online.
    
- E-mailgegevens zijn beschikbaar voor gebruikers van alle soorten apparaten, omdat ze zijn opgeslagen in de cloud.
    
## <a name="importing-sharepoint-data-to-microsoft-365"></a>SharePoint-gegevens importeren in Microsoft 365

U kunt ook bestanden en documenten importeren in SharePoint-sites en OneDrive-accounts in uw organisatie. Zie de volgende artikelen voor meer informatie:

- [Migreren naar SharePoint Online](/sharepointmigration/migrate-to-sharepoint-online)

- [Het SharePoint-migratieprogramma](/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [Migreren naar SharePoint Online met behulp van PowerShell](/sharepointmigration/overview-spmt-ps-cmdlets)

- [Inhoud van uw bestandshares migreren naar SharePoint Online met behulp van het Azure-gegevensvak](/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)

## <a name="frequently-asked-questions-about-importing-pst-files"></a>Veelgestelde vragen over het importeren van PST-bestanden
  
Hier zijn een aantal veelgestelde vragen over het gebruik van de Office 365-importservice om PST-bestanden bulksgewijs te importeren in Microsoft 365-postvakken. 
  
- [PST-bestanden importeren via het netwerk](#using-network-upload-to-import-pst-files)
  
- [PST-bestanden importeren door schijfverzending](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a>PST-bestanden importeren via het netwerk

 **Welke machtigingen zijn vereist voor het maken van importtaken in de Office 365-importservice?**
  
U moet de rol Postvak importeren exporteren toegewezen krijgen in Exchange Online om PST-bestanden te kunnen importeren in Microsoft 365-postvakken. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer. U kunt ook een nieuwe rollengroep maken, de rol Postvak importeren exporteren daaraan toewijzen, en uzelf of andere gebruikers als lid toevoegen. Zie de secties Een rol aan een rollengroep toevoegen of Een rollengroep maken in [Rollengroepen beheren in Exchange Online](/Exchange/permissions-exo/role-groups) voor meer informatie.
  
Als u importtaken wilt maken in het beveiligings- en compliancecentrum, moet bovendien sprake zijn van een van de volgende gevallen:
  
- De rol van e-mailgeadresseerde moet aan u zijn toegewezen in Exchange Online. Deze rol wordt standaard toegewezen aan de rollengroepen Organisatiebeheer en Recipient Management.

    Of
    
- U moet globale beheerder zijn in uw organisatie.

> [!TIP]
> U zou een nieuwe rollengroep kunnen maken in Exchange Online die speciaal is bedoeld voor het importeren van PST-bestanden in Office 365. Wijs de rollen Postvak importeren exporteren en E-mailgeadresserde toe aan de nieuwe rollengroep en voeg er vervolgens leden aan toe voor het minimale niveau van machtigingen die zijn vereist voor het importeren van PST-bestanden. 
  
 **Waar kan ik uploaden via een netwerk?**
  
Uploaden via het netwerk is momenteel beschikbaar in deze regio's: Verenigde Staten, Canada, Brazilië, het Verenigd Koninkrijk, Frankrijk, Duitsland, Zwitserland, Noorwegen, Europa, India, Oost-Azië, Zuidoost-Azië, Japan, de Republiek Korea, Australië en de Verenigde Arabische Emiraten (VAE). Deze mogelijkheid komt binnenkort in meer regio's beschikbaar.
  
 **Wat zijn de kosten voor het importeren van PST-bestanden door middel van uploaden via een netwerk?**
  
PST-bestanden importeren via een netwerk is gratis.
  
Dit betekent ook dat nadat de PST-bestanden uit het Azure-opslaggebied zijn verwijderd, deze niet langer worden weergegeven in de bestandenlijst voor een voltooide importtaak in het Microsoft 365-beheercentrum. Hoewel er nog steeds een importtaak kan worden vermeld op de pagina **Gegevens importeren in Office 365**, kan de lijst met PST-bestanden leeg zijn als u de details van oudere importtaken bekijkt.
  
 **Welke versie van de PST-bestandsindeling wordt ondersteund voor importeren in Office 365?**
  
Er bestaan twee versies van de PST-bestandsindeling: ANSI en Unicode. U wordt aangeraden bestanden te importeren die de PST-bestandsindeling Unicode gebruiken. Bestanden die de PST-bestandsindeling ANSI gebruiken, bijvoorbeeld voor talen met Double Byte Character Set (DBCS), kunnen ook in Office 365 worden geïmporteerd. Zie stap 4 in [Uploaden via een netwerk gebruiken voor het importeren van PST-bestanden in Office 365](./use-network-upload-to-import-pst-files.md) voor meer informatie over het importeren van PST-bestanden in ANSI-indeling.
  
Er kunnen ook PST-bestanden vanuit Outlook 2007 en nieuwere versies in Office 365 worden geïmporteerd.
  
 **Nadat mijn PST-bestanden in het Azure-opslaggebied zijn geüpload, hoelang worden ze dan bewaard voordat ze worden verwijderd?**
  
Als u PST-bestanden importeert door middel van uploaden via een netwerk, uploadt u ze naar een Azure-blobcontainer met de naam `ingestiondata`. Als er geen importtaken worden uitgevoerd op de pagina **PST-bestanden importeren** in het beveiligings- en compliancecentrum worden alle PST-bestanden 30 dagen nadat de meest recente importtaak in het beveiligings- en compliancecentrum is gemaakt in de `ingestiondata`-container in Azure, verwijderd. Dat betekent ook dat u een nieuwe importtaak moet maken in het beveiligings- en compliancecentrum (beschreven bij stap 5 in de instructies voor uploaden via het netwerk) binnen 30 dagen nadat u PST-bestanden hebt geüpload naar Azure.
  
Dit betekent ook dat nadat de PST-bestanden uit het Azure-opslaggebied zijn verwijderd, deze niet langer worden weergegeven in de bestandenlijst voor een voltooide importtaak in het beveiligings- en compliancecentrum. Hoewel er nog steeds een importtaak kan worden vermeld op de pagina **PST-bestanden importeren** in het beveiligings- en compliancecentrum, kan de lijst met PST-bestanden leeg zijn als u de details van oudere importtaken bekijkt.
  
 **Hoelang duurt het om een PST-bestand in een postvak te importeren?**
  
Dat hangt af van de capaciteit van uw netwerk. Normaliter duurt het enkele uren voordat één terabyte (TB) aan gegevens is geüpload in het Azure-opslaggebied voor uw organisatie. Nadat de PST-bestanden naar het Azure-opslaggebied zijn gekopieerd, wordt een PST-bestand in een Microsoft 365-postvak geïmporteerd met een snelheid van minimaal 24 GB per dag. Als deze snelheid niet aan uw wensen voldoet, kunt u andere methoden overwegen om e-mailgegevens in Office 365 te plaatsen. Zie [Manieren om meerdere e-mailaccounts naar Office 365 te migreren](/Exchange/mailbox-migration/mailbox-migration) voor meer informatie.
  
Als er verschillende PST-bestanden in verschillende postvakken worden geïmporteerd, verlopen de importprocessen parallel. Met andere woorden: elk PST/postvak-paar wordt tegelijkertijd geïmporteerd. Zo zullen ook meerdere PST-bestanden tegelijkertijd worden geïmporteerd als deze in hetzelfde postvak worden geïmporteerd.
  
 **Hoe gaat het PST-importproces om met dubbele e-mailitems?**

Het PST-importproces controleert op dubbele items en kopieert geen items van een PST-bestand naar een postvak of archief als in de doelmap in het doelpostvak of doelarchief al een overeenkomend item bestaat. Als u hetzelfde PST-bestand opnieuw importeert en een andere doelmap opgeeft (met de eigenschap TargetRootFolder in het PST-importtoewijzingsbestand) dan die u in een eerdere importeertaak had opgegeven, worden alle items in het PST-bestand opnieuw geïmporteerd.
 
 **Is er een limiet aan de berichtgrootte tijdens het importeren van PST-bestanden?**
  
Ja. Als een PST-bestand een postvakitem bevat dat groter is dan 150 MB, wordt het item overgeslagen en niet geïmporteerd tijdens het importeerproces. Items die groter zijn dan 150 MB worden niet geïmporteerd, omdat 150 MB de limiet is voor de berichtgrootte in Exchange Online. Zie [Limieten voor berichten in Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits) voor meer informatie.
  
 **Blijven berichteigenschappen, zoals de datum waarop het bericht is verzonden of ontvangen, de lijst met ontvangers en dergelijke, behouden als PST-bestanden in een Microsoft 365-postvak worden geïmporteerd?**
  
Ja. De oorspronkelijke metagegevens van het bericht worden tijdens het importproces niet gewijzigd.
  
 **Is er een beperking voor het aantal niveaus in een mappenhiërarchie voor een PST-bestand dat ik naar een postvak wil importeren?**
  
Ja. U kunt een PST-bestand met 300 of meer niveaus van geneste mappen niet importeren.
  
 **Kan ik uploaden via een netwerk gebruiken voor het importeren van PST-bestanden in een inactief postvak in Office 365?**
  
Ja, deze mogelijkheid is nu beschikbaar.
  
 **Kan ik uploaden via een netwerk gebruiken voor het importeren van PST-bestanden in een onlinearchiefpostvak in een hybride Exchange-implementatie?**
  
Ja, deze mogelijkheid is nu beschikbaar. 
  
 **Kan ik PST-bestanden importeren in openbare mappen in Exchange Online door te uploaden via een netwerk?**
  
Nee, u kunt PST-bestanden niet importeren in openbare mappen.
  
### <a name="using-drive-shipping-to-import-pst-files"></a>PST-bestanden importeren door schijfverzending

 **Welke machtigingen zijn vereist voor het maken van importtaken in de Office 365-importservice?**
  
U moet de rol Postvak importeren exporteren toegewezen krijgen om PST-bestanden te kunnen importeren in Microsoft 365-postvakken. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer. U kunt ook een nieuwe rollengroep maken, de rol Postvak importeren exporteren daaraan toewijzen, en uzelf of andere gebruikers als lid toevoegen. Zie de secties Een rol aan een rollengroep toevoegen of Een rollengroep maken in [Rollengroepen beheren in Exchange Online](/Exchange/permissions-exo/role-groups) voor meer informatie.
  
Als u importtaken wilt maken in het beveiligings- en compliancecentrum, moet bovendien sprake zijn van een van de volgende gevallen:
  
- De rol van e-mailgeadresseerde moet aan u zijn toegewezen in Exchange Online. Deze rol wordt standaard toegewezen aan de rollengroepen Organisatiebeheer en Recipient Management.
    
    Of
    
- U moet globale beheerder zijn in uw organisatie.
    
> [!TIP]
> U zou een nieuwe rollengroep kunnen maken in Exchange Online die speciaal is bedoeld voor het importeren van PST-bestanden in Office 365. Wijs de rollen Postvak importeren exporteren en E-mailgeadresserde toe aan de nieuwe rollengroep en voeg er vervolgens leden aan toe voor het minimale niveau van machtigingen die zijn vereist voor het importeren van PST-bestanden. 
  
 **Waar kan ik verzenden per schijf?**
  
Verzenden per schijf is momenteel mogelijk in de Verenigde Staten, Canada, Brazilië, het Verenigd Koninkrijk, Europa, India, Oost-Azië, Zuidoost-Azië, Japan, de Republiek Korea en Australië. Deze mogelijkheid komt binnenkort in meer regio's beschikbaar.

> [!NOTE]
> Op dit moment is verzenden per schijf om PST-bestanden te importeren niet beschikbaar in Duitsland en Zwitserland. Deze veelgestelde vragen worden bijgewerkt wanneer verzenden per schijf in deze landen beschikbaar is.
  
 **Welke commerciële licentieovereenkomsten ondersteunen het verzenden per schijf?**
  
Verzenden per schijf voor het importeren van PST-bestanden in Microsoft 365 is mogelijk via een Microsoft Enterprise Agreement (EA). Verzenden per schijf is niet mogelijk via een Microsoft Products and Services Agreement (MPSA).
  
 **Wat kost het gebruik van verzenden per schijf voor het importeren van PST-bestanden in Microsoft 365?**
  
De kosten voor het gebruik van verzenden per schijf voor het importeren van PST-bestanden in Microsoft 365-postvakken bedragen 2 USD per GB aan gegevens. Als u bijvoorbeeld een harde schijf verzendt met 1000 GB (1 TB) aan PST-bestanden, dan kost dit 2000 euro. U kunt de importvergoeding met een partner delen. Zie [Een Microsoft-partner of -wederverkoper zoeken](../admin/manage/find-your-partner-or-reseller.md) voor informatie over het vinden van een partner.
  
 **Welke typen harde schijf worden voor verzenden per schijf ondersteund?**
  
Alleen 2,5 inch SSD’s (solid-state drive) of 2,5 of 3,5 inch SATA II/III interne harde schijven worden ondersteund voor gebruik met de Office 365-importservice. U kunt harde schijven gebruiken van maximaal 10 TB. Voor importtaken wordt alleen het eerste gegevensvolume op de harde schijf verwerkt. Het gegevensvolume moet worden geformatteerd met NTFS. Wanneer u gegevens kopieert naar een harde schijf, kunt u deze rechtstreeks aansluiten met behulp van een 2,5 inch SSD of 2,5 of 3,5 inch SATA II/III-kabel of u kunt deze extern aansluiten met behulp van een externe 2,5 inch SSD of 2,5 of 3,5 inch SATA II-III USB-adapter.
  
> [!IMPORTANT]
> Externe harde schijven met een ingebouwde USB-adapter worden niet ondersteund door de Office 365-importservice. Bovendien kan de schijf in de behuizing van een externe harde schijf niet worden gebruikt. Verzend geen externe harde schijven. 
  
 **Hoeveel harde schijven kan ik verzenden voor één importtaak?**
  
U kunt maximaal tien harde schijven verzenden voor één importtaak.
  
 **Hoe lang duurt het voordat mijn harde schijf bij het Microsoft-datacenter aankomt?**
  
Dat hangt van een paar dingen af, bijvoorbeeld de nabijheid van het Microsoft-datacenter en de manier waarop de harde schijf wordt verzonden (bijvoorbeeld bezorging de volgende dag, na twee dagen of via vervoer over de weg). Bij de meeste verzendbedrijven kunt u een traceercode gebruiken om de bezorgstatus te achterhalen.
  
 **Hoe lang duurt het om mijn PST-bestanden te uploaden naar Azure als mijn harde schijf is binnengekomen bij het Microsoft Datacenter?**
  
Nadat uw harde schijf is ontvangen door het Microsoft Datacenter, duurt het 7 tot 10 werkdagen voordat uw PST-bestanden zijn geüpload naar de Azure-opslaglocatie voor uw organisatie. De PST-bestanden worden geüpload naar een Azure-blobcontainer met de naam `ingestiondata`. 
  
 **Hoelang duurt het om een PST-bestand in een postvak te importeren?**
  
Nadat de PST-bestanden zijn geüpload naar de Azure-opslagruimte, analyseert Microsoft 365 de gegevens in de PST-bestanden (op een veilige manier) om de ouderdom van de items en de verschillende berichttypen in de PST-bestanden te bepalen. Wanneer deze analyse is voltooid, kunt ervoor kiezen alle gegevens te importeren in de PST-bestanden of filters in te stellen die bepalen welke gegevens worden geïmporteerd. Nadat u de taak importeren start, worden PST-bestanden geïmporteerd in een Microsoft 365-postvak met een snelheid van minimaal 24 GB per dag. Als deze snelheid niet aan uw wensen voldoet, kunt u andere methoden overwegen om e-mailgegevens in Microsoft 365 te plaatsen. Zie [Manieren om meerdere e-mailaccounts naar Microsoft 365 te migreren](/Exchange/mailbox-migration/mailbox-migration) voor meer informatie.
  
Als er verschillende PST-bestanden in verschillende postvakken worden geïmporteerd, verlopen de importprocessen parallel. Met andere woorden: elk PST/postvak-paar wordt tegelijkertijd geïmporteerd. Zo zullen ook meerdere PST-bestanden tegelijkertijd worden geïmporteerd als deze in hetzelfde postvak worden geïmporteerd.
  
 **Nadat mijn PST-bestanden in Azure zijn geüpload, hoelang worden ze dan bewaard voordat ze worden verwijderd?**
  
30 dagen nadat de meest recente importtaak is gemaakt op de pagina **PST-bestanden importeren** in het beveiligings- en compliancecentrum, worden alle PST-bestanden in de Azure-opslaglocatie voor uw organisatie (in de blobcontainer met de naam `ingestiondata`) verwijderd. 
  
Dit betekent ook dat nadat de PST-bestanden uit het Azure-opslaggebied zijn verwijderd, deze niet langer worden weergegeven in de bestandenlijst voor een voltooide importtaak in het beveiligings- en compliancecentrum. Hoewel er nog steeds een importtaak kan worden vermeld op de pagina **PST-bestanden importeren** in het beveiligings- en compliancecentrum, kan de lijst met PST-bestanden leeg zijn als u de details van oudere importtaken bekijkt. 
  
 **Welke versie van de PST-bestandsindeling wordt ondersteund voor importeren in Microsoft 365?**
  
Er bestaan twee versies van de PST-bestandsindeling: ANSI en Unicode. U wordt aangeraden bestanden te importeren die de PST-bestandsindeling Unicode gebruiken. Bestanden die de PST-bestandsindeling ANSI gebruiken, bijvoorbeeld voor talen met Double Byte Character Set (DBCS), kunnen ook in Microsoft 365 worden geïmporteerd. Zie stap 3 in [Verzenden per schijf gebruiken voor het importeren van PST-bestanden van uw organisatie in Microsoft 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file) voor meer informatie over het importeren van PST-bestanden in ANSI-indeling.
  
Er kunnen ook PST-bestanden vanuit Outlook 2007 en nieuwere versies in Microsoft 365 worden geïmporteerd.
  
 **Is er een limiet aan de berichtgrootte tijdens het importeren van PST-bestanden?**
  
Ja. Als een PST-bestand een postvakitem bevat dat groter is dan 150 MB, wordt het item overgeslagen en niet geïmporteerd tijdens het importeerproces. Items die groter zijn dan 150 MB worden niet geïmporteerd, omdat 150 MB de limiet is voor de berichtgrootte in Exchange Online. Zie [Limieten voor berichten in Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits) voor meer informatie.
  
  **Hoe gaat het PST-importproces om met dubbele e-mailitems?**

Het PST-importproces controleert op dubbele items en kopieert geen items van een PST-bestand naar een postvak of archief als in de doelmap in het doelpostvak of doelarchief al een overeenkomend item bestaat. Als u hetzelfde PST-bestand opnieuw importeert en een andere doelmap opgeeft (met de eigenschap TargetRootFolder in het PST-importtoewijzingsbestand) dan die u in een eerdere importeertaak had opgegeven, worden alle items in het PST-bestand opnieuw geïmporteerd.
 
 **Blijven berichteigenschappen, zoals de datum waarop het bericht is verzonden of ontvangen, de lijst met ontvangers en dergelijke, behouden als PST-bestanden in een Microsoft 365-postvak worden geïmporteerd?**
  
Ja. De oorspronkelijke metagegevens van het bericht worden tijdens het importproces niet gewijzigd.
  
 **Is er een beperking voor het aantal niveaus in een mappenhiërarchie voor een PST-bestand dat ik naar een postvak wil importeren?**
  
Ja. U kunt een PST-bestand met 300 of meer niveaus van geneste mappen niet importeren.
  
 **Kan ik verzenden per schijf gebruiken voor het importeren van PST-bestanden in een inactief postvak in Microsoft 365?**
  
Ja, deze mogelijkheid is nu beschikbaar. 
  
 **Kan ik verzenden per schijf gebruiken voor het importeren van PST-bestanden in een onlinearchiefpostvak in een hybride Exchange-implementatie?**
  
Ja, deze mogelijkheid is nu beschikbaar. 
  
 **Kan ik PST-bestanden importeren in openbare mappen in Exchange Online door een schijf te verzenden?**
  
Nee, u kunt PST-bestanden niet importeren in openbare mappen.
  
 **Kan Microsoft mijn harde schijf wissen voordat deze naar mij wordt teruggestuurd?**
  
Nee, Microsoft wist geen harde schijven voordat ze naar de klant worden teruggestuurd. Harde schijven worden geretourneerd in dezelfde toestand als waarin ze door Microsoft zijn ontvangen.
  
 **Kan Microsoft mijn harde schijf versnipperen in plaats dat deze wordt teruggestuurd?**
  
Nee, Microsoft vernietigt de harde schijf niet. Harde schijven worden geretourneerd in dezelfde toestand als waarin ze door Microsoft zijn ontvangen.
  
 **Welke bezorgservices kunnen worden gebruikt voor het terugzenden?**
  
Als u een klant bent in Europa of de Verenigde Staten, wordt gebruikgemaakt van FedEx om de harde schijf terug te sturen. Voor alle andere regio's wordt gebruikgemaakt van DHL.
  
 **Wat zijn de kosten van het terugsturen?**
  
Deze kosten variëren, afhankelijk van de afstand tot het Microsoft-datacenter waar u de harde schijf naartoe hebt gestuurd. U krijgt een factuur van Microsoft voor het terugsturen van uw harde schijf. Voor de kosten van het retourneren bent u zelf verantwoordelijk.
  
 **Kan ik een bezorgservice naar wens inschakelen om mijn harde schijf naar Microsoft te sturen?**
  
Ja.
  
 **Ik moet de harde schijf naar een ander land verzenden. Moet ik hiervoor nog iets speciaals doen?**
  
De harde schijf die u naar Microsoft stuurt, passeert mogelijk internationale landsgrenzen. In dat geval bent u er zelf verantwoordelijk voor dat de harde schijf en de erop opgeslagen gegevens worden geïmporteerd en/of geëxporteerd in overeenstemming met de toepasselijke wetgeving. Voordat u een harde schijf verstuurt, dient u zich ervan te overtuigen dat de schijf en de gegevens op legale wijze naar het opgegeven Microsoft-datacenter mogen worden verstuurd. Op die manier wordt de schijf op tijd bij Microsoft bezorgd.