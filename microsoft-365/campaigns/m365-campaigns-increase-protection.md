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
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5abfef7b-5957-484a-b06b-a7c55e013e44
description: Hulp krijgen bij het verhogen van het beschermingsniveau in Microsoft 365
ms.openlocfilehash: 1e98f2dea06c342858a8acf2c221ea8f955eb75e
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527208"
---
# <a name="increase-threat-protection"></a>Bedreigingsbeveiliging verbeteren

In dit artikel u de bescherming in uw Microsoft 365-abonnement vergroten om u te beschermen tegen phishing, malware en andere bedreigingen. Deze aanbevelingen zijn geschikt voor organisaties met een verhoogde behoefte aan veiligheid, zoals politieke campagnes, advocatenkantoren en klinieken voor gezondheidszorg. 

Controleer uw Microsoft Secure Score voordat u begint. Microsoft Secure Score analyseert de beveiliging van uw organisatie op basis van uw reguliere activiteiten en beveiligingsinstellingen en kent een score toe. Begin met het noteren van uw huidige score. Het nemen van de acties aanbevolen in dit artikel verhoogt uw score. Het doel is niet om de maximale score te bereiken, maar om je bewust te zijn van mogelijkheden om je omgeving te beschermen die de productiviteit voor je gebruikers niet negatief beïnvloeden. 

Zie [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)voor meer informatie.


## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Verhoog het niveau van bescherming tegen malware in e-mail

Uw Office 365- of Microsoft 365-omgeving biedt bescherming tegen malware, maar u deze bescherming verhogen door bijlagen te blokkeren met bestandstypen die vaak worden gebruikt voor malware. Om malwarebescherming in e-mail te stoten:
  
1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw beheerdersaccountgegevens. 
    
2. Kies in het Security &amp; Compliance Center in het linkernavigatiedeelvenster onder **Bedreigingsbeheer** **de optie** \> **Beleidsantimalware**.
    
3. Dubbelklik op het standaardbeleid om dit bedrijfsbrede beleid te bewerken.
    
4. Klik op **Instellingen**.
    
5. Selecteer onder **Filter Algemene bijlagetypen**de optie **Aan**. De bestandstypen die worden geblokkeerd, worden in het venster direct onder dit besturingselement weergegeven.  Zorg ervoor dat u deze bestandstypen toevoegt:
   - ade, adp, ani, bas, vleermuis, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdzz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsf, wsf, wsh, exe, pif  <br/> U indien nodig bestandstypen later toevoegen of verwijderen.
    
6. Klik **op Opslaan.**
    
Zie [Bescherming tegen malware voor](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409)meer informatie.
  


## <a name="protect-against-ransomware"></a>Beveiligen tegen ransomware

Ransomware beperkt de toegang tot gegevens door bestanden te versleutelen of computerschermen te vergrendelen. Het probeert vervolgens om geld af te persen van slachtoffers door te vragen om "losgeld", meestal in de vorm van cryptocurrencies zoals Bitcoin, in ruil voor toegang tot gegevens. 
  
