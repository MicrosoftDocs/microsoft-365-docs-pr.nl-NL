---
title: IRM (Information Rights Management) toepassen op een lijst of bibliotheek
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
ms.collection:
- M365-security-compliance
- SPO_Content
description: U kunt IRM (Information Rights Management) gebruiken om bestanden te beheren en te beveiligen die worden gedownload uit lijsten of bibliotheken.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0648d511ee882765f1905e83ebdea673f306c186
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/12/2021
ms.locfileid: "52161691"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a>IRM (Information Rights Management) toepassen op een lijst of bibliotheek

U kunt IRM (Information Rights Management) gebruiken om bestanden te beheren en te beveiligen die worden gedownload uit lijsten of bibliotheken. Deze functie wordt alleen ondersteund in de globale microsoft-cloud. IRM wordt niet ondersteund voor SharePoint lijsten en bibliotheken in nationale cloudimplementaties.
  
## <a name="administrator-preparations-before-applying-irm"></a>Voorbereidingen voor beheerders voordat u IRM toe te passen

- De Azure Rights Management service (Azure RMS) van Azure Information Protection en het on-premises equivalent, Active Directory Rights Management Services (AD RMS), ondersteunen Information Rights Management voor sites. Er zijn geen afzonderlijke of extra installaties vereist.

- Voordat u IRM op een lijst of bibliotheek gaat toepassen, moet u IRM voor uw site inschakelen. U hebt beheerdersmachtigingen nodig om IRM in te stellen.

- Als u IRM wilt toepassen op een lijst of bibliotheek, moet u beheerdersmachtigingen hebben voor die lijst of bibliotheek.

- Als u gebruik maakt van SharePoint Online, kunnen uw gebruikers time-outs ervaren bij het downloaden van grotere met IRM beveiligde bestanden. Als u time-outs wilt voorkomen, gebruikt u uw Office programma's om IRM-beveiliging toe te passen en grotere bestanden op te slaan in een SharePoint bibliotheek die geen IRM gebruikt.

> [!NOTE]
> Als u SharePoint Server 2013 gebruikt, moet een serverbeheerder beschermers installeren op alle front-endwebservers voor elk bestandstype dat de personen in uw organisatie willen beveiligen met behulp van IRM.
  
## <a name="apply-irm-to-a-list-or-library"></a>IRM toepassen op een lijst of bibliotheek
<a name="__toc256598179"> </a>

