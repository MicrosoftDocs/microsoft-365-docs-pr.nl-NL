---
title: Top 10 manieren om Microsoft 365 te beveiligen voor zakelijke abonnementen
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: de2da300-dbb6-4725-bb12-b85a9d296e75
description: 'Bescherm uw zakelijke e-mail en gegevens tegen cyberbedreigingen, waaronder ransomware, phishing en schadelijke bijlagen. '
ms.openlocfilehash: cffc922aec3ca46543b5b1608fa37e6fa0acfa23
ms.sourcegitcommit: f7566dd6010744c72684efdc37f4471672330b61
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138288"
---
# <a name="top-10-ways-to-secure-microsoft-365-for-business-plans"></a>Top 10 manieren om Microsoft 365 te beveiligen voor zakelijke abonnementen

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Als u een kleine of middelgrote organisatie bent die een van de bedrijfsplannen van Microsoft gebruikt en uw type organisatie het doelwit is van cybercriminelen en hackers, gebruikt u de richtlijnen in dit artikel om de beveiliging van uw organisatie te verhogen. Deze begeleiding helpt uw organisatie de doelen te bereiken die worden beschreven in het Harvard Kennedy School [Cybersecurity Campaign Handbook](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409).
  
Microsoft raadt u aan de taken in de volgende tabel uit te voeren die van toepassing zijn op uw serviceplan. 
  