U beschermen tegen ransomware door het creëren van een of meer mail flow regels om bestandsextensies die vaak worden gebruikt voor ransomware te blokkeren (deze werden toegevoegd in de [verhoging van het niveau van bescherming tegen malware in e-mail](#raise-the-level-of-protection-against-malware-in-mail) stap), of om gebruikers die deze bijlagen ontvangen in e-mail te waarschuwen.

Naast de bestanden die u in de vorige stap hebt geblokkeerd, is het ook een goede gewoonte om een regel te maken om gebruikers te waarschuwen voordat u Office-bestandsbijlagen opent die macro's bevatten. Ransomware kan worden verborgen in macro's, dus waarschuwen gebruikers om deze bestanden niet te openen van mensen die ze niet kennen.

Ga als een regel voor e-mailtransport:
  
1. Ga naar het beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> en kies **Beheercentra** \> **Exchange**.
    
2. Klik in de categorie **e-mailstroom** op **regels**.
    
3. Klik **+** op en klik vervolgens op Een nieuwe regel **maken**.
    
4. Klik onder aan het dialoogvenster op **Meer opties** om de volledige set opties weer te geven. 
    
5. Pas de instellingen in de volgende tabel toe voor de regel. Laat de rest van de instellingen bij de standaardinstelling, tenzij u ze wilt wijzigen.
    
6. Klik op **Opslaan**.
    
|**Instelling**|**Gebruikers waarschuwen voordat u bijlagen van Office-bestanden opent**||
|:-----|:-----|:-----|
|Naam  <br/> |Anti-ransomware regel: waarschuwen gebruikers  <br/>  |
|Pas deze regel toe als . . .  <br/> |Elke bijlage . . . bestandsextensie komt overeen met . . .  <br/> |
|Woorden of zinnen opgeven  <br/> |Voeg deze bestandstypen toe:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm  <br/>|
|Ga als volgt te werk. . .  <br/> |De ontvanger op de hoogte stellen met een bericht  <br/> |
|Berichttekst weergeven  <br/> |Open dit soort bestanden niet van mensen die u niet kent, omdat ze mogelijk macro's met schadelijke code bevatten.  <br/> |
   
Zie voor meer informatie:
  
- [Hoe om te gaan met ransomware](https://go.microsoft.com/fwlink/?linkid=2016501&amp;clcid=0x409)
    
- [Uw OneDrive herstellen](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)
    


## <a name="stop-auto-forwarding-for-email"></a>Automatisch doorsturen voor e-mail stoppen

Hackers die toegang krijgen tot het postvak van een gebruiker kunnen uw e-mail stelen door het postvak in te stellen om automatisch e-mail door te sturen. Dit kan zelfs gebeuren zonder het bewustzijn van de gebruiker. U dit voorkomen door een e-mailstroomregel te configureren. 
  
Als u een regel voor e-mailtransport wilt maken, bekijkt u [deze korte video](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) of volgt u de volgende stappen:
  
1. Klik in het Microsoft 365-beheercentrum op **Beheercentra** \> **Exchange**.
    
2. Klik in de categorie **e-mailstroom** op **regels**.
    
3. Klik **+** op en klik vervolgens op Een nieuwe regel **maken**.
    
4. Klik onder aan het dialoogvenster op **Meer opties** om de volledige set opties weer te geven. 
    
5. Pas de instellingen toe in de volgende tabel. Laat de rest van de instellingen bij de standaardinstelling, tenzij u ze wilt wijzigen.
    
6. Klik op **Opslaan**.
    
|**Instelling**|**Gebruikers waarschuwen voordat u bijlagen van Office-bestanden opent**|
|:-----|:-----|
|Naam  <br/> |Automatisch doorsturen van e-mail naar externe domeinen voorkomen  <br/> |
|Pas deze regel toe als ...  <br/> |De afzender. . . is extern/intern . . . Binnen de organisatie  <br/> |
|Voorwaarde toevoegen  <br/> |De eigenschappen van het bericht . . . het berichttype op te nemen. . . Automatisch doorsturen  <br/> |
|Doe het volgende ...  <br/> |Blokkeer het bericht . . . het bericht te weigeren en een uitleg op te nemen.  <br/> |
|Berichttekst weergeven  <br/> |E-mail automatisch doorschakelen buiten deze organisatie wordt om veiligheidsredenen voorkomen.  <br/> |


## <a name="protect-your-email-from-phishing-attacks"></a>Bescherm uw e-mail tegen phishing-aanvallen

Als u een of meer aangepaste domeinen hebt geconfigureerd voor uw Office 365- of Microsoft 365-omgeving, u gerichte bescherming tegen phishing configureren. ATP-bescherming tegen phishing, onderdeel van Office 365 Advanced Threat Protection, kan uw organisatie beschermen tegen schadelijke imitatiegebaseerde phishing-aanvallen en andere phishing-aanvallen. Als u een aangepast domein nog niet hebt geconfigureerd, hoeft u dit niet te doen.
  
We raden u aan om aan de slag te gaan met deze bescherming door een beleid te maken om uw belangrijkste gebruikers en uw aangepaste domein te beschermen. 

Als u een ATP-antiphishingbeleid wilt maken, bekijkt [u deze korte trainingsvideo](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)of voert u de volgende stappen uit:
  
1. Ga naar [https://protection.office.com](https://protection.office.com). 
    
2. Kies beleid in het Security &amp; Compliance Center in het linkernavigatiedeelvenster onder **Bedreigingsbeheer**. **Policy**
    
3. Kies **op** de pagina Beleid de optie **ATP-anti-phishing**.
    
4. Selecteer **+ Maken**op de pagina **Anti-phishing** . Een wizard lanceert die u door het definiëren van uw anti-phishing beleid.
    
5. Geef de naam, beschrijving en instellingen voor uw beleid op zoals aanbevolen in de onderstaande grafiek. Zie Meer informatie [over atp-beleidsopties voor antiphishing.](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies) 
    
6. Nadat u uw instellingen hebt bekeken, kiest u **Dit beleid maken** of **Opslaan**, naar gelang van het geval.
    

|**Instellen of optie**<br/>|**Aanbevolen instelling** <br/>|
|:-----|:-----|
|Naam  <br/> |Domein en meest waardevolle campagnemedewerkers  <br/> |
|Beschrijving  <br/> |Zorg ervoor dat de belangrijkste medewerkers en ons domein niet worden nagebootst.  <br/> |
|Gebruikers toevoegen om te beschermen  <br/> |Selecteer **+ Een voorwaarde toevoegen, de ontvanger is**. Typ gebruikersnamen of voer het e-mailadres in van de kandidaat, campagnemanager en andere belangrijke medewerkers. U maximaal 20 interne en externe adressen toevoegen die u wilt beschermen tegen imitatie.  <br/> |
|Domeinen toevoegen om te beschermen  <br/> |Selecteer **+ Een voorwaarde toevoegen, het domein van de ontvanger is**. Voer het aangepaste domein in dat is gekoppeld aan uw Microsoft 365-abonnement als u er een hebt gedefinieerd. U meer dan één domein invoeren.  <br/> |
|Acties kiezen  <br/> |Als e-mail wordt verzonden door een geïmiteerde gebruiker: Kies **Bericht omleiden naar een ander e-mailadres**en typ het e-mailadres van de beveiligingsbeheerder; *Bijvoorbeeld Alice <span> <span> @contoso.com*.          Als e-mail wordt verzonden door een geïmiteerd domein: Kies **Quarantainebericht**.  <br/> |
|Postvakintelligentie  <br/> |Standaard wordt postvakinformatie geselecteerd wanneer u een nieuw antiphishingbeleid maakt. Laat deze instelling **aan** staan voor de beste resultaten.  <br/> |
|Vertrouwde afzenders en domeinen toevoegen  <br/> |Hier u uw eigen domein of andere vertrouwde domeinen toevoegen.  <br/> |
|Toegepast op  <br/> |Selecteer **Het geadresseerdedomein is**. Selecteer onder **Een van deze**opties de optie **Kiezen**. Selecteren **+ Toevoegen**. Schakel het selectievakje in naast de naam van het domein, bijvoorbeeld *contoso. <span> <span> com*, in de lijst en selecteer **Toevoegen**. Selecteer **Gereed**.  <br/> |
   
Zie Het [antiphishingbeleid van Office 365 ATP instellen](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)voor meer informatie .
  
## <a name="protect-against-malicious-attachments-files-and-links-with-advanced-threat-protection-atp"></a>Bescherm tegen schadelijke bijlagen, bestanden en koppelingen met Advanced Threat Protection (ATP)

![Banner die wijzen op https://aka.ms/aboutM365preview .](../media/m365admincenterchanging.png)

Zorg er eerst voor dat u in het beheercentrum de <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> nieuwe preview-versie van het beheercentrum hebt ingeschakeld. Schakel de schakelaar naast de tekst in **Het nieuwe beheercentrum**.

   ![De nieuwe preview van het beheercentrum op.](../media/previewon.png)

Als u de pagina **Setup** met kaarten in uw tenant nog niet ziet, raadpleegt u hoe u deze stappen uitvoeren in Security &amp; Compliance Center. Zie [Veilige ATP-bijlagen instellen in het Security & Compliance Center](#set-up-atp-safe-attachments-in-the-security--compliance-center) en [ATP Safe Links instellen in het Security & Compliance Center](#set-up-atp-safe-links-in-the-security--compliance-center).

1.  Kies **Setup**in het linkerv.
2. Kies **op** de pagina Setup **de** optie Weergave op de **bescherming verhoog de bedreigingen.**</br></br>
    ![Kies Weergave op de bescherming verhoog tegen geavanceerde bedreigingen.](../media/startatp.png) 

3. Kies op de pagina **Bescherming verhoog met geavanceerde bedreigingen** de optie Aan de **slag**.
4. Schakel in het deelvenster dat wordt geopend de selectievakjes in naast **Koppelingen en bijlagen in e-mail,** **Bestanden scannen in SharePoint, OneDrive en Teams en**De **koppelingen Scannen in Office-bureaublad- en Office Online-apps** onder **Items scannen op schadelijke inhoud**.

      - Typ **onder Koppelingen en bijlagen in e-mail**alle gebruikers of de specifieke gebruikers waarvan u de e-mail wilt scannen.

    ![Schakel alle selectievakjes in Beveiliging verhogen tegen geavanceerde bedreigingen in.](../media/setatp.png)
5. Kies **Beleid maken** om atp-veilige bijlagen en ATP-veilige koppelingen in te schakelen.

### <a name="set-up-atp-safe-attachments-in-the-security--compliance-center"></a>ATP-veilige bijlagen instellen in het Security & Compliance Center

Mensen verzenden, ontvangen en delen regelmatig bijlagen, zoals documenten, presentaties, spreadsheets en meer. Het is niet altijd gemakkelijk om te zien of een bijlage veilig of kwaadaardig is door alleen maar naar een e-mailbericht te kijken. Office 365 Advanced Threat Protection bevat atp-beveiliging voor veilige bevestiging, maar deze beveiliging is niet standaard ingeschakeld. We raden u aan een nieuwe regel te maken om deze beveiliging te gaan gebruiken. Deze beveiliging strekt zich uit tot bestanden in SharePoint, OneDrive en Microsoft Teams.
  
Als u een ATP-beleid voor veilige bijlagen wilt maken, bekijkt [u deze korte video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)of voert u de volgende stappen uit:
  
1. Ga naar [https://protection.office.com](https://protection.office.com) en meld je aan met je beheerdersaccount. 
    
2. Kies beleid in het Security &amp; Compliance Center in het linkernavigatiedeelvenster onder **Bedreigingsbeheer**. **Policy**
    
3. Kies op de pagina Beleid **de optie VEILIGE BIJLAGEN ATP**.
    
4. Pas deze beveiliging op de pagina Veilige bijlagen breed toe door het selectievakje **ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams in** te schakelen. 
    
5. Selecteer **+** om een nieuw beleid te maken. 
    
6. Pas de instellingen toe in de volgende tabel. 
    
7. Nadat u uw instellingen hebt gecontroleerd, kiest **u Dit beleid maken** of **Opslaan**, naar gelang van het geval.
    

|**Instellen of optie**|**Aanbevolen instelling** <br/>|
|:-----|:-----|
|Naam  <br/> |Blokkeer huidige en toekomstige e-mails met gedetecteerde malware.  <br/> |
|Beschrijving  <br/> |Blokkeer huidige en toekomstige e-mails en bijlagen met gedetecteerde malware.  <br/> |
|Bijlagen opslaan onbekende malware reactie  <br/> |Selecteer **Blokkeren - Blokkeer de huidige en toekomstige e-mails en bijlagen met gedetecteerde malware.**  <br/> |
|Bijlage omleiden bij detectie  <br/> |Omleiding inschakelen (selecteer dit vak) Voer het beheerdersaccount of een postvakinstelling in voor quarantaine.          Pas de bovenstaande selectie toe als er een keer een keer een fout optreedt voor malwarescannen voor bijlagen (selecteer dit vak).  <br/> |
|Toegepast op  <br/> |Het domein van de ontvanger is . . . selecteer uw domein.  <br/> |
   
Zie Het [antiphishingbeleid van Office 365 ATP instellen](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)voor meer informatie .
  
### <a name="set-up-atp-safe-links-in-the-security--compliance-center"></a>ATP Safe Links instellen in het Security & Compliance Center

Hackers verbergen soms kwaadaardige websites in links in e-mail of andere bestanden. Office 365 ATP Safe Links (ATP Safe Links), onderdeel van Office 365 Advanced Threat Protection, kan uw organisatie helpen beschermen door tijd-van-klikverificatie van webadressen (URL's) in e-mailberichten en Office-documenten te bieden. Bescherming wordt gedefinieerd via atp-beleid voor veilige koppelingen.
  
We raden u aan het volgende te doen:
  
- Wijzig het standaardbeleid om de beveiliging te verhogen.
    
- Voeg een nieuw beleid toe dat is gericht op alle ontvangers in uw domein.
    
Als u ATP Safe Links wilt instellen, bekijkt u [deze korte trainingsvideo](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)of voert u de volgende stappen uit:
  
1. Ga naar [https://protection.office.com](https://protection.office.com) en meld je aan met je beheerdersaccount. 
    
2. Kies beleid in het Security &amp; Compliance Center in het linkernavigatiedeelvenster onder **Bedreigingsbeheer**. **Policy**
    
3. Kies op de pagina Beleid **de optie VEILIGE VERBINDING MET ATP**.
    
Ga alstkader het standaardbeleid wijzigen:
  
1. Selecteer op de pagina Veilige koppelingen onder **Beleid dat van toepassing is op de hele organisatie**het **standaardbeleid.** 
    
2. Selecteer onder **Instellingen die van toepassing zijn op inhoud, behalve e-mail,** Microsoft **365-apps voor bedrijven, Office voor iOS en Android**.
    
3. Klik op **Opslaan**. 
    
Ga als een nieuw beleid maken dat is gericht op alle ontvangers in uw domein:
  
1. Klik op de pagina Veilige koppelingen onder **Beleid dat van toepassing is op de hele organisatie**om een nieuw beleid te **+** maken. 
    
2. Pas de instellingen toe die in de volgende tabel worden vermeld.
    
3. Klik op **Opslaan**. 

|**Instellen of optie**|**Aanbevolen instelling** <br/>|
|:-----|:-----|
|Naam  <br/> |Beleid voor veilige koppelingen voor alle ontvangers in het domein  <br/> |
|Selecteer de actie voor onbekende mogelijk schadelijke URL's in berichten  <br/> |Selecteer **Aan - URL's worden herschreven en gecontroleerd aan de hand van een lijst met bekende schadelijke koppelingen wanneer gebruikers op de link klikken.**  <br/> |
|Veilige bijlagen gebruiken om downloadbare inhoud te scannen  <br/> |Selecteer dit vak.  <br/> |
|Toegepast op  <br/> |Het domein van de ontvanger is . . . selecteer uw domein.  <br/> |
   
Zie veilige koppelingen met [Office 365 ATP](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409)voor meer informatie .
  
## <a name="turn-on-the-unified-audit-log"></a>Het unified auditlogboek inschakelen

Nadat u de zoekopdracht voor het controlelogboek in het Security &amp; Compliance Center hebt ingeschakeld, u de beheerder en andere gebruikersactiviteit in het logboek behouden en doorzoeken. 

U moet de rol Controlelogboeken in Exchange Online toegewezen krijgen om het zoeken naar controlelogboeken in of uit te schakelen in uw Microsoft 365-abonnement. Standaard wordt deze rol toegewezen aan de rolgroepen Compliance Management en Organisatiebeheer op de pagina Machtigingen in het Exchange-beheercentrum. Globale beheerders in Microsoft 365 zijn standaard lid van deze groep.

1. Als u de zoekopdracht voor het controlelogboek wilt inschakelen, gaat u naar het beheercentrum <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> bij en kiest u **Naleving** onder **Beheercentra** in het linkernavigatiesysteem. 
2. Kies op de **nalevingspagina van Microsoft 365** de optie **Meer resources**en **opent** vervolgens op de **Office 365-beveiligingscentrumkaart. &amp; **

    ![Kies Open op de beveiligingsauto's & compliance auto's.](../media/gotosecandcomp.png)
3. Kies zoeken op de pagina beveiliging en naleving **en** controleer vervolgens **het zoeken naar controlelogboeken**.
1. Kies boven aan de **zoekpagina controlelogboek** de optie **Controle inschakelen.**

Nadat de functie is ingeschakeld, u zoeken naar bestanden, mappen en veel activiteiten. Zie [zoeken in het controlelogboek voor](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)meer informatie.

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a>Instellingen voor anoniem delen voor SharePoint- en OneDrive-bestanden en -mappen af te stemmen

(wijzig de standaardverloop van anonieme koppelingen naar 14 dagen, wijzig het standaarddelingstype in 'Specifieke personen') Ga alst u de instellingen voor delen voor OneDrive en SharePoint wijzigen:
1. Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> en kies **SharePoint** onder **Beheercentra** in het linkernavigatiesysteem. 
2. Ga in het SharePoint-beheercentrum naar **Policies** \> **Beleidsdeling**.
3. Selecteer op de pagina **Delen** onder **Koppelingen voor bestanden en mappen** **specifieke personen**en selecteer onder Geavanceerde instellingen **voor koppelingen voor iedereen**de optie Deze **koppelingen moeten binnen deze vele dagen verlopen**en typ 14 (of een ander aantal dagen waartoe u de levensduur van de koppeling wilt beperken).

    ![Kies Specifieke personen en stel de vervaldatum van de koppeling in op 14 dagen.](../media/anyonelinks.png)

## <a name="activity-alerts"></a>Activiteitswaarschuwingen

U activiteitswaarschuwingen gebruiken om beheerders- en gebruikersactiviteiten bij te houden en malware- en gegevensverliespreventieincidenten in uw organisatie te detecteren. Uw abonnement bevat een set standaardbeleid, maar u ook aangepaste beleidsregels maken. Zie [waarschuwingsbeleid voor](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)meer informatie . Als u bijvoorbeeld een belangrijk bestand opslaat in SharePoint waarvan u niet wilt dat iemand extern deelt, u een melding maken die u waarschuwt als iemand het wel deelt.

In het volgende cijfer ziet u het standaardbeleid dat is opgenomen in Microsoft 365. <br/><br/>
    ![Standaardwaarschuwingsbeleid dat is opgenomen in Microsoft 365](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a>Het delen van agenda's uitschakelen of beheren

U voorkomen dat mensen in uw organisatie hun agenda's delen of u ook beheren wat ze kunnen delen. U het delen bijvoorbeeld beperken tot alleen vrije/drukke tijden.

1. Ga naar het beheercentrum <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> en kies **Instellingen** services \> **& invoegtoepassingen**.
2. Kies agenda's op de pagina **Services & invoegtoepassingen** en kies of mensen in uw organisatie hun agenda's kunnen delen met mensen buiten die Office 365 of Exchange hebben of met iemand. **Calendar** 
    Als u de optie delen met iemand kiest, u besluiten om ook alleen gratis/drukke informatie te delen.

3. Kies **Wijzigingen opslaan** onder aan de pagina.

    In de volgende afbeelding wordt weergegeven dat het delen van agenda's niet is toegestaan. </br></br>
    ![Schermafbeelding van het weergeven van extern delen van agenda's als niet toegestaan.](../media/nocalendarsharing.png)

    De volgende afbeelding toont de instellingen wanneer het delen van agenda is toegestaan met een e-maillink met alleen gratis/drukke informatie.

   ![Schermafbeelding van agendavrij/druk delen met iedereen.](../media/sharefreebusy.png)

Als uw gebruikers hun agenda's mogen delen, raadpleegt u [deze instructies](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) voor delen in de webversie van Outlook.
