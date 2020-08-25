---
title: Reageren op een gehackt e-mailaccount
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Lees hoe u een gehackt e-mailaccount kunt herkennen en hierop kunt reageren met behulp van de hulpmiddelen die beschikbaar zijn in Microsoft 365.
ms.openlocfilehash: cfd20b0d5e6e13343346761b9b909a333b9a6ff5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827515"
---
# <a name="responding-to-a-compromised-email-account"></a>Reageren op een gehackt e-mailaccount

**Overzicht** Lees hoe u een gehackt e-mailaccount in Microsoft 365 kunt herkennen en hierop kunt reageren

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a>Wat is een gehackt e-mailaccount in Microsoft 365?

Toegang tot Microsoft 365-postvakken, -gegevens en andere services wordt geregeld door het gebruik van referenties, zoals een gebruikersnaam en wachtwoord of pincode. Als iemand anders dan de bedoelde gebruiker die referenties steelt, worden de gestolen referenties geacht te zijn gehackt. Hiermee kan de hacker zich aanmelden als de oorspronkelijke gebruiker en illegale acties uitvoeren.
Met de gestolen referenties kan de hacker toegang krijgen tot het Microsoft 365-postvak, SharePoint-mappen of bestanden in de OneDrive van de gebruiker. Een actie die vaak wordt gezien, is dat de hacker e-mails verzendt als de oorspronkelijke gebruiker naar geadresseerden binnen en buiten de organisatie. Wanneer de hacker gegevens naar externe geadresseerden stuurt, wordt dit gegevensexfiltratie genoemd.

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a>Symptomen van een gehackt Microsoft-e-mailaccount

Gebruikers kunnen ongebruikelijke activiteiten in hun Microsoft 365-postvakken opmerken en melden. Hier volgen enkele veelvoorkomende symptomen:

- Verdachte activiteiten, zoals ontbrekende of verwijderde e-mails.

- Het is mogelijk dat andere gebruikers e-mails ontvangen van het gehackte account, zonder dat de desbetreffende e-mail aanwezig is in de map met **Verzonden items** van de afzender.

- De aanwezigheid van regels voor Postvak IN die niet zijn aangemaakt door de bedoelde gebruiker of door de beheerder. Met deze regels kunnen e-mails automatisch worden doorgestuurd naar onbekende adressen of worden deze verplaatst naar de mappen met **Notities**, **Ongewenste e-mail** of **RSS-abonnementen**.

- De weergavenaam van de gebruiker kan worden gewijzigd in de algemene adreslijst.

- Het postvak van de gebruiker is geblokkeerd voor het verzenden van e-mails.

- De mappen met Verzonden of Verwijderde items in Microsoft Outlook of de webversie van Outlook (voorheen bekend als Outlook Web App) bevatten berichten die vaak worden gestuurd door gehackte accounts, zoals "Ik zit vast in Londen, stuur geld".

- Ongebruikelijke profielwijzigingen, zoals de naam, het telefoonnummer of de postcode zijn bijgewerkt.

- Ongebruikelijke referentiewijzigingen, zoals meerdere wachtwoordwijzigingen.

- Het doorsturen van e-mail is onlangs toegevoegd.

- Er is onlangs een ongebruikelijke handtekening toegevoegd, zoals een valse bankhandtekening of een handtekening voor voorgeschreven medicijnen.

Als een gebruiker een van de bovenstaande problemen meldt, moet u nader onderzoek doen. Het Microsoft 365-beveiligings- en compliancecentrum en de Azure-portal bieden hulpmiddelen voor het onderzoeken van de activiteiten van een gebruikersaccount waarvan u vermoedt dat het niet meer betrouwbaar is.

- **Geïntegreerde auditlogboeken in het Beveiligings- en compliancecentrum**: Bekijk alle activiteiten van het verdachte account door de resultaten te filteren op het datumbereik van vlak voordat de verdachte activiteiten zich voordeden tot nu. Filter niet op de activiteiten tijdens het zoeken.

