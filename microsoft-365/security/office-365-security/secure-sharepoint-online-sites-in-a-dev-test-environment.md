---
title: Beveiligde SharePoint Online-sites in een ontwikkel-/testomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/26/2019
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 06af70f3-e7dc-4ee2-a385-fb4d61a5e93b
description: 'Samenvatting: maak gevoelige en zeer vertrouwelijke SharePoint Online-teamsites in een ontwikkel-/testomgeving.'
ms.openlocfilehash: 6294daa943c3815b86a9e12154901ed0b58d5e8d
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809873"
---
# <a name="secure-sharepoint-online-sites-in-a-devtest-environment"></a>Beveiligde SharePoint Online-sites in een ontwikkel-/testomgeving

In dit artikel vindt u stapsgewijze instructies voor het maken van een ontwikkel-/testomgeving met gevoelige en zeer vertrouwelijke SharePoint-sites met de oplossing [Beveiligde SharePoint Online-sites en bestanden](secure-sharepoint-online-sites-and-files.md).

![Gevoelige en zeer vertrouwelijke SharePoint Online-sites voor bestanden.](../../media/sensitive-highly-confidential-sp-sites-dev-test.png)

Gebruik deze ontwikkel-/testomgeving om instellingen te testen en te verfijnen voor uw specifieke behoeften voordat u dit soort teamsites in de productie implementeert.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: uw Microsoft 365 Enterprise-testomgeving uitbouwen

Als u enkel gevoelige en zeer vertrouwelijke teamsites op een eenvoudige manier wilt testen met de minimale vereisten, volgt u de instructies in [Lichtgewicht basisconfiguratie](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).

Als u gevoelige en zeer vertrouwelijke teamsites in een gesimuleerde onderneming wilt testen, volgt u de instructies in [Wachtwoord-hash-synchronisatie](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).

> [!NOTE]
> Voor het testen van gevoelige en zeer vertrouwelijke teamsites hebt u geen testomgeving van een gesimuleerde onderneming nodig. Deze omgeving bevat een gesimuleerd intranet dat verbonden is met internet en een adreslijstsynchronisatie van een AD DS-forest (Active Directory Domain Services). Dit wordt hier als optie gegeven, zodat u gevoelige en zeer vertrouwelijke teamsites kunt testen en er mee kunt experimenteren in een omgeving die een standaardorganisatie voorstelt.

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a>Fase 2: uw Microsoft Azure AD-groepen (Active Directory) en -gebruikers maken en configureren

In deze fase maakt en configureert u de Microsoft Azure AD-groepen en -gebruikers voor uw fictieve organisatie.

Maak eerst twee groepen voor een standaardorganisatie met de Microsoft Azure Portal.

