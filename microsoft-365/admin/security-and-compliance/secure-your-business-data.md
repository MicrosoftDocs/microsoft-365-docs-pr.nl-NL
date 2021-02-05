---
title: De tien belangrijkste manieren om microsoft 365 voor bedrijven-abonnementen te beveiligen
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: de2da300-dbb6-4725-bb12-b85a9d296e75
description: 'Bescherm uw zakelijke e-mail en gegevens tegen cyberaanvallen, waaronder ransomware, phishing en schadelijke bijlagen. '
ms.openlocfilehash: 3ae6d896d5ef060e2f077167f81e2029a3a143ac
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114403"
---
# <a name="top-10-ways-to-secure-microsoft-365-for-business-plans"></a>De tien belangrijkste manieren om microsoft 365 voor bedrijven-abonnementen te beveiligen

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Als u een kleine of middelgrote organisatie bent die gebruik maakt van een van de bedrijfsplannen van Microsoft en uw type organisatie wordt gericht door cybercriminelen en hackers, gebruikt u de richtlijnen in dit artikel om de beveiliging van uw organisatie te vergroten. Deze richtlijnen helpen uw organisatie de doelen te bereiken die worden beschreven in het handboek [Marketingcampagne van](https://go.microsoft.com/fwlink/p/?linkid=2015598)De Harvard School.

Microsoft raadt u aan de taken uit de volgende tabel te voltooien die van toepassing zijn op uw serviceplan.

||Taak|Microsoft 365 Business Standard|Microsoft 365 Business Premium|
|---|---|---|---|
|1|[Meervoudige verificatie instellen](secure-your-business-data.md#setup)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|2|[Uw gebruikers trainen](secure-your-business-data.md#train)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|3|[Toegewezen beheerdersaccounts gebruiken](secure-your-business-data.md#admin)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4|[Het beschermingsniveau verhogen tegen malware in e-mail](secure-your-business-data.md#malware)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5|[Beveiligen tegen ransomware](secure-your-business-data.md#ransomware)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6|[Automatisch doorsturen voor e-mail stoppen](secure-your-business-data.md#forwarding)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7|[Office-berichtversleuteling gebruiken](secure-your-business-data.md#encryption)||![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8|[Bescherm uw e-mail tegen phishing-aanvallen](secure-your-business-data.md#phishing)||![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9|[Beveiligen tegen schadelijke bijlagen en bestanden met veilige bijlagen](secure-your-business-data.md#atp)||![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10|[Bescherm u tegen phishing-aanvallen met veilige koppelingen](secure-your-business-data.md#phishingatp)||![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|

Controleer voordat u begint uw [Microsoft 365 Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) in het Microsoft 365-beveiligingscentrum. Vanuit een gecentraliseerd dashboard kunt u de beveiliging van uw Microsoft 365-identiteiten, gegevens, apps, apparaten en infrastructuur controleren en verbeteren. U krijgt punten voor het configureren van aanbevolen beveiligingsfuncties, het uitvoeren van beveiligingstaken (zoals het weergeven van rapporten) of het oplossen van aanbevelingen met een toepassing of software van derden. Met meer inzichten en meer inzicht in een bredere set Microsoft-producten en -services, kunt u er zeker van zijn dat u zeker weet wat de beveiligingstoestand van uw organisatie is.

![Schermafbeelding van Microsoft Secure Score](../../media/secure-score.png)

## <a name="1-set-up-multi-factor-authentication"></a>1: Meervoudige verificatie instellen
<a name="setup"> </a>

Het gebruik van meervoudige verificatie is een van de makkelijkste en meest effectieve manieren om de beveiliging van uw organisatie te vergroten. Dit is gemakkelijker dan wordt gezegd: wanneer u zich aanmeldt, betekent meervoudige verificatie dat u een code van uw telefoon typt om toegang te krijgen tot Microsoft 365. Dit kan voorkomen dat hackers de foto's overnemen als ze uw wachtwoord kennen. Meervoudige verificatie wordt ook wel verificatie in twee stappen genoemd. Personen kunnen eenvoudig verificatie in twee stappen toevoegen aan de meeste accounts, bijvoorbeeld aan hun Google- of Microsoft-account. U voegt als volgende [tweestapsverificatie toe aan uw persoonlijke Microsoft-account.](https://go.microsoft.com/fwlink/p/?linkid=2016403)

Voor bedrijven die Microsoft 365 gebruiken, voegt u een instelling toe waarin uw gebruikers zich moeten aanmelden met meervoudige verificatie. Wanneer u deze wijziging aan brengen, wordt gebruikers gevraagd hun telefoon in te stellen voor tweestapsverificatie wanneer ze zich de volgende keer aanmelden.
Als u een trainingsvideo wilt zien over het instellen van MFA en hoe gebruikers de set-up voltooien, bekijkt u het instellen van [MFA](https://support.microsoft.com/office/e12187b8-216a-4490-9e3b-df34a06fb787) en het instellen [van de gebruiker.](https://support.microsoft.com/office/a32541df-079c-420d-9395-9d59354f7225)

Als u meervoudige verificatie wilt instellen, moet u beveiligingsinstellingen inschakelen:

Voor de meeste organisaties bieden standaardinstellingen voor beveiliging een goed niveau aanvullende aanmeldingsbeveiliging. Raadpleeg [Wat zijn standaardinstellingen voor beveiliging?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) voor meer informatie

Als uw abonnement nieuw is, zijn de standaardinstellingen voor beveiliging mogelijk al automatisch ingeschakeld.

U kunt standaardinstellingen voor beveiliging in- of uitschakelen vanuit het deelvenster **Eigenschappen** voor Azure Active Directory (Azure AD) in Azure Portal.

1. Meld u aan bij [Microsoft 365-beheercentrum](https://admin.microsoft.com) met algemeen beheerdersreferenties.
2. Kies in het linker navigatievenster **Alle weergeven** en kies onder **Beheercentra** **Azure Active Directory**.
3. Kies in het **Azure Active Directory-beheercentrum** **Azure Active Directory** > **-eigenschappen**.
4. Kies onderaan de pagina de optie **Standaardinstellingen voor beveiliging beheren**.
5. Kies **Ja** als u de standaardinstellingen voor beveiliging wilt inschakelen of **Nee** om deze uit te schakelen en kies vervolgens **Opslaan**.

Nadat u meervoudige verificatie voor uw organisatie hebt ingesteld, moeten uw gebruikers tweestapsverificatie op hun apparaten instellen. Zie Verificatie in twee stappen instellen [voor Microsoft 365](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)voor meer informatie.

Zie Meervoudige verificatie instellen voor gebruikers voor meer informatie [en volledige aanbevelingen.](set-up-multi-factor-authentication.md)

## <a name="2-train-your-users"></a>2: Uw gebruikers trainen
<a name="train"> </a>

Het handboek Marketingcampagne van Harvard [School biedt](https://go.microsoft.com/fwlink/p/?linkid=2015598) uitstekende richtlijnen voor het creëren van een sterke beveiligingscultuur binnen uw organisatie, waaronder training voor het identificeren van phishing-aanvallen.

Naast deze richtlijnen raadt Microsoft uw gebruikers aan de acties uit te voeren die in dit artikel worden beschreven: Bescherm uw account en apparaten [tegen hackers en malware.](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6) Dit zijn onder andere de volgende acties:

- Sterke wachtwoorden gebruiken

- Apparaten beveiligen

- Beveiligingsfuncties inschakelen op Windows 10- en Mac-pc's

Microsoft raadt gebruikers ook aan hun persoonlijke e-mailaccounts te beveiligen door de acties uit te voeren die worden aanbevolen in de volgende artikelen:

- [Uw e-mailaccount Outlook.com beschermen](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [Uw Gmail-account beveiligen met verificatie in twee stappen](https://go.microsoft.com/fwlink/p/?linkid=2015688&)

## <a name="3-use-dedicated-admin-accounts"></a>3: Toegewezen beheerdersaccounts gebruiken
<a name="admin"> </a>

De beheeraccounts die u gebruikt om uw Microsoft 365-omgeving te beheren, bevatten verhoogde bevoegdheden. Dit zijn waardevolle doelen voor hackers en cybercriminelen. Gebruik alleen beheerdersaccounts voor beheer. Beheerders moeten een afzonderlijk gebruikersaccount hebben voor regulier, niet-beheergebruik en hun beheerdersaccount alleen gebruiken als dat nodig is om een taak te voltooien die aan de functie is gekoppeld. Aanvullende aanbevelingen:

- Zorg ervoor dat beheerdersaccounts ook zijn ingesteld voor meervoudige verificatie.

- Sluit voordat u beheerdersaccounts gebruikt, alle niet-gerelateerde browsersessies en -apps, inclusief persoonlijke e-mailaccounts.

- Nadat u beheertaken heeft uitgevoerd, moet u zich afmelden bij de browsersessie.

## <a name="4-raise-the-level-of-protection-against-malware-in-mail"></a>4: Het beschermingsniveau verhogen tegen malware in e-mail
<a name="malware"> </a>

Uw Microsoft 365-omgeving omvat beveiliging tegen malware, maar u kunt deze beveiliging verhogen door bijlagen te blokkeren bij bestandstypen die veel worden gebruikt voor malware. Als u malwarebeveiliging in e-mail wilt tegen gaan, bekijkt u een [korte trainingsvideo](https://support.microsoft.com/office/02b5783a-eea0-42e8-8856-62440718c3f0)of volgt u de volgende stappen:

1. Meld u <https://protection.office.com> aan met de referenties van uw beheerdersaccount.

2. Kies in het & Compliancecentrum aan de linkerkant onder **Bedreigingsbeheer** de optie  \> **Beleid anti-malware.**

3. Dubbelklik op het standaardbeleid om dit beleid voor het hele bedrijf te bewerken.

4. Selecteer **Instellingen.**

5. Selecteer **onder Filter voor veelgebruikte** bijlagetypen de optie **Op.** De geblokkeerde bestandstypen worden weergegeven in het venster direct onder dit besturingselement. U kunt later, indien nodig, bestandstypen toevoegen of verwijderen.

6. Selecteer **Opslaan.**

Zie [Anti-malwarebeveiliging in EOP voor meer informatie.](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection)

## <a name="5-protect-against-ransomware"></a>5: Beveiligen tegen ransomware
<a name="ransomware"> </a>

Ransomware beperkt de toegang tot gegevens door bestanden te versleutelen of computerschermen te vergrendelen. Vervolgens wordt geprobeerd geld af te trekken van een haar door te vragen om 'hoer', meestal in de vorm van Eendige zoalsJe, in plaats van toegang tot gegevens.

U kunt beveiligen tegen ransomware door een of meer regels voor de e-mailstroom te maken om bestandsextensies te blokkeren die veel worden gebruikt voor ransomware of om gebruikers te waarschuwen die deze bijlagen in e-mail ontvangen. Een goed uitgangspunt is het maken van twee regels:

- Waarschuw gebruikers voordat ze Office-bestandsbijlagen met macro's openen. Ransomware kunnen worden verborgen in macro's, dus we waarschuwen gebruikers om deze bestanden niet te openen van personen die ze niet kennen.

- Blokkeer bestandstypen die ransomware of andere schadelijke code kunnen bevatten. We beginnen met een algemene lijst met uitvoerbare bestanden (weergegeven in de onderstaande tabel). Als uw organisatie een van deze uitvoerbare typen gebruikt en u verwacht dat deze via e-mail worden verzonden, voegt u deze toe aan de vorige regel (gebruikers waarschuwen).

Als u een e-mail transportregel wilt maken, bekijkt u een [korte trainingsvideo](https://support.microsoft.com/office/a9ecca03-42a6-4867-b9fd-38e3f6bb06ad)of volgt u de volgende stappen:

1. Ga naar het [Exchange-beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2059104).

2. Selecteer regels **in de** categorie **e-mailstroom.**

3. Selecteer **+** en maak vervolgens een nieuwe **regel.**

4. Selecteer **** onder aan het dialoogvenster om de volledige set opties weer te geven.

5. Pas de instellingen in de volgende tabel voor elke regel toe. Laat de rest van de instellingen op de standaardwaarde staan, tenzij u deze wilt wijzigen.

6. Kies **Opslaan**.
    
| Instelling | Gebruikers waarschuwen voordat ze bijlagen van Office-bestanden openen | Bestandstypen blokkeren die ransomware of andere schadelijke code kunnen bevatten |
|:-----|:-----|:-----|
|Naam  <br/> |Regel tegen ransomware: gebruikers waarschuwen  <br/> |Regel tegen ransomware: bestandstypen blokkeren  <br/> |
|Pas deze regel toe als . . .  <br/> |Eventuele bijlagen. . . komt overeen met de bestandsextensie. . .  <br/> |Eventuele bijlagen. . . komt overeen met de bestandsextensie. . .  <br/> |
|Woorden of woordgroepen opgeven  <br/> |Voeg de volgende bestandstypen toe:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm  <br/> |Voeg de volgende bestandstypen toe:  <br/> ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, mst, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif  <br/> |
|Ga als volgt te werk: . .  <br/> |Een vrijwaring voorbereiden  <br/> |Het bericht blokkeren. . . het bericht weigeren en een uitleg opnemen  <br/> |
|Berichttekst verzenden  <br/> |Open deze typen bestanden niet, tenzij u ze verwachtte, omdat de bestanden mogelijk schadelijke code bevatten en weten dat de afzender geen garantie op veiligheid is.  <br/> ||
   
> [!TIP]
> In stap 4 kunt u ook de bestanden die u wilt blokkeren, toevoegen aan de lijst met [malware.](#4-raise-the-level-of-protection-against-malware-in-mail)

Zie voor meer informatie:

- [Ransomware: risico beperken](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Uw OneDrive herstellen](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="6-stop-auto-forwarding-for-email"></a>6: Automatisch doorsturen voor e-mail stoppen
<a name="forwarding"> </a>

Hackers die toegang krijgen tot het postvak van een gebruiker, kunnen e-mail verzenden door het postvak zo te configureren dat e-mail automatisch wordt doorgestuurd. Dit kan zelfs gebeuren zonder dat de gebruiker zich daar bewust van is. U kunt dit voorkomen door een regel voor de e-mailstroom te configureren.

Een e-mail transportregel maken:

1. Ga naar het [Exchange-beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2059104).

2. Selecteer regels **in de** categorie **e-mailstroom.**

3. Selecteer **+** en maak vervolgens een nieuwe **regel.**

4. Selecteer **Meer opties** onder aan het dialoogvenster om de volledige set opties weer te geven.

5. Pas de instellingen in de volgende tabel toe. Laat de rest van de instellingen op de standaardwaarde staan, tenzij u deze wilt wijzigen.

6. Kies **Opslaan**.

|Instelling|Automatisch doorsturen van e-mailberichten naar externe domeinen weigeren|
|---|---|
|Naam|Voorkomen dat e-mail automatisch wordt doorgestuurd naar externe domeinen|
|Pas deze regel toe als...|De afzender. . . extern/intern is. . . Binnen de organisatie|
|Voorwaarde toevoegen|De geadresseerde. . . extern/intern is. . . Buiten de organisatie|
|Voorwaarde toevoegen|De berichteigenschappen. . . het berichttype opnemen. . . Automatisch doorsturen|
|Ga als volgt te werk...|Het bericht blokkeren. . . het bericht weigeren en een uitleg opnemen.|
|Berichttekst verzenden|Het automatisch doorsturen van e-mail buiten deze organisatie wordt om veiligheidsredenen voorkomen.|

## <a name="7-use-office-message-encryption"></a>7: Office-berichtversleuteling gebruiken
<a name="encryption"> </a>

Office-berichtversleuteling is inbegrepen in Microsoft 365. Deze is al ingesteld. Met Office-berichtversleuteling kan uw organisatie versleutelde e-mailberichten verzenden en ontvangen tussen personen binnen en buiten uw organisatie. Office 365-berichtversleuteling werkt met Outlook.com, Yahoo!, Gmail en andere e-mailservices. Versleuteling van e-mailberichten zorgt ervoor dat alleen beoogde geadresseerden de inhoud van berichten kunnen bekijken.

Office-berichtversleuteling biedt twee beveiligingsopties bij het verzenden van e-mail:

- Niet doorsturen

- Versleutelen

Uw organisatie heeft mogelijk extra opties geconfigureerd voor het toepassen van een label op e-mailberichten, zoals Vertrouwelijk.

### <a name="to-send-protected-email"></a>Beveiligde e-mail verzenden

Selecteer in Outlook voor pc Opties in **het** e-mailbericht en kies **machtigingen.**

![E-mailberichtversleuteling in Outlook](../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639a.png)

Selecteer Outlook.com in **de e-mail.** De standaardbeveiliging is **Niet doorsturen.** Als u dit wilt wijzigen in versleutelen, **selecteert u Machtigingen** \> **wijzigen.**

![E-mailberichtversleuteling in Outlook.com](../../media/329ccf50-f6b1-4fb8-b249-60b907a82b7e.png)

### <a name="to-receive-encrypted-email"></a>Versleutelde e-mail ontvangen

Als de geadresseerde Outlook 2013 of Outlook 2016 en een Microsoft-e-mailaccount heeft, ziet deze een waarschuwing over de beperkte machtigingen voor het item in het leesvenster. Nadat het bericht is geopend, kan de geadresseerde het bericht op dezelfde als alle andere weergeven.

Als de geadresseerde een andere e-mailclient of een ander e-mailaccount gebruikt, zoals Gmail of Yahoo, ziet deze een koppeling waarmee de ontvanger zich kan aanmelden om het e-mailbericht te lezen of een time passcode kan aanvragen om het bericht in een webbrowser te bekijken. Als gebruikers de e-mail niet ontvangen, laat u hen de map Ongewenste e-mail controleren.

Zie Versleutelde berichten verzenden, weergeven en [beantwoorden in Outlook voor pc voor meer informatie.](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980)

## <a name="8-protect-your-email-from-phishing-attacks"></a>8. Uw e-mail beschermen tegen phishing-aanvallen
<a name="phishing"> </a>

Als u een of meer aangepaste domeinen hebt geconfigureerd voor uw Microsoft 365-omgeving, kunt u gerichte beveiliging tegen phishing instellen. Anti-phishingbeveiliging, een onderdeel van Microsoft Defender voor Office 365, kan uw organisatie helpen beschermen tegen kwaadaardige imitatie-phishing-aanvallen en andere phishing-aanvallen. Als u geen aangepast domein hebt geconfigureerd, hoeft u dit niet te doen.

Het is raadzaam om aan de slag te gaan met deze beveiliging door een beleid te maken ter bescherming van uw belangrijkste gebruikers en uw aangepaste domein.

![Een anti-phishingbeleid maken in Microsoft Defender voor Office 365](../../media/security-and-compliance-center.png)

Als u een anti-phishingbeleid wilt maken in Defender voor Office 365, bekijkt u een [korte trainingsvideo](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)of volgt u de volgende stappen:

1. Ga naar <https://protection.office.com>.

2. Selecteer beleid in het & compliancecentrum aan de linkerkant, onder **Bedreigingsbeheer.**

3. Selecteer **Anti-phishing** op de pagina Beleid.

4. Selecteer + Maken op de **anti-phishing-pagina.** Een wizard start die u stap voor stap door het definiëren van uw anti-phishingbeleid.

5. Geef de naam, beschrijving en instellingen voor uw beleid op zoals wordt aanbevolen in de onderstaande grafiek. Zie [meer informatie over anti-phishingbeleid in de opties van Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies) voor meer informatie.

6. Nadat u de instellingen hebt gecontroleerd, **selecteert** u Dit beleid maken of **Opslaan,** waar van toepassing.

|Instelling of optie|Aanbevolen instelling|
|---|---|
|Naam|Domein en meest waardevolle campagnemedewerkers|
|Beschrijving|Zorg ervoor dat het belangrijkste personeel en ons domein niet worden gemitmiteerd.|
|Gebruikers toevoegen om te beveiligen|Selecteer **+ Een voorwaarde toevoegen. De geadresseerde is.** Typ gebruikersnamen of voer het e-mailadres in van de kandidaat, campagnemanager en andere belangrijke personeelsleden. U kunt maximaal 20 interne en externe adressen toevoegen die u wilt beveiligen tegen imitatie.|
|Domeinen toevoegen om te beveiligen|Selecteer **+ Een voorwaarde toevoegen. Het domein van de ontvanger is.** Voer het aangepaste domein in dat is gekoppeld aan uw Microsoft 365-abonnement, als u dit hebt gedefinieerd. U kunt meer dan één domein invoeren.|
|Acties kiezen|Als e-mail wordt verzonden door een gemitmiteerde gebruiker: selecteer Bericht omleiden naar een ander e-mailadres **en** typ vervolgens het e-mailadres van de beveiligingsbeheerder. bijvoorbeeld securityadmin@contoso.com. <br/> Als e-mail wordt verzonden door een gemitmiteerd domein: selecteer **Quarantainebericht.**|
|Postvakinformatie|Postvakinformatie wordt standaard geselecteerd wanneer u een nieuw anti-phishingbeleid maakt. Laat deze instelling **aan voor** de beste resultaten.|
|Vertrouwde afzenders en domeinen toevoegen|Definieer in dit voorbeeld geen overschrijvingen.|
|Toegepast op|Selecteer **het domein van de ontvanger.** Selecteer **Onder Een van deze opties** de optie **Kiezen.** Selecteer **+ Toevoegen.** Schakel het selectievakje naast de naam van het domein in, bijvoorbeeld contoso.com, in de lijst en selecteer vervolgens **Toevoegen.** Selecteer **Gereed**.|
|

Zie Anti-phishingbeleid instellen [in Defender voor Office 365 voor meer informatie.](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-atp-anti-phishing-policies)

## <a name="9-protect-against-malicious-attachments-and-files-with-safe-attachments"></a>9: Beveiligen tegen schadelijke bijlagen en bestanden met veilige bijlagen
<a name="atp"> </a>

Personen verzenden, ontvangen en delen regelmatig bijlagen, zoals documenten, presentaties, spreadsheets en meer. Het is niet altijd eenvoudig om te bepalen of een bijlage veilig of schadelijk is door alleen maar naar een e-mailbericht te kijken. Microsoft Defender voor Office 365 bevat beveiliging tegen veilige bijlagen, maar deze beveiliging is niet standaard ingeschakeld. U wordt aangeraden een nieuwe regel te maken om deze beveiliging te gebruiken. Deze beveiliging geldt ook voor bestanden in SharePoint, OneDrive en Microsoft Teams.

Als u een veilig bijlagebeleid wilt maken, bekijkt u een [korte trainingsvideo](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)of volgt u de volgende stappen:

1. Meld u <https://protection.office.com> aan met uw beheerdersaccount.

2. Selecteer beleid in het & compliancecentrum aan de linkerkant, onder **Bedreigingsbeheer.**

3. Selecteer Veilige bijlagen op de pagina **Beleid.**

4. Pas deze beveiliging breed toe op de pagina Veilige bijlagen door het selectievakje ATP in te schakel voor **SharePoint, OneDrive en Microsoft Teams** in.

5. Selecteer **+** deze optie om een nieuw beleid te maken.

6. Pas de instellingen in de volgende tabel toe.

7. Nadat u de instellingen hebt gecontroleerd, **selecteert** u Dit beleid maken of **Opslaan,** waar van toepassing.

|Instelling of optie|Aanbevolen instelling|
|---|---|
|Naam|Huidige en toekomstige e-mailberichten blokkeren met gedetecteerde malware.|
|Beschrijving|Huidige en toekomstige e-mailberichten en bijlagen blokkeren met gedetecteerde malware.|
|Onbekende malwarereactie bijlagen opslaan|Blokkeren **selecteren: de huidige en toekomstige e-mailberichten en bijlagen met gedetecteerde malware blokkeren.**|
|Bijlage omleiden bij detectie|Omleiding inschakelen (selecteer dit vakje) <br/> Voer het beheerdersaccount of het postvak in voor quarantaine. <br/> De bovenstaande selectie toepassen als er malware wordt gescand op bijlagen of als er een fout optreedt (selecteer dit vakje).|
|Toegepast op|Het domein van de ontvanger is . . . selecteert u uw domein.|
|

Zie Anti-phishingbeleid instellen [in Defender voor Office 365 voor meer informatie.](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-atp-anti-phishing-policies)

## <a name="10-protect-against-phishing-attacks-with-safe-links"></a>10: Beschermen tegen phishing-aanvallen met veilige koppelingen
<a name="phishingatp"> </a>

Hackers verbergen soms schadelijke websites in koppelingen in e-mail of andere bestanden. Veilige koppelingen, onderdeel van Microsoft Defender voor Office 365, kunnen uw organisatie helpen beschermen door middel van tijd-van-klik-verificatie van webadressen (URL's) in e-mailberichten en Office-documenten. Beveiliging is gedefinieerd via beleidsregels voor veilige koppelingen.

U wordt aangeraden het volgende te doen:

- Wijzig het standaardbeleid om de beveiliging te verhogen.

- Voeg een nieuw beleid toe dat is gericht op alle geadresseerden in uw domein.

Als u veilige koppelingen wilt weergeven, bekijkt u een [korte trainingsvideo](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)of volgt u de volgende stappen:

1. Meld u <https://protection.office.com> aan met uw beheerdersaccount.

2. Selecteer beleid in het & compliancecentrum aan de linkerkant, onder **Bedreigingsbeheer.**

3. Selecteer Veilige koppelingen op de **pagina Beleid.**

Het standaardbeleid wijzigen:

1. Dubbelklik op de pagina Veilige koppelingen onder Beleid dat **van toepassing** is op de hele organisatie op **Het** standaardbeleid.

2. Voer onder Instellingen die van toepassing zijn op inhoud in **Office 365** een URL in die _moet_ worden geblokkeerd, zoals example.com en **+** selecteer.

3. Selecteer **onder** Instellingen die van toepassing zijn op inhoud behalve e-mail, **Office 365-toepassingen,** Houd niet bij wanneer gebruikers op veilige koppelingen klikken en laat gebruikers niet door veilige koppelingen naar de oorspronkelijke URL **klikken.**

4. Kies **Opslaan**.

Een nieuw beleid maken dat is gericht op alle geadresseerden in uw domein:

1. Selecteer op de pagina Veilige koppelingen onder Beleid **dat** van toepassing is op specifieke geadresseerden om **+** een nieuw beleid te maken.

2. Pas de instellingen uit de volgende tabel toe.

3. Kies **Opslaan**.

|Instelling of optie|Aanbevolen instelling|
|---|---|
|Naam|Beleid voor veilige koppelingen voor alle geadresseerden in het domein|
|De actie selecteren voor onbekende, potentieel schadelijke URL's in berichten|Select **On : URL's worden herschreven en gecontroleerd** aan de hand van een lijst met bekende schadelijke koppelingen wanneer de gebruiker op de koppeling klikt.|
|Real-time URL's scannen op verdachte koppelingen en koppelingen die naar bestanden wijzen|Selecteer dit vakje.|
|Toegepast op|Het domein van de ontvanger is . . . selecteert u uw domein.|
|

Zie Veilige koppelingen [in Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)voor meer informatie.
