---
title: Inleiding tot informatiebeheerbeleid
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2014
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- WSU150
- SPO160
- OSU150
- MET150
ms.assetid: 63a0b501-ba59-44b7-a35c-999f3be057b2
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Lees hoe u beleidsregels voor informatiebeheer kunt gebruiken om zaken te beheren en bij te houden, zoals hoe lang inhoud wordt bewaard of welke acties gebruikers met die inhoud kunnen uitvoeren.
ms.openlocfilehash: dfb1aeb3dbd3a2b17f18bbd03d5f4d3e198e4c47
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "52161469"
---
# <a name="introduction-to-information-management-policies"></a>Inleiding tot informatiebeheerbeleid

Een informatiebeheerbeleid is een set regels voor een type inhoud. Met beleidsregels voor informatiebeheer kunnen organisaties zaken beheren en bijhouden, zoals hoe lang inhoud wordt bewaard of welke acties gebruikers met die inhoud kunnen uitvoeren. Informatiebeheerbeleid kan organisaties helpen om te voldoen aan wettelijke of overheidsvoorschriften, of ze kunnen interne bedrijfsprocessen gewoon afdwingen. 
  
Een organisatie die zich bijvoorbeeld moet houden aan overheidsvoorschriften die vereisen dat ze 'adequate controles' van hun financiële overzichten aantonen, kan een of meer informatiebeheerbeleidsregels maken die specifieke acties in het ontwerp- en goedkeuringsproces controleren voor alle documenten met betrekking tot financiële archivering.
  
Zie Beleidsregels voor informatiebeheer maken [en toepassen](create-info-mgmt-policies.md)voor informatie.
  
## <a name="features-of-information-management-policies"></a>Functies van informatiebeheerbeleid
<a name="__top"> </a>

Er zijn vier basiscategorieën met vooraf gedefinieerde beleidsfuncties die organisaties afzonderlijk of in combinatie kunnen gebruiken om inhoud en processen te beheren. 
  
