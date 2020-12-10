---
title: Een geïsoleerde SharePoint Online-teamsite beheren
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
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: U kunt een geïsoleerde SharePoint Online-team site beheren, nieuwe gebruikers en groepen toevoegen, gebruikers en groepen verwijderen en de submap documenten maken met aangepaste machtigingen.
ms.openlocfilehash: 1e244738071b434efd09e8fd700462bbef7e116a
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616762"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>Een geïsoleerde SharePoint Online-teamsite beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 **Overzicht:** Beheer de geïsoleerde SharePoint Online-team site met deze procedures.

In dit artikel worden veelvoorkomende beheerbewerkingen beschreven voor een geïsoleerde SharePoint Online-team site.

## <a name="add-a-new-user"></a>Een nieuwe gebruiker toevoegen

Wanneer iemand nieuwe lid is van de site, moet u het niveau van deelname aan de site bepalen:

- Beheer: het nieuwe gebruikersaccount toevoegen aan de groep sitebeheerders toegang

- Actieve samenwerking: het gebruikersaccount toevoegen aan de groep toegang tot siteleden

- Weergeven: het gebruikersaccount toevoegen aan de groep toegang tot sitebezoekers

Als u gebruikersaccounts en groepen beheert via Active Directory Domain Services (AD DS), voegt u de juiste gebruikers toe aan de juiste toegangsgroepen met behulp van uw normale Active Directory-gebruikers-en groepsbeheer procedures en wacht op synchronisatie met uw abonnement.

Als u gebruikersaccounts en groepen beheert via Microsoft 365, kunt u het Microsoft 365-Beheercentrum of Microsoft PowerShell gebruiken:

- Voor het Microsoft 365-Beheercentrum, meldt u zich aan met een gebruikersaccount waaraan de rol van beheerder of beheerder van het bedrijf is toegewezen en groepen om de juiste gebruikers aan de juiste toegangsgroepen toe te voegen.

- Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell voor Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module). Gebruik het volgende PowerShell-opdracht blok om een gebruikersaccount toe te voegen aan een Access-groep met de UPN (User Principal Name) van de gebruiker:

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Gebruik het volgende PowerShell-opdracht blok om een gebruikersaccount toe te voegen aan een Access-groep met de bijbehorende schermnaam:

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>Een nieuwe groep toevoegen

Als u toegang wilt tot een volledige groep, moet u het niveau van deelname aan de leden van de groep op de site bepalen:

- Beheer: de groep toevoegen aan de groep sitebeheerders toegang

- Actieve samenwerking: de groep toevoegen aan de groep toegang tot siteleden

- Weergave: de groep toevoegen aan de groep toegang tot sitebezoekers

Als u gebruikersaccounts en groepen beheert via Active Directory, voegt u de juiste groepen toe aan de juiste groepen met behulp van uw normale Active Directory-gebruikers-en groepsbeheer procedures en wacht op synchronisatie met uw abonnement.

Als u gebruikersaccounts en groepen beheert via Office 365, kunt u het Microsoft 365-Beheercentrum of PowerShell gebruiken:

- Voor het Microsoft 365-Beheercentrum, meldt u zich aan met een gebruikersaccount waaraan de rol van beheerder of beheerder van het bedrijf is toegewezen en groepen om de juiste groepen toe te voegen aan de juiste toegangsgroepen.

- Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell voor Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
 Gebruik de volgende PowerShell-opdrachten:

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>Een gebruiker verwijderen

Wanneer iemands toegang moet worden verwijderd van de site, verwijdert u deze uit de Access-groep waarvan ze momenteel lid zijn op basis van hun deelname aan de site:

- Beheer: Verwijder het gebruikersaccount uit de groep sitebeheerders toegang

- Actieve samenwerking: Verwijder het gebruikersaccount uit de groep toegang tot siteleden.

- Weergave: Verwijder het gebruikersaccount uit de groep sitebezoekers toegang

Als u gebruikersaccounts en groepen via Active Directory beheert, verwijdert u de juiste gebruikers uit de juiste toegangsgroepen met behulp van uw normale Active Directory-gebruikers-en groepsbeheer procedures en wacht op synchronisatie met uw abonnement.

Als u gebruikersaccounts en groepen beheert via Office 365, kunt u het Microsoft 365-Beheercentrum of PowerShell gebruiken:

- Voor het Microsoft 365-Beheercentrum, meldt u zich aan met een gebruikersaccount waaraan de rol van beheerder of beheerder van het bedrijf is toegewezen, en groepen waarmee u de juiste gebruikers uit de juiste toegangsgroepen kunt verwijderen.

- Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell voor Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
Als u een gebruikersaccount wilt verwijderen uit een Access-groep met de UPN, gebruikt u het volgende PowerShell-opdracht blok:

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Als u een gebruikersaccount wilt verwijderen uit een Access-groep met de weergavenaam, gebruikt u het volgende PowerShell-opdracht blok:

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a>Een groep verwijderen

Als u de toegang voor een hele groep wilt verwijderen, verwijdert u de groep van de Access-groep waarvan ze lid zijn op basis van hun deelname aan de site:

- Beheer: de groep verwijderen uit de groep sitebeheerders toegang

- Actieve samenwerking: de groep verwijderen uit de groep Siteleden toegang

- Weergeven: de groep verwijderen uit de groep sitebezoekers toegang

Als u gebruikersaccounts en groepen beheert via Windows Server Active Directory, verwijdert u de betreffende groepen uit de juiste toegangsgroepen met behulp van uw normale Active Directory-gebruikers-en groepsbeheer procedures en wacht op synchronisatie met uw abonnement.

Als u gebruikersaccounts en groepen beheert via Office 365, kunt u het Microsoft 365-Beheercentrum of PowerShell gebruiken:

- Voor het Microsoft 365-Beheercentrum, meldt u zich aan met een gebruikersaccount waaraan de rol van beheerder of beheerder van het bedrijf is toegewezen en groepen om de juiste groepen uit de juiste toegangsgroepen te verwijderen.

- Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell voor Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
Als u een groep wilt verwijderen uit een Access-groep met behulp van hun scherm namen, gebruikt u het volgende PowerShell-opdracht blok:

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>Een submap documenten maken met aangepaste machtigingen

In sommige gevallen moet een subset van de personen die werken in de geïsoleerde site een meer persoonlijke plaats hebben om samen te werken. Voor SharePoint Online-sites kunt u in de map documenten van de site een submap maken en aangepaste machtigingen toewijzen. Gebruikers zonder machtigingen krijgen de submap niet te zien.

Ga als volgt te werk om een submap van een document met aangepaste machtigingen te maken:

1. Meld u aan bij een account dat lid is van de groep beheerderstoegang voor de site. Zie [Waar kan ik me aanmelden in Microsoft 365?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.

2. Ga naar de geïsoleerde team site en klik op **documenten**.

3. Blader naar de map in de map documenten die de submap met aangepaste machtigingen bevat, maak de map en open deze.

4. Klik op **delen**.

5. Klik op **gedeeld met > Geavanceerd**.

6. Klik op **overname van machtigingen stoppen** en vervolgens op **OK**.

7. Klik op **delen**.

8. Klik op **gedeeld met > Geavanceerd**.

9. Klik op **machtigingen verlenen > gedeeld met > Geavanceerd**.

10. Klik op de pagina Machtigingen op **\<site name> leden in de lijst**.

11. Schakel op de pagina **\<site name> leden** het selectievakje in naast de groep Siteleden toegang, klik op **acties**, klik op **gebruikers uit groep verwijderen** en klik vervolgens op **OK**.

12. Als u specifieke leden aan deze submap wilt toevoegen, klikt u op **nieuw > gebruikers toevoegen**.

13. Typ in het dialoogvenster **delen** de namen van de gebruikersaccounts waarmee u kunt samenwerken aan bestanden in de submap en klik vervolgens op **delen**.

14. Vernieuw de webpagina om de nieuwe resultaten te bekijken.

15. Klik in het linkernavigatievenster onder **groepen** op de groep **\<site name> bezoekers** en gebruik stap 11-14 om de reeks gebruikersaccounts op te geven waarmee de bestanden in de submap kunnen worden weergegeven (indien nodig).

16. Klik in het linkernavigatievenster onder **groepen** op de groep **\<site name> eigenaren** en gebruik stappen 11-14 om de set gebruikersaccounts op te geven waarmee de machtigingen in de submap kunnen worden beheerd (indien nodig).

17. Sluit het tabblad **personen en groepen** in uw browser.

## <a name="see-also"></a>Zie ook

[Geïsoleerde SharePoint Online-teamsites](isolated-sharepoint-online-team-sites.md)

[Een geïsoleerde SharePoint Online-teamsite ontwerpen](design-an-isolated-sharepoint-online-team-site.md)

[Een geïsoleerde SharePoint Online-teamsite implementeren](deploy-an-isolated-sharepoint-online-team-site.md)
