---
title: 'Stap 3: Levering van Office- en LOB-apps'
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/27/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Leer hoe u Office-en LOB-apps kunt leveren.
ms.openlocfilehash: 1cead6563719c49ab591122e0c3864818746d4f0
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809147"
---
# <a name="step-3-office-and-lob-app-delivery"></a>Stap 3: Levering van Office- en LOB-apps

![](../media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-6.png" alt="Step 3" height="130" width="130" /></td>
<td><p><strong>Stap 3: Levering van Office- en LOB-apps</strong></p>
<p>Zorg ervoor dat uw-apps zijn verpakt en gereed zijn voor geautomatiseerde installatie. Ontdek hoe het klik-en-klaar-pakket met Office 365 ProPlus u nieuwe opties biedt voor de configuratie, de levering en het behoud van uw Office-apps.</p></td>
<td><a href="https://aka.ms/ddev3" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-16.png" alt="Step 3" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>De levering van Office- en LOB-apps is de derde stap in ons aanbevolen implementatieproces voor de installatie en het beheer van Office en LOB. Voor een geslaagde implementatie moet u de eerste twee stappen niet overslaan.  Ga naar het [Implementatiecentrum voor desktops](https://aka.ms/HowToShift) om het volledige desktop-implementatieproces te zien.
>

U bent nu klaar om Office en uw Line-of-Business-apps te leveren. U kunt dit op verschillende manieren doen, onder andere met enkele interessante nieuwe opties. Sommige toepassingen zijn alleen beschikbaar als een 32-bits of 64-bits versie, maar andere toepassingen, zoals Office 365 ProPlus, bieden standaard zowel de 32-bits als 64-bits code. Een van de belangrijkste beslissingen die u moet nemen, is de versie die u wilt implementeren. Als u beter gebruik wilt maken van de rekenkracht en het RAM-geheugen op nieuwe apparaten, wordt u aangeraden de 64-bits versie te gebruiken als er geen 32-bits afhankelijkheden zijn. Als u wilt weten welke compatibiliteitsproblemen met een invoegtoepassing of bestand kunnen optreden, wordt u aangeraden om Stap 1 Apparaat en App Readiness nog een door te nemen voordat u doorgaat.

Als er geen belemmeringen zijn, raden we u aan om 64-bits versies van alle apps te implementeren, waaronder Microsoft Office. 64-bits native gecompileerde apps bieden de beste prestaties en zijn de meest geschikte keuze voor de toekomst.

Er zijn veel methoden en modellen voor het installeren van apps in Windows, maar we gaan nu eerst kijken naar de leveringsopties.

[Toepassingsbeheer voor Windows 10](https://docs.microsoft.com/windows/application-management/)

## <a name="msi-based-deployments"></a>Implementaties op basis van MSI

Voor uw Line-of-Business-apps gebruikt u waarschijnlijk MSI-pakketten of uitvoerbare bestanden en installeert u apps als onderdeel van een takenreeks voor de implementatie van een besturingssysteem. Windows 10 blijft werken met deze pakketten.

Software-implementatieprogramma's, zoals Microsoft Endpoint Configuration Manager en Microsoft Intune, zijn ook geoptimaliseerd voor het leveren van apps met MSI-pakketten. Wanneer u uw apps in Windows 10 hebt gevalideerd, kunt u Microsoft Endpoint Configuration Manager (Current Branch) gebruiken voor levering van de app. Als u de bedrijfsportal van Microsoft Intune gebruikt, kunt u de keuze van de door IT goedgekeurde apps die beschikbaar zijn voor uw organisatie, uitbreiden met de meest recente toepassingen en kunnen gebruikers zelf selecteren wat ze nodig hebben.

![](../media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-3.png)

## <a name="pc-imaging"></a>PC-imaging

Een ander veelgebruikte methode voor de levering van apps is PC-imaging. In dit geval worden toepassingen geïnstalleerd via een takenreeks of handmatig op een voorbeeld-pc. Vervolgens wordt een systeeminstallatiekopie vastgelegd met de vereiste toepassingen die vooraf zijn geïnstalleerd. Met de imaging-benadering voor het maken en vastleggen bespaart u tijd bij het inrichten van nieuwe pc's, maar mogelijk verlopen de besturingssystemen en apps in de installatiekopie sneller. Het model voor cumulatieve updates in Windows 10 en Office 365 ProPlus hulp bij dit probleem, maar kan het niet volledig verhelpen. Daarom wordt u aangeraden een thin-image-benadering te gebruiken, waarbij uw toepassingen vanaf een andere locatie dan de installatiekopie worden geïnstalleerd tijdens de implementatie.

![](../media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-4.png)

Als u Office 365 ProPlus in uw installatiekopie wilt opnemen, is activering door de gebruiker vereist. Dit kan niet vooraf worden geactiveerd door de systeembeheerder. Gebruik het Office-implementatieprogramma om Office vooraf te installeren op het apparaat dat u repliceert en sla de aanmelding door de gebruiker over. Wanneer de installatiekopie is geïmplementeerd, kunnen eindgebruikers zich aanmelden met hun Office 365-referenties en Office 365 ProPlus activeren.

[Een takenreeks maken om een besturingssysteem te installeren](https://docs.microsoft.com/configmgr/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system)

[Office 365 ProPlus implementeren als onderdeel van een installatiekopie van het besturingssysteem](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-as-part-of-an-operating-system-image)

## <a name="office-click-to-run"></a>Office Klik-en-Klaar 

Office 365 ProPlus is geïnstalleerd met Klik-en-Klaar. Klik-en-Klaar komt als vervanging voor het MSI-pakket in elke versie van de aanstaande release van Office 2019 voor Windows. Het biedt een aantal voordelen, zoals snellere installaties, snellere en efficiëntere updates en een schonere manier om de installatie ongedaan te maken. 

Programma's die worden geleverd via Klik-en-Klaar, worden uitgevoerd in een virtuele toepassingsomgeving en kunnen zonder conflict op uw computer bestaan naast andere toepassingen. Daarnaast hebben ze slechts de helft van de schijfruimte nodig in vergelijking met een MSI-pakket. Office-toepassingen worden geleverd en beheerd via het [Office-implementatieprogramma](https://www.microsoft.com/download/details.aspx?id=49117). Hiervoor is het installatieprogramma van Office nodig om uw Office-apps te downloaden, te configureren en aan te passen. Met het Office-implementatieprogramma leest u een XML-configuratiebestand met aanwijzingen over de metagegevens voor het configureren en aanpassen van uw Office-installatie.

Microsoft raadt u aan de [Office Customization Tool](https://config.office.com/) te gebruiken voor het aanpassen van de implementatie-instellingen en het maken van uw XML-bestand voor de configuratie. Met de Office Customization Tool kunt u instellen welke toepassingen en talen worden geïnstalleerd en hoe de toepassingen worden bijgewerkt. Daarnaast kunt u de voorkeuren voor toepassingen en instellingen voor de installatie-ervaring aangeven.

![](../media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-7.png)

U kunt ook nog steeds Configuration Manager gebruiken voor een grootschalige implementatie van Office 365 ProPlus. Configuration Manager (Current Branch) biedt ingebouwde ondersteuning voor de bijgewerkte Office Customization Tool, pakketaanpassing voor Klik-en-Klaar bij de installatie en systeemeigen ondersteuning voor software-updatebeheer na de installatie.

![](../media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-6.png)

[Implementatiehandleiding voor Office 365 ProPlus](https://docs.microsoft.com/deployoffice/deployment-guide-for-office-365-proplus)

[Bestaande MSI-versies van Office verwijderen bij het uitvoeren van een upgrade naar Office 365 ProPlus](https://docs.microsoft.com/deployoffice/upgrade-from-msi-version)

[Office 365 ProPlus met Configuration Manager beheren](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates)

[Office 365-apps toewijzen aan Windows 10-apparaten met Microsoft Intune](https://docs.microsoft.com/intune/apps-add-office365)

## <a name="browser-based-apps"></a>Browser-apps

Er zijn enkele zaken die u moet overwegen om ervoor te zorgen dat uw browser-toepassingen blijven werken zoals verwacht. Als u specifieke websites en apps hebt die compatibiliteitsproblemen veroorzaken met Microsoft Edge, kunt u de lijst met websites voor Ondernemingsmodus gebruiken zodat de websites automatisch worden geopend met Internet Explorer 11.

Als u weet dat uw intranetsites niet goed werken met Microsoft Edge, kunt u instellen dat alle intranetsites automatisch worden geopend met Internet Explorer 11. Bij dit proces wordt een XML-bestand gebruikt om te bepalen of IE11 wordt gebruikt voor elke site en wordt Groepsbeleid gebruikt om instellingen af te dwingen.

[Wat is de Ondernemingsmodus?](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#what-is-enterprise-mode)

Tot nu toe hebben we bekende implementatiemethoden besproken. Er zijn echter twee nieuwe benaderingen voor het implementeren van apps.

## <a name="microsoft-store-for-business"></a>Microsoft Store voor Bedrijven 

Microsoft Store voor Bedrijven biedt een flexibele manier om gratis en betaalde apps voor Windows 10-apparaten op schaal te ontdekken, te verkrijgen, te beheren en te distribueren. Als IT-beheerder kunt u de geselecteerde apps voor Microsoft Store, samen met uw aangepaste apps, publiceren naar uw eigen persoonlijke store wanneer u licenties toewijst en opnieuw gebruikt. Uw gebruikers worden alleen doorgestuurd naar deze store. Hierdoor kunnen ze alleen goedgekeurde apps vinden en installeren.

Store-apps kunnen zelf als UWP-apps worden gemaakt of u kunt de Desktopbrug gebruiken om uw bestaande apps voor de store te hergebruiken en moderne ervaringen voor Windows 10 toe te voegen. Afgezien van de code die u gebruikt om de Windows 10-ervaring te verrijken, blijft de app ongewijzigd en wordt nog steeds uitgevoerd in de gebruikersmodus voor volledig vertrouwen.

## <a name="msix-containerization"></a>MSIX-containervorming

MSIX is een nieuwe optie voor het inpakken van toepassingen. MSIX maakt gebruik van de beschikbare technologie voor containervorming in Windows, waarbij de beste aspecten van Klik-en-Klaar-, UWP- en MSI-pakketten worden samengebracht. Hulpprogramma's voor het migreren van bestaande installatieprogramma's, zoals EXE, MSI, APPV en APPX, zijn rechtstreeks ingebouwd in MSIX, zodat MSIX-containervorming een geïntegreerd pad biedt voor de vele installatietechnologieën die tegenwoordig worden gebruikt. MSIX-ondersteuning maakt deel uit van de huidige versies van Windows: elk apparaat met Windows 10 RS5 of nieuwer bevat alles wat u nodig hebt om met MSIX verpakte apps te installeren en uit te voeren. In Windows 10 worden ontvangen MSIX-containers dynamisch geïntegreerd en worden de toepassingen gescheiden van het besturingssysteem.

Met containervorming worden pakketten volledig verwijderd, in tegenstelling tot veel MSI- en EXE-pakketten die items mogelijk achterlaten op het systeem. Daarnaast zijn alleen standaardgebruikersreferenties vereist om toepassingen te installeren. U hoeft geen beheerdersreferenties te hebben om MSIX-containers te installeren. MSIX containers kunnen ook efficiënter worden bijgewerkt. Wanneer een update wordt gepubliceerd, worden alleen netto nieuwe binaire bestanden toegepast door het gebruik van differentiaties op blokniveau. Hierdoor wordt de nettolading van updates verkleind, zodat de implementatie minder netwerkbandbreedte verbruikt.

Meer informatie over MSIX vindt u via de [site van de MSIX-tech-community ](https://techcommunity.microsoft.com/t5/MSIX/ct-p/MSIX)

## <a name="next-step"></a>Volgende stap

## <a name="step-4-user-files-and-settings"></a>[Stap 4: gebruikersbestanden en -instellingen](https://aka.ms/mdd4)

## <a name="previous-step"></a>Vorige stap

## <a name="step-2-directory-and-network-readiness"></a>[Stap 2: gereedheid van directory en netwerk](https://aka.ms/mdd2) 