![Inhoudsbeleidstypen](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
Met de functie Controlebeleid kunnen organisaties analyseren hoe hun inhoudsbeheersystemen worden gebruikt door gebeurtenissen en bewerkingen te registreren die worden uitgevoerd op documenten en lijstitems. U kunt de functie Controlebeleid zo configureren dat gebeurtenissen worden bijgehouden, zoals wanneer een document of item wordt bewerkt, bekeken, ingecheckt, uitgecheckt, verwijderd of de machtigingen zijn gewijzigd. Alle controlegegevens worden opgeslagen in één auditlogboek op de server en sitebeheerders kunnen er rapporten op uitvoeren. 
  
Met de functie Verloopbeleid kunnen organisaties op een consistente, bij te houden manier verouderd inhoud van hun sites verwijderen of verwijderen. Op deze manier kunt u de kosten en risico's beheren die samenhangen met het behouden van verouderd materiaal. U kunt een verloopbeleid zo configureren dat bepaalde soorten inhoud verlopen op een bepaalde datum of binnen een periode nadat het document is gemaakt of voor het laatst is gewijzigd.
  
Organisaties kunnen ook aangepaste beleidsfuncties maken en implementeren om aan specifieke behoeften te voldoen. Een productieorganisatie wil bijvoorbeeld een informatiebeheerbeleid definiëren voor alle conceptdocumenten met productontwerpspecificaties die gebruikers verbieden kopieën van deze documenten af te drukken op niet-secureprinters. Als u dit soort informatiebeheerbeleid wilt definiëren, kunt u een beleidsfunctie afdrukbeperking maken en implementeren die kan worden toegevoegd aan het relevante informatiebeheerbeleid voor het inhoudstype productontwerpspecificatie.
  
## <a name="locations-to-use-an-information-management-policy"></a>Locaties voor het gebruik van een informatiebeheerbeleid
<a name="__toc340213528"> </a>

Als u een informatiebeheerbeleid wilt implementeren, moet u dit toevoegen aan een lijst, bibliotheek of inhoudstype op een site. De locatie waar u een informatiebeheerbeleid maakt of toevoegt, is van invloed op de manier waarop het beleid breed wordt toegepast of hoe breed het beleid kan worden gebruikt. U kunt:
  
 **Een siteverzamelingsbeleid maken en dit beleid vervolgens toevoegen aan een inhoudstype, lijst of bibliotheek** U kunt een siteverzamelingsbeleid maken in de lijst Beleid op de site op het hoogste niveau van een siteverzameling. Nadat u een siteverzamelingsbeleid hebt gemaakt, kunt u het exporteren, zodat beheerders van andere siteverzamelingen het kunnen importeren in de lijst Beleid. Als u een exporteerbaar siteverzamelingsbeleid maakt, kunt u het informatiebeheerbeleid standaardiseren op de sites in uw organisatie. 
  
Wanneer u een siteverzamelingsbeleid toevoegt aan een site-inhoudstype en een exemplaar van dat site-inhoudstype wordt toegevoegd aan een lijst of bibliotheek, kan de eigenaar van die lijst of bibliotheek het siteverzamelingsbeleid voor de lijst of bibliotheek niet wijzigen. Het toevoegen van een siteverzamelingsbeleid aan een site-inhoudstype is een goede manier om ervoor te zorgen dat siteverzamelingsbeleid wordt afgedwongen op elk niveau van uw sitehiërarchie.
  
![Koppeling Inhoudstypebeleidssjabloon op Instellingen site](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
 Een informatiebeheerbeleid maken voor een site-inhoudstype in de galerie **Site-inhoudstype** van de site op het hoogste niveau en dit inhoudstype toevoegen aan een of meer lijsten of bibliotheken U kunt ook rechtstreeks een informatiebeheerbeleid maken voor een site-inhoudstype en vervolgens een exemplaar van dat site-inhoudstype koppelen aan meerdere lijsten of bibliotheken. Als u op deze manier een informatiebeheerbeleid maakt, heeft elk item in de siteverzameling van dat inhoudstype of een inhoudstype dat van dat inhoudstype wordt overgenomen, het beleid. Als u echter rechtstreeks een informatiebeheerbeleid maakt voor een site-inhoudstype, is het moeilijker om dit informatiebeheerbeleid opnieuw te gebruiken in andere siteverzamelingen, omdat beleidsregels die op deze manier worden gemaakt, niet kunnen worden geëxporteerd. 
  
![Koppeling site-inhoudstypen op sitepagina Instellingen pagina](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
![Koppeling informatiebeheerbeleid op instellingenpagina voor een site-inhoudstype](../media/15d83a34-6c8f-4b6e-b6ee-e9b0a70cbb4b.png)
  
Opmerking Als u wilt bepalen welk beleid wordt gebruikt in een siteverzameling, kunnen beheerders van siteverzamelingen de mogelijkheid uitschakelen om beleidsfuncties rechtstreeks op een inhoudstype in te stellen. Wanneer deze beperking van kracht is, kunnen gebruikers die inhoudstypen maken, alleen beleid selecteren in de lijst Beleidsregels voor siteverzamelingen.
  
 **Een informatiebeheerbeleid maken voor een lijst of bibliotheek** Als uw organisatie een specifiek informatiebeheerbeleid moet toepassen op een zeer beperkte set inhoud, kunt u een informatiebeheerbeleid maken dat alleen van toepassing is op een afzonderlijke lijst of bibliotheek. Deze methode voor het maken van een informatiebeheerbeleid is het minst flexibel, omdat het beleid slechts op één locatie van toepassing is en het niet kan worden geëxporteerd of hergebruikt voor andere locaties. Soms moet u echter unieke informatiebeheerbeleidsregels maken met beperkte toepassingsmogelijkheden om specifieke situaties aan te pakken. 
  
![Koppeling informatiebeheerbeleid op instellingenpagina voor documentbibliotheek](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
Opmerkingen 
  
U kunt alleen een informatiebeheerbeleid voor een lijst of bibliotheek maken als deze lijst of bibliotheek niet meerdere inhoudstypen ondersteunt. Als een lijst of bibliotheek meerdere inhoudstypen ondersteunt, moet u een informatiebeheerbeleid definiëren voor elk afzonderlijk lijstinhoudstype dat is gekoppeld aan die lijst of bibliotheek. (Exemplaren van een site-inhoudstype dat is gekoppeld aan een specifieke lijst of bibliotheek, worden lijstinhoudstypen genoemd.)
  
Als u wilt bepalen welk beleid wordt gebruikt in een siteverzameling, kunnen beheerders van siteverzamelingen de mogelijkheid uitschakelen om beleidsfuncties rechtstreeks op een lijst of bibliotheek in te stellen. Wanneer deze beperking van kracht is, kunnen gebruikers die lijsten of bibliotheken beheren, alleen beleid selecteren in de lijst Beleidsregels voor siteverzamelingen.
  
[Een informatiebeheerbeleid is een set regels voor een type inhoud. Met beleidsregels voor informatiebeheer kunnen organisaties zaken beheren en bijhouden, zoals hoe lang inhoud wordt bewaard of welke acties gebruikers met die inhoud kunnen uitvoeren. Informatiebeheerbeleid kan organisaties helpen om te voldoen aan wettelijke of overheidsvoorschriften, of ze kunnen interne bedrijfsprocessen gewoon afdwingen. Een organisatie die zich bijvoorbeeld moet houden aan overheidsvoorschriften die vereisen dat ze 'adequate controles' van hun financiële overzichten aantonen, kan een of meer informatiebeheerbeleidsregels maken die specifieke acties in het ontwerp- en goedkeuringsproces controleren voor alle documenten met betrekking tot financiële archivering. Zie Beleidsregels voor informatiebeheer maken en toepassen voor informatie.](intro-to-info-mgmt-policies.md#__top)
  

