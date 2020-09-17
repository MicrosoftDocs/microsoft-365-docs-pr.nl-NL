---
title: Bedreigingsbeveiliging voor Microsoft 365 voor bedrijven verbeteren
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Stel Office 365 Advanced Threat Protection in en Bescherm gevoelige gegevens tegen phishing, malware en andere bedreigingen.
ms.openlocfilehash: d56a5371bc5fc4da22f4625024769cc0325a25ca
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948583"
---
# <a name="increase-threat-protection"></a>Bedreigingsbeveiliging verbeteren

Dit artikel helpt u bij het verbeteren van de bescherming van uw Microsoft 365-abonnement om te beschermen tegen phishing, malware en andere bedreigingen. Deze aanbevelingen zijn geschikt voor organisaties met een sterkere behoefte aan beveiliging, zoals wetten van kantoren en gezondheidszorg.

Voordat u begint, controleert u de Secure Score van Office 365. Secure Score van Office 365 analyse van de beveiliging van uw organisatie op basis van uw regelmatige activiteiten en beveiligingsinstellingen, en wijst een score toe. Begin met het noteren van uw huidige score. Als u de score wilt verhogen, voert u de acties uit die in dit artikel worden aanbevolen. Het doel is niet de maximum score te bereiken, maar om rekening te houden met verkoopkansen om uw omgeving te beschermen en de productiviteit van uw gebruikers niet negatief beïnvloeden.

Zie [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)voor meer informatie.

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Het beschermingsniveau voor malware in e-mail verhogen

Uw Office 365-of Microsoft 365-omgeving omvat beveiliging tegen malware. U kunt deze beveiliging verhogen door bijlagen te blokkeren met bestandstypen die vaak worden gebruikt voor malware. De bescherming van malware via e-mail verbeteren:

1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met de referenties van uw beheerdersaccount.

2. Kies in het &amp; gedeelte beveiligings compliance in het linker navigatiedeelvenster onder **Threat Management**de optie **beleids** \> **anti malware**.

3. Dubbelklik op het standaardbeleid om dit beleid voor het hele bedrijf te bewerken.

4. Selecteer **instellingen**.

5. Selecteer **aan**onder **common Attachment types filter**. De geblokkeerde bestandstypen worden weergegeven in het venster direct onder dit besturingselement. Zorg ervoor dat u deze bestandstypen toevoegt:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   U kunt later bestandstypen toevoegen of verwijderen.

6. Selecteer **opslaan.**

Zie [bescherming tegen malware in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection)voor meer informatie.

## <a name="protect-against-ransomware"></a>Beveiligen tegen ransomware

Ransomware beperkt de toegang tot gegevens door het versleutelen van bestanden of het vergrendelen van computerschermen. Vervolgens probeert u te extort van de slachtoffers door te vragen om ' Ransom ', meestal in de vorm van cryptocurrencies zoals Bitcoin, in Exchange voor toegang tot gegevens.