||**Taak**|**Microsoft 365 Business Standard**|**Microsoft 365 Business Premium**|
|:-----|:-----|:-----|:-----|
|1  <br/> |[Meervoudige verificatie instellen](secure-your-business-data.md#setup) <br/> |![Opgenomen](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Opgenomen](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|2  <br/> |[Uw gebruikers trainen](secure-your-business-data.md#train) <br/> |![Opgenomen](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Opgenomen](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|3  <br/> |[Speciale beheerdersaccounts gebruiken](secure-your-business-data.md#admin) <br/> |![Opgenomen](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Opgenomen](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|4  <br/> |[Verhoog het niveau van bescherming tegen malware in e-mail](secure-your-business-data.md#malware) <br/> |![Opgenomen](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Opgenomen](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|5  <br/> |[Beveiligen tegen ransomware](secure-your-business-data.md#ransomware) <br/> |![Opgenomen](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Opgenomen](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|6  <br/> |[Automatisch doorsturen voor e-mail stoppen](secure-your-business-data.md#forwarding) <br/> |![Opgenomen](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Opgenomen](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|7  <br/> |[Office-berichtversleuteling gebruiken](secure-your-business-data.md#encryption) <br/> ||![Opgenomen](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|8  <br/> |[Bescherm uw e-mail tegen phishing-aanvallen](secure-your-business-data.md#phishing) <br/> ||![Opgenomen](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|9  <br/> |[Bescherm tegen schadelijke bijlagen en bestanden met ATP Safe Attachments](secure-your-business-data.md#atp) <br/> ||![Opgenomen](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|10  <br/> |[Bescherm tegen phishing-aanvallen met ATP Safe Links](secure-your-business-data.md#phishingatp) <br/> ||![Opgenomen](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
   
Controleer uw Microsoft [365 Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) in het Microsoft 365-beveiligingscentrum voordat u begint. Vanuit een gecentraliseerd dashboard u de beveiliging van uw Microsoft 365-identiteiten, gegevens, apps, apparaten en infrastructuur bewaken en verbeteren. U krijgt punten voor het configureren van aanbevolen beveiligingsfuncties, het uitvoeren van beveiligingstaken (zoals het bekijken van rapporten) of het adresseren van aanbevelingen met een toepassing of software van derden. Met aanvullende inzichten en meer inzicht in een bredere reeks Microsoft-producten en -services, u er zeker van zijn dat u rapporteert over de beveiligingsstatus van uw organisatie.
  
![Schermafbeelding van microsoft secure score](../../media/secure-score.png)
  
## <a name="1-set-up-multi-factor-authentication"></a>1: Meervoudige verificatie instellen
<a name="setup"> </a>

Het gebruik van multi-factor authenticatie is een van de gemakkelijkste en meest effectieve manieren om de beveiliging van uw organisatie te verhogen. Het is makkelijker dan het klinkt - wanneer u zich aanmeldt, betekent multi-factor authenticatie dat u een code typt vanaf uw telefoon om toegang te krijgen tot Microsoft 365. Dit kan voorkomen dat hackers het overnemen als ze uw wachtwoord kennen. Multi-factor authenticatie wordt ook wel 2-staps verificatie genoemd. Personen kunnen verificatie in twee stappen eenvoudig toevoegen aan de meeste accounts, bijvoorbeeld aan hun Google- of Microsoft-accounts. Zo voeg je [tweestapsverificatie toe aan je persoonlijke Microsoft-account.](https://go.microsoft.com/fwlink/?linkid=2016403&amp;clcid=0x409)
  
Voor bedrijven die Microsoft 365 gebruiken, voegt u een instelling toe waarvoor uw gebruikers zich moeten aanmelden met behulp van meervoudige verificatie. Wanneer u deze wijziging aanbrengt, worden gebruikers gevraagd hun telefoon in te stellen voor tweestapsverificatie de volgende keer dat ze zich aanmelden.
Zie [MFA](https://support.microsoft.com/office/e12187b8-216a-4490-9e3b-df34a06fb787) instellen en [gebruikers instellen](https://support.microsoft.com/office/a32541df-079c-420d-9395-9d59354f7225)voor een trainingsvideo voor het instellen van MFA en het voltooien van de set-up.
  
Ga als u naar meervoudige verificatie:

1. Selecteer In het [beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=834822)de optie **Actieve gebruikers**van gebruikers  >  **Active Users**.

2. Selecteer **in** de sectie Actieve gebruikers de optie **Multi-Factor Authentication**.

3. Selecteer **gebruiker op** de pagina **Multi-Factor Authentication** als u dit voor één gebruiker inschakelt Of u een **bulkupdate**uitvoeren.

4. Selecteer **Inschakelen** onder **Snelle stappen**.

5. Kies in het pop-upvenster **Multi-factor authenticatie inschakelen**.


Nadat u meervoudige verificatie voor uw organisatie hebt ingesteld, moeten uw gebruikers tweestapsverificatie op hun apparaten instellen. Zie [Verificatie in twee stappen instellen voor Microsoft 365 voor](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)meer informatie.
  
Zie [Meervoudige verificatie instellen voor gebruikers voor](set-up-multi-factor-authentication.md)meer informatie en volledige aanbevelingen.
  
## <a name="2-train-your-users"></a>2: Train uw gebruikers
<a name="train"> </a>

Het Harvard Kennedy School [Cybersecurity Campaign Handbook](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) biedt uitstekende richtlijnen voor het creëren van een sterke cultuur van beveiligingsbewustzijn binnen uw organisatie, inclusief het trainen van gebruikers om phishing-aanvallen te identificeren. 
  
Naast deze richtlijnen raadt Microsoft uw gebruikers aan de in dit artikel beschreven acties uit te voeren: [Bescherm uw account en apparaten tegen hackers en malware.](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6) Deze acties omvatten:
  
- Sterke wachtwoorden gebruiken
    
- Apparaten beveiligen
    
- Beveiligingsfuncties inschakelen op Windows 10- en Mac-pc's
    
Microsoft raadt gebruikers ook aan hun persoonlijke e-mailaccounts te beschermen door de in de volgende artikelen aanbevolen acties uit te voeren:
  
- [Help uw Outlook.com e-mailaccount te beschermen](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
    
- [Bescherm je Gmail-account met verificatie in twee stappen](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
    
## <a name="3-use-dedicated-admin-accounts"></a>3: Speciale beheerdersaccounts gebruiken
<a name="admin"> </a>

De beheeraccounts die u gebruikt om uw Microsoft 365-omgeving te beheren, bevatten verhoogde bevoegdheden. Dit zijn waardevolle doelwitten voor hackers en cybercriminelen. Gebruik alleen beheerdersaccounts voor beheer. Beheerders moeten een apart gebruikersaccount hebben voor regelmatig, niet-administratief gebruik en alleen hun administratieve account gebruiken wanneer dat nodig is om een taak te voltooien die is gekoppeld aan hun taakfunctie. Aanvullende aanbevelingen:
  
- Zorg ervoor dat beheerdersaccounts ook zijn ingesteld voor meervoudige verificatie. 
    
- Voordat u beheerdersaccounts gebruikt, sluit u alle niet-gerelateerde browsersessies en -apps, inclusief persoonlijke e-mailaccounts.
    
- Nadat u beheerderstaken hebt voltooid, moet u zich afmelden bij de browsersessie.
    
## <a name="4-raise-the-level-of-protection-against-malware-in-mail"></a>4: Verhoog het niveau van bescherming tegen malware in e-mail
<a name="malware"> </a>

Uw Microsoft 365-omgeving biedt bescherming tegen malware, maar u deze bescherming verhogen door bijlagen te blokkeren met bestandstypen die vaak worden gebruikt voor malware. Als u de bescherming tegen malware in e-mail wilt instellen, bekijkt u een [korte trainingsvideo](https://support.microsoft.com/office/02b5783a-eea0-42e8-8856-62440718c3f0)of voert u de volgende stappen uit:
  
1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw beheerdersaccountgegevens. 
    
2. Kies in het Security &amp; Compliance Center in het linkernavigatiedeelvenster onder **Bedreigingsbeheer** **de optie** \> **Beleidsantimalware**.
    
3. Dubbelklik op het standaardbeleid om dit bedrijfsbrede beleid te bewerken.
    
4. Selecteer **Instellingen**.
    
5. Selecteer onder **Filter Algemene bijlagetypen**de optie **Aan**. De bestandstypen die worden geblokkeerd, worden in het venster direct onder dit besturingselement weergegeven. U indien nodig bestandstypen later toevoegen of verwijderen.
    
6. Selecteer **Opslaan.**
    
Zie [Bescherming tegen malware voor](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409)meer informatie.
  
## <a name="5-protect-against-ransomware"></a>5: Beschermen tegen ransomware
<a name="ransomware"> </a>

Ransomware beperkt de toegang tot gegevens door bestanden te versleutelen of computerschermen te vergrendelen. Het probeert vervolgens om geld af te persen van slachtoffers door te vragen om "losgeld", meestal in de vorm van cryptocurrencies zoals Bitcoin, in ruil voor toegang tot gegevens. 
  
U beschermen tegen ransomware door het creëren van een of meer mail flow regels om bestandsextensies die vaak worden gebruikt voor ransomware te blokkeren, of om gebruikers die deze bijlagen ontvangen in e-mail te waarschuwen. Een goed uitgangspunt is het maken van twee regels:
  
- Gebruikers waarschuwen voordat u Office-bestandsbijlagen opent die macro's bevatten. Ransomware kan worden verborgen in macro's, dus we zullen gebruikers waarschuwen om deze bestanden niet te openen van mensen die ze niet kennen. 
    
- Blokkeer bestandstypen die ransomware of andere schadelijke code kunnen bevatten. We beginnen met een gemeenschappelijke lijst met uitvoerbare objecten (vermeld in de onderstaande tabel). Als uw organisatie een van deze uitvoerbare typen gebruikt en u verwacht dat deze per e-mail worden verzonden, voegt u deze toe aan de vorige regel (gebruikers waarschuwen).
    
Als u een regel voor e-mailtransport wilt maken, bekijkt u een [korte trainingsvideo](https://support.microsoft.com/office/a9ecca03-42a6-4867-b9fd-38e3f6bb06ad)of voert u de volgende stappen uit:
  
1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.

2. Selecteer **regels**in de categorie **e-mailstroom** .
    
3. Selecteer **+** en **maak vervolgens een nieuwe regel**.
    
4. Selecteer **** onder aan het dialoogvenster om de volledige set opties te bekijken. 
    
5. Pas de instellingen in de volgende tabel voor elke regel toe. Laat de rest van de instellingen bij de standaardinstelling, tenzij u deze wilt wijzigen.
    
6. Kies **Opslaan**.
    
|**Instelling**|**Gebruikers waarschuwen voordat u bijlagen van Office-bestanden opent**|**Bestandstypen blokkeren die ransomware of andere schadelijke code kunnen bevatten**|
|:-----|:-----|:-----|
|Naam  <br/> |Anti-ransomware regel: waarschuwen gebruikers  <br/> |Anti-ransomware regel: blok bestandstypen  <br/> |
|Pas deze regel toe als . . .  <br/> |Elke bijlage . . . bestandsextensie komt overeen met . . .  <br/> |Elke bijlage . . . bestandsextensie komt overeen met . . .  <br/> |
|Woorden of zinnen opgeven  <br/> |Voeg deze bestandstypen toe:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm  <br/> |Voeg deze bestandstypen toe:  <br/> ade, adp, ani, bas, vleermuis, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdzz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsf, wsf, wsh, exe, pif  <br/> |
|Ga als volgt te werk. . .  <br/> |De ontvanger op de hoogte stellen met een bericht  <br/> |Blokkeer het bericht . . . het bericht afwijzen en een uitleg opnemen  <br/> |
|Berichttekst weergeven  <br/> |Open dit soort bestanden niet, tenzij u ze verwachtte, omdat de bestanden schadelijke code kunnen bevatten en weten dat de afzender geen garantie voor veiligheid is.  <br/> ||
   
> [!TIP]
> U de bestanden die u wilt blokkeren ook toevoegen aan de lijst met malware in [stap 4.](#4-raise-the-level-of-protection-against-malware-in-mail)

Zie voor meer informatie:
  
- [Hoe om te gaan met ransomware](https://go.microsoft.com/fwlink/?linkid=2016501&amp;clcid=0x409)
    
- [Uw OneDrive herstellen](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)
    
## <a name="6-stop-auto-forwarding-for-email"></a>6: Stop automatisch doorsturen voor e-mail
<a name="forwarding"> </a>

Hackers die toegang krijgen tot het postvak van een gebruiker kunnen e-mail exfiltreren door het postvak te configureren om automatisch e-mail door te sturen. Dit kan zelfs gebeuren zonder het bewustzijn van de gebruiker. U dit voorkomen door een e-mailstroomregel te configureren. 
  
Ga als een regel voor e-mailtransport:
  
1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.

2. Selecteer **regels**in de categorie **e-mailstroom** .
    
3. Selecteer **+** en **maak vervolgens een nieuwe regel**.
    
4. Selecteer **Meer opties** onder aan het dialoogvenster om de volledige set opties te bekijken. 
    
5. Pas de instellingen toe in de volgende tabel. Laat de rest van de instellingen bij de standaardinstelling, tenzij u deze wilt wijzigen.
    
6. Kies **Opslaan**.
    
|**Instelling**|**E-mails automatisch doorsturen naar externe domeinen**|
|:-----|:-----|
|Naam  <br/> |Automatisch doorsturen van e-mail naar externe domeinen voorkomen  <br/> |
|Pas deze regel toe als ...  <br/> |De afzender. . . is extern/intern . . . Binnen de organisatie  <br/> |
|Voorwaarde toevoegen  <br/> |De ontvanger . . . is extern/intern . . . Buiten de organisatie  <br/> |
|Voorwaarde toevoegen  <br/> |De eigenschappen van het bericht . . . het berichttype op te nemen. . . Automatisch doorsturen  <br/> |
|Doe het volgende ...  <br/> |Blokkeer het bericht . . . het bericht te weigeren en een uitleg op te nemen.  <br/> |
|Berichttekst weergeven  <br/> |E-mail automatisch doorschakelen buiten deze organisatie wordt om veiligheidsredenen voorkomen.  <br/> |
   
## <a name="7-use-office-message-encryption"></a>7: Versleuteling van Office-berichten gebruiken
<a name="encryption"> </a>

Office Message Encryption is inbegrepen bij Microsoft 365. Het is al geregeld. Met Office Message Encryption kan uw organisatie versleutelde e-mailberichten verzenden en ontvangen tussen mensen binnen en buiten uw organisatie. Office 365 Message Encryption werkt met Outlook.com, Yahoo!, Gmail en andere e-mailservices. E-mailberichtenversleuteling zorgt ervoor dat alleen beoogde ontvangers de inhoud van berichten kunnen bekijken.
  
Office Message Encryption biedt twee beveiligingsopties bij het verzenden van e-mail:
  
- Niet doorsturen
    
- Coderen
    
Uw organisatie heeft mogelijk aanvullende opties geconfigureerd waarmee een label op e-mail wordt toegepast, zoals Vertrouwelijk.
  
### <a name="to-send-protected-email"></a>Beveiligde e-mail verzenden

**Selecteer** opties in de e-mail in Outlook voor pc en kies **Machtigingen**. 
  
![Versleuteling van e-mailberichten in Outlook](../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639a.png)
  
**Selecteer** beveiligen in Outlook.com in de e-mail. De standaardbeveiliging is **Niet doorsturen.** Als u dit wilt wijzigen om te versleutelen, selecteert u **Machtigingen** \> **versleutelen wijzigen.** 
  
![Versleuteling van e-mailberichten in Outlook.com](../../media/329ccf50-f6b1-4fb8-b249-60b907a82b7e.png)
  
### <a name="to-receive-encrypted-email"></a>Versleutelde e-mail ontvangen

Als de ontvanger Outlook 2013 of Outlook 2016 en een E-mailaccount van Microsoft heeft, wordt er een waarschuwing weergegeven over de beperkte machtigingen van het item in het leesvenster. Na het openen van het bericht kan de ontvanger het bericht net als alle andere bekijken.
  
Als de ontvanger een andere e-mailclient of e-mailaccount gebruikt, zoals Gmail of Yahoo, ziet hij/zij een koppeling waarmee hij zich kan aanmelden om het e-mailbericht te lezen of een eenmalige toegangscode te vragen om het bericht in een webbrowser te bekijken. Als gebruikers de e-mail niet ontvangen, laat ze hun map Spam of Ongewenste e-mail controleren. 
  
Zie [Versleutelde berichten verzenden, weergeven en beantwoorden in Outlook voor pc voor](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980)meer informatie.
  
## <a name="8-protect-your-email-from-phishing-attacks"></a>8. Bescherm uw e-mail tegen phishing-aanvallen
<a name="phishing"> </a>

Als u een of meer aangepaste domeinen hebt geconfigureerd voor uw Microsoft 365-omgeving, u gerichte bescherming tegen phishing configureren. ATP-bescherming tegen phishing, onderdeel van Office 365 Advanced Threat Protection, kan uw organisatie beschermen tegen schadelijke imitatiegebaseerde phishing-aanvallen en andere phishing-aanvallen. Als u een aangepast domein nog niet hebt geconfigureerd, hoeft u dit niet te doen.
  
We raden u aan om aan de slag te gaan met deze bescherming door een beleid te maken om uw belangrijkste gebruikers en uw aangepaste domein te beschermen. 
  
![Een ATP-anti-phishingbeleid maken](../../media/security-and-compliance-center.png)
  
Als u een ATP-antiphishingbeleid wilt maken, bekijkt u een [korte trainingsvideo](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)of voert u de volgende stappen uit:
  
1. Ga naar [https://protection.office.com](https://protection.office.com). 
    
2. Selecteer beleid in het Security &amp; Compliance Center in het **Policy**linkernavigatiedeelvenster onder **Bedreigingsbeheer**.
    
3. Selecteer op de pagina Beleid de optie **ATP-anti-phishing**.
    
4. Selecteer **+ Maken**op de pagina Anti-phishing . Een wizard lanceert die u door het definiëren van uw anti-phishing beleid.
    
5. Geef de naam, beschrijving en instellingen voor uw beleid op zoals aanbevolen in de onderstaande grafiek. [Zie Meer informatie over atp-beleidsopties voor antiphishingbeleid](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies) voor meer informatie. 
    
6. Nadat u uw instellingen hebt bekeken, selecteert u **Dit beleid maken** of **Opslaan**, indien van toepassing.


|**Instellen of optie**|**Aanbevolen instelling** <br/>|
|:-----|:-----|
|Naam  <br/> |Domein en meest waardevolle campagnemedewerkers  <br/> |
|Beschrijving  <br/> |Zorg ervoor dat de belangrijkste medewerkers en ons domein niet worden nagebootst.  <br/> |
|Gebruikers toevoegen om te beschermen  <br/> |Selecteer **+ Een voorwaarde toevoegen, de ontvanger is**. Typ gebruikersnamen of voer het e-mailadres in van de kandidaat, campagnemanager en andere belangrijke medewerkers. U maximaal 20 interne en externe adressen toevoegen die u wilt beschermen tegen imitatie.  <br/> |
|Domeinen toevoegen om te beschermen  <br/> |Selecteer **+ Een voorwaarde toevoegen, het domein van de ontvanger is**. Voer het aangepaste domein in dat is gekoppeld aan uw Microsoft 365-abonnement als u er een hebt gedefinieerd. U meer dan één domein invoeren.  <br/> |
|Acties kiezen  <br/> |Als e-mail wordt verzonden door een geïmiteerde gebruiker: selecteer **Bericht omleiden naar een ander e-mailadres**en typt u het e-mailadres van de beveiligingsbeheerder. securityadmin@contoso.com bijvoorbeeld.          Als e-mail wordt verzonden door een geïmcipeel domein: selecteer **Quarantainebericht**.  <br/> |
|Postvakintelligentie  <br/> |Standaard wordt postvakinformatie geselecteerd wanneer u een nieuw antiphishingbeleid maakt. Laat deze instelling **aan** staan voor de beste resultaten.  <br/> |
|Vertrouwde afzenders en domeinen toevoegen  <br/> |Definieer in dit voorbeeld geen overschrijvingen.  <br/> |
|Toegepast op  <br/> |Selecteer **Het geadresseerdedomein is**. Selecteer onder **Een van deze**opties de optie **Kiezen**. Selecteren **+ Toevoegen**. Schakel het selectievakje naast de naam van het domein in, bijvoorbeeld contoso.com, in de lijst en selecteer **Toevoegen**. Selecteer **Gereed**.  <br/> |
|
   
Zie Het [antiphishingbeleid van Office 365 ATP instellen](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-atp-anti-phishing-policies)voor meer informatie .
  
## <a name="9-protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>9: Bescherm tegen schadelijke bijlagen en bestanden met ATP Safe Attachments
<a name="atp"> </a>

Mensen verzenden, ontvangen en delen regelmatig bijlagen, zoals documenten, presentaties, spreadsheets en meer. Het is niet altijd gemakkelijk om te zien of een bijlage veilig of kwaadaardig is door alleen maar naar een e-mailbericht te kijken. Office 365 Advanced Threat Protection bevat atp-beveiliging voor veilige bevestiging, maar deze beveiliging is niet standaard ingeschakeld. We raden u aan een nieuwe regel te maken om deze beveiliging te gaan gebruiken. Deze beveiliging strekt zich uit tot bestanden in SharePoint, OneDrive en Microsoft Teams.
  
Als u een ATP-beleid voor veilige bijlagen wilt maken, bekijkt u een [korte trainingsvideo](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)of voert u de volgende stappen uit:
  
1. Ga naar [https://protection.office.com](https://protection.office.com) en meld je aan met je beheerdersaccount. 
    
2. Selecteer beleid in het Security &amp; Compliance Center in het **Policy**linkernavigatiedeelvenster onder **Bedreigingsbeheer**.
    
3. Selecteer op de pagina Beleid de optie **VEILIGE BIJLAGEN atp**.
    
4. Pas deze beveiliging op de pagina Veilige bijlagen breed toe door het selectievakje **ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams in** te schakelen. 
    
5. Selecteer **+** om een nieuw beleid te maken. 
    
6. Pas de instellingen toe in de volgende tabel. 
    
7. Nadat u uw instellingen hebt bekeken, selecteert u **Dit beleid maken** of **Opslaan**, indien van toepassing.
    

|**Instellen of optie**|**Aanbevolen instelling** <br/>|
|:-----|:-----|
|Naam  <br/> |Blokkeer huidige en toekomstige e-mails met gedetecteerde malware.  <br/> |
|Beschrijving  <br/> |Blokkeer huidige en toekomstige e-mails en bijlagen met gedetecteerde malware.  <br/> |
|Bijlagen opslaan onbekende malware reactie  <br/> |Selecteer **Blokkeren - Blokkeer de huidige en toekomstige e-mails en bijlagen met gedetecteerde malware.**  <br/> |
|Bijlage omleiden bij detectie  <br/> |Omleiding inschakelen (selecteer dit vak) Voer het beheerdersaccount of een postvakinstelling in voor quarantaine.          Pas de bovenstaande selectie toe als er een keer een keer een fout optreedt voor malwarescannen voor bijlagen (selecteer dit vak).  <br/> |
|Toegepast op  <br/> |Het domein van de ontvanger is . . . selecteer uw domein.  <br/> |
|
   
Zie Het [antiphishingbeleid van Office 365 ATP instellen](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-atp-anti-phishing-policies)voor meer informatie .
  
## <a name="10-protect-against-phishing-attacks-with-atp-safe-links"></a>10: Bescherm tegen phishing-aanvallen met ATP Safe Links
<a name="phishingatp"> </a>

Hackers verbergen soms kwaadaardige websites in links in e-mail of andere bestanden. Office 365 ATP Safe Links (ATP Safe Links), onderdeel van Office 365 Advanced Threat Protection, kan uw organisatie helpen beschermen door tijd-van-klikverificatie van webadressen (URL's) in e-mailberichten en Office-documenten te bieden. Bescherming wordt gedefinieerd via atp-beleid voor veilige koppelingen.
  
We raden u aan het volgende te doen:
  
- Wijzig het standaardbeleid om de beveiliging te verhogen.
    
- Voeg een nieuw beleid toe dat is gericht op alle ontvangers in uw domein.
    
Als u naar ATP Safe Links wilt gaan, bekijkt u een [korte trainingsvideo](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)of voert u de volgende stappen uit:
  
1. Ga naar [https://protection.office.com](https://protection.office.com) en meld je aan met je beheerdersaccount. 
    
2. Selecteer beleid in het Security &amp; Compliance Center in het **Policy**linkernavigatiedeelvenster onder **Bedreigingsbeheer**.
    
3. Selecteer op de pagina Beleid de optie **VEILIGEKNOPEN VAN ATP**.
    
Ga alstkader het standaardbeleid wijzigen:
  
1. Dubbelklik op de pagina Veilige koppelingen onder **Beleid dat van toepassing is op de hele organisatie,** op het **standaardbeleid.** 
    
2. Voer onder **Instellingen die van toepassing zijn op inhoud in Office 365**een URL in die moet worden geblokkeerd, zoals _example.com_en selecteer **+** .

3. Selecteer **onder Instellingen die van toepassing zijn op inhoud, behalve e-mail,** Office **365-toepassingen**, **Houd niet bij wanneer gebruikers op veilige koppelingen klikken**en laat gebruikers niet door veilige **koppelingen naar de oorspronkelijke URL klikken.**
    
4. Kies **Opslaan**. 
    
Ga als een nieuw beleid maken dat is gericht op alle ontvangers in uw domein:
  
1. Selecteer op de pagina Veilige koppelingen onder **Beleid dat van toepassing is op specifieke ontvangers**de optie Een nieuw beleid **+** maken. 
    
2. Pas de instellingen toe die in de volgende tabel worden vermeld.
    
3. Kies **Opslaan**. 
    
|**Instellen of optie**|**Aanbevolen instelling** <br/>|
|:-----|:-----|
|Naam  <br/> |Beleid voor veilige koppelingen voor alle ontvangers in het domein  <br/> |
|Selecteer de actie voor onbekende mogelijk schadelijke URL's in berichten  <br/> |Selecteer **Aan - URL's worden herschreven en gecontroleerd aan de hand van een lijst met bekende schadelijke koppelingen wanneer gebruikers op de link klikken.**  <br/> |
|Real-time URL-scannen toepassen op verdachte koppelingen en koppelingen die verwijzen naar bestanden  <br/> |Selecteer dit vak.  <br/> |
|Toegepast op  <br/> |Het domein van de ontvanger is . . . selecteer uw domein.  <br/> |
|
   
Zie veilige koppelingen met [Office 365 ATP](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409)voor meer informatie .
