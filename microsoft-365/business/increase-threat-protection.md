---
title: Bescherming tegen bedreigingen voor Microsoft 365 voor Bedrijven vergroten
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
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
description: Stel Geavanceerde bedreigingsbeveiliging van Office 365 in en bescherm gevoelige gegevens tegen phishing, malware en andere bedreigingen.
ms.openlocfilehash: 2dd75b20bf203b9b8f0cdefb2459c45d1d0ccec1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627121"
---
# <a name="increase-threat-protection"></a>Bedreigingsbeveiliging verbeteren

Met dit artikel u de bescherming in uw Microsoft 365-abonnement verhogen om te beschermen tegen phishing, malware en andere bedreigingen. Deze aanbevelingen zijn geschikt voor organisaties met een verhoogde behoefte aan veiligheid, zoals advocatenkantoren en klinieken voor gezondheidszorg.

Controleer voordat u begint de beveiligde score van Office 365. Office 365 Secure Score analyseert de beveiliging van uw organisatie op basis van uw reguliere activiteiten en beveiligingsinstellingen en kent een score toe. Begin met het noteren van uw huidige score. Voer de in dit artikel aanbevolen acties uit om uw score te verhogen. Het doel is niet om de maximale score te bereiken, maar om je bewust te zijn van mogelijkheden om je omgeving te beschermen die de productiviteit van je gebruikers niet negatief beïnvloeden. 

Zie [Microsoft Secure Score voor](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)meer informatie.

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Verhoog het niveau van bescherming tegen malware in e-mail

Uw Office 365- of Microsoft 365-omgeving biedt bescherming tegen malware. U deze bescherming verhogen door bijlagen te blokkeren met bestandstypen die vaak worden gebruikt voor malware. Ga als bedoeld als het gaat om meer bescherming tegen malware in e-mail:
  
