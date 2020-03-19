---
title: Een geïsoleerde SharePoint Online-teamsite implementeren
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: 'Samenvatting: Implementeer een nieuwe geïsoleerde SharePoint Online-teamsite met deze stapsgewijze instructies.'
ms.openlocfilehash: 07867b4646926468f808f8f34086cf9267d7ab7b
ms.sourcegitcommit: 9afcc63b1a7e73f6946f67207337f10b71a5d7f3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/12/2020
ms.locfileid: "42809170"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a>Een geïsoleerde SharePoint Online-teamsite implementeren

 **Samenvatting:** Implementeer een nieuwe geïsoleerde SharePoint Online-teamsite met deze stapsgewijze instructies.
  
Dit artikel is een stapsgewijze implementatiehandleiding voor het maken en configureren van een geïsoleerde SharePoint Online-teamsite in Microsoft Office 365. In deze stappen wordt uitgegaan van het gebruik van de drie standaard SharePoint-groepen en de bijbehorende machtigingsniveaus, met één op Azure Active Directory (AD)gebaseerde toegangsgroep voor elk toegangsniveau.
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a>Fase 1: De toegangsgroepen voor de teamsite maken en invullen

In deze fase maakt u de drie Azure AD-gebaseerde toegangsgroepen voor de drie standaard SharePoint-groepen en vult u deze met de juiste gebruikersaccounts.
  
> [!NOTE]
> In de volgende stappen wordt ervan uitgegaan dat alle benodigde gebruikersaccounts al bestaan en de juiste licenties toegewezen krijgen. Zo niet, voeg ze toe en wijs licenties toe voordat u verdergaat naar stap 1. 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a>Stap 1: De SharePoint Online-beheerders voor de site weergeven

Bepaal de set gebruikersaccounts die overeenkomen met de SharePoint Online-beheerders voor de geïsoleerde teamsite.
  
