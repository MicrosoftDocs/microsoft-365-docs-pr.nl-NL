---
title: Bepalen of gecentraliseerde implementatie van invoegingen werkt voor uw organisatie
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Bepaal of uw tenant en gebruikers aan de vereisten voldoen, zodat u gecentraliseerde implementatie gebruiken om Office-invoegins te implementeren.
ms.openlocfilehash: bd1c9ca0a034494f6556f0badca66284c3d9e1de
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214250"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>Bepalen of gecentraliseerde implementatie van invoegingen werkt voor uw organisatie

Gecentraliseerde implementatie is de aanbevolen en meest veelzijdige manier voor de meeste klanten om Office-invoegtoepassingen te implementeren voor gebruikers en groepen binnen uw organisatie. Als u een beheerder bent, gebruikt u deze richtlijnen om te bepalen of uw tenant en gebruikers aan de vereisten voldoen, zodat u gecentraliseerde implementatie gebruiken.
Gecentraliseerde implementatie ondersteunt Windows-, Mac-, iOS-, Android- en Online Office-apps.
Het kan tot 12 uur duren voordat een invoegtoepassing voor alle gebruikers wordt weergegeven.
  
## <a name="requirements"></a>Vereisten

Gecentraliseerde implementatie van invoegtoepassingvereist dat de gebruikers Microsoft 365 Apps voor ondernemingen gebruiken (en zijn aangemeld bij Office met hun organisatie-ID) en dat ze Exchange Online- en actieve Exchange Online-postvakken hebben. Uw abonnementsmap moet zich in of gefedereerd bevinden in Azure Active Directory.
U hieronder specifieke vereisten voor Office en Exchange bekijken of de [centrale controlevan de compatibiliteitscontrole voor implementatie](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker)gebruiken.

Gecentraliseerde implementatie biedt geen ondersteuning voor het volgende:
  
- Invoegtoepassingen die zijn gericht op Word, Excel of PowerPoint in Office 2013
    
- Een on-premises adreslijstservice
    
- Implementatie van invoegtoepassingen op SharePoint  

- Teams-apps
   
- Implementatie van COM- (Component Object Model) of VSTO-invoegtoepassingen (Visual Studio Tools for Office)
    
- Implementaties van Microsoft 365 die geen Exchange bevatten, zoals Microsoft 365 Apps voor bedrijven

### <a name="office-requirements"></a>Office-vereisten

- Voor Word-, Excel- en PowerPoint-invoegtoepassings moeten uw gebruikers een van de volgende opties gebruiken:
  - Op een Windows-apparaat, versie 1704 of hoger van Microsoft 365 Apps voor bedrijven.
  - Op een Mac, versie 15.34 of hoger.

- Voor Outlook moeten uw gebruikers een van de volgende opties gebruiken: 
  - Versie 1701 of hoger van Microsoft 365 Apps for enterprise.
  - Versie 1808 of hoger van Office Professional Plus 2019 of Office Standard 2019.
  - Versie 16.0.4494.1000 of hoger van Office Professional Plus 2016 (MSI) of Office Standard 2016 (MSI)\*
  - Versie 15.0.4937.1000 of hoger van Office Professional Plus 2013 (MSI) of Office Standard 2013 (MSI)\*
  - Versie 16.0.9318.1000 of hoger van Office 2016 voor Mac 
- Versie 2.75.0 of hoger van Outlook mobile voor iOS 
- Versie 2.2.145 of hoger van Outlook mobile voor Android 
    
    *MSI-versies van Outlook tonen door de beheerder geïnstalleerde invoegingen in het juiste Outlook-lint, niet in de sectie Mijn invoegingen.
    

#### <a name="find-out-if-microsoft-365-apps-for-enterprise-is-installed"></a>Controleren of Microsoft 365 Apps voor bedrijven is geïnstalleerd

