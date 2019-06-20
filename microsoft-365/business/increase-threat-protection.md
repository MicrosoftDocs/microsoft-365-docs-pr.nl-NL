---
title: Bescherming van de bedreiging voor Microsoft 365 Business verhogen
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Office 365 Advanced Threat Protection instellen en vertrouwelijke gegevens te beschermen.
ms.openlocfilehash: b6e9941eee9de4f295b0f8056c1c91b7076e530c
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/31/2019
ms.locfileid: "35086301"
---
# <a name="increase-threat-protection"></a>Dreigingen verhogen

Dit artikel helpt u bij het verhogen van de bescherming van uw abonnement op Microsoft 365 ter bescherming tegen phishing, malware en andere bedreigingen. Deze aanbevelingen zijn geschikt voor organisaties met een verhoogde behoefte aan beveiliging, zoals wet kantoren en gezondheidszorg klinieken.

Voordat u begint, controleert u uw Office 365 Secure Score. Office 365 Secure Score wordt geanalyseerd op basis van de reguliere activiteiten en de beveiligingsinstellingen van uw organisatie Office 365-beveiliging en een score wordt toegewezen. Eerst kennis te nemen van uw huidige score. Nemen van de acties die in dit artikel aan te raden verhoogt uw score. Het doel is niet de maximale score te bereiken, maar zich bewust zijn van de mogelijkheden om het milieu te beschermen die de productiviteit van uw gebruikers niet nadelig beïnvloedt. 