Als u zich wilt beschermen tegen Ransomware, maakt u een of meer e-mail stroom regels om bestandsextensies te blokkeren die meestal voor Ransomware worden gebruikt. (U hebt deze regels toegevoegd in de stap [het beveiligingsniveau tegen malware verhogen in e-mail](#raise-the-level-of-protection-against-malware-in-mail) stap.) U kunt ook gebruikers waarschuwen die deze bijlagen in een e-mail ontvangen.

Naast de bestanden die u in de vorige stap hebt geblokkeerd, is het een goede gewoonte om een regel te maken om gebruikers te waarschuwen voordat ze Office-bestandsbijlagen openen die macro's bevatten. Ransomware kan in macro's worden verborgen, dus waarschuwt gebruikers deze bestanden niet te openen van personen die ze niet kennen.

Een e-mail transportregel maken:

1. Ga naar het Beheercentrum <https://admin.microsoft.com> en kies Exchange **Center** \> **Exchange**.

2. Selecteer in de categorie **e-mail stroom** de optie **regels**.

3. Selecteer **+** en selecteer vervolgens **een nieuwe regel maken**.

4. Selecteer **meer opties** onder in het dialoogvenster om alle opties weer te geven.

5. De instellingen in de onderstaande tabel voor de regel toepassen. Gebruik de standaardwaarden voor de rest van de instellingen, tenzij u deze wilt wijzigen.

6. Selecteer **Opslaan**.

|Instelling|Gebruikers waarschuwen voordat bijlagen van Office-bestanden worden geopend||
|---|---|---|
|Naam|Regel voor een anti-Ransomware-regel: gebruikers waarschuwen|
|Pas deze regel toe. . .|Een bijlage. . . komt overeen met bestandsextensies. . .|
|Woorden of zinsdelen opgeven|Dit soort bestanden toevoegen:  <br/> dotm, DOCM, xlsm, sltm, xla, xlam, XLL, PPTM, POTM, PPAM, PPSM, sldm|
|Ga als volgt te werk. . .|De geadresseerde informeren met een bericht|
|Berichttekst geven|Open deze typen bestanden niet van personen die u niet kent, omdat ze macro's kunnen bevatten met schadelijke code.|

Zie voor meer informatie:

- [Ransomware: Risico's verminderen](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Uw OneDrive herstellen](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Automatisch doorsturen van e-mail stoppen

Hackers die toegang krijgen tot het postvak van een gebruiker kunnen e-mail stelen door het postvak in te stellen op het automatisch doorsturen van e-mail. Dit kan zelfs zonder de aandacht van de gebruiker. Om te voorkomen dat dit gebeurt, configureert u een e-mail stroom regel.

Voor het maken van een transportregel kunt u [deze korte video](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) bekijken of volgt u deze stappen:

1. Selecteer in het Microsoft 365-Beheercentrum de optie **beheer centra** \> **Exchange**.

2. Selecteer in de categorie **e-mail stroom** de optie **regels**.

3. Selecteer **+** en selecteer vervolgens **een nieuwe regel maken**.

4. Als u alle opties wilt zien, selecteert u **meer opties** onder aan het dialoogvenster.

5. De instellingen in de onderstaande tabel toepassen. Gebruik de standaardwaarden voor de rest van de instellingen, tenzij u deze wilt wijzigen.

6. Selecteer **Opslaan**.

|Instelling|Gebruikers waarschuwen voordat bijlagen van Office-bestanden worden geopend|
|---|---|
|Naam|Voorkom automatisch doorsturen van e-mail naar externe domeinen|
|Deze regel toepassen als...|De afzender. . . is extern/intern. . . Binnen de organisatie|
|Voorwaarde toevoegen|De berichteigenschappen. . . het berichttype opnemen. . . Automatisch doorsturen|
|Voer een van de volgende handelingen uit...|Het bericht blokkeren. . . u ziet het bericht af en voegt een uitleg toe.|
|Berichttekst geven|Het automatisch doorsturen van e-mail buiten deze organisatie kan beveiligingsredenen voorkomen.|


## <a name="protect-your-email-from-phishing-attacks"></a>Uw e-mail beschermen tegen phishing-aanvallen

Als u een of meer aangepaste domeinen hebt geconfigureerd voor uw Office 365-of Microsoft 365-omgeving, kunt u de gerichte bescherming tegen phishing instellen. Met een anti-virusbeveiliging van ATP, een onderdeel van Office 365 Advanced Threat Protection, kunt u uw organisatie beschermen tegen kwaadaardige aanvallen op basis van kwaadaardige aanvallen en andere phishing-aanvallen. U hoeft dit niet te doen als u geen aangepast domein hebt geconfigureerd.

U wordt geadviseerd om aan de slag te gaan met deze bescherming door een beleid te maken voor de bescherming van de belangrijkste gebruikers en uw aangepaste domein.

Bekijk  [deze korte trainings video](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)of voer de volgende stappen uit als u een ATP anti-phishingfilter wilt maken:

1. Ga naar [https://protection.office.com](https://protection.office.com).

2. Kies in het &amp; gedeelte beveiligings compliance in het linker navigatiedeelvenster onder **Threat Management**de optie **beleid**.

3. Kies op de pagina **beleid** de optie **ATP anti-phishing**.

4. Selecteer **+ maken**op de pagina **anti phishing** . Met een wizard wordt u stapsgewijs begeleid bij het definiëren van uw anti phishing-beleid.

5. Geef in de volgende tabel de naam, de beschrijving en de instellingen voor het beleid op. Zie voor meer informatie [meer informatie over ATP anti-phishingfilter-opties](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).

6. Wanneer u de instellingen hebt gecontroleerd, kiest u **dit beleid maken** of **Opslaan**.

|Instelling of optie|Aanbevolen instelling|
|---|---|
|Naam|Domein en meeste waardevolle campagne medewerkers|
|Beschrijving|Zorg ervoor dat het belangrijkste personeel en ons domein niet worden nagebootst.|
|Gebruikers toevoegen om te beschermen|Selecteer **+ een voorwaarde toevoegen, de ontvanger is**. Typ gebruikersnamen of voer het e-mailadres in van de kandidaat, campagne manager en andere belangrijke personeelsleden. U kunt maximaal 20 interne en externe adressen toevoegen die u wilt beveiligen tegen imitatie.|
|Domeinen toevoegen die u wilt beveiligen|Selecteer **+ een voorwaarde toevoegen, het domein van de ontvanger is**. Voer het aangepaste domein in dat is gekoppeld aan uw Microsoft 365-abonnement als u er een hebt gedefinieerd. U kunt meer dan één domein opgeven.|
|Acties kiezen|Als e-mail wordt verzonden door een geïmiteerde gebruiker: Kies **Bericht omleiden naar een ander e-mailadres**en typ vervolgens het e-mailadres van de beveiligingsbeheerder. bijvoorbeeld *Alice <span> <span> @contoso. com*. Als e-mail wordt verzonden door een geïmiteerd domein: Kies **quarantaine bericht**.|
|Postvak intelligentie|Standaard is postvak intelligentie geselecteerd wanneer u een nieuw anti-phishings beleid maakt. Voor de beste resultaten hoeft u **deze instelling niet** te selecteren.|
|Vertrouwde afzenders en domeinen toevoegen|U kunt hier uw eigen domein of een ander vertrouwd domein toevoegen.|
|Toegepast op|Selecteer **het domein van de ontvanger**. Selecteer **kiezen**onder **een van deze**opties. Selecteer **+ toevoegen**. Schakel het selectievakje in naast de naam van het domein, bijvoorbeeld *contoso. <span> <span> com*, in de lijst en selecteer vervolgens **toevoegen**. Selecteer **Gereed**.|

## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>Beveiligen tegen kwaadaardige bijlagen en bestanden met veilige ATP

Mensen verzenden, ontvangen en delen van bijlagen, zoals documenten, presentaties, spreadsheets en meer. Het is niet altijd eenvoudig om te zien of een bijlage veilig of schadelijk is, net zoals u een e-mailbericht bekijkt. Office 365 Advanced Threat Protection bevat bescherming tegen een vrije voorraad bijlage, maar deze bescherming is niet standaard ingeschakeld. U wordt geadviseerd om een nieuwe regel te maken om deze beveiliging te gaan gebruiken. Deze bescherming breidt zich uit naar bestanden in SharePoint, OneDrive en Microsoft teams.

Als u een voorbeeld van een vrije-en eind bijlage wilt maken, bekijkt u [deze korte video](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)of voert u de volgende stappen uit:

1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw beheerdersaccount.

2. Kies in het &amp; gedeelte beveiligings compliance in het linker navigatiedeelvenster onder **Threat Management**de optie **beleid**.

3. Kies op de pagina beleid de optie **veilige bijlagen met ATP**.

4. Op de pagina veilige bijlagen past u deze beveiliging algemeen toe door het selectievakje **ATP voor SharePoint, OneDrive en Microsoft teams inschakelen** in te schakelen.

5. Selecteer **+** om een nieuw beleid te maken.

6. De instellingen in de onderstaande tabel toepassen.

7. Wanneer u de instellingen hebt gecontroleerd, kiest u **dit beleid maken** of **Opslaan**.

|Instelling of optie|Aanbevolen instelling|
|---|---|
|Naam|Huidige en toekomstige e-mails blokkeren met gedetecteerde malware.|
|Beschrijving|Huidige en toekomstige e-mailberichten en bijlagen blokkeren met gedetecteerde malware.|
|Bijlagen opslaan, onbekende malware van malware|Selecteer **blokkeren de huidige en toekomstige e-mailberichten en bijlagen blokkeren met gedetecteerde malware**.|
|Bijlage omleiden bij detectie|Omleiding inschakelen (Selecteer dit vakje) Voer het beheerdersaccount of een postvak instelling in voor quarantaine.          De bovenstaande selectie toepassen als de malware wordt gescand op bijlagen wanneer een fout is opgetreden of als er een fout optreedt (Selecteer dit vak).|
|Toegepast op|Het domein van de ontvanger is. . . Selecteer uw domein.|

Zie voor meer informatie [Office 365 ATP anti phishingfilter-beleid instellen](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).

## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a>Beveiliging tegen phishing met veilige ATP-koppelingen

Hackers verbergen soms schadelijke websites via e-mailberichten of andere bestanden. Veilige koppelingen in Office 365 ATP (veilige koppelingen voor ATP), een onderdeel van Office 365 Advanced Threat Protection, kan u helpen uw organisatie te beschermen door geklikt verificatie van webadressen (url's) te geven in e-mailberichten en Office-documenten. Beveiliging wordt gedefinieerd via het beleid voor veilige koppelingen voor regels.

U wordt aangeraden het volgende te doen:

- Wijzig het standaardbeleid om de beveiliging te verbeteren.

- Een nieuwe beleidsregel toevoegen die is bedoeld voor alle geadresseerden in uw domein.

Bekijk [deze korte trainings video](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)of voer de volgende stappen uit om in te stellen dat u vrije verbindingen via ATP kunt instellen:

1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw beheerdersaccount.

2. Kies in het &amp; gedeelte beveiligings compliance in het linker navigatiedeelvenster onder **Threat Management**de optie **beleid**.

3. Kies op de pagina beleid de optie **veilige koppelingen voor ATP**.

Het standaardbeleid wijzigen:

1. Selecteer op de pagina veilige koppelingen onder **beleidsregels die van toepassing zijn op de hele organisatie**het **standaard** beleid.

2. Selecteer onder **instellingen die van toepassing zijn op inhoud met uitzondering van e-mail de**optie **Microsoft 365-apps voor Enterprise, Office voor IOS en Android**.

3. Selecteer **Opslaan**.

Een nieuwe beleidsregel maken voor alle geadresseerden in uw domein:

1. Selecteer op de pagina veilige koppelingen onder **beleidsregels die op de hele organisatie van toepassing zijn**, **+** om een nieuw beleid te maken.

2. De instellingen in de volgende tabel toepassen.

3. Selecteer **Opslaan**.

|Instelling of optie|Aanbevolen instelling|
|---|---|
|Naam|Beleid voor veilige koppelingen voor alle geadresseerden in het domein|
|Selecteer de actie voor onbekende, mogelijk schadelijke Url's in berichten|Selecteer **on-url's worden herschreven en gecontroleerd tegen een lijst met bekende kwaadaardige koppelingen wanneer de gebruiker klikt op de koppeling**.|
|Veilige bijlagen gebruiken om downloadbare inhoud te scannen|Schakel dit selectievakje in.|
|Toegepast op|Het domein van de ontvanger is. . . Selecteer uw domein.|

Zie voor meer informatie de [veilige koppelingen in Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links).

## <a name="go-to-intune-admin-center"></a>Ga naar het intune-Beheercentrum

1. Meld u aan bij [Azure Portal](https://portal.azure.com/).

2. Selecteer **alle services** en typ *intune* **in het zoekvak.**

3. Wanneer de resultaten worden weergegeven, selecteert u de start naast **Microsoft intune** zodat u deze later eenvoudig kunt terugvinden.

Naast het Beheercentrum, kunt u intune gebruiken om de apparaten van uw organisatie in te schrijven en te beheren. Zie [mogelijkheden voor inschrijvings methode voor Windows-apparaten](https://docs.microsoft.com/intune/enrollment/enrollment-method-capab) en opties voor [inschrijving voor apparaten die worden beheerd door intune](https://docs.microsoft.com/intune/enrollment-options)voor meer informatie.
