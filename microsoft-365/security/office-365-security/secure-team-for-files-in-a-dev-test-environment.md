---
title: Veilige teams voor bestanden in een ontwikkel- en testomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 06af70f3-e7dc-4ee2-a385-fb4d61a5e93b
description: 'Samenvatting: maak gevoelige en zeer vertrouwelijke teams in Microsoft Teams voor bestanden in een ontwikkel-/testomgeving.'
ms.openlocfilehash: 5b3f5c74ac484eb00852d5756b3269fb7c8c6a5b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637966"
---
# <a name="secure-teams-for-files-in-a-devtest-environment"></a>Veilige teams voor bestanden in een ontwikkel-/testomgeving

Dit artikel bevat stapsgewijze instructies om een ontwikkel-/testomgeving te creëren met gevoelige en zeer vertrouwelijke teams voor de [beveiligde bestanden in Microsoft Teams](secure-files-in-teams.md)-oplossing.
  
![Gevoelige en zeer vertrouwelijke teams in Microsoft Teams voor bestanden.](../../media/sensitive-highly-confidential-teams-dev-test.png)
  
Gebruik deze ontwikkel-/testomgeving om te experimenteren en instellingen af te stemmen op uw specifieke behoeften voordat u dit soort teams in productie neemt.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: uw Microsoft 365 Enterprise-testomgeving uitbouwen

Als u alleen gevoelige en zeer vertrouwelijke teams op een eenvoudige manier wilt testen met de minimale vereisten, volgt u de instructies in [Lichtgewicht basisconfiguratie](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).

Als u gevoelige en zeer vertrouwelijke teams in een gesimuleerde onderneming wilt testen, volgt u de instructies in [Wachtwoord-hash-synchronisatie](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).

>[!Note]
>Voor het testen van gevoelige en zeer vertrouwelijke teams is de testomgeving van een gesimuleerde onderneming niet nodig. Deze omgeving bevat een gesimuleerd intranet dat verbonden is met internet en adreslijstsynchronisatie van een AD DS-forest (Active Directory Domain Services). Dit wordt hier als optie gegeven, zodat u gevoelige en zeer vertrouwelijke teams kunt testen en er mee kunt experimenteren in een omgeving die een standaardorganisatie voorstelt.
>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a>Fase 2: uw Azure AD-groepen (Active Directory) en -gebruikers maken en configureren

In deze fase maakt en configureert u de Microsoft Azure AD-groepen en -gebruikers voor uw fictieve organisatie.
  
Maak eerst twee groepen voor een standaardorganisatie met de Microsoft Azure Portal.
  
