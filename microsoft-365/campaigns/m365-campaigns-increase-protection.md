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
ms.openlocfilehash: 56a6cd7fa82e8a35ea52a47475a14781ea0160cd
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044520"
---
# <a name="increase-threat-protection-for-microsoft-365-subscription"></a>Risicobeveiliging verhogen voor Microsoft 365-abonnement

In dit artikel kunt u uw Microsoft 365-abonnement beveiligen tegen phishing, malware en andere bedreigingen. Deze aanbevelingen zijn geschikt voor organisaties met een toenemende behoefte aan beveiliging, zoals beleidscampagnes, advocatenkantoren en medische klinieken.

Controleer voordat u begint uw Microsoft Secure Score. Microsoft Secure Score analyseert de beveiliging van uw organisatie op basis van uw reguliere activiteiten en beveiligingsinstellingen en wijst een score toe. Noteer eerst uw huidige score. Door de acties uit dit artikel uit te voeren, wordt uw score verhoogd. Het doel is niet de maximale score te bereiken, maar om rekening te houden met mogelijkheden om uw omgeving te beschermen die de productiviteit van uw gebruikers niet negatief beïnvloeden.

Zie Microsoft Secure Score voor [meer informatie.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Het beschermingsniveau verhogen tegen malware in e-mail

Uw Office 365- of Microsoft 365-omgeving bevat beveiliging tegen malware, maar u kunt deze beveiliging verhogen door bijlagen te blokkeren bij bestandstypen die veel worden gebruikt voor malware. Malwarebeveiliging in e-mail tegen gaan:

1. Meld u <https://protection.office.com> aan met de referenties van uw beheerdersaccount.

2. Kies in het & compliancecentrum aan de linkerkant, onder **Bedreigingsbeheer,** **De** optie \> **Beleid tegen malware.**

3. Dubbelklik op het standaardbeleid om dit beleid voor het hele bedrijf te bewerken.

4. Klik op **Instellingen**.

5. Selecteer **onder Filter voor veelgebruikte** bijlagetypen de optie **Op.** De geblokkeerde bestandstypen worden weergegeven in het venster direct onder dit besturingselement. Zorg ervoor dat u deze bestandstypen toevoegt:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   U kunt later, indien nodig, bestandstypen toevoegen of verwijderen.

6. Klik **op Opslaan.**

Zie [Anti-malwarebeveiliging in EOP voor meer informatie.](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection)

## <a name="protect-against-ransomware"></a>Beveiligen tegen ransomware

Ransomware beperkt de toegang tot gegevens door bestanden te versleutelen of computerschermen te vergrendelen. Vervolgens wordt er geprobeerd geld af te trekken van een haar door te vragen om 'hoer', meestal in de vorm van Eendige zoals Euro, in plaats van toegang tot gegevens.

U kunt beveiligen tegen ransomware door een of meer regels voor de e-mailstroom te maken om bestandsextensies te blokkeren die veel worden gebruikt voor ransomware (deze zijn toegevoegd om [malware in e-mail](#raise-the-level-of-protection-against-malware-in-mail) stap hoger te beschermen) of om gebruikers te waarschuwen die deze bijlagen in e-mail ontvangen.

Naast de bestanden die u in de vorige stap hebt geblokkeerd, is het ook een goede gewoonte om een regel te maken om gebruikers te waarschuwen voordat ze Office-bestandsbijlagen met macro's openen. Ransomware kunnen worden verborgen in macro's, dus u waarschuwt gebruikers om deze bestanden niet te openen bij mensen die ze niet kennen.

Een e-mail transportregel maken:

1. Ga naar het beheercentrum en <https://admin.microsoft.com> kies **Beheercentra** \> **Exchange.**

2. Klik in **de categorie e-mailstroom** op **regels.**

3. Klik **+** en klik vervolgens op Een nieuwe regel **maken.**

4. Klik **op Meer** opties onder aan het dialoogvenster om de volledige set opties weer te geven.

5. Pas de instellingen in de volgende tabel toe op de regel. Laat de rest van de instellingen op de standaardwaarde staan, tenzij u deze wilt wijzigen.

6. Klik op **Opslaan**.

|Instelling|Gebruikers waarschuwen voordat ze bijlagen van Office-bestanden openen|
|---|---|
|Naam|Regel tegen ransomware: gebruikers waarschuwen|
|Pas deze regel toe als . . .|Eventuele bijlagen. . . komt overeen met de bestandsextensie. . .|
|Woorden of woordgroepen opgeven|Voeg de volgende bestandstypen toe: <br/> `dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm`|
|Ga als volgt te werk: . .|De geadresseerde op de hoogte stellen met een bericht|
|Berichttekst verzenden|Open dergelijke bestandstypen niet van personen die u niet kent, omdat ze mogelijk macro's met schadelijke code bevatten.|

Zie voor meer informatie:

- [Ransomware: risico beperken](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Uw OneDrive herstellen](https://support.microsoft.com//office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="stop-auto-forwarding-for-email"></a>Automatisch doorsturen voor e-mail stoppen

Hackers die toegang krijgen tot het postvak van een gebruiker kunnen uw e-mail stelen door het postvak zo in te stellen dat e-mail automatisch wordt doorgestuurd. Dit kan zelfs gebeuren zonder dat de gebruiker zich daar bewust van is. U kunt dit voorkomen door een regel voor de e-mailstroom te configureren.

Als u een e-mail transportregel wilt maken, [bekijkt](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) u deze korte video of volgt u deze stappen:

1. Klik in het Microsoft 365-beheercentrum op **Exchange-beheercentra.** \> 

2. Klik in **de categorie e-mailstroom** op **regels.**

3. Klik **+** en klik vervolgens op Een nieuwe regel **maken.**

4. Klik **op Meer** opties onder aan het dialoogvenster om de volledige set opties weer te geven.

5. Pas de instellingen in de volgende tabel toe. Laat de rest van de instellingen op de standaardwaarde staan, tenzij u deze wilt wijzigen.

6. Klik op **Opslaan**.

|Instelling|Gebruikers waarschuwen voordat ze bijlagen van Office-bestanden openen|
|---|---|
|Naam|Voorkomen dat e-mail automatisch wordt doorgestuurd naar externe domeinen|
|Pas deze regel toe als...|De afzender. . . extern/intern is. . . Binnen de organisatie|
|Voorwaarde toevoegen|De berichteigenschappen. . . het berichttype opnemen. . . Automatisch doorsturen|
|Ga als volgt te werk...|Het bericht blokkeren. . . het bericht weigeren en een uitleg opnemen.|
|Berichttekst verzenden|Het automatisch doorsturen van e-mail buiten deze organisatie wordt om veiligheidsredenen voorkomen.|

## <a name="protect-your-email-from-phishing-attacks"></a>Bescherm uw e-mail tegen phishing-aanvallen

Als u een of meer aangepaste domeinen hebt geconfigureerd voor uw Office 365- of Microsoft 365-omgeving, kunt u gerichte beveiliging tegen phishing configureren. Anti-phishingbeveiliging, onderdeel van Microsoft Defender voor Office 365, kan uw organisatie helpen beschermen tegen kwaadaardige imitatie-phishing-aanvallen en andere phishing-aanvallen. Als u geen aangepast domein hebt geconfigureerd, hoeft u dit niet te doen.

Het is raadzaam om aan de slag te gaan met deze beveiliging door een beleid te maken ter bescherming van uw belangrijkste gebruikers en uw aangepaste domein.

Als u een anti-phishingbeleid wilt maken in Defender voor Office 365, bekijkt u deze korte [trainingsvideo](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)of voltooit u de volgende stappen:

1. Ga naar <https://protection.office.com>.

2. Kies in het & compliancecentrum aan de linkerkant, onder **Bedreigingsbeheer,** **de optie Beleid.**

3. Kies  **Anti-phishing** op de pagina Beleid.

4. Selecteer + Maken op de **anti-phishing-pagina.**  Een wizard start die u stap voor stap door het definiëren van uw anti-phishingbeleid.

5. Geef de naam, beschrijving en instellingen voor uw beleid op zoals wordt aanbevolen in de onderstaande grafiek. Zie meer informatie over [anti-phishingbeleid in de opties van Microsoft Defender voor Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)

6. Nadat u de instellingen hebt bekeken, kiest u **Dit beleid maken** of **Opslaan,** waar van toepassing.

|Instelling of optie|Aanbevolen instelling|
|---|---|
|Naam|Domein en meest waardevolle personeel|
|Beschrijving|Zorg ervoor dat het belangrijkste personeel en ons domein niet worden gemitmiteerd.|
|Gebruikers toevoegen om te beveiligen|Selecteer **+ Een voorwaarde toevoegen. De geadresseerde is.** Typ gebruikersnamen of voer het e-mailadres in van de eigenaren, partners of kandidaat, managers en andere belangrijke personeelsleden. U kunt maximaal 20 interne en externe adressen toevoegen die u wilt beveiligen tegen imitatie.|
|Domeinen toevoegen om te beveiligen|Selecteer **+ Een voorwaarde toevoegen, het domein van de ontvanger is.** Voer het aangepaste domein in dat is gekoppeld aan uw Microsoft 365-abonnement, als u dit hebt gedefinieerd. U kunt meer dan één domein invoeren.|
|Acties kiezen|Als e-mail wordt verzonden door een gemitmiteerde gebruiker: **Kies** Bericht omleiden naar een ander e-mailadres en typ vervolgens het e-mailadres van de beveiligingsbeheerder. Bijvoorbeeld: *Als <span> <span> @contoso.com.* <br/> Als e-mail wordt verzonden door een gemitmiteerd domein: Kies **Quarantainebericht.**|
|Postvakinformatie|Postvakinformatie wordt standaard geselecteerd wanneer u een nieuw anti-phishingbeleid maakt. Laat deze instelling **aan voor** de beste resultaten.|
|Vertrouwde afzenders en domeinen toevoegen|Hier kunt u uw eigen domein of andere vertrouwde domeinen toevoegen.|
|Toegepast op|Selecteer **het domein van de ontvanger.** Selecteer **Onder Een van deze opties** de optie **Kiezen.** Selecteer **+ Toevoegen.** Schakel het selectievakje naast de naam van het domein in, bijvoorbeeld *contoso. <span> <span> in* de lijst en selecteer vervolgens **Toevoegen.** Selecteer **Gereed**.|

Zie Anti-phishingbeleid instellen [in Defender voor Office 365 voor meer informatie.](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)

## <a name="protect-against-malicious-attachments-files-and-links-with-defender-for-office-365"></a>Beveiligen tegen schadelijke bijlagen, bestanden en koppelingen met Defender voor Office 365

![Banner die naar https://aka.ms/aboutM365preview .](../media/m365admincenterchanging.png)

Zorg er eerst voor dat in het beheercentrum de nieuwe preview-versie van het <https://admin.microsoft.com> beheercentrum is ingeschakeld. Zet de schakelaar naast de tekst in **het nieuwe beheercentrum.**

   ![De nieuwe preview-versie van het beheercentrum is in.](../media/previewon.png)

Als u de pagina  Setup met kaarten in uw tenant nog niet ziet, bekijkt u hoe u deze stappen kunt voltooien in het & Compliancecentrum. Zie Veilige bijlagen instellen in het beveiligings- [& compliancecentrum](#set-up-safe-attachments-in-the-security--compliance-center) en Veilige koppelingen instellen in het & [Compliancecentrum.](#set-up-safe-links-in-the-security--compliance-center)

1. Kies Setup in het **linkernavigatienavigatiebalkje.**
2. Kies op **de** pagina Setup de optie **Weergeven** op **de kaart Betere beveiliging tegen geavanceerde bedreigingen.**

   ![Kies Weergeven op de beveiliging verhogen tegen geavanceerde bedreigingen.](../media/startatp.png)

3. Kies Aan **de slag op** de pagina Beveiliging verhogen tegen geavanceerde **bedreigingen.**
4. Schakel in het deelvenster dat wordt geopend de **selectievakjes** in naast Koppelingen en bijlagen in e-mail, Bestanden scannen **in SharePoint, OneDrive** en Teams, en scan koppelingen in de bureaublad- en **Office Online-apps** onder Items scannen op schadelijke **inhoud.**

   Typ **onder Koppelingen en bijlagen in e-mail** alle gebruikers of de specifieke gebruikers van wie u de e-mail wilt scannen.

   ![Schakel alle selectievakjes in Beveiliging tegen geavanceerde bedreigingen vergroten in.](../media/setatp.png)

5. Kies **Beleid maken** om Veilige bijlagen en veilige koppelingen in te stellen.

### <a name="set-up-safe-attachments-in-the-security--compliance-center"></a>Veilige bijlagen instellen in het beveiligings- & compliancecentrum

Personen verzenden, ontvangen en delen regelmatig bijlagen, zoals documenten, presentaties, spreadsheets en meer. Het is niet altijd eenvoudig om te bepalen of een bijlage veilig of schadelijk is door alleen maar naar een e-mailbericht te kijken. Microsoft Defender voor Office 365 bevat beveiliging tegen veilige bijlagen, maar deze beveiliging is niet standaard ingeschakeld. U wordt aangeraden een nieuwe regel te maken om deze beveiliging te gebruiken. Deze beveiliging geldt ook voor bestanden in SharePoint, OneDrive en Microsoft Teams.

Als u een beleid voor veilige bijlagen wilt maken, bekijkt u [deze korte video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)of volgt u de volgende stappen:

1. Meld u <https://protection.office.com> aan met uw beheerdersaccount.

2. Kies in het & compliancecentrum aan de linkerkant, onder **Bedreigingsbeheer,** **de optie Beleid.**

3. Kies Veilige bijlagen op de pagina **Beleid.**

4. Pas deze beveiliging breed toe op de pagina Veilige bijlagen door het selectievakje ATP in te schakel voor **SharePoint, OneDrive en Microsoft Teams** in.

5. Selecteer **+** deze optie om een nieuw beleid te maken.

6. Pas de instellingen in de volgende tabel toe.

7. Nadat u de instellingen hebt door herzien, kiest **u Dit beleid maken** of Opslaan, waar van toepassing. 

|Instelling of optie|Aanbevolen instelling|
|---|---|
|Naam|Huidige en toekomstige e-mailberichten blokkeren met gedetecteerde malware.|
|Beschrijving|Huidige en toekomstige e-mailberichten en bijlagen blokkeren met gedetecteerde malware.|
|Onbekende malwarereactie bijlagen opslaan|Blokkeren **selecteren: de huidige en toekomstige e-mailberichten en bijlagen met gedetecteerde malware blokkeren.**|
|Bijlage omleiden bij detectie|Omleiding inschakelen (selecteer dit vakje) <br/> Voer het beheerdersaccount of het postvak in voor quarantaine. <br/> De bovenstaande selectie toepassen als er malware wordt gescand op bijlagen of als er een fout optreedt (selecteer dit vakje).|
|Toegepast op|Het domein van de ontvanger is . . . selecteert u uw domein.|

Zie Anti-phishingbeleid instellen [in Defender voor Office 365 voor meer informatie.](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)

### <a name="set-up-safe-links-in-the-security--compliance-center"></a>Veilige koppelingen instellen in het beveiligings- & compliancecentrum

Hackers verbergen soms schadelijke websites in koppelingen in e-mail of andere bestanden. Veilige koppelingen, onderdeel van Microsoft Defender voor Office 365, kunnen uw organisatie helpen beschermen door middel van tijd-van-klik-verificatie van webadressen (URL's) in e-mailberichten en Office-documenten. Beveiliging is gedefinieerd via beleidsregels voor veilige koppelingen.

U wordt aangeraden het volgende te doen:

- Wijzig het standaardbeleid om de beveiliging te verhogen.

- Voeg een nieuw beleid toe dat is gericht op alle geadresseerden in uw domein.

Bekijk deze korte trainingsvideo of volg de volgende [stappen](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)om Veilige koppelingen in te stellen:

1. Ga naar <https://protection.office.com> en meld u aan met uw beheerdersaccount.

2. Kies in het & compliancecentrum aan de linkerkant, onder **Bedreigingsbeheer,** **de optie Beleid.**

3. Kies Veilige koppelingen op de pagina **Beleid.**

Het standaardbeleid wijzigen:

1. Selecteer op de pagina Veilige koppelingen, onder Beleid **dat van toepassing** is op de hele organisatie, het **standaardbeleid.**

2. Selecteer onder Instellingen die van toepassing zijn op inhoud behalve **e-mail,** **Microsoft 365-apps voor ondernemingen, Office voor iOS en Android.**

3. Klik op **Opslaan**.

Een nieuw beleid maken dat is gericht op alle geadresseerden in uw domein:

1. Klik op de pagina Veilige koppelingen onder Beleid **dat van toepassing** is op de hele organisatie op een nieuw **+** beleid.

2. Pas de instellingen uit de volgende tabel toe.

3. Klik op **Opslaan**.

|Instelling of optie|Aanbevolen instelling|
|---|---|
|Naam|Beleid voor veilige koppelingen voor alle geadresseerden in het domein|
|De actie selecteren voor onbekende, potentieel schadelijke URL's in berichten|Selecteren **op - URL's** worden herschreven en gecontroleerd aan de hand van een lijst met bekende schadelijke koppelingen wanneer de gebruiker op de koppeling klikt.|
|Veilige bijlagen gebruiken om downloadbare inhoud te scannen|Selecteer dit vakje.|
|Toegepast op|Het domein van de ontvanger is . . . selecteert u uw domein.|

Zie Veilige koppelingen [in Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)voor meer informatie.

## <a name="turn-on-the-unified-audit-log"></a>Het geïntegreerde auditlogboek inloggen

Nadat u de zoekopdracht in het auditlogboek in het beveiligings- & Compliancecentrum hebt in werking, kunt u de beheerder en andere gebruikersactiviteit in het logboek behouden en doorzoeken.

U moet de rol Auditlogboeken hebben toegewezen in Exchange Online om zoeken in auditlogboeken in of uit te schakelen in uw Microsoft 365-abonnement. Deze rol is standaard toegewezen aan de rollengroepen Compliancebeheer en Organisatiebeheer op de pagina Machtigingen in het Exchange-beheercentrum. Globale beheerders in Microsoft 365 zijn standaard lid van deze groep.

1. Als u zoeken in het auditlogboek wilt inloggen, gaat u naar het beheercentrum en kiest u Beveiliging <https://admin.microsoft.com> onder **Beheercentra** in  de linkernavigatiebalk.
2. Op de **pagina Microsoft 365-beveiliging** kiest  u Meer **bronnen** en vervolgens Openen op de kaart & beveiligingscentrum van **Office 365.**

    ![Kies Openen in de beveiligings- & complianceauto's.](../media/gotosecandcomp.png)
3. Kies op de pagina Beveiliging en naleving de optie **Zoeken** en vervolgens Zoeken in **auditlogboek.**
4. Kies boven aan de zoekpagina van het **auditlogboek** de **optie Controle in turn on.**

Nadat de functie is ingeschakeld, kunt u zoeken naar bestanden, mappen en veel activiteiten. Zie het auditlogboek [doorzoeken voor meer informatie.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a>Instellingen voor anoniem delen aanpassen voor SharePoint- en OneDrive-bestanden en -mappen

(standaardverlooptijd van anonieme koppeling wijzigen in 14 dagen, standaardtype voor delen wijzigen in 'Specifieke personen') De instellingen voor delen voor OneDrive en SharePoint wijzigen:

1. Ga naar het beheercentrum en <https://admin.microsoft.com> kies **SharePoint** onder **Beheercentra** in het linkernavigatiedeelcentrum.
2. Ga in het SharePoint-beheercentrum naar **Beleid** \> **delen.**
3. Selecteer  op de pagina Delen, onder Koppelingen naar bestanden en **mappen,** Specifieke personen en selecteer onder Geavanceerde instellingen voor koppelingen voor Iedereen de optie Deze koppelingen moeten binnen dit aantal dagen verlopen en 14 (of een ander aantal dagen dat u de levensduur van de koppeling wilt beperken) typen.

   ![Kies Specifieke personen en stel de verlooptijd van de koppeling in op 14 dagen.](../media/anyonelinks.png)

## <a name="activity-alerts"></a>Activiteitswaarschuwingen

U kunt meldingen over activiteiten gebruiken om activiteiten van beheerders en gebruikers bij te houden en incidenten met malware en preventie van gegevensverlies in uw organisatie te detecteren. Uw abonnement bevat een reeks standaardbeleidsregels, maar u kunt ook aangepaste beleidsregels maken. Zie beleidsregels voor [waarschuwingen voor meer informatie.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) Als u bijvoorbeeld een belangrijk bestand opgeslagen in SharePoint en u wilt niet dat iemand extern deelt, kunt u een melding maken waarin u wordt gewaarschuwd als iemand het bestand wel deelt.

In de volgende afbeelding ziet u het standaardbeleid dat is opgenomen in Microsoft 365.

![Standaardbeleidsregels voor waarschuwingen van Microsoft 365](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a>Agenda's delen uitschakelen of beheren

U kunt voorkomen dat personen in uw organisatie hun agenda's delen, maar u kunt ook beheren wat ze kunnen delen. U kunt bijvoorbeeld het delen beperken tot alleen vrij/bezet tijden.

1. Ga naar het beheercentrum en <https://admin.microsoft.com> kies Instellingen  \> **organisatie-instellingen.**
2. Kies Agenda op de pagina **Services** en kies of personen in uw organisatie hun agenda's kunnen delen met personen buiten die Office 365 of Exchange hebben of met wie dan ook.

   Als u de optie Delen met iedereen kiest, kunt u besluiten om ook alleen de informatie over vrij/bezet te delen.

3. Kies **Wijzigingen opslaan** onder aan de pagina.

   In de volgende afbeelding ziet u dat het delen van agenda's niet is toegestaan.

   ![Schermafbeelding van het delen van een externe agenda als niet toegestaan.](../media/nocalendarsharing.png)

   In de volgende afbeelding ziet u de instellingen wanneer het delen van agenda's is toegestaan, met een koppeling naar een e-mail met alleen de informatie over vrij/bezet.

   ![Schermafbeelding van het delen van de agenda met iedereen.](../media/sharefreebusy.png)

Als uw gebruikers hun agenda mogen [](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) delen, bekijkt u deze instructies voor het delen vanuit de webversie van Outlook.