![Information Rights Management Instellingen](../media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. Ga naar de lijst of bibliotheek waarvoor u IRM wilt configureren.

2. Selecteer op het lint het tabblad **Bibliotheek** en selecteer vervolgens **Bibliotheek Instellingen.** (Als u in een lijst werkt, selecteert u **het** tabblad Lijst en selecteert u **vervolgens Lijst Instellingen).**
    
    ![SharePoint Bibliotheekknoppen Instellingen op het lint](../media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. Selecteer **onder Machtigingen en beheer** de optie Information Rights **Management**. Als de koppeling Information Rights Management niet wordt weergegeven, is IRM mogelijk niet ingeschakeld voor uw site. Neem contact op met de serverbeheerder om te kijken of u IRM voor uw site kunt inschakelen. De **koppeling Information Rights Management** wordt niet weergegeven voor afbeeldingsbibliotheken.

4. Schakel op **de pagina Information Rights Management Instellingen** het selectievakje Machtiging beperken voor documenten in deze bibliotheek bij **downloaden** in om beperkte machtigingen toe te passen op documenten die gebruikers uit deze lijst of bibliotheek downloaden.

5. Voer in **het vak Titel van** machtigingsbeleid maken een beschrijvende naam voor het beleid in. Gebruik een naam waarmee u dit beleid kunt identificeren op basis van andere beleidsregels. Gebruik bijvoorbeeld Bedrijfs **vertrouwelijk om** beperkte machtigingen toe te passen op een lijst of bibliotheek met vertrouwelijke bedrijfsdocumenten.

6. Typ in **het** vak Beschrijving van machtigingsbeleid toevoegen een beschrijving die wordt weergegeven voor personen die deze lijst of bibliotheek gebruiken, waarin wordt uitgelegd hoe ze de documenten in deze lijst of bibliotheek moeten verwerken. U kunt bijvoorbeeld alleen de inhoud van dit document bespreken typen **met** andere werknemers als u de toegang tot de informatie in deze documenten wilt beperken tot interne werknemers. 

7. Als u extra beperkingen wilt toepassen op de documenten in deze lijst of bibliotheek, **selecteert** u Opties tonen en doet u een van de volgende opties:

|**Ga als volgende te werk:**|**Ga als volgende te werk:**|
|:-----|:-----|
|Personen toestaan documenten uit deze lijst of bibliotheek af te drukken|Schakel het **selectievakje Toestaan dat gebruikers kunnen afdrukken** in.|
|Sta personen met ten minste de machtiging Items weergeven toe om ingesloten code of macro's in een document uit te voeren.|Schakel het **selectievakje Toestaan dat gebruikers script en schermlezer** kunnen uitvoeren in voor gedownloade documenten in. Als u deze optie selecteert, kunnen gebruikers code uitvoeren om de inhoud van een document op te halen.           |
|Selecteer deze optie als u de toegang tot inhoud tot een bepaalde periode wilt beperken. Als u deze optie selecteert, verlopen de uitgiftelicenties van personen voor toegang tot de inhoud na het opgegeven aantal dagen en moeten personen terugkeren naar de server om hun referenties te verifiëren en een nieuw exemplaar te downloaden.|Schakel het selectievakje Na het downloaden de rechten voor documenttoegang na dit aantal dagen **(1-365)** in en geef vervolgens het aantal dagen op waarvoor u wilt dat het document kan worden bekeken.|
| Voorkomen dat personen documenten uploaden die geen ondersteuning bieden voor IRM naar deze lijst of bibliotheek. Als u deze optie selecteert, kunnen personen geen van de volgende bestandstypen uploaden: Bestandstypen waarop geen bijbehorende IRM-beschermers zijn geïnstalleerd op alle front-endwebservers. Bestandstypen die SharePoint Server 2010 kunnen niet worden ontsleuteld. Bestandstypen die IRM-beveiligd zijn in een ander programma.|Schakel het selectievakje Geen gebruikers toestaan om documenten te uploaden die geen **ondersteuning bieden voor IRM** in.|
|Verwijder beperkte machtigingen uit deze lijst of bibliotheek op een bepaalde datum.|Schakel het **selectievakje Toegang beperken tot de bibliotheek** stoppen bij in en selecteer vervolgens de juiste datum.|
|Besturingselement het interval dat referenties in de cache worden opgeslagen voor het programma dat is gelicentieerd om het document te openen.|Schakel het selectievakje Gebruikers moeten hun referenties verifiëren met behulp van dit **interval (dagen)** in en voer vervolgens het interval in voor cachingreferenties in het aantal dagen.|
|Groepsbeveiliging toestaan, zodat gebruikers kunnen delen met leden van dezelfde groep.|Selecteer **Groepsbeveiliging toestaan** en voer de naam van de groep in voor delen.|

8. Nadat u klaar bent met het selecteren van de opties die u wilt selecteren, selecteert u **OK.**
  
## <a name="what-is-information-rights-management"></a>Wat is Information Rights Management?
<a name="__toc256598175"> </a>

Met IRM (Information Rights Management) kunt u de acties beperken die gebruikers kunnen uitvoeren op bestanden die zijn gedownload uit lijsten of bibliotheken. IRM versleutelt de gedownloade bestanden en beperkt de set gebruikers en programma's die deze bestanden mogen ontsleutelen. IRM kan ook de rechten beperken van de gebruikers die bestanden mogen lezen, zodat ze geen acties kunnen uitvoeren, zoals kopieën van de bestanden afdrukken of tekst ervan kopiëren.
  
U kunt IRM in lijsten of bibliotheken gebruiken om de verspreiding van gevoelige inhoud te beperken. Als u bijvoorbeeld een documentbibliotheek maakt om informatie over toekomstige producten te delen met geselecteerde marketingvertegenwoordigers, kunt u IRM gebruiken om te voorkomen dat deze personen deze inhoud delen met andere werknemers in het bedrijf.
  
Op een site kunt u IRM toepassen op een hele lijst of bibliotheek, in plaats van op afzonderlijke bestanden. Hierdoor kunt u eenvoudiger een consistent beveiligingsniveau voor een hele set documenten of bestanden garanderen. IRM kan uw organisatie helpen bij het afdwingen van bedrijfsbeleid dat van toepassing is op het gebruik en de verspreiding van vertrouwelijke of bedrijfseigen informatie.
  
> [!NOTE]
> De informatie op deze pagina met betrekking tot Information Rights Management komt boven alle voorwaarden die verwijzen naar 'Information Rights Management' in een licentieovereenkomst van Microsoft SharePoint Server 2013 en SharePoint Server 2016. 
  
### <a name="how-irm-can-help-protect-content"></a>Hoe IRM inhoud kan beschermen
<a name="__toc256598176"> </a>

IRM helpt om beperkte inhoud op de volgende manieren te beveiligen:
  
- Hiermee voorkomt u dat een geautoriseerde viewer de inhoud kopieert, wijzigt, afdrukt, faxt of kopieert en kopieert voor niet-geautoriseerd gebruik
    
- Hiermee voorkomt u dat een geautoriseerde viewer de inhoud kopieert met de functie Scherm afdrukken in Microsoft Windows
    
- Hiermee voorkomt u dat een niet-geautoriseerde viewer de inhoud kan bekijken als deze per e-mail wordt verzonden nadat deze van de server is gedownload
    
- Beperkt de toegang tot inhoud tot een bepaalde periode, waarna gebruikers hun referenties moeten bevestigen en de inhoud opnieuw moeten downloaden
    
- Helpt bij het afdwingen van bedrijfsbeleid dat van toepassing is op het gebruik en de verspreiding van inhoud binnen uw organisatie
    
### <a name="how-irm-cannot-help-protect-content"></a>Hoe IRM inhoud niet kan beschermen
<a name="__toc256598177"> </a>

IRM kan beperkte inhoud niet als volgt beveiligen:
  
- Wissen, diefstal, vastleggen of verzenden door schadelijke programma's zoals Trojaanse paarden, toetsaanslagloggers en bepaalde typen spyware
    
- Verlies of beschadiging vanwege de acties van computervirussen
    
- Handmatig kopiëren of opnieuwtyping van inhoud vanuit de weergave op een scherm
    
- Digitale of filmfoto's van inhoud die wordt weergegeven op een scherm
    
- Kopiëren via het gebruik van schermopnameprogramma's van derden
    
- Kopiëren van metagegevens van inhoud (kolomwaarden) via het gebruik van programma's voor schermopname van derden of kopieer- en plakactie
  
## <a name="how-irm-works-for-lists-and-libraries"></a>Hoe IRM werkt voor lijsten en bibliotheken
<a name="__toc256598178"> </a>

IRM-beveiliging wordt toegepast op bestanden op lijst- of bibliotheekniveau. Wanneer IRM is ingeschakeld voor een bibliotheek, is rechtenbeheer van toepassing op alle bestanden in die bibliotheek. Wanneer IRM is ingeschakeld voor een lijst, is rechtenbeheer alleen van toepassing op bestanden die zijn gekoppeld aan lijstitems, niet de werkelijke lijstitems.
  
Wanneer personen bestanden downloaden in een lijst of bibliotheek met IRM-functie, worden de bestanden versleuteld, zodat alleen geautoriseerde personen ze kunnen bekijken. Elk door rechten beheerd bestand bevat ook een uitgiftelicentie die beperkingen oplegt aan de personen die het bestand bekijken. Typische beperkingen zijn het maken van een bestand alleen-lezen, het uitschakelen van het kopiëren van tekst, het voorkomen dat personen een lokale kopie opslaan en voorkomen dat personen het bestand afdrukken. Clientprogramma's die door IRM ondersteunde bestandstypen kunnen lezen, gebruiken de uitgiftelicentie in het door rechten beheerde bestand om deze beperkingen af te dwingen. Op deze manier behoudt een door rechten beheerd bestand de beveiliging ervan, zelfs nadat het van de server is gedownload.
  
De typen beperkingen die worden toegepast op een bestand wanneer het wordt gedownload uit een lijst of bibliotheek, zijn gebaseerd op de machtigingen van de afzonderlijke gebruiker op de site die het bestand bevat. In de volgende tabel wordt uitgelegd hoe de machtigingen op sites overeenkomen met IRM-machtigingen.
  
|**Machtigingen**|**IRM-machtigingen**|
|:-----|:-----|
|Machtigingen beheren, website beheren|**Volledig beheer** (zoals gedefinieerd door het clientprogramma): Met deze machtiging kan een gebruiker over het algemeen machtigingen voor door rechten beheerde inhoud lezen, bewerken, kopiëren, opslaan en wijzigen.|
|Items bewerken, Lijsten beheren, Pagina's toevoegen en aanpassen|**Bewerken,** **kopiëren** en **opslaan:** een gebruiker kan  een bestand alleen afdrukken als het selectievakje Gebruikers toestaan documenten af te drukken is ingeschakeld op de pagina Information Rights Management Instellingen voor de lijst of bibliotheek.|
|Items weergeven|**Lezen:** Een gebruiker kan het document lezen, maar kan de inhoud ervan niet kopiëren of wijzigen. Een gebruiker kan alleen afdrukken als het selectievakje **Gebruikers toestaan** documenten af te drukken is ingeschakeld op de pagina Information Rights Management Instellingen voor de lijst of bibliotheek.|
|Overige|Geen andere machtigingen komen rechtstreeks overeen met IRM-machtigingen.|
   
Wanneer u IRM inschakelen voor een lijst of bibliotheek in SharePoint Server 2013, kunt u alleen bestandstypen in die lijst of bibliotheek beveiligen waarvoor een protector is geïnstalleerd op alle front-endwebservers. Een protector is een programma dat de versleuteling en ontsleuteling van door rechten beheerde bestanden van een specifieke bestandsindeling regelt. SharePoint bevat beschermers voor de volgende bestandstypen:
  
- Microsoft Office InfoPath-formulieren
    
- De bestandsindelingen 97-2003 voor de volgende Microsoft Office: Word, Excel en PowerPoint
    
- De Office XML-indelingen openen voor de volgende Microsoft Office: Word, Excel en PowerPoint
    
- De XPS-indeling (XML Paper Specification)
    
Als uw organisatie van plan is IRM te gebruiken om andere bestandstypen te beveiligen, moet uw serverbeheerder beschermers installeren voor deze extra bestandsindelingen.
  

