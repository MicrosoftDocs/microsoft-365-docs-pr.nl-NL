---
title: Bedreigingsbeveiliging verbeteren
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5abfef7b-5957-484a-b06b-a7c55e013e44
description: Hulp krijgen bij het verhogen van het beschermingsniveau in Microsoft 365
ms.openlocfilehash: 39c79f438bd8018f2e70863225664c55e4bcd615
ms.sourcegitcommit: 5c43e89ed94ad9fd1db049446383c65e548189b7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2020
ms.locfileid: "44322121"
---
# <a name="increase-threat-protection"></a>Bedreigingsbeveiliging verbeteren

Met dit artikel u de bescherming in uw Microsoft 365-abonnement verhogen om te beschermen tegen phishing, malware en andere bedreigingen. Deze aanbevelingen zijn geschikt voor organisaties met een verhoogde behoefte aan veiligheid, zoals politieke campagnes, advocatenkantoren en klinieken voor gezondheidszorg. 

Controleer voordat u begint de beveiligde score van Office 365. Office 365 Secure Score analyseert de beveiliging van uw organisatie op basis van uw reguliere activiteiten en beveiligingsinstellingen en wijst een score toe. Begin met het noteren van uw huidige score. Het nemen van de acties die in dit artikel worden aanbevolen, verhoogt uw score. Het doel is niet om de maximale score te bereiken, maar om je bewust te zijn van mogelijkheden om je omgeving te beschermen die de productiviteit van je gebruikers niet negatief beïnvloeden. 

Zie [Microsoft Secure Score voor](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)meer informatie.


## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Verhoog het niveau van bescherming tegen malware in e-mail

Uw Office 365- of Microsoft 365-omgeving bevat bescherming tegen malware, maar u deze bescherming verhogen door bijlagen te blokkeren met bestandstypen die vaak worden gebruikt voor malware. Ga als bedoeld als het gaat om malwarebescherming in e-mail:
  
1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw beheerdersaccountreferenties. 
    
2. Kies in het Security &amp; Compliance Center in het linkernavigatiedeelvenster onder **Bedreigingsbeheer** **de** optie \> **Beleid Anti-Malware**.
    
3. Dubbelklik op het standaardbeleid om dit bedrijfsbrede beleid te bewerken.
    
4. Klik op **Instellingen**.
    
5. Selecteer **onder het filter Algemene bijlagetypen**, Selecteer **Aan**. De geblokkeerde bestandstypen worden weergegeven in het venster direct onder dit besturingselement.  Zorg ervoor dat u deze bestandstypen toevoegt:
   - ade, adp, ani, bas, vleermuis, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsc, wsf, wsh, exe, pif  <br/> U bestandstypen later toevoegen of verwijderen, indien nodig.
    
6. Klik **op Opslaan.**
    
Zie [Bescherming tegen malware](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409)voor meer informatie .
  


## <a name="protect-against-ransomware"></a>Beveiligen tegen ransomware

Ransomware beperkt de toegang tot gegevens door het versleutelen van bestanden of het vergrendelen van computerschermen. Het probeert vervolgens om geld af te persen van slachtoffers door te vragen om "losgeld", meestal in de vorm van cryptocurrencies zoals Bitcoin, in ruil voor toegang tot gegevens. 
  
