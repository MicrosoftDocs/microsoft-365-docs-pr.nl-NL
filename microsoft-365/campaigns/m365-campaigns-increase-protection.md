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
description: Hulp bij het verhogen van het beveiligingsniveau in Microsoft 365
ms.openlocfilehash: 61ac32d3debe391794e85df8c129e5df72887e9e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198373"
---
# <a name="increase-threat-protection-for-microsoft-365-subscription"></a>Bedreigingsbeveiliging voor Microsoft 365-abonnement verhogen

In dit artikel kunt u de beveiliging in uw Microsoft 365-abonnement vergroten om te beschermen tegen phishing, malware en andere bedreigingen. Deze aanbevelingen zijn geschikt voor organisaties die meer behoefte hebben aan beveiliging, zoals politieke campagnes, advocatenkantoren en klinieken in de gezondheidszorg.

Controleer voordat u begint uw Microsoft Secure Score. Microsoft Secure Score analyseert de beveiliging van uw organisatie op basis van uw reguliere activiteiten en beveiligingsinstellingen en wijst een score toe. Begin met het noteren van uw huidige score. Als u de acties onderneemt die in dit artikel worden aanbevolen, wordt uw score verhoogd. Het doel is niet om de maximale score te behalen, maar om rekening te houden met de mogelijkheden om uw omgeving te beschermen die de productiviteit van uw gebruikers niet negatief beïnvloeden.

Zie Microsoft Secure Score voor [meer informatie.](../security/defender/microsoft-secure-score.md)

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Het niveau van beveiliging tegen malware in e-mail verhogen

Uw Office 365- of Microsoft 365-omgeving bevat bescherming tegen malware, maar u kunt deze beveiliging verhogen door bijlagen te blokkeren met bestandstypen die vaak voor malware worden gebruikt. Malwarebeveiliging in e-mail tegen gaan:

1. Ga naar <https://protection.office.com> en meld u aan met uw beheerdersaccountreferenties.

2. Kies in het & compliancecentrum in het linkernavigatiedeelvenster onder Bedreigingsbeheer **de** optie **Beleid** \> **tegen malware.**

3. Dubbelklik op het standaardbeleid om dit beleid voor het hele bedrijf te bewerken.

4. Klik op **Instellingen**.

5. Selecteer **onder Gemeenschappelijke bijlagetypenfilter** de optie **Op**. De geblokkeerde bestandstypen worden weergegeven in het venster direct onder dit besturingselement. Zorg ervoor dat u deze bestandstypen toevoegt:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   U kunt later, indien nodig, bestandstypen toevoegen of verwijderen.

6. Klik **op Opslaan.**

Zie Bescherming tegen [malware in EOP voor meer informatie.](../security/office-365-security/anti-malware-protection.md)

## <a name="protect-against-ransomware"></a>Beveiligen tegen ransomware

Ransomware beperkt de toegang tot gegevens door bestanden te versleutelen of computerschermen te vergrendelen. Vervolgens wordt geprobeerd geld af te persen van de slachtoffers door om 'los geld' te vragen, meestal in de vorm van cryptovaluta zoals Bitcoin, in ruil voor toegang tot gegevens.

