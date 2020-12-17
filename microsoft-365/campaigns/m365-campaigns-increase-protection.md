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
description: Hulp bij het verhogen van het beschermingsniveau in Microsoft 365
ms.openlocfilehash: 2078f9b40f6f556b2aacee28d6ff3c25be90fcc4
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698449"
---
# <a name="increase-threat-protection-for-microsoft-365-subscription"></a>Bedreigingsbeveiliging voor Microsoft 365-abonnement verhogen

Dit artikel helpt u bij het verbeteren van de bescherming van uw Microsoft 365-abonnement om te beschermen tegen phishing, malware en andere bedreigingen. Deze aanbevelingen zijn geschikt voor organisaties met een betere beveiliging, zoals politieke campagnes, Law oren en gezondheidszorg.

Voordat u begint, controleert u de Secure Score van Microsoft. Secure Score van Microsoft: Hiermee wordt de beveiliging van uw organisatie geanalyseerd op basis van uw regelmatige activiteiten en beveiligingsinstellingen, en wordt een score toegewezen. Begin met het noteren van uw huidige score. Als u de acties in dit artikel uitvoert, wordt uw score verhoogd. Het doel is niet de maximum score te bereiken, maar om rekening te houden met verkoopkansen om uw omgeving te beschermen en de productiviteit van uw gebruikers niet negatief beïnvloeden.

Zie [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)voor meer informatie.

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Het beschermingsniveau voor malware in e-mail verhogen

Uw Office 365-of Microsoft 365-omgeving bevat bescherming tegen malware, maar u kunt deze beveiliging vergroten door bijlagen te blokkeren met bestandstypen die meestal voor malware worden gebruikt. De bescherming van malware tegenkomt in e-mail:

1. Ga naar <https://protection.office.com> en meld u aan met de referenties van uw beheerdersaccount.

2. Kies in het gedeelte beveiligings & compliance in het linker navigatiedeelvenster onder **Threat Management** de optie **beleids** \> **anti malware**.

3. Dubbelklik op het standaardbeleid om dit beleid voor het hele bedrijf te bewerken.

4. Klik op **Instellingen**.

5. Selecteer **aan** onder **common Attachment types filter**. De geblokkeerde bestandstypen worden weergegeven in het venster direct onder dit besturingselement. Zorg ervoor dat u deze bestandstypes toevoegt:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   U kunt later, indien nodig, bestandstypen toevoegen of verwijderen.

6. Selecteer **opslaan.**

Zie [bescherming tegen malware in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection)voor meer informatie.

## <a name="protect-against-ransomware"></a>Beveiligen tegen ransomware

Ransomware beperkt de toegang tot gegevens door het versleutelen van bestanden of het vergrendelen van computerschermen. Vervolgens probeert u te extort van de slachtoffers door te vragen om ' Ransom ', meestal in de vorm van cryptocurrencies zoals Bitcoin, in Exchange voor toegang tot gegevens.