Als u Microsoft 365 Apps voor ondernemingen wilt gebruiken, moet een gebruiker een Microsoft 365-account hebben en een licentie hebben gekregen. Zie [Overzicht van Microsoft 365 Apps for enterprise voor](https://go.microsoft.com/fwlink/p/?linkid=846328)meer informatie.

De eenvoudigste manier om te detecteren of een gebruiker Microsoft 365 Apps voor bedrijven heeft geïnstalleerd en deze onlangs heeft gebruikt, is door het microsoft Office-activeringsrapport te gebruiken, dat beschikbaar is in het Microsoft 365-beheercentrum. Het rapport bevat een lijst met alle gebruikers die Microsoft 365 Apps voor bedrijven hebben geactiveerd in de afgelopen 7 dagen, 30 dagen, 90 dagen of 180 dagen. Voor gecentraliseerde implementatiedoeleinden zijn de bureaubladactiveringen voor Windows of Mac de belangrijke kolommen in het rapport. U kunt het rapport exporteren naar Excel. Zie [Microsoft 365-rapporten in het beheercentrum - Microsoft Office-activeringen](../activity-reports/microsoft-office-activations.md)voor meer informatie over het rapport.
  
Als u het rapport Activeringen niet wilt gebruiken, u een gebruiker vragen een Office-toepassing zoals Word op zijn of haar machine te openen en vervolgens **Account bestand** te \> **Account**kiezen. Zie **Onder Productgegevens**ziet u **Abonnementsproduct** en **Microsoft 365 voor ondernemingen,** zoals weergegeven in de volgende afbeelding.

![Productinformatie in een Office-toepassing](../../media/product-information-microsoft-365-enterprise.png)
  
Zie [Tips voor probleemoplossing voor Microsoft 365 Apps voor bedrijven voor](https://go.microsoft.com/fwlink/p/?linkid=846339)hulp bij Microsoft 365 Apps voor bedrijven.


### <a name="exchange-online-requirements"></a>Exchange Online-vereisten

Microsoft Exchange slaat de invoegtoepassingsmanifesten op in de tenant van uw organisatie. De beheerder die invoegingen implementeert en de gebruikers die deze invoegingen ontvangen, moeten zich op een versie van Exchange Online begeven die OAuth-verificatie ondersteunt.
  
Vraag de Exchange-beheerder van uw organisatie welke configuratie in gebruik is. OAuth-connectiviteit per gebruiker kan worden geverifieerd door de PowerShell-cmdlet [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) te gebruiken. 


### <a name="centralized-deployment-compatibility-checker"></a>Controle van gecentraliseerde implementatiecompatibiliteit

Met behulp van de centrale controle van de compatibiliteit van implementatie u controleren of de gebruikers op uw tenant zijn ingesteld om gecentraliseerde implementatie voor Word, Excel en PowerPoint te gebruiken. De compatibiliteitscontrole is niet vereist voor ondersteuning voor Outlook. Download [hier](https://aka.ms/officeaddindeploymentorgcompatibilitychecker) de compatibiliteitscontrole.
  
#### <a name="run-the-compatibility-checker"></a>De compatibiliteitscontrole uitvoeren
  
1. Start een verhoogd PowerShell.exe-venster.
    
2. Voer de volgende opdracht uit:

```powershell
Import-Module O365CompatibilityChecker
```
    
3. Voer de opdracht **Aanroepen-CompatabilityCheck uit:**

```powershell
Invoke-CompatibilityCheck
```
   die u vraagt voor *_TenantDomain_* (bijvoorbeeld *TailspinToysIncorporated.onmicrosoft. </span> com)* en *_TenantAdmin-referenties_* (gebruik uw globale beheerdersreferenties) en vraagt vervolgens toestemming.
    
> [!NOTE]
> Afhankelijk van het aantal gebruikers in uw tenant, kan het afronden van de controle minuten of uren in beslag nemen. 
  
Als het hulpprogramma is uitgevoerd, wordt een uitvoerbestand gegenereerd in een CSV-indeling (door komma's gescheiden). Het bestand wordt standaard opgeslagen in **C:\windows\system32.** Het uitvoerbestand bevat de volgende gegevens:
  
- Gebruikersnaam
    
- Gebruikers-id (e-mailadres van de gebruiker)
    
- Geschikt voor Gecentraliseerde implementatie (als de overige items waar zijn)
    
- Office-abonnement - Het office-abonnement waarvoor ze een licentie hebben
    
- Office geactiveerd (als Office is geactiveerd)
    
- Ondersteund postvak (als er een OAuth-postvak wordt gebruikt)


  
## <a name="user-and-group-assignments"></a>Toewijzingen van gebruikers en groepen

De functie Gecentraliseerde implementatie ondersteunt momenteel de meeste groepen die worden ondersteund door Azure Active Directory, waaronder Microsoft 365-groepen, distributielijsten en beveiligingsgroepen.
  
> [!NOTE]
> Niet door e-mail ingeschakelde beveiligingsgroepen worden momenteel niet ondersteund. 
  
Gecentraliseerde implementatie ondersteunt toewijzingen aan individuele gebruikers, groepen en iedereen in de tenant. Gecentraliseerde implementatie ondersteunt gebruikers in groepen op het hoogste niveau of groepen zonder bovenliggende groepen, maar niet gebruikers in geneste groepen of groepen die bovenliggende groepen hebben.
   
Bekijk het volgende voorbeeld, waarin Femke, Assia en de groep Verkoopafdeling zijn toegewezen aan een invoegtoepassing. Omdat de afdeling Verkoop regio West een geneste groep is, zijn Jaap en Roelf niet toegewezen aan een invoegtoepassing.
  
![Diagram van de verkoopafdeling](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a>Controleren of een groep geneste groepen bevat

De gemakkelijkste manier om te controleren of een groep geneste groepen bevat, is het visitekaartje van de groep in Outlook te bekijken. Als u de groepsnaam invoert in het veld **Aan** van een e-mail en vervolgens de groepsnaam selecteert wanneer deze wordt opgelost, wordt u weergegeven of deze gebruikers of geneste groepen bevat. In het onderstaande voorbeeld toont het tabblad **Leden** van het Outlook-visitekaartje voor de Testgroep geen gebruikers en slechts twee subgroepen. 
  
![Tabblad Leden van Outlook-visitekaartje](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
U kunt de tegenovergestelde query uitvoeren door de groep om te zetten om te zien of deze een lid van een groep is. In het onderstaande voorbeeld kunt u op het tabblad **Lidmaatschap** van het Outlook-visitekaartje zien dat Subgroep 1 een lid van de Testgroep is. 
  
![Tabblad Lidmaatschap van het Outlook-visitekaartje](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
U kunt ook de Azure Active Directory Graph API gebruiken voor het uitvoeren van query's om de lijst met groepen in een groep te vinden. Zie [Bewerkingen op groepen | Graph API-verwijzing](https://go.microsoft.com/fwlink/p/?linkid=846342) voor meer informatie.
  
### <a name="contacting-microsoft-for-support"></a>Contact opnemen met Microsoft voor ondersteuning

Als u of uw gebruikers problemen ondervinden bij het laden van de invoegtoepassing tijdens het gebruik van Office-apps voor het web (Word, Excel, enz.), die centraal zijn geïmplementeerd, moet u mogelijk contact opnemen met microsoft-ondersteuning[(meer informatie).](../contact-support-for-business-products.md) Geef de volgende informatie over uw Microsoft 365-omgeving op in het ondersteuningsticket.
  
|**Platform**|**Foutopsporingsgegevens**|
|:-----|:-----|
|Office  <br/> | Charles/Fiddler-logboeken  <br/>  Tenant-ID ( [meer informatie over hoe](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))  <br/>  Correlatie-ID. Bekijk de bron van een van de kantoorpagina's en zoek naar de correlatie-id-waarde en stuur deze naar ondersteuning:  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|Uitgebreide clients (Windows, Mac)  <br/> | Charles/Fiddler-logboeken  <br/>  Nummers van de client-app maken (bij voorkeur als screenshot van **Bestand/Account)**  <br/> |
   

