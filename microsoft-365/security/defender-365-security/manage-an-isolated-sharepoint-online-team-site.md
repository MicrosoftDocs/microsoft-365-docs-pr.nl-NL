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
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Beheer een geïsoleerde SharePoint Online-teamsite, voeg nieuwe gebruikers en groepen toe, verwijder gebruikers en groepen en maak een submap voor documenten met aangepaste machtigingen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 99b773547fa67068d75a79260af14010e456cb01
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059866"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>Een geïsoleerde SharePoint Online-teamsite beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- SharePoint Online 

 **Overzicht:** Beheer uw geïsoleerde SharePoint Online-teamsite met deze procedures.

In dit artikel worden algemene beheerbewerkingen beschreven voor een geïsoleerde SharePoint Online-teamsite.

## <a name="add-a-new-user"></a>Een nieuwe gebruiker toevoegen

Wanneer iemand nieuw lid wordt van de site, moet u het deelnameniveau van de site bepalen:

- Beheer: Het nieuwe gebruikersaccount toevoegen aan de toegangsgroep voor sitebeheerders

- Actieve samenwerking: Het gebruikersaccount toevoegen aan de toegangsgroep voor siteleden

- Weergeven: Het gebruikersaccount toevoegen aan de groep sitekijkers

Als u gebruikersaccounts en groepen beheert via Ad DS (Active Directory Domain Services), voegt u de juiste gebruikers toe aan de juiste toegangsgroepen met uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw abonnement.

Als u gebruikersaccounts en groepen beheert via Microsoft 365, kunt u het Microsoft 365-beheercentrum of Microsoft PowerShell gebruiken:

- Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount dat is toegewezen aan de rol Gebruikersaccountbeheerder of Bedrijfsbeheerder en gebruik Groepen om de juiste gebruikers toe te voegen aan de juiste toegangsgroepen.

- Voor PowerShell maakt u eerst [verbinding met de Azure Active Directory PowerShell voor Graph-module.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) Als u een gebruikersaccount wilt toevoegen aan een access-groep met de naam van de gebruikersnaam (UPN), gebruikt u het volgende PowerShell-opdrachtblok:

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Als u een gebruikersaccount wilt toevoegen aan een access-groep met de weergavenaam, gebruikt u het volgende PowerShell-opdrachtblok:

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>Een nieuwe groep toevoegen

Als u toegang wilt toevoegen aan een hele groep, moet u het deelnameniveau bepalen van alle leden van de groep op de site:

- Beheer: De groep toevoegen aan de toegangsgroep voor sitebeheerders

- Actieve samenwerking: De groep toevoegen aan de toegangsgroep voor siteleden

- Weergeven: De groep toevoegen aan de groep sitekijkers

Als u gebruikersaccounts en groepen beheert via AD DS, voegt u de juiste groepen toe aan de juiste groepen met uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw abonnement.

Als u gebruikersaccounts en groepen beheert via Office 365, kunt u het Microsoft 365-beheercentrum of PowerShell gebruiken:

- Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount dat is toegewezen aan de rol Gebruikersaccountbeheerder of Bedrijfsbeheerder en gebruik Groepen om de juiste groepen toe te voegen aan de juiste toegangsgroepen.

