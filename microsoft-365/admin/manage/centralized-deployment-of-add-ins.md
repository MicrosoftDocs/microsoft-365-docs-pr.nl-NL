---
title: Bepalen of gecentraliseerde implementatie van invoegtoepassingen werkt voor uw organisatie
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Bepaal of uw Tenant en gebruikers aan de vereisten voldoen, zodat u gecentraliseerde implementatie kunt gebruiken om Office-invoegtoepassingen te implementeren.
ms.openlocfilehash: 04c5f9090ca788f00f2d17d3af59e8022195e9be
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519363"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>Bepalen of gecentraliseerde implementatie van invoegtoepassingen werkt voor uw organisatie

Gecentraliseerde implementatie is de aanbevolen en krach functionele manier voor de meeste klanten om Office-invoegtoepassingen te implementeren voor gebruikers en groepen binnen uw organisatie. Als u een beheerder bent, kunt u deze richtlijnen gebruiken om te bepalen of uw organisatie en gebruikers aan de vereisten voldoen, zodat u gecentraliseerde implementatie kunt gebruiken.

Gecentraliseerde implementatie biedt de volgende voordelen:
  
- Een globale beheerder kan een invoegtoepassing rechtstreeks aan een gebruiker toewijzen, aan meerdere gebruikers via een groep of aan iedereen in de organisatie.
    
- Wanneer de relevante Office-toepassing wordt gestart, wordt de invoegtoepassing automatisch gedownload. Als de invoegtoepassing ondersteuning biedt voor opdrachten van invoegtoepassingen, wordt de invoegtoepassing automatisch weergegeven op het lint in de Office-toepassing.
    
- Invoegtoepassingen worden niet langer weergegeven voor gebruikers als de beheerder de invoegtoepassing uitschakelt of verwijdert, of als de gebruiker wordt verwijderd uit Azure Active Directory of een groep waaraan de invoegtoepassing is toegewezen.

Gecentraliseerde implementatie ondersteunt drie bureaublad platforms, Windows-apps en online Office-apps. Gecentraliseerde implementatie biedt ook ondersteuning voor iOS en Android (alleen voor mobiele Outlook-invoegtoepassingen).

Het kan maximaal 24 uur duren voordat een invoegtoepassing aan alle gebruikers wordt weergegeven.
  
## <a name="requirements"></a>Vereisten

