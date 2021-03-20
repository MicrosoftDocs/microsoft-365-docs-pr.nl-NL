---
title: Bedreigingsbeveiliging voor Microsoft 365 voor Bedrijven verhogen
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
description: Stel Microsoft Defender voor Office 365 in en bebeveiligen gevoelige gegevens tegen phishing, malware en andere bedreigingen.
ms.openlocfilehash: 0424fd56e30477f4e8d9e84b7ac78ba6255781fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913281"
---
# <a name="increase-threat-protection"></a>Bedreigingsbeveiliging verbeteren

In dit artikel kunt u de beveiliging in uw Microsoft 365-abonnement vergroten om te beschermen tegen phishing, malware en andere bedreigingen. Deze aanbevelingen zijn geschikt voor organisaties die meer behoefte hebben aan beveiliging, zoals advocatenkantoren en klinieken in de gezondheidszorg.

Controleer voordat u begint uw Office 365 Secure Score. Office 365 Secure Score analyseert de beveiliging van uw organisatie op basis van uw reguliere activiteiten en beveiligingsinstellingen en wijst een score toe. Begin met het noteren van uw huidige score. Als u uw score wilt verhogen, voltooit u de acties die in dit artikel worden aanbevolen. Het doel is niet om de maximale score te behalen, maar om rekening te houden met de mogelijkheden om uw omgeving te beschermen die de productiviteit van uw gebruikers niet negatief beïnvloeden.

Zie Microsoft Secure Score voor [meer informatie.](../security/mtp/microsoft-secure-score.md)

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Het niveau van beveiliging tegen malware in e-mail verhogen

Uw Office 365- of Microsoft 365-omgeving bevat bescherming tegen malware. U kunt deze beveiliging verhogen door bijlagen te blokkeren met bestandstypen die vaak worden gebruikt voor malware. Malwarebeveiliging in e-mail vergroten:

1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw beheerdersaccountreferenties.

2. Kies in het &amp; beveiligings compliancecentrum in het linkernavigatiedeelvenster onder **Bedreigingsbeheer** de optie  \> **Beleid tegen malware.**

3. Dubbelklik op het standaardbeleid om dit beleid voor het hele bedrijf te bewerken.

4. Selecteer **Instellingen**.

5. Selecteer **onder Gemeenschappelijke bijlagetypenfilter** de optie **Op**. De geblokkeerde bestandstypen worden weergegeven in het venster direct onder dit besturingselement. Zorg ervoor dat u deze bestandstypen toevoegt:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Zo nodig kunt u later bestandstypen toevoegen of verwijderen.

6. Selecteer **Opslaan.**

Zie Bescherming tegen [malware in EOP voor meer informatie.](../security/office-365-security/anti-malware-protection.md)

## <a name="protect-against-ransomware"></a>Beveiligen tegen ransomware

Ransomware beperkt de toegang tot gegevens door bestanden te versleutelen of computerschermen te vergrendelen. Vervolgens wordt geprobeerd geld af te persen van de slachtoffers door om 'los geld' te vragen, meestal in de vorm van cryptovaluta zoals Bitcoin, in ruil voor toegang tot gegevens.