U beschermen tegen ransomware door het creëren van een of meer mail flow regels om bestandsextensies die vaak worden gebruikt voor ransomware te blokkeren (deze werden toegevoegd in de [verhoging van het niveau van bescherming tegen malware in e-mail](#raise-the-level-of-protection-against-malware-in-mail) stap), of om gebruikers die deze bijlagen ontvangen in e-mail te waarschuwen.

Naast de bestanden die u in de vorige stap hebt geblokkeerd, is het ook een goede gewoonte om een regel te maken om gebruikers te waarschuwen voordat u Office-bestandsbijlagen opent die macro's bevatten. Ransomware kan worden verborgen in macro's, dus gebruikers waarschuwen om deze bestanden niet te openen van mensen die ze niet kennen.

Ga als lid van het openbaar vervoer naar een andere regel:
  
1. Ga naar het beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> en kies **Exchange voor beheercentra** \> **Exchange**.
    
2. Klik in de categorie **e-mailstroom** op **regels**.
    
3. Klik **+** op en klik vervolgens op Een nieuwe regel **maken**.
    
4. Klik onder aan het dialoogvenster op **Meer opties** om de volledige set opties weer te geven. 
    
5. Pas de instellingen in de volgende tabel toe voor de regel. Laat de rest van de instellingen standaard staan, tenzij u deze wilt wijzigen.
    
6. Klik op **Opslaan**.
    
|**Instelling**|**Gebruikers waarschuwen voordat u bijlagen van Office-bestanden opent**||
|:-----|:-----|:-----|
|Name  <br/> |Anti-ransomware regel: gebruikers waarschuwen  <br/>  |
|Deze regel toepassen als . . .  <br/> |Elke bijlage . . . bestandsextensie komt overeen . . .  <br/> |
|Woorden of zinnen opgeven  <br/> |Voeg deze bestandstypen toe:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm  <br/>|
|Doe het volgende. . .  <br/> |De ontvanger op de hoogte stellen met een bericht  <br/> |
|Berichttekst opgeven  <br/> |Open dit soort bestanden niet van mensen die u niet kent, omdat ze macro's met kwaadaardige code kunnen bevatten.  <br/> |
   
Zie voor meer informatie:
  
- [Hoe om te gaan met ransomware](https://go.microsoft.com/fwlink/?linkid=2016501&amp;clcid=0x409)
    
- [Uw OneDrive herstellen](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)
    


## <a name="stop-auto-forwarding-for-email"></a>Automatisch doorsturen voor e-mail stoppen

Hackers die toegang krijgen tot het postvak van een gebruiker kunnen uw e-mail stelen door het postvak in te stellen om e-mail automatisch door te sturen. Dit kan zelfs gebeuren zonder het bewustzijn van de gebruiker. U dit voorkomen door een regel voor e-mailstroom te configureren. 
  
Als u een regel voor het vervoer van e-mail wilt maken, bekijkt u [deze korte video](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) of volgt u de volgende stappen:
  
1. Klik in het Microsoft 365-beheercentrum op **Exchange-beheercentra** \> **Exchange**.
    
2. Klik in de categorie **e-mailstroom** op **regels**.
    
3. Klik **+** op en klik vervolgens op Een nieuwe regel **maken**.
    
4. Klik onder aan het dialoogvenster op **Meer opties** om de volledige set opties weer te geven. 
    
5. Pas de instellingen toe in de volgende tabel. Laat de rest van de instellingen standaard staan, tenzij u deze wilt wijzigen.
    
6. Klik op **Opslaan**.
    
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
    
2. Kies Beleid in het &amp; Beveiligingscompliancecentrum in het linkernavigatiedeelvenster onder **Bedreigingsbeheer**. **Policy**
    
3. Kies **op** de pagina Beleid **atp-antiphishing**.
    
4. Selecteer op de **antiphishingpagina** **+ Maak**. Een wizard lanceert u door uw antiphishingbeleid te definiëren.
    
5. Geef de naam, beschrijving en instellingen voor uw beleid op, zoals aanbevolen in de onderstaande grafiek. Zie [Meer informatie over beleidsopties voor antiphishing op ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)voor meer informatie . 
    
6. Nadat u uw instellingen hebt gecontroleerd, kiest **u Dit beleid maken** of **Opslaan,** naar gelang van het geval.
    

|**Instellen of optie**<br/>|**Aanbevolen instelling** <br/>|
|:-----|:-----|
|Name  <br/> |Domein en meest waardevolle campagnemedewerkers  <br/> |
|Beschrijving  <br/> |Zorg ervoor dat de belangrijkste medewerkers en ons domein niet worden nagebootst.  <br/> |
|Gebruikers toevoegen om te beschermen  <br/> |Selecteer **+ Voeg een voorwaarde toe, De ontvanger is**. Typ gebruikersnamen of voer het e-mailadres in van de kandidaat, campagnemanager en andere belangrijke medewerkers. U maximaal 20 interne en externe adressen toevoegen die u wilt beschermen tegen imitatie.  <br/> |
|Domeinen toevoegen om te beschermen  <br/> |Selecteer **+ Een voorwaarde toevoegen, Het domein van de geadresseerden is**. Voer het aangepaste domein in dat is gekoppeld aan uw Microsoft 365-abonnement als u er een hebt gedefinieerd. U meer dan één domein invoeren.  <br/> |
|Acties kiezen  <br/> |Als e-mail wordt verzonden door een nagebootste gebruiker: Kies **Bericht omleiden naar een ander e-mailadres**en typ vervolgens het e-mailadres van de beveiligingsbeheerder. *Bijvoorbeeld Alice <span> <span> @contoso.com*.          Als e-mail wordt verzonden door een nagebootst domein: Kies **Quarantainebericht**.  <br/> |
|Postvakintelligentie  <br/> |Postvakinformatie wordt standaard geselecteerd wanneer u een nieuw antiphishingbeleid maakt. Laat deze instelling **Aan** voor de beste resultaten.  <br/> |
|Vertrouwde afzenders en domeinen toevoegen  <br/> |Hier u uw eigen domein of andere vertrouwde domeinen toevoegen.  <br/> |
|Toegepast op  <br/> |Selecteer **Het domein van de geadresseerde is**. Selecteer **onder Een van deze**opties **Kiezen**. Selecteer **+ Toevoegen**. Schakel het selectievakje in naast de naam van het domein, bijvoorbeeld *contoso. <span> <span> com*, in de lijst en selecteer **Toevoegen**. Selecteer **Gereed**.  <br/> |
   
Zie [Office 365 ATP-beleid voor phishing instellen](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)voor meer informatie .
  
## <a name="protect-against-malicious-attachments-files-and-links-with-advanced-threat-protection-atp"></a>Beschermen tegen schadelijke bijlagen, bestanden en koppelingen met Advanced Threat Protection (ATP)

![Banner die wijzen op https://aka.ms/aboutM365preview .](../media/m365admincenterchanging.png)

Zorg er eerst voor dat in het beheercentrum <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> de nieuwe preview van het beheercentrum is ingeschakeld. Schakel de schakelschakelaar in naast de tekst **Het nieuwe beheercentrum**.

   ![De nieuwe preview van het beheercentrum.](../media/previewon.png)

Als u de **pagina Setup** met kaarten in uw tenant nog niet ziet, raadpleegt u hoe u deze stappen uitvoeren in Security &amp; Compliance Center. Zie [ATP-veilige bijlagen instellen in het Security & Compliance Center](#set-up-atp-safe-attachments-in-the-security--compliance-center) en [ATP-veilige koppelingen instellen in het Security & Compliance Center.](#set-up-atp-safe-links-in-the-security--compliance-center)

1.  Kies In het linkernavigatiesysteem de optie **Instellen**.
2. Kies **op** de pagina Setup de optie **Weergave** op de **bewaarlijn voor geavanceerde bedreigingen.**</br></br>
    ![Kies Weergave op de bescherming verhogen tegen geavanceerde bedreigingen.](../media/startatp.png) 

3. Kies aan de slag op de pagina **Meer bescherming tegen geavanceerde bedreigingen** **.**
4. Schakel in het deelvenster dat wordt geopend de selectievakjes in naast **Koppelingen en bijlagen in e-mail,** Bestanden scannen in **SharePoint, OneDrive en Teams**en Koppelingen scannen in **Office-bureaublad- en Office Online-apps** onder **Items scannen op schadelijke inhoud**.

      - Onder **Koppelingen en bijlagen in e-mail**, Typ in Alle gebruikers of de specifieke gebruikers waarvan u de e-mail wilt scannen.

    ![Schakel alle selectievakjes in Meer bescherming tegen geavanceerde bedreigingen in.](../media/setatp.png)
5. Kies **Beleid maken** om veilige ATP-bijlagen en ATP-veilige koppelingen in te schakelen.

### <a name="set-up-atp-safe-attachments-in-the-security--compliance-center"></a>ATP-veilige bijlagen instellen in het Security & Compliance Center

Mensen verzenden, ontvangen en delen regelmatig bijlagen, zoals documenten, presentaties, spreadsheets en meer. Het is niet altijd gemakkelijk om te vertellen of een bijlage veilig of kwaadaardig is door alleen maar naar een e-mailbericht te kijken. Office 365 Advanced Threat Protection bevat ATP Safe Attachment protection, maar deze beveiliging is niet standaard ingeschakeld. We raden u aan een nieuwe regel te maken om deze beveiliging te gebruiken. Deze beveiliging geldt ook voor bestanden in SharePoint, OneDrive en Microsoft Teams.
  
Als u een ATP-beleid voor veilige bijlagen wilt maken, bekijkt u [deze korte video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)of voert u de volgende stappen uit:
  
1. Ga naar [https://protection.office.com](https://protection.office.com) en meld je aan met je beheerdersaccount. 
    
2. Kies Beleid in het &amp; Beveiligingscompliancecentrum in het linkernavigatiedeelvenster onder **Bedreigingsbeheer**. **Policy**
    
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
  
### <a name="set-up-atp-safe-links-in-the-security--compliance-center"></a>ATP-veilige koppelingen instellen in het beveiligingscentrum & compliance

Hackers verbergen soms kwaadaardige websites in links in e-mail of andere bestanden. Office 365 ATP Safe Links (ATP Safe Links), onderdeel van Office 365 Advanced Threat Protection, kan uw organisatie helpen beschermen door de time-of-click verificatie van webadressen (URL's) in e-mailberichten en Office-documenten te bieden. Bescherming wordt gedefinieerd via het ATP Safe Links-beleid.
  
Wij raden u aan het volgende te doen:
  
- Wijzig het standaardbeleid om de beveiliging te verhogen.
    
- Voeg een nieuw beleid toe dat is gericht op alle ontvangers in uw domein.
    
Als u ATP Safe Links wilt instellen, bekijkt u [deze korte trainingsvideo](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)of voert u de volgende stappen uit:
  
1. Ga naar [https://protection.office.com](https://protection.office.com) en meld je aan met je beheerdersaccount. 
    
2. Kies Beleid in het &amp; Beveiligingscompliancecentrum in het linkernavigatiedeelvenster onder **Bedreigingsbeheer**. **Policy**
    
3. Kies op de pagina Beleid de optie **Veilige links van ATP**.
    
Ga als u het standaardbeleid wijzigen:
  
1. Selecteer op de pagina Veilige koppelingen onder **Beleid dat van toepassing is op de hele organisatie**het **standaardbeleid.** 
    
2. Selecteer **Microsoft 365 Apps voor bedrijven, Office voor iOS en Android**onder Instellingen die van toepassing zijn op **inhoud, behalve e-mail.**
    
3. Klik op **Opslaan**. 
    
Ga als bedoeld als het gaat om een nieuw beleid te maken dat is gericht op alle ontvangers in uw domein:
  
1. Klik op de pagina Veilige koppelingen onder **Beleid dat van toepassing is op de hele organisatie**om een nieuw beleid te **+** maken. 
    
2. Pas de instellingen in de volgende tabel toe.
    
3. Klik op **Opslaan**. 

|**Instellen of optie**|**Aanbevolen instelling** <br/>|
|:-----|:-----|
|Name  <br/> |Beleid voor veilige koppelingen voor alle ontvangers in het domein  <br/> |
|De actie selecteren voor onbekende mogelijk schadelijke URL's in berichten  <br/> |Selecteer **Op - URL's worden herschreven en gecontroleerd aan de hand van een lijst met bekende schadelijke links wanneer de gebruiker op de koppeling klikt.**  <br/> |
|Veilige bijlagen gebruiken om downloadbare inhoud te scannen  <br/> |Selecteer dit vak.  <br/> |
|Toegepast op  <br/> |Het domein van de ontvanger is . . . selecteer uw domein.  <br/> |
   
Zie [veilige koppelingen van Office 365 ATP voor](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409)meer informatie .
  
## <a name="turn-on-the-unified-audit-log"></a>Het uniform controlelogboek inschakelen

Nadat u de zoekopdracht voor controlelogboeken hebt ingeschakeld in het Security &amp; Compliance-centrum, u de beheerder en andere gebruikersactiviteit in het logboek behouden en deze doorzoeken. 

U moet de rol Controlelogboeken in Exchange Online toegewezen krijgen om zoeken in het controlelogboek in of uit te schakelen in uw Microsoft 365-abonnement. Standaard wordt deze rol toegewezen aan de rolgroepen Compliance Management en Organisatiebeheer op de pagina Machtigingen in het Exchange-beheercentrum. Globale beheerders in Microsoft 365 zijn standaard lid van deze groep.

1. Als u de zoekopdracht voor het controlelogboek wilt inschakelen, gaat u naar het beheercentrum <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> en kiest u **Naleving** onder **Beheercentra** in de linkernavigatie. 
2. Kies op de **microsoft 365-nalevingspagina** **Meer resources**en **open** vervolgens op de **Office 365-beveiligingscentrumkaart. &amp; **

    ![Kies Openen op de beveiligings- & compliance-auto's.](../media/gotosecandcomp.png)
3. Kies op de pagina beveiliging en naleving de optie **Zoeken** en vervolgens **Zoeken in het logboek .**
1. Kies **rechtsonweergeven**boven aan de **zoekpagina van het logboek** controleren .

Nadat de functie is ingeschakeld, u zoeken naar bestanden, mappen en veel activiteiten. Zie [zoeken in het controlelogboek](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)voor meer informatie .

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a>Instellingen voor anoniem delen afstemmen voor SharePoint- en OneDrive-bestanden en -mappen

(wijzig standaard anonieme koppelingsverloop in 14 dagen, wijzig standaardtype voor delen in 'Specifieke personen') Ga als het gaat om het wijzigen van de instellingen voor delen voor OneDrive en SharePoint:
1. Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> en kies **Vervolgens SharePoint** onder **Beheercentra** in de linkernavigatie. 
2. Ga in het SharePoint-beheercentrum naar **Beleid** \> **delen**.
3. Selecteer **Op** de pagina Delen onder **Koppelingen voor bestanden en mappen**de optie Specifieke **personen**en selecteer onder Geavanceerde instellingen voor **koppelingen 'Iedereen'** **deze koppelingen moet binnen deze dagen verlopen**en typ 14 (of een ander aantal dagen waarop u de koppelingslevensduur wilt beperken).

    ![Kies Specifieke personen en stel de vervaldatum van de koppeling in op 14 dagen.](../media/anyonelinks.png)

## <a name="activity-alerts"></a>Activiteitswaarschuwingen

U activiteitswaarschuwingen gebruiken om beheerders- en gebruikersactiviteiten bij te houden en incidenten ter voorkoming van malware en gegevensverlies in uw organisatie te detecteren. Uw abonnement bevat een set standaardbeleidsregels, maar u ook aangepaste beleidsregels maken. Zie [waarschuwingsbeleid voor](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)meer informatie . Als u bijvoorbeeld een belangrijk bestand opslaat in SharePoint dat u niet wilt dat iemand extern deelt, u een melding maken die u waarschuwt als iemand het wel deelt.

In de volgende afbeelding ziet u het standaardbeleid dat bij Microsoft 365 is opgenomen. <br/><br/>
    ![Standaardwaarschuwingsbeleid dat is opgenomen in Microsoft 365](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a>Agendadelen uitschakelen of beheren

U voorkomen dat mensen in uw organisatie hun agenda's delen of u ook beheren wat ze kunnen delen. U het delen bijvoorbeeld beperken tot alleen vrije/drukke tijden.

1. Ga naar het beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> en kies **Instellingen** services \> **& invoegingen**.
2. Kies op de pagina **Services & invoegtoepassing** en kies **Agenda**en kies of mensen in uw organisatie hun agenda's kunnen delen met mensen buiten die Office 365 of Exchange of met wie dan ook hebben. 
    Als u kiest voor het aandeel met iemand optie, u besluiten om ook alleen delen gratis / drukke informatie.

3. Kies Wijzigingen onder aan de pagina **opslaan.**

    Het volgende cijfer toont het delen van agenda's niet toegestaan. </br></br>
    ![Schermafbeelding van het weergeven van extern delen van agenda's als niet toegestaan.](../media/nocalendarsharing.png)

    Het volgende cijfer toont de instellingen wanneer het delen van agenda's is toegestaan met een e-mailkoppeling met alleen vrije/drukke informatie.

   ![Schermafbeelding van agendavrij/bezet delen met iedereen.](../media/sharefreebusy.png)

Als uw gebruikers hun agenda's mogen delen, raadpleegt u [deze instructies](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) voor het delen vanuit de webversie van Outlook.