1. Open een afzonderlijk tabblad in uw browser en ga naar de Microsoft Azure Portal op [https://portal.azure.com](https://portal.azure.com). Indien nodig meldt u zich aan met de inloggegevens van het algemene beheerdersaccount van uw proefabonnement of uw betaald abonnement op Microsoft 365 E5.

2. Klik in de Microsoft Azure-portal op **Microsoft Azure Active Directory > Groepen**.

3. Klik in de blade **Groepen: Alle groepen** op **Nieuwe groep**.

4. In de blade **Groep**:

   - Selecteer **Beveiliging** bij **Groepstype**.

   - Typ **C-Suite** bij **Naam**.

   - Selecteer **Toegewezen** bij **Lidmaatschapstype**.

5. Klik op **Maken** en sluit vervolgens de blade**Groep**.

6. Herhaal stappen 3-5 voor een nieuwe groep met de naam **Marketingpersoneel**.

Vervolgens configureert u automatische licentieverlening, zodat de leden van uw groepen automatisch licenties krijgen toegewezen voor uw Office 365- en EMS-abonnementen.

1. Klik in de Microsoft Azure-portal op **Microsoft Azure Active Directory > Licenties > Alle producten**.

2. Selecteer in de lijst **Microsoft 365 Enterprise E5** en klik vervolgens op **Toewijzen**.

3. Klik in de blade **Licentie toewijzen** op ** Gebruikers en groepen**.

4. In de lijst met groepen selecteert u het volgende:

   - C-Suite

   - Marketingpersoneel

5. Klik op **Selecteren** en klik vervolgens op **Toewijzen**.

6. Sluit het tabblad Azure Portal in uw browser.

Vervolgens maakt u [Verbinding met de Windows PowerShell voor Graph-module van Microsoft Azure Active Directory](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).

Vul de naam van uw organisatie, uw locatie en een gemeenschappelijk wachtwoord in en voer vervolgens deze opdrachten uit in de opdrachtprompt van Windows PowerShell of de Integrated Scripting Environment (ISE) om gebruikersaccounts te maken en toe te voegen aan hun groepen:

```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO")
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Marketing staff"
$userNames=@("Marketing1", "Marketing2")
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> U gebruikt hier een gemeenschappelijk wachtwoord voor de automatisering en het configuratiesgemak in een ontwikkel-/testomgeving. Uiteraard wordt dit sterk afgeraden voor productieabonnementen.

Volg deze stappen om te controleren of de licentieverlening op groepsbasis correct werkt.

1. Klik in het tabblad **Microsoft Office voor Thuisgebruik** van uw browser op de tegel **Beheerder**.

2. Klik in het nieuwe tabblad **Microsoft 365-beheercentrum** van uw browser op **Gebruikers**.

3. Klik in de lijst met gebruikers op **CEO**.

4. In het deelvenster met de eigenschappen van het gebruikersaccount van de **CEO** controleert u dat dit account de licentie **Microsoft 365 Enterprise E5** heeft toegewezen gekregen (bij **Productlicenties**).

## <a name="phase-3-create-office-365-retention-labels"></a>Fase 3: retentielabels voor Office 365 maken

In deze fase maakt u de retentielabels voor documenten in uw SharePoint-teamsites.

1. Meld u aan bij het [Microsoft 365-compliancecentrum](https://compliance.microsoft.com) met uw algemeen beheerdersaccount.

2. Klik op het tabblad **Start: Microsoft 365-compliancecentrum** van uw browser op **Classificaties > Labels**.

3. Klik op **Retentielabels > Een label maken**.

4. Typ in het deelvenster **Uw label een naam geven** **Gevoelig** in **Uw label een naam geven** en klik vervolgens op **Volgende**.

5. Klik in het deelvenster **Bestandsplandescriptors** op **Volgende**.

6. Indien nodig kunt u in het deelvenster **Labelinstellingen** de **Retentie** instellen op **Aan** en vervolgens klikt u op **Volgende**.

7. Klik in het deelvenster **Uw instellingen controleren** op **Label maken**.

8. Herhaal stappen 3-7 voor een extra retentielabel met de naam **Zeer vertrouwelijk**.

9. Klik in het deelvenster **Start > Labels** op **Labels publiceren**.

10. Klik in het deelvenster **Labels kiezen om te publiceren** op de optie **Labels kiezen om te publiceren**.

11. Klik op de deelvenster **Labels kiezen** op **Toevoegen** en selecteer alle vier de labels.

12. Klik op **Gereed**.

13. Klik in het deelvenster **Labels kiezen om te publiceren** op **Volgende**.

14. Klik in het deelvenster **Locaties kiezen** op **Volgende**.

15. Typ in het deelvenster **Uw beleid een naam geven** **Voorbeeldorganisatie** in **Naam** en klik vervolgens op **Volgende**.

16. Klik in het deelvenster **Uw instellingen controleren** op **Labels publiceren** en klik vervolgens op **Sluiten**.

## <a name="phase-4-create-your-team-sites"></a>Fase 4: uw teamsites maken

In deze fase maakt en configureert u gevoelige en zeer vertrouwelijke teamsites voor uw voorbeeldorganisatie.

### <a name="sensitive-team-site-for-marketing-campaigns"></a>Gevoelige teamsite voor marketingcampagnes

Maak eerst een gevoelige teamsite met voor leden van de marketinggroep waarin zij kunnen samenwerken aan lopende marketingcampagnes.

1. [Maak een nieuwe privéteamsite](https://support.office.com/article/ef10c1e7-15f3-42a3-98aa-b5972711777d) met de naam **Marketingcampagnes**.

2. Klik op de werkbalk van de SharePoint-teamsite op het pictogram Instellingen en vervolgens op **Sitemachtigingen**.

3. Klik in het deelvenster **Site-machtigingen**, onder **Instellingen voor delen** op **Instellingen voor delen wijzigen**.

4. Kies onder **Machtigingen voor delen** de optie **Alleen site-eigenaren kunnen bestanden, mappen en de site delen** en klik vervolgens op **Opslaan**.

Configureer vervolgens de documentenmap van de SharePoint-teamsite Marketingcampagnes voor het retentielabel Gevoelig.

1. Klik op het tabblad **Start: Marketingcampagnes** van uw browser op **Documenten**.

2. Klik op het pictogram Instellingen en daarna op **Bibliotheekinstellingen**.

3. Klik onder **Machtigingen en beheer** op **Label op deze bibliotheek toepassen**.

4. Selecteer in **Instellingen: Label toepassen** de optie **Gevoelig**en klik vervolgens op **Opslaan**.

Configureer vervolgens een beleid voor de preventie van gegevensverlies (DLP) waardoor gebruikers worden gewaarschuwd wanneer ze een document met het label Gevoelig buiten de organisatie delen, waaronder documenten op de site Marketingcampagnes.

1. Meld u aan bij het [Microsoft 365-compliancecentrum](https://compliance.microsoft.com/) met uw algemeen beheerdersaccount.

2. Klik op het nieuwe tabblad **Microsoft 365-compliance** in uw browser op **Beleid > Preventie van gegevensverlies**.

3. Klik in het deelvenster **Start > preventie van gegevensverlies** op **Een beleid maken**.

4. Klik in het deelvenster **Met een sjabloon beginnen of een aangepast beleid maken** op **Aangepast**en klik vervolgens op **Volgende**.

5. Typ in het deelvenster **Uw beleid een naam geven** **Label Gevoelig voor SharePoint-sites** in **Naam**en klik vervolgens op **Volgende**.

6. Klik in het deelvenster **Locaties kiezen** op **Laat mij specifieke locaties kiezen** en klik vervolgens op **Volgende**.

7. Schakel in de lijst met locaties de locaties **Exchange-e-mail**, **OneDrive-accounts** en **chat- en kanaalberichten in Teams** uit en klik vervolgens op **Volgende**.

8. Klik in het deelvenster **Het type inhoud aanpassen dat u wilt beveiligen** op **Bewerken**.

9. Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Toevoegen** in de vervolgkeuzelijst en klik vervolgens op **Retentielabels**.

10. Klik in het deelvenster **Retentielabels** op **Toevoegen**, selecteer het label **Gevoelig**, klik op **Toevoegen**en klik vervolgens op **Gereed**.

11. Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Opslaan**.

12. Klik in het deelvenster **Het type inhoud aanpassen dat u wilt beveiligen** op **Volgende**.

13. Klik in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** op **De tip en de e-mail aanpassen**.

14. Klik in het deelvenster **Beleidstips en e-mailmeldingen aanpassen** op **tekst voor beleidstip aanpassen**.

15. Typ of plak in het tekstvak de volgende tekst:

    Als u wilt delen met een gebruiker buiten de organisatie downloadt en opent u het bestand. Klik op Bestand, vervolgens op Document beveiligen en daarna op Versleutelen met wachtwoord en geef tot slot een sterk wachtwoord op. Stuur het wachtwoord in een afzonderlijk e-mailbericht of via een ander communicatiemiddel.

16. Klik op **OK**.

17. Klik in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** op **Volgende**.

18. Klik in het deelvenster **Wilt u het beleid inschakelen of eerst testen?** op **Ja, schakel het meteen in** en klik vervolgens op **Volgende**.

19. Klik in het deelvenster **Uw instellingen controleren** op **Maken** en klik vervolgens op **Sluiten**.

### <a name="company-strategy-team-site"></a>Teamsite Bedrijfsstrategie

Maak eerst u een zeer vertrouwelijk teamsite voor het senior leiderschapsteam zodat zij kunnen samenwerken aan de bedrijfsstrategie.

1. [Maak een nieuwe privéteamsite](https://support.office.com/article/ef10c1e7-15f3-42a3-98aa-b5972711777d) met de naam **Bedrijfsstrategie**.
2. Klik op de werkbalk van de SharePoint-teamsite op het pictogram Instellingen en vervolgens op **Sitemachtigingen**.

3. Klik in het deelvenster **Site-machtigingen**, onder **Instellingen voor delen** op **Instellingen voor delen wijzigen**.

4. Kies onder **Machtigingen voor delen**, **Alleen site-eigenaren kunnen bestanden, mappen en de site delen**.

5. Schakel **Toegangsaanvragen toestaan** uit en klik op **Opslaan**.

Configureer vervolgens de documentenmap van de SharePoint-teamsite Bedrijfsstrategie voor het label Zeer vertrouwelijk.

1. Klik op het tabblad **Start: Bedrijfsstrategie** van uw browser op **Documenten**.

2. Klik op het pictogram Instellingen en daarna op **Bibliotheekinstellingen**.

3. Klik onder **Machtigingen en beheer** op **Label op deze bibliotheek toepassen**.

4. Selecteer in **Instellingen: label toepassen** de optie **Zeer vertrouwelijk**en klik vervolgens op **Opslaan**.

Configureer vervolgens een DLP-beleid waarbij gebruikers worden geblokkeerd wanneer ze een document met het label Zeer vertrouwelijk buiten de organisatie delen, waaronder documenten van de Bedrijfsstrategiesite.

1. Meld u aan bij het [Microsoft 365-compliancecentrum](https://compliance.microsoft.com/) met uw algemeen beheerdersaccount.

2. Klik op het nieuwe tabblad **Microsoft 365-compliance** in uw browser op **Beleid > Preventie van gegevensverlies**.

3. Klik in het deelvenster **Start > preventie van gegevensverlies** op **Een beleid maken**.

4. Klik in het deelvenster **Met een sjabloon beginnen of een aangepast beleid maken** op **Aangepast**en klik vervolgens op **Volgende**.

5. Typ in het deelvenster **Uw beleid een naam geven** **Label Zeer vertrouwelijk voor SharePoint-sites** in **Naam**en klik vervolgens op **Volgende**.

6. Klik in het deelvenster **Locaties kiezen** op **Laat mij specifieke locaties kiezen** en klik vervolgens op **Volgende**.

7. Schakel in de lijst met locaties de locaties **Exchange-e-mail**, **OneDrive-accounts** en **chat- en kanaalberichten in Teams** uit en klik vervolgens op **Volgende**.

8. Klik in het deelvenster **Het type inhoud aanpassen dat u wilt beveiligen** op **Bewerken**.

9. Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Toevoegen** in de vervolgkeuzelijst en klik vervolgens op **Retentielabels**.

10. Klik in het deelvenster **Retentielabels** op **Toevoegen**, selecteer het label **Zeer Vertrouwelijk**, klik op **Toevoegen**en klik vervolgens op **Gereed**.

11. Klik in het deelvenster **Kies de typen inhoud die u wilt beveiligen** op **Opslaan**.

12. Klik in het deelvenster **Het type inhoud aanpassen dat u wilt beveiligen** op **Volgende**.

13. Klik in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** op **De tip en de e-mail aanpassen**.

14. Klik in het deelvenster **Beleidstips en e-mailmeldingen aanpassen** op **tekst voor beleidstip aanpassen**.

15. Typ of plak in het tekstvak de volgende tekst:

    Als u wilt delen met een gebruiker buiten de organisatie downloadt en opent u het bestand. Klik op Bestand, vervolgens op Document beveiligen en daarna op Versleutelen met wachtwoord en geef tot slot een sterk wachtwoord op. Stuur het wachtwoord in een afzonderlijk e-mailbericht of via een ander communicatiemiddel.

16. Klik op **OK**.

17. Klik in het deelvenster **Wilt u het beleid inschakelen of eerst testen?** op **Ja, schakel het meteen in** en klik vervolgens op **Volgende**.

18. Klik in het deelvenster **Wilt u het beleid inschakelen of eerst testen?** op **Ja, schakel het meteen in** en klik vervolgens op **Volgende**.

19. Klik in het deelvenster **Uw instellingen controleren** op **Maken** en klik vervolgens op **Sluiten**.

Gebruik [deze instructies](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) om een gevoeligheidslabel met de volgende instellingen te configureren:

- De naam van het label is Bedrijfsstrategie

- Versleuteling is ingeschakeld.

- De groep Bedrijfsstrategie heeft cocreatie-machtigingen

Publiceer na het maken het nieuwe label. Als u zich aanmeldt als lid van de groep Bedrijfsstrategie ziet u het nieuwe label in de optie Gevoeligheid op de werkbalk Start van Word, Excel en PowerPoint. Selecteer het label Bedrijfsstrategie bij de optie Gevoeligheid om het label aan een bestand toe te wijzen.

Bestanden in het documentgedeelte van de SharePoint-site Bedrijfsstrategie krijgen het bewaarlabel Zeer vertrouwelijk toegewezen en zijn onderworpen aan het geconfigureerde DLP-beleid. Aan bestanden kan ook het gevoeligheidslabel Bedrijfsstrategie worden toegewezen.

Hier vindt u de uiteindelijke configuratie voor de teamsites Marketingcampagnes en Bedrijfsstrategie.

![Gevoelige en zeer vertrouwelijke SharePoint Online-sites voor bestanden.](../../media/sensitive-highly-confidential-sp-sites-dev-test.png)

## <a name="next-step"></a>Volgende stap

Wanneer u klaar bent voor productie-implementatie van beveiligde SharePoint Online-sites, raadpleegt u [Beveiligde SharePoint Online-sites en bestanden](secure-sharepoint-online-sites-and-files.md) voor meer informatie en koppelingen naar artikelen met stapsgewijze implementatie.

## <a name="see-also"></a>Zie ook

[Cloud adoption and hybrid solutions](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions) (Overstappen op de cloud en hybride oplossingen)

[Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) (Beveiligingsrichtlijnen van Microsoft voor politieke campagnes, non-profitorganisaties en andere agile organisaties)