Zie voor meer informatie de [Microsoft Secure Score](https://docs.microsoft.com/en-us/office365/securitycompliance/microsoft-secure-score).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Verhogen van het niveau van bescherming tegen malware in e-mail

Uw Office 365 of Microsoft 365 omgeving inclusief bescherming tegen malware, maar kunt u deze beveiliging vergroten door de blokkering van bijlagen met bestandstypen die worden gebruikt voor malware. Beveiliging tegen in e-mailbericht vergroten:
  
1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw referenties van de account Administrator. 
    
2. Bij de beveiligingsupdate voor Office 365 &amp; conformiteit, kies in het linkernavigatievenster onder **Threat management** **beleid** \> **Anti-Malware**.
    
3. Dubbelklik op het standaardbeleid om het bewerken van dit beleid voor het hele bedrijf.
    
4. Klik op **Instellingen**.
    
5. Selecteer onder **Algemeen bijlage typen Filter** **op**. De bestandstypen die worden geblokkeerd worden in het venster direct onder dit besturingselement weergegeven.  Zorg ervoor dat u deze filetypes toevoegen:
   - ADE, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, taak, js, jse, lnk, mda, mdb, MDE-, mdz, msc, msi, msp, mst, pcd, reg, li, Eenvoudige opvanglade, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, PIF-bestand  <br/> U kunt toevoegen of verwijderen van bestandstypen later, indien nodig.
    
6. Klik op **opslaan.**
    
Voor meer informatie, Zie [Anti-malware bescherming](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409).
  
## <a name="protect-against-ransomware"></a>Bescherming tegen ransomware

Ransomware beperkt de toegang tot gegevens door bestanden coderen of vergrendelen computerschermen. Vervolgens probeert te extort geld van slachtoffers door te vragen voor 'ransom', meestal in de vorm van cryptocurrencies zoals Bitcoin, in ruil voor toegang tot gegevens. 
  
U kunt zich beschermen tegen ransomware door een of meer e-mailberichten maken stroomregels voor het blokkeren van bestandsextensies die vaak worden gebruikt voor ransomware (deze zijn toegevoegd aan de stap [verhogen het niveau van bescherming tegen malware in e-mail](#raise-the-level-of-protection-against-malware-in-mail) ) of waarschuwt gebruikers die deze ontvangen bijlagen in e-mailbericht.

Naast de bestanden die u in de vorige stap hebt geblokkeerd, is het ook raadzaam een regel om gebruikers te waarschuwen voor het openen van Office-bestandsbijlagen die macro's maken. Ransomware kan worden verborgen in de macro's, zodat we je waarschuwen gebruikers deze bestanden niet openen van mensen die ze niet kent.

Voor het maken van een e-mailregel transport:
  
1. Ga naar de admin center op <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> en kies **Admin centers** \> **Exchange**.
    
2. Klik op de **regels**in de categorie **e-mailverkeer** .
    
3. Klik op **+**, en klik vervolgens op **een nieuwe regel maken**.
    
4. Klik op **meer opties** onder aan het dialoogvenster om te zien de volledige reeks opties. 
    
5. De instellingen in de volgende tabel voor de regel van toepassing. Laat de rest van de instellingen op standaard, tenzij u wilt deze wijzigen.
    
6. Klik op **Opslaan**.
    
|**Instelling**|**Waarschuw gebruikers voordat u bijlagen van Office-bestanden openen**||
|:-----|:-----|:-----|
|Name  <br/> |Anti-ransomware-regel: Waarschuw gebruikers  <br/>  |
|Als deze regel van toepassing. . .  <br/> |Bijlagen. . . bestandsextensie overeenkomt. . .  <br/> |
|Geef woorden of woordgroepen  <br/> |Deze bestandstypen toevoegen:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm  <br/>|
|Voer de volgende handelingen uit. . .  <br/> |Kennis van de ontvanger met een bericht  <br/> |
|Tekst van bericht  <br/> |Dit type bestanden niet openen van mensen die u niet kent omdat deze macro met schadelijke code kunnen bevatten.  <br/> |
   
Zie voor meer informatie:
  
- [Het omgaan met ransomware](https://go.microsoft.com/fwlink/?linkid=2016501&amp;clcid=0x409)
    
- [De OneDrive herstellen](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)
    


## <a name="stop-auto-forwarding-for-email"></a>Automatisch doorsturen via e-mail stoppen

Hackers die toegang hebben tot het postvak van een gebruiker kunnen uw e-mailberichten door het postvak in voor het doorsturen van e-mailadres automatisch stelen. Dit kan gebeuren ook zonder kennis van de gebruiker. U kunt voorkomen dat dit gebeurt door het configureren van een e-mailregel stroom. 
  
Als u wilt een e-mailregel transport, Bekijk [deze korte video](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) of als volgt te werk:
  
1. Klik in het beheercentrum van Microsoft 365 **Admin centers** \> **Exchange**.
    
2. Klik op de **regels**in de categorie **e-mailverkeer** .
    
3. Klik op **+**, en klik vervolgens op **een nieuwe regel maken**.
    
4. Klik op **meer opties** onder aan het dialoogvenster om te zien de volledige reeks opties. 
    
5. De instellingen in de volgende tabel toepassen. Laat de rest van de instellingen op standaard, tenzij u wilt deze wijzigen.
    
6. Klik op **Opslaan**.
    
|**Instelling**|**Waarschuw gebruikers voordat u bijlagen van Office-bestanden openen**|
|:-----|:-----|
|Name  <br/> |Automatisch doorsturen van e-mail voorkomen voor externe domeinen  <br/> |
|Deze regel toepassen als...  <br/> |De afzender. . . is extern/intern. . . Binnen de organisatie  <br/> |
|Voorwaarde toevoegen  <br/> |De berichteigenschappen. . . het berichttype opnemen. . . Automatisch doorsturen  <br/> |
|Voer de volgende...  <br/> |Het bericht geblokkeerd. . . het bericht negeren en een uitleg bevatten.  <br/> |
|Tekst van bericht  <br/> |E-mail automatisch doorsturen buiten deze organisatie om veiligheidsredenen niet.  <br/> |


## <a name="protect-your-email-from-phishing-attacks"></a>Uw e-mailadres beschermen tegen phishing

Als u een of meer aangepaste domeinen hebt geconfigureerd voor uw Office 365 of 365 Microsoft-omgeving, kunt u gerichte anti-phishing bescherming. ATP anti-phishing bescherming, onderdeel van Office 365 Advanced Threat Protection, kunt uw organisatie beschermen tegen schadelijke op basis van imitatie phishingaanvallen en andere phishingaanvallen. Als u een aangepast domein nog niet hebt geconfigureerd, hoeft u niet om dit te doen.
  
Wij raden aan dat u aan de slag met deze bescherming door het maken van een beleid ter bescherming van de belangrijkste gebruikers en uw aangepaste domein. 

  
Bekijk [deze korte video training](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)een ATP anti-phishing om beleid te maken, of Voer de volgende stappen uit:
  
1. Ga naar [https://protection.office.com](https://protection.office.com). 
    
2. Bij de beveiligingsupdate voor Office 365 &amp; conformiteit, kies in het linkernavigatievenster onder **Threat management** **beleid**.
    
3. Kies op de pagina **beleid** **ATP anti-phishing**.
    
4. Selecteer op de pagina **Anti-phishing** **+ maken**. Een wizard gestart waarmee u uw anti-phishing-beleid definiëren.
    
5. Geef de naam, beschrijving en instellingen voor het beleid, zoals aangegeven in de onderstaande grafiek. Zie [meer informatie over ATP anti-phishing beleidsopties](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409) voor meer informatie. 
    
6. Nadat u de instellingen hebt gecontroleerd, kiest u **Dit beleid maken** of **Opslaan**, zo nodig.
    

|**Instelling of optie**<br/>|**Aanbevolen instelling** <br/>|
|:-----|:-----|
|Name  <br/> |Domein en de meest waardevolle campagne personeel  <br/> |
|Beschrijving  <br/> |Controleer belangrijkste medewerkers en onze domein niet wordt nagebootst.  <br/> |
|Toevoegen van gebruikers te beschermen  <br/> |Selecteer **+ een voorwaarde van de geadresseerde is toevoegen**. Typ gebruikersnamen of het e-mailadres van de kandidaat, campagne manager en andere belangrijke personeelsleden. U kunt maximaal 20 interne en externe adressen die u wilt beschermen tegen imitatie toevoegen.  <br/> |
|Toevoegen van domeinen te beschermen  <br/> |Selecteer **+ een voorwaarde, het domein van de geadresseerde is toevoegen**. Geef het aangepaste domein dat uw Microsoft 365-abonnement als u een gedefinieerd. U kunt meer dan één domein.  <br/> |
|Kies Acties  <br/> |Als het e-mailbericht is verzonden door een geïmiteerde gebruiker: Kies het **doorsturen van berichten naar een ander e-mailadres**en typ vervolgens het e-mailadres van de beheerder van de veiligheid; bijvoorbeeld *Els<span><span>@contoso.com*.          Als e-mail wordt verzonden door een nagebootste domein: **quarantaine bericht**kiezen.  <br/> |
|Postbus intelligence  <br/> |Postbus intelligence is standaard ingeschakeld wanneer u een nieuw anti-phishing-beleid maakt. Laat deze instelling **op** voor de beste resultaten.  <br/> |
|Vertrouwde afzenders en domeinen toevoegen  <br/> |Hier kunt u uw eigen domein of andere vertrouwde domeinen toevoegen.  <br/> |
|Toegepast op  <br/> |Selecteer het **domein van de geadresseerde is**. Selecteer onder **deze**, **kiezen**. **+ Toevoegen**selecteert. Schakel het selectievakje in naast de naam van het domein, bijvoorbeeld *contoso.<span> <span>com*, in de lijst en klik vervolgens op **toevoegen**. Selecteer **Gereed**.  <br/> |
   
Zie [Office 365 ATP anti-phishing-beleid instellen](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409)voor meer informatie.
  
## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>Bescherming tegen schadelijke bijlagen en bestanden met ATP veilige bijlagen

Mensen regelmatig verzenden, ontvangen en bijlagen, zoals documenten, presentaties en spreadsheets delen. Het is niet altijd eenvoudig om te zien of een bijlage veilig of schadelijk is door te kijken naar een e-mailbericht. Office 365 Advanced Threat Protection bescherming ATP veilige bijlage bevat, maar deze bescherming is niet standaard ingeschakeld. Het is raadzaam dat u een nieuwe regel maakt te beginnen met behulp van deze bescherming. Deze bescherming zich uitstrekt tot bestanden in SharePoint en OneDrive Microsoft-Teams.
  
Bekijk [deze korte video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)een ATP veilige bijlage om beleid te maken, of Voer de volgende stappen uit:
  
1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw Administrator-account. 
    
2. Bij de beveiligingsupdate voor Office 365 &amp; conformiteit, kies in het linkernavigatievenster onder **Threat management** **beleid**.
    
3. Kies op de pagina beleid **ATP veilige bijlagen**.
    
4. Klik op de pagina veilige bijlagen Algemeen van toepassing deze bescherming door het selectievakje **inschakelen in het ATP voor SharePoint, OneDrive, en Microsoft-Teams** . 
    
5. Selecteer **+** een nieuw beleid maken. 
    
6. De instellingen in de volgende tabel toepassen. 
    
7. Nadat u de instellingen hebt gecontroleerd, kiest u **Dit beleid maken** of **Opslaan**, zo nodig.
    

|**Instelling of optie**|**Aanbevolen instelling** <br/>|
|:-----|:-----|
|Name  <br/> |Huidige en toekomstige e-mailberichten met gedetecteerde malware blokkeren.  <br/> |
|Beschrijving  <br/> |Huidige en toekomstige e-mailberichten en bijlagen met gedetecteerde malware blokkeren.  <br/> |
|Sla bijlagen onbekende malware antwoord  <br/> |Selecteer **blok - de huidige en toekomstige e-mailberichten en bijlagen met gedetecteerde malware blokkeren**.  <br/> |
|Bijlage detectie omleiden  <br/> |Omleiding inschakelen (Schakel dit in) de admin-account of een postbus instellen voor quarantaine invoeren.          De bovenstaande selectie toepassen als malware scannen voor bijlagen een optreedt time-out of fout optreedt (Schakel dit in).  <br/> |
|Toegepast op  <br/> |Domein van de geadresseerde is. . . Selecteer uw domein.  <br/> |
   
Zie [Office 365 ATP anti-phishing-beleid instellen](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409)voor meer informatie.
  


## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a>Bescherming tegen phishingaanvallen met veilige ATP-koppelingen

Hackers verbergen soms schadelijke websites koppelingen in e-mail of andere bestanden. Office 365 ATP veilige koppelingen (ATP veilige koppelingen), onderdeel van Office 365 Advanced Threat Protection, kunt uw organisatie beschermen door middel van controle op tijd en op de webadressen (URL's) in Office-documenten en e-mailberichten. Bescherming is via veilige koppelingen ATP-beleid gedefinieerd.
  
Wij raden aan dat u het volgende doen:
  
- Wijzig het standaardbeleid om bescherming te verhogen.
    
- Een nieuw beleid gericht naar alle geadresseerden in uw domein toevoegen.
    
Bekijk [deze korte video training](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)ATP veilige koppelingen instellen, of Voer de volgende stappen uit:
  
1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw Administrator-account. 
    
2. Bij de beveiligingsupdate voor Office 365 &amp; conformiteit, kies in het linkernavigatievenster onder **Threat management** **beleid**.
    
3. Kies op de pagina beleid **ATP veilige koppelingen**.
    
Het standaardbeleid wijzigen:
  
1. Selecteer op de pagina koppelingen veilig onder **die van toepassing zijn op de gehele organisatie beleid**, **het standaardbeleid** . 
    
2. Schakel onder **instellingen die van toepassing zijn op inhoud, met uitzondering van e-mail** **Office 365 ProPlus, Office voor iOS en Android**.
    
3. Klik op **Opslaan**. 
    
Voor het maken van een nieuw beleid gericht naar alle geadresseerden in uw domein:
  
1. Klik op de pagina koppelingen veilig onder **die van toepassing zijn op de gehele organisatie beleid**, **+** een nieuw beleid maken. 
    
2. De instellingen die worden vermeld in de volgende tabel toepassen.
    
3. Klik op **Opslaan**. 

|**Instelling of optie**|**Aanbevolen instelling** <br/>|
|:-----|:-----|
|Name  <br/> |Beleid voor veilige links voor alle geadresseerden in het domein  <br/> |
|Selecteer de actie voor onbekende, mogelijk schadelijke URL's in berichten  <br/> |Selecteer **op - URL's worden herschreven en gecontroleerd aan de hand van een lijst van bekende schadelijke koppelingen wanneer de gebruiker op de koppeling klikt**.  <br/> |
|Veilige bijlagen gebruiken voor het scannen van downloadbare content  <br/> |Schakel deze in.  <br/> |
|Toegepast op  <br/> |Domein van de geadresseerde is. . . Selecteer uw domein.  <br/> |
   
Zie [Office 365 ATP veilige koppelingen](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409)voor meer informatie.

## <a name="go-to-intune-admin-center"></a>Ga naar Intune admin center

1. Inloggen op [portal Azure](https://portal.azure.com/).

2. Selecteer **alle services** en typ *Intune* in het **Vak Zoeken**.

3. Zodra de resultaten worden weergegeven, klikt u op het begin volgende voor **Microsoft Intune** een favoriet maken en later gemakkelijk te vinden.

Naast het beheercentrum kunt u Intune inschrijven apparaten en beheren van uw organisatie. Zie voor meer informatie [mogelijkheden door de methode voor certificaatinschrijving voor apparaten met Windows](https://docs.microsoft.com/intune/enrollment-method-capabs) en [Opties voor inschrijving voor apparaten beheerd door Intune](https://docs.microsoft.com/intune/enrollment-options).
