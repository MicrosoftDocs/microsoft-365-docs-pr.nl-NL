---
title: Gescheiden dev/testomgeving van een SharePoint Online-teamsite
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: 'Overzicht: Configureer een SharePoint Online-teamsite die geïsoleerd is van de rest van de organisatie in uw Microsoft 365-dev/testomgeving.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 103ba1ddb2b5123db80be91f40c4fce8c6e2eb3d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286607"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a>Gescheiden dev/testomgeving van een SharePoint Online-teamsite

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender voor Office 365-abonnement 1](office-365-atp.md)
- SharePoint Online 


 **Overzicht:** Configureer een SharePoint Online-teamsite die geïsoleerd is van de rest van de organisatie in uw Microsoft 365-dev/testomgeving.

SharePoint Online-teamsites in Microsoft 365 zijn locaties voor samenwerking met behulp van een gemeenschappelijke documentbibliotheek, een OneNote-notitieblok en andere services. In veel gevallen wilt u brede toegang en samenwerking tussen afdelingen of organisaties. In sommige gevallen wilt u echter de toegang en machtigingen voor samenwerking tussen een kleine groep personen nauw bepalen.

Toegang tot teamsites van SharePoint Online en wat gebruikers kunnen doen, wordt bepaald door SharePoint-groepen en machtigingsniveaus. SharePoint Online-sites hebben standaard drie toegangsniveaus:

- **Leden** die resources op de site kunnen bekijken, maken en wijzigen.
- **Eigenaren,** die volledige controle over de site hebben, inclusief de mogelijkheid om machtigingen te wijzigen.
- **Bezoekers,** die alleen resources op de site kunnen bekijken.

In dit artikel wordt u stap voor stap door de configuratie van een geïsoleerd SharePoint Online-teamsite voor een geheim onderzoeksproject genaamd ProjectX beschreven. De toegangsvereisten zijn:

- Alleen leden van het project hebben toegang tot de site en de inhoud ervan (documenten, OneNote-notitieblok, pagina's), met sharePoint-machtigingsniveaus die worden beheerd via groepslidmaatschap, te bewerken en weer te geven.

- Alleen de maker en leden van een beheerdersgroep voor de site kunnen sitebeheer uitvoeren, waaronder het wijzigen van machtigingen op siteniveau.

Er zijn drie fasen voor het instellen van een afzonderlijke SharePoint Online-teamsite in uw Microsoft 365-dev/testomgeving:

1. Maak de Microsoft 365-dev/testomgeving.

2. Maak de gebruikers en groepen voor ProjectX.

3. Maak een nieuwe ProjectX SharePoint Online-teamsite en isoleert deze.

> [!TIP]
> Klik [hier](https://aka.ms/catlgstack) voor een visuele plattegrond van alle artikelen in de One Microsoft Cloud Test Lab Guide stack.

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a>Fase 1: Uw lichtgewicht of gesimuleerde bedrijfsomgeving met Microsoft 365-dev/test bouwen

Als u alleen een afzonderlijke SharePoint Online-teamsite wilt maken met minimale vereisten, volgt u de instructies in fasen 2 en 3 van de [basisconfiguratie.](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)

Als u een geïsoleerd SharePoint Online-teamsite wilt maken in een gesimuleerde bedrijfsconfiguratie, volgt u de instructies in Wachtwoord-hashsynchronisatie voor uw [Microsoft 365-testomgeving.](../../enterprise/password-hash-sync-m365-ent-test-environment.md)

> [!NOTE]
> Als u een afzonderlijke SharePoint Online-site maakt, hebt u niet de gesimuleerde bedrijfsdev/testomgeving nodig, die een gesimuleerd intranet bevat dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services). U kunt hier een afzonderlijke SharePoint Online-site testen en daarmee experimenteren in een omgeving die een gewone organisatie vertegenwoordigt.

## <a name="phase-2-create-user-accounts-and-access-groups"></a>Fase 2: Gebruikersaccounts maken en groepen openen

Gebruik de instructies in [Verbinding maken met Office 365 PowerShell](../../enterprise/connect-to-microsoft-365-powershell.md) om verbinding te maken met uw proefabonnement met uw globale beheerdersaccount vanuit:

- Uw computer (voor de lichtgewicht Microsoft 365-dev/testomgeving).

- De virtuele client1-machine (voor de gesimuleerde microsoft 365-dev/testomgeving voor enterprise Microsoft 365).

Als u de nieuwe toegangsgroepen wilt maken voor de teamsite van ProjectX SharePoint Online, voert u deze opdrachten uit vanuit de Windows Azure Active Directory-module voor Windows PowerShell-prompt:

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

Vul de naam van uw organisatie in (bijvoorbeeld: contospartycompany), de landcode van twee tekens voor uw locatie en voer vervolgens de volgende opdrachten uit vanuit de Windows Azure Active Directory-module voor Windows PowerShell:

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Noteer vanuit de weergave van de opdracht **New-MsolUser** het gegenereerde wachtwoord voor het Lead Designer-account en noteer het op een veilige locatie.

Voer de volgende opdrachten uit vanuit de Windows Azure Active Directory-module voor Windows PowerShell-prompt:

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Noteer vanuit de weergave van de opdracht **New-MsolUser** het gegenereerde wachtwoord voor het account Onderzoek voor leads en noteer het op een veilige locatie.

Voer de volgende opdrachten uit vanuit de Windows Azure Active Directory-module voor Windows PowerShell-prompt:

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Noteer vanuit de weergave van de opdracht **New-MsolUser** het gegenereerde wachtwoord voor het DEVELOPMENT VP-account en neem het op in een veilige locatie.

Als u vervolgens de nieuwe accounts wilt toevoegen aan de nieuwe toegangsgroepen, voert u deze PowerShell-opdrachten uit vanuit de Windows Azure Active Directory-module voor Windows PowerShell-prompt:

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

- De ProjectX-Members groep Toegang bevat de gebruikersaccounts Lead Designer en Lead Researcher

- De ProjectX-Admins groep toegang bevat het globale beheerdersaccount voor uw proefabonnement

- Het ProjectX-Viewers de groep Toegang bevat het gebruikersaccount Vicepresident ontwikkeling

Afbeelding 1 bevat de toegangsgroepen en hun lidmaatschap.

**Afbeelding 1:**

![De Microsoft 365-groepen en hun lidmaatschap voor een afzonderlijke SharePoint Online-groepssite](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a>Fase 3: Een nieuwe ProjectX SharePoint Online-teamsite maken en isoleren

Ga als volgt te werk om een SharePoint Online-teamsite te maken voor ProjectX:

1. Meld u aan bij het Microsoft 365-beheercentrum met behulp van uw globale beheerdersaccount met behulp van een browser op uw lokale computer (basisconfiguratie) of client1 (gesimuleerde <https://admin.microsoft.com> bedrijfsconfiguratie).

2. Klik in de lijst met tegels op **SharePoint**.

3. Klik in het nieuwe SharePoint-tabblad in uw browser op **+ Site maken**.

4. Typ **ProjectX in de** naam van de **teamsite.** Selecteer **Privé in** privacy-instellingen. Alleen leden hebben toegang tot deze **site.**

5. Typ **een** **SharePoint-site** voor ProjectX in de beschrijving van de teamsite en klik op **Volgende.**

6. Op de **wie wilt u toevoegen?** op **Voltooien.**

7. Klik op het nieuwe tabblad **ProjectX-start** in uw browser op de werkbalk op het instellingenpictogram en klik vervolgens op **Sitemachtigingen.**

8. Klik in het deelvenster **Sitemachtigingen** op **Geavanceerde machtigingsinstellingen**.

9. Klik op het **nieuwe tabblad Machtigingen: Project X** in uw browser op Instellingen voor **toegangsaanvraag.**

10. In **het** dialoogvenster Instellingen voor toegangsaanvragen, selecteert u Leden toestaan om de site en afzonderlijke bestanden en mappen te delen en **Toegangsaanvragen** toestaan **(zodat** alle drie de selectievakjes zijn gewist) uit en klikt u op **OK.**

11. Klik **op ProjectX-leden** in de lijst.

12. Klik op de pagina **Personen en groepen** op **Nieuw**.

13. Typ  **ProjectX-leden** in het dialoogvenster Delen, selecteer het en klik op **Delen.**

14. Klik op de terugknop in uw browser.

15. Klik **in de lijst op ProjectX-eigenaren.**

16. Klik op de pagina **Personen en groepen** op **Nieuw**.

17. Typ  **ProjectX-beheerders** in het dialoogvenster Delen, selecteer dit en klik op **Delen.**

18. Klik op de terugknop in uw browser.

19. Klik **in de lijst op ProjectX-bezoekers.**

20. Klik op de pagina **Personen en groepen** op **Nieuw**.

21. Typ  **ProjectX-Viewers** in het dialoogvenster Delen, selecteer dit en klik op **Delen.**

22. Sluit het **tabblad Personen en** groepen in uw browser, klik op het tabblad **ProjectX-Start** in uw browser en sluit het deelvenster **Sitemachtigingen.**

Dit zijn de resultaten van het configureren van machtigingen:

- De SharePoint-groep ProjectX-leden bevat alleen de toegangsgroep ProjectX-Members (die alleen de gebruikersaccounts Lead Designer en Lead Researcher bevat) en de ProjectX-groep (die alleen het globale beheerdersgebruikersaccount bevat).

- De SharePoint-groep ProjectX-eigenaren bevat alleen ProjectX-Admins toegangsgroep (die alleen het globale beheerdersaccount bevat).

- De SharePoint-groep ProjectX-bezoekers bevat alleen ProjectX-Viewers toegangsgroep (die alleen het gebruikersaccount van development vp bevat).

- Leden kunnen machtigingen op siteniveau niet wijzigen (dit kan alleen worden gedaan door leden van de ProjectX-Admins groep).

- Andere gebruikersaccounts hebben geen toegang tot de site of de bijbehorende resources en kunnen geen toegang tot de site aanvragen.

Afbeelding 2 bevat de SharePoint-groepen en hun lidmaatschap.

**Afbeelding 2**

![De SharePoint Online-groepen en hun lidmaatschap voor een afzonderlijke SharePoint Online-groepssite](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

Laten we nu eens een demonstratie geven van de toegang met behulp van het lead designer-gebruikersaccount:

1. Sluit het **tabblad ProjectX-start** in uw browser en klik in uw browser op het tabblad **Microsoft Office** Home.

2. Klik op de naam van uw globale beheerder en klik vervolgens **op Afloggen.**

3. Meld u aan bij het Microsoft 365-beheercentrum () met de naam en het wachtwoord van het <https://admin.microsoft.com> Lead Designer-account.

4. Klik in de lijst met tegels op **SharePoint**.

5. Typ op het nieuwe **SharePoint-tabblad** in uw browser **ProjectX** in het zoekvak, activeer de zoekopdracht en klik vervolgens op de **ProjectX-teamsite.** U ziet nu een nieuw tabblad in uw browser voor de ProjectX-teamsite.

6. Klik op het instellingenpictogram. U ziet dat er geen optie is voor **Sitemachtigingen.** Dit is juist omdat alleen de leden van ProjectX-Admins groep machtigingen voor de site kunnen wijzigen

7. Open Kladblok of een teksteditor van uw keuze.

8. Kopieer de URL van de ProjectX-teamsite en plak deze op een nieuwe regel in Kladblok of de teksteditor.

9. Klik op het **nieuwe tabblad ProjectX-start** in uw browser op **Documenten.**

10. Kopieer de URL van de map ProjectX-documenten en plak deze op een nieuwe regel in Kladblok of de teksteditor.

11. Klik op het **nieuwe tabblad ProjectX-documenten** in uw browser op **> Word-document.**

12. Typ wat tekst op de pagina, wacht tot de status Opgeslagen wordt **weergegeven,** klik op de knop Terug in uw browser en vernieuw vervolgens de pagina. U ziet nu een **nieuw** Document.docxin de **map** Documenten.

13. Klik op het beletselteken voor **Document.docx** document en klik vervolgens **op Koppeling maken.**

14. Kopieer de URL in het dialoogvenster **'Document.docx'** delen en plak deze op een nieuwe regel in Kladblok of de teksteditor. Sluit vervolgens het dialoogvenster **'Document.docx'** delen.

15. Sluit de **tabbladen ProjectX-documenten** en **SharePoint** in uw browser en klik vervolgens op het tabblad **Start van Microsoft Office.**

16. Klik op **de naam van de** leadontwerper en klik vervolgens op **Afloggen.**

Laten we nu de toegang laten zien met behulp van het gebruikersaccount Development VP:

1. Meld u aan bij het Microsoft 365-beheercentrum ( ) met de naam en het wachtwoord van de <https://admin.microsoft.com> VP-account voor ontwikkeling.

2. Klik in de lijst met tegels op **SharePoint**.

3. Typ op het nieuwe **SharePoint-tabblad** in uw browser **ProjectX** in het zoekvak, activeer de zoekopdracht en klik vervolgens op de **ProjectX-teamsite.** U ziet nu een nieuw tabblad in uw browser voor de ProjectX-teamsite.

4. Klik **op Documenten** en klik vervolgens op **Document.docx** bestand.

5. Probeer de **Document.docx** te wijzigen op het tabbladDocument.docxin de browser. Er wordt een bericht weergegeven met de mededeling **dat dit document alleen-lezen is.** Dit is verwacht omdat het gebruikersaccount van de vicepresident van development alleen weergavemachtigingen voor de site heeft.

6. Sluit de **Document.docx** in uw browser, **ProjectX-documenten** en **SharePoint.**

7. Klik op het tabblad Start van **Microsoft Office,** klik op de naam van de **vicepresident** voor ontwikkelaars en klik vervolgens **op Afloggen.**

Laten we nu de toegang laten zien met een gebruikersaccount dat geen machtigingen heeft:

1. Meld u aan bij het Microsoft 365-beheercentrum () met de accountnaam en <https://admin.microsoft.com> het wachtwoord van Gebruiker 3.

2. Klik in de lijst met tegels op **SharePoint**.

3. Typ **ProjectX** in het zoekvak op het nieuwe **tabblad SharePoint** in uw browser en activeer vervolgens de zoekopdracht. U ziet nu het bericht **Niets komt overeen met uw zoekopdracht.**

4. Kopieer vanuit het geopende exemplaar van Kladblok of uw teksteditor de URL voor de ProjectX-site naar de adresbalk van uw browser en druk op **Enter.** U ziet nu de pagina **Toegang geweigerd.**

5. Kopieer in Kladblok of uw teksteditor de URL voor de map ProjectX-documenten naar de adresbalk van uw browser en druk op **Enter.** U ziet nu de pagina **Toegang geweigerd.**

6. Kopieer vanuit Kladblok of de teksteditor de URL voor het Documents.docx-bestand naar de adresbalk van uw browser en druk op **Enter.** U ziet nu de pagina **Toegang geweigerd.**

7. Sluit het **tabblad SharePoint** in uw browser, klik op het tabblad **Microsoft Office Voor** thuisgebruik, klik op de naam gebruiker **3** en klik vervolgens **op Afloggen.**

Uw afzonderlijke SharePoint Online-site is nu klaar voor extra experiment.

## <a name="next-step"></a>Volgende stap

Als u klaar bent om een geïsoleerde SharePoint Online-teamsite in productie te implementeren, raadpleegt u de stapsgewijze overwegingen voor het ontwerpen in [Een geïsoleerde SharePoint Online-teamsite ontwerpen](design-an-isolated-sharepoint-online-team-site.md).

## <a name="see-also"></a>Zie ook

[Geïsoleerde SharePoint Online-teamsites](isolated-sharepoint-online-team-sites.md)

[Cloud adoption Test Lab Guides (TLGs)](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[De basisconfiguratie voor een gesimuleerde Enterprise](../../enterprise/simulated-ent-base-configuration-microsoft-365-enterprise.md)

[De lichtgewicht basisconfiguratie](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)

[Microsoft 365-oplossingen- en -architectuurcentrum](../../solutions/index.yml)