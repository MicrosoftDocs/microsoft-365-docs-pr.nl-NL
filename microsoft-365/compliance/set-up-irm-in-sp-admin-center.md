---
title: IRM (Information Rights Management) instellen in het SharePoint-beheercentrum
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: Meer informatie over het gebruik SharePoint Online IRM via Microsoft Azure Active Directory Rights Management Services (RMS) om SharePoint lijsten en documentbibliotheken te beveiligen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68db84118ac8ccd7c734152aa28816db819198f7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161967"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>IRM (Information Rights Management) instellen in het SharePoint-beheercentrum

Binnen SharePoint Online wordt IRM-beveiliging toegepast op bestanden op lijst- en bibliotheekniveau. Voordat uw organisatie IRM-beveiliging kan gebruiken, moet u eerst Rights Management instellen. IRM is afhankelijk van de Azure Rights Management Azure Information Protection om gebruiksbeperkingen te versleutelen en toe te wijzen. Sommige Microsoft 365 zijn Azure Rights Management, maar niet alle. Voor meer informatie leest u Hoe Office toepassingen en services ondersteuning bieden [Azure Rights Management.](/azure/information-protection/understand-explore/office-apps-services-support)
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>IRM-service in SharePoint beheercentrum

Voordat uw organisatie IRM-beveiligen SharePoint lijsten en bibliotheken, moet u eerst de Rights Management-service voor uw organisatie activeren. Voor meer informatie over het [activeren van Azure Rights Management.](/information-protection/deploy-use/activate-service) U moet een werk- of schoolaccount met globale beheerdersbevoegdheden gebruiken om de Rights Management-service in te stellen. Anders kunt u IRM-functies niet gebruiken met SharePoint Online.
  
Nadat u de Rights Management-service heeft geactiveerd, meld u zich aan bij het SharePoint beheercentrum om IRM in te stellen.
  
1. Meld u aan als globale beheerder of SharePoint beheerder.
    
2. Selecteer het pictogram voor het startpictogram voor apps Het pictogram voor het startpictogram voor apps in Office 365 in de linkerbovenhoek en kies Beheerder om het Microsoft 365 ![ ](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) openen.  (Als u de tegel Beheerder niet ziet, hebt u geen beheerdersmachtigingen in uw organisatie.) 
    
3. Kies in het linkerdeelvenster **beheercentra** \> **SharePoint.**
    
4. Kies in het linkerdeelvenster **instellingen** en kies vervolgens **de pagina Klassieke instellingen.**
    
5. Kies in **de sectie Information Rights Management (IRM)** de optie Gebruik de **IRM-service** die is opgegeven in uw configuratie en kies vervolgens IRM vernieuwen **Instellingen.** Nadat u de IRM-instellingen hebt vernieuwd, kunnen personen in uw organisatie IRM gaan gebruiken in hun SharePoint lijsten en documentbibliotheken. De opties om dit te doen, kunnen echter maximaal een uur duren voordat ze worden weergegeven in Instellingen en Lijst Instellingen.
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>IRM-enable SharePoint documentbibliotheken en lijsten
<a name="__toc220831191"> </a>

Nadat de IRM-instellingen zijn vernieuwd, kunnen site-eigenaren hun SharePoint en documentbibliotheken IRM-beveiligen. Zie Information Rights Management toepassen op een lijst [of bibliotheek voor meer informatie.](apply-irm-to-a-list-or-library.md)
  
Wanneer site-eigenaren IRM inschakelen voor een lijst of bibliotheek, kunnen ze alle ondersteunde bestandstypen in die lijst of bibliotheek beveiligen. Wanneer IRM is ingeschakeld voor een bibliotheek, is rechtenbeheer van toepassing op alle bestanden in die bibliotheek. Wanneer u IRM inschakelen voor een lijst, is rechtenbeheer alleen van toepassing op bestanden die zijn gekoppeld aan lijstitems, niet de werkelijke lijstitems.
  
Wanneer personen bestanden downloaden in een lijst of bibliotheek met IRM-functie, worden de bestanden versleuteld, zodat alleen geautoriseerde personen ze kunnen bekijken. Elk door rechten beheerd bestand bevat ook een uitgiftelicentie die beperkingen oplegt aan de personen die het bestand bekijken. Typische beperkingen zijn het maken van een bestand alleen-lezen, het uitschakelen van het kopiëren van tekst, het voorkomen dat personen een lokale kopie opslaan en voorkomen dat personen het bestand afdrukken. Clientprogramma's die door IRM ondersteunde bestandstypen kunnen lezen, gebruiken de uitgiftelicentie in het door rechten beheerde bestand om deze beperkingen af te dwingen. Op deze manier behoudt een door rechten beheerd bestand de beveiliging ervan, zelfs nadat het is gedownload. Zie Information Rights Management toepassen op een lijst of bibliotheek als u IRM wilt inschakelen voor een lijst [of bibliotheek.](apply-irm-to-a-list-or-library.md)
  
U kunt geen documenten maken of bewerken in een IRM-bibliotheek met Office in een browser. In plaats daarvan kan één persoon tegelijk bestanden met IRM-versleutelde bestanden downloaden en bewerken. Gebruik in- en uitchecken om  *coauteuring*  te beheren of te schrijven voor meerdere gebruikers. 
  
Wanneer u een PDF-bestand downloadt vanuit een met IRM beveiligde bibliotheek, Microsoft 365 u een beveiligd PDF-bestand. De extensie van het bestand wordt niet gewijzigd, maar het bestand is wel beveiligd. Als u dit bestand wilt weergeven, hebt u de Azure Information Protection Viewer, de volledige Azure Information Protection-client of een andere toepassing nodig die het weergeven van beveiligde PDF-bestanden ondersteunt. 
  
SharePoint Online ondersteunt versleuteling van de volgende bestandstypen:
  
- PDF
    
- De bestandsindelingen 97-2003 voor de volgende Microsoft Office: Word, Excel en PowerPoint
    
- De Office XML-indelingen openen voor de volgende Microsoft Office programma's: Word, Excel en PowerPoint
    
- De XPS-indeling (XML Paper Specification)
 
> [!NOTE]
> IRM-beveiliging kan niet worden toegepast op beveiligde documenten (zoals digitaal ondertekende PDF-bestanden) omdat SharePoint het document bij uploaden moet openen. 

## <a name="next-steps"></a>Volgende stappen
<a name="__toc220831191"> </a>

Nadat u IRM voor SharePoint Online hebt ingeschakeld, kunt u beginnen met het toepassen van rechtenbeheer op lijsten en bibliotheken. Zie Information Rights Management toepassen op een lijst of bibliotheek voor [meer informatie.](apply-irm-to-a-list-or-library.md)
  
De nieuwe OneDrive-synchronisatieclient voor Windows ondersteunt nu het synchroniseren van met IRM beveiligde SharePoint-documentbibliotheken en OneDrive-locaties (zolang de IRM-instelling voor de bibliotheek niet is ingesteld op het verlopen van toegangsrechten voor documenten). Zie De nieuwe synchronisatieclient voor OneDrive implementeren voor meer informatie of om aan de slag te gaan met het implementeren van de nieuwe synchronisatieclient voor [Windows.](/onedrive/deploy-on-windows)
  
[Top of page](set-up-irm-in-sp-admin-center.md)