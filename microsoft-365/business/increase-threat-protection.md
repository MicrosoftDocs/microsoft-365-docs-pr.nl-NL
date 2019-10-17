---
title: Bedreigingsbeveiliging voor Microsoft 365 Business verhogen
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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Stel de geavanceerde Bedreigingsbeveiliging van Office 365 in en beveilig gevoelige gegevens.
ms.openlocfilehash: 0b0c1ac1d23bc7b167a58ecf93019a77c51c4366
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/17/2019
ms.locfileid: "37576013"
---
# <a name="increase-threat-protection"></a>Verhoog de bescherming tegen dreigingen

Dit artikel helpt u bij het verhogen van de beveiliging in uw Microsoft 365-abonnement ter bescherming tegen phishing, malware en andere bedreigingen. Deze aanbevelingen zijn geschikt voor organisaties met een verhoogde behoefte aan veiligheid, zoals advocatenkantoren, en zorg klinieken.

Controleer voordat u begint de Secure Score van Office 365. Office 365 Secure Score analyseert de beveiliging van uw Office 365-organisatie op basis van uw reguliere activiteiten en beveiligingsinstellingen en wijst een score aan. Begin met het noteren van uw huidige score. Het nemen van de acties aanbevolen in dit artikel verhoogt uw score. Het doel is niet om de maximale score te behalen, maar om zich bewust te zijn van de mogelijkheden om uw omgeving te beschermen die de productiviteit voor uw gebruikers niet nadelig beïnvloeden. 