- **Auditlogboeken voor beheerders in het Exchange-beheercentrum (EAC)**: In Exchange Online kunt u het Exchange-beheercentrum gebruiken om vermeldingen te zoeken en weer te geven in het auditlogboek van de beheerder. In het auditlogboek van de beheerder worden specifieke acties vastgelegd, gebaseerd op Exchange Online PowerShell-cmdlets, die worden uitgevoerd door beheerders en gebruikers aan wie beheerdersbevoegdheden zijn toegewezen. Vermeldingen in het auditlogboek van de beheerder bieden informatie over welke cmdlet is uitgevoerd, welke parameters zijn gebruikt, wie de cmdlet heeft uitgevoerd en welke objecten zijn beïnvloed.

- **Azure AD-aanmeldingslogboeken en andere risicorapporten in de Azure AD-portal**: Bekijk de waarden in deze kolommen:

  - Controleer het IP-adres
  - aanmeldingslocaties
  - aanmeldingstijden
  - geslaagde of misluke aanmeldingen

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a>E-mailfunctionaliteit van een vermoedelijk gehackt Microsoft 365-account en -postvak beveiligen en herstellen

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

Zelfs nadat u opnieuw toegang heeft gekregen tot uw account, is het mogelijk dat de hacker verborgen toegangsmogelijkheden heeft aangemaakt waardoor de hacker beheer van het account kan hervatten.

U moet de volgende stappen uitvoeren om weer toegang te krijgen tot uw account. Het is verstandig dit zo snel mogelijk te doen, zodat de hacker niet opnieuw controle over uw account kan krijgen. Met deze stappen verwijdert u alle verborgen toegangsmogelijkheden die de hacker mogelijk aan uw account heeft toegevoegd. Nadat u deze stappen hebt uitgevoerd, raden we u aan een virusscan uit te voeren om er zeker van te zijn dat uw computer niet gehackt is.

### <a name="step-1-reset-the-users-password"></a>Stap 1 Stel het gebruikerswachtwoord opnieuw in