Gecentraliseerde implementatie van invoegtoepassingen vereist dat de gebruikers Microsoft 365 Enterprise-Sku's: E3/E5/F3 of Business Sku's: Business Basic, Business Standard, Business Premium (en zijn aangemeld bij Office met hun organisatie-ID), en de postvakken Exchange Online en Active Exchange Online gebruiken. Uw abonnements gids moet zijn aangemeld of federatief zijn voor Azure Active Directory.
U kunt de specifieke vereisten voor Office en Exchange bekijken of de [compatibiliteitscontrole voor gecentraliseerde implementatie](#centralized-deployment-compatibility-checker)gebruiken.

Gecentraliseerde implementatie biedt geen ondersteuning voor het volgende:
  
- Invoegtoepassingen die zijn gericht op Word, Excel of PowerPoint in Office 2013 
- Een on-premises adreslijstservice
- Implementatie van invoegtoepassing aan een Exchange on-premises Postvak
- Implementatie van invoegtoepassingen op SharePoint  
- Teams-apps
- Implementatie van COM-invoegtoepassingen (Component Object Model) of VSTO-invoegtoepassingen (Visual Studio Tools for Office).
- Implementaties van Microsoft 365 die geen Exchange Online bevatten, zoals Sku's: Microsoft 365 apps for Business en Microsoft 365 apps for Enterprise.

### <a name="office-requirements"></a>Office-vereisten

- Voor Word-, Excel-en PowerPoint-invoegtoepassingen moeten de gebruikers een van de volgende handelingen uitvoeren:
  - Op een Windows-apparaat, versie 1704 of hoger van Microsoft 365 Enterprise Sku's: E3/E5/F3 of Business Sku's: Business Basic, Business Standard, Business Premium.
  - Op een Mac, versie 15,34 of hoger.

- Voor Outlook moeten de gebruikers een van de volgende handelingen uitvoeren: 
  - Versie 1701 of hoger van Microsoft 365 Enterprise Sku's: E3/E5/F3 of Business Sku's: Business Basic, Business Standard, Business Premium.
  - Versie 1808 of hoger van Office Professional Plus 2019 of Office Standard 2019.
  - Versie 16.0.4494.1000 of hoger van Office Professional Plus 2016 (MSI) of Office Standard 2016 (MSI)\*
  - Versie 15.0.4937.1000 of hoger van Office Professional Plus 2013 (MSI) of Office Standard 2013 (MSI)\*
  - Versie 16.0.9318.1000 of hoger van Office 2016 voor Mac 
- Versie 2.75.0 of hoger van Outlook Mobile voor iOS 
- Versie 2.2.145 of hoger van Outlook Mobile voor Android 
    
    * MSI-versies van Outlook tonen beheerders geïnstalleerde invoegtoepassingen op het juiste Outlook-lint, niet de sectie ' mijn invoegtoepassingen '.

### <a name="exchange-online-requirements"></a>Vereisten voor Exchange Online

Microsoft Exchange slaat de invoegtoepassingsmanifesten op in de tenant van uw organisatie. De beheerder die invoegtoepassingen implementeert en de gebruikers die deze invoegtoepassingen ontvangen, moeten beschikken over een versie van Exchange Online die OAuth-verificatie ondersteunt.
  
Vraag de Exchange-beheerder van uw organisatie welke configuratie in gebruik is. OAuth-connectiviteit per gebruiker kan worden geverifieerd door de PowerShell-cmdlet [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) te gebruiken. 


### <a name="centralized-deployment-compatibility-checker"></a>Compatibiliteitscontrole voor gecentraliseerde implementatie

Met behulp van de compatibiliteitscontrole voor gecentraliseerde implementatie kunt u controleren of de gebruikers in uw Tenant zijn geconfigureerd voor het gebruik van gecentraliseerde implementatie voor Word, Excel en PowerPoint. De compatibiliteitscontrole is niet vereist voor ondersteuning voor Outlook. Download [hier](https://aka.ms/officeaddindeploymentorgcompatibilitychecker) de compatibiliteitscontrole.
  
#### <a name="run-the-compatibility-checker"></a>De compatibiliteitscontrole uitvoeren
  
1. Start een verhoogd PowerShell.exe-venster.
    
2. Voer de volgende opdracht uit:

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. Voer de opdracht **invoke-CompatabilityCheck** uit:

   ```powershell
   Invoke-CompatibilityCheck
   ```
   Met deze opdracht vraagt u om  *_TenantDomain_* (bijvoorbeeld *TailspinToysIncorporated. onmicrosoft. </span> com*-en  *_TenantAdmin_* -referenties (gebruik uw globale-beheerdersreferenties) en vraagt u om toestemming.
    
   > [!NOTE]
   > Afhankelijk van het aantal gebruikers in uw tenant, kan het afronden van de controle minuten of uren in beslag nemen. 
  
Als het hulpprogramma is uitgevoerd, wordt een uitvoerbestand gegenereerd in een CSV-indeling (door komma's gescheiden). Het bestand wordt standaard opgeslagen in **C:\Windows\System32** . Het uitvoerbestand bevat de volgende gegevens:
  
- Gebruikersnaam
    
- Gebruikers-id (e-mailadres van de gebruiker)
    
- Geschikt voor Gecentraliseerde implementatie (als de overige items waar zijn)
    
- Kantoor abonnement: het abonnement van de Office-licentie voor
    
- Office geactiveerd (als Office is geactiveerd)
    
- Ondersteund postvak (als er een OAuth-postvak wordt gebruikt)

> [!NOTE]
> Meervoudige verificatie wordt niet ondersteund wanneer u de PowerShell-module van de centrale implementatie gebruikt.
  
## <a name="user-and-group-assignments"></a>Toewijzingen van gebruikers en groepen

De functie gecentraliseerde implementatie ondersteunt momenteel de meeste groepen die worden ondersteund door Azure Active Directory, waaronder Microsoft 365-groepen, distributielijsten en beveiligingsgroepen.
  
> [!NOTE]
> Niet door e-mail ingeschakelde beveiligingsgroepen worden momenteel niet ondersteund. 
  
Gecentraliseerde implementatie ondersteunt opdrachten voor afzonderlijke gebruikers, groepen en iedereen in de Tenant. Gecentraliseerde implementatie ondersteunt gebruikers in groepen op het hoogste niveau of groepen zonder bovenliggende groepen, maar niet gebruikers in geneste groepen of groepen die bovenliggende groepen hebben.
   
Bekijk het volgende voorbeeld, waarin Femke, Assia en de groep Verkoopafdeling zijn toegewezen aan een invoegtoepassing. Omdat de afdeling Verkoop regio West een geneste groep is, zijn Jaap en Roelf niet toegewezen aan een invoegtoepassing.
  
![Diagram van verkoopafdeling](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a>Controleren of een groep geneste groepen bevat

De gemakkelijkste manier om te controleren of een groep geneste groepen bevat, is het visitekaartje van de groep in Outlook te bekijken. Als u de groepsnaam opgeeft in het veld **aan** van een e-mailbericht en vervolgens de groepsnaam selecteert wanneer deze wordt opgelost, wordt u weergegeven als het een of meer gebruikers zijn met een geneste groep. In het onderstaande voorbeeld toont het tabblad **Leden** van het Outlook-visitekaartje voor de Testgroep geen gebruikers en slechts twee subgroepen. 
  
![Tabblad leden van Outlook-visitekaartje](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
U kunt de tegenovergestelde query uitvoeren door de groep om te zetten om te zien of deze een lid van een groep is. In het onderstaande voorbeeld kunt u op het tabblad **Lidmaatschap** van het Outlook-visitekaartje zien dat Subgroep 1 een lid van de Testgroep is. 
  
![Het tabblad lidmaatschap van het Outlook-visitekaartje](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
U kunt ook de Azure Active Directory Graph API gebruiken voor het uitvoeren van query's om de lijst met groepen in een groep te vinden. Zie [Bewerkingen op groepen | Graph API-verwijzing](https://go.microsoft.com/fwlink/p/?linkid=846342) voor meer informatie.
  
### <a name="contacting-microsoft-for-support"></a>Contact opnemen met Microsoft voor ondersteuning

Als u of uw gebruikers problemen ondervinden bij het laden van de invoegtoepassing wanneer u Office-apps gebruikt voor het web (Word, Excel, enzovoort) die centraal zijn geïmplementeerd, moet u mogelijk contact opnemen met Microsoft ondersteuning ([meer informatie](../contact-support-for-business-products.md)). Voer de volgende informatie in over uw Microsoft 365-omgeving in het ondersteuningsticket.
  
|**Platform**|**Foutopsporingsgegevens**|
|:-----|:-----|
|Office  <br/> | Charles/Fiddler-logboeken  <br/>  Tenant-ID ( [meer informatie over hoe](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))  <br/>  39379. Geef de bron van een van de Office-pagina's weer en zoek de waarde van de correlatie-ID en verzend deze naar ondersteuning:  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|Uitgebreide clients (Windows, Mac)  <br/> | Charles/Fiddler-logboeken  <br/>  Bouw nummers van de client-app (bij voorkeur als een schermafbeelding van **bestand/account**)  <br/> |
   