Zie [Microsoft Secure Score](https://docs.microsoft.com/en-us/office365/securitycompliance/microsoft-secure-score)voor meer informatie.

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Verhoog het niveau van bescherming tegen malware in mail

Uw Office 365-of Microsoft 365-omgeving bevat bescherming tegen malware, maar u deze beveiliging verhogen door bijlagen te blokkeren met bestandstypen die vaak worden gebruikt voor malware. Om malware bescherming in e-mail te verhogen:
  
1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met de referenties van uw beheerdersaccount. 
    
2. In de Office 365 Security &amp; compliance Center, in het linkernavigatievenster onder **bedreigings beheer**, kiest u **beleid** \> **anti-malware**.
    
3. Dubbelklik op het standaardbeleid om dit bedrijfsbrede beleid te bewerken.
    
4. Klik op **instellingen**.
    
5. Onder **algemene Bijlagetypen filter**, selecteer **aan**. De bestandstypen die worden geblokkeerd, worden in het venster direct onder dit besturingselement weergegeven.  Zorg ervoor dat u deze bestandstypen toevoegt:
   - ADE, ADP, Ani, bas, bat, chm, cmd, com, cpl, CRT, HLP, HT, HTA, inf, ins, ISP, job, js, JSE, LNK, MDA, MDB, MDE, MDZ, MSC, MSI, MSP, MST, PCD, reg, SCR, SCT, SHS, URL, VB, VBE, vbs, WSC, wsf, WSH, exe, PIF  <br/> U later, indien nodig, bestandstypen toevoegen of verwijderen.
    
6. Klik op **opslaan.**
    
Zie voor meer informatie, [anti-malware bescherming](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409).
  
## <a name="protect-against-ransomware"></a>Beschermen tegen Ransomware

Ransomware beperkt de toegang tot gegevens door het versleutelen van bestanden of het vergrendelen van computerschermen. Het probeert vervolgens om geld af te persen van slachtoffers door te vragen voor "losgeld," meestal in de vorm van cryptocurrencies zoals Bitcoin, in ruil voor toegang tot gegevens. 
  
U beschermen tegen Ransomware door het creëren van een of meer mail flow regels om bestandsextensies die vaak worden gebruikt voor Ransomware blokkeren (deze werden toegevoegd in de [verhoging van het niveau van bescherming tegen malware in mail](#raise-the-level-of-protection-against-malware-in-mail) stap), of om gebruikers te waarschuwen die deze ontvangen bijlagen in e-mail.

Naast de bestanden die u in de vorige stap hebt geblokkeerd, is het ook een goede gewoonte om een regel te maken om gebruikers te waarschuwen voordat u Office-bestandsbijlagen opent die macro's bevatten. Ransomware kan worden verborgen in macro's, dus we zullen gebruikers waarschuwen om deze bestanden niet te openen van mensen die ze niet kennen.

Een regel voor e-mail transport maken:
  
1. Ga naar het Admin Center op <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> en kies **admin Centers** \> **Exchange**.
    
2. Klik in de categorie **e-mail stroom** op **regels**.
    
3. Klik **+** op en klik vervolgens op **een nieuwe regel maken**.
    
4. Klik op **meer opties** onder in het dialoogvenster om de volledige set opties weer te geven. 
    
5. Pas de instellingen in de volgende tabel voor de regel toe. Laat de rest van de instellingen op de standaardwaarde staan, tenzij u deze wilt wijzigen.
    
6. Klik op **Opslaan**.
    
|**Instelling**|**Waarschuw gebruikers voordat u bijlagen van Office-bestanden opent**||
|:-----|:-----|:-----|
|Name  <br/> |Anti-Ransomware regel: Waarschuw gebruikers  <br/>  |
|Deze regel toepassen als. . .  <br/> |Elke bijlage. . . bestandsextensie wedstrijden. . .  <br/> |
|Woorden of zinnen opgeven  <br/> |Voeg deze bestandstypen toe:  <br/> dotm, DOCM, xlsm, sltm, xla, xlam, XLL, PPTM, POTM, PPAM, PPSM, sldm  <br/>|
|Het volgende doen. . .  <br/> |De geadresseerde waarschuwen met een bericht  <br/> |
|Berichttekst opgeven  <br/> |Open dit type bestanden niet van mensen die je niet kent, omdat ze macro's met schadelijke code kunnen bevatten.  <br/> |
   
Zie voor meer informatie:
  
- [Hoe om te gaan met Ransomware](https://go.microsoft.com/fwlink/?linkid=2016501&amp;clcid=0x409)
    
- [Uw OneDrive herstellen](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)
    


## <a name="stop-auto-forwarding-for-email"></a>Automatisch doorsturen voor e-mail stoppen

Hackers die toegang krijgen tot het postvak van een gebruiker kunnen uw e-mail stelen door het postvak in te stellen om e-mail automatisch door te sturen. Dit kan zelfs gebeuren zonder het bewustzijn van de gebruiker. U voorkomen dat dit gebeurt door het configureren van een e-mail stroom regel. 
  
Als u een regel voor e-mail transport wilt maken, bekijkt u [deze korte video](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) of volgt u deze stappen:
  
1. In de Microsoft 365 Admin Center, klikt u op **admin Centers** \> **Exchange**.
    
2. Klik in de categorie **e-mail stroom** op **regels**.
    
3. Klik **+** op en klik vervolgens op **een nieuwe regel maken**.
    
4. Klik op **meer opties** onder in het dialoogvenster om de volledige set opties weer te geven. 
    
5. Pas de instellingen toe in de volgende tabel. Laat de rest van de instellingen op de standaardwaarde staan, tenzij u deze wilt wijzigen.
    
6. Klik op **Opslaan**.
    
|**Instelling**|**Waarschuw gebruikers voordat u bijlagen van Office-bestanden opent**|
|:-----|:-----|
|Name  <br/> |Voorkom het automatisch doorsturen van e-mail naar externe domeinen  <br/> |
|Deze regel toepassen als...  <br/> |De afzender. . . is extern/intern. . . Binnen de organisatie  <br/> |
|Voorwaarde toevoegen  <br/> |De berichteigenschappen. . . het berichttype opnemen. . . Automatisch vooruitspoelen  <br/> |
|Doe het volgende...  <br/> |Blokkeer het bericht. . . het bericht afwijzen en een toelichting opnemen.  <br/> |
|Berichttekst opgeven  <br/> |E-mail automatisch doorsturen buiten deze organisatie wordt om veiligheidsredenen verhinderd.  <br/> |


## <a name="protect-your-email-from-phishing-attacks"></a>Bescherm uw e-mail tegen phishing-aanvallen

Als u een of meer aangepaste domeinen hebt geconfigureerd voor uw Office 365-of Microsoft 365-omgeving, u gerichte anti-phishing-beveiliging configureren. ATP anti-phishing-beveiliging, onderdeel van Office 365 Advanced Threat Protection, u uw organisatie beschermen tegen schadelijke imitatie gebaseerde phishing-aanvallen en andere phishing-aanvallen. Als u een aangepast domein nog niet hebt geconfigureerd, hoeft u dit niet te doen.
  
We raden aan aan de slag te gaan met deze beveiliging door een beleid te maken om uw belangrijkste gebruikers en uw aangepaste domein te beschermen. 

  
Als u een ATP anti-phishing-beleid wilt maken, bekijkt u [deze korte trainingsvideo](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)of voert u de volgende stappen uit:
  
1. Ga naar [https://protection.office.com](https://protection.office.com). 
    
2. In de Office 365 Security &amp; compliance Center, in het linkernavigatievenster onder **bedreigings beheer**, kiest u **beleid**.
    
3. Kies op de pagina **beleid** **ATP anti-phishing**.
    
4. Selecteer **+ maken**op de pagina **anti-phishing** . Er wordt een wizard gestart die u begeleidt bij het definiëren van uw anti-phishingbeleid.
    
5. Geef de naam, beschrijving en instellingen voor uw beleid zoals aanbevolen in de onderstaande grafiek. Zie [meer informatie over ATP anti-phishing-beleidsopties](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409) voor meer informatie. 
    
6. Nadat u uw instellingen hebt gecontroleerd, kiest u **dit beleid maken** of **Opslaan**, indien van toepassing.
    

|**Instelling of optie**<br/>|**Aanbevolen instelling** <br/>|
|:-----|:-----|
|Name  <br/> |Domein en meest waardevolle campagne medewerkers  <br/> |
|Beschrijving  <br/> |Zorg voor het belangrijkste personeel en ons domein wordt niet geïmiteerd.  <br/> |
|Gebruikers toevoegen om te beschermen  <br/> |Selecteer **+ een voorwaarde toevoegen, de geadresseerde is**. Typ gebruikersnamen of voer het e-mailadres in van de kandidaat, campaign manager en andere belangrijke personeelsleden. U maximaal 20 interne en externe adressen toevoegen die u wilt beschermen tegen imitatie.  <br/> |
|Domeinen toevoegen om te beschermen  <br/> |Selecteer **+ een voorwaarde toevoegen, het domein van de geadresseerde is**. Voer het aangepaste domein dat is gekoppeld aan uw Microsoft 365-abonnement, als u een hebt gedefinieerd. U meer dan één domein invoeren.  <br/> |
|Acties kiezen  <br/> |Als e-mail wordt verzonden door een geïmiteerde gebruiker: Kies **Bericht omleiden naar een ander e-mailadres**en typ vervolgens het e-mailadres van de beveiligingsbeheerder; bijvoorbeeld, *Alice<span><span>@contoso. com*.          Als e-mail wordt verzonden door een geïmiteerd domein: Kies **quarantaine bericht**.  <br/> |
|Mailbox Intelligence  <br/> |Mailbox Intelligence wordt standaard geselecteerd wanneer u een nieuw antiphishing-beleid maakt. Laat **deze instelling voor** de beste resultaten.  <br/> |
|Vertrouwde afzenders en domeinen toevoegen  <br/> |Hier u uw eigen domein of andere vertrouwde domeinen toevoegen.  <br/> |
|Toegepast op  <br/> |Selecteer **het domein van de geadresseerde is**. Selecteer onder **een van deze**, **kiezen**. Selecteer **+ toevoegen**. Schakel het selectievakje in naast de naam van het domein, bijvoorbeeld *contoso.<span> com <span>*, in de lijst en selecteer vervolgens **toevoegen**. Selecteer **Gereed**.  <br/> |
  
## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>Bescherm tegen schadelijke bijlagen en bestanden met ATP veilige bijlagen

Mensen sturen, ontvangen en delen regelmatig bijlagen, zoals documenten, presentaties, spreadsheets en meer. Het is niet altijd gemakkelijk om te zien of een bijlage veilig of schadelijk is door alleen naar een e-mail bericht te kijken. Office 365 Advanced Threat Protection bevat ATP veilige bijlagebeveiliging, maar deze beveiliging is niet standaard ingeschakeld. Het is raadzaam dat u een nieuwe regel maken om te beginnen met deze beveiliging. Deze bescherming strekt zich uit tot bestanden in SharePoint, OneDrive en Microsoft-teams.
  
Als u een ATP Safe Attachment-beleid wilt maken, bekijkt u [deze korte video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)of voert u de volgende stappen uit:
  
1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw beheerdersaccount. 
    
2. In de Office 365 Security &amp; compliance Center, in het linkernavigatievenster onder **bedreigings beheer**, kiest u **beleid**.
    
3. Kies op de pagina beleid **ATP veilige bijlagen**.
    
4. Op de veilige bijlagen pagina, deze beveiliging breed toepassen door het selectievakje **ATP inschakelen voorsharepoint, OneDrive en Microsoft-teams** . 
    
5. Selecteer **+** om een nieuw beleid te maken. 
    
6. Pas de instellingen toe in de volgende tabel. 
    
7. Nadat u uw instellingen hebt gecontroleerd, kiest u **dit beleid maken** of **Opslaan**, indien van toepassing.
    

|**Instelling of optie**|**Aanbevolen instelling** <br/>|
|:-----|:-----|
|Name  <br/> |Blokkeer huidige en toekomstige e-mails met gedetecteerde malware.  <br/> |
|Beschrijving  <br/> |Blokkeer huidige en toekomstige e-mails en bijlagen met gedetecteerde malware.  <br/> |
|Bijlagen opslaan onbekende malware reactie  <br/> |Selecteer **blokkeren-Blokkeer de huidige en toekomstige e-mails en bijlagen met gedetecteerde malware**.  <br/> |
|Omleidings bijlage bij detectie  <br/> |Omleiding inschakelen (Schakel dit selectievakje in) Voer de beheerdersaccount of een postbus instellen voor quarantaine in.          De bovenstaande selectie toepassen als het scannen van malware voor bijlagen een time-out of fout optreedt (Selecteer dit vak).  <br/> |
|Toegepast op  <br/> |Het domein van de geadresseerde is. . . Selecteer uw domein.  <br/> |
   
Zie voor meer informatie, [Office 365 ATP anti-phishing-beleid instellen](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409).
  


## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a>Bescherm tegen phishing-aanvallen met ATP Safe links

Hackers verbergen soms kwaadaardige websites in links in e-mail of andere bestanden. Office 365 ATP veilige koppelingen (ATP veilige koppelingen), onderdeel van Office 365 geavanceerde Bedreigingsbeveiliging, u uw organisatie beveiligen door het bieden van tijd-van-klik verificatie van webadressen (Url's) in e-mail berichten en Office-documenten. Beveiliging wordt gedefinieerd via ATP-beleid voor veilige koppelingen.
  
Wij raden u aan het volgende te doen:
  
- Wijzig het standaardbeleid om de beveiliging te verhogen.
    
- Voeg een nieuw beleid toe dat is gericht op alle ontvangers in uw domein.
    
Als u ATP-veilige koppelingen wilt instellen, bekijkt u [deze korte trainingsvideo](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)of voert u de volgende stappen uit:
  
1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw beheerdersaccount. 
    
2. In de Office 365 Security &amp; compliance Center, in het linkernavigatievenster onder **bedreigings beheer**, kiest u **beleid**.
    
3. Kies op de pagina beleid **ATP veilige koppelingen**.
    
Het standaardbeleid wijzigen:
  
1. Selecteer het **standaard** beleid op de pagina Safe links onder **beleid dat van toepassing is op de hele organisatie**. 
    
2. Selecteer onder **instellingen die van toepassing zijn op inhoud behalve e-mail**, **Office 365 ProPlus, Office voor IOS en Android**.
    
3. Klik op **Opslaan**. 
    
Een nieuw beleid maken dat is gericht op alle ontvangers in uw domein:
  
1. Klik **+** op de pagina veilige koppelingen onder **beleid dat van toepassing is op de hele organisatie**, om een nieuw beleid te maken. 
    
2. Pas de instellingen toe die in de volgende tabel worden weergegeven.
    
3. Klik op **Opslaan**. 

|**Instelling of optie**|**Aanbevolen instelling** <br/>|
|:-----|:-----|
|Name  <br/> |Beleid voor veilige koppelingen voor alle geadresseerden in het domein  <br/> |
|Selecteer de actie voor onbekende mogelijk schadelijke Url's in berichten  <br/> |Selecteer **on-url's worden herschreven en gecontroleerd op basis van een lijst met bekende schadelijke koppelingen wanneer de gebruiker op de koppeling klikt**.  <br/> |
|Gebruik veilige bijlagen om downloadbare content te scannen  <br/> |Schakel dit selectievakje in.  <br/> |
|Toegepast op  <br/> |Het domein van de geadresseerde is. . . Selecteer uw domein.  <br/> |
   
Zie voor meer informatie, [Office 365 ATP veilige koppelingen](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409).

## <a name="go-to-intune-admin-center"></a>Ga naar intune Admin Center

1. Meld u aan bij [Azure Portal](https://portal.azure.com/).

2. Selecteer **alle services** en typ *intune* in het **zoekvak**.

3. Zodra de resultaten worden weergegeven, klikt u op de start naast **Microsoft intune** om het een favoriet te maken en later gemakkelijk te vinden.

Naast het Beheercentrum u intune gebruiken om de apparaten van uw organisatie in te schrijven en te beheren. Zie [mogelijkheden per inschrijvingsmethode voor Windows-apparaten](https://docs.microsoft.com/intune/enrollment-method-capabs) en [inschrijvingsopties voor apparaten die worden beheerd door intune](https://docs.microsoft.com/intune/enrollment-options)voor meer informatie.