1. Ga [https://protection.office.com](https://protection.office.com) naar en meld u aan met uw beheerdersaccountreferenties. 
    
2. Kies in &amp; het Security Compliance Center in het linkernavigatiedeelvenster onder **Bedreigingsbeheer** **de** \> optie **Beleid Anti-Malware**.
    
3. Dubbelklik op het standaardbeleid om dit bedrijfsbrede beleid te bewerken.
    
4. Selecteer **Instellingen**.
    
5. Selecteer **onder het filter Algemene bijlagetypen**, Selecteer **Aan**. De geblokkeerde bestandstypen worden weergegeven in het venster direct onder dit besturingselement. Zorg ervoor dat u deze bestandstypen toevoegt:
   - ade, adp, ani, bas, vleermuis, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsc, wsf, wsh, exe, pif  <br/> 
   
   Indien nodig u later bestandstypen toevoegen of verwijderen.
    
6. Selecteer **Opslaan.**
    
Zie [Bescherming tegen malware](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409)voor meer informatie .
  
## <a name="protect-against-ransomware"></a>Beveiligen tegen ransomware

Ransomware beperkt de toegang tot gegevens door het versleutelen van bestanden of het vergrendelen van computerschermen. Het probeert vervolgens om geld af te persen van slachtoffers door te vragen om "losgeld", meestal in de vorm van cryptocurrencies zoals Bitcoin, in ruil voor toegang tot gegevens. 
  
Om te beschermen tegen ransomware, maak een of meer mail flow regels om bestandsextensies die vaak worden gebruikt voor ransomware te blokkeren. (U hebt deze regels toegevoegd in de [verhoging van het niveau van bescherming tegen malware in e-mailstap.)](#raise-the-level-of-protection-against-malware-in-mail) U gebruikers die deze bijlagen in e-mail ontvangen ook waarschuwen.

Naast de bestanden die u in de vorige stap hebt geblokkeerd, is het een goede gewoonte om een regel te maken om gebruikers te waarschuwen voordat u Office-bestandsbijlagen opent die macro's bevatten. Ransomware kan worden verborgen in macro's, dus waarschuwen gebruikers niet om deze bestanden te openen van mensen die ze niet kennen.

Ga als lid van het openbaar vervoer naar een andere regel:
  
1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>beheercentrum bij , en kies **Beheercentra** \> **Exchange**.
    
2. Selecteer **regels**in de categorie **e-mailstroom** .
    
3. Selecteer **+** en selecteer **Vervolgens Een nieuwe regel maken**.
    
4. Selecteer **Meer opties** onder aan het dialoogvenster om de volledige set opties te bekijken. 
    
5. Pas de instellingen in de volgende tabel toe voor de regel. Gebruik de standaardwaarden voor de rest van de instellingen, tenzij u deze wilt wijzigen.
    
6. Kies **Opslaan**.
    
|**Instelling**|**Gebruikers waarschuwen voordat u bijlagen van Office-bestanden opent**||
|:-----|:-----|:-----|
|Name  <br/> |Anti-ransomware regel: gebruikers waarschuwen  <br/>  |
|Deze regel toepassen als . . .  <br/> |Elke bijlage . . . bestandsextensie komt overeen . . .  <br/> |
|Woorden of zinnen opgeven  <br/> |Voeg deze bestandstypen toe:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm  <br/>|
|Doe het volgende. . .  <br/> |De ontvanger op de hoogte stellen met een bericht  <br/> |
|Berichttekst opgeven  <br/> |Open dit soort bestanden niet van mensen die u niet kent, omdat ze macro's met kwaadaardige code kunnen bevatten.  <br/> |
   
Zie voor meer informatie:
  
- [Hoe om te gaan met ransomware](https://go.microsoft.com/fwlink/?linkid=2016501)
    
- [Uw OneDrive herstellen](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Automatisch doorsturen voor e-mail stoppen

Hackers die toegang krijgen tot het postvak van een gebruiker kunnen e-mail stelen door het postvak in te stellen om e-mail automatisch door te sturen. Dit kan zelfs gebeuren zonder het bewustzijn van de gebruiker. Als u dit wilt voorkomen, configureert u een regel voor e-mailstroom. 
  
Als u een regel voor het vervoer van e-mail wilt maken, bekijkt u [deze korte video](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) of volgt u de volgende stappen:
  
1. Selecteer In het Microsoft 365-beheercentrum de optie **Beheercentra** \> **Exchange**.
    
2. Selecteer **regels**in de categorie **e-mailstroom** .
    
3. Selecteer **+** en selecteer **Vervolgens Een nieuwe regel maken**.
    
4. Als u alle opties wilt bekijken, selecteert u **Meer opties** onder aan het dialoogvenster. 
    
5. Pas de instellingen toe in de volgende tabel. Gebruik de standaardwaarden voor de rest van de instellingen, tenzij u deze wilt wijzigen.
    
6. Kies **Opslaan**.
    
|**Instelling**|**Gebruikers waarschuwen voordat u bijlagen van Office-bestanden opent**|
|:-----|:-----|
|Name  <br/> |Automatisch doorsturen van e-mail naar externe domeinen voorkomen  <br/> |
|Pas deze regel toe als ...  <br/> |De afzender . . . is extern/intern . . . Binnen de organisatie  <br/> |
|Voorwaarde toevoegen  <br/> |De berichteigenschappen . . . het berichttype opnemen . . . Automatisch doorsturen  <br/> |
|Doe de volgende ...  <br/> |Het bericht blokkeren . . . het bericht af te wijzen en een uitleg op te nemen.  <br/> |
|Berichttekst opgeven  <br/> |Het automatisch doorsturen van e-mail buiten deze organisatie wordt om veiligheidsredenen voorkomen.  <br/> |


## <a name="protect-your-email-from-phishing-attacks"></a>Bescherm uw e-mail tegen phishing-aanvallen

Als u een of meer aangepaste domeinen hebt geconfigureerd voor uw Office 365- of Microsoft 365-omgeving, u gerichte antiphishingbeveiliging configureren. ATP-bescherming tegen phishing, onderdeel van Office 365 Advanced Threat Protection, kan uw organisatie beschermen tegen schadelijke phishing-aanvallen en andere phishing-aanvallen. Als u geen aangepast domein hebt geconfigureerd, hoeft u dit niet te doen.
  
We raden u aan aan aan de slag te gaan met deze bescherming door een beleid te maken om uw belangrijkste gebruikers en uw aangepaste domein te beschermen. 

Als u een ATP-antiphishingbeleid wilt maken, bekijkt u [deze korte trainingsvideo](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)of voert u de volgende stappen uit:
  
1. Ga naar [https://protection.office.com](https://protection.office.com). 
    
2. Kies &amp; **Beleid**in het Beveiligingscompliancecentrum in het linkernavigatiedeelvenster onder **Bedreigingsbeheer**.
    
3. Kies **op** de pagina Beleid **atp-antiphishing**.
    
4. Selecteer op de **antiphishingpagina** **+ Maak**. Een wizard lanceert u door uw antiphishingbeleid te definiëren.
    
5. Geef de naam, beschrijving en instellingen voor uw beleid op zoals aanbevolen in de volgende tabel. Zie [Meer informatie over beleidsopties voor antiphishing op ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#learn-about-atp-anti-phishing-policy-options)voor meer informatie . 
    
6. Nadat u uw instellingen hebt gecontroleerd, kiest **u Dit beleid maken** of **Opslaan,** naar gelang van het geval.
    

|**Instellen of optie**<br/>|**Aanbevolen instelling** <br/>|
|:-----|:-----|
|Name  <br/> |Domein en meest waardevolle campagnemedewerkers  <br/> |
|Beschrijving  <br/> |Zorg ervoor dat de belangrijkste medewerkers en ons domein niet worden nagebootst.  <br/> |
|Gebruikers toevoegen om te beschermen  <br/> |Selecteer **+ Voeg een voorwaarde toe, De ontvanger is**. Typ gebruikersnamen of voer het e-mailadres in van de kandidaat, campagnemanager en andere belangrijke medewerkers. U maximaal 20 interne en externe adressen toevoegen die u wilt beschermen tegen imitatie.  <br/> |
|Domeinen toevoegen om te beschermen  <br/> |Selecteer **+ Een voorwaarde toevoegen, Het domein van de geadresseerden is**. Voer het aangepaste domein in dat is gekoppeld aan uw Microsoft 365-abonnement als u er een hebt gedefinieerd. U meer dan één domein invoeren.  <br/> |
|Acties kiezen  <br/> |Als e-mail wordt verzonden door een nagebootste gebruiker: Kies **Bericht omleiden naar een ander e-mailadres**en typ vervolgens het e-mailadres van de beveiligingsbeheerder. *Bijvoorbeeld<span><span>Alice @contoso.com*. Als e-mail wordt verzonden door een nagebootst domein: Kies **Quarantainebericht**.  <br/> |
|Postvakintelligentie  <br/> |Postvakinformatie wordt standaard geselecteerd wanneer u een nieuw antiphishingbeleid maakt. Laat deze instelling **Aan** voor de beste resultaten.  <br/> |
|Vertrouwde afzenders en domeinen toevoegen  <br/> |Hier u uw eigen domein of andere vertrouwde domeinen toevoegen.  <br/> |
|Toegepast op  <br/> |Selecteer **Het domein van de geadresseerde is**. Selecteer **onder Een van deze**opties **Kiezen**. Selecteer **+ Toevoegen**. Schakel het selectievakje in naast de naam van het domein, bijvoorbeeld *contoso.<span> com <span>*, in de lijst en selecteer **Toevoegen**. Selecteer **Gereed**.  <br/> |
  
## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>Beschermen tegen schadelijke bijlagen en bestanden met ATP Safe Attachments

Mensen verzenden, ontvangen en delen regelmatig bijlagen, zoals documenten, presentaties, spreadsheets en meer. Het is niet altijd gemakkelijk om te vertellen of een bijlage veilig of kwaadaardig is door alleen maar naar een e-mailbericht te kijken. Office 365 Advanced Threat Protection bevat ATP Safe Attachment protection, maar deze beveiliging is niet standaard ingeschakeld. We raden u aan een nieuwe regel te maken om deze beveiliging te gebruiken. Deze beveiliging geldt ook voor bestanden in SharePoint, OneDrive en Microsoft Teams.
  
Als u een ATP-beleid voor veilige bijlagen wilt maken, bekijkt u [deze korte video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)of voert u de volgende stappen uit:
  
1. Ga [https://protection.office.com](https://protection.office.com)naar en meld je aan met je beheerdersaccount. 
    
2. Kies &amp; **Beleid**in het Beveiligingscompliancecentrum in het linkernavigatiedeelvenster onder **Bedreigingsbeheer**.
    
3. Kies op de pagina Beleid de optie **Veilige ATP-bijlagen**.
    
4. Pas deze beveiliging op de pagina Veilige bijlagen breed toe door het selectievakje **ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams in** te schakelen. 
    
5. Selecteer **+** om een nieuw beleid te maken. 
    
6. Pas de instellingen toe in de volgende tabel. 
    
7. Nadat u uw instellingen hebt gecontroleerd, kiest **u Dit beleid maken** of **Opslaan,** indien van toepassing.
    

|**Instellen of optie**|**Aanbevolen instelling** <br/>|
|:-----|:-----|
|Name  <br/> |Blokkeer huidige en toekomstige e-mails met gedetecteerde malware.  <br/> |
|Beschrijving  <br/> |Blokkeer huidige en toekomstige e-mails en bijlagen met gedetecteerde malware.  <br/> |
|Bijlagen opslaan onbekende malware reactie  <br/> |Selecteer **Blokkeren - Blokkeer de huidige en toekomstige e-mails en bijlagen met gedetecteerde malware.**  <br/> |
|Bijlage bij detectie omleiden  <br/> |Omleiding inschakelen (selecteer dit vak) Voer het beheerdersaccount of een postvakinstelling in voor quarantaine.          Pas de bovenstaande selectie toe als malware scannen op bijlagen een keer uit of fout optreedt (selecteer dit vak).  <br/> |
|Toegepast op  <br/> |Het domein van de ontvanger is . . . selecteer uw domein.  <br/> |
   
Zie [Office 365 ATP-beleid voor phishing instellen](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)voor meer informatie .
  
## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a>Bescherm tegen phishing-aanvallen met ATP Safe Links

Hackers verbergen soms kwaadaardige websites in links in e-mail of andere bestanden. Office 365 ATP Safe Links (ATP Safe Links), onderdeel van Office 365 Advanced Threat Protection, kan uw organisatie helpen beschermen door de time-of-click verificatie van webadressen (URL's) in e-mailberichten en Office-documenten te bieden. Bescherming wordt gedefinieerd via het ATP Safe Links-beleid.
  
Wij raden u aan het volgende te doen:
  
- Wijzig het standaardbeleid om de beveiliging te verhogen.
    
- Voeg een nieuw beleid toe dat is gericht op alle ontvangers in uw domein.
    
Als u ATP Safe Links wilt instellen, bekijkt u [deze korte trainingsvideo](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)of voert u de volgende stappen uit:
  
1. Ga [https://protection.office.com](https://protection.office.com)naar en meld je aan met je beheerdersaccount. 
    
2. Kies &amp; **Beleid**in het Beveiligingscompliancecentrum in het linkernavigatiedeelvenster onder **Bedreigingsbeheer**.
    
3. Kies op de pagina Beleid de optie **Veilige links van ATP**.
    
Ga als u het standaardbeleid wijzigen:
  
1. Selecteer op de pagina Veilige koppelingen onder **Beleid dat van toepassing is op de hele organisatie**het **standaardbeleid.** 
    
2. Selecteer **Microsoft 365 Apps voor bedrijven, Office voor iOS en Android**onder Instellingen die van toepassing zijn op **inhoud, behalve e-mail.**
    
3. Kies **Opslaan**. 
    
Ga als bedoeld als het gaat om een nieuw beleid te maken dat is gericht op alle ontvangers in uw domein:
  
1. Selecteer **+** op de pagina Veilige koppelingen onder **Beleid dat van toepassing is op de hele organisatie**om een nieuw beleid te maken. 
    
2. Pas de instellingen in de volgende tabel toe.
    
3. Kies **Opslaan**. 

|**Instellen of optie**|**Aanbevolen instelling** <br/>|
|:-----|:-----|
|Name  <br/> |Beleid voor veilige koppelingen voor alle ontvangers in het domein  <br/> |
|De actie selecteren voor onbekende mogelijk schadelijke URL's in berichten  <br/> |Selecteer **Op - URL's worden herschreven en gecontroleerd aan de hand van een lijst met bekende schadelijke links wanneer de gebruiker op de koppeling klikt.**  <br/> |
|Veilige bijlagen gebruiken om downloadbare inhoud te scannen  <br/> |Selecteer dit vak.  <br/> |
|Toegepast op  <br/> |Het domein van de ontvanger is . . . selecteer uw domein.  <br/> |
   
Zie [veilige koppelingen van Office 365 ATP voor](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409)meer informatie .

## <a name="go-to-intune-admin-center"></a>Ga naar Intune-beheercentrum

1. Meld u aan bij [Azure portal](https://portal.azure.com/).

2. Selecteer **Alle services** en typ *Intune* in het **zoekvak**.

3. Zodra de resultaten worden weergegeven, selecteert u de start naast **Microsoft Intune** om het later een favoriet en gemakkelijk te vinden.

Naast het beheercentrum u Intune gebruiken om de apparaten van uw organisatie in te schrijven en te beheren. Zie [Mogelijkheden per inschrijvingsmethode voor Windows-apparaten](https://docs.microsoft.com/intune/enrollment/enrollment-method-capab) en [inschrijvingsopties voor apparaten die door Intune worden beheerd voor](https://docs.microsoft.com/intune/enrollment-options)meer informatie.