Als u wilt beschermen tegen ransomware, maakt u een of meer regels voor e-mailstroom om bestandsextensies te blokkeren die vaak voor ransomware worden gebruikt. (U hebt deze regels toegevoegd aan het [verhogen van het beschermingsniveau tegen malware in de e-mailstap.)](#raise-the-level-of-protection-against-malware-in-mail) U kunt ook gebruikers waarschuwen die deze bijlagen per e-mail ontvangen.

Naast de bestanden die u in de vorige stap hebt geblokkeerd, is het een goede gewoonte om een regel te maken om gebruikers te waarschuwen voordat ze Office-bestandsbijlagen openen met macro's. Ransomware kan worden verborgen in macro's, dus waarschuw gebruikers om deze bestanden niet te openen van mensen die ze niet kennen.

Een regel voor e-mailtransport maken:

1. Ga naar het beheercentrum op <https://admin.microsoft.com> en kies **Beheercentra** \> **Exchange.**

2. Selecteer regels in **de categorie** **E-mailstroom.**

3. Selecteer **+** en selecteer vervolgens Een nieuwe regel **maken.**

4. Selecteer **Meer opties** onder aan het dialoogvenster om de volledige set opties weer te geven.

5. Pas de instellingen in de volgende tabel voor de regel toe. Gebruik de standaardwaarden voor de rest van de instellingen, tenzij u deze wilt wijzigen.

6. Kies **Opslaan**.

|Instelling|Gebruikers waarschuwen voordat ze bijlagen van Office-bestanden openen||
|---|---|---|
|Naam|Anti-ransomwareregel: gebruikers waarschuwen|
|Pas deze regel toe als . . .|Elke bijlage . . . bestandsextensie komt overeen. . .|
|Woorden of woordgroepen opgeven|Voeg deze bestandstypen toe:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm|
|Ga als volgt te werk. . .|De geadresseerde op de hoogte stellen met een bericht|
|Berichttekst verstrekken|Open dit type bestanden niet van personen die u niet kent, omdat ze mogelijk macro's met schadelijke code bevatten.|

Zie voor meer informatie:

- [Ransomware: risico's beperken](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Uw OneDrive herstellen](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Automatisch doorsturen voor e-mail stoppen

Hackers die toegang krijgen tot het postvak van een gebruiker, kunnen e-mail stelen door het postvak zo in te stellen dat e-mail automatisch wordt doorgestuurd. Dit kan zelfs gebeuren zonder dat de gebruiker dit weet. U kunt dit voorkomen door een e-mailstroomregel te configureren.

Als u een regel voor e-mailtransport wilt maken, [bekijkt](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) u deze korte video of volgt u de volgende stappen:

1. Selecteer in het Microsoft 365-beheercentrum de optie **Beheercentra** \> **Exchange**.

2. Selecteer regels in **de categorie** **E-mailstroom.**

3. Selecteer **+** en selecteer vervolgens Een nieuwe regel **maken.**

4. Als u alle opties wilt zien, **selecteert** u Meer opties onder aan het dialoogvenster.

5. Pas de instellingen in de volgende tabel toe. Gebruik de standaardwaarden voor de rest van de instellingen, tenzij u deze wilt wijzigen.

6. Kies **Opslaan**.

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

Als u een anti-phishingbeleid wilt maken in Microsoft Defender voor Office 365, bekijkt u deze korte  [trainingsvideo](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)of volgt u de volgende stappen:

1. Ga naar [https://protection.office.com](https://protection.office.com).

2. Kies in het &amp; Beveiligings compliancecentrum in het linkernavigatiedeelvenster onder **Bedreigingsbeheer** de optie **Beleid.**

3. Kies op **de** pagina Beleid de optie **Anti-phishing**.

4. Selecteer op **de pagina Anti-phishing** **+ Maken.** Er wordt een wizard gelanceerd om uw anti-phishingbeleid te definiëren.

5. Geef de naam, beschrijving en instellingen voor uw beleid op zoals aanbevolen in de volgende tabel. Zie Meer informatie over [anti-phishingbeleid in Opties voor Microsoft Defender voor Office 365](../security/office-365-security/set-up-anti-phishing-policies.md)voor meer informatie.

6. Nadat u de instellingen hebt gecontroleerd, kiest u **Dit beleid maken** of **Opslaan,** naar eigen goed.

|Instelling of optie|Aanbevolen instelling|
|---|---|
|Naam|Domein en meest waardevolle campagnemedewerkers|
|Beschrijving|Zorg ervoor dat het belangrijkste personeel en ons domein niet worden nagebootst.|
|Gebruikers toevoegen om ze te beveiligen|Selecteer **+ Een voorwaarde toevoegen, De ontvanger is**. Typ gebruikersnamen of voer het e-mailadres in van de kandidaat, campagnemanager en andere belangrijke personeelsleden. U kunt maximaal 20 interne en externe adressen toevoegen die u wilt beschermen tegen imitatie.|
|Domeinen toevoegen om te beveiligen|Selecteer **+ Een voorwaarde toevoegen, Het domein van de geadresseerde is**. Voer het aangepaste domein in dat is gekoppeld aan uw Microsoft 365-abonnement, als u er een hebt gedefinieerd. U kunt meer dan één domein invoeren.|
|Acties kiezen|Als e-mail wordt verzonden door een nagebootste gebruiker: Kies **Bericht omleiden** naar een ander e-mailadres en typ vervolgens het e-mailadres van de beveiligingsbeheerder; bijvoorbeeld: *<span> <span> Els @contoso.com.* Als e-mail wordt verzonden door een nagebootsd domein: Kies **Quarantainebericht.**|
|Postvakintelligentie|Standaard is postvakinformatie geselecteerd wanneer u een nieuw anti-phishingbeleid maakt. Laat deze instelling **aan voor** de beste resultaten.|
|Vertrouwde afzenders en domeinen toevoegen|Hier kunt u uw eigen domein of andere vertrouwde domeinen toevoegen.|
|Toegepast op|Selecteer **Het domein van de geadresseerde is**. Selecteer **onder Een van deze** opties de optie **Kiezen**. Selecteer **+ Toevoegen.** Schakel het selectievakje in naast de naam van het domein, bijvoorbeeld *contoso. <span> <span> com*, in de lijst en selecteer vervolgens **Toevoegen**. Selecteer **Gereed**.|

## <a name="protect-against-malicious-attachments-and-files-with-safe-attachments"></a>Beschermen tegen schadelijke bijlagen en bestanden met veilige bijlagen

Personen verzenden, ontvangen en delen regelmatig bijlagen, zoals documenten, presentaties, spreadsheets en meer. Het is niet altijd eenvoudig om te zien of een bijlage veilig of schadelijk is door alleen maar naar een e-mailbericht te kijken. Microsoft Defender voor Office 365 bevat veilige bijlagebeveiliging, maar deze beveiliging is niet standaard ingeschakeld. U wordt aangeraden een nieuwe regel te maken om deze beveiliging te gaan gebruiken. Deze beveiliging geldt voor bestanden in SharePoint, OneDrive en Microsoft Teams.

Als u een beleid voor veilige bijlagen wilt maken, bekijkt u [deze korte video](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)of volgt u de volgende stappen:

1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw beheerdersaccount.

2. Kies in het &amp; Beveiligings compliancecentrum in het linkernavigatiedeelvenster onder **Bedreigingsbeheer** de optie **Beleid.**

3. Kies op de pagina Beleid **de optie Veilige bijlagen.**

4. Pas deze beveiliging op de pagina Veilige bijlagen breed toe door het selectievakje ATP voor **SharePoint, OneDrive** en Microsoft Teams in te schakel.

5. Selecteer **+** om een nieuw beleid te maken.

6. Pas de instellingen in de volgende tabel toe.

7. Nadat u de instellingen hebt bekeken, kiest u **Dit beleid maken** of **Opslaan,** naar eigen goed.

|Instelling of optie|Aanbevolen instelling|
|---|---|
|Naam|Huidige en toekomstige e-mailberichten blokkeren met gedetecteerde malware.|
|Beschrijving|Blokkeer huidige en toekomstige e-mailberichten en bijlagen met gedetecteerde malware.|
|Bijlages opslaan onbekende malwarereactie|Selecteer **Blokkeren: blokkeer de huidige en toekomstige e-mailberichten en bijlagen met gedetecteerde malware.**|
|Bijlage omleiden bij detectie|Omleiding inschakelen (selecteer dit vak) Voer het beheerdersaccount of een postvakinstelling in voor quarantaine.          Pas de bovenstaande selectie toe als er malware wordt gescand op bijlagen of als er een fout optreedt (schakel dit vakje in).|
|Toegepast op|Het domein van de geadresseerde is . . . selecteer uw domein.|

Zie [Anti-phishingbeleid instellen in Microsoft Defender voor Office 365](../security/office-365-security/set-up-anti-phishing-policies.md)voor meer informatie.

## <a name="protect-against-phishing-attacks-with-safe-links"></a>Beschermen tegen phishingaanvallen met veilige koppelingen

Hackers verbergen soms schadelijke websites in koppelingen in e-mail of andere bestanden. Veilige koppelingen, onderdeel van Microsoft Defender voor Office 365, kunnen uw organisatie helpen beschermen door een time-of-click verificatie van webadressen (URL's) in e-mailberichten en Office-documenten te bieden. Beveiliging wordt gedefinieerd via beleidsregels voor veilige koppelingen.

U wordt aangeraden het volgende te doen:

- Wijzig het standaardbeleid om de beveiliging te verhogen.

- Voeg een nieuw beleid toe dat is gericht op alle geadresseerden in uw domein.

Als u Veilige koppelingen wilt instellen, [bekijkt u deze korte trainingsvideo](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)of volgt u de volgende stappen:

1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw beheerdersaccount.

2. Kies in het &amp; Beveiligings compliancecentrum in het linkernavigatiedeelvenster onder **Bedreigingsbeheer** de optie **Beleid.**

3. Kies op de pagina Beleid **de optie Veilige koppelingen.**

Het standaardbeleid wijzigen:

1. Selecteer op de pagina Veilige koppelingen, onder **Beleidsregels die van** toepassing zijn op de hele organisatie, het **standaardbeleid.**

2. Selecteer **onder Instellingen die van toepassing zijn op inhoud,** behalve e-mail, **microsoft 365 apps voor ondernemingen, Office voor iOS en Android.**

3. Kies **Opslaan**.

Een nieuw beleid maken dat is gericht op alle geadresseerden in uw domein:

1. Selecteer op de pagina Veilige koppelingen, onder **Beleidsregels** die van toepassing zijn op de hele organisatie, **+** om een nieuw beleid te maken.

2. Pas de instellingen toe die in de volgende tabel worden vermeld.

3. Kies **Opslaan**.

|Instelling of optie|Aanbevolen instelling|
|---|---|
|Naam|Beleid voor veilige koppelingen voor alle geadresseerden in het domein|
|Selecteer de actie voor onbekende potentieel schadelijke URL's in berichten|Selecteer **Aan - URL's worden herschreven** en gecontroleerd op een lijst met bekende schadelijke koppelingen wanneer de gebruiker op de koppeling klikt.|
|Veilige bijlagen gebruiken om downloadbare inhoud te scannen|Schakel dit vakje in.|
|Toegepast op|Het domein van de geadresseerde is . . . selecteer uw domein.|

Zie Veilige koppelingen voor [meer informatie.](../security/office-365-security/atp-safe-links.md)

## <a name="go-to-intune-admin-center"></a>Ga naar het Intune-beheercentrum

1. Meld u aan bij [azure portal.](https://portal.azure.com/)

2. Selecteer **Alle services en** typ *Intune* in het **zoekvak.**

3. Zodra de resultaten worden weergegeven, selecteert u de start naast **Microsoft Intune om** het een favoriet te maken en later gemakkelijk te vinden.

Naast het beheercentrum kunt u Intune gebruiken om de apparaten van uw organisatie in te schrijven en te beheren. Zie Mogelijkheden op inschrijvingsmethode voor [Windows-apparaten](/intune/enrollment/enrollment-method-capab) en Inschrijvingsopties voor apparaten die worden beheerd [door Intune](/intune/enrollment-options)voor meer informatie.