Als u gebruikersaccounts en groepen beheert via Office 365 en Windows PowerShell wilt gebruiken, maakt u een lijst met de hoofdnamen (UPN's) van hun gebruikers (bijvoorbeeld UPN: belindan@contoso.com).
  
### <a name="step-2-list-the-members-for-the-site"></a>Stap 2: De leden voor de site opsommen

Bepaal de set gebruikersaccounts die overeenkomen met de leden voor de geïsoleerde teamsite, degenen die zullen samenwerken aan resources die op de site zijn opgeslagen.
  
Als u gebruikersaccounts en groepen beheert via Office 365 en PowerShell wilt gebruiken, maakt u een lijst met hun UPN's. Als er veel siteleden zijn, u de lijst met UPN's opslaan in een tekstbestand en ze allemaal toevoegen met één PowerShell-opdracht.
  
### <a name="step-3-list-the-viewers-for-the-site"></a>Stap 3: De kijkers voor de site weergeven

Bepaal de set gebruikersaccounts die overeenkomen met de kijkers van de geïsoleerde teamsite, degenen die de bronnen kunnen bekijken die op de site zijn opgeslagen, maar deze niet wijzigen of rechtstreeks samenwerken aan de inhoud ervan.
  
Als u gebruikersaccounts en groepen beheert via Office 365 en PowerShell wilt gebruiken, maakt u een lijst met hun UPN's. Als er veel siteleden zijn, u de lijst met UPN's opslaan in een tekstbestand en ze allemaal toevoegen met één PowerShell-opdracht.
  
Kijkers voor de site kunnen bestaan uit executive management, juridisch adviseur of belanghebbenden tussen afdelingen.
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a>Stap 4: De drie toegangsgroepen voor de site maken in Azure AD

U moet de volgende toegangsgroepen maken in Azure AD:
  
- Sitebeheerders (die de lijst uit stap 1 bevatten)
    
- Siteleden (die de lijst van stap 2 bevatten)
    
- Sitekijkers (die de lijst van stap 3 bevatten)
    
1. Ga in uw browser naar [https://portal.azure.com](https://portal.azure.com) de Azure-portal en meld u aan met de referenties van een account dat is toegewezen bij de rol User Management Admin of Company Administrator.
    
2. Klik in de Azure-portal op **Azure Active Directory > Groepen**.
    
3. Klik op het blad **groepen - Alle groepen** op + Nieuwe **groep**.
    
4. Op het **nieuwe groepsblad:**
    
    - Selecteer **Beveiliging** in **groepstype**.

    - Typ de groepsnaam in **Naam**.

    - Typ een beschrijving van de groep in **groepsbeschrijving**.

    - Selecteer **Toegewezen** in **het type lidmaatschap**.
    
5. Klik op **Maken**en sluit het **groepsblad.**
    
6. Herhaal stap 3-5 voor uw extra groepen.
    
> [!NOTE]
> U moet de Azure-portal gebruiken om de groepen te maken, zodat ze Office-functies hebben ingeschakeld. Als een geïsoleerde SharePoint Online-site later is geconfigureerd als een zeer vertrouwelijke site met een Azure Information Protection-label om bestanden te versleutelen en toestemming toe te wijzen aan specifieke groepen, moeten de toegestane groepen zijn gemaakt met Office-functies ingeschakeld. U de instelling Voor Office-functies van een Azure AD-groep niet wijzigen nadat deze is gemaakt. 
  
Hier is uw resulterende configuratie met de drie site toegangsgroepen.
  
![De drie toegangsgroepen voor uw implementatie van een geïsoleerde SharePoint Online-site.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a>Stap 5. De gebruikersaccounts toevoegen aan de toegangsgroepen

Ga in deze stap als volgt te werk:
  
1. De lijst met gebruikers van stap 1 toevoegen aan de toegangsgroep voor sitebeheerders
    
2. De lijst met gebruikers van stap 2 toevoegen aan de toegangsgroep van siteleden
    
3. De lijst met gebruikers van stap 3 toevoegen aan de groep toegang van sitekijkers
    
Als u gebruikersaccounts en groepen beheert via Active Directory Domain Services (AD DS), voegt u gebruikers toe aan de juiste toegangsgroepen met behulp van uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw Office 365-abonnement.
  
Als u gebruikersaccounts en groepen beheert via Office 365, u het Microsoft 365-beheercentrum of PowerShell gebruiken. Als u dubbele groepsnamen hebt voor een van de toegangsgroepen, moet u het Microsoft 365-beheercentrum gebruiken.
  
Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount waaraan de rol Gebruikersaccountbeheerder of Bedrijfsbeheerder is toegewezen en gebruik Groepen om de juiste gebruikersaccounts en groepen toe te voegen aan de juiste toegangsgroepen.
  
Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell for Graph-module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Gebruik vervolgens het volgende opdrachtblok om een individueel gebruikersaccount toe te voegen aan een toegangsgroep:
  
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```
Als u de UPN's van gebruikersaccounts hebt opgeslagen voor een van de toegangsgroepen in een tekstbestand, u het volgende Opdrachtblok PowerShell gebruiken om ze allemaal tegelijk toe te voegen:
  
```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

Gebruik voor PowerShell het volgende opdrachtblok om een afzonderlijke groep toe te voegen aan een toegangsgroep:
  
```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

De resultaten moeten de volgende zijn:
  
- De Azure AD-groep sitebeheerders bevat de gebruikersaccounts of -groepen voor sitebeheerder
    
- De Azure AD-groep van siteleden bevat de gebruikersaccounts of -groepen van het sitelid
    
- De sitekijkers Azure AD-groep bevat de gebruikersaccounts of -groepen die alleen de site-inhoud kunnen weergeven
    
Valideer de lijst met groepsleden voor elke toegangsgroep met het Microsoft 365-beheercentrum of met het volgende opdrachtblok PowerShell:
  
```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

Hier is uw resulterende configuratie met de drie sitetoegangsgroepen gevuld met gebruikersaccounts of groepen.
  
![De drie toegangsgroepen gevuld met gebruikersaccounts.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a>Fase 2: De geïsoleerde teamsite maken en configureren

In deze fase maakt u de geïsoleerde SharePoint Online-site en configureert u de machtigingen voor de standaardmachtigingsniveaus van SharePoint Online om uw nieuwe Azure AD-gebaseerde toegangsgroepen te gebruiken. Standaard bevatten nieuwe teamsites een Office 365-groep en andere gerelateerde bronnen, maar in dit geval maken we een teamsite zonder Office 365-groep. Hierdoor kunnen machtigingen volledig worden onderhouden via SharePoint.
  
Maak eerst de SharePoint Online-teamsite met deze stappen.
  
1. Meld u aan bij het Microsoft 365-beheercentrum met een account dat ook wordt gebruikt om de SharePoint Online-teamsite (een SharePoint Online-beheerder) te beheren. Zie Waar [u zich aanmelden bij Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. Klik in het Microsoft 365-beheercentrum onder **Beheercentra**op **SharePoint**.

3. Vouw in het SharePoint-beheercentrum **Sites** uit en klik op **Actieve sites**.

4. Klik op **Maken**en kies **vervolgens Andere opties**.

5. Kies **teamsite**in de lijst **Een sjabloon kiezen.**
   
6. Typ in **Sitenaam**een naam voor de teamsite. 
    
7. Typ in **primaire beheerder**het account waarmee u bent aangemeld.
 
8. Klik op **Voltooien**.
    
Configureer vervolgens vanaf de nieuwe SharePoint Online-teamsite machtigingen.
  
1. Klik op de **gereedschapsbalk**op het pictogram Instellingen en klik vervolgens op Sitemachtigingen .

2. Klik onder **Sitedelen**op **Wijzigen hoe leden kunnen delen**.

3. Kies de **enige site-eigenaren kunnen bestanden, mappen en de site delen.**

4. **Toegangsaanvragen toestaan** instellen op **Uit**.

5. Klik op **Opslaan**.
    
6. Klik in het deelvenster **Machtigingen** op **Instellingen voor Geavanceerde machtigingen**.
    
7. Klik op het tabblad **Machtigingen** van uw browser op ** \<sitenaam> leden** in de lijst.
    
8. Klik in **Personen en groepen**op **Nieuw**.
    
9. Typ in het dialoogvenster **Delen** de naam van de groep toegang van siteleden, selecteer deze en klik op **Delen**.
    
10. Klik op de terugknop in uw browser.
    
11. Klik op ** \<sitenaam> Eigenaren** in de lijst.
    
12. Klik in **Personen en groepen**op **Nieuw**.
    
13. Typ in het dialoogvenster **Delen** de naam van de toegangsgroep voor sitebeheerders, selecteer deze en klik op **Delen**.
    
14. Klik op de terugknop in uw browser.
    
15. Klik op ** \<sitenaam> bezoekers** in de lijst.
    
16. Klik in **Personen en groepen**op **Nieuw**.
    
17. Typ in het dialoogvenster **Delen** de naam van de groep toegang van de sitekijkers, selecteer deze en klik op **Delen**.
    
18. Sluit het tabblad **Machtigingen** van uw browser.
    
De resultaten van deze machtigingsinstellingen zijn:
  
- De ** \<sitenaam>** SharePoint-groep eigenaren bevat de toegangsgroep voor sitebeheerders, waarin alle leden het **machtigingsniveau Volledig beheer** hebben.
    
- De ** \<sitenaam> SharePoint-groep Leden** bevat de toegangsgroep voor siteleden, waarin alle leden het **machtigingsniveau Bewerken** hebben.
    
- De ** \<sitenaam>** SharePoint-groep Bezoekers bevat de groep toegang voor sitekijkers, waarin alle leden het **machtigingsniveau Lezen** hebben.
    
- De mogelijkheid voor leden om andere leden uit te nodigen of voor niet-leden om toegang aan te vragen, is uitgeschakeld.
    
Hier volgt de resulterende configuratie met de drie SharePoint-groepen voor de site die is geconfigureerd om de drie toegangsgroepen te gebruiken, die worden gevuld met gebruikersaccounts of Azure AD-groepen.
  
![De uiteindelijke configuratie van uw geïsoleerde SharePoint Online-site met toegangsgroepen en gebruikersaccounts.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
U en de leden van de site kunnen via groepslidmaatschap in een van de toegangsgroepen nu samenwerken met behulp van de bronnen van de site.
  
## <a name="next-step"></a>Volgende stap

Zie [Een geïsoleerde SharePoint Online-teamsite](manage-an-isolated-sharepoint-online-team-site.md)beheren als u het groepslidmaatschap van de sitetoegang moet wijzigen of een documentmap met aangepaste machtigingen moet maken.
  
## <a name="see-also"></a>Zie ook

[Geïsoleerde SharePoint Online-teamsites](isolated-sharepoint-online-team-sites.md)
  
[Een geïsoleerde SharePoint Online-teamsite ontwerpen](design-an-isolated-sharepoint-online-team-site.md)
  
[Een geïsoleerde SharePoint Online-teamsite beheren](manage-an-isolated-sharepoint-online-team-site.md)
  