U kunt u beschermen tegen ransomware door een of meer regels voor de e-mailstroom te maken om bestandsextensies te blokkeren die vaak voor ransomware worden gebruikt (deze zijn toegevoegd in het verhogen van het beschermingsniveau tegen malware in de [e-mailstap) of](#raise-the-level-of-protection-against-malware-in-mail) om gebruikers te waarschuwen die deze bijlagen per e-mail ontvangen.

Naast de bestanden die u in de vorige stap hebt geblokkeerd, is het ook een goede gewoonte om een regel te maken om gebruikers te waarschuwen voordat ze Office-bestandsbijlagen openen die macro's bevatten. Ransomware kan worden verborgen in macro's, dus waarschuw gebruikers om deze bestanden niet te openen van mensen die ze niet kennen.

Een regel voor e-mailtransport maken:

1. Ga naar het beheercentrum bij <https://admin.microsoft.com> en kies **Beheercentra** \> **Exchange**.

2. Klik in **de categorie E-mailstroom** op **regels.**

3. Klik **+** op en klik vervolgens op Een nieuwe regel **maken.**

4. Klik **onder aan** het dialoogvenster op Meer opties om de volledige set opties weer te geven.

5. Pas de instellingen in de volgende tabel voor de regel toe. Laat de overige instellingen standaard staan, tenzij u ze wilt wijzigen.

6. Klik op **Opslaan**.

|Instelling|Gebruikers waarschuwen voordat ze bijlagen van Office-bestanden openen|
|---|---|
|Naam|Anti-ransomwareregel: gebruikers waarschuwen|
|Pas deze regel toe als . . .|Elke bijlage . . . bestandsextensie komt overeen. . .|
|Woorden of woordgroepen opgeven|Voeg deze bestandstypen toe: <br/> `dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm`|
|Ga als volgt te werk. . .|De geadresseerde op de hoogte stellen met een bericht|
|Berichttekst verstrekken|Open dit type bestanden niet van personen die u niet kent, omdat ze mogelijk macro's met schadelijke code bevatten.|

Zie voor meer informatie:

- [Ransomware: risico's beperken](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Uw OneDrive herstellen](https://support.microsoft.com//office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="stop-auto-forwarding-for-email"></a>Automatisch doorsturen voor e-mail stoppen

Hackers die toegang krijgen tot het postvak van een gebruiker, kunnen uw e-mail stelen door het postvak in te stellen om e-mail automatisch door te sturen. Dit kan zelfs gebeuren zonder dat de gebruiker dit weet. U kunt dit voorkomen door een e-mailstroomregel te configureren.

Als u een regel voor e-mailtransport wilt maken, [bekijkt](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) u deze korte video of volgt u de volgende stappen:

1. Klik in het Microsoft 365-beheercentrum op **Beheercentra** \> **Exchange**.

2. Klik in **de categorie E-mailstroom** op **regels.**

3. Klik **+** op en klik vervolgens op Een nieuwe regel **maken.**

4. Klik **onder aan** het dialoogvenster op Meer opties om de volledige set opties weer te geven.

5. Pas de instellingen in de volgende tabel toe. Laat de overige instellingen standaard staan, tenzij u ze wilt wijzigen.

6. Klik op **Opslaan**.

|Instelling|Gebruikers waarschuwen voordat ze bijlagen van Office-bestanden openen|
|---|---|
|Naam|Voorkomen dat e-mail automatisch wordt doorgestuurd naar externe domeinen|
|Pas deze regel toe als ...|De afzender . . . is extern/intern. . . Binnen de organisatie|
|Voorwaarde toevoegen|De berichteigenschappen . . . het berichttype opnemen. . . Automatisch doorsturen|
|Ga als volgt te werk ...|Blokkeer het bericht . . . het bericht weigeren en een uitleg opnemen.|
|Berichttekst verstrekken|Het automatisch doorsturen van e-mail buiten deze organisatie wordt om beveiligingsredenen voorkomen.|

## <a name="protect-your-email-from-phishing-attacks"></a>Uw e-mail beschermen tegen phishingaanvallen

Als u een of meer aangepaste domeinen hebt geconfigureerd voor uw Office 365- of Microsoft 365-omgeving, kunt u gerichte bescherming tegen phishing configureren. Anti-phishingbeveiliging, onderdeel van Microsoft Defender voor Office 365, kan uw organisatie helpen beschermen tegen kwaadwillende phishingaanvallen en andere phishingaanvallen. Als u een aangepast domein niet hebt geconfigureerd, hoeft u dit niet te doen.

We raden u aan aan de slag te gaan met deze beveiliging door een beleid te maken om uw belangrijkste gebruikers en uw aangepaste domein te beschermen.

Als u een anti-phishingbeleid wilt maken in Defender voor Office 365, bekijkt u deze korte [trainingsvideo](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)of volgt u de volgende stappen:

1. Ga naar <https://protection.office.com>.

2. Kies in het & compliancecentrum in het linkernavigatiedeelvenster onder **Bedreigingsbeheer** de optie **Beleid.**

3. Kies op **de** pagina Beleid de optie **Anti-phishing**.

4. Selecteer op **de pagina Anti-phishing** **+ Maken.** Er wordt een wizard gelanceerd om uw anti-phishingbeleid te definiëren.

5. Geef de naam, beschrijving en instellingen voor uw beleid op zoals aanbevolen in de onderstaande grafiek. Zie Meer informatie over [anti-phishingbeleid in Opties voor Microsoft Defender voor Office 365](../security/office-365-security/set-up-anti-phishing-policies.md)voor meer informatie.

6. Nadat u de instellingen hebt gecontroleerd, kiest u **Dit beleid maken** of **Opslaan,** naar eigen goed.

|Instelling of optie|Aanbevolen instelling|
|---|---|
|Naam|Domein en meest waardevolle medewerkers|
|Beschrijving|Zorg ervoor dat het belangrijkste personeel en ons domein niet worden nagebootst.|
|Gebruikers toevoegen om ze te beveiligen|Selecteer **+ Een voorwaarde toevoegen, De ontvanger is**. Typ gebruikersnamen of voer het e-mailadres in van de eigenaren, partners of kandidaten, managers en andere belangrijke personeelsleden. U kunt maximaal 20 interne en externe adressen toevoegen die u wilt beschermen tegen imitatie.|
|Domeinen toevoegen om te beveiligen|Selecteer **+ Een voorwaarde toevoegen, Het domein van de geadresseerde is**. Voer het aangepaste domein in dat is gekoppeld aan uw Microsoft 365-abonnement, als u er een hebt gedefinieerd. U kunt meer dan één domein invoeren.|
|Acties kiezen|Als e-mail wordt verzonden door een nagebootste gebruiker: Kies **Bericht omleiden** naar een ander e-mailadres en typ vervolgens het e-mailadres van de beveiligingsbeheerder; bijvoorbeeld: *<span> <span> Els @contoso.com.* <br/> Als e-mail wordt verzonden door een nagebootsd domein: Kies **Quarantainebericht.**|
|Postvakintelligentie|Standaard is postvakinformatie geselecteerd wanneer u een nieuw anti-phishingbeleid maakt. Laat deze instelling **aan voor** de beste resultaten.|
|Vertrouwde afzenders en domeinen toevoegen|Hier kunt u uw eigen domein of andere vertrouwde domeinen toevoegen.|
|Toegepast op|Selecteer **Het domein van de geadresseerde is**. Selecteer **onder Een van deze** opties de optie **Kiezen**. Selecteer **+ Toevoegen.** Schakel het selectievakje in naast de naam van het domein, bijvoorbeeld *contoso. <span> <span> com*, in de lijst en selecteer vervolgens **Toevoegen**. Selecteer **Gereed**.|

Zie [Anti-phishingbeleid instellen in Defender voor Office 365](../security/office-365-security/set-up-anti-phishing-policies.md)voor meer informatie.

## <a name="protect-against-malicious-attachments-files-and-links-with-defender-for-office-365"></a>Beschermen tegen schadelijke bijlagen, bestanden en koppelingen met Defender voor Office 365

![Banner die naar https://aka.ms/aboutM365preview .](../media/m365admincenterchanging.png)

Zorg er eerst voor dat in het beheercentrum het nieuwe voorbeeld van het <https://admin.microsoft.com> beheercentrum is ingeschakeld. Schakel de schakelknop in naast de tekst **Het nieuwe beheercentrum.**

   ![De preview van het nieuwe beheercentrum op.](../media/previewon.png)

Als u de pagina  Setup nog niet ziet met kaarten in uw tenant, bekijkt u hoe u deze stappen kunt voltooien in & Compliancecentrum. Zie Veilige bijlagen instellen in het [beveiligings-](#set-up-safe-attachments-in-the-security--compliance-center) & compliancecentrum en Veilige koppelingen instellen in het beveiligings- [& compliancecentrum.](#set-up-safe-links-in-the-security--compliance-center)

1. Kies in het linkernavigatienavigatiebalkje **Setup**.
2. Kies op **de** pagina Setup **de** optie Weergeven op de kaart Beveiliging tegen **geavanceerde bedreigingen** verhogen.

   ![Kies Beeld op de optie Beveiliging tegen geavanceerde bedreigingen vergroten.](../media/startatp.png)

3. Kies op **de pagina Beveiliging tegen geavanceerde bedreigingen** de optie Aan de **slag.**
4. Schakel in het deelvenster dat wordt geopend de **selectievakjes** in naast Koppelingen en bijlagen in e-mail, Bestanden **scannen in SharePoint, OneDrive** en Teams en Koppelingen **scannen in Office-bureaublad- en Office Online-apps** onder Items **scannen** op schadelijke inhoud.

   Typ **onder Koppelingen en bijlagen in e-mail** alle gebruikers of de specifieke gebruikers van wie u de e-mail wilt scannen.

   ![Schakel alle selectievakjes in Beveiliging tegen geavanceerde bedreigingen verhogen in.](../media/setatp.png)

5. Kies **Beleid maken om** Veilige bijlagen en veilige koppelingen in te stellen.

### <a name="set-up-safe-attachments-in-the-security--compliance-center"></a>Veilige bijlagen instellen in het beveiligings- & compliancecentrum

Personen verzenden, ontvangen en delen regelmatig bijlagen, zoals documenten, presentaties, spreadsheets en meer. Het is niet altijd eenvoudig om te zien of een bijlage veilig of schadelijk is door alleen maar naar een e-mailbericht te kijken. Microsoft Defender voor Office 365 bevat veilige bijlagebeveiliging, maar deze beveiliging is niet standaard ingeschakeld. U wordt aangeraden een nieuwe regel te maken om deze beveiliging te gaan gebruiken. Deze beveiliging geldt voor bestanden in SharePoint, OneDrive en Microsoft Teams.

Als u een beleid voor veilige bijlagen wilt maken, bekijkt u [deze korte video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)of volgt u de volgende stappen:

1. Ga naar <https://protection.office.com> en meld u aan met uw beheerdersaccount.

2. Kies in het & compliancecentrum in het linkernavigatiedeelvenster onder **Bedreigingsbeheer** de optie **Beleid.**

3. Kies op de pagina Beleid **de optie Veilige bijlagen.**

4. Pas deze beveiliging op de pagina Veilige bijlagen breed toe door het selectievakje ATP voor **SharePoint, OneDrive** en Microsoft Teams in te schakel.

5. Selecteer **+** om een nieuw beleid te maken.

6. Pas de instellingen in de volgende tabel toe.

7. Nadat u de instellingen hebt beoordeeld, kiest **u Dit beleid maken** of **Opslaan,** waar van toepassing.

|Instelling of optie|Aanbevolen instelling|
|---|---|
|Naam|Huidige en toekomstige e-mailberichten blokkeren met gedetecteerde malware.|
|Beschrijving|Blokkeer huidige en toekomstige e-mailberichten en bijlagen met gedetecteerde malware.|
|Bijlages opslaan onbekende malwarereactie|Selecteer **Blokkeren: blokkeer de huidige en toekomstige e-mailberichten en bijlagen met gedetecteerde malware.**|
|Bijlage omleiden bij detectie|Omleiding inschakelen (selecteer dit vak) <br/> Voer het beheerdersaccount of een postvakinstelling in voor quarantaine. <br/> Pas de bovenstaande selectie toe als er malware wordt gescand op bijlagen of als er een fout optreedt (schakel dit vakje in).|
|Toegepast op|Het domein van de geadresseerde is . . . selecteer uw domein.|

Zie [Anti-phishingbeleid instellen in Defender voor Office 365](../security/office-365-security/set-up-anti-phishing-policies.md)voor meer informatie.

### <a name="set-up-safe-links-in-the-security--compliance-center"></a>Veilige koppelingen instellen in het beveiligings- & compliancecentrum

Hackers verbergen soms schadelijke websites in koppelingen in e-mail of andere bestanden. Veilige koppelingen, onderdeel van Microsoft Defender voor Office 365, kunnen uw organisatie helpen beschermen door een time-of-click verificatie van webadressen (URL's) in e-mailberichten en Office-documenten te bieden. Beveiliging wordt gedefinieerd via beleidsregels voor veilige koppelingen.

U wordt aangeraden het volgende te doen:

- Wijzig het standaardbeleid om de beveiliging te verhogen.

- Voeg een nieuw beleid toe dat is gericht op alle geadresseerden in uw domein.

Als u Veilige koppelingen wilt instellen, [bekijkt u deze korte trainingsvideo](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)of volgt u de volgende stappen:

1. Ga naar <https://protection.office.com> en meld u aan met uw beheerdersaccount.

2. Kies in het & compliancecentrum in het linkernavigatiedeelvenster onder **Bedreigingsbeheer** de optie **Beleid.**

3. Kies op de pagina Beleid **de optie Veilige koppelingen.**

Het standaardbeleid wijzigen:

1. Selecteer op de pagina Veilige koppelingen, onder **Beleidsregels die van** toepassing zijn op de hele organisatie, het **standaardbeleid.**

2. Selecteer **onder Instellingen die van toepassing zijn op inhoud,** behalve e-mail, **microsoft 365 apps voor ondernemingen, Office voor iOS en Android.**

3. Klik op **Opslaan**.

Een nieuw beleid maken dat is gericht op alle geadresseerden in uw domein:

1. Klik op de pagina Veilige koppelingen, onder **Beleidsregels die** van toepassing zijn op de hele organisatie, **+** op om een nieuw beleid te maken.

2. Pas de instellingen toe die in de volgende tabel worden vermeld.

3. Klik op **Opslaan**.

|Instelling of optie|Aanbevolen instelling|
|---|---|
|Naam|Beleid voor veilige koppelingen voor alle geadresseerden in het domein|
|Selecteer de actie voor onbekende potentieel schadelijke URL's in berichten|Selecteer **Aan - URL's worden herschreven** en gecontroleerd op een lijst met bekende schadelijke koppelingen wanneer de gebruiker op de koppeling klikt.|
|Veilige bijlagen gebruiken om downloadbare inhoud te scannen|Schakel dit vakje in.|
|Toegepast op|Het domein van de geadresseerde is . . . selecteer uw domein.|

Zie Veilige koppelingen [in Defender voor Office 365](../security/office-365-security/safe-links.md)voor meer informatie.

## <a name="turn-on-the-unified-audit-log"></a>Het unified auditlogboek in-

Nadat u de zoekopdracht in het auditlogboek hebt in & beveiligingslogboek, kunt u de beheerder en andere gebruikersactiviteit in het logboek behouden en zoeken.

U moet de rol Auditlogboeken in Exchange Online toegewezen krijgen om de zoekopdracht in het auditlogboek in of uit te schakelen in uw Microsoft 365-abonnement. Deze rol is standaard toegewezen aan de rollengroepen Compliancebeheer en Organisatiebeheer op de pagina Machtigingen in het Exchange-beheercentrum. Globale beheerders in Microsoft 365 zijn standaard lid van deze groep.

1. Als u de zoekfunctie voor het auditlogboek wilt in- of uit te zetten, gaat u naar het beheercentrum bij en kiest u vervolgens <https://admin.microsoft.com> **Beveiliging** onder **Beheercentra** in de linkernavigatienavigatie.
2. Kies op de pagina Beveiliging van **Microsoft 365** de optie Meer **resources** en open vervolgens op de **kaart Office 365-beveiligingscentrum & compliancecentrum.** 

    ![Kies Openen op de beveiligings- & complianceauto's.](../media/gotosecandcomp.png)
3. Kies op de pagina Beveiliging en naleving de optie **Zoeken en** vervolgens Zoeken **in auditlogboek.**
4. Kies boven aan de **zoekpagina van het auditlogboek** de optie **Auditing in-/uit- zetten.**

Nadat de functie is ingeschakeld, kunt u zoeken naar bestanden, mappen en veel activiteiten. Zie het auditlogboek [doorzoeken voor meer informatie.](../compliance/search-the-audit-log-in-security-and-compliance.md)

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a>Instellingen voor anoniem delen voor SharePoint- en OneDrive-bestanden en -mappen aanpassen

(standaardverloop van anonieme koppeling wijzigen in 14 dagen, standaardtype voor delen wijzigen in 'Specifieke personen') De instellingen voor delen voor OneDrive en SharePoint wijzigen:

1. Ga naar het beheercentrum bij <https://admin.microsoft.com> en kies **vervolgens SharePoint** onder **Beheercentra** in de linkernavigatie.
2. Ga in het SharePoint-beheercentrum naar **Beleid** \> **delen.**
3. Selecteer  op de pagina Delen onder Bestands- en mapkoppelingen de optie Specifieke personen **en** selecteer onder Geavanceerde instellingen voor koppelingen 'Iedereen' deze **koppelingen** moeten binnen deze dagen verlopen en typ 14 (of een ander aantal dagen dat u de levensduur van de koppeling wilt beperken).

   ![Kies Specifieke personen en stel het verloop van de koppeling in op 14 dagen.](../media/anyonelinks.png)

## <a name="activity-alerts"></a>Activiteitswaarschuwingen

U kunt activiteitswaarschuwingen gebruiken om beheerders- en gebruikersactiviteiten bij te houden en incidenten met malware en preventie van gegevensverlies in uw organisatie te detecteren. Uw abonnement bevat een set standaardbeleidsregels, maar u kunt ook aangepaste beleidsregels maken. Zie [waarschuwingsbeleid voor meer informatie.](../compliance/alert-policies.md) Als u bijvoorbeeld een belangrijk bestand opgeslagen in SharePoint dat u niet wilt dat iemand extern deelt, kunt u een melding maken waarin u wordt gewaarschuwd als iemand het deelt.

In de volgende afbeelding ziet u de standaardbeleidsregels die zijn opgenomen in Microsoft 365.

![Standaardwaarschuwingsbeleid inbegrepen bij Microsoft 365](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a>Agenda delen uitschakelen of beheren

U kunt voorkomen dat personen in uw organisatie hun agenda's delen, of u kunt ook beheren wat ze kunnen delen. U kunt het delen bijvoorbeeld beperken tot alleen vrije/drukke tijden.

1. Ga naar het beheercentrum op <https://admin.microsoft.com> en kies **Instellingen** \> **Organisatie-instellingen**.
2. Kies **agenda** op de pagina Services en kies of personen in uw organisatie hun agenda's kunnen delen met personen buiten Office 365 of Exchange of met iemand anders.

   Als u de optie Delen met iedereen kiest, kunt u besluiten om ook alleen vrije/drukke informatie te delen.

3. Kies **Wijzigingen opslaan** onder aan de pagina.

   In de volgende afbeelding wordt het delen van agenda's niet toegestaan.

   ![Schermafbeelding van het weergeven van het delen van een externe agenda als niet toegestaan.](../media/nocalendarsharing.png)

   In de volgende afbeelding ziet u de instellingen wanneer delen van agenda's is toegestaan met een e-mailkoppeling met alleen vrije/drukke informatie.

   ![Schermafbeelding van het gratis/bezet delen van agenda's met iedereen.](../media/sharefreebusy.png)

Als uw gebruikers hun agenda's mogen delen, bekijkt u deze [instructies](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) voor het delen vanuit de webversie van Outlook.