1. Open een afzonderlijk tabblad in uw browser en ga naar de Microsoft Azure Portal op [https://portal.azure.com](https://portal.azure.com). Indien nodig meldt u zich aan met de inloggegevens van het algemene beheerdersaccount van uw proefabonnement of uw betaald abonnement op Microsoft 365 E5.
    
2. Klik in de Microsoft Azure-portal op **Microsoft Azure Active Directory > Groepen**.
    
3. Klik in de blade **Groepen: Alle groepen** op **+ Nieuwe groep**.
    
4. In de blade **Groep**:
    
  - Selecteer **Beveiliging** bij **Groepstype**.
    
  - Typ **C-Suite** bij **Naam**.
    
  - Selecteer **Toegewezen** bij **Lidmaatschapstype**.
      
5. Klik op **Maken** en sluit vervolgens de blade**Groep**.
    
6.    Herhaal stappen 3-5 voor een nieuwe groep met de naam **Marketingpersoneel**.
    
Vervolgens configureert u automatische licentieverlening, zodat de leden van uw groepen automatisch licenties krijgen toegewezen voor uw Microsoft 365- en EMS-abonnementen.
  
1. Klik in de Microsoft Azure-portal op **licenties voor Azure Active Directory > alle producten**.
    
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
> U gebruikt hier een gemeenschappelijk wachtwoord voor automatisering en configuratiegemak in een ontwikkel-/testomgeving. Uiteraard wordt dit sterk afgeraden voor productieabonnementen. 
  
Volg deze stappen om te controleren of de licentieverlening op groepsbasis correct werkt.
  
1. Klik in het tabblad **Microsoft Office voor Thuisgebruik** van uw browser op de tegel **Beheerder**.
    
2. Klik in het nieuwe tabblad **Microsoft 365-beheercentrum** van uw browser op **Gebruikers**.
    
3. Klik in de lijst met gebruikers op **CEO**.
    
4. In het deelvenster met de eigenschappen van het gebruikersaccount van de **CEO** controleert u dat dit account de licentie **Microsoft 365 Enterprise E5** heeft toegewezen gekregen (bij **Productlicenties**).
    
## <a name="phase-3-create-retention-labels"></a>Fase 3: retentielabels maken

In deze fase maakt u de retentielabels voor de verschillende beveiligingsniveaus voor onderliggende documentenmappen van de SharePoint-site.

1. Meld u aan bij de [Microsoft 365-complianceportal](https://compliance.microsoft.com) met uw algemeen beheerdersaccount.
    
2. Klik op het tabblad **Start: Microsoft 365-compliancecentrum** van uw browser op **Classificaties > Labels**.
    
3. Klik op **Retentielabels > Een label maken**.
    
4. Typ in het deelvenster **Uw label een naam geven** **Vertrouwelijk** in **Uw label een naam geven** en klik vervolgens op **Volgende**.

5. Klik in het deelvenster **Bestandsplandescriptors** op **Volgende**.
    
6. Indien nodig kunt u in het deelvenster **Labelinstellingen** de **Retentie** instellen op **Aan** en vervolgens klikt u op **Volgende**.
    
7. Klik in het deelvenster **Uw instellingen controleren** op **Label maken**.
    
8. Herhaal stappen 3-7 voor een extra retentielabel met de naam **Zeer vertrouwelijk**.
    
9. Klik in het deelvenster **Start > Labels** op **Labels publiceren**.
    
10. Klik in het deelvenster **Labels kiezen om te publiceren** op de optie **Labels kiezen om te publiceren**.
    
11. Klik op het deelvenster **Labels kiezen** op **Toevoegen** en selecteer alle vier de labels.
    
12. Klik op **Gereed**.
    
13. Klik in het deelvenster **Labels kiezen om te publiceren** op **Volgende**.
    
14. Klik in het deelvenster **Locaties kiezen** op **Volgende**.
    
15. Typ in het deelvenster **Uw beleid een naam geven** **Voorbeeldorganisatie** in **Naam** en klik vervolgens op **Volgende**.
    
16. Klik in het deelvenster **Uw instellingen controleren** op **Labels publiceren** en klik vervolgens op **Sluiten**.
    
## <a name="phase-4-create-your-teams"></a>Fase 4: uw teams maken

In deze fase maakt en configureert u gevoelige en zeer vertrouwelijke teamsites voor uw voorbeeldorganisatie.

### <a name="sensitive-team-for-marketing-campaigns"></a>Gevoelig team voor marketingcampagnes

Ga als volgt te werk om een team te maken met een gevoeligheidsniveau voor leden van de marketinggroep waarin zij kunnen samenwerken aan lopende marketingcampagnes:

1. [Maak een nieuwe privéteamsite](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) met de naam **Marketingcampagnes**.
2. Open het team **marketingcampagnes**.
3.    Klik in de werkbalk van het team op **Bestanden**.
4.    Klik op het beletselteken en klik vervolgens op **Openen in SharePoint**.
5.    Klik op de werkbalk van de onderliggende SharePoint-site op het pictogram Instellingen en vervolgens op **Sitemachtigingen**.
6.    Klik in het deelvenster **Sitemachtigingen** onder **Instellingen voor delen** op **Instellingen voor delen wijzigen**.
7.    Kies onder **Machtigingen voor delen** de optie **Alleen site-eigenaren kunnen bestanden, mappen en de site delen** en klik vervolgens op **Opslaan**.

Configureer vervolgens de documentenmap van de onderliggende SharePoint-site Marketingcampagnes voor het label Gevoelig.

1.    Klik op het tabblad **Start Marketingcampagnes** van uw browser op **Documenten**.
2.    Klik op het pictogram Instellingen en vervolgens op **Bibliotheekinstellingen**.
3.    Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.
4.    Selecteer in **Instellingen: Label toepassen** de optie **Gevoelig**en klik vervolgens op **Opslaan**. 

Configureer vervolgens een beleid voor de preventie van gegevensverlies (DLP) waardoor gebruikers worden gewaarschuwd wanneer ze een document met het label Gevoelig op de onderliggende SharePoint-site en buiten de organisatie delen, waaronder op de site Marketingcampagnes.

1. Meld u aan bij de [Microsoft 365-complianceportal](https://compliance.microsoft.com/) met uw algemeen beheerdersaccount.
    
2. Klik op het nieuwe tabblad **Microsoft 365-compliance** in uw browser op **Beleid > Preventie van gegevensverlies**.
    
3. Klik in het deelvenster **Start > Preventie van gegevensverlies** op **Een beleid maken**.
    
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
    
  - Als u wilt delen met een gebruiker buiten de organisatie downloadt en opent u het bestand. Klik op Bestand, vervolgens op Document beveiligen en daarna op Versleutelen met wachtwoord en geef tot slot een sterk wachtwoord op. Stuur het wachtwoord in een afzonderlijk e-mailbericht of via een ander communicatiemiddel.
    
16. Klik op **OK**.
    
17. Klik in het deelvenster **Wat wilt u doen als we gevoelige informatie herkennen?** op **Volgende**.
    
18. Klik in het deelvenster **Wilt u het beleid inschakelen of eerst testen?** op **Ja, schakel het meteen in** en klik vervolgens op **Volgende**.
    
19. Klik in het deelvenster **Uw instellingen controleren** op **Maken** en klik vervolgens op **Sluiten**.

Hier is de resulterende configuratie voor het bedrijfsstrategieteam.

![Configuratie voor het bedrijfsstrategieteam.](../../media/sensitive-team-config-dev-test.png)
  
### <a name="company-strategy-team-site"></a>Teamsite bedrijfsstrategie

Zo maakt u een zeer vertrouwelijk team voor leden van het senior leiderschapsteam zodat zij kunnen samenwerken aan de bedrijfsstrategie:

1. [Maak een nieuw persoonlijk team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) met de naam **Bedrijfsstrategie**.
2. Open het **bedrijfsstrategie**-team.
3.    Klik in de werkbalk van het team op **Bestanden**.
4.    Klik op het beletselteken en klik vervolgens op **Openen in SharePoint**.
5.    Klik op de werkbalk van de onderliggende SharePoint-site op het pictogram Instellingen en vervolgens op **Sitemachtigingen**.
6.    Klik in het deelvenster **Sitemachtigingen** onder **Instellingen voor delen** op **Instellingen voor delen wijzigen**.
7.    Kies onder **Machtigingen voor delen**, **Alleen site-eigenaren kunnen bestanden, mappen en de site delen**.
8.    Schakel **Toegangsaanvragen toestaan** uit en klik vervolgens op **Opslaan**.

Configureer vervolgens de documentenmap van de onderliggende Company Strategy SharePoint-site voor het label Gevoelig.

1.    Klik op het tabblad **Start bedrijfsstrategie** van uw browser op **Documenten**.
2.    Klik op het pictogram Instellingen en vervolgens op **Bibliotheekinstellingen**.
3.    Klik onder **Machtigingen en beheer** op **Label op items in deze bibliotheek toepassen**.
4.    Selecteer in **Instellingen: label toepassen** de optie **Gevoelig**en klik vervolgens op **Opslaan**. 

Configureer vervolgens een DLP-beleid dat gebruikers blokkeert wanneer ze een document op een onderliggende SharePoint-site met het label Gevoelig, waaronder de bedrijfsstrategiesite, buiten de organisatie delen.
  
1. Meld u aan bij de [Microsoft 365-complianceportal](https://compliance.microsoft.com/) met uw algemeen beheerdersaccount.
    
2. Klik op het nieuwe tabblad **Microsoft 365-compliance** in uw browser op **Beleid > Preventie van gegevensverlies**.
    
3. Klik in het deelvenster **Start > Preventie van gegevensverlies** op **Een beleid maken**.
    
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
    
  - Als u wilt delen met een gebruiker buiten de organisatie downloadt en opent u het bestand. Klik op Bestand, vervolgens op Document beveiligen en daarna op Versleutelen met wachtwoord en geef tot slot een sterk wachtwoord op. Stuur het wachtwoord in een afzonderlijk e-mailbericht of via een ander communicatiemiddel.
    
16. Klik op **OK**.
    
17. Klik in het deelvenster **Wilt u het beleid inschakelen of eerst testen?** op **Ja, schakel het meteen in** en klik vervolgens op **Volgende**.

18. Klik in het deelvenster **Wilt u het beleid inschakelen of eerst testen?** op **Ja, schakel het meteen in** en klik vervolgens op **Volgende**.
    
19. Klik in het deelvenster **Uw instellingen controleren** op **Maken** en klik vervolgens op **Sluiten**.

Gebruik [deze instructies](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) om een gevoeligheidslabel met de volgende instellingen te configureren:

- De naam van het label is Bedrijfsstrategie
- Versleuteling is ingeschakeld.
- De groep Bedrijfsstrategie heeft cocreatie-machtigingen

Publiceer na het maken het nieuwe label. Als u zich aanmeldt als lid van de groep Bedrijfsstrategie ziet u het nieuwe label in de optie Gevoeligheid op de werkbalk Start van Word, Excel en PowerPoint. Selecteer het label Bedrijfsstrategie bij de optie Gevoeligheid om het label aan een bestand toe te wijzen.

Hier is de resulterende configuratie voor het bedrijfsstrategieteam.

![Configuratie voor het bedrijfsstrategieteam.](../../media/highlyconfidential-team-config-dev-test.png) 

Bestanden in het documentgedeelte van de onderliggende SharePoint-site voor bedrijfsstrategie krijgen het retentielabel Zeer gevoelig toegewezen en zijn onderworpen aan het geconfigureerde DLP-beleid. Aan bestanden kan ook het gevoeligheidslabel Bedrijfsstrategie worden toegewezen.    
  
## <a name="next-step"></a>Volgende stap

Wanneer u klaar bent voor productie-implementatie, raadpleegt u [beveiligde bestanden in Microsoft Teams](secure-files-in-teams.md) voor meer informatie en koppelingen naar artikelen met stapsgewijze implementatie.
  
## <a name="see-also"></a>Zie ook

[Cloud acceptatie en hybride oplossingen](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