U kunt zich beschermen tegen Ransomware door een of meer e-mail stroom regels te maken voor het blokkeren van bestandsextensies die vaak worden gebruikt voor Ransomware (ze zijn toegevoegd aan het [niveau van de bescherming tegen malware in een e-mail](#raise-the-level-of-protection-against-malware-in-mail) stap), of om gebruikers te waarschuwen die deze bijlagen in een e-mail ontvangen.

Naast de bestanden die u in de vorige stap hebt geblokkeerd, is het ook verstandig om een regel te maken om gebruikers te waarschuwen voordat ze Office-bestandsbijlagen openen die macro's bevatten. Ransomware kan niet in macro's worden verborgen, dus waarschuwt gebruikers deze bestanden niet te openen van personen die ze niet kennen.

Een e-mail transportregel maken:

1. Ga naar het Beheercentrum op <https://admin.microsoft.com> en kies **beheer centra** \> **Exchange**.

2. Klik in de categorie **mail flow** op **regels**.

3. Klik op **+** en klik vervolgens op **een nieuwe regel maken**.

4. Klik op **meer opties** onder aan het dialoogvenster om de volledige set met opties weer te geven.

5. De instellingen in de onderstaande tabel voor de regel toepassen. Laat de rest van de instellingen op de standaardinstelling, tenzij u deze wilt wijzigen.

6. Klik op **Opslaan**.

|Instelling|Gebruikers waarschuwen voordat bijlagen van Office-bestanden worden geopend|
|---|---|
|Naam|Regel voor een anti-Ransomware-regel: gebruikers waarschuwen|
|Pas deze regel toe. . .|Een bijlage. . . komt overeen met bestandsextensies. . .|
|Woorden of zinsdelen opgeven|Dit soort bestanden toevoegen: <br/> `dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm`|
|Ga als volgt te werk. . .|De geadresseerde informeren met een bericht|
|Berichttekst geven|Open deze typen bestanden niet van personen die u niet kent, omdat ze macro's kunnen bevatten met schadelijke code.|

Zie voor meer informatie:

- [Ransomware: Risico's verminderen](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Uw OneDrive herstellen](https://support.microsoft.com//office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="stop-auto-forwarding-for-email"></a>Automatisch doorsturen van e-mail stoppen

Hackers die toegang krijgen tot het postvak van een gebruiker kunnen uw e-mail stelen door het postvak in te stellen op het automatisch doorsturen van e-mail. Dit kan zelfs zonder de aandacht van de gebruiker. U kunt dit voorkomen door een e-mail stroom regel te configureren.

Voor het maken van een transportregel kunt u [deze korte video](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) bekijken of volgt u deze stappen:

1. Klik in het Microsoft 365-Beheercentrum op Exchange **Centers** \> **Exchange**.

2. Klik in de categorie **mail flow** op **regels**.

3. Klik op **+** en klik vervolgens op **een nieuwe regel maken**.

4. Klik op **meer opties** onder aan het dialoogvenster om de volledige set met opties weer te geven.

5. De instellingen in de onderstaande tabel toepassen. Laat de rest van de instellingen op de standaardinstelling, tenzij u deze wilt wijzigen.

6. Klik op **Opslaan**.

|Instelling|Gebruikers waarschuwen voordat bijlagen van Office-bestanden worden geopend|
|---|---|
|Naam|Voorkom automatisch doorsturen van e-mail naar externe domeinen|
|Deze regel toepassen als...|De afzender. . . is extern/intern. . . Binnen de organisatie|
|Voorwaarde toevoegen|De berichteigenschappen. . . het berichttype opnemen. . . Automatisch doorsturen|
|Voer een van de volgende handelingen uit...|Het bericht blokkeren. . . u ziet het bericht af en voegt een uitleg toe.|
|Berichttekst geven|Het automatisch doorsturen van e-mail buiten deze organisatie kan beveiligingsredenen voorkomen.|

## <a name="protect-your-email-from-phishing-attacks"></a>Uw e-mail beschermen tegen phishing-aanvallen

Als u een of meer aangepaste domeinen hebt geconfigureerd voor uw Office 365-of Microsoft 365-omgeving, kunt u de gerichte bescherming tegen phishing instellen. Bescherming tegen phishing, Microsoft Defender for Office 365, kan u helpen uw organisatie te beschermen tegen kwaadaardige aanvallen op basis van kwaadaardige aanvallen en andere phishing. U hoeft dit niet te doen als u geen aangepast domein hebt geconfigureerd.

U wordt geadviseerd om aan de slag te gaan met deze bescherming door een beleid te maken voor de bescherming van de belangrijkste gebruikers en uw aangepaste domein.

Als u een anti-phishingfilter wilt maken in Defender voor Office 365, bekijkt u [deze korte trainings video](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)of voert u de volgende stappen uit:

1. Ga naar <https://protection.office.com>.

2. Kies in het gedeelte beveiligings & compliance in het linker navigatiedeelvenster onder **Threat Management** de optie **beleid**.

3. Kies op de pagina **beleid** de optie **anti phishing**.

4. Selecteer **+ maken** op de pagina **anti phishing** . Met een wizard wordt u stapsgewijs begeleid bij het definiëren van uw anti phishing-beleid.

5. Geef de naam, de beschrijving en de instellingen op voor het beleid zoals aanbevolen in de onderstaande tabel. Zie voor meer informatie het artikel [over anti phishingfilter in de opties voor Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).

6. Wanneer u de instellingen hebt gecontroleerd, kiest u **dit beleid maken** of **Opslaan**.

|Instelling of optie|Aanbevolen instelling|
|---|---|
|Naam|Domein en meeste waardevolle campagne medewerkers|
|Beschrijving|Zorg ervoor dat het belangrijkste personeel en ons domein niet worden nagebootst.|
|Gebruikers toevoegen om te beschermen|Selecteer **+ een voorwaarde toevoegen, de ontvanger is**. Typ gebruikersnamen of voer het e-mailadres in van de kandidaat, campagne manager en andere belangrijke personeelsleden. U kunt maximaal 20 interne en externe adressen toevoegen die u wilt beveiligen tegen imitatie.|
|Domeinen toevoegen die u wilt beveiligen|Selecteer **+ een voorwaarde toevoegen, het domein van de ontvanger is**. Voer het aangepaste domein in dat is gekoppeld aan uw Microsoft 365-abonnement als u er een hebt gedefinieerd. U kunt meer dan één domein opgeven.|
|Acties kiezen|Als e-mail wordt verzonden door een geïmiteerde gebruiker: Kies **Bericht omleiden naar een ander e-mailadres** en typ vervolgens het e-mailadres van de beveiligingsbeheerder. bijvoorbeeld *Alice <span> <span> @contoso. com*. <br/> Als e-mail wordt verzonden door een geïmiteerd domein: Kies **quarantaine bericht**.|
|Postvak intelligentie|Standaard is postvak intelligentie geselecteerd wanneer u een nieuw anti-phishings beleid maakt. Voor de beste resultaten hoeft u **deze instelling niet** te selecteren.|
|Vertrouwde afzenders en domeinen toevoegen|U kunt hier uw eigen domein of een ander vertrouwd domein toevoegen.|
|Toegepast op|Selecteer **het domein van de ontvanger**. Selecteer **kiezen** onder **een van deze** opties. Selecteer **+ toevoegen**. Schakel het selectievakje in naast de naam van het domein, bijvoorbeeld *contoso. <span> <span> com*, in de lijst en selecteer vervolgens **toevoegen**. Selecteer **Gereed**.|

Zie [anti phishingfilter instellen in de Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)voor meer informatie.

## <a name="protect-against-malicious-attachments-files-and-links-with-defender-for-office-365"></a>Beveiligings bescherming tegen kwaadaardige bijlagen, bestanden en koppelingen met Defender voor Office 365

![Banner waarnaar wordt verwezen https://aka.ms/aboutM365preview .](../media/m365admincenterchanging.png)

Zorg er eerst voor dat in het Beheercentrum <https://admin.microsoft.com> de preview-versie van het nieuwe Beheercentrum is ingeschakeld. Zet de wisselknop naast de tekst in **het nieuwe Beheercentrum**.

   ![De nieuwe preview-versie van het Beheercentrum.](../media/previewon.png)

Als u de **instellings** pagina nog niet ziet met kaarten in uw Tenant, raadpleegt u de stappen uitvoeren in beveiliging & compliance Center. Zie [voor informatie over het instellen van veilige bijlagen in het beveiligings & nalevings centrum](#set-up-safe-attachments-in-the-security--compliance-center) en [veilige koppelingen instellen in het beveiligings & nalevings centrum](#set-up-safe-links-in-the-security--compliance-center).

1. Kies in het linkernavigatievenster de optie **instellen**.
2. Kies op de pagina **instellingen** de optie **weergeven** op de kaart **meer beveiliging van de geavanceerde bedreiging** .

   ![Kies weergeven bij een grotere bescherming tegen geavanceerde bedreigingen.](../media/startatp.png)

3. Kies aan de **slag** op de pagina **meer bescherming tegen geavanceerde bedreigingen** .
4. Selecteer in het deelvenster dat wordt geopend, de selectievakjes naast **koppelingen en bijlagen in e-mail**, **Scan bestanden in SharePoint, OneDrive en teams**, en **Scan koppelingen in Office-bureaublad en Office Online-apps** onder **items voor schadelijke inhoud scannen**.

   Typ onder **koppelingen en bijlagen bij e-mail** de tekst alle gebruikers of de specifieke gebruikers van wie u het e-mailbericht wilt scannen.

   ![Schakel alle selectievakjes in voor een grotere bescherming tegen geavanceerde bedreigingen.](../media/setatp.png)

5. Kies **beleid maken** om veilige bijlagen en veilige koppelingen in te schakelen.

### <a name="set-up-safe-attachments-in-the-security--compliance-center"></a>Veilige bijlagen instellen in het beveiligings & nalevings centrum

Mensen verzenden, ontvangen en delen van bijlagen, zoals documenten, presentaties, spreadsheets en meer. Het is niet altijd eenvoudig om te zien of een bijlage veilig of schadelijk is, net zoals u een e-mailbericht bekijkt. Microsoft Defender voor Office 365 bevat veilige bijlagebeveiliging, maar deze bescherming is niet standaard ingeschakeld. U wordt geadviseerd om een nieuwe regel te maken om deze beveiliging te gaan gebruiken. Deze bescherming breidt zich uit naar bestanden in SharePoint, OneDrive en Microsoft teams.

Voor het maken van een veilig bijlage beleid bekijkt u [deze korte video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)of voert u de volgende stappen uit:

1. Ga naar <https://protection.office.com> en meld u aan met uw beheerdersaccount.

2. Kies in het gedeelte beveiligings & compliance in het linker navigatiedeelvenster onder **Threat Management** de optie **beleid**.

3. Kies op de pagina beleid de optie **veilige bijlagen**.

4. Op de pagina veilige bijlagen past u deze beveiliging algemeen toe door het selectievakje **ATP voor SharePoint, OneDrive en Microsoft teams inschakelen** in te schakelen.

5. Selecteer **+** om een nieuw beleid te maken.

6. De instellingen in de onderstaande tabel toepassen.

7. Wanneer u de instellingen hebt gecontroleerd, kiest u **dit beleid maken** of **Opslaan**.

|Instelling of optie|Aanbevolen instelling|
|---|---|
|Naam|Huidige en toekomstige e-mails blokkeren met gedetecteerde malware.|
|Beschrijving|Huidige en toekomstige e-mailberichten en bijlagen blokkeren met gedetecteerde malware.|
|Bijlagen opslaan, onbekende malware van malware|Selecteer **blokkeren de huidige en toekomstige e-mailberichten en bijlagen blokkeren met gedetecteerde malware**.|
|Bijlage omleiden bij detectie|Omleiding inschakelen (Selecteer dit vak) <br/> Voer het beheerdersaccount of postvak in voor quarantaine. <br/> De bovenstaande selectie toepassen als de malware wordt gescand op bijlagen wanneer een fout is opgetreden of als er een fout optreedt (Selecteer dit vak).|
|Toegepast op|Het domein van de ontvanger is. . . Selecteer uw domein.|

Zie [anti phishingfilter instellen in de Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)voor meer informatie.

### <a name="set-up-safe-links-in-the-security--compliance-center"></a>Veilige koppelingen instellen in het beveiligings & nalevings centrum

Hackers verbergen soms schadelijke websites via e-mailberichten of andere bestanden. Met behulp van veilige koppelingen, Microsoft Defender voor Office 365, kunt u uw organisatie beschermen door geklikt verificatie van webadressen (url's) te verstrekken aan e-mailberichten en Office-documenten. Beveiliging wordt bepaald door beleid voor veilige koppelingen.

U wordt aangeraden het volgende te doen:

- Wijzig het standaardbeleid om de beveiliging te verbeteren.

- Een nieuwe beleidsregel toevoegen die is bedoeld voor alle geadresseerden in uw domein.

Voor het instellen van veilige koppelingen bekijkt u [deze korte trainings video](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)of voert u de volgende stappen uit:

1. Ga naar <https://protection.office.com> en meld u aan met uw beheerdersaccount.

2. Kies in het gedeelte beveiligings & compliance in het linker navigatiedeelvenster onder **Threat Management** de optie **beleid**.

3. Kies op de pagina beleid de optie **veilige koppelingen**.

Het standaardbeleid wijzigen:

1. Selecteer op de pagina veilige koppelingen onder **beleidsregels die van toepassing zijn op de hele organisatie** het **standaard** beleid.

2. Selecteer onder **instellingen die van toepassing zijn op inhoud met uitzondering van e-mail de** optie **Microsoft 365-apps voor Enterprise, Office voor IOS en Android**.

3. Klik op **Opslaan**.

Een nieuwe beleidsregel maken voor alle geadresseerden in uw domein:

1. Klik op de pagina veilige koppelingen onder **beleidsregels die op de hele organisatie van toepassing zijn**, **+** om een nieuw beleid te maken.

2. De instellingen in de volgende tabel toepassen.

3. Klik op **Opslaan**.

|Instelling of optie|Aanbevolen instelling|
|---|---|
|Naam|Beleid voor veilige koppelingen voor alle geadresseerden in het domein|
|Selecteer de actie voor onbekende, mogelijk schadelijke Url's in berichten|Selecteer **on-url's worden herschreven en gecontroleerd tegen een lijst met bekende kwaadaardige koppelingen wanneer de gebruiker klikt op de koppeling**.|
|Veilige bijlagen gebruiken om downloadbare inhoud te scannen|Schakel dit selectievakje in.|
|Toegepast op|Het domein van de ontvanger is. . . Selecteer uw domein.|

Zie voor meer informatie [veilige koppelingen in Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links).

## <a name="turn-on-the-unified-audit-log"></a>Het Unified audit logboek inschakelen

Nadat u de zoekopdracht in het auditlogboek in de beveiligings & compliance hebt ingeschakeld, kunt u de beheerder en andere gebruikersactiviteit in het logboek bewaren en de zoekfunctie in het logboek doorzoeken.

U moet de rol Auditlogboeken in Exchange Online hebben als u de zoekfunctie voor auditlogboeken wilt in-of uitschakelen in uw Microsoft 365-abonnement. Deze functie wordt standaard toegewezen aan de rollen groepen Compliance Management en Organisatiebeheer op de pagina machtigingen in het Exchange-Beheercentrum. Globale beheerders in Microsoft 365 zijn standaard lid van deze groep.

1. Als u de zoekopdracht in het auditlogboek wilt inschakelen, gaat u naar het Beheercentrum op <https://admin.microsoft.com> en kiest u vervolgens **beveiliging** onder **beheer centra** in het navigatiemenu aan de linkerkant.
2. Op de pagina **Microsoft 365-beveiliging** kiest u **meer bronnen** en **opent** u vervolgens de kaart **Office 365-beveiliging & compliance Center** .

    ![Kies openen in het & voor de naleving van de beschermings auto's.](../media/gotosecandcomp.png)
3. Kies op de pagina beveiliging en compliance de optie **Search** en vervolgens **audit log Search**.
4. Kies op de bovenkant van de pagina zoeken in het **audit logboek** de optie **controle inschakelen**.

Nadat de functie is ingeschakeld, kunt u zoeken naar bestanden, mappen en veel activiteiten. Zie [Zoeken in het auditlogboek](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)voor meer informatie.

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a>Instellingen voor anonieme delen voor SharePoint-en OneDrive-bestanden en-mappen optimaliseren

(de standaardinstelling voor anonieme koppelingen wijzigen naar 14 dagen, standaardtype delen wijzigen in ' specifieke personen ') U wijzigt als volgt de instellingen voordelen in OneDrive en SharePoint:

1. Ga naar het Beheercentrum <https://admin.microsoft.com> en kies vervolgens **SharePoint** onder **admin Centers** in het navigatiemenu aan de linkerkant.
2. Ga in het SharePoint-Beheercentrum naar **beleid** \> **delen**.
3. Selecteer op de pagina voor **delen** onder **koppelingen naar bestanden en mappen** de optie **specifieke personen** en selecteer onder **Geavanceerde instellingen voor ' iedereen '** de optie **deze koppelingen moeten binnen het volgende aantal dagen verlopen** en typ in 14 (of een ander aantal dagen waarvoor u de levensduur van de verbinding wilt beperken).

   ![Kies specifieke personen en stel de einddatum van de koppeling in op 14 dagen.](../media/anyonelinks.png)

## <a name="activity-alerts"></a>Waarschuwingen voor activiteiten

U kunt met activiteiten waarschuwingen beheerders en gebruikersactiviteiten bijhouden en malware en preventie van gegevensverlies detecteren in uw organisatie. Uw abonnement bevat een set standaardbeleid, maar u kunt ook aangepaste sjablonen maken. Zie [waarschuwings beleid](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)voor meer informatie. Als u bijvoorbeeld een belangrijk bestand opslaat in SharePoint en u niet wilt dat iedereen extern kan delen, kunt u een melding maken waarmee u wordt gewaarschuwd als iemand de afbeelding deelt.

In de volgende afbeelding ziet u het standaardbeleid dat is opgenomen in Microsoft 365.

![Standaard waarschuwings beleidsregels in Microsoft 365](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a>Het delen van agenda's uitschakelen of beheren

U kunt voorkomen dat personen in uw organisatie hun agenda delen of u kunt ook beheren wat ze kunnen delen. U kunt bijvoorbeeld instellen dat alleen beschikbaarheidsinfo mag worden gedeeld.

1. Ga naar het Beheercentrum op <https://admin.microsoft.com> en kies **instellingen** \> **organisatie-instellingen**.
2. Op de pagina **Services** kiest u **agenda** en kiest u of personen in uw organisatie hun agenda kunnen delen met personen buiten de organisatie van Office 365 of Exchange, of met iedereen.

   Als u de optie delen met iedereen kiest, kunt u ook de beschikbaarheidsinfo delen.

3. Kies **wijzigingen opslaan** onder aan de pagina.

   In de volgende afbeelding ziet u dat het delen van de agenda niet is toegestaan.

   ![Schermafbeelding van het weergeven van externe agenda delen als niet toegestaan.](../media/nocalendarsharing.png)

   In de volgende afbeelding ziet u de instellingen wanneer het delen van de agenda wordt toegestaan met een e-mailkoppeling met alleen beschikbaarheidsinfo.

   ![Schermafbeelding van beschikbaarheidsinfo met anderen delen.](../media/sharefreebusy.png)

Als uw gebruikers hun agenda mogen delen, raadpleegt u [deze instructies](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) voor het delen vanuit de webversie van Outlook.
