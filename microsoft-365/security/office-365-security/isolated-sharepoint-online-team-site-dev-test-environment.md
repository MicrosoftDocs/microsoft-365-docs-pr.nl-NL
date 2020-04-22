---
title: Dev/testomgeving van de geïsoleerde SharePoint Online-teamsite
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: 'Samenvatting: Configureer een SharePoint Online-teamsite die is geïsoleerd van de rest van de organisatie in uw Microsoft 365-dev/testomgeving.'
ms.openlocfilehash: 2a1c728f5cbc1d622bb46ffd7532f1103a7995d3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634120"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a>Dev/testomgeving van de geïsoleerde SharePoint Online-teamsite

 **Samenvatting:** Configureer een SharePoint Online-teamsite die is geïsoleerd van de rest van de organisatie in uw Microsoft 365-dev/testomgeving.

SharePoint Online-teamsites in Microsoft 365 zijn locaties voor samenwerking met behulp van een algemene documentbibliotheek, een OneNote-notitieblok en andere services. In veel gevallen wilt u brede toegang en samenwerking tussen afdelingen of organisaties. In sommige gevallen wilt u echter de toegang en machtigingen voor samenwerking tussen een kleine groep mensen streng beheren.

Toegang tot SharePoint Online-teamsites en wat gebruikers kunnen doen, wordt beheerd door SharePoint-groepen en machtigingsniveaus. SharePoint Online-sites hebben standaard drie toegangsniveaus:

- **Leden**, die bronnen op de site kunnen bekijken, maken en wijzigen.

- **Eigenaren**, die volledige controle over de site hebben, inclusief de mogelijkheid om machtigingen te wijzigen.

- **Bezoekers**, die alleen bronnen op de site kunnen bekijken.

In dit artikel wordt u door de configuratie van een geïsoleerde SharePoint Online-teamsite geplaatst voor een geheim onderzoeksproject met de naam ProjectX. De toegangsvereisten zijn:

- Alleen leden van het project hebben toegang tot de site en de inhoud ervan (documenten, OneNote-notitieblok, pagina's), met sharepoint-machtigingsniveaus bewerken en bekijken die worden beheerd via groepslidmaatschap.

- Alleen de maker van de site en leden van een groep Beheerders voor de site kunnen sitebeheer uitvoeren, waaronder het wijzigen van machtigingen op siteniveau.

Er zijn drie fasen voor het instellen van een geïsoleerde SharePoint Online-teamsite in uw Microsoft 365-dev/testomgeving:

1. Maak de Microsoft 365-dev/testomgeving.

2. Maak de gebruikers en groepen voor ProjectX.

3. Maak een nieuwe ProjectX SharePoint Online-teamsite en isoleer deze.

> [!TIP]
> Klik [hier](https://aka.ms/catlgstack) voor een visuele kaart voor alle artikelen in de One Microsoft Cloud Test Lab Guide stack.

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a>Fase 1: Bouw uw lichtgewicht of gesimuleerde Microsoft 365-testomgeving uit

Als u gewoon een geïsoleerde SharePoint Online-teamsite op een lichtgewicht manier wilt maken met de minimale vereisten, volgt u de instructies in fase 2 en 3 van [de Microsoft 365-dev/testomgeving.](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)

Als u een geïsoleerde SharePoint Online-teamsite wilt maken in een gesimuleerde bedrijfsconfiguratie, volgt u de instructies in [DirSync voor uw Microsoft 365-dev/testomgeving.](https://docs.microsoft.com/office365/enterprise/dirsync-for-your-office-365-dev-test-environment)

> [!NOTE]
> Voor het maken van een geïsoleerde SharePoint Online-site is de gesimuleerde bedrijfsdev/testomgeving niet vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services). Het wordt hier als optie aangeboden, zodat u een geïsoleerde SharePoint Online-site testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt.

## <a name="phase-2-create-user-accounts-and-access-groups"></a>Fase 2: Gebruikersaccounts en toegangsgroepen maken

Gebruik de instructies in [Verbinding maken met Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) om verbinding te maken met uw proefabonnement met uw wereldwijde beheerdersaccount vanaf:

- Uw computer (voor de lichtgewicht Microsoft 365 dev/testomgeving).

- De client1 virtuele machine (voor de gesimuleerde onderneming Microsoft 365 dev/test omgeving).

Als u de nieuwe toegangsgroepen voor de ProjectX SharePoint Online-teamsite wilt maken, voert u deze opdrachten uit vanuit de prompt van Windows Azure Active Directory Module voor Windows PowerShell:

```powershell
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

Vul de naam van uw organisatie in (bijvoorbeeld: contosotoycompany), de landcode met twee tekens voor uw locatie en voer vervolgens de volgende opdrachten uit vanuit de prompt van Windows Azure Active Directory Module voor Windows PowerShell:

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Noteer bij de weergave van de opdracht **Nieuw-MsolUser** het gegenereerde wachtwoord voor het Lead Designer-account en neem het op een veilige locatie op.

Voer de volgende opdrachten uit de Windows Azure Active Directory Module voor Windows PowerShell-prompt:

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Noteer bij de weergave van de opdracht **Nieuw-MsolUser** het gegenereerde wachtwoord voor het Lead Researcher-account en noteer het op een veilige locatie.

Voer de volgende opdrachten uit de Windows Azure Active Directory Module voor Windows PowerShell-prompt:

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Noteer bij de weergave van de opdracht **Nieuw-MsolUser** het gegenereerde wachtwoord voor het Development VP-account en neem het op een veilige locatie op.

Voer vervolgens de volgende PowerShell-opdrachten uit vanuit de Prompt van Windows Azure Active Directory Module voor Windows PowerShell om de nieuwe accounts toe te voegen aan de nieuwe toegangsgroepen:

```powershell
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

Resultaten:

- De toegangsgroep ProjectX-Leden bevat de gebruikersaccounts Lead Designer en Lead Researcher

- De toegangsgroep ProjectX-Administrators bevat het globale beheerdersaccount voor uw proefabonnement

- De toegangsgroep ProjectX-Kijkers bevat het Gebruikersaccount Development VP

Figuur 1 toont de toegangsgroepen en hun lidmaatschap.

**Figuur 1**

![De Microsoft 365-groepen en hun lidmaatschap voor een geïsoleerde SharePoint Online-groepsite](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a>Fase 3: Een nieuwe ProjectX SharePoint Online-teamsite maken en deze isoleren

Ga als volgt te werk om een SharePoint Online-teamsite voor ProjectX te maken:

1. Meld u aan bij het Microsoft 365-beheercentrum ([https://admin.microsoft.com](https://admin.microsoft.com)) met uw algemene beheerdersaccount met behulp van een browser op uw lokale computer (lichtgewicht configuratie) of client1 (gesimuleerde bedrijfsconfiguratie).

2. Klik in de lijst met tegels op **SharePoint**.

3. Klik in het nieuwe SharePoint-tabblad in uw browser op **+ Site maken**.

4. Typ **ProjectX**in **teamsitenaam**. Selecteer **privé-** in **Privacy-instellingen**en selecteer deze site .

5. Typ **in Teamsitebeschrijving** **SharePoint-site voor ProjectX**en klik op **Volgende**.

6. Op de **Wie wil je toevoegen?** op **Voltooien**klikken.

7. Klik op het nieuwe tabblad **ProjectX-Start** in uw browser op de **gereedschapsbalk**op het pictogram Instellingen en klik vervolgens op Sitemachtigingen .

8. Klik in het deelvenster **Sitemachtigingen** op **Geavanceerde machtigingsinstellingen**.

9. Klik in het nieuwe **tabblad Machtigingen: Project X** in uw browser op Instellingen voor **toegangsaanvragen**.

10. Schakel in het dialoogvenster **Instellingen voor toegangsaanvragen** de **schakel Instellingen voor toegang uit om de site en afzonderlijke bestanden en mappen te delen** en **toegangsaanvragen toestaan** (zodat alle drie de selectievakjes zijn gewist) en klik vervolgens op **OK**.

11. Klik op **ProjectX-leden** in de lijst.

12. Klik op de pagina **Personen en groepen** op **Nieuw**.

13. Typ **projectx-leden**in het dialoogvenster **Delen,** selecteer deze en klik op **Delen**.

14. Klik op de terugknop in uw browser.

15. Klik op **ProjectX-eigenaren** in de lijst.

16. Klik op de pagina **Personen en groepen** op **Nieuw**.

17. Typ **projectx-beheerders**in het dialoogvenster **Delen,** selecteer deze en klik op **Delen**.

18. Klik op de terugknop in uw browser.

19. Klik op **ProjectX-bezoekers** in de lijst.

20. Klik op de pagina **Personen en groepen** op **Nieuw**.

21. Typ **projectx-viewers**in het dialoogvenster **Delen,** selecteer deze en klik op **Delen**.

22. Sluit het tabblad **Personen en groepen** in uw browser, klik op het tabblad **ProjectX-Start** in uw browser en sluit het deelvenster **Sitemachtigingen.**

Dit zijn de resultaten van het configureren van machtigingen:

- De SharePoint-groep ProjectX-leden bevat alleen de toegangsgroep ProjectX-Leden (die alleen de gebruikersaccounts leaddesigner en leadonderzoeker bevat) en de ProjectX-groep (die alleen het algemene beheerdersgebruikersaccount bevat).

- De SharePoint-groep ProjectX-eigenaren bevat alleen de toegangsgroep projectx-beheerders (die alleen het gebruikersaccount van de globale beheerder bevat).

- De SharePoint-groep ProjectX-bezoekers bevat alleen de toegangsgroep ProjectX-Kijkers (die alleen het gebruikersaccount Van De VP-gebruiker van Ontwikkeling bevat).

- Leden kunnen machtigingen op siteniveau niet wijzigen (dit kan alleen worden gedaan door leden van de projectx-beheerdersgroep).

- Andere gebruikersaccounts hebben geen toegang tot de site of de bijbehorende resources en kunnen geen toegang tot de site aanvragen.

Figuur 2 toont de SharePoint-groepen en hun lidmaatschap.

**Figuur 2**

![De SharePoint Online-groepen en hun lidmaatschap voor een geïsoleerde SharePoint Online-groepssite](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

Laten we nu de toegang demonstreren met het Lead Designer-gebruikersaccount:

1. Sluit het tabblad **ProjectX-Start** in uw browser en klik op het tabblad **Microsoft Office Start** in uw browser.

2. Klik op de naam van uw globale beheerder en klik vervolgens op **Afmelden**.

3. Meld u aan bij het Microsoft[https://admin.microsoft.com](https://admin.microsoft.com)365-beheercentrum ( ) met de naam van het Lead Designer-account en het wachtwoord ervan.

4. Klik in de lijst met tegels op **SharePoint**.

5. Typ **ProjectX** op het nieuwe **tabblad SharePoint** in uw browser in het zoekvak, activeer de zoekopdracht en klik vervolgens op de **projectx-teamsite.** U ziet een nieuw tabblad in uw browser voor de ProjectX-teamsite.

6. Klik op het pictogram Instellingen. Merk op dat er geen optie is voor **sitemachtigingen.** Dit is juist omdat alleen de leden van de groep ProjectX-Administrators machtigingen op de site kunnen wijzigen

7. Open Kladblok of een teksteditor naar keuze.

8. Kopieer de URL van de ProjectX-teamsite en plak deze op een nieuwe regel in Kladblok of uw teksteditor.

9. Klik op het nieuwe tabblad **ProjectX-Start** in uw browser op **Documenten**.

10. Kopieer de URL van de map ProjectX-documenten en plak deze op een nieuwe regel in Kladblok of uw teksteditor.

11. Klik op het nieuwe tabblad **ProjectX-Documenten** in uw browser op **Nieuw > Word-document**.

12. Typ tekst op de pagina, wacht tot de status **is opgeslagen,** klik op de knop Vorige in uw browser en vernieuw de pagina. U ziet een nieuwe **Document.docx** in de map **Documenten.**

13. Klik op de ellips voor het **document Document.docx** en klik vervolgens op **Een koppeling opvragen.**

14. Kopieer de URL in het dialoogvenster **'Document.docx' delen** en plak deze op een nieuwe regel in Kladblok of uw teksteditor en sluit het dialoogvenster **'Document.docx' delen.**

15. Sluit de **Tabbladen ProjectX-Documents** en **SharePoint** in uw browser en klik op het tabblad **Microsoft Office Start.**

16. Klik op de naam **Van hoofdontwerper** en klik vervolgens op **Afmelden**.

Laten we nu de toegang demonstreren met het Gebruikersaccount Van Ontwikkeling VP:

1. Meld u aan bij het Microsoft[https://admin.microsoft.com](https://admin.microsoft.com)365-beheercentrum ( ) met de naam van het Development VP-account en het wachtwoord ervan.

2. Klik in de lijst met tegels op **SharePoint**.

3. Typ **ProjectX** op het nieuwe **tabblad SharePoint** in uw browser in het zoekvak, activeer de zoekopdracht en klik vervolgens op de **projectx-teamsite.** U ziet een nieuw tabblad in uw browser voor de ProjectX-teamsite.

4. Klik **op Documenten**en klik vervolgens op het **document.docx-bestand.**

5. Probeer de tekst in het tabblad **Document.docx** in uw browser te wijzigen. U ziet een bericht met de vermelding **Dit document is alleen-lezen.** Dit wordt verwacht omdat het gebruikersaccount van Development VP alleen weergavemachtigingen voor de site heeft.

6. Sluit de tabbladen **Document.docx,** **ProjectX-Documents**en **SharePoint** in uw browser.

7. Klik op het tabblad **Microsoft Office Start,** klik op de naam **Development VP** en klik vervolgens op **Afmelden**.

Laten we nu de toegang demonstreren met een gebruikersaccount dat geen machtigingen heeft:

1. Meld u aan bij het Microsoft[https://admin.microsoft.com](https://admin.microsoft.com)365-beheercentrum ( ) met de naam van het account gebruiker 3 en het wachtwoord.

2. Klik in de lijst met tegels op **SharePoint**.

3. Typ **ProjectX** op het nieuwe **tabblad SharePoint** in uw browser in het zoekvak en activeer de zoekopdracht. U ziet het bericht **Niets hier komt overeen met uw zoekopdracht.**

4. Kopieer vanuit het geopende exemplaar van Kladblok of uw teksteditor de URL voor de ProjectX-site naar de adresbalk van uw browser en druk op **Enter**. U ziet een pagina **Toegang geweigerd.**

5. Kopieer vanuit Kladblok of uw teksteditor de URL voor de map ProjectX-documenten naar de adresbalk van uw browser en druk op **Enter**. U ziet een pagina **Toegang geweigerd.**

6. Kopieer vanuit Kladblok of uw teksteditor de URL voor het bestand Documents.docx naar de adresbalk van uw browser en druk op **Enter**. U ziet een pagina **Toegang geweigerd.**

7. Sluit het tabblad **SharePoint** in uw browser, klik op het tabblad **Microsoft Office Start,** klik op de naam **Gebruiker 3** en klik vervolgens op **Afmelden**.

Uw geïsoleerde SharePoint Online-site is nu klaar voor uw aanvullende experimenten.

## <a name="next-step"></a>Volgende stap

Als u klaar bent om een geïsoleerde SharePoint Online-teamsite in productie te implementeren, raadpleegt u de stapsgewijze overwegingen voor het ontwerpen in [Een geïsoleerde SharePoint Online-teamsite ontwerpen](design-an-isolated-sharepoint-online-team-site.md).

## <a name="see-also"></a>Zie ook

[Geïsoleerde SharePoint Online-teamsites](isolated-sharepoint-online-team-sites.md)

[Cloud adoption Test Lab Guides (TLGs)](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[Basisconfiguratiedev/testomgeving](https://docs.microsoft.com/office365/enterprise/base-configuration-dev-test-environment)

[Microsoft 365 dev/testomgeving](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)

[Cloud adoption and hybrid solutions](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions) (Overstappen op de cloud en hybride oplossingen)