Volg de procedures in [Een zakelijk wachtwoord opnieuw instellen voor iemand](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords#reset-my-admin-password).

> [!IMPORTANT]
>
> - Stuur het nieuwe wachtwoord niet via e-mail naar de bedoelde gebruiker, aangezien de hacker op dit moment nog steeds toegang tot het postvak heeft.
>
> - Zorg ervoor dat het wachtwoord sterk is en dat het hoofdletters en kleine letters, tenminste één cijfer en tenminste één speciaal teken bevat.
>
> - Gebruik uw laatste vijf wachtwoorden niet opnieuw. Hoewel u volgens de vereisten voor wachtwoordgeschiedenis een recenter wachtwoord opnieuw kunt gebruiken, is het verstandig om iets te selecteren dat de hacker niet kan raden.
>
> - Als uw identiteit op locatie federatief is met Microsoft 365, moet u uw wachtwoord op locatie wijzigen en uw beheerder op de hoogte stellen van de aanval.
>
> - Vergeet niet om app-wachtwoorden bij te werken. App-wachtwoorden worden niet automatisch ingetrokken bij het opnieuw instellen van een wachtwoord voor een gebruikersaccount. De gebruiker moet bestaande app-wachtwoorden verwijderen en nieuwe app-wachtwoorden maken. Voor meer informatie, zie [App-wachtwoorden maken en verwijderen op de pagina Aanvullende beveiligingsverificatie](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).
>
> - We raden u ten zeerste aan om meervoudige verificatie in te schakelen om een inbreuk te voorkomen, met name voor accounts met beheerdersbevoegdheden. Voor meer informatie over MFA gaat u naar [Meervoudige verificatie instellen](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>Stap 2 E-mailadressen verwijderen die verdachte mails doorsturen

1. Het Microsoft 365-beheercentrum openen in <https://admin.microsoft.com>

2. Ga naar **Gebruikers** \> **Actieve gebruikers**. Zoek het desbetreffende gebruikersaccount en selecteer de gebruiker (rij) zonder het selectievakje in te schakelen.

3. Selecteer in de flyout met details, het tabblad **E-mail**.

4. Als de waarde in de sectie **E-mail doorsturen** is **Toegepast**, klikt u op **E-mail doorsturen beheren**. Schakel in de flyout **E-mail doorsturen beheren**, **Alle e-mailberichten naar dit postvak IN doorsturen** uit en klik vervolgens op **Wijzigingen opslaan**.

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>Stap 3 Alle verdachte regels voor Postvak IN uitschakelen

1. Meld u aan bij het postvak van de gebruiker met de webversie van Outlook.

2. Klik op het tandwielpictogram en klik op **Mail**.

3. Klik op **Regels voor postvak in en opruimen** en controleer de regels.

4. Blokkeer of verwijder alle verdachte regels.

### <a name="step-4-unblock-the-user-from-sending-mail"></a>Stap 4 De gebruiker opnieuw toestemming geven om mail te verzenden

Als het vermoedelijk gehackte postvak op illegale wijze is gebruikt voor het verzenden van ongewenste e-mail, is de kans groot dat het verzenden van mails vanuit dit postvak is geblokkeerd.

Om ervoor te zorgen dat er weer mails kunnen worden verzonden vanuit dit postvak, volgt u de procedures in [Een gebruiker verwijderen uit de portal voor gebruikers met beperkte rechten na het verzenden van ongewenste e-mail](removing-user-from-restricted-users-portal-after-spam.md).

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>Stap 5 Optioneel: Aanmelden bij het gebruikersaccount blokkeren

> [!IMPORTANT]
> U kunt ervoor zorgen dat er niet meer ingelogd kan worden bij het vermoedelijk gehackte account tot u ervan overtuigd bent dat het veilig is om de blokkering op te heffen.

1. Ga in het Microsoft 365-beheercentrum naar **Gebruikers** \> **Actieve gebruikers**.

2. Zoek en selecteer het gebruikersaccount, klik op ![Meer](../../media/ITPro-EAC-MoreOptionsIcon.png)en selecteer vervolgens **Aanmeldstatus bewerken**.

3. Selecteer in het deelvenster **Aanmelding blokkeren** de optie **Aanmelden van deze gebruiker blokkeren** en klik vervolgens op **Wijzigingen opslaan**.

4. Open het Exchange-Beheercentrum (SBV) op <admin.protection.outlook.com/ecp/> en ga naar **Geadresseerden > Postvakken**.

5. Zoek en selecteer de gebruiker. In het detailvenster voert u de volgende stappen uit:

   - Voer de volgende stappen uit in de sectie **Telefoon- en spraakfuncties** :

     - Selecteer **Exchange ActiveSync uitschakelen** en klik vervolgens op **Ja** in het waarschuwingsbericht.
     - Selecteer **OWA voor apparaten uitschakelen** en klik vervolgens op **Ja** in het waarschuwingsbericht.

   - Klik in de sectie **E-mailconnectiviteit** voor de webversie van Outlook op **Uitschakelen** en klik vervolgens op **Ja** in het waarschuwingsbericht.

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>Stap 6 Optioneel: Verwijder het vermoedelijk gehackte account uit alle beheerdersrollen.

> [!NOTE]
> Het lidmaatschap van de administratieve rolgroep kan worden hersteld nadat het account is beveiligd.

1. Meld u aan met een globale beheerdersaccount:

2. Voer de volgende stappen uit in het Microsoft 365-beheercentrum:

   1. Ga naar **Gebruikers** \> **Actieve gebruikers**.
   2. Zoek en selecteer het gebruikersaccount, klik op ![Meer](../../media/ITPro-EAC-MoreOptionsIcon.png) en selecteer vervolgens **Rollen beheren**.
   3. Verwijder alle beheerrollen die aan het account zijn toegewezen. Wanneer u gereed bent, klikt u op **Wijzigingen opslaan**.

3. Voer de volgende stappen uit in het beveiligings- en compliancecentrum op <https://protection.office.com>:

   Selecteer **Machtigingen**, selecteer elke rollengroep in de lijst en zoek het gebruikersaccount in de sectie **Leden** in de flyout met details. Als de rollengroep het gebruikersaccount bevat, voert u de volgende stappen uit:

   a. Klik op **Bewerken** naast **Leden**.
   b. Klik in de flyout **Bewerken van leden kiezen** op **Bewerken**.
   c. Selecteer in de flyout **Leden kiezen** het gebruikersaccount en klik vervolgens op **Verwijderen**. Wanneer u gereed bent, klikt u op **Gereed**, **Opslaan** en vervolgens op **Sluiten**.

4. Voer de volgende stappen uit in het Exchange-beheercentrum SBV via <admin.protection.outlook.com/ecp/>:

   Selecteer **Machtigingen**, selecteer elke rollengroep handmatig en controleer de gebruikersaccounts in de sectie **Leden** in het detailvenster.  Als de rollengroep het gebruikersaccount bevat, voert u de volgende stappen uit:

   a. Selecteer de rollengroep, klik op **Bewerken** ![Pictogram bewerken](../../media/ITPro-EAC-EditIcon.png).
   b. Selecteer in de sectie **Lid** het gebruikersaccount en klik vervolgens op **Verwijderen** ![Pictogram verwijderen](../../media/ITPro-EAC-RemoveIcon.gif). Wanneer u gereed bent, klikt u op **Opslaan**.

### <a name="step-7-optional-additional-precautionary-steps"></a>Stap 7 Optioneel: Extra voorzorgsmaatregelen

1. Zorg ervoor dat u uw verzonden items controleert. Het is verstandig om de personen in uw contactenlijst op de hoogte te stellen van het feit dat uw account is gehackt. De hacker heeft hen mogelijk om geld gevraagd, spoofing, bijvoorbeeld dat u zich in een ander land bevindt en geld nodig heeft, of het kan zijn dat de hacker een virus heeft verstuurd om ook hun computers te overnemen.

2. Een andere service die gebruik heeft gemaakt van dit Exchange-account als alternatief e-mailaccount kan ook gehackt zijn. Voer deze stappen eerst uit voor uw Microsoft 365-abonnement en voer ze vervolgens uit voor uw andere accounts.

3. Zorg ervoor dat uw contactgegevens, zoals telefoonnummers en adressen, correct zijn.

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Microsoft 365 beveiligen als een cybersecurity pro

Uw Microsoft 365-abonnement heeft een krachtige reeks aan beveiligingsmogelijkheden die u kunt gebruiken om uw gegevens en gebruikers te beschermen.  Gebruik de [Microsoft 365-roadmap voor beveiliging - Topprioriteiten voor de eerste 30 dagen, 90 dagen en verder](security-roadmap.md) om door Microsoft aanbevolen procedures voor het beveiligen van uw Microsoft 365-tenant te implementeren.

- Taken die in de eerste 30 dagen moeten worden uitgevoerd.  Deze hebben direct effect en weinig invloed op uw gebruikers.

- Taken die binnen 90 dagen moeten worden uitgevoerd. Deze nemen qua planning en implementatie iets meer tijd in beslag, maar zorgen voor aanzienlijke verbeteringen in uw beveiligingspostuur.

- Na 90 dagen. Deze verbeteringen zijn gebaseerd op de eerste 90 dagen.

## <a name="see-also"></a>Zie ook

- [Injectieaanvallen op Outlook-regels en aangepaste formulieren detecteren en verhelpen in Microsoft 365](detect-and-remediate-outlook-rules-forms-attack.md)

- [Internet Crime Complaint Center](https://www.ic3.gov/preventiontips.aspx)

- [Securities and Exchange Commission - "Phishing" fraude](https://www.sec.gov/investor/pubs/phishing.htm)

- Om ongewenste e-mailberichten rechtstreeks bij Microsoft en uw beheerder te melden, kunt u [De invoegtoepassing rapporteer bericht gebruiken](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
