---
title: Geïsoleerde ontwikkelaar van SharePoint Online-team site/testomgeving
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
description: 'Overzicht: een SharePoint Online-team site configureren die is geïsoleerd van de rest van de organisatie in uw Microsoft 365-ontwikkelomgeving/testomgeving.'
ms.openlocfilehash: e21dccb9ef535bb997d6e62b70e5576bf531041c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199659"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a>Geïsoleerde ontwikkelaar van SharePoint Online-team site/testomgeving

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 **Overzicht:** Configureer een SharePoint Online-team site die is geïsoleerd van de rest van de organisatie in uw Microsoft 365-ontwikkelomgeving/testomgeving.

SharePoint Online-team sites in Microsoft 365 zijn locaties voor samenwerking waarbij een gemeenschappelijke documentbibliotheek, een OneNote-notitieblok en andere services worden gebruikt. In veel gevallen wilt u toegang hebben tot de hele afdeling of organisatie. In sommige gevallen wilt u echter de toegang en machtigingen voor samenwerking tussen een kleine groep personen nauwkeurig beheren.

Toegang tot SharePoint Online-team sites en wat gebruikers kunnen doen, wordt beheerd door SharePoint-groepen en machtigingsniveaus. SharePoint Online-sites hebben standaard drie toegangsniveaus:

- **Leden**van de site, die de bronnen op de site kunnen bekijken, maken en wijzigen.

- **Eigenaren**van de volledige controle over de site, waaronder de mogelijkheid om machtigingen te wijzigen.

- **Gebruikers**die alleen de resources op de site kunnen weergeven.

In dit artikel wordt u stapsgewijs begeleid bij de configuratie van een alleenstaande SharePoint Online-team site voor een Secret Research project met de naam Projectx. De toegangsvereisten zijn:

- Alleen leden van het project hebben toegang tot de site en de inhoud daarvan (documenten, OneNote-notitieblok, pagina's), met behulp van SharePoint-machtigingsniveaus die worden beheerd via groepslidmaatschap.

- Alleen de site Auteur en leden van een groep beheerders van de site kunnen Sitebeheer uitvoeren, waaronder het wijzigen van machtigingen op siteniveau.

U kunt op drie manieren een geïsoleerde SharePoint Online-team site instellen in uw Microsoft 365-ontwikkelomgeving/testomgeving:

1. Maak de Microsoft 365 dev/testomgeving.

2. Maak de gebruikers en groepen voor Projectx.

3. Maak een nieuwe Projectx SharePoint Online-team site en Isoleer dit.

> [!TIP]
> Klik [hier](https://aka.ms/catlgstack) voor een visuele kaart voor alle artikelen in de ene Microsoft Cloud test lab-gids.

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a>Fase 1: uw lichtgewicht of gesimuleerde Enterprise Microsoft 365 dev/testomgeving maken

Als u een afzonderlijke SharePoint Online-team site op een lichte manier wilt maken met de minimumvereisten, volgt u de instructies in de fasen 2 en 3 van [de Lightweight Base configuration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).

Als u een geïsoleerde SharePoint Online-team site wilt maken in de gesimuleerde Enterprise-configuratie, volgt u de instructies in de [wachtwoord hash-synchronisatie voor uw Microsoft 365-testomgeving](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).

> [!NOTE]
> Voor het maken van een geïsoleerde SharePoint Online-site is de gesimuleerde Enterprise dev/testomgeving niet vereist, waaronder een gesimuleerd intranet dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest. U kunt dit hier opgeven als een optie, zodat u een geïsoleerde SharePoint Online-site kunt testen en in een omgeving kunt experimenteren die een typische organisatie voorstelt.

## <a name="phase-2-create-user-accounts-and-access-groups"></a>Fase 2: gebruikersaccounts en toegangsgroepen maken

Gebruik de instructies in [verbinding maken met Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell) om verbinding te maken met uw proefabonnement met uw globale-beheerdersaccount van:

- Uw computer (voor de lichte Microsoft 365-omgeving voor ontwikkelaars/testen).

- De virtuele computer van CLIENT1 (voor de gesimuleerde Enterprise Microsoft 365 dev/testomgeving).

Als u de nieuwe toegangsgroepen wilt maken voor de team site van Projectx SharePoint Online, voert u deze opdrachten uit in de Windows Azure Active Directory-module voor Windows PowerShell:

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

Vul de naam van uw organisatie in (voorbeeld: contosotoycompany), het landnummer van twee tekens voor uw locatie en voer de volgende opdrachten uit vanuit de Windows Azure Active Directory-module voor Windows PowerShell-prompt:

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Let in de weergave van de **MsolUser-** opdracht op het gegenereerde wachtwoord voor het account van de potentiële klant en neem het op een veilige locatie op.

Voer de volgende opdrachten uit in de Windows Azure Active Directory-module voor Windows PowerShell:

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Let in de weergave van de **MsolUser-** opdracht op het gegenereerde wachtwoord voor het account van de potentiële klant voor de potentiële klant en leg dit op een veilige plaats vast.

Voer de volgende opdrachten uit in de Windows Azure Active Directory-module voor Windows PowerShell:

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Let in de weergave van de **nieuwe MsolUser-** opdracht op het gegenereerde wachtwoord voor het account van Development VP en leg dit op een veilige plaats vast.

Vervolgens kunt u de nieuwe accounts toevoegen aan de nieuwe toegangsgroepen door deze PowerShell-opdrachten uit te voeren vanuit de Windows Azure Active Directory-module voor Windows PowerShell:

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

Uitvoer

- De groep Projectx-leden bevat de gebruikersaccounts voor de potentiële klant en de gebruikers van de potentiële klant

- De groep Projectx-beheerderstoegang bevat het account van de globale beheerder voor uw proefabonnement.

- De groep Projectx-viewers heeft het gebruikersaccount Development VP.

Afbeelding 1 toont de toegangsgroepen en hun lidmaatschap.

**Afbeelding 1**

![De Microsoft 365-groepen en hun lidmaatschap van een geïsoleerde site van een SharePoint Online-groep](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a>Fase 3: Maak een nieuwe Projectx SharePoint Online-team site en Isoleer dit

Ga als volgt te werk om een SharePoint Online-team site voor Projectx te maken:

1. Meld u aan bij het Microsoft 365-Beheercentrum [https://admin.microsoft.com](https://admin.microsoft.com) met uw globale beheerdersaccount en gebruik een browser op uw lokale computer (Lightweight Configuration) of op CLIENT1 (gesimuleerde Enterprise Configuration).

2. Klik in de lijst met tegels op **SharePoint**.

3. Klik in het nieuwe SharePoint-tabblad in uw browser op **+ Site maken**.

4. In de naam van de **team site**typt u **projectx**. Selecteer bij **privacyinstellingen**de optie **persoonlijke leden hebben toegang tot deze site**.

5. Typ in de beschrijving van de **team site**een **SharePoint-site voor projectx**en klik vervolgens op **volgende**.

6. Aan **wie wilt u toevoegen**? Klik op **Voltooien**.

7. Klik op het tabblad nieuw **projectx-start** in de browser op het pictogram instellingen in de werkbalk en klik vervolgens op **site machtigingen**.

8. Klik in het deelvenster **Sitemachtigingen** op **Geavanceerde machtigingsinstellingen**.

9. Klik op het tabblad nieuwe **machtigingen: Project X** in de browser op **instellingen voor toegangsaanvragen**.

10. Schakel in het dialoogvenster **instellingen voor toegangsaanvragen** **het vakje leden toestaan de site en afzonderlijke bestanden en mappen te delen** en **toegangsaanvragen toe** (zodat alle drie de selectievakjes zijn uitgeschakeld), en klik vervolgens op **OK**.

11. Klik op **projectx-leden** in de lijst.

12. Klik op de pagina **Personen en groepen** op **Nieuw**.

13. Typ in het dialoogvenster **delen** de tekst **projectx-leden**, Selecteer deze en klik vervolgens op **delen**.

14. Klik op de terugknop in uw browser.

15. Klik op **projectx-eigenaren** in de lijst.

16. Klik op de pagina **Personen en groepen** op **Nieuw**.

17. Typ in het dialoogvenster **delen** **projectx-beheerders**, selecteer het en klik vervolgens op **delen**.

18. Klik op de terugknop in uw browser.

19. Klik op de **bezoekers van projectx** in de lijst.

20. Klik op de pagina **Personen en groepen** op **Nieuw**.

21. In het dialoogvenster **delen** typt u **Projectx-viewers**, selecteert u het en klikt u op **delen**.

22. Sluit het tabblad **personen en groepen** in uw browser, klik op het tabblad **Start** in uw browser en sluit het deelvenster **site machtigingen** .

Dit zijn de resultaten van het configureren van machtigingen:

- De SharePoint-groep leden van Projectx bevat alleen de groep Projectx-leden (die alleen de gebruikersaccounts voor de potentiële klant en de gebruikers van de potentiële klant voor de potentiële klanten bevat) en de Projectx-groep (die alleen het globale beheerdersaccount bevat).

- De SharePoint-groep eigenaren van Projectx bevat alleen de groep Projectx-beheerderstoegang (die alleen het hoofd beheerders gebruikersaccount bevat).

- De SharePoint-groep voor bezoekers van Projectx bevat alleen de groep Projectx-viewers, die alleen het gebruikersaccount van Development VP bevat.

- Leden kunnen geen machtigingen op siteniveau wijzigen (dit kan alleen worden uitgevoerd door leden van de groep Projectx-beheerders).

- Andere gebruikersaccounts hebben geen toegang tot de site of de bijbehorende resources en kunnen geen toegang tot de site aanvragen.

Afbeelding 2 toont de SharePoint-groepen en hun lidmaatschap.

**Afbeelding 2**

![De SharePoint Online-groepen en hun lidmaatschap van een geïsoleerde site van een SharePoint Online-groep](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

Laten we Access demonstreren met behulp van de gebruikersaccount van de potentiële klant:

1. Sluit het tabblad **Start van projectx** in uw browser en klik op het tabblad **Start van Microsoft Office** in uw browser.

2. Klik op de naam van de globale beheerder en klik vervolgens op **Afmelden**.

3. Meld u aan bij het Microsoft 365-Beheercentrum ( [https://admin.microsoft.com](https://admin.microsoft.com) ) met behulp van de naam van het account en het wachtwoord van de potentiële klant.

4. Klik in de lijst met tegels op **SharePoint**.

5. Typ op het tabblad nieuwe **SharePoint** in uw browser **projectx** in het zoekvak, activeer de zoekfunctie en klik vervolgens op de **projectx** -team site. U ziet nu een nieuw tabblad in uw browser voor de Projectx-team site.

6. Klik op het pictogram instellingen. Let erop dat er geen optie is voor **site machtigingen**. Dit klopt niet omdat alleen de leden van de groep Projectx-beheerdersmachtigingen voor de site kunnen wijzigen.

7. Open Kladblok of een teksteditor van uw keuze.

8. Kopieer de URL van de Projectx-team site en plak deze op een nieuwe regel in Kladblok of in de teksteditor.

9. Klik op het tabblad nieuw **projectx-start** in de browser op **documenten**.

10. Kopieer de URL van de map Projectx en plak deze op een nieuwe regel in Kladblok of in de teksteditor.

11. Klik in uw browser op het tabblad nieuwe **projectx-documenten** op **Nieuw > Word-document**.

12. Voer wat tekst op de pagina in, wacht tot de status is **opgeslagen**en klik op de knop terug in uw browser en vernieuw de pagina. U ziet nu een nieuwe **Document.docx** in de map **documenten** .

13. Klik op het beletselteken voor het **Document.docx** document en klik vervolgens op **koppeling weer**geven.

14. Kopieer de URL in het dialoogvenster **' Document.docx ' delen** en plak deze op een nieuwe regel in Kladblok of in de teksteditor en sluit vervolgens het dialoogvenster **' Document.docx '** .

15. Sluit de tabbladen **projectx-documenten** en **SharePoint** in uw browser en klik vervolgens op het tabblad **Start van Microsoft Office** .

16. Klik op de naam van de ontwerper van de **potentiële klant** en klik vervolgens op **Afmelden**.

Laten we nu eens kijken hoe u het gebruikersaccount van Development VP gebruikt:

1. Meld u aan bij het Microsoft 365-Beheercentrum ( [https://admin.microsoft.com](https://admin.microsoft.com) ) met de accountnaam van Development VP en het bijbehorende wachtwoord.

2. Klik in de lijst met tegels op **SharePoint**.

3. Typ op het tabblad nieuwe **SharePoint** in uw browser **projectx** in het zoekvak, activeer de zoekfunctie en klik vervolgens op de **projectx** -team site. U ziet nu een nieuw tabblad in uw browser voor de Projectx-team site.

4. Klik op **documenten**en klik vervolgens op het **Document.docx** bestand.

5. Probeer de tekst te wijzigen op het tabblad **Document.docx** in de browser. U ziet een bericht **met de mededeling dat het document alleen-lezen is.** Dit wordt verwacht omdat het gebruikersaccount van Development VP alleen weergave machtigingen voor de site heeft.

6. Sluit de tabbladen **Document.docx**, **projectx-documenten**en **SharePoint** in uw browser.

7. Ga naar het tabblad **Start van Microsoft Office** , klik op de naam van de naam van de **ontwikkelaars** en klik vervolgens op **Afmelden**.

Laten we nu eens kijken naar Access met een gebruikersaccount zonder machtigingen:

1. Meld u aan bij het Microsoft 365-Beheercentrum ( [https://admin.microsoft.com](https://admin.microsoft.com) ) met behulp van de accountnaam en het wachtwoord van de gebruiker.

2. Klik in de lijst met tegels op **SharePoint**.

3. Typ op het tabblad nieuwe **SharePoint** in uw browser **projectx** in het zoekvak en activeer vervolgens de zoekopdracht. U ziet het bericht **er niets** te zien.

4. Kopieer de URL van de Projectx-site in de adresbalk van uw browser in het geopende exemplaar van Kladblok of in de teksteditor **.** U dient een pagina **toegang geweigerd** te zien.

5. Kopieer in Kladblok of teksteditor de URL voor de map Projectx-documenten naar de adresbalk van uw browser en druk op **Enter**. U dient een pagina **toegang geweigerd** te zien.

6. Kopieer de URL voor het Documents.docx bestand in de adresbalk van uw browser en druk op **Enter**. U dient een pagina **toegang geweigerd** te zien.

7. Sluit het tabblad **SharePoint** in de browser, klik op het tabblad **Start van Microsoft Office** , klik op de naam van de **gebruiker** en klik vervolgens op **Afmelden**.

De geïsoleerde SharePoint Online-site is nu klaar voor een extra experimentatie.

## <a name="next-step"></a>Volgende stap

Als u klaar bent om een geïsoleerde SharePoint Online-teamsite in productie te implementeren, raadpleegt u de stapsgewijze overwegingen voor het ontwerpen in [Een geïsoleerde SharePoint Online-teamsite ontwerpen](design-an-isolated-sharepoint-online-team-site.md).

## <a name="see-also"></a>Zie ook

[Geïsoleerde SharePoint Online-teamsites](isolated-sharepoint-online-team-sites.md)

[Testlabrichtlijnen voor cloudacceptatie (TLG's)](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[De basisconfiguratie voor een gesimuleerde Enterprise](https://docs.microsoft.com/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise)

[De lichtgewicht basisconfiguratie](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)

[Cloud adoption and hybrid solutions](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