- Voor PowerShell maakt u eerst [verbinding met de Azure Active Directory PowerShell voor Graph-module.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
 Gebruik vervolgens de volgende PowerShell-opdrachten:

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>Een gebruiker verwijderen

Wanneer iemands toegang van de site moet worden verwijderd, verwijdert u deze uit de toegangsgroep waarvoor hij of zij momenteel lid is op basis van zijn of haar deelname aan de site:

- Beheer: Het gebruikersaccount verwijderen uit de toegangsgroep voor sitebeheerders

- Actieve samenwerking: Het gebruikersaccount verwijderen uit de toegangsgroep voor siteleden

- Weergeven: Het gebruikersaccount verwijderen uit de groep toegang van sitekijkers

Als u gebruikersaccounts en groepen beheert via AD DS, verwijdert u de juiste gebruikers uit de juiste toegangsgroepen met uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw abonnement.

Als u gebruikersaccounts en groepen beheert via Office 365, kunt u het Microsoft 365-beheercentrum of PowerShell gebruiken:

- Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount dat is toegewezen aan de rol Gebruikersaccountbeheerder of Bedrijfsbeheerder en gebruik Groepen om de juiste gebruikers uit de juiste toegangsgroepen te verwijderen.

- Voor PowerShell maakt u eerst [verbinding met de Azure Active Directory PowerShell voor Graph-module.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
Als u een gebruikersaccount wilt verwijderen uit een access-groep met de UPN, gebruikt u het volgende PowerShell-opdrachtblok:

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Als u een gebruikersaccount wilt verwijderen uit een access-groep met de weergavenaam, gebruikt u het volgende PowerShell-opdrachtblok:

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a>Een groep verwijderen

Als u de toegang voor een hele groep wilt verwijderen, verwijdert u de groep uit de toegangsgroep waarvan ze momenteel lid zijn op basis van hun deelname aan de site:

- Beheer: De groep verwijderen uit de toegangsgroep voor sitebeheerders

- Actieve samenwerking: De groep verwijderen uit de toegangsgroep voor siteleden

- Weergeven: De groep verwijderen uit de groep toegang van sitekijkers

Als u gebruikersaccounts en groepen beheert via Windows Server Active Directory, verwijdert u de juiste groepen uit de juiste toegangsgroepen met uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw abonnement.

Als u gebruikersaccounts en groepen beheert via Office 365, kunt u het Microsoft 365-beheercentrum of PowerShell gebruiken:

- Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount dat is toegewezen aan de rol Gebruikersaccountbeheerder of Bedrijfsbeheerder en gebruik Groepen om de juiste groepen uit de juiste toegangsgroepen te verwijderen.

- Voor PowerShell maakt u eerst [verbinding met de Azure Active Directory PowerShell voor Graph-module.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
Als u een groep wilt verwijderen uit een access-groep met de weergavenamen, gebruikt u het volgende PowerShell-opdrachtblok:

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>Een submap voor documenten maken met aangepaste machtigingen

In sommige gevallen moet een subset van de personen die op de geïsoleerde site werken, een meer privélocatie hebben om samen te werken. Voor SharePoint Online-sites kunt u een submap maken in de map Documenten van de site en aangepaste machtigingen toewijzen. Personen zonder machtigingen zien de submap niet.

Ga als volgt te werk om een submap voor documenten te maken met aangepaste machtigingen:

1. Meld u aan bij een account dat lid is van de groep beheerderstoegang voor de site. Zie [Waar kan ik me aanmelden in Microsoft 365?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.

2. Ga naar de geïsoleerde teamsite en klik op **Documenten.**

3. Blader naar de map in de map met documenten met de submap met aangepaste machtigingen, maak de map en open deze.

4. Klik **op Delen.**

5. Klik **op Gedeeld met > Geavanceerd.**

6. Klik **op Machtigingen stoppen en** klik vervolgens op **OK.**

7. Klik **op Delen.**

8. Klik **op Gedeeld met > Geavanceerd.**

9. Klik **op Machtigingen verlenen > gedeeld met > Geavanceerd.**

10. Klik op de pagina Machtigingen op **\<site name> Leden in de lijst**.

11. Selecteer op **\<site name> de** pagina Leden het vinkje naast de groep siteledentoegang, klik op **Acties,** klik op **Gebruikers** verwijderen uit groep en klik vervolgens op **OK.**

12. Als u specifieke leden wilt toevoegen aan deze submap, klikt u op **Nieuwe > Gebruikers toevoegen.**

13. Typ in **het** dialoogvenster Delen de namen van de gebruikersaccounts die kunnen samenwerken aan bestanden in de submap en klik vervolgens op **Delen.**

14. Vernieuw de webpagina om de nieuwe resultaten weer te geven.

15. Klik **onder** Groepen in het **\<site name>** linkernavigatievenster op de groep Bezoekers en gebruik stap 11-14 om de set gebruikersaccounts op te geven die de bestanden in de submap (zo nodig) kunnen weergeven.

16. Klik **onder** Groepen in het **\<site name>** linkernavigatievenster op de groep Eigenaren en gebruik stap 11-14 om de set gebruikersaccounts op te geven die de machtigingen in de submap (zo nodig) kunnen beheren.

17. Sluit het **tabblad Personen en groepen** in uw browser.

## <a name="see-also"></a>Zie ook

[Geïsoleerde SharePoint Online-teamsites](isolated-sharepoint-online-team-sites.md)

[Een team configureren met beveiligingsisolatie](/microsoft-365/solutions/secure-teams-security-isolation)